# CDoc::AttemptBFCacheNavigation(ulong,ulong)

- ea: `0x1808491a4`
- end: `0x18084944a`
- name: `?AttemptBFCacheNavigation@CDoc@@QEAAJKK@Z`
- size: `678`
- prototype: `__int64 __fastcall(struct IUnknown **this, int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1806d4ea8`
- `0x180883d20`

## callees

- `0x1805f2dec`
- `0x1805f7f7c`
- `0x1808491a4`
- `0x181091fe4`
- `0x1810f6516`
- `0x1810f65c0`
- `0x181104010`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18084922a`
- `KERNEL32!GetCurrentProcessId` at `0x18084922a`
- `KERNEL32!GetCurrentThreadId` at `0x1808491d8`
- `KERNEL32!GetCurrentThreadId` at `0x18084927f`
- `KERNEL32!GetCurrentThreadId` at `0x1808491d8`
- `KERNEL32!GetCurrentThreadId` at `0x18084927f`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18084936c`
- `iertutil!__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z` at `0x18084936c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18084925c`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x18084925c`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180849299`
- `msIso!__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z` at `0x180849299`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084926b`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x18084926b`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18084923e`
- `msIso!__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z` at `0x18084923e`
- `OLEAUT32!__imp_VariantInit` at `0x1808492e8`
- `OLEAUT32!__imp_VariantInit` at `0x180849338`
- `OLEAUT32!__imp_VariantInit` at `0x1808492e8`
- `OLEAUT32!__imp_VariantInit` at `0x180849338`
- `OLEAUT32!__imp_VariantClear` at `0x180849349`
- `OLEAUT32!__imp_VariantClear` at `0x180849349`

## pseudocode

```c
__int64 __fastcall CDoc::AttemptBFCacheNavigation(struct IUnknown **this, int a2, unsigned int a3)
{
  int v6; // ebx
  DWORD CurrentThreadId; // eax
  bool *v8; // r9
  char Integrity; // al
  DWORD v10; // eax
  unsigned int v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  struct IEUserBroker *v14; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v17[80]; // [rsp+70h] [rbp-90h] BYREF
  LONGLONG llVal; // [rsp+C0h] [rbp-40h]
  __int128 v19; // [rsp+100h] [rbp+0h] BYREF
  int v20; // [rsp+110h] [rbp+10h]
  unsigned int v21; // [rsp+120h] [rbp+20h] BYREF
  int v22; // [rsp+124h] [rbp+24h]
  DWORD CurrentProcessId; // [rsp+138h] [rbp+38h]
  int v24; // [rsp+13Ch] [rbp+3Ch]
  int v25; // [rsp+140h] [rbp+40h]
  int DWORD; // [rsp+148h] [rbp+48h]
  __int128 v27; // [rsp+154h] [rbp+54h]

  LOBYTE(v12) = 0;
  v6 = -2147467259;
  CurrentThreadId = GetCurrentThreadId();
  BFCacheUtils::IsAdvertisedBFCacheCookie((BFCacheUtils *)a3, CurrentThreadId, (unsigned int)&v12, v8);
  if ( (_BYTE)v12 )
  {
    memset_0(v17, 0, 0x90u);
    v20 = 0;
    v19 = 0;
    memset_0(&v21, 0, 0x44u);
    CurrentProcessId = GetCurrentProcessId();
    Integrity = IsoGetIntegrity(1);
    v25 = 0;
    v24 = Integrity & 0x7F;
    DWORD = IEConfiguration_GetDWORD(536870929);
    v27 = *(_OWORD *)GlobalThreadState();
    v10 = GetCurrentThreadId();
    LCIEGetTypedComponentFromThread(0x203u, v10, &v21, 0);
    v22 |= a2;
    LODWORD(v19) = 3;
    HIDWORD(v19) = a3;
    if ( !(unsigned int)CDoc::CheckBFCacheCandidacy((__int64)this, 0x3038E7F1u) )
      v22 |= 0x40000u;
    if ( this[8] )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      if ( (int)CTExec(this[8], &CGID_Explorer, 0x78u, 0, 0, &pvarg) >= 0 )
      {
        if ( pvarg.vt == 8 )
        {
          llVal = pvarg.llVal;
          VariantInit(&pvarg);
        }
        VariantClear(&pvarg);
      }
    }
    v15 = 0;
    v14 = 0;
    v6 = CoCreateUserBroker(&v14);
    if ( v6 >= 0 )
    {
      v13 = 0;
      v6 = (*(__int64 (__fastcall **)(struct IEUserBroker *, GUID *, GUID *, __int64 *))(*(_QWORD *)v14 + 48LL))(
             v14,
             &CLSID_CShdocvwBroker,
             &IID_IUnknown,
             &v13);
      if ( v6 >= 0 )
      {
        v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v13)(
               v13,
               &GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42,
               &v15);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
      (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)v14 + 16LL))(v14);
      if ( v6 >= 0 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *, unsigned int *, __int128 *))(*(_QWORD *)v15 + 1144LL))(
               v15,
               v17,
               &v21,
               &v19);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1808491a4  push    rbp
