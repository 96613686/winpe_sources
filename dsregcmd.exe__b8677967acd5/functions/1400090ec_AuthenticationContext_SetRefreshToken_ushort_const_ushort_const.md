# AuthenticationContext::SetRefreshToken(ushort const *,ushort const *)

- ea: `0x1400090ec`
- end: `0x14000921f`
- name: `?SetRefreshToken@AuthenticationContext@@QEAAXPEBG0@Z`
- size: `307`
- prototype: `void(AuthenticationContext *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140009518`

## callees

- `0x14000579c`
- `0x1400061dc`
- `0x1400090ec`
- `0x14000be24`
- `0x14000f2ac`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AuthenticationContext::SetRefreshToken(
        AuthenticationContext *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // r8
  __int64 v7; // r8
  _QWORD *v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v11[8]; // [rsp+28h] [rbp-40h] BYREF

  ArgumentException::ThrowIfNullOrEmpty(a3, 0xCAA10014);
  if ( a2 && *a2 )
  {
    v10 = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v11[0] = ((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24;
    v11[1] = 0;
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v10, a2, v6);
    if ( a3 )
    {
      v7 = -1;
      do
        ++v7;
      while ( a3[v7] );
    }
    else
    {
      v7 = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString(v11, a3, v7);
    TokenCache::Add((AuthenticationContext *)((char *)this + 168), (const struct TokenCache::Item *)&v10);
    CSecureString::~CSecureString((CSecureString *)v11);
    v8 = (_QWORD *)(v10 - 24);
    if ( _InterlockedDecrement((volatile signed __int32 *)(v10 - 24 + 16)) <= 0 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
  }
  else
  {
    if ( a3 )
    {
      v9 = -1;
      do
        ++v9;
      while ( a3[v9] );
    }
    else
    {
      LODWORD(v9) = 0;
    }
    ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 48, a3, (unsigned int)v9);
  }
}

```

## disassembly

```asm
0x1400090ec  push    rbx
0x1400090ee  push    rbp
0x1400090ef  push    rsi
0x1400090f0  push    rdi
0x1400090f1  push    r14
0x1400090f3  sub     rsp, 40h
0x1400090f7  mov     rdi, r8
0x1400090fa  mov     rsi, rdx
0x1400090fd  mov     rbp, rcx
0x140009100  mov     edx, 0CAA10014h; unsigned int
0x140009105  mov     rcx, r8; unsigned __int16 *
0x140009108  call    ?ThrowIfNullOrEmpty@ArgumentException@@SAXPEBGK@Z; ArgumentException::ThrowIfNullOrEmpty(ushort const *,ulong)
0x14000910d  xor     r14d, r14d
0x140009110  test    rsi, rsi
0x140009113  jz      loc_1400091ED
0x140009119  cmp     [rsi], r14w
0x14000911d  jz      loc_1400091ED
0x140009123  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000912a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009131  mov     rax, [rax+18h]
0x140009135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000913a  add     rax, 18h
0x14000913e  mov     [rsp+68h+var_48], rax
0x140009143  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x14000914a  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x140009151  mov     rax, [rax+18h]
0x140009155  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000915a  add     rax, 18h
0x14000915e  mov     [rsp+68h+var_40], rax
0x140009163  mov     [rsp+68h+var_38], r14
0x140009168  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14000916c  mov     r8, rbx
0x14000916f  inc     r8
0x140009172  cmp     [rsi+r8*2], r14w
0x140009177  jnz     short loc_14000916F
0x140009179  mov     rdx, rsi
0x14000917c  lea     rcx, [rsp+68h+var_48]
0x140009181  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140009186  test    rdi, rdi
0x140009189  jnz     short loc_140009190
0x14000918b  mov     r8d, r14d
0x14000918e  jmp     short loc_14000919D
0x140009190  mov     r8, rbx
0x140009193  inc     r8
0x140009196  cmp     [rdi+r8*2], r14w
0x14000919b  jnz     short loc_140009193
0x14000919d  mov     rdx, rdi
0x1400091a0  lea     rcx, [rsp+68h+var_40]
0x1400091a5  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1400091aa  lea     rcx, [rbp+0A8h]; this
0x1400091b1  lea     rdx, [rsp+68h+var_48]; struct TokenCache::Item *
0x1400091b6  call    ?Add@TokenCache@@QEAAXAEBVItem@1@@Z; TokenCache::Add(TokenCache::Item const &)
0x1400091bb  nop
0x1400091bc  lea     rcx, [rsp+68h+var_40]; this
0x1400091c1  call    ??1CSecureString@@QEAA@XZ; CSecureString::~CSecureString(void)
0x1400091c6  mov     rdx, [rsp+68h+var_48]
0x1400091cb  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1400091cf  mov     eax, ebx
0x1400091d1  lock xadd [rdx+10h], eax
0x1400091d6  add     eax, ebx
0x1400091d8  test    eax, eax
0x1400091da  jg      short loc_140009214
0x1400091dc  mov     rcx, [rdx]
0x1400091df  mov     rax, [rcx]
0x1400091e2  mov     rax, [rax+8]
0x1400091e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400091eb  jmp     short loc_140009214
0x1400091ed  test    rdi, rdi
0x1400091f0  jnz     short loc_1400091F7
0x1400091f2  mov     ebx, r14d
0x1400091f5  jmp     short loc_140009205
0x1400091f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400091fb  inc     rbx
0x1400091fe  cmp     [rdi+rbx*2], r14w
0x140009203  jnz     short loc_1400091FB
0x140009205  lea     rcx, [rbp+30h]
0x140009209  mov     r8d, ebx
0x14000920c  mov     rdx, rdi
0x14000920f  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140009214  add     rsp, 40h
0x140009218  pop     r14
0x14000921a  pop     rdi
0x14000921b  pop     rsi
0x14000921c  pop     rbp
0x14000921d  pop     rbx
0x14000921e  retn
```
