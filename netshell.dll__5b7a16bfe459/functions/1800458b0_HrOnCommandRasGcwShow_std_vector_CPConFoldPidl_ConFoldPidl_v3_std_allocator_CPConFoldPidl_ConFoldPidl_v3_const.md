# HrOnCommandRasGcwShow(std::vector<CPConFoldPidl<ConFoldPidl_v3>,std::allocator<CPConFoldPidl<ConFoldPidl_v3>>> const &,HWND__ *,IShellFolder *)

- ea: `0x1800458b0`
- end: `0x1800458f7`
- name: `?HrOnCommandRasGcwShow@@YAJAEBV?$vector@V?$CPConFoldPidl@VConFoldPidl_v3@@@@V?$allocator@V?$CPConFoldPidl@VConFoldPidl_v3@@@@@std@@@std@@PEAUHWND__@@PEAUIShellFolder@@@Z`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800458b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800458dc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800458dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800458ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800458ea`

## pseudocode

```c
__int64 HrOnCommandRasGcwShow()
{
  HANDLE v0; // rax
  DWORD ThreadId; // [rsp+58h] [rbp+20h] BYREF

  ThreadId = 0;
  v0 = CreateThread(0, 0, LaunchVANThreadProc, 0, 0, &ThreadId);
  if ( v0 )
    CloseHandle(v0);
  return 0;
}

```

## disassembly

```asm
0x1800458b0  sub     rsp, 38h
0x1800458b4  lea     rax, [rsp+38h+ThreadId]
0x1800458b9  mov     [rsp+38h+ThreadId], 0
0x1800458c1  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1800458c6  lea     r8, ?LaunchVANThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800458cd  xor     r9d, r9d; lpParameter
0x1800458d0  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1800458d8  xor     edx, edx; dwStackSize
0x1800458da  xor     ecx, ecx; lpThreadAttributes
0x1800458dc  call    cs:__imp_CreateThread
0x1800458e2  test    rax, rax
0x1800458e5  jz      short loc_1800458F0
0x1800458e7  mov     rcx, rax; hObject
0x1800458ea  call    cs:__imp_CloseHandle
0x1800458f0  xor     eax, eax
0x1800458f2  add     rsp, 38h
0x1800458f6  retn
```
