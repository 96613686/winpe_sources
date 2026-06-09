# TdhpPopulateCacheWithFilterInfo

- ea: `0x180026ba8`
- end: `0x180026cf9`
- name: `TdhpPopulateCacheWithFilterInfo`
- size: `337`
- prototype: `__int64 __fastcall(__int64, unsigned int *, char **, _DWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180026dc8`

## callees

- `0x1800086f4`
- `0x18000872c`
- `0x180009570`
- `0x180009a34`
- `0x180009bdc`
- `0x180017c40`
- `0x180018380`
- `0x1800207c0`
- `0x18002658c`
- `0x180026ba8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TdhpPopulateCacheWithFilterInfo(__int64 a1, unsigned int *a2, char **a3, _DWORD *a4)
{
  const struct _GUID *v7; // r9
  unsigned int v8; // ebx
  void **v10; // [rsp+30h] [rbp-D0h] BYREF
  struct PUBLISHER_LOOKUP_ENTRY near **v11; // [rsp+38h] [rbp-C8h] BYREF
  int v12; // [rsp+40h] [rbp-C0h]
  char v13; // [rsp+44h] [rbp-BCh]
  void ***v14; // [rsp+48h] [rbp-B8h]
  __int64 v15; // [rsp+50h] [rbp-B0h]
  void **v16; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v17; // [rsp+60h] [rbp-A0h]
  __int128 v18; // [rsp+70h] [rbp-90h]
  _QWORD v19[2]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v20[24]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[25]; // [rsp+A8h] [rbp-58h] BYREF

  v19[1] = a1;
  v16 = &PublisherManifestTdhConfig::`vftable';
  v12 = 2;
  v10 = &ModuleLoaderImpl::`vftable';
  v13 = 0;
  v19[0] = &ManifestResourceLoaderImpl::`vftable';
  v14 = &v10;
  v11 = &g_EnvironmentTable;
  v17 = 0;
  v18 = 0;
  PublisherLookupNLoader<PublisherManifestResource>::PublisherLookupNLoader<PublisherManifestResource>(v20, v19, a3, a1);
  v15 = 0;
  if ( PublisherManifestTdhConfig::ReadConfig((PublisherManifestTdhConfig *)&v16, v7) )
  {
    v8 = -1073217792;
  }
  else if ( !*((_QWORD *)&v18 + 1)
         || (v8 = PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(&v11, *((_QWORD *)&v18 + 1))) == 0 )
  {
    if ( *((_QWORD *)&v17 + 1) )
    {
      v8 = PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(v20);
      if ( !v8 )
        v8 = PmresEnumFilters(v15, v21, a2, a3, a4);
    }
    else
    {
      v8 = 4316;
    }
  }
  PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(v20);
  PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(&v11);
  v16 = &PublisherManifestConfig::`vftable';
  PublisherManifestConfig::Free((PublisherManifestConfig *)&v16);
  return v8;
}

```

## disassembly

