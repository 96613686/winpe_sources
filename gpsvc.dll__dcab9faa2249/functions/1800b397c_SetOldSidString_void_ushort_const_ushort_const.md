# SetOldSidString(void *,ushort const *,ushort const *)

- ea: `0x1800b397c`
- end: `0x1800b3bc9`
- name: `?SetOldSidString@@YAHPEAXPEBG1@Z`
- size: `589`
- prototype: `__int64 __fastcall(HANDLE hToken, BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800631a8`

## callees

- `0x18002c690`
- `0x180049c90`
- `0x180075ec0`
- `0x18007d320`
- `0x1800b2d88`
- `0x1800b397c`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3b98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800b3b98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b39d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3a7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b3b24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3b80`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b3b80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3b90`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b3b90`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b3b18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800b3b18`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b3a72`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b3a72`

## string_xrefs

- `0x1800b3a9f`: `GetOldSidString:  Failed to open profile profile guid key with error %d`
- `0x1800b3aca`: `GetOldSidString:  Failed to open profile profile guid key with error %d`
- `0x1800b3b03`: `SidString`
- `0x1800b3b41`: `SetOldSidString:  Failed to set SidString with error %d`
- `0x1800b3b69`: `SetOldSidString:  Failed to set SidString with error %d`

## pseudocode

```c
__int64 __fastcall SetOldSidString(HANDLE hToken, BYTE *lpData, const unsigned __int16 *a3)
{
  DWORD LastError; // edi
  unsigned __int16 *UserGuid; // r14
  int v7; // eax
  unsigned __int16 *v8; // rax
  unsigned int v9; // ebx
  void (*v10)(unsigned int, const unsigned __int16 *, ...); // rax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  unsigned int lpdwDisposition[2]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  lpdwDisposition[1] = 0;
  hKey = 0;
  lpdwDisposition[0] = 0;
  LastError = GetLastError();
  UserGuid = GetUserGuid(hToken);
  if ( !UserGuid )
  {
    LastError = GetLastError();
    goto LABEL_28;
  }
  v7 = StringCchCopyW(SubKey, 0x105u, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\PolicyGuid");
  if ( v7 >= 0 )
  {
    v8 = CheckSlashEx(SubKey, 0x105u, lpdwDisposition);
    if ( !v8 )
    {
      LastError = 122;
      goto LABEL_27;
    }
    v7 = StringCchCopyW(v8, lpdwDisposition[0], UserGuid);
    if ( v7 >= 0 )
    {
      v9 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &lpdwDisposition[1]);
      if ( v9 )
      {
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_27;
        v10 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(4u, L"GetOldSidString:  Failed to open profile profile guid key with error %d", v9);
          goto LABEL_27;
        }
        v11 = L"GetOldSidString:  Failed to open profile profile guid key with error %d";
        v12 = 4;
      }
      else
      {
        if ( lpData )
        {
          v13 = -1;
          do
            ++v13;
          while ( *(_WORD *)&lpData[2 * v13] );
        }
        else
        {
          LODWORD(v13) = 0;
        }
        v9 = RegSetValueExW(hKey, L"SidString", 0, 1u, lpData, 2 * v13 + 2);
        if ( !v9 )
          goto LABEL_27;
        LastError = GetLastError();
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_27;
        v10 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"SetOldSidString:  Failed to set SidString with error %d", v9);
          goto LABEL_27;
        }
        v11 = L"SetOldSidString:  Failed to set SidString with error %d";
        v12 = 2;
      }
      v10(v12, v11, v9);
      goto LABEL_27;
    }
  }
  LastError = (unsigned __int16)v7;
LABEL_27:
  LocalFree(UserGuid);
LABEL_28:
  if ( hKey )
    RegCloseKey(hKey);
  SetLastError(LastError);
  return 1;
}

```

## disassembly

