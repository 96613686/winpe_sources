# NetworkPropertyMaps::GetNetworkDescription(_GUID const &,wchar_t * *)

- ea: `0x1800137f0`
- end: `0x180013ca3`
- name: `?GetNetworkDescription@NetworkPropertyMaps@@SAXAEBU_GUID@@PEAPEA_W@Z`
- size: `1203`
- prototype: `void __fastcall(const struct _GUID *Buf1, wchar_t **)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800e3a50`

## callees

- `0x180013748`
- `0x1800137f0`
- `0x180014aa0`
- `0x180014d80`
- `0x180014e20`
- `0x180014fb0`
- `0x180015608`
- `0x180015ae8`
- `0x180035dc4`
- `0x1800a88a0`
- `0x1800a9738`
- `0x1800aba19`
- `0x1800aba25`
- `0x1800baf04`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800138f2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800138f2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800139cf`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800139cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b08`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180013b08`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800139bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800139bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180013ac9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b87`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180013b87`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013aa6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013bdf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013aa6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013bdf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013af9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013af9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013a37`

## string_xrefs

- `0x18001395e`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x180013bf1`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x180013c09`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x180013c8e`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall NetworkPropertyMaps::GetNetworkDescription(const struct _GUID *Buf1, HKEY *a2)
{
  __m128i v4; // xmm6
  __int64 v5; // r8
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  BOOL v8; // ebx
  const char *v9; // r9
  HKEY v10; // r9
  LPCWSTR *v11; // r9
  LSTATUS v12; // eax
  unsigned int v13; // ecx
  HKEY v14; // r15
  LSTATUS Value; // eax
  unsigned int v16; // edi
  signed int v17; // ebx
  BYTE *v18; // rax
  wchar_t *v19; // rsi
  volatile signed __int32 *v20; // xmm6_8
  LSTATUS v21; // eax
  wchar_t *v22; // r9
  unsigned int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  int phkResultb; // [rsp+28h] [rbp-E0h]
  DWORD cbData[2]; // [rsp+50h] [rbp-B8h] BYREF
  DWORD Type[2]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+68h] [rbp-A0h] BYREF
  WCHAR Buffer[256]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v31[2064]; // [rsp+2B8h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B10h] [rbp+A08h]

  v4 = 0;
  v5 = (__int64)*(&xmmword_1801C8608 + 1);
  if ( *(&xmmword_1801C8608 + 1) )
  {
    v6 = *((_DWORD *)*(&xmmword_1801C8608 + 1) + 2);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v4 = *(__m128i *)&xmmword_1801C8608;
        break;
      }
    }
  }
  if ( !v4.m128i_i64[0] )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x12D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
      (const char *)0x15,
      phkResult);
  *a2 = 0;
  if ( !memcmp_0(Buf1, &g_unidentifiedGuid, 0x10u) || !memcmp_0(Buf1, &g_identifyingGuid, 0x10u) )
  {
    v8 = memcmp_0(Buf1, &g_unidentifiedGuid, 0x10u) != 0;
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( !LoadStringW(g_moduleHandle, v8 + 204, Buffer, 256) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x51A,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v9);
    wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
      &hKey,
      Buffer);
    v10 = hKey;
    *a2 = hKey;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, v10);
    goto LABEL_32;
  }
  memset_0(v31, 0, 0x802u);
  if ( (unsigned int)GetPolicyData(Buf1, 2u, v31) == 1 )
  {
    memset_0(sz, 0, 0x4Eu);
    StringFromGUID2(Buf1, sz, 39);
    EnterCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 784));
    hKey = 0;
    v11 = &qword_1801C7140;
    if ( (unsigned __int64)qword_1801C7158 > 7 )
      v11 = (LPCWSTR *)qword_1801C7140;
    StringCchPrintfW(Buffer, 0x78u, L"%s\\%s", v11, sz);
    v12 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, Buffer, 0, 0x20019u, &hKey);
    v13 = v12;
    if ( v12 > 0 )
      v13 = (unsigned __int16)v12 | 0x80070000;
    if ( v13 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x577,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v13 != 0 ? (const char *)0x8000FFFFLL : 0,
        phkResulta);
    Type[0] = 0;
    v14 = hKey;
    *a2 = 0;
    cbData[0] = 200;
    Value = RegQueryValueExW(v14, L"Description", 0, Type, (LPBYTE)Buffer, cbData);
    v16 = Value;
    if ( Value > 0 )
      v16 = (unsigned __int16)Value | 0x80070000;
    v17 = 0;
    if ( v16 != -2147024662 )
      v17 = v16;
    if ( v17 )
      goto LABEL_27;
    v18 = (BYTE *)CoTaskMemAlloc(cbData[0]);
    v19 = (wchar_t *)v18;
    if ( !v18 )
    {
      v17 = -2147024882;
LABEL_27:
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x57A,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
          (const char *)(unsigned int)v17,
          phkResultb);
      if ( hKey )
        RegCloseKey(hKey);
      if ( v4.m128i_i64[0] != -784 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v4.m128i_i64[0] + 784));
      goto LABEL_32;
    }
    if ( v16 == -2147024662 )
    {
      v21 = RegQueryValueExW(v14, L"Description", 0, Type, v18, cbData);
      v17 = v21;
      if ( v21 > 0 )
        v17 = (unsigned __int16)v21 | 0x80070000;
      if ( v17 )
        goto LABEL_38;
    }
    else
    {
      memcpy_0(v18, Buffer, cbData[0]);
      v17 = 0;
    }
    *a2 = (HKEY)v19;
    v19 = 0;
LABEL_38:
    if ( v19 )
      CoTaskMemFree(v19);
    goto LABEL_27;
  }
  *(_QWORD *)Type = 0;
  wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
    Type,
    v31);
  v22 = *(wchar_t **)Type;
  *(_QWORD *)Type = 0;
  *a2 = (HKEY)v22;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids, v22);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(Type);
LABEL_32:
  v20 = (volatile signed __int32 *)_mm_srli_si128(v4, 8).m128i_u64[0];
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v20);
    }
  }
}

```

