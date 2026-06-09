# EapHost::HostPeerApis::EapHostPeerGetIdentity(ulong,ulong,_EAP_METHOD_TYPE,ulong,uchar const *,ulong,uchar const *,ulong,__int64,int *,ulong *,uchar * *,wchar_t * *,_EAP_ERROR * *,uchar * *)

- ea: `0x180006310`
- end: `0x1800067e2`
- name: `?EapHostPeerGetIdentity@HostPeerApis@EapHost@@UEAAJKKU_EAP_METHOD_TYPE@@KPEBEK1K_JPEAHPEAKPEAPEAEPEAPEA_WPEAPEAU_EAP_ERROR@@5@Z`
- size: `1234`
- prototype: `int(EapHost::HostPeerApis *__hidden this, unsigned int, unsigned int, struct _EAP_METHOD_TYPE *__struct_ptr, unsigned int, const unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, __int64, int *, unsigned int *, unsigned __int8 **, wchar_t **, struct _EAP_ERROR **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1800049d8`
- `0x180004e7c`
- `0x180005728`
- `0x180006310`
- `0x1800072cc`
- `0x180009dc4`
- `0x180009dec`
- `0x180009e2c`
- `0x180009fd0`
- `0x180010e54`
- `0x1800112d4`
- `0x18002ed84`
- `0x18002f1f4`
- `0x18002f93c`
- `0x180033d54`
- `0x180033d78`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800065c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006627`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800065c5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006627`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000676b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180006750`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000676b`

## string_xrefs

