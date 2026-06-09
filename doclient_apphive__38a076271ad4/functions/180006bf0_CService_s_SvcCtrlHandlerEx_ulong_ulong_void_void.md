# CService::s_SvcCtrlHandlerEx(ulong,ulong,void *,void *)

- ea: `0x180006bf0`
- end: `0x180006d1a`
- name: `?s_SvcCtrlHandlerEx@CService@@CAKKKPEAX0@Z`
- size: `298`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x180006bf0`
- `0x180006d20`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c8e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006c8e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006c96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180006c96`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006cc5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180006cc5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c1f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006c1f`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006c85`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180006c85`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CService::s_SvcCtrlHandlerEx(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        LPVOID lpContext)
{
  unsigned int v6; // esi
  CService *v7; // rbx
  const void *v8; // r9

  v6 = 0;
  if ( dwControl == 4 )
  {
    AcquireSRWLockExclusive(&CService::_svcStatusLock);
    if ( CService::_hSvcStatus )
    {
      CService::_svcStatusInfo.dwControlsAccepted = 0;
      if ( CService::_svcStatusInfo.dwCurrentState - 2 <= 1 )
      {
        ++CService::_svcStatusInfo.dwCheckPoint;
        CService::_svcStatusInfo.dwWaitHint = 60000;
      }
      else
      {
        *(_QWORD *)&CService::_svcStatusInfo.dwCheckPoint = 0;
        if ( CService::_svcStatusInfo.dwCurrentState == 4 )
        {
          CService::_svcStatusInfo.dwControlsAccepted = 1473;
        }
        else if ( CService::_svcStatusInfo.dwCurrentState == 1 )
        {
          *(_QWORD *)&CService::_svcStatusInfo.dwWin32ExitCode = 0;
        }
      }
      SetServiceStatus(CService::_hSvcStatus, &CService::_svcStatusInfo);
    }
    ReleaseSRWLockExclusive(&CService::_svcStatusLock);
  }
  else
  {
    AcquireSRWLockShared(&CService::_svcStatusLock);
    v7 = CService::s_spServiceRef;
    if ( CService::s_spServiceRef )
      (*(void (__fastcall **)(CService *))(*(_QWORD *)CService::s_spServiceRef + 8LL))(CService::s_spServiceRef);
    ReleaseSRWLockShared(&CService::_svcStatusLock);
    if ( v7 )
    {
      v6 = CService::_SvcCtrlHandler(v7, dwControl, dwEventType, v8);
      (*(void (__fastcall **)(CService *))(*(_QWORD *)v7 + 16LL))(v7);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180006bf0  mov     rax, rsp
0x180006bf3  mov     [rax+8], rbx
0x180006bf7  mov     [rax+10h], rbp
0x180006bfb  mov     [rax+18h], rsi
0x180006bff  mov     [rax+20h], rdi
0x180006c03  push    r14
0x180006c05  sub     rsp, 30h
0x180006c09  mov     r14d, edx
0x180006c0c  mov     ebp, ecx
0x180006c0e  xor     esi, esi
0x180006c10  lea     rdi, ?_svcStatusLock@CService@@0VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock CService::_svcStatusLock
0x180006c17  cmp     ecx, 4
0x180006c1a  mov     rcx, rdi; SRWLock
0x180006c1d  jnz     short loc_180006C96
0x180006c1f  call    cs:__imp_AcquireSRWLockExclusive
0x180006c25  mov     ecx, cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwCurrentState; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c2b  mov     r8, cs:?_hSvcStatus@CService@@0PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * CService::_hSvcStatus
0x180006c32  test    r8, r8
0x180006c35  jz      short loc_180006C8B
0x180006c37  mov     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwControlsAccepted, esi; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c3d  lea     eax, [rcx-2]
0x180006c40  cmp     eax, 1
0x180006c43  jbe     short loc_180006C6B
0x180006c45  mov     qword ptr cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwCheckPoint, rsi; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c4c  cmp     ecx, 4
0x180006c4f  jnz     short loc_180006C5D
0x180006c51  mov     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwControlsAccepted, 5C1h; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c5b  jmp     short loc_180006C7B
0x180006c5d  cmp     ecx, 1
0x180006c60  jnz     short loc_180006C7B
0x180006c62  mov     qword ptr cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwWin32ExitCode, rsi; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c69  jmp     short loc_180006C7B
0x180006c6b  inc     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwCheckPoint; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c71  mov     cs:?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS CService::_svcStatusInfo ...
0x180006c7b  lea     rdx, ?_svcStatusInfo@CService@@0U_SERVICE_STATUS@@A; lpServiceStatus
0x180006c82  mov     rcx, r8; hServiceStatus
0x180006c85  call    cs:__imp_SetServiceStatus
0x180006c8b  mov     rcx, rdi; SRWLock
0x180006c8e  call    cs:__imp_ReleaseSRWLockExclusive
0x180006c94  jmp     short loc_180006CFD
0x180006c96  call    cs:__imp_AcquireSRWLockShared
0x180006c9c  mov     [rsp+38h+var_18], rdi
0x180006ca1  mov     rbx, cs:?s_spServiceRef@CService@@0V?$ComPtr@VCService@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<CService> CService::s_spServiceRef
0x180006ca8  mov     [rsp+38h+var_10], rbx
0x180006cad  test    rbx, rbx
0x180006cb0  jz      short loc_180006CC2
0x180006cb2  mov     rax, [rbx]
0x180006cb5  mov     rcx, rbx
0x180006cb8  mov     rax, [rax+8]
0x180006cbc  call    _guard_dispatch_icall
0x180006cc1  nop
0x180006cc2  mov     rcx, rdi; SRWLock
0x180006cc5  call    cs:__imp_ReleaseSRWLockShared
0x180006ccb  mov     [rsp+38h+var_18], 0
0x180006cd4  test    rbx, rbx
0x180006cd7  jz      short loc_180006CE8
0x180006cd9  mov     r8d, r14d; unsigned int
0x180006cdc  mov     edx, ebp; unsigned int
0x180006cde  mov     rcx, rbx; this
0x180006ce1  call    ?_SvcCtrlHandler@CService@@AEAAKKKPEBX@Z; CService::_SvcCtrlHandler(ulong,ulong,void const *)
0x180006ce6  mov     esi, eax
0x180006ce8  test    rbx, rbx
0x180006ceb  jz      short loc_180006CFD
0x180006ced  mov     rcx, [rbx]
0x180006cf0  mov     rax, [rcx+10h]
0x180006cf4  mov     rcx, rbx
0x180006cf7  call    _guard_dispatch_icall
0x180006cfc  nop
0x180006cfd  mov     eax, esi
0x180006cff  mov     rbx, [rsp+38h+arg_0]
0x180006d04  mov     rbp, [rsp+38h+arg_8]
0x180006d09  mov     rsi, [rsp+38h+arg_10]
0x180006d0e  mov     rdi, [rsp+38h+arg_18]
0x180006d13  add     rsp, 30h
0x180006d17  pop     r14
0x180006d19  retn
```
