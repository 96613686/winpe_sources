# com_ref<tagEapPeerMethodResult>::~com_ref<tagEapPeerMethodResult>(void)

- ea: `0x180027ec0`
- end: `0x180027f20`
- name: `??1?$com_ref@UtagEapPeerMethodResult@@@@QEAA@XZ`
- size: `96`
- prototype: `void *__fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180032cac`

## callees

- `0x18000213c`
- `0x18001330c`
- `0x180027ce4`
- `0x180027ec0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ecd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027ed7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027eef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180027f07`

## pseudocode

```c
void *__fastcall com_ref<tagEapPeerMethodResult>::~com_ref<tagEapPeerMethodResult>(LPVOID *a1)
{
  unsigned int *v2; // rcx
  LPVOID *v3; // rcx

  CoTaskMemFree(a1[2]);
  CoTaskMemFree(a1[4]);
  v2 = (unsigned int *)a1[5];
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(a1[5]);
  }
  v3 = (LPVOID *)a1[6];
  if ( v3 )
  {
    Free<TaskAllocator>(v3);
    CoTaskMemFree(a1[6]);
  }
  return memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x180027ec0  push    rbx
0x180027ec2  sub     rsp, 20h
0x180027ec6  mov     rbx, rcx
0x180027ec9  mov     rcx, [rcx+10h]; pv
0x180027ecd  call    cs:__imp_CoTaskMemFree
0x180027ed3  mov     rcx, [rbx+20h]; pv
0x180027ed7  call    cs:__imp_CoTaskMemFree
0x180027edd  mov     rcx, [rbx+28h]
0x180027ee1  test    rcx, rcx
0x180027ee4  jz      short loc_180027EF5
0x180027ee6  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x180027eeb  mov     rcx, [rbx+28h]; pv
0x180027eef  call    cs:__imp_CoTaskMemFree
0x180027ef5  mov     rcx, [rbx+30h]; void *
0x180027ef9  test    rcx, rcx
0x180027efc  jz      short loc_180027F0D
0x180027efe  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180027f03  mov     rcx, [rbx+30h]; pv
0x180027f07  call    cs:__imp_CoTaskMemFree
0x180027f0d  xor     edx, edx; Val
0x180027f0f  mov     rcx, rbx; void *
0x180027f12  lea     r8d, [rdx+48h]; Size
0x180027f16  add     rsp, 20h
0x180027f1a  pop     rbx
0x180027f1b  jmp     memset_0
```
