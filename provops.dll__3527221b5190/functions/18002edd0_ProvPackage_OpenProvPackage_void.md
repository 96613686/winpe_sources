# ProvPackage::OpenProvPackage(void)

- ea: `0x18002edd0`
- end: `0x18002f0bf`
- name: `?OpenProvPackage@ProvPackage@@UEAA_NXZ`
- size: `751`
- prototype: `char __fastcall(ProvPackage *this, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting`

## callers

- `0x180023558`
- `0x180023830`

## callees

- `0x1800015b4`
- `0x18000164c`
- `0x180001678`
- `0x1800017ec`
- `0x180001878`
- `0x180001920`
- `0x180004d68`
- `0x18001b388`
- `0x1800210f0`
- `0x180021200`
- `0x18002edd0`
- `0x180032c44`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002ee9a`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x18002ee9a`

## pseudocode

```c
char __fastcall ProvPackage::OpenProvPackage(ProvPackage *this, __int64 a2, __int64 a3, int a4)
{
  char *v5; // rbx
  char *v6; // rax
  char *v7; // rcx
  int v8; // esi
  char *v9; // rcx
  int v10; // r9d
  int v12; // ebx
  int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rcx
  int v17; // r9d
  unsigned int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // r9d
  unsigned int v22; // eax
  int v23; // [rsp+20h] [rbp-E0h]
  int v24[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h] BYREF
  _WORD *v26; // [rsp+40h] [rbp-C0h] BYREF
  _WORD Src[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v5 = (char *)this + 8;
  if ( *(_DWORD *)g_hProvTraceProvider > 5u )
  {
    if ( *((_QWORD *)this + 4) < 8u )
      v6 = (char *)this + 8;
    else
      v6 = *(char **)v5;
    *(_QWORD *)v24 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      g_hProvTraceProvider,
      (unsigned int)byte_180041D5D,
      0,
      a4,
      (__int64)v24);
  }
  if ( !*((_QWORD *)this + 3) )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 3u )
      tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, byte_180041D3B, 0, 0);
    return 0;
  }
  v25 = 0;
  if ( *((_QWORD *)this + 4) < 8u )
    v7 = (char *)this + 8;
  else
    v7 = *(char **)v5;
  v8 = OpenProvisioningPackageForRead(v7, &v25);
  if ( v8 < 0 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
    {
      v24[0] = v8;
      v19 = std::wstring::c_str((char *)this + 8);
      v20 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v26, v19);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&byte_180041CFF,
        0,
        v21,
        v20,
        (__int64)v24);
    }
    v22 = wil::verify_hresult<long>((unsigned int)v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v22,
      v23);
  }
  if ( *((_QWORD *)this + 4) < 8u )
    v9 = (char *)this + 8;
  else
    v9 = *(char **)v5;
  if ( !(unsigned __int8)Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
                           v9,
                           (char *)this + 112) )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u )
    {
      if ( *((_QWORD *)this + 4) >= 8u )
        v5 = *(char **)v5;
      *(_QWORD *)v24 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (unsigned int)byte_180041CBD,
        0,
        v10,
        (__int64)v24);
    }
    return 0;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v25 + 8LL))(v25, Src, 260);
  if ( v12 < 0 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
    {
      v24[0] = v12;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)&byte_180041C87,
        0,
        v17,
        (__int64)v24);
    }
    v18 = wil::verify_hresult<long>((unsigned int)v12);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v18,
      v23);
  }
  if ( *(_DWORD *)g_hProvTraceProvider > 4u )
  {
    v24[0] = v12;
    v26 = Src;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      g_hProvTraceProvider,
      (unsigned int)&unk_180041C50,
      0,
      v13,
      (__int64)&v26,
      (__int64)v24);
  }
  if ( Src[0] )
  {
    v14 = -1;
    do
      ++v14;
    while ( Src[v14] );
  }
  std::wstring::assign((char *)this + 72, Src);
  v15 = v25;
  v16 = *((_QWORD *)this + 13);
  if ( v25 != v16 )
  {
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 128LL))(v16);
    *((_QWORD *)this + 13) = v15;
  }
  return 1;
}

```

## disassembly

