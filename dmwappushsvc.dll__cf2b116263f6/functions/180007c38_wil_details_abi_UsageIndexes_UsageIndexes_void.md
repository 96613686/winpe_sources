# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180007c38`
- end: `0x180007c8f`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007ae0`
- `0x180009d5c`
- `0x18000a76c`
- `0x180011b3c`

## callees

- `0x180007c38`
- `0x180008794`

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
0x180007c38  push    rbx
0x180007c3a  sub     rsp, 20h
0x180007c3e  mov     rbx, rcx
0x180007c41  mov     rcx, [rcx+0B0h]; this
0x180007c48  mov     qword ptr [rbx+0B0h], 0
0x180007c53  test    rcx, rcx
0x180007c56  jz      short loc_180007C5D
0x180007c58  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007c5d  mov     rcx, [rbx+70h]; this
0x180007c61  mov     qword ptr [rbx+70h], 0
0x180007c69  test    rcx, rcx
0x180007c6c  jz      short loc_180007C73
0x180007c6e  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007c73  mov     rcx, [rbx+30h]; this
0x180007c77  mov     qword ptr [rbx+30h], 0
0x180007c7f  test    rcx, rcx
0x180007c82  jz      short loc_180007C89
0x180007c84  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180007c89  add     rsp, 20h
0x180007c8d  pop     rbx
0x180007c8e  retn
```
