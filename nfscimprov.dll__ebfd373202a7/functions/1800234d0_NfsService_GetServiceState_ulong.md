# NfsService::GetServiceState(ulong *)

- ea: `0x1800234d0`
- end: `0x18002356b`
- name: `?GetServiceState@NfsService@@QEAAKPEAK@Z`
- size: `155`
- prototype: `unsigned int __fastcall(NfsService *__hidden this, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800103cc`
- `0x180010f28`

## callees

- `0x1800219fc`
- `0x1800234d0`
- `0x180035b40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002352c`
- `KERNEL32!GetLastError` at `0x18002352c`
- `ADVAPI32!QueryServiceStatus` at `0x180023522`
- `ADVAPI32!QueryServiceStatus` at `0x180023522`

## pseudocode

```c
__int64 __fastcall NfsService::GetServiceState(NfsService *this, unsigned int *a2)
{
  int v2; // eax
  unsigned int v4; // ebx
  _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  v2 = *((_DWORD *)this + 262);
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( v2 < 0 )
    return NfsGetErrorFromHr(v2);
  v4 = 0;
  if ( *((_QWORD *)this + 129) && *((_QWORD *)this + 130) )
  {
    if ( !QueryServiceStatus(*((SC_HANDLE *)this + 129), &ServiceStatus) )
      return GetLastError();
    *a2 = (ServiceStatus.dwCurrentState == 4) + 1;
  }
  else
  {
    *a2 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x1800234d0  mov     [rsp+arg_10], rbx
0x1800234d5  push    rdi
0x1800234d6  sub     rsp, 50h
0x1800234da  mov     rax, cs:__security_cookie
0x1800234e1  xor     rax, rsp
0x1800234e4  mov     [rsp+58h+var_18], rax
0x1800234e9  mov     eax, [rcx+418h]
0x1800234ef  xorps   xmm0, xmm0
0x1800234f2  mov     rdi, rdx
0x1800234f5  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1800234fa  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1800234ff  test    eax, eax
0x180023501  js      short loc_180023548
0x180023503  mov     rax, [rcx+408h]
0x18002350a  xor     ebx, ebx
0x18002350c  test    rax, rax
0x18002350f  jz      short loc_180023544
0x180023511  cmp     [rcx+410h], rbx
0x180023518  jz      short loc_180023544
0x18002351a  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x18002351f  mov     rcx, rax; hService
0x180023522  call    cs:__imp_QueryServiceStatus
0x180023528  test    eax, eax
0x18002352a  jnz     short loc_180023534
0x18002352c  call    cs:__imp_GetLastError
0x180023532  jmp     short loc_18002354F
0x180023534  xor     eax, eax
0x180023536  cmp     [rsp+58h+ServiceStatus.dwCurrentState], 4
0x18002353b  setz    al
0x18002353e  inc     eax
0x180023540  mov     [rdi], eax
0x180023542  jmp     short loc_180023551
0x180023544  mov     [rdx], ebx
0x180023546  jmp     short loc_180023551
0x180023548  mov     ecx, eax; int
0x18002354a  call    ?NfsGetErrorFromHr@@YAKJ@Z; NfsGetErrorFromHr(long)
0x18002354f  mov     ebx, eax
0x180023551  mov     eax, ebx
0x180023553  mov     rcx, [rsp+58h+var_18]
0x180023558  xor     rcx, rsp; StackCookie
0x18002355b  call    __security_check_cookie
0x180023560  mov     rbx, [rsp+58h+arg_10]
0x180023565  add     rsp, 50h
0x180023569  pop     rdi
0x18002356a  retn
```
