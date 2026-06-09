# ChallengeResponseBuilder::CreateChallengeResponseForHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x140025ccc`
- end: `0x140025e3f`
- name: `?CreateChallengeResponseForHeader@ChallengeResponseBuilder@@QEAA?AVChallengeResponse@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `371`
- prototype: `__int64 __fastcall(const struct ILogContext **this, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14001604c`

## callees

- `0x140005458`
- `0x140005998`
- `0x14000be04`
- `0x14000c12c`
- `0x14000c7d8`
- `0x140025adc`
- `0x140025ccc`
- `0x140025e48`
- `0x140026800`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ChallengeResponseBuilder::CreateChallengeResponseForHeader(
        const struct ILogContext **this,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v6; // rdx
  volatile signed __int32 *v7; // rdx
  __int64 v9; // [rsp+20h] [rbp-39h] BYREF
  _QWORD pExceptionObject[2]; // [rsp+30h] [rbp-29h] BYREF
  __int64 v11; // [rsp+40h] [rbp-19h] BYREF
  __int64 v12; // [rsp+48h] [rbp-11h] BYREF
  __int64 v13; // [rsp+50h] [rbp-9h] BYREF
  __int64 v14; // [rsp+58h] [rbp-1h] BYREF
  __int64 v15; // [rsp+60h] [rbp+7h] BYREF
  __int64 v16; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v17; // [rsp+70h] [rbp+17h] BYREF
  __int64 v18; // [rsp+78h] [rbp+1Fh] BYREF
  __int64 v19; // [rsp+80h] [rbp+27h] BYREF
  __int64 v20; // [rsp+88h] [rbp+2Fh] BYREF
  __int64 v21; // [rsp+90h] [rbp+37h] BYREF
  __int64 v22[3]; // [rsp+98h] [rbp+3Fh] BYREF
  __int64 v23; // [rsp+D8h] [rbp+7Fh] BYREF

  ATL::operator+(&v23, a3, L",");
  if ( !*(_DWORD *)(*a3 - 16LL) )
  {
    Log::Error(this[2], 0xCAA82F76);
    Log::Verbose(this[2], L"Device Cert Request Invalid: challengeHeaderValue is empty");
    ArgumentException::ArgumentException((ArgumentException *)pExceptionObject, -894947466);
    throw (ArgumentException *)pExceptionObject;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v9,
    &v23);
  ChallengeResponseBuilder::GetChallengeRequestFromHeader(
    (ChallengeResponseBuilder *)this,
    (struct ChallengeRequest *)&v17);
  pExceptionObject[0] = &v11;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v11,
    &v17);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v12,
    &v18);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v13,
    &v19);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v14,
    &v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v15,
    &v21);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    v22);
  ChallengeResponseBuilder::GetDeviceCertResponse(this, a2, &v11);
  ChallengeRequest::~ChallengeRequest((ChallengeRequest *)&v17);
  v6 = (_QWORD *)(v23 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v23 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  v7 = (volatile signed __int32 *)(*a3 - 24LL);
  if ( _InterlockedDecrement(v7 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  return a2;
}

```

## disassembly

```asm
0x140025ccc  mov     [rsp-8+arg_0], rbx
0x140025cd1  mov     [rsp-8+arg_10], r8
0x140025cd6  push    rbp
0x140025cd7  push    rsi
0x140025cd8  push    rdi
0x140025cd9  lea     rbp, [rsp-47h]
0x140025cde  sub     rsp, 0A0h
0x140025ce5  mov     rbx, r8
0x140025ce8  mov     rdi, rdx
0x140025ceb  mov     rsi, rcx
0x140025cee  lea     r8, asc_140037514; ","
0x140025cf5  mov     rdx, rbx
0x140025cf8  lea     rcx, [rbp+57h+arg_18]
0x140025cfc  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140025d01  nop
0x140025d02  mov     rax, [rbx]
0x140025d05  cmp     dword ptr [rax-10h], 0
0x140025d09  jz      loc_140025E03
0x140025d0f  lea     rdx, [rbp+57h+arg_18]
0x140025d13  lea     rcx, [rbp+57h+var_90]
0x140025d17  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d1c  mov     r8, rax
0x140025d1f  lea     rdx, [rbp+57h+var_40]; struct ChallengeRequest *
0x140025d23  mov     rcx, rsi; this
0x140025d26  call    ?GetChallengeRequestFromHeader@ChallengeResponseBuilder@@AEAA?AVChallengeRequest@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; ChallengeResponseBuilder::GetChallengeRequestFromHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x140025d2b  nop
0x140025d2c  lea     rax, [rbp+57h+var_70]
0x140025d30  mov     [rbp+57h+pExceptionObject], rax
0x140025d34  lea     rdx, [rbp+57h+var_40]
0x140025d38  lea     rcx, [rbp+57h+var_70]
0x140025d3c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d41  nop
0x140025d42  lea     rdx, [rbp+57h+var_38]
0x140025d46  lea     rcx, [rbp+57h+var_68]
0x140025d4a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d4f  nop
0x140025d50  lea     rdx, [rbp+57h+var_30]
0x140025d54  lea     rcx, [rbp+57h+var_60]
0x140025d58  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d5d  nop
0x140025d5e  lea     rdx, [rbp+57h+var_28]
0x140025d62  lea     rcx, [rbp+57h+var_58]
0x140025d66  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d6b  nop
0x140025d6c  lea     rdx, [rbp+57h+var_20]
0x140025d70  lea     rcx, [rbp+57h+var_50]
0x140025d74  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d79  nop
0x140025d7a  lea     rdx, [rbp+57h+var_18]
0x140025d7e  lea     rcx, [rbp+57h+var_48]
0x140025d82  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140025d87  nop
0x140025d88  lea     r8, [rbp+57h+var_70]
0x140025d8c  mov     rdx, rdi
0x140025d8f  mov     rcx, rsi
0x140025d92  call    ?GetDeviceCertResponse@ChallengeResponseBuilder@@AEAA?AVChallengeResponse@@VChallengeRequest@@@Z; ChallengeResponseBuilder::GetDeviceCertResponse(ChallengeRequest)
0x140025d97  nop
0x140025d98  lea     rcx, [rbp+57h+var_40]; this
0x140025d9c  call    ??1ChallengeRequest@@QEAA@XZ; ChallengeRequest::~ChallengeRequest(void)
0x140025da1  nop
0x140025da2  mov     rdx, [rbp+57h+arg_18]
0x140025da6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025daa  or      esi, 0FFFFFFFFh
0x140025dad  mov     eax, esi
0x140025daf  lock xadd [rdx+10h], eax
0x140025db4  add     eax, esi
0x140025db6  test    eax, eax
0x140025db8  jg      short loc_140025DCA
0x140025dba  mov     rcx, [rdx]
0x140025dbd  mov     rax, [rcx]
0x140025dc0  mov     rax, [rax+8]
0x140025dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025dc9  nop
0x140025dca  mov     rdx, [rbx]
0x140025dcd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140025dd1  mov     eax, esi
0x140025dd3  lock xadd [rdx+10h], eax
0x140025dd8  add     eax, esi
0x140025dda  test    eax, eax
0x140025ddc  jg      short loc_140025DED
0x140025dde  mov     rcx, [rdx]
0x140025de1  mov     rax, [rcx]
0x140025de4  mov     rax, [rax+8]
0x140025de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025ded  mov     rax, rdi
0x140025df0  mov     rbx, [rsp+0B0h+arg_0]
0x140025df8  add     rsp, 0A0h
0x140025dff  pop     rdi
0x140025e00  pop     rsi
0x140025e01  pop     rbp
0x140025e02  retn
0x140025e03  mov     ebx, 0CAA82F76h
0x140025e08  mov     edx, ebx; unsigned int
0x140025e0a  mov     rcx, [rsi+10h]; struct ILogContext *
0x140025e0e  call    ?Error@Log@@SAXPEBVILogContext@@K@Z; Log::Error(ILogContext const *,ulong)
0x140025e13  lea     rdx, aDeviceCertRequ_0; "Device Cert Request Invalid: challengeH"...
0x140025e1a  mov     rcx, [rsi+10h]; struct ILogContext *
0x140025e1e  call    ?Verbose@Log@@SAXPEBVILogContext@@PEBGZZ; Log::Verbose(ILogContext const *,ushort const *,...)
0x140025e23  mov     edx, ebx; unsigned int
0x140025e25  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140025e29  call    ??0ArgumentException@@QEAA@K@Z; ArgumentException::ArgumentException(ulong)
0x140025e2e  lea     rdx, _TI3?AVArgumentException@@; pThrowInfo
0x140025e35  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140025e39  call    _CxxThrowException_0
```
