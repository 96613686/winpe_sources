# RleCompress

- ea: `0x180002250`
- end: `0x180002414`
- name: `RleCompress`
- size: `452`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`

## callees

- `0x180002250`
- `0x18000241c`
- `0x180002954`
- `0x1800035d8`

## pseudocode

```c
__int64 __fastcall RleCompress(_DWORD *a1, __int64 a2)
{
  __int64 result; // rax
  __int64 *v5; // r14
  unsigned __int64 v6; // rcx
  unsigned __int64 v7; // r8
  int v8; // eax
  int v9; // edx
  unsigned int v10; // ecx
  unsigned int v11; // eax
  __int64 *v12; // rsi
  __int64 v13; // rcx
  int *v14; // rdx
  BOOL v15; // ebp
  int v16; // eax
  __int64 v17; // r10
  _DWORD *v18; // rcx
  _DWORD *v19; // rax

  if ( !a1 )
    return 4294967288LL;
  v5 = (__int64 *)(a2 + 24);
  if ( !a1[11] )
  {
    result = RleCompressBegin(a1, *v5, *(_QWORD *)(a2 + 8));
    if ( (_DWORD)result )
      return result;
    a1[11] = 0;
  }
  v6 = *(unsigned int *)(*v5 + 4) * (unsigned __int64)*(unsigned int *)(*v5 + 8);
  if ( v6 <= 0xFFFFFFFF )
  {
    v7 = 2LL * (unsigned int)v6;
    if ( v7 <= 0xFFFFFFFF )
    {
      v8 = *(_DWORD *)(a2 + 64);
      if ( v8 == -1 )
      {
        v8 = 8500;
        *(_DWORD *)(a2 + 64) = 8500;
      }
      v9 = *(_DWORD *)(a2 + 60);
      v10 = 10000 - v8;
      if ( v9 )
      {
        a1[6] = v9;
        v11 = *(_DWORD *)(a2 + 60);
        if ( v11 > 0x1F4 )
          a1[5] = v11 - 500;
        a1[9] = v10;
        v12 = (__int64 *)(a2 + 72);
        a1[7] = -1;
        a1[8] = v10 >> 3;
        CrunchDib(
          (__int64)a1,
          *(_DWORD **)(a2 + 8),
          *(_QWORD *)(a2 + 16),
          v7,
          *(_QWORD *)(a2 + 72),
          *(_QWORD *)(a2 + 80),
          *(unsigned int **)(a2 + 24),
          *(char **)(a2 + 32));
        v13 = *(_QWORD *)(a2 + 8);
        v14 = *(int **)(a2 + 40);
        v15 = *(_DWORD *)(v13 + 16) == 2019715428;
        if ( v14 )
        {
          v16 = 25444;
          if ( *(_DWORD *)(v13 + 16) == 2019715428 )
            v16 = 30820;
          *v14 = v16;
        }
        *(_DWORD *)(v13 + 16) = 1;
      }
      else
      {
        a1[8] = v10;
        v12 = (__int64 *)(a2 + 72);
        v15 = 0;
        a1[7] = v10 >> 3;
        v17 = *(_QWORD *)(a2 + 8);
        if ( (unsigned int)v7 <= *(_DWORD *)(v17 + 20) )
          RleDeltaFrame(
            v17,
            *(_QWORD *)(a2 + 16),
            v7,
            *v12,
            *(_QWORD *)(a2 + 80),
            *v5,
            *(_QWORD *)(a2 + 32),
            0,
            -1,
            v10 >> 3,
            v10,
            a1[10],
            4);
        v18 = *(_DWORD **)(a2 + 40);
        if ( v18 )
          *v18 = 25444;
      }
      v19 = *(_DWORD **)(a2 + 48);
      if ( v19 )
      {
        if ( *v12 || v15 )
          *v19 |= 2u;
        else
          *v19 |= 0x12u;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180002250  push    rbx
0x180002252  push    rbp
0x180002253  push    rsi
0x180002254  push    rdi
0x180002255  push    r14
0x180002257  sub     rsp, 70h
0x18000225b  mov     rbx, rdx
0x18000225e  mov     rdi, rcx
0x180002261  test    rcx, rcx
0x180002264  jnz     short loc_180002270
0x180002266  mov     eax, 0FFFFFFF8h
0x18000226b  jmp     loc_180002409
0x180002270  cmp     dword ptr [rcx+2Ch], 0
0x180002274  lea     r14, [rdx+18h]
0x180002278  jnz     short loc_180002291
0x18000227a  mov     r8, [rdx+8]
0x18000227e  mov     rdx, [r14]
0x180002281  call    RleCompressBegin
0x180002286  test    eax, eax
0x180002288  jnz     loc_180002409
0x18000228e  mov     [rdi+2Ch], eax
0x180002291  mov     rax, [r14]
0x180002294  mov     edx, 0FFFFFFFFh
0x180002299  mov     ecx, [rax+8]
0x18000229c  mov     eax, [rax+4]
0x18000229f  imul    rcx, rax
0x1800022a3  cmp     rcx, rdx
0x1800022a6  ja      loc_180002407
0x1800022ac  mov     r8d, ecx
0x1800022af  add     r8, r8
0x1800022b2  cmp     r8, rdx
0x1800022b5  ja      loc_180002407
0x1800022bb  mov     eax, [rbx+40h]
0x1800022be  cmp     eax, edx
0x1800022c0  jnz     short loc_1800022CA
0x1800022c2  mov     eax, 2134h
0x1800022c7  mov     [rbx+40h], eax
0x1800022ca  mov     edx, [rbx+3Ch]
0x1800022cd  mov     ecx, 2710h
0x1800022d2  sub     ecx, eax
0x1800022d4  test    edx, edx
0x1800022d6  jz      loc_180002376
0x1800022dc  mov     [rdi+18h], edx
0x1800022df  mov     eax, [rbx+3Ch]
0x1800022e2  cmp     eax, 1F4h
0x1800022e7  jbe     short loc_1800022F1
0x1800022e9  add     eax, 0FFFFFE0Ch
0x1800022ee  mov     [rdi+14h], eax
0x1800022f1  mov     [rdi+24h], ecx
0x1800022f4  lea     rsi, [rbx+48h]
0x1800022f8  mov     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x1800022ff  mov     r9d, r8d
0x180002302  shr     ecx, 3
0x180002305  mov     [rdi+20h], ecx
0x180002308  mov     rcx, rdi
0x18000230b  mov     rax, [rbx+20h]
0x18000230f  mov     r8, [rbx+10h]
0x180002313  mov     rdx, [rbx+8]
0x180002317  mov     [rsp+98h+var_60], rax
0x18000231c  mov     rax, [rbx+18h]
0x180002320  mov     [rsp+98h+var_68], rax
0x180002325  mov     rax, [rbx+50h]
0x180002329  mov     [rsp+98h+var_70], rax
0x18000232e  mov     rax, [rsi]
0x180002331  mov     [rsp+98h+var_78], rax
0x180002336  call    CrunchDib
0x18000233b  mov     rcx, [rbx+8]
0x18000233f  xor     ebp, ebp
0x180002341  mov     rdx, [rbx+28h]
0x180002345  mov     r9d, 78626964h
0x18000234b  cmp     [rcx+10h], r9d
0x18000234f  setz    bpl
0x180002353  test    rdx, rdx
0x180002356  jz      short loc_18000236D
0x180002358  cmp     [rcx+10h], r9d
0x18000235c  mov     eax, 6364h
0x180002361  mov     r8d, 7864h
0x180002367  cmovz   eax, r8d
0x18000236b  mov     [rdx], eax
0x18000236d  mov     dword ptr [rcx+10h], 1
0x180002374  jmp     short loc_1800023EC
0x180002376  mov     [rdi+20h], ecx
0x180002379  lea     rsi, [rbx+48h]
0x18000237d  mov     edx, ecx
0x18000237f  xor     ebp, ebp
0x180002381  shr     edx, 3
0x180002384  mov     [rdi+1Ch], edx
0x180002387  mov     r10, [rbx+8]
0x18000238b  cmp     r8d, [r10+14h]
0x18000238f  ja      short loc_1800023DD
0x180002391  mov     eax, [rdi+28h]
0x180002394  mov     r9, [rsi]
0x180002397  mov     [rsp+98h+var_38], 4
0x18000239f  mov     [rsp+98h+var_40], eax
0x1800023a3  mov     rax, [rbx+20h]
0x1800023a7  mov     [rsp+98h+var_48], ecx
0x1800023ab  mov     rcx, r10
0x1800023ae  mov     [rsp+98h+var_50], edx
0x1800023b2  mov     rdx, [rbx+10h]
0x1800023b6  mov     [rsp+98h+var_58], 0FFFFFFFFh
0x1800023be  mov     dword ptr [rsp+98h+var_60], ebp
0x1800023c2  mov     [rsp+98h+var_68], rax
0x1800023c7  mov     rax, [r14]
0x1800023ca  mov     [rsp+98h+var_70], rax
0x1800023cf  mov     rax, [rbx+50h]
0x1800023d3  mov     [rsp+98h+var_78], rax
0x1800023d8  call    RleDeltaFrame
0x1800023dd  mov     rcx, [rbx+28h]
0x1800023e1  test    rcx, rcx
0x1800023e4  jz      short loc_1800023EC
0x1800023e6  mov     dword ptr [rcx], 6364h
0x1800023ec  mov     rax, [rbx+30h]
0x1800023f0  test    rax, rax
0x1800023f3  jz      short loc_180002407
0x1800023f5  cmp     qword ptr [rsi], 0
0x1800023f9  jnz     short loc_180002404
0x1800023fb  test    ebp, ebp
0x1800023fd  jnz     short loc_180002404
0x1800023ff  or      dword ptr [rax], 12h
0x180002402  jmp     short loc_180002407
0x180002404  or      dword ptr [rax], 2
0x180002407  xor     eax, eax
0x180002409  add     rsp, 70h
0x18000240d  pop     r14
0x18000240f  pop     rdi
0x180002410  pop     rsi
0x180002411  pop     rbp
0x180002412  pop     rbx
0x180002413  retn
```
