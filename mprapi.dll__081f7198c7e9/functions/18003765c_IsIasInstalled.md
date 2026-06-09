# IsIasInstalled

- ea: `0x18003765c`
- end: `0x180037713`
- name: `IsIasInstalled`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update`

## callers

- `0x18001555c`

## callees

- `0x18003765c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800376c5`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180037683`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180037683`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800376f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800376fb`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800376f2`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x1800376fb`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800376ba`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x1800376ba`

## string_xrefs

- `0x180037674`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall IsIasInstalled(__int64 a1, _DWORD *a2)
{
  SC_HANDLE v3; // rax
  SC_HANDLE v4; // rsi
  signed int v5; // eax
  unsigned int v6; // ebx
  SC_HANDLE v7; // rax
  signed int LastError; // eax

  *a2 = 0;
  v3 = OpenSCManagerW(0, L"ServicesActive", 0x80000000);
  v4 = v3;
  if ( v3 )
  {
    v6 = 0;
    v7 = OpenServiceW(v3, L"IAS", 0x80000000);
    if ( v7 )
    {
      *a2 = 1;
      CloseServiceHandle(v7);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 1060 )
      {
        *a2 = 0;
      }
      else if ( LastError > 0 )
      {
        v6 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v6 = LastError;
      }
    }
    CloseServiceHandle(v4);
  }
  else
  {
    v5 = GetLastError();
    v6 = v5;
    if ( v5 > 0 )
      return (unsigned __int16)v5 | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18003765c  mov     [rsp+arg_0], rbx
0x180037661  mov     [rsp+arg_8], rsi
0x180037666  push    rdi
0x180037667  sub     rsp, 20h
0x18003766b  mov     rdi, rdx
0x18003766e  mov     dword ptr [rdx], 0
0x180037674  lea     rdx, DatabaseName; "ServicesActive"
0x18003767b  mov     r8d, 80000000h; dwDesiredAccess
0x180037681  xor     ecx, ecx; lpMachineName
0x180037683  call    cs:__imp_OpenSCManagerW
0x180037689  mov     rsi, rax
0x18003768c  test    rax, rax
0x18003768f  jnz     short loc_1800376A8
0x180037691  call    cs:__imp_GetLastError
0x180037697  mov     ebx, eax
0x180037699  test    eax, eax
0x18003769b  jle     short loc_180037701
0x18003769d  movzx   ebx, ax
0x1800376a0  or      ebx, 80070000h
0x1800376a6  jmp     short loc_180037701
0x1800376a8  mov     r8d, 80000000h; dwDesiredAccess
0x1800376ae  lea     rdx, aIas; "IAS"
0x1800376b5  mov     rcx, rsi; hSCManager
0x1800376b8  xor     ebx, ebx
0x1800376ba  call    cs:__imp_OpenServiceW
0x1800376c0  test    rax, rax
0x1800376c3  jnz     short loc_1800376E9
0x1800376c5  call    cs:__imp_GetLastError
0x1800376cb  cmp     eax, 424h
0x1800376d0  jnz     short loc_1800376D6
0x1800376d2  mov     [rdi], ebx
0x1800376d4  jmp     short loc_1800376F8
0x1800376d6  test    eax, eax
0x1800376d8  jg      short loc_1800376DE
0x1800376da  mov     ebx, eax
0x1800376dc  jmp     short loc_1800376F8
0x1800376de  movzx   ebx, ax
0x1800376e1  or      ebx, 80070000h
0x1800376e7  jmp     short loc_1800376F8
0x1800376e9  mov     rcx, rax; hSCObject
0x1800376ec  mov     dword ptr [rdi], 1
0x1800376f2  call    cs:__imp_CloseServiceHandle
0x1800376f8  mov     rcx, rsi; hSCObject
0x1800376fb  call    cs:__imp_CloseServiceHandle
0x180037701  mov     rsi, [rsp+28h+arg_8]
0x180037706  mov     eax, ebx
0x180037708  mov     rbx, [rsp+28h+arg_0]
0x18003770d  add     rsp, 20h
0x180037711  pop     rdi
0x180037712  retn
```
