# DeprecatedDll_Resolve(unsigned __int64,unsigned __int64,unsigned __int64,void *)

- ea: `0x1800b73d0`
- end: `0x1800b78a5`
- name: `?DeprecatedDll_Resolve@@YAK_K00PEAX@Z`
- size: `1237`
- prototype: `unsigned int(unsigned __int64, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting`

## callees

- `0x1800065e4`
- `0x180006960`
- `0x180012920`
- `0x180013fac`
- `0x18001b320`
- `0x1800212b0`
- `0x18008cdfc`
- `0x18008cf64`
- `0x18008cfd0`
- `0x18008d184`
- `0x1800b5808`
- `0x1800b73d0`
- `0x1800ee8c8`
- `0x1800eedb8`
- `0x1800eee18`
- `0x1800eef68`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800b75e9`
- `ntdll!RtlFreeHeap` at `0x1800b75e9`
- `ntdll!RtlAllocateHeap` at `0x1800b771b`
- `ntdll!RtlAllocateHeap` at `0x1800b771b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b77f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b77f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b777f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b781d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b777f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b781d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b7775`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b7775`
- `USER32!LoadStringW` at `0x1800b7813`
- `USER32!LoadStringW` at `0x1800b7813`

## string_xrefs

- `0x1800b77f1`: `pcasvc.dll`
- `0x1800b7876`: `Failed to read the Os version info [%d]`
- `0x1800b7639`: `Failed to read the guid info [%d]`
- `0x1800b76b9`: `Failed to read dialog strings [%d]`
- `0x1800b77df`: `Failed to read dialog strings [%d]`
- `0x1800b7538`: `RemovedOsVersion`
- `0x1800b7586`: `Resolver,DeprecatedDll`
- `0x1800b7477`: `DeprecatedDll_Resolve`
- `0x1800b7498`: `DeprecatedDll_Resolve`

## pseudocode

