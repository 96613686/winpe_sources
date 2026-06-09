# RetrieveFullPath(CADMCOMW *,ulong,ushort const *,STRU *)

- ea: `0x18000f30c`
- end: `0x18000f460`
- name: `?RetrieveFullPath@@YAJPEAVCADMCOMW@@KPEBGPEAVSTRU@@@Z`
- size: `340`
- prototype: `__int64 __fastcall(struct CADMCOMW *, unsigned int, const unsigned __int16 *, struct STRU *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000238c`
- `0x18000f468`

## callees

- `0x180007068`
- `0x18000be20`
- `0x18000f30c`

## import_xrefs

- `msvcrt!wcschr` at `0x18000f404`
- `msvcrt!wcschr` at `0x18000f404`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f3bb`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f3e8`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f3bb`
- `IisRTL!?Append@STRU@@QEAAJPEBG@Z` at `0x18000f3e8`
- `IisRTL!?SetLen@STRU@@QEAA_NK@Z` at `0x18000f429`
- `IisRTL!?SetLen@STRU@@QEAA_NK@Z` at `0x18000f429`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f398`
- `IisRTL!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000f398`

## pseudocode

```c
__int64 __fastcall RetrieveFullPath(
        struct CADMCOMW *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        const wchar_t **a4)
{
  COpenHandle *v7; // rdi
  int v8; // eax
  int v9; // ebx
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rax
  const wchar_t *i; // rcx
  wchar_t *v13; // rax
  const wchar_t *v14; // rax
  __int64 v15; // rdx
  unsigned int v17; // [rsp+30h] [rbp-58h] BYREF
  COpenHandle *v18; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v19; // [rsp+90h] [rbp+8h] BYREF

  v18 = 0;
  v17 = 0;
  v19 = 0;
  v7 = 0;
  if ( !a1 || !a4 )
  {
LABEL_23:
    v9 = -2147024809;
    goto LABEL_24;
  }
  v8 = CADMCOMW::Lookup(a1, a2, &v17, &v19, &v18);
  v7 = v18;
  v9 = v8;
  if ( v8 < 0 )
    goto LABEL_24;
  v10 = *(const unsigned __int16 **)v18;
  if ( !*(_QWORD *)v18 )
  {
    v9 = -2147467259;
    goto LABEL_24;
  }
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  if ( !v11 || (v9 = STRU::Copy((STRU *)a4, v10), v9 >= 0) )
  {
    if ( !a3 )
    {
LABEL_22:
      v9 = 0;
      goto LABEL_24;
    }
    v9 = STRU::Append((STRU *)a4, L"/");
    if ( v9 >= 0 )
    {
      if ( *a3 == 47 || *a3 == 92 )
        ++a3;
      v9 = STRU::Append((STRU *)a4, a3);
      if ( v9 >= 0 )
      {
        for ( i = a4[4]; ; i = v13 )
        {
          v13 = wcschr(i, 0x5Cu);
          if ( !v13 )
            break;
          *v13 = 47;
        }
        v14 = a4[4];
        v15 = (unsigned int)(*((_DWORD *)a4 + 12) - 1);
        if ( v14[v15] != 47 && v14[v15] != 92 || STRU::SetLen((STRU *)a4, v15) )
          goto LABEL_22;
        goto LABEL_23;
      }
    }
  }
LABEL_24:
  if ( v7 )
    COpenHandle::Release(v7, a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000f30c  mov     r11, rsp
0x18000f30f  push    rbx
0x18000f310  push    rbp
0x18000f311  push    rsi
0x18000f312  push    rdi
0x18000f313  push    r12
0x18000f315  push    r13
0x18000f317  push    r14
0x18000f319  push    r15
0x18000f31b  sub     rsp, 48h
0x18000f31f  xor     r15d, r15d
0x18000f322  mov     rsi, r9
0x18000f325  mov     [r11-50h], r15
0x18000f329  mov     r14, r8
0x18000f32c  mov     [r11-58h], r15d
0x18000f330  mov     rbp, rcx
0x18000f333  mov     [r11+8], r15d
0x18000f337  mov     edi, r15d
0x18000f33a  test    rcx, rcx
0x18000f33d  jz      loc_18000F438
0x18000f343  test    r9, r9
0x18000f346  jz      loc_18000F438
0x18000f34c  lea     rax, [r11-50h]
0x18000f350  lea     r9, [r11+8]; unsigned int *
0x18000f354  mov     [r11-68h], rax
0x18000f358  lea     r8, [r11-58h]; unsigned int *
0x18000f35c  call    ?Lookup@CADMCOMW@@QEAAJKPEAK0PEAPEAVCOpenHandle@@@Z; CADMCOMW::Lookup(ulong,ulong *,ulong *,COpenHandle * *)
0x18000f361  mov     rdi, [rsp+88h+var_50]
0x18000f366  mov     ebx, eax
0x18000f368  test    eax, eax
0x18000f36a  js      loc_18000F43D
0x18000f370  mov     rdx, [rdi]
0x18000f373  test    rdx, rdx
0x18000f376  jnz     short loc_18000F382
0x18000f378  mov     ebx, 80004005h
0x18000f37d  jmp     loc_18000F43D
0x18000f382  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000f386  inc     rax
0x18000f389  cmp     [rdx+rax*2], r15w
0x18000f38e  jnz     short loc_18000F386
0x18000f390  test    rax, rax
0x18000f393  jz      short loc_18000F3A8
0x18000f395  mov     rcx, rsi
0x18000f398  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000f39e  mov     ebx, eax
0x18000f3a0  test    eax, eax
0x18000f3a2  js      loc_18000F43D
0x18000f3a8  test    r14, r14
0x18000f3ab  jz      loc_18000F433
0x18000f3b1  lea     rdx, asc_180011C70; "/"
0x18000f3b8  mov     rcx, rsi
0x18000f3bb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f3c1  mov     ebx, eax
0x18000f3c3  test    eax, eax
0x18000f3c5  js      short loc_18000F43D
0x18000f3c7  mov     r12d, 5Ch ; '\'
0x18000f3cd  lea     r13d, [r12-2Dh]
0x18000f3d2  cmp     [r14], r13w
0x18000f3d6  jz      short loc_18000F3DE
0x18000f3d8  cmp     [r14], r12w
0x18000f3dc  jnz     short loc_18000F3E2
0x18000f3de  add     r14, 2
0x18000f3e2  mov     rdx, r14
0x18000f3e5  mov     rcx, rsi
0x18000f3e8  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000f3ee  mov     ebx, eax
0x18000f3f0  test    eax, eax
0x18000f3f2  js      short loc_18000F43D
0x18000f3f4  mov     rcx, [rsi+20h]
0x18000f3f8  jmp     short loc_18000F401
0x18000f3fa  mov     [rax], r13w
0x18000f3fe  mov     rcx, rax; Str
0x18000f401  mov     edx, r12d; Ch
0x18000f404  call    cs:__imp_wcschr
0x18000f40a  test    rax, rax
0x18000f40d  jnz     short loc_18000F3FA
0x18000f40f  mov     edx, [rsi+30h]
0x18000f412  mov     rax, [rsi+20h]
0x18000f416  dec     edx
0x18000f418  cmp     [rax+rdx*2], r13w
0x18000f41d  jz      short loc_18000F426
0x18000f41f  cmp     [rax+rdx*2], r12w
0x18000f424  jnz     short loc_18000F433
0x18000f426  mov     rcx, rsi
0x18000f429  call    cs:__imp_?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18000f42f  test    al, al
0x18000f431  jz      short loc_18000F438
0x18000f433  mov     ebx, r15d
0x18000f436  jmp     short loc_18000F43D
0x18000f438  mov     ebx, 80070057h
0x18000f43d  test    rdi, rdi
0x18000f440  jz      short loc_18000F44D
0x18000f442  mov     rdx, rbp; void *
0x18000f445  mov     rcx, rdi; this
0x18000f448  call    ?Release@COpenHandle@@QEAAXPEAX@Z; COpenHandle::Release(void *)
0x18000f44d  mov     eax, ebx
0x18000f44f  add     rsp, 48h
0x18000f453  pop     r15
0x18000f455  pop     r14
0x18000f457  pop     r13
0x18000f459  pop     r12
0x18000f45b  pop     rdi
0x18000f45c  pop     rsi
0x18000f45d  pop     rbp
0x18000f45e  pop     rbx
0x18000f45f  retn
```