```asm
0x18002edd0  mov     [rsp-8+arg_8], rbx
0x18002edd5  mov     [rsp-8+arg_10], rsi
0x18002edda  push    rbp
0x18002eddb  push    rdi
0x18002eddc  push    r14
0x18002edde  lea     rbp, [rsp-190h]
0x18002ede6  sub     rsp, 290h
0x18002eded  mov     rax, cs:__security_cookie
0x18002edf4  xor     rax, rsp
0x18002edf7  mov     [rbp+1A0h+var_20], rax
0x18002edfe  mov     rdi, rcx
0x18002ee01  mov     rcx, cs:g_hProvTraceProvider
0x18002ee08  mov     eax, [rcx]
0x18002ee0a  lea     rbx, [rdi+8]
0x18002ee0e  cmp     eax, 5
0x18002ee11  jbe     short loc_18002EE40
0x18002ee13  cmp     qword ptr [rbx+18h], 8
0x18002ee18  jb      short loc_18002EE1F
0x18002ee1a  mov     rax, [rbx]
0x18002ee1d  jmp     short loc_18002EE22
0x18002ee1f  mov     rax, rbx
0x18002ee22  mov     qword ptr [rsp+2A0h+var_270], rax
0x18002ee27  lea     rax, [rsp+2A0h+var_270]
0x18002ee2c  mov     qword ptr [rsp+2A0h+var_280], rax
0x18002ee31  xor     r8d, r8d
0x18002ee34  lea     rdx, byte_180041D5D
0x18002ee3b  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002ee40  xor     r14d, r14d
0x18002ee43  cmp     [rbx+10h], r14
0x18002ee47  jnz     short loc_18002EE81
0x18002ee49  mov     rcx, cs:g_hProvTraceProvider
0x18002ee50  mov     eax, [rcx]
0x18002ee52  cmp     eax, 3
0x18002ee55  jbe     loc_18002EEFC
0x18002ee5b  lea     rax, [rsp+2A0h+var_258]
0x18002ee60  mov     [rsp+2A0h+var_278], rax
0x18002ee65  mov     [rsp+2A0h+var_280], 2
0x18002ee6d  xor     r9d, r9d
0x18002ee70  xor     r8d, r8d
0x18002ee73  lea     rdx, byte_180041D3B
0x18002ee7a  call    _tlgWriteTransfer_EventWriteTransfer
0x18002ee7f  jmp     short loc_18002EEFC
0x18002ee81  mov     [rsp+2A0h+var_268], r14
0x18002ee86  cmp     qword ptr [rbx+18h], 8
0x18002ee8b  jb      short loc_18002EE92
0x18002ee8d  mov     rcx, [rbx]
0x18002ee90  jmp     short loc_18002EE95
0x18002ee92  mov     rcx, rbx
0x18002ee95  lea     rdx, [rsp+2A0h+var_268]
0x18002ee9a  call    cs:__imp_OpenProvisioningPackageForRead
0x18002eea0  mov     esi, eax
0x18002eea2  test    eax, eax
0x18002eea4  js      loc_18002F045
0x18002eeaa  cmp     qword ptr [rbx+18h], 8
0x18002eeaf  jb      short loc_18002EEB6
0x18002eeb1  mov     rcx, [rbx]
0x18002eeb4  jmp     short loc_18002EEB9
0x18002eeb6  mov     rcx, rbx
0x18002eeb9  lea     rdx, [rdi+70h]
0x18002eebd  call    ?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x18002eec2  test    al, al
0x18002eec4  jnz     short loc_18002EF03
0x18002eec6  mov     rcx, cs:g_hProvTraceProvider
0x18002eecd  mov     eax, [rcx]
0x18002eecf  cmp     eax, 2
0x18002eed2  jbe     short loc_18002EEFC
0x18002eed4  cmp     qword ptr [rbx+18h], 8
0x18002eed9  jb      short loc_18002EEDE
0x18002eedb  mov     rbx, [rbx]
0x18002eede  mov     qword ptr [rsp+2A0h+var_270], rbx
0x18002eee3  lea     rax, [rsp+2A0h+var_270]
0x18002eee8  mov     qword ptr [rsp+2A0h+var_280], rax
0x18002eeed  xor     r8d, r8d
0x18002eef0  lea     rdx, byte_180041CBD
0x18002eef7  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18002eefc  xor     al, al
0x18002eefe  jmp     loc_18002EFBE
0x18002ef03  mov     rcx, [rsp+2A0h+var_268]
0x18002ef08  mov     rax, [rcx]
0x18002ef0b  mov     r8d, 104h
0x18002ef11  lea     rdx, [rsp+2A0h+Src]
0x18002ef16  mov     rax, [rax+8]
0x18002ef1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ef1f  mov     ebx, eax
0x18002ef21  test    eax, eax
0x18002ef23  js      loc_18002EFE5
0x18002ef29  mov     rcx, cs:g_hProvTraceProvider
0x18002ef30  mov     eax, [rcx]
0x18002ef32  cmp     eax, 4
0x18002ef35  jbe     short loc_18002EF68
0x18002ef37  mov     [rsp+2A0h+var_270], ebx
0x18002ef3b  lea     rax, [rsp+2A0h+Src]
0x18002ef40  mov     [rsp+2A0h+var_260], rax
0x18002ef45  lea     rax, [rsp+2A0h+var_270]
0x18002ef4a  mov     [rsp+2A0h+var_278], rax
0x18002ef4f  lea     rax, [rsp+2A0h+var_260]
0x18002ef54  mov     qword ptr [rsp+2A0h+var_280], rax
0x18002ef59  xor     r8d, r8d
0x18002ef5c  lea     rdx, unk_180041C50
0x18002ef63  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002ef68  cmp     [rsp+2A0h+Src], r14w
0x18002ef6e  jnz     short loc_18002EF75
0x18002ef70  mov     r8, r14
0x18002ef73  jmp     short loc_18002EF88
0x18002ef75  lea     rax, [rsp+2A0h+Src]
0x18002ef7a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002ef7e  inc     r8
0x18002ef81  cmp     [rax+r8*2], r14w
0x18002ef86  jnz     short loc_18002EF7E
0x18002ef88  lea     rcx, [rdi+48h]; void *
0x18002ef8c  lea     rdx, [rsp+2A0h+Src]; Src
0x18002ef91  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002ef96  mov     rbx, [rsp+2A0h+var_268]
0x18002ef9b  mov     rcx, [rdi+68h]
0x18002ef9f  cmp     rbx, rcx
0x18002efa2  jz      short loc_18002EFBC
0x18002efa4  test    rcx, rcx
0x18002efa7  jz      short loc_18002EFB8
0x18002efa9  mov     rax, [rcx]
0x18002efac  mov     rax, [rax+80h]
0x18002efb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002efb8  mov     [rdi+68h], rbx
0x18002efbc  mov     al, 1
0x18002efbe  mov     rcx, [rbp+1A0h+var_20]
0x18002efc5  xor     rcx, rsp; StackCookie
0x18002efc8  call    __security_check_cookie
0x18002efcd  lea     r11, [rsp+2A0h+var_10]
0x18002efd5  mov     rbx, [r11+28h]
0x18002efd9  mov     rsi, [r11+30h]
0x18002efdd  mov     rsp, r11
0x18002efe0  pop     r14
0x18002efe2  pop     rdi
0x18002efe3  pop     rbp
0x18002efe4  retn
0x18002efe5  mov     r9, cs:g_hProvTraceProvider
0x18002efec  mov     ecx, [r9]
0x18002efef  cmp     ecx, 2
0x18002eff2  jbe     short loc_18002F022
0x18002eff4  xor     edx, edx
0x18002eff6  mov     rcx, r9
0x18002eff9  call    _tlgKeywordOn
0x18002effe  test    al, al
0x18002f000  jz      short loc_18002F022
0x18002f002  mov     [rsp+2A0h+var_270], ebx
0x18002f006  lea     rax, [rsp+2A0h+var_270]
0x18002f00b  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18002f010  xor     r8d, r8d
0x18002f013  lea     rdx, byte_180041C87
0x18002f01a  mov     rcx, r9
0x18002f01d  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002f022  mov     ecx, ebx
0x18002f024  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f029  mov     r9d, eax; char *
0x18002f02c  mov     rcx, [rbp+1A8h]; this
0x18002f033  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002f03a  mov     edx, 83h; void *
0x18002f03f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002f045  mov     r9, cs:g_hProvTraceProvider
0x18002f04c  mov     edx, [r9]
0x18002f04f  cmp     edx, 2
0x18002f052  jbe     short loc_18002F09C
0x18002f054  xor     edx, edx
0x18002f056  mov     rcx, r9
0x18002f059  call    _tlgKeywordOn
0x18002f05e  test    al, al
0x18002f060  jz      short loc_18002F09C
0x18002f062  mov     [rsp+2A0h+var_270], esi
0x18002f066  mov     rcx, rbx
0x18002f069  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x18002f06e  mov     rdx, rax
0x18002f071  lea     rcx, [rsp+2A0h+var_260]
0x18002f076  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18002f07b  lea     rcx, [rsp+2A0h+var_270]
0x18002f080  mov     [rsp+2A0h+var_278], rcx
0x18002f085  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x18002f08a  xor     r8d, r8d
0x18002f08d  lea     rdx, byte_180041CFF
0x18002f094  mov     rcx, r9
0x18002f097  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002f09c  mov     ecx, esi
0x18002f09e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002f0a3  mov     r9d, eax; char *
0x18002f0a6  mov     rcx, [rbp+1A8h]; this
0x18002f0ad  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002f0b4  mov     edx, 71h ; 'q'; void *
0x18002f0b9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
