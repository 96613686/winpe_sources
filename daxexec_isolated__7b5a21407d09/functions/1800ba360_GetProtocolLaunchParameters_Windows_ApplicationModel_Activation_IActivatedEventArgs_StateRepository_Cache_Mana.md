# GetProtocolLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800ba360`
- end: `0x1800ba872`
- name: `?GetProtocolLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1298`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b8250`

## callees

- `0x180004f70`
- `0x18000e074`
- `0x18000ff24`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x1800136dc`
- `0x1800b3980`
- `0x1800b5828`
- `0x1800b738c`
- `0x1800b7d2c`
- `0x1800ba360`
- `0x1800bba18`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba5ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba404`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba49e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba5ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba605`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba737`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ba74d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ba440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ba4da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ba440`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800ba4da`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba725`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba5dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba70a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ba725`

## string_xrefs

- `0x1800ba6aa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Protocol.hpp`
- `0x1800ba7bf`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba7d4`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba7e9`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba7fe`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba813`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba828`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba84b`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800ba860`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
bool __fastcall GetProtocolLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  _QWORD *v13; // rsi
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, HSTRING *); // rbx
  int v16; // eax
  PCWSTR v17; // rax
  const unsigned __int16 *v18; // rbx
  char *v19; // r8
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  unsigned int v26; // eax
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+40h] [rbp-C0h]
  UINT32 length; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  HSTRING v31; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v37; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v30 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24,
         &v30);
  if ( v7 != -2147467262 )
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x302,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v7,
        v27);
    v33 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL))(v30, &v33);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x305,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v8,
        v27);
    string = 0;
    v9 = v33;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 136LL);
    WindowsDeleteString(0);
    string = 0;
    v11 = v10(v9, &string);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x308,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v11,
        v27);
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v36, StringRawBuffer, length);
    v13 = (_QWORD *)((char *)a4 + 328);
    std::wstring::operator=((char *)a4 + 328, &v36);
    std::wstring::~wstring(&v36);
    v31 = 0;
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 128LL);
    WindowsDeleteString(0);
    v31 = 0;
    v16 = v15(v14, &v31);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30C,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v16,
        v27);
    length = 0;
    v17 = WindowsGetStringRawBuffer(v31, &length);
    v36 = 0;
    v37 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v36, v17, length);
    std::wstring::operator=((char *)a4 + 360, &v36);
    std::wstring::~wstring(&v36);
    LOBYTE(v28) = 0;
    v34 = 0;
    v35 = 0;
    if ( *((_QWORD *)a4 + 44) > 7u )
      v13 = (_QWORD *)*v13;
    v18 = (const unsigned __int16 *)((char *)a4 + 64);
    if ( *((_QWORD *)a4 + 11) <= 7u )
      v19 = (char *)a4 + 64;
    else
      v19 = *(char **)v18;
    v20 = StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(a2, a3, v19, v13);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x313,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v20,
        3);
    if ( *((_QWORD *)a4 + 11) > 7u )
      v18 = *(const unsigned __int16 **)v18;
    if ( !IsRuntimeBehaviorUniversal(a2, a3, v18) )
    {
      v26 = wil::verify_hresult(2147943568LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x320,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)v26,
        3);
    }
    v21 = *((_QWORD *)&v35 + 1);
    *((_QWORD *)&v35 + 1) = 0;
    if ( v21 )
      SRCache_Free();
    v22 = v35;
    *(_QWORD *)&v35 = 0;
    if ( v22 )
      SRCache_Free();
    WindowsDeleteString(v31);
    v31 = 0;
    WindowsDeleteString(string);
    string = 0;
    v23 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
  }
  v24 = v30;
  if ( v30 )
  {
    v30 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  }
  return 0;
}

