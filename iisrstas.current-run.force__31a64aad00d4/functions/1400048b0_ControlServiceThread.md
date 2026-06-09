# ControlServiceThread

- ea: `0x1400048b0`
- end: `0x140004944`
- name: `ControlServiceThread`
- size: `148`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x140001054`
- `0x1400048b0`
- `0x1400054c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400048f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400048f5`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400048eb`
- `api-ms-win-service-winsvc-l1-1-0!ControlService` at `0x1400048eb`

## pseudocode

```c
__int64 __fastcall ControlServiceThread(PVOID Parameter)
{
  signed int LastError; // eax
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( !Parameter )
    return 87;
  if ( ControlService(*((SC_HANDLE *)Parameter + 2), *((_DWORD *)Parameter + 2), &ServiceStatus) )
    goto LABEL_6;
  LastError = GetLastError();
  if ( LastError != 1062 )
  {
    if ( LastError <= 0 )
      goto LABEL_7;
LABEL_11:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_7;
  }
  if ( *((_DWORD *)Parameter + 2) != 1 )
    goto LABEL_11;
LABEL_6:
  LastError = 0;
LABEL_7:
  *(_DWORD *)Parameter = LastError;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)Parameter + 1, 0xFFFFFFFF) == 1 )
    operator delete(Parameter);
  return 0;
}

```

## disassembly

```asm
0x1400048b0  push    rbx
0x1400048b2  sub     rsp, 50h
0x1400048b6  mov     rax, cs:__security_cookie
0x1400048bd  xor     rax, rsp
0x1400048c0  mov     [rsp+58h+var_18], rax
0x1400048c5  xorps   xmm0, xmm0
0x1400048c8  mov     rbx, rcx
0x1400048cb  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x1400048d0  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x1400048d5  test    rcx, rcx
0x1400048d8  jnz     short loc_1400048DF
0x1400048da  lea     eax, [rcx+57h]
0x1400048dd  jmp     short loc_140004923
0x1400048df  mov     edx, [rcx+8]; dwControl
0x1400048e2  lea     r8, [rsp+58h+ServiceStatus]; lpServiceStatus
0x1400048e7  mov     rcx, [rcx+10h]; hService
0x1400048eb  call    cs:__imp_ControlService
0x1400048f1  test    eax, eax
0x1400048f3  jnz     short loc_140004908
0x1400048f5  call    cs:__imp_GetLastError
0x1400048fb  cmp     eax, 426h
0x140004900  jnz     short loc_140004936
0x140004902  cmp     dword ptr [rbx+8], 1
0x140004906  jnz     short loc_14000493A
0x140004908  xor     eax, eax
0x14000490a  mov     [rbx], eax
0x14000490c  or      eax, 0FFFFFFFFh
0x14000490f  lock xadd [rbx+4], eax
0x140004914  cmp     eax, 1
0x140004917  jnz     short loc_140004921
0x140004919  mov     rcx, rbx; Block
0x14000491c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004921  xor     eax, eax
0x140004923  mov     rcx, [rsp+58h+var_18]
0x140004928  xor     rcx, rsp; StackCookie
0x14000492b  call    __security_check_cookie
0x140004930  add     rsp, 50h
0x140004934  pop     rbx
0x140004935  retn
0x140004936  test    eax, eax
0x140004938  jle     short loc_14000490A
0x14000493a  movzx   eax, ax
0x14000493d  or      eax, 80070000h
0x140004942  jmp     short loc_14000490A
```