```c
__int64 __fastcall DeprecatedDll_Resolve(_QWORD *a1, _DWORD *a2, unsigned __int64 a3, void *a4)
{
  LPWSTR v6; // r14
  __int64 v7; // rdx
  void *v8; // rbx
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  unsigned __int64 v13; // rax
  const unsigned __int16 **v14; // r8
  ULONGLONG v15; // rcx
  DWORD EntryTagRef; // eax
  unsigned int v17; // r13d
  unsigned int v18; // eax
  struct _PCA_CHAIN *v19; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r9
  const char *v24; // r9
  int v25; // r8d
  unsigned __int16 **v26; // rax
  ULONGLONG v27; // rcx
  unsigned __int16 *v28; // r14
  unsigned int v29; // r9d
  unsigned __int16 *v30; // rcx
  unsigned __int16 *v31; // r8
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 nSize; // r15
  const unsigned __int16 *v35; // r13
  HMODULE ModuleHandleW; // rax
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v39; // [rsp+44h] [rbp-BCh] BYREF
  ULONGLONG pullResult; // [rsp+48h] [rbp-B8h] BYREF
  void *inited; // [rsp+50h] [rbp-B0h]
  va_list Arguments; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR Heap; // [rsp+60h] [rbp-A0h]
  struct _PCA_CHAIN *v44; // [rsp+68h] [rbp-98h]
  unsigned __int64 v45; // [rsp+70h] [rbp-90h]
  OLECHAR v46[64]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 Source[256]; // [rsp+180h] [rbp+80h] BYREF
  WCHAR Buffer[256]; // [rsp+380h] [rbp+280h] BYREF

  v45 = a3;
  Arguments = 0;
  v39 = 0;
  sz[0] = 0;
  v46[0] = 0;
  Buffer[0] = 0;
  v44 = PcapChainFromHandle(a3);
  Source[0] = 0;
  v6 = 0;
  Heap = 0;
  inited = (void *)SdbInitDatabaseEx(0, v7, 332);
  v8 = inited;
  if ( !inited )
  {
    v9 = 1359;
    lpBuffer = 1359;
    AslLogCallPrintf(
      1,
      (unsigned int)"DeprecatedDll_Resolve",
      262,
      (unsigned int)"Failed to initialize main database [%d]");
    goto LABEL_17;
  }
  v13 = a1[2];
  if ( !v13 )
    goto LABEL_15;
  while ( 1 )
  {
    v38 = 0;
    v14 = 0;
    if ( (unsigned __int64)v6 < v13 )
    {
      v15 = a1[1];
      pullResult = 0;
      if ( ULongLongMult(v15, (ULONGLONG)v6, &pullResult) < 0
        || (v14 = (const unsigned __int16 **)(a1[5] + pullResult), (unsigned __int64)v14 < a1[5]) )
      {
        v14 = 0;
      }
    }
    EntryTagRef = PcaUtilityGetEntryTagRef(&v38, v8, *v14);
    v9 = EntryTagRef;
    if ( EntryTagRef )
    {
      v24 = "Failed to get the entry tag ref [%d]";
      v25 = 274;
      goto LABEL_50;
    }
    v8 = inited;
    v17 = v38;
    v18 = PcaUtilityCheckApphelpFlag(inited, v38);
    if ( !v18 )
      break;
    lpBuffer = v18;
    AslLogCallPrintf(
      1,
      (unsigned int)"DeprecatedDll_Resolve",
      280,
      (unsigned int)"The apphelp tag doesn't exit or entry is disabled [%d]");
LABEL_14:
    v13 = a1[2];
    v6 = (LPWSTR)((char *)v6 + 1);
    if ( (unsigned __int64)v6 >= v13 )
      goto LABEL_15;
  }
  v38 = 4;
  EntryTagRef = PcaUtilityGetApphelpExtraData(&v39, &v38, L"RemovedOsVersion", v8, v17);
  v9 = EntryTagRef;
  if ( EntryTagRef )
  {
    v24 = "Failed to read the Os version info [%d]";
    v25 = 292;
    goto LABEL_50;
  }
  if ( *((_DWORD *)v44 + 1180) >= v39 )
  {
    v19 = PcapChainFromHandle(v45);
    PcaTracePrintf(
      "Resolver,DeprecatedDll",
      *((_DWORD *)v19 + 4),
      0,
      "Ignored,Application OS version is later than the one the detector is targeting");
    v8 = inited;
    goto LABEL_14;
  }
  EntryTagRef = PcaUtilityGetGuidInfo(sz, v46, inited, v17);
  v9 = EntryTagRef;
  if ( EntryTagRef )
  {
    v24 = "Failed to read the guid info [%d]";
    v25 = 314;
LABEL_50:
    lpBuffer = EntryTagRef;
    AslLogCallPrintf(1, (unsigned int)"DeprecatedDll_Resolve", v25, (_DWORD)v24);
    goto LABEL_16;
  }
  v26 = 0;
  if ( (unsigned __int64)v6 < a1[2] )
  {
    v27 = a1[1];
    pullResult = 0;
    if ( ULongLongMult(v27, (ULONGLONG)v6, &pullResult) < 0
      || (v26 = (unsigned __int16 **)(a1[5] + pullResult), (unsigned __int64)v26 < a1[5]) )
    {
      v26 = 0;
    }
  }
  v28 = *v26;
  if ( *v26 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl'::`2'::impl,
                            v21,
                            v22,
                            v23,
                            lpBuffer) )
    {
      EntryTagRef = PcaDialogLoadStrings((unsigned __int64)a2, 0x708u, 0x834u, v29);
      v9 = EntryTagRef;
      if ( EntryTagRef )
      {
        v24 = "Failed to read dialog strings [%d]";
        v25 = 337;
        goto LABEL_50;
      }
      PcaDialogGetStrings(v30, Source, v31, (unsigned __int64)a2);
      v32 = -1;
      v33 = -1;
      do
        ++v33;
      while ( Source[v33] );
      do
        ++v32;
      while ( v28[v32] );
      v9 = 8;
      nSize = v33 + v32 + 1;
      Heap = (LPWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * nSize);
      v35 = Heap;
      if ( !Heap )
      {
        AslLogCallPrintf(1, (unsigned int)"DeprecatedDll_Resolve", 350, (unsigned int)"Out of memory");
        goto LABEL_16;
      }
      Arguments = (va_list)v28;
      if ( !FormatMessageW(0x2400u, Source, 0, 0, Heap, nSize, &Arguments) )
      {
        EntryTagRef = GetLastError();
        v24 = "FormatMessageW failed [%d].";
        v25 = 369;
        if ( !EntryTagRef )
          EntryTagRef = 1359;
        v9 = EntryTagRef;
        goto LABEL_50;
      }
      EntryTagRef = PcaDialogSetStrings((unsigned __int64)a2, 0, v35, 0);
      v9 = EntryTagRef;
      if ( EntryTagRef )
      {
        v24 = "Failed to set dialog strings [%d]";
        v25 = 382;
        goto LABEL_50;
      }
    }
    else
    {
      EntryTagRef = PcaDialogLoadStrings((unsigned __int64)a2, 0x708u, 0x70Du, v29);
      v9 = EntryTagRef;
      if ( EntryTagRef )
      {
        v24 = "Failed to read dialog strings [%d]";
        v25 = 396;
        goto LABEL_50;
      }
    }
    ModuleHandleW = GetModuleHandleW(L"pcasvc.dll");
    if ( LoadStringW(ModuleHandleW, 0x70Cu, Buffer, 256) )
    {
      a2[1] |= 1u;
      *a2 = 4;
      EntryTagRef = PcaDialogAddCheckOnlineButton((unsigned __int64)a2, Buffer, sz, v46, v28);
      v9 = EntryTagRef;
      if ( !EntryTagRef )
        goto LABEL_15;
      v24 = "Failed to add check online button [%d]";
      v25 = 422;
    }
    else
    {
      EntryTagRef = GetLastError();
      v24 = "Failed to load resource strings [%d]";
      v25 = 410;
      v9 = EntryTagRef;
    }
    goto LABEL_50;
  }
