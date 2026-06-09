# WriterGetCaps

- ea: `0x180013108`
- end: `0x1800133d1`
- name: `WriterGetCaps`
- size: `713`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18000d830`
- `0x18000fb14`

## callees

- `0x180007bd4`
- `0x180007d40`
- `0x1800127ec`
- `0x180012a2c`
- `0x180013108`
- `0x180019010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x1800133a1`
- `ole32!CoTaskMemFree` at `0x1800133b0`
- `ole32!CoTaskMemFree` at `0x1800133a1`
- `ole32!CoTaskMemFree` at `0x1800133b0`

## pseudocode

```c
__int64 __fastcall WriterGetCaps(__int64 a1, _BYTE *a2, unsigned int *a3, unsigned int *a4, _DWORD *a5)
{
  _BYTE *v5; // r10
  unsigned int v10; // edi
  int v11; // eax
  unsigned int v12; // ebx
  unsigned int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // ebx
  int v16; // eax
  __int64 v17; // r8
  int v18; // eax
  unsigned int v19; // r8d
  unsigned int v20; // edx
  bool v21; // zf
  _DWORD *v22; // rax
  _BYTE *v24; // [rsp+30h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-8h] BYREF
  int v26; // [rsp+70h] [rbp+30h] BYREF

  v5 = 0;
  v24 = 0;
  pv = 0;
  v26 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 10, &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids, *(_QWORD *)a1);
    v5 = v24;
  }
  if ( a1 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _BYTE **, int *))(**(_QWORD **)(a1 + 8) + 104LL))(
            *(_QWORD *)(a1 + 8),
            42,
            0,
            &v24,
            &v26);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v14 = 1000 * ((unsigned __int8)v24[19] | ((unsigned __int8)v24[18] << 8)) + 999;
      v15 = (v14 + 400 * (v14 / 0x2B110 + 1)) / 0x2B110;
      if ( v15 > 3 && (v15 & 1) != 0 )
        --v15;
      v16 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, int *))(**(_QWORD **)(a1 + 8) + 64LL))(
              *(_QWORD *)(a1 + 8),
              &pv,
              &v26);
      v10 = v16;
      if ( v16 >= 0 )
      {
        if ( *((_BYTE *)pv + 24) == 7 && v15 > 4 )
        {
          v18 = *((unsigned __int16 *)pv + 13);
          if ( (unsigned __int16)v18 < 2u )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
              WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 13, v17, 7, v18, v15);
            *(_DWORD *)(a1 + 16) |= 2u;
            v15 = 4;
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_DDD(*((_QWORD *)WPP_GLOBAL_Control + 7), 14, v17, 7, v18, v15);
          }
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            12,
            &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
            (unsigned int)v16);
        v10 = 0;
      }
      v5 = v24;
      *a3 = v15;
      v19 = 1000 * ((unsigned __int8)v5[21] | ((unsigned __int8)v5[20] << 8)) + 999;
      v20 = (v19 + 400 * (v19 / 0x2B110 + 1)) / 0x2B110;
      if ( v20 > 3 && (v20 & 1) != 0 )
        --v20;
      v21 = (v5[3] & 1) == 0;
      *a2 = v5[4] >> 7;
      v22 = a5;
      *a4 = v20;
      *v22 = 0;
      if ( !v21 )
        *v22 = 1;
      if ( (v5[3] & 2) != 0 )
        *v22 = 2;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          11,
          &WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids,
          (unsigned int)v11);
      v13 = TranslateIMAPI2Error(v12);
      v5 = v24;
      v10 = v13;
    }
  }
  else
  {
    v10 = -2147467261;
  }
  if ( v5 )
    CoTaskMemFree(v5);
  if ( pv )
    CoTaskMemFree(pv);
  return v10;
}

