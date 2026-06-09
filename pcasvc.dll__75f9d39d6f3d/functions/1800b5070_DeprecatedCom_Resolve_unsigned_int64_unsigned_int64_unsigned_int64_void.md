# DeprecatedCom_Resolve(unsigned __int64,unsigned __int64,unsigned __int64,void *)

- ea: `0x1800b5070`
- end: `0x1800b5569`
- name: `?DeprecatedCom_Resolve@@YAK_K00PEAX@Z`
- size: `1273`
- prototype: `unsigned int(unsigned __int64, unsigned __int64, unsigned __int64, void *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

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
- `0x1800b5070`
- `0x1800b5808`
- `0x1800ee8c8`
- `0x1800eedb8`
- `0x1800eee18`
- `0x1800eef68`
- `0x1800f1f10`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800b5537`
- `ntdll!RtlFreeHeap` at `0x1800b5537`
- `ntdll!RtlAllocateHeap` at `0x1800b53ae`
- `ntdll!RtlAllocateHeap` at `0x1800b53ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b547e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800b547e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b5408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b54a3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b53fe`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800b53fe`
- `USER32!LoadStringW` at `0x1800b5499`
- `USER32!LoadStringW` at `0x1800b5499`

## string_xrefs

- `0x1800b5477`: `pcasvc.dll`
- `0x1800b52f4`: `DllName`
- `0x1800b5328`: `Failed to read the Os version info [%d]`
- `0x1800b52dd`: `Failed to read the guid info [%d]`
- `0x1800b5247`: `Resolver,DeprecatedCom`
- `0x1800b52ad`: `Failed to read dialog strings [%d]`
- `0x1800b5465`: `Failed to read dialog strings [%d]`
- `0x1800b5319`: `Failed to read Dll name [%d]`
- `0x1800b512e`: `DeprecatedCom_Resolve`
- `0x1800b5146`: `DeprecatedCom_Resolve`
- `0x1800b51f9`: `RemovedOsVersion`

## pseudocode

```c
__int64 __fastcall DeprecatedCom_Resolve(_QWORD *a1, _DWORD *a2, unsigned __int64 a3, void *a4)
{
  _QWORD *v4; // rbx
  WCHAR *Heap; // r13
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // r8
  void *v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  ULONGLONG v15; // rax
  ULONGLONG v16; // r15
  const unsigned __int16 **v17; // r8
  ULONGLONG v18; // rcx
  DWORD EntryTagRef; // eax
  void *v20; // rbx
  unsigned int v21; // r12d
  unsigned int v22; // eax
  struct _PCA_CHAIN *v23; // rax
  unsigned int v24; // r9d
  unsigned __int16 *v25; // rcx
  unsigned __int16 *v26; // r8
  const char *v27; // r9
  int v28; // r8d
  void *v29; // r15
  __int64 v30; // rax
  __int64 v31; // rcx
  __int64 nSize; // r15
  HMODULE ModuleHandleW; // rax
  int lpBuffer; // [rsp+20h] [rbp-E0h]
  unsigned int v36; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-BCh] BYREF
  void *inited; // [rsp+48h] [rbp-B8h]
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  ULONGLONG pullResult; // [rsp+58h] [rbp-A8h] BYREF
  struct _PCA_CHAIN *v41; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v42; // [rsp+68h] [rbp-98h]
  _QWORD *v43; // [rsp+70h] [rbp-90h]
  va_list Arguments; // [rsp+78h] [rbp-88h] BYREF
  OLECHAR v45[64]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR sz[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v47[264]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 Source[256]; // [rsp+390h] [rbp+290h] BYREF
  WCHAR Buffer[256]; // [rsp+590h] [rbp+490h] BYREF

  v43 = a1;
  v4 = a1;
  v37 = 0;
  sz[0] = 0;
  v45[0] = 0;
  v47[0] = 0;
  Arguments = (va_list)v47;
  Buffer[0] = 0;
  v42 = a3;
  v39 = 520;
  v41 = PcapChainFromHandle(a3);
  Source[0] = 0;
  Heap = 0;
  inited = (void *)SdbInitDatabaseEx(0, v7, 332);
  v10 = inited;
  if ( !inited )
  {
    v11 = 1359;
    lpBuffer = 1359;
    AslLogCallPrintf(
      1,
      (unsigned int)"DeprecatedCom_Resolve",
      283,
      (unsigned int)"Failed to initialize main database [%d]");
    goto LABEL_47;
  }
  v15 = v4[2];
  if ( !v15 )
    goto LABEL_17;
  v16 = 0;
  while ( 1 )
  {
    v36 = 0;
    v17 = 0;
    if ( v16 < v15 )
    {
      v18 = v4[1];
      pullResult = 0;
      if ( ULongLongMult(v18, v16, &pullResult) < 0
        || (v17 = (const unsigned __int16 **)(v4[5] + pullResult), (unsigned __int64)v17 < v4[5]) )
      {
        v17 = 0;
      }
    }
    EntryTagRef = PcaUtilityGetEntryTagRef(&v36, v10, *v17);
    v11 = EntryTagRef;
    if ( EntryTagRef )
    {
      v27 = "Failed to get the entry tag ref [%d]";
      v28 = 295;
      goto LABEL_27;
    }
    v20 = inited;
    v21 = v36;
    v22 = PcaUtilityCheckApphelpFlag(inited, v36);
    if ( v22 )
    {
      lpBuffer = v22;
      AslLogCallPrintf(
        1,
        (unsigned int)"DeprecatedCom_Resolve",
        301,
        (unsigned int)"The apphelp tag doesn't exit or entry is disabled [%d]");
      goto LABEL_16;
    }
    v36 = 4;
    EntryTagRef = PcaUtilityGetApphelpExtraData(&v37, &v36, L"RemovedOsVersion", v20, v21);
    v11 = EntryTagRef;
    if ( EntryTagRef )
    {
      v27 = "Failed to read the Os version info [%d]";
      v28 = 313;
      goto LABEL_27;
    }
    if ( *((_DWORD *)v41 + 1180) < v37 )
      break;
    v23 = PcapChainFromHandle(v42);
    PcaTracePrintf(
      "Resolver,DeprecatedCom",
      *((_DWORD *)v23 + 4),
      0,
      "Ignored,Application OS version is later than the one the detector is targeting");
LABEL_16:
    v4 = v43;
    ++v16;
    v15 = v43[2];
    if ( v16 >= v15 )
      goto LABEL_17;
    v10 = inited;
  }
  v29 = inited;
  EntryTagRef = PcaUtilityGetGuidInfo(sz, v45, inited, v21);
  v11 = EntryTagRef;
  if ( EntryTagRef )
  {
    v27 = "Failed to read the guid info [%d]";
    v28 = 335;
    goto LABEL_27;
  }
  EntryTagRef = PcaUtilityGetApphelpExtraData(v47, &v39, L"DllName", v29, v21);
  v11 = EntryTagRef;
  if ( EntryTagRef )
  {
    v27 = "Failed to read Dll name [%d]";
    v28 = 350;
    goto LABEL_27;
  }
LABEL_17:
  if ( v47[0] )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(
                            `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl'::`2'::impl,
                            v8,
                            v9,
                            v10,
                            lpBuffer) )
    {
      EntryTagRef = PcaDialogLoadStrings((unsigned __int64)a2, 0x708u, 0x834u, v24);
      v11 = EntryTagRef;
      if ( EntryTagRef )
      {
        v27 = "Failed to read dialog strings [%d]";
        v28 = 372;
        goto LABEL_27;
      }
      PcaDialogGetStrings(v25, Source, v26, (unsigned __int64)a2);
      v30 = -1;
      v31 = -1;
      do
        ++v31;
      while ( v47[v31] );
      do
        ++v30;
      while ( Source[v30] );
      v11 = 8;
      nSize = v30 + v31 + 1;
      Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * nSize);
      if ( !Heap )
      {
        AslLogCallPrintf(1, (unsigned int)"DeprecatedCom_Resolve", 385, (unsigned int)"Out of memory");
        goto LABEL_46;
      }
      if ( !FormatMessageW(0x2400u, Source, 0, 0, Heap, nSize, &Arguments) )
      {
        EntryTagRef = GetLastError();
        v27 = "FormatMessageW failed [%d].";
        v28 = 403;
        if ( !EntryTagRef )
          EntryTagRef = 1359;
        v11 = EntryTagRef;
        goto LABEL_27;
      }
      EntryTagRef = PcaDialogSetStrings((unsigned __int64)a2, 0, Heap, 0);
      v11 = EntryTagRef;
      if ( EntryTagRef )
      {
        v27 = "Failed to set dialog strings [%d]";
        v28 = 416;
LABEL_27:
        lpBuffer = EntryTagRef;
        AslLogCallPrintf(1, (unsigned int)"DeprecatedCom_Resolve", v28, (_DWORD)v27);
        goto LABEL_46;
      }
    }
    else
    {
      EntryTagRef = PcaDialogLoadStrings((unsigned __int64)a2, 0x708u, 0x70Du, v24);
      v11 = EntryTagRef;
      if ( EntryTagRef )
      {
        v27 = "Failed to read dialog strings [%d]";
        v28 = 430;
        goto LABEL_27;
      }
    }
    ModuleHandleW = GetModuleHandleW(L"pcasvc.dll");
    if ( !LoadStringW(ModuleHandleW, 0x70Cu, Buffer, 256) )
    {
      EntryTagRef = GetLastError();
      v27 = "Failed to load resource strings [%d]";
      v28 = 444;
      v11 = EntryTagRef;
      goto LABEL_27;
    }
    a2[1] |= 1u;
    *a2 = 4;
    EntryTagRef = PcaDialogAddCheckOnlineButton((unsigned __int64)a2, Buffer, sz, v45, v47);
    v11 = EntryTagRef;
    if ( EntryTagRef )
    {
      v27 = "Failed to add check online button [%d]";
      v28 = 456;
      goto LABEL_27;
    }
  }
  v11 = 0;
