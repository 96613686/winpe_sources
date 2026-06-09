# EapLm::Peer::ThirdPartyDispatcherConfig::QueryCredentialInputFields(__int64,_EAP_METHOD_TYPE,ulong,ulong,uchar const *,_EAP_CONFIG_INPUT_FIELD_ARRAY *,_EAP_ERROR * *)

- ea: `0x18000e450`
- end: `0x18000e5d1`
- name: `?QueryCredentialInputFields@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJ_JU_EAP_METHOD_TYPE@@KKPEBEPEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAPEAU_EAP_ERROR@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, __int64, struct _EAP_METHOD_TYPE *, unsigned int, unsigned int, const unsigned __int8 *, struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000ccf4`
- `0x18000ce64`
- `0x18000e450`
- `0x180012a00`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## string_xrefs

- `0x18000e55f`: `com_ref:Assign`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::QueryCredentialInputFields(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        __int64 a2,
        struct _EAP_METHOD_TYPE *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a7,
        struct _EAP_ERROR **a8)
{
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY *v10; // rbx
  _QWORD *v12; // r9
  int *v13; // r9
  struct _EAP_CONFIG_INPUT_FIELD_ARRAY v14; // xmm1
  struct _EAP_ERROR *v15; // [rsp+30h] [rbp-78h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-70h] BYREF
  DWORD dwAuthorId; // [rsp+50h] [rbp-58h]
  __int128 v18; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v19[2]; // [rsp+68h] [rbp-40h] BYREF
  const ATL::CAtlException *v20; // [rsp+78h] [rbp-30h] BYREF
  const EapHost::EapException *v21; // [rsp+80h] [rbp-28h] BYREF
  const Exception *v22; // [rsp+88h] [rbp-20h] BYREF
  const Exception *v23; // [rsp+90h] [rbp-18h] BYREF

