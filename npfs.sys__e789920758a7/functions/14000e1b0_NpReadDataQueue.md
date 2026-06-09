# NpReadDataQueue

- ea: `0x14000e1b0`
- end: `0x14000e420`
- name: `NpReadDataQueue`
- size: `624`
- prototype: `__int64 __fastcall(__int64, __int64, char, char, __int64, size_t Size, char, int, __int64, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x14000c800`
- `0x14000d8d0`
- `0x14000db40`
- `0x14000f400`

## callees

- `0x140001e40`
- `0x14000b054`
- `0x14000e1b0`
- `0x140010290`
- `0x140010310`
- `0x1400113b0`
- `0x140013e30`

## pseudocode

```c
__int64 __fastcall NpReadDataQueue(
        __int64 a1,
        __int64 a2,
        char a3,
        char a4,
        __int64 a5,
        size_t Size,
        char a7,
        int a8,
        __int64 a9,
        __int64 a10)
{
  char v12; // cl
  unsigned int v13; // r8d
  unsigned int v14; // r13d
  __int64 v15; // rdi
  __int64 NextRealDataQueueEntry; // rax
  __int64 v17; // rcx
  unsigned int v18; // r12d
  unsigned int v19; // r13d
  void *v20; // rdx
  void *v21; // rcx
  unsigned int v22; // r12d
  unsigned int v23; // eax
  unsigned int v24; // ecx
  __int64 v25; // rdx
  __int64 v26; // rax
  _QWORD *v27; // rcx
  _QWORD *v28; // rax
  char v30; // [rsp+20h] [rbp-58h]
  unsigned int v31; // [rsp+24h] [rbp-54h]
  unsigned int v32; // [rsp+28h] [rbp-50h]
  unsigned int v33; // [rsp+2Ch] [rbp-4Ch]
  char v34; // [rsp+90h] [rbp+18h]

  *(_DWORD *)(a1 + 4) = 0;
  v34 = 0;
  v12 = 1;
  if ( !a4 )
    v12 = a3;
  v30 = v12;
  v13 = Size;
  v31 = Size;
  *(_DWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v14 = 0;
  v32 = 0;
  if ( !v12 )
    goto LABEL_5;
  v15 = *(_QWORD *)a2;
  while ( v15 != a2 )
  {
    if ( !v12 || *(_DWORD *)(v15 + 32) <= 1u )
    {
      if ( *(_DWORD *)(v15 + 32) == 1 )
        v17 = *(_QWORD *)(*(_QWORD *)(v15 + 16) + 24LL);
      else
        v17 = v15 + 48;
      v33 = *(_DWORD *)(v15 + 40);
      v18 = v33;
      if ( v15 == *(_QWORD *)a2 )
        v18 = v33 - *(_DWORD *)(a2 + 36);
      v19 = v18;
      if ( v18 >= v13 )
        v19 = v13;
      v20 = (void *)(v17 + *(_DWORD *)(v15 + 40) - v18);
      v21 = (void *)((unsigned int)Size - v13 + a5);
      if ( a7 )
        RtlCopyToUser(v21, v20, v19);
      else
        RtlCopyVolatileMemory(v21, v20, v19);
      v31 -= v19;
      v22 = v18 - v19;
      v32 += v19;
      if ( !v30 )
      {
        v23 = *(_DWORD *)(v15 + 36);
        v24 = v23;
        if ( v23 > v19 )
          v24 = v19;
        *(_DWORD *)(v15 + 36) = v23 - v24;
        *(_DWORD *)(a2 + 32) -= v24;
        *(_DWORD *)(a2 + 36) += v19;
        v34 = 1;
      }
      NpCopyClientContext(a9, *(_QWORD *)(v15 + 24));
      *(_QWORD *)(v15 + 24) = 0;
      v14 = v32;
      if ( v22 || a4 && !v32 )
      {
        if ( a8 == 1 )
        {
          *(_DWORD *)a1 = -2147483643;
          break;
        }
        v12 = v30;
      }
      else
      {
        v12 = v30;
        if ( !v30 || a4 )
        {
          if ( a4 )
            NpGetNextRealDataQueueEntry(a2, a10);
          LOBYTE(v25) = 1;
          v26 = NpRemoveDataQueueEntry(a2, v25, a10);
          if ( v26 )
          {
            *(_QWORD *)(v26 + 56) = v33;
            *(_DWORD *)(v26 + 48) = 0;
            v27 = *(_QWORD **)(a10 + 8);
            if ( *v27 != a10 )
              __fastfail(3u);
            v28 = (_QWORD *)(v26 + 168);
            *v28 = a10;
            v28[1] = v27;
            *v27 = v28;
            *(_QWORD *)(a10 + 8) = v28;
          }
          v12 = v30;
        }
        if ( a8 == 1 )
        {
          *(_DWORD *)a1 = 0;
          break;
        }
      }
      v13 = v31;
    }
    if ( !v13 )
      break;
    if ( v12 )
    {
      v15 = *(_QWORD *)v15;
    }
    else
    {
LABEL_5:
      NextRealDataQueueEntry = NpGetNextRealDataQueueEntry(a2, a10);
      v13 = v31;
      v12 = v30;
      v15 = NextRealDataQueueEntry;
    }
  }
  *(_QWORD *)(a1 + 8) = v14;
  if ( v34 )
    NpCompleteStalledWrites(a2, a10);
  return a1;
}

```

