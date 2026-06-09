# HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry(wil::com_ptr_t<HNSObject,wil::err_exception_policy>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180181144`
- end: `0x1801815ea`
- name: `?WriteDevicePropertiesToRegistry@VmNicPolicy@Policy@Service@HNS@@AEAAXV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1190`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180180f50`

## callees

- `0x18005f0c0`
- `0x180067c00`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x18007cbc8`
- `0x18007f05c`
- `0x180180c8c`
- `0x180181144`
- `0x18019cd40`
- `0x18019dbb4`
- `0x18019dcb8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801811f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1801811f8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801813fb`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1801813fb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180181547`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180181547`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180181445`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801814c8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180181513`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180181445`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x1801814c8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180181513`

## string_xrefs

- `0x180181599`: `onecore\vm\dv\net\hns\service\entity\policy\vmnicpolicy.cpp`
- `0x1801815ae`: `onecore\vm\dv\net\hns\service\entity\policy\vmnicpolicy.cpp`
- `0x1801815c3`: `onecore\vm\dv\net\hns\service\entity\policy\vmnicpolicy.cpp`
- `0x1801815d8`: `onecore\vm\dv\net\hns\service\entity\policy\vmnicpolicy.cpp`
- `0x180181181`: `HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry`
- `0x180181526`: `HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry`
- `0x180181505`: `Compartment`
- `0x180181393`: `System\CurrentControlSet\Services\Netvsc\InterfaceMap`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry(__int64 a1, HNSObject **a2, HKEY a3)
{
  HNSObject *v6; // rbx
  _QWORD *String; // rax
  int v8; // ebx
  HNSObject *v9; // rbx
  HNSObject *v10; // rbx
  __int64 v11; // rax
  HNSObject *v12; // rbx
  HNSObject *v13; // rbx
  __int64 v14; // rax
  const WCHAR *v15; // rdx
  unsigned int Key; // eax
  LPCVOID *v17; // rcx
  unsigned int v18; // eax
  LPCVOID *v19; // rcx
  unsigned int v20; // eax
  HKEY v21; // rax
  unsigned int v22; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-E0h]
  HKEY hKey[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+68h] [rbp-98h] BYREF
  __int128 v29; // [rsp+78h] [rbp-88h]
  LPCVOID lpData[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  unsigned __int64 v32; // [rsp+A0h] [rbp-60h]
  LPCVOID Src[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v34; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v35; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpSubKey[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  _BYTE v38[32]; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  hKey[1] = (HKEY)a2;
  hKey[2] = a3;
  HNSTraceProvider::TraceEnter("HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry", 0x28u);
  *(_OWORD *)lpData = 0;
  v31 = 0;
  v32 = 7;
  LOWORD(lpData[0]) = 0;
  v6 = *a2;
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"Type", 4u);
  String = (_QWORD *)HNSObject::GetString(v6, v38, &v28);
  if ( String[3] > 7u )
    String = (_QWORD *)*String;
  v8 = _o__wcsicmp(String, L"VmNic");
  std::wstring::~wstring(v38);
  std::wstring::~wstring(&v28);
  if ( !v8 )
  {
    v9 = *a2;
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"DeviceInstanceId", 0x10u);
    LODWORD(v9) = HNSObject::PropertyExists(v9, &v28);
    std::wstring::~wstring(&v28);
    if ( !(_DWORD)v9 )
    {
      v10 = *a2;
      v28 = 0;
      v29 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"DeviceInstanceId", 0x10u);
      v11 = HNSObject::GetString(v10, v38, &v28);
      std::wstring::operator=(a1 + 144, v11);
      std::wstring::~wstring(v38);
      std::wstring::~wstring(&v28);
    }
    v12 = *a2;
    v28 = 0;
    v29 = 0;
    std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"VfInstanceId", 0xCu);
    LODWORD(v12) = HNSObject::PropertyExists(v12, &v28);
    std::wstring::~wstring(&v28);
    if ( !(_DWORD)v12 )
    {
      v13 = *a2;
      v28 = 0;
      v29 = 0;
      std::wstring::_Construct<1,unsigned short const *>((char **)&v28, L"VfInstanceId", 0xCu);
      v14 = HNSObject::GetString(v13, v38, &v28);
      std::wstring::operator=(lpData, v14);
      std::wstring::~wstring(v38);
      std::wstring::~wstring(&v28);
    }
  }
  *(_OWORD *)lpSubKey = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpSubKey[0]) = 0;
  Vml::FormatString(lpSubKey, (wchar_t *)L"%ls\\%ls");
  hKey[0] = 0;
  v15 = (const WCHAR *)lpSubKey;
  if ( si128.m128i_i64[1] > 7uLL )
    v15 = lpSubKey[0];
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0, 1u, 0x20006u, 0, hKey, 0);
  if ( Key )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\policy\\vmnicpolicy.cpp",
      (const char *)Key,
      dwOptions);
  if ( v31 )
  {
    v17 = lpData;
    if ( v32 > 7 )
      v17 = (LPCVOID *)lpData[0];
    v18 = RegSetKeyValueW(hKey[0], 0, L"VfId", 1u, v17, 2 * v31 + 2);
    if ( v18 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\policy\\vmnicpolicy.cpp",
        (const char *)v18,
        dwOptionsa);
  }
  *(_OWORD *)Src = 0;
  v34 = 0;
  v35 = 7;
  LOWORD(Src[0]) = 0;
  Vml::FormatString(Src, (wchar_t *)L"VMBUS\\{%ls}\\%ls");
  v19 = Src;
  if ( v35 > 7 )
    v19 = (LPCVOID *)Src[0];
  v20 = RegSetKeyValueW(hKey[0], 0, L"PnpId", 1u, v19, 2 * v34 + 2);
  if ( v20 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\policy\\vmnicpolicy.cpp",
      (const char *)v20,
      dwOptionsb);
  if ( *((_QWORD *)a3 + 2) )
  {
    v21 = *((_QWORD *)a3 + 3) <= 7u ? a3 : *(HKEY *)a3;
    v22 = RegSetKeyValueW(hKey[0], 0, L"Compartment", 1u, v21, 2 * *((_DWORD *)a3 + 4) + 2);
    if ( v22 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\policy\\vmnicpolicy.cpp",
        (const char *)v22,
        dwOptionsc);
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Policy::VmNicPolicy::WriteDevicePropertiesToRegistry", 0x77u);
  std::wstring::~wstring(Src);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  std::wstring::~wstring(lpSubKey);
  std::wstring::~wstring(lpData);
  if ( *a2 )
    HNSObject::Release(*a2);
  std::wstring::~wstring(a3);
}