LABEL_15:
  v9 = 0;
LABEL_16:
  SdbReleaseDatabase(inited);
  v6 = Heap;
LABEL_17:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl'::`2'::impl,
                          v10,
                          v11,
                          v12,
                          lpBuffer)
    && v6 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v6);
  }
  return v9;
}

```

## disassembly

```asm
0x1800b73d0  mov     [rsp-8+arg_18], rbx
0x1800b73d5  push    rbp
0x1800b73d6  push    rsi
0x1800b73d7  push    rdi
0x1800b73d8  push    r12
0x1800b73da  push    r13
0x1800b73dc  push    r14
0x1800b73de  push    r15
0x1800b73e0  lea     rbp, [rsp-490h]
0x1800b73e8  sub     rsp, 590h
0x1800b73ef  mov     rax, cs:__security_cookie
0x1800b73f6  xor     rax, rsp
0x1800b73f9  mov     [rbp+4C0h+var_40], rax
0x1800b7400  xor     r13d, r13d
0x1800b7403  mov     [rsp+5C0h+var_550], r8
0x1800b7408  mov     r15, rcx
0x1800b740b  mov     [rsp+5C0h+var_568], r13
0x1800b7410  mov     rcx, r8; unsigned __int64
0x1800b7413  mov     [rsp+5C0h+var_57C], r13d
0x1800b7418  mov     [rbp+4C0h+sz], r13w
0x1800b741d  mov     r12, rdx
0x1800b7420  mov     [rbp+4C0h+var_540], r13w
0x1800b7425  mov     [rbp+4C0h+Buffer], r13w
0x1800b742d  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b7432  xor     ecx, ecx
0x1800b7434  mov     [rsp+5C0h+var_558], rax
0x1800b7439  mov     r8d, 14Ch
0x1800b743f  mov     [rbp+4C0h+Source], r13w
0x1800b7447  mov     r14d, r13d
0x1800b744a  mov     [rsp+5C0h+var_560], r13
0x1800b744f  call    SdbInitDatabaseEx
0x1800b7454  mov     [rsp+5C0h+var_570], rax
0x1800b7459  mov     rbx, rax
0x1800b745c  test    rax, rax
0x1800b745f  jnz     short loc_1800B748B
0x1800b7461  mov     ebx, 54Fh
0x1800b7466  lea     r9, aFailedToInitia_8; "Failed to initialize main database [%d]"
0x1800b746d  mov     r8d, 106h
0x1800b7473  mov     dword ptr [rsp+5C0h+lpBuffer], ebx
0x1800b7477  lea     rdx, aDeprecateddllR; "DeprecatedDll_Resolve"
0x1800b747e  lea     ecx, [rax+1]
0x1800b7481  call    AslLogCallPrintf
0x1800b7486  jmp     loc_1800B75C2
0x1800b748b  mov     rax, [r15+10h]
0x1800b748f  test    rax, rax
0x1800b7492  jz      loc_1800B75B0
0x1800b7498  lea     rsi, aDeprecateddllR; "DeprecatedDll_Resolve"
0x1800b749f  mov     edi, 1
0x1800b74a4  mov     [rsp+5C0h+var_580], r13d
0x1800b74a9  mov     r8, r13
0x1800b74ac  cmp     r14, rax
0x1800b74af  jnb     short loc_1800B74DD
0x1800b74b1  mov     rcx, [r15+8]; ullMultiplicand
0x1800b74b5  lea     r8, [rsp+5C0h+pullResult]; pullResult
0x1800b74ba  mov     rdx, r14; ullMultiplier
0x1800b74bd  mov     [rsp+5C0h+pullResult], r13
0x1800b74c2  call    ULongLongMult
0x1800b74c7  test    eax, eax
0x1800b74c9  js      short loc_1800B74DA
0x1800b74cb  mov     r8, [rsp+5C0h+pullResult]
0x1800b74d0  add     r8, [r15+28h]
0x1800b74d4  cmp     r8, [r15+28h]
0x1800b74d8  jnb     short loc_1800B74DD
0x1800b74da  mov     r8, r13
0x1800b74dd  mov     r8, [r8]; unsigned __int16 *
0x1800b74e0  lea     rcx, [rsp+5C0h+var_580]; unsigned int *
0x1800b74e5  mov     rdx, rbx; void *
0x1800b74e8  call    ?PcaUtilityGetEntryTagRef@@YAKPEAKPEAXPEBG@Z; PcaUtilityGetEntryTagRef(ulong *,void *,ushort const *)
0x1800b74ed  mov     ebx, eax
0x1800b74ef  test    eax, eax
0x1800b74f1  jnz     loc_1800B7885
0x1800b74f7  mov     rbx, [rsp+5C0h+var_570]
0x1800b74fc  mov     r13d, [rsp+5C0h+var_580]
0x1800b7501  mov     rcx, rbx; void *
0x1800b7504  mov     edx, r13d; unsigned int
0x1800b7507  call    ?PcaUtilityCheckApphelpFlag@@YAKPEAXK@Z; PcaUtilityCheckApphelpFlag(void *,ulong)
0x1800b750c  test    eax, eax
0x1800b750e  jz      short loc_1800B752D
0x1800b7510  lea     r9, aTheApphelpTagD; "The apphelp tag doesn't exit or entry i"...
0x1800b7517  mov     dword ptr [rsp+5C0h+lpBuffer], eax
0x1800b751b  mov     r8d, 118h
0x1800b7521  mov     rdx, rsi
0x1800b7524  mov     ecx, edi
0x1800b7526  call    AslLogCallPrintf
0x1800b752b  jmp     short loc_1800B759A
0x1800b752d  mov     r9, rbx; void *
0x1800b7530  mov     [rsp+5C0h+var_580], 4
0x1800b7538  lea     r8, aRemovedosversi; "RemovedOsVersion"
0x1800b753f  mov     dword ptr [rsp+5C0h+lpBuffer], r13d; unsigned int
0x1800b7544  lea     rdx, [rsp+5C0h+var_580]; unsigned int *
0x1800b7549  lea     rcx, [rsp+5C0h+var_57C]; void *
0x1800b754e  call    ?PcaUtilityGetApphelpExtraData@@YAKPEAXPEAKPEBG0K@Z; PcaUtilityGetApphelpExtraData(void *,ulong *,ushort const *,void *,ulong)
0x1800b7553  mov     ebx, eax
0x1800b7555  test    eax, eax
0x1800b7557  jnz     loc_1800B7876
0x1800b755d  mov     rcx, [rsp+5C0h+var_558]
0x1800b7562  mov     eax, [rsp+5C0h+var_57C]
0x1800b7566  cmp     [rcx+1270h], eax
0x1800b756c  jb      loc_1800B761B
0x1800b7572  mov     rcx, [rsp+5C0h+var_550]; unsigned __int64
0x1800b7577  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b757c  lea     r9, aIgnoredApplica; "Ignored,Application OS version is later"...
0x1800b7583  xor     r8d, r8d; unsigned int
0x1800b7586  lea     rcx, aResolverDeprec; "Resolver,DeprecatedDll"
0x1800b758d  mov     edx, [rax+10h]; unsigned int
0x1800b7590  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b7595  mov     rbx, [rsp+5C0h+var_570]
0x1800b759a  mov     rax, [r15+10h]
0x1800b759e  add     r14, rdi
0x1800b75a1  mov     r13d, 0
0x1800b75a7  cmp     r14, rax
0x1800b75aa  jb      loc_1800B74A4
0x1800b75b0  mov     ebx, r13d
0x1800b75b3  mov     rcx, [rsp+5C0h+var_570]
0x1800b75b8  call    SdbReleaseDatabase
0x1800b75bd  mov     r14, [rsp+5C0h+var_560]
0x1800b75c2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes> `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl(void)'::`2'::impl
0x1800b75c9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(void)
0x1800b75ce  test    al, al
0x1800b75d0  jz      short loc_1800B75EF
0x1800b75d2  test    r14, r14
0x1800b75d5  jz      short loc_1800B75EF
0x1800b75d7  mov     rcx, gs:60h
0x1800b75e0  mov     r8, r14; P
0x1800b75e3  xor     edx, edx; Flags
0x1800b75e5  mov     rcx, [rcx+30h]; HeapHandle
0x1800b75e9  call    cs:__imp_RtlFreeHeap
0x1800b75ef  mov     eax, ebx
0x1800b75f1  mov     rcx, [rbp+4C0h+var_40]
0x1800b75f8  xor     rcx, rsp; StackCookie
0x1800b75fb  call    __security_check_cookie
0x1800b7600  mov     rbx, [rsp+5C0h+arg_18]
0x1800b7608  add     rsp, 590h
0x1800b760f  pop     r15
0x1800b7611  pop     r14
0x1800b7613  pop     r13
0x1800b7615  pop     r12
0x1800b7617  pop     rdi
0x1800b7618  pop     rsi
0x1800b7619  pop     rbp
0x1800b761a  retn
0x1800b761b  mov     r8, [rsp+5C0h+var_570]; void *
0x1800b7620  lea     rdx, [rbp+4C0h+var_540]; LPOLESTR
0x1800b7624  mov     r9d, r13d; unsigned int
0x1800b7627  lea     rcx, [rbp+4C0h+sz]; lpsz
0x1800b762b  call    ?PcaUtilityGetGuidInfo@@YAKPEAG0PEAXK@Z; PcaUtilityGetGuidInfo(ushort *,ushort *,void *,ulong)
0x1800b7630  xor     r13d, r13d
0x1800b7633  mov     ebx, eax
0x1800b7635  test    eax, eax
0x1800b7637  jz      short loc_1800B764B
0x1800b7639  lea     r9, aFailedToReadTh_1; "Failed to read the guid info [%d]"
0x1800b7640  mov     r8d, 13Ah
0x1800b7646  jmp     loc_1800B7892
0x1800b764b  mov     rax, r13
0x1800b764e  cmp     r14, [r15+10h]
0x1800b7652  jnb     short loc_1800B7680
0x1800b7654  mov     rcx, [r15+8]; ullMultiplicand
0x1800b7658  lea     r8, [rsp+5C0h+pullResult]; pullResult
0x1800b765d  mov     rdx, r14; ullMultiplier
0x1800b7660  mov     [rsp+5C0h+pullResult], r13
0x1800b7665  call    ULongLongMult
0x1800b766a  test    eax, eax
0x1800b766c  js      short loc_1800B767D
0x1800b766e  mov     rax, [rsp+5C0h+pullResult]
0x1800b7673  add     rax, [r15+28h]
0x1800b7677  cmp     rax, [r15+28h]
0x1800b767b  jnb     short loc_1800B7680
0x1800b767d  mov     rax, r13
0x1800b7680  mov     r14, [rax]
0x1800b7683  test    r14, r14
0x1800b7686  jz      loc_1800B75B0
0x1800b768c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes> `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl(void)'::`2'::impl
0x1800b7693  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(void)
0x1800b7698  mov     edx, 708h; uID
0x1800b769d  mov     rcx, r12; unsigned __int64
0x1800b76a0  test    al, al
0x1800b76a2  jz      loc_1800B77CE
0x1800b76a8  mov     r8d, 834h; UINT
0x1800b76ae  call    ?PcaDialogLoadStrings@@YAK_KIII@Z; PcaDialogLoadStrings(unsigned __int64,uint,uint,uint)
0x1800b76b3  mov     ebx, eax
0x1800b76b5  test    eax, eax
0x1800b76b7  jz      short loc_1800B76CB
0x1800b76b9  lea     r9, aFailedToReadDi_0; "Failed to read dialog strings [%d]"
0x1800b76c0  mov     r8d, 151h
0x1800b76c6  jmp     loc_1800B7892
0x1800b76cb  mov     r9, r12; unsigned __int64
0x1800b76ce  lea     rdx, [rbp+4C0h+Source]; unsigned __int16 *
0x1800b76d5  call    ?PcaDialogGetStrings@@YAKPEAG00_K@Z; PcaDialogGetStrings(ushort *,ushort *,ushort *,unsigned __int64)
0x1800b76da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b76de  lea     rdx, [rbp+4C0h+Source]
0x1800b76e5  mov     rcx, rax
0x1800b76e8  inc     rcx
0x1800b76eb  cmp     [rdx+rcx*2], r13w
0x1800b76f0  jnz     short loc_1800B76E8
0x1800b76f2  inc     rax
0x1800b76f5  cmp     [r14+rax*2], r13w
0x1800b76fa  jnz     short loc_1800B76F2
0x1800b76fc  lea     r15, [rax+1]
0x1800b7700  mov     ebx, 8
0x1800b7705  add     r15, rcx
0x1800b7708  mov     edx, ebx; Flags
0x1800b770a  mov     rcx, gs:60h
0x1800b7713  lea     r8, [r15+r15]; Size
0x1800b7717  mov     rcx, [rcx+30h]; HeapHandle
0x1800b771b  call    cs:__imp_RtlAllocateHeap
0x1800b7721  mov     [rsp+5C0h+var_560], rax
0x1800b7726  mov     r13, rax
0x1800b7729  test    rax, rax
0x1800b772c  jnz     short loc_1800B774A
0x1800b772e  lea     r9, aOutOfMemory; "Out of memory"
0x1800b7735  mov     r8d, 15Eh
0x1800b773b  mov     rdx, rsi
0x1800b773e  mov     ecx, edi
0x1800b7740  call    AslLogCallPrintf
0x1800b7745  jmp     loc_1800B75B3
0x1800b774a  lea     rax, [rsp+5C0h+var_568]
0x1800b774f  mov     [rsp+5C0h+var_568], r14
0x1800b7754  mov     [rsp+5C0h+Arguments], rax; Arguments
0x1800b7759  lea     rdx, [rbp+4C0h+Source]; lpSource
0x1800b7760  mov     [rsp+5C0h+nSize], r15d; nSize
0x1800b7765  xor     r9d, r9d; dwLanguageId
0x1800b7768  xor     r8d, r8d; dwMessageId
0x1800b776b  mov     [rsp+5C0h+lpBuffer], r13; lpBuffer
0x1800b7770  mov     ecx, 2400h; dwFlags
0x1800b7775  call    cs:__imp_FormatMessageW
0x1800b777b  test    eax, eax
0x1800b777d  jnz     short loc_1800B77A3
0x1800b777f  call    cs:__imp_GetLastError
0x1800b7785  mov     ebx, 54Fh
0x1800b778a  lea     r9, aFormatmessagew; "FormatMessageW failed [%d]."
0x1800b7791  test    eax, eax
0x1800b7793  mov     r8d, 171h
0x1800b7799  cmovz   eax, ebx
0x1800b779c  mov     ebx, eax
0x1800b779e  jmp     loc_1800B7892
0x1800b77a3  xor     r9d, r9d; unsigned __int16 *
0x1800b77a6  mov     r8, r13; unsigned __int16 *
0x1800b77a9  xor     edx, edx; unsigned __int16 *
0x1800b77ab  mov     rcx, r12; unsigned __int64
0x1800b77ae  call    ?PcaDialogSetStrings@@YAK_KPEBG11@Z; PcaDialogSetStrings(unsigned __int64,ushort const *,ushort const *,ushort const *)
0x1800b77b3  xor     r13d, r13d
0x1800b77b6  mov     ebx, eax
0x1800b77b8  test    eax, eax
0x1800b77ba  jz      short loc_1800B77F1
0x1800b77bc  lea     r9, aFailedToSetDia; "Failed to set dialog strings [%d]"
0x1800b77c3  mov     r8d, 17Eh
0x1800b77c9  jmp     loc_1800B7892
0x1800b77ce  mov     r8d, 70Dh; UINT
0x1800b77d4  call    ?PcaDialogLoadStrings@@YAK_KIII@Z; PcaDialogLoadStrings(unsigned __int64,uint,uint,uint)
0x1800b77d9  mov     ebx, eax
0x1800b77db  test    eax, eax
0x1800b77dd  jz      short loc_1800B77F1
0x1800b77df  lea     r9, aFailedToReadDi_0; "Failed to read dialog strings [%d]"
0x1800b77e6  mov     r8d, 18Ch
0x1800b77ec  jmp     loc_1800B7892
0x1800b77f1  lea     rcx, aPcasvcDll_0; "pcasvc.dll"
0x1800b77f8  call    cs:__imp_GetModuleHandleW
0x1800b77fe  mov     r9d, 100h; cchBufferMax
0x1800b7804  lea     r8, [rbp+4C0h+Buffer]; lpBuffer
0x1800b780b  mov     rcx, rax; hInstance
0x1800b780e  mov     edx, 70Ch; uID
0x1800b7813  call    cs:__imp_LoadStringW
0x1800b7819  test    eax, eax
0x1800b781b  jnz     short loc_1800B7834
0x1800b781d  call    cs:__imp_GetLastError
0x1800b7823  lea     r9, aFailedToLoadRe; "Failed to load resource strings [%d]"
0x1800b782a  mov     r8d, 19Ah
0x1800b7830  mov     ebx, eax
0x1800b7832  jmp     short loc_1800B7892
0x1800b7834  or      [r12+4], edi
0x1800b7839  lea     r9, [rbp+4C0h+var_540]; unsigned __int16 *
0x1800b783d  lea     r8, [rbp+4C0h+sz]; unsigned __int16 *
0x1800b7841  mov     dword ptr [r12], 4
0x1800b7849  lea     rdx, [rbp+4C0h+Buffer]; unsigned __int16 *
0x1800b7850  mov     [rsp+5C0h+lpBuffer], r14; unsigned __int16 *
0x1800b7855  mov     rcx, r12; unsigned __int64
0x1800b7858  call    ?PcaDialogAddCheckOnlineButton@@YAK_KPEBG111@Z; PcaDialogAddCheckOnlineButton(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b785d  mov     ebx, eax
0x1800b785f  test    eax, eax
0x1800b7861  jz      loc_1800B75B0
0x1800b7867  lea     r9, aFailedToAddChe; "Failed to add check online button [%d]"
0x1800b786e  mov     r8d, 1A6h
0x1800b7874  jmp     short loc_1800B7892
0x1800b7876  lea     r9, aFailedToReadTh_6; "Failed to read the Os version info [%d]"
0x1800b787d  mov     r8d, 124h
0x1800b7883  jmp     short loc_1800B7892
0x1800b7885  lea     r9, aFailedToGetThe_35; "Failed to get the entry tag ref [%d]"
0x1800b788c  mov     r8d, 112h
0x1800b7892  mov     rdx, rsi
0x1800b7895  mov     dword ptr [rsp+5C0h+lpBuffer], eax
0x1800b7899  mov     ecx, edi
0x1800b789b  call    AslLogCallPrintf
0x1800b78a0  jmp     loc_1800B75B3
```