## disassembly

```asm
0x14000e1b0  mov     [rsp+arg_18], r9b
0x14000e1b5  mov     [rsp+arg_8], rdx
0x14000e1ba  mov     [rsp+arg_0], rcx
0x14000e1bf  push    rsi
0x14000e1c0  push    rdi
0x14000e1c1  push    r12
0x14000e1c3  push    r13
0x14000e1c5  push    r14
0x14000e1c7  push    r15
0x14000e1c9  sub     rsp, 48h
0x14000e1cd  mov     r14, rdx
0x14000e1d0  mov     rsi, rcx
0x14000e1d3  mov     dword ptr [rcx+4], 0
0x14000e1da  mov     [rsp+78h+arg_10], 0
0x14000e1e2  mov     ecx, 1
0x14000e1e7  movzx   eax, r8b
0x14000e1eb  test    r9b, r9b
0x14000e1ee  cmovz   ecx, eax
0x14000e1f1  mov     [rsp+78h+var_58], ecx
0x14000e1f5  mov     r8d, dword ptr [rsp+78h+Size]
0x14000e1fd  mov     [rsp+78h+var_54], r8d
0x14000e202  mov     dword ptr [rsi], 0
0x14000e208  mov     qword ptr [rsi+8], 0
0x14000e210  xor     r13d, r13d
0x14000e213  mov     [rsp+78h+var_50], r13d
0x14000e218  mov     r15, [rsp+78h+arg_48]
0x14000e220  test    cl, cl
0x14000e222  jz      short loc_14000E229
0x14000e224  mov     rdi, [rdx]
0x14000e227  jmp     short loc_14000E240
0x14000e229  mov     rdx, r15
0x14000e22c  mov     rcx, r14
0x14000e22f  call    NpGetNextRealDataQueueEntry
0x14000e234  mov     r8d, [rsp+78h+var_54]
0x14000e239  mov     ecx, [rsp+78h+var_58]
0x14000e23d  mov     rdi, rax
0x14000e240  cmp     rdi, r14
0x14000e243  jz      loc_14000E3F1
0x14000e249  test    cl, cl
0x14000e24b  jz      short loc_14000E257
0x14000e24d  cmp     dword ptr [rdi+20h], 1
0x14000e251  ja      loc_14000E3C0
0x14000e257  cmp     dword ptr [rdi+20h], 1
0x14000e25b  jnz     short loc_14000E267
0x14000e25d  mov     rax, [rdi+10h]
0x14000e261  mov     rcx, [rax+18h]
0x14000e265  jmp     short loc_14000E26B
0x14000e267  lea     rcx, [rdi+30h]
0x14000e26b  mov     eax, [rdi+28h]
0x14000e26e  mov     [rsp+78h+var_4C], eax
0x14000e272  mov     r12d, eax
0x14000e275  cmp     rdi, [r14]
0x14000e278  jnz     short loc_14000E27E
0x14000e27a  sub     r12d, [r14+24h]
0x14000e27e  mov     r13d, r12d
0x14000e281  cmp     r12d, r8d
0x14000e284  cmovnb  r13d, r8d
0x14000e288  sub     eax, r12d
0x14000e28b  mov     edx, eax
0x14000e28d  add     rdx, rcx; Src
0x14000e290  mov     eax, dword ptr [rsp+78h+Size]
0x14000e297  sub     eax, r8d
0x14000e29a  mov     rcx, [rsp+78h+arg_20]
0x14000e2a2  add     rcx, rax; void *
0x14000e2a5  mov     r8d, r13d; Size
0x14000e2a8  cmp     [rsp+78h+arg_30], 0
0x14000e2b0  jz      short loc_14000E2B9
0x14000e2b2  call    RtlCopyToUser
0x14000e2b7  jmp     short loc_14000E2BF
0x14000e2b9  call    RtlCopyVolatileMemory
0x14000e2be  nop
0x14000e2bf  sub     [rsp+78h+var_54], r13d
0x14000e2c4  sub     r12d, r13d
0x14000e2c7  add     [rsp+78h+var_50], r13d
0x14000e2cc  cmp     byte ptr [rsp+78h+var_58], 0
0x14000e2d1  jnz     short loc_14000E2F4
0x14000e2d3  mov     eax, [rdi+24h]
0x14000e2d6  mov     ecx, eax
0x14000e2d8  cmp     eax, r13d
0x14000e2db  cmova   ecx, r13d
0x14000e2df  sub     eax, ecx
0x14000e2e1  mov     [rdi+24h], eax
0x14000e2e4  sub     [r14+20h], ecx
0x14000e2e8  add     [r14+24h], r13d
0x14000e2ec  mov     [rsp+78h+arg_10], 1
0x14000e2f4  mov     rdx, [rdi+18h]
0x14000e2f8  mov     rcx, [rsp+78h+arg_40]
0x14000e300  call    NpCopyClientContext
0x14000e305  mov     qword ptr [rdi+18h], 0
0x14000e30d  mov     r13d, [rsp+78h+var_50]
0x14000e312  test    r12d, r12d
0x14000e315  jnz     loc_14000E3A5
0x14000e31b  mov     r12b, [rsp+78h+arg_18]
0x14000e323  test    r12b, r12b
0x14000e326  jz      short loc_14000E32D
0x14000e328  test    r13d, r13d
0x14000e32b  jz      short loc_14000E3A5
0x14000e32d  mov     ecx, [rsp+78h+var_58]
0x14000e331  test    cl, cl
0x14000e333  jz      short loc_14000E33A
0x14000e335  test    r12b, r12b
0x14000e338  jz      short loc_14000E393
0x14000e33a  test    r12b, r12b
0x14000e33d  jz      short loc_14000E34A
0x14000e33f  mov     rdx, r15
0x14000e342  mov     rcx, r14
0x14000e345  call    NpGetNextRealDataQueueEntry
0x14000e34a  mov     r8, r15
0x14000e34d  mov     dl, 1
0x14000e34f  mov     rcx, r14
0x14000e352  call    NpRemoveDataQueueEntry
0x14000e357  test    rax, rax
0x14000e35a  jz      short loc_14000E38F
0x14000e35c  mov     ecx, [rsp+78h+var_4C]
0x14000e360  mov     [rax+38h], rcx
0x14000e364  mov     dword ptr [rax+30h], 0
0x14000e36b  mov     rcx, [r15+8]
0x14000e36f  cmp     [rcx], r15
0x14000e372  jz      short loc_14000E37B
0x14000e374  mov     ecx, 3
0x14000e379  int     29h; Win8: RtlFailFast(ecx)
0x14000e37b  add     rax, 0A8h
0x14000e381  mov     [rax], r15
0x14000e384  mov     [rax+8], rcx
0x14000e388  mov     [rcx], rax
0x14000e38b  mov     [r15+8], rax
0x14000e38f  mov     ecx, [rsp+78h+var_58]
0x14000e393  cmp     [rsp+78h+arg_38], 1
0x14000e39b  jnz     short loc_14000E3BB
0x14000e39d  mov     dword ptr [rsi], 0
0x14000e3a3  jmp     short loc_14000E3F1
0x14000e3a5  cmp     [rsp+78h+arg_38], 1
0x14000e3ad  jnz     short loc_14000E3B7
0x14000e3af  mov     dword ptr [rsi], 80000005h
0x14000e3b5  jmp     short loc_14000E3F1
0x14000e3b7  mov     ecx, [rsp+78h+var_58]
0x14000e3bb  mov     r8d, [rsp+78h+var_54]
0x14000e3c0  test    r8d, r8d
0x14000e3c3  jz      short loc_14000E3F1
0x14000e3c5  test    cl, cl
0x14000e3c7  jz      loc_14000E229
0x14000e3cd  mov     rdi, [rdi]
0x14000e3d0  jmp     loc_14000E240
0x14000e3d5  mov     rsi, [rsp+78h+arg_0]
0x14000e3dd  mov     [rsi], eax
0x14000e3df  mov     r15, [rsp+78h+arg_48]
0x14000e3e7  mov     r14, [rsp+78h+arg_8]
0x14000e3ef  jmp     short loc_14000E3F8
0x14000e3f1  mov     eax, r13d
0x14000e3f4  mov     [rsi+8], rax
0x14000e3f8  cmp     [rsp+78h+arg_10], 0
0x14000e400  jz      short loc_14000E40D
0x14000e402  mov     rdx, r15
0x14000e405  mov     rcx, r14
0x14000e408  call    NpCompleteStalledWrites
0x14000e40d  mov     rax, rsi
0x14000e410  add     rsp, 48h
0x14000e414  pop     r15
0x14000e416  pop     r14
0x14000e418  pop     r13
0x14000e41a  pop     r12
0x14000e41c  pop     rdi
0x14000e41d  pop     rsi
0x14000e41e  retn
0x140016653  push    rbp
0x140016655  sub     rsp, 20h
0x140016659  mov     rbp, rdx
0x14001665c  xor     eax, eax
0x14001665e  cmp     [rbp+0B0h], al
0x140016664  setnz   al
0x140016667  mov     [rbp+30h], eax
0x14001666a  mov     eax, [rbp+30h]
0x14001666d  add     rsp, 20h
0x140016671  pop     rbp
0x140016672  retn
```
