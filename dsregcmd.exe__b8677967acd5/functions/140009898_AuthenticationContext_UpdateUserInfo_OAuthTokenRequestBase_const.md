# AuthenticationContext::UpdateUserInfo(OAuthTokenRequestBase const &)

- ea: `0x140009898`
- end: `0x140009b1d`
- name: `?UpdateUserInfo@AuthenticationContext@@AEAAXAEBVOAuthTokenRequestBase@@@Z`
- size: `645`
- prototype: `void __fastcall(AuthenticationContext *__hidden this, const struct OAuthTokenRequestBase *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140009518`

## callees

- `0x140005458`
- `0x140007bf8`
- `0x140009898`
- `0x140014bd8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AuthenticationContext::UpdateUserInfo(
        AuthenticationContext *this,
        const struct OAuthTokenRequestBase *a2)
{
  __int64 *IdToken; // rax
  __int64 v4; // rdx
  __int64 v5; // r8
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rbx
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  _QWORD *v10; // rdx
  _QWORD *v11; // rdx
  _QWORD *v12; // rdx
  _QWORD *v13; // rdx
  __int64 v14; // [rsp+20h] [rbp-18h] BYREF
  volatile signed __int32 *v15; // [rsp+28h] [rbp-10h]
  __int64 v16; // [rsp+60h] [rbp+28h] BYREF

  IdToken = OAuthTokenRequestBase::GetIdToken(a2, &v14);
  v4 = *IdToken;
  v5 = IdToken[1];
  *IdToken = 0;
  IdToken[1] = 0;
  *((_QWORD *)this + 38) = v4;
  v6 = (volatile signed __int32 *)*((_QWORD *)this + 39);
  *((_QWORD *)this + 39) = v5;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = v15;
  if ( v15 )
  {
    if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 40LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 40,
    &v16);
  v8 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 32LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 41,
    &v16);
  v9 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 24LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 42,
    &v16);
  v10 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v10 + 8LL))(*v10);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 56LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 43,
    &v16);
  v11 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 64LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 44,
    &v16);
  v12 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 8LL))(*v12);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &v16,
    (__int64 *)(*((_QWORD *)this + 38) + 72LL));
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
    (_QWORD *)this + 45,
    &v16);
  v13 = (_QWORD *)(v16 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v16 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v13 + 8LL))(*v13);
}

```

## disassembly

