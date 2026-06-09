# CQueryContext::Create(_DEV_QUERY_DATA *,ushort *,ulong,void *,int,int,CQueryContext * *)

- ea: `0x180021fe4`
- end: `0x180022221`
- name: `?Create@CQueryContext@@SAJPEAU_DEV_QUERY_DATA@@PEAGKPEAXHHPEAPEAV1@@Z`
- size: `573`
- prototype: `__int64 __fastcall(struct _DEV_QUERY_DATA *, unsigned __int16 *, unsigned int, void *, int, int, struct CQueryContext **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180026e30`

## callees

- `0x180015488`
- `0x180021fe4`
- `0x180022228`
- `0x18003474c`
- `0x18003c9f8`
- `0x180044c70`
- `0x180050428`
- `0x180053b80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022093`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800220ac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022093`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800220ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800220be`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022068`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180022068`

## pseudocode

```c
__int64 __fastcall CQueryContext::Create(
        struct _DEV_QUERY_DATA *a1,
        unsigned __int16 *a2,
        unsigned int a3,
        void *a4,
        int a5,
        int a6,
        struct CQueryContext **a7)
{
  RTL_SRWLOCK *v11; // rax
  PTP_WORK ThreadpoolWork; // rax
  HANDLE EventW; // rax
  HANDLE v14; // rax
  signed int LastError; // eax
  __int64 *v16; // rdx
  signed int v17; // ebx
  __int64 v18; // r8
  __int64 v19; // r12
  __int128 v20; // kr10_16
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  CQueryContext *v24; // rdi
  __int64 v26; // [rsp+0h] [rbp-78h] BYREF
  CQueryContext *v27; // [rsp+30h] [rbp-48h]

  v27 = 0;
  *a7 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v11 = (RTL_SRWLOCK *)operator new(0x280u);
    v24 = CQueryContext::CQueryContext(v11, a3, a5, a6);
    v27 = v24;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v16 = &v26;
      v17 = -2147024882;
      v24 = v27;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800221F6);
      goto LABEL_31;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl)
    && (ThreadpoolWork = CreateThreadpoolWork(CQueryContext::QueryWork, v24, 0),
        wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
          (char *)v24 + 568,
          ThreadpoolWork),
        !wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator bool((_QWORD *)v24 + 71))
    || (EventW = CreateEventW(0, 1, 0, 0), (*((_QWORD *)v24 + 7) = EventW) == 0)
    || (v14 = CreateEventW(0, 1, 0, 0), (*((_QWORD *)v24 + 54) = v14) == 0) )
  {
    LastError = GetLastError();
    v17 = LastError;
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    if ( v17 < 0 )
      goto LABEL_31;
    return (unsigned int)v17;
  }
  v17 = 0;
  v18 = 0;
  LODWORD(v16) = *((_DWORD *)a1 + 24);
  if ( !(_DWORD)v16 )
    goto LABEL_29;
  v19 = DEVPKEY_DasParam_PassiveScanning;
  v20 = DEVPKEY_DasParam_AepStoreOnly;
  do
  {
    v21 = *((_QWORD *)a1 + 13);
    if ( *(_DWORD *)(v21 + 40 * v18 + 16) == 4 )
    {
      v22 = *(_QWORD *)(v21 + 40 * v18) - v20;
      if ( !v22 )
        v22 = *(_QWORD *)(v21 + 40 * v18 + 8) - *((_QWORD *)&v20 + 1);
      if ( !v22 )
      {
        if ( *((_DWORD *)a1 + 4) == 10 || *(_DWORD *)(v21 + 40 * v18 + 20) != 17 )
        {
LABEL_24:
          v17 = -2147024809;
          goto LABEL_27;
        }
        *((_DWORD *)v24 + 118) = **(_BYTE **)(v21 + 40 * v18 + 32) == 0xFF;
        goto LABEL_26;
      }
    }
    else if ( *(_DWORD *)(v21 + 40 * v18 + 16) == 3 )
    {
      v23 = *(_QWORD *)(v21 + 40 * v18) - v19;
      if ( !v23 )
        v23 = *(_QWORD *)(v21 + 40 * v18 + 8) + 0x428F82CDE07D6A6CLL;
      if ( !v23 )
      {
        if ( *(_DWORD *)(v21 + 40 * v18 + 20) != 17 )
          goto LABEL_24;
        *((_DWORD *)v24 + 119) = **(_BYTE **)(v21 + 40 * v18 + 32) == 0xFF;
LABEL_26:
        v19 = DEVPKEY_DasParam_PassiveScanning;
        v20 = DEVPKEY_DasParam_AepStoreOnly;
      }
    }
LABEL_27:
    v18 = (unsigned int)(v18 + 1);
    LODWORD(v16) = *((_DWORD *)a1 + 24);
  }
  while ( (unsigned int)v18 < (unsigned int)v16 );
  if ( v17 >= 0 )
  {
LABEL_29:
    v17 = SanitizeExtendedParamters(
            a2,
            (unsigned int)v16,
            *((const struct _DEV_QUERY_PARAMETER **)a1 + 13),
            (unsigned int *)v24 + 6,
            (struct _DEV_QUERY_PARAMETER **)v24 + 4);
    if ( v17 >= 0 )
    {
      *((_QWORD *)v24 + 17) = a1;
      *((_QWORD *)v24 + 2) = a2;
      *((_QWORD *)v24 + 51) = a4;
      *a7 = v24;
      return (unsigned int)v17;
    }
  }
LABEL_31:
  if ( v24 )
    CQueryContext::`scalar deleting destructor'(v24, (unsigned int)v16);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180021fe4  push    rbx
