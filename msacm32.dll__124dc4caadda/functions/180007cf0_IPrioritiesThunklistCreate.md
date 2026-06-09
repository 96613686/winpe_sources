# IPrioritiesThunklistCreate

- ea: `0x180007cf0`
- end: `0x180007ee3`
- name: `IPrioritiesThunklistCreate`
- size: `499`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180001570`

## callees

- `0x180001210`
- `0x180001c40`
- `0x180001cd0`
- `0x180002220`
- `0x180007380`
- `0x180007cf0`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007d82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007d82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007eb7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007eb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e93`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007e93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007de8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e45`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007de8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180007e45`

## pseudocode

```c
int __fastcall IPrioritiesThunklistCreate(__int64 a1, __int64 a2)
{
  HKEY v4; // rbx
  unsigned int i; // esi
  char *v6; // rax
  __int64 v7; // rdi
  int v8; // r15d
  int Next; // eax
  __int64 v10; // rdx
  __int64 v12; // rdi
  __int64 v13; // rcx
  wchar_t *v14; // rax
  __int64 v15; // rdx
  DWORD Type; // [rsp+30h] [rbp-1E8h] BYREF
  DWORD cbData[2]; // [rsp+38h] [rbp-1E0h] BYREF
  wchar_t pszDest[32]; // [rsp+40h] [rbp-1D8h] BYREF
  wchar_t Data[176]; // [rsp+80h] [rbp-198h] BYREF

  v4 = IRegOpenKeyAcm(L"Priority v4.00");
  for ( i = 1; ; ++i )
  {
    StringCchPrintfW(pszDest, 0x20u, L"Priority%u", i);
    Type = -2;
    cbData[0] = 352;
    LODWORD(v6) = RegQueryValueExW(v4, pszDest, 0, &Type, (LPBYTE)Data, cbData);
    if ( (_DWORD)v6 || Type != 1 )
      break;
    v7 = 0;
    v8 = 1;
    *(_QWORD *)cbData = 0;
    while ( 1 )
    {
      Next = IDriverGetNext(a1, cbData, v7, 0xC0000000);
      v7 = *(_QWORD *)cbData;
      if ( Next )
        break;
      if ( (unsigned int)IDriverPrioritiesIsMatch(*(_QWORD *)cbData, Data) )
      {
        v8 = 0;
        break;
      }
    }
    v6 = (char *)LocalAlloc(0x40u, 0x14u);
    *(_QWORD *)(a2 + 12) = v6;
    if ( !v6 )
    {
      if ( !v4 )
        return (int)v6;
      goto LABEL_23;
    }
    *(_QWORD *)(v6 + 12) = 0;
    **(_DWORD **)(a2 + 12) = v8;
    if ( v8 )
    {
      v10 = -1;
      while ( Data[++v10] != 0 )
        ;
      v12 = *(_QWORD *)(a2 + 12);
      *(_QWORD *)(v12 + 4) = LocalAlloc(0x40u, 2 * v10 + 2);
      v13 = *(_QWORD *)(a2 + 12);
      v14 = *(wchar_t **)(v13 + 4);
      if ( !v14 )
      {
        LODWORD(v6) = (unsigned int)LocalFree((HLOCAL)v13);
        *(_QWORD *)(a2 + 12) = 0;
        if ( !v4 )
          return (int)v6;
        goto LABEL_23;
      }
      v15 = -1;
      do
        ++v15;
      while ( Data[v15] );
      StringCchCopyW(v14, v15 + 1, Data);
    }
    else
    {
      *(_QWORD *)(*(_QWORD *)(a2 + 12) + 4LL) = v7;
    }
    a2 = *(_QWORD *)(a2 + 12);
  }
  if ( !v4 )
    return (int)v6;
LABEL_23:
  LODWORD(v6) = RegCloseKey(v4);
  return (int)v6;
}

```

## disassembly