```asm
0x140009898  push    rbp
0x14000989a  push    rbx
0x14000989b  push    rsi
0x14000989c  push    rdi
0x14000989d  mov     rbp, rsp
0x1400098a0  sub     rsp, 38h
0x1400098a4  mov     rax, rdx
0x1400098a7  mov     rdi, rcx
0x1400098aa  lea     rdx, [rbp+var_18]
0x1400098ae  mov     rcx, rax
0x1400098b1  call    ?GetIdToken@OAuthTokenRequestBase@@QEBA?AV?$shared_ptr@VIdToken@@@std@@XZ; OAuthTokenRequestBase::GetIdToken(void)
0x1400098b6  mov     rdx, [rax]
0x1400098b9  mov     r8, [rax+8]
0x1400098bd  mov     qword ptr [rax], 0
0x1400098c4  mov     qword ptr [rax+8], 0
0x1400098cc  mov     [rdi+130h], rdx
0x1400098d3  mov     rbx, [rdi+138h]
0x1400098da  mov     [rdi+138h], r8
0x1400098e1  or      esi, 0FFFFFFFFh
0x1400098e4  test    rbx, rbx
0x1400098e7  jz      short loc_14000991C
0x1400098e9  mov     eax, esi
0x1400098eb  lock xadd [rbx+8], eax
0x1400098f0  add     eax, esi
0x1400098f2  jnz     short loc_14000991C
0x1400098f4  mov     rax, [rbx]
0x1400098f7  mov     rcx, rbx
0x1400098fa  mov     rax, [rax]
0x1400098fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009902  mov     eax, esi
0x140009904  lock xadd [rbx+0Ch], eax
0x140009909  add     eax, esi
0x14000990b  jnz     short loc_14000991C
0x14000990d  mov     rax, [rbx]
0x140009910  mov     rcx, rbx
0x140009913  mov     rax, [rax+8]
0x140009917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000991c  mov     rbx, [rbp+var_10]
0x140009920  test    rbx, rbx
0x140009923  jz      short loc_140009958
0x140009925  mov     eax, esi
0x140009927  lock xadd [rbx+8], eax
0x14000992c  add     eax, esi
0x14000992e  jnz     short loc_140009958
0x140009930  mov     rax, [rbx]
0x140009933  mov     rcx, rbx
0x140009936  mov     rax, [rax]
0x140009939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000993e  mov     eax, esi
0x140009940  lock xadd [rbx+0Ch], eax
0x140009945  add     eax, esi
0x140009947  jnz     short loc_140009958
0x140009949  mov     rax, [rbx]
0x14000994c  mov     rcx, rbx
0x14000994f  mov     rax, [rax+8]
0x140009953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009958  mov     rdx, [rdi+130h]
0x14000995f  add     rdx, 28h ; '('
0x140009963  lea     rcx, [rbp+arg_0]
0x140009967  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000996c  nop
0x14000996d  lea     rcx, [rdi+140h]
0x140009974  lea     rdx, [rbp+arg_0]
0x140009978  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x14000997d  nop
0x14000997e  mov     rdx, [rbp+arg_0]
0x140009982  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009986  mov     eax, esi
0x140009988  lock xadd [rdx+10h], eax
0x14000998d  add     eax, esi
0x14000998f  test    eax, eax
0x140009991  jg      short loc_1400099A2
0x140009993  mov     rcx, [rdx]
0x140009996  mov     rax, [rcx]
0x140009999  mov     rax, [rax+8]
0x14000999d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099a2  mov     rdx, [rdi+130h]
0x1400099a9  add     rdx, 20h ; ' '
0x1400099ad  lea     rcx, [rbp+arg_0]
0x1400099b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400099b6  nop
0x1400099b7  lea     rcx, [rdi+148h]
0x1400099be  lea     rdx, [rbp+arg_0]
0x1400099c2  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1400099c7  nop
0x1400099c8  mov     rdx, [rbp+arg_0]
0x1400099cc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400099d0  mov     eax, esi
0x1400099d2  lock xadd [rdx+10h], eax
0x1400099d7  add     eax, esi
0x1400099d9  test    eax, eax
0x1400099db  jg      short loc_1400099EC
0x1400099dd  mov     rcx, [rdx]
0x1400099e0  mov     rax, [rcx]
0x1400099e3  mov     rax, [rax+8]
0x1400099e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400099ec  mov     rdx, [rdi+130h]
0x1400099f3  add     rdx, 18h
0x1400099f7  lea     rcx, [rbp+arg_0]
0x1400099fb  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009a00  nop
0x140009a01  lea     rcx, [rdi+150h]
0x140009a08  lea     rdx, [rbp+arg_0]
0x140009a0c  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009a11  nop
0x140009a12  mov     rdx, [rbp+arg_0]
0x140009a16  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009a1a  mov     eax, esi
0x140009a1c  lock xadd [rdx+10h], eax
0x140009a21  add     eax, esi
0x140009a23  test    eax, eax
0x140009a25  jg      short loc_140009A36
0x140009a27  mov     rcx, [rdx]
0x140009a2a  mov     rax, [rcx]
0x140009a2d  mov     rax, [rax+8]
0x140009a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a36  mov     rdx, [rdi+130h]
0x140009a3d  add     rdx, 38h ; '8'
0x140009a41  lea     rcx, [rbp+arg_0]
0x140009a45  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009a4a  nop
0x140009a4b  lea     rcx, [rdi+158h]
0x140009a52  lea     rdx, [rbp+arg_0]
0x140009a56  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009a5b  nop
0x140009a5c  mov     rdx, [rbp+arg_0]
0x140009a60  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009a64  mov     eax, esi
0x140009a66  lock xadd [rdx+10h], eax
0x140009a6b  add     eax, esi
0x140009a6d  test    eax, eax
0x140009a6f  jg      short loc_140009A80
0x140009a71  mov     rcx, [rdx]
0x140009a74  mov     rax, [rcx]
0x140009a77  mov     rax, [rax+8]
0x140009a7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009a80  mov     rdx, [rdi+130h]
0x140009a87  add     rdx, 40h ; '@'
0x140009a8b  lea     rcx, [rbp+arg_0]
0x140009a8f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009a94  nop
0x140009a95  lea     rcx, [rdi+160h]
0x140009a9c  lea     rdx, [rbp+arg_0]
0x140009aa0  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009aa5  nop
0x140009aa6  mov     rdx, [rbp+arg_0]
0x140009aaa  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009aae  mov     eax, esi
0x140009ab0  lock xadd [rdx+10h], eax
0x140009ab5  add     eax, esi
0x140009ab7  test    eax, eax
0x140009ab9  jg      short loc_140009ACA
0x140009abb  mov     rcx, [rdx]
0x140009abe  mov     rax, [rcx]
0x140009ac1  mov     rax, [rax+8]
0x140009ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009aca  mov     rdx, [rdi+130h]
0x140009ad1  add     rdx, 48h ; 'H'
0x140009ad5  lea     rcx, [rbp+arg_0]
0x140009ad9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009ade  nop
0x140009adf  lea     rcx, [rdi+168h]
0x140009ae6  lea     rdx, [rbp+arg_0]
0x140009aea  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140009aef  nop
0x140009af0  mov     rdx, [rbp+arg_0]
0x140009af4  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140009af8  mov     eax, esi
0x140009afa  lock xadd [rdx+10h], eax
0x140009aff  add     eax, esi
0x140009b01  test    eax, eax
0x140009b03  jg      short loc_140009B14
0x140009b05  mov     rcx, [rdx]
0x140009b08  mov     rax, [rcx]
0x140009b0b  mov     rax, [rax+8]
0x140009b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b14  add     rsp, 38h
0x140009b18  pop     rdi
0x140009b19  pop     rsi
0x140009b1a  pop     rbx
0x140009b1b  pop     rbp
0x140009b1c  retn
```
