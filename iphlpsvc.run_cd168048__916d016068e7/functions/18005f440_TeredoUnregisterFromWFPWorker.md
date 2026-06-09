# TeredoUnregisterFromWFPWorker

- ea: `0x18005f440`
- end: `0x18005f60d`
- name: `TeredoUnregisterFromWFPWorker`
- size: `461`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f50`
- `0x180007698`
- `0x1800077d8`
- `0x18000ce90`
- `0x18000d7b0`
- `0x1800190e0`
- `0x180022b30`
- `0x1800363b4`
- `0x180042638`
- `0x180042ea0`
- `0x18005f224`
- `0x18005f440`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f450`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f450`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f4df`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f4df`
- `fwpuclnt!FwpmEngineClose0` at `0x18005f586`
- `fwpuclnt!FwpmEngineClose0` at `0x18005f586`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005f568`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005f568`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f49c`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4b6`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f49c`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4b6`

## string_xrefs

- `0x18005f5e0`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f5f5`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f4ff`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f5ce`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f50f`: `Teredo un-registering with WFP in a worker: Unable to grab the config lock`

## pseudocode

```c
void __fastcall TeredoUnregisterFromWFPWorker(PTP_CALLBACK_INSTANCE Instance, char *Context)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  void *v5; // rcx
  void *v6; // rdx

  EnterCriticalSection(&TeredoFiltersLock);
  v4 = *((_QWORD *)Context + 349);
  Context[2788] = 1;
  if ( v4 )
  {
    EtDeleteWfpFilters(v4, v3, Context + 2848);
    EtRemoveAllFilters(*((HANDLE *)Context + 349));
    FwpmProviderDeleteByKey0(*((HANDLE *)Context + 349), (const GUID *)Context + 1220);
    FwpmProviderDeleteByKey0(*((HANDLE *)Context + 349), (const GUID *)Context + 1224);
  }
  EtRemoveOthersFilters(Context + 19504);
  *((_DWORD *)Context + 4870) = 0;
  LeaveCriticalSection(&TeredoFiltersLock);
  if ( (unsigned int)GetAndTraceLock(
                       "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
                       "TeredoUnregisterFromWFPWorker",
                       2215,
                       g_TeredoLock) )
  {
    if ( (unsigned int)(*((_DWORD *)Context + 694) - 1) <= 1 )
    {
      TeredoStopCompartment(Context);
      v5 = (void *)*((_QWORD *)Context + 349);
      if ( v5 )
      {
        v6 = (void *)*((_QWORD *)Context + 350);
        if ( v6 )
        {
          FwpmFilterUnsubscribeChanges0(v5, v6);
          *((_QWORD *)Context + 350) = 0;
        }
        FwpmEngineClose0(*((HANDLE *)Context + 349));
        *((_QWORD *)Context + 349) = 0;
      }
      if ( *((_DWORD *)Context + 694) == 2 )
        TeredoRegisterWithWFP((FWPM_PROVIDER0 *)Context);
      else
        *((_DWORD *)Context + 694) = 0;
    }
    else
    {
      EventWrite0(0x100000, L"Unregisteration processing not necessary.Current state is %d");
    }
    ReleaseAndTraceLock(
      "onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c",
      "TeredoUnregisterFromWFPWorker",
      2262,
      g_TeredoLock);
  }
  else
  {
    EventWriteError0(0x100000, L"Teredo un-registering with WFP in a worker: Unable to grab the config lock");
  }
  DereferenceCompartmentEx(Context, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 2265);
  DereferenceServiceEx("TeredoUnregisterFromWFPWorker", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\wfp.c", 2266);
}

