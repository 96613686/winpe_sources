# StartServiceW(ushort const *,ulong,ushort const * *)

- ea: `0x1800809a8`
- end: `0x180080ac2`
- name: `?StartServiceW@@YAKPEBGKPEAPEBG@Z`
- size: `282`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180081908`
- `0x180081a28`
- `0x180081b50`

## callees

- `0x1800809a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800809d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080a78`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180080a5f`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x180080a5f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800809f6`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800809f6`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180080a2c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180080a2c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080a94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080aa3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080a94`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180080aa3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800809bf`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800809bf`

## pseudocode

```c
__int64 __fastcall StartServiceW(const unsigned __int16 *a1, __int64 a2, const unsigned __int16 **a3)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  DWORD LastError; // ebx
  SC_HANDLE v6; // rdi
  unsigned __int8 i; // bl
  int v8; // eax

  v3 = OpenSCManagerW(0, 0, 1u);
  v4 = v3;
  if ( v3 )
  {
    v6 = OpenServiceW(v3, L"IPxlatCfgSvc", 0x14u);
    if ( v6 )
    {
      for ( i = 0; i < 2u; ++i )
      {
        if ( !StartServiceW(v6, 0, 0) && GetLastError() != 1056 || (v8 = WaitServiceState(v6, 9, 30000)) == 0 )
        {
          LastError = GetLastError();
          goto LABEL_15;
        }
        if ( v8 == 4 )
        {
          LastError = 0;
          goto LABEL_15;
        }
      }
      LastError = 1077;
LABEL_15:
      CloseServiceHandle(v6);
    }
    else
    {
      LastError = GetLastError();
    }
    CloseServiceHandle(v4);
  }
  else
  {
    return GetLastError();
  }
  return LastError;
}

```

## disassembly

```asm
0x1800809a8  mov     [rsp+arg_0], rbx
0x1800809ad  mov     [rsp+arg_8], rsi
0x1800809b2  push    rdi
0x1800809b3  sub     rsp, 20h
0x1800809b7  xor     edx, edx; lpDatabaseName
0x1800809b9  xor     ecx, ecx; lpMachineName
0x1800809bb  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800809bf  call    cs:__imp_OpenSCManagerW
0x1800809c6  nop     dword ptr [rax+rax+00h]
0x1800809cb  mov     rsi, rax
0x1800809ce  test    rax, rax
0x1800809d1  jnz     short loc_1800809E6
0x1800809d3  call    cs:__imp_GetLastError
0x1800809da  nop     dword ptr [rax+rax+00h]
0x1800809df  mov     ebx, eax
0x1800809e1  jmp     loc_180080AAF
0x1800809e6  mov     r8d, 14h; dwDesiredAccess
0x1800809ec  lea     rdx, aIpxlatcfgsvc; "IPxlatCfgSvc"
0x1800809f3  mov     rcx, rsi; hSCManager
0x1800809f6  call    cs:__imp_OpenServiceW
0x1800809fd  nop     dword ptr [rax+rax+00h]
0x180080a02  mov     rdi, rax
0x180080a05  test    rax, rax
0x180080a08  jnz     short loc_180080A1D
0x180080a0a  call    cs:__imp_GetLastError
0x180080a11  nop     dword ptr [rax+rax+00h]
0x180080a16  mov     ebx, eax
0x180080a18  jmp     loc_180080AA0
0x180080a1d  xor     bl, bl
0x180080a1f  cmp     bl, 2
0x180080a22  jnb     short loc_180080A8C
0x180080a24  xor     r8d, r8d; lpServiceArgVectors
0x180080a27  xor     edx, edx; dwNumServiceArgs
0x180080a29  mov     rcx, rdi; hService
0x180080a2c  call    cs:__imp_StartServiceW
0x180080a33  nop     dword ptr [rax+rax+00h]
0x180080a38  test    eax, eax
0x180080a3a  jnz     short loc_180080A4F
0x180080a3c  call    cs:__imp_GetLastError
0x180080a43  nop     dword ptr [rax+rax+00h]
0x180080a48  cmp     eax, 420h
0x180080a4d  jnz     short loc_180080A78
0x180080a4f  xor     r9d, r9d
0x180080a52  mov     r8d, 7530h
0x180080a58  mov     rcx, rdi
0x180080a5b  lea     edx, [r9+9]
0x180080a5f  call    cs:__imp_WaitServiceState
0x180080a66  nop     dword ptr [rax+rax+00h]
0x180080a6b  test    eax, eax
0x180080a6d  jz      short loc_180080A78
0x180080a6f  cmp     eax, 4
0x180080a72  jz      short loc_180080A88
0x180080a74  inc     bl
0x180080a76  jmp     short loc_180080A1F
0x180080a78  call    cs:__imp_GetLastError
0x180080a7f  nop     dword ptr [rax+rax+00h]
0x180080a84  mov     ebx, eax
0x180080a86  jmp     short loc_180080A91
0x180080a88  xor     ebx, ebx
0x180080a8a  jmp     short loc_180080A91
0x180080a8c  mov     ebx, 435h
0x180080a91  mov     rcx, rdi; hSCObject
0x180080a94  call    cs:__imp_CloseServiceHandle
0x180080a9b  nop     dword ptr [rax+rax+00h]
0x180080aa0  mov     rcx, rsi; hSCObject
0x180080aa3  call    cs:__imp_CloseServiceHandle
0x180080aaa  nop     dword ptr [rax+rax+00h]
0x180080aaf  mov     rsi, [rsp+28h+arg_8]
0x180080ab4  mov     eax, ebx
0x180080ab6  mov     rbx, [rsp+28h+arg_0]
0x180080abb  add     rsp, 20h
0x180080abf  pop     rdi
0x180080ac0  retn
```
