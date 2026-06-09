# SecureUserKey(ushort const *,ushort const *,int)

- ea: `0x1800b5894`
- end: `0x1800b5adb`
- name: `?SecureUserKey@@YAJPEBG0H@Z`
- size: `583`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800baaa0`

## callees

- `0x180003770`
- `0x18002c690`
- `0x18003d8d0`
- `0x1800b5610`
- `0x1800b5894`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b590e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b590e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b59aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5a11`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5900`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b599c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b5900`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800b599c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5aab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5abb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a92`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5aab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b5abb`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5a07`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5a5f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5a07`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800b5a5f`

## pseudocode

```c
__int64 __fastcall SecureUserKey(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 v7; // r9
  __int64 v8; // rax
  unsigned __int64 v9; // r14
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbp
  signed int v12; // eax
  signed int v13; // ebx
  unsigned __int64 v14; // r14
  unsigned __int16 *v15; // rdi
  signed int LastError; // eax
  const unsigned __int16 *v17; // r8
  signed int v18; // eax
  const unsigned __int16 *v19; // r8
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+8h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+78h] [rbp+10h] BYREF

  v3 = -1;
  SecurityDescriptor = 0;
  hMem = 0;
  if ( a1 )
  {
    v7 = -1;
    do
      ++v7;
    while ( a1[v7] );
  }
  else
  {
    v7 = 0;
  }
  if ( a2 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a2[v8] );
  }
  else
  {
    v8 = 0;
  }
  v9 = v7 + v8 + 2;
  v10 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v9);
  v11 = v10;
  if ( v10 )
  {
    v13 = StringCchCopyW(v10, v9, a1);
    if ( v13 < 0 )
      goto LABEL_34;
    v13 = StringCchCatW(v11, v9, L"\\");
    if ( v13 < 0 )
      goto LABEL_34;
    v13 = StringCchCatW(v11, v9, a2);
    if ( v13 < 0 )
      goto LABEL_34;
    if ( a1 )
    {
      do
        ++v3;
      while ( a1[v3] );
    }
    else
    {
      v3 = 0;
    }
    v14 = v3 + 211;
    v15 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * (v3 + 211));
    if ( !v15 )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_34;
    }
    v17 = L"D:PAI(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;%s)";
    if ( a3 )
      v17 = L"D:PAI(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A;OICI;KR;;;RC)(A;OICI;KR;;;%s)(A;OICI;KR;;;AC)(A;OICI;KR;;;S-1-15-3-1"
             "024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)";
    v13 = StringCchPrintfW(v15, v14, v17, a1);
    if ( v13 >= 0 )
    {
      if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &SecurityDescriptor, 0) )
        goto LABEL_25;
      v19 = L"D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;OICIID;KR;;;%s)";
      if ( a3 )
        v19 = L"D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA)(A;OICIID;KR;;;RC)(A;OICIID;KR;;;%s)(A;OICIID;KR;;;AC)(A;OICIID;KR"
               ";;;S-1-15-3-1024-1065365936-1281604716-3511738428-1654721687-432734479-3232135806-4053264122-3456934681)";
      v13 = StringCchPrintfW(v15, v14, v19, a1);
      if ( v13 < 0 )
        goto LABEL_33;
      if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(v15, 1u, &hMem, 0) )
      {
        v13 = ApplySecurityToRegistryTree(HKEY_USERS, v11, SecurityDescriptor, hMem, 1);
        if ( v13 >= 0 )
          v13 = 0;
      }
      else
      {
LABEL_25:
        v18 = GetLastError();
        v13 = v18;
        if ( v18 > 0 )
          v13 = (unsigned __int16)v18 | 0x80070000;
      }
    }
LABEL_33:
    LocalFree(v15);
