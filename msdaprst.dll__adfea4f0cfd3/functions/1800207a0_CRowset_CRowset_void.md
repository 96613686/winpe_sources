# CRowset::~CRowset(void)

- ea: `0x1800207a0`
- end: `0x18002097d`
- name: `??1CRowset@@UEAA@XZ`
- size: `477`
- prototype: `void __fastcall(CRowset *__hidden this)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18000a6e4`
- `0x180020990`
- `0x180028df0`

## callees

- `0x180001db8`
- `0x1800027b0`
- `0x18001153c`
- `0x180017408`
- `0x1800207a0`
- `0x1800213b8`
- `0x18002e834`
- `0x180031010`

## import_xrefs

- `KERNEL32!VirtualFree` at `0x180020877`
- `KERNEL32!VirtualFree` at `0x180020877`
- `ole32!CoTaskMemFree` at `0x180020857`
- `ole32!CoTaskMemFree` at `0x180020857`
- `MSDART!MPDeleteCriticalSection` at `0x180020902`
- `MSDART!MPDeleteCriticalSection` at `0x180020902`
- `MSDART!MPDeleteCriticalSection` at `0x180020971`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRowset::~CRowset(CRowset *this)
{
  __int64 v2; // rcx
  void *v3; // rdi
  void *v4; // rcx
  __int64 v5; // rax
  unsigned int v6; // esi
  unsigned int i; // edi
  void *v8; // rdi
  void *v9; // [rsp+40h] [rbp+8h] BYREF

  *(_QWORD *)this = &CRowset::`vftable';
  v2 = *((_QWORD *)this + 49);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  ReleaseDataConvert(*((struct IDataConvert **)this + 66));
  operator delete(*((void **)this + 21));
  operator delete(*((void **)this + 20));
  operator delete(*((void **)this + 22));
  operator delete(*((void **)this + 23));
  operator delete(*((void **)this + 35));
  operator delete(*((void **)this + 36));
  operator delete(*((void **)this + 37));
  v3 = (void *)*((_QWORD *)this + 26);
  if ( v3 )
  {
    CExtBuffer::~CExtBuffer(*((CExtBuffer **)this + 26));
    operator delete(v3);
  }
  CoTaskMemFree(*((LPVOID *)this + 47));
  v4 = (void *)*((_QWORD *)this + 25);
  if ( v4 )
    VirtualFree(v4, 0, 0x8000u);
  v5 = *((_QWORD *)this + 24);
  if ( v5 )
  {
    v9 = 0;
    v6 = *(_DWORD *)(v5 + 4);
    for ( i = 1; i <= v6; ++i )
    {
      CExtBuffer::GetItemOfExtBuffer(*((CExtBuffer **)this + 24), i, &v9);
      operator delete(v9);
    }
    v8 = (void *)*((_QWORD *)this + 24);
    if ( v8 )
    {
      CExtBuffer::~CExtBuffer(*((CExtBuffer **)this + 24));
      operator delete(v8);
    }
  }
  CProps::~CProps((CRowset *)((char *)this + 400));
  CMetaData::~CMetaData((CRowset *)((char *)this + 304));
  MPDeleteCriticalSection((char *)this + 128);
  *((_QWORD *)this + 14) = &CRowset::CNotUpdt_BidGeneric::`vftable';
  if ( *((_DWORD *)this + 30) && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, _QWORD, _QWORD))off_180043128)(
      bidID,
      `CRowset::CNotUpdt_BidGeneric::BidRecycleID'::`7'::_bidPtrSA_053_221[0],
      7,
      *((int *)this + 30),
      0);
  *((_DWORD *)this + 30) = 0;
  MPDeleteCriticalSection((char *)this + 16);
}

