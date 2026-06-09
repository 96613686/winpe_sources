# ProvPackage::OpenProvPackage(void)

- ea: `0x180034150`
- end: `0x18003442c`
- name: `?OpenProvPackage@ProvPackage@@UEAA_NXZ`
- size: `732`
- prototype: `bool __fastcall(ProvPackage *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting`

## callees

- `0x180001a30`
- `0x180001a40`
- `0x180001a70`
- `0x180001b14`
- `0x180001ba8`
- `0x180001cf0`
- `0x1800046ac`
- `0x1800090e0`
- `0x18000929c`
- `0x180009fac`
- `0x180034150`
- `0x180035624`
- `0x1800358a0`
- `0x180038010`

## import_xrefs

- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180034218`
- `provpackageapidll!OpenProvisioningPackageForRead` at `0x180034218`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ProvPackage::OpenProvPackage(ProvPackage *this, __int64 a2, int a3, int a4)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _QWORD *v7; // rcx
  int v8; // esi
  _QWORD *v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int v14; // ecx
  int v15; // ebx
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // r8
  __int64 v19; // rbx
  __int64 v20; // rcx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // eax
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // r8d
  int v28; // r9d
  unsigned int v29; // eax
  int v30; // [rsp+20h] [rbp-E0h]
  int v31[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v32; // [rsp+38h] [rbp-C8h] BYREF
  _WORD *v33; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+48h] [rbp-B8h] BYREF
  _WORD Src[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v5 = (_QWORD *)((char *)this + 8);
  if ( (unsigned int)dword_1800495B0 > 5 )
  {
    if ( *((_QWORD *)this + 4) < 8u )
      v6 = (char *)this + 8;
    else
      v6 = (char *)*v5;
    *(_QWORD *)v31 = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      (_DWORD)this,
      (unsigned int)qword_180041D70,
      a3,
      a4,
      (__int64)v31);
  }
  if ( !v5[2] )
  {
    if ( (unsigned int)dword_1800495B0 > 3 )
      tlgWriteTransfer_EventWriteTransfer((__int64)&dword_1800495B0, (unsigned __int8 *)&word_180041D4E, 0, 0, 2u, &v34);
    return 0;
  }
  v32 = 0;
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_QWORD *)*v5;
  v8 = OpenProvisioningPackageForRead(v7, &v32);
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
    {
      v31[0] = v8;
      v25 = std::wstring::c_str(v5);
      v26 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v33, v25);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (unsigned int)v31,
        (unsigned int)&dword_180041CDC,
        v27,
        v28,
        v26,
        (__int64)v31);
    }
    v29 = wil::verify_hresult<long>((unsigned int)v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x71,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v29,
      v30);
  }
  if ( v5[3] < 8u )
    v9 = v5;
  else
    v9 = (_QWORD *)*v5;
  if ( !(unsigned __int8)Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(
                           v9,
                           (char *)this + 112) )
  {
    if ( (unsigned int)dword_1800495B0 > 2 )
    {
      if ( v5[3] >= 8u )
        v5 = (_QWORD *)*v5;
      *(_QWORD *)v31 = v5;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v10,
        (unsigned int)word_180041C9A,
        v11,
        v12,
        (__int64)v31);
    }
    return 0;
  }
  v15 = (*(__int64 (__fastcall **)(__int64, _WORD *, __int64))(*(_QWORD *)v32 + 8LL))(v32, Src, 260);
  if ( v15 < 0 )
  {
    if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
    {
      v31[0] = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)&unk_180041D18,
        v22,
        v23,
        (__int64)v31);
    }
    v24 = wil::verify_hresult<long>((unsigned int)v15);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackage.cpp",
      (const char *)v24,
      v30);
  }
  if ( (unsigned int)dword_1800495B0 > 4 )
  {
    v31[0] = v15;
    v33 = Src;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v14,
      (unsigned int)byte_180041C33,
      v16,
      v17,
      (__int64)&v33,
      (__int64)v31);
  }
  if ( Src[0] )
  {
    v18 = -1;
    do
      ++v18;
    while ( Src[v18] );
  }
  std::wstring::assign((char *)this + 72, Src);
  v19 = v32;
  v20 = *((_QWORD *)this + 13);
  if ( v32 != v20 )
  {
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 128LL))(v20);
    *((_QWORD *)this + 13) = v19;
  }
  return 1;
}

```

## disassembly

