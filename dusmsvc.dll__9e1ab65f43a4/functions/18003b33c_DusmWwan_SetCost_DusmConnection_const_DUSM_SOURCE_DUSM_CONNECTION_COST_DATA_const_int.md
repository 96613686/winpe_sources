# DusmWwan::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)

- ea: `0x18003b33c`
- end: `0x18003b563`
- name: `?SetCost@DusmWwan@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callers

- `0x18001d29c`

## callees

- `0x180007c90`
- `0x180008704`
- `0x18000f214`
- `0x180012fcc`
- `0x180017cec`
- `0x180018080`
- `0x1800183f8`
- `0x180019154`
- `0x18001d87c`
- `0x18002b21c`
- `0x180039824`
- `0x18003adf0`
- `0x18003b33c`
- `0x18003b64c`

## import_xrefs

- `RPCRT4!UuidToStringW` at `0x18003b450`
- `RPCRT4!UuidToStringW` at `0x18003b450`
- `wwapi!WwanFreeMemory` at `0x18003b4f4`
- `wwapi!WwanFreeMemory` at `0x18003b4f4`

## string_xrefs

- `0x18003b4b2`: `DusmWwan::SetCost::QueryWwanSubscriberInfo - IccId and/or Imsi properties are empty for profile %ws (GUID %ws) (iccid: %ws, imsi: %ws)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall DusmWwan::SetCost(DusmConnection *a1, unsigned int a2, __int64 a3, int a4)
{
  const WCHAR *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 v13; // rdx
  bool IsConnectionKeySet; // al
  const char *v15; // r8
  __int64 v16; // r9
  __int64 v17; // r10
  __int64 v18; // r11
  __int64 v19; // rcx
  const char *v20; // [rsp+28h] [rbp-D8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  RPC_WSTR StringUuid; // [rsp+58h] [rbp-A8h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v24[32]; // [rsp+70h] [rbp-90h] BYREF
  UUID v25; // [rsp+90h] [rbp-70h]
  _BYTE v26[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v27[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v28[176]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  if ( a2 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
      (const char *)0x57,
      (unsigned int)"DusmWwan::SetCost",
      v20);
  memset_0(v24, 0, 0x140u);
  v8 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a1 + 48);
  DusmConnection::DusmConnection((__int64)v24, (_OWORD *)a1 + 2, v8, 3, 0);
  if ( DusmConnection::IsConnectionKeySet(a1) )
  {
    std::wstring::operator=(v28, (char *)a1 + 144);
    std::wstring::operator=(v27, (char *)a1 + 112);
  }
  else
  {
    DusmWwan::QueryWwanSubscriberInfo(v9, &v21, (__int64)a1 + 32);
    v10 = v21 + 8;
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v10 + 2 * v12) );
    std::wstring::_Assign<wchar_t>(v27, v10, v12);
    v13 = v21 + 40;
    do
      ++v11;
    while ( *(_WORD *)(v13 + 2 * v11) );
    std::wstring::_Assign<wchar_t>(v28, v13, v11);
    Uuid = v25;
    StringUuid = 0;
    UuidToStringW(&Uuid, &StringUuid);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v27);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v28);
    std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v26);
    IsConnectionKeySet = DusmConnection::IsConnectionKeySet((DusmConnection *)v24);
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x39D,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
      (const char *)0x8000FFFFLL,
      !IsConnectionKeySet,
      (bool)"DusmWwan::SetCost::QueryWwanSubscriberInfo - IccId and/or Imsi properties are empty for profile %ws (GUID %w"
            "s) (iccid: %ws, imsi: %ws)",
      v15,
      v17,
      v16,
      v18);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
    v19 = v21;
    v21 = 0;
    if ( v19 )
      WwanFreeMemory(v19);
  }
  DusmStore::SetCost((__int64)v24, a2, a3, a4);
  DusmConnection::~DusmConnection((DusmConnection *)v24);
}

