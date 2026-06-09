# EapHost::HostPeerApis::EapHostPeerGetIdentity(ulong,ulong,_EAP_METHOD_TYPE,ulong,uchar const *,ulong,uchar const *,ulong,__int64,int *,ulong *,uchar * *,wchar_t * *,_EAP_ERROR * *,uchar * *)

- ea: `0x180006580`
- end: `0x180006a6b`
- name: `?EapHostPeerGetIdentity@HostPeerApis@EapHost@@UEAAJKKU_EAP_METHOD_TYPE@@KPEBEK1K_JPEAHPEAKPEAPEAEPEAPEA_WPEAPEAU_EAP_ERROR@@5@Z`
- size: `1259`
- prototype: `int(EapHost::HostPeerApis *__hidden this, unsigned int, unsigned int, struct _EAP_METHOD_TYPE *__struct_ptr, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, __int64, int *, unsigned int *, unsigned __int8 **, wchar_t **, struct _EAP_ERROR **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180004b4c`
- `0x180004fb8`
- `0x180005940`
- `0x180006580`
- `0x180007564`
- `0x18000a21c`
- `0x18000a24c`
- `0x18000a290`
- `0x18000a44c`
- `0x180011504`
- `0x180011a04`
- `0x18002fe84`
- `0x18003032c`
- `0x180030b08`
- `0x180035114`
- `0x180035138`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000689d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000689d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800069ed`

## string_xrefs

- `0x1800068b1`: `ComCopy`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall EapHost::HostPeerApis::EapHostPeerGetIdentity(
        EapHost::HostPeerApis *this,
        __int64 a2,
        __int64 a3,
        struct _EAP_METHOD_TYPE *a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        unsigned int a7,
        const unsigned __int8 *a8,
        DWORD dwProcessId,
        HANDLE hSourceHandle,
        int *a11,
        unsigned int *a12,
        unsigned __int8 **a13,
        wchar_t **a14,
        struct _EAP_ERROR **a15,
        unsigned __int8 **a16)
{
  unsigned int v17; // r12d
  EapHost::Peer::Host *v18; // rcx
  LPVOID *v19; // rdi
  LPVOID *v20; // r14
  unsigned int v21; // eax
  unsigned int v22; // esi
  int *v23; // r9
  size_t v24; // r12
  unsigned __int8 *v25; // rax
  unsigned __int8 *v26; // r13
  __int64 *v27; // r12
  __int64 v28; // rax
  wchar_t *v29; // rax
  wchar_t *v30; // r13
  _BYTE v32[4]; // [rsp+50h] [rbp-F8h] BYREF
  int v33; // [rsp+54h] [rbp-F4h] BYREF
  void *v34; // [rsp+58h] [rbp-F0h] BYREF
  ReferenceCounted *v35; // [rsp+60h] [rbp-E8h]
  EapLm::BaseEapLibraryManager *v36; // [rsp+68h] [rbp-E0h] BYREF
  void *Src; // [rsp+70h] [rbp-D8h]
  _QWORD v38[2]; // [rsp+78h] [rbp-D0h] BYREF
  void *v39; // [rsp+88h] [rbp-C0h] BYREF
  SIZE_T cb; // [rsp+90h] [rbp-B8h]
  _QWORD v41[2]; // [rsp+98h] [rbp-B0h] BYREF
  _QWORD v42[2]; // [rsp+A8h] [rbp-A0h] BYREF
  void **v43; // [rsp+B8h] [rbp-90h] BYREF
  DWORD dwAuthorId; // [rsp+D0h] [rbp-78h]
  _QWORD pExceptionObject[3]; // [rsp+D8h] [rbp-70h] BYREF
  const ATL::CAtlException *v46; // [rsp+F0h] [rbp-58h] BYREF
  const EapHost::EapException *v47; // [rsp+F8h] [rbp-50h] BYREF
  const Exception *v48; // [rsp+100h] [rbp-48h] BYREF

  v17 = a3;
  v33 = 0;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Ddddddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a4->eapType.type,
      a3,
      (unsigned int)a3,
      a4->dwAuthorId,
      a4->eapType.dwVendorId,
      a4->eapType.dwVendorType,
      a4->eapType.type,
      a5,
      a7);
    v18 = WPP_GLOBAL_Control;
  }
  v19 = (LPVOID *)a14;
  if ( a14 && a12 && (v20 = (LPVOID *)a13) != 0 && a11 && a16 )
  {
    try
    {
      *a11 = 0;
      *a12 = 0;
      *a13 = 0;
      *a14 = 0;
      *a16 = 0;
      EapLm::Peer::EapLibraryManagerRuntime::CreateInstance(&v36);
      EapHost::EapType::EapType((EapHost::EapType *)&v43, &a4->eapType);
      v43 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a4->dwAuthorId;
      EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(v36);
      v41[0] = a8;
      v41[1] = a7;
      v42[0] = a6;
      v42[1] = a5;
      v39 = 0;
      cb = 0;
      v32[0] = 0;
      v34 = 0;
      v38[0] = &ObjectHandle::`vftable';
      v38[1] = 0;
      v21 = DupImpersonationHandle(dwProcessId, hSourceHandle, (struct ObjectHandle *)v38);
      v22 = v21;
      v33 = v21;
      if ( v21 )
      {
        if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids, v21);
        }
        v38[0] = &ObjectHandle::`vftable';
        ObjectHandle::Clear((ObjectHandle *)v38);
        HeapAllocator::Free(v34);
        v34 = 0;
        HeapAllocator::Free(v39);
        if ( v35 )
          ReferenceCounted::Release(v35);
        v43 = &EapHost::EapType::`vftable';
        std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v36);
      }
      else
      {
        (*(void (__fastcall **)(ReferenceCounted *, _QWORD, _QWORD *, _QWORD *, _QWORD *, void **, void **, _BYTE *))(*(_QWORD *)v35 + 32LL))(
          v35,
          v17,
          v38,
          v42,
          v41,
          &v39,
          &v34,
          v32);
        v24 = cb;
        if ( cb )
        {
          Src = v39;
          v25 = (unsigned __int8 *)CoTaskMemAlloc(cb);
          v26 = v25;
          if ( !v25 )
          {
            pExceptionObject[2] = 0;
            pExceptionObject[1] = "bad allocation";
            pExceptionObject[0] = &std::bad_alloc::`vftable';
            throw (std::bad_alloc *)pExceptionObject;
          }
          memcpy_0(v25, Src, v24);
          *a13 = v26;
          *a12 = cb;
        }
        v27 = &`BasicSimpleString<wchar_t>::EmptyString'::`2'::empty;
        if ( v34 )
          v27 = (__int64 *)v34;
        v28 = -1;
        do
          ++v28;
        while ( *((_WORD *)v27 + v28) );
        Src = (void *)(2 * v28 + 2);
        v29 = (wchar_t *)CoTaskMemAlloc((SIZE_T)Src);
        v30 = v29;
        if ( !v29 )
          LowMemoryError::Throw(L"ComCopy");
        memcpy_0(v29, v27, (size_t)Src);
        *a14 = v30;
        *a11 = v32[0] != 0;
        v38[0] = &ObjectHandle::`vftable';
        ObjectHandle::Clear((ObjectHandle *)v38);
        HeapAllocator::Free(v34);
        v34 = 0;
        HeapAllocator::Free(v39);
        if ( v35 )
          ReferenceCounted::Release(v35);
        v43 = &EapHost::EapType::`vftable';
        std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(&v36);
      }
    }
    catch ( std::bad_alloc )
    {
      v33 = -2147024882;
      if ( a15 )
        *a15 = 0;
      v19 = (LPVOID *)a14;
      v20 = (LPVOID *)a13;
      v22 = v33;
      goto LABEL_31;
    }
    catch ( const ATL::CAtlException *v46 )
    {
      v33 = *(_DWORD *)v46;
      if ( a15 )
        *a15 = 0;
      v19 = (LPVOID *)a14;
      v20 = (LPVOID *)a13;
      v22 = v33;
    }
    catch ( const EapHost::EapException *v47 )
    {
      EapHost::EapException2EapErrorOle(v47, (const struct EapHost::EapException *)a15, (struct _EAP_ERROR **)&v33, v23);
      v19 = (LPVOID *)a14;
      v20 = (LPVOID *)a13;
      v22 = v33;
    }
    catch ( const Exception *v48 )
    {
      EapHost::Exception2EapErrorOle(v48, (const struct Exception *)a15, (struct _EAP_ERROR **)&v33, v23);
      v19 = (LPVOID *)a14;
      v20 = (LPVOID *)a13;
      v22 = v33;
    }
    if ( v22 )
    {
LABEL_31:
      if ( *v20 )
      {
        CoTaskMemFree(*v20);
        *v20 = 0;
        *a12 = 0;
      }
      if ( *v19 )
      {
        CoTaskMemFree(*v19);
        *v19 = 0;
      }
    }
    if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        52,
        (unsigned int)WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids,
        v22,
        (__int64)*v19);
    }
    return v22;
  }
  else
  {
    if ( v18 != (EapHost::Peer::Host *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)v18 + 2), 50, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids);
    return 87;
  }
}

