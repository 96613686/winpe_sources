# EapLm::Peer::ThirdPartyDispatcherConfig::QueryUserBlobFromCredentialInputFields(__int64,_EAP_METHOD_TYPE,ulong,ulong,uchar const *,_EAP_CONFIG_INPUT_FIELD_ARRAY const *,ulong *,uchar * *,_EAP_ERROR * *)

- ea: `0x18000e950`
- end: `0x18000eb2e`
- name: `?QueryUserBlobFromCredentialInputFields@ThirdPartyDispatcherConfig@Peer@EapLm@@UEAAJ_JU_EAP_METHOD_TYPE@@KKPEBEPEBU_EAP_CONFIG_INPUT_FIELD_ARRAY@@PEAKPEAPEAEPEAPEAU_EAP_ERROR@@@Z`
- size: `478`
- prototype: `__int64 __fastcall(EapLm::Peer::ThirdPartyDispatcherConfig *__hidden this, __int64, struct _EAP_METHOD_TYPE *, unsigned int, unsigned int, const unsigned __int8 *, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, unsigned int *, unsigned __int8 **, struct _EAP_ERROR **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x18000439c`
- `0x18000503c`
- `0x180005894`
- `0x18000bf94`
- `0x18000e950`
- `0x1800126f8`
- `0x180012c10`
- `0x180016e44`
- `0x180034010`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall EapLm::Peer::ThirdPartyDispatcherConfig::QueryUserBlobFromCredentialInputFields(
        EapLm::Peer::ThirdPartyDispatcherConfig *this,
        __int64 a2,
        struct _EAP_METHOD_TYPE *a3,
        unsigned int a4,
        unsigned int a5,
        const unsigned __int8 *a6,
        const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *a7,
        unsigned int *a8,
        unsigned __int8 **a9,
        struct _EAP_ERROR **a10)
{
  const void **v14; // rbx
  __int64 v15; // r9
  void *v16; // rax
  int *v17; // r9
  struct _EAP_ERROR *v19; // [rsp+40h] [rbp-98h] BYREF
  const ATL::CAtlException *v20; // [rsp+48h] [rbp-90h] BYREF
  const EapHost::EapException *v21; // [rsp+50h] [rbp-88h] BYREF
  const Exception *v22; // [rsp+58h] [rbp-80h] BYREF
  void *Src; // [rsp+60h] [rbp-78h] BYREF
  size_t Size; // [rsp+68h] [rbp-70h]
  _QWORD v25[2]; // [rsp+70h] [rbp-68h] BYREF
  void **v26; // [rsp+80h] [rbp-58h] BYREF
  BYTE type; // [rsp+88h] [rbp-50h]
  __int64 v28; // [rsp+8Ch] [rbp-4Ch]
  DWORD dwAuthorId; // [rsp+98h] [rbp-40h]

