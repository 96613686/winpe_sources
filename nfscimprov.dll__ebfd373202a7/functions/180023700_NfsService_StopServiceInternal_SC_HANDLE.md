# NfsService::StopServiceInternal(SC_HANDLE__ *)

- ea: `0x180023700`
- end: `0x180023848`
- name: `?StopServiceInternal@NfsService@@AEAAKPEAUSC_HANDLE__@@@Z`
- size: `328`
- prototype: `unsigned int(NfsService *__hidden this, struct SC_HANDLE__ *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800236cc`

## callees

- `0x180023700`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002378e`
- `KERNEL32!GetLastError` at `0x18002381d`
- `KERNEL32!GetLastError` at `0x18002378e`
- `KERNEL32!GetLastError` at `0x18002381d`
- `KERNEL32!Sleep` at `0x180023808`
- `KERNEL32!Sleep` at `0x180023808`
- `KERNEL32!GetTickCount` at `0x180023736`
- `KERNEL32!GetTickCount` at `0x1800237d6`
- `KERNEL32!GetTickCount` at `0x180023736`
- `KERNEL32!GetTickCount` at `0x1800237d6`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002375d`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800237c6`
- `ADVAPI32!QueryServiceStatusEx` at `0x18002375d`
- `ADVAPI32!QueryServiceStatusEx` at `0x1800237c6`
- `ADVAPI32!ControlService` at `0x180023784`
- `ADVAPI32!ControlService` at `0x180023784`

## pseudocode

```c
__int64 __fastcall NfsService::StopServiceInternal(NfsService *this, SC_HANDLE a2)
{
  DWORD TickCount; // esi
  unsigned int v4; // ebx
  DWORD LastError; // ecx
  __int64 result; // rax
  DWORD v7; // edx
  DWORD pcbBytesNeeded; // [rsp+30h] [rbp-40h] BYREF
  BYTE Buffer[16]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v10; // [rsp+48h] [rbp-28h]
  int v11; // [rsp+58h] [rbp-18h]

  *(_OWORD *)Buffer = 0;
  v11 = 0;
  v10 = 0;
  pcbBytesNeeded = 0;
  TickCount = GetTickCount();
  if ( !QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    return GetLastError();
  if ( *(_DWORD *)&Buffer[4] == 1 )
    return 0;
  if ( ControlService(a2, 1u, (LPSERVICE_STATUS)Buffer) )
  {
    v4 = 0;
    while ( QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, Buffer, 0x24u, &pcbBytesNeeded) )
    {
      if ( *(_DWORD *)&Buffer[4] == 1 )
        return v4;
      if ( GetTickCount() - TickCount > 0xEA60 )
        return 1053;
      v7 = DWORD2(v10) / 0x14;
      if ( DWORD2(v10) / 0x14 >= 0x3E8 )
      {
        if ( v7 > 0x2710 )
          v7 = 10000;
      }
      else
      {
        v7 = 1000;
      }
      Sleep(v7);
      if ( *(_DWORD *)&Buffer[4] == 1 )
        return v4;
    }
    return GetLastError();
  }
  LastError = GetLastError();
  result = 0;
  if ( LastError != 1062 )
    return LastError;
  return result;
}