```asm
0x1800b397c  mov     [rsp-8+arg_10], rbx
0x1800b3981  push    rbp
0x1800b3982  push    rsi
0x1800b3983  push    rdi
0x1800b3984  push    r14
0x1800b3986  push    r15
0x1800b3988  lea     rbp, [rsp-180h]
0x1800b3990  sub     rsp, 280h
0x1800b3997  mov     rax, cs:__security_cookie
0x1800b399e  xor     rax, rsp
0x1800b39a1  mov     [rbp+1A0h+var_30], rax
0x1800b39a8  xor     r15d, r15d
0x1800b39ab  mov     rsi, rdx
0x1800b39ae  mov     [rsp+2A0h+var_250+4], r15d
0x1800b39b3  mov     rbx, rcx
0x1800b39b6  mov     [rsp+2A0h+hKey], r15
0x1800b39bb  mov     [rsp+2A0h+var_250], r15d
0x1800b39c0  call    cs:__imp_GetLastError
0x1800b39c6  mov     rcx, rbx; hToken
0x1800b39c9  mov     edi, eax
0x1800b39cb  call    ?GetUserGuid@@YAPEAGPEAX@Z; GetUserGuid(void *)
0x1800b39d0  mov     r14, rax
0x1800b39d3  test    rax, rax
0x1800b39d6  jnz     short loc_1800B39E5
0x1800b39d8  call    cs:__imp_GetLastError
0x1800b39de  mov     edi, eax
0x1800b39e0  jmp     loc_1800B3B86
0x1800b39e5  mov     ebx, 105h
0x1800b39ea  lea     r8, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800b39f1  mov     edx, ebx; unsigned __int64
0x1800b39f3  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800b39f8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b39fd  test    eax, eax
0x1800b39ff  jns     short loc_1800B3A09
0x1800b3a01  movzx   edi, ax
0x1800b3a04  jmp     loc_1800B3B7D
0x1800b3a09  lea     r8, [rsp+2A0h+var_250]; unsigned int *
0x1800b3a0e  mov     edx, ebx; unsigned int
0x1800b3a10  lea     rcx, [rsp+2A0h+SubKey]; unsigned __int16 *
0x1800b3a15  call    ?CheckSlashEx@@YAPEAGPEAGIPEAI@Z; CheckSlashEx(ushort *,uint,uint *)
0x1800b3a1a  test    rax, rax
0x1800b3a1d  jnz     short loc_1800B3A27
0x1800b3a1f  lea     edi, [rax+7Ah]
0x1800b3a22  jmp     loc_1800B3B7D
0x1800b3a27  mov     edx, [rsp+2A0h+var_250]; unsigned __int64
0x1800b3a2b  mov     r8, r14; unsigned __int16 *
0x1800b3a2e  mov     rcx, rax; unsigned __int16 *
0x1800b3a31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b3a36  test    eax, eax
0x1800b3a38  js      short loc_1800B3A01
0x1800b3a3a  lea     rax, [rsp+2A0h+var_250+4]
0x1800b3a3f  xor     r9d, r9d; lpClass
0x1800b3a42  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x1800b3a47  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x1800b3a4c  lea     rax, [rsp+2A0h+hKey]
0x1800b3a51  xor     r8d, r8d; Reserved
0x1800b3a54  mov     [rsp+2A0h+phkResult], rax; phkResult
0x1800b3a59  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b3a60  mov     [rsp+2A0h+lpSecurityAttributes], r15; lpSecurityAttributes
0x1800b3a65  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x1800b3a6d  mov     [rsp+2A0h+dwOptions], r15d; dwOptions
0x1800b3a72  call    cs:__imp_RegCreateKeyExW
0x1800b3a78  mov     ebx, eax
0x1800b3a7a  test    eax, eax
0x1800b3a7c  jz      short loc_1800B3ADB
0x1800b3a7e  call    cs:__imp_GetLastError
0x1800b3a84  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b3a8b  mov     edi, eax
0x1800b3a8d  jz      loc_1800B3B7D
0x1800b3a93  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3a9a  test    rax, rax
0x1800b3a9d  jz      short loc_1800B3AB0
0x1800b3a9f  lea     rdx, aGetoldsidstrin_0; "GetOldSidString:  Failed to open profil"...
0x1800b3aa6  mov     ecx, 4
0x1800b3aab  jmp     loc_1800B3B4D
0x1800b3ab0  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b3ab7  jz      loc_1800B3B7D
0x1800b3abd  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3ac4  jz      loc_1800B3B7D
0x1800b3aca  lea     rdx, aGetoldsidstrin_0; "GetOldSidString:  Failed to open profil"...
0x1800b3ad1  mov     ecx, 4
0x1800b3ad6  jmp     loc_1800B3B75
0x1800b3adb  test    rsi, rsi
0x1800b3ade  jnz     short loc_1800B3AE5
0x1800b3ae0  mov     eax, r15d
0x1800b3ae3  jmp     short loc_1800B3AF3
0x1800b3ae5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b3ae9  inc     rax
0x1800b3aec  cmp     [rsi+rax*2], r15w
0x1800b3af1  jnz     short loc_1800B3AE9
0x1800b3af3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b3af8  lea     eax, ds:2[rax*2]
0x1800b3aff  mov     [rsp+2A0h+samDesired], eax; cbData
0x1800b3b03  lea     rdx, aSidstring; "SidString"
0x1800b3b0a  mov     r9d, 1; dwType
0x1800b3b10  mov     qword ptr [rsp+2A0h+dwOptions], rsi; lpData
0x1800b3b15  xor     r8d, r8d; Reserved
0x1800b3b18  call    cs:__imp_RegSetValueExW
0x1800b3b1e  mov     ebx, eax
0x1800b3b20  test    eax, eax
0x1800b3b22  jz      short loc_1800B3B7D
0x1800b3b24  call    cs:__imp_GetLastError
0x1800b3b2a  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800b3b31  mov     edi, eax
0x1800b3b33  jz      short loc_1800B3B7D
0x1800b3b35  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800b3b3c  test    rax, rax
0x1800b3b3f  jz      short loc_1800B3B57
0x1800b3b41  lea     rdx, aSetoldsidstrin; "SetOldSidString:  Failed to set SidStri"...
0x1800b3b48  mov     ecx, 2
0x1800b3b4d  mov     r8d, ebx
0x1800b3b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b3b55  jmp     short loc_1800B3B7D
0x1800b3b57  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800b3b5e  jz      short loc_1800B3B7D
0x1800b3b60  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800b3b67  jz      short loc_1800B3B7D
0x1800b3b69  lea     rdx, aSetoldsidstrin; "SetOldSidString:  Failed to set SidStri"...
0x1800b3b70  mov     ecx, 2; unsigned int
0x1800b3b75  mov     r8d, ebx
0x1800b3b78  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800b3b7d  mov     rcx, r14; hMem
0x1800b3b80  call    cs:__imp_LocalFree
0x1800b3b86  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1800b3b8b  test    rcx, rcx
0x1800b3b8e  jz      short loc_1800B3B96
0x1800b3b90  call    cs:__imp_RegCloseKey
0x1800b3b96  mov     ecx, edi; dwErrCode
0x1800b3b98  call    cs:__imp_SetLastError
0x1800b3b9e  mov     eax, 1
0x1800b3ba3  mov     rcx, [rbp+1A0h+var_30]
0x1800b3baa  xor     rcx, rsp; StackCookie
0x1800b3bad  call    __security_check_cookie
0x1800b3bb2  mov     rbx, [rsp+2A0h+arg_10]
0x1800b3bba  add     rsp, 280h
0x1800b3bc1  pop     r15
0x1800b3bc3  pop     r14
0x1800b3bc5  pop     rdi
0x1800b3bc6  pop     rsi
0x1800b3bc7  pop     rbp
0x1800b3bc8  retn
```
