# Free<TaskAllocator>(_EAP_METHOD_INFO &)

- ea: `0x180004084`
- end: `0x1800040c9`
- name: `??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z`
- size: `69`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003cec`
- `0x180004084`
- `0x1800040d0`

## callees

- `0x180004084`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040bd`

## pseudocode

```c
void __fastcall Free<TaskAllocator>(__int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  v2 = *(void **)(a1 + 16);
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = *(void **)(a1 + 24);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *(_QWORD *)(a1 + 40);
  if ( v4 )
  {
    Free<TaskAllocator>(v4);
    CoTaskMemFree(*(LPVOID *)(a1 + 40));
  }
}

```

## disassembly

```asm
0x180004084  push    rbx
0x180004086  sub     rsp, 20h
0x18000408a  mov     rbx, rcx
0x18000408d  mov     rcx, [rcx+10h]; pv
0x180004091  test    rcx, rcx
0x180004094  jz      short loc_18000409C
0x180004096  call    cs:__imp_CoTaskMemFree
0x18000409c  mov     rcx, [rbx+18h]; pv
0x1800040a0  test    rcx, rcx
0x1800040a3  jz      short loc_1800040AB
0x1800040a5  call    cs:__imp_CoTaskMemFree
0x1800040ab  mov     rcx, [rbx+28h]
0x1800040af  test    rcx, rcx
0x1800040b2  jz      short loc_1800040C3
0x1800040b4  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x1800040b9  mov     rcx, [rbx+28h]; pv
0x1800040bd  call    cs:__imp_CoTaskMemFree
0x1800040c3  add     rsp, 20h
0x1800040c7  pop     rbx
0x1800040c8  retn
```
