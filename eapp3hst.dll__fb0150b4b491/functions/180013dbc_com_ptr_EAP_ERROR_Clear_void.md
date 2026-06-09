# com_ptr<_EAP_ERROR>::Clear(void)

- ea: `0x180013dbc`
- end: `0x180013de8`
- name: `?Clear@?$com_ptr@U_EAP_ERROR@@@@QEAAXXZ`
- size: `44`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `29`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180013bfc`
- `0x180013d44`
- `0x180014064`
- `0x1800140f4`
- `0x18001e83c`
- `0x18001e84c`
- `0x18001e85c`
- `0x18001e8b0`
- `0x18001eb30`
- `0x18001ede0`
- `0x18001efa0`
- `0x18001f170`
- `0x18001f360`
- `0x18001f440`
- `0x18001f5a0`
- `0x18001f680`
- `0x18001f7e0`
- `0x18001f990`
- `0x18001fb30`
- `0x1800280d0`
- `0x180028680`
- `0x1800287c0`
- `0x180028a60`
- `0x180028b60`
- `0x180028c90`
- `0x180028ec0`
- `0x180029040`
- `0x180029170`
- `0x1800292a0`

## callees

- `0x18001330c`
- `0x180013dbc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013dd5`

## pseudocode

```c
void __fastcall com_ptr<_EAP_ERROR>::Clear(LPVOID *a1)
{
  LPVOID *v2; // rcx

  v2 = (LPVOID *)*a1;
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(*a1);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180013dbc  push    rbx
0x180013dbe  sub     rsp, 20h
0x180013dc2  mov     rbx, rcx
0x180013dc5  mov     rcx, [rcx]; void *
0x180013dc8  test    rcx, rcx
0x180013dcb  jz      short loc_180013DE2
0x180013dcd  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180013dd2  mov     rcx, [rbx]; pv
0x180013dd5  call    cs:__imp_CoTaskMemFree
0x180013ddb  mov     qword ptr [rbx], 0
0x180013de2  add     rsp, 20h
0x180013de6  pop     rbx
0x180013de7  retn
```