  LODWORD(v15) = 0;
  v18 = 0;
  v10 = a7;
  if ( a7 )
  {
    v12 = (_QWORD *)*((_QWORD *)this - 12);
    v16[8] = a3->eapType.type;
    *(_DWORD *)&v16[12] = a3->eapType.dwVendorId;
    *(_DWORD *)&v16[16] = a3->eapType.dwVendorType;
    if ( v16[8] != 0xFE )
      *(_QWORD *)&v16[12] = 0;
    try
    {
      *(_QWORD *)v16 = &EapHost::EapMethodType::`vftable';
      dwAuthorId = a3->dwAuthorId;
      EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(v12, (ReferenceCounted *)&a7, (__int64)v16);
      *(_QWORD *)v16 = &EapHost::EapType::`vftable';
      v19[1] = a5;
      v19[0] = a6;
      (*(void (__fastcall **)(struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, __int64, _QWORD, _QWORD *, __int128 *))(*(_QWORD *)&a7->dwVersion + 40LL))(
        a7,
        a2,
        a4,
        v19,
        &v18);
      *(_OWORD *)v16 = 0;
      *(_QWORD *)&v16[16] = 1;
      if ( !Copy<TaskAllocator>((__int64)v16, (__int64)&v18) )
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
      EapHost::EapException2EapErrorOle(v21, (const struct EapHost::EapException *)a8, &v15, v13);
      goto LABEL_9;
    }
    catch ( const Exception *v22 )
    {
      EapHost::Exception2EapErrorOle(v22, (const struct Exception *)a8, &v15, v13);
      goto LABEL_9;
    }
    v14 = *(struct _EAP_CONFIG_INPUT_FIELD_ARRAY *)v16;
    *(_OWORD *)v16 = 0;
    *(_QWORD *)&v16[16] = 1;
    *v10 = v14;
    Free<TaskAllocator>((__int64)v16);
    if ( a7 )
      ReferenceCounted::Release((ReferenceCounted *)a7);
LABEL_9:
    Free<HeapAllocator>((__int64)&v18);
    return (unsigned int)v15;
  }
  else
  {
    Free<HeapAllocator>((__int64)&v18);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18000e450  mov     rax, rsp
0x18000e453  mov     [rax+8], rbx
0x18000e457  mov     [rax+10h], rsi
0x18000e45b  push    rdi
0x18000e45c  sub     rsp, 0A0h
0x18000e463  mov     edi, r9d
0x18000e466  mov     rsi, rdx
0x18000e469  mov     dword ptr [rax-78h], 0
0x18000e470  xorps   xmm0, xmm0
0x18000e473  movups  xmmword ptr [rax-50h], xmm0
0x18000e477  mov     rbx, [rsp+0A8h+arg_30]
0x18000e47f  test    rbx, rbx
0x18000e482  jnz     short loc_18000E497
0x18000e484  lea     rcx, [rax-50h]
0x18000e488  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<HeapAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000e48d  mov     eax, 80004003h
0x18000e492  jmp     loc_18000E5BC
0x18000e497  mov     r9, [rcx-60h]
0x18000e49b  mov     cl, [r8]
0x18000e49e  mov     byte ptr [rsp+0A8h+var_70+8], cl
0x18000e4a2  mov     eax, [r8+4]
0x18000e4a6  mov     dword ptr [rsp+0A8h+var_70+0Ch], eax
0x18000e4aa  mov     eax, [r8+8]
0x18000e4ae  mov     dword ptr [rsp+0A8h+var_60], eax
0x18000e4b2  cmp     cl, 0FEh
0x18000e4b5  jz      short loc_18000E4C0
0x18000e4b7  mov     qword ptr [rsp+0A8h+var_70+0Ch], 0
0x18000e4c0  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000e4c7  mov     qword ptr [rsp+0A8h+var_70], rax
0x18000e4cc  mov     eax, [r8+0Ch]
0x18000e4d0  mov     [rsp+0A8h+var_58], eax
0x18000e4d4  lea     r8, [rsp+0A8h+var_70]
0x18000e4d9  lea     rdx, [rsp+0A8h+arg_30]
0x18000e4e1  mov     rcx, r9
0x18000e4e4  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000e4e9  nop
0x18000e4ea  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000e4f1  mov     qword ptr [rsp+0A8h+var_70], rax
0x18000e4f6  mov     eax, [rsp+0A8h+arg_20]
0x18000e4fd  mov     [rsp+0A8h+var_38], rax
0x18000e502  mov     rax, [rsp+0A8h+arg_28]
0x18000e50a  mov     [rsp+0A8h+var_40], rax
0x18000e50f  mov     rcx, [rsp+0A8h+arg_30]
0x18000e517  mov     rax, [rcx]
0x18000e51a  lea     rdx, [rsp+0A8h+var_50]
0x18000e51f  mov     [rsp+0A8h+var_88], rdx
0x18000e524  lea     r9, [rsp+0A8h+var_40]
0x18000e529  mov     r8d, edi
0x18000e52c  mov     rdx, rsi
0x18000e52f  mov     rax, [rax+28h]
0x18000e533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e538  xorps   xmm0, xmm0
0x18000e53b  xor     eax, eax
0x18000e53d  movups  [rsp+0A8h+var_70], xmm0
0x18000e542  mov     [rsp+0A8h+var_60], rax
0x18000e547  mov     byte ptr [rsp+0A8h+var_60], 1
0x18000e54c  lea     rdx, [rsp+0A8h+var_50]
0x18000e551  lea     rcx, [rsp+0A8h+var_70]
0x18000e556  call    ??$Copy@VTaskAllocator@@@@YA_NAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@AEBU0@@Z; Copy<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &,_EAP_CONFIG_INPUT_FIELD_ARRAY const &)
0x18000e55b  test    al, al
0x18000e55d  jnz     short loc_18000E56B
0x18000e55f  lea     rcx, aComRefAssign; "com_ref:Assign"
0x18000e566  call    ?Throw@LowMemoryError@@SAXPEB_W@Z; LowMemoryError::Throw(wchar_t const *)
0x18000e56b  movups  xmm1, [rsp+0A8h+var_70]
0x18000e570  xorps   xmm0, xmm0
0x18000e573  xor     eax, eax
0x18000e575  movups  [rsp+0A8h+var_70], xmm0
0x18000e57a  mov     [rsp+0A8h+var_60], rax
0x18000e57f  mov     byte ptr [rsp+0A8h+var_60], 1
0x18000e584  movdqu  xmmword ptr [rbx], xmm1
0x18000e588  lea     rcx, [rsp+0A8h+var_70]
0x18000e58d  call    ??$Free@VTaskAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<TaskAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000e592  nop
0x18000e593  mov     rcx, [rsp+0A8h+arg_30]; this
0x18000e59b  test    rcx, rcx
0x18000e59e  jz      short loc_18000E5A6
0x18000e5a0  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000e5a5  nop
0x18000e5a6  jmp     short loc_18000E5AE
0x18000e5a8  jmp     short loc_18000E5AE
0x18000e5aa  jmp     short loc_18000E5AE
0x18000e5ac  jmp     short $+2
0x18000e5ae  lea     rcx, [rsp+0A8h+var_50]
0x18000e5b3  call    ??$Free@VHeapAllocator@@@@YAXAEAU_EAP_CONFIG_INPUT_FIELD_ARRAY@@@Z; Free<HeapAllocator>(_EAP_CONFIG_INPUT_FIELD_ARRAY &)
0x18000e5b8  mov     eax, dword ptr [rsp+0A8h+var_78]
0x18000e5bc  lea     r11, [rsp+0A8h+var_8]
0x18000e5c4  mov     rbx, [r11+10h]
0x18000e5c8  mov     rsi, [r11+18h]
0x18000e5cc  mov     rsp, r11
0x18000e5cf  pop     rdi
0x18000e5d0  retn
```
