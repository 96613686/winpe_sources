# ISAPI_DLL::SetName(ushort const *,void *)

- ea: `0x180005ad8`
- end: `0x180005c3d`
- name: `?SetName@ISAPI_DLL@@QEAAJPEBGPEAX@Z`
- size: `357`
- prototype: `int __fastcall(LPCWSTR *this, const unsigned __int16 *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005224`

## callees

- `0x180005ad8`
- `0x18001249a`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005b3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005c0b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005b33`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180005b33`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005c2a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180005c2a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005ba0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180005ba0`
- `iisutil!PuDbgPrint` at `0x180005b91`
- `iisutil!PuDbgPrint` at `0x180005bf7`
- `iisutil!PuDbgPrint` at `0x180005b91`
- `iisutil!PuDbgPrint` at `0x180005bf7`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005af0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005af0`
- `iisutil!MakePathCanonicalizationProof` at `0x180005b05`
- `iisutil!MakePathCanonicalizationProof` at `0x180005b05`

## string_xrefs

- `0x180005b68`: `Attempt impersonate to get file attributes on %S failed with error 0x%08x.\n`
- `0x180005b73`: `ISAPI_DLL::SetName`
- `0x180005bce`: `ISAPI_DLL::SetName`
- `0x180005b7f`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x180005bd9`: `servercommon\inetsrv\iis\iisrearc\iis70\isapi\dll_manager.cxx`
- `0x180005be0`: `Attempt to get file attributes on %S failed with error %d.\n`

## pseudocode

```c
int __fastcall ISAPI_DLL::SetName(LPCWSTR *this, const unsigned __int16 *a2, void *a3)
{
  int result; // eax
  signed int PathCanonicalizationProof; // ebx
  BOOL v8; // ebp
  signed int v9; // eax
  DWORD LastError; // eax
  signed int v11; // eax

  result = STRU::Copy((STRU *)(this + 1), a2);
  if ( result >= 0 )
  {
    PathCanonicalizationProof = MakePathCanonicalizationProof(a2, (struct STRU *)(this + 8));
    if ( PathCanonicalizationProof >= 0 )
    {
      v8 = 0;
      if ( wcsncmp_0(a2, L"\\\\", 2u) || (v8 = SetThreadToken(0, a3)) )
      {
        if ( GetFileAttributesW(this[12]) == -1 )
        {
          if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
          {
            LastError = GetLastError();
            PuDbgPrint(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
              159,
              "ISAPI_DLL::SetName",
              "Attempt to get file attributes on %S failed with error %d.\r\n",
              a2,
              LastError);
          }
          if ( GetLastError() == 2 )
            SetLastError(0x7Eu);
          v11 = GetLastError();
          PathCanonicalizationProof = v11;
          if ( v11 > 0 )
            PathCanonicalizationProof = (unsigned __int16)v11 | 0x80070000;
        }
        if ( v8 )
          RevertToSelf();
      }
      else
      {
        v9 = GetLastError();
        PathCanonicalizationProof = v9;
        if ( v9 > 0 )
          PathCanonicalizationProof = (unsigned __int16)v9 | 0x80070000;
        if ( (g_dwDebugFlags & 3) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\isapi\\dll_manager.cxx",
            142,
            "ISAPI_DLL::SetName",
            "Attempt impersonate to get file attributes on %S failed with error 0x%08x.\r\n",
            a2,
            PathCanonicalizationProof);
      }
    }
    return PathCanonicalizationProof;
  }
  return result;
}