## disassembly

```asm
0x1800137f0  mov     rax, rsp
0x1800137f3  mov     [rax+18h], rbx
0x1800137f7  mov     [rax+20h], rsi
0x1800137fb  push    rbp
0x1800137fc  push    rdi
0x1800137fd  push    r12
0x1800137ff  push    r14
0x180013801  push    r15
0x180013803  lea     rbp, [rax-0A08h]
0x18001380a  sub     rsp, 0AE0h
0x180013811  movaps  xmmword ptr [rax-38h], xmm6
0x180013815  mov     rax, cs:__security_cookie
0x18001381c  xor     rax, rsp
0x18001381f  mov     [rbp+0A00h+var_40], rax
0x180013826  mov     r14, rdx
0x180013829  mov     rbx, rcx
0x18001382c  xorps   xmm6, xmm6
0x18001382f  movdqu  xmmword ptr [rsp+0B00h+lpcbData+8], xmm6
0x180013835  mov     r8, qword ptr cs:xmmword_1801C8608+8
0x18001383c  test    r8, r8
0x18001383f  jz      short loc_180013861
0x180013841  mov     eax, [r8+8]
0x180013845  test    eax, eax
0x180013847  jz      short loc_180013861
0x180013849  lea     ecx, [rax+1]
0x18001384c  lock cmpxchg [r8+8], ecx
0x180013852  jnz     short loc_180013845
0x180013854  movups  xmm6, cs:xmmword_1801C8608
0x18001385b  movdqu  xmmword ptr [rsp+0B00h+lpcbData+8], xmm6
0x180013861  movq    rdi, xmm6
0x180013866  test    rdi, rdi
0x180013869  jz      loc_180013951
0x18001386f  mov     qword ptr [rdx], 0
0x180013876  mov     esi, 10h
0x18001387b  mov     r8d, esi; Size
0x18001387e  lea     rdx, ?g_unidentifiedGuid@@3U_GUID@@A; Buf2
0x180013885  mov     rcx, rbx; Buf1
0x180013888  call    memcmp_0
0x18001388d  test    eax, eax
0x18001388f  jz      short loc_1800138AB
0x180013891  mov     r8d, esi; Size
0x180013894  lea     rdx, ?g_identifyingGuid@@3U_GUID@@A; Buf2
0x18001389b  mov     rcx, rbx; Buf1
0x18001389e  call    memcmp_0
0x1800138a3  test    eax, eax
0x1800138a5  jnz     loc_180013970
0x1800138ab  mov     r8, rsi; Size
0x1800138ae  lea     rdx, ?g_unidentifiedGuid@@3U_GUID@@A; Buf2
0x1800138b5  mov     rcx, rbx; Buf1
0x1800138b8  call    memcmp_0
0x1800138bd  neg     eax
0x1800138bf  sbb     ebx, ebx
0x1800138c1  neg     ebx
0x1800138c3  xor     edx, edx; Val
0x1800138c5  mov     r8d, 200h; Size
0x1800138cb  lea     rcx, [rbp+0A00h+Buffer]; void *
0x1800138cf  call    memset_0
0x1800138d4  mov     rdi, [rbp+0A08h]
0x1800138db  mov     r9d, 100h; cchBufferMax
0x1800138e1  lea     r8, [rbp+0A00h+Buffer]; lpBuffer
0x1800138e5  lea     edx, [rbx+0CCh]; uID
0x1800138eb  mov     rcx, cs:?g_moduleHandle@@3PEAUHINSTANCE__@@EA; hInstance
0x1800138f2  call    cs:__imp_LoadStringW
0x1800138f8  test    eax, eax
0x1800138fa  jz      loc_180013C8E
0x180013900  lea     rdx, [rbp+0A00h+Buffer]
0x180013904  lea     rcx, [rsp+0B00h+hKey]
0x180013909  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x18001390e  mov     r9, [rsp+0B00h+hKey]
0x180013913  mov     [r14], r9
0x180013916  lea     rax, WPP_GLOBAL_Control
0x18001391d  mov     rcx, cs:WPP_GLOBAL_Control
0x180013924  cmp     rcx, rax
0x180013927  jz      loc_180013B0F
0x18001392d  test    byte ptr [rcx+1Ch], 8
0x180013931  jz      loc_180013B0F
0x180013937  mov     edx, 16h
0x18001393c  lea     r8, WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids
0x180013943  mov     rcx, [rcx+10h]
0x180013947  call    WPP_SF_S
0x18001394c  jmp     loc_180013B0F
0x180013951  mov     rcx, [rbp+0A08h]; this
0x180013958  mov     r9d, 15h; char *
0x18001395e  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x180013965  mov     edx, 12Dh; void *
0x18001396a  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180013970  xor     edx, edx; Val
0x180013972  mov     r8d, 802h; Size
0x180013978  lea     rcx, [rbp+0A00h+var_850]; void *
0x18001397f  call    memset_0
0x180013984  lea     r8, [rbp+0A00h+var_850]
0x18001398b  mov     edx, 2; unsigned int
0x180013990  mov     rcx, rbx; Buf1
0x180013993  call    ?GetPolicyData@@YAJPEBU_GUID@@KZZ; GetPolicyData(_GUID const *,ulong,...)
0x180013998  cmp     eax, 1
0x18001399b  jnz     loc_180013C26
0x1800139a1  xor     edx, edx; Val
0x1800139a3  lea     r8d, [rax+4Dh]; Size
0x1800139a7  lea     rcx, [rsp+0B00h+sz]; void *
0x1800139ac  call    memset_0
0x1800139b1  mov     r8d, 27h ; '''; cchMax
0x1800139b7  lea     rdx, [rsp+0B00h+sz]; lpsz
0x1800139bc  mov     rcx, rbx; rguid
0x1800139bf  call    cs:__imp_StringFromGUID2
0x1800139c5  lea     r12, [rdi+310h]
0x1800139cc  mov     rcx, r12; lpCriticalSection
0x1800139cf  call    cs:__imp_EnterCriticalSection
0x1800139d5  mov     qword ptr [rsp+0B00h+var_AC0], r12
0x1800139da  mov     [rsp+0B00h+hKey], 0
0x1800139e3  lea     r9, qword_1801C7140
0x1800139ea  cmp     cs:qword_1801C7158, 7
0x1800139f2  cmova   r9, cs:qword_1801C7140
0x1800139fa  lea     rax, [rsp+0B00h+sz]
0x1800139ff  mov     [rsp+0B00h+phkResult], rax
0x180013a04  lea     r8, aSS; "%s\\%s"
0x180013a0b  mov     edx, 78h ; 'x'; unsigned __int64
0x180013a10  lea     rcx, [rbp+0A00h+Buffer]; wchar_t *
0x180013a14  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180013a19  lea     rax, [rsp+0B00h+hKey]
0x180013a1e  mov     [rsp+0B00h+phkResult], rax; int
0x180013a23  mov     r9d, 20019h; samDesired
0x180013a29  xor     r8d, r8d; ulOptions
0x180013a2c  lea     rdx, [rbp+0A00h+Buffer]; lpSubKey
0x180013a30  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013a37  call    cs:__imp_RegOpenKeyExW
0x180013a3d  mov     ecx, eax
0x180013a3f  mov     ebx, 80070000h
0x180013a44  test    eax, eax
0x180013a46  jg      loc_180013BB4
0x180013a4c  mov     eax, ecx
0x180013a4e  neg     eax
0x180013a50  sbb     r9d, r9d
0x180013a53  and     r9d, 8000FFFFh; char *
0x180013a5a  mov     rax, [rbp+0A08h]
0x180013a61  test    ecx, ecx
0x180013a63  jnz     loc_180013BF1
0x180013a69  mov     [rsp+0B00h+Type], ecx
0x180013a6d  mov     r15, [rsp+0B00h+hKey]
0x180013a72  mov     qword ptr [r14], 0
0x180013a79  mov     [rsp+0B00h+cbData], 0C8h
0x180013a81  lea     rax, [rsp+0B00h+cbData]
0x180013a86  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x180013a8b  lea     rax, [rbp+0A00h+Buffer]
0x180013a8f  mov     [rsp+0B00h+phkResult], rax; int
0x180013a94  lea     r9, [rsp+0B00h+Type]; lpType
0x180013a99  xor     r8d, r8d; lpReserved
0x180013a9c  lea     rdx, aDescription; "Description"
0x180013aa3  mov     rcx, r15; hKey
0x180013aa6  call    cs:__imp_RegQueryValueExW
0x180013aac  mov     edi, eax
0x180013aae  test    eax, eax
0x180013ab0  jg      loc_180013BAA
0x180013ab6  xor     ebx, ebx
0x180013ab8  cmp     edi, 800700EAh
0x180013abe  cmovnz  ebx, edi
0x180013ac1  test    ebx, ebx
0x180013ac3  jnz     short loc_180013AE0
0x180013ac5  mov     ecx, [rsp+0B00h+cbData]; cb
0x180013ac9  call    cs:__imp_CoTaskMemAlloc
0x180013acf  mov     rsi, rax
0x180013ad2  test    rax, rax
0x180013ad5  jnz     loc_180013B5B
0x180013adb  mov     ebx, 8007000Eh
0x180013ae0  mov     rcx, [rbp+0A08h]; this
0x180013ae7  test    ebx, ebx
0x180013ae9  js      loc_180013C06
0x180013aef  mov     rcx, [rsp+0B00h+hKey]; hKey
0x180013af4  test    rcx, rcx
0x180013af7  jz      short loc_180013B00
0x180013af9  call    cs:__imp_RegCloseKey
0x180013aff  nop
0x180013b00  test    r12, r12
0x180013b03  jz      short loc_180013B0F
0x180013b05  mov     rcx, r12; lpCriticalSection
0x180013b08  call    cs:__imp_LeaveCriticalSection
0x180013b0e  nop
0x180013b0f  psrldq  xmm6, 8
0x180013b14  movq    rbx, xmm6
0x180013b19  test    rbx, rbx
0x180013b1c  jz      short loc_180013B2B
0x180013b1e  or      eax, 0FFFFFFFFh
0x180013b21  lock xadd [rbx+8], eax
0x180013b26  cmp     eax, 1
0x180013b29  jz      short loc_180013B92
0x180013b2b  mov     rcx, [rbp+0A00h+var_40]
0x180013b32  xor     rcx, rsp; StackCookie
0x180013b35  call    __security_check_cookie
0x180013b3a  lea     r11, [rsp+0B00h+var_20]
0x180013b42  mov     rbx, [r11+40h]
0x180013b46  mov     rsi, [r11+48h]
0x180013b4a  movaps  xmm6, xmmword ptr [r11-10h]
0x180013b4f  mov     rsp, r11
0x180013b52  pop     r15
0x180013b54  pop     r14
0x180013b56  pop     r12
0x180013b58  pop     rdi
0x180013b59  pop     rbp
0x180013b5a  retn
0x180013b5b  cmp     edi, 800700EAh
0x180013b61  jz      short loc_180013BBE
0x180013b63  mov     r8d, [rsp+0B00h+cbData]; Size
0x180013b68  lea     rdx, [rbp+0A00h+Buffer]; Src
0x180013b6c  mov     rcx, rsi; void *
0x180013b6f  call    memcpy_0
0x180013b74  xor     ebx, ebx
0x180013b76  mov     [r14], rsi
0x180013b79  xor     esi, esi
0x180013b7b  test    rsi, rsi
0x180013b7e  jz      loc_180013AE0
0x180013b84  mov     rcx, rsi; pv
0x180013b87  call    cs:__imp_CoTaskMemFree
0x180013b8d  jmp     loc_180013AE0
0x180013b92  mov     rax, [rbx]
0x180013b95  mov     rcx, rbx
0x180013b98  mov     rax, [rax]
0x180013b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ba0  mov     rcx, rbx; this
0x180013ba3  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180013ba8  jmp     short loc_180013B2B
0x180013baa  movzx   edi, ax
0x180013bad  or      edi, ebx
0x180013baf  jmp     loc_180013AB6
0x180013bb4  movzx   ecx, ax
0x180013bb7  or      ecx, ebx
0x180013bb9  jmp     loc_180013A4C
0x180013bbe  lea     rax, [rsp+0B00h+cbData]
0x180013bc3  mov     [rsp+0B00h+lpcbData], rax; lpcbData
0x180013bc8  mov     [rsp+0B00h+phkResult], rsi; lpData
0x180013bcd  lea     r9, [rsp+0B00h+Type]; lpType
0x180013bd2  xor     r8d, r8d; lpReserved
0x180013bd5  lea     rdx, aDescription; "Description"
0x180013bdc  mov     rcx, r15; hKey
0x180013bdf  call    cs:__imp_RegQueryValueExW
0x180013be5  mov     ebx, eax
0x180013be7  test    eax, eax
0x180013be9  jg      short loc_180013C1B
0x180013beb  test    ebx, ebx
0x180013bed  jz      short loc_180013B76
0x180013bef  jmp     short loc_180013B7B
0x180013bf1  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x180013bf8  mov     edx, 577h; void *
0x180013bfd  mov     rcx, rax; this
0x180013c00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013c06  mov     r9d, ebx; char *
0x180013c09  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x180013c10  mov     edx, 57Ah; void *
0x180013c15  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180013c1b  movzx   ebx, ax
0x180013c1e  or      ebx, 80070000h
0x180013c24  jmp     short loc_180013BEB
0x180013c26  mov     qword ptr [rsp+0B00h+Type], 0
0x180013c2f  lea     rdx, [rbp+0A00h+var_850]
0x180013c36  lea     rcx, [rsp+0B00h+Type]
0x180013c3b  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wchar_t const *,unsigned __int64)
0x180013c40  mov     r9, qword ptr [rsp+0B00h+Type]
0x180013c45  mov     qword ptr [rsp+0B00h+Type], 0
0x180013c4e  mov     [r14], r9
0x180013c51  lea     rax, WPP_GLOBAL_Control
0x180013c58  mov     rcx, cs:WPP_GLOBAL_Control
0x180013c5f  cmp     rcx, rax
0x180013c62  jz      short loc_180013C7F
0x180013c64  test    byte ptr [rcx+1Ch], 8
0x180013c68  jz      short loc_180013C7F
0x180013c6a  mov     edx, 17h
0x180013c6f  lea     r8, WPP_87eca99fb86d3f2974af9b60843a1c5f_Traceguids
0x180013c76  mov     rcx, [rcx+10h]
0x180013c7a  call    WPP_SF_S
0x180013c7f  lea     rcx, [rsp+0B00h+Type]
0x180013c84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180013c89  jmp     loc_180013B0F
0x180013c8e  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x180013c95  mov     edx, 51Ah; void *
0x180013c9a  mov     rcx, rdi; this
0x180013c9d  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