0x180021fe6  push    rsi
0x180021fe7  push    rdi
0x180021fe8  push    r12
0x180021fea  push    r13
0x180021fec  push    r14
0x180021fee  push    r15
0x180021ff0  sub     rsp, 40h
0x180021ff4  mov     r13, r9
0x180021ff7  mov     ebx, r8d
0x180021ffa  mov     r15, rdx
0x180021ffd  mov     rsi, rcx
0x180022000  mov     [rsp+78h+var_48], 0
0x180022009  mov     r14, [rsp+78h+arg_30]
0x180022011  mov     qword ptr [r14], 0
0x180022018  mov     ecx, 280h; Size
0x18002201d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180022022  mov     r9d, [rsp+78h+arg_28]; int
0x18002202a  mov     r8d, [rsp+78h+arg_20]; int
0x180022032  mov     edx, ebx; unsigned int
0x180022034  mov     rcx, rax; SRWLock
0x180022037  call    ??0CQueryContext@@IEAA@KHH@Z; CQueryContext::CQueryContext(ulong,int,int)
0x18002203c  mov     rdi, rax
0x18002203f  mov     [rsp+78h+var_48], rax
0x180022044  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x18002204b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180022050  test    al, al
0x180022052  jz      short loc_180022085
0x180022054  lea     rbx, [rdi+238h]
0x18002205b  xor     r8d, r8d; pcbe
0x18002205e  mov     rdx, rdi; pv
0x180022061  lea     rcx, ?QueryWork@CQueryContext@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180022068  call    cs:__imp_CreateThreadpoolWork
0x18002206e  mov     rdx, rax
0x180022071  mov     rcx, rbx
0x180022074  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180022079  mov     rcx, rbx
0x18002207c  call    ??B?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEBA_NXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>>::operator bool(void)
0x180022081  test    al, al
0x180022083  jz      short loc_1800220BE
0x180022085  xor     r9d, r9d; lpName
0x180022088  xor     r8d, r8d; bInitialState
0x18002208b  lea     ebx, [r9+1]
0x18002208f  mov     edx, ebx; bManualReset
0x180022091  xor     ecx, ecx; lpEventAttributes
0x180022093  call    cs:__imp_CreateEventW
0x180022099  mov     [rdi+38h], rax
0x18002209d  test    rax, rax
0x1800220a0  jz      short loc_1800220BE
0x1800220a2  xor     r9d, r9d; lpName
0x1800220a5  xor     r8d, r8d; bInitialState
0x1800220a8  mov     edx, ebx; bManualReset
0x1800220aa  xor     ecx, ecx; lpEventAttributes
0x1800220ac  call    cs:__imp_CreateEventW
0x1800220b2  mov     [rdi+1B0h], rax
0x1800220b9  test    rax, rax
0x1800220bc  jnz     short loc_1800220E0
0x1800220be  call    cs:__imp_GetLastError
0x1800220c4  mov     ebx, eax
0x1800220c6  test    eax, eax
0x1800220c8  jle     short loc_1800220D3
0x1800220ca  movzx   ebx, ax
0x1800220cd  or      ebx, 80070000h
0x1800220d3  test    ebx, ebx
0x1800220d5  js      loc_180022202
0x1800220db  jmp     loc_18002220F
0x1800220e0  xor     ebx, ebx
0x1800220e2  xor     r8d, r8d
0x1800220e5  mov     edx, [rsi+60h]
0x1800220e8  test    edx, edx
0x1800220ea  jz      loc_1800221C0
0x1800220f0  mov     r9, qword ptr cs:DEVPKEY_DasParam_AepStoreOnly+8
0x1800220f7  mov     r10, qword ptr cs:DEVPKEY_DasParam_AepStoreOnly
0x1800220fe  mov     r11, cs:qword_18008CE10
0x180022105  mov     r12, cs:DEVPKEY_DasParam_PassiveScanning
0x18002210c  lea     rax, [r8+r8*4]
0x180022110  mov     rcx, [rsi+68h]
0x180022114  cmp     dword ptr [rcx+rax*8+10h], 4
0x180022119  jnz     short loc_180022153
0x18002211b  mov     rdx, [rcx+rax*8]
0x18002211f  sub     rdx, r10
0x180022122  jnz     short loc_18002212C
0x180022124  mov     rdx, [rcx+rax*8+8]
0x180022129  sub     rdx, r9
0x18002212c  test    rdx, rdx
0x18002212f  jnz     short loc_1800221AD
0x180022131  cmp     dword ptr [rsi+10h], 0Ah
0x180022135  jz      short loc_180022177
0x180022137  cmp     dword ptr [rcx+rax*8+14h], 11h
0x18002213c  jnz     short loc_180022177
0x18002213e  mov     rax, [rcx+rax*8+20h]
0x180022143  xor     ecx, ecx
0x180022145  cmp     byte ptr [rax], 0FFh
0x180022148  setz    cl
0x18002214b  mov     [rdi+1D8h], ecx
0x180022151  jmp     short loc_180022191
0x180022153  cmp     dword ptr [rcx+rax*8+10h], 3
0x180022158  jnz     short loc_1800221AD
0x18002215a  mov     rdx, [rcx+rax*8]
0x18002215e  sub     rdx, r12
0x180022161  jnz     short loc_18002216B
0x180022163  mov     rdx, [rcx+rax*8+8]
0x180022168  sub     rdx, r11
0x18002216b  test    rdx, rdx
0x18002216e  jnz     short loc_1800221AD
0x180022170  cmp     dword ptr [rcx+rax*8+14h], 11h
0x180022175  jz      short loc_18002217E
0x180022177  mov     ebx, 80070057h
0x18002217c  jmp     short loc_1800221AD
0x18002217e  mov     rax, [rcx+rax*8+20h]
0x180022183  xor     ecx, ecx
0x180022185  cmp     byte ptr [rax], 0FFh
0x180022188  setz    cl
0x18002218b  mov     [rdi+1DCh], ecx
0x180022191  mov     r12, cs:DEVPKEY_DasParam_PassiveScanning
0x180022198  mov     r11, cs:qword_18008CE10
0x18002219f  mov     r10, qword ptr cs:DEVPKEY_DasParam_AepStoreOnly
0x1800221a6  mov     r9, qword ptr cs:DEVPKEY_DasParam_AepStoreOnly+8
0x1800221ad  inc     r8d
0x1800221b0  mov     edx, [rsi+60h]; unsigned int
0x1800221b3  cmp     r8d, edx
0x1800221b6  jb      loc_18002210C
0x1800221bc  test    ebx, ebx
0x1800221be  js      short loc_180022202
0x1800221c0  lea     rax, [rdi+20h]
0x1800221c4  lea     r9, [rdi+18h]; unsigned int *
0x1800221c8  mov     [rsp+78h+var_58], rax; struct _DEV_QUERY_PARAMETER **
0x1800221cd  mov     r8, [rsi+68h]; struct _DEV_QUERY_PARAMETER *
0x1800221d1  mov     rcx, r15; unsigned __int16 *
0x1800221d4  call    ?SanitizeExtendedParamters@@YAJPEBGKPEBU_DEV_QUERY_PARAMETER@@PEAKPEAPEAU1@@Z; SanitizeExtendedParamters(ushort const *,ulong,_DEV_QUERY_PARAMETER const *,ulong *,_DEV_QUERY_PARAMETER * *)
0x1800221d9  mov     ebx, eax
0x1800221db  test    eax, eax
0x1800221dd  js      short loc_180022202
0x1800221df  mov     [rdi+88h], rsi
0x1800221e6  mov     [rdi+10h], r15
0x1800221ea  mov     [rdi+198h], r13
0x1800221f1  mov     [r14], rdi
0x1800221f4  jmp     short loc_18002220F
0x1800221f6  mov     ebx, dword ptr [rsp+78h+arg_30]
0x1800221fd  mov     rdi, [rsp+78h+var_48]
0x180022202  test    rdi, rdi
0x180022205  jz      short loc_18002220F
0x180022207  mov     rcx, rdi; this
0x18002220a  call    ??_GCQueryContext@@IEAAPEAXI@Z; CQueryContext::`scalar deleting destructor'(uint)
0x18002220f  mov     eax, ebx
0x180022211  add     rsp, 40h
0x180022215  pop     r15
0x180022217  pop     r14
0x180022219  pop     r13
0x18002221b  pop     r12
0x18002221d  pop     rdi
0x18002221e  pop     rsi
0x18002221f  pop     rbx
0x180022220  retn
```
