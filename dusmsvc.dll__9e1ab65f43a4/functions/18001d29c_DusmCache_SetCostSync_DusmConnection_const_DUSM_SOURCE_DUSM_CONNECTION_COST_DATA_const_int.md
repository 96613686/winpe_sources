# DusmCache::SetCostSync(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)

- ea: `0x18001d29c`
- end: `0x18001d51b`
- name: `?SetCostSync@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z`
- size: `639`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `4`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x18001b650`
- `0x18001ceac`
- `0x18001d1d0`
- `0x18001d910`

## callees

- `0x180003ae8`
- `0x18000ea78`
- `0x18000f214`
- `0x180012fcc`
- `0x180013444`
- `0x1800173fc`
- `0x18001742c`
- `0x18001a000`
- `0x18001b3f4`
- `0x18001b888`
- `0x18001b8cc`
- `0x18001b944`
- `0x18001cee0`
- `0x18001d29c`
- `0x18001d87c`
- `0x18001db50`
- `0x18002f44c`
- `0x1800359dc`
- `0x180038550`
- `0x18003b33c`

## string_xrefs

- `0x18001d4de`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d509`: `onecoreuap\net\dusm\lib\dusmcache.cpp`
- `0x18001d4f7`: `DusmCache::SetCostSync::source`
- `0x18001d4cc`: `DusmCache::SetCostSync::mediaType`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DusmCache::SetCostSync(
        __int64 a1,
        const struct DusmConnection *a2,
        unsigned int a3,
        __int64 *a4,
        unsigned int a5)
{
  DusmCache *v8; // r12
  unsigned int v9; // r15d
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rcx
  _DWORD *v14; // rdi
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // rdx
  const char *v18; // rax
  const char *v19; // r8
  const char *v20; // r9
  const wchar_t *v21; // r10
  const char *v22; // [rsp+30h] [rbp-D8h]
  __int64 v23; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  __int64 v27; // [rsp+78h] [rbp-90h] BYREF
  int v28; // [rsp+80h] [rbp-88h] BYREF
  __int128 v29; // [rsp+84h] [rbp-84h]
  int v30; // [rsp+94h] [rbp-74h]
  _BYTE v31[64]; // [rsp+98h] [rbp-70h] BYREF
  _BYTE v32[320]; // [rsp+D8h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+240h] [rbp+138h]
  __int64 v34; // [rsp+248h] [rbp+140h] BYREF

  v34 = a1;
  if ( a3 - 2 > 1 )
    wil::details::in1diag3::Throw_Win32Msg(
      retaddr,
      (void *)0x217,
      (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
      (const char *)0x57,
      (unsigned int)"DusmCache::SetCostSync::source",
      v22);
  v8 = DusmCache::s_pInstance;
  v9 = *((_DWORD *)a2 + 4);
  if ( v9 == 1 )
  {
    v10 = a5;
    DusmEthernet::SetCost(a2, a3, a4, a5);
  }
  else if ( *((_DWORD *)a2 + 4) == 2 )
  {
    v10 = a5;
    DusmWlan::SetCost((__int64)a2, a3, a4, a5 != 0);
  }
  else
  {
    if ( *((_DWORD *)a2 + 4) != 3 )
      wil::details::in1diag3::Throw_Win32Msg(
        retaddr,
        (void *)0x228,
        (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmcache.cpp",
        (const char *)0x57,
        (unsigned int)"DusmCache::SetCostSync::mediaType",
        v22);
    v10 = a5;
    DusmWwan::SetCost(a2, a3, a4, a5);
  }
  DusmCache::SetCostCache(v8, a2, a3, a4, v10, 1);
  DusmConnection::DusmConnection((DusmConnection *)v32, a2);
  std::function_void___cdecl_void__::function_void___cdecl_void____DusmCache::SetCostSync_::_2_::_lambda_1__0_(v31, v32);
  DusmAsync::SubmitNlaUpdateWork((__int64)v31);
  std::function<long (void)>::~function<long (void)>((__int64)v31, v11);
  DusmConnection::~DusmConnection((DusmConnection *)v32);
  if ( **(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v13, v12) + 8) <= 5u )
  {
    v14 = (_DWORD *)((char *)a2 + 48);
  }
  else
  {
    v34 = EnumToString(*((unsigned int *)a4 + 1));
    v23 = EnumToString(*(unsigned int *)a4);
    v24 = EnumToString(a3);
    v25 = DusmMediaTypeToSz(v9);
    v14 = (_DWORD *)((char *)a2 + 48);
    v26 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr((char *)a2 + 48);
    v27 = (__int64)a2 + 32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v15,
      (int)&byte_180056E85,
      v15,
      v16,
      &v27,
      (const WCHAR **)&v26,
      (const WCHAR **)&v25,
      (const wchar_t **)&v24,
      (const wchar_t **)&v23,
      (const wchar_t **)&v34);
  }
  std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v14);
  v28 = 1;
  v29 = *(_OWORD *)((char *)a2 + v17);
  v30 = DusmMediaToIfType(v9);
  EnumToString(*((unsigned int *)a4 + 1));
  EnumToString(*(unsigned int *)a4);
  v18 = (const char *)EnumToString(a3);
  NetworkingTriageScenario::GetConnected::ConnectionCostChangedEvent(
    (const struct NetworkingTriageScenario::GetConnected::RequiredFields *)&v28,
    v18,
    v19,
    v20,
    v21);
}