```

## disassembly

```asm
0x180181144  push    rbp
0x180181146  push    rbx
0x180181147  push    rsi
0x180181148  push    rdi
0x180181149  push    r12
0x18018114b  push    r13
0x18018114d  push    r14
0x18018114f  lea     rbp, [rsp-10h]
0x180181154  sub     rsp, 110h
0x18018115b  mov     rax, cs:__security_cookie
0x180181162  xor     rax, rsp
0x180181165  mov     [rbp+40h+var_38], rax
0x180181169  mov     rdi, r8
0x18018116c  mov     rsi, rdx
0x18018116f  mov     r14, rcx
0x180181172  mov     [rsp+140h+var_E8], rdx
0x180181177  mov     [rsp+140h+var_E0], r8
0x18018117c  mov     edx, 28h ; '('; unsigned int
0x180181181  lea     rcx, aHnsServicePoli_22; "HNS::Service::Policy::VmNicPolicy::Writ"...
0x180181188  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18018118d  xorps   xmm0, xmm0
0x180181190  movups  xmmword ptr [rbp+40h+lpData], xmm0
0x180181194  mov     [rbp+40h+var_A8], 0
0x18018119c  mov     r12d, 7
0x1801811a2  mov     [rbp+40h+var_A0], r12
0x1801811a6  xor     eax, eax
0x1801811a8  mov     word ptr [rbp+40h+lpData], ax
0x1801811ac  mov     rbx, [rsi]
0x1801811af  movups  [rsp+140h+var_D8], xmm0
0x1801811b4  xorps   xmm1, xmm1
0x1801811b7  movdqu  [rsp+140h+var_C8], xmm1
0x1801811bd  lea     r8d, [r12-3]
0x1801811c2  lea     rdx, aType; "Type"
0x1801811c9  lea     rcx, [rsp+140h+var_D8]
0x1801811ce  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801811d3  nop
0x1801811d4  lea     r8, [rsp+140h+var_D8]
0x1801811d9  lea     rdx, [rbp+40h+var_58]
0x1801811dd  mov     rcx, rbx
0x1801811e0  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x1801811e5  cmp     [rax+18h], r12
0x1801811e9  jbe     short loc_1801811EE
0x1801811eb  mov     rax, [rax]
0x1801811ee  lea     rdx, aVmnic_0; "VmNic"
0x1801811f5  mov     rcx, rax
0x1801811f8  call    cs:__imp__o__wcsicmp
0x1801811fe  mov     ebx, eax
0x180181200  lea     rcx, [rbp+40h+var_58]; void *
0x180181204  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181209  nop
0x18018120a  lea     rcx, [rsp+140h+var_D8]; void *
0x18018120f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181214  test    ebx, ebx
0x180181216  jnz     loc_180181369
0x18018121c  mov     rbx, [rsi]
0x18018121f  xorps   xmm0, xmm0
0x180181222  movups  [rsp+140h+var_D8], xmm0
0x180181227  xorps   xmm1, xmm1
0x18018122a  movdqu  [rsp+140h+var_C8], xmm1
0x180181230  mov     r13d, 10h
0x180181236  mov     r8d, r13d
0x180181239  lea     rdx, aDeviceinstance_0; "DeviceInstanceId"
0x180181240  lea     rcx, [rsp+140h+var_D8]
0x180181245  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18018124a  lea     rdx, [rsp+140h+var_D8]
0x18018124f  mov     rcx, rbx
0x180181252  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x180181257  mov     ebx, eax
0x180181259  lea     rcx, [rsp+140h+var_D8]; void *
0x18018125e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181263  test    ebx, ebx
0x180181265  jnz     short loc_1801812C4
0x180181267  mov     rbx, [rsi]
0x18018126a  xorps   xmm0, xmm0
0x18018126d  movups  [rsp+140h+var_D8], xmm0
0x180181272  xorps   xmm1, xmm1
0x180181275  movdqu  [rsp+140h+var_C8], xmm1
0x18018127b  mov     r8d, r13d
0x18018127e  lea     rdx, aDeviceinstance_0; "DeviceInstanceId"
0x180181285  lea     rcx, [rsp+140h+var_D8]
0x18018128a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18018128f  nop
0x180181290  lea     r8, [rsp+140h+var_D8]
0x180181295  lea     rdx, [rbp+40h+var_58]
0x180181299  mov     rcx, rbx
0x18018129c  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x1801812a1  lea     rcx, [r14+90h]
0x1801812a8  mov     rdx, rax
0x1801812ab  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801812b0  lea     rcx, [rbp+40h+var_58]; void *
0x1801812b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801812b9  nop
0x1801812ba  lea     rcx, [rsp+140h+var_D8]; void *
0x1801812bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801812c4  mov     rbx, [rsi]
0x1801812c7  xorps   xmm0, xmm0
0x1801812ca  movups  [rsp+140h+var_D8], xmm0
0x1801812cf  xorps   xmm1, xmm1
0x1801812d2  movdqu  [rsp+140h+var_C8], xmm1
0x1801812d8  mov     r13d, 0Ch
0x1801812de  mov     r8d, r13d
0x1801812e1  lea     rdx, aVfinstanceid; "VfInstanceId"
0x1801812e8  lea     rcx, [rsp+140h+var_D8]
0x1801812ed  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1801812f2  lea     rdx, [rsp+140h+var_D8]
0x1801812f7  mov     rcx, rbx
0x1801812fa  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801812ff  mov     ebx, eax
0x180181301  lea     rcx, [rsp+140h+var_D8]; void *
0x180181306  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018130b  test    ebx, ebx
0x18018130d  jnz     short loc_180181369
0x18018130f  mov     rbx, [rsi]
0x180181312  xorps   xmm0, xmm0
0x180181315  movups  [rsp+140h+var_D8], xmm0
0x18018131a  xorps   xmm1, xmm1
0x18018131d  movdqu  [rsp+140h+var_C8], xmm1
0x180181323  mov     r8d, r13d
0x180181326  lea     rdx, aVfinstanceid; "VfInstanceId"
0x18018132d  lea     rcx, [rsp+140h+var_D8]
0x180181332  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180181337  nop
0x180181338  lea     r8, [rsp+140h+var_D8]
0x18018133d  lea     rdx, [rbp+40h+var_58]
0x180181341  mov     rcx, rbx
0x180181344  call    ?GetString@HNSObject@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; HNSObject::GetString(std::wstring const &)
0x180181349  mov     rdx, rax
0x18018134c  lea     rcx, [rbp+40h+lpData]
0x180181350  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180181355  lea     rcx, [rbp+40h+var_58]; void *
0x180181359  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018135e  nop
0x18018135f  lea     rcx, [rsp+140h+var_D8]; void *
0x180181364  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181369  xorps   xmm0, xmm0
0x18018136c  movups  xmmword ptr [rbp+40h+lpSubKey], xmm0
0x180181370  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180181378  movdqu  [rbp+40h+var_68], xmm1
0x18018137d  xor     eax, eax
0x18018137f  mov     word ptr [rbp+40h+lpSubKey], ax
0x180181383  lea     r9, [r14+90h]
0x18018138a  cmp     [r9+18h], r12
0x18018138e  jbe     short loc_180181393
0x180181390  mov     r9, [r9]
0x180181393  lea     r8, aSystemCurrentc_11; "System\\CurrentControlSet\\Services\\Ne"...
0x18018139a  lea     rdx, aLsLs; "%ls\\%ls"
0x1801813a1  lea     rcx, [rbp+40h+lpSubKey]; Src
0x1801813a5  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1801813aa  nop
0x1801813ab  mov     [rsp+140h+hKey], 0
0x1801813b4  lea     rdx, [rbp+40h+lpSubKey]
0x1801813b8  cmp     qword ptr [rbp+40h+var_68+8], r12
0x1801813bc  cmova   rdx, [rbp+40h+lpSubKey]; lpSubKey
0x1801813c1  mov     [rsp+140h+lpdwDisposition], 0; lpdwDisposition
0x1801813ca  lea     rax, [rsp+140h+hKey]
0x1801813cf  mov     [rsp+140h+phkResult], rax; phkResult
0x1801813d4  mov     [rsp+140h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1801813dd  mov     [rsp+140h+samDesired], 20006h; samDesired
0x1801813e5  mov     ebx, 1
0x1801813ea  mov     [rsp+140h+dwOptions], ebx; unsigned int
0x1801813ee  xor     r9d, r9d; lpClass
0x1801813f1  xor     r8d, r8d; Reserved
0x1801813f4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801813fb  call    cs:__imp_RegCreateKeyExW
0x180181401  mov     rcx, [rbp+48h]; this
0x180181405  test    eax, eax
0x180181407  jnz     loc_1801815AB
0x18018140d  cmp     [rbp+40h+var_A8], 0
0x180181412  jz      short loc_180181457
0x180181414  mov     eax, dword ptr [rbp+40h+var_A8]
0x180181417  lea     rcx, [rbp+40h+lpData]
0x18018141b  cmp     [rbp+40h+var_A0], r12
0x18018141f  cmova   rcx, [rbp+40h+lpData]
0x180181424  lea     eax, ds:2[rax*2]
0x18018142b  mov     [rsp+140h+samDesired], eax; cbData
0x18018142f  mov     qword ptr [rsp+140h+dwOptions], rcx; unsigned int
0x180181434  mov     r9d, ebx; dwType
0x180181437  lea     r8, ValueName; "VfId"
0x18018143e  xor     edx, edx; lpSubKey
0x180181440  mov     rcx, [rsp+140h+hKey]; hKey
0x180181445  call    cs:__imp_RegSetKeyValueW
0x18018144b  mov     rcx, [rbp+48h]; this
0x18018144f  test    eax, eax
0x180181451  jnz     loc_1801815C0
0x180181457  xorps   xmm0, xmm0
0x18018145a  movups  xmmword ptr [rbp+40h+Src], xmm0
0x18018145e  mov     [rbp+40h+var_88], 0
0x180181466  mov     [rbp+40h+var_80], r12
0x18018146a  xor     eax, eax
0x18018146c  mov     word ptr [rbp+40h+Src], ax
0x180181470  lea     r9, [r14+90h]
0x180181477  cmp     [r9+18h], r12
0x18018147b  jbe     short loc_180181480
0x18018147d  mov     r9, [r9]
0x180181480  lea     r8, aF8615163Df3e46; "F8615163-DF3E-46c5-913F-F2D2F965ED0E"
0x180181487  lea     rdx, aVmbusLsLs; "VMBUS\\{%ls}\\%ls"
0x18018148e  lea     rcx, [rbp+40h+Src]; Src
0x180181492  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x180181497  mov     eax, dword ptr [rbp+40h+var_88]
0x18018149a  lea     eax, ds:2[rax*2]
0x1801814a1  lea     rcx, [rbp+40h+Src]
0x1801814a5  cmp     [rbp+40h+var_80], r12
0x1801814a9  cmova   rcx, [rbp+40h+Src]
0x1801814ae  mov     [rsp+140h+samDesired], eax; cbData
0x1801814b2  mov     qword ptr [rsp+140h+dwOptions], rcx; unsigned int
0x1801814b7  mov     r9d, ebx; dwType
0x1801814ba  lea     r8, aPnpid; "PnpId"
0x1801814c1  xor     edx, edx; lpSubKey
0x1801814c3  mov     rcx, [rsp+140h+hKey]; hKey
0x1801814c8  call    cs:__imp_RegSetKeyValueW
0x1801814ce  mov     rcx, [rbp+48h]; this
0x1801814d2  test    eax, eax
0x1801814d4  jnz     loc_1801815D5
0x1801814da  cmp     qword ptr [rdi+10h], 0
0x1801814df  jz      short loc_180181521
0x1801814e1  mov     eax, [rdi+10h]
0x1801814e4  lea     ecx, ds:2[rax*2]
0x1801814eb  cmp     [rdi+18h], r12
0x1801814ef  jbe     short loc_1801814F6
0x1801814f1  mov     rax, [rdi]
0x1801814f4  jmp     short loc_1801814F9
0x1801814f6  mov     rax, rdi
0x1801814f9  mov     [rsp+140h+samDesired], ecx; cbData
0x1801814fd  mov     qword ptr [rsp+140h+dwOptions], rax; unsigned int
0x180181502  mov     r9d, ebx; dwType
0x180181505  lea     r8, aCompartment; "Compartment"
0x18018150c  xor     edx, edx; lpSubKey
0x18018150e  mov     rcx, [rsp+140h+hKey]; hKey
0x180181513  call    cs:__imp_RegSetKeyValueW
0x180181519  mov     rcx, [rbp+48h]; this
0x18018151d  test    eax, eax
0x18018151f  jnz     short loc_180181596
0x180181521  mov     edx, 77h ; 'w'; unsigned int
0x180181526  lea     rcx, aHnsServicePoli_22; "HNS::Service::Policy::VmNicPolicy::Writ"...
0x18018152d  call    ?TraceSuccess@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceSuccess(char const *,uint)
0x180181532  nop
0x180181533  lea     rcx, [rbp+40h+Src]; void *
0x180181537  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18018153c  nop
0x18018153d  mov     rcx, [rsp+140h+hKey]; hKey
0x180181542  test    rcx, rcx
0x180181545  jz      short loc_18018154E
0x180181547  call    cs:__imp_RegCloseKey
0x18018154d  nop
0x18018154e  lea     rcx, [rbp+40h+lpSubKey]; void *
0x180181552  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181557  nop
0x180181558  lea     rcx, [rbp+40h+lpData]; void *
0x18018155c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181561  nop
0x180181562  mov     rcx, [rsi]; this
0x180181565  test    rcx, rcx
0x180181568  jz      short loc_180181570
0x18018156a  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x18018156f  nop
0x180181570  mov     rcx, rdi; void *
0x180181573  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180181578  mov     rcx, [rbp+40h+var_38]
0x18018157c  xor     rcx, rsp; StackCookie
0x18018157f  call    __security_check_cookie
0x180181584  add     rsp, 110h
0x18018158b  pop     r14
0x18018158d  pop     r13
0x18018158f  pop     r12
0x180181591  pop     rdi
0x180181592  pop     rsi
0x180181593  pop     rbx
0x180181594  pop     rbp
0x180181595  retn
0x180181596  mov     r9d, eax; char *
0x180181599  lea     r8, aOnecoreVmDvNet_122; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x1801815a0  mov     edx, 75h ; 'u'; void *
0x1801815a5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801815ab  mov     r9d, eax; char *
0x1801815ae  lea     r8, aOnecoreVmDvNet_122; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x1801815b5  mov     edx, 4Eh ; 'N'; void *
0x1801815ba  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801815c0  mov     r9d, eax; char *
0x1801815c3  lea     r8, aOnecoreVmDvNet_122; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x1801815ca  mov     edx, 59h ; 'Y'; void *
0x1801815cf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1801815d5  mov     r9d, eax; char *
0x1801815d8  lea     r8, aOnecoreVmDvNet_122; "onecore\\vm\\dv\\net\\hns\\service\\ent"...
0x1801815df  mov     edx, 6Ah ; 'j'; void *
0x1801815e4  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
