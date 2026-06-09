# AuthenticationContext::GetRefreshTokenInfo(ushort const *)

- ea: `0x140008a5c`
- end: `0x140008ba0`
- name: `?GetRefreshTokenInfo@AuthenticationContext@@QEAA?AURefreshTokenInfo@@PEBG@Z`
- size: `324`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x14000a34c`
- `0x140015dfc`

## callees

- `0x1400054e8`
- `0x14000579c`
- `0x140007bf8`
- `0x140008a5c`
- `0x14000f5f0`
- `0x140030010`

## pseudocode

```c
__int64 __fastcall AuthenticationContext::GetRefreshTokenInfo(__int64 a1, __int64 a2, __int64 a3)
{
  char v6; // bl
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v11; // [rsp+20h] [rbp-20h] BYREF
  __int64 v12; // [rsp+28h] [rbp-18h] BYREF
  _QWORD v13[2]; // [rsp+30h] [rbp-10h] BYREF

  v12 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v13[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  v13[1] = 0;
  *(_QWORD *)a2 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v11,
    a3);
  v6 = TokenCache::Get((unsigned __int8 (__fastcall ***)(_QWORD, _QWORD *, __int64))(a1 + 168), &v11, &v12, a1);
  v7 = (_QWORD *)(v11 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 8LL))(*v7);
  if ( v6 )
  {
    *(_BYTE *)(a2 + 8) = 0;
    v8 = v13;
  }
  else
  {
    *(_BYTE *)(a2 + 8) = 1;
    v8 = (_QWORD *)(a1 + 48);
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)a2,
    v8);
  CSecureString::~CSecureString((CSecureString *)v13);
  v9 = (_QWORD *)(v12 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v12 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  return a2;
}

```

## disassembly

```asm
0x140008a5c  mov     [rsp-18h+arg_0], rbx
0x140008a61  mov     [rsp-18h+arg_10], rsi
0x140008a66  mov     [rsp-18h+arg_8], rdx
0x140008a6b  push    rbp
0x140008a6c  push    rdi
0x140008a6d  push    r14
0x140008a6f  mov     rbp, rsp
0x140008a72  sub     rsp, 40h
0x140008a76  mov     rbx, r8
0x140008a79  mov     rdi, rdx
0x140008a7c  mov     rsi, rcx
0x140008a7f  mov     [rbp+arg_18], 1
0x140008a86  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008a8d  lea     r14, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008a94  mov     rcx, r14
0x140008a97  mov     rax, [rax+18h]
0x140008a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008aa0  add     rax, 18h
0x140008aa4  mov     [rbp+var_18], rax
0x140008aa8  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008aaf  mov     rcx, r14
0x140008ab2  mov     rax, [rax+18h]
0x140008ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008abb  add     rax, 18h
0x140008abf  mov     [rbp+var_10], rax
0x140008ac3  mov     [rbp+var_8], 0
0x140008acb  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140008ad2  mov     rcx, r14
0x140008ad5  mov     rax, [rax+18h]
0x140008ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ade  add     rax, 18h
0x140008ae2  mov     [rdi], rax
0x140008ae5  mov     [rbp+arg_18], 1
0x140008aec  mov     rdx, rbx
0x140008aef  lea     rcx, [rbp+var_20]
0x140008af3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140008af8  nop
0x140008af9  lea     rcx, [rsi+0A8h]
0x140008b00  mov     r9, rsi
0x140008b03  lea     r8, [rbp+var_18]
0x140008b07  lea     rdx, [rbp+var_20]
0x140008b0b  call    ?Get@TokenCache@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAVItem@1@PEAVILogContext@@@Z; TokenCache::Get(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,TokenCache::Item &,ILogContext *)
0x140008b10  mov     bl, al
0x140008b12  mov     rdx, [rbp+var_20]
0x140008b16  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140008b1a  or      r14d, 0FFFFFFFFh
0x140008b1e  mov     ecx, r14d
0x140008b21  lock xadd [rdx+10h], ecx
0x140008b26  add     ecx, r14d
0x140008b29  test    ecx, ecx
0x140008b2b  jg      short loc_140008B3C
0x140008b2d  mov     rcx, [rdx]
0x140008b30  mov     r8, [rcx]
0x140008b33  mov     rax, [r8+8]
0x140008b37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b3c  mov     rcx, rdi
0x140008b3f  test    bl, bl
0x140008b41  jz      short loc_140008B4D
0x140008b43  mov     byte ptr [rdi+8], 0
0x140008b47  lea     rdx, [rbp+var_10]
0x140008b4b  jmp     short loc_140008B55
0x140008b4d  mov     byte ptr [rdi+8], 1
0x140008b51  lea     rdx, [rsi+30h]
0x140008b55  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140008b5a  nop
0x140008b5b  lea     rcx, [rbp+var_10]; this
0x140008b5f  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140008b64  mov     rdx, [rbp+var_18]
0x140008b68  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140008b6c  mov     eax, r14d
0x140008b6f  lock xadd [rdx+10h], eax
0x140008b74  add     eax, r14d
0x140008b77  test    eax, eax
0x140008b79  jg      short loc_140008B8A
0x140008b7b  mov     rcx, [rdx]
0x140008b7e  mov     rax, [rcx]
0x140008b81  mov     rax, [rax+8]
0x140008b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008b8a  mov     rax, rdi
0x140008b8d  mov     rbx, [rsp+40h+arg_0]
0x140008b92  mov     rsi, [rsp+40h+arg_10]
0x140008b97  add     rsp, 40h
0x140008b9b  pop     r14
0x140008b9d  pop     rdi
0x140008b9e  pop     rbp
0x140008b9f  retn
```
