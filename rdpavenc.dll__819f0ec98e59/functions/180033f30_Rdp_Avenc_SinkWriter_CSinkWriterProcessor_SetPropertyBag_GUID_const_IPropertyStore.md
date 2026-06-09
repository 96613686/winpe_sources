# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::SetPropertyBag(_GUID const &,IPropertyStore *)

- ea: `0x180033f30`
- end: `0x1800341c3`
- name: `?SetPropertyBag@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJAEBU_GUID@@PEAUIPropertyStore@@@Z`
- size: `659`
- prototype: `int(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this, const struct _GUID *, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180006580`
- `0x1800065a4`
- `0x1800069a0`
- `0x18000cf44`
- `0x18000d0ac`
- `0x18000d13c`
- `0x18000e848`
- `0x180010c10`
- `0x1800126b0`
- `0x180017b98`
- `0x180019d6c`
- `0x18001afac`
- `0x180022840`
- `0x180022c9c`
- `0x1800238a0`
- `0x180023fb8`
- `0x180033f30`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003405b`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003405b`

## string_xrefs

- `0x180033faf`: `Failed to retrieve PKEY_ProtocolName property`
- `0x180033fbe`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x180034002`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::SetPropertyBag(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this,
        const struct _GUID *a2,
        struct IPropertyStore *a3)
{
  unsigned int WString; // eax
  unsigned int *v6; // r9
  unsigned int UInt32; // eax
  __int64 v8; // rax
  _QWORD *v9; // rbx
  void *v10; // rcx
  __int64 v11; // rsi
  int v12; // r14d
  __int64 v13; // rbx
  __int64 v14; // r8
  __int128 *v15; // r9
  int v16; // eax
  int v17; // r8d
  __int64 Session; // rax
  volatile signed __int32 *v19; // rbx
  const char *v20; // r9
  __int64 result; // rax
  const char *v22; // [rsp+28h] [rbp-D0h]
  const char *v23; // [rsp+28h] [rbp-D0h]
  _BYTE v24[24]; // [rsp+40h] [rbp-B8h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+68h] [rbp-90h]
  unsigned __int64 v27; // [rsp+70h] [rbp-88h]
  _BYTE v28[32]; // [rsp+78h] [rbp-80h] BYREF
  _BYTE v29[32]; // [rsp+98h] [rbp-60h] BYREF
  _BYTE v30[32]; // [rsp+B8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  if ( *(_OWORD *)a2 != *(_OWORD *)&GUID_ConfigPropStore )
    return 2147500033LL;
  v25 = 0;
  v26 = 0;
  v27 = 7;
  LOWORD(v25) = 0;
  WString = Rdp::Utils::Props::IPropertyStore_GetWString(a3, a2, &v25);
  try
  {
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x27D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      (const char *)WString,
      (int)"Failed to retrieve PKEY_ProtocolName property",
      v22);
    *(_DWORD *)v24 = 0;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               (Rdp::Utils::Props *)a3,
               (struct IPropertyStore *)&PKEY_ConnectionId,
               (const struct _tagpropertykey *)v24,
               v6);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x285,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_ConnectionId property",
      v23);
    *(_QWORD *)&v24[8] = operator new(0xC0u);
    v8 = Rdp::Utils::Perf::CRdpGraphPerfMonLogger::CRdpGraphPerfMonLogger(*(PPERF_PROVIDER_CONTEXT *)&v24[8]);
    v9 = (_QWORD *)*((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = v8;
    if ( v9 )
    {
      std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(v9 + 9);
      std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(v9 + 7);
      v10 = (void *)v9[5];
      if ( v10 )
        PerfStopProvider(v10);
      operator delete(v9);
    }
    v11 = *((_QWORD *)this + 21);
    v12 = *((_DWORD *)this + 14);
    v13 = std::to_wstring(v30, *(unsigned int *)v24);
    if ( v26 == 0x7FFFFFFFFFFFFFFELL )
      std::_Xlen_string();
    v15 = &v25;
    if ( v27 > 7 )
      v15 = (__int128 *)v25;
    std::wstring::wstring(v28, v26, v14, v15, v26, L" ", 1);
    v16 = std::operator+<unsigned short>(v29, v28, v13);
    Session = Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::CreateSession(
                v11,
                (unsigned int)&v24[8],
                v17,
                v16,
                v12);
    std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=((char *)this + 208, Session);
    v19 = *(volatile signed __int32 **)&v24[16];
    if ( *(_QWORD *)&v24[16] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v24[16] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    std::wstring::~wstring(v29);
    std::wstring::~wstring(v28);
    std::wstring::~wstring(v30);
    std::wstring::~wstring(&v25);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x296,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x180033f30  mov     [rsp+arg_8], rbx
0x180033f35  push    rsi
0x180033f36  push    rdi
0x180033f37  push    r14
0x180033f39  sub     rsp, 0E0h
0x180033f40  mov     rax, cs:__security_cookie
0x180033f47  xor     rax, rsp
0x180033f4a  mov     [rsp+0F8h+var_20], rax
0x180033f52  mov     rbx, r8
0x180033f55  mov     rdi, rcx
0x180033f58  mov     rax, [rdx]
0x180033f5b  cmp     rax, qword ptr cs:GUID_ConfigPropStore.Data1
0x180033f62  jnz     loc_18003418D
0x180033f68  mov     rax, [rdx+8]
0x180033f6c  cmp     rax, qword ptr cs:GUID_ConfigPropStore.Data4
0x180033f73  jnz     loc_18003418D
0x180033f79  xorps   xmm0, xmm0
0x180033f7c  movups  [rsp+0F8h+var_A0], xmm0
0x180033f81  mov     [rsp+0F8h+var_90], 0
0x180033f8a  mov     [rsp+0F8h+var_88], 7
0x180033f93  xor     eax, eax
0x180033f95  mov     word ptr [rsp+0F8h+var_A0], ax
0x180033f9a  lea     r8, [rsp+0F8h+var_A0]
0x180033f9f  mov     rcx, rbx
0x180033fa2  call    ?IPropertyStore_GetWString@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Rdp::Utils::Props::IPropertyStore_GetWString(IPropertyStore *,_tagpropertykey const &,std::wstring &)
0x180033fa7  mov     rcx, [rsp+0F8h]; this
0x180033faf  lea     rdx, aFailedToRetrie_10; "Failed to retrieve PKEY_ProtocolName pr"...
0x180033fb6  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180033fbb  mov     r9d, eax; char *
0x180033fbe  lea     r8, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180033fc5  mov     edx, 27Dh; void *
0x180033fca  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180033fcf  mov     dword ptr [rsp+0F8h+var_B8], 0
0x180033fd7  lea     r8, [rsp+0F8h+var_B8]; struct _tagpropertykey *
0x180033fdc  lea     rdx, PKEY_ConnectionId; struct IPropertyStore *
0x180033fe3  mov     rcx, rbx; this
0x180033fe6  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180033feb  mov     rcx, [rsp+0F8h]; this
0x180033ff3  lea     rdx, aFailedToRetrie_11; "Failed to retrieve PKEY_ConnectionId pr"...
0x180033ffa  mov     qword ptr [rsp+0F8h+var_D8], rdx; int
0x180033fff  mov     r9d, eax; char *
0x180034002  lea     r8, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180034009  mov     edx, 285h; void *
0x18003400e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034013  mov     esi, 0C0h
0x180034018  mov     ecx, esi; Size
0x18003401a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003401f  mov     qword ptr [rsp+0F8h+var_B8+8], rax
0x180034024  mov     rcx, rax; ProviderContext
0x180034027  call    ??0CRdpGraphPerfMonLogger@Perf@Utils@Rdp@@QEAA@XZ; Rdp::Utils::Perf::CRdpGraphPerfMonLogger::CRdpGraphPerfMonLogger(void)
0x18003402c  nop
0x18003402d  mov     rbx, [rdi+0A8h]
0x180034034  mov     [rdi+0A8h], rax
0x18003403b  test    rbx, rbx
0x18003403e  jz      short loc_18003406C
0x180034040  lea     rcx, [rbx+48h]
0x180034044  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VCSharedFence@Graphics@Utils@Rdp@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(void)
0x180034049  lea     rcx, [rbx+38h]
0x18003404d  call    ??1?$list@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(void)
0x180034052  mov     rcx, [rbx+28h]; ProviderHandle
0x180034056  test    rcx, rcx
0x180034059  jz      short loc_180034061
0x18003405b  call    cs:__imp_PerfStopProvider
0x180034061  mov     rdx, rsi
0x180034064  mov     rcx, rbx; Block
0x180034067  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003406c  mov     rsi, [rdi+0A8h]
0x180034073  mov     r14d, [rdi+38h]
0x180034077  mov     edx, dword ptr [rsp+0F8h+var_B8]
0x18003407b  lea     rcx, [rsp+0F8h+var_40]
0x180034083  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@I@Z; std::to_wstring(uint)
0x180034088  mov     rbx, rax
0x18003408b  mov     rdx, [rsp+0F8h+var_90]
0x180034090  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18003409a  sub     rcx, rdx
0x18003409d  cmp     rcx, 1
0x1800340a1  jb      loc_1800341BC
0x1800340a7  lea     r9, [rsp+0F8h+var_A0]
0x1800340ac  cmp     [rsp+0F8h+var_88], 7
0x1800340b2  cmova   r9, qword ptr [rsp+0F8h+var_A0]
0x1800340b8  mov     [rsp+0F8h+var_C8], 1
0x1800340c1  lea     rax, asc_180093D78; " "
0x1800340c8  mov     [rsp+0F8h+var_D0], rax
0x1800340cd  mov     qword ptr [rsp+0F8h+var_D8], rdx
0x1800340d2  lea     rcx, [rsp+0F8h+var_80]
0x1800340d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800340dc  nop
0x1800340dd  mov     r8, rbx
0x1800340e0  lea     rdx, [rsp+0F8h+var_80]
0x1800340e5  lea     rcx, [rsp+0F8h+var_60]
0x1800340ed  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800340f2  nop
0x1800340f3  mov     [rsp+0F8h+var_D8], r14d
0x1800340f8  mov     r9, rax
0x1800340fb  lea     rdx, [rsp+0F8h+var_B8+8]
0x180034100  mov     rcx, rsi
0x180034103  call    ?CreateSession@?$CPerfMonLogger@$1?RDPPerfMonCountersGuid@@3U_GUID@@A@details@Perf@Utils@Rdp@@QEAA?AV?$shared_ptr@VCPerfMonSession@Perf@Utils@Rdp@@@std@@AEBU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@I@Z; Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::CreateSession(_GUID const &,std::wstring const &,uint)
0x180034108  lea     rcx, [rdi+0D0h]
0x18003410f  mov     rdx, rax
0x180034112  call    ??4?$shared_ptr@VCPerfMonSession@Perf@Utils@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=(std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession> &&)
0x180034117  mov     rbx, qword ptr [rsp+0F8h+var_B8+10h]
0x18003411c  test    rbx, rbx
0x18003411f  jz      short loc_180034158
0x180034121  or      edi, 0FFFFFFFFh
0x180034124  mov     eax, edi
0x180034126  lock xadd [rbx+8], eax
0x18003412b  add     eax, edi
0x18003412d  jnz     short loc_180034158
0x18003412f  mov     rax, [rbx]
0x180034132  mov     rcx, rbx
0x180034135  mov     rax, [rax]
0x180034138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003413d  mov     eax, edi
0x18003413f  lock xadd [rbx+0Ch], eax
0x180034144  add     eax, edi
0x180034146  jnz     short loc_180034158
0x180034148  mov     rax, [rbx]
0x18003414b  mov     rcx, rbx
0x18003414e  mov     rax, [rax+8]
0x180034152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034157  nop
0x180034158  lea     rcx, [rsp+0F8h+var_60]
0x180034160  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034165  nop
0x180034166  lea     rcx, [rsp+0F8h+var_80]
0x18003416b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034170  nop
0x180034171  lea     rcx, [rsp+0F8h+var_40]
0x180034179  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003417e  nop
0x18003417f  lea     rcx, [rsp+0F8h+var_A0]
0x180034184  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180034189  xor     eax, eax
0x18003418b  jmp     short loc_180034198
0x18003418d  mov     eax, 80004001h
0x180034192  jmp     short loc_180034198
0x180034194  mov     eax, dword ptr [rsp+0F8h+var_B8]
0x180034198  mov     rcx, [rsp+0F8h+var_20]
0x1800341a0  xor     rcx, rsp; StackCookie
0x1800341a3  call    __security_check_cookie
0x1800341a8  mov     rbx, [rsp+0F8h+arg_8]
0x1800341b0  add     rsp, 0E0h
0x1800341b7  pop     r14
0x1800341b9  pop     rdi
0x1800341ba  pop     rsi
0x1800341bb  retn
0x1800341bc  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
