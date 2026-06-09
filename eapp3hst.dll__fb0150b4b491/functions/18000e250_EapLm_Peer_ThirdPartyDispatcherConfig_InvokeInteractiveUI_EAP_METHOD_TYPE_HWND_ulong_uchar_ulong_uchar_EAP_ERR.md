# EapLm::Peer::ThirdPartyDispatcherConfig::InvokeInteractiveUI(_EAP_METHOD_TYPE *,HWND__ *,ulong,uchar *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000e250`
- end: `0x18000e43f`
- name: `?InvokeInteractiveUI@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@PEAUHWND__@@KPEAEPEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `495`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, struct _EAP_METHOD_TYPE *, HWND, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x180005894`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000bf94`
- `0x18000e250`
- `0x18000ec84`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::InvokeInteractiveUI(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        HWND a3,
        unsigned int a4,
        unsigned __int8 *a5,
        unsigned int *a6,
        unsigned __int8 **a7,
        struct _EAP_ERROR **a8)
{
  __int64 v8; // r12
  unsigned __int8 **v12; // r14
  unsigned __int8 **v13; // rsi
  unsigned __int64 v14; // rcx
  int *v15; // r9
  struct _EAP_ERROR *v17; // [rsp+30h] [rbp-A8h] BYREF
  void *v18; // [rsp+38h] [rbp-A0h] BYREF
  size_t v19; // [rsp+40h] [rbp-98h]
  ReferenceCounted *v20; // [rsp+48h] [rbp-90h] BYREF
  void **v21; // [rsp+50h] [rbp-88h] BYREF
  BYTE type; // [rsp+58h] [rbp-80h]
  __int64 v23; // [rsp+5Ch] [rbp-7Ch]
  DWORD dwAuthorId; // [rsp+68h] [rbp-70h]
  _QWORD v25[2]; // [rsp+70h] [rbp-68h] BYREF
  const ATL::CAtlException *v26; // [rsp+80h] [rbp-58h] BYREF
  const EapHost::EapException *v27; // [rsp+88h] [rbp-50h] BYREF
  const Exception *v28; // [rsp+90h] [rbp-48h] BYREF

  v8 = a4;
  LODWORD(v17) = 0;
  v12 = a7;
  if ( !a7 || !a6 )
    return 2147500035LL;
  *a6 = 0;
  *v12 = 0;
  v13 = 0;
  a7 = 0;
  v18 = 0;
  v19 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a4);
  type = a2->eapType.type;
  v23 = *(_QWORD *)&a2->eapType.dwVendorId;
  if ( type != 0xFE )
    v23 = 0;
  try
  {
    v21 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a2->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
      *((_QWORD **)this - 12),
      (ReferenceCounted *)&v20,
      (__int64)&v21);
    v21 = &EapHost::EapType::`vftable';
    v25[1] = v8;
    v25[0] = a5;
    (*(void (__fastcall **)(ReferenceCounted *, _QWORD *, HWND, void **))(*(_QWORD *)v20 + 64LL))(v20, v25, a3, &v18);
    v14 = v19;
    if ( v19 )
    {
      com_ptr<unsigned char>::Assign(&a7, v18, v19);
      v13 = a7;
      v14 = v19;
    }
    *a6 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v14);
    a7 = 0;
    *v12 = (unsigned __int8 *)v13;
    if ( v20 )
      ReferenceCounted::Release(v20);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v17) = -2147024882;
    if ( a8 )
      *a8 = 0;
  }
  catch ( const ATL::CAtlException *v26 )
  {
    LODWORD(v17) = *(_DWORD *)v26;
    if ( a8 )
      *a8 = 0;
  }
  catch ( const EapHost::EapException *v27 )
  {
    EapHost::EapException2EapErrorOle(v27, (const struct EapHost::EapException *)a8, &v17, v15);
  }
  catch ( const Exception *v28 )
  {
    EapHost::Exception2EapErrorOle(v28, (const struct Exception *)a8, &v17, v15);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids,
      *a6,
      (_DWORD)v17);
  HeapAllocator::Free(v18);
  com_ptr<unsigned char>::Clear((void **)&a7);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18000e250  push    rbx
