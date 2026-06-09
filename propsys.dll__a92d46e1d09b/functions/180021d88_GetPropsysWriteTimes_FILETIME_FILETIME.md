# GetPropsysWriteTimes(_FILETIME *,_FILETIME *)

- ea: `0x180021d88`
- end: `0x180021f41`
- name: `?GetPropsysWriteTimes@@YAJPEAU_FILETIME@@0@Z`
- size: `441`
- prototype: `__int64 __fastcall(struct _FILETIME *, struct _FILETIME *)`
- caller_count: `4`
- callee_count: `6`
- tags: `reparse_path, loader_planting`

## callers

- `0x1800209d0`
- `0x1800223c4`
- `0x180022448`
- `0x18009011c`

## callees

- `0x180021d88`
- `0x180021f48`
- `0x180021fb4`
- `0x180024418`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021e36`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021e6a`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021e36`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180021e6a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021e18`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180021e18`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021e7d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180021e7d`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180021e54`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x180021e54`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180021ea5`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x180021ea5`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180021f39`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x180021f39`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x180021e3f`
- `api-ms-win-shcore-sysinfo-l1-1-0!IsOS` at `0x180021e3f`

## string_xrefs

- `0x180021e26`: `propsys.dll`
- `0x180021e5a`: `propsys.dll`

## pseudocode

```c
__int64 __fastcall GetPropsysWriteTimes(struct _FILETIME *a1, struct _FILETIME *a2)
{
  int Error; // esi
  UINT SystemWow64DirectoryW; // ebx
  WCHAR *p_Buffer; // rbx
  WCHAR *v7; // rdi
  BOOL v8; // r14d
  PVOID OldValue; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[526]; // [rsp+32h] [rbp-CEh] BYREF
  WCHAR Buffer; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v14[526]; // [rsp+242h] [rbp+142h] BYREF

  *a1 = 0;
  *a2 = 0;
  Buffer = 0;
  Error = 0;
  memset_0(v14, 0, 0x206u);
  pszPath = 0;
  memset_0(v12, 0, 0x206u);
  if ( (unsigned int)_IsPropsysLoadedFromDotLocal() )
  {
    p_Buffer = &g_szPropsysPathDotLocal;
    v7 = &g_szPropsysPathDotLocal;
    goto LABEL_8;
  }
  if ( !GetSystemDirectoryW(&Buffer, 0x104u) )
  {
    Error = ResultFromKnownLastError();
    p_Buffer = 0;
LABEL_17:
    v7 = 0;
    goto LABEL_8;
  }
  PathCchAppend(&Buffer, 0x104u, L"propsys.dll");
  if ( !IsOS(0x28u) )
  {
    p_Buffer = &Buffer;
    goto LABEL_17;
  }
  SystemWow64DirectoryW = GetSystemWow64DirectoryW(&pszPath, 0x104u);
  PathCchAppend(&pszPath, 0x104u, L"propsys.dll");
  if ( SystemWow64DirectoryW && PathFileExistsW(&pszPath) )
    p_Buffer = &pszPath;
  else
    p_Buffer = 0;
  v7 = &Buffer;
LABEL_8:
  OldValue = 0;
  v8 = Wow64DisableWow64FsRedirection(&OldValue);
  if ( p_Buffer )
    Error = GetLastWriteTime(p_Buffer, a1);
  if ( Error >= 0 && v7 )
    Error = GetLastWriteTime(v7, a2);
  if ( v8 )
    Wow64RevertWow64FsRedirection(OldValue);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180021d88  mov     [rsp-8+arg_10], rbx
0x180021d8d  mov     [rsp-8+arg_18], rsi
0x180021d92  push    rbp
0x180021d93  push    rdi
0x180021d94  push    r12
0x180021d96  push    r14
0x180021d98  push    r15
0x180021d9a  lea     rbp, [rsp-360h]
0x180021da2  sub     rsp, 460h
0x180021da9  mov     rax, cs:__security_cookie
0x180021db0  xor     rax, rsp
0x180021db3  mov     [rbp+380h+var_30], rax
0x180021dba  xor     eax, eax
0x180021dbc  mov     r12, rdx
0x180021dbf  mov     [rcx], rax
0x180021dc2  mov     r15, rcx
0x180021dc5  mov     [rdx], rax
0x180021dc8  lea     rcx, [rbp+380h+var_23E]; void *
0x180021dcf  mov     ebx, 206h
0x180021dd4  mov     [rbp+380h+Buffer], ax
0x180021ddb  xor     edx, edx; Val
0x180021ddd  mov     r8d, ebx; Size
0x180021de0  xor     esi, esi
0x180021de2  call    memset_0
0x180021de7  xor     eax, eax
0x180021de9  lea     rcx, [rsp+480h+var_44E]; void *
0x180021dee  mov     r8d, ebx; Size
0x180021df1  mov     [rsp+480h+pszPath], ax
0x180021df6  xor     edx, edx; Val
0x180021df8  call    memset_0
0x180021dfd  call    ?_IsPropsysLoadedFromDotLocal@@YAHXZ; _IsPropsysLoadedFromDotLocal(void)
0x180021e02  test    eax, eax
0x180021e04  jnz     loc_180021F1E
0x180021e0a  mov     edi, 104h
0x180021e0f  lea     rcx, [rbp+380h+Buffer]; lpBuffer
0x180021e16  mov     edx, edi; uSize
0x180021e18  call    cs:__imp_GetSystemDirectoryW
0x180021e1e  test    eax, eax
0x180021e20  jz      loc_180021F08
0x180021e26  lea     r8, pszFullModuleName; "propsys.dll"
0x180021e2d  mov     edx, edi; cchPath
0x180021e2f  lea     rcx, [rbp+380h+Buffer]; pszPath
0x180021e36  call    cs:__imp_PathCchAppend
0x180021e3c  lea     ecx, [rsi+28h]; dwOS
0x180021e3f  call    cs:__imp_IsOS
0x180021e45  test    eax, eax
0x180021e47  jz      loc_180021F15
0x180021e4d  mov     edx, edi; uSize
0x180021e4f  lea     rcx, [rsp+480h+pszPath]; lpBuffer
0x180021e54  call    cs:__imp_GetSystemWow64DirectoryW
0x180021e5a  lea     r8, pszFullModuleName; "propsys.dll"
0x180021e61  mov     edx, edi; cchPath
0x180021e63  lea     rcx, [rsp+480h+pszPath]; pszPath
0x180021e68  mov     ebx, eax
0x180021e6a  call    cs:__imp_PathCchAppend
0x180021e70  test    ebx, ebx
0x180021e72  jz      loc_180021F2D
0x180021e78  lea     rcx, [rsp+480h+pszPath]; pszPath
0x180021e7d  call    cs:__imp_PathFileExistsW
0x180021e83  test    eax, eax
0x180021e85  jz      loc_180021F2D
0x180021e8b  lea     rbx, [rsp+480h+pszPath]
0x180021e90  lea     rdi, [rbp+380h+Buffer]
0x180021e97  lea     rcx, [rsp+480h+OldValue]; OldValue
0x180021e9c  mov     [rsp+480h+OldValue], 0
0x180021ea5  call    cs:__imp_Wow64DisableWow64FsRedirection
0x180021eab  mov     r14d, eax
0x180021eae  test    rbx, rbx
0x180021eb1  jz      short loc_180021EC0
0x180021eb3  mov     rdx, r15; struct _FILETIME *
0x180021eb6  mov     rcx, rbx; unsigned __int16 *
0x180021eb9  call    ?GetLastWriteTime@@YAJPEBGPEAU_FILETIME@@@Z; GetLastWriteTime(ushort const *,_FILETIME *)
0x180021ebe  mov     esi, eax
0x180021ec0  test    esi, esi
0x180021ec2  js      short loc_180021ED6
0x180021ec4  test    rdi, rdi
0x180021ec7  jz      short loc_180021ED6
0x180021ec9  mov     rdx, r12; struct _FILETIME *
0x180021ecc  mov     rcx, rdi; unsigned __int16 *
0x180021ecf  call    ?GetLastWriteTime@@YAJPEBGPEAU_FILETIME@@@Z; GetLastWriteTime(ushort const *,_FILETIME *)
0x180021ed4  mov     esi, eax
0x180021ed6  test    r14d, r14d
0x180021ed9  jnz     short loc_180021F34
0x180021edb  mov     eax, esi
0x180021edd  mov     rcx, [rbp+380h+var_30]
0x180021ee4  xor     rcx, rsp; StackCookie
0x180021ee7  call    __security_check_cookie
0x180021eec  lea     r11, [rsp+480h+var_20]
0x180021ef4  mov     rbx, [r11+40h]
0x180021ef8  mov     rsi, [r11+48h]
0x180021efc  mov     rsp, r11
0x180021eff  pop     r15
0x180021f01  pop     r14
0x180021f03  pop     r12
0x180021f05  pop     rdi
0x180021f06  pop     rbp
0x180021f07  retn
0x180021f08  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180021f0d  mov     esi, eax
0x180021f0f  xor     ebx, ebx
0x180021f11  xor     edi, edi
0x180021f13  jmp     short loc_180021E97
0x180021f15  lea     rbx, [rbp+380h+Buffer]
0x180021f1c  jmp     short loc_180021F11
0x180021f1e  lea     rbx, ?g_szPropsysPathDotLocal@@3PAGA; ushort near * g_szPropsysPathDotLocal
0x180021f25  mov     rdi, rbx
0x180021f28  jmp     loc_180021E97
0x180021f2d  xor     ebx, ebx
0x180021f2f  jmp     loc_180021E90
0x180021f34  mov     rcx, [rsp+480h+OldValue]; OlValue
0x180021f39  call    cs:__imp_Wow64RevertWow64FsRedirection
0x180021f3f  jmp     short loc_180021EDB
```
