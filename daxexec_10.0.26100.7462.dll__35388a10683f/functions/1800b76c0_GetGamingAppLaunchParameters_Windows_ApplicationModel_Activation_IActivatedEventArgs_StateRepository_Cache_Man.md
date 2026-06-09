# GetGamingAppLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b76c0`
- end: `0x1800b7d62`
- name: `?GetGamingAppLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1698`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1800b6398`

## callees

- `0x1800053a0`
- `0x18000e234`
- `0x180010a84`
- `0x180011300`
- `0x180011820`
- `0x180011a64`
- `0x180038f68`
- `0x18003b244`
- `0x1800b16cc`
- `0x1800b17ac`
- `0x1800b2540`
- `0x1800b3b14`
- `0x1800b5004`
- `0x1800b5f44`
- `0x1800b76c0`
- `0x1800ba2d0`
- `0x1800baac0`
- `0x1800cc010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b780b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7763`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b780b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b7b79`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b77a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b77a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b7849`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7aba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7b47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7c2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7aba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7b47`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b7c2f`

## string_xrefs

- `0x1800b79fe`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b7a39`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b7a88`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b7c0f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b7954`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800b7c78`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7c8d`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7ca2`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7cb7`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7ccc`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7ce1`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7cf6`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7d0e`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7d23`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7d3b`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b7d50`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b792c`: `windows.appExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall GetGamingAppLaunchParameters(
        struct Windows::ApplicationModel::Activation::IActivatedEventArgs *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        struct ActivationProperties *a4)
{
  int v7; // eax
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rdi
  int v15; // eax
  PCWSTR v16; // rax
  _QWORD *v17; // r8
  int v18; // eax
  int v19; // [rsp+20h] [rbp-E0h]
  char v20; // [rsp+30h] [rbp-D0h]
  UINT32 length[2]; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v22; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING string; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26[2]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v27; // [rsp+E0h] [rbp-20h]
  __int64 v28; // [rsp+E8h] [rbp-18h]
  __int128 v29; // [rsp+F0h] [rbp-10h]
  __int128 v30; // [rsp+100h] [rbp+0h]
  __int128 v31; // [rsp+110h] [rbp+10h]
  __int128 v32; // [rsp+120h] [rbp+20h]
  __int128 v33; // [rsp+180h] [rbp+80h] BYREF
  __int128 v34; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v25 = 0;
  v7 = (**(__int64 (__fastcall ***)(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, GUID *, __int64 *))a1)(
         a1,
         &GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24,
         &v25);
  if ( v7 >= 0 )
  {
    v24 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, &v24);
    if ( v8 >= 0 )
    {
      string = 0;
      v9 = v24;
      v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 136LL);
      WindowsDeleteString(0);
      string = 0;
      v11 = v10(v9, &string);
      if ( v11 >= 0 )
      {
        length[0] = 0;
        StringRawBuffer = WindowsGetStringRawBuffer(string, length);
        v33 = 0;
        v34 = 0;
        std::wstring::_Construct<1,unsigned short const *>(&v33, StringRawBuffer, length[0]);
        std::wstring::operator=((char *)a4 + 328, &v33);
        std::wstring::~wstring(&v33);
        v22 = 0;
        v13 = v24;
        v14 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v24 + 128LL);
        WindowsDeleteString(0);
        v22 = 0;
        v15 = v14(v13, &v22);
        if ( v15 >= 0 )
        {
          length[0] = 0;
          v16 = WindowsGetStringRawBuffer(v22, length);
          v33 = 0;
          v34 = 0;
          std::wstring::_Construct<1,unsigned short const *>(&v33, v16, length[0]);
          std::wstring::operator=((char *)a4 + 360, &v33);
          std::wstring::~wstring(&v33);
          v20 = 0;
          *(_OWORD *)v26 = 0;
          v27 = 0;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          v31 = 0;
          v32 = 0;
          v17 = (_QWORD *)((char *)a4 + 64);
          if ( *((_QWORD *)a4 + 11) > 7u )
            v17 = (_QWORD *)*v17;
          v18 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(a2, a3, v17, 0);
          if ( v18 >= 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3B1,
              (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
              (const char *)0x80270254LL,
              (int)v26);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x3B0,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
            (const char *)(unsigned int)v18,
            (int)v26);
        }
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3AB,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
          (const char *)(unsigned int)v15,
          v19);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3A7,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
        (const char *)(unsigned int)v11,
        v19);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A4,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
      (const char *)(unsigned int)v8,
      v19);
  }
  wil::details::in1diag3::Throw_Hr(
    retaddr,
    (void *)0x3A1,
    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\aamextensions.cpp",
    (const char *)(unsigned int)v7,
    v19);
}

```

