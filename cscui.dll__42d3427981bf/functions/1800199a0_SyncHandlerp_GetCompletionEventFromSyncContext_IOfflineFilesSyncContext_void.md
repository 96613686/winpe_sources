# SyncHandlerp_GetCompletionEventFromSyncContext(IOfflineFilesSyncContext *,void * *)

- ea: `0x1800199a0`
- end: `0x180019a0f`
- name: `?SyncHandlerp_GetCompletionEventFromSyncContext@@YAJPEAUIOfflineFilesSyncContext@@PEAPEAX@Z`
- size: `111`
- prototype: `__int64 __fastcall(struct IOfflineFilesSyncContext *, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180019450`
- `0x180019a20`

## callees

- `0x180008b40`
- `0x1800199a0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800199e2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800199e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800199fc`

## pseudocode

```c
__int64 __fastcall SyncHandlerp_GetCompletionEventFromSyncContext(struct IOfflineFilesSyncContext *a1, void **a2)
{
  __int64 v3; // rax
  int Error; // ebx
  HANDLE EventW; // rax
  LPCWSTR lpName; // [rsp+30h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = *(_QWORD *)a1;
  lpName = 0;
  Error = (*(__int64 (__fastcall **)(struct IOfflineFilesSyncContext *, LPCWSTR *))(v3 + 88))(a1, &lpName);
  if ( Error >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, lpName);
    *a2 = EventW;
    if ( !EventW )
      Error = ResultFromLastError();
    CoTaskMemFree((LPVOID)lpName);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800199a0  mov     [rsp+arg_8], rbx
0x1800199a5  push    rdi
0x1800199a6  sub     rsp, 20h
0x1800199aa  mov     qword ptr [rdx], 0
0x1800199b1  mov     rdi, rdx
0x1800199b4  mov     rax, [rcx]
0x1800199b7  lea     rdx, [rsp+28h+lpName]
0x1800199bc  mov     [rsp+28h+lpName], 0
0x1800199c5  mov     rax, [rax+58h]
0x1800199c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199ce  mov     ebx, eax
0x1800199d0  test    eax, eax
0x1800199d2  js      short loc_180019A02
0x1800199d4  mov     r9, [rsp+28h+lpName]; lpName
0x1800199d9  xor     r8d, r8d; bInitialState
0x1800199dc  xor     ecx, ecx; lpEventAttributes
0x1800199de  lea     edx, [r8+1]; bManualReset
0x1800199e2  call    cs:__imp_CreateEventW
0x1800199e8  mov     [rdi], rax
0x1800199eb  test    rax, rax
0x1800199ee  jnz     short loc_1800199F7
0x1800199f0  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1800199f5  mov     ebx, eax
0x1800199f7  mov     rcx, [rsp+28h+lpName]; pv
0x1800199fc  call    cs:__imp_CoTaskMemFree
0x180019a02  mov     eax, ebx
0x180019a04  mov     rbx, [rsp+28h+arg_8]
0x180019a09  add     rsp, 20h
0x180019a0d  pop     rdi
0x180019a0e  retn
```
