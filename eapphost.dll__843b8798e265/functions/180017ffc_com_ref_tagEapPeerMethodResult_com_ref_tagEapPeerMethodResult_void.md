# com_ref<tagEapPeerMethodResult>::~com_ref<tagEapPeerMethodResult>(void)

- ea: `0x180017ffc`
- end: `0x180018074`
- name: `??1?$com_ref@UtagEapPeerMethodResult@@@@QEAA@XZ`
- size: `120`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036b68`

## callees

- `0x1800034cc`
- `0x1800040f4`
- `0x180004160`
- `0x180017ffc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018055`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018019`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018037`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018055`

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
0x180017ffc  push    rbx
0x180017ffe  sub     rsp, 20h
0x180018002  mov     rbx, rcx
0x180018005  mov     rcx, [rcx+10h]; pv
0x180018009  call    cs:__imp_CoTaskMemFree
0x180018010  nop     dword ptr [rax+rax+00h]
0x180018015  mov     rcx, [rbx+20h]; pv
0x180018019  call    cs:__imp_CoTaskMemFree
0x180018020  nop     dword ptr [rax+rax+00h]
0x180018025  mov     rcx, [rbx+28h]
0x180018029  test    rcx, rcx
0x18001802c  jz      short loc_180018043
0x18001802e  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ATTRIBUTES@@@Z; Free<TaskAllocator>(_EAP_ATTRIBUTES &)
0x180018033  mov     rcx, [rbx+28h]; pv
0x180018037  call    cs:__imp_CoTaskMemFree
0x18001803e  nop     dword ptr [rax+rax+00h]
0x180018043  mov     rcx, [rbx+30h]; void *
0x180018047  test    rcx, rcx
0x18001804a  jz      short loc_180018061
0x18001804c  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_ERROR@@@Z; Free<TaskAllocator>(_EAP_ERROR &)
0x180018051  mov     rcx, [rbx+30h]; pv
0x180018055  call    cs:__imp_CoTaskMemFree
0x18001805c  nop     dword ptr [rax+rax+00h]
0x180018061  xor     edx, edx; Val
0x180018063  mov     rcx, rbx; void *
0x180018066  lea     r8d, [rdx+48h]; Size
0x18001806a  add     rsp, 20h
0x18001806e  pop     rbx
0x18001806f  jmp     memset_0
```
