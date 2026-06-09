# _WSTrustTokenRequest::GetWSTrustResponse_::_1_::catch$41

- ea: `0x14002e298`
- end: `0x14002e341`
- name: `_WSTrustTokenRequest::GetWSTrustResponse_::_1_::catch$41`
- size: `169`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140005458`
- `0x1400055c8`
- `0x140005678`
- `0x140005954`
- `0x140007bf8`
- `0x140009c50`
- `0x14000c078`
- `0x1400168a8`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
void __fastcall __noreturn WSTrustTokenRequest::GetWSTrustResponse_::_1_::catch_41(__int64 a1, __int64 a2)
{
  Exception *v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rcx
  _QWORD *v7; // rax
  ResourceId *v8; // rax

  v3 = *(Exception **)(a2 + 96);
  v4 = Exception::ErrorCode(v3);
  v5 = *(_QWORD *)(a2 + 176);
  *(_DWORD *)(v5 + 60) = v4;
  v7 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 8LL))(v6, a2 + 176);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)(v5 + 72),
    v7);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((_QWORD *)(a2 + 176));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    v5 + 64,
    L"authentication_failed");
  Log::Error((const struct ILogContext *)v5, v3);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (_QWORD *)(a2 + 48),
    *(__int64 **)(a2 + 208));
  v8 = ResourceId::ResourceId((ResourceId *)(a2 + 176), 0x4AAE0009u);
  Log::Error<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
    v5,
    *(unsigned int *)(v5 + 60),
    *(unsigned int *)v8);
  throw;
}

```

## disassembly

```asm
0x14002e298  mov     [rsp+arg_8], rdx
0x14002e29d  push    rbx
0x14002e29e  push    rbp
0x14002e29f  push    rdi
0x14002e2a0  sub     rsp, 30h
0x14002e2a4  mov     rbp, rdx
0x14002e2a7  mov     rbx, [rbp+60h]
0x14002e2ab  mov     rcx, rbx; this
0x14002e2ae  call    ?ErrorCode@Exception@@QEBAKXZ; Exception::ErrorCode(void)
0x14002e2b3  mov     rdi, [rbp+0B0h]
0x14002e2ba  mov     [rdi+3Ch], eax
0x14002e2bd  mov     rax, [rbx]
0x14002e2c0  lea     rdx, [rbp+0B0h]
0x14002e2c7  mov     rax, [rax+8]
0x14002e2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002e2d0  nop
0x14002e2d1  lea     rcx, [rdi+48h]
0x14002e2d5  mov     rdx, rax
0x14002e2d8  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002e2dd  nop
0x14002e2de  lea     rcx, [rbp+0B0h]
0x14002e2e5  call    ??1?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::~CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x14002e2ea  lea     rcx, [rdi+40h]
0x14002e2ee  lea     rdx, aAuthentication; "authentication_failed"
0x14002e2f5  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ushort const *)
0x14002e2fa  mov     rdx, rbx; struct Exception *
0x14002e2fd  mov     rcx, rdi; struct ILogContext *
0x14002e300  call    ?Error@Log@@SAXPEBVILogContext@@AEBVException@@@Z; Log::Error(ILogContext const *,Exception const &)
0x14002e305  mov     rdx, [rbp+0D0h]
0x14002e30c  lea     rcx, [rbp+30h]
0x14002e310  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14002e315  mov     r9, rax
0x14002e318  mov     edx, 4AAE0009h; unsigned int
0x14002e31d  lea     rcx, [rbp+0B0h]; this
0x14002e324  call    ??0ResourceId@@QEAA@I@Z; ResourceId::ResourceId(uint)
0x14002e329  mov     r8d, [rax]
0x14002e32c  mov     edx, [rdi+3Ch]
0x14002e32f  mov     rcx, rdi
0x14002e332  call    ??$Error@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Log@@SAXPEBVILogContext@@KVResourceId@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; Log::Error<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ILogContext const *,ulong,ResourceId,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x14002e337  xor     edx, edx; pThrowInfo
0x14002e339  xor     ecx, ecx; pExceptionObject
0x14002e33b  call    _CxxThrowException_0
```
