# CImpIRowset::~CImpIRowset(void)

- ea: `0x18000a8a4`
- end: `0x18000a911`
- name: `??1CImpIRowset@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(CImpIRowset *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a5e8`

## callees

- `0x18000a8a4`
- `0x180031010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x18000a905`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CImpIRowset::~CImpIRowset(CImpIRowset *this)
{
  *((_QWORD *)this + 4) = &CImpIRowset::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 10) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180043128)(
      bidID,
      `CImpIRowset::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_337[0],
      7,
      *((int *)this + 10),
      0);
  *((_DWORD *)this + 10) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x18000a8a4  push    rbx
0x18000a8a6  sub     rsp, 30h
0x18000a8aa  mov     rbx, rcx
0x18000a8ad  lea     rax, ??_7CNotUpdt_BidGeneric@CImpIRowset@@6B@; const CImpIRowset::CNotUpdt_BidGeneric::`vftable'
0x18000a8b4  mov     [rcx+20h], rax
0x18000a8b8  cmp     dword ptr [rcx+28h], 0
0x18000a8bc  jz      short loc_18000A8F5
0x18000a8be  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x18000a8c6  jz      short loc_18000A8F5
0x18000a8c8  mov     rax, cs:off_180043128
0x18000a8cf  movsxd  r9, dword ptr [rcx+28h]
0x18000a8d3  mov     [rsp+38h+var_18], 0
0x18000a8dc  mov     r8d, 7
0x18000a8e2  mov     rdx, cs:?_bidPtrSA_053_337@?6??BidRecycleID@CNotUpdt_BidGeneric@CImpIRowset@@AEAAHXZ@4REBGEB; ushort const * const `CImpIRowset::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_337
0x18000a8e9  mov     rcx, cs:_bidID
0x18000a8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8f5  mov     dword ptr [rbx+28h], 0
0x18000a8fc  lea     rcx, [rbx+10h]
0x18000a900  add     rsp, 30h
0x18000a904  pop     rbx
0x18000a905  jmp     cs:__imp_MPDeleteCriticalSection
```
