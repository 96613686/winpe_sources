# ReadWPPTracingState

- ea: `0x1800bcf34`
- end: `0x1800bd182`
- name: `ReadWPPTracingState`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800bcccc`

## callees

- `0x18007e3a8`
- `0x1800b1004`
- `0x1800bb930`
- `0x1800bc6d8`
- `0x1800bca58`
- `0x1800bcf04`
- `0x1800bcf34`
- `0x1800bd188`
- `0x1800bd1c8`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcffa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcffa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd14f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bd14f`
- `ntdll!wcsnlen` at `0x1800bd06b`
- `ntdll!wcsnlen` at `0x1800bd06b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd0fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bd0fe`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800bd0cd`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800bd0cd`

## string_xrefs

- `0x1800bcfbe`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\Tracing\Microsoft\RemoteAccess\`

## pseudocode

```c
__int64 __fastcall ReadWPPTracingState(__int64 a1, _DWORD *a2, __int64 *a3)
{
  unsigned int v6; // r15d
  wchar_t *v7; // rbx
  wchar_t *v8; // rsi
  int String; // eax
  int v10; // eax
  int v11; // eax
  void *FolderHandle; // rax
  void *v13; // r14
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *Source; // [rsp+38h] [rbp-C8h]
  STRSAFE_PCNZWCH pszSrc; // [rsp+40h] [rbp-C0h]
  wchar_t pszDest[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[524]; // [rsp+54h] [rbp-ACh] BYREF

  hKey = 0;
  *(_DWORD *)pszDest = 0;
  v6 = 0;
  memset_0(v19, 0, 0x206u);
  Source = 0;
  v7 = 0;
  pszSrc = 0;
  v8 = 0;
  if ( a1 )
  {
    if ( *(_QWORD *)(a1 + 32) )
    {
      StringCchPrintfW(
        pszDest,
        0x105u,
        L"%s%s",
        L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\Microsoft\\RemoteAccess\\",
        a1 + 562);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &hKey) )
      {
        RegReadDword(hKey, L"Active", a1);
        RegReadDword(hKey, L"ControlFlags", a1 + 4);
        RegReadDword(hKey, L"ControlLevel", a1 + 8);
        String = RegReadString(hKey, L"Guid");
        v8 = Source;
        if ( !String )
        {
          v10 = wcsnlen(Source, 0x10u);
          ConvertString2Guid(v8, (unsigned int)(2 * v10), a1 + 12);
        }
        v11 = RegReadString(hKey, L"LogFileName");
        v7 = (wchar_t *)pszSrc;
        if ( v11 || !pszSrc )
          goto LABEL_12;
        StringCchCopyNW(pszDest, 0x105u, pszSrc, 0x105u);
        if ( !PathCchRemoveFileSpec(pszDest, 0x105u) )
        {
          FolderHandle = (void *)GetFolderHandle(pszDest);
          v13 = FolderHandle;
          if ( FolderHandle != (void *)-1LL )
          {
            *a3 = GetFileHandle((__int64)pszDest, FolderHandle);
            CloseHandle(v13);
            if ( *a3 != -1 )
            {
              *a2 = 1;
              StringCchCopyNW(
                (STRSAFE_LPWSTR)(*(_QWORD *)(a1 + 32) + *(unsigned int *)(*(_QWORD *)(a1 + 32) + 112LL)),
                0x105u,
                v7,
                0x105u);
LABEL_12:
              v6 = 1;
            }
          }
        }
      }
    }
  }
  MemoryFree(v7);
  MemoryFree(v8);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800bcf34  mov     [rsp-8+arg_18], rbx
