# CryptServiceMain(ulong,ushort * *)

- ea: `0x18000f2b0`
- end: `0x18000f361`
- name: `?CryptServiceMain@@YAXKPEAPEAG@Z`
- size: `177`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x18000f2b0`
- `0x18000f6c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f313`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2bf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f313`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f331`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f2e8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f331`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000f303`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18000f303`

## pseudocode

```c
void __fastcall CryptServiceMain(__int64 a1, unsigned __int16 **a2)
{
  int v2; // ebx
  SERVICE_STATUS_HANDLE v3; // rbx

  v2 = 0;
  AcquireSRWLockExclusive(&stru_180020220);
  if ( !sshStatusHandle && !dword_180020238 )
  {
    v2 = 1;
    dword_180020238 = 1;
  }
  ReleaseSRWLockExclusive(&stru_180020220);
  if ( v2 )
  {
    v3 = RegisterServiceCtrlHandlerExW(L"CryptSvc", service_ctrlEx, 0);
    AcquireSRWLockExclusive(&stru_180020220);
    sshStatusHandle = v3;
    dword_180020238 = 0;
    ReleaseSRWLockExclusive(&stru_180020220);
    if ( v3 )
    {
      ServiceStatus.dwServiceType = 16;
      ServiceStatus.dwServiceSpecificExitCode = 0;
      ServiceStatus.dwWin32ExitCode = ServiceStart();
    }
  }
}

```

## disassembly

```asm
0x18000f2b0  push    rbx
0x18000f2b2  sub     rsp, 20h
0x18000f2b6  lea     rcx, stru_180020220; SRWLock
0x18000f2bd  xor     ebx, ebx
0x18000f2bf  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2c5  cmp     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rbx; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x18000f2cc  jnz     short loc_18000F2E1
0x18000f2ce  cmp     cs:dword_180020238, ebx
0x18000f2d4  jnz     short loc_18000F2E1
0x18000f2d6  mov     ebx, 1
0x18000f2db  mov     cs:dword_180020238, ebx
0x18000f2e1  lea     rcx, stru_180020220; SRWLock
0x18000f2e8  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f2ee  test    ebx, ebx
0x18000f2f0  jz      short loc_18000F35B
0x18000f2f2  xor     r8d, r8d; lpContext
0x18000f2f5  lea     rdx, ?service_ctrlEx@@YAKKKPEAX0@Z; lpHandlerProc
0x18000f2fc  lea     rcx, ServiceName; "CryptSvc"
0x18000f303  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18000f309  lea     rcx, stru_180020220; SRWLock
0x18000f310  mov     rbx, rax
0x18000f313  call    cs:__imp_AcquireSRWLockExclusive
0x18000f319  lea     rcx, stru_180020220; SRWLock
0x18000f320  mov     cs:?sshStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rbx; SERVICE_STATUS_HANDLE__ * sshStatusHandle
0x18000f327  mov     cs:dword_180020238, 0
0x18000f331  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f337  test    rbx, rbx
0x18000f33a  jz      short loc_18000F35B
0x18000f33c  mov     cs:ServiceStatus.dwServiceType, 10h
0x18000f346  mov     cs:ServiceStatus.dwServiceSpecificExitCode, 0
0x18000f350  call    ServiceStart
0x18000f355  mov     cs:ServiceStatus.dwWin32ExitCode, eax
0x18000f35b  add     rsp, 20h
0x18000f35f  pop     rbx
0x18000f360  retn
```
