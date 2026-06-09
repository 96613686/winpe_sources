# GetValidNodePathRegistryValues(HKEY__ *,ushort const *,utl::list<ushort *,utl::allocator<ushort *>> *)

- ea: `0x18001f654`
- end: `0x18001f955`
- name: `?GetValidNodePathRegistryValues@@YAJPEAUHKEY__@@PEBGPEAV?$list@PEAGV?$allocator@PEAG@utl@@@utl@@@Z`
- size: `769`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180051824`

## callees

- `0x18000dd20`
- `0x18001ab40`
- `0x18001f654`
- `0x18002e1a0`
- `0x18002e570`
- `0x18002e614`
- `0x18002ec8c`
- `0x180030fa5`
- `0x18004c458`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f7d5`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001f7d5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f730`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001f730`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f6c9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001f6c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001f8a0`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001f836`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x18001f836`

## string_xrefs

- `0x18001f6bb`: `Software\Microsoft\Enrollments\ValidNodePaths`

## pseudocode

```c
__int64 __fastcall GetValidNodePathRegistryValues(__int64 a1, __int64 a2, _QWORD *a3)
{
  WCHAR *v4; // r15
  LSTATUS v5; // eax
  signed int v6; // ebx
  LSTATUS v7; // eax
  unsigned __int64 v8; // rax
  DWORD i; // edi
  LSTATUS v10; // eax
  __int64 v11; // rcx
  DWORD v12; // esi
  unsigned __int64 v13; // rax
  void *v14; // rax
  struct CSPPair near **j; // rdi
  struct CSPPair near *v16; // rsi
  __int64 v17; // rax
  unsigned __int64 v18; // r15
  unsigned __int64 v19; // rax
  void *v20; // rax
  DWORD cchLength[2]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbData[4]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Data[264]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  v4 = 0;
  cchValueName = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  if ( !a3 )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments\\ValidNodePaths", 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 >= 0 )
  {
    v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
    v6 = v7;
    if ( v7 > 0 )
      v6 = (unsigned __int16)v7 | 0x80070000;
    if ( v6 >= 0 )
    {
      v8 = 2LL * (cbMaxValueNameLen + 1);
      if ( !is_mul_ok(cbMaxValueNameLen + 1, 2u) )
        v8 = -1;
      v4 = (WCHAR *)operator new[](v8, (const struct std::nothrow_t *)&std::nothrow);
      if ( v4 )
      {
        for ( i = 0; i < cValues; ++i )
        {
          memset_0(Data, 0, 0x208u);
          cchValueName = cbMaxValueNameLen + 1;
          cbData[0] = 520;
          cchLength[0] = 0;
          v10 = RegEnumValueW(hKey, i, v4, &cchValueName, 0, 0, (LPBYTE)Data, cbData);
          v6 = v10;
          if ( v10 > 0 )
            v6 = (unsigned __int16)v10 | 0x80070000;
          if ( v6 < 0 )
            break;
          v11 = -1;
          do
            ++v11;
          while ( Data[v11] );
          v6 = ULongLongToULong(v11 + 1, cchLength);
          if ( v6 < 0 )
            break;
          v6 = ULongLongToULong(2LL * cchLength[0], cchLength);
          if ( v6 < 0 )
            break;
          CharLowerBuffW(Data, cchLength[0]);
          v12 = cchLength[0];
          v13 = 2LL * cchLength[0];
          if ( !is_mul_ok(cchLength[0], 2u) )
            v13 = -1;
          v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
          *(_QWORD *)cchLength = v14;
          if ( !v14 )
            goto LABEL_26;
          memcpy_0(v14, Data, v12);
          if ( !(unsigned __int8)utl::list<unsigned short *,utl::allocator<unsigned short *>>::push_back(a3, cchLength) )
            goto LABEL_26;
        }
      }
      else
      {
LABEL_26:
        v6 = -2147024882;
      }
    }
  }
  RegCloseKey(hKey);
  operator delete(v4);
  if ( (_QWORD *)*a3 == a3 )
  {
    v6 = 0;
    for ( j = (struct CSPPair near **)off_1800AF4C0; j != &mapping; ++j )
    {
      v16 = *j;
      v17 = -1;
      do
        ++v17;
      while ( *((_WORD *)v16 + v17) );
      v18 = 2 * v17 + 2;
      v19 = 2 * v18;
      if ( !is_mul_ok(v18, 2u) )
        v19 = -1;
      v20 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
      *(_QWORD *)cbData = v20;
      if ( v20 )
      {
        memcpy_0(v20, v16, v18);
        if ( (unsigned __int8)utl::list<unsigned short *,utl::allocator<unsigned short *>>::push_back(a3, cbData) )
          continue;
      }
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f654  push    rbp
0x18001f656  push    rbx
0x18001f657  push    rsi
0x18001f658  push    rdi
0x18001f659  push    r12
0x18001f65b  push    r13
0x18001f65d  push    r14
0x18001f65f  push    r15
0x18001f661  lea     rbp, [rsp-1B8h]
0x18001f669  sub     rsp, 2B8h
0x18001f670  mov     rax, cs:__security_cookie
0x18001f677  xor     rax, rsp
0x18001f67a  mov     [rbp+1F0h+var_50], rax
0x18001f681  xor     r12d, r12d
0x18001f684  mov     r14, r8
0x18001f687  mov     [rsp+2F0h+hKey], r12
0x18001f68c  mov     r15d, r12d
0x18001f68f  mov     [rsp+2F0h+cchValueName], r12d
0x18001f694  mov     [rsp+2F0h+cValues], r12d
0x18001f699  mov     [rsp+2F0h+cbMaxValueNameLen], r12d
0x18001f69e  test    r8, r8
0x18001f6a1  jnz     short loc_18001F6A8
0x18001f6a3  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "pNodeList != NULL")
0x18001f6a8  lea     rax, [rsp+2F0h+hKey]
0x18001f6ad  mov     r9d, 20019h; samDesired
0x18001f6b3  xor     r8d, r8d; ulOptions
0x18001f6b6  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18001f6bb  lea     rdx, aSoftwareMicros_17; "Software\\Microsoft\\Enrollments\\Valid"...
0x18001f6c2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f6c9  call    cs:__imp_RegOpenKeyExW
0x18001f6cf  mov     ebx, eax
0x18001f6d1  mov     esi, 80070000h
0x18001f6d6  test    eax, eax
0x18001f6d8  jle     short loc_18001F6DF
0x18001f6da  movzx   ebx, ax
0x18001f6dd  or      ebx, esi
0x18001f6df  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001f6e3  mov     r13d, 8007000Eh
0x18001f6e9  test    ebx, ebx
0x18001f6eb  js      loc_18001F89B
0x18001f6f1  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001f6f6  lea     rax, [rsp+2F0h+cbMaxValueNameLen]
0x18001f6fb  mov     [rsp+2F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x18001f700  xor     r9d, r9d; lpReserved
0x18001f703  mov     [rsp+2F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x18001f708  xor     r8d, r8d; lpcchClass
0x18001f70b  mov     [rsp+2F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x18001f710  xor     edx, edx; lpClass
0x18001f712  mov     [rsp+2F0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001f717  lea     rax, [rsp+2F0h+cValues]
0x18001f71c  mov     [rsp+2F0h+lpcValues], rax; lpcValues
0x18001f721  mov     [rsp+2F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x18001f726  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r12; lpcbMaxSubKeyLen
0x18001f72b  mov     [rsp+2F0h+phkResult], r12; lpcSubKeys
0x18001f730  call    cs:__imp_RegQueryInfoKeyW
0x18001f736  mov     ebx, eax
0x18001f738  test    eax, eax
0x18001f73a  jle     short loc_18001F741
0x18001f73c  movzx   ebx, ax
0x18001f73f  or      ebx, esi
0x18001f741  test    ebx, ebx
0x18001f743  js      loc_18001F89B
0x18001f749  mov     ecx, [rsp+2F0h+cbMaxValueNameLen]
0x18001f74d  mov     eax, 2
0x18001f752  inc     ecx
0x18001f754  mul     rcx
0x18001f757  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f75e  cmovb   rax, rdi
0x18001f762  mov     rcx, rax; unsigned __int64
0x18001f765  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f76a  mov     r15, rax
0x18001f76d  test    rax, rax
0x18001f770  jz      loc_18001F898
0x18001f776  mov     edi, r12d
0x18001f779  cmp     edi, [rsp+2F0h+cValues]
0x18001f77d  jnb     loc_18001F89B
0x18001f783  xor     edx, edx; Val
0x18001f785  lea     rcx, [rbp+1F0h+Data]; void *
0x18001f789  mov     r8d, 208h; Size
0x18001f78f  call    memset_0
0x18001f794  mov     eax, [rsp+2F0h+cbMaxValueNameLen]
0x18001f798  lea     r9, [rsp+2F0h+cchValueName]; lpcchValueName
0x18001f79d  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001f7a2  inc     eax
0x18001f7a4  mov     [rsp+2F0h+cchValueName], eax
0x18001f7a8  mov     r8, r15; lpValueName
0x18001f7ab  lea     rax, [rbp+1F0h+cbData]
0x18001f7af  mov     [rbp+1F0h+cbData], 208h
0x18001f7b6  mov     [rsp+2F0h+lpcValues], rax; lpcbData
0x18001f7bb  mov     edx, edi; dwIndex
0x18001f7bd  lea     rax, [rbp+1F0h+Data]
0x18001f7c1  mov     [rsp+2F0h+cchLength], r12d
0x18001f7c6  mov     [rsp+2F0h+lpcbMaxClassLen], rax; lpData
0x18001f7cb  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r12; lpType
0x18001f7d0  mov     [rsp+2F0h+phkResult], r12; lpReserved
0x18001f7d5  call    cs:__imp_RegEnumValueW
0x18001f7db  mov     ebx, eax
0x18001f7dd  test    eax, eax
0x18001f7df  jle     short loc_18001F7E6
0x18001f7e1  movzx   ebx, ax
0x18001f7e4  or      ebx, esi
0x18001f7e6  test    ebx, ebx
0x18001f7e8  js      loc_18001F89B
0x18001f7ee  lea     rax, [rbp+1F0h+Data]
0x18001f7f2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f7f6  inc     rcx
0x18001f7f9  cmp     [rax+rcx*2], r12w
0x18001f7fe  jnz     short loc_18001F7F6
0x18001f800  inc     rcx; unsigned __int64
0x18001f803  lea     rdx, [rsp+2F0h+cchLength]; unsigned int *
0x18001f808  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001f80d  mov     ebx, eax
0x18001f80f  test    eax, eax
0x18001f811  js      loc_18001F89B
0x18001f817  mov     ecx, [rsp+2F0h+cchLength]
0x18001f81b  lea     rdx, [rsp+2F0h+cchLength]; unsigned int *
0x18001f820  add     rcx, rcx; unsigned __int64
0x18001f823  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18001f828  mov     ebx, eax
0x18001f82a  test    eax, eax
0x18001f82c  js      short loc_18001F89B
0x18001f82e  mov     edx, [rsp+2F0h+cchLength]; cchLength
0x18001f832  lea     rcx, [rbp+1F0h+Data]; lpsz
0x18001f836  call    cs:__imp_CharLowerBuffW
0x18001f83c  mov     esi, [rsp+2F0h+cchLength]
0x18001f840  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f847  mov     eax, 2
0x18001f84c  mul     rsi
0x18001f84f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f856  cmovb   rax, rcx
0x18001f85a  mov     rcx, rax; unsigned __int64
0x18001f85d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f862  mov     qword ptr [rsp+2F0h+cchLength], rax
0x18001f867  test    rax, rax
0x18001f86a  jz      short loc_18001F898
0x18001f86c  mov     r8d, esi; Size
0x18001f86f  lea     rdx, [rbp+1F0h+Data]; Src
0x18001f873  mov     rcx, rax; void *
0x18001f876  call    memcpy_0
0x18001f87b  lea     rdx, [rsp+2F0h+cchLength]
0x18001f880  mov     rcx, r14
0x18001f883  call    ?push_back@?$list@PEAGV?$allocator@PEAG@utl@@@utl@@QEAA_NAEBQEAG@Z; utl::list<ushort *,utl::allocator<ushort *>>::push_back(ushort * const &)
0x18001f888  test    al, al
0x18001f88a  jz      short loc_18001F898
0x18001f88c  inc     edi
0x18001f88e  mov     esi, 80070000h
0x18001f893  jmp     loc_18001F779
0x18001f898  mov     ebx, r13d
0x18001f89b  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18001f8a0  call    cs:__imp_RegCloseKey
0x18001f8a6  mov     rcx, r15; Block
0x18001f8a9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f8ae  cmp     [r14], r14
0x18001f8b1  jnz     short loc_18001F930
0x18001f8b3  mov     ebx, r12d
0x18001f8b6  lea     rdi, off_1800AF4C0; "certificatestore"
0x18001f8bd  lea     rax, ?mapping@@3PAUCSPPair@@A; CSPPair near * mapping
0x18001f8c4  cmp     rdi, rax
0x18001f8c7  jz      short loc_18001F930
0x18001f8c9  mov     rsi, [rdi]
0x18001f8cc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18001f8d0  mov     rax, rcx
0x18001f8d3  inc     rax
0x18001f8d6  cmp     [rsi+rax*2], r12w
0x18001f8db  jnz     short loc_18001F8D3
0x18001f8dd  lea     r15, ds:2[rax*2]
0x18001f8e5  mov     eax, 2
0x18001f8ea  mul     r15
0x18001f8ed  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f8f4  cmovb   rax, rcx
0x18001f8f8  mov     rcx, rax; unsigned __int64
0x18001f8fb  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001f900  mov     qword ptr [rbp+1F0h+cbData], rax
0x18001f904  test    rax, rax
0x18001f907  jz      short loc_18001F92D
0x18001f909  mov     r8, r15; Size
0x18001f90c  mov     rdx, rsi; Src
0x18001f90f  mov     rcx, rax; void *
0x18001f912  call    memcpy_0
0x18001f917  lea     rdx, [rbp+1F0h+cbData]
0x18001f91b  mov     rcx, r14
0x18001f91e  call    ?push_back@?$list@PEAGV?$allocator@PEAG@utl@@@utl@@QEAA_NAEBQEAG@Z; utl::list<ushort *,utl::allocator<ushort *>>::push_back(ushort * const &)
0x18001f923  test    al, al
0x18001f925  jz      short loc_18001F92D
0x18001f927  add     rdi, 8
0x18001f92b  jmp     short loc_18001F8BD
0x18001f92d  mov     ebx, r13d
0x18001f930  mov     eax, ebx
0x18001f932  mov     rcx, [rbp+1F0h+var_50]
0x18001f939  xor     rcx, rsp; StackCookie
0x18001f93c  call    __security_check_cookie
0x18001f941  add     rsp, 2B8h
0x18001f948  pop     r15
0x18001f94a  pop     r14
0x18001f94c  pop     r13
0x18001f94e  pop     r12
0x18001f950  pop     rdi
0x18001f951  pop     rsi
0x18001f952  pop     rbx
0x18001f953  pop     rbp
0x18001f954  retn
```