LABEL_34:
    LocalFree(v11);
    goto LABEL_35;
  }
  v12 = GetLastError();
  v13 = v12;
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
LABEL_35:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800b5894  mov     [rsp+arg_10], rbx
0x1800b5899  push    rbp
0x1800b589a  push    rsi
0x1800b589b  push    rdi
0x1800b589c  push    r12
0x1800b589e  push    r13
0x1800b58a0  push    r14
0x1800b58a2  push    r15
0x1800b58a4  sub     rsp, 30h
0x1800b58a8  xor     r13d, r13d
0x1800b58ab  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b58af  mov     [rsp+68h+SecurityDescriptor], r13
0x1800b58b4  mov     r12d, r8d
0x1800b58b7  mov     [rsp+68h+hMem], r13
0x1800b58bc  mov     r15, rdx
0x1800b58bf  mov     rsi, rcx
0x1800b58c2  test    rcx, rcx
0x1800b58c5  jnz     short loc_1800B58CC
0x1800b58c7  mov     r9d, r13d
0x1800b58ca  jmp     short loc_1800B58D9
0x1800b58cc  mov     r9, rdi
0x1800b58cf  inc     r9
0x1800b58d2  cmp     [rcx+r9*2], r13w
0x1800b58d7  jnz     short loc_1800B58CF
0x1800b58d9  test    r15, r15
0x1800b58dc  jnz     short loc_1800B58E3
0x1800b58de  mov     rax, r13
0x1800b58e1  jmp     short loc_1800B58F0
0x1800b58e3  mov     rax, rdi
0x1800b58e6  inc     rax
0x1800b58e9  cmp     [rdx+rax*2], r13w
0x1800b58ee  jnz     short loc_1800B58E6
0x1800b58f0  lea     r14, [rax+2]
0x1800b58f4  mov     ecx, 40h ; '@'; uFlags
0x1800b58f9  add     r14, r9
0x1800b58fc  lea     rdx, [r14+r14]; uBytes
0x1800b5900  call    cs:__imp_LocalAlloc
0x1800b5906  mov     rbp, rax
0x1800b5909  test    rax, rax
0x1800b590c  jnz     short loc_1800B592C
0x1800b590e  call    cs:__imp_GetLastError
0x1800b5914  mov     ebx, eax
0x1800b5916  test    eax, eax
0x1800b5918  jle     loc_1800B5AA1
0x1800b591e  movzx   ebx, ax
0x1800b5921  or      ebx, 80070000h
0x1800b5927  jmp     loc_1800B5AA1
0x1800b592c  mov     r8, rsi; unsigned __int16 *
0x1800b592f  mov     rdx, r14; unsigned __int64
0x1800b5932  mov     rcx, rbp; unsigned __int16 *
0x1800b5935  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b593a  mov     ebx, eax
0x1800b593c  test    eax, eax
0x1800b593e  js      loc_1800B5A98
0x1800b5944  lea     r8, asc_1800C3A8C; "\\"
0x1800b594b  mov     rdx, r14; unsigned __int64
0x1800b594e  mov     rcx, rbp; unsigned __int16 *
0x1800b5951  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b5956  mov     ebx, eax
0x1800b5958  test    eax, eax
0x1800b595a  js      loc_1800B5A98
0x1800b5960  mov     r8, r15; unsigned __int16 *
0x1800b5963  mov     rdx, r14; unsigned __int64
0x1800b5966  mov     rcx, rbp; unsigned __int16 *
0x1800b5969  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800b596e  mov     ebx, eax
0x1800b5970  test    eax, eax
0x1800b5972  js      loc_1800B5A98
0x1800b5978  test    rsi, rsi
0x1800b597b  jnz     short loc_1800B5982
0x1800b597d  mov     rdi, r13
0x1800b5980  jmp     short loc_1800B598C
0x1800b5982  inc     rdi
0x1800b5985  cmp     [rsi+rdi*2], r13w
0x1800b598a  jnz     short loc_1800B5982
0x1800b598c  lea     r14, [rdi+0D3h]
0x1800b5993  mov     ecx, 40h ; '@'; uFlags
0x1800b5998  lea     rdx, [r14+r14]; uBytes
0x1800b599c  call    cs:__imp_LocalAlloc
0x1800b59a2  mov     rdi, rax
0x1800b59a5  test    rax, rax
0x1800b59a8  jnz     short loc_1800B59C8
0x1800b59aa  call    cs:__imp_GetLastError
0x1800b59b0  mov     ebx, eax
0x1800b59b2  test    eax, eax
0x1800b59b4  jle     loc_1800B5A98
0x1800b59ba  movzx   ebx, ax
0x1800b59bd  or      ebx, 80070000h
0x1800b59c3  jmp     loc_1800B5A98
0x1800b59c8  lea     rax, aDPaiAOiciKaSyA; "D:PAI(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A"...
0x1800b59cf  test    r12d, r12d
0x1800b59d2  lea     r8, aDPaiAOiciKaSyA_0; "D:PAI(A;OICI;KA;;;SY)(A;OICI;KA;;;BA)(A"...
0x1800b59d9  mov     r9, rsi
0x1800b59dc  cmovnz  r8, rax; unsigned __int16 *
0x1800b59e0  mov     rdx, r14; unsigned __int64
0x1800b59e3  mov     rcx, rdi; unsigned __int16 *
0x1800b59e6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b59eb  mov     ebx, eax
0x1800b59ed  test    eax, eax
0x1800b59ef  js      loc_1800B5A8F
0x1800b59f5  xor     r9d, r9d; SecurityDescriptorSize
0x1800b59f8  lea     r8, [rsp+68h+SecurityDescriptor]; SecurityDescriptor
0x1800b59fd  mov     rcx, rdi; StringSecurityDescriptor
0x1800b5a00  lea     r15d, [r9+1]
0x1800b5a04  mov     edx, r15d; StringSDRevision
0x1800b5a07  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b5a0d  test    eax, eax
0x1800b5a0f  jnz     short loc_1800B5A28
0x1800b5a11  call    cs:__imp_GetLastError
0x1800b5a17  mov     ebx, eax
0x1800b5a19  test    eax, eax
0x1800b5a1b  jle     short loc_1800B5A8F
0x1800b5a1d  movzx   ebx, ax
0x1800b5a20  or      ebx, 80070000h
0x1800b5a26  jmp     short loc_1800B5A8F
0x1800b5a28  lea     rax, aDAiAOiciidKaSy; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x1800b5a2f  test    r12d, r12d
0x1800b5a32  lea     r8, aDAiAOiciidKaSy_0; "D:AI(A;OICIID;KA;;;SY)(A;OICIID;KA;;;BA"...
0x1800b5a39  mov     r9, rsi
0x1800b5a3c  cmovnz  r8, rax; unsigned __int16 *
0x1800b5a40  mov     rdx, r14; unsigned __int64
0x1800b5a43  mov     rcx, rdi; unsigned __int16 *
0x1800b5a46  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800b5a4b  mov     ebx, eax
0x1800b5a4d  test    eax, eax
0x1800b5a4f  js      short loc_1800B5A8F
0x1800b5a51  xor     r9d, r9d; SecurityDescriptorSize
0x1800b5a54  lea     r8, [rsp+68h+hMem]; SecurityDescriptor
0x1800b5a59  mov     edx, r15d; StringSDRevision
0x1800b5a5c  mov     rcx, rdi; StringSecurityDescriptor
0x1800b5a5f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800b5a65  test    eax, eax
0x1800b5a67  jz      short loc_1800B5A11
0x1800b5a69  mov     r9, [rsp+68h+hMem]; void *
0x1800b5a6e  mov     rdx, rbp; unsigned __int16 *
0x1800b5a71  mov     r8, [rsp+68h+SecurityDescriptor]; void *
0x1800b5a76  mov     rcx, 0FFFFFFFF80000003h; HKEY
0x1800b5a7d  mov     [rsp+68h+var_48], r15d; int
0x1800b5a82  call    ?ApplySecurityToRegistryTree@@YAJPEAUHKEY__@@PEBGPEAX2H@Z; ApplySecurityToRegistryTree(HKEY__ *,ushort const *,void *,void *,int)
0x1800b5a87  test    eax, eax
0x1800b5a89  mov     ebx, eax
0x1800b5a8b  cmovns  ebx, r13d
0x1800b5a8f  mov     rcx, rdi; hMem
0x1800b5a92  call    cs:__imp_LocalFree
0x1800b5a98  mov     rcx, rbp; hMem
0x1800b5a9b  call    cs:__imp_LocalFree
0x1800b5aa1  mov     rcx, [rsp+68h+SecurityDescriptor]; hMem
0x1800b5aa6  test    rcx, rcx
0x1800b5aa9  jz      short loc_1800B5AB1
0x1800b5aab  call    cs:__imp_LocalFree
0x1800b5ab1  mov     rcx, [rsp+68h+hMem]; hMem
0x1800b5ab6  test    rcx, rcx
0x1800b5ab9  jz      short loc_1800B5AC1
0x1800b5abb  call    cs:__imp_LocalFree
0x1800b5ac1  mov     eax, ebx
0x1800b5ac3  mov     rbx, [rsp+68h+arg_10]
0x1800b5acb  add     rsp, 30h
0x1800b5acf  pop     r15
0x1800b5ad1  pop     r14
0x1800b5ad3  pop     r13
0x1800b5ad5  pop     r12
0x1800b5ad7  pop     rdi
0x1800b5ad8  pop     rsi
0x1800b5ad9  pop     rbp
0x1800b5ada  retn
```
