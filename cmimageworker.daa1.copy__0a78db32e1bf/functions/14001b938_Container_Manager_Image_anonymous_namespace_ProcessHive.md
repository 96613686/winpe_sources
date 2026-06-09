# Container::Manager::Image::_anonymous_namespace_::ProcessHive

- ea: `0x14001b938`
- end: `0x14001bb24`
- name: `Container::Manager::Image::_anonymous_namespace_::ProcessHive`
- size: `492`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000aca8`
- `0x14000c6a4`
- `0x14000c914`
- `0x1400118a4`
- `0x140019b98`
- `0x14001adb0`
- `0x14001b938`
- `0x14001bb2c`
- `0x140021914`
- `0x1400228fc`

## string_xrefs

- `0x14001ba6d`: `Registry adjustment failed: %ws`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::ProcessHive(__int64 *a1, int a2, __int64 *a3)
{
  int HivePath; // eax
  int v5; // ebx
  const struct Path *v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rbx
  __int64 v10; // rdi
  int v11; // esi
  int v12; // eax
  int v13; // [rsp+20h] [rbp-29h]
  _BYTE v14[8]; // [rsp+30h] [rbp-19h] BYREF
  __int64 v15; // [rsp+38h] [rbp-11h]
  void *v16[2]; // [rsp+40h] [rbp-9h] BYREF
  _WORD v17[8]; // [rsp+50h] [rbp+7h] BYREF
  char *v18[2]; // [rsp+60h] [rbp+17h] BYREF
  _WORD v19[24]; // [rsp+70h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v16[0] = v17;
  v16[1] = v17;
  v17[0] = 0;
  HivePath = Container::Manager::Image::_anonymous_namespace_::GetHivePath(a1, a2, (__int64)v16);
  v5 = HivePath;
  if ( HivePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x212,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)HivePath,
      v13);
LABEL_3:
    if ( v16[0] != v17 )
      operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v5;
  }
  v14[0] = 0;
  v15 = 0;
  v5 = Csl::OfflineHive::Open((Csl::OfflineHive *)v14, (LPCWSTR *)v16);
  if ( v5 < 0 )
  {
    v8 = 534;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v5,
      v13);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v14);
    goto LABEL_3;
  }
  v9 = *a3;
  v10 = a3[1];
  while ( v9 != v10 )
  {
    v11 = Container::Manager::Image::_anonymous_namespace_::ProcessRegistryAdjustment((Csl::OfflineHive *)v14);
    if ( v11 < 0 )
    {
      v18[0] = (char *)v19;
      v18[1] = (char *)v19;
      v19[0] = 0;
      v12 = Csl::MarshalToJson<Container::Manager::Image::RegistryAdjustment>(v9, v18);
      if ( v12 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x221,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)(unsigned int)v12,
          v13);
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x223,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v11,
        (int)"Registry adjustment failed: %ws",
        v18[0]);
      if ( (_WORD *)v18[0] != v19 )
        operator delete(v18[0], (const struct std::nothrow_t *)&std::nothrow);
      Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v14);
      if ( v16[0] != v17 )
        operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v11;
    }
    v9 += 120;
  }
  v5 = Csl::DeletePath((LPCWSTR *)v16, v7);
  if ( v5 < 0 )
  {
    v8 = 552;
    goto LABEL_8;
  }
  v5 = Csl::OfflineHive::Save((Csl::OfflineHive *)v14, (LPCWSTR *)v16);
  if ( v5 < 0 )
  {
    v8 = 555;
    goto LABEL_8;
  }
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v14);
  if ( v16[0] != v17 )
    operator delete(v16[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14001b938  push    rbp
0x14001b93a  push    rbx
0x14001b93b  push    rsi
0x14001b93c  push    rdi
0x14001b93d  lea     rbp, [rsp-3Fh]
0x14001b942  sub     rsp, 88h
0x14001b949  lea     rax, [rbp+57h+var_50]
0x14001b94d  mov     rdi, r8
0x14001b950  mov     [rbp+57h+var_60], rax
0x14001b954  lea     r8, [rbp+57h+var_60]
0x14001b958  lea     rax, [rbp+57h+var_50]
0x14001b95c  mov     [rbp+57h+var_58], rax
0x14001b960  xor     eax, eax
0x14001b962  mov     [rbp+57h+var_50], ax
0x14001b966  call    Container__Manager__Image___anonymous_namespace___GetHivePath
0x14001b96b  mov     ebx, eax
0x14001b96d  test    eax, eax
0x14001b96f  jns     short loc_14001B9A9
0x14001b971  mov     rcx, [rbp+5Fh]; this
0x14001b975  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001b97c  mov     r9d, eax; char *
0x14001b97f  mov     edx, 212h; void *
0x14001b984  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b989  mov     rcx, [rbp+57h+var_60]; void *
0x14001b98d  lea     rax, [rbp+57h+var_50]
0x14001b991  cmp     rcx, rax
0x14001b994  jz      short loc_14001B9A2
0x14001b996  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001b99d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001b9a2  mov     eax, ebx
0x14001b9a4  jmp     loc_14001BB17
0x14001b9a9  lea     rdx, [rbp+57h+var_60]; struct Path *
0x14001b9ad  mov     [rbp+57h+var_70], 0
0x14001b9b1  lea     rcx, [rbp+57h+var_70]; this
0x14001b9b5  mov     [rbp+57h+var_68], 0
0x14001b9bd  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x14001b9c2  mov     ebx, eax
0x14001b9c4  test    eax, eax
0x14001b9c6  jns     short loc_14001B9EB
0x14001b9c8  mov     edx, 216h; void *
0x14001b9cd  mov     rcx, [rbp+5Fh]; this
0x14001b9d1  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001b9d8  mov     r9d, ebx; char *
0x14001b9db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001b9e0  lea     rcx, [rbp+57h+var_70]; this
0x14001b9e4  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001b9e9  jmp     short loc_14001B989
0x14001b9eb  mov     rbx, [rdi]
0x14001b9ee  mov     rdi, [rdi+8]
0x14001b9f2  cmp     rbx, rdi
0x14001b9f5  jz      loc_14001BABD
0x14001b9fb  mov     rdx, rbx
0x14001b9fe  lea     rcx, [rbp+57h+var_70]; this
0x14001ba02  call    Container__Manager__Image___anonymous_namespace___ProcessRegistryAdjustment
0x14001ba07  mov     esi, eax
0x14001ba09  test    eax, eax
0x14001ba0b  js      short loc_14001BA13
0x14001ba0d  add     rbx, 78h ; 'x'
0x14001ba11  jmp     short loc_14001B9F2
0x14001ba13  lea     rax, [rbp+57h+var_30]
0x14001ba17  mov     rcx, rbx
0x14001ba1a  mov     [rbp+57h+var_40], rax
0x14001ba1e  lea     rdx, [rbp+57h+var_40]
0x14001ba22  lea     rax, [rbp+57h+var_30]
0x14001ba26  mov     [rbp+57h+var_38], rax
0x14001ba2a  xor     eax, eax
0x14001ba2c  mov     [rbp+57h+var_30], ax
0x14001ba30  call    ??$MarshalToJson@URegistryAdjustment@Image@Manager@Container@@@Csl@@YAJAEBURegistryAdjustment@Image@Manager@Container@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Csl::MarshalToJson<Container::Manager::Image::RegistryAdjustment>(Container::Manager::Image::RegistryAdjustment const &,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x14001ba35  test    eax, eax
0x14001ba37  jns     short loc_14001BA51
0x14001ba39  mov     rcx, [rbp+5Fh]; this
0x14001ba3d  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001ba44  mov     r9d, eax; char *
0x14001ba47  mov     edx, 221h; void *
0x14001ba4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14001ba51  mov     rax, [rbp+57h+var_40]
0x14001ba55  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001ba5c  mov     rcx, [rbp+5Fh]; this
0x14001ba60  mov     r9d, esi; char *
0x14001ba63  mov     [rsp+0A0h+var_78], rax; char *
0x14001ba68  mov     edx, 223h; void *
0x14001ba6d  lea     rax, aRegistryAdjust; "Registry adjustment failed: %ws"
0x14001ba74  mov     qword ptr [rsp+0A0h+var_80], rax; int
0x14001ba79  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14001ba7e  mov     rcx, [rbp+57h+var_40]; void *
0x14001ba82  lea     rax, [rbp+57h+var_30]
0x14001ba86  cmp     rcx, rax
0x14001ba89  jz      short loc_14001BA97
0x14001ba8b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001ba92  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001ba97  lea     rcx, [rbp+57h+var_70]; this
0x14001ba9b  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001baa0  mov     rcx, [rbp+57h+var_60]; void *
0x14001baa4  lea     rax, [rbp+57h+var_50]
0x14001baa8  cmp     rcx, rax
0x14001baab  jz      short loc_14001BAB9
0x14001baad  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bab4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bab9  mov     eax, esi
0x14001babb  jmp     short loc_14001BB17
0x14001babd  lea     rcx, [rbp+57h+var_60]; this
0x14001bac1  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x14001bac6  mov     ebx, eax
0x14001bac8  test    eax, eax
0x14001baca  jns     short loc_14001BAD6
0x14001bacc  mov     edx, 228h
0x14001bad1  jmp     loc_14001B9CD
0x14001bad6  lea     rdx, [rbp+57h+var_60]; struct Path *
0x14001bada  lea     rcx, [rbp+57h+var_70]; this
0x14001bade  call    ?Save@OfflineHive@Csl@@QEBAJAEBVPath@2@@Z; Csl::OfflineHive::Save(Csl::Path const &)
0x14001bae3  mov     ebx, eax
0x14001bae5  test    eax, eax
0x14001bae7  jns     short loc_14001BAF3
0x14001bae9  mov     edx, 22Bh
0x14001baee  jmp     loc_14001B9CD
0x14001baf3  lea     rcx, [rbp+57h+var_70]; this
0x14001baf7  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001bafc  mov     rcx, [rbp+57h+var_60]; void *
0x14001bb00  lea     rax, [rbp+57h+var_50]
0x14001bb04  cmp     rcx, rax
0x14001bb07  jz      short loc_14001BB15
0x14001bb09  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001bb10  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001bb15  xor     eax, eax
0x14001bb17  add     rsp, 88h
0x14001bb1e  pop     rdi
0x14001bb1f  pop     rsi
0x14001bb20  pop     rbx
0x14001bb21  pop     rbp
0x14001bb22  retn
```
