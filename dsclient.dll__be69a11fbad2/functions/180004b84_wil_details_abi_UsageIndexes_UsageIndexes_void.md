# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180004b84`
- end: `0x180004bdb`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004a54`
- `0x180006b68`
- `0x1800071dc`

## callees

- `0x180004b84`
- `0x18000563c`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::~UsageIndexes(wil::details_abi::UsageIndexes *this, void *a2)
{
  wil::details *v3; // rcx
  wil::details *v4; // rcx
  wil::details *v5; // rcx

  v3 = (wil::details *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v3 )
    wil::details::FreeProcessHeap(v3, a2);
  v4 = (wil::details *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = 0;
  if ( v4 )
    wil::details::FreeProcessHeap(v4, a2);
  v5 = (wil::details *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v5 )
    wil::details::FreeProcessHeap(v5, a2);
}

```

## disassembly

```asm
0x180004b84  push    rbx
0x180004b86  sub     rsp, 20h
0x180004b8a  mov     rbx, rcx
0x180004b8d  mov     rcx, [rcx+0B0h]; this
0x180004b94  mov     qword ptr [rbx+0B0h], 0
0x180004b9f  test    rcx, rcx
0x180004ba2  jz      short loc_180004BA9
0x180004ba4  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004ba9  mov     rcx, [rbx+70h]; this
0x180004bad  mov     qword ptr [rbx+70h], 0
0x180004bb5  test    rcx, rcx
0x180004bb8  jz      short loc_180004BBF
0x180004bba  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004bbf  mov     rcx, [rbx+30h]; this
0x180004bc3  mov     qword ptr [rbx+30h], 0
0x180004bcb  test    rcx, rcx
0x180004bce  jz      short loc_180004BD5
0x180004bd0  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180004bd5  add     rsp, 20h
0x180004bd9  pop     rbx
0x180004bda  retn
```