```

## disassembly

```asm
0x180023700  mov     [rsp-18h+arg_0], rbx
0x180023705  mov     [rsp-18h+arg_10], rsi
0x18002370a  push    rbp
0x18002370b  push    rdi
0x18002370c  push    r12
0x18002370e  mov     rbp, rsp
0x180023711  sub     rsp, 70h
0x180023715  mov     rax, cs:__security_cookie
0x18002371c  xor     rax, rsp
0x18002371f  mov     [rbp+var_10], rax
0x180023723  xorps   xmm0, xmm0
0x180023726  xor     eax, eax
0x180023728  movups  xmmword ptr [rbp+Buffer], xmm0
0x18002372c  mov     [rbp+var_18], eax
0x18002372f  mov     rdi, rdx
0x180023732  movups  [rbp+var_28], xmm0
0x180023736  call    cs:__imp_GetTickCount
0x18002373c  mov     r9d, 24h ; '$'; cbBufSize
0x180023742  mov     [rbp+var_40], 0
0x180023749  mov     esi, eax
0x18002374b  lea     r8, [rbp+Buffer]; lpBuffer
0x18002374f  lea     rax, [rbp+var_40]
0x180023753  xor     edx, edx; InfoLevel
0x180023755  mov     rcx, rdi; hService
0x180023758  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18002375d  call    cs:__imp_QueryServiceStatusEx
0x180023763  test    eax, eax
0x180023765  jz      loc_18002381D
0x18002376b  cmp     dword ptr [rbp+Buffer+4], 1
0x18002376f  jnz     short loc_180023778
0x180023771  xor     ebx, ebx
0x180023773  jmp     loc_180023825
0x180023778  lea     r8, [rbp+Buffer]; lpServiceStatus
0x18002377c  mov     edx, 1; dwControl
0x180023781  mov     rcx, rdi; hService
0x180023784  call    cs:__imp_ControlService
0x18002378a  test    eax, eax
0x18002378c  jnz     short loc_1800237A6
0x18002378e  call    cs:__imp_GetLastError
0x180023794  mov     ecx, eax
0x180023796  xor     eax, eax
0x180023798  cmp     ecx, 426h
0x18002379e  cmovnz  eax, ecx
0x1800237a1  jmp     loc_180023827
0x1800237a6  xor     ebx, ebx
0x1800237a8  mov     r12d, 2710h
0x1800237ae  lea     rax, [rbp+var_40]
0x1800237b2  mov     r9d, 24h ; '$'; cbBufSize
0x1800237b8  lea     r8, [rbp+Buffer]; lpBuffer
0x1800237bc  mov     [rsp+70h+pcbBytesNeeded], rax; pcbBytesNeeded
0x1800237c1  xor     edx, edx; InfoLevel
0x1800237c3  mov     rcx, rdi; hService
0x1800237c6  call    cs:__imp_QueryServiceStatusEx
0x1800237cc  test    eax, eax
0x1800237ce  jz      short loc_18002381D
0x1800237d0  cmp     dword ptr [rbp+Buffer+4], 1
0x1800237d4  jz      short loc_180023825
0x1800237d6  call    cs:__imp_GetTickCount
0x1800237dc  sub     eax, esi
0x1800237de  cmp     eax, 0EA60h
0x1800237e3  ja      short loc_180023816
0x1800237e5  mov     eax, 0CCCCCCCDh
0x1800237ea  mul     dword ptr [rbp+var_28+8]
0x1800237ed  shr     edx, 4
0x1800237f0  cmp     edx, 3E8h
0x1800237f6  jnb     short loc_1800237FF
0x1800237f8  mov     edx, 3E8h
0x1800237fd  jmp     short loc_180023806
0x1800237ff  cmp     edx, r12d
0x180023802  cmova   edx, r12d
0x180023806  mov     ecx, edx; dwMilliseconds
0x180023808  call    cs:__imp_Sleep
0x18002380e  cmp     dword ptr [rbp+Buffer+4], 1
0x180023812  jnz     short loc_1800237AE
0x180023814  jmp     short loc_180023825
0x180023816  mov     ebx, 41Dh
0x18002381b  jmp     short loc_180023825
0x18002381d  call    cs:__imp_GetLastError
0x180023823  mov     ebx, eax
0x180023825  mov     eax, ebx
0x180023827  mov     rcx, [rbp+var_10]
0x18002382b  xor     rcx, rsp; StackCookie
0x18002382e  call    __security_check_cookie
0x180023833  lea     r11, [rsp+70h+var_s0]
0x180023838  mov     rbx, [r11+20h]
0x18002383c  mov     rsi, [r11+30h]
0x180023840  mov     rsp, r11
0x180023843  pop     r12
0x180023845  pop     rdi
0x180023846  pop     rbp
0x180023847  retn
```
