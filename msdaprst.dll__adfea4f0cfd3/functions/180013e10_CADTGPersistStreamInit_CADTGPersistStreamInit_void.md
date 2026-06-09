# CADTGPersistStreamInit::~CADTGPersistStreamInit(void)

- ea: `0x180013e10`
- end: `0x180013e9d`
- name: `??1CADTGPersistStreamInit@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(CADTGPersistStreamInit *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180013d60`

## callees

- `0x180013e10`
- `0x180031010`

## import_xrefs

- `MSDART!MPDeleteCriticalSection` at `0x180013e91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CADTGPersistStreamInit::~CADTGPersistStreamInit(CADTGPersistStreamInit *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CADTGPersistStreamInit::`vftable';
  v2 = *((_QWORD *)this + 7);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  *((_QWORD *)this + 3) = &CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 8) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180043128)(
      bidID,
      `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_525[0],
      7,
      *((int *)this + 8),
      0);
  *((_DWORD *)this + 8) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x180013e10  push    rbx
0x180013e12  sub     rsp, 30h
0x180013e16  mov     rbx, rcx
0x180013e19  lea     rax, ??_7CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::`vftable'
0x180013e20  mov     [rcx], rax
0x180013e23  mov     rcx, [rcx+38h]
0x180013e27  test    rcx, rcx
0x180013e2a  jz      short loc_180013E39
0x180013e2c  mov     rax, [rcx]
0x180013e2f  mov     rax, [rax+10h]
0x180013e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e38  nop
0x180013e39  lea     rax, ??_7CNotUpdt_BidGeneric@CADTGPersistStreamInit@@6B@; const CADTGPersistStreamInit::CNotUpdt_BidGeneric::`vftable'
0x180013e40  mov     [rbx+18h], rax
0x180013e44  cmp     dword ptr [rbx+20h], 0
0x180013e48  jz      short loc_180013E81
0x180013e4a  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180013e52  jz      short loc_180013E81
0x180013e54  mov     rax, cs:off_180043128
0x180013e5b  movsxd  r9, dword ptr [rbx+20h]
0x180013e5f  mov     [rsp+38h+var_18], 0
0x180013e68  mov     r8d, 7
0x180013e6e  mov     rdx, cs:?_bidPtrSA_053_525@?6??BidRecycleID@CNotUpdt_BidGeneric@CADTGPersistStreamInit@@AEAAHXZ@4REBGEB; ushort const * const `CADTGPersistStreamInit::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_525
0x180013e75  mov     rcx, cs:_bidID
0x180013e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e81  mov     dword ptr [rbx+20h], 0
0x180013e88  lea     rcx, [rbx+10h]
0x180013e8c  add     rsp, 30h
0x180013e90  pop     rbx
0x180013e91  jmp     cs:__imp_MPDeleteCriticalSection
```
