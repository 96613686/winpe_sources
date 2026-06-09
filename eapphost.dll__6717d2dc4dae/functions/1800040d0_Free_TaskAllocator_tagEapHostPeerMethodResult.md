# Free<TaskAllocator>(tagEapHostPeerMethodResult &)

- ea: `0x1800040d0`
- end: `0x180004148`
- name: `??$Free@VTaskAllocator@@@@YAXAEAUtagEapHostPeerMethodResult@@@Z`
- size: `120`
- prototype: `void *__fastcall(LPVOID *)`
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003dbc`
- `0x180006970`

## callees

- `0x18000343c`
- `0x180003fec`
- `0x18000404c`
- `0x180004084`
- `0x1800040d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000412f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800040ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004117`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000412f`

## pseudocode

```c
void *__fastcall Free<TaskAllocator>(LPVOID *a1)
{
  unsigned int *v2; // rcx
  __int64 v3; // rcx
  LPVOID *v4; // rcx

  CoTaskMemFree(a1[2]);
  CoTaskMemFree(a1[4]);
  v2 = (unsigned int *)a1[5];
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(a1[5]);
  }
  v3 = (__int64)a1[7];
  if ( v3 )
  {
    Free<TaskAllocator>(v3);
    CoTaskMemFree(a1[7]);
  }
  v4 = (LPVOID *)a1[8];
  if ( v4 )
  {
    Free<TaskAllocator>(v4);
    CoTaskMemFree(a1[8]);
  }
  return memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x1800040d0  push    rbx
0x1800040d2  sub     rsp, 20h
0x1800040d6  mov     rbx, rcx
0x1800040d9  mov     rcx, [rcx+10h]; pv
0x1800040dd  call    cs:__imp_CoTaskMemFree
0x1800040e3  mov     rcx, [rbx+20h]; pv
0x1800040e7  call    cs:__imp_CoTaskMemFree
0x1800040ed  mov     rcx, [rbx+28h]
0x1800040f1  test    rcx, rcx
0x1800040f4  jz      short loc_180004105
0x1800040f6  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x1800040fb  mov     rcx, [rbx+28h]; pv
0x1800040ff  call    cs:__imp_CoTaskMemFree
0x180004105  mov     rcx, [rbx+38h]
0x180004109  test    rcx, rcx
0x18000410c  jz      short loc_18000411D
0x18000410e  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_METHOD_INFO@@@Z; Free<TaskAllocator>(_EAP_METHOD_INFO &)
0x180004113  mov     rcx, [rbx+38h]; pv
0x180004117  call    cs:__imp_CoTaskMemFree
0x18000411d  mov     rcx, [rbx+40h]; void *
0x180004121  test    rcx, rcx
0x180004124  jz      short loc_180004135
0x180004126  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x18000412b  mov     rcx, [rbx+40h]; pv
0x18000412f  call    cs:__imp_CoTaskMemFree
0x180004135  xor     edx, edx; Val
0x180004137  mov     rcx, rbx; void *
0x18000413a  lea     r8d, [rdx+48h]; Size
0x18000413e  add     rsp, 20h
0x180004142  pop     rbx
0x180004143  jmp     memset_0
```