```

## disassembly

```asm
0x180013108  mov     [rsp-28h+arg_8], rbx
0x18001310d  mov     [rsp-28h+arg_10], rsi
0x180013112  push    rbp
0x180013113  push    rdi
0x180013114  push    r12
0x180013116  push    r14
0x180013118  push    r15
0x18001311a  mov     rbp, rsp
0x18001311d  sub     rsp, 40h
0x180013121  xor     r10d, r10d
0x180013124  mov     r14, r9
0x180013127  mov     [rbp+var_10], r10
0x18001312b  mov     r12, r8
0x18001312e  mov     [rbp+pv], r10
0x180013132  mov     r15, rdx
0x180013135  mov     [rbp+arg_0], r10d
0x180013139  mov     rsi, rcx
0x18001313c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013143  lea     rdi, WPP_GLOBAL_Control
0x18001314a  cmp     rcx, rdi
0x18001314d  jz      short loc_180013170
0x18001314f  test    byte ptr [rcx+44h], 1
0x180013153  jz      short loc_180013170
0x180013155  mov     r9, [rsi]
0x180013158  lea     edx, [r10+0Ah]
0x18001315c  mov     rcx, [rcx+38h]
0x180013160  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x180013167  call    WPP_SF_q
0x18001316c  mov     r10, [rbp+var_10]
0x180013170  test    rsi, rsi
0x180013173  jnz     short loc_18001317F
0x180013175  mov     edi, 80004003h
0x18001317a  jmp     loc_180013399
0x18001317f  mov     rcx, [rsi+8]
0x180013183  lea     rdx, [rbp+arg_0]
0x180013187  xor     r8d, r8d
0x18001318a  mov     [rsp+40h+var_20], rdx
0x18001318f  lea     r9, [rbp+var_10]
0x180013193  mov     rax, [rcx]
0x180013196  lea     edx, [r8+2Ah]
0x18001319a  mov     rax, [rax+68h]
0x18001319e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131a3  mov     ebx, eax
0x1800131a5  test    eax, eax
0x1800131a7  jns     short loc_1800131E5
0x1800131a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131b0  cmp     rcx, rdi
0x1800131b3  jz      short loc_1800131D3
0x1800131b5  test    byte ptr [rcx+44h], 1
0x1800131b9  jz      short loc_1800131D3
0x1800131bb  mov     rcx, [rcx+38h]
0x1800131bf  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x1800131c6  mov     edx, 0Bh
0x1800131cb  mov     r9d, eax
0x1800131ce  call    WPP_SF_d
0x1800131d3  mov     ecx, ebx
0x1800131d5  call    TranslateIMAPI2Error
0x1800131da  mov     r10, [rbp+var_10]
0x1800131de  mov     edi, eax
0x1800131e0  jmp     loc_180013399
0x1800131e5  mov     rax, [rbp+var_10]
0x1800131e9  mov     r9d, 0BE37C63Bh
0x1800131ef  movzx   ecx, byte ptr [rax+12h]
0x1800131f3  movzx   eax, byte ptr [rax+13h]
0x1800131f7  shl     ecx, 8
0x1800131fa  or      ecx, eax
0x1800131fc  mov     eax, r9d
0x1800131ff  imul    r8d, ecx, 3E8h
0x180013206  add     r8d, 3E7h
0x18001320d  mul     r8d
0x180013210  mov     eax, r9d
0x180013213  shr     edx, 11h
0x180013216  inc     edx
0x180013218  imul    ecx, edx, 190h
0x18001321e  add     ecx, r8d
0x180013221  mul     ecx
0x180013223  mov     ebx, edx
0x180013225  shr     ebx, 11h
0x180013228  cmp     ebx, 3
0x18001322b  jbe     short loc_180013234
0x18001322d  test    bl, 1
0x180013230  jz      short loc_180013234
0x180013232  dec     ebx
0x180013234  mov     rcx, [rsi+8]
0x180013238  lea     r8, [rbp+arg_0]
0x18001323c  lea     rdx, [rbp+pv]
0x180013240  mov     rax, [rcx]
0x180013243  mov     rax, [rax+40h]
0x180013247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001324c  mov     edi, eax
0x18001324e  mov     edx, 2
0x180013253  test    eax, eax
0x180013255  jns     short loc_18001328F
0x180013257  mov     rcx, cs:WPP_GLOBAL_Control
0x18001325e  lea     rdx, WPP_GLOBAL_Control
0x180013265  cmp     rcx, rdx
0x180013268  jz      short loc_180013288
0x18001326a  test    byte ptr [rcx+44h], 1
0x18001326e  jz      short loc_180013288
0x180013270  mov     rcx, [rcx+38h]
0x180013274  lea     r8, WPP_dc6944b0a17d382a152a5c74b8cf7000_Traceguids
0x18001327b  mov     edx, 0Ch
0x180013280  mov     r9d, eax
0x180013283  call    WPP_SF_d
0x180013288  xor     edi, edi
0x18001328a  jmp     loc_180013315
0x18001328f  mov     rcx, [rbp+pv]
0x180013293  mov     r9d, 7
0x180013299  cmp     [rcx+18h], r9b
0x18001329d  jnz     short loc_180013315
0x18001329f  cmp     ebx, 4
0x1800132a2  jbe     short loc_180013315
0x1800132a4  movzx   eax, word ptr [rcx+1Ah]
0x1800132a8  cmp     ax, dx
0x1800132ab  jb      short loc_1800132DD
0x1800132ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132b4  lea     rdx, WPP_GLOBAL_Control
0x1800132bb  cmp     rcx, rdx
0x1800132be  jz      short loc_180013315
0x1800132c0  test    byte ptr [rcx+44h], 1
0x1800132c4  jz      short loc_180013315
0x1800132c6  mov     rcx, [rcx+38h]
0x1800132ca  lea     edx, [r9+7]
0x1800132ce  mov     [rsp+40h+var_18], ebx
0x1800132d2  mov     dword ptr [rsp+40h+var_20], eax
0x1800132d6  call    WPP_SF_DDD
0x1800132db  jmp     short loc_180013315
0x1800132dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800132e4  lea     rdx, WPP_GLOBAL_Control
0x1800132eb  cmp     rcx, rdx
0x1800132ee  jz      short loc_18001330C
0x1800132f0  test    byte ptr [rcx+44h], 1
0x1800132f4  jz      short loc_18001330C
0x1800132f6  mov     rcx, [rcx+38h]
0x1800132fa  mov     edx, 0Dh
0x1800132ff  mov     [rsp+40h+var_18], ebx
0x180013303  mov     dword ptr [rsp+40h+var_20], eax
0x180013307  call    WPP_SF_DDD
0x18001330c  or      dword ptr [rsi+10h], 2
0x180013310  mov     ebx, 4
0x180013315  mov     r10, [rbp+var_10]
0x180013319  mov     r9d, 0BE37C63Bh
0x18001331f  mov     eax, r9d
0x180013322  mov     [r12], ebx
0x180013326  movzx   ecx, byte ptr [r10+15h]
0x18001332b  movzx   edx, byte ptr [r10+14h]
0x180013330  shl     edx, 8
0x180013333  or      edx, ecx
0x180013335  imul    r8d, edx, 3E8h
0x18001333c  add     r8d, 3E7h
0x180013343  mul     r8d
0x180013346  mov     eax, r9d
0x180013349  shr     edx, 11h
0x18001334c  inc     edx
0x18001334e  imul    ecx, edx, 190h
0x180013354  add     ecx, r8d
0x180013357  mul     ecx
0x180013359  shr     edx, 11h
0x18001335c  cmp     edx, 3
0x18001335f  jbe     short loc_180013368
0x180013361  test    dl, 1
0x180013364  jz      short loc_180013368
0x180013366  dec     edx
0x180013368  mov     al, [r10+4]
0x18001336c  shr     al, 7
0x18001336f  test    byte ptr [r10+3], 1
0x180013374  mov     [r15], al
0x180013377  mov     rax, [rbp+arg_20]
0x18001337b  mov     [r14], edx
0x18001337e  mov     dword ptr [rax], 0
0x180013384  jz      short loc_18001338C
0x180013386  mov     dword ptr [rax], 1
0x18001338c  test    byte ptr [r10+3], 2
0x180013391  jz      short loc_180013399
0x180013393  mov     dword ptr [rax], 2
0x180013399  test    r10, r10
0x18001339c  jz      short loc_1800133A7
0x18001339e  mov     rcx, r10; pv
0x1800133a1  call    cs:__imp_CoTaskMemFree
0x1800133a7  mov     rcx, [rbp+pv]; pv
0x1800133ab  test    rcx, rcx
0x1800133ae  jz      short loc_1800133B6
0x1800133b0  call    cs:__imp_CoTaskMemFree
0x1800133b6  lea     r11, [rsp+40h+var_s0]
0x1800133bb  mov     eax, edi
0x1800133bd  mov     rbx, [r11+38h]
0x1800133c1  mov     rsi, [r11+40h]
0x1800133c5  mov     rsp, r11
0x1800133c8  pop     r15
0x1800133ca  pop     r14
0x1800133cc  pop     r12
0x1800133ce  pop     rdi
0x1800133cf  pop     rbp
0x1800133d0  retn
```
