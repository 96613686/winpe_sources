# StartServiceW(ushort const *,ulong,ushort const * *)

- ea: `0x1800807c8`
- end: `0x1800808e2`
- name: `?StartServiceW@@YAKPEBGKPEAPEBG@Z`
- size: `282`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int, const unsigned __int16 **)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180081718`
- `0x180081838`
- `0x180081960`

## callees

- `0x1800807c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008082a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008085c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080898`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800807f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008082a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008085c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080898`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18008087f`
- `api-ms-win-service-private-l1-1-0!WaitServiceState` at `0x18008087f`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180080816`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180080816`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18008084c`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18008084c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800808b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800808c3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800808b4`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800808c3`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800807df`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1800807df`

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
0x1800807c8  mov     [rsp+arg_0], rbx
0x1800807cd  mov     [rsp+arg_8], rsi
0x1800807d2  push    rdi
0x1800807d3  sub     rsp, 20h
0x1800807d7  xor     edx, edx; lpDatabaseName
0x1800807d9  xor     ecx, ecx; lpMachineName
0x1800807db  lea     r8d, [rdx+1]; dwDesiredAccess
0x1800807df  call    cs:__imp_OpenSCManagerW
0x1800807e6  nop     dword ptr [rax+rax+00h]
0x1800807eb  mov     rsi, rax
0x1800807ee  test    rax, rax
0x1800807f1  jnz     short loc_180080806
0x1800807f3  call    cs:__imp_GetLastError
0x1800807fa  nop     dword ptr [rax+rax+00h]
0x1800807ff  mov     ebx, eax
0x180080801  jmp     loc_1800808CF
0x180080806  mov     r8d, 14h; dwDesiredAccess
0x18008080c  lea     rdx, aIpxlatcfgsvc; "IPxlatCfgSvc"
0x180080813  mov     rcx, rsi; hSCManager
0x180080816  call    cs:__imp_OpenServiceW
0x18008081d  nop     dword ptr [rax+rax+00h]
0x180080822  mov     rdi, rax
0x180080825  test    rax, rax
0x180080828  jnz     short loc_18008083D
0x18008082a  call    cs:__imp_GetLastError
0x180080831  nop     dword ptr [rax+rax+00h]
0x180080836  mov     ebx, eax
0x180080838  jmp     loc_1800808C0
0x18008083d  xor     bl, bl
0x18008083f  cmp     bl, 2
0x180080842  jnb     short loc_1800808AC
0x180080844  xor     r8d, r8d; lpServiceArgVectors
0x180080847  xor     edx, edx; dwNumServiceArgs
0x180080849  mov     rcx, rdi; hService
0x18008084c  call    cs:__imp_StartServiceW
0x180080853  nop     dword ptr [rax+rax+00h]
0x180080858  test    eax, eax
0x18008085a  jnz     short loc_18008086F
0x18008085c  call    cs:__imp_GetLastError
0x180080863  nop     dword ptr [rax+rax+00h]
0x180080868  cmp     eax, 420h
0x18008086d  jnz     short loc_180080898
0x18008086f  xor     r9d, r9d
0x180080872  mov     r8d, 7530h
0x180080878  mov     rcx, rdi
0x18008087b  lea     edx, [r9+9]
0x18008087f  call    cs:__imp_WaitServiceState
0x180080886  nop     dword ptr [rax+rax+00h]
0x18008088b  test    eax, eax
0x18008088d  jz      short loc_180080898
0x18008088f  cmp     eax, 4
0x180080892  jz      short loc_1800808A8
0x180080894  inc     bl
0x180080896  jmp     short loc_18008083F
0x180080898  call    cs:__imp_GetLastError
0x18008089f  nop     dword ptr [rax+rax+00h]
0x1800808a4  mov     ebx, eax
0x1800808a6  jmp     short loc_1800808B1
0x1800808a8  xor     ebx, ebx
0x1800808aa  jmp     short loc_1800808B1
0x1800808ac  mov     ebx, 435h
0x1800808b1  mov     rcx, rdi; hSCObject
0x1800808b4  call    cs:__imp_CloseServiceHandle
0x1800808bb  nop     dword ptr [rax+rax+00h]
0x1800808c0  mov     rcx, rsi; hSCObject
0x1800808c3  call    cs:__imp_CloseServiceHandle
0x1800808ca  nop     dword ptr [rax+rax+00h]
0x1800808cf  mov     rsi, [rsp+28h+arg_8]
0x1800808d4  mov     eax, ebx
0x1800808d6  mov     rbx, [rsp+28h+arg_0]
0x1800808db  add     rsp, 20h
0x1800808df  pop     rdi
0x1800808e0  retn
```
