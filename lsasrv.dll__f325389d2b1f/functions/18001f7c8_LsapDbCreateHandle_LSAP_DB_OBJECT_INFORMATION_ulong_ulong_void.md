# LsapDbCreateHandle(_LSAP_DB_OBJECT_INFORMATION *,ulong,ulong,void * *)

- ea: `0x18001f7c8`
- end: `0x18001fdd6`
- name: `?LsapDbCreateHandle@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@KKPEAPEAX@Z`
- size: `1550`
- prototype: `__int64 __fastcall(struct _LSAP_DB_OBJECT_INFORMATION *, unsigned int, unsigned int, void **)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x18001efd0`
- `0x18010c0e0`

## callees

- `0x18000c300`
- `0x18000dd90`
- `0x180011278`
- `0x180014160`
- `0x18001c740`
- `0x18001f7c8`
- `0x18001fde0`
- `0x18005578c`
- `0x180097568`
- `0x1800a0cd8`
- `0x1800a14ec`
- `0x1800ada18`
- `0x18012d0f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fdc5`
- `ntdll!RtlCopySid` at `0x18001fceb`
- `ntdll!RtlCopySid` at `0x18001fceb`
- `ntdll!RtlAllocateHeap` at `0x18001f8d5`
- `ntdll!RtlAllocateHeap` at `0x18001f8d5`
- `ntdll!RtlFreeUnicodeString` at `0x18001fd77`
- `ntdll!RtlFreeUnicodeString` at `0x18001fd77`
- `ntdll!RtlValidSid` at `0x18001fca1`
- `ntdll!RtlValidSid` at `0x18001fca1`
- `ntdll!RtlLengthSid` at `0x18001fcbe`
- `ntdll!RtlLengthSid` at `0x18001fcbe`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f8a9`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f95b`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f8a9`
- `ntdll!RtlLeaveCriticalSection` at `0x18001f95b`
- `ntdll!RtlEnterCriticalSection` at `0x18001f843`
- `ntdll!RtlEnterCriticalSection` at `0x18001fb58`
- `ntdll!RtlEnterCriticalSection` at `0x18001f843`
- `ntdll!RtlEnterCriticalSection` at `0x18001fb58`

## pseudocode

```c
__int64 __fastcall LsapDbCreateHandle(struct _LSAP_DB_OBJECT_INFORMATION *a1, int a2, unsigned int a3, void **a4)
{
  unsigned __int8 v6; // r13
  void *v7; // r12
  char *Heap; // rbx
  int TokenUserSid; // edi
  int v10; // esi
  __int64 v12; // rax
  int RpcClientLUIDAndToken; // eax
  struct _UNICODE_STRING *v14; // rdi
  __int64 v15; // rax
  struct _UNICODE_STRING *v16; // r15
  __int64 v17; // rax
  bool v18; // al
  __int64 v19; // rax
  bool v20; // cl
  bool v21; // dl
  _WORD *v22; // rbp
  void *v23; // rdx
  void *v24; // rdi
  LsaHandleCache *v25; // rcx
  int v26; // eax
  LsaHandleCache *v27; // rcx
  ULONG v28; // esi
  void *NoZero; // rax
  struct _RTL_BALANCED_NODE *v30; // rcx
  struct _RTL_BALANCED_NODE *v31; // rcx
  struct _LUID v32; // [rsp+30h] [rbp-48h] BYREF
  void *v33; // [rsp+38h] [rbp-40h] BYREF
  int v34; // [rsp+88h] [rbp+10h]

  v6 = LsaDbExtIsDsWriteDs();
  v32 = 0;
  v7 = 0;
  v33 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    v34 = 0;
  }
  else
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 38, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids);
    RtlEnterCriticalSection(&stru_18019F240);
    v34 = 1;
  }
  v32 = LsapZeroLogonId;
  if ( (a2 & 0x40) == 0 )
  {
    v12 = *((_QWORD *)a1 + 2);
    if ( !v12 || !*(_BYTE *)(v12 + 133) )
    {
      if ( (a2 & 0x10000000) != 0 )
      {
        RpcClientLUIDAndToken = LsapGetRpcClientLUIDAndToken(&v32, &v33, 0);
        v7 = v33;
        TokenUserSid = RpcClientLUIDAndToken;
        if ( RpcClientLUIDAndToken < 0 )
          goto LABEL_12;
      }
      else
      {
        LsapGetRpcClientLUIDAndToken(&v32, 0, 0);
      }
    }
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids);
    RtlLeaveCriticalSection(&stru_18019F240);
    v34 = 0;
  }
  Heap = (char *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0xC0u);
  if ( !Heap )
  {
    TokenUserSid = -1073741670;
LABEL_12:
    Heap = 0;
LABEL_13:
    v10 = v34;
    goto LABEL_14;
  }
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
    Heap[48] = 1;
  *((_QWORD *)Heap + 12) = 0;
  v14 = (struct _UNICODE_STRING *)(Heap + 56);
  *((_DWORD *)Heap + 13) = 1;
  *((_DWORD *)Heap + 26) = *(_DWORD *)a1;
  v15 = *((_QWORD *)a1 + 2);
  *((_QWORD *)Heap + 11) = 0;
  *(_WORD *)(Heap + 133) = 0;
  Heap[132] = 0;
  *((_QWORD *)Heap + 8) = 0;
  *((_QWORD *)Heap + 10) = 0;
  v16 = (struct _UNICODE_STRING *)(Heap + 144);
  *((_QWORD *)Heap + 14) = v15;
  *((_QWORD *)Heap + 19) = 0;
  *((_DWORD *)Heap + 34) = a2;
  *((_DWORD *)Heap + 32) = *((_DWORD *)a1 + 17);
  *((_QWORD *)Heap + 3) = Heap + 16;
  *((_QWORD *)Heap + 2) = Heap + 16;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    *((_QWORD *)Heap + 5) = Heap + 32;
    *((_QWORD *)Heap + 4) = Heap + 32;
  }
  *((_QWORD *)Heap + 21) = 0;
  Heap[49] = (a2 & 0x40000000) != 0;
  v17 = *((_QWORD *)a1 + 2);
  v18 = v17 && *(_BYTE *)(v17 + 49);
  Heap[50] = v18;
  v19 = *((_QWORD *)Heap + 14);
  v20 = v19 && *(_BYTE *)(v19 + 176);
  Heap[176] = v20;
  if ( v19 )
    Heap[133] = *(_BYTE *)(v19 + 133);
  if ( (a2 & 0x40) != 0 )
    Heap[133] = 1;
  if ( (a2 & 0x10000000) != 0 )
  {
    TokenUserSid = LsapQueryTokenUserSid(v7, (void **)Heap + 23);
    if ( TokenUserSid < 0 )
    {
      v22 = Heap + 72;
      goto LABEL_84;
    }
    v14 = (struct _UNICODE_STRING *)(Heap + 56);
  }
  v21 = 1;
  v16->Length = 0;
  if ( *(_DWORD *)a1 == 1 )
    goto LABEL_46;
  if ( *(_DWORD *)a1 != 2 )
  {
    if ( *(_DWORD *)a1 == 3 )
    {
LABEL_46:
      v16 = 0;
      goto LABEL_47;
    }
    if ( *(_DWORD *)a1 == 4 )
    {
      if ( !v6 || (a2 & 0x100000) == 0 )
        goto LABEL_46;
      goto LABEL_47;
    }
    if ( *(_DWORD *)a1 != 6 )
      goto LABEL_46;
  }
  *((_DWORD *)Heap + 26) = 2;
  v21 = v6 == 0;
  if ( !v6 )
    goto LABEL_46;
