# OutOfProcessExceptionEventCallback(void *,_WER_RUNTIME_EXCEPTION_INFORMATION const *,int *,ushort *,ulong *,ulong *)

- ea: `0x180062d50`
- end: `0x180062ebc`
- name: `?OutOfProcessExceptionEventCallback@@YAJPEAXPEBU_WER_RUNTIME_EXCEPTION_INFORMATION@@PEAHPEAGPEAK4@Z`
- size: `364`
- prototype: `int(void *, const struct _WER_RUNTIME_EXCEPTION_INFORMATION *, int *, unsigned __int16 *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180031670`
- `0x18004f890`
- `0x180053a98`
- `0x180062d50`
- `0x180083c10`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180062dec`
- `msvcrt!_wcsicmp` at `0x180062e0b`
- `msvcrt!_wcsicmp` at `0x180062e2a`
- `msvcrt!_wcsicmp` at `0x180062e49`
- `msvcrt!_wcsicmp` at `0x180062dec`
- `msvcrt!_wcsicmp` at `0x180062e0b`
- `msvcrt!_wcsicmp` at `0x180062e2a`
- `msvcrt!_wcsicmp` at `0x180062e49`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180062daf`
- `api-ms-win-core-psapi-l1-1-0!K32GetModuleFileNameExW` at `0x180062daf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062ddc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062dfb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062e1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062e39`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062ddc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062dfb`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062e1a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180062e39`

## pseudocode