- `0x180006635`: `ComCopy`

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
0x180006310  push    rbx
0x180006312  push    rsi
0x180006313  push    rdi
0x180006314  push    r12
0x180006316  push    r13
0x180006318  push    r14
0x18000631a  push    r15
0x18000631c  sub     rsp, 110h
0x180006323  mov     rsi, r9
0x180006326  mov     r12d, r8d
0x180006329  xor     ebx, ebx
0x18000632b  mov     [rsp+148h+var_F4], ebx
0x18000632f  lea     r15, WPP_GLOBAL_Control
0x180006336  mov     rcx, cs:WPP_GLOBAL_Control
0x18000633d  cmp     rcx, r15
0x180006340  jz      short loc_180006391
0x180006342  test    byte ptr [rcx+1Ch], 4
0x180006346  jz      short loc_180006391
0x180006348  movzx   edx, byte ptr [r9]
0x18000634c  mov     eax, [rsp+148h+arg_30]
0x180006353  mov     [rsp+148h+var_100], eax
0x180006357  mov     eax, [rsp+148h+arg_20]
0x18000635e  mov     [rsp+148h+var_108], eax
0x180006362  mov     dword ptr [rsp+148h+var_110], edx
0x180006366  mov     eax, [r9+8]
0x18000636a  mov     dword ptr [rsp+148h+var_118], eax
0x18000636e  mov     eax, [r9+4]
0x180006372  mov     dword ptr [rsp+148h+var_120], eax
0x180006376  mov     eax, [r9+0Ch]
0x18000637a  mov     dword ptr [rsp+148h+var_128], eax
0x18000637e  mov     r9d, r8d
0x180006381  mov     rcx, [rcx+10h]
0x180006385  call    WPP_SF_Ddddddd
0x18000638a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006391  mov     rdi, [rsp+148h+arg_68]
0x180006399  test    rdi, rdi
0x18000639c  jz      loc_1800067AA
0x1800063a2  mov     rax, [rsp+148h+arg_58]
0x1800063aa  test    rax, rax
0x1800063ad  jz      loc_1800067AA
0x1800063b3  mov     r14, [rsp+148h+arg_60]
0x1800063bb  test    r14, r14
0x1800063be  jz      loc_1800067AA
0x1800063c4  mov     r8, [rsp+148h+arg_50]
0x1800063cc  test    r8, r8
0x1800063cf  jz      loc_1800067AA
0x1800063d5  mov     rdx, [rsp+148h+arg_78]
0x1800063dd  test    rdx, rdx
0x1800063e0  jz      loc_1800067AA
0x1800063e6  mov     [r8], ebx
0x1800063e9  mov     [rax], ebx
0x1800063eb  mov     [r14], rbx
0x1800063ee  mov     [rdi], rbx
0x1800063f1  mov     [rdx], rbx
0x1800063f4  lea     rcx, [rsp+148h+var_E0]
0x1800063f9  call    ?CreateInstance@EapLibraryManagerRuntime@Peer@EapLm@@SA?AV?$unique_ptr@VEapLibraryManagerRuntime@Peer@EapLm@@U?$default_delete@VEapLibraryManagerRuntime@Peer@EapLm@@@std@@@std@@W4EapLibraryLocationType@EapLibraryLocationValue@3@@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateInstance(EapLm::EapLibraryLocationValue::EapLibraryLocationType)
0x1800063fe  nop
0x1800063ff  mov     rdx, rsi; struct _EAP_TYPE *
0x180006402  lea     rcx, [rsp+148h+var_90]; this
0x18000640a  call    ??0EapType@EapHost@@QEAA@AEBU_EAP_TYPE@@@Z; EapHost::EapType::EapType(_EAP_TYPE const &)
0x18000640f  lea     rcx, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x180006416  mov     [rsp+148h+var_90], rcx
0x18000641e  mov     eax, [rsi+0Ch]
0x180006421  mov     [rsp+148h+var_78], eax
0x180006428  lea     r8, [rsp+148h+var_90]
0x180006430  lea     rdx, [rsp+148h+var_E8]
0x180006435  mov     rcx, [rsp+148h+var_E0]; this
0x18000643a  call    ?GetEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodRuntime@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerRuntime::GetEapMethodRuntime(EapHost::EapMethodType const &)
0x18000643f  nop
0x180006440  mov     rax, [rsp+148h+arg_38]
0x180006448  mov     [rsp+148h+var_B0], rax
0x180006450  mov     eax, [rsp+148h+arg_30]
0x180006457  mov     [rsp+148h+var_A8], rax
0x18000645f  mov     rax, [rsp+148h+arg_28]
0x180006467  mov     [rsp+148h+var_A0], rax
0x18000646f  mov     eax, [rsp+148h+arg_20]
0x180006476  mov     [rsp+148h+var_98], rax
0x18000647e  mov     [rsp+148h+var_C0], rbx
0x180006486  mov     [rsp+148h+cb], rbx
0x18000648e  mov     [rsp+148h+var_F8], bl
0x180006492  mov     [rsp+148h+var_F0], rbx
0x180006497  lea     r13, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18000649e  mov     [rsp+148h+var_D0], r13
0x1800064a3  mov     [rsp+148h+var_C8], rbx
0x1800064ab  lea     r8, [rsp+148h+var_D0]; this
0x1800064b0  mov     rdx, [rsp+148h+hSourceHandle]; hSourceHandle
0x1800064b8  mov     ecx, [rsp+148h+dwProcessId]; dwProcessId
0x1800064bf  call    ?DupImpersonationHandle@@YAJK_JAEAVObjectHandle@@@Z; DupImpersonationHandle(ulong,__int64,ObjectHandle &)
0x1800064c4  mov     esi, eax
0x1800064c6  mov     [rsp+148h+var_F4], eax
0x1800064ca  test    eax, eax
0x1800064cc  jz      loc_180006559
0x1800064d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064d9  cmp     rcx, r15
0x1800064dc  jz      short loc_1800064FD
0x1800064de  test    byte ptr [rcx+1Ch], 4
0x1800064e2  jz      short loc_1800064FD
0x1800064e4  mov     edx, 33h ; '3'
0x1800064e9  mov     r9d, eax
0x1800064ec  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800064f3  mov     rcx, [rcx+10h]
0x1800064f7  call    WPP_SF_d
0x1800064fc  nop
0x1800064fd  mov     [rsp+148h+var_D0], r13
0x180006502  lea     rcx, [rsp+148h+var_D0]; this
0x180006507  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x18000650c  nop
0x18000650d  mov     rcx, [rsp+148h+var_F0]; void *
0x180006512  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006517  mov     [rsp+148h+var_F0], rbx
0x18000651c  mov     rcx, [rsp+148h+var_C0]; void *
0x180006524  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180006529  nop
0x18000652a  mov     rcx, [rsp+148h+var_E8]; this
0x18000652f  test    rcx, rcx
0x180006532  jz      short loc_18000653A
0x180006534  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x180006539  nop
0x18000653a  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x180006541  mov     [rsp+148h+var_90], rax
0x180006549  lea     rcx, [rsp+148h+var_E0]
0x18000654e  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180006553  nop
0x180006554  jmp     loc_180006744
0x180006559  mov     rcx, [rsp+148h+var_E8]
0x18000655e  mov     rax, [rcx]
0x180006561  lea     rdx, [rsp+148h+var_F8]
0x180006566  mov     [rsp+148h+var_110], rdx
0x18000656b  lea     rdx, [rsp+148h+var_F0]
0x180006570  mov     [rsp+148h+var_118], rdx
0x180006575  lea     rdx, [rsp+148h+var_C0]
0x18000657d  mov     [rsp+148h+var_120], rdx
0x180006582  lea     rdx, [rsp+148h+var_B0]
0x18000658a  mov     [rsp+148h+var_128], rdx
0x18000658f  lea     r9, [rsp+148h+var_A0]
0x180006597  lea     r8, [rsp+148h+var_D0]
0x18000659c  mov     edx, r12d
0x18000659f  mov     rax, [rax+20h]
0x1800065a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065a8  mov     r12, [rsp+148h+cb]
0x1800065b0  test    r12, r12
0x1800065b3  jz      short loc_1800065F7
0x1800065b5  mov     rax, [rsp+148h+var_C0]
0x1800065bd  mov     [rsp+148h+Src], rax
0x1800065c2  mov     rcx, r12; cb
0x1800065c5  call    cs:__imp_CoTaskMemAlloc
0x1800065cb  mov     r13, rax
0x1800065ce  test    rax, rax
0x1800065d1  jz      short loc_180006641
0x1800065d3  mov     r8, r12; Size
0x1800065d6  mov     rdx, [rsp+148h+Src]; Src
0x1800065db  mov     rcx, rax; void *
0x1800065de  call    memcpy_0
0x1800065e3  mov     [r14], r13
0x1800065e6  mov     rcx, [rsp+148h+arg_58]
0x1800065ee  mov     eax, dword ptr [rsp+148h+cb]
0x1800065f5  mov     [rcx], eax
0x1800065f7  lea     r12, ?empty@?1??EmptyString@?$BasicSimpleString@_W@@CAPEB_WXZ@4QB_WB; wchar_t const near * const `BasicSimpleString<wchar_t>::EmptyString(void)'::`2'::empty
0x1800065fe  cmp     [rsp+148h+var_F0], rbx
0x180006603  cmovnz  r12, [rsp+148h+var_F0]
0x180006609  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000660d  inc     rax
0x180006610  cmp     [r12+rax*2], bx
0x180006615  jnz     short loc_18000660D
0x180006617  lea     rax, ds:2[rax*2]
0x18000661f  mov     [rsp+148h+Src], rax
0x180006624  mov     rcx, rax; cb
0x180006627  call    cs:__imp_CoTaskMemAlloc
0x18000662d  mov     r13, rax
0x180006630  test    rax, rax
0x180006633  jnz     short loc_18000667E
0x180006635  lea     rcx, aComcopy; "ComCopy"
0x18000663c  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x180006641  xorps   xmm0, xmm0
0x180006644  movups  [rsp+148h+var_68], xmm0
0x18000664c  lea     rax, aBadAllocation; "bad allocation"
0x180006653  mov     qword ptr [rsp+148h+var_68], rax
0x18000665b  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180006662  mov     [rsp+148h+pExceptionObject], rax
0x18000666a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180006671  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180006679  call    _CxxThrowException_0
0x18000667e  mov     r8, [rsp+148h+Src]; Size
0x180006683  mov     rdx, r12; Src
0x180006686  mov     rcx, r13; void *
0x180006689  call    memcpy_0
0x18000668e  mov     [rdi], r13
0x180006691  mov     eax, ebx
0x180006693  cmp     [rsp+148h+var_F8], bl
0x180006697  setnz   al
0x18000669a  mov     rcx, [rsp+148h+arg_50]
0x1800066a2  mov     [rcx], eax
0x1800066a4  lea     rax, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x1800066ab  mov     [rsp+148h+var_D0], rax
0x1800066b0  lea     rcx, [rsp+148h+var_D0]; this
0x1800066b5  call    ?Clear@ObjectHandle@@QEAAXXZ; ObjectHandle::Clear(void)
0x1800066ba  nop
0x1800066bb  mov     rcx, [rsp+148h+var_F0]; void *
0x1800066c0  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800066c5  mov     [rsp+148h+var_F0], rbx
0x1800066ca  mov     rcx, [rsp+148h+var_C0]; void *
0x1800066d2  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x1800066d7  nop
0x1800066d8  mov     rcx, [rsp+148h+var_E8]; this
0x1800066dd  test    rcx, rcx
0x1800066e0  jz      short loc_1800066E8
0x1800066e2  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x1800066e7  nop
0x1800066e8  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x1800066ef  mov     [rsp+148h+var_90], rax
0x1800066f7  lea     rcx, [rsp+148h+var_E0]
0x1800066fc  call    ??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ; std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(void)
0x180006701  nop
0x180006702  jmp     short loc_180006744
0x180006704  xor     ebx, ebx
0x180006706  lea     r15, WPP_GLOBAL_Control
0x18000670d  mov     rdi, [rsp+148h+arg_68]
0x180006715  mov     r14, [rsp+148h+arg_60]
0x18000671d  mov     esi, [rsp+148h+var_F4]
0x180006721  jmp     short loc_180006748
0x180006723  jmp     short loc_180006727
0x180006725  jmp     short $+2
0x180006727  xor     ebx, ebx
0x180006729  lea     r15, WPP_GLOBAL_Control
0x180006730  mov     rdi, [rsp+148h+arg_68]
0x180006738  mov     r14, [rsp+148h+arg_60]
0x180006740  mov     esi, [rsp+148h+var_F4]
0x180006744  test    esi, esi
0x180006746  jz      short loc_180006774
0x180006748  cmp     [r14], rbx
0x18000674b  jz      short loc_180006763
0x18000674d  mov     rcx, [r14]; pv
0x180006750  call    cs:__imp_CoTaskMemFree
0x180006756  mov     [r14], rbx
0x180006759  mov     rax, [rsp+148h+arg_58]
0x180006761  mov     [rax], ebx
0x180006763  cmp     [rdi], rbx
0x180006766  jz      short loc_180006774
0x180006768  mov     rcx, [rdi]; pv
0x18000676b  call    cs:__imp_CoTaskMemFree
0x180006771  mov     [rdi], rbx
0x180006774  mov     rcx, cs:WPP_GLOBAL_Control
0x18000677b  cmp     rcx, r15
0x18000677e  jz      short loc_1800067A6
0x180006780  test    byte ptr [rcx+1Ch], 4
0x180006784  jz      short loc_1800067A6
0x180006786  mov     edx, 34h ; '4'
0x18000678b  mov     r9, [rdi]
0x18000678e  mov     [rsp+148h+var_128], r9
0x180006793  mov     r9d, esi
0x180006796  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x18000679d  mov     rcx, [rcx+10h]
0x1800067a1  call    WPP_SF_dS
0x1800067a6  mov     eax, esi
0x1800067a8  jmp     short loc_1800067CF
0x1800067aa  cmp     rcx, r15
0x1800067ad  jz      short loc_1800067CA
0x1800067af  test    byte ptr [rcx+1Ch], 1
0x1800067b3  jz      short loc_1800067CA
0x1800067b5  mov     edx, 32h ; '2'
0x1800067ba  lea     r8, WPP_19fe9e40ce2639fd1fea5b1994aee223_Traceguids
0x1800067c1  mov     rcx, [rcx+10h]
0x1800067c5  call    WPP_SF_
0x1800067ca  mov     eax, 57h ; 'W'
0x1800067cf  add     rsp, 110h
0x1800067d6  pop     r15
0x1800067d8  pop     r14
0x1800067da  pop     r13
0x1800067dc  pop     r12
0x1800067de  pop     rdi
0x1800067df  pop     rsi
0x1800067e0  pop     rbx
0x1800067e1  retn
```