  LODWORD(v19) = 0;
  v14 = (const void **)a9;
  if ( !a9 || !a8 )
    return 2147500035LL;
  v15 = *a8;
  if ( (_DWORD)v15 && *a9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids, v15);
  }
  else
  {
    *a8 = 0;
    *v14 = 0;
  }
  type = a3->eapType.type;
  v28 = *(_QWORD *)&a3->eapType.dwVendorId;
  if ( type != 0xFE )
    v28 = 0;
  try
  {
    v26 = &EapHost::EapMethodType::`vftable';
    dwAuthorId = a3->dwAuthorId;
    EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(
      *((_QWORD **)this - 12),
      (ReferenceCounted *)&a9,
      (__int64)&v26);
    v25[1] = a5;
    v25[0] = a6;
    Src = 0;
    Size = 0;
    TempBuffer<0>::Assign((__int64)&Src, *a8, *v14);
    (*((void (__fastcall **)(unsigned __int8 **, __int64, _QWORD, _QWORD *, const struct _EAP_CONFIG_INPUT_FIELD_ARRAY *, void **))*a9
     + 6))(
      a9,
      a2,
      a4,
      v25,
      a7,
      &Src);
    if ( Size )
    {
      v16 = Copy<TaskAllocator>(Src, Size);
      *v14 = v16;
      if ( !v16 )
        LODWORD(v19) = -2147024882;
    }
    else
    {
      *v14 = 0;
    }
    *a8 = wil::safe_cast_failfast<unsigned long,unsigned __int64,0>(Size);
    HeapAllocator::Free(Src);
    if ( a9 )
      ReferenceCounted::Release((ReferenceCounted *)a9);
  }
  catch ( std::bad_alloc )
  {
    LODWORD(v19) = -2147024882;
    if ( a10 )
      *a10 = 0;
    return (unsigned int)v19;
  }
  catch ( const ATL::CAtlException *v20 )
  {
    LODWORD(v19) = *(_DWORD *)v20;
    if ( a10 )
      *a10 = 0;
    return (unsigned int)v19;
  }
  catch ( const EapHost::EapException *v21 )
  {
    EapHost::EapException2EapErrorOle(v21, (const struct EapHost::EapException *)a10, &v19, v17);
    return (unsigned int)v19;
  }
  catch ( const Exception *v22 )
  {
    EapHost::Exception2EapErrorOle(v22, (const struct Exception *)a10, &v19, v17);
  }
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x18000e950  push    rbx
0x18000e952  push    rsi
0x18000e953  push    rdi
0x18000e954  push    r12
0x18000e956  push    r14
0x18000e958  push    r15
0x18000e95a  sub     rsp, 0A8h
0x18000e961  mov     r15d, r9d
0x18000e964  mov     rsi, r8
0x18000e967  mov     r12, rdx
0x18000e96a  mov     r14, rcx
0x18000e96d  mov     dword ptr [rsp+0D8h+var_98], 0
0x18000e975  mov     rbx, [rsp+0D8h+arg_40]
0x18000e97d  test    rbx, rbx
0x18000e980  jz      loc_18000EB18
0x18000e986  mov     rdi, [rsp+0D8h+arg_38]
0x18000e98e  test    rdi, rdi
0x18000e991  jz      loc_18000EB18
0x18000e997  mov     r9d, [rdi]
0x18000e99a  test    r9d, r9d
0x18000e99d  jz      short loc_18000E9D5
0x18000e99f  cmp     qword ptr [rbx], 0
0x18000e9a3  jz      short loc_18000E9D5
0x18000e9a5  lea     rax, WPP_GLOBAL_Control
0x18000e9ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e9b3  cmp     rcx, rax
0x18000e9b6  jz      short loc_18000E9E2
0x18000e9b8  test    byte ptr [rcx+1Ch], 4
0x18000e9bc  jz      short loc_18000E9E2
0x18000e9be  mov     edx, 0Eh
0x18000e9c3  lea     r8, WPP_054249383b5d3a79a2637b10c11f2f07_Traceguids
0x18000e9ca  mov     rcx, [rcx+10h]
0x18000e9ce  call    WPP_SF_d
0x18000e9d3  jmp     short loc_18000E9E2
0x18000e9d5  mov     dword ptr [rdi], 0
0x18000e9db  mov     qword ptr [rbx], 0
0x18000e9e2  mov     cl, [rsi]
0x18000e9e4  mov     [rsp+0D8h+var_50], cl
0x18000e9eb  mov     eax, [rsi+4]
0x18000e9ee  mov     dword ptr [rsp+0D8h+var_4C], eax
0x18000e9f5  mov     eax, [rsi+8]
0x18000e9f8  mov     dword ptr [rsp+0D8h+var_4C+4], eax
0x18000e9ff  cmp     cl, 0FEh
0x18000ea02  jz      short loc_18000EA10
0x18000ea04  mov     [rsp+0D8h+var_4C], 0
0x18000ea10  lea     rax, ??_7EapMethodType@EapHost@@6B@; const EapHost::EapMethodType::`vftable'
0x18000ea17  mov     [rsp+0D8h+var_58], rax
0x18000ea1f  mov     eax, [rsi+0Ch]
0x18000ea22  mov     [rsp+0D8h+var_40], eax
0x18000ea29  lea     r8, [rsp+0D8h+var_58]
0x18000ea31  lea     rdx, [rsp+0D8h+arg_40]
0x18000ea39  mov     rcx, [r14-60h]
0x18000ea3d  call    ?GetEapMethodConfig@EapLibraryManagerConfig@Peer@EapLm@@QEAA?AV?$SmartPointer@UIEapMethodConfig@Peer@EapLm@@@@AEBVEapMethodType@EapHost@@@Z; EapLm::Peer::EapLibraryManagerConfig::GetEapMethodConfig(EapHost::EapMethodType const &)
0x18000ea42  nop
0x18000ea43  mov     eax, [rsp+0D8h+arg_20]
0x18000ea4a  mov     [rsp+0D8h+var_60], rax
0x18000ea4f  mov     rax, [rsp+0D8h+arg_28]
0x18000ea57  mov     [rsp+0D8h+var_68], rax
0x18000ea5c  mov     [rsp+0D8h+Src], 0
0x18000ea65  mov     [rsp+0D8h+Size], 0
0x18000ea6e  mov     edx, [rdi]
0x18000ea70  mov     r8, [rbx]
0x18000ea73  lea     rcx, [rsp+0D8h+Src]
0x18000ea78  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18000ea7d  mov     rcx, [rsp+0D8h+arg_40]
0x18000ea85  mov     rax, [rcx]
0x18000ea88  lea     rdx, [rsp+0D8h+Src]
0x18000ea8d  mov     [rsp+0D8h+var_B0], rdx
0x18000ea92  mov     rdx, [rsp+0D8h+arg_30]
0x18000ea9a  mov     [rsp+0D8h+var_B8], rdx
0x18000ea9f  lea     r9, [rsp+0D8h+var_68]
0x18000eaa4  mov     r8d, r15d
0x18000eaa7  mov     rdx, r12
0x18000eaaa  mov     rax, [rax+30h]
0x18000eaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eab3  mov     rdx, [rsp+0D8h+Size]; Size
0x18000eab8  test    rdx, rdx
0x18000eabb  jz      short loc_18000EAD9
0x18000eabd  mov     rcx, [rsp+0D8h+Src]; Src
0x18000eac2  call    ??$Copy@VTaskAllocator@@@@YAPEAEPEBE_K@Z; Copy<TaskAllocator>(uchar const *,unsigned __int64)
0x18000eac7  mov     [rbx], rax
0x18000eaca  test    rax, rax
0x18000eacd  jnz     short loc_18000EAE0
0x18000eacf  mov     dword ptr [rsp+0D8h+var_98], 8007000Eh
0x18000ead7  jmp     short loc_18000EAE0
0x18000ead9  mov     qword ptr [rbx], 0
0x18000eae0  mov     rcx, [rsp+0D8h+Size]
0x18000eae5  call    ??$safe_cast_failfast@K_K$0A@@wil@@YAK_K@Z; wil::safe_cast_failfast<ulong,unsigned __int64,0>(unsigned __int64)
0x18000eaea  mov     [rdi], eax
0x18000eaec  mov     rcx, [rsp+0D8h+Src]; void *
0x18000eaf1  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x18000eaf6  nop
0x18000eaf7  mov     rcx, [rsp+0D8h+arg_40]; this
0x18000eaff  test    rcx, rcx
0x18000eb02  jz      short loc_18000EB0A
0x18000eb04  call    ?Release@ReferenceCounted@@QEAAXXZ; ReferenceCounted::Release(void)
0x18000eb09  nop
0x18000eb0a  jmp     short loc_18000EB12
0x18000eb0c  jmp     short loc_18000EB12
0x18000eb0e  jmp     short loc_18000EB12
0x18000eb10  jmp     short $+2
0x18000eb12  mov     eax, dword ptr [rsp+0D8h+var_98]
0x18000eb16  jmp     short loc_18000EB1D
0x18000eb18  mov     eax, 80004003h
0x18000eb1d  add     rsp, 0A8h
0x18000eb24  pop     r15
0x18000eb26  pop     r14
0x18000eb28  pop     r12
0x18000eb2a  pop     rdi
0x18000eb2b  pop     rsi
0x18000eb2c  pop     rbx
0x18000eb2d  retn
```
