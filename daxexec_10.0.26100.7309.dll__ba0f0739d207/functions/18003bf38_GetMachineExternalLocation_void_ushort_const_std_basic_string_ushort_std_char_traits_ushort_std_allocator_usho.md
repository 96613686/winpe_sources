# GetMachineExternalLocation(void *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003bf38`
- end: `0x18003c36d`
- name: `?GetMachineExternalLocation@@YA_NPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1077`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x18003c3dc`

## callees

- `0x1800053a0`
- `0x18000e234`
- `0x180010a84`
- `0x180011820`
- `0x180011a64`
- `0x1800279fc`
- `0x18002b240`
- `0x180038f68`
- `0x18003917c`
- `0x18003a704`
- `0x18003b244`
- `0x18003b6a0`
- `0x18003b850`
- `0x18003bf38`
- `0x18003d314`
- `0x18003fa44`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003c16f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003c25d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003c16f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003c25d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c13e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c22c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c13e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003c22c`

## string_xrefs

- `0x18003c09c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall GetMachineExternalLocation(PSID Sid, __int64 a2)
{
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // [rsp+20h] [rbp-E0h]
  int v8; // [rsp+30h] [rbp-D0h]
  __int64 v9; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v10; // [rsp+40h] [rbp-C0h] BYREF
  int v11[4]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v12; // [rsp+E0h] [rbp-20h]
  __int64 v13; // [rsp+E8h] [rbp-18h]
  __int128 v14; // [rsp+F0h] [rbp-10h]
  __int128 v15; // [rsp+100h] [rbp+0h]
  __int128 v16; // [rsp+110h] [rbp+10h]
  __int128 v17; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v9 = 0;
  v4 = StateRepository::Cache::Manager_NoThrow::Open((StateRepository::Cache::Manager_NoThrow *)&v9);
  if ( v4 >= 0 )
  {
    v10 = 0;
    v5 = StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(
           (struct StateRepository::Cache::Manager_NoThrow *)&v9,
           Sid,
           &v10);
    if ( v5 >= 0 )
    {
      if ( v10 )
      {
        *(_OWORD *)v11 = 0;
        v12 = 0;
        v13 = 0;
        v14 = 0;
        v15 = 0;
        v16 = 0;
        v17 = 0;
        LOBYTE(v8) = 0;
        v6 = StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(&v9, v10, a2, 0);
        if ( v6 >= 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x228,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
            (const char *)0x80070490LL,
            (int)v11);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x227,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
          (const char *)(unsigned int)v6,
          (int)v11);
      }
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
        (const char *)0x80070002LL,
        v7);
    }
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
      (const char *)(unsigned int)v5,
      v7);
  }
  wil::details::in1diag3::Throw_Hr(
    retaddr,
    (void *)0x21D,
    (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\packageutils.cpp",
    (const char *)(unsigned int)v4,
    v7);
}

```

## disassembly

