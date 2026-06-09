# HrSvcQueryStatus(ushort const *,ulong *)

- ea: `0x180031328`
- end: `0x1800313d6`
- name: `?HrSvcQueryStatus@@YAJPEBGPEAK@Z`
- size: `174`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180022098`

## callees

- `0x180001710`
- `0x18003060c`
- `0x180031200`
- `0x18003123c`
- `0x1800312b4`
- `0x180031328`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x180031387`
- `ADVAPI32!QueryServiceStatus` at `0x180031387`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall HrSvcQueryStatus(const unsigned __int16 *a1, unsigned int *a2)
{
  unsigned int Win32Error; // ebx
  SC_HANDLE hService; // [rsp+30h] [rbp-48h] BYREF
  __int128 v6; // [rsp+38h] [rbp-40h] BYREF
  struct _SERVICE_STATUS ServiceStatus; // [rsp+48h] [rbp-30h] BYREF

  *a2 = 0;
  v6 = 0;
  hService = 0;
  Win32Error = CServiceManager::HrOpenService((SC_HANDLE *)&v6, (CService *)&hService);
  if ( !Win32Error )
  {
    memset(&ServiceStatus, 0, sizeof(ServiceStatus));
    if ( QueryServiceStatus(hService, &ServiceStatus) )
    {
      *a2 = ServiceStatus.dwCurrentState;
      Win32Error = 0;
    }
    else
    {
      *a2 = 0;
      Win32Error = HrFromLastWin32Error();
    }
  }
  CService::Close(&hService);
  CServiceManager::~CServiceManager((CServiceManager *)&v6);
  return Win32Error;
}

```

## disassembly

```asm
0x180031328  mov     r11, rsp
0x18003132b  mov     [r11+8], rbx
0x18003132f  push    rdi
0x180031330  sub     rsp, 70h
0x180031334  mov     rax, cs:__security_cookie
0x18003133b  xor     rax, rsp
0x18003133e  mov     [rsp+78h+var_10], rax
0x180031343  mov     rdi, rdx
0x180031346  mov     dword ptr [rdx], 0
0x18003134c  xorps   xmm0, xmm0
0x18003134f  movdqu  [rsp+78h+var_40], xmm0
0x180031355  mov     qword ptr [r11-48h], 0
0x18003135d  lea     rdx, [r11-48h]
0x180031361  lea     rcx, [r11-40h]
0x180031365  call    ?HrOpenService@CServiceManager@@QEAAJPEAVCService@@PEBGW4CSLOCK@@KK@Z; CServiceManager::HrOpenService(CService *,ushort const *,CSLOCK,ulong,ulong)
0x18003136a  mov     ebx, eax
0x18003136c  test    eax, eax
0x18003136e  jnz     short loc_1800313A4
0x180031370  xorps   xmm0, xmm0
0x180031373  movups  xmmword ptr [rsp+78h+ServiceStatus.dwServiceType], xmm0
0x180031378  movups  xmmword ptr [rsp+78h+ServiceStatus.dwWin32ExitCode], xmm0
0x18003137d  lea     rdx, [rsp+78h+ServiceStatus]; lpServiceStatus
0x180031382  mov     rcx, [rsp+78h+hService]; hService
0x180031387  call    cs:__imp_QueryServiceStatus
0x18003138d  test    eax, eax
0x18003138f  jnz     short loc_18003139C
0x180031391  mov     [rdi], eax
0x180031393  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180031398  mov     ebx, eax
0x18003139a  jmp     short loc_1800313A4
0x18003139c  mov     eax, [rsp+78h+ServiceStatus.dwCurrentState]
0x1800313a0  mov     [rdi], eax
0x1800313a2  xor     ebx, ebx
0x1800313a4  lea     rcx, [rsp+78h+hService]; this
0x1800313a9  call    ?Close@CService@@QEAAXXZ; CService::Close(void)
0x1800313ae  nop
0x1800313af  lea     rcx, [rsp+78h+var_40]; this
0x1800313b4  call    ??1CServiceManager@@QEAA@XZ; CServiceManager::~CServiceManager(void)
0x1800313b9  mov     eax, ebx
0x1800313bb  mov     rcx, [rsp+78h+var_10]
0x1800313c0  xor     rcx, rsp; StackCookie
0x1800313c3  call    __security_check_cookie
0x1800313c8  mov     rbx, [rsp+78h+arg_0]
0x1800313d0  add     rsp, 70h
0x1800313d4  pop     rdi
0x1800313d5  retn
```
