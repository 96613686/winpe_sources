# CLocationWriter::Sort(ulong *)

- ea: `0x18002e8ec`
- end: `0x18002eb75`
- name: `?Sort@CLocationWriter@@AEAAJPEAK@Z`
- size: `649`
- prototype: `__int64 __fastcall(CLocationWriter *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006204`

## callees

- `0x1800089c8`
- `0x180008a08`
- `0x18002e8ec`
- `0x18003099a`
- `0x1800309d0`
- `0x180031010`

## import_xrefs

- `msvcrt!qsort` at `0x18002eaab`
- `msvcrt!qsort` at `0x18002eaca`
- `msvcrt!qsort` at `0x18002eaab`
- `msvcrt!qsort` at `0x18002eaca`

## pseudocode

```c
__int64 __fastcall CLocationWriter::Sort(CLocationWriter *this, unsigned int *a2)
{
  unsigned int v3; // ebx
  __int64 *v4; // r14
  __int64 *v5; // rsi
  unsigned int v6; // r12d
  unsigned int v7; // r13d
  unsigned int i; // r15d
  int v9; // eax
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rcx
  unsigned int *v14; // r9
  unsigned int v15; // r8d
  __int64 j; // rdx
  unsigned int k; // edx
  __int64 v18; // rax
  __int64 v19; // rcx
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v22; // [rsp+48h] [rbp-B8h]
  _QWORD v23[8]; // [rsp+50h] [rbp-B0h] BYREF
  _DWORD *v24; // [rsp+90h] [rbp-70h]
  __int64 v25; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v26[248]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v27; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v28[248]; // [rsp+1A8h] [rbp+A8h] BYREF

  v22 = a2;
  v27 = 0;
  v3 = -2147024882;
  memset_0(v28, 0, sizeof(v28));
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  if ( *((_DWORD *)this + 12) <= 0x10u )
  {
    v4 = &v25;
  }
  else
  {
    v4 = (__int64 *)operator new(saturated_mul(*((unsigned int *)this + 12), 0x10u));
    if ( !v4 )
      return v3;
  }
  if ( *((_DWORD *)this + 13) <= 0x10u )
  {
    v5 = &v27;
    goto LABEL_9;
  }
  v5 = (__int64 *)operator new(saturated_mul(*((unsigned int *)this + 13), 0x10u));
  if ( v5 )
  {
LABEL_9:
    v6 = 0;
    v7 = 0;
    for ( i = 0; ; ++i )
    {
      v21 = 8;
      memset_0(v23, 0, 0x48u);
      v9 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, __int64 *, _QWORD, _QWORD, _QWORD *))(**(_QWORD **)(*((_QWORD *)this + 3) + 65608LL) + 96LL))(
             *(_QWORD *)(*((_QWORD *)this + 3) + 65608LL),
             i,
             2,
             &v21,
             0,
             0,
             v23);
      v3 = v9;
      if ( v9 == -2145318890 )
        break;
      if ( v9 < 0 )
        goto LABEL_29;
      if ( *v24 == 66 || !*v24 )
      {
        if ( v6 >= *((_DWORD *)this + 12) )
        {
LABEL_19:
          v3 = -2147024872;
          goto LABEL_29;
        }
        v12 = v23[0];
        v13 = 2LL * v6++;
        LODWORD(v4[v13 + 1]) = i;
        v4[v13] = v12;
      }
      else
      {
        if ( v7 >= *((_DWORD *)this + 13) )
          goto LABEL_19;
        v10 = v23[0];
        v11 = 2LL * v7++;
        LODWORD(v5[v11 + 1]) = i;
        v5[v11] = v10;
      }
    }
    if ( *((_DWORD *)this + 12) )
      qsort(v4, *((unsigned int *)this + 12), 0x10u, MyCompare);
    if ( *((_DWORD *)this + 13) )
      qsort(v5, *((unsigned int *)this + 13), 0x10u, MyCompare);
    v14 = v22;
    v15 = 0;
    for ( j = 0; (unsigned int)j < *((_DWORD *)this + 13); v15 = j )
    {
      v14[j] = v5[2 * (unsigned int)j + 1];
      j = (unsigned int)(j + 1);
    }
    for ( k = 0; k < *((_DWORD *)this + 12); v14[v19] = v4[2 * v18 + 1] )
    {
      v18 = k++;
      v19 = v15++;
    }
    v3 = 0;
  }
LABEL_29:
  if ( v4 && &v25 != v4 )
    operator delete(v4);
  if ( v5 && &v27 != v5 )
    operator delete(v5);
  return v3;
}

```

## disassembly

