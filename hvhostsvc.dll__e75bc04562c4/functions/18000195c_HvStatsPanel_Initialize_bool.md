# HvStatsPanel::Initialize(bool)

- ea: `0x18000195c`
- end: `0x180001a7a`
- name: `?Initialize@HvStatsPanel@@QEAAJ_N@Z`
- size: `286`
- prototype: `__int64 __fastcall(HvStatsPanel *__hidden this, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004928`

## callees

- `0x18000195c`
- `0x180001a80`
- `0x180002bd0`
- `0x180007a74`
- `0x180007e94`
- `0x18000a010`

## string_xrefs

- `0x180001983`: `Object already initialized.`

## pseudocode

```c
__int64 __fastcall HvStatsPanel::Initialize(HvStatsPanel *this, bool a2)
{
  volatile signed __int32 *v3; // rbx
  std::_Ref_count_base *v4; // rax
  RTL_SRWLOCK *v5; // rcx
  std::_Ref_count_base *v6; // rcx
  __int64 result; // rax
  const wil::ResultException *v8; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  _DWORD *v10; // [rsp+50h] [rbp+8h]

  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x44D,
      (unsigned int)"onecore\\hv\\hvhostsvc\\lib\\hvstatspanel.cpp",
      (const char *)0x80004005LL,
      g_HypervisorStatsPanel != 0,
      (bool)"Object already initialized.",
      (const char *)v8);
    v10 = operator new(0x108u);
    v10[2] = 1;
    v10[3] = 1;
    *(_QWORD *)v10 = &std::_Ref_count_obj2<HvStatsPanel::Impl>::`vftable';
    HvStatsPanel::Impl::Impl(
      (HvStatsPanel::Impl *)(v10 + 4),
      (unsigned int (*)(unsigned int, void *, unsigned int))HvStatsPanel::ProviderCallback,
      a2);
    g_HypervisorStatsPanel = (PSRWLOCK)(v10 + 4);
    v3 = (volatile signed __int32 *)qword_1800127E0;
    qword_1800127E0 = (std::_Ref_count_base *)v10;
    if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v3);
    }
    v4 = qword_1800127E0;
    if ( qword_1800127E0 )
    {
      v5 = g_HypervisorStatsPanel;
      _InterlockedIncrement((volatile signed __int32 *)qword_1800127E0 + 3);
    }
    else
    {
      v5 = 0;
    }
    staticInstance = v5;
    v6 = qword_1800127F0;
    qword_1800127F0 = v4;
    if ( v6 )
      std::_Ref_count_base::_Decwref(v6);
    result = 0;
  }
  catch ( const wil::ResultException *v8 )
  {
    return *((unsigned int *)v8 + 8);
  }
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x44D,
    (unsigned int)"onecore\\hv\\hvhostsvc\\lib\\hvstatspanel.cpp",
    (const char *)0x80004005LL,
    g_HypervisorStatsPanel != 0,
    (bool)"Object already initialized.",
    (const char *)v8);
}

```

## disassembly

```asm
0x18000195c  mov     r11, rsp
0x18000195f  mov     [r11+10h], rbx
0x180001963  mov     [r11+18h], rsi
0x180001967  mov     [r11+8], rcx
0x18000196b  push    rdi
0x18000196c  sub     rsp, 40h
0x180001970  mov     sil, dl
0x180001973  cmp     cs:?g_HypervisorStatsPanel@@3VHvStatsPanel@@A, 0; HvStatsPanel g_HypervisorStatsPanel
0x18000197b  setnz   al
0x18000197e  mov     rcx, [rsp+48h]; this
0x180001983  lea     rdx, aObjectAlreadyI; "Object already initialized."
0x18000198a  mov     [r11-20h], rdx
0x18000198e  mov     [rsp+48h+var_28], al; char
0x180001992  mov     r9d, 80004005h; char *
0x180001998  lea     r8, aOnecoreHvHvhos; "onecore\\hv\\hvhostsvc\\lib\\hvstatspan"...
0x18000199f  mov     edx, 44Dh; void *
0x1800019a4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800019a9  mov     ecx, 108h; Size
0x1800019ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800019b3  mov     rdi, rax
0x1800019b6  mov     [rsp+48h+arg_0], rax
0x1800019bb  mov     dword ptr [rax+8], 1
0x1800019c2  mov     dword ptr [rax+0Ch], 1
0x1800019c9  lea     rax, ??_7?$_Ref_count_obj2@VImpl@HvStatsPanel@@@std@@6B@; const std::_Ref_count_obj2<HvStatsPanel::Impl>::`vftable'
0x1800019d0  mov     [rdi], rax
0x1800019d3  lea     rbx, [rdi+10h]
0x1800019d7  mov     r8b, sil; bool
0x1800019da  lea     rdx, ?ProviderCallback@HvStatsPanel@@CAKKPEAXK@Z; unsigned int (*)(unsigned int, void *, unsigned int)
0x1800019e1  mov     rcx, rbx; this
0x1800019e4  call    ??0Impl@HvStatsPanel@@QEAA@P6AKKPEAXK@Z_N@Z; HvStatsPanel::Impl::Impl(ulong (*)(ulong,void *,ulong),bool)
0x1800019e9  nop
0x1800019ea  mov     cs:?g_HypervisorStatsPanel@@3VHvStatsPanel@@A, rbx; HvStatsPanel g_HypervisorStatsPanel
0x1800019f1  mov     rbx, cs:qword_1800127E0
0x1800019f8  mov     cs:qword_1800127E0, rdi
0x1800019ff  test    rbx, rbx
0x180001a02  jz      short loc_180001A27
0x180001a04  or      eax, 0FFFFFFFFh
0x180001a07  lock xadd [rbx+8], eax
0x180001a0c  cmp     eax, 1
0x180001a0f  jnz     short loc_180001A27
0x180001a11  mov     rax, [rbx]
0x180001a14  mov     rcx, rbx
0x180001a17  mov     rax, [rax]
0x180001a1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a1f  mov     rcx, rbx; this
0x180001a22  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180001a27  mov     rax, cs:qword_1800127E0
0x180001a2e  test    rax, rax
0x180001a31  jz      short loc_180001A40
0x180001a33  mov     rcx, cs:?g_HypervisorStatsPanel@@3VHvStatsPanel@@A; HvStatsPanel g_HypervisorStatsPanel
0x180001a3a  lock inc dword ptr [rax+0Ch]
0x180001a3e  jmp     short loc_180001A42
0x180001a40  xor     ecx, ecx
0x180001a42  mov     cs:?staticInstance@@3V?$weak_ptr@VImpl@HvStatsPanel@@@std@@A, rcx; std::weak_ptr<HvStatsPanel::Impl> staticInstance
0x180001a49  mov     rcx, cs:qword_1800127F0; this
0x180001a50  mov     cs:qword_1800127F0, rax
0x180001a57  test    rcx, rcx
0x180001a5a  jz      short loc_180001A61
0x180001a5c  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180001a61  xor     eax, eax
0x180001a63  jmp     short loc_180001A69
0x180001a65  mov     eax, dword ptr [rsp+48h+arg_0]
0x180001a69  mov     rbx, [rsp+48h+arg_8]
0x180001a6e  mov     rsi, [rsp+48h+arg_10]
0x180001a73  add     rsp, 40h
0x180001a77  pop     rdi
0x180001a78  retn
```