```

## disassembly

```asm
0x18005f440  push    rbx
0x18005f442  sub     rsp, 20h
0x18005f446  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x18005f44d  mov     rbx, rdx
0x18005f450  call    cs:__imp_EnterCriticalSection
0x18005f457  nop     dword ptr [rax+rax+00h]
0x18005f45c  mov     rcx, [rbx+0AE8h]
0x18005f463  mov     byte ptr [rbx+0AE4h], 1
0x18005f46a  test    rcx, rcx
0x18005f46d  jz      short loc_18005F4C2
0x18005f46f  lea     r8, [rbx+0B20h]
0x18005f476  call    EtDeleteWfpFilters
0x18005f47b  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f482  lea     rdx, [rbx+4C20h]
0x18005f489  call    EtRemoveAllFilters
0x18005f48e  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f495  lea     rdx, [rbx+4C40h]; key
0x18005f49c  call    cs:__imp_FwpmProviderDeleteByKey0
0x18005f4a3  nop     dword ptr [rax+rax+00h]
0x18005f4a8  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f4af  lea     rdx, [rbx+4C80h]; key
0x18005f4b6  call    cs:__imp_FwpmProviderDeleteByKey0
0x18005f4bd  nop     dword ptr [rax+rax+00h]
0x18005f4c2  lea     rcx, [rbx+4C30h]
0x18005f4c9  call    EtRemoveOthersFilters
0x18005f4ce  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x18005f4d5  mov     dword ptr [rbx+4C18h], 0
0x18005f4df  call    cs:__imp_LeaveCriticalSection
0x18005f4e6  nop     dword ptr [rax+rax+00h]
0x18005f4eb  mov     r9, cs:g_TeredoLock
0x18005f4f2  lea     rdx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f4f9  mov     r8d, 8A7h
0x18005f4ff  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f506  call    GetAndTraceLock
0x18005f50b  test    eax, eax
0x18005f50d  jnz     short loc_18005F525
0x18005f50f  lea     rdx, aTeredoUnRegist; "Teredo un-registering with WFP in a wor"...
0x18005f516  mov     ecx, 100000h
0x18005f51b  call    EventWriteError0
0x18005f520  jmp     loc_18005F5DA
0x18005f525  mov     r8d, [rbx+0AD8h]
0x18005f52c  lea     eax, [r8-1]
0x18005f530  cmp     eax, 1
0x18005f533  jbe     short loc_18005F548
0x18005f535  lea     rdx, aUnregisteratio; "Unregisteration processing not necessar"...
0x18005f53c  mov     ecx, 100000h
0x18005f541  call    EventWrite0
0x18005f546  jmp     short loc_18005F5BA
0x18005f548  mov     rcx, rbx
0x18005f54b  call    TeredoStopCompartment
0x18005f550  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f557  test    rcx, rcx
0x18005f55a  jz      short loc_18005F59D
0x18005f55c  mov     rdx, [rbx+0AF0h]; changeHandle
0x18005f563  test    rdx, rdx
0x18005f566  jz      short loc_18005F57F
0x18005f568  call    cs:__imp_FwpmFilterUnsubscribeChanges0
0x18005f56f  nop     dword ptr [rax+rax+00h]
0x18005f574  mov     qword ptr [rbx+0AF0h], 0
0x18005f57f  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f586  call    cs:__imp_FwpmEngineClose0
0x18005f58d  nop     dword ptr [rax+rax+00h]
0x18005f592  mov     qword ptr [rbx+0AE8h], 0
0x18005f59d  cmp     dword ptr [rbx+0AD8h], 2
0x18005f5a4  jnz     short loc_18005F5B0
0x18005f5a6  mov     rcx, rbx; context
0x18005f5a9  call    TeredoRegisterWithWFP
0x18005f5ae  jmp     short loc_18005F5BA
0x18005f5b0  mov     dword ptr [rbx+0AD8h], 0
0x18005f5ba  mov     r9, cs:g_TeredoLock
0x18005f5c1  lea     rdx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f5c8  mov     r8d, 8D6h
0x18005f5ce  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f5d5  call    ReleaseAndTraceLock
0x18005f5da  mov     r8d, 8D9h
0x18005f5e0  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f5e7  mov     rcx, rbx
0x18005f5ea  call    DereferenceCompartmentEx
0x18005f5ef  mov     r8d, 8DAh
0x18005f5f5  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f5fc  lea     rcx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f603  add     rsp, 20h
0x18005f607  pop     rbx
0x18005f608  jmp     DereferenceServiceEx
```