```

## disassembly

```asm
0x1800ba360  push    rbp
0x1800ba362  push    rbx
0x1800ba363  push    rsi
0x1800ba364  push    rdi
0x1800ba365  push    r12
0x1800ba367  push    r13
0x1800ba369  push    r14
0x1800ba36b  push    r15
0x1800ba36d  lea     rbp, [rsp-18h]
0x1800ba372  sub     rsp, 118h
0x1800ba379  mov     rax, cs:__security_cookie
0x1800ba380  xor     rax, rsp
0x1800ba383  mov     [rbp+50h+var_50], rax
0x1800ba387  mov     r15, r9
0x1800ba38a  mov     r12, r8
0x1800ba38d  mov     r14, rdx
0x1800ba390  xor     r13d, r13d
0x1800ba393  mov     [rsp+150h+var_108], r13
0x1800ba398  mov     rax, [rcx]
0x1800ba39b  lea     r8, [rsp+150h+var_108]
0x1800ba3a0  lea     rdx, _GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24
0x1800ba3a7  mov     rax, [rax]
0x1800ba3aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3af  cmp     eax, 80004002h
0x1800ba3b4  jnz     short loc_1800BA3BB
0x1800ba3b6  jmp     loc_1800BA632
0x1800ba3bb  mov     rcx, [rbp+58h]; this
0x1800ba3bf  test    eax, eax
0x1800ba3c1  js      loc_1800BA7D1
0x1800ba3c7  mov     [rsp+150h+var_F0], r13
0x1800ba3cc  mov     rcx, [rsp+150h+var_108]
0x1800ba3d1  mov     rax, [rcx]
0x1800ba3d4  lea     rdx, [rsp+150h+var_F0]
0x1800ba3d9  mov     rax, [rax+30h]
0x1800ba3dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba3e2  mov     rcx, [rbp+58h]; this
0x1800ba3e6  test    eax, eax
0x1800ba3e8  js      loc_1800BA7E6
0x1800ba3ee  mov     [rsp+150h+string], r13
0x1800ba3f3  mov     rdi, [rsp+150h+var_F0]
0x1800ba3f8  mov     rax, [rdi]
0x1800ba3fb  mov     rbx, [rax+88h]
0x1800ba402  xor     ecx, ecx; string
0x1800ba404  call    cs:__imp_WindowsDeleteString
0x1800ba40b  nop     dword ptr [rax+rax+00h]
0x1800ba410  mov     [rsp+150h+string], r13
0x1800ba415  lea     rdx, [rsp+150h+string]
0x1800ba41a  mov     rcx, rdi
0x1800ba41d  mov     rax, rbx
0x1800ba420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba425  mov     rcx, [rbp+58h]; this
0x1800ba429  test    eax, eax
0x1800ba42b  js      loc_1800BA7FB
0x1800ba431  mov     [rsp+150h+length], r13d
0x1800ba436  lea     rdx, [rsp+150h+length]; length
0x1800ba43b  mov     rcx, [rsp+150h+string]; string
0x1800ba440  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ba447  nop     dword ptr [rax+rax+00h]
0x1800ba44c  xorps   xmm0, xmm0
0x1800ba44f  movups  [rbp+50h+var_70], xmm0
0x1800ba453  xorps   xmm1, xmm1
0x1800ba456  movdqu  [rbp+50h+var_60], xmm1
0x1800ba45b  mov     r8d, [rsp+150h+length]
0x1800ba460  mov     rdx, rax
0x1800ba463  lea     rcx, [rbp+50h+var_70]
0x1800ba467  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800ba46c  lea     rsi, [r15+148h]
0x1800ba473  lea     rdx, [rbp+50h+var_70]
0x1800ba477  mov     rcx, rsi
0x1800ba47a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800ba47f  lea     rcx, [rbp+50h+var_70]; void *
0x1800ba483  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ba488  mov     [rsp+150h+var_100], r13
0x1800ba48d  mov     rdi, [rsp+150h+var_F0]
0x1800ba492  mov     rax, [rdi]
0x1800ba495  mov     rbx, [rax+80h]
0x1800ba49c  xor     ecx, ecx; string
0x1800ba49e  call    cs:__imp_WindowsDeleteString
0x1800ba4a5  nop     dword ptr [rax+rax+00h]
0x1800ba4aa  mov     [rsp+150h+var_100], r13
0x1800ba4af  lea     rdx, [rsp+150h+var_100]
0x1800ba4b4  mov     rcx, rdi
0x1800ba4b7  mov     rax, rbx
0x1800ba4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba4bf  mov     rcx, [rbp+58h]; this
0x1800ba4c3  test    eax, eax
0x1800ba4c5  js      loc_1800BA810
0x1800ba4cb  mov     [rsp+150h+length], r13d
0x1800ba4d0  lea     rdx, [rsp+150h+length]; length
0x1800ba4d5  mov     rcx, [rsp+150h+var_100]; string
0x1800ba4da  call    cs:__imp_WindowsGetStringRawBuffer
0x1800ba4e1  nop     dword ptr [rax+rax+00h]
0x1800ba4e6  xorps   xmm0, xmm0
0x1800ba4e9  movups  [rbp+50h+var_70], xmm0
0x1800ba4ed  xorps   xmm1, xmm1
0x1800ba4f0  movdqu  [rbp+50h+var_60], xmm1
0x1800ba4f5  mov     r8d, [rsp+150h+length]
0x1800ba4fa  mov     rdx, rax
0x1800ba4fd  lea     rcx, [rbp+50h+var_70]
0x1800ba501  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800ba506  lea     rcx, [r15+168h]
0x1800ba50d  lea     rdx, [rbp+50h+var_70]
0x1800ba511  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800ba516  lea     rcx, [rbp+50h+var_70]; void *
0x1800ba51a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ba51f  mov     byte ptr [rsp+150h+var_110], r13b
0x1800ba524  xorps   xmm0, xmm0
0x1800ba527  movdqu  [rsp+150h+var_E8], xmm0
0x1800ba52d  xorps   xmm1, xmm1
0x1800ba530  movdqu  [rsp+150h+var_D8], xmm1
0x1800ba536  cmp     qword ptr [rsi+18h], 7
0x1800ba53b  jbe     short loc_1800BA540
0x1800ba53d  mov     rsi, [rsi]
0x1800ba540  lea     rbx, [r15+40h]
0x1800ba544  cmp     qword ptr [rbx+18h], 7
0x1800ba549  jbe     short loc_1800BA550
0x1800ba54b  mov     r8, [rbx]
0x1800ba54e  jmp     short loc_1800BA553
0x1800ba550  mov     r8, rbx
0x1800ba553  lea     rax, [rsp+150h+var_110]
0x1800ba558  mov     [rsp+150h+var_120], rax
0x1800ba55d  lea     rax, [rsp+150h+var_E8]
0x1800ba562  mov     [rsp+150h+var_128], rax
0x1800ba567  mov     qword ptr [rsp+150h+var_130], 3; int
0x1800ba570  mov     r9, rsi
0x1800ba573  mov     rdx, r12
0x1800ba576  mov     rcx, r14
0x1800ba579  call    ?GetByUserAndApplicationUserModelIdAndName@Protocol_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBG2W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Protocol_NoThrow::GetByUserAndApplicationUserModelIdAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,ushort const *,StateRepository::Cache::Entity::Protocol_NoThrow::CacheFlags,StateRepository::Cache::Entity::Protocol_NoThrow &,bool &)
0x1800ba57e  mov     rcx, [rbp+58h]; this
0x1800ba582  test    eax, eax
0x1800ba584  js      loc_1800BA825
0x1800ba58a  cmp     byte ptr [rsp+150h+var_110], r13b
0x1800ba58f  jnz     loc_1800BA655
0x1800ba595  cmp     qword ptr [rbx+18h], 7
0x1800ba59a  jbe     short loc_1800BA59F
0x1800ba59c  mov     rbx, [rbx]
0x1800ba59f  mov     r8, rbx; unsigned __int16 *
0x1800ba5a2  mov     rdx, r12; __int64
0x1800ba5a5  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba5a8  call    ?IsRuntimeBehaviorUniversal@@YA_NAEAVManager_NoThrow@Cache@StateRepository@@_JPEBG@Z; IsRuntimeBehaviorUniversal(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800ba5ad  test    al, al
0x1800ba5af  jz      loc_1800BA83A
0x1800ba5b5  mov     rcx, qword ptr [rbp+50h+var_D8+8]
0x1800ba5b9  mov     qword ptr [rbp+50h+var_D8+8], r13
0x1800ba5bd  test    rcx, rcx
0x1800ba5c0  jz      short loc_1800BA5CE
0x1800ba5c2  call    cs:__imp_SRCache_Free
0x1800ba5c9  nop     dword ptr [rax+rax+00h]
0x1800ba5ce  mov     rcx, qword ptr [rsp+150h+var_D8]
0x1800ba5d3  mov     qword ptr [rsp+150h+var_D8], r13
0x1800ba5d8  test    rcx, rcx
0x1800ba5db  jz      short loc_1800BA5EA
0x1800ba5dd  call    cs:__imp_SRCache_Free
0x1800ba5e4  nop     dword ptr [rax+rax+00h]
0x1800ba5e9  nop
0x1800ba5ea  mov     rcx, [rsp+150h+var_100]; string
0x1800ba5ef  call    cs:__imp_WindowsDeleteString
0x1800ba5f6  nop     dword ptr [rax+rax+00h]
0x1800ba5fb  mov     [rsp+150h+var_100], r13
0x1800ba600  mov     rcx, [rsp+150h+string]; string
0x1800ba605  call    cs:__imp_WindowsDeleteString
0x1800ba60c  nop     dword ptr [rax+rax+00h]
0x1800ba611  mov     [rsp+150h+string], r13
0x1800ba616  mov     rcx, [rsp+150h+var_F0]
0x1800ba61b  test    rcx, rcx
0x1800ba61e  jz      short loc_1800BA632
0x1800ba620  mov     [rsp+150h+var_F0], r13
0x1800ba625  mov     rax, [rcx]
0x1800ba628  mov     rax, [rax+10h]
0x1800ba62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba631  nop
0x1800ba632  mov     rcx, [rsp+150h+var_108]
0x1800ba637  test    rcx, rcx
0x1800ba63a  jz      short loc_1800BA64E
0x1800ba63c  mov     [rsp+150h+var_108], r13
0x1800ba641  mov     rax, [rcx]
0x1800ba644  mov     rax, [rax+10h]
0x1800ba648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba64d  nop
0x1800ba64e  xor     al, al
0x1800ba650  jmp     loc_1800BA798
0x1800ba655  mov     byte ptr [rsp+150h+var_110], r13b
0x1800ba65a  xorps   xmm0, xmm0
0x1800ba65d  movdqa  [rbp+50h+var_C0], xmm0
0x1800ba662  mov     [rbp+50h+var_B0], r13
0x1800ba666  mov     [rbp+50h+var_A8], r13
0x1800ba66a  movdqa  [rbp+50h+var_A0], xmm0
0x1800ba66f  xorps   xmm1, xmm1
0x1800ba672  movdqa  [rbp+50h+var_90], xmm1
0x1800ba677  mov     [rbp+50h+var_80], r13
0x1800ba67b  mov     [rbp+50h+var_78], r13d
0x1800ba67f  lea     rax, [rsp+150h+var_110]
0x1800ba684  mov     qword ptr [rsp+150h+var_130], rax; int
0x1800ba689  lea     r9, [rbp+50h+var_C0]
0x1800ba68d  xor     r8d, r8d
0x1800ba690  mov     rdx, qword ptr [rsp+150h+var_E8+8]
0x1800ba695  mov     rcx, r14
0x1800ba698  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800ba69d  mov     ebx, eax
0x1800ba69f  test    eax, eax
0x1800ba6a1  jns     short loc_1800BA6BD
0x1800ba6a3  mov     rcx, [rbp+58h]; this
0x1800ba6a7  mov     r9d, eax; char *
0x1800ba6aa  lea     r8, aOnecorePrivate_10; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ba6b1  mov     edx, 2E0h; void *
0x1800ba6b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ba6bb  jmp     short loc_1800BA6C0
0x1800ba6bd  mov     ebx, r13d
0x1800ba6c0  mov     rcx, [rbp+58h]; this
0x1800ba6c4  test    ebx, ebx
0x1800ba6c6  js      loc_1800BA85D
0x1800ba6cc  cmp     byte ptr [rsp+150h+var_110], r13b
0x1800ba6d1  setz    al
0x1800ba6d4  mov     rcx, [rbp+58h]; this
0x1800ba6d8  test    al, al
0x1800ba6da  jnz     loc_1800BA7B9
0x1800ba6e0  mov     r9, r15; struct ActivationProperties *
0x1800ba6e3  mov     r8, r12; __int64
0x1800ba6e6  lea     rdx, [rbp+50h+var_C0]; struct StateRepository::Cache::Entity::ApplicationExtension_NoThrow *
0x1800ba6ea  mov     rcx, r14; struct StateRepository::Cache::Manager_NoThrow *
0x1800ba6ed  call    ?GetExecutableInformationForExtension@@YAXAEAVManager_NoThrow@Cache@StateRepository@@AEAVApplicationExtension_NoThrow@Entity@23@_JAEAUActivationProperties@@@Z; GetExecutableInformationForExtension(StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,__int64,ActivationProperties &)
0x1800ba6f2  nop
0x1800ba6f3  lea     rcx, [rbp+50h+var_C0]; this
0x1800ba6f7  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800ba6fc  nop
0x1800ba6fd  mov     rcx, qword ptr [rbp+50h+var_D8+8]
0x1800ba701  mov     qword ptr [rbp+50h+var_D8+8], r13
0x1800ba705  test    rcx, rcx
0x1800ba708  jz      short loc_1800BA716
0x1800ba70a  call    cs:__imp_SRCache_Free
0x1800ba711  nop     dword ptr [rax+rax+00h]
0x1800ba716  mov     rcx, qword ptr [rsp+150h+var_D8]
0x1800ba71b  mov     qword ptr [rsp+150h+var_D8], r13
0x1800ba720  test    rcx, rcx
0x1800ba723  jz      short loc_1800BA732
0x1800ba725  call    cs:__imp_SRCache_Free
0x1800ba72c  nop     dword ptr [rax+rax+00h]
0x1800ba731  nop
0x1800ba732  mov     rcx, [rsp+150h+var_100]; string
0x1800ba737  call    cs:__imp_WindowsDeleteString
0x1800ba73e  nop     dword ptr [rax+rax+00h]
0x1800ba743  mov     [rsp+150h+var_100], r13
0x1800ba748  mov     rcx, [rsp+150h+string]; string
0x1800ba74d  call    cs:__imp_WindowsDeleteString
0x1800ba754  nop     dword ptr [rax+rax+00h]
0x1800ba759  mov     [rsp+150h+string], r13
0x1800ba75e  mov     rcx, [rsp+150h+var_F0]
0x1800ba763  test    rcx, rcx
0x1800ba766  jz      short loc_1800BA77A
0x1800ba768  mov     [rsp+150h+var_F0], r13
0x1800ba76d  mov     rax, [rcx]
0x1800ba770  mov     rax, [rax+10h]
0x1800ba774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba779  nop
0x1800ba77a  mov     rcx, [rsp+150h+var_108]
0x1800ba77f  test    rcx, rcx
0x1800ba782  jz      short loc_1800BA796
0x1800ba784  mov     [rsp+150h+var_108], r13
0x1800ba789  mov     rax, [rcx]
0x1800ba78c  mov     rax, [rax+10h]
0x1800ba790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ba795  nop
0x1800ba796  mov     al, 1
0x1800ba798  mov     rcx, [rbp+50h+var_50]
0x1800ba79c  xor     rcx, rsp; StackCookie
0x1800ba79f  call    __security_check_cookie
0x1800ba7a4  add     rsp, 118h
0x1800ba7ab  pop     r15
0x1800ba7ad  pop     r14
0x1800ba7af  pop     r13
0x1800ba7b1  pop     r12
0x1800ba7b3  pop     rdi
0x1800ba7b4  pop     rsi
0x1800ba7b5  pop     rbx
0x1800ba7b6  pop     rbp
0x1800ba7b7  retn
0x1800ba7b9  mov     r9d, 80070490h; char *
0x1800ba7bf  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba7c6  mov     edx, 327h; void *
0x1800ba7cb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba7d1  mov     r9d, eax; char *
0x1800ba7d4  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba7db  mov     edx, 302h; void *
0x1800ba7e0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba7e6  mov     r9d, eax; char *
0x1800ba7e9  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba7f0  mov     edx, 305h; void *
0x1800ba7f5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba7fb  mov     r9d, eax; char *
0x1800ba7fe  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba805  mov     edx, 308h; void *
0x1800ba80a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba810  mov     r9d, eax; char *
0x1800ba813  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba81a  mov     edx, 30Ch; void *
0x1800ba81f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ba825  mov     r9d, eax; char *
0x1800ba828  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800ba82f  mov     edx, 313h; void *
0x1800ba834  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