0x1808491a6  push    rbx
0x1808491a7  push    rsi
0x1808491a8  push    rdi
0x1808491a9  push    r14
0x1808491ab  lea     rbp, [rsp-80h]
0x1808491b0  sub     rsp, 180h
0x1808491b7  mov     rax, cs:__security_cookie
0x1808491be  xor     rax, rsp
0x1808491c1  mov     [rbp+0A0h+var_30], rax
0x1808491c5  mov     esi, r8d
0x1808491c8  mov     byte ptr [rsp+1A0h+var_170], 0
0x1808491cd  mov     r14d, edx
0x1808491d0  mov     rdi, rcx
0x1808491d3  mov     ebx, 80004005h
0x1808491d8  call    cs:__imp_GetCurrentThreadId
0x1808491df  nop     dword ptr [rax+rax+00h]
0x1808491e4  lea     r8, [rsp+1A0h+var_170]; unsigned int
0x1808491e9  mov     ecx, esi; this
0x1808491eb  mov     edx, eax; unsigned int
0x1808491ed  call    ?IsAdvertisedBFCacheCookie@BFCacheUtils@@YAJKKPEA_N@Z; BFCacheUtils::IsAdvertisedBFCacheCookie(ulong,ulong,bool *)
0x1808491f2  cmp     byte ptr [rsp+1A0h+var_170], 0
0x1808491f7  jz      loc_18084942D
0x1808491fd  xor     edx, edx; Val
0x1808491ff  lea     rcx, [rsp+1A0h+var_130]; void *
0x180849204  mov     r8d, 90h; Size
0x18084920a  call    memset_0
0x18084920f  xor     eax, eax
0x180849211  lea     rcx, [rbp+0A0h+var_80]; void *
0x180849215  xorps   xmm0, xmm0
0x180849218  mov     [rbp+0A0h+var_90], eax
0x18084921b  xor     edx, edx; Val
0x18084921d  movups  [rbp+0A0h+var_A0], xmm0
0x180849221  lea     r8d, [rax+44h]; Size
0x180849225  call    memset_0
0x18084922a  call    cs:__imp_GetCurrentProcessId
0x180849231  nop     dword ptr [rax+rax+00h]
0x180849236  mov     ecx, 1
0x18084923b  mov     [rbp+0A0h+var_68], eax
0x18084923e  call    cs:__imp_?IsoGetIntegrity@@YA?AW4_IsoIntegrity@@K@Z; IsoGetIntegrity(ulong)
0x180849245  nop     dword ptr [rax+rax+00h]
0x18084924a  mov     ecx, 20000011h
0x18084924f  mov     [rbp+0A0h+var_60], 0
0x180849256  and     eax, 7Fh
0x180849259  mov     [rbp+0A0h+var_64], eax
0x18084925c  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x180849263  nop     dword ptr [rax+rax+00h]
0x180849268  mov     [rbp+0A0h+var_58], eax
0x18084926b  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180849272  nop     dword ptr [rax+rax+00h]
0x180849277  movups  xmm0, xmmword ptr [rax]
0x18084927a  movdqu  [rbp+0A0h+var_4C], xmm0
0x18084927f  call    cs:__imp_GetCurrentThreadId
0x180849286  nop     dword ptr [rax+rax+00h]
0x18084928b  xor     r9d, r9d
0x18084928e  lea     r8, [rbp+0A0h+var_80]
0x180849292  mov     edx, eax
0x180849294  mov     ecx, 203h
0x180849299  call    cs:__imp_?LCIEGetTypedComponentFromThread@@YAJKKPEAKPEAPEAU_IsoComponent@@@Z; LCIEGetTypedComponentFromThread(ulong,ulong,ulong *,_IsoComponent * *)
0x1808492a0  nop     dword ptr [rax+rax+00h]
0x1808492a5  or      [rbp+0A0h+var_7C], r14d
0x1808492a9  mov     edx, 3038E7F1h
0x1808492ae  mov     rcx, rdi
0x1808492b1  mov     dword ptr [rbp+0A0h+var_A0], 3
0x1808492b8  mov     dword ptr [rbp+0A0h+var_A0+0Ch], esi
0x1808492bb  call    ?CheckBFCacheCandidacy@CDoc@@QEAA?AW4tagBFCACHE_CANDIDACY_FAILURE_FLAGS@@W42@@Z; CDoc::CheckBFCacheCandidacy(tagBFCACHE_CANDIDACY_FAILURE_FLAGS)
0x1808492c0  test    eax, eax
0x1808492c2  jnz     short loc_1808492C9
0x1808492c4  bts     [rbp+0A0h+var_7C], 12h
0x1808492c9  cmp     qword ptr [rdi+40h], 0
0x1808492ce  jz      loc_180849355
0x1808492d4  xorps   xmm0, xmm0
0x1808492d7  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x1808492dc  xor     eax, eax
0x1808492de  movups  xmmword ptr [rsp+1A0h+pvarg], xmm0
0x1808492e3  mov     qword ptr [rsp+1A0h+pvarg+10h], rax
0x1808492e8  call    cs:__imp_VariantInit
0x1808492ef  nop     dword ptr [rax+rax+00h]
0x1808492f4  mov     rcx, [rdi+40h]; struct IUnknown *
0x1808492f8  lea     rax, [rsp+1A0h+pvarg]
0x1808492fd  xor     r9d, r9d; unsigned int
0x180849300  mov     [rsp+1A0h+var_178], rax; struct tagVARIANT *
0x180849305  lea     rdx, CGID_Explorer; struct _GUID *
0x18084930c  mov     [rsp+1A0h+var_180], 0; struct tagVARIANT *
0x180849315  lea     r8d, [r9+78h]; unsigned int
0x180849319  call    ?CTExec@@YAJPEAUIUnknown@@PEBU_GUID@@KKPEAUtagVARIANT@@2@Z; CTExec(IUnknown *,_GUID const *,ulong,ulong,tagVARIANT *,tagVARIANT *)
0x18084931e  test    eax, eax
0x180849320  js      short loc_180849355
0x180849322  cmp     word ptr [rsp+1A0h+pvarg], 8
0x180849328  jnz     short loc_180849344
0x18084932a  mov     rax, qword ptr [rsp+1A0h+pvarg+8]
0x18084932f  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x180849334  mov     [rbp+0A0h+var_E0], rax
0x180849338  call    cs:__imp_VariantInit
0x18084933f  nop     dword ptr [rax+rax+00h]
0x180849344  lea     rcx, [rsp+1A0h+pvarg]; pvarg
0x180849349  call    cs:__imp_VariantClear
0x180849350  nop     dword ptr [rax+rax+00h]
0x180849355  lea     rcx, [rsp+1A0h+var_160]
0x18084935a  mov     [rsp+1A0h+var_158], 0
0x180849363  mov     [rsp+1A0h+var_160], 0
0x18084936c  call    cs:__imp_?CoCreateUserBroker@@YAJPEAPEAUIEUserBroker@@@Z; CoCreateUserBroker(IEUserBroker * *)
0x180849373  nop     dword ptr [rax+rax+00h]
0x180849378  mov     ebx, eax
0x18084937a  test    eax, eax
0x18084937c  js      loc_18084942D
0x180849382  mov     rcx, [rsp+1A0h+var_160]
0x180849387  lea     r9, [rsp+1A0h+var_168]
0x18084938c  mov     [rsp+1A0h+var_168], 0
0x180849395  lea     r8, IID_IUnknown
0x18084939c  lea     rdx, CLSID_CShdocvwBroker
0x1808493a3  mov     rax, [rcx]
0x1808493a6  mov     rax, [rax+30h]
0x1808493aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808493af  mov     ebx, eax
0x1808493b1  test    eax, eax
0x1808493b3  js      short loc_1808493E4
0x1808493b5  mov     rcx, [rsp+1A0h+var_168]
0x1808493ba  lea     r8, [rsp+1A0h+var_158]
0x1808493bf  lea     rdx, _GUID_cd45afe8_9a64_402a_8cfd_22bb4ebd8b42
0x1808493c6  mov     rax, [rcx]
0x1808493c9  mov     rax, [rax]
0x1808493cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808493d1  mov     rcx, [rsp+1A0h+var_168]
0x1808493d6  mov     ebx, eax
0x1808493d8  mov     rax, [rcx]
0x1808493db  mov     rax, [rax+10h]
0x1808493df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808493e4  mov     rcx, [rsp+1A0h+var_160]
0x1808493e9  mov     rax, [rcx]
0x1808493ec  mov     rax, [rax+10h]
0x1808493f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1808493f5  test    ebx, ebx
0x1808493f7  js      short loc_18084942D
0x1808493f9  mov     rcx, [rsp+1A0h+var_158]
0x1808493fe  lea     r9, [rbp+0A0h+var_A0]
0x180849402  lea     r8, [rbp+0A0h+var_80]
0x180849406  lea     rdx, [rsp+1A0h+var_130]
0x18084940b  mov     rax, [rcx]
0x18084940e  mov     rax, [rax+478h]
0x180849415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18084941a  mov     rcx, [rsp+1A0h+var_158]
0x18084941f  mov     ebx, eax
0x180849421  mov     rax, [rcx]
0x180849424  mov     rax, [rax+10h]
0x180849428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18084942d  mov     eax, ebx
0x18084942f  mov     rcx, [rbp+0A0h+var_30]
0x180849433  xor     rcx, rsp; StackCookie
0x180849436  call    __security_check_cookie
0x18084943b  add     rsp, 180h
0x180849442  pop     r14
0x180849444  pop     rdi
0x180849445  pop     rsi
0x180849446  pop     rbx
0x180849447  pop     rbp
0x180849448  retn
```