```asm
0x180007cf0  push    rbx
0x180007cf2  push    rbp
0x180007cf3  push    rsi
0x180007cf4  push    rdi
0x180007cf5  push    r14
0x180007cf7  sub     rsp, 1F0h
0x180007cfe  mov     rax, cs:__security_cookie
0x180007d05  xor     rax, rsp
0x180007d08  mov     [rsp+218h+var_38], rax
0x180007d10  mov     rbp, rcx
0x180007d13  mov     r14, rdx
0x180007d16  lea     rcx, gszSecPriority; "Priority v4.00"
0x180007d1d  call    IRegOpenKeyAcm
0x180007d22  mov     rbx, rax
0x180007d25  mov     [rsp+218h+arg_10], r15
0x180007d2d  mov     esi, 1
0x180007d32  mov     r9d, esi
0x180007d35  lea     r8, gszKeyPriority; "Priority%u"
0x180007d3c  mov     edx, 20h ; ' '; cchDest
0x180007d41  lea     rcx, [rsp+218h+pszDest]; pszDest
0x180007d46  call    StringCchPrintfW
0x180007d4b  lea     rax, [rsp+218h+cbData]
0x180007d50  mov     [rsp+218h+Type], 0FFFFFFFEh
0x180007d58  mov     [rsp+218h+lpcbData], rax; lpcbData
0x180007d5d  lea     r9, [rsp+218h+Type]; lpType
0x180007d62  lea     rax, [rsp+218h+Data]
0x180007d6a  mov     [rsp+218h+cbData], 160h
0x180007d72  xor     r8d, r8d; lpReserved
0x180007d75  mov     [rsp+218h+lpData], rax; lpData
0x180007d7a  lea     rdx, [rsp+218h+pszDest]; lpValueName
0x180007d7f  mov     rcx, rbx; hKey
0x180007d82  call    cs:__imp_RegQueryValueExW
0x180007d88  test    eax, eax
0x180007d8a  jnz     loc_180007EAF
0x180007d90  cmp     [rsp+218h+Type], 1
0x180007d95  jnz     loc_180007EAF
0x180007d9b  xor     edi, edi
0x180007d9d  mov     r15d, 1
0x180007da3  mov     qword ptr [rsp+218h+cbData], rdi
0x180007da8  mov     r9d, 0C0000000h
0x180007dae  lea     rdx, [rsp+218h+cbData]
0x180007db3  mov     r8, rdi
0x180007db6  mov     rcx, rbp
0x180007db9  call    IDriverGetNext
0x180007dbe  mov     rdi, qword ptr [rsp+218h+cbData]
0x180007dc3  test    eax, eax
0x180007dc5  jnz     short loc_180007DDE
0x180007dc7  lea     rdx, [rsp+218h+Data]
0x180007dcf  mov     rcx, rdi
0x180007dd2  call    IDriverPrioritiesIsMatch
0x180007dd7  test    eax, eax
0x180007dd9  jz      short loc_180007DA8
0x180007ddb  xor     r15d, r15d
0x180007dde  mov     edx, 14h; uBytes
0x180007de3  mov     ecx, 40h ; '@'; uFlags
0x180007de8  call    cs:__imp_LocalAlloc
0x180007dee  mov     [r14+0Ch], rax
0x180007df2  test    rax, rax
0x180007df5  jz      loc_180007EA8
0x180007dfb  mov     qword ptr [rax+0Ch], 0
0x180007e03  mov     rax, [r14+0Ch]
0x180007e07  mov     [rax], r15d
0x180007e0a  test    r15d, r15d
0x180007e0d  jnz     short loc_180007E19
0x180007e0f  mov     rax, [r14+0Ch]
0x180007e13  mov     [rax+4], rdi
0x180007e17  jmp     short loc_180007E88
0x180007e19  lea     rax, [rsp+218h+Data]
0x180007e21  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180007e28  cmp     word ptr [rax+rdx*2+2], 0
0x180007e2e  lea     rdx, [rdx+1]
0x180007e32  jnz     short loc_180007E28
0x180007e34  mov     rdi, [r14+0Ch]
0x180007e38  lea     rdx, ds:2[rdx*2]; uBytes
0x180007e40  mov     ecx, 40h ; '@'; uFlags
0x180007e45  call    cs:__imp_LocalAlloc
0x180007e4b  mov     [rdi+4], rax
0x180007e4f  mov     rcx, [r14+0Ch]; hMem
0x180007e53  mov     rax, [rcx+4]
0x180007e57  test    rax, rax
0x180007e5a  jz      short loc_180007E93
0x180007e5c  lea     rcx, [rsp+218h+Data]
0x180007e64  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180007e6b  inc     rdx
0x180007e6e  cmp     word ptr [rcx+rdx*2], 0
0x180007e73  jnz     short loc_180007E6B
0x180007e75  inc     rdx; cchDest
0x180007e78  lea     r8, [rsp+218h+Data]; pszSrc
0x180007e80  mov     rcx, rax; pszDest
0x180007e83  call    StringCchCopyW
0x180007e88  mov     r14, [r14+0Ch]
0x180007e8c  inc     esi
0x180007e8e  jmp     loc_180007D32
0x180007e93  call    cs:__imp_LocalFree
0x180007e99  mov     qword ptr [r14+0Ch], 0
0x180007ea1  test    rbx, rbx
0x180007ea4  jnz     short loc_180007EB4
0x180007ea6  jmp     short loc_180007EBD
0x180007ea8  test    rbx, rbx
0x180007eab  jz      short loc_180007EBD
0x180007ead  jmp     short loc_180007EB4
0x180007eaf  test    rbx, rbx
0x180007eb2  jz      short loc_180007EBD
0x180007eb4  mov     rcx, rbx; hKey
0x180007eb7  call    cs:__imp_RegCloseKey
0x180007ebd  mov     r15, [rsp+218h+arg_10]
0x180007ec5  mov     rcx, [rsp+218h+var_38]
0x180007ecd  xor     rcx, rsp; StackCookie
0x180007ed0  call    __security_check_cookie
0x180007ed5  add     rsp, 1F0h
0x180007edc  pop     r14
0x180007ede  pop     rdi
0x180007edf  pop     rsi
0x180007ee0  pop     rbp
0x180007ee1  pop     rbx
0x180007ee2  retn
```