```

## disassembly

```asm
0x180005ad8  push    rbx
0x180005ada  push    rbp
0x180005adb  push    rsi
0x180005adc  push    rdi
0x180005add  push    r14
0x180005adf  sub     rsp, 40h
0x180005ae3  mov     rsi, rcx
0x180005ae6  mov     r14, r8
0x180005ae9  add     rcx, 8
0x180005aed  mov     rdi, rdx
0x180005af0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005af6  test    eax, eax
0x180005af8  js      loc_180005C32
0x180005afe  lea     rdx, [rsi+40h]
0x180005b02  mov     rcx, rdi
0x180005b05  call    cs:__imp_?MakePathCanonicalizationProof@@YAJPEBGPEAVSTRU@@@Z; MakePathCanonicalizationProof(ushort const *,STRU *)
0x180005b0b  mov     ebx, eax
0x180005b0d  test    eax, eax
0x180005b0f  js      loc_180005C30
0x180005b15  xor     ebp, ebp
0x180005b17  lea     rdx, asc_180016DCC; "\\\\"
0x180005b1e  mov     rcx, rdi; String1
0x180005b21  lea     r8d, [rbp+2]; MaxCount
0x180005b25  call    wcsncmp_0
0x180005b2a  test    eax, eax
0x180005b2c  jnz     short loc_180005B9C
0x180005b2e  mov     rdx, r14; Token
0x180005b31  xor     ecx, ecx; Thread
0x180005b33  call    cs:__imp_SetThreadToken
0x180005b39  mov     ebp, eax
0x180005b3b  test    eax, eax
0x180005b3d  jnz     short loc_180005B9C
0x180005b3f  call    cs:__imp_GetLastError
0x180005b45  mov     ebx, eax
0x180005b47  test    eax, eax
0x180005b49  jle     short loc_180005B54
0x180005b4b  movzx   ebx, ax
0x180005b4e  or      ebx, 80070000h
0x180005b54  test    byte ptr cs:g_dwDebugFlags, 3
0x180005b5b  jz      loc_180005C30
0x180005b61  mov     rcx, cs:g_pDebug
0x180005b68  lea     rax, aAttemptImperso; "Attempt impersonate to get file attribu"...
0x180005b6f  mov     [rsp+68h+var_38], ebx
0x180005b73  lea     r9, aIsapiDllSetnam; "ISAPI_DLL::SetName"
0x180005b7a  mov     [rsp+68h+var_40], rdi
0x180005b7f  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005b86  mov     r8d, 8Eh
0x180005b8c  mov     [rsp+68h+var_48], rax
0x180005b91  call    cs:__imp_PuDbgPrint
0x180005b97  jmp     loc_180005C30
0x180005b9c  mov     rcx, [rsi+60h]; lpFileName
0x180005ba0  call    cs:__imp_GetFileAttributesW
0x180005ba6  cmp     eax, 0FFFFFFFFh
0x180005ba9  jnz     short loc_180005C26
0x180005bab  mov     eax, cs:g_dwDebugFlags
0x180005bb1  test    al, 3
0x180005bb3  setnz   cl
0x180005bb6  bt      eax, 1Fh
0x180005bba  setb    al
0x180005bbd  test    al, cl
0x180005bbf  jz      short loc_180005BFD
0x180005bc1  call    cs:__imp_GetLastError
0x180005bc7  mov     rcx, cs:g_pDebug
0x180005bce  lea     r9, aIsapiDllSetnam; "ISAPI_DLL::SetName"
0x180005bd5  mov     [rsp+68h+var_38], eax
0x180005bd9  lea     rdx, aServercommonIn_5; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005be0  lea     rax, aAttemptToGetFi; "Attempt to get file attributes on %S fa"...
0x180005be7  mov     [rsp+68h+var_40], rdi
0x180005bec  mov     r8d, 9Fh
0x180005bf2  mov     [rsp+68h+var_48], rax
0x180005bf7  call    cs:__imp_PuDbgPrint
0x180005bfd  call    cs:__imp_GetLastError
0x180005c03  cmp     eax, 2
0x180005c06  jnz     short loc_180005C11
0x180005c08  lea     ecx, [rax+7Ch]; dwErrCode
0x180005c0b  call    cs:__imp_SetLastError
0x180005c11  call    cs:__imp_GetLastError
0x180005c17  mov     ebx, eax
0x180005c19  test    eax, eax
0x180005c1b  jle     short loc_180005C26
0x180005c1d  movzx   ebx, ax
0x180005c20  or      ebx, 80070000h
0x180005c26  test    ebp, ebp
0x180005c28  jz      short loc_180005C30
0x180005c2a  call    cs:__imp_RevertToSelf
0x180005c30  mov     eax, ebx
0x180005c32  add     rsp, 40h
0x180005c36  pop     r14
0x180005c38  pop     rdi
0x180005c39  pop     rsi
0x180005c3a  pop     rbp
0x180005c3b  pop     rbx
0x180005c3c  retn
```
