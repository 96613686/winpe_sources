# GetClusterSharedVolumeNameForFile

- ea: `0x18002e500`
- end: `0x18002e7c2`
- name: `GetClusterSharedVolumeNameForFile`
- size: `706`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpszFileName@<rcx>, LPCWSTR lpszVolumeMountPoint@<rdx>, __int64, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path`

## callees

- `0x180002f50`
- `0x18001cc08`
- `0x18001ce30`
- `0x18001dc5c`
- `0x180029578`
- `0x18002e500`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002e620`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002e603`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x18002e603`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002e616`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18002e616`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall GetClusterSharedVolumeNameForFile(
        LPCWSTR lpszFileName,
        WCHAR *lpszVolumeMountPoint,
        DWORD *a3,
        WCHAR *a4,
        DWORD *a5,
        int a6)
{
  DWORD v10; // r8d
  DWORD v11; // r12d
  DWORD LastError; // [rsp+20h] [rbp-168h]
  _BYTE v14[32]; // [rsp+28h] [rbp-160h] BYREF
  _BYTE v15[32]; // [rsp+48h] [rbp-140h] BYREF
  _BYTE v16[32]; // [rsp+68h] [rbp-120h] BYREF
  _BYTE v17[32]; // [rsp+88h] [rbp-100h] BYREF
  _BYTE v18[32]; // [rsp+A8h] [rbp-E0h] BYREF
  _BYTE v19[32]; // [rsp+C8h] [rbp-C0h] BYREF
  _BYTE v20[32]; // [rsp+E8h] [rbp-A0h] BYREF
  _BYTE v21[32]; // [rsp+108h] [rbp-80h] BYREF
  _BYTE v22[32]; // [rsp+128h] [rbp-60h] BYREF

  LastError = 0;
  std::wstring::wstring(v22);
  std::wstring::wstring(v21);
  std::wstring::wstring(v20);
  std::wstring::wstring(v19);
  std::wstring::wstring(v18);
  std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(v14);
  std::wstring::wstring(v17);
  std::wstring::wstring(v16);
  std::wstring::wstring(v15);
  v10 = 0;
  v11 = 0;
  if ( a3 )
  {
    v10 = *a3;
    *a3 = 0;
  }
  if ( a5 )
  {
    v11 = *a5;
    *a5 = 0;
  }
  if ( lpszFileName && *lpszFileName && lpszVolumeMountPoint && a3 && a4 && a5 && a6 )
  {
    if ( !GetVolumePathNameW(lpszFileName, lpszVolumeMountPoint, v10)
      || !GetVolumeNameForVolumeMountPointW(lpszVolumeMountPoint, a4, v11) )
    {
      LastError = GetLastError();
    }
    std::wstring::_Tidy_deallocate(v15);
    std::wstring::_Tidy_deallocate(v16);
    std::wstring::_Tidy_deallocate(v17);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v14);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(v22);
    return LastError;
  }
  else
  {
    std::wstring::_Tidy_deallocate(v15);
    std::wstring::_Tidy_deallocate(v16);
    std::wstring::_Tidy_deallocate(v17);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v14);
    std::wstring::_Tidy_deallocate(v18);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v21);
    std::wstring::_Tidy_deallocate(v22);
    return 87;
  }
}

