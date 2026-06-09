# CRecordGroup::~CRecordGroup(void)

- ea: `0x180011230`
- end: `0x18001132b`
- name: `??1CRecordGroup@@QEAA@XZ`
- size: `251`
- prototype: `void __fastcall(CRecordGroup *__hidden this)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x18004a31c`
- `0x1800af1f0`
- `0x1800ce309`
- `0x1800ce322`
- `0x1800ce33b`
- `0x1800ce8e4`
- `0x1800cf4c2`

## callees

- `0x180011230`
- `0x180011530`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x1800112a1`
- `MSDART!MpHeapFree` at `0x1800112c3`
- `MSDART!MpHeapFree` at `0x1800112a1`
- `MSDART!MpHeapFree` at `0x1800112c3`
- `ole32!CoTaskMemFree` at `0x1800112dd`
- `ole32!CoTaskMemFree` at `0x1800112dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRecordGroup::~CRecordGroup(CRecordGroup *this)
{
  __int64 v2; // rdx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rdx

  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    MpHeapFree(g_hHeapHandle, v2);
    *((_QWORD *)this + 5) = 0;
  }
  if ( *((_BYTE *)this + 96) )
  {
    v5 = *((_QWORD *)this + 6);
    if ( v5 )
    {
      MpHeapFree(g_hHeapHandle, v5);
      *((_QWORD *)this + 6) = 0;
    }
  }
  *((_QWORD *)this + 3) = 0;
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    operator delete(v3);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 11) = 0;
  }
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 && *((_DWORD *)this + 15) )
  {
    CoTaskMemFree(v4);
    *((_QWORD *)this + 9) = 0;
  }
  *((_BYTE *)this + 97) = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 13) = &CRecordGroup::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 28) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180121278)(
      bidID,
      `CRecordGroup::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_88[0],
      7,
      *((int *)this + 28),
      0);
  *((_DWORD *)this + 28) = 0;
}

```

## disassembly

```asm
0x180011230  mov     [rsp+arg_0], rbx
0x180011235  push    rdi
0x180011236  sub     rsp, 30h
0x18001123a  mov     rbx, rcx
0x18001123d  mov     rdx, [rcx+28h]
0x180011241  xor     edi, edi
0x180011243  test    rdx, rdx
0x180011246  jnz     short loc_18001129A
0x180011248  cmp     [rbx+60h], dil
0x18001124c  jnz     short loc_1800112B3
0x18001124e  mov     [rbx+18h], rdi
0x180011252  mov     rcx, [rbx+50h]; void *
0x180011256  test    rcx, rcx
0x180011259  jnz     short loc_18001128B
0x18001125b  mov     rcx, [rbx+48h]; pv
0x18001125f  test    rcx, rcx
0x180011262  jnz     short loc_1800112D8
0x180011264  mov     [rbx+61h], dil
0x180011268  mov     [rbx+8], rdi
0x18001126c  lea     rax, ??_7CNotUpdt_BidGeneric@CRecordGroup@@6B@; const CRecordGroup::CNotUpdt_BidGeneric::`vftable'
0x180011273  mov     [rbx+68h], rax
0x180011277  cmp     [rbx+70h], edi
0x18001127a  jnz     short loc_1800112F2
0x18001127c  mov     [rbx+70h], edi
0x18001127f  mov     rbx, [rsp+38h+arg_0]
0x180011284  add     rsp, 30h
0x180011288  pop     rdi
0x180011289  retn
0x18001128b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180011290  mov     [rbx+50h], rdi
0x180011294  mov     [rbx+58h], rdi
0x180011298  jmp     short loc_18001125B
0x18001129a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800112a1  call    cs:__imp_MpHeapFree
0x1800112a8  nop     dword ptr [rax+rax+00h]
0x1800112ad  mov     [rbx+28h], rdi
0x1800112b1  jmp     short loc_180011248
0x1800112b3  mov     rdx, [rbx+30h]
0x1800112b7  test    rdx, rdx
0x1800112ba  jz      short loc_18001124E
0x1800112bc  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800112c3  call    cs:__imp_MpHeapFree
0x1800112ca  nop     dword ptr [rax+rax+00h]
0x1800112cf  mov     [rbx+30h], rdi
0x1800112d3  jmp     loc_18001124E
0x1800112d8  cmp     [rbx+3Ch], edi
0x1800112db  jz      short loc_180011264
0x1800112dd  call    cs:__imp_CoTaskMemFree
0x1800112e4  nop     dword ptr [rax+rax+00h]
0x1800112e9  mov     [rbx+48h], rdi
0x1800112ed  jmp     loc_180011264
0x1800112f2  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x1800112fa  jz      short loc_18001127C
0x1800112fc  mov     rax, cs:off_180121278
0x180011303  movsxd  r9, dword ptr [rbx+70h]
0x180011307  mov     [rsp+38h+var_18], rdi
0x18001130c  mov     r8d, 7
0x180011312  mov     rdx, cs:?_bidPtrSA_053_88@?6??BidRecycleID@CNotUpdt_BidGeneric@CRecordGroup@@AEAAHXZ@4REBGEB; ushort const * const `CRecordGroup::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_88
0x180011319  mov     rcx, cs:_bidID
0x180011320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011325  jmp     loc_18001127C
```
