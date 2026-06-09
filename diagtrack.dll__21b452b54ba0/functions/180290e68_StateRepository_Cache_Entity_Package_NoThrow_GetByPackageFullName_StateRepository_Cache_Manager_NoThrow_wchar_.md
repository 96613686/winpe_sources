# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,wchar_t const *,__int64 &)

- ea: `0x180290e68`
- end: `0x18029111f`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEB_WAEA_J@Z`
- size: `695`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const wchar_t *, __int64 *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180291e64`

## callees

- `0x180064e8c`
- `0x18020aac0`
- `0x18020bab8`
- `0x18028605c`
- `0x18028784c`
- `0x18028788c`
- `0x180290e68`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180290fbc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802910e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180290fbc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802910e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180290ec6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180290ec6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180291072`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180291072`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180290f21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180291053`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802910d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802910fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180290f21`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180291053`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802910d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802910fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180290ff4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180290ff4`

## string_xrefs

- `0x180290ee3`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180291011`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180291085`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180290f03`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180290f95`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180291031`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const wchar_t *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int *v22; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v24 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v20 = 0;
  v22 = v20;
  v23 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v7 = 1128;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
LABEL_4:
    v9 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v9 )
      SRCacheContext_Close(v9, v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v20 )
  {
    v6 = -2140733422;
    v7 = 1129;
    goto LABEL_3;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      v20[0]);
LABEL_11:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCache_Free();
    goto LABEL_4;
  }
  v22 = (int *)&v21;
  v21 = 0;
  v23 = 0;
  v24 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v29, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v22);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v13 = 1136;
    goto LABEL_15;
  }
  if ( v21 )
  {
    v15 = SRCacheContext_EnumerateData(v21, 0, a3);
    v6 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v15,
        v20[0]);
      v13 = 1139;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"Package\\Index\\PackageFullName");
  if ( v6 < 0 )
  {
    v13 = 1142;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v14 = v21;
    v21 = 0;
    if ( v14 )
      SRCacheContext_Close(v14, v8);
    goto LABEL_11;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    ((void (*)(void))SRCacheContext_Close)();
  v18 = v25;
  v25 = 0;
  if ( v18 )
    SRCache_Free();
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19, v16);
  return 0;
}

```

## disassembly

