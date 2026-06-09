# GetCachedSettingRegPath(PackageContext *,_MVProvisionData *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180034380`
- end: `0x1800346d2`
- name: `?GetCachedSettingRegPath@@YAJPEAUPackageContext@@PEAU_MVProvisionData@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z`
- size: `850`
- prototype: `__int64 __fastcall(_QWORD *, __int64, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180033c48`
- `0x180033fa0`
- `0x1800346d8`

## callees

- `0x1800010c8`
- `0x1800018ec`
- `0x1800098dc`
- `0x18000b030`
- `0x180021e40`
- `0x180021f40`
- `0x1800228e4`
- `0x180033784`
- `0x180034380`
- `0x180034920`
- `0x180037664`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800344f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800346a4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800344f0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800346a4`

## string_xrefs

- `0x180034484`: `CachedCRCs`
- `0x180034638`: `CachedCRCs`
- `0x18003442f`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetCachedSettingRegPath(_QWORD *a1, __int64 a2, _QWORD *a3, _QWORD *a4)
{
  int StringFromProvisionState; // eax
  int UniqueId; // ebx
  __int64 v10; // rdx
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r8
  _QWORD *v14; // rax
  char *v15; // rdx
  struct IMVHandler *v16; // rcx
  int ContextSubKeyPath; // eax
  __int64 v18; // r9
  unsigned __int64 v19; // r8
  unsigned __int16 *v20; // rdx
  _QWORD *v21; // rax
  int v22; // [rsp+20h] [rbp-E0h]
  unsigned int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v25; // [rsp+48h] [rbp-B8h] BYREF
  void *v26[3]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v27; // [rsp+68h] [rbp-98h]
  int *v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+78h] [rbp-88h]
  unsigned __int16 v30[264]; // [rsp+80h] [rbp-80h] BYREF
  char v31[528]; // [rsp+290h] [rbp+190h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  StringFromProvisionState = GetStringFromProvisionState(*(unsigned int *)(a1[2] + 24LL), v31);
  UniqueId = StringFromProvisionState;
  if ( StringFromProvisionState < 0 )
  {
    if ( (unsigned int)dword_18005A000 > 2 )
    {
      v24 = StringFromProvisionState;
      v28 = &v24;
      v29 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, byte_18004FF83, 0, 0, 3, v26);
    }
    v10 = 270;
    goto LABEL_5;
  }
  if ( *(_QWORD *)(a2 + 56) )
  {
    v12 = -1;
    if ( *gc_wszRegMultivariantStatus )
    {
      v13 = -1;
      do
        ++v13;
      while ( gc_wszRegMultivariantStatus[v13] );
    }
    else
    {
      v13 = 0;
    }
    std::wstring::assign(a3, (char *)gc_wszRegMultivariantStatus, v13);
    std::wstring::push_back(a3);
    std::wstring::append((const void **)a3, (char *)L"CachedCRCs");
    std::wstring::push_back(a3);
    std::wstring::append((const void **)a3, v31);
    std::wstring::push_back(a3);
    v14 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*a1 + 16LL))(*a1, v26);
    std::wstring::append(a3, v14, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v27 >= 8 )
      operator delete(v26[0]);
    if ( a4 )
    {
      v15 = *(char **)(a2 + 56);
      if ( *(_WORD *)v15 )
      {
        do
          ++v12;
        while ( *(_WORD *)&v15[2 * v12] );
      }
      else
      {
        v12 = 0;
      }
      std::wstring::assign(a4, v15, v12);
    }
  }
  else if ( *(_QWORD *)(a2 + 40) )
  {
    v16 = *(struct IMVHandler **)a1[2];
    if ( v16 )
    {
      ContextSubKeyPath = MvGetContextSubKeyPath(
                            v16,
                            (const unsigned int *)((a2 + 92) & -(__int64)(*(_DWORD *)(a2 + 96) != 0)),
                            gc_wszRegMultivariant,
                            0,
                            v30,
                            v23,
                            (struct _MVProvisionData *)a2);
      UniqueId = ContextSubKeyPath;
      if ( ContextSubKeyPath < 0 )
      {
        if ( (unsigned int)dword_18005A000 > 2 )
        {
          v24 = ContextSubKeyPath;
          v25 = (__int64 *)gc_wszRegMultivariant;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (__int64)&dword_18005A000,
            (__int64)byte_180050023,
            0,
            v18,
            &v25,
            (__int64)&v24);
        }
        v10 = 321;
        goto LABEL_5;
      }
      if ( v30[0] )
      {
        v19 = -1;
        do
          ++v19;
        while ( v30[v19] );
      }
      else
      {
        v19 = 0;
      }
      v20 = v30;
    }
    else
    {
      v20 = (unsigned __int16 *)gc_wszRegMultivariantStatus;
      if ( *gc_wszRegMultivariantStatus )
      {
        v19 = -1;
        do
          ++v19;
        while ( gc_wszRegMultivariantStatus[v19] );
      }
      else
      {
        v19 = 0;
      }
    }
    std::wstring::assign(a3, (char *)v20, v19);
    std::wstring::push_back(a3);
    std::wstring::append((const void **)a3, (char *)L"CachedCRCs");
    std::wstring::push_back(a3);
    std::wstring::append((const void **)a3, v31);
    std::wstring::push_back(a3);
    v21 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD, void **))(*(_QWORD *)*a1 + 16LL))(*a1, v26);
    std::wstring::append(a3, v21, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v27 >= 8 )
      operator delete(v26[0]);
    if ( a4 )
    {
      UniqueId = MvGetUniqueId(a2, a4);
      if ( UniqueId < 0 )
      {
        v10 = 348;
LABEL_5:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v10,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
          (const char *)(unsigned int)UniqueId,
          v22);
        return (unsigned int)UniqueId;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180034380  push    rbp
0x180034382  push    rbx
0x180034383  push    rsi
0x180034384  push    rdi
0x180034385  push    r13
0x180034387  push    r14
0x180034389  push    r15
0x18003438b  lea     rbp, [rsp-3B0h]
0x180034393  sub     rsp, 4B0h
0x18003439a  mov     rax, cs:__security_cookie
0x1800343a1  xor     rax, rsp
0x1800343a4  mov     [rbp+3E0h+var_40], rax
0x1800343ab  mov     r14, r9
0x1800343ae  mov     rsi, r8
0x1800343b1  mov     rdi, rdx
0x1800343b4  mov     r15, rcx
0x1800343b7  mov     rcx, [rcx+10h]
0x1800343bb  lea     rdx, [rbp+3E0h+var_250]
0x1800343c2  mov     ecx, [rcx+18h]
0x1800343c5  call    ?GetStringFromProvisionState@@YAJW4__MIDL___MIDL_itf_mvengine_0000_0000_0001@@PEAGK@Z; GetStringFromProvisionState(__MIDL___MIDL_itf_mvengine_0000_0000_0001,ushort *,ulong)
0x1800343ca  mov     ebx, eax
0x1800343cc  xor     r13d, r13d
0x1800343cf  test    eax, eax
0x1800343d1  jns     short loc_180034442
0x1800343d3  mov     ecx, cs:dword_18005A000
0x1800343d9  cmp     ecx, 2
0x1800343dc  jbe     short loc_180034420
0x1800343de  mov     [rsp+4E0h+var_4A0], eax
0x1800343e2  lea     rax, [rsp+4E0h+var_4A0]
0x1800343e7  mov     [rsp+4E0h+var_470], rax
0x1800343ec  mov     [rsp+4E0h+var_468], 4
0x1800343f5  lea     rax, [rsp+4E0h+var_490]
0x1800343fa  mov     [rsp+4E0h+var_4B8], rax
0x1800343ff  mov     dword ptr [rsp+4E0h+var_4C0], 3; int
0x180034407  xor     r9d, r9d
0x18003440a  xor     r8d, r8d
0x18003440d  lea     rdx, byte_18004FF83
0x180034414  lea     rcx, dword_18005A000
0x18003441b  call    _tlgWriteTransfer_EventWriteTransfer
0x180034420  mov     edx, 10Eh; void *
0x180034425  mov     rcx, [rbp+3E8h]; this
0x18003442c  mov     r9d, ebx; char *
0x18003442f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034436  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003443b  mov     eax, ebx
0x18003443d  jmp     loc_180034521
0x180034442  cmp     [rdi+38h], r13
0x180034446  jz      loc_180034542
0x18003444c  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; Src
0x180034453  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180034457  cmp     [rdx], r13w
0x18003445b  jnz     short loc_180034462
0x18003445d  mov     r8, r13
0x180034460  jmp     short loc_18003446F
0x180034462  mov     r8, rbx
0x180034465  inc     r8
0x180034468  cmp     [rdx+r8*2], r13w
0x18003446d  jnz     short loc_180034465
0x18003446f  mov     rcx, rsi; void *
0x180034472  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180034477  mov     edx, 5Ch ; '\'
0x18003447c  mov     rcx, rsi; Src
0x18003447f  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180034484  lea     rdx, ?gc_wszRegCachedSettingCRCs@@3QBGB; "CachedCRCs"
0x18003448b  mov     rcx, rsi; Src
0x18003448e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180034493  mov     edx, 5Ch ; '\'
0x180034498  mov     rcx, rsi; Src
0x18003449b  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800344a0  lea     rdx, [rbp+3E0h+var_250]; void *
0x1800344a7  mov     rcx, rsi; Src
0x1800344aa  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800344af  mov     edx, 5Ch ; '\'
0x1800344b4  mov     rcx, rsi; Src
0x1800344b7  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x1800344bc  mov     rcx, [r15]
0x1800344bf  mov     rax, [rcx]
0x1800344c2  lea     rdx, [rsp+4E0h+var_490]
0x1800344c7  mov     rax, [rax+10h]
0x1800344cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344d0  nop
0x1800344d1  mov     r9, rbx
0x1800344d4  xor     r8d, r8d
0x1800344d7  mov     rdx, rax
0x1800344da  mov     rcx, rsi
0x1800344dd  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800344e2  nop
0x1800344e3  cmp     [rsp+4E0h+var_478], 8
0x1800344e9  jb      short loc_1800344F6
0x1800344eb  mov     rcx, [rsp+4E0h+var_490]
0x1800344f0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800344f6  test    r14, r14
0x1800344f9  jz      short loc_18003451F
0x1800344fb  mov     rdx, [rdi+38h]; Src
0x1800344ff  cmp     [rdx], r13w
0x180034503  jnz     short loc_18003450A
0x180034505  mov     rbx, r13
0x180034508  jmp     short loc_180034514
0x18003450a  inc     rbx
0x18003450d  cmp     [rdx+rbx*2], r13w
0x180034512  jnz     short loc_18003450A
0x180034514  mov     r8, rbx
0x180034517  mov     rcx, r14; void *
0x18003451a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003451f  xor     eax, eax
0x180034521  mov     rcx, [rbp+3E0h+var_40]
0x180034528  xor     rcx, rsp; StackCookie
0x18003452b  call    __security_check_cookie
0x180034530  add     rsp, 4B0h
0x180034537  pop     r15
0x180034539  pop     r14
0x18003453b  pop     r13
0x18003453d  pop     rdi
0x18003453e  pop     rsi
0x18003453f  pop     rbx
0x180034540  pop     rbp
0x180034541  retn
0x180034542  cmp     [rdi+28h], r13
0x180034546  jz      short loc_18003451F
0x180034548  mov     rax, [r15+10h]
0x18003454c  mov     rcx, [rax]; struct IMVHandler *
0x18003454f  test    rcx, rcx
0x180034552  jz      loc_180034600
0x180034558  mov     eax, [rdi+60h]
0x18003455b  lea     r9, [rdi+5Ch]
0x18003455f  neg     eax
0x180034561  sbb     rdx, rdx
0x180034564  and     rdx, r9; unsigned int *
0x180034567  mov     [rsp+4E0h+pv], rdi; pv
0x18003456c  lea     rax, [rbp+3E0h+var_460]
0x180034570  mov     [rsp+4E0h+var_4C0], rax; unsigned __int16 *
0x180034575  xor     r9d, r9d; unsigned __int16 *
0x180034578  mov     r8, cs:?gc_wszRegMultivariant@@3PEBGEB; unsigned __int16 *
0x18003457f  call    ?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z; MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)
0x180034584  mov     ebx, eax
0x180034586  test    eax, eax
0x180034588  jns     short loc_1800345D9
0x18003458a  mov     ecx, cs:dword_18005A000
0x180034590  cmp     ecx, 2
0x180034593  jbe     short loc_1800345CF
0x180034595  mov     [rsp+4E0h+var_4A0], eax
0x180034599  mov     rcx, cs:?gc_wszRegMultivariant@@3PEBGEB; ushort const * const gc_wszRegMultivariant
0x1800345a0  mov     [rsp+4E0h+var_498], rcx
0x1800345a5  lea     rax, [rsp+4E0h+var_4A0]
0x1800345aa  mov     [rsp+4E0h+var_4B8], rax
0x1800345af  lea     rax, [rsp+4E0h+var_498]
0x1800345b4  mov     [rsp+4E0h+var_4C0], rax
0x1800345b9  xor     r8d, r8d
0x1800345bc  lea     rdx, byte_180050023
0x1800345c3  lea     rcx, dword_18005A000
0x1800345ca  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800345cf  mov     edx, 141h
0x1800345d4  jmp     loc_180034425
0x1800345d9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800345dd  cmp     [rbp+3E0h+var_460], r13w
0x1800345e2  jnz     short loc_1800345E9
0x1800345e4  mov     r8, r13
0x1800345e7  jmp     short loc_1800345FA
0x1800345e9  lea     rax, [rbp+3E0h+var_460]
0x1800345ed  mov     r8, rbx
0x1800345f0  inc     r8
0x1800345f3  cmp     [rax+r8*2], r13w
0x1800345f8  jnz     short loc_1800345F0
0x1800345fa  lea     rdx, [rbp+3E0h+var_460]
0x1800345fe  jmp     short loc_180034623
0x180034600  mov     rdx, cs:?gc_wszRegMultivariantStatus@@3PEBGEB; Src
0x180034607  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003460b  cmp     [rdx], r13w
0x18003460f  jnz     short loc_180034616
0x180034611  mov     r8, r13
0x180034614  jmp     short loc_180034623
0x180034616  mov     r8, rbx
0x180034619  inc     r8
0x18003461c  cmp     [rdx+r8*2], r13w
0x180034621  jnz     short loc_180034619
0x180034623  mov     rcx, rsi; void *
0x180034626  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003462b  mov     edx, 5Ch ; '\'
0x180034630  mov     rcx, rsi; Src
0x180034633  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180034638  lea     rdx, ?gc_wszRegCachedSettingCRCs@@3QBGB; "CachedCRCs"
0x18003463f  mov     rcx, rsi; Src
0x180034642  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180034647  mov     edx, 5Ch ; '\'
0x18003464c  mov     rcx, rsi; Src
0x18003464f  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180034654  lea     rdx, [rbp+3E0h+var_250]; void *
0x18003465b  mov     rcx, rsi; Src
0x18003465e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180034663  mov     edx, 5Ch ; '\'
0x180034668  mov     rcx, rsi; Src
0x18003466b  call    ?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z; std::wstring::push_back(ushort)
0x180034670  mov     rcx, [r15]
0x180034673  mov     rax, [rcx]
0x180034676  lea     rdx, [rsp+4E0h+var_490]
0x18003467b  mov     rax, [rax+10h]
0x18003467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034684  nop
0x180034685  mov     r9, rbx
0x180034688  xor     r8d, r8d
0x18003468b  mov     rdx, rax
0x18003468e  mov     rcx, rsi
0x180034691  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180034696  nop
0x180034697  cmp     [rsp+4E0h+var_478], 8
0x18003469d  jb      short loc_1800346AA
0x18003469f  mov     rcx, [rsp+4E0h+var_490]
0x1800346a4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800346aa  test    r14, r14
0x1800346ad  jz      loc_18003451F
0x1800346b3  mov     rdx, r14
0x1800346b6  mov     rcx, rdi
0x1800346b9  call    ?MvGetUniqueId@@YAJAEBU_MVProvisionData@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MvGetUniqueId(_MVProvisionData const &,std::wstring *)
0x1800346be  mov     ebx, eax
0x1800346c0  test    eax, eax
0x1800346c2  jns     loc_18003451F
0x1800346c8  mov     edx, 15Ch
0x1800346cd  jmp     loc_180034425
```
