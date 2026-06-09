# JWSBuilder::EncodeJsonString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140029c50`
- end: `0x140029d42`
- name: `?EncodeJsonString@JWSBuilder@@AEAA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEBV23@@Z`
- size: `242`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140029854`
- `0x14002a154`

## callees

- `0x140007bf8`
- `0x14000caac`
- `0x14000e6a0`
- `0x1400129ec`
- `0x140012de4`
- `0x140029c50`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall JWSBuilder::EncodeJsonString(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v5; // rax
  _QWORD *v6; // rdx
  _BYTE pExceptionObject[16]; // [rsp+28h] [rbp-28h] BYREF
  __int128 v9; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+48h] [rbp-8h]
  __int64 v11; // [rsp+60h] [rbp+10h] BYREF
  _QWORD *v12; // [rsp+68h] [rbp+18h]

  v12 = a2;
  v11 = a1;
  *a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v9 = 0;
  v10 = 0;
  StringUtility::EncodeString(a3, &v9);
  v5 = (_QWORD *)StringUtility::Base64UrlEncode(&v11, v9, (unsigned int)(DWORD2(v9) - v9));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(a2, v5);
  v6 = (_QWORD *)(v11 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 - 24 + 16), 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 8LL))(*v6);
  if ( !*(_DWORD *)(*a2 - 16LL) )
  {
    Exception::Exception((Exception *)pExceptionObject, -894828542);
    throw (Exception *)pExceptionObject;
  }
  std::vector<unsigned char>::~vector<unsigned char>((char **)&v9);
  return a2;
}

```

## disassembly

```asm
0x140029c50  mov     rax, rsp
0x140029c53  mov     [rax+18h], rbx
0x140029c57  mov     [rax+20h], rdi
0x140029c5b  mov     [rax+10h], rdx
0x140029c5f  mov     [rax+8], rcx
0x140029c63  push    rbp
0x140029c64  mov     rbp, rsp
0x140029c67  sub     rsp, 50h
0x140029c6b  mov     rbx, r8
0x140029c6e  mov     rdi, rdx
0x140029c71  mov     [rbp+var_30], 0
0x140029c78  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140029c7f  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140029c86  mov     rax, [rax+18h]
0x140029c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029c8f  add     rax, 18h
0x140029c93  mov     [rdi], rax
0x140029c96  mov     [rbp+var_30], 1
0x140029c9d  xorps   xmm0, xmm0
0x140029ca0  movdqu  [rbp+var_18], xmm0
0x140029ca5  mov     [rbp+var_8], 0
0x140029cad  lea     rdx, [rbp+var_18]
0x140029cb1  mov     rcx, rbx
0x140029cb4  call    ?EncodeString@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$vector@EV?$allocator@E@std@@@std@@I@Z; StringUtility::EncodeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::vector<uchar> &,uint)
0x140029cb9  mov     rdx, qword ptr [rbp+var_18]
0x140029cbd  mov     r8d, dword ptr [rbp+var_18+8]
0x140029cc1  sub     r8d, edx
0x140029cc4  lea     rcx, [rbp+arg_0]
0x140029cc8  call    ?Base64UrlEncode@StringUtility@@SA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBEH@Z; StringUtility::Base64UrlEncode(uchar const *,int)
0x140029ccd  nop
0x140029cce  mov     rdx, rax
0x140029cd1  mov     rcx, rdi
0x140029cd4  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140029cd9  nop
0x140029cda  mov     rdx, [rbp+arg_0]
0x140029cde  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140029ce2  or      eax, 0FFFFFFFFh
0x140029ce5  lock xadd [rdx+10h], eax
0x140029cea  sub     eax, 1
0x140029ced  jg      short loc_140029CFE
0x140029cef  mov     rcx, [rdx]
0x140029cf2  mov     rax, [rcx]
0x140029cf5  mov     rax, [rax+8]
0x140029cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029cfe  mov     rax, [rdi]
0x140029d01  cmp     dword ptr [rax-10h], 0
0x140029d05  jz      short loc_140029D23
0x140029d07  lea     rcx, [rbp+var_18]
0x140029d0b  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x140029d10  mov     rax, rdi
0x140029d13  mov     rbx, [rsp+50h+arg_10]
0x140029d18  mov     rdi, [rsp+50h+arg_18]
0x140029d1d  add     rsp, 50h
0x140029d21  pop     rbp
0x140029d22  retn
0x140029d23  mov     edx, 0CAAA0002h; unsigned int
0x140029d28  lea     rcx, [rbp+pExceptionObject]; this
0x140029d2c  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x140029d31  lea     rdx, _TI1?AVException@@; pThrowInfo
0x140029d38  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140029d3c  call    _CxxThrowException_0
```
