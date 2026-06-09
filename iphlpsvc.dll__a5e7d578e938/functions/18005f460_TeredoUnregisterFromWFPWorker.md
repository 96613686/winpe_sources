# TeredoUnregisterFromWFPWorker

- ea: `0x18005f460`
- end: `0x18005f62d`
- name: `TeredoUnregisterFromWFPWorker`
- size: `461`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004f60`
- `0x1800076a8`
- `0x1800077e8`
- `0x18000cea0`
- `0x18000d7c0`
- `0x1800190f0`
- `0x180022b40`
- `0x1800363c4`
- `0x1800425f8`
- `0x180042e60`
- `0x18005f244`
- `0x18005f460`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f470`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005f470`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f4ff`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005f4ff`
- `fwpuclnt!FwpmEngineClose0` at `0x18005f5a6`
- `fwpuclnt!FwpmEngineClose0` at `0x18005f5a6`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005f588`
- `fwpuclnt!FwpmFilterUnsubscribeChanges0` at `0x18005f588`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4bc`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4d6`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4bc`
- `fwpuclnt!FwpmProviderDeleteByKey0` at `0x18005f4d6`

## string_xrefs

- `0x18005f600`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f615`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f51f`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f5ee`: `onecoreuap\net\netio\iphlpsvc\service\wfp.c`
- `0x18005f52f`: `Teredo un-registering with WFP in a worker: Unable to grab the config lock`

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
0x18005f460  push    rbx
0x18005f462  sub     rsp, 20h
0x18005f466  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x18005f46d  mov     rbx, rdx
0x18005f470  call    cs:__imp_EnterCriticalSection
0x18005f477  nop     dword ptr [rax+rax+00h]
0x18005f47c  mov     rcx, [rbx+0AE8h]
0x18005f483  mov     byte ptr [rbx+0AE4h], 1
0x18005f48a  test    rcx, rcx
0x18005f48d  jz      short loc_18005F4E2
0x18005f48f  lea     r8, [rbx+0B20h]
0x18005f496  call    EtDeleteWfpFilters
0x18005f49b  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f4a2  lea     rdx, [rbx+4C20h]
0x18005f4a9  call    EtRemoveAllFilters
0x18005f4ae  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f4b5  lea     rdx, [rbx+4C40h]; key
0x18005f4bc  call    cs:__imp_FwpmProviderDeleteByKey0
0x18005f4c3  nop     dword ptr [rax+rax+00h]
0x18005f4c8  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f4cf  lea     rdx, [rbx+4C80h]; key
0x18005f4d6  call    cs:__imp_FwpmProviderDeleteByKey0
0x18005f4dd  nop     dword ptr [rax+rax+00h]
0x18005f4e2  lea     rcx, [rbx+4C30h]
0x18005f4e9  call    EtRemoveOthersFilters
0x18005f4ee  lea     rcx, TeredoFiltersLock; lpCriticalSection
0x18005f4f5  mov     dword ptr [rbx+4C18h], 0
0x18005f4ff  call    cs:__imp_LeaveCriticalSection
0x18005f506  nop     dword ptr [rax+rax+00h]
0x18005f50b  mov     r9, cs:g_TeredoLock
0x18005f512  lea     rdx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f519  mov     r8d, 8A7h
0x18005f51f  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f526  call    GetAndTraceLock
0x18005f52b  test    eax, eax
0x18005f52d  jnz     short loc_18005F545
0x18005f52f  lea     rdx, aTeredoUnRegist; "Teredo un-registering with WFP in a wor"...
0x18005f536  mov     ecx, 100000h
0x18005f53b  call    EventWriteError0
0x18005f540  jmp     loc_18005F5FA
0x18005f545  mov     r8d, [rbx+0AD8h]
0x18005f54c  lea     eax, [r8-1]
0x18005f550  cmp     eax, 1
0x18005f553  jbe     short loc_18005F568
0x18005f555  lea     rdx, aUnregisteratio; "Unregisteration processing not necessar"...
0x18005f55c  mov     ecx, 100000h
0x18005f561  call    EventWrite0
0x18005f566  jmp     short loc_18005F5DA
0x18005f568  mov     rcx, rbx
0x18005f56b  call    TeredoStopCompartment
0x18005f570  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f577  test    rcx, rcx
0x18005f57a  jz      short loc_18005F5BD
0x18005f57c  mov     rdx, [rbx+0AF0h]; changeHandle
0x18005f583  test    rdx, rdx
0x18005f586  jz      short loc_18005F59F
0x18005f588  call    cs:__imp_FwpmFilterUnsubscribeChanges0
0x18005f58f  nop     dword ptr [rax+rax+00h]
0x18005f594  mov     qword ptr [rbx+0AF0h], 0
0x18005f59f  mov     rcx, [rbx+0AE8h]; engineHandle
0x18005f5a6  call    cs:__imp_FwpmEngineClose0
0x18005f5ad  nop     dword ptr [rax+rax+00h]
0x18005f5b2  mov     qword ptr [rbx+0AE8h], 0
0x18005f5bd  cmp     dword ptr [rbx+0AD8h], 2
0x18005f5c4  jnz     short loc_18005F5D0
0x18005f5c6  mov     rcx, rbx; context
0x18005f5c9  call    TeredoRegisterWithWFP
0x18005f5ce  jmp     short loc_18005F5DA
0x18005f5d0  mov     dword ptr [rbx+0AD8h], 0
0x18005f5da  mov     r9, cs:g_TeredoLock
0x18005f5e1  lea     rdx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f5e8  mov     r8d, 8D6h
0x18005f5ee  lea     rcx, aOnecoreuapNetN_48; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f5f5  call    ReleaseAndTraceLock
0x18005f5fa  mov     r8d, 8D9h
0x18005f600  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f607  mov     rcx, rbx
0x18005f60a  call    DereferenceCompartmentEx
0x18005f60f  mov     r8d, 8DAh
0x18005f615  lea     rdx, aOnecoreuapNetN_2; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18005f61c  lea     rcx, aTeredounregist_0; "TeredoUnregisterFromWFPWorker"
0x18005f623  add     rsp, 20h
0x18005f627  pop     rbx
0x18005f628  jmp     DereferenceServiceEx
```
