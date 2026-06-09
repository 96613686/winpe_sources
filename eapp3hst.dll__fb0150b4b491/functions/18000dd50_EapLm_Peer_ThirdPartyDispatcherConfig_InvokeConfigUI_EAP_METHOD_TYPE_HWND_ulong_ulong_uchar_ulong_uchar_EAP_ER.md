# EapLm::Peer::ThirdPartyDispatcherConfig::InvokeConfigUI(_EAP_METHOD_TYPE *,HWND__ *,ulong,ulong,uchar *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000dd50`
- end: `0x18000df4d`
- name: `?InvokeConfigUI@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJPEAU_EAP_METHOD_TYPE@@PEAUHWND__@@KKPEAEPEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, struct _EAP_METHOD_TYPE *, HWND, unsigned int, unsigned int, unsigned __int8 *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000439c`
- `0x180005894`
- `0x1800067cc`
- `0x180006c0c`
- `0x18000bf94`
- `0x18000dd50`
- `0x18000ec84`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::InvokeConfigUI(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        struct _EAP_METHOD_TYPE *a2,
        HWND a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int *a7,
        unsigned __int8 **a8,
        struct _EAP_ERROR **a9)
{
  unsigned __int8 **v13; // r14
  unsigned __int8 **v15; // rsi
  unsigned __int64 v16; // rcx
  int *v17; // r9
  struct _EAP_ERROR *v18; // [rsp+30h] [rbp-A8h] BYREF
  void *v19; // [rsp+38h] [rbp-A0h] BYREF
  size_t v20; // [rsp+40h] [rbp-98h]
  ReferenceCounted *v21; // [rsp+48h] [rbp-90h] BYREF
  void **v22; // [rsp+50h] [rbp-88h] BYREF
  BYTE type; // [rsp+58h] [rbp-80h]
  __int64 v24; // [rsp+5Ch] [rbp-7Ch]
  DWORD dwAuthorId; // [rsp+68h] [rbp-70h]
  _QWORD v26[2]; // [rsp+70h] [rbp-68h] BYREF
  const ATL::CAtlException *v27; // [rsp+80h] [rbp-58h] BYREF
  const EapHost::EapException *v28; // [rsp+88h] [rbp-50h] BYREF
  const Exception *v29; // [rsp+90h] [rbp-48h] BYREF