```

## disassembly

```asm
0x1800207a0  mov     [rsp+arg_8], rbx
0x1800207a5  mov     [rsp+arg_10], rsi
0x1800207aa  push    rdi
0x1800207ab  sub     rsp, 30h
0x1800207af  mov     rbx, rcx
0x1800207b2  lea     rax, ??_7CRowset@@6B@; const CRowset::`vftable'
0x1800207b9  mov     [rcx], rax
0x1800207bc  mov     rcx, [rcx+188h]
0x1800207c3  test    rcx, rcx
0x1800207c6  jz      short loc_1800207D4
0x1800207c8  mov     rax, [rcx]
0x1800207cb  mov     rax, [rax+10h]
0x1800207cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800207d4  mov     rcx, [rbx+210h]; struct IDataConvert *
0x1800207db  call    ?ReleaseDataConvert@@YAXPEAUIDataConvert@@@Z; ReleaseDataConvert(IDataConvert *)
0x1800207e0  mov     rcx, [rbx+0A8h]; void *
0x1800207e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800207ec  mov     rcx, [rbx+0A0h]; void *
0x1800207f3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800207f8  mov     rcx, [rbx+0B0h]; void *
0x1800207ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020804  mov     rcx, [rbx+0B8h]; void *
0x18002080b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020810  mov     rcx, [rbx+118h]; void *
0x180020817  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002081c  mov     rcx, [rbx+120h]; void *
0x180020823  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020828  mov     rcx, [rbx+128h]; void *
0x18002082f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020834  mov     rdi, [rbx+0D0h]
0x18002083b  test    rdi, rdi
0x18002083e  jz      short loc_180020850
0x180020840  mov     rcx, rdi; this
0x180020843  call    ??1CExtBuffer@@QEAA@XZ; CExtBuffer::~CExtBuffer(void)
0x180020848  mov     rcx, rdi; void *
0x18002084b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180020850  mov     rcx, [rbx+178h]; pv
0x180020857  call    cs:__imp_CoTaskMemFree
0x18002085e  nop     dword ptr [rax+rax+00h]
0x180020863  mov     rcx, [rbx+0C8h]; lpAddress
0x18002086a  test    rcx, rcx
0x18002086d  jz      short loc_180020883
0x18002086f  xor     edx, edx; dwSize
0x180020871  mov     r8d, 8000h; dwFreeType
0x180020877  call    cs:__imp_VirtualFree
0x18002087e  nop     dword ptr [rax+rax+00h]
0x180020883  mov     rax, [rbx+0C0h]
0x18002088a  test    rax, rax
0x18002088d  jz      short loc_1800208E3
0x18002088f  mov     [rsp+38h+arg_0], 0
0x180020898  mov     esi, [rax+4]
0x18002089b  mov     edi, 1
0x1800208a0  cmp     esi, edi
0x1800208a2  jb      short loc_1800208C7
0x1800208a4  lea     r8, [rsp+38h+arg_0]; void *
0x1800208a9  mov     edx, edi; unsigned int
0x1800208ab  mov     rcx, [rbx+0C0h]; this
0x1800208b2  call    ?GetItemOfExtBuffer@CExtBuffer@@QEAAJKPEAX@Z; CExtBuffer::GetItemOfExtBuffer(ulong,void *)
0x1800208b7  mov     rcx, [rsp+38h+arg_0]; void *
0x1800208bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800208c1  inc     edi
0x1800208c3  cmp     edi, esi
0x1800208c5  jbe     short loc_1800208A4
0x1800208c7  mov     rdi, [rbx+0C0h]
0x1800208ce  test    rdi, rdi
0x1800208d1  jz      short loc_1800208E3
0x1800208d3  mov     rcx, rdi; this
0x1800208d6  call    ??1CExtBuffer@@QEAA@XZ; CExtBuffer::~CExtBuffer(void)
0x1800208db  mov     rcx, rdi; void *
0x1800208de  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800208e3  lea     rcx, [rbx+190h]; this
0x1800208ea  call    ??1CProps@@UEAA@XZ; CProps::~CProps(void)
0x1800208ef  lea     rcx, [rbx+130h]; this
0x1800208f6  call    ??1CMetaData@@QEAA@XZ; CMetaData::~CMetaData(void)
0x1800208fb  lea     rcx, [rbx+80h]
0x180020902  call    cs:__imp_MPDeleteCriticalSection
0x180020909  nop     dword ptr [rax+rax+00h]
0x18002090e  nop
0x18002090f  lea     rax, ??_7CNotUpdt_BidGeneric@CRowset@@6B@; const CRowset::CNotUpdt_BidGeneric::`vftable'
0x180020916  mov     [rbx+70h], rax
0x18002091a  cmp     dword ptr [rbx+78h], 0
0x18002091e  jz      short loc_180020957
0x180020920  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180020928  jz      short loc_180020957
0x18002092a  mov     rax, cs:off_180043128
0x180020931  movsxd  r9, dword ptr [rbx+78h]
0x180020935  mov     [rsp+38h+var_18], 0
0x18002093e  mov     r8d, 7
0x180020944  mov     rdx, cs:?_bidPtrSA_053_221@?6??BidRecycleID@CNotUpdt_BidGeneric@CRowset@@AEAAHXZ@4REBGEB; ushort const * const `CRowset::CNotUpdt_BidGeneric::BidRecycleID(void)'::`7'::_bidPtrSA_053_221
0x18002094b  mov     rcx, cs:_bidID
0x180020952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020957  mov     dword ptr [rbx+78h], 0
0x18002095e  lea     rcx, [rbx+10h]
0x180020962  mov     rbx, [rsp+38h+arg_8]
0x180020967  mov     rsi, [rsp+38h+arg_10]
0x18002096c  add     rsp, 30h
0x180020970  pop     rdi
0x180020971  jmp     cs:__imp_MPDeleteCriticalSection
```
