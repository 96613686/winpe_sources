# Free<TaskAllocator>(_EAP_METHOD_INFO &)

- ea: `0x1800041a4`
- end: `0x1800041fc`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z`
- size: `88`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003dc8`
- `0x1800041a4`
- `0x180004204`

## callees

- `0x1800041a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041cb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800041e9`

## pseudocode

```c
void __fastcall Free<TaskAllocator>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx

  v2 = *(void **)(a1 + 16);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = *(void **)(a1 + 24);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *(_QWORD *)(a1 + 40) )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(*(LPVOID *)(a1 + 40));
  }
}

```

## disassembly

```asm
0x1800041a4  push    rbx
0x1800041a6  sub     rsp, 20h
0x1800041aa  mov     rbx, rcx
0x1800041ad  mov     rcx, [rcx+10h]; pv
0x1800041b1  test    rcx, rcx
0x1800041b4  jz      short loc_1800041C2
0x1800041b6  call    cs:__imp_CoTaskMemFree
0x1800041bd  nop     dword ptr [rax+rax+00h]
0x1800041c2  mov     rcx, [rbx+18h]; pv
0x1800041c6  test    rcx, rcx
0x1800041c9  jz      short loc_1800041D7
0x1800041cb  call    cs:__imp_CoTaskMemFree
0x1800041d2  nop     dword ptr [rax+rax+00h]
0x1800041d7  mov     rcx, [rbx+28h]
0x1800041db  test    rcx, rcx
0x1800041de  jz      short loc_1800041F5
0x1800041e0  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x1800041e5  mov     rcx, [rbx+28h]; pv
0x1800041e9  call    cs:__imp_CoTaskMemFree
0x1800041f0  nop     dword ptr [rax+rax+00h]
0x1800041f5  add     rsp, 20h
0x1800041f9  pop     rbx
0x1800041fa  retn
```