LABEL_46:
  SdbReleaseDatabase(inited);
LABEL_47:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(
                          `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl'::`2'::impl,
                          v12,
                          v13,
                          v14,
                          lpBuffer)
    && Heap )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  }
  return v11;
}

```

## disassembly

```asm
0x1800b5070  mov     [rsp-8+arg_18], rbx
0x1800b5075  push    rbp
0x1800b5076  push    rsi
0x1800b5077  push    rdi
0x1800b5078  push    r12
0x1800b507a  push    r13
0x1800b507c  push    r14
0x1800b507e  push    r15
0x1800b5080  lea     rbp, [rsp-6A0h]
0x1800b5088  sub     rsp, 7A0h
0x1800b508f  mov     rax, cs:__security_cookie
0x1800b5096  xor     rax, rsp
0x1800b5099  mov     [rbp+6D0h+var_40], rax
0x1800b50a0  xor     r12d, r12d
0x1800b50a3  mov     [rsp+7D0h+var_760], rcx
0x1800b50a8  mov     rbx, rcx
0x1800b50ab  mov     [rsp+7D0h+var_78C], r12d
0x1800b50b0  lea     rax, [rbp+6D0h+var_650]
0x1800b50b7  mov     [rbp+6D0h+sz], r12w
0x1800b50bc  mov     rcx, r8; unsigned __int64
0x1800b50bf  mov     [rbp+6D0h+var_750], r12w
0x1800b50c4  mov     [rbp+6D0h+var_650], r12w
0x1800b50cc  mov     r14, rdx
0x1800b50cf  mov     [rsp+7D0h+var_758], rax
0x1800b50d4  mov     [rbp+6D0h+Buffer], r12w
0x1800b50dc  mov     [rsp+7D0h+var_768], r8
0x1800b50e1  mov     [rsp+7D0h+var_780], 208h
0x1800b50e9  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b50ee  xor     ecx, ecx
0x1800b50f0  mov     [rsp+7D0h+var_770], rax
0x1800b50f5  mov     r8d, 14Ch
0x1800b50fb  mov     [rbp+6D0h+Source], r12w
0x1800b5103  mov     r13d, r12d
0x1800b5106  call    SdbInitDatabaseEx
0x1800b510b  mov     [rsp+7D0h+var_788], rax
0x1800b5110  mov     r9, rax
0x1800b5113  test    rax, rax
0x1800b5116  jnz     short loc_1800B5142
0x1800b5118  mov     ebx, 54Fh
0x1800b511d  lea     r9, aFailedToInitia_8; "Failed to initialize main database [%d]"
0x1800b5124  mov     r8d, 11Bh
0x1800b512a  mov     dword ptr [rsp+7D0h+lpBuffer], ebx
0x1800b512e  lea     rdx, aDeprecatedcomR; "DeprecatedCom_Resolve"
0x1800b5135  lea     ecx, [rax+1]
0x1800b5138  call    AslLogCallPrintf
0x1800b513d  jmp     loc_1800B5510
0x1800b5142  mov     rax, [rbx+10h]
0x1800b5146  lea     rsi, aDeprecatedcomR; "DeprecatedCom_Resolve"
0x1800b514d  mov     edi, 1
0x1800b5152  test    rax, rax
0x1800b5155  jz      loc_1800B526E
0x1800b515b  mov     r15, r12
0x1800b515e  jmp     short loc_1800B5165
0x1800b5160  mov     r9, [rsp+7D0h+var_788]
0x1800b5165  mov     [rsp+7D0h+var_790], r12d
0x1800b516a  mov     r8, r12
0x1800b516d  cmp     r15, rax
0x1800b5170  jnb     short loc_1800B519E
0x1800b5172  mov     rcx, [rbx+8]; ullMultiplicand
0x1800b5176  lea     r8, [rsp+7D0h+pullResult]; pullResult
0x1800b517b  mov     rdx, r15; ullMultiplier
0x1800b517e  mov     [rsp+7D0h+pullResult], r12
0x1800b5183  call    ULongLongMult
0x1800b5188  test    eax, eax
0x1800b518a  js      short loc_1800B519B
0x1800b518c  mov     r8, [rsp+7D0h+pullResult]
0x1800b5191  add     r8, [rbx+28h]
0x1800b5195  cmp     r8, [rbx+28h]
0x1800b5199  jnb     short loc_1800B519E
0x1800b519b  mov     r8, r12
0x1800b519e  mov     r8, [r8]; unsigned __int16 *
0x1800b51a1  lea     rcx, [rsp+7D0h+var_790]; unsigned int *
0x1800b51a6  mov     rdx, r9; void *
0x1800b51a9  call    ?PcaUtilityGetEntryTagRef@@YAKPEAKPEAXPEBG@Z; PcaUtilityGetEntryTagRef(ulong *,void *,ushort const *)
0x1800b51ae  mov     ebx, eax
0x1800b51b0  test    eax, eax
0x1800b51b2  jnz     loc_1800B5337
0x1800b51b8  mov     rbx, [rsp+7D0h+var_788]
0x1800b51bd  mov     r12d, [rsp+7D0h+var_790]
0x1800b51c2  mov     rcx, rbx; void *
0x1800b51c5  mov     edx, r12d; unsigned int
0x1800b51c8  call    ?PcaUtilityCheckApphelpFlag@@YAKPEAXK@Z; PcaUtilityCheckApphelpFlag(void *,ulong)
0x1800b51cd  test    eax, eax
0x1800b51cf  jz      short loc_1800B51EE
0x1800b51d1  lea     r9, aTheApphelpTagD; "The apphelp tag doesn't exit or entry i"...
0x1800b51d8  mov     dword ptr [rsp+7D0h+lpBuffer], eax
0x1800b51dc  mov     r8d, 12Dh
0x1800b51e2  mov     rdx, rsi
0x1800b51e5  mov     ecx, edi
0x1800b51e7  call    AslLogCallPrintf
0x1800b51ec  jmp     short loc_1800B5256
0x1800b51ee  mov     r9, rbx; void *
0x1800b51f1  mov     [rsp+7D0h+var_790], 4
0x1800b51f9  lea     r8, aRemovedosversi; "RemovedOsVersion"
0x1800b5200  mov     dword ptr [rsp+7D0h+lpBuffer], r12d; unsigned int
0x1800b5205  lea     rdx, [rsp+7D0h+var_790]; unsigned int *
0x1800b520a  lea     rcx, [rsp+7D0h+var_78C]; void *
0x1800b520f  call    ?PcaUtilityGetApphelpExtraData@@YAKPEAXPEAKPEBG0K@Z; PcaUtilityGetApphelpExtraData(void *,ulong *,ushort const *,void *,ulong)
0x1800b5214  mov     ebx, eax
0x1800b5216  test    eax, eax
0x1800b5218  jnz     loc_1800B5328
0x1800b521e  mov     rcx, [rsp+7D0h+var_770]
0x1800b5223  mov     eax, [rsp+7D0h+var_78C]
0x1800b5227  cmp     [rcx+1270h], eax
0x1800b522d  jb      loc_1800B52BF
0x1800b5233  mov     rcx, [rsp+7D0h+var_768]; unsigned __int64
0x1800b5238  call    ?PcapChainFromHandle@@YAPEAU_PCA_CHAIN@@_K@Z; PcapChainFromHandle(unsigned __int64)
0x1800b523d  lea     r9, aIgnoredApplica; "Ignored,Application OS version is later"...
0x1800b5244  xor     r8d, r8d; unsigned int
0x1800b5247  lea     rcx, aResolverDeprec_0; "Resolver,DeprecatedCom"
0x1800b524e  mov     edx, [rax+10h]; unsigned int
0x1800b5251  call    ?PcaTracePrintf@@YAXPEBDIK0ZZ; PcaTracePrintf(char const *,uint,ulong,char const *,...)
0x1800b5256  mov     rbx, [rsp+7D0h+var_760]
0x1800b525b  add     r15, rdi
0x1800b525e  mov     r12, r13
0x1800b5261  mov     rax, [rbx+10h]
0x1800b5265  cmp     r15, rax
0x1800b5268  jb      loc_1800B5160
0x1800b526e  cmp     [rbp+6D0h+var_650], r12w
0x1800b5276  jz      loc_1800B5503
0x1800b527c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes> `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl(void)'::`2'::impl
0x1800b5283  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(void)
0x1800b5288  mov     edx, 708h; uID
0x1800b528d  mov     rcx, r14; unsigned __int64
0x1800b5290  test    al, al
0x1800b5292  jz      loc_1800B5454
0x1800b5298  mov     r8d, 834h; UINT
0x1800b529e  call    ?PcaDialogLoadStrings@@YAK_KIII@Z; PcaDialogLoadStrings(unsigned __int64,uint,uint,uint)
0x1800b52a3  mov     ebx, eax
0x1800b52a5  test    eax, eax
0x1800b52a7  jz      loc_1800B5357
0x1800b52ad  lea     r9, aFailedToReadDi_0; "Failed to read dialog strings [%d]"
0x1800b52b4  mov     r8d, 174h
0x1800b52ba  jmp     loc_1800B5344
0x1800b52bf  mov     r15, [rsp+7D0h+var_788]
0x1800b52c4  lea     rdx, [rbp+6D0h+var_750]; LPOLESTR
0x1800b52c8  mov     r8, r15; void *
0x1800b52cb  lea     rcx, [rbp+6D0h+sz]; lpsz
0x1800b52cf  mov     r9d, r12d; unsigned int
0x1800b52d2  call    ?PcaUtilityGetGuidInfo@@YAKPEAG0PEAXK@Z; PcaUtilityGetGuidInfo(ushort *,ushort *,void *,ulong)
0x1800b52d7  mov     ebx, eax
0x1800b52d9  test    eax, eax
0x1800b52db  jz      short loc_1800B52EC
0x1800b52dd  lea     r9, aFailedToReadTh_1; "Failed to read the guid info [%d]"
0x1800b52e4  mov     r8d, 14Fh
0x1800b52ea  jmp     short loc_1800B5344
0x1800b52ec  mov     r9, r15; void *
0x1800b52ef  mov     dword ptr [rsp+7D0h+lpBuffer], r12d; unsigned int
0x1800b52f4  lea     r8, aDllname; "DllName"
0x1800b52fb  lea     rdx, [rsp+7D0h+var_780]; unsigned int *
0x1800b5300  lea     rcx, [rbp+6D0h+var_650]; void *
0x1800b5307  call    ?PcaUtilityGetApphelpExtraData@@YAKPEAXPEAKPEBG0K@Z; PcaUtilityGetApphelpExtraData(void *,ulong *,ushort const *,void *,ulong)
0x1800b530c  xor     r12d, r12d
0x1800b530f  mov     ebx, eax
0x1800b5311  test    eax, eax
0x1800b5313  jz      loc_1800B526E
0x1800b5319  lea     r9, aFailedToReadDl_1; "Failed to read Dll name [%d]"
0x1800b5320  mov     r8d, 15Eh
0x1800b5326  jmp     short loc_1800B5344
0x1800b5328  lea     r9, aFailedToReadTh_6; "Failed to read the Os version info [%d]"
0x1800b532f  mov     r8d, 139h
0x1800b5335  jmp     short loc_1800B5344
0x1800b5337  lea     r9, aFailedToGetThe_35; "Failed to get the entry tag ref [%d]"
0x1800b533e  mov     r8d, 127h
0x1800b5344  mov     rdx, rsi
0x1800b5347  mov     dword ptr [rsp+7D0h+lpBuffer], eax
0x1800b534b  mov     ecx, edi
0x1800b534d  call    AslLogCallPrintf
0x1800b5352  jmp     loc_1800B5506
0x1800b5357  mov     r9, r14; unsigned __int64
0x1800b535a  lea     rdx, [rbp+6D0h+Source]; unsigned __int16 *
0x1800b5361  call    ?PcaDialogGetStrings@@YAKPEAG00_K@Z; PcaDialogGetStrings(ushort *,ushort *,ushort *,unsigned __int64)
0x1800b5366  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800b536a  lea     rdx, [rbp+6D0h+var_650]
0x1800b5371  mov     rcx, rax
0x1800b5374  inc     rcx
0x1800b5377  cmp     [rdx+rcx*2], r12w
0x1800b537c  jnz     short loc_1800B5374
0x1800b537e  lea     rdx, [rbp+6D0h+Source]
0x1800b5385  inc     rax
0x1800b5388  cmp     [rdx+rax*2], r12w
0x1800b538d  jnz     short loc_1800B5385
0x1800b538f  lea     r15, [rcx+1]
0x1800b5393  mov     ebx, 8
0x1800b5398  mov     rcx, gs:60h
0x1800b53a1  add     r15, rax
0x1800b53a4  mov     edx, ebx; Flags
0x1800b53a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800b53aa  lea     r8, [r15+r15]; Size
0x1800b53ae  call    cs:__imp_RtlAllocateHeap
0x1800b53b4  mov     r13, rax
0x1800b53b7  test    rax, rax
0x1800b53ba  jnz     short loc_1800B53D8
0x1800b53bc  lea     r9, aOutOfMemory; "Out of memory"
0x1800b53c3  mov     r8d, 181h
0x1800b53c9  mov     rdx, rsi
0x1800b53cc  mov     ecx, edi
0x1800b53ce  call    AslLogCallPrintf
0x1800b53d3  jmp     loc_1800B5506
0x1800b53d8  lea     rax, [rsp+7D0h+var_758]
0x1800b53dd  xor     r9d, r9d; dwLanguageId
0x1800b53e0  mov     [rsp+7D0h+Arguments], rax; Arguments
0x1800b53e5  lea     rdx, [rbp+6D0h+Source]; lpSource
0x1800b53ec  mov     [rsp+7D0h+nSize], r15d; nSize
0x1800b53f1  xor     r8d, r8d; dwMessageId
0x1800b53f4  mov     ecx, 2400h; dwFlags
0x1800b53f9  mov     [rsp+7D0h+lpBuffer], r13; lpBuffer
0x1800b53fe  call    cs:__imp_FormatMessageW
0x1800b5404  test    eax, eax
0x1800b5406  jnz     short loc_1800B542C
0x1800b5408  call    cs:__imp_GetLastError
0x1800b540e  mov     ebx, 54Fh
0x1800b5413  lea     r9, aFormatmessagew; "FormatMessageW failed [%d]."
0x1800b541a  test    eax, eax
0x1800b541c  mov     r8d, 193h
0x1800b5422  cmovz   eax, ebx
0x1800b5425  mov     ebx, eax
0x1800b5427  jmp     loc_1800B5344
0x1800b542c  xor     r9d, r9d; unsigned __int16 *
0x1800b542f  mov     r8, r13; unsigned __int16 *
0x1800b5432  xor     edx, edx; unsigned __int16 *
0x1800b5434  mov     rcx, r14; unsigned __int64
0x1800b5437  call    ?PcaDialogSetStrings@@YAK_KPEBG11@Z; PcaDialogSetStrings(unsigned __int64,ushort const *,ushort const *,ushort const *)
0x1800b543c  mov     ebx, eax
0x1800b543e  test    eax, eax
0x1800b5440  jz      short loc_1800B5477
0x1800b5442  lea     r9, aFailedToSetDia; "Failed to set dialog strings [%d]"
0x1800b5449  mov     r8d, 1A0h
0x1800b544f  jmp     loc_1800B5344
0x1800b5454  mov     r8d, 70Dh; UINT
0x1800b545a  call    ?PcaDialogLoadStrings@@YAK_KIII@Z; PcaDialogLoadStrings(unsigned __int64,uint,uint,uint)
0x1800b545f  mov     ebx, eax
0x1800b5461  test    eax, eax
0x1800b5463  jz      short loc_1800B5477
0x1800b5465  lea     r9, aFailedToReadDi_0; "Failed to read dialog strings [%d]"
0x1800b546c  mov     r8d, 1AEh
0x1800b5472  jmp     loc_1800B5344
0x1800b5477  lea     rcx, aPcasvcDll_0; "pcasvc.dll"
0x1800b547e  call    cs:__imp_GetModuleHandleW
0x1800b5484  mov     r9d, 100h; cchBufferMax
0x1800b548a  lea     r8, [rbp+6D0h+Buffer]; lpBuffer
0x1800b5491  mov     rcx, rax; hInstance
0x1800b5494  mov     edx, 70Ch; uID
0x1800b5499  call    cs:__imp_LoadStringW
0x1800b549f  test    eax, eax
0x1800b54a1  jnz     short loc_1800B54BD
0x1800b54a3  call    cs:__imp_GetLastError
0x1800b54a9  lea     r9, aFailedToLoadRe; "Failed to load resource strings [%d]"
0x1800b54b0  mov     r8d, 1BCh
0x1800b54b6  mov     ebx, eax
0x1800b54b8  jmp     loc_1800B5344
0x1800b54bd  or      [r14+4], edi
0x1800b54c1  lea     rax, [rbp+6D0h+var_650]
0x1800b54c8  lea     r9, [rbp+6D0h+var_750]; unsigned __int16 *
0x1800b54cc  mov     [rsp+7D0h+lpBuffer], rax; unsigned __int16 *
0x1800b54d1  lea     r8, [rbp+6D0h+sz]; unsigned __int16 *
0x1800b54d5  mov     dword ptr [r14], 4
0x1800b54dc  lea     rdx, [rbp+6D0h+Buffer]; unsigned __int16 *
0x1800b54e3  mov     rcx, r14; unsigned __int64
0x1800b54e6  call    ?PcaDialogAddCheckOnlineButton@@YAK_KPEBG111@Z; PcaDialogAddCheckOnlineButton(unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *)
0x1800b54eb  mov     ebx, eax
0x1800b54ed  test    eax, eax
0x1800b54ef  jz      short loc_1800B5503
0x1800b54f1  lea     r9, aFailedToAddChe; "Failed to add check online button [%d]"
0x1800b54f8  mov     r8d, 1C8h
0x1800b54fe  jmp     loc_1800B5344
0x1800b5503  mov     ebx, r12d
0x1800b5506  mov     rcx, [rsp+7D0h+var_788]
0x1800b550b  call    SdbReleaseDatabase
0x1800b5510  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes> `wil::Feature<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::GetImpl(void)'::`2'::impl
0x1800b5517  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_PcaDeprecatedDllFixes@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PcaDeprecatedDllFixes>::__private_IsEnabled(void)
0x1800b551c  test    al, al
0x1800b551e  jz      short loc_1800B553D
0x1800b5520  test    r13, r13
0x1800b5523  jz      short loc_1800B553D
0x1800b5525  mov     rcx, gs:60h
0x1800b552e  mov     r8, r13; P
0x1800b5531  xor     edx, edx; Flags
0x1800b5533  mov     rcx, [rcx+30h]; HeapHandle
0x1800b5537  call    cs:__imp_RtlFreeHeap
0x1800b553d  mov     eax, ebx
0x1800b553f  mov     rcx, [rbp+6D0h+var_40]
0x1800b5546  xor     rcx, rsp; StackCookie
0x1800b5549  call    __security_check_cookie
0x1800b554e  mov     rbx, [rsp+7D0h+arg_18]
0x1800b5556  add     rsp, 7A0h
0x1800b555d  pop     r15
0x1800b555f  pop     r14
0x1800b5561  pop     r13
0x1800b5563  pop     r12
0x1800b5565  pop     rdi
0x1800b5566  pop     rsi
0x1800b5567  pop     rbp
0x1800b5568  retn
```
