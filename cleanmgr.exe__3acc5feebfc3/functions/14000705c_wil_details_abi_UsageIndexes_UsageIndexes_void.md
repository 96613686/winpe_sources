# wil::details_abi::UsageIndexes::~UsageIndexes(void)

- ea: `0x14000705c`
- end: `0x1400070b3`
- name: `??1UsageIndexes@details_abi@wil@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, void *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140006f2c`
- `0x14000853c`
- `0x140008c6c`
- `0x1400177c0`

## callees

- `0x1400045bc`
- `0x14000705c`

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
0x14000705c  push    rbx
0x14000705e  sub     rsp, 20h
0x140007062  mov     rbx, rcx
0x140007065  mov     rcx, [rcx+0B0h]; this
0x14000706c  mov     qword ptr [rbx+0B0h], 0
0x140007077  test    rcx, rcx
0x14000707a  jz      short loc_140007081
0x14000707c  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140007081  mov     rcx, [rbx+70h]; this
0x140007085  mov     qword ptr [rbx+70h], 0
0x14000708d  test    rcx, rcx
0x140007090  jz      short loc_140007097
0x140007092  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x140007097  mov     rcx, [rbx+30h]; this
0x14000709b  mov     qword ptr [rbx+30h], 0
0x1400070a3  test    rcx, rcx
0x1400070a6  jz      short loc_1400070AD
0x1400070a8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1400070ad  add     rsp, 20h
0x1400070b1  pop     rbx
0x1400070b2  retn
```