```

## disassembly

```asm
0x18002e500  mov     r11, rsp
0x18002e503  push    rbx
0x18002e504  push    rsi
0x18002e505  push    rdi
0x18002e506  push    r12
0x18002e508  push    r13
0x18002e50a  push    r14
0x18002e50c  push    r15
0x18002e50e  sub     rsp, 150h
0x18002e515  mov     rax, cs:__security_cookie
0x18002e51c  xor     rax, rsp
0x18002e51f  mov     [rsp+188h+var_40], rax
0x18002e527  mov     r15, r9
0x18002e52a  mov     rdi, r8
0x18002e52d  mov     r14, rdx
0x18002e530  mov     rsi, rcx
0x18002e533  mov     rbx, [rsp+188h+arg_20]
0x18002e53b  xor     r13d, r13d
0x18002e53e  mov     [rsp+188h+var_168], r13d
0x18002e543  lea     rcx, [r11-60h]
0x18002e547  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e54c  nop
0x18002e54d  lea     rcx, [rsp+188h+var_80]
0x18002e555  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e55a  nop
0x18002e55b  lea     rcx, [rsp+188h+var_A0]
0x18002e563  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e568  nop
0x18002e569  lea     rcx, [rsp+188h+var_C0]
0x18002e571  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e576  nop
0x18002e577  lea     rcx, [rsp+188h+var_E0]
0x18002e57f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e584  nop
0x18002e585  lea     rcx, [rsp+188h+var_160]
0x18002e58a  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::wstring>::map<std::wstring,std::wstring>(void)
0x18002e58f  lea     rcx, [rsp+188h+var_100]
0x18002e597  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e59c  lea     rcx, [rsp+188h+var_120]
0x18002e5a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e5a6  lea     rcx, [rsp+188h+var_140]
0x18002e5ab  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002e5b0  mov     r8d, r13d
0x18002e5b3  mov     r12d, r13d
0x18002e5b6  test    rdi, rdi
0x18002e5b9  jz      short loc_18002E5C1
0x18002e5bb  mov     r8d, [rdi]; cchBufferLength
0x18002e5be  mov     [rdi], r13d
0x18002e5c1  test    rbx, rbx
0x18002e5c4  jz      short loc_18002E5CC
0x18002e5c6  mov     r12d, [rbx]
0x18002e5c9  mov     [rbx], r13d
0x18002e5cc  test    rsi, rsi
0x18002e5cf  jz      loc_18002E6AA
0x18002e5d5  cmp     [rsi], r13w
0x18002e5d9  jz      loc_18002E6AA
0x18002e5df  test    r14, r14
0x18002e5e2  jz      short loc_18002E62F
0x18002e5e4  test    rdi, rdi
0x18002e5e7  jz      short loc_18002E62F
0x18002e5e9  test    r15, r15
0x18002e5ec  jz      short loc_18002E62F
0x18002e5ee  test    rbx, rbx
0x18002e5f1  jz      short loc_18002E62F
0x18002e5f3  cmp     [rsp+188h+arg_28], r13d
0x18002e5fb  jz      short loc_18002E62F
0x18002e5fd  mov     rdx, r14; lpszVolumePathName
0x18002e600  mov     rcx, rsi; lpszFileName
0x18002e603  call    cs:__imp_GetVolumePathNameW
0x18002e609  test    eax, eax
0x18002e60b  jz      short loc_18002E620
0x18002e60d  mov     r8d, r12d; cchBufferLength
0x18002e610  mov     rdx, r15; lpszVolumeName
0x18002e613  mov     rcx, r14; lpszVolumeMountPoint
0x18002e616  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x18002e61c  test    eax, eax
0x18002e61e  jnz     short loc_18002E62A
0x18002e620  call    cs:__imp_GetLastError
0x18002e626  mov     [rsp+188h+var_168], eax
0x18002e62a  jmp     loc_18002E72A
0x18002e62f  lea     rcx, [rsp+188h+var_140]
0x18002e634  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e639  lea     rcx, [rsp+188h+var_120]
0x18002e63e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e643  lea     rcx, [rsp+188h+var_100]
0x18002e64b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e650  lea     rcx, [rsp+188h+var_160]
0x18002e655  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002e65a  nop
0x18002e65b  lea     rcx, [rsp+188h+var_E0]
0x18002e663  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e668  nop
0x18002e669  lea     rcx, [rsp+188h+var_C0]
0x18002e671  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e676  nop
0x18002e677  lea     rcx, [rsp+188h+var_A0]
0x18002e67f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e684  nop
0x18002e685  lea     rcx, [rsp+188h+var_80]
0x18002e68d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e692  nop
0x18002e693  lea     rcx, [rsp+188h+var_60]
0x18002e69b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6a0  mov     eax, 57h ; 'W'
0x18002e6a5  jmp     loc_18002E79F
0x18002e6aa  lea     rcx, [rsp+188h+var_140]
0x18002e6af  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6b4  lea     rcx, [rsp+188h+var_120]
0x18002e6b9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6be  lea     rcx, [rsp+188h+var_100]
0x18002e6c6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6cb  lea     rcx, [rsp+188h+var_160]
0x18002e6d0  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002e6d5  nop
0x18002e6d6  lea     rcx, [rsp+188h+var_E0]
0x18002e6de  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6e3  nop
0x18002e6e4  lea     rcx, [rsp+188h+var_C0]
0x18002e6ec  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6f1  nop
0x18002e6f2  lea     rcx, [rsp+188h+var_A0]
0x18002e6fa  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e6ff  nop
0x18002e700  lea     rcx, [rsp+188h+var_80]
0x18002e708  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e70d  nop
0x18002e70e  lea     rcx, [rsp+188h+var_60]
0x18002e716  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e71b  mov     eax, 57h ; 'W'
0x18002e720  jmp     short loc_18002E79F
0x18002e722  jmp     short loc_18002E72A
0x18002e724  jmp     short loc_18002E72A
0x18002e726  jmp     short loc_18002E72A
0x18002e728  jmp     short $+2
0x18002e72a  lea     rcx, [rsp+188h+var_140]
0x18002e72f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e734  lea     rcx, [rsp+188h+var_120]
0x18002e739  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e73e  lea     rcx, [rsp+188h+var_100]
0x18002e746  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e74b  lea     rcx, [rsp+188h+var_160]
0x18002e750  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(void)
0x18002e755  nop
0x18002e756  lea     rcx, [rsp+188h+var_E0]
0x18002e75e  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e763  nop
0x18002e764  lea     rcx, [rsp+188h+var_C0]
0x18002e76c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e771  nop
0x18002e772  lea     rcx, [rsp+188h+var_A0]
0x18002e77a  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e77f  nop
0x18002e780  lea     rcx, [rsp+188h+var_80]
0x18002e788  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e78d  nop
0x18002e78e  lea     rcx, [rsp+188h+var_60]
0x18002e796  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e79b  mov     eax, [rsp+188h+var_168]
0x18002e79f  mov     rcx, [rsp+188h+var_40]
0x18002e7a7  xor     rcx, rsp; StackCookie
0x18002e7aa  call    __security_check_cookie
0x18002e7af  add     rsp, 150h
0x18002e7b6  pop     r15
0x18002e7b8  pop     r14
0x18002e7ba  pop     r13
0x18002e7bc  pop     r12
0x18002e7be  pop     rdi
0x18002e7bf  pop     rsi
0x18002e7c0  pop     rbx
0x18002e7c1  retn
```
