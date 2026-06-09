# StateRepository::Cache::Entity::User_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)

- ea: `0x18009efbc`
- end: `0x18009f273`
- name: `?Get@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `695`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18009f27c`

## callees

- `0x18000b3c9`
- `0x18000e214`
- `0x18000e234`
- `0x180015400`
- `0x18009efbc`
- `0x18009fa20`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f181`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18009f219`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f1f2`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18009f1f2`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009f142`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18009f142`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009f082`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18009f082`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f046`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f1d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f24f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f046`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f1d5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18009f24f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f19b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f233`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f103`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f19b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18009f233`

## string_xrefs

- `0x18009f09b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18009efee`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009f027`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009f0e1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009f165`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009f1b6`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18009f077`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  unsigned int LastError; // ebx
  bool *v9; // rdi
  int v10; // eax
  __int64 v11; // rcx
  int Field_String; // eax
  LPCWSTR v13; // rcx
  LPCWSTR v14; // rcx
  LPCWSTR v15; // rcx
  BOOL v16; // ebx
  const char *v17; // r9
  LPCWSTR v18; // rcx
  __int64 v19; // rcx
  HLOCAL v20; // rbx
  DWORD LengthSid; // eax
  bool v22; // zf
  HLOCAL hMem; // [rsp+20h] [rbp-40h] BYREF
  LPCWSTR *p_StringSid; // [rsp+28h] [rbp-38h]
  const WCHAR *v25; // [rsp+30h] [rbp-30h] BYREF
  char v26; // [rsp+38h] [rbp-28h]
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  PSID Sid; // [rsp+48h] [rbp-18h] BYREF
  char v29; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  LPCWSTR StringSid; // [rsp+98h] [rbp+38h] BYREF
  __int64 v32; // [rsp+A0h] [rbp+40h] BYREF

  v32 = a3;
  if ( !a2 )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)0x80070057LL,
      (int)hMem);
    return LastError;
  }
  v32 = 0;
  v9 = a5;
  v10 = StateRepository::Cache::Entity::User_NoThrow::Open(
          a1,
          a2,
          (struct StateRepository::Cache::Context_NoThrow *)&v32,
          a5);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v10,
      (int)hMem);
    v11 = v32;
    v32 = 0;
    if ( v11 )
      SRCacheContext_Close();
    return LastError;
  }
  if ( *v9 )
  {
    StringSid = 0;
    p_StringSid = &StringSid;
    v25 = 0;
    v26 = 1;
    Field_String = SRCacheContext_GetField_String(v32, L"UserSid", &v25);
    LastError = Field_String;
    if ( Field_String >= 0 )
      LastError = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x246,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_String,
        (int)hMem);
    if ( v26 )
    {
      v13 = *p_StringSid;
      *p_StringSid = v25;
      if ( v13 )
        SRCache_Free();
    }
    if ( (LastError & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x347,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)LastError,
        (int)hMem);
      v14 = StringSid;
      StringSid = 0;
      if ( v14 )
        SRCache_Free();
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
        (const char *)LastError,
        (int)hMem);
      v19 = v32;
      v32 = 0;
      if ( v19 )
        SRCacheContext_Close();
      return LastError;
    }
    v15 = StringSid;
    if ( !StringSid )
    {
      a4[10] = 0;
LABEL_32:
      StringSid = 0;
      if ( v15 )
        SRCache_Free();
      *a4 = a2;
      goto LABEL_35;
    }
    hMem = 0;
    p_hMem = &hMem;
    Sid = 0;
    v29 = 1;
    v16 = ConvertStringSidToSidW(StringSid, &Sid);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hMem);
    if ( v16 )
    {
      v20 = hMem;
      LengthSid = GetLengthSid(hMem);
      memcpy_0(a4 + 1, v20, LengthSid);
      a4[10] = (__int64)(a4 + 1);
      if ( hMem )
        LocalFree(hMem);
      v15 = StringSid;
      goto LABEL_32;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x34F,
                  (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
                  v17);
    if ( hMem )
      LocalFree(hMem);
    v18 = StringSid;
    StringSid = 0;
    if ( v18 )
      SRCache_Free();
    if ( (LastError & 0x80000000) != 0 )
      goto LABEL_26;
  }
LABEL_35:
  v22 = v32 == 0;
  v32 = 0;
  if ( !v22 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x18009efbc  mov     [rsp-28h+arg_0], rbx
0x18009efc1  mov     [rsp-28h+arg_10], r8
0x18009efc6  push    rbp
0x18009efc7  push    rsi
0x18009efc8  push    rdi
0x18009efc9  push    r14
0x18009efcb  push    r15
0x18009efcd  mov     rbp, rsp
0x18009efd0  sub     rsp, 60h
0x18009efd4  mov     rsi, r9
0x18009efd7  mov     r14, rdx
0x18009efda  xor     r15d, r15d
0x18009efdd  test    rdx, rdx
0x18009efe0  jnz     short loc_18009F006
0x18009efe2  mov     rcx, [rbp+28h]; this
0x18009efe6  mov     ebx, 80070057h
0x18009efeb  mov     r9d, ebx; char *
0x18009efee  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009eff5  mov     edx, 98h; void *
0x18009effa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009efff  mov     eax, ebx
0x18009f001  jmp     loc_18009F25E
0x18009f006  mov     [rbp+arg_10], r15
0x18009f00a  mov     rdi, [rbp+arg_20]
0x18009f00e  mov     r9, rdi; bool *
0x18009f011  lea     r8, [rbp+arg_10]; this
0x18009f015  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18009f01a  mov     ebx, eax
0x18009f01c  test    eax, eax
0x18009f01e  jns     short loc_18009F055
0x18009f020  mov     rcx, [rbp+28h]; this
0x18009f024  mov     r9d, eax; char *
0x18009f027  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f02e  mov     edx, 9Bh; void *
0x18009f033  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f038  nop
0x18009f039  mov     rcx, [rbp+arg_10]
0x18009f03d  mov     [rbp+arg_10], r15
0x18009f041  test    rcx, rcx
0x18009f044  jz      short loc_18009F053
0x18009f046  call    cs:__imp_SRCacheContext_Close
0x18009f04d  nop     dword ptr [rax+rax+00h]
0x18009f052  nop
0x18009f053  jmp     short loc_18009EFFF
0x18009f055  cmp     [rdi], r15b
0x18009f058  jnz     short loc_18009F05F
0x18009f05a  jmp     loc_18009F242
0x18009f05f  mov     [rbp+StringSid], r15
0x18009f063  lea     rax, [rbp+StringSid]
0x18009f067  mov     [rbp+var_38], rax
0x18009f06b  mov     [rbp+var_30], r15
0x18009f06f  mov     [rbp+var_28], 1
0x18009f073  lea     r8, [rbp+var_30]
0x18009f077  lea     rdx, aUsersid; "UserSid"
0x18009f07e  mov     rcx, [rbp+arg_10]
0x18009f082  call    cs:__imp_SRCacheContext_GetField_String
0x18009f089  nop     dword ptr [rax+rax+00h]
0x18009f08e  mov     ebx, eax
0x18009f090  test    eax, eax
0x18009f092  jns     short loc_18009F0AE
0x18009f094  mov     rcx, [rbp+28h]; this
0x18009f098  mov     r9d, eax; char *
0x18009f09b  lea     r8, aOnecorePrivate_16; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f0a2  mov     edx, 246h; void *
0x18009f0a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f0ac  jmp     short loc_18009F0B1
0x18009f0ae  mov     ebx, r15d
0x18009f0b1  cmp     [rbp+var_28], r15b
0x18009f0b5  jz      short loc_18009F0D6
0x18009f0b7  mov     rdx, [rbp+var_38]
0x18009f0bb  mov     rcx, [rdx]
0x18009f0be  mov     rax, [rbp+var_30]
0x18009f0c2  mov     [rdx], rax
0x18009f0c5  test    rcx, rcx
0x18009f0c8  jz      short loc_18009F0D6
0x18009f0ca  call    cs:__imp_SRCache_Free
0x18009f0d1  nop     dword ptr [rax+rax+00h]
0x18009f0d6  test    ebx, ebx
0x18009f0d8  jns     short loc_18009F114
0x18009f0da  mov     rcx, [rbp+28h]; this
0x18009f0de  mov     r9d, ebx; char *
0x18009f0e1  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f0e8  mov     edx, 347h; void *
0x18009f0ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f0f2  mov     rcx, [rbp+StringSid]
0x18009f0f6  mov     [rbp+StringSid], r15
0x18009f0fa  test    rcx, rcx
0x18009f0fd  jz      loc_18009F1AF
0x18009f103  call    cs:__imp_SRCache_Free
0x18009f10a  nop     dword ptr [rax+rax+00h]
0x18009f10f  jmp     loc_18009F1AF
0x18009f114  mov     rcx, [rbp+StringSid]
0x18009f118  test    rcx, rcx
0x18009f11b  jnz     short loc_18009F126
0x18009f11d  mov     [rsi+50h], r15
0x18009f121  jmp     loc_18009F22A
0x18009f126  mov     [rbp+hMem], r15
0x18009f12a  lea     rax, [rbp+hMem]
0x18009f12e  mov     [rbp+var_20], rax
0x18009f132  mov     [rbp+Sid], r15
0x18009f136  mov     [rbp+var_10], 1
0x18009f13a  lea     rdx, [rbp+Sid]; Sid
0x18009f13e  mov     rcx, [rbp+StringSid]; StringSid
0x18009f142  call    cs:__imp_ConvertStringSidToSidW
0x18009f149  nop     dword ptr [rax+rax+00h]
0x18009f14e  mov     ebx, eax
0x18009f150  lea     rcx, [rbp+var_20]
0x18009f154  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009f159  test    ebx, ebx
0x18009f15b  jnz     loc_18009F1E7
0x18009f161  mov     rcx, [rbp+28h]; this
0x18009f165  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f16c  mov     edx, 34Fh; void *
0x18009f171  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009f176  mov     ebx, eax
0x18009f178  mov     rcx, [rbp+hMem]; hMem
0x18009f17c  test    rcx, rcx
0x18009f17f  jz      short loc_18009F18E
0x18009f181  call    cs:__imp_LocalFree
0x18009f188  nop     dword ptr [rax+rax+00h]
0x18009f18d  nop
0x18009f18e  mov     rcx, [rbp+StringSid]
0x18009f192  mov     [rbp+StringSid], r15
0x18009f196  test    rcx, rcx
0x18009f199  jz      short loc_18009F1A7
0x18009f19b  call    cs:__imp_SRCache_Free
0x18009f1a2  nop     dword ptr [rax+rax+00h]
0x18009f1a7  test    ebx, ebx
0x18009f1a9  jns     loc_18009F242
0x18009f1af  mov     rcx, [rbp+28h]; this
0x18009f1b3  mov     r9d, ebx; char *
0x18009f1b6  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18009f1bd  mov     edx, 0A0h; void *
0x18009f1c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f1c7  nop
0x18009f1c8  mov     rcx, [rbp+arg_10]
0x18009f1cc  mov     [rbp+arg_10], r15
0x18009f1d0  test    rcx, rcx
0x18009f1d3  jz      short loc_18009F1E2
0x18009f1d5  call    cs:__imp_SRCacheContext_Close
0x18009f1dc  nop     dword ptr [rax+rax+00h]
0x18009f1e1  nop
0x18009f1e2  jmp     loc_18009EFFF
0x18009f1e7  mov     rbx, [rbp+hMem]
0x18009f1eb  lea     rdi, [rsi+8]
0x18009f1ef  mov     rcx, rbx; pSid
0x18009f1f2  call    cs:__imp_GetLengthSid
0x18009f1f9  nop     dword ptr [rax+rax+00h]
0x18009f1fe  mov     r8d, eax; Size
0x18009f201  mov     rdx, rbx; Src
0x18009f204  mov     rcx, rdi; void *
0x18009f207  call    memcpy_0
0x18009f20c  mov     [rsi+50h], rdi
0x18009f210  mov     rcx, [rbp+hMem]; hMem
0x18009f214  test    rcx, rcx
0x18009f217  jz      short loc_18009F226
0x18009f219  call    cs:__imp_LocalFree
0x18009f220  nop     dword ptr [rax+rax+00h]
0x18009f225  nop
0x18009f226  mov     rcx, [rbp+StringSid]
0x18009f22a  mov     [rbp+StringSid], r15
0x18009f22e  test    rcx, rcx
0x18009f231  jz      short loc_18009F23F
0x18009f233  call    cs:__imp_SRCache_Free
0x18009f23a  nop     dword ptr [rax+rax+00h]
0x18009f23f  mov     [rsi], r14
0x18009f242  mov     rcx, [rbp+arg_10]
0x18009f246  test    rcx, rcx
0x18009f249  mov     [rbp+arg_10], r15
0x18009f24d  jz      short loc_18009F25C
0x18009f24f  call    cs:__imp_SRCacheContext_Close
0x18009f256  nop     dword ptr [rax+rax+00h]
0x18009f25b  nop
0x18009f25c  xor     eax, eax
0x18009f25e  mov     rbx, [rsp+60h+arg_0]
0x18009f266  add     rsp, 60h
0x18009f26a  pop     r15
0x18009f26c  pop     r14
0x18009f26e  pop     rdi
0x18009f26f  pop     rsi
0x18009f270  pop     rbp
0x18009f271  retn
```
