# CMDCOM::CImpIConnectionPointContainer::EnumConnectionPoints(IEnumConnectionPoints * *)

- ea: `0x1800287a0`
- end: `0x18002885e`
- name: `?EnumConnectionPoints@CImpIConnectionPointContainer@CMDCOM@@UEAAJPEAPEAUIEnumConnectionPoints@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(struct IUnknown *this, struct IEnumConnectionPoints **)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800089c8`
- `0x180027b18`
- `0x180027c8c`
- `0x180028148`
- `0x1800287a0`
- `0x180031010`

## import_xrefs

- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028846`
- `IisRTL!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180028846`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800287bc`
- `IisRTL!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800287bc`

## pseudocode

```c
__int64 __fastcall CMDCOM::CImpIConnectionPointContainer::EnumConnectionPoints(
        struct IUnknown *this,
        struct IEnumConnectionPoints **a2)
{
  COEnumConnectionPoints *v4; // rax
  COEnumConnectionPoints *v5; // rax
  COEnumConnectionPoints *v6; // rdi
  unsigned int v7; // edx
  int v8; // ebx
  struct IConnectionPoint *v10[2]; // [rsp+20h] [rbp-18h] BYREF

  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)&g_LockSinkResource);
  *a2 = 0;
  *(_OWORD *)v10 = *(_OWORD *)&this[1].lpVtbl[1].AddRef;
  v4 = (COEnumConnectionPoints *)operator new(0x28u);
  if ( v4 && (v5 = COEnumConnectionPoints::COEnumConnectionPoints(v4, this), (v6 = v5) != 0) )
  {
    v8 = COEnumConnectionPoints::Init(v5, 2u, v10, 0);
    if ( v8 < 0
      || (v8 = (**(__int64 (__fastcall ***)(COEnumConnectionPoints *, GUID *, struct IEnumConnectionPoints **))v6)(
                 v6,
                 &IID_IEnumConnectionPoints,
                 a2),
          v8 < 0) )
    {
      COEnumConnectionPoints::`scalar deleting destructor'(v6, v7);
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)&g_LockSinkResource);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800287a0  mov     [rsp+arg_0], rbx
0x1800287a5  mov     [rsp+arg_8], rsi
0x1800287aa  push    rdi
0x1800287ab  sub     rsp, 30h
0x1800287af  mov     rbx, rcx
0x1800287b2  mov     rsi, rdx
0x1800287b5  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x1800287bc  call    cs:__imp_?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800287c2  mov     qword ptr [rsi], 0
0x1800287c9  mov     ecx, 28h ; '('; Size
0x1800287ce  mov     rax, [rbx+8]
0x1800287d2  movups  xmm0, xmmword ptr [rax+20h]
0x1800287d6  movups  xmmword ptr [rsp+38h+var_18], xmm0
0x1800287db  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800287e0  test    rax, rax
0x1800287e3  jz      short loc_18002883A
0x1800287e5  mov     rdx, rbx; struct IUnknown *
0x1800287e8  mov     rcx, rax; this
0x1800287eb  call    ??0COEnumConnectionPoints@@QEAA@PEAUIUnknown@@@Z; COEnumConnectionPoints::COEnumConnectionPoints(IUnknown *)
0x1800287f0  mov     rdi, rax
0x1800287f3  test    rax, rax
0x1800287f6  jz      short loc_18002883A
0x1800287f8  xor     r9d, r9d; unsigned int
0x1800287fb  lea     r8, [rsp+38h+var_18]; struct IConnectionPoint **
0x180028800  mov     rcx, rax; this
0x180028803  lea     edx, [r9+2]; unsigned int
0x180028807  call    ?Init@COEnumConnectionPoints@@QEAAJKPEAPEAUIConnectionPoint@@K@Z; COEnumConnectionPoints::Init(ulong,IConnectionPoint * *,ulong)
0x18002880c  mov     ebx, eax
0x18002880e  test    eax, eax
0x180028810  js      short loc_180028830
0x180028812  mov     rcx, [rdi]
0x180028815  lea     rdx, IID_IEnumConnectionPoints
0x18002881c  mov     r8, rsi
0x18002881f  mov     rax, [rcx]
0x180028822  mov     rcx, rdi
0x180028825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002882a  mov     ebx, eax
0x18002882c  test    eax, eax
0x18002882e  jns     short loc_18002883F
0x180028830  mov     rcx, rdi; this
0x180028833  call    ??_GCOEnumConnectionPoints@@QEAAPEAXI@Z; COEnumConnectionPoints::`scalar deleting destructor'(uint)
0x180028838  jmp     short loc_18002883F
0x18002883a  mov     ebx, 8007000Eh
0x18002883f  lea     rcx, ?g_LockSinkResource@@3VCReaderWriterLock3@@A; CReaderWriterLock3 g_LockSinkResource
0x180028846  call    cs:__imp_?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002884c  mov     rsi, [rsp+38h+arg_8]
0x180028851  mov     eax, ebx
0x180028853  mov     rbx, [rsp+38h+arg_0]
0x180028858  add     rsp, 30h
0x18002885c  pop     rdi
0x18002885d  retn
```
