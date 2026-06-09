# EapLm::Peer::ThirdPartyDispatcherConfig::QueryInteractiveUIInputFields(ulong,_EAP_METHOD_TYPE,ulong,ulong,uchar const *,_EAP_INTERACTIVE_UI_DATA *,_EAP_ERROR * *,uchar * *)

- ea: `0x18000e5e0`
- end: `0x18000e76d`
- name: `?QueryInteractiveUIInputFields@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJKU_EAP_METHOD_TYPE@@KKPEBEPEAU_EAP_INTERACTIVE_UI_DATA@@PEAPEAU_EAP_ERROR@@PEAPEAE@Z`
- size: `397`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, unsigned int, struct _EAP_METHOD_TYPE *, unsigned int, unsigned int, const unsigned __int8 *, struct _EAP_INTERACTIVE_UI_DATA *, struct _EAP_ERROR **, unsigned __int8 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000caec`
- `0x18000cd8c`
- `0x18000cf00`
- `0x18000e5e0`
- `0x180012a00`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## string_xrefs

- `0x18000e6f3`: `com_ref:Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::QueryInteractiveUIInputFields(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        unsigned int a2,
        struct _EAP_METHOD_TYPE *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        struct _EAP_INTERACTIVE_UI_DATA *a7,
        struct _EAP_ERROR **a8)
{
  struct _EAP_INTERACTIVE_UI_DATA *v10; // rbx
  int *v12; // r9
  __int128 v13; // xmm1
  EAP_UI_DATA_FORMAT v14; // xmm2_8
  struct _EAP_ERROR *v15; // [rsp+30h] [rbp-78h] BYREF
  _OWORD v16[2]; // [rsp+38h] [rbp-70h] BYREF
  __int128 v17; // [rsp+58h] [rbp-50h] BYREF
  __int64 v18; // [rsp+68h] [rbp-40h]
  _QWORD v19[2]; // [rsp+70h] [rbp-38h] BYREF
  const ATL::CAtlException *v20; // [rsp+80h] [rbp-28h] BYREF
  const EapHost::EapException *v21; // [rsp+88h] [rbp-20h] BYREF
  const Exception *v22; // [rsp+90h] [rbp-18h] BYREF
  const Exception *v23; // [rsp+98h] [rbp-10h] BYREF

