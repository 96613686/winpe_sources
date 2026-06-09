# CuipAMUninitializeAPCProc(unsigned __int64)

- ea: `0x140006b30`
- end: `0x140006b9f`
- name: `?CuipAMUninitializeAPCProc@@YAX_K@Z`
- size: `111`
- prototype: `void __fastcall(_DWORD *Parameter)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x140006b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006b82`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140006b82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140006b97`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006b74`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140006b74`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140006b6e`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x140006b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006b53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006b53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140006b90`
- `Amsi!AmsiUninitialize` at `0x140006b66`
- `Amsi!AmsiUninitialize` at `0x140006b66`

## pseudocode

```c
void __fastcall CuipAMUninitializeAPCProc(_DWORD *Parameter)
{
  void *v2; // rcx
  HAMSICONTEXT v3; // rcx

  if ( *(_QWORD *)Parameter )
  {
    if ( !Parameter[4] )
    {
      v2 = *(void **)(*(_QWORD *)Parameter + 8LL);
      if ( v2 )
        CoTaskMemFree(v2);
    }
    LocalFree(*(HLOCAL *)Parameter);
  }
  v3 = *(HAMSICONTEXT *)(*((_QWORD *)Parameter + 1) + 32LL);
  if ( v3 )
  {
    AmsiUninitialize(v3);
    CoDisableCallCancellation(0);
    CoUninitialize();
  }
  SetEvent(*(HANDLE *)(*((_QWORD *)Parameter + 1) + 16LL));
  LocalFree(Parameter);
}

```

## disassembly

```asm
0x140006b30  push    rbx
0x140006b32  sub     rsp, 20h
0x140006b36  mov     rax, [rcx]
0x140006b39  mov     rbx, rcx
0x140006b3c  test    rax, rax
0x140006b3f  jz      short loc_140006B59
0x140006b41  cmp     dword ptr [rcx+10h], 0
0x140006b45  jnz     short loc_140006B50
0x140006b47  mov     rcx, [rax+8]; pv
0x140006b4b  test    rcx, rcx
0x140006b4e  jnz     short loc_140006B97
0x140006b50  mov     rcx, [rbx]; hMem
0x140006b53  call    cs:__imp_LocalFree
0x140006b59  mov     rax, [rbx+8]
0x140006b5d  mov     rcx, [rax+20h]; amsiContext
0x140006b61  test    rcx, rcx
0x140006b64  jz      short loc_140006B7A
0x140006b66  call    cs:__imp_AmsiUninitialize
0x140006b6c  xor     ecx, ecx; pReserved
0x140006b6e  call    cs:__imp_CoDisableCallCancellation
0x140006b74  call    cs:__imp_CoUninitialize
0x140006b7a  mov     rcx, [rbx+8]
0x140006b7e  mov     rcx, [rcx+10h]; hEvent
0x140006b82  call    cs:__imp_SetEvent
0x140006b88  mov     rcx, rbx
0x140006b8b  add     rsp, 20h
0x140006b8f  pop     rbx
0x140006b90  jmp     cs:__imp_LocalFree
0x140006b97  call    cs:__imp_CoTaskMemFree
0x140006b9d  jmp     short loc_140006B50
```