  LODWORD(v18) = 0;
  v13 = a8;
  if ( !a8 )
    return 2147500035LL;
  *a7 = 0;
  *v13 = 0;
  v15 = 0;
  a8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, a5);
  v19 = 0;
  v20 = 0;
  type = a2->eapType.type;
  v24 = *(_QWORD *)&a2->eapType.dwVendorId;
  if ( type != 0xFE )
    v24 = 0;
  try
  {
    v22 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a2->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
      *((_QWORD **)this - 12),
      (ReferenceCounted *)&v21,
      (__int64)&v22);
    v22 = &EapHost::EapType::`vftable';
    v26[1] = a5;
    v26[0] = a6;
    (*(void (__fastcall **)(ReferenceCounted *, _QWORD, _QWORD *, HWND, void **))(*(_QWORD *)v21 + 32LL))(
      v21,
      a4,
      v26,
      a3,
      &v19);
    v16 = v20;
    if ( v20 )
    {
      com_ptr<unsigned char>::Assign(&a8, v19, v20);
      v15 = a8;
      v16 = v20;
    }
    *a7 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(v16);
    a8 = 0;
    *v13 = (unsigned __int8 *)v15;
    if ( v21 )
      ReferenceCounted::Release(v21);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v18) = -2147024882;
    if ( a9 )
      *a9 = 0;
  }
  catch ( const ATL::CAtlException *v27 )
  {
    LODWORD(v18) = *(_DWORD *)v27;
    if ( a9 )
      *a9 = 0;
  }
  catch ( const EapHost::EapException *v28 )
  {
    EapHost::EapException2EapErrorOle(v28, (const struct EapHost::EapException *)a9, &v18, v17);
  }
  catch ( const Exception *v29 )
  {
    EapHost::Exception2EapErrorOle(v29, (const struct Exception *)a9, &v18, v17);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids,
      *a7,
      (_DWORD)v18);
  HeapAllocator::Free(v19);
  com_ptr<unsigned char>::Clear((void **)&a8);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18000dd50  push    rbx
0x18000dd52  push    rsi
0x18000dd53  push    rdi
0x18000dd54  push    r12
0x18000dd56  push    r13
0x18000dd58  push    r14
0x18000dd5a  push    r15
0x18000dd5c  sub     rsp, 0A0h
0x18000dd63  mov     r12d, r9d
0x18000dd66  mov     r13, r8
0x18000dd69  mov     rdi, rdx
0x18000dd6c  mov     r15, rcx
0x18000dd6f  xor     edx, edx
0x18000dd71  mov     dword ptr [rsp+0D8h+var_A8], edx
0x18000dd75  mov     r14, [rsp+0D8h+arg_38]
0x18000dd7d  test    r14, r14
0x18000dd80  jnz     short loc_18000DD8C
0x18000dd82  mov     eax, 80004003h
0x18000dd87  jmp     loc_18000DF3A
0x18000dd8c  mov     rax, [rsp+0D8h+arg_30]
0x18000dd94  mov     [rax], edx
0x18000dd96  mov     [r14], rdx
0x18000dd99  mov     rsi, rdx
0x18000dd9c  mov     [rsp+0D8h+arg_38], rdx
0x18000dda4  lea     rbx, WPP_GLOBAL_Control
0x18000ddab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ddb2  cmp     rcx, rbx
0x18000ddb5  jz      short loc_18000DDDC
0x18000ddb7  test    byte ptr [rcx+1Ch], 4
0x18000ddbb  jz      short loc_18000DDDC
0x18000ddbd  mov     edx, 0Ah
0x18000ddc2  mov     r9d, [rsp+0D8h+arg_20]
0x18000ddca  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000ddd1  mov     rcx, [rcx+10h]
0x18000ddd5  call    WPP_SF_d
0x18000ddda  xor     edx, edx
0x18000dddc  mov     [rsp+0D8h+var_A0], rdx
0x18000dde1  mov     [rsp+0D8h+var_98], rdx
0x18000dde6  mov     cl, [rdi]
0x18000dde8  mov     [rsp+0D8h+var_80], cl
0x18000ddec  mov     eax, [rdi+4]
0x18000ddef  mov     dword ptr [rsp+0D8h+var_7C], eax
0x18000ddf3  mov     eax, [rdi+8]
0x18000ddf6  mov     dword ptr [rsp+0D8h+var_7C+4], eax
0x18000ddfa  cmp     cl, 0FEh
0x18000ddfd  jz      short loc_18000DE08
0x18000ddff  mov     [rsp+0D8h+var_7C], 0
0x18000de08  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000de0f  mov     [rsp+0D8h+var_88], rax
0x18000de14  mov     eax, [rdi+0Ch]
0x18000de17  mov     [rsp+0D8h+var_70], eax
0x18000de1b  lea     r8, [rsp+0D8h+var_88]
0x18000de20  lea     rdx, [rsp+0D8h+var_90]
0x18000de25  mov     rcx, [r15-60h]
0x18000de29  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000de2e  nop
0x18000de2f  lea     rax, ??_7EapType@EapHost@@6B@; const EapHost::EapType::`vftable'
0x18000de36  mov     [rsp+0D8h+var_88], rax
0x18000de3b  mov     eax, [rsp+0D8h+arg_20]
0x18000de42  mov     [rsp+0D8h+var_60], rax
0x18000de47  mov     rax, [rsp+0D8h+arg_28]
0x18000de4f  mov     [rsp+0D8h+var_68], rax
0x18000de54  mov     rcx, [rsp+0D8h+var_90]
0x18000de59  mov     rax, [rcx]
0x18000de5c  lea     rdx, [rsp+0D8h+var_A0]
0x18000de61  mov     [rsp+0D8h+var_B8], rdx
0x18000de66  mov     r9, r13
0x18000de69  lea     r8, [rsp+0D8h+var_68]
0x18000de6e  mov     edx, r12d
0x18000de71  mov     rax, [rax+20h]
0x18000de75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de7a  mov     rcx, [rsp+0D8h+var_98]
0x18000de7f  test    rcx, rcx
0x18000de82  jz      short loc_18000DEA6
0x18000de84  mov     r8, rcx
0x18000de87  mov     rdx, [rsp+0D8h+var_A0]
0x18000de8c  lea     rcx, [rsp+0D8h+arg_38]
0x18000de94  call    ?Assign@?$com_ptr@E@@QEAAXPEBE_K@Z; com_ptr<uchar>::Assign(uchar const *,unsigned __int64)
0x18000de99  mov     rsi, [rsp+0D8h+arg_38]
0x18000dea1  mov     rcx, [rsp+0D8h+var_98]
0x18000dea6  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000deab  mov     rcx, [rsp+0D8h+arg_30]
0x18000deb3  mov     [rcx], eax
0x18000deb5  mov     [rsp+0D8h+arg_38], 0
0x18000dec1  mov     [r14], rsi
0x18000dec4  mov     rcx, [rsp+0D8h+var_90]; this
0x18000dec9  test    rcx, rcx
0x18000decc  jz      short loc_18000DED4
0x18000dece  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000ded3  nop
0x18000ded4  jmp     short loc_18000DEE3
0x18000ded6  jmp     short loc_18000DEDC
0x18000ded8  jmp     short loc_18000DEDC
0x18000deda  jmp     short $+2
0x18000dedc  lea     rbx, WPP_GLOBAL_Control
0x18000dee3  mov     rcx, cs:WPP_GLOBAL_Control
0x18000deea  cmp     rcx, rbx
0x18000deed  jz      short loc_18000DF1E
0x18000deef  test    byte ptr [rcx+1Ch], 4
0x18000def3  jz      short loc_18000DF1E
0x18000def5  mov     edx, 0Bh
0x18000defa  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18000defe  mov     dword ptr [rsp+0D8h+var_B8], eax
0x18000df02  mov     r9, [rsp+0D8h+arg_30]
0x18000df0a  mov     r9d, [r9]
0x18000df0d  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000df14  mov     rcx, [rcx+10h]
0x18000df18  call    WPP_SF_dd
0x18000df1d  nop
0x18000df1e  mov     rcx, [rsp+0D8h+var_A0]; void *
0x18000df23  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000df28  nop
0x18000df29  lea     rcx, [rsp+0D8h+arg_38]
0x18000df31  call    ?Clear@?$com_ptr@E@@QEAAXXZ; com_ptr<uchar>::Clear(void)
0x18000df36  mov     eax, dword ptr [rsp+0D8h+var_A8]
0x18000df3a  add     rsp, 0A0h
0x18000df41  pop     r15
0x18000df43  pop     r14
0x18000df45  pop     r13
0x18000df47  pop     r12
0x18000df49  pop     rdi
0x18000df4a  pop     rsi
0x18000df4b  pop     rbx
0x18000df4c  retn
```
