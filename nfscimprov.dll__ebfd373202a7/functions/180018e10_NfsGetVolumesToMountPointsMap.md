# NfsGetVolumesToMountPointsMap

- ea: `0x180018e10`
- end: `0x180019009`
- name: `NfsGetVolumesToMountPointsMap`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path`

## callers

- `0x180019010`

## callees

- `0x180009704`
- `0x18000eae4`
- `0x180016e80`
- `0x180018230`
- `0x1800182b8`
- `0x1800185dc`
- `0x180018e10`
- `0x18001c028`
- `0x18001cba0`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180018e55`
- `KERNEL32!GetLastError` at `0x180018e8c`
- `KERNEL32!GetLastError` at `0x180018fab`
- `KERNEL32!GetLastError` at `0x180018fc6`
- `KERNEL32!GetLastError` at `0x180018e55`
- `KERNEL32!GetLastError` at `0x180018e8c`
- `KERNEL32!GetLastError` at `0x180018fab`
- `KERNEL32!GetLastError` at `0x180018fc6`
- `KERNEL32!LocalFree` at `0x180018f7e`
- `KERNEL32!LocalFree` at `0x180018fc0`
- `KERNEL32!LocalFree` at `0x180018f7e`
- `KERNEL32!LocalFree` at `0x180018fc0`
- `KERNEL32!FindFirstVolumeW` at `0x180018e46`
- `KERNEL32!FindFirstVolumeW` at `0x180018e46`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180018e82`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180018ec8`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180018e82`
- `KERNEL32!GetVolumePathNamesForVolumeNameW` at `0x180018ec8`
- `KERNEL32!LocalAlloc` at `0x180018ea6`
- `KERNEL32!LocalAlloc` at `0x180018ea6`
- `KERNEL32!FindNextVolumeW` at `0x180018f92`
- `KERNEL32!FindNextVolumeW` at `0x180018f92`
- `KERNEL32!FindVolumeClose` at `0x180018fe2`
- `KERNEL32!FindVolumeClose` at `0x180018fe2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
DWORD __fastcall NfsGetVolumesToMountPointsMap(__int64 a1)
{
  HANDLE FirstVolumeW; // rsi
  WCHAR *v4; // rax
  WCHAR *v5; // rbx
  WCHAR *v6; // rdi
  __int64 v7; // rdx
  __int64 v9; // rdx
  _BYTE *v10; // rdi
  __int64 v11; // r8
  DWORD v12; // eax
  DWORD LastError; // ebx
  char v14; // [rsp+20h] [rbp-E0h]
  DWORD cchReturnLength; // [rsp+24h] [rbp-DCh] BYREF
  _BYTE v16[16]; // [rsp+28h] [rbp-D8h] BYREF
  char v17[16]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v18[40]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR szVolumeName[264]; // [rsp+70h] [rbp-90h] BYREF

  FirstVolumeW = FindFirstVolumeW(szVolumeName, 0x104u);
  if ( FirstVolumeW == (HANDLE)-1LL )
    return GetLastError();
  while ( 1 )
  {
    cchReturnLength = 0;
    std::set<std::wstring>::set<std::wstring>(v16);
    if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, 0, 0, &cchReturnLength) && GetLastError() != 234 )
      goto LABEL_21;
    v4 = (WCHAR *)LocalAlloc(0, 2LL * cchReturnLength);
    v5 = v4;
    if ( !v4 )
    {
      LastError = 8;
      goto LABEL_23;
    }
    if ( !GetVolumePathNamesForVolumeNameW(szVolumeName, v4, cchReturnLength, 0) )
    {
      LocalFree(v5);
LABEL_21:
      LastError = GetLastError();
      goto LABEL_23;
    }
    if ( *v5 )
    {
      v6 = v5;
      do
      {
        std::wstring::wstring(v18, v6);
        std::set<std::wstring>::insert(v16, v17, v18);
        LOBYTE(v7) = 1;
        std::wstring::_Tidy(v18, v7, 0);
        while ( *v6++ )
          ;
      }
      while ( *v6 );
      std::wstring::wstring(v18, szVolumeName);
      v10 = (_BYTE *)std::map<std::wstring,std::set<std::wstring>>::operator[](a1, v18);
      if ( v10 != v16 )
      {
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(v10);
        LOBYTE(v11) = v14;
        std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy<std::integral_constant<bool,0>>(
          v10,
          v16,
          v11);
      }
      LOBYTE(v9) = 1;
      std::wstring::_Tidy(v18, v9, 0);
    }
    LocalFree(v5);
    if ( !FindNextVolumeW(FirstVolumeW, szVolumeName, 0x104u) )
      break;
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v16);
  }
  v12 = GetLastError();
  LastError = 0;
  if ( v12 != 18 )
    LastError = v12;