```

## disassembly

```asm
0x180006580  push    rbx
0x180006582  push    rsi
0x180006583  push    rdi
0x180006584  push    r12
0x180006586  push    r13
0x180006588  push    r14
0x18000658a  push    r15
0x18000658c  sub     rsp, 110h
0x180006593  mov     rsi, r9
0x180006596  mov     r12d, r8d
0x180006599  xor     ebx, ebx
0x18000659b  mov     [rsp+148h+var_F4], ebx
0x18000659f  lea     r15, WPP_GLOBAL_Control
0x1800065a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800065ad  cmp     rcx, r15
0x1800065b0  jz      short loc_180006601
0x1800065b2  test    byte ptr [rcx+1Ch], 4
0x1800065b6  jz      short loc_180006601
0x1800065b8  movzx   edx, byte ptr [r9]
0x1800065bc  mov     eax, [rsp+148h+arg_30]
0x1800065c3  mov     [rsp+148h+var_100], eax
0x1800065c7  mov     eax, [rsp+148h+arg_20]
0x1800065ce  mov     [rsp+148h+var_108], eax
0x1800065d2  mov     dword ptr [rsp+148h+var_110], edx
0x1800065d6  mov     eax, [r9+8]
0x1800065da  mov     dword ptr [rsp+148h+var_118], eax
0x1800065de  mov     eax, [r9+4]
0x1800065e2  mov     dword ptr [rsp+148h+var_120], eax
0x1800065e6  mov     eax, [r9+0Ch]
0x1800065ea  mov     dword ptr [rsp+148h+var_128], eax
0x1800065ee  mov     r9d, r8d
0x1800065f1  mov     rcx, [rcx+10h]
0x1800065f5  call    WPP_SF_Ddddddd
0x1800065fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006601  mov     rdi, [rsp+148h+arg_68]
0x180006609  test    rdi, rdi
0x18000660c  jz      loc_180006A32
0x180006612  mov     rax, [rsp+148h+arg_58]
0x18000661a  test    rax, rax
0x18000661d  jz      loc_180006A32
0x180006623  mov     r14, [rsp+148h+arg_60]
0x18000662b  test    r14, r14
0x18000662e  jz      loc_180006A32
0x180006634  mov     r8, [rsp+148h+arg_50]
0x18000663c  test    r8, r8
0x18000663f  jz      loc_180006A32
0x180006645  mov     rdx, [rsp+148h+arg_78]
0x18000664d  test    rdx, rdx
0x180006650  jz      loc_180006A32
0x180006656  mov     [r8], ebx
0x180006659  mov     [rax], ebx
0x18000665b  mov     [r14], rbx
0x18000665e  mov     [rdi], rbx
0x180006661  mov     [rdx], rbx
0x180006664  lea     rcx, [rsp+148h+var_E0]
0x180006669  call    ?CreateInstance@EapLibraryManagerRuntime@Peer@EapLm@@SA?AV?$unique_ptr@VEapLibraryManagerRuntime@Peer@EapLm@@U?$default_delete@VEapLibraryManagerRuntime@Peer@EapLm@@@std@@@std@@W4EapLibraryLocationType@EapLibraryLocationValue@3@@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateInstance(EapLm::EapLibraryLocationValue::EapLibraryLocationType)
0x18000666e  nop
0x18000666f  mov     rdx, rsi; struct _EAP_TYPE *
0x180006672  lea     rcx, [rsp+148h+var_90]; this
0x18000667a  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x18000667f  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180006686  mov     [rsp+148h+var_90], rcx
0x18000668e  mov     eax, [rsi+0Ch]
0x180006691  mov     [rsp+148h+var_78], eax
0x180006698  lea     r8, [rsp+148h+var_90]
0x1800066a0  lea     rdx, [rsp+148h+var_E8]
0x1800066a5  mov     rcx, [rsp+148h+var_E0]; this
0x1800066aa  call    ?GetEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(EapHost::EapMethodType const &)
0x1800066af  nop
0x1800066b0  mov     rax, [rsp+148h+arg_38]
0x1800066b8  mov     [rsp+148h+var_B0], rax
0x1800066c0  mov     eax, [rsp+148h+arg_30]
0x1800066c7  mov     [rsp+148h+var_A8], rax
0x1800066cf  mov     rax, [rsp+148h+arg_28]
0x1800066d7  mov     [rsp+148h+var_A0], rax
0x1800066df  mov     eax, [rsp+148h+arg_20]
0x1800066e6  mov     [rsp+148h+var_98], rax
0x1800066ee  mov     [rsp+148h+var_C0], rbx
0x1800066f6  mov     [rsp+148h+cb], rbx
0x1800066fe  mov     [rsp+148h+var_F8], bl
0x180006702  mov     [rsp+148h+var_F0], rbx
0x180006707  lea     r13, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18000670e  mov     [rsp+148h+var_D0], r13
0x180006713  mov     [rsp+148h+var_C8], rbx
0x18000671b  lea     r8, [rsp+148h+var_D0]; this
0x180006720  mov     rdx, [rsp+148h+hSourceHandle]; hSourceHandle
0x180006728  mov     ecx, [rsp+148h+dwProcessId]; dwProcessId
0x18000672f  call    ?DupImpersonationHandle@@YAJK_JAEAVObjectHandle@@@Z; DupImpersonationHandle(ulong,__int64,ObjectHandle &)
0x180006734  mov     esi, eax
0x180006736  mov     [rsp+148h+var_F4], eax
0x18000673a  test    eax, eax
0x18000673c  jz      loc_1800067C9
0x180006742  mov     rcx, cs:WPP_GLOBAL_Control
0x180006749  cmp     rcx, r15
0x18000674c  jz      short loc_18000676D
0x18000674e  test    byte ptr [rcx+1Ch], 4
0x180006752  jz      short loc_18000676D
0x180006754  mov     edx, 33h ; '3'
0x180006759  mov     r9d, eax
0x18000675c  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006763  mov     rcx, [rcx+10h]
0x180006767  call    WPP_SF_d
0x18000676c  nop
0x18000676d  mov     [rsp+148h+var_D0], r13
0x180006772  lea     rcx, [rsp+148h+var_D0]; this
0x180006777  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000677c  nop
0x18000677d  mov     rcx, [rsp+148h+var_F0]; void *
0x180006782  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006787  mov     [rsp+148h+var_F0], rbx
0x18000678c  mov     rcx, [rsp+148h+var_C0]; void *
0x180006794  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006799  nop
0x18000679a  mov     rcx, [rsp+148h+var_E8]; this
0x18000679f  test    rcx, rcx
0x1800067a2  jz      short loc_1800067AA
0x1800067a4  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800067a9  nop
0x1800067aa  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x1800067b1  mov     [rsp+148h+var_90], rax
0x1800067b9  lea     rcx, [rsp+148h+var_E0]
0x1800067be  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x1800067c3  nop
0x1800067c4  jmp     loc_1800069C0
0x1800067c9  mov     rcx, [rsp+148h+var_E8]
0x1800067ce  mov     rax, [rcx]
0x1800067d1  lea     rdx, [rsp+148h+var_F8]
0x1800067d6  mov     [rsp+148h+var_110], rdx
0x1800067db  lea     rdx, [rsp+148h+var_F0]
0x1800067e0  mov     [rsp+148h+var_118], rdx
0x1800067e5  lea     rdx, [rsp+148h+var_C0]
0x1800067ed  mov     [rsp+148h+var_120], rdx
0x1800067f2  lea     rdx, [rsp+148h+var_B0]
0x1800067fa  mov     [rsp+148h+var_128], rdx
0x1800067ff  lea     r9, [rsp+148h+var_A0]
0x180006807  lea     r8, [rsp+148h+var_D0]
0x18000680c  mov     edx, r12d
0x18000680f  mov     rax, [rax+20h]
0x180006813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006818  mov     r12, [rsp+148h+cb]
0x180006820  test    r12, r12
0x180006823  jz      short loc_18000686D
0x180006825  mov     rax, [rsp+148h+var_C0]
0x18000682d  mov     [rsp+148h+Src], rax
0x180006832  mov     rcx, r12; cb
0x180006835  call    cs:__imp_CoTaskMemAlloc
0x18000683c  nop     dword ptr [rax+rax+00h]
0x180006841  mov     r13, rax
0x180006844  test    rax, rax
0x180006847  jz      short loc_1800068BD
0x180006849  mov     r8, r12; Size
0x18000684c  mov     rdx, [rsp+148h+Src]; Src
0x180006851  mov     rcx, rax; void *
0x180006854  call    memcpy_0
0x180006859  mov     [r14], r13
0x18000685c  mov     rcx, [rsp+148h+arg_58]
0x180006864  mov     eax, dword ptr [rsp+148h+cb]
0x18000686b  mov     [rcx], eax
0x18000686d  lea     r12, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x180006874  cmp     [rsp+148h+var_F0], rbx
0x180006879  cmovnz  r12, [rsp+148h+var_F0]
0x18000687f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006883  inc     rax
0x180006886  cmp     [r12+rax*2], bx
0x18000688b  jnz     short loc_180006883
0x18000688d  lea     rax, ds:2[rax*2]
0x180006895  mov     [rsp+148h+Src], rax
0x18000689a  mov     rcx, rax; cb
0x18000689d  call    cs:__imp_CoTaskMemAlloc
0x1800068a4  nop     dword ptr [rax+rax+00h]
0x1800068a9  mov     r13, rax
0x1800068ac  test    rax, rax
0x1800068af  jnz     short loc_1800068FA
0x1800068b1  lea     rcx, aComcopy; "ComCopy"
0x1800068b8  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x1800068bd  xorps   xmm0, xmm0
0x1800068c0  movups  [rsp+148h+var_68], xmm0
0x1800068c8  lea     rax, aBadAllocation; "bad allocation"
0x1800068cf  mov     qword ptr [rsp+148h+var_68], rax
0x1800068d7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800068de  mov     [rsp+148h+pExceptionObject], rax
0x1800068e6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800068ed  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x1800068f5  call    _CxxThrowException_0
0x1800068fa  mov     r8, [rsp+148h+Src]; Size
0x1800068ff  mov     rdx, r12; Src
0x180006902  mov     rcx, r13; void *
0x180006905  call    memcpy_0
0x18000690a  mov     [rdi], r13
0x18000690d  mov     eax, ebx
0x18000690f  cmp     [rsp+148h+var_F8], bl
0x180006913  setnz   al
0x180006916  mov     rcx, [rsp+148h+arg_50]
0x18000691e  mov     [rcx], eax
0x180006920  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180006927  mov     [rsp+148h+var_D0], rax
0x18000692c  lea     rcx, [rsp+148h+var_D0]; this
0x180006931  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x180006936  nop
0x180006937  mov     rcx, [rsp+148h+var_F0]; void *
0x18000693c  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006941  mov     [rsp+148h+var_F0], rbx
0x180006946  mov     rcx, [rsp+148h+var_C0]; void *
0x18000694e  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006953  nop
0x180006954  mov     rcx, [rsp+148h+var_E8]; this
0x180006959  test    rcx, rcx
0x18000695c  jz      short loc_180006964
0x18000695e  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180006963  nop
0x180006964  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000696b  mov     [rsp+148h+var_90], rax
0x180006973  lea     rcx, [rsp+148h+var_E0]
0x180006978  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x18000697d  nop
0x18000697e  jmp     short loc_1800069C0
0x180006980  xor     ebx, ebx
0x180006982  lea     r15, WPP_GLOBAL_Control
0x180006989  mov     rdi, [rsp+148h+arg_68]
0x180006991  mov     r14, [rsp+148h+arg_60]
0x180006999  mov     esi, [rsp+148h+var_F4]
0x18000699d  jmp     short loc_1800069C4
0x18000699f  jmp     short loc_1800069A3
0x1800069a1  jmp     short $+2
0x1800069a3  xor     ebx, ebx
0x1800069a5  lea     r15, WPP_GLOBAL_Control
0x1800069ac  mov     rdi, [rsp+148h+arg_68]
0x1800069b4  mov     r14, [rsp+148h+arg_60]
0x1800069bc  mov     esi, [rsp+148h+var_F4]
0x1800069c0  test    esi, esi
0x1800069c2  jz      short loc_1800069FC
0x1800069c4  cmp     [r14], rbx
0x1800069c7  jz      short loc_1800069E5
0x1800069c9  mov     rcx, [r14]; pv
0x1800069cc  call    cs:__imp_CoTaskMemFree
0x1800069d3  nop     dword ptr [rax+rax+00h]
0x1800069d8  mov     [r14], rbx
0x1800069db  mov     rax, [rsp+148h+arg_58]
0x1800069e3  mov     [rax], ebx
0x1800069e5  cmp     [rdi], rbx
0x1800069e8  jz      short loc_1800069FC
0x1800069ea  mov     rcx, [rdi]; pv
0x1800069ed  call    cs:__imp_CoTaskMemFree
0x1800069f4  nop     dword ptr [rax+rax+00h]
0x1800069f9  mov     [rdi], rbx
0x1800069fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a03  cmp     rcx, r15
0x180006a06  jz      short loc_180006A2E
0x180006a08  test    byte ptr [rcx+1Ch], 4
0x180006a0c  jz      short loc_180006A2E
0x180006a0e  mov     edx, 34h ; '4'
0x180006a13  mov     r9, [rdi]
0x180006a16  mov     [rsp+148h+var_128], r9
0x180006a1b  mov     r9d, esi
0x180006a1e  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006a25  mov     rcx, [rcx+10h]
0x180006a29  call    WPP_SF_dS
0x180006a2e  mov     eax, esi
0x180006a30  jmp     short loc_180006A57
0x180006a32  cmp     rcx, r15
0x180006a35  jz      short loc_180006A52
0x180006a37  test    byte ptr [rcx+1Ch], 1
0x180006a3b  jz      short loc_180006A52
0x180006a3d  mov     edx, 32h ; '2'
0x180006a42  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x180006a49  mov     rcx, [rcx+10h]
0x180006a4d  call    WPP_SF_
0x180006a52  mov     eax, 57h ; 'W'
0x180006a57  add     rsp, 110h
0x180006a5e  pop     r15
0x180006a60  pop     r14
0x180006a62  pop     r13
0x180006a64  pop     r12
0x180006a66  pop     rdi
0x180006a67  pop     rsi
0x180006a68  pop     rbx
0x180006a69  retn
```