```c
__int64 __fastcall OutOfProcessExceptionEventCallback(
        void *a1,
        const struct _WER_RUNTIME_EXCEPTION_INFORMATION *a2,
        int *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        unsigned int *a6)
{
  const char *v8; // r9
  const wchar_t *FileNameW; // rax
  const wchar_t *v11; // rax
  const wchar_t *v12; // rax
  const wchar_t *v13; // rax
  int v14; // eax
  unsigned int v15; // ebx
  int Filename[132]; // [rsp+20h] [rbp-238h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  *a3 = 0;
  if ( a2->exceptionRecord.ExceptionCode == -805306369 )
  {
    if ( !K32GetModuleFileNameExW(a2->hProcess, 0, (LPWSTR)Filename, 0x104u) )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x113,
               (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
               v8);
    FileNameW = PathFindFileNameW((LPCWSTR)Filename);
    if ( !_wcsicmp(FileNameW, L"microsoftedgecp.exe")
      || (v11 = PathFindFileNameW((LPCWSTR)Filename), !_wcsicmp(v11, L"microsoftedgebchost.exe"))
      || (v12 = PathFindFileNameW((LPCWSTR)Filename), !_wcsicmp(v12, L"microsoftedgedevtools.exe"))
      || (v13 = PathFindFileNameW((LPCWSTR)Filename), !_wcsicmp(v13, L"microsoftedge.exe")) )
    {
      v14 = StringCchCopyW(a4, *a5, L"MoAppHang");
      v15 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11B,
          (unsigned int)"onecoreuap\\inetcore\\iertutil\\werexceptionhandler.cpp",
          (const char *)(unsigned int)v14,
          Filename[0]);
        return v15;
      }
      *a6 = 6;
      *a3 = 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180062d50  mov     [rsp+arg_0], rbx
0x180062d55  push    rbp
0x180062d56  push    rsi
0x180062d57  push    rdi
0x180062d58  sub     rsp, 240h
0x180062d5f  mov     rax, cs:__security_cookie
0x180062d66  xor     rax, rsp
0x180062d69  mov     [rsp+258h+var_28], rax
0x180062d71  mov     rbp, [rsp+258h+arg_20]
0x180062d79  mov     rbx, r9
0x180062d7c  mov     rsi, [rsp+258h+arg_28]
0x180062d84  mov     rdi, r8
0x180062d87  mov     dword ptr [r8], 0
0x180062d8e  mov     rax, rdx
0x180062d91  cmp     dword ptr [rdx+18h], 0CFFFFFFFh
0x180062d98  jnz     loc_180062E97
0x180062d9e  mov     rcx, [rax+8]; hProcess
0x180062da2  lea     r8, [rsp+258h+Filename]; lpFilename
0x180062da7  mov     r9d, 104h; nSize
0x180062dad  xor     edx, edx; hModule
0x180062daf  call    cs:__imp_K32GetModuleFileNameExW
0x180062db5  test    eax, eax
0x180062db7  jnz     short loc_180062DD7
0x180062db9  mov     rcx, [rsp+258h]; this
0x180062dc1  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x180062dc8  mov     edx, 113h; void *
0x180062dcd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180062dd2  jmp     loc_180062E99
0x180062dd7  lea     rcx, [rsp+258h+Filename]; pszPath
0x180062ddc  call    cs:__imp_PathFindFileNameW
0x180062de2  mov     rcx, rax; String1
0x180062de5  lea     rdx, aMicrosoftedgec; "microsoftedgecp.exe"
0x180062dec  call    cs:__imp__wcsicmp
0x180062df2  test    eax, eax
0x180062df4  jz      short loc_180062E53
0x180062df6  lea     rcx, [rsp+258h+Filename]; pszPath
0x180062dfb  call    cs:__imp_PathFindFileNameW
0x180062e01  mov     rcx, rax; String1
0x180062e04  lea     rdx, aMicrosoftedgeb; "microsoftedgebchost.exe"
0x180062e0b  call    cs:__imp__wcsicmp
0x180062e11  test    eax, eax
0x180062e13  jz      short loc_180062E53
0x180062e15  lea     rcx, [rsp+258h+Filename]; pszPath
0x180062e1a  call    cs:__imp_PathFindFileNameW
0x180062e20  mov     rcx, rax; String1
0x180062e23  lea     rdx, aMicrosoftedged; "microsoftedgedevtools.exe"
0x180062e2a  call    cs:__imp__wcsicmp
0x180062e30  test    eax, eax
0x180062e32  jz      short loc_180062E53
0x180062e34  lea     rcx, [rsp+258h+Filename]; pszPath
0x180062e39  call    cs:__imp_PathFindFileNameW
0x180062e3f  mov     rcx, rax; String1
0x180062e42  lea     rdx, aMicrosoftedgeE; "microsoftedge.exe"
0x180062e49  call    cs:__imp__wcsicmp
0x180062e4f  test    eax, eax
0x180062e51  jnz     short loc_180062E97
0x180062e53  mov     edx, [rbp+0]; unsigned __int64
0x180062e56  lea     r8, aMoapphang; "MoAppHang"
0x180062e5d  mov     rcx, rbx; unsigned __int16 *
0x180062e60  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062e65  mov     ebx, eax
0x180062e67  test    eax, eax
0x180062e69  jns     short loc_180062E8B
0x180062e6b  mov     rcx, [rsp+258h]; this
0x180062e73  lea     r8, aOnecoreuapInet_12; "onecoreuap\\inetcore\\iertutil\\werexce"...
0x180062e7a  mov     r9d, eax; char *
0x180062e7d  mov     edx, 11Bh; void *
0x180062e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180062e87  mov     eax, ebx
0x180062e89  jmp     short loc_180062E99
0x180062e8b  mov     dword ptr [rsi], 6
0x180062e91  mov     dword ptr [rdi], 1
0x180062e97  xor     eax, eax
0x180062e99  mov     rcx, [rsp+258h+var_28]
0x180062ea1  xor     rcx, rsp; StackCookie
0x180062ea4  call    __security_check_cookie
0x180062ea9  mov     rbx, [rsp+258h+arg_0]
0x180062eb1  add     rsp, 240h
0x180062eb8  pop     rdi
0x180062eb9  pop     rsi
0x180062eba  pop     rbp
0x180062ebb  retn
```