```asm
0x18002e8ec  mov     [rsp-8+arg_10], rbx
0x18002e8f1  push    rbp
0x18002e8f2  push    rsi
0x18002e8f3  push    rdi
0x18002e8f4  push    r12
0x18002e8f6  push    r13
0x18002e8f8  push    r14
0x18002e8fa  push    r15
0x18002e8fc  lea     rbp, [rsp-1B0h]
0x18002e904  sub     rsp, 2B0h
0x18002e90b  mov     rax, cs:__security_cookie
0x18002e912  xor     rax, rsp
0x18002e915  mov     [rbp+1E0h+var_40], rax
0x18002e91c  mov     [rsp+2E0h+var_298], rdx
0x18002e921  mov     rdi, rcx
0x18002e924  mov     esi, 0F8h
0x18002e929  mov     [rbp+1E0h+var_140], 0
0x18002e934  mov     r8d, esi; Size
0x18002e937  lea     rcx, [rbp+1E0h+var_138]; void *
0x18002e93e  xor     edx, edx; Val
0x18002e940  mov     ebx, 8007000Eh
0x18002e945  call    memset_0
0x18002e94a  mov     r8d, esi; Size
0x18002e94d  mov     [rbp+1E0h+var_240], 0
0x18002e955  xor     edx, edx; Val
0x18002e957  lea     rcx, [rbp+1E0h+var_238]; void *
0x18002e95b  call    memset_0
0x18002e960  or      r15, 0FFFFFFFFFFFFFFFFh
0x18002e964  lea     esi, [r15+11h]
0x18002e968  cmp     [rdi+30h], esi
0x18002e96b  jbe     short loc_18002E98F
0x18002e96d  mov     ecx, [rdi+30h]
0x18002e970  mov     eax, esi
0x18002e972  mul     rcx
0x18002e975  cmovb   rax, r15
0x18002e979  mov     rcx, rax; Size
0x18002e97c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e981  mov     r14, rax
0x18002e984  test    rax, rax
0x18002e987  jz      loc_18002EB49
0x18002e98d  jmp     short loc_18002E993
0x18002e98f  lea     r14, [rbp+1E0h+var_240]
0x18002e993  cmp     [rdi+34h], esi
0x18002e996  jbe     short loc_18002E9BB
0x18002e998  mov     ecx, [rdi+34h]
0x18002e99b  mov     rax, rsi
0x18002e99e  mul     rcx
0x18002e9a1  cmovb   rax, r15
0x18002e9a5  mov     rcx, rax; Size
0x18002e9a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002e9ad  mov     rsi, rax
0x18002e9b0  test    rax, rax
0x18002e9b3  jz      loc_18002EB1A
0x18002e9b9  jmp     short loc_18002E9C2
0x18002e9bb  lea     rsi, [rbp+1E0h+var_140]
0x18002e9c2  xor     r12d, r12d
0x18002e9c5  xor     r13d, r13d
0x18002e9c8  xor     r15d, r15d
0x18002e9cb  xor     edx, edx; Val
0x18002e9cd  mov     [rsp+2E0h+var_2A0], 8
0x18002e9d6  lea     rcx, [rsp+2E0h+var_290]; void *
0x18002e9db  lea     r8d, [rdx+48h]; Size
0x18002e9df  call    memset_0
0x18002e9e4  mov     rax, [rdi+18h]
0x18002e9e8  lea     rdx, [rsp+2E0h+var_290]
0x18002e9ed  mov     [rsp+2E0h+var_2B0], rdx
0x18002e9f2  lea     r9, [rsp+2E0h+var_2A0]
0x18002e9f7  mov     [rsp+2E0h+var_2B8], 0
0x18002ea00  mov     r8d, 2
0x18002ea06  mov     edx, r15d
0x18002ea09  mov     [rsp+2E0h+var_2C0], 0
0x18002ea12  mov     rcx, [rax+10048h]
0x18002ea19  mov     rax, [rcx]
0x18002ea1c  mov     rax, [rax+60h]
0x18002ea20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea25  mov     ebx, eax
0x18002ea27  cmp     eax, 80210816h
0x18002ea2c  jz      short loc_18002EA92
0x18002ea2e  test    eax, eax
0x18002ea30  js      loc_18002EB1A
0x18002ea36  mov     rax, [rbp+1E0h+var_250]
0x18002ea3a  cmp     dword ptr [rax], 42h ; 'B'
0x18002ea3d  jz      short loc_18002EA63
0x18002ea3f  cmp     dword ptr [rax], 0
0x18002ea42  jz      short loc_18002EA63
0x18002ea44  cmp     r13d, [rdi+34h]
0x18002ea48  jnb     short loc_18002EA88
0x18002ea4a  mov     rax, [rsp+2E0h+var_290]
0x18002ea4f  mov     ecx, r13d
0x18002ea52  add     rcx, rcx
0x18002ea55  inc     r13d
0x18002ea58  mov     [rsi+rcx*8+8], r15d
0x18002ea5d  mov     [rsi+rcx*8], rax
0x18002ea61  jmp     short loc_18002EA80
0x18002ea63  cmp     r12d, [rdi+30h]
0x18002ea67  jnb     short loc_18002EA88
0x18002ea69  mov     rax, [rsp+2E0h+var_290]
0x18002ea6e  mov     ecx, r12d
0x18002ea71  add     rcx, rcx
0x18002ea74  inc     r12d
0x18002ea77  mov     [r14+rcx*8+8], r15d
0x18002ea7c  mov     [r14+rcx*8], rax
0x18002ea80  inc     r15d
0x18002ea83  jmp     loc_18002E9CB
0x18002ea88  mov     ebx, 80070018h
0x18002ea8d  jmp     loc_18002EB1A
0x18002ea92  cmp     dword ptr [rdi+30h], 0
0x18002ea96  jbe     short loc_18002EAB1
0x18002ea98  mov     edx, [rdi+30h]; NumOfElements
0x18002ea9b  lea     r9, ?MyCompare@@YAHPEBX0@Z; CompareFunction
0x18002eaa2  mov     r8d, 10h; SizeOfElements
0x18002eaa8  mov     rcx, r14; Base
0x18002eaab  call    cs:__imp_qsort
0x18002eab1  cmp     dword ptr [rdi+34h], 0
0x18002eab5  jbe     short loc_18002EAD0
0x18002eab7  mov     edx, [rdi+34h]; NumOfElements
0x18002eaba  lea     r9, ?MyCompare@@YAHPEBX0@Z; CompareFunction
0x18002eac1  mov     r8d, 10h; SizeOfElements
0x18002eac7  mov     rcx, rsi; Base
0x18002eaca  call    cs:__imp_qsort
0x18002ead0  mov     r9, [rsp+2E0h+var_298]
0x18002ead5  xor     r8d, r8d
0x18002ead8  xor     edx, edx
0x18002eada  cmp     [rdi+34h], edx
0x18002eadd  jbe     short loc_18002EAF6
0x18002eadf  mov     eax, edx
0x18002eae1  add     rax, rax
0x18002eae4  mov     eax, [rsi+rax*8+8]
0x18002eae8  mov     [r9+rdx*4], eax
0x18002eaec  inc     edx
0x18002eaee  mov     r8d, edx
0x18002eaf1  cmp     edx, [rdi+34h]
0x18002eaf4  jb      short loc_18002EADF
0x18002eaf6  xor     edx, edx
0x18002eaf8  cmp     [rdi+30h], edx
0x18002eafb  jbe     short loc_18002EB18
0x18002eafd  mov     eax, edx
0x18002eaff  inc     edx
0x18002eb01  add     rax, rax
0x18002eb04  mov     ecx, r8d
0x18002eb07  inc     r8d
0x18002eb0a  mov     eax, [r14+rax*8+8]
0x18002eb0f  mov     [r9+rcx*4], eax
0x18002eb13  cmp     edx, [rdi+30h]
0x18002eb16  jb      short loc_18002EAFD
0x18002eb18  xor     ebx, ebx
0x18002eb1a  test    r14, r14
0x18002eb1d  jz      short loc_18002EB30
0x18002eb1f  lea     rax, [rbp+1E0h+var_240]
0x18002eb23  cmp     rax, r14
0x18002eb26  jz      short loc_18002EB30
0x18002eb28  mov     rcx, r14; Block
0x18002eb2b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002eb30  test    rsi, rsi
0x18002eb33  jz      short loc_18002EB49
0x18002eb35  lea     rax, [rbp+1E0h+var_140]
0x18002eb3c  cmp     rax, rsi
0x18002eb3f  jz      short loc_18002EB49
0x18002eb41  mov     rcx, rsi; Block
0x18002eb44  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002eb49  mov     eax, ebx
0x18002eb4b  mov     rcx, [rbp+1E0h+var_40]
0x18002eb52  xor     rcx, rsp; StackCookie
0x18002eb55  call    __security_check_cookie
0x18002eb5a  mov     rbx, [rsp+2E0h+arg_10]
0x18002eb62  add     rsp, 2B0h
0x18002eb69  pop     r15
0x18002eb6b  pop     r14
0x18002eb6d  pop     r13
0x18002eb6f  pop     r12
0x18002eb71  pop     rdi
0x18002eb72  pop     rsi
0x18002eb73  pop     rbp
0x18002eb74  retn
```