LABEL_47:
  v22 = Heap + 72;
  TokenUserSid = LsapDbGetNamesObject(
                   a1,
                   a3,
                   v14,
                   (struct _UNICODE_STRING *)((unsigned __int64)(Heap + 72) & -(__int64)v21),
                   v16);
  if ( TokenUserSid < 0 )
  {
LABEL_84:
    v30 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)Heap + 11);
    if ( v30 )
      LsapSubProv_FreeRoutine(v30, v23);
    if ( *((_WORD *)Heap + 28) && *((_QWORD *)Heap + 8) )
      RtlFreeUnicodeString((PUNICODE_STRING)(Heap + 56));
    if ( *v22 )
    {
      v31 = (struct _RTL_BALANCED_NODE *)*((_QWORD *)Heap + 10);
      if ( v31 )
        LsapSubProv_FreeRoutine(v31, v23);
    }
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)Heap, v23);
    goto LABEL_12;
  }
  v24 = (void *)*((_QWORD *)a1 + 7);
  if ( !v24 )
    goto LABEL_49;
  if ( !RtlValidSid(*((PSID *)a1 + 7)) )
  {
    TokenUserSid = -1073741704;
    goto LABEL_84;
  }
  v28 = RtlLengthSid(v24);
  NoZero = (void *)LsapAllocateNoZero(v28);
  *((_QWORD *)Heap + 11) = NoZero;
  if ( !NoZero )
  {
    TokenUserSid = -1073741670;
    goto LABEL_84;
  }
  RtlCopySid(v28, NoZero, v24);
