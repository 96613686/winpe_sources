# GetGamingAppLaunchParameters(Windows::ApplicationModel::Activation::IActivatedEventArgs *,StateRepository::Cache::Manager_NoThrow &,__int64,ActivationProperties &)

- ea: `0x1800b9520`
- end: `0x1800b9bec`
- name: `?GetGamingAppLaunchParameters@@YA_NPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@AEAVManager_NoThrow@Cache@StateRepository@@_JAEAUActivationProperties@@@Z`
- size: `1740`
- prototype: `bool(struct Windows::ApplicationModel::Activation::IActivatedEventArgs *, struct StateRepository::Cache::Manager_NoThrow *, __int64, struct ActivationProperties *)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting`

## callers

- `0x1800b8250`

## callees

- `0x180004f70`
- `0x18000ff24`
- `0x1800125f4`
- `0x180012fb8`
- `0x180013510`
- `0x1800136dc`
- `0x18003ab48`
- `0x18003ce48`
- `0x1800b388c`
- `0x1800b3980`
- `0x1800b4678`
- `0x1800b573c`
- `0x1800b6e0c`
- `0x1800b7d2c`
- `0x1800b9520`
- `0x1800bc0cc`
- `0x1800bc8bc`
- `0x1800cd010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b95c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b966b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b95c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b966b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9a4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800b9a61`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b9601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b96a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b9601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800b96a9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9912`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9974`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b99a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9a2f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9912`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9974`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b99a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800b9a2f`

## string_xrefs

- `0x1800b97b4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800b985b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b989a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b98ee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b9950`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-AppExtension.hpp`
- `0x1800b9b02`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b17`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b2c`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b41`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b56`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b6b`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b80`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9b98`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9bad`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9bc5`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b9bda`: `onecore\base\appmodel\execmodel\desktopappx\lib\aamextensions.cpp`
- `0x1800b978c`: `windows.appExtension`

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
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING *); // rbx
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
0x1800b9520  push    rbp
0x1800b9522  push    rbx
0x1800b9523  push    rsi
0x1800b9524  push    rdi
0x1800b9525  push    r12
0x1800b9527  push    r13
0x1800b9529  push    r14
0x1800b952b  push    r15
0x1800b952d  lea     rbp, [rsp-0B8h]
0x1800b9535  sub     rsp, 1B8h
0x1800b953c  mov     rax, cs:__security_cookie
0x1800b9543  xor     rax, rsp
0x1800b9546  mov     [rbp+0F0h+var_50], rax
0x1800b954d  mov     r13, r9
0x1800b9550  mov     r12, r8
0x1800b9553  mov     r15, rdx
0x1800b9556  xor     esi, esi
0x1800b9558  mov     [rsp+1F0h+var_198], rsi
0x1800b955d  mov     rax, [rcx]
0x1800b9560  lea     r8, [rsp+1F0h+var_198]
0x1800b9565  lea     rdx, _GUID_6095f4dd_b7c0_46ab_81fe_d90f36d00d24
0x1800b956c  mov     rax, [rax]
0x1800b956f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9574  mov     rcx, [rbp+0F8h]; this
0x1800b957b  test    eax, eax
0x1800b957d  js      loc_1800B9B29
0x1800b9583  mov     [rsp+1F0h+var_1A0], rsi
0x1800b9588  mov     rcx, [rsp+1F0h+var_198]
0x1800b958d  mov     rax, [rcx]
0x1800b9590  lea     rdx, [rsp+1F0h+var_1A0]
0x1800b9595  mov     rax, [rax+30h]
0x1800b9599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b959e  mov     rcx, [rbp+0F8h]; this
0x1800b95a5  test    eax, eax
0x1800b95a7  js      loc_1800B9B3E
0x1800b95ad  mov     [rsp+1F0h+string], rsi
0x1800b95b2  mov     rdi, [rsp+1F0h+var_1A0]
0x1800b95b7  mov     rax, [rdi]
0x1800b95ba  mov     rbx, [rax+88h]
0x1800b95c1  xor     ecx, ecx; string
0x1800b95c3  call    cs:__imp_WindowsDeleteString
0x1800b95ca  nop     dword ptr [rax+rax+00h]
0x1800b95cf  mov     [rsp+1F0h+string], rsi
0x1800b95d4  lea     rdx, [rsp+1F0h+string]
0x1800b95d9  mov     rcx, rdi
0x1800b95dc  mov     rax, rbx
0x1800b95df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b95e4  mov     rcx, [rbp+0F8h]; this
0x1800b95eb  test    eax, eax
0x1800b95ed  js      loc_1800B9B53
0x1800b95f3  mov     [rsp+1F0h+length], esi
0x1800b95f7  lea     rdx, [rsp+1F0h+length]; length
0x1800b95fc  mov     rcx, [rsp+1F0h+string]; string
0x1800b9601  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b9608  nop     dword ptr [rax+rax+00h]
0x1800b960d  xorps   xmm0, xmm0
0x1800b9610  movups  [rbp+0F0h+var_70], xmm0
0x1800b9617  xorps   xmm1, xmm1
0x1800b961a  movdqu  [rbp+0F0h+var_60], xmm1
0x1800b9622  mov     r8d, [rsp+1F0h+length]
0x1800b9627  mov     rdx, rax
0x1800b962a  lea     rcx, [rbp+0F0h+var_70]
0x1800b9631  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b9636  lea     rcx, [r13+148h]
0x1800b963d  lea     rdx, [rbp+0F0h+var_70]
0x1800b9644  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b9649  lea     rcx, [rbp+0F0h+var_70]; void *
0x1800b9650  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b9655  mov     [rsp+1F0h+var_1B0], rsi
0x1800b965a  mov     rdi, [rsp+1F0h+var_1A0]
0x1800b965f  mov     rax, [rdi]
0x1800b9662  mov     rbx, [rax+80h]
0x1800b9669  xor     ecx, ecx; string
0x1800b966b  call    cs:__imp_WindowsDeleteString
0x1800b9672  nop     dword ptr [rax+rax+00h]
0x1800b9677  mov     [rsp+1F0h+var_1B0], rsi
0x1800b967c  lea     rdx, [rsp+1F0h+var_1B0]
0x1800b9681  mov     rcx, rdi
0x1800b9684  mov     rax, rbx
0x1800b9687  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b968c  mov     rcx, [rbp+0F8h]; this
0x1800b9693  test    eax, eax
0x1800b9695  js      loc_1800B9B68
0x1800b969b  mov     [rsp+1F0h+length], esi
0x1800b969f  lea     rdx, [rsp+1F0h+length]; length
0x1800b96a4  mov     rcx, [rsp+1F0h+var_1B0]; string
0x1800b96a9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800b96b0  nop     dword ptr [rax+rax+00h]
0x1800b96b5  xorps   xmm0, xmm0
0x1800b96b8  movups  [rbp+0F0h+var_70], xmm0
0x1800b96bf  xorps   xmm1, xmm1
0x1800b96c2  movdqu  [rbp+0F0h+var_60], xmm1
0x1800b96ca  mov     r8d, [rsp+1F0h+length]
0x1800b96cf  mov     rdx, rax
0x1800b96d2  lea     rcx, [rbp+0F0h+var_70]
0x1800b96d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800b96de  lea     rcx, [r13+168h]
0x1800b96e5  lea     rdx, [rbp+0F0h+var_70]
0x1800b96ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800b96f1  lea     rcx, [rbp+0F0h+var_70]; void *
0x1800b96f8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800b96fd  mov     [rsp+1F0h+var_1C0], sil
0x1800b9702  xorps   xmm0, xmm0
0x1800b9705  movdqa  xmmword ptr [rbp+0F0h+var_120], xmm0
0x1800b970a  mov     [rbp+0F0h+var_110], rsi
0x1800b970e  mov     [rbp+0F0h+var_108], rsi
0x1800b9712  movdqa  [rbp+0F0h+var_100], xmm0
0x1800b9717  xorps   xmm1, xmm1
0x1800b971a  movdqa  [rbp+0F0h+var_F0], xmm1
0x1800b971f  movdqa  [rbp+0F0h+var_E0], xmm0
0x1800b9724  movdqa  [rbp+0F0h+var_D0], xmm1
0x1800b9729  lea     r8, [r13+40h]
0x1800b972d  cmp     qword ptr [r8+18h], 7
0x1800b9732  jbe     short loc_1800B9737
0x1800b9734  mov     r8, [r8]
0x1800b9737  lea     rax, [rsp+1F0h+var_1C0]
0x1800b973c  mov     [rsp+1F0h+var_1C8], rax
0x1800b9741  lea     rax, [rbp+0F0h+var_120]
0x1800b9745  mov     qword ptr [rsp+1F0h+var_1D0], rax; int
0x1800b974a  xor     r9d, r9d
0x1800b974d  mov     rdx, r12
0x1800b9750  mov     rcx, r15
0x1800b9753  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x1800b9758  mov     rcx, [rbp+0F8h]; this
0x1800b975f  test    eax, eax
0x1800b9761  js      loc_1800B9B7D
0x1800b9767  cmp     [rsp+1F0h+var_1C0], sil
0x1800b976c  setz    al
0x1800b976f  mov     rcx, [rbp+0F8h]; this
0x1800b9776  test    al, al
0x1800b9778  jnz     loc_1800B9B92
0x1800b977e  mov     [rsp+1F0h+var_190], rsi
0x1800b9783  mov     [rsp+1F0h+var_188], esi
0x1800b9787  mov     [rsp+1F0h+var_180], rsi
0x1800b978c  lea     r9, aWindowsAppexte; "windows.appExtension"
0x1800b9793  mov     r8, [rbp+0F0h+var_120]; __int64
0x1800b9797  mov     rdx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b979a  lea     rcx, [rsp+1F0h+var_190]; this
0x1800b979f  call    ?OpenByApplicationAndCategory@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_JPEBG@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::OpenByApplicationAndCategory(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *)
0x1800b97a4  mov     ebx, eax
0x1800b97a6  test    eax, eax
0x1800b97a8  jns     short loc_1800B97C7
0x1800b97aa  mov     rcx, [rbp+0F8h]; this
0x1800b97b1  mov     r9d, eax; char *
0x1800b97b4  lea     r8, aOnecorePrivate_11; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b97bb  mov     edx, 3B9h; void *
0x1800b97c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b97c5  jmp     short loc_1800B97C9
0x1800b97c7  mov     ebx, esi
0x1800b97c9  mov     rcx, [rbp+0F8h]; this
0x1800b97d0  test    ebx, ebx
0x1800b97d2  js      loc_1800B9BAA
0x1800b97d8  xorps   xmm0, xmm0
0x1800b97db  movdqa  xmmword ptr [rbp+0F0h+var_170], xmm0
0x1800b97e0  mov     [rbp+0F0h+var_160], rsi
0x1800b97e4  mov     [rbp+0F0h+var_158], rsi
0x1800b97e8  movdqa  [rbp+0F0h+var_150], xmm0
0x1800b97ed  xorps   xmm1, xmm1
0x1800b97f0  movdqa  [rbp+0F0h+var_140], xmm1
0x1800b97f5  mov     [rbp+0F0h+var_130], rsi
0x1800b97f9  mov     [rbp+0F0h+var_128], esi
0x1800b97fc  lea     r9, [rsp+1F0h+var_1C0]
0x1800b9801  lea     r8, [rbp+0F0h+var_170]
0x1800b9805  lea     rcx, [rsp+1F0h+var_190]
0x1800b980a  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b980f  mov     rcx, [rbp+0F8h]; this
0x1800b9816  test    eax, eax
0x1800b9818  js      loc_1800B9B14
0x1800b981e  jmp     loc_1800B99F7
0x1800b9823  xorps   xmm0, xmm0
0x1800b9826  movdqa  [rbp+0F0h+var_C0], xmm0
0x1800b982b  xorps   xmm1, xmm1
0x1800b982e  movdqa  [rbp+0F0h+var_B0], xmm1
0x1800b9833  movdqa  [rbp+0F0h+var_A0], xmm0
0x1800b9838  movdqa  [rbp+0F0h+var_90], xmm1
0x1800b983d  mov     [rbp+0F0h+var_80], esi
0x1800b9840  mov     rdx, [rbp+0F0h+var_170]; __int64
0x1800b9844  mov     [rsp+1F0h+var_1BF], sil
0x1800b9849  test    rdx, rdx
0x1800b984c  jnz     short loc_1800B9876
0x1800b984e  mov     rcx, [rbp+0F8h]; this
0x1800b9855  mov     r9d, 80070057h; char *
0x1800b985b  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b9862  mov     edx, 119h; void *
0x1800b9867  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b986c  mov     ebx, 80070057h
0x1800b9871  jmp     loc_1800B99AE
0x1800b9876  mov     [rsp+1F0h+var_178], 0
0x1800b987f  lea     r9, [rsp+1F0h+var_178]; __int64 *
0x1800b9884  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b9887  call    ?GetByExtensionAndName@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGAEA_J@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::GetByExtensionAndName(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,__int64 &)
0x1800b988c  mov     ebx, eax
0x1800b988e  test    eax, eax
0x1800b9890  jns     short loc_1800B98B2
0x1800b9892  mov     r9d, eax; char *
0x1800b9895  mov     edx, 11Ch; void *
0x1800b989a  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b98a1  mov     rcx, [rbp+0F8h]; this
0x1800b98a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b98ad  jmp     loc_1800B99AE
0x1800b98b2  mov     rdi, [rsp+1F0h+var_178]
0x1800b98b7  test    rdi, rdi
0x1800b98ba  jz      loc_1800B99AC
0x1800b98c0  mov     qword ptr [rsp+1F0h+length], 0
0x1800b98c9  lea     r9, [rsp+1F0h+var_1BF]; bool *
0x1800b98ce  lea     r8, [rsp+1F0h+length]; this
0x1800b98d3  mov     rdx, rdi; __int64
0x1800b98d6  mov     rcx, r15; struct StateRepository::Cache::Manager_NoThrow *
0x1800b98d9  call    ?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800b98de  mov     ebx, eax
0x1800b98e0  test    eax, eax
0x1800b98e2  jns     short loc_1800B9925
0x1800b98e4  mov     rcx, [rbp+0F8h]; this
0x1800b98eb  mov     r9d, eax; char *
0x1800b98ee  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b98f5  mov     edx, 0DCh; void *
0x1800b98fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b98ff  mov     rcx, qword ptr [rsp+1F0h+length]
0x1800b9904  mov     qword ptr [rsp+1F0h+length], 0
0x1800b990d  test    rcx, rcx
0x1800b9910  jz      short loc_1800B991E
0x1800b9912  call    cs:__imp_SRCacheContext_Close
0x1800b9919  nop     dword ptr [rax+rax+00h]
0x1800b991e  mov     sil, [rsp+1F0h+var_1BF]
0x1800b9923  jmp     short loc_1800B9980
0x1800b9925  mov     sil, [rsp+1F0h+var_1BF]
0x1800b992a  test    sil, sil
0x1800b992d  jz      short loc_1800B998D
0x1800b992f  mov     r9, rdi
0x1800b9932  lea     rdx, [rbp+0F0h+var_C0]
0x1800b9936  lea     rcx, [rsp+1F0h+length]
0x1800b993b  call    ?ContextToObject@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,__int64)
0x1800b9940  mov     ebx, eax
0x1800b9942  test    eax, eax
0x1800b9944  jns     short loc_1800B998D
0x1800b9946  mov     rcx, [rbp+0F8h]; this
0x1800b994d  mov     r9d, eax; char *
0x1800b9950  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800b9957  mov     edx, 0E1h; void *
0x1800b995c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b9961  mov     rcx, qword ptr [rsp+1F0h+length]
0x1800b9966  mov     qword ptr [rsp+1F0h+length], 0
0x1800b996f  test    rcx, rcx
0x1800b9972  jz      short loc_1800B9980
0x1800b9974  call    cs:__imp_SRCacheContext_Close
0x1800b997b  nop     dword ptr [rax+rax+00h]
0x1800b9980  mov     r9d, ebx
0x1800b9983  mov     edx, 11Fh
0x1800b9988  jmp     loc_1800B989A
0x1800b998d  mov     rcx, qword ptr [rsp+1F0h+length]
0x1800b9992  test    rcx, rcx
0x1800b9995  mov     qword ptr [rsp+1F0h+length], 0
0x1800b999e  jz      short loc_1800B99AC
0x1800b99a0  call    cs:__imp_SRCacheContext_Close
0x1800b99a7  nop     dword ptr [rax+rax+00h]
0x1800b99ac  xor     ebx, ebx
0x1800b99ae  mov     rcx, [rbp+0F8h]; this
0x1800b99b5  test    ebx, ebx
0x1800b99b7  js      loc_1800B9AFF
0x1800b99bd  test    sil, sil
0x1800b99c0  jnz     loc_1800B9AD0
0x1800b99c6  inc     [rsp+1F0h+var_188]
0x1800b99ca  lea     r9, [rsp+1F0h+var_1C0]
0x1800b99cf  lea     r8, [rbp+0F0h+var_170]
0x1800b99d3  lea     rcx, [rsp+1F0h+var_190]
0x1800b99d8  call    ?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1800b99dd  mov     rcx, [rbp+0F8h]; this
0x1800b99e4  xor     esi, esi
0x1800b99e6  test    eax, eax
0x1800b99e8  js      loc_1800B9BD7
0x1800b99ee  lea     rcx, [rbp+0F0h+var_C0]; this
0x1800b99f2  call    ??1AppExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppExtension_NoThrow::~AppExtension_NoThrow(void)
0x1800b99f7  mov     r14b, [rsp+1F0h+var_1C0]
0x1800b99fc  test    r14b, r14b
0x1800b99ff  jnz     loc_1800B9823
0x1800b9a05  mov     al, 1
0x1800b9a07  mov     rcx, [rbp+0F8h]; this
0x1800b9a0e  test    al, al
0x1800b9a10  jnz     loc_1800B9BBF
0x1800b9a16  lea     rcx, [rbp+0F0h+var_170]; this
0x1800b9a1a  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1800b9a1f  nop
0x1800b9a20  mov     rcx, [rsp+1F0h+var_190]
0x1800b9a25  mov     [rsp+1F0h+var_190], rsi
0x1800b9a2a  test    rcx, rcx
0x1800b9a2d  jz      short loc_1800B9A3C
0x1800b9a2f  call    cs:__imp_SRCacheContext_Close
0x1800b9a36  nop     dword ptr [rax+rax+00h]
0x1800b9a3b  nop
0x1800b9a3c  lea     rcx, [rbp+0F0h+var_120]; this
0x1800b9a40  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x1800b9a45  nop
0x1800b9a46  mov     rcx, [rsp+1F0h+var_1B0]; string
0x1800b9a4b  call    cs:__imp_WindowsDeleteString
0x1800b9a52  nop     dword ptr [rax+rax+00h]
0x1800b9a57  mov     [rsp+1F0h+var_1B0], rsi
0x1800b9a5c  mov     rcx, [rsp+1F0h+string]; string
0x1800b9a61  call    cs:__imp_WindowsDeleteString
0x1800b9a68  nop     dword ptr [rax+rax+00h]
0x1800b9a6d  mov     [rsp+1F0h+string], rsi
  ... truncated ...
```
