# WaitForServiceStatus(SC_HANDLE__ *,ulong)

- ea: `0x180009ac4`
- end: `0x180009b44`
- name: `?WaitForServiceStatus@@YAXPEAUSC_HANDLE__@@K@Z`
- size: `128`
- prototype: `void __fastcall(SC_HANDLE hService, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800046a4`
- `0x180008ae0`

## callees

- `0x180009ac4`
- `0x18000fb50`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x180009afe`
- `ADVAPI32!QueryServiceStatus` at `0x180009afe`
- `KERNEL32!Sleep` at `0x180009b13`
- `KERNEL32!Sleep` at `0x180009b13`

## pseudocode

```c
void __fastcall WaitForServiceStatus(SC_HANDLE hService, int a2)
{
  unsigned int i; // ebx
  struct _SERVICE_STATUS ServiceStatus; // [rsp+20h] [rbp-38h] BYREF

  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  for ( i = 0; i < 0x2BF20; i += 500 )
  {
    if ( !QueryServiceStatus(hService, &ServiceStatus) )
      break;
    if ( ServiceStatus.dwCurrentState == a2 )
      break;
    Sleep(0x1F4u);
  }
}

```

## disassembly

```asm
0x180009ac4  mov     [rsp+arg_8], rbx
0x180009ac9  mov     [rsp+arg_10], rsi
0x180009ace  push    rdi
0x180009acf  sub     rsp, 50h
0x180009ad3  mov     rax, cs:__security_cookie
0x180009ada  xor     rax, rsp
0x180009add  mov     [rsp+58h+var_18], rax
0x180009ae2  xorps   xmm0, xmm0
0x180009ae5  mov     edi, edx
0x180009ae7  movups  xmmword ptr [rsp+58h+ServiceStatus.dwServiceType], xmm0
0x180009aec  mov     rsi, rcx
0x180009aef  xor     ebx, ebx
0x180009af1  movups  xmmword ptr [rsp+58h+ServiceStatus.dwWin32ExitCode], xmm0
0x180009af6  lea     rdx, [rsp+58h+ServiceStatus]; lpServiceStatus
0x180009afb  mov     rcx, rsi; hService
0x180009afe  call    cs:__imp_QueryServiceStatus
0x180009b04  test    eax, eax
0x180009b06  jz      short loc_180009B27
0x180009b08  cmp     [rsp+58h+ServiceStatus.dwCurrentState], edi
0x180009b0c  jz      short loc_180009B27
0x180009b0e  mov     ecx, 1F4h; dwMilliseconds
0x180009b13  call    cs:__imp_Sleep
0x180009b19  add     ebx, 1F4h
0x180009b1f  cmp     ebx, 2BF20h
0x180009b25  jb      short loc_180009AF6
0x180009b27  mov     rcx, [rsp+58h+var_18]
0x180009b2c  xor     rcx, rsp; StackCookie
0x180009b2f  call    __security_check_cookie
0x180009b34  mov     rbx, [rsp+58h+arg_8]
0x180009b39  mov     rsi, [rsp+58h+arg_10]
0x180009b3e  add     rsp, 50h
0x180009b42  pop     rdi
0x180009b43  retn
```
