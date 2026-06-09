# Free<TaskAllocator>(_EAP_METHOD_INFO &)

- ea: `0x18000cf00`
- end: `0x18000cf58`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cf00`
- `0x18000cf94`

## callees

- `0x18000cf00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf45`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf27`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf45`

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
0x18000cf00  push    rbx
0x18000cf02  sub     rsp, 20h
0x18000cf06  mov     rbx, rcx
0x18000cf09  mov     rcx, [rcx+10h]; pv
0x18000cf0d  test    rcx, rcx
0x18000cf10  jz      short loc_18000CF1E
0x18000cf12  call    cs:__imp_CoTaskMemFree
0x18000cf19  nop     dword ptr [rax+rax+00h]
0x18000cf1e  mov     rcx, [rbx+18h]; pv
0x18000cf22  test    rcx, rcx
0x18000cf25  jz      short loc_18000CF33
0x18000cf27  call    cs:__imp_CoTaskMemFree
0x18000cf2e  nop     dword ptr [rax+rax+00h]
0x18000cf33  mov     rcx, [rbx+28h]
0x18000cf37  test    rcx, rcx
0x18000cf3a  jz      short loc_18000CF51
0x18000cf3c  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x18000cf41  mov     rcx, [rbx+28h]; pv
0x18000cf45  call    cs:__imp_CoTaskMemFree
0x18000cf4c  nop     dword ptr [rax+rax+00h]
0x18000cf51  add     rsp, 20h
0x18000cf55  pop     rbx
0x18000cf56  retn
```