```

## disassembly

```asm
0x18001d29c  mov     rax, rsp
0x18001d29f  mov     [rax+10h], rbx
0x18001d2a3  mov     [rax+18h], rsi
0x18001d2a7  mov     [rax+8], rcx
0x18001d2ab  push    rbp
0x18001d2ac  push    rdi
0x18001d2ad  push    r12
0x18001d2af  push    r14
0x18001d2b1  push    r15
0x18001d2b3  lea     rbp, [rax-138h]
0x18001d2ba  sub     rsp, 210h
0x18001d2c1  mov     r14, r9
0x18001d2c4  mov     esi, r8d
0x18001d2c7  mov     rbx, rdx
0x18001d2ca  lea     eax, [r8-2]
0x18001d2ce  cmp     eax, 1
0x18001d2d1  ja      loc_18001D4F0
0x18001d2d7  mov     r12, cs:?s_pInstance@DusmCache@@0PEAV1@EA; DusmCache * DusmCache::s_pInstance
0x18001d2de  mov     r15d, [rdx+10h]
0x18001d2e2  mov     ecx, r15d
0x18001d2e5  sub     ecx, 1
0x18001d2e8  jz      short loc_18001D32B
0x18001d2ea  sub     ecx, 1
0x18001d2ed  jz      short loc_18001D310
0x18001d2ef  cmp     ecx, 1
0x18001d2f2  jnz     loc_18001D4C5
0x18001d2f8  mov     edi, [rbp+130h+arg_20]
0x18001d2fe  mov     r9d, edi
0x18001d301  mov     r8, r14
0x18001d304  mov     edx, esi
0x18001d306  mov     rcx, rbx
0x18001d309  call    ?SetCost@DusmWwan@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z; DusmWwan::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)
0x18001d30e  jmp     short loc_18001D341
0x18001d310  mov     edi, [rbp+130h+arg_20]
0x18001d316  test    edi, edi
0x18001d318  setnz   r9b
0x18001d31c  mov     r8, r14
0x18001d31f  mov     edx, esi
0x18001d321  mov     rcx, rbx
0x18001d324  call    ?SetCost@DusmWlan@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@_N@Z; DusmWlan::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,bool)
0x18001d329  jmp     short loc_18001D341
0x18001d32b  mov     edi, [rbp+130h+arg_20]
0x18001d331  mov     r9d, edi
0x18001d334  mov     r8, r14
0x18001d337  mov     edx, esi
0x18001d339  mov     rcx, rbx
0x18001d33c  call    ?SetCost@DusmEthernet@@SAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@H@Z; DusmEthernet::SetCost(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int)
0x18001d341  mov     dword ptr [rsp+230h+var_208], 1
0x18001d349  mov     dword ptr [rsp+230h+var_210], edi
0x18001d34d  mov     r9, r14
0x18001d350  mov     r8d, esi
0x18001d353  mov     rdx, rbx
0x18001d356  mov     rcx, r12
0x18001d359  call    ?SetCostCache@DusmCache@@AEAAXAEBVDusmConnection@@W4_DUSM_SOURCE@@AEBU_DUSM_CONNECTION_COST_DATA@@HH@Z; DusmCache::SetCostCache(DusmConnection const &,_DUSM_SOURCE,_DUSM_CONNECTION_COST_DATA const &,int,int)
0x18001d35e  mov     rdx, rbx; struct DusmConnection *
0x18001d361  lea     rcx, [rbp+130h+var_160]; this
0x18001d365  call    ??0DusmConnection@@QEAA@AEBV0@@Z; DusmConnection::DusmConnection(DusmConnection const &)
0x18001d36a  nop
0x18001d36b  lea     rdx, [rbp+130h+var_160]
0x18001d36f  lea     rcx, [rbp+130h+var_1A0]
0x18001d373  call    std__function_void___cdecl_void____function_void___cdecl_void____DusmCache__SetCostSync____2____lambda_1__0_
0x18001d378  lea     rcx, [rbp+130h+var_1A0]
0x18001d37c  call    ?SubmitNlaUpdateWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitNlaUpdateWork(std::function<void (void)> &&)
0x18001d381  lea     rcx, [rbp+130h+var_1A0]
0x18001d385  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18001d38a  nop
0x18001d38b  lea     rcx, [rbp+130h+var_160]; this
0x18001d38f  call    ??1DusmConnection@@QEAA@XZ; DusmConnection::~DusmConnection(void)
0x18001d394  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18001d399  mov     r8, [rax+8]
0x18001d39d  mov     eax, [r8]
0x18001d3a0  cmp     eax, 5
0x18001d3a3  jbe     loc_18001D448
0x18001d3a9  mov     ecx, [r14+4]
0x18001d3ad  call    ?EnumToString@@YAPEBDW4COST_SET_SOURCE@@@Z; EnumToString(COST_SET_SOURCE)
0x18001d3b2  mov     [rbp+130h+arg_0], rax
0x18001d3b9  mov     ecx, [r14]
0x18001d3bc  call    ?EnumToString@@YAPEBDW4_DUSM_CONNECTION_COST@@@Z; EnumToString(_DUSM_CONNECTION_COST)
0x18001d3c1  mov     [rsp+230h+var_1E0], rax
0x18001d3c6  mov     ecx, esi
0x18001d3c8  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001d3cd  mov     [rsp+230h+var_1D8], rax
0x18001d3d2  mov     ecx, r15d
0x18001d3d5  call    ?DusmMediaTypeToSz@@YAPEB_WW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaTypeToSz(_DUSM_MEDIA_TYPE)
0x18001d3da  mov     [rsp+230h+var_1D0], rax
0x18001d3df  lea     rdi, [rbx+30h]
0x18001d3e3  mov     rcx, rdi
0x18001d3e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d3eb  mov     [rsp+230h+var_1C8], rax
0x18001d3f0  lea     rax, [rbx+20h]
0x18001d3f4  mov     [rsp+230h+var_1C0], rax
0x18001d3f9  lea     rax, [rbp+130h+arg_0]
0x18001d400  mov     [rsp+230h+var_1E8], rax; __int64
0x18001d405  lea     rax, [rsp+230h+var_1E0]
0x18001d40a  mov     [rsp+230h+var_1F0], rax; __int64
0x18001d40f  lea     rax, [rsp+230h+var_1D8]
0x18001d414  mov     [rsp+230h+var_1F8], rax; __int64
0x18001d419  lea     rax, [rsp+230h+var_1D0]
0x18001d41e  mov     [rsp+230h+var_200], rax; __int64
0x18001d423  lea     rax, [rsp+230h+var_1C8]
0x18001d428  mov     [rsp+230h+var_208], rax; __int64
0x18001d42d  lea     rax, [rsp+230h+var_1C0]
0x18001d432  mov     [rsp+230h+var_210], rax; __int64
0x18001d437  lea     rdx, byte_180056E85; int
0x18001d43e  mov     rcx, r8; int
0x18001d441  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapSz@D@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapSz@D@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18001d446  jmp     short loc_18001D44C
0x18001d448  lea     rdi, [rbx+30h]
0x18001d44c  mov     edx, 20h ; ' '
0x18001d451  mov     rcx, rdi
0x18001d454  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001d459  mov     r10, rax
0x18001d45c  mov     [rsp+230h+var_1B8], 1
0x18001d464  movups  xmm0, xmmword ptr [rdx+rbx]
0x18001d468  movdqu  [rsp+230h+var_1B4], xmm0
0x18001d46e  mov     ecx, r15d
0x18001d471  call    ?DusmMediaToIfType@@YAIW4_DUSM_MEDIA_TYPE@@@Z; DusmMediaToIfType(_DUSM_MEDIA_TYPE)
0x18001d476  mov     [rbp+130h+var_1A4], eax
0x18001d479  mov     ecx, [r14+4]
0x18001d47d  call    ?EnumToString@@YAPEBDW4COST_SET_SOURCE@@@Z; EnumToString(COST_SET_SOURCE)
0x18001d482  mov     r9, rax
0x18001d485  mov     ecx, [r14]
0x18001d488  call    ?EnumToString@@YAPEBDW4_DUSM_CONNECTION_COST@@@Z; EnumToString(_DUSM_CONNECTION_COST)
0x18001d48d  mov     r8, rax
0x18001d490  mov     ecx, esi
0x18001d492  call    ?EnumToString@@YAPEBDW4_DUSM_SOURCE@@@Z; EnumToString(_DUSM_SOURCE)
0x18001d497  mov     rdx, rax; char *
0x18001d49a  mov     [rsp+230h+var_210], r10; wchar_t *
0x18001d49f  lea     rcx, [rsp+230h+var_1B8]; struct NetworkingTriageScenario::GetConnected::RequiredFields *
0x18001d4a4  call    ?ConnectionCostChangedEvent@GetConnected@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBD11PEB_W@Z; NetworkingTriageScenario::GetConnected::ConnectionCostChangedEvent(NetworkingTriageScenario::GetConnected::RequiredFields const &,char const *,char const *,char const *,wchar_t const *)
0x18001d4a9  lea     r11, [rsp+230h+var_20]
0x18001d4b1  mov     rbx, [r11+38h]
0x18001d4b5  mov     rsi, [r11+40h]
0x18001d4b9  mov     rsp, r11
0x18001d4bc  pop     r15
0x18001d4be  pop     r14
0x18001d4c0  pop     r12
0x18001d4c2  pop     rdi
0x18001d4c3  pop     rbp
0x18001d4c4  retn
0x18001d4c5  mov     rcx, [rbp+138h]; this
0x18001d4cc  lea     rax, aDusmcacheSetco_0; "DusmCache::SetCostSync::mediaType"
0x18001d4d3  mov     [rsp+230h+var_210], rax; unsigned int
0x18001d4d8  mov     r9d, 57h ; 'W'; char *
0x18001d4de  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d4e5  mov     edx, 228h; void *
0x18001d4ea  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18001d4f0  mov     rcx, [rbp+138h]; this
0x18001d4f7  lea     rax, aDusmcacheSetco; "DusmCache::SetCostSync::source"
0x18001d4fe  mov     [rsp+230h+var_210], rax; unsigned int
0x18001d503  mov     r9d, 57h ; 'W'; char *
0x18001d509  lea     r8, aOnecoreuapNetD_3; "onecoreuap\\net\\dusm\\lib\\dusmcache.c"...
0x18001d510  mov     edx, 217h; void *
0x18001d515  call    ?Throw_Win32Msg@in1diag3@details@wil@@YAXPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_Win32Msg(void *,uint,char const *,ulong,char const *,...)
```
