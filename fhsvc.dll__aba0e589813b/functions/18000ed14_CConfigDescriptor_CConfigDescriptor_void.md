# CConfigDescriptor::CConfigDescriptor(void)

- ea: `0x18000ed14`
- end: `0x18000edc0`
- name: `??0CConfigDescriptor@@QEAA@XZ`
- size: `172`
- prototype: `CConfigDescriptor *__fastcall(CConfigDescriptor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000aa08`

## callees

- `0x1800092b0`
- `0x18000b1cc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ed8c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000ed8c`

## pseudocode

```c
CConfigDescriptor *__fastcall CConfigDescriptor::CConfigDescriptor(CConfigDescriptor *this)
{
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+10h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(this);
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 7) = -1;
  *((_QWORD *)this + 8) = -1;
  *((_QWORD *)this + 9) = -1;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  *((_QWORD *)this + 13) = -1;
  *((_QWORD *)this + 14) = -1;
  *((_QWORD *)this + 15) = -1;
  *((_QWORD *)this + 16) = -1;
  SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>((_QWORD *)this + 17);
  *((_DWORD *)this + 36) = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)this + 4) = SystemTimeAsFileTime;
  *((_QWORD *)this + 6) = -1;
  *(_QWORD *)((char *)this + 148) = 0;
  return this;
}

```

## disassembly

```asm
0x18000ed14  mov     [rsp+arg_10], rbx
0x18000ed19  mov     [rsp+arg_18], rsi
0x18000ed1e  mov     [rsp+arg_0], rcx
0x18000ed23  push    rdi
0x18000ed24  sub     rsp, 20h
0x18000ed28  mov     rbx, rcx
0x18000ed2b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000ed30  nop
0x18000ed31  xor     edi, edi
0x18000ed33  mov     [rbx+8], rdi
0x18000ed37  mov     [rbx+10h], rdi
0x18000ed3b  mov     [rbx+18h], edi
0x18000ed3e  mov     [rbx+28h], rdi
0x18000ed42  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ed46  mov     [rbx+38h], rsi
0x18000ed4a  mov     [rbx+40h], rsi
0x18000ed4e  mov     [rbx+48h], rsi
0x18000ed52  mov     [rbx+50h], rdi
0x18000ed56  mov     [rbx+58h], rdi
0x18000ed5a  mov     [rbx+60h], edi
0x18000ed5d  mov     [rbx+68h], rsi
0x18000ed61  mov     [rbx+70h], rsi
0x18000ed65  mov     [rbx+78h], rsi
0x18000ed69  mov     [rbx+80h], rsi
0x18000ed70  lea     rcx, [rbx+88h]
0x18000ed77  call    ??0?$SmartPtr@VCWorkerThread@@@@QEAA@PEAVCWorkerThread@@@Z; SmartPtr<CWorkerThread>::SmartPtr<CWorkerThread>(CWorkerThread *)
0x18000ed7c  mov     [rbx+90h], edi
0x18000ed82  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18000ed87  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ed8c  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ed92  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x18000ed96  mov     [rbx+20h], eax
0x18000ed99  mov     eax, [rsp+28h+SystemTimeAsFileTime.dwHighDateTime]
0x18000ed9d  mov     [rbx+24h], eax
0x18000eda0  mov     [rbx+30h], rsi
0x18000eda4  xor     eax, eax
0x18000eda6  mov     [rbx+94h], rax
0x18000edad  mov     rax, rbx
0x18000edb0  mov     rbx, [rsp+28h+arg_10]
0x18000edb5  mov     rsi, [rsp+28h+arg_18]
0x18000edba  add     rsp, 20h
0x18000edbe  pop     rdi
0x18000edbf  retn
```