LABEL_23:
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(v16);
  FindVolumeClose(FirstVolumeW);
  return LastError;
}

```

## disassembly

```asm
0x180018e10  push    rbp
0x180018e12  push    rbx
0x180018e13  push    rsi
0x180018e14  push    rdi
0x180018e15  push    r14
0x180018e17  push    r15
0x180018e19  lea     rbp, [rsp-198h]
0x180018e21  sub     rsp, 298h
0x180018e28  mov     rax, cs:__security_cookie
0x180018e2f  xor     rax, rsp
0x180018e32  mov     [rbp+1C0h+var_40], rax
0x180018e39  mov     r14, rcx
0x180018e3c  mov     edx, 104h; cchBufferLength
0x180018e41  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180018e46  call    cs:__imp_FindFirstVolumeW
0x180018e4c  mov     rsi, rax
0x180018e4f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018e53  jnz     short loc_180018E60
0x180018e55  call    cs:__imp_GetLastError
0x180018e5b  jmp     loc_180018FEA
0x180018e60  xor     r15d, r15d
0x180018e63  mov     [rsp+2C0h+cchReturnLength], r15d
0x180018e68  lea     rcx, [rsp+2C0h+var_298]
0x180018e6d  call    ??0?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring>::set<std::wstring>(void)
0x180018e72  nop
0x180018e73  lea     r9, [rsp+2C0h+cchReturnLength]; lpcchReturnLength
0x180018e78  xor     r8d, r8d; cchBufferLength
0x180018e7b  xor     edx, edx; lpszVolumePathNames
0x180018e7d  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180018e82  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180018e88  test    eax, eax
0x180018e8a  jnz     short loc_180018E9D
0x180018e8c  call    cs:__imp_GetLastError
0x180018e92  cmp     eax, 0EAh
0x180018e97  jnz     loc_180018FC6
0x180018e9d  mov     edx, [rsp+2C0h+cchReturnLength]
0x180018ea1  add     rdx, rdx; uBytes
0x180018ea4  xor     ecx, ecx; uFlags
0x180018ea6  call    cs:__imp_LocalAlloc
0x180018eac  mov     rbx, rax
0x180018eaf  test    rax, rax
0x180018eb2  jz      loc_180018FD0
0x180018eb8  xor     r9d, r9d; lpcchReturnLength
0x180018ebb  mov     r8d, [rsp+2C0h+cchReturnLength]; cchBufferLength
0x180018ec0  mov     rdx, rax; lpszVolumePathNames
0x180018ec3  lea     rcx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180018ec8  call    cs:__imp_GetVolumePathNamesForVolumeNameW
0x180018ece  test    eax, eax
0x180018ed0  jz      loc_180018FBD
0x180018ed6  cmp     [rbx], r15w
0x180018eda  jz      loc_180018F7B
0x180018ee0  mov     rdi, rbx
0x180018ee3  mov     rdx, rdi
0x180018ee6  lea     rcx, [rsp+2C0h+var_278]
0x180018eeb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018ef0  nop
0x180018ef1  lea     r8, [rsp+2C0h+var_278]
0x180018ef6  lea     rdx, [rsp+2C0h+var_288]
0x180018efb  lea     rcx, [rsp+2C0h+var_298]
0x180018f00  call    ?insert@?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@2@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::set<std::wstring>::insert(std::wstring &&)
0x180018f05  nop
0x180018f06  xor     r8d, r8d
0x180018f09  mov     dl, 1
0x180018f0b  lea     rcx, [rsp+2C0h+var_278]
0x180018f10  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018f15  movzx   eax, word ptr [rdi]
0x180018f18  add     rdi, 2
0x180018f1c  test    ax, ax
0x180018f1f  jnz     short loc_180018F15
0x180018f21  cmp     [rdi], r15w
0x180018f25  jnz     short loc_180018EE3
0x180018f27  lea     rdx, [rsp+2C0h+szVolumeName]
0x180018f2c  lea     rcx, [rsp+2C0h+var_278]
0x180018f31  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180018f36  nop
0x180018f37  lea     rdx, [rsp+2C0h+var_278]
0x180018f3c  mov     rcx, r14
0x180018f3f  call    ??A?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@@std@@@2@@std@@QEAAAEAV?$set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::map<std::wstring,std::set<std::wstring>>::operator[](std::wstring &&)
0x180018f44  mov     rdi, rax
0x180018f47  lea     rax, [rsp+2C0h+var_298]
0x180018f4c  cmp     rdi, rax
0x180018f4f  jz      short loc_180018F6C
0x180018f51  mov     rcx, rdi
0x180018f54  call    ?clear@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::clear(void)
0x180018f59  mov     r8b, [rsp+2C0h+var_2A0]
0x180018f5e  lea     rdx, [rsp+2C0h+var_298]
0x180018f63  mov     rcx, rdi
0x180018f66  call    ??$_Copy@U?$integral_constant@_N$0A@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEAAXAEBV01@U?$integral_constant@_N$0A@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Copy<std::integral_constant<bool,0>>(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>> const &,std::integral_constant<bool,0>)
0x180018f6b  nop
0x180018f6c  xor     r8d, r8d
0x180018f6f  mov     dl, 1
0x180018f71  lea     rcx, [rsp+2C0h+var_278]
0x180018f76  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180018f7b  mov     rcx, rbx; hMem
0x180018f7e  call    cs:__imp_LocalFree
0x180018f84  mov     r8d, 104h; cchBufferLength
0x180018f8a  lea     rdx, [rsp+2C0h+szVolumeName]; lpszVolumeName
0x180018f8f  mov     rcx, rsi; hFindVolume
0x180018f92  call    cs:__imp_FindNextVolumeW
0x180018f98  test    eax, eax
0x180018f9a  jz      short loc_180018FAB
0x180018f9c  lea     rcx, [rsp+2C0h+var_298]
0x180018fa1  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180018fa6  jmp     loc_180018E63
0x180018fab  call    cs:__imp_GetLastError
0x180018fb1  nop
0x180018fb2  mov     ebx, r15d
0x180018fb5  cmp     eax, 12h
0x180018fb8  cmovnz  ebx, eax
0x180018fbb  jmp     short loc_180018FD5
0x180018fbd  mov     rcx, rbx; hMem
0x180018fc0  call    cs:__imp_LocalFree
0x180018fc6  call    cs:__imp_GetLastError
0x180018fcc  mov     ebx, eax
0x180018fce  jmp     short loc_180018FD5
0x180018fd0  mov     ebx, 8
0x180018fd5  lea     rcx, [rsp+2C0h+var_298]
0x180018fda  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>(void)
0x180018fdf  mov     rcx, rsi; hFindVolume
0x180018fe2  call    cs:__imp_FindVolumeClose
0x180018fe8  mov     eax, ebx
0x180018fea  mov     rcx, [rbp+1C0h+var_40]
0x180018ff1  xor     rcx, rsp; StackCookie
0x180018ff4  call    __security_check_cookie
0x180018ff9  add     rsp, 298h
0x180019000  pop     r15
0x180019002  pop     r14
0x180019004  pop     rdi
0x180019005  pop     rsi
0x180019006  pop     rbx
0x180019007  pop     rbp
0x180019008  retn
```
