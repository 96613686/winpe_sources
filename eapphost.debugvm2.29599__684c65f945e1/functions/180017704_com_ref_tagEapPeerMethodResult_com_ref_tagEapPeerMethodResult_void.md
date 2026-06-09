# com_ref<tagEapPeerMethodResult>::~com_ref<tagEapPeerMethodResult>(void)

- ea: `0x180017704`
- end: `0x180017764`
- name: `??1?$com_ref@UtagEapPeerMethodResult@@@@QEAA@XZ`
- size: `96`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800357ad`

## callees

- `0x18000343c`
- `0x180003fec`
- `0x18000404c`
- `0x180017704`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001771b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001774b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017711`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001771b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180017733`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001774b`

## pseudocode

```c
void *__fastcall com_ref<tagEapPeerMethodResult>::~com_ref<tagEapPeerMethodResult>(LPVOID *a1)
{
  void *v2; // rcx

  CoTaskMemFree(a1[2]);
  CoTaskMemFree(a1[4]);
  if ( a1[5] )
  {
    Free<TaskAllocator>();
    CoTaskMemFree(a1[5]);
  }
  v2 = a1[6];
  if ( v2 )
  {
    Free<TaskAllocator>(v2);
    CoTaskMemFree(a1[6]);
  }
  return memset_0(a1, 0, 0x48u);
}

```

## disassembly

```asm
0x180017704  push    rbx
0x180017706  sub     rsp, 20h
0x18001770a  mov     rbx, rcx
0x18001770d  mov     rcx, [rcx+10h]; pv
0x180017711  call    cs:__imp_CoTaskMemFree
0x180017717  mov     rcx, [rbx+20h]; pv
0x18001771b  call    cs:__imp_CoTaskMemFree
0x180017721  mov     rcx, [rbx+28h]
0x180017725  test    rcx, rcx
0x180017728  jz      short loc_180017739
0x18001772a  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x18001772f  mov     rcx, [rbx+28h]; pv
0x180017733  call    cs:__imp_CoTaskMemFree
0x180017739  mov     rcx, [rbx+30h]; void *
0x18001773d  test    rcx, rcx
0x180017740  jz      short loc_180017751
0x180017742  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180017747  mov     rcx, [rbx+30h]; pv
0x18001774b  call    cs:__imp_CoTaskMemFree
0x180017751  xor     edx, edx; Val
0x180017753  mov     rcx, rbx; void *
0x180017756  lea     r8d, [rdx+48h]; Size
0x18001775a  add     rsp, 20h
0x18001775e  pop     rbx
0x18001775f  jmp     memset_0
```