0x1800bcf39  push    rbp
0x1800bcf3a  push    rsi
0x1800bcf3b  push    rdi
0x1800bcf3c  push    r12
0x1800bcf3e  push    r13
0x1800bcf40  push    r14
0x1800bcf42  push    r15
0x1800bcf44  lea     rbp, [rsp-170h]
0x1800bcf4c  sub     rsp, 270h
0x1800bcf53  mov     rax, cs:__security_cookie
0x1800bcf5a  xor     rax, rsp
0x1800bcf5d  mov     [rbp+1A0h+var_40], rax
0x1800bcf64  xor     r14d, r14d
0x1800bcf67  mov     r12, r8
0x1800bcf6a  mov     r13, rdx
0x1800bcf6d  mov     [rsp+2A0h+hKey], r14
0x1800bcf72  mov     rdi, rcx
0x1800bcf75  mov     dword ptr [rsp+2A0h+pszDest], r14d
0x1800bcf7a  xor     edx, edx; Val
0x1800bcf7c  lea     rcx, [rsp+2A0h+var_24C]; void *
0x1800bcf81  mov     r8d, 206h; Size
0x1800bcf87  mov     r15d, r14d
0x1800bcf8a  call    memset_0
0x1800bcf8f  mov     [rsp+2A0h+Source], r14
0x1800bcf94  mov     ebx, r14d
0x1800bcf97  mov     [rsp+2A0h+pszSrc], rbx
0x1800bcf9c  mov     esi, r14d
0x1800bcf9f  test    rdi, rdi
0x1800bcfa2  jz      loc_1800BD135
0x1800bcfa8  cmp     [rdi+20h], r14
0x1800bcfac  jz      loc_1800BD135
0x1800bcfb2  lea     rax, [rdi+232h]
0x1800bcfb9  mov     edx, 105h; cchDest
0x1800bcfbe  lea     r9, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800bcfc5  mov     [rsp+2A0h+phkResult], rax
0x1800bcfca  lea     r8, aSS_3; "%s%s"
0x1800bcfd1  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bcfd6  call    StringCchPrintfW
0x1800bcfdb  lea     rax, [rsp+2A0h+hKey]
0x1800bcfe0  mov     r9d, 20019h; samDesired
0x1800bcfe6  xor     r8d, r8d; ulOptions
0x1800bcfe9  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800bcfee  lea     rdx, [rsp+2A0h+pszDest]; lpSubKey
0x1800bcff3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bcffa  call    cs:__imp_RegOpenKeyExW
0x1800bd000  test    eax, eax
0x1800bd002  jnz     loc_1800BD135
0x1800bd008  mov     rcx, [rsp+2A0h+hKey]
0x1800bd00d  lea     rdx, aActive; "Active"
0x1800bd014  mov     r8, rdi
0x1800bd017  call    RegReadDword
0x1800bd01c  mov     rcx, [rsp+2A0h+hKey]
0x1800bd021  lea     r8, [rdi+4]
0x1800bd025  lea     rdx, aControlflags; "ControlFlags"
0x1800bd02c  call    RegReadDword
0x1800bd031  mov     rcx, [rsp+2A0h+hKey]
0x1800bd036  lea     r8, [rdi+8]
0x1800bd03a  lea     rdx, aControllevel; "ControlLevel"
0x1800bd041  call    RegReadDword
0x1800bd046  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800bd04b  lea     r8, [rsp+2A0h+Source]
0x1800bd050  lea     rdx, aGuid_0; "Guid"
0x1800bd057  call    RegReadString
0x1800bd05c  mov     rsi, [rsp+2A0h+Source]
0x1800bd061  test    eax, eax
0x1800bd063  jnz     short loc_1800BD080
0x1800bd065  lea     edx, [rax+10h]; MaxCount
0x1800bd068  mov     rcx, rsi; Source
0x1800bd06b  call    cs:__imp_wcsnlen
0x1800bd071  lea     r8, [rdi+0Ch]
0x1800bd075  mov     rcx, rsi
0x1800bd078  lea     edx, [rax+rax]
0x1800bd07b  call    ConvertString2Guid
0x1800bd080  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800bd085  lea     r8, [rsp+2A0h+pszSrc]
0x1800bd08a  lea     rdx, aLogfilename; "LogFileName"
0x1800bd091  call    RegReadString
0x1800bd096  mov     rbx, [rsp+2A0h+pszSrc]
0x1800bd09b  test    eax, eax
0x1800bd09d  jnz     loc_1800BD12F
0x1800bd0a3  test    rbx, rbx
0x1800bd0a6  jz      loc_1800BD12F
0x1800bd0ac  mov     eax, 105h
0x1800bd0b1  lea     rcx, [rsp+2A0h+pszDest]; pszDest
0x1800bd0b6  mov     r9d, eax; cchToCopy
0x1800bd0b9  mov     edx, eax; cchDest
0x1800bd0bb  mov     r8, rbx; pszSrc
0x1800bd0be  call    StringCchCopyNW
0x1800bd0c3  mov     edx, 105h; cchPath
0x1800bd0c8  lea     rcx, [rsp+2A0h+pszDest]; pszPath
0x1800bd0cd  call    cs:__imp_PathCchRemoveFileSpec
0x1800bd0d3  test    eax, eax
0x1800bd0d5  jnz     short loc_1800BD135
0x1800bd0d7  lea     rcx, [rsp+2A0h+pszDest]; String1
0x1800bd0dc  call    GetFolderHandle
0x1800bd0e1  mov     r14, rax
0x1800bd0e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bd0e8  jz      short loc_1800BD135
0x1800bd0ea  mov     rdx, rax
0x1800bd0ed  lea     rcx, [rsp+2A0h+pszDest]
0x1800bd0f2  call    GetFileHandle
0x1800bd0f7  mov     rcx, r14; hObject
0x1800bd0fa  mov     [r12], rax
0x1800bd0fe  call    cs:__imp_CloseHandle
0x1800bd104  cmp     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x1800bd109  jz      short loc_1800BD135
0x1800bd10b  mov     dword ptr [r13+0], 1
0x1800bd113  mov     r8, rbx; pszSrc
0x1800bd116  mov     rax, [rdi+20h]
0x1800bd11a  mov     ecx, [rax+70h]
0x1800bd11d  add     rcx, rax; pszDest
0x1800bd120  mov     eax, 105h
0x1800bd125  mov     r9d, eax; cchToCopy
0x1800bd128  mov     edx, eax; cchDest
0x1800bd12a  call    StringCchCopyNW
0x1800bd12f  mov     r15d, 1
0x1800bd135  mov     rcx, rbx; lpMem
0x1800bd138  call    MemoryFree
0x1800bd13d  mov     rcx, rsi; lpMem
0x1800bd140  call    MemoryFree
0x1800bd145  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800bd14a  test    rcx, rcx
0x1800bd14d  jz      short loc_1800BD155
0x1800bd14f  call    cs:__imp_RegCloseKey
0x1800bd155  mov     eax, r15d
0x1800bd158  mov     rcx, [rbp+1A0h+var_40]
0x1800bd15f  xor     rcx, rsp; StackCookie
0x1800bd162  call    __security_check_cookie
0x1800bd167  mov     rbx, [rsp+2A0h+arg_18]
0x1800bd16f  add     rsp, 270h
0x1800bd176  pop     r15
0x1800bd178  pop     r14
0x1800bd17a  pop     r13
0x1800bd17c  pop     r12
0x1800bd17e  pop     rdi
0x1800bd17f  pop     rsi
0x1800bd180  pop     rbp
0x1800bd181  retn
```
