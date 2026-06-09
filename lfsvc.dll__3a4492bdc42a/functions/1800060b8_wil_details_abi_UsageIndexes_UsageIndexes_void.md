# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x1800060b8`
- end: `0x18000610f`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ff8`
- `0x180008208`
- `0x180008658`
- `0x18000b544`
- `0x18000b556`

## callees

- `0x1800060b8`
- `0x180006b7c`

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
0x1800060b8  push    rbx
0x1800060ba  sub     rsp, 20h
0x1800060be  mov     rbx, rcx
0x1800060c1  mov     rcx, [rcx+0B0h]; this
0x1800060c8  mov     qword ptr [rbx+0B0h], 0
0x1800060d3  test    rcx, rcx
0x1800060d6  jz      short loc_1800060DD
0x1800060d8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800060dd  mov     rcx, [rbx+70h]; this
0x1800060e1  mov     qword ptr [rbx+70h], 0
0x1800060e9  test    rcx, rcx
0x1800060ec  jz      short loc_1800060F3
0x1800060ee  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800060f3  mov     rcx, [rbx+30h]; this
0x1800060f7  mov     qword ptr [rbx+30h], 0
0x1800060ff  test    rcx, rcx
0x180006102  jz      short loc_180006109
0x180006104  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180006109  add     rsp, 20h
0x18000610d  pop     rbx
0x18000610e  retn
```