LABEL_49:
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl) )
  {
    if ( gpLsaHandleCache )
    {
      v26 = LsaHandleCache::Insert(v25, (struct _LSAP_DB_HANDLE *)Heap, &v32);
      v27 = WPP_GLOBAL_Control;
      TokenUserSid = v26;
      if ( v26 >= 0 )
      {
        _InterlockedIncrement(&dword_18019F178);
        goto LABEL_13;
      }
      if ( *((char *)WPP_GLOBAL_Control + 108) >= 0 )
        goto LABEL_81;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 12),
        63,
        &WPP_27dc9bbfa4593641296446d8de402159_Traceguids,
        (unsigned int)v26);
    }
    else
    {
      TokenUserSid = -1073741595;
    }
    v27 = WPP_GLOBAL_Control;
LABEL_81:
    if ( *((char *)v27 + 108) < 0 )
      WPP_SF_d(*((_QWORD *)v27 + 12), 40, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids, (unsigned int)TokenUserSid);
    goto LABEL_84;
  }
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids, Heap);
  RtlEnterCriticalSection(&stru_18019F240);
  v10 = 1;
  v34 = 1;
  TokenUserSid = LsapDbInsertHandleInTable(a1, Heap, &v32);
  if ( TokenUserSid < 0 )
    goto LABEL_84;
  ++dword_18019F178;
LABEL_14:
  *a4 = Heap;
  if ( *((char *)WPP_GLOBAL_Control + 108) < 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids, Heap);
  if ( !wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl'::`2'::impl)
    && v10 )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0 )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, &WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids, Heap);
    RtlLeaveCriticalSection(&stru_18019F240);
  }
  if ( v7 )
    CloseHandle(v7);
  return (unsigned int)TokenUserSid;
}