```asm
0x180034150  mov     [rsp-8+arg_8], rbx
0x180034155  mov     [rsp-8+arg_10], rsi
0x18003415a  push    rbp
0x18003415b  push    rdi
0x18003415c  push    r14
0x18003415e  lea     rbp, [rsp-190h]
0x180034166  sub     rsp, 290h
0x18003416d  mov     rax, cs:__security_cookie
0x180034174  xor     rax, rsp
0x180034177  mov     [rbp+1A0h+var_20], rax
0x18003417e  mov     rdi, rcx
0x180034181  mov     eax, cs:dword_1800495B0
0x180034187  lea     rbx, [rcx+8]
0x18003418b  cmp     eax, 5
0x18003418e  jbe     short loc_1800341BA
0x180034190  cmp     qword ptr [rbx+18h], 8
0x180034195  jb      short loc_18003419C
0x180034197  mov     rax, [rbx]
0x18003419a  jmp     short loc_18003419F
0x18003419c  mov     rax, rbx
0x18003419f  mov     qword ptr [rsp+2A0h+var_270], rax
0x1800341a4  lea     rax, [rsp+2A0h+var_270]
0x1800341a9  mov     qword ptr [rsp+2A0h+var_280], rax
0x1800341ae  lea     rdx, qword_180041D70
0x1800341b5  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800341ba  xor     r14d, r14d
0x1800341bd  cmp     [rbx+10h], r14
0x1800341c1  jnz     short loc_1800341FF
0x1800341c3  mov     eax, cs:dword_1800495B0
0x1800341c9  cmp     eax, 3
0x1800341cc  jbe     loc_18003427A
0x1800341d2  lea     rax, [rsp+2A0h+var_258]
0x1800341d7  mov     [rsp+2A0h+var_278], rax
0x1800341dc  mov     [rsp+2A0h+var_280], 2
0x1800341e4  xor     r9d, r9d
0x1800341e7  xor     r8d, r8d
0x1800341ea  lea     rdx, word_180041D4E
0x1800341f1  lea     rcx, dword_1800495B0
0x1800341f8  call    _tlgWriteTransfer_EventWriteTransfer
0x1800341fd  jmp     short loc_18003427A
0x1800341ff  mov     [rsp+2A0h+var_268], r14
0x180034204  cmp     qword ptr [rbx+18h], 8
0x180034209  jb      short loc_180034210
0x18003420b  mov     rcx, [rbx]
0x18003420e  jmp     short loc_180034213
0x180034210  mov     rcx, rbx
0x180034213  lea     rdx, [rsp+2A0h+var_268]
0x180034218  call    cs:__imp_OpenProvisioningPackageForRead
0x18003421f  nop     dword ptr [rax+rax+00h]
0x180034224  mov     esi, eax
0x180034226  test    eax, eax
0x180034228  js      loc_1800343B8
0x18003422e  cmp     qword ptr [rbx+18h], 8
0x180034233  jb      short loc_18003423A
0x180034235  mov     rcx, [rbx]
0x180034238  jmp     short loc_18003423D
0x18003423a  mov     rcx, rbx
0x18003423d  lea     rdx, [rdi+70h]
0x180034241  call    ?TryCreateProvisioningFileManagerOnPPKG@Provisioning@Management@Internal@Windows@@YA_NPEBGAEAV?$unique_ptr@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@U?$default_delete@VIProvisioningFileManager@Provisioning@Management@Internal@Windows@@@std@@@std@@@Z; Windows::Internal::Management::Provisioning::TryCreateProvisioningFileManagerOnPPKG(ushort const *,std::unique_ptr<Windows::Internal::Management::Provisioning::IProvisioningFileManager> &)
0x180034246  test    al, al
0x180034248  jnz     short loc_180034281
0x18003424a  mov     eax, cs:dword_1800495B0
0x180034250  cmp     eax, 2
0x180034253  jbe     short loc_18003427A
0x180034255  cmp     qword ptr [rbx+18h], 8
0x18003425a  jb      short loc_18003425F
0x18003425c  mov     rbx, [rbx]
0x18003425f  mov     qword ptr [rsp+2A0h+var_270], rbx
0x180034264  lea     rax, [rsp+2A0h+var_270]
0x180034269  mov     qword ptr [rsp+2A0h+var_280], rax
0x18003426e  lea     rdx, word_180041C9A
0x180034275  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003427a  xor     al, al
0x18003427c  jmp     loc_180034336
0x180034281  mov     rcx, [rsp+2A0h+var_268]
0x180034286  mov     rax, [rcx]
0x180034289  mov     r8d, 104h
0x18003428f  lea     rdx, [rsp+2A0h+Src]
0x180034294  mov     rax, [rax+8]
0x180034298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003429d  mov     ebx, eax
0x18003429f  test    eax, eax
0x1800342a1  js      loc_18003435E
0x1800342a7  mov     eax, cs:dword_1800495B0
0x1800342ad  cmp     eax, 4
0x1800342b0  jbe     short loc_1800342E0
0x1800342b2  mov     [rsp+2A0h+var_270], ebx
0x1800342b6  lea     rax, [rsp+2A0h+Src]
0x1800342bb  mov     [rsp+2A0h+var_260], rax
0x1800342c0  lea     rax, [rsp+2A0h+var_270]
0x1800342c5  mov     [rsp+2A0h+var_278], rax
0x1800342ca  lea     rax, [rsp+2A0h+var_260]
0x1800342cf  mov     qword ptr [rsp+2A0h+var_280], rax
0x1800342d4  lea     rdx, byte_180041C33
0x1800342db  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800342e0  cmp     [rsp+2A0h+Src], r14w
0x1800342e6  jnz     short loc_1800342ED
0x1800342e8  mov     r8, r14
0x1800342eb  jmp     short loc_180034300
0x1800342ed  lea     rax, [rsp+2A0h+Src]
0x1800342f2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800342f6  inc     r8
0x1800342f9  cmp     [rax+r8*2], r14w
0x1800342fe  jnz     short loc_1800342F6
0x180034300  lea     rcx, [rdi+48h]; void *
0x180034304  lea     rdx, [rsp+2A0h+Src]; Src
0x180034309  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003430e  mov     rbx, [rsp+2A0h+var_268]
0x180034313  mov     rcx, [rdi+68h]
0x180034317  cmp     rbx, rcx
0x18003431a  jz      short loc_180034334
0x18003431c  test    rcx, rcx
0x18003431f  jz      short loc_180034330
0x180034321  mov     rax, [rcx]
0x180034324  mov     rax, [rax+80h]
0x18003432b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034330  mov     [rdi+68h], rbx
0x180034334  mov     al, 1
0x180034336  mov     rcx, [rbp+1A0h+var_20]
0x18003433d  xor     rcx, rsp; StackCookie
0x180034340  call    __security_check_cookie
0x180034345  lea     r11, [rsp+2A0h+var_10]
0x18003434d  mov     rbx, [r11+28h]
0x180034351  mov     rsi, [r11+30h]
0x180034355  mov     rsp, r11
0x180034358  pop     r14
0x18003435a  pop     rdi
0x18003435b  pop     rbp
0x18003435c  retn
0x18003435e  mov     ecx, cs:dword_1800495B0
0x180034364  cmp     ecx, 2
0x180034367  jbe     short loc_180034395
0x180034369  xor     edx, edx
0x18003436b  lea     rcx, dword_1800495B0
0x180034372  call    _tlgKeywordOn
0x180034377  test    al, al
0x180034379  jz      short loc_180034395
0x18003437b  mov     [rsp+2A0h+var_270], ebx
0x18003437f  lea     rax, [rsp+2A0h+var_270]
0x180034384  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x180034389  lea     rdx, unk_180041D18
0x180034390  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180034395  mov     ecx, ebx
0x180034397  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003439c  mov     r9d, eax; char *
0x18003439f  mov     rcx, [rbp+1A8h]; this
0x1800343a6  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800343ad  mov     edx, 83h; void *
0x1800343b2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800343b8  mov     edx, cs:dword_1800495B0
0x1800343be  cmp     edx, 2
0x1800343c1  jbe     short loc_180034409
0x1800343c3  xor     edx, edx
0x1800343c5  lea     rcx, dword_1800495B0
0x1800343cc  call    _tlgKeywordOn
0x1800343d1  test    al, al
0x1800343d3  jz      short loc_180034409
0x1800343d5  mov     [rsp+2A0h+var_270], esi
0x1800343d9  mov     rcx, rbx
0x1800343dc  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800343e1  mov     rdx, rax
0x1800343e4  lea     rcx, [rsp+2A0h+var_260]
0x1800343e9  call    ??0?$_tlgWrapSz@G@@QEAA@PEBG@Z; _tlgWrapSz<ushort>::_tlgWrapSz<ushort>(ushort const *)
0x1800343ee  lea     rcx, [rsp+2A0h+var_270]
0x1800343f3  mov     [rsp+2A0h+var_278], rcx
0x1800343f8  mov     qword ptr [rsp+2A0h+var_280], rax; int
0x1800343fd  lea     rdx, dword_180041CDC
0x180034404  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180034409  mov     ecx, esi
0x18003440b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180034410  mov     r9d, eax; char *
0x180034413  mov     rcx, [rbp+1A8h]; this
0x18003441a  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180034421  mov     edx, 71h ; 'q'; void *
0x180034426  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
