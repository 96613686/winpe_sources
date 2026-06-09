# WebRequest::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,void (*)(unsigned __int64,long))

- ea: `0x14002266c`
- end: `0x14002270c`
- name: `?Open@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00_NP6AX_KJ@Z@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `5`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000d9a8`
- `0x140014ea4`
- `0x1400176b4`
- `0x14001bd58`
- `0x1400249f0`

## callees

- `0x140007bf8`
- `0x14000e000`
- `0x14000f1b8`
- `0x14002266c`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall WebRequest::Open(__int64 a1, _QWORD *a2, _QWORD *a3, _QWORD *a4)
{
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1)
    || (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1) )
  {
    InvalidCallException::InvalidCallException((InvalidCallException *)pExceptionObject, -895418334);
    throw (InvalidCallException *)pExceptionObject;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)(a1 + 32),
    a2);
  Url::CreateUrl(a1 + 96, a3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)(a1 + 40),
    a4);
  *(_BYTE *)(a1 + 121) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 88), 1);
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
}

```

## disassembly

```asm
0x14002266c  push    rbx
0x14002266e  push    rbp
0x14002266f  push    rsi
0x140022670  push    rdi
0x140022671  sub     rsp, 38h
0x140022675  mov     rax, [rcx]
0x140022678  mov     rdi, r9
0x14002267b  mov     rsi, r8
0x14002267e  mov     rbp, rdx
0x140022681  mov     rbx, rcx
0x140022684  mov     rax, [rax+8]
0x140022688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002268d  test    al, al
0x14002268f  jnz     short loc_1400226EB
0x140022691  mov     rax, [rbx]
0x140022694  mov     rcx, rbx
0x140022697  mov     rax, [rax+10h]
0x14002269b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400226a0  test    al, al
0x1400226a2  jnz     short loc_1400226EB
0x1400226a4  lea     rcx, [rbx+20h]
0x1400226a8  mov     rdx, rbp
0x1400226ab  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400226b0  lea     rcx, [rbx+60h]
0x1400226b4  mov     rdx, rsi
0x1400226b7  call    ?CreateUrl@Url@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Url::CreateUrl(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400226bc  lea     rcx, [rbx+28h]
0x1400226c0  mov     rdx, rdi
0x1400226c3  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400226c8  mov     eax, 1
0x1400226cd  mov     byte ptr [rbx+79h], 0
0x1400226d1  xchg    eax, [rbx+58h]
0x1400226d4  mov     rcx, [rbx]
0x1400226d7  mov     rax, [rcx+28h]
0x1400226db  mov     rcx, rbx
0x1400226de  add     rsp, 38h
0x1400226e2  pop     rdi
0x1400226e3  pop     rsi
0x1400226e4  pop     rbp
0x1400226e5  pop     rbx
0x1400226e6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
0x1400226eb  mov     edx, 0CAA10022h; unsigned int
0x1400226f0  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1400226f5  call    ??0InvalidCallException@@QEAA@K@Z; InvalidCallException::InvalidCallException(ulong)
0x1400226fa  lea     rdx, _TI3?AVInvalidCallException@@; pThrowInfo
0x140022701  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140022706  call    _CxxThrowException_0
```