```

## disassembly

```asm
0x18003b33c  push    rbp
0x18003b33e  push    rbx
0x18003b33f  push    rsi
0x18003b340  push    rdi
0x18003b341  push    r12
0x18003b343  push    r14
0x18003b345  push    r15
0x18003b347  lea     rbp, [rsp-0C0h]
0x18003b34f  sub     rsp, 1C0h
0x18003b356  mov     rax, cs:__security_cookie
0x18003b35d  xor     rax, rsp
0x18003b360  mov     [rbp+0F0h+var_40], rax
0x18003b367  mov     r14d, r9d
0x18003b36a  mov     r15, r8
0x18003b36d  mov     edi, edx
0x18003b36f  mov     rbx, rcx
0x18003b372  lea     eax, [rdx-2]
0x18003b375  cmp     eax, 1
0x18003b378  ja      loc_18003B538
0x18003b37e  xor     edx, edx; Val
0x18003b380  mov     r8d, 140h; Size
0x18003b386  lea     rcx, [rsp+1F0h+var_180]; void *
0x18003b38b  call    memset_0
0x18003b390  lea     rcx, [rbx+30h]
0x18003b394  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003b399  xor     r12d, r12d
0x18003b39c  mov     qword ptr [rsp+1F0h+var_1D0], r12
0x18003b3a1  lea     r9d, [r12+3]
0x18003b3a6  mov     r8, rax
0x18003b3a9  lea     rdx, [rbx+20h]
0x18003b3ad  lea     rcx, [rsp+1F0h+var_180]
0x18003b3b2  call    ??0DusmConnection@@QEAA@PEBU_GUID@@PEB_WW4_DUSM_MEDIA_TYPE@@1@Z; DusmConnection::DusmConnection(_GUID const *,wchar_t const *,_DUSM_MEDIA_TYPE,wchar_t const *)
0x18003b3b7  nop
0x18003b3b8  mov     rcx, rbx; this
0x18003b3bb  call    ?IsConnectionKeySet@DusmConnection@@QEBA_NXZ; DusmConnection::IsConnectionKeySet(void)
0x18003b3c0  test    al, al
0x18003b3c2  jz      short loc_18003B3E6
0x18003b3c4  lea     rdx, [rbx+90h]
0x18003b3cb  lea     rcx, [rbp+0F0h+var_F0]
0x18003b3cf  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b3d4  lea     rdx, [rbx+70h]
0x18003b3d8  lea     rcx, [rbp+0F0h+var_110]
0x18003b3dc  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18003b3e1  jmp     loc_18003B4FA
0x18003b3e6  lea     r8, [rbx+20h]
0x18003b3ea  lea     rdx, [rsp+1F0h+var_1A0]
0x18003b3ef  call    ?QueryWwanSubscriberInfo@DusmWwan@@AEBA?AV?$unique_ptr@UWWAN_SUBSCRIBER_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@AEBU_GUID@@@Z; DusmWwan::QueryWwanSubscriberInfo(_GUID const &)
0x18003b3f4  nop
0x18003b3f5  mov     rdx, [rsp+1F0h+var_1A0]
0x18003b3fa  add     rdx, 8
0x18003b3fe  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18003b402  mov     r8, rbx
0x18003b405  inc     r8
0x18003b408  cmp     [rdx+r8*2], r12w
0x18003b40d  jnz     short loc_18003B405
0x18003b40f  lea     rcx, [rbp+0F0h+var_110]
0x18003b413  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003b418  mov     rdx, [rsp+1F0h+var_1A0]
0x18003b41d  add     rdx, 28h ; '('
0x18003b421  inc     rbx
0x18003b424  cmp     [rdx+rbx*2], r12w
0x18003b429  jnz     short loc_18003B421
0x18003b42b  mov     r8, rbx
0x18003b42e  lea     rcx, [rbp+0F0h+var_F0]
0x18003b432  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x18003b437  movaps  xmm0, [rbp+0F0h+var_160]
0x18003b43b  movdqu  xmmword ptr [rsp+1F0h+Uuid.Data1], xmm0
0x18003b441  mov     [rsp+1F0h+StringUuid], r12
0x18003b446  lea     rdx, [rsp+1F0h+StringUuid]; StringUuid
0x18003b44b  lea     rcx, [rsp+1F0h+Uuid]; Uuid
0x18003b450  call    cs:__imp_UuidToStringW
0x18003b456  mov     edx, eax
0x18003b458  lea     rcx, [rbp+0F0h+var_110]
0x18003b45c  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003b461  mov     r11, rax
0x18003b464  lea     rcx, [rbp+0F0h+var_F0]
0x18003b468  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003b46d  mov     r9, rax
0x18003b470  lea     r10, aUuidtostringFa; "(UuidToString failed)"
0x18003b477  test    edx, edx
0x18003b479  cmovz   r10, [rsp+1F0h+StringUuid]
0x18003b47f  lea     rcx, [rbp+0F0h+var_150]
0x18003b483  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18003b488  mov     r8, rax
0x18003b48b  lea     rcx, [rsp+1F0h+var_180]; this
0x18003b490  call    ?IsConnectionKeySet@DusmConnection@@QEBA_NXZ; DusmConnection::IsConnectionKeySet(void)
0x18003b495  xor     al, 1
0x18003b497  mov     rcx, [rbp+0F8h]; this
0x18003b49e  mov     [rsp+1F0h+var_1A8], r11
0x18003b4a3  mov     [rsp+1F0h+var_1B0], r9
0x18003b4a8  mov     [rsp+1F0h+var_1B8], r10
0x18003b4ad  mov     [rsp+1F0h+var_1C0], r8; char *
0x18003b4b2  lea     rdx, aDusmwwanSetcos; "DusmWwan::SetCost::QueryWwanSubscriberI"...
0x18003b4b9  mov     qword ptr [rsp+1F0h+var_1C8], rdx; bool
0x18003b4be  mov     [rsp+1F0h+var_1D0], al; char
0x18003b4c2  mov     r9d, 8000FFFFh; char *
0x18003b4c8  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003b4cf  mov     edx, 39Dh; void *
0x18003b4d4  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003b4d9  nop
0x18003b4da  lea     rcx, [rsp+1F0h+StringUuid]
0x18003b4df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003b4e4  nop
0x18003b4e5  mov     rcx, [rsp+1F0h+var_1A0]
0x18003b4ea  mov     [rsp+1F0h+var_1A0], r12
0x18003b4ef  test    rcx, rcx
0x18003b4f2  jz      short loc_18003B4FA
0x18003b4f4  call    cs:__imp_WwanFreeMemory
0x18003b4fa  mov     r9d, r14d
0x18003b4fd  mov     r8, r15
0x18003b500  mov     edx, edi
0x18003b502  lea     rcx, [rsp+1F0h+var_180]
0x18003b507  call    ?SetCost@DusmStore@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z; DusmStore::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)
0x18003b50c  nop
0x18003b50d  lea     rcx, [rsp+1F0h+var_180]; this
0x18003b512  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x18003b517  mov     rcx, [rbp+0F0h+var_40]
0x18003b51e  xor     rcx, rsp; StackCookie
0x18003b521  call    __security_check_cookie
0x18003b526  add     rsp, 1C0h
0x18003b52d  pop     r15
0x18003b52f  pop     r14
0x18003b531  pop     r12
0x18003b533  pop     rdi
0x18003b534  pop     rsi
0x18003b535  pop     rbx
0x18003b536  pop     rbp
0x18003b537  retn
0x18003b538  mov     rcx, [rbp+0F8h]; this
0x18003b53f  lea     rax, aDusmwwanSetcos_0; "DusmWwan::SetCost"
0x18003b546  mov     qword ptr [rsp+1F0h+var_1D0], rax; unsigned int
0x18003b54b  mov     r9d, 57h ; 'W'; char *
0x18003b551  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003b558  mov     edx, 383h; void *
0x18003b55d  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
