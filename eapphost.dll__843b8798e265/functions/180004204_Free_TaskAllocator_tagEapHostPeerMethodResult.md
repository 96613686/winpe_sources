# Free<TaskAllocator>(tagEapHostPeerMethodResult &)

- ea: `0x180004204`
- end: `0x18000429a`
- name: `??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003ea0`
- `0x180006c00`

## callees

- `0x1800034cc`
- `0x1800040f4`
- `0x180004160`
- `0x1800041a4`
- `0x180004204`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000423f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000425d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000427b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004221`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000423f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000425d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000427b`

## pseudocode

```c
void *__fastcall Free<TaskAllocator>(LPVOID *a1)
{
  void *v2; // rcx

  CoTaskMemFree(a1[2]);
  CoTaskMemFree(a1[4]);
  if ( a1[5] )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(a1[5]);
  }
  if ( a1[7] )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(a1[7]);
  }
  v2 = a1[8];
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(a1[8]);
  }
  return memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x180004204  push    rbx
0x180004206  sub     rsp, 20h
0x18000420a  mov     rbx, rcx
0x18000420d  mov     rcx, [rcx+10h]; pv
0x180004211  call    cs:__imp_CoTaskMemFree
0x180004218  nop     dword ptr [rax+rax+00h]
0x18000421d  mov     rcx, [rbx+20h]; pv
0x180004221  call    cs:__imp_CoTaskMemFree
0x180004228  nop     dword ptr [rax+rax+00h]
0x18000422d  mov     rcx, [rbx+28h]
0x180004231  test    rcx, rcx
0x180004234  jz      short loc_18000424B
0x180004236  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x18000423b  mov     rcx, [rbx+28h]; pv
0x18000423f  call    cs:__imp_CoTaskMemFree
0x180004246  nop     dword ptr [rax+rax+00h]
0x18000424b  mov     rcx, [rbx+38h]
0x18000424f  test    rcx, rcx
0x180004252  jz      short loc_180004269
0x180004254  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x180004259  mov     rcx, [rbx+38h]; pv
0x18000425d  call    cs:__imp_CoTaskMemFree
0x180004264  nop     dword ptr [rax+rax+00h]
0x180004269  mov     rcx, [rbx+40h]; void *
0x18000426d  test    rcx, rcx
0x180004270  jz      short loc_180004287
0x180004272  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180004277  mov     rcx, [rbx+40h]; pv
0x18000427b  call    cs:__imp_CoTaskMemFree
0x180004282  nop     dword ptr [rax+rax+00h]
0x180004287  xor     edx, edx; Val
0x180004289  mov     rcx, rbx; void *
0x18000428c  lea     r8d, [rdx+48h]; Size
0x180004290  add     rsp, 20h
0x180004294  pop     rbx
0x180004295  jmp     memset_0
```