```asm
0x18003bf38  push    rbp
0x18003bf3a  push    rbx
0x18003bf3b  push    rsi
0x18003bf3c  push    rdi
0x18003bf3d  push    r14
0x18003bf3f  lea     rbp, [rsp-0A0h]
0x18003bf47  sub     rsp, 1A0h
0x18003bf4e  mov     rax, cs:__security_cookie
0x18003bf55  xor     rax, rsp
0x18003bf58  mov     [rbp+0C0h+var_30], rax
0x18003bf5f  mov     rsi, r8
0x18003bf62  mov     rdi, rdx
0x18003bf65  mov     rbx, rcx
0x18003bf68  xor     r14d, r14d
0x18003bf6b  mov     [rsp+1C0h+var_188], r14
0x18003bf70  lea     rcx, [rsp+1C0h+var_188]; this
0x18003bf75  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x18003bf7a  mov     rcx, [rbp+0C8h]; this
0x18003bf81  test    eax, eax
0x18003bf83  js      loc_18003C2A1
0x18003bf89  mov     [rsp+1C0h+var_180], r14
0x18003bf8e  lea     r8, [rsp+1C0h+var_180]; __int64 *
0x18003bf93  mov     rdx, rbx; Sid
0x18003bf96  lea     rcx, [rsp+1C0h+var_188]; struct StateRepository::Cache::Manager_NoThrow *
0x18003bf9b  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18003bfa0  mov     rcx, [rbp+0C8h]; this
0x18003bfa7  test    eax, eax
0x18003bfa9  js      loc_18003C2B6
0x18003bfaf  mov     rdx, [rsp+1C0h+var_180]
0x18003bfb4  test    rdx, rdx
0x18003bfb7  setz    al
0x18003bfba  mov     rcx, [rbp+0C8h]; this
0x18003bfc1  test    al, al
0x18003bfc3  jnz     loc_18003C2CB
0x18003bfc9  xorps   xmm0, xmm0
0x18003bfcc  movdqa  xmmword ptr [rbp+0C0h+var_F0], xmm0
0x18003bfd1  mov     [rbp+0C0h+var_E0], r14
0x18003bfd5  mov     [rbp+0C0h+var_D8], r14
0x18003bfd9  movdqa  [rbp+0C0h+var_D0], xmm0
0x18003bfde  xorps   xmm1, xmm1
0x18003bfe1  movdqa  [rbp+0C0h+var_C0], xmm1
0x18003bfe6  movdqa  [rbp+0C0h+var_B0], xmm0
0x18003bfeb  movdqa  [rbp+0C0h+var_A0], xmm1
0x18003bff0  mov     byte ptr [rsp+1C0h+var_190], r14b
0x18003bff5  lea     rax, [rsp+1C0h+var_190]
0x18003bffa  mov     [rsp+1C0h+var_198], rax
0x18003bfff  lea     rax, [rbp+0C0h+var_F0]
0x18003c003  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18003c008  xor     r9d, r9d
0x18003c00b  mov     r8, rdi
0x18003c00e  lea     rcx, [rsp+1C0h+var_188]
0x18003c013  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18003c018  mov     rcx, [rbp+0C8h]; this
0x18003c01f  test    eax, eax
0x18003c021  js      loc_18003C2E3
0x18003c027  cmp     byte ptr [rsp+1C0h+var_190], r14b
0x18003c02c  setz    al
0x18003c02f  mov     rcx, [rbp+0C8h]; this
0x18003c036  test    al, al
0x18003c038  jnz     loc_18003C2F8
0x18003c03e  xorps   xmm0, xmm0
0x18003c041  movdqa  [rsp+1C0h+var_150], xmm0
0x18003c047  mov     [rbp+0C0h+var_140], r14
0x18003c04b  mov     [rbp+0C0h+var_138], r14
0x18003c04f  mov     [rbp+0C0h+var_130], r14
0x18003c053  mov     [rbp+0C0h+var_128], r14
0x18003c057  mov     [rbp+0C0h+var_120], r14
0x18003c05b  mov     [rbp+0C0h+var_118], r14
0x18003c05f  movdqa  [rbp+0C0h+var_110], xmm0
0x18003c064  mov     [rbp+0C0h+var_100], r14d
0x18003c068  mov     [rbp+0C0h+var_F8], r14
0x18003c06c  lea     rax, [rsp+1C0h+var_190]
0x18003c071  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18003c076  lea     r9, [rsp+1C0h+var_150]
0x18003c07b  xor     r8d, r8d
0x18003c07e  mov     rdx, qword ptr [rbp+0C0h+var_F0+8]
0x18003c082  lea     rcx, [rsp+1C0h+var_188]
0x18003c087  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18003c08c  mov     ebx, eax
0x18003c08e  test    eax, eax
0x18003c090  jns     short loc_18003C0AF
0x18003c092  mov     rcx, [rbp+0C8h]; this
0x18003c099  mov     r9d, eax; char *
0x18003c09c  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003c0a3  mov     edx, 44Ch; void *
0x18003c0a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003c0ad  jmp     short loc_18003C0B2
0x18003c0af  mov     ebx, r14d
0x18003c0b2  mov     rcx, [rbp+0C8h]; this
0x18003c0b9  test    ebx, ebx
0x18003c0bb  js      loc_18003C310
0x18003c0c1  cmp     byte ptr [rsp+1C0h+var_190], r14b
0x18003c0c6  setz    al
0x18003c0c9  mov     rcx, [rbp+0C8h]; this
0x18003c0d0  test    al, al
0x18003c0d2  jnz     loc_18003C325
0x18003c0d8  test    dword ptr [rbp+0C0h+var_138+4], 200000h
0x18003c0df  jz      short loc_18003C14B
0x18003c0e1  xorps   xmm0, xmm0
0x18003c0e4  movdqu  xmmword ptr [rsp+1C0h+var_178], xmm0
0x18003c0ea  mov     [rsp+1C0h+var_168], r14
0x18003c0ef  mov     [rsp+1C0h+var_160], r14
0x18003c0f4  lea     rax, [rsp+1C0h+var_190]
0x18003c0f9  mov     [rsp+1C0h+var_198], rax
0x18003c0fe  lea     rax, [rsp+1C0h+var_178]
0x18003c103  mov     qword ptr [rsp+1C0h+var_1A0], rax; int
0x18003c108  mov     r8, qword ptr [rsp+1C0h+var_150]
0x18003c10d  xor     edx, edx
0x18003c10f  lea     rcx, [rsp+1C0h+var_188]
0x18003c114  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003c119  mov     rcx, [rbp+0C8h]; this
0x18003c120  test    eax, eax
0x18003c122  js      loc_18003C33D
0x18003c128  cmp     byte ptr [rsp+1C0h+var_190], r14b
0x18003c12d  jnz     short loc_18003C182
0x18003c12f  mov     rcx, [rsp+1C0h+var_160]
0x18003c134  mov     [rsp+1C0h+var_160], r14
0x18003c139  test    rcx, rcx
0x18003c13c  jz      short loc_18003C14B
0x18003c13e  call    cs:__imp_SRCache_Free
0x18003c145  nop     dword ptr [rax+rax+00h]
0x18003c14a  nop
0x18003c14b  lea     rcx, [rsp+1C0h+var_150]; this
0x18003c150  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003c155  nop
0x18003c156  lea     rcx, [rbp+0C0h+var_F0]; this
0x18003c15a  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003c15f  nop
0x18003c160  mov     rcx, [rsp+1C0h+var_188]
0x18003c165  test    rcx, rcx
0x18003c168  mov     [rsp+1C0h+var_188], r14
0x18003c16d  jz      short loc_18003C17B
0x18003c16f  call    cs:__imp_SRCacheManager_Close
0x18003c176  nop     dword ptr [rax+rax+00h]
0x18003c17b  xor     al, al
0x18003c17d  jmp     loc_18003C26B
0x18003c182  mov     rcx, [rsp+1C0h+var_160]
0x18003c187  test    rcx, rcx
0x18003c18a  setz    al
0x18003c18d  mov     r10, [rbp+0C8h]
0x18003c194  test    al, al
0x18003c196  jnz     loc_18003C352
0x18003c19c  mov     [rbp+0C0h+var_90], rcx
0x18003c1a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c1a4  inc     rax
0x18003c1a7  cmp     [rcx+rax*2], r14w
0x18003c1ac  jnz     short loc_18003C1A4
0x18003c1ae  mov     [rbp+0C0h+var_88], rax
0x18003c1b2  lea     rdx, [rbp+0C0h+var_90]
0x18003c1b6  lea     rcx, [rbp+0C0h+var_70]
0x18003c1ba  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18003c1bf  nop
0x18003c1c0  lea     rdx, [rbp+0C0h+var_70]
0x18003c1c4  lea     rcx, [rbp+0C0h+var_50]
0x18003c1c8  call    ?canonical@filesystem@std@@YA?AVpath@12@AEBV312@@Z; std::filesystem::canonical(std::filesystem::path const &)
0x18003c1cd  nop
0x18003c1ce  lea     rcx, [rbp+0C0h+var_70]; void *
0x18003c1d2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c1d7  cmp     [rbp+0C0h+var_40], r14
0x18003c1de  setz    al
0x18003c1e1  mov     rcx, [rbp+0C8h]; this
0x18003c1e8  test    al, al
0x18003c1ea  jnz     loc_18003C289
0x18003c1f0  lea     rdx, [rbp+0C0h+var_50]
0x18003c1f4  lea     rcx, [rbp+0C0h+var_90]
0x18003c1f8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003c1fd  lea     rdx, [rbp+0C0h+var_90]
0x18003c201  mov     rcx, rsi
0x18003c204  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003c209  lea     rcx, [rbp+0C0h+var_90]; void *
0x18003c20d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c212  nop
0x18003c213  lea     rcx, [rbp+0C0h+var_50]; void *
0x18003c217  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c21c  nop
0x18003c21d  mov     rcx, [rsp+1C0h+var_160]
0x18003c222  mov     [rsp+1C0h+var_160], r14
0x18003c227  test    rcx, rcx
0x18003c22a  jz      short loc_18003C239
0x18003c22c  call    cs:__imp_SRCache_Free
0x18003c233  nop     dword ptr [rax+rax+00h]
0x18003c238  nop
0x18003c239  lea     rcx, [rsp+1C0h+var_150]; this
0x18003c23e  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003c243  nop
0x18003c244  lea     rcx, [rbp+0C0h+var_F0]; this
0x18003c248  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003c24d  nop
0x18003c24e  mov     rcx, [rsp+1C0h+var_188]
0x18003c253  mov     [rsp+1C0h+var_188], r14
0x18003c258  test    rcx, rcx
0x18003c25b  jz      short loc_18003C269
0x18003c25d  call    cs:__imp_SRCacheManager_Close
0x18003c264  nop     dword ptr [rax+rax+00h]
0x18003c269  mov     al, 1
0x18003c26b  mov     rcx, [rbp+0C0h+var_30]
0x18003c272  xor     rcx, rsp; StackCookie
0x18003c275  call    __security_check_cookie
0x18003c27a  add     rsp, 1A0h
0x18003c281  pop     r14
0x18003c283  pop     rdi
0x18003c284  pop     rsi
0x18003c285  pop     rbx
0x18003c286  pop     rbp
0x18003c287  retn
0x18003c289  mov     r9d, 80070490h; char *
0x18003c28f  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c296  mov     edx, 23Fh; void *
0x18003c29b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c2a1  mov     r9d, eax; char *
0x18003c2a4  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c2ab  mov     edx, 21Dh; void *
0x18003c2b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c2b6  mov     r9d, eax; char *
0x18003c2b9  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c2c0  mov     edx, 220h; void *
0x18003c2c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c2cb  mov     r9d, 80070002h; char *
0x18003c2d1  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c2d8  mov     edx, 221h; void *
0x18003c2dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c2e3  mov     r9d, eax; char *
0x18003c2e6  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c2ed  mov     edx, 227h; void *
0x18003c2f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c2f8  mov     r9d, 80070490h; char *
0x18003c2fe  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c305  mov     edx, 228h; void *
0x18003c30a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c310  mov     r9d, ebx; char *
0x18003c313  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c31a  mov     edx, 22Bh; void *
0x18003c31f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c325  mov     r9d, 80070490h; char *
0x18003c32b  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c332  mov     edx, 22Ch; void *
0x18003c337  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c33d  mov     r9d, eax; char *
0x18003c340  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c347  mov     edx, 237h; void *
0x18003c34c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c352  mov     r9d, 80070490h; char *
0x18003c358  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003c35f  mov     edx, 23Ch; void *
0x18003c364  mov     rcx, r10; this
0x18003c367  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
