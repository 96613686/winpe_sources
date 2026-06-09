# HvSysConfigTimer::Teardown(void)

- ea: `0x180008818`
- end: `0x1800088b2`
- name: `?Teardown@HvSysConfigTimer@@QEAAXXZ`
- size: `154`
- prototype: `void __fastcall(HvSysConfigTimer *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x180004a80`

## callees

- `0x180008818`
- `0x180008e70`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000884c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000884c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800088a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800088a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000886b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000886b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000887d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000887d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000888a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000888a`

## pseudocode

```c
void __fastcall HvSysConfigTimer::Teardown(HvSysConfigTimer *this)
{
  bool v1; // bl

  v1 = 0;
  if ( qword_1800127C0 )
    wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
      (wil::details::registry_watcher_state **)&qword_1800127C0,
      0);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    v1 = WaitForSingleObject(hObject, 0xFFFFFFFF) == 0;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(pti, 1);
    CloseThreadpoolTimer(pti);
    pti = 0;
  }
  if ( v1 )
    ReleaseMutex(hObject);
}

```

## disassembly

```asm
0x180008818  push    rbx
0x18000881a  sub     rsp, 20h
0x18000881e  xor     bl, bl
0x180008820  cmp     cs:qword_1800127C0, 0
0x180008828  jz      short loc_180008838
0x18000882a  xor     edx, edx
0x18000882c  lea     rcx, qword_1800127C0
0x180008833  call    ?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)
0x180008838  mov     rcx, cs:hObject; hHandle
0x18000883f  lea     rax, [rcx-1]
0x180008843  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180008847  ja      short loc_180008857
0x180008849  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000884c  call    cs:__imp_WaitForSingleObject
0x180008852  test    eax, eax
0x180008854  setz    bl
0x180008857  mov     rcx, cs:pti; pti
0x18000885e  test    rcx, rcx
0x180008861  jz      short loc_18000889B
0x180008863  xor     r9d, r9d; msWindowLength
0x180008866  xor     r8d, r8d; msPeriod
0x180008869  xor     edx, edx; pftDueTime
0x18000886b  call    cs:__imp_SetThreadpoolTimer
0x180008871  mov     rcx, cs:pti; pti
0x180008878  mov     edx, 1; fCancelPendingCallbacks
0x18000887d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008883  mov     rcx, cs:pti; pti
0x18000888a  call    cs:__imp_CloseThreadpoolTimer
0x180008890  mov     cs:pti, 0
0x18000889b  test    bl, bl
0x18000889d  jz      short loc_1800088AC
0x18000889f  mov     rcx, cs:hObject; hMutex
0x1800088a6  call    cs:__imp_ReleaseMutex
0x1800088ac  add     rsp, 20h
0x1800088b0  pop     rbx
0x1800088b1  retn
```
