# OAuthTokenRequestBase::~OAuthTokenRequestBase(void)

- ea: `0x1400145ec`
- end: `0x140014727`
- name: `??1OAuthTokenRequestBase@@UEAA@XZ`
- size: `315`
- prototype: `void __fastcall(OAuthTokenRequestBase *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x140014860`
- `0x140015fb8`
- `0x1400169c0`
- `0x14002dfd6`

## callees

- `0x14000579c`
- `0x140007b90`
- `0x1400145ec`
- `0x140030010`

## pseudocode

```c
void __fastcall OAuthTokenRequestBase::~OAuthTokenRequestBase(OAuthTokenRequestBase *this)
{
  volatile signed __int32 *v1; // rdx
  volatile signed __int32 *v3; // rdi
  volatile signed __int32 *v4; // rdx
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx
  volatile signed __int32 *v7; // rdx

  v1 = (volatile signed __int32 *)(*((_QWORD *)this + 16) - 24LL);
  *(_QWORD *)this = &OAuthTokenRequestBase::`vftable';
  if ( _InterlockedDecrement(v1 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v1 + 8LL))(*(_QWORD *)v1);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (volatile signed __int32 *)(*((_QWORD *)this + 12) - 24LL);
  if ( _InterlockedDecrement(v4 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  v5 = (volatile signed __int32 *)(*((_QWORD *)this + 11) - 24LL);
  if ( _InterlockedDecrement(v5 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  v6 = (volatile signed __int32 *)(*((_QWORD *)this + 9) - 24LL);
  if ( _InterlockedDecrement(v6 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  v7 = (volatile signed __int32 *)(*((_QWORD *)this + 8) - 24LL);
  if ( _InterlockedDecrement(v7 + 4) <= 0 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 8LL))(*(_QWORD *)v7);
  CSecureString::~CSecureString((OAuthTokenRequestBase *)((char *)this + 48));
  CSecureString::~CSecureString((OAuthTokenRequestBase *)((char *)this + 32));
  TokenRequest::~TokenRequest(this);
}

```

## disassembly

```asm
0x1400145ec  mov     [rsp+arg_0], rbx
0x1400145f1  mov     [rsp+arg_8], rsi
0x1400145f6  push    rdi
0x1400145f7  sub     rsp, 20h
0x1400145fb  mov     rdx, [rcx+80h]
0x140014602  lea     rax, ??_7OAuthTokenRequestBase@@6B@; const OAuthTokenRequestBase::`vftable'
0x140014609  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001460d  mov     [rcx], rax
0x140014610  or      esi, 0FFFFFFFFh
0x140014613  mov     rbx, rcx
0x140014616  mov     eax, esi
0x140014618  lock xadd [rdx+10h], eax
0x14001461d  add     eax, esi
0x14001461f  test    eax, eax
0x140014621  jg      short loc_140014632
0x140014623  mov     rcx, [rdx]
0x140014626  mov     rax, [rcx]
0x140014629  mov     rax, [rax+8]
0x14001462d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014632  mov     rdi, [rbx+70h]
0x140014636  test    rdi, rdi
0x140014639  jz      short loc_14001466E
0x14001463b  mov     eax, esi
0x14001463d  lock xadd [rdi+8], eax
0x140014642  add     eax, esi
0x140014644  jnz     short loc_14001466E
0x140014646  mov     rax, [rdi]
0x140014649  mov     rcx, rdi
0x14001464c  mov     rax, [rax]
0x14001464f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014654  mov     eax, esi
0x140014656  lock xadd [rdi+0Ch], eax
0x14001465b  add     eax, esi
0x14001465d  jnz     short loc_14001466E
0x14001465f  mov     rax, [rdi]
0x140014662  mov     rcx, rdi
0x140014665  mov     rax, [rax+8]
0x140014669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001466e  mov     rdx, [rbx+60h]
0x140014672  mov     eax, esi
0x140014674  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140014678  lock xadd [rdx+10h], eax
0x14001467d  add     eax, esi
0x14001467f  test    eax, eax
0x140014681  jg      short loc_140014692
0x140014683  mov     rcx, [rdx]
0x140014686  mov     rax, [rcx]
0x140014689  mov     rax, [rax+8]
0x14001468d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014692  mov     rdx, [rbx+58h]
0x140014696  mov     eax, esi
0x140014698  add     rdx, 0FFFFFFFFFFFFFFE8h
0x14001469c  lock xadd [rdx+10h], eax
0x1400146a1  add     eax, esi
0x1400146a3  test    eax, eax
0x1400146a5  jg      short loc_1400146B6
0x1400146a7  mov     rcx, [rdx]
0x1400146aa  mov     rax, [rcx]
0x1400146ad  mov     rax, [rax+8]
0x1400146b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146b6  mov     rdx, [rbx+48h]
0x1400146ba  mov     eax, esi
0x1400146bc  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400146c0  lock xadd [rdx+10h], eax
0x1400146c5  add     eax, esi
0x1400146c7  test    eax, eax
0x1400146c9  jg      short loc_1400146DA
0x1400146cb  mov     rcx, [rdx]
0x1400146ce  mov     rax, [rcx]
0x1400146d1  mov     rax, [rax+8]
0x1400146d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146da  mov     rdx, [rbx+40h]
0x1400146de  mov     eax, esi
0x1400146e0  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400146e4  lock xadd [rdx+10h], eax
0x1400146e9  add     eax, esi
0x1400146eb  test    eax, eax
0x1400146ed  jg      short loc_1400146FE
0x1400146ef  mov     rcx, [rdx]
0x1400146f2  mov     rax, [rcx]
0x1400146f5  mov     rax, [rax+8]
0x1400146f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400146fe  lea     rcx, [rbx+30h]; this
0x140014702  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140014707  lea     rcx, [rbx+20h]; this
0x14001470b  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x140014710  mov     rcx, rbx; this
0x140014713  mov     rbx, [rsp+28h+arg_0]
0x140014718  mov     rsi, [rsp+28h+arg_8]
0x14001471d  add     rsp, 20h
0x140014721  pop     rdi
0x140014722  jmp     ??1TokenRequest@@UEAA@XZ; TokenRequest::~TokenRequest(void)
```