  LODWORD(v15) = 0;
  v17 = 0;
  v18 = 0;
  v10 = a7;
  if ( a7 )
  {
    BYTE8(v16[0]) = a3->eapType.type;
    *(_QWORD *)((char *)v16 + 12) = *(_QWORD *)&a3->eapType.dwVendorId;
    if ( BYTE8(v16[0]) != 0xFE )
      *(_QWORD *)((char *)v16 + 12) = 0;
    try
    {
      *(_QWORD *)&v16[0] = &EapHost::EapMethodType::`vftable';
      DWORD2(v16[1]) = a3->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
        *((_QWORD **)this - 12),
        (ReferenceCounted *)&a7,
        (__int64)v16);
      *(_QWORD *)&v16[0] = &EapHost::EapType::`vftable';
      v19[1] = a5;
      v19[0] = a6;
      (*(void (__fastcall **)(struct _EAP_INTERACTIVE_UI_DATA *, _QWORD, _QWORD, _QWORD *, __int128 *))(*(_QWORD *)&a7->dwVersion + 72LL))(
        a7,
        a2,
        a4,
        v19,
        &v17);
      memset(v16, 0, sizeof(v16));
      BYTE8(v16[1]) = 1;
      if ( !Copy<TaskAllocator>((__int64)v16, (__int64)&v17) )
      {
        try
        {
          LowMemoryError::Throw(L"com_ref:Assign");
        }
        catch ( const Exception *v23 )
        {
          Free<TaskAllocator>((__int64)v16);
          throw;
        }
      }
    }
    catch ( std::bad_alloc )
    {
      LODWORD(v15) = -2147024882;
      if ( a8 )
        *a8 = 0;
      goto LABEL_9;
    }
    catch ( const ATL::CAtlException *v20 )
    {
      LODWORD(v15) = *(_DWORD *)v20;
      if ( a8 )
        *a8 = 0;
      goto LABEL_9;
    }
    catch ( const EapHost::EapException *v21 )
    {
      EapHost::EapException2EapErrorOle(v21, (const struct EapHost::EapException *)a8, &v15, v12);
      goto LABEL_9;
    }
    catch ( const Exception *v22 )
    {
      EapHost::Exception2EapErrorOle(v22, (const struct Exception *)a8, &v15, v12);
      goto LABEL_9;
    }
    v13 = v16[0];
    v14.credData = *(EAP_CRED_REQ **)&v16[1];
    memset(v16, 0, sizeof(v16));
    BYTE8(v16[1]) = 1;
    *(_OWORD *)&v10->dwVersion = v13;
    v10->pbUiData = v14;
    Free<TaskAllocator>((__int64)v16);
    if ( a7 )
      ReferenceCounted::Release((ReferenceCounted *)a7);
LABEL_9:
    Free<HeapAllocator>(&v17);
    return (unsigned int)v15;
  }
  else
  {
    Free<HeapAllocator>(&v17);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000e5e0  mov     r11, rsp
0x18000e5e3  mov     [r11+8], rbx
0x18000e5e7  mov     [r11+10h], rsi
0x18000e5eb  push    rdi
0x18000e5ec  sub     rsp, 0A0h
0x18000e5f3  mov     edi, r9d
0x18000e5f6  mov     esi, edx
0x18000e5f8  mov     r10, rcx
0x18000e5fb  mov     dword ptr [rsp+0A8h+var_78], 0
0x18000e603  xorps   xmm0, xmm0
0x18000e606  xor     eax, eax
0x18000e608  movups  [rsp+0A8h+var_50], xmm0
0x18000e60d  mov     [r11-40h], rax
0x18000e611  mov     rbx, [rsp+0A8h+arg_30]
0x18000e619  test    rbx, rbx
0x18000e61c  jnz     short loc_18000E631
0x18000e61e  lea     rcx, [r11-50h]
0x18000e622  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<HeapAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18000e627  mov     eax, 80004003h
0x18000e62c  jmp     loc_18000E758
0x18000e631  mov     cl, [r8]
0x18000e634  mov     byte ptr [rsp+0A8h+var_70+8], cl
0x18000e638  mov     eax, [r8+4]
0x18000e63c  mov     dword ptr [rsp+0A8h+var_70+0Ch], eax
0x18000e640  mov     eax, [r8+8]
0x18000e644  mov     dword ptr [rsp+0A8h+var_60], eax
0x18000e648  cmp     cl, 0FEh
0x18000e64b  jz      short loc_18000E656
0x18000e64d  mov     qword ptr [rsp+0A8h+var_70+0Ch], 0
0x18000e656  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000e65d  mov     qword ptr [rsp+0A8h+var_70], rax
0x18000e662  mov     eax, [r8+0Ch]
0x18000e666  mov     dword ptr [rsp+0A8h+var_60+8], eax
0x18000e66a  lea     r8, [rsp+0A8h+var_70]
0x18000e66f  lea     rdx, [rsp+0A8h+arg_30]
0x18000e677  mov     rcx, [r10-60h]
0x18000e67b  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000e680  nop
0x18000e681  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000e688  mov     qword ptr [rsp+0A8h+var_70], rax
0x18000e68d  mov     eax, [rsp+0A8h+arg_20]
0x18000e694  mov     [rsp+0A8h+var_30], rax
0x18000e699  mov     rax, [rsp+0A8h+arg_28]
0x18000e6a1  mov     [rsp+0A8h+var_38], rax
0x18000e6a6  mov     rcx, [rsp+0A8h+arg_30]
0x18000e6ae  mov     rax, [rcx]
0x18000e6b1  lea     rdx, [rsp+0A8h+var_50]
0x18000e6b6  mov     [rsp+0A8h+var_88], rdx
0x18000e6bb  lea     r9, [rsp+0A8h+var_38]
0x18000e6c0  mov     r8d, edi
0x18000e6c3  mov     edx, esi
0x18000e6c5  mov     rax, [rax+48h]
0x18000e6c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6ce  xorps   xmm0, xmm0
0x18000e6d1  movups  [rsp+0A8h+var_70], xmm0
0x18000e6d6  movups  [rsp+0A8h+var_60], xmm0
0x18000e6db  mov     byte ptr [rsp+0A8h+var_60+8], 1
0x18000e6e0  lea     rdx, [rsp+0A8h+var_50]
0x18000e6e5  lea     rcx, [rsp+0A8h+var_70]
0x18000e6ea  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_INTERACTIVE_UI_DATA@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &,_EAP_INTERACTIVE_UI_DATA const &)
0x18000e6ef  test    al, al
0x18000e6f1  jnz     short loc_18000E6FF
0x18000e6f3  lea     rcx, aComRefAssign; "com_ref:Assign"
0x18000e6fa  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18000e6ff  movups  xmm1, [rsp+0A8h+var_70]
0x18000e704  movsd   xmm2, qword ptr [rsp+0A8h+var_60]
0x18000e70a  xorps   xmm0, xmm0
0x18000e70d  movups  [rsp+0A8h+var_70], xmm0
0x18000e712  movups  [rsp+0A8h+var_60], xmm0
0x18000e717  mov     byte ptr [rsp+0A8h+var_60+8], 1
0x18000e71c  movups  xmmword ptr [rbx], xmm1
0x18000e71f  movsd   qword ptr [rbx+10h], xmm2
0x18000e724  lea     rcx, [rsp+0A8h+var_70]
0x18000e729  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<TaskAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18000e72e  nop
0x18000e72f  mov     rcx, [rsp+0A8h+arg_30]; this
0x18000e737  test    rcx, rcx
0x18000e73a  jz      short loc_18000E742
0x18000e73c  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000e741  nop
0x18000e742  jmp     short loc_18000E74A
0x18000e744  jmp     short loc_18000E74A
0x18000e746  jmp     short loc_18000E74A
0x18000e748  jmp     short $+2
0x18000e74a  lea     rcx, [rsp+0A8h+var_50]
0x18000e74f  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_INTERACTIVE_UI_DATA@@@Z; Free<HeapAllocator>(_EAP_INTERACTIVE_UI_DATA &)
0x18000e754  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18000e758  lea     r11, [rsp+0A8h+var_8]
0x18000e760  mov     rbx, [r11+10h]
0x18000e764  mov     rsi, [r11+18h]
0x18000e768  mov     rsp, r11
0x18000e76b  pop     rdi
0x18000e76c  retn
```
