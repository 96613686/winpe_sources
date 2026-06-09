# GetMachineExternalLocation(void *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003db44`
- end: `0x18003df80`
- name: `?GetMachineExternalLocation@@YA_NPEAXPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation`

## callers

- `0x18003dfe4`

## callees

- `0x180004f70`
- `0x18000ff24`
- `0x1800125f4`
- `0x180013510`
- `0x1800136dc`
- `0x1800281a0`
- `0x18002bab4`
- `0x18003ab48`
- `0x18003ad7c`
- `0x18003c3a0`
- `0x18003ce48`
- `0x18003d29c`
- `0x18003d45c`
- `0x18003db44`
- `0x18003f050`
- `0x1800417dc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003dd4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003de3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003dd4d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18003de3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003dd7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003de70`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003dd7e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18003de70`

## string_xrefs

- `0x18003dcac`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

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
  int v11[4]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v12; // [rsp+F0h] [rbp-10h]
  __int64 v13; // [rsp+F8h] [rbp-8h]
  __int128 v14; // [rsp+100h] [rbp+0h]
  __int128 v15; // [rsp+110h] [rbp+10h]
  __int128 v16; // [rsp+120h] [rbp+20h]
  __int128 v17; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

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
0x18003db44  push    rbp
0x18003db46  push    rbx
0x18003db47  push    rsi
0x18003db48  push    rdi
0x18003db49  push    r14
0x18003db4b  lea     rbp, [rsp-0B0h]
0x18003db53  sub     rsp, 1B0h
0x18003db5a  mov     rax, cs:__security_cookie
0x18003db61  xor     rax, rsp
0x18003db64  mov     [rbp+0D0h+var_30], rax
0x18003db6b  mov     rsi, r8
0x18003db6e  mov     rdi, rdx
0x18003db71  mov     rbx, rcx
0x18003db74  xor     r14d, r14d
0x18003db77  mov     [rsp+1D0h+var_198], r14
0x18003db7c  lea     rcx, [rsp+1D0h+var_198]; this
0x18003db81  call    ?Open@Manager_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::Manager_NoThrow::Open(void)
0x18003db86  mov     rcx, [rbp+0D8h]; this
0x18003db8d  test    eax, eax
0x18003db8f  js      loc_18003DEB4
0x18003db95  mov     [rsp+1D0h+var_190], r14
0x18003db9a  lea     r8, [rsp+1D0h+var_190]; __int64 *
0x18003db9f  mov     rdx, rbx; Sid
0x18003dba2  lea     rcx, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18003dba7  call    ?GetByUserSid@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByUserSid(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18003dbac  mov     rcx, [rbp+0D8h]; this
0x18003dbb3  test    eax, eax
0x18003dbb5  js      loc_18003DEC9
0x18003dbbb  mov     rdx, [rsp+1D0h+var_190]
0x18003dbc0  test    rdx, rdx
0x18003dbc3  setz    al
0x18003dbc6  mov     rcx, [rbp+0D8h]; this
0x18003dbcd  test    al, al
0x18003dbcf  jnz     loc_18003DEDE
0x18003dbd5  xorps   xmm0, xmm0
0x18003dbd8  movdqa  xmmword ptr [rbp+0D0h+var_F0], xmm0
0x18003dbdd  mov     [rbp+0D0h+var_E0], r14
0x18003dbe1  mov     [rbp+0D0h+var_D8], r14
0x18003dbe5  movdqa  [rbp+0D0h+var_D0], xmm0
0x18003dbea  xorps   xmm1, xmm1
0x18003dbed  movdqa  [rbp+0D0h+var_C0], xmm1
0x18003dbf2  movdqa  [rbp+0D0h+var_B0], xmm0
0x18003dbf7  movdqa  [rbp+0D0h+var_A0], xmm1
0x18003dbfc  mov     byte ptr [rsp+1D0h+var_1A0], r14b
0x18003dc01  lea     rax, [rsp+1D0h+var_1A0]
0x18003dc06  mov     [rsp+1D0h+var_1A8], rax
0x18003dc0b  lea     rax, [rbp+0D0h+var_F0]
0x18003dc0f  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18003dc14  xor     r9d, r9d
0x18003dc17  mov     r8, rdi
0x18003dc1a  lea     rcx, [rsp+1D0h+var_198]
0x18003dc1f  call    ?GetByUserAndApplicationUserModelId@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JPEBGW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::GetByUserAndApplicationUserModelId(StateRepository::Cache::Manager_NoThrow &,__int64,ushort const *,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x18003dc24  mov     rcx, [rbp+0D8h]; this
0x18003dc2b  test    eax, eax
0x18003dc2d  js      loc_18003DEF6
0x18003dc33  cmp     byte ptr [rsp+1D0h+var_1A0], r14b
0x18003dc38  setz    al
0x18003dc3b  mov     rcx, [rbp+0D8h]; this
0x18003dc42  test    al, al
0x18003dc44  jnz     loc_18003DF0B
0x18003dc4a  xorps   xmm0, xmm0
0x18003dc4d  movdqa  [rsp+1D0h+var_160], xmm0
0x18003dc53  mov     [rbp+0D0h+var_150], r14
0x18003dc57  mov     [rbp+0D0h+var_148], r14
0x18003dc5b  mov     [rbp+0D0h+var_140], r14
0x18003dc5f  mov     [rbp+0D0h+var_138], r14
0x18003dc63  mov     [rbp+0D0h+var_130], r14
0x18003dc67  mov     [rbp+0D0h+var_128], r14
0x18003dc6b  movdqa  [rbp+0D0h+var_120], xmm0
0x18003dc70  mov     [rbp+0D0h+var_110], r14d
0x18003dc74  mov     [rbp+0D0h+var_108], r14
0x18003dc78  mov     [rbp+0D0h+var_100], r14
0x18003dc7c  lea     rax, [rsp+1D0h+var_1A0]
0x18003dc81  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18003dc86  lea     r9, [rsp+1D0h+var_160]
0x18003dc8b  xor     r8d, r8d
0x18003dc8e  mov     rdx, qword ptr [rbp+0D0h+var_F0+8]
0x18003dc92  lea     rcx, [rsp+1D0h+var_198]
0x18003dc97  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18003dc9c  mov     ebx, eax
0x18003dc9e  test    eax, eax
0x18003dca0  jns     short loc_18003DCBF
0x18003dca2  mov     rcx, [rbp+0D8h]; this
0x18003dca9  mov     r9d, eax; char *
0x18003dcac  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x18003dcb3  mov     edx, 44Ch; void *
0x18003dcb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003dcbd  jmp     short loc_18003DCC2
0x18003dcbf  mov     ebx, r14d
0x18003dcc2  mov     rcx, [rbp+0D8h]; this
0x18003dcc9  test    ebx, ebx
0x18003dccb  js      loc_18003DF23
0x18003dcd1  cmp     byte ptr [rsp+1D0h+var_1A0], r14b
0x18003dcd6  setz    al
0x18003dcd9  mov     rcx, [rbp+0D8h]; this
0x18003dce0  test    al, al
0x18003dce2  jnz     loc_18003DF38
0x18003dce8  test    dword ptr [rbp+0D0h+var_148+4], 200000h
0x18003dcef  jz      short loc_18003DD5A
0x18003dcf1  xorps   xmm0, xmm0
0x18003dcf4  movdqu  xmmword ptr [rsp+1D0h+var_188], xmm0
0x18003dcfa  xorps   xmm1, xmm1
0x18003dcfd  movdqu  [rsp+1D0h+var_178], xmm1
0x18003dd03  lea     rax, [rsp+1D0h+var_1A0]
0x18003dd08  mov     [rsp+1D0h+var_1A8], rax
0x18003dd0d  lea     rax, [rsp+1D0h+var_188]
0x18003dd12  mov     qword ptr [rsp+1D0h+var_1B0], rax; int
0x18003dd17  mov     r8, qword ptr [rsp+1D0h+var_160]
0x18003dd1c  xor     edx, edx
0x18003dd1e  lea     rcx, [rsp+1D0h+var_198]
0x18003dd23  call    ?GetByUserAndPackage@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1W4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::GetByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExternalLocation_NoThrow &,bool &)
0x18003dd28  mov     rcx, [rbp+0D8h]; this
0x18003dd2f  test    eax, eax
0x18003dd31  js      loc_18003DF50
0x18003dd37  cmp     byte ptr [rsp+1D0h+var_1A0], r14b
0x18003dd3c  jnz     short loc_18003DD91
0x18003dd3e  mov     rcx, qword ptr [rsp+1D0h+var_178+8]
0x18003dd43  mov     qword ptr [rsp+1D0h+var_178+8], r14
0x18003dd48  test    rcx, rcx
0x18003dd4b  jz      short loc_18003DD5A
0x18003dd4d  call    cs:__imp_SRCache_Free
0x18003dd54  nop     dword ptr [rax+rax+00h]
0x18003dd59  nop
0x18003dd5a  lea     rcx, [rsp+1D0h+var_160]; this
0x18003dd5f  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003dd64  nop
0x18003dd65  lea     rcx, [rbp+0D0h+var_F0]; this
0x18003dd69  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003dd6e  nop
0x18003dd6f  mov     rcx, [rsp+1D0h+var_198]
0x18003dd74  test    rcx, rcx
0x18003dd77  mov     [rsp+1D0h+var_198], r14
0x18003dd7c  jz      short loc_18003DD8A
0x18003dd7e  call    cs:__imp_SRCacheManager_Close
0x18003dd85  nop     dword ptr [rax+rax+00h]
0x18003dd8a  xor     al, al
0x18003dd8c  jmp     loc_18003DE7E
0x18003dd91  mov     rcx, qword ptr [rsp+1D0h+var_178+8]
0x18003dd96  mov     rax, [rbp+0D8h]
0x18003dd9d  test    rcx, rcx
0x18003dda0  jz      loc_18003DF65
0x18003dda6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003ddaa  inc     rax
0x18003ddad  cmp     [rcx+rax*2], r14w
0x18003ddb2  jnz     short loc_18003DDAA
0x18003ddb4  mov     [rbp+0D0h+var_90], rcx
0x18003ddb8  mov     [rbp+0D0h+var_88], rax
0x18003ddbc  lea     rdx, [rbp+0D0h+var_90]
0x18003ddc0  lea     rcx, [rbp+0D0h+var_70]
0x18003ddc4  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@V?$basic_string_view@GU?$char_traits@G@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::basic_string_view<ushort>,std::filesystem::_Normal_conversion)
0x18003ddc9  nop
0x18003ddca  lea     rdx, [rbp+0D0h+var_70]
0x18003ddce  lea     rcx, [rbp+0D0h+var_50]
0x18003ddd5  call    ?canonical@filesystem@std@@YA?AVpath@12@AEBV312@@Z; std::filesystem::canonical(std::filesystem::path const &)
0x18003ddda  nop
0x18003dddb  lea     rcx, [rbp+0D0h+var_70]; void *
0x18003dddf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003dde4  cmp     [rbp+0D0h+var_40], r14
0x18003ddeb  setz    al
0x18003ddee  mov     rcx, [rbp+0D8h]; this
0x18003ddf5  test    al, al
0x18003ddf7  jnz     loc_18003DE9C
0x18003ddfd  lea     rdx, [rbp+0D0h+var_50]
0x18003de04  lea     rcx, [rbp+0D0h+var_90]
0x18003de08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003de0d  lea     rdx, [rbp+0D0h+var_90]
0x18003de11  mov     rcx, rsi
0x18003de14  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18003de19  lea     rcx, [rbp+0D0h+var_90]; void *
0x18003de1d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003de22  nop
0x18003de23  lea     rcx, [rbp+0D0h+var_50]; void *
0x18003de2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003de2f  nop
0x18003de30  mov     rcx, qword ptr [rsp+1D0h+var_178+8]
0x18003de35  mov     qword ptr [rsp+1D0h+var_178+8], r14
0x18003de3a  test    rcx, rcx
0x18003de3d  jz      short loc_18003DE4C
0x18003de3f  call    cs:__imp_SRCache_Free
0x18003de46  nop     dword ptr [rax+rax+00h]
0x18003de4b  nop
0x18003de4c  lea     rcx, [rsp+1D0h+var_160]; this
0x18003de51  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x18003de56  nop
0x18003de57  lea     rcx, [rbp+0D0h+var_F0]; this
0x18003de5b  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x18003de60  nop
0x18003de61  mov     rcx, [rsp+1D0h+var_198]
0x18003de66  mov     [rsp+1D0h+var_198], r14
0x18003de6b  test    rcx, rcx
0x18003de6e  jz      short loc_18003DE7C
0x18003de70  call    cs:__imp_SRCacheManager_Close
0x18003de77  nop     dword ptr [rax+rax+00h]
0x18003de7c  mov     al, 1
0x18003de7e  mov     rcx, [rbp+0D0h+var_30]
0x18003de85  xor     rcx, rsp; StackCookie
0x18003de88  call    __security_check_cookie
0x18003de8d  add     rsp, 1B0h
0x18003de94  pop     r14
0x18003de96  pop     rdi
0x18003de97  pop     rsi
0x18003de98  pop     rbx
0x18003de99  pop     rbp
0x18003de9a  retn
0x18003de9c  mov     r9d, 80070490h; char *
0x18003dea2  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003dea9  mov     edx, 23Fh; void *
0x18003deae  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003deb4  mov     r9d, eax; char *
0x18003deb7  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003debe  mov     edx, 21Dh; void *
0x18003dec3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003dec9  mov     r9d, eax; char *
0x18003decc  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003ded3  mov     edx, 220h; void *
0x18003ded8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003dede  mov     r9d, 80070002h; char *
0x18003dee4  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003deeb  mov     edx, 221h; void *
0x18003def0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003def6  mov     r9d, eax; char *
0x18003def9  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df00  mov     edx, 227h; void *
0x18003df05  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003df0b  mov     r9d, 80070490h; char *
0x18003df11  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df18  mov     edx, 228h; void *
0x18003df1d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003df23  mov     r9d, ebx; char *
0x18003df26  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df2d  mov     edx, 22Bh; void *
0x18003df32  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003df38  mov     r9d, 80070490h; char *
0x18003df3e  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df45  mov     edx, 22Ch; void *
0x18003df4a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003df50  mov     r9d, eax; char *
0x18003df53  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df5a  mov     edx, 237h; void *
0x18003df5f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003df65  mov     r9d, 80070490h; char *
0x18003df6b  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appmodel\\execmodel\\des"...
0x18003df72  mov     edx, 23Ch; void *
0x18003df77  mov     rcx, rax; this
0x18003df7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
