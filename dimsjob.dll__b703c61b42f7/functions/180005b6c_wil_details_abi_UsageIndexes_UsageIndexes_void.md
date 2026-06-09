# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x180005b6c`
- end: `0x180005bc3`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180005ab4`
- `0x180007fa8`
- `0x180008370`
- `0x18000b58d`

## callees

- `0x180005b6c`
- `0x1800064e4`

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
0x180005b6c  push    rbx
0x180005b6e  sub     rsp, 20h
0x180005b72  mov     rbx, rcx
0x180005b75  mov     rcx, [rcx+0B0h]; this
0x180005b7c  mov     qword ptr [rbx+0B0h], 0
0x180005b87  test    rcx, rcx
0x180005b8a  jz      short loc_180005B91
0x180005b8c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005b91  mov     rcx, [rbx+70h]; this
0x180005b95  mov     qword ptr [rbx+70h], 0
0x180005b9d  test    rcx, rcx
0x180005ba0  jz      short loc_180005BA7
0x180005ba2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005ba7  mov     rcx, [rbx+30h]; this
0x180005bab  mov     qword ptr [rbx+30h], 0
0x180005bb3  test    rcx, rcx
0x180005bb6  jz      short loc_180005BBD
0x180005bb8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180005bbd  add     rsp, 20h
0x180005bc1  pop     rbx
0x180005bc2  retn
```