## disassembly

```asm
0x1800b76c0  push    rbp
0x1800b76c2  push    rbx
0x1800b76c3  push    rsi
0x1800b76c4  push    rdi
0x1800b76c5  push    r12
0x1800b76c7  push    r13
0x1800b76c9  push    r14
0x1800b76cb  push    r15
0x1800b76cd  lea     rbp, [rsp-0B8h]
0x1800b76d5  sub     rsp, 1B8h
0x1800b76dc  mov     rax, cs:__security_cookie
0x1800b76e3  xor     rax, rsp
0x1800b76e6  mov     [rbp+0F0h+var_50], rax
0x1800b76ed  mov     r13, r9
0x1800b76f0  mov     r12, r8
0x1800b76f3  mov     r15, rdx
0x1800b76f6  xor     esi, esi
0x1800b76f8  mov     [rsp+1F0h+var_198], rsi
0x1800b76fd  mov     rax, [rcx]
0x1800b7700  lea     r8, [rsp+1F0h+var_198]
0x1800b7705  lea     rdx, _GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24
0x1800b770c  mov     rax, [rax]
0x1800b770f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7714  mov     rcx, [rbp+0F8h]; this
0x1800b771b  test    eax, eax
0x1800b771d  js      loc_1800B7C9F
0x1800b7723  mov     [rsp+1F0h+var_1A0], rsi
0x1800b7728  mov     rcx, [rsp+1F0h+var_198]
0x1800b772d  mov     rax, [rcx]
0x1800b7730  lea     rdx, [rsp+1F0h+var_1A0]
0x1800b7735  mov     rax, [rax+30h]
0x1800b7739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b773e  mov     rcx, [rbp+0F8h]; this
0x1800b7745  test    eax, eax
0x1800b7747  js      loc_1800B7CB4
0x1800b774d  mov     [rsp+1F0h+string], rsi
0x1800b7752  mov     rbx, [rsp+1F0h+var_1A0]
0x1800b7757  mov     rax, [rbx]
0x1800b775a  mov     rdi, [rax+88h]
0x1800b7761  xor     ecx, ecx; string
0x1800b7763  call    cs:__imp_WindowsDeleteString
0x1800b776a  nop     dword ptr [rax+rax+00h]
0x1800b776f  mov     [rsp+1F0h+string], rsi
0x1800b7774  lea     rdx, [rsp+1F0h+string]
0x1800b7779  mov     rcx, rbx
0x1800b777c  mov     rax, rdi
0x1800b777f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7784  mov     rcx, [rbp+0F8h]; this
0x1800b778b  test    eax, eax
0x1800b778d  js      loc_1800B7CC9
0x1800b7793  mov     [rsp+1F0h+length], esi
0x1800b7797  lea     rdx, [rsp+1F0h+length]; length
0x1800b779c  mov     rcx, [rsp+1F0h+string]; string
0x1800b77a1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b77a8  nop     dword ptr [rax+rax+00h]
0x1800b77ad  mov     r8d, [rsp+1F0h+length]
0x1800b77b2  xorps   xmm0, xmm0
0x1800b77b5  movups  [rbp+0F0h+var_70], xmm0
0x1800b77bc  xorps   xmm1, xmm1
0x1800b77bf  movdqu  [rbp+0F0h+var_60], xmm1
0x1800b77c7  mov     rdx, rax
0x1800b77ca  lea     rcx, [rbp+0F0h+var_70]
0x1800b77d1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b77d6  lea     rcx, [r13+148h]
0x1800b77dd  lea     rdx, [rbp+0F0h+var_70]
0x1800b77e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b77e9  lea     rcx, [rbp+0F0h+var_70]; void *
0x1800b77f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b77f5  mov     [rsp+1F0h+var_1B0], rsi
0x1800b77fa  mov     rbx, [rsp+1F0h+var_1A0]
0x1800b77ff  mov     rax, [rbx]
0x1800b7802  mov     rdi, [rax+80h]
0x1800b7809  xor     ecx, ecx; string
0x1800b780b  call    cs:__imp_WindowsDeleteString
0x1800b7812  nop     dword ptr [rax+rax+00h]
0x1800b7817  mov     [rsp+1F0h+var_1B0], rsi
0x1800b781c  lea     rdx, [rsp+1F0h+var_1B0]
0x1800b7821  mov     rcx, rbx
0x1800b7824  mov     rax, rdi
0x1800b7827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b782c  mov     rcx, [rbp+0F8h]; this
0x1800b7833  test    eax, eax
0x1800b7835  js      loc_1800B7CDE
0x1800b783b  mov     [rsp+1F0h+length], esi
0x1800b783f  lea     rdx, [rsp+1F0h+length]; length
0x1800b7844  mov     rcx, [rsp+1F0h+var_1B0]; string
0x1800b7849  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b7850  nop     dword ptr [rax+rax+00h]
0x1800b7855  mov     r8d, [rsp+1F0h+length]
0x1800b785a  xorps   xmm0, xmm0
0x1800b785d  movups  [rbp+0F0h+var_70], xmm0
0x1800b7864  xorps   xmm1, xmm1
0x1800b7867  movdqu  [rbp+0F0h+var_60], xmm1
0x1800b786f  mov     rdx, rax
0x1800b7872  lea     rcx, [rbp+0F0h+var_70]
0x1800b7879  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b787e  lea     rcx, [r13+168h]
0x1800b7885  lea     rdx, [rbp+0F0h+var_70]
0x1800b788c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b7891  lea     rcx, [rbp+0F0h+var_70]; void *
0x1800b7898  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b789d  mov     [rsp+1F0h+var_1C0], sil
0x1800b78a2  xorps   xmm0, xmm0
0x1800b78a5  movdqa  xmmword ptr [rbp+0F0h+var_120], xmm0
0x1800b78aa  mov     [rbp+0F0h+var_110], rsi
0x1800b78ae  mov     [rbp+0F0h+var_108], rsi
0x1800b78b2  movdqa  [rbp+0F0h+var_100], xmm0
0x1800b78b7  xorps   xmm1, xmm1
0x1800b78ba  movdqa  [rbp+0F0h+var_F0], xmm1
0x1800b78bf  movdqa  [rbp+0F0h+var_E0], xmm0
0x1800b78c4  movdqa  [rbp+0F0h+var_D0], xmm1
0x1800b78c9  lea     r8, [r13+40h]
0x1800b78cd  cmp     qword ptr [r8+18h], 7
0x1800b78d2  jbe     short loc_1800B78D7
0x1800b78d4  mov     r8, [r8]
0x1800b78d7  lea     rax, [rsp+1F0h+var_1C0]
0x1800b78dc  mov     [rsp+1F0h+var_1C8], rax
0x1800b78e1  lea     rax, [rbp+0F0h+var_120]
0x1800b78e5  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x1800b78ea  xor     r9d, r9d
0x1800b78ed  mov     rdx, r12
0x1800b78f0  mov     rcx, r15
0x1800b78f3  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1800b78f8  mov     rcx, [rbp+0F8h]; this
0x1800b78ff  test    eax, eax
0x1800b7901  js      loc_1800B7CF3
0x1800b7907  cmp     [rsp+1F0h+var_1C0], sil
0x1800b790c  setz    al
0x1800b790f  mov     rcx, [rbp+0F8h]; this
0x1800b7916  test    al, al
0x1800b7918  jnz     loc_1800B7D08
0x1800b791e  mov     [rsp+1F0h+var_190], rsi
0x1800b7923  mov     [rsp+1F0h+var_188], esi
0x1800b7927  mov     [rsp+1F0h+var_180], rsi
0x1800b792c  lea     r9, aWindowsAppexte; "windows.appExtension"
0x1800b7933  mov     r8, [rbp+0F0h+var_120]; __int64
0x1800b7937  mov     rdx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b793a  lea     rcx, [rsp+1F0h+var_190]; this
0x1800b793f  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b7944  mov     ebx, eax
0x1800b7946  test    eax, eax
0x1800b7948  jns     short loc_1800B7967
0x1800b794a  mov     rcx, [rbp+0F8h]; this
0x1800b7951  mov     r9d, eax; char *
0x1800b7954  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b795b  mov     edx, 3B9h; void *
0x1800b7960  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7965  jmp     short loc_1800B7969
0x1800b7967  mov     ebx, esi
0x1800b7969  mov     rcx, [rbp+0F8h]; this
0x1800b7970  test    ebx, ebx
0x1800b7972  js      loc_1800B7D20
0x1800b7978  xorps   xmm0, xmm0
0x1800b797b  movdqa  xmmword ptr [rbp+0F0h+var_170], xmm0
0x1800b7980  mov     [rbp+0F0h+var_160], rsi
0x1800b7984  mov     [rbp+0F0h+var_158], rsi
0x1800b7988  movdqa  [rbp+0F0h+var_150], xmm0
0x1800b798d  xorps   xmm1, xmm1
0x1800b7990  movdqa  [rbp+0F0h+var_140], xmm1
0x1800b7995  mov     [rbp+0F0h+var_130], rsi
0x1800b7999  mov     [rbp+0F0h+var_128], esi
0x1800b799c  lea     r9, [rsp+1F0h+var_1C0]
0x1800b79a1  lea     r8, [rbp+0F0h+var_170]
0x1800b79a5  lea     rcx, [rsp+1F0h+var_190]
0x1800b79aa  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b79af  mov     rcx, [rbp+0F8h]; this
0x1800b79b6  test    eax, eax
0x1800b79b8  js      loc_1800B7C8A
0x1800b79be  jmp     loc_1800B7B0F
0x1800b79c3  xorps   xmm0, xmm0
0x1800b79c6  movdqa  [rbp+0F0h+var_C0], xmm0
0x1800b79cb  xorps   xmm1, xmm1
0x1800b79ce  movdqa  [rbp+0F0h+var_B0], xmm1
0x1800b79d3  movdqa  [rbp+0F0h+var_A0], xmm0
0x1800b79d8  movdqa  [rbp+0F0h+var_90], xmm1
0x1800b79dd  mov     [rbp+0F0h+var_80], esi
0x1800b79e0  mov     r14b, sil
0x1800b79e3  mov     [rsp+1F0h+var_1BF], sil
0x1800b79e8  mov     rdx, [rbp+0F0h+var_170]; __int64
0x1800b79ec  test    rdx, rdx
0x1800b79ef  jnz     short loc_1800B7A19
0x1800b79f1  mov     rcx, [rbp+0F8h]; this
0x1800b79f8  mov     r9d, 80070057h; char *
0x1800b79fe  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7a05  mov     edx, 119h; void *
0x1800b7a0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7a0f  mov     ebx, 80070057h
0x1800b7a14  jmp     loc_1800B7AC8
0x1800b7a19  mov     [rsp+1F0h+var_178], rsi
0x1800b7a1e  lea     r9, [rsp+1F0h+var_178]; __int64 *
0x1800b7a23  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b7a26  call    ?GetByExtensionAndName@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::GetByExtensionAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x1800b7a2b  mov     ebx, eax
0x1800b7a2d  test    eax, eax
0x1800b7a2f  jns     short loc_1800B7A4E
0x1800b7a31  mov     r9d, eax; char *
0x1800b7a34  mov     edx, 11Ch; void *
0x1800b7a39  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7a40  mov     rcx, [rbp+0F8h]; this
0x1800b7a47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7a4c  jmp     short loc_1800B7AC8
0x1800b7a4e  mov     rsi, [rsp+1F0h+var_178]
0x1800b7a53  test    rsi, rsi
0x1800b7a56  jz      short loc_1800B7AC6
0x1800b7a58  and     qword ptr [rsp+1F0h+length], 0
0x1800b7a5e  lea     r9, [rsp+1F0h+var_1BF]; bool *
0x1800b7a63  lea     r8, [rsp+1F0h+length]; this
0x1800b7a68  mov     rdx, rsi; __int64
0x1800b7a6b  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b7a6e  call    ?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b7a73  mov     ebx, eax
0x1800b7a75  mov     r14b, [rsp+1F0h+var_1BF]
0x1800b7a7a  test    eax, eax
0x1800b7a7c  jns     short loc_1800B7AA0
0x1800b7a7e  mov     rcx, [rbp+0F8h]; this
0x1800b7a85  mov     r9d, eax; char *
0x1800b7a88  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b7a8f  mov     edx, 0DCh; void *
0x1800b7a94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b7a99  xor     esi, esi
0x1800b7a9b  jmp     loc_1800B7C20
0x1800b7aa0  test    r14b, r14b
0x1800b7aa3  jnz     loc_1800B7BE8
0x1800b7aa9  xor     esi, esi
0x1800b7aab  mov     rcx, qword ptr [rsp+1F0h+length]
0x1800b7ab0  mov     qword ptr [rsp+1F0h+length], rsi
0x1800b7ab5  test    rcx, rcx
0x1800b7ab8  jz      short loc_1800B7AC6
0x1800b7aba  call    cs:__imp_SRCacheContext_Close
0x1800b7ac1  nop     dword ptr [rax+rax+00h]
0x1800b7ac6  mov     ebx, esi
0x1800b7ac8  mov     rcx, [rbp+0F8h]; this
0x1800b7acf  test    ebx, ebx
0x1800b7ad1  js      loc_1800B7C75
0x1800b7ad7  test    r14b, r14b
0x1800b7ada  jnz     loc_1800B7C48
0x1800b7ae0  inc     [rsp+1F0h+var_188]
0x1800b7ae4  lea     r9, [rsp+1F0h+var_1C0]
0x1800b7ae9  lea     r8, [rbp+0F0h+var_170]
0x1800b7aed  lea     rcx, [rsp+1F0h+var_190]
0x1800b7af2  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b7af7  mov     rcx, [rbp+0F8h]; this
0x1800b7afe  test    eax, eax
0x1800b7b00  js      loc_1800B7D4D
0x1800b7b06  lea     rcx, [rbp+0F0h+var_C0]; this
0x1800b7b0a  call    ??1AppExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppExtension_NoThrow::~AppExtension_NoThrow(void)
0x1800b7b0f  mov     dil, [rsp+1F0h+var_1C0]
0x1800b7b14  test    dil, dil
0x1800b7b17  jnz     loc_1800B79C3
0x1800b7b1d  mov     al, 1
0x1800b7b1f  mov     rcx, [rbp+0F8h]; this
0x1800b7b26  test    al, al
0x1800b7b28  jnz     loc_1800B7D35
0x1800b7b2e  lea     rcx, [rbp+0F0h+var_170]; this
0x1800b7b32  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b7b37  nop
0x1800b7b38  mov     rcx, [rsp+1F0h+var_190]
0x1800b7b3d  mov     [rsp+1F0h+var_190], rsi
0x1800b7b42  test    rcx, rcx
0x1800b7b45  jz      short loc_1800B7B54
0x1800b7b47  call    cs:__imp_SRCacheContext_Close
0x1800b7b4e  nop     dword ptr [rax+rax+00h]
0x1800b7b53  nop
0x1800b7b54  lea     rcx, [rbp+0F0h+var_120]; this
0x1800b7b58  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800b7b5d  nop
0x1800b7b5e  mov     rcx, [rsp+1F0h+var_1B0]; string
0x1800b7b63  call    cs:__imp_WindowsDeleteString
0x1800b7b6a  nop     dword ptr [rax+rax+00h]
0x1800b7b6f  mov     [rsp+1F0h+var_1B0], rsi
0x1800b7b74  mov     rcx, [rsp+1F0h+string]; string
0x1800b7b79  call    cs:__imp_WindowsDeleteString
0x1800b7b80  nop     dword ptr [rax+rax+00h]
0x1800b7b85  mov     [rsp+1F0h+string], rsi
0x1800b7b8a  mov     rcx, [rsp+1F0h+var_1A0]
0x1800b7b8f  test    rcx, rcx
0x1800b7b92  jz      short loc_1800B7BA6
0x1800b7b94  mov     [rsp+1F0h+var_1A0], rsi
0x1800b7b99  mov     rax, [rcx]
0x1800b7b9c  mov     rax, [rax+10h]
0x1800b7ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7ba5  nop
0x1800b7ba6  mov     rcx, [rsp+1F0h+var_198]
0x1800b7bab  test    rcx, rcx
0x1800b7bae  jz      short loc_1800B7BC2
0x1800b7bb0  mov     [rsp+1F0h+var_198], rsi
0x1800b7bb5  mov     rdx, [rcx]
0x1800b7bb8  mov     rax, [rdx+10h]
0x1800b7bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7bc1  nop
0x1800b7bc2  mov     al, 1
0x1800b7bc4  mov     rcx, [rbp+0F0h+var_50]
0x1800b7bcb  xor     rcx, rsp; StackCookie
0x1800b7bce  call    __security_check_cookie
0x1800b7bd3  add     rsp, 1B8h
0x1800b7bda  pop     r15
0x1800b7bdc  pop     r14
0x1800b7bde  pop     r13
0x1800b7be0  pop     r12
0x1800b7be2  pop     rdi
  ... truncated ...
```