0x18000e252  push    rsi
0x18000e253  push    rdi
0x18000e254  push    r12
0x18000e256  push    r13
0x18000e258  push    r14
0x18000e25a  push    r15
0x18000e25c  sub     rsp, 0A0h
0x18000e263  mov     r12d, r9d
0x18000e266  mov     r13, r8
0x18000e269  mov     rdi, rdx
0x18000e26c  mov     r15, rcx
0x18000e26f  xor     edx, edx
0x18000e271  mov     dword ptr [rsp+0D8h+var_A8], edx
0x18000e275  mov     r14, [rsp+0D8h+arg_30]
0x18000e27d  test    r14, r14
0x18000e280  jz      loc_18000E427
0x18000e286  mov     rax, [rsp+0D8h+arg_28]
0x18000e28e  test    rax, rax
0x18000e291  jz      loc_18000E427
0x18000e297  mov     [rax], edx
0x18000e299  mov     [r14], rdx
0x18000e29c  mov     esi, edx
0x18000e29e  mov     [rsp+0D8h+arg_30], rdx
0x18000e2a6  mov     [rsp+0D8h+var_A0], rdx
0x18000e2ab  mov     [rsp+0D8h+var_98], rdx
0x18000e2b0  lea     rbx, WPP_GLOBAL_Control
0x18000e2b7  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e2be  cmp     rcx, rbx
0x18000e2c1  jz      short loc_18000E2E0
0x18000e2c3  test    byte ptr [rcx+1Ch], 4
0x18000e2c7  jz      short loc_18000E2E0
0x18000e2c9  lea     edx, [rsi+17h]
0x18000e2cc  mov     r9d, r12d
0x18000e2cf  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000e2d6  mov     rcx, [rcx+10h]
0x18000e2da  call    WPP_SF_d
0x18000e2df  nop
0x18000e2e0  mov     cl, [rdi]
0x18000e2e2  mov     [rsp+0D8h+var_80], cl
0x18000e2e6  mov     eax, [rdi+4]
0x18000e2e9  mov     dword ptr [rsp+0D8h+var_7C], eax
0x18000e2ed  mov     eax, [rdi+8]
0x18000e2f0  mov     dword ptr [rsp+0D8h+var_7C+4], eax
0x18000e2f4  cmp     cl, 0FEh
0x18000e2f7  jz      short loc_18000E302
0x18000e2f9  mov     [rsp+0D8h+var_7C], 0
0x18000e302  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000e309  mov     [rsp+0D8h+var_88], rax
0x18000e30e  mov     eax, [rdi+0Ch]
0x18000e311  mov     [rsp+0D8h+var_70], eax
0x18000e315  lea     r8, [rsp+0D8h+var_88]
0x18000e31a  lea     rdx, [rsp+0D8h+var_90]
0x18000e31f  mov     rcx, [r15-60h]
0x18000e323  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000e328  nop
0x18000e329  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000e330  mov     [rsp+0D8h+var_88], rax
0x18000e335  mov     [rsp+0D8h+var_60], r12
0x18000e33a  mov     rax, [rsp+0D8h+arg_20]
0x18000e342  mov     [rsp+0D8h+var_68], rax
0x18000e347  mov     rcx, [rsp+0D8h+var_90]
0x18000e34c  mov     rax, [rcx]
0x18000e34f  lea     r9, [rsp+0D8h+var_A0]
0x18000e354  mov     r8, r13
0x18000e357  lea     rdx, [rsp+0D8h+var_68]
0x18000e35c  mov     rax, [rax+40h]
0x18000e360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e365  mov     rcx, [rsp+0D8h+var_98]
0x18000e36a  test    rcx, rcx
0x18000e36d  jz      short loc_18000E391
0x18000e36f  mov     r8, rcx
0x18000e372  mov     rdx, [rsp+0D8h+var_A0]
0x18000e377  lea     rcx, [rsp+0D8h+arg_30]
0x18000e37f  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000e384  mov     rsi, [rsp+0D8h+arg_30]
0x18000e38c  mov     rcx, [rsp+0D8h+var_98]
0x18000e391  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000e396  mov     rcx, [rsp+0D8h+arg_28]
0x18000e39e  mov     [rcx], eax
0x18000e3a0  mov     [rsp+0D8h+arg_30], 0
0x18000e3ac  mov     [r14], rsi
0x18000e3af  mov     rcx, [rsp+0D8h+var_90]; this
0x18000e3b4  test    rcx, rcx
0x18000e3b7  jz      short loc_18000E3BF
0x18000e3b9  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000e3be  nop
0x18000e3bf  jmp     short loc_18000E3CE
0x18000e3c1  jmp     short loc_18000E3C7
0x18000e3c3  jmp     short loc_18000E3C7
0x18000e3c5  jmp     short $+2
0x18000e3c7  lea     rbx, WPP_GLOBAL_Control
0x18000e3ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e3d5  cmp     rcx, rbx
0x18000e3d8  jz      short loc_18000E409
0x18000e3da  test    byte ptr [rcx+1Ch], 4
0x18000e3de  jz      short loc_18000E409
0x18000e3e0  mov     edx, 18h
0x18000e3e5  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18000e3e9  mov     [rsp+0D8h+var_B8], eax
0x18000e3ed  mov     r9, [rsp+0D8h+arg_28]
0x18000e3f5  mov     r9d, [r9]
0x18000e3f8  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000e3ff  mov     rcx, [rcx+10h]
0x18000e403  call    WPP_SF_dd
0x18000e408  nop
0x18000e409  mov     rcx, [rsp+0D8h+var_A0]; void *
0x18000e40e  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000e413  nop
0x18000e414  lea     rcx, [rsp+0D8h+arg_30]
0x18000e41c  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000e421  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18000e425  jmp     short loc_18000E42C
0x18000e427  mov     eax, 80004003h
0x18000e42c  add     rsp, 0A0h
0x18000e433  pop     r15
0x18000e435  pop     r14
0x18000e437  pop     r13
0x18000e439  pop     r12
0x18000e43b  pop     rdi
0x18000e43c  pop     rsi
0x18000e43d  pop     rbx
0x18000e43e  retn
```