```asm
0x180026ba8  push    rbp
0x180026baa  push    rbx
0x180026bab  push    rsi
0x180026bac  push    rdi
0x180026bad  push    r14
0x180026baf  lea     rbp, [rsp-80h]
0x180026bb4  sub     rsp, 180h
0x180026bbb  mov     rax, cs:__security_cookie
0x180026bc2  xor     rax, rsp
0x180026bc5  mov     [rbp+0A0h+var_30], rax
0x180026bc9  lea     rax, ??_7PublisherManifestTdhConfig@@6B@; const PublisherManifestTdhConfig::`vftable'
0x180026bd0  mov     [rbp+0A0h+var_118], rcx
0x180026bd4  mov     [rsp+1A0h+var_148], rax
0x180026bd9  mov     r14, r9
0x180026bdc  lea     rax, ??_7ModuleLoaderImpl@@6B@; const ModuleLoaderImpl::`vftable'
0x180026be3  mov     [rsp+1A0h+var_160], 2
0x180026beb  mov     [rsp+1A0h+var_170], rax
0x180026bf0  mov     r9, rcx
0x180026bf3  lea     rax, ??_7ManifestResourceLoaderImpl@@6B@; const ManifestResourceLoaderImpl::`vftable'
0x180026bfa  mov     [rsp+1A0h+var_15C], 0
0x180026bff  mov     [rbp+0A0h+var_120], rax
0x180026c03  lea     rcx, [rbp+0A0h+var_110]
0x180026c07  lea     rax, [rsp+1A0h+var_170]
0x180026c0c  mov     rdi, rdx
0x180026c0f  mov     [rsp+1A0h+var_158], rax
0x180026c14  lea     rdx, [rbp+0A0h+var_120]
0x180026c18  lea     rax, ?g_EnvironmentTable@@3PAUPUBLISHER_LOOKUP_ENTRY@@A; PUBLISHER_LOOKUP_ENTRY near * g_EnvironmentTable
0x180026c1f  xorps   xmm0, xmm0
0x180026c22  xorps   xmm1, xmm1
0x180026c25  mov     [rsp+1A0h+var_168], rax
0x180026c2a  mov     rsi, r8
0x180026c2d  movdqu  [rsp+1A0h+var_140], xmm0
0x180026c33  movdqu  [rsp+1A0h+var_130], xmm1
0x180026c39  call    ??0?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAA@PEAV?$IPublisherLoader@VPublisherManifestResource@@@@PEAUPUBLISHER_LOOKUP_ENTRY@@K@Z; PublisherLookupNLoader<PublisherManifestResource>::PublisherLookupNLoader<PublisherManifestResource>(IPublisherLoader<PublisherManifestResource> *,PUBLISHER_LOOKUP_ENTRY *,ulong)
0x180026c3e  lea     rcx, [rsp+1A0h+var_148]; this
0x180026c43  mov     [rsp+1A0h+var_150], 0
0x180026c4c  mov     rdx, r9; struct _GUID *
0x180026c4f  call    ?ReadConfig@PublisherManifestTdhConfig@@UEAAKAEBU_GUID@@@Z; PublisherManifestTdhConfig::ReadConfig(_GUID const &)
0x180026c54  test    eax, eax
0x180026c56  jz      short loc_180026C5F
0x180026c58  mov     ebx, 0C007FF00h
0x180026c5d  jmp     short loc_180026CB4
0x180026c5f  mov     rdx, qword ptr [rsp+1A0h+var_130+8]
0x180026c64  test    rdx, rdx
0x180026c67  jz      short loc_180026C79
0x180026c69  lea     rcx, [rsp+1A0h+var_168]
0x180026c6e  call    ?LookupNLoad@?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<HINSTANCE__ *>::LookupNLoad(wchar_t const *)
0x180026c73  mov     ebx, eax
0x180026c75  test    eax, eax
0x180026c77  jnz     short loc_180026CB4
0x180026c79  mov     rdx, qword ptr [rsp+1A0h+var_140+8]
0x180026c7e  test    rdx, rdx
0x180026c81  jnz     short loc_180026C8A
0x180026c83  mov     ebx, 10DCh
0x180026c88  jmp     short loc_180026CB4
0x180026c8a  lea     rcx, [rbp+0A0h+var_110]
0x180026c8e  call    ?LookupNLoad@?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAAKPEB_W@Z; PublisherLookupNLoader<PublisherManifestResource>::LookupNLoad(wchar_t const *)
0x180026c93  mov     ebx, eax
0x180026c95  test    eax, eax
0x180026c97  jnz     short loc_180026CB4
0x180026c99  mov     rcx, [rsp+1A0h+var_150]
0x180026c9e  lea     rdx, [rbp+0A0h+var_F8]
0x180026ca2  mov     r9, rsi
0x180026ca5  mov     [rsp+1A0h+var_180], r14
0x180026caa  mov     r8, rdi
0x180026cad  call    PmresEnumFilters
0x180026cb2  mov     ebx, eax
0x180026cb4  lea     rcx, [rbp+0A0h+var_110]
0x180026cb8  call    ??1?$PublisherLookupNLoader@VPublisherManifestResource@@@@QEAA@XZ; PublisherLookupNLoader<PublisherManifestResource>::~PublisherLookupNLoader<PublisherManifestResource>(void)
0x180026cbd  lea     rcx, [rsp+1A0h+var_168]
0x180026cc2  call    ??1?$PublisherLookupNLoader@PEAUHINSTANCE__@@@@QEAA@XZ; PublisherLookupNLoader<HINSTANCE__ *>::~PublisherLookupNLoader<HINSTANCE__ *>(void)
0x180026cc7  lea     rax, ??_7PublisherManifestConfig@@6B@; const PublisherManifestConfig::`vftable'
0x180026cce  lea     rcx, [rsp+1A0h+var_148]; this
0x180026cd3  mov     [rsp+1A0h+var_148], rax
0x180026cd8  call    ?Free@PublisherManifestConfig@@AEAAXXZ; PublisherManifestConfig::Free(void)
0x180026cdd  mov     eax, ebx
0x180026cdf  mov     rcx, [rbp+0A0h+var_30]
0x180026ce3  xor     rcx, rsp; StackCookie
0x180026ce6  call    __security_check_cookie
0x180026ceb  add     rsp, 180h
0x180026cf2  pop     r14
0x180026cf4  pop     rdi
0x180026cf5  pop     rsi
0x180026cf6  pop     rbx
0x180026cf7  pop     rbp
0x180026cf8  retn
```