```asm
0x180290e68  push    rbp
0x180290e6a  push    rbx
0x180290e6b  push    rsi
0x180290e6c  push    rdi
0x180290e6d  push    r14
0x180290e6f  lea     rbp, [rsp-180h]
0x180290e77  sub     rsp, 280h
0x180290e7e  mov     rax, cs:__security_cookie
0x180290e85  xor     rax, rsp
0x180290e88  mov     [rbp+1A0h+var_30], rax
0x180290e8f  xor     r14d, r14d
0x180290e92  mov     [rsp+2A0h+var_260], 1
0x180290e97  mov     [r8], r14
0x180290e9a  lea     rax, [rsp+2A0h+var_280]
0x180290e9f  mov     rcx, [rcx]
0x180290ea2  lea     r9, [rsp+2A0h+var_268]
0x180290ea7  mov     rdi, r8
0x180290eaa  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180290eaf  mov     rsi, rdx
0x180290eb2  mov     [rsp+2A0h+var_270], rax
0x180290eb7  xor     r8d, r8d
0x180290eba  mov     [rsp+2A0h+var_268], r14
0x180290ebf  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x180290ec6  call    cs:__imp_SRCacheContext_Open
0x180290ecc  lea     rcx, [rsp+2A0h+var_270]
0x180290ed1  mov     ebx, eax
0x180290ed3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180290ed8  test    ebx, ebx
0x180290eda  jns     short loc_180290F2E
0x180290edc  mov     rcx, [rbp+1A8h]; this
0x180290ee3  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180290eea  mov     r9d, ebx; char *
0x180290eed  mov     edx, 18Ch; void *
0x180290ef2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180290ef7  mov     edx, 468h; void *
0x180290efc  mov     rcx, [rbp+1A8h]; this
0x180290f03  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180290f0a  mov     r9d, ebx; char *
0x180290f0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180290f12  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180290f17  mov     qword ptr [rsp+2A0h+var_280], r14
0x180290f1c  test    rcx, rcx
0x180290f1f  jz      short loc_180290F27
0x180290f21  call    cs:__imp_SRCacheContext_Close
0x180290f27  mov     eax, ebx
0x180290f29  jmp     loc_180291102
0x180290f2e  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180290f33  setnz   al
0x180290f36  test    al, al
0x180290f38  jnz     short loc_180290F46
0x180290f3a  mov     ebx, 80670012h
0x180290f3f  mov     edx, 469h
0x180290f44  jmp     short loc_180290EFC
0x180290f46  xor     edx, edx; Val
0x180290f48  mov     [rsp+2A0h+var_250], r14
0x180290f4d  mov     r8d, 200h; Size
0x180290f53  lea     rcx, [rsp+2A0h+var_248]; void *
0x180290f58  call    memset_0
0x180290f5d  lea     rax, [rsp+2A0h+var_248]
0x180290f62  mov     [rbp+1A0h+var_48], r14
0x180290f69  mov     rdx, rsi; wchar_t *
0x180290f6c  mov     [rbp+1A0h+var_38], rax
0x180290f73  lea     rcx, [rsp+2A0h+var_250]; this
0x180290f78  mov     [rbp+1A0h+var_40], 100h
0x180290f83  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x180290f88  mov     ebx, eax
0x180290f8a  test    eax, eax
0x180290f8c  jns     short loc_180290FC7
0x180290f8e  mov     rcx, [rbp+1A8h]; this
0x180290f95  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180290f9c  mov     r9d, eax; char *
0x180290f9f  mov     edx, 46Ch; void *
0x180290fa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180290fa9  mov     rcx, [rsp+2A0h+var_250]
0x180290fae  mov     [rsp+2A0h+var_250], r14
0x180290fb3  test    rcx, rcx
0x180290fb6  jz      loc_180290F12
0x180290fbc  call    cs:__imp_SRCache_Free
0x180290fc2  jmp     loc_180290F12
0x180290fc7  mov     rdx, [rbp+1A0h+var_38]
0x180290fce  lea     rax, [rsp+2A0h+var_278]
0x180290fd3  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180290fd8  lea     r9, [rsp+2A0h+var_268]
0x180290fdd  xor     r8d, r8d
0x180290fe0  mov     [rsp+2A0h+var_270], rax
0x180290fe5  mov     [rsp+2A0h+var_278], r14
0x180290fea  mov     [rsp+2A0h+var_268], r14
0x180290fef  mov     [rsp+2A0h+var_260], 1
0x180290ff4  call    cs:__imp_SRCacheContext_OpenSubContext
0x180290ffa  lea     rcx, [rsp+2A0h+var_270]
0x180290fff  mov     ebx, eax
0x180291001  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180291006  test    ebx, ebx
0x180291008  jns     short loc_18029105E
0x18029100a  mov     rcx, [rbp+1A8h]; this
0x180291011  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180291018  mov     r9d, ebx; char *
0x18029101b  mov     edx, 1B0h; void *
0x180291020  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180291025  mov     edx, 470h; void *
0x18029102a  mov     rcx, [rbp+1A8h]; this
0x180291031  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180291038  mov     r9d, ebx; char *
0x18029103b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180291040  mov     rcx, [rsp+2A0h+var_278]
0x180291045  mov     [rsp+2A0h+var_278], r14
0x18029104a  test    rcx, rcx
0x18029104d  jz      loc_180290FA9
0x180291053  call    cs:__imp_SRCacheContext_Close
0x180291059  jmp     loc_180290FA9
0x18029105e  mov     rcx, [rsp+2A0h+var_278]
0x180291063  test    rcx, rcx
0x180291066  setnz   al
0x180291069  test    al, al
0x18029106b  jz      short loc_1802910A0
0x18029106d  mov     r8, rdi
0x180291070  xor     edx, edx
0x180291072  call    cs:__imp_SRCacheContext_EnumerateData
0x180291078  mov     ebx, eax
0x18029107a  test    eax, eax
0x18029107c  jns     short loc_1802910A0
0x18029107e  mov     rcx, [rbp+1A8h]; this
0x180291085  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x18029108c  mov     r9d, eax; char *
0x18029108f  mov     edx, 2A6h; void *
0x180291094  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180291099  mov     edx, 473h
0x18029109e  jmp     short loc_18029102A
0x1802910a0  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x1802910a7  lea     rcx, [rsp+2A0h+var_280]; this
0x1802910ac  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802910b1  mov     ebx, eax
0x1802910b3  test    eax, eax
0x1802910b5  jns     short loc_1802910C1
0x1802910b7  mov     edx, 476h
0x1802910bc  jmp     loc_18029102A
0x1802910c1  mov     rcx, [rsp+2A0h+var_278]
0x1802910c6  mov     [rsp+2A0h+var_278], r14
0x1802910cb  test    rcx, rcx
0x1802910ce  jz      short loc_1802910D6
0x1802910d0  call    cs:__imp_SRCacheContext_Close
0x1802910d6  mov     rcx, [rsp+2A0h+var_250]
0x1802910db  mov     [rsp+2A0h+var_250], r14
0x1802910e0  test    rcx, rcx
0x1802910e3  jz      short loc_1802910EB
0x1802910e5  call    cs:__imp_SRCache_Free
0x1802910eb  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802910f0  mov     qword ptr [rsp+2A0h+var_280], r14
0x1802910f5  test    rcx, rcx
0x1802910f8  jz      short loc_180291100
0x1802910fa  call    cs:__imp_SRCacheContext_Close
0x180291100  xor     eax, eax
0x180291102  mov     rcx, [rbp+1A0h+var_30]
0x180291109  xor     rcx, rsp; StackCookie
0x18029110c  call    __security_check_cookie
0x180291111  add     rsp, 280h
0x180291118  pop     r14
0x18029111a  pop     rdi
0x18029111b  pop     rsi
0x18029111c  pop     rbx
0x18029111d  pop     rbp
0x18029111e  retn
```