```

## disassembly

```asm
0x18001f7c8  mov     [rsp+arg_0], rbx
0x18001f7cd  mov     [rsp+arg_18], r9
0x18001f7d2  mov     [rsp+arg_10], r8d
0x18001f7d7  push    rbp
0x18001f7d8  push    rsi
0x18001f7d9  push    rdi
0x18001f7da  push    r12
0x18001f7dc  push    r13
0x18001f7de  push    r14
0x18001f7e0  push    r15
0x18001f7e2  sub     rsp, 40h
0x18001f7e6  mov     esi, edx
0x18001f7e8  mov     r14, rcx
0x18001f7eb  call    ?LsaDbExtIsDsWriteDs@@YAEXZ; LsaDbExtIsDsWriteDs(void)
0x18001f7f0  xor     r15d, r15d
0x18001f7f3  mov     r13b, al
0x18001f7f6  mov     qword ptr [rsp+78h+var_48.LowPart], r15
0x18001f7fb  mov     r12d, r15d
0x18001f7fe  mov     [rsp+78h+var_40], r15
0x18001f803  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001f80a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001f80f  mov     ebx, 800h
0x18001f814  test    al, al
0x18001f816  jnz     loc_18001FBD8
0x18001f81c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f823  test    [rcx+6Ch], ebx
0x18001f826  jz      short loc_18001F83C
0x18001f828  mov     rcx, [rcx+60h]
0x18001f82c  lea     edx, [r15+26h]
0x18001f830  lea     r8, WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids
0x18001f837  call    WPP_SF_
0x18001f83c  lea     rcx, stru_18019F240; CriticalSection
0x18001f843  call    cs:__imp_RtlEnterCriticalSection
0x18001f84a  nop     dword ptr [rax+rax+00h]
0x18001f84f  mov     [rsp+78h+arg_8], 1
0x18001f85a  mov     rax, cs:?LsapZeroLogonId@@3U_LUID@@A; _LUID LsapZeroLogonId
0x18001f861  mov     ebp, esi
0x18001f863  mov     qword ptr [rsp+78h+var_48.LowPart], rax
0x18001f868  and     ebp, 40h
0x18001f86b  jz      loc_18001F98B
0x18001f871  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001f878  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001f87d  test    al, al
0x18001f87f  jnz     short loc_18001F8BD
0x18001f881  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f888  test    [rcx+6Ch], ebx
0x18001f88b  jz      short loc_18001F8A2
0x18001f88d  mov     rcx, [rcx+60h]
0x18001f891  lea     r8, WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids
0x18001f898  mov     edx, 27h ; '''
0x18001f89d  call    WPP_SF_
0x18001f8a2  lea     rcx, stru_18019F240; CriticalSection
0x18001f8a9  call    cs:__imp_RtlLeaveCriticalSection
0x18001f8b0  nop     dword ptr [rax+rax+00h]
0x18001f8b5  mov     [rsp+78h+arg_8], r15d
0x18001f8bd  mov     rcx, gs:60h
0x18001f8c6  mov     edx, 8; Flags
0x18001f8cb  mov     r8d, 0C0h; Size
0x18001f8d1  mov     rcx, [rcx+30h]; HeapHandle
0x18001f8d5  call    cs:__imp_RtlAllocateHeap
0x18001f8dc  nop     dword ptr [rax+rax+00h]
0x18001f8e1  mov     rbx, rax
0x18001f8e4  test    rax, rax
0x18001f8e7  jnz     loc_18001F9C8
0x18001f8ed  mov     edi, 0C000009Ah
0x18001f8f2  mov     rbx, r15
0x18001f8f5  mov     esi, [rsp+78h+arg_8]
0x18001f8fc  mov     rax, [rsp+78h+arg_18]
0x18001f904  mov     [rax], rbx
0x18001f907  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f90e  test    byte ptr [rcx+6Ch], 80h
0x18001f912  jnz     loc_18001FDA5
0x18001f918  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001f91f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001f924  test    al, al
0x18001f926  jnz     short loc_18001F967
0x18001f928  test    esi, esi
0x18001f92a  jz      short loc_18001F967
0x18001f92c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f933  test    dword ptr [rcx+6Ch], 800h
0x18001f93a  jz      short loc_18001F954
0x18001f93c  mov     rcx, [rcx+60h]
0x18001f940  lea     r8, WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids
0x18001f947  mov     edx, 2Bh ; '+'
0x18001f94c  mov     r9, rbx
0x18001f94f  call    WPP_SF_q
0x18001f954  lea     rcx, stru_18019F240; CriticalSection
0x18001f95b  call    cs:__imp_RtlLeaveCriticalSection
0x18001f962  nop     dword ptr [rax+rax+00h]
0x18001f967  test    r12, r12
0x18001f96a  jnz     loc_18001FDC2
0x18001f970  mov     rbx, [rsp+78h+arg_0]
0x18001f978  mov     eax, edi
0x18001f97a  add     rsp, 40h
0x18001f97e  pop     r15
0x18001f980  pop     r14
0x18001f982  pop     r13
0x18001f984  pop     r12
0x18001f986  pop     rdi
0x18001f987  pop     rsi
0x18001f988  pop     rbp
0x18001f989  retn
0x18001f98b  mov     rax, [r14+10h]
0x18001f98f  test    rax, rax
0x18001f992  jnz     loc_18001FBE5
0x18001f998  xor     r8d, r8d; unsigned int
0x18001f99b  lea     rcx, [rsp+78h+var_48]; struct _LUID *
0x18001f9a0  bt      esi, 1Ch
0x18001f9a4  jnb     loc_18001FB95
0x18001f9aa  lea     rdx, [rsp+78h+var_40]; void **
0x18001f9af  call    ?LsapGetRpcClientLUIDAndToken@@YAJPEAU_LUID@@PEAPEAXK@Z; LsapGetRpcClientLUIDAndToken(_LUID *,void * *,ulong)
0x18001f9b4  mov     r12, [rsp+78h+var_40]
0x18001f9b9  mov     edi, eax
0x18001f9bb  test    eax, eax
0x18001f9bd  jns     loc_18001F871
0x18001f9c3  jmp     loc_18001F8F2
0x18001f9c8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001f9cf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001f9d4  test    al, al
0x18001f9d6  jnz     short loc_18001F9DC
0x18001f9d8  mov     byte ptr [rbx+30h], 1
0x18001f9dc  mov     [rbx+60h], r15
0x18001f9e0  lea     rdi, [rbx+38h]
0x18001f9e4  mov     dword ptr [rbx+34h], 1
0x18001f9eb  mov     eax, [r14]
0x18001f9ee  mov     [rbx+68h], eax
0x18001f9f1  mov     rax, [r14+10h]
0x18001f9f5  mov     [rbx+58h], r15
0x18001f9f9  mov     [rbx+85h], r15w
0x18001fa01  mov     [rbx+84h], r15b
0x18001fa08  mov     [rdi+8], r15
0x18001fa0c  mov     [rbx+50h], r15
0x18001fa10  lea     r15, [rbx+90h]
0x18001fa17  mov     [rbx+70h], rax
0x18001fa1b  mov     qword ptr [r15+8], 0
0x18001fa23  mov     [rbx+88h], esi
0x18001fa29  mov     eax, [r14+44h]
0x18001fa2d  mov     [rbx+80h], eax
0x18001fa33  lea     rax, [rbx+10h]
0x18001fa37  mov     [rax+8], rax
0x18001fa3b  mov     [rax], rax
0x18001fa3e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001fa45  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001fa4a  test    al, al
0x18001fa4c  jnz     loc_18001FBF7
0x18001fa52  mov     eax, esi
0x18001fa54  mov     qword ptr [rbx+0A8h], 0
0x18001fa5f  shr     eax, 1Eh
0x18001fa62  and     al, 1
0x18001fa64  mov     [rbx+31h], al
0x18001fa67  mov     rax, [r14+10h]
0x18001fa6b  test    rax, rax
0x18001fa6e  jnz     loc_18001FC07
0x18001fa74  xor     eax, eax
0x18001fa76  mov     [rbx+32h], al
0x18001fa79  mov     rax, [rbx+70h]
0x18001fa7d  test    rax, rax
0x18001fa80  jnz     loc_18001FC18
0x18001fa86  xor     ecx, ecx
0x18001fa88  mov     [rbx+0B0h], cl
0x18001fa8e  test    rax, rax
0x18001fa91  jnz     loc_18001FC2C
0x18001fa97  test    ebp, ebp
0x18001fa99  jnz     loc_18001FC3D
0x18001fa9f  bt      esi, 1Ch
0x18001faa3  jb      loc_18001FC49
0x18001faa9  xor     eax, eax
0x18001faab  mov     dl, 1
0x18001faad  mov     [r15], ax
0x18001fab1  mov     ecx, [r14]
0x18001fab4  sub     ecx, 1
0x18001fab7  jz      short loc_18001FAD9
0x18001fab9  sub     ecx, 1
0x18001fabc  jz      loc_18001FC83
0x18001fac2  sub     ecx, 1
0x18001fac5  jz      short loc_18001FAD9
0x18001fac7  sub     ecx, 1
0x18001faca  jz      loc_18001FC6B
0x18001fad0  cmp     ecx, 2
0x18001fad3  jz      loc_18001FC83
0x18001fad9  xor     r15d, r15d
0x18001fadc  neg     dl
0x18001fade  mov     [rsp+78h+var_58], r15; struct _UNICODE_STRING *
0x18001fae3  mov     edx, [rsp+78h+arg_10]; unsigned int
0x18001faea  lea     rbp, [rbx+48h]
0x18001faee  sbb     r9, r9
0x18001faf1  mov     r8, rdi; struct _UNICODE_STRING *
0x18001faf4  and     r9, rbp; struct _UNICODE_STRING *
0x18001faf7  mov     rcx, r14; struct _LSAP_DB_OBJECT_INFORMATION *
0x18001fafa  call    ?LsapDbGetNamesObject@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@KPEAU_UNICODE_STRING@@11@Z; LsapDbGetNamesObject(_LSAP_DB_OBJECT_INFORMATION *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x18001faff  xor     r15d, r15d
0x18001fb02  mov     edi, eax
0x18001fb04  test    eax, eax
0x18001fb06  js      loc_18001FD59
0x18001fb0c  mov     rdi, [r14+38h]
0x18001fb10  test    rdi, rdi
0x18001fb13  jnz     loc_18001FC9E
0x18001fb19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements> `wil::Feature<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::GetImpl(void)'::`2'::impl
0x18001fb20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_LsaHandleCache_Improvements>::__private_IsEnabled(void)
0x18001fb25  test    al, al
0x18001fb27  jnz     short loc_18001FBA1
0x18001fb29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb30  test    dword ptr [rcx+6Ch], 800h
0x18001fb37  jz      short loc_18001FB51
0x18001fb39  mov     rcx, [rcx+60h]
0x18001fb3d  lea     r8, WPP_c9e206ddee0b3a6fc7b8330ee59b4bb3_Traceguids
0x18001fb44  mov     edx, 29h ; ')'
0x18001fb49  mov     r9, rbx
0x18001fb4c  call    WPP_SF_q
0x18001fb51  lea     rcx, stru_18019F240; CriticalSection
0x18001fb58  call    cs:__imp_RtlEnterCriticalSection
0x18001fb5f  nop     dword ptr [rax+rax+00h]
0x18001fb64  mov     esi, 1
0x18001fb69  lea     r8, [rsp+78h+var_48]; struct _LUID *
0x18001fb6e  mov     rdx, rbx; void *
0x18001fb71  mov     [rsp+78h+arg_8], esi
0x18001fb78  mov     rcx, r14; struct _LSAP_DB_OBJECT_INFORMATION *
0x18001fb7b  call    ?LsapDbInsertHandleInTable@@YAJPEAU_LSAP_DB_OBJECT_INFORMATION@@PEAXPEAU_LUID@@@Z; LsapDbInsertHandleInTable(_LSAP_DB_OBJECT_INFORMATION *,void *,_LUID *)
0x18001fb80  mov     edi, eax
0x18001fb82  test    eax, eax
0x18001fb84  js      loc_18001FD59
0x18001fb8a  inc     cs:dword_18019F178
0x18001fb90  jmp     loc_18001F8FC
0x18001fb95  xor     edx, edx; void **
0x18001fb97  call    ?LsapGetRpcClientLUIDAndToken@@YAJPEAU_LUID@@PEAPEAXK@Z; LsapGetRpcClientLUIDAndToken(_LUID *,void * *,ulong)
0x18001fb9c  jmp     loc_18001F871
0x18001fba1  cmp     cs:?gpLsaHandleCache@@3PEAVLsaHandleCache@@EA, r15; LsaHandleCache * gpLsaHandleCache
0x18001fba8  jz      loc_18001FCFC
0x18001fbae  lea     r8, [rsp+78h+var_48]; struct _LUID *
0x18001fbb3  mov     rdx, rbx; struct _LSAP_DB_HANDLE *
0x18001fbb6  call    ?Insert@LsaHandleCache@@QEAAJPEAU_LSAP_DB_HANDLE@@PEAU_LUID@@@Z; LsaHandleCache::Insert(_LSAP_DB_HANDLE *,_LUID *)
0x18001fbbb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbc2  mov     edi, eax
0x18001fbc4  test    eax, eax
0x18001fbc6  js      loc_18001FD24
0x18001fbcc  lock inc cs:dword_18019F178
0x18001fbd3  jmp     loc_18001F8F5
0x18001fbd8  mov     [rsp+78h+arg_8], r15d
0x18001fbe0  jmp     loc_18001F85A
0x18001fbe5  cmp     [rax+85h], r15b
0x18001fbec  jnz     loc_18001F871
0x18001fbf2  jmp     loc_18001F998
0x18001fbf7  lea     rax, [rbx+20h]
0x18001fbfb  mov     [rax+8], rax
0x18001fbff  mov     [rax], rax
0x18001fc02  jmp     loc_18001FA52
0x18001fc07  cmp     byte ptr [rax+31h], 0
0x18001fc0b  jz      loc_18001FA74
0x18001fc11  mov     al, 1
0x18001fc13  jmp     loc_18001FA76
0x18001fc18  cmp     byte ptr [rax+0B0h], 0
0x18001fc1f  jz      loc_18001FA86
0x18001fc25  mov     cl, 1
0x18001fc27  jmp     loc_18001FA88
0x18001fc2c  mov     al, [rax+85h]
0x18001fc32  mov     [rbx+85h], al
0x18001fc38  jmp     loc_18001FA97
0x18001fc3d  mov     byte ptr [rbx+85h], 1
0x18001fc44  jmp     loc_18001FA9F
0x18001fc49  lea     rdx, [rbx+0B8h]; void **
0x18001fc50  mov     rcx, r12; TokenHandle
0x18001fc53  call    ?LsapQueryTokenUserSid@@YAJPEAXPEAPEAX@Z; LsapQueryTokenUserSid(void *,void * *)
0x18001fc58  mov     edi, eax
0x18001fc5a  test    eax, eax
0x18001fc5c  js      loc_18001FD52
0x18001fc62  lea     rdi, [rbx+38h]
0x18001fc66  jmp     loc_18001FAA9
0x18001fc6b  test    r13b, r13b
0x18001fc6e  jz      loc_18001FAD9
0x18001fc74  bt      esi, 14h
0x18001fc78  jnb     loc_18001FAD9
0x18001fc7e  jmp     loc_18001FADC
0x18001fc83  test    r13b, r13b
0x18001fc86  mov     dword ptr [rbx+68h], 2
0x18001fc8d  setz    dl
0x18001fc90  test    r13b, r13b
0x18001fc93  jnz     loc_18001FADC
0x18001fc99  jmp     loc_18001FAD9
0x18001fc9e  mov     rcx, rdi; Sid
0x18001fca1  call    cs:__imp_RtlValidSid
0x18001fca8  nop     dword ptr [rax+rax+00h]
0x18001fcad  test    al, al
0x18001fcaf  jnz     short loc_18001FCBB
0x18001fcb1  mov     edi, 0C0000078h
0x18001fcb6  jmp     loc_18001FD59
0x18001fcbb  mov     rcx, rdi; Sid
0x18001fcbe  call    cs:__imp_RtlLengthSid
0x18001fcc5  nop     dword ptr [rax+rax+00h]
0x18001fcca  mov     ecx, eax
0x18001fccc  mov     esi, eax
0x18001fcce  call    LsapAllocateNoZero
0x18001fcd3  mov     [rbx+58h], rax
0x18001fcd7  test    rax, rax
0x18001fcda  jnz     short loc_18001FCE3
0x18001fcdc  mov     edi, 0C000009Ah
0x18001fce1  jmp     short loc_18001FD59
0x18001fce3  mov     r8, rdi; SourceSid
0x18001fce6  mov     rdx, rax; DestinationSid
0x18001fce9  mov     ecx, esi; DestinationSidLength
0x18001fceb  call    cs:__imp_RtlCopySid
  ... truncated ...
```
