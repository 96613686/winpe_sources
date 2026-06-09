# EapLm::Peer::EapLibraryManagerRuntime::CreateEapMethodRuntime(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,ulong)

- ea: `0x180010d10`
- end: `0x180010e4b`
- name: `?CreateEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@EEAA?AV?$SmartPointer@UIEapMethod@EapLm@@@@AEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@K@Z`
- size: `315`
- prototype: `__int64 __usercall@<rax>(EapLm::Peer::EapLibraryManagerRuntime *this@<rcx>, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000ada8`
- `0x180010d10`
- `0x180011064`
- `0x180011374`
- `0x1800123f0`
- `0x180014e0c`
- `0x18001bd04`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
volatile signed __int32 **__fastcall EapLm::Peer::EapLibraryManagerRuntime::CreateEapMethodRuntime(
        struct IThirdPartyEapDispatcherPeerRuntime **this,
        volatile signed __int32 **a2,
        __int64 a3,
        unsigned int a4,
        __int16 a5)
{
  DWORD v7; // eax
  __int64 v8; // rcx
  __int64 v9; // r10
  unsigned int v10; // r11d
  volatile signed __int32 *v11; // rax
  struct _EAP_METHOD_TYPE v13; // [rsp+30h] [rbp-10h] BYREF

  *(_WORD *)(&v13.eapType.type + 1) = 0;
  *(&v13.eapType.type + 3) = 0;
  *(_QWORD *)&v13.eapType.dwVendorId = 0;
  v13.eapType.type = *(_BYTE *)(a3 + 8);
  v13.eapType.dwVendorId = *(_DWORD *)(a3 + 12);
  v13.eapType.dwVendorType = *(_DWORD *)(a3 + 16);
  v7 = *(_DWORD *)(a3 + 24);
  v13.dwAuthorId = v7;
  if ( *((_DWORD *)this + 19) )
  {
    if ( v7 )
    {
      v11 = (volatile signed __int32 *)HeapAllocator::Alloc(0x200u);
      if ( v11 )
        v11 = (volatile signed __int32 *)EapLm::Peer::EapMethodRuntime::EapMethodRuntime(
                                           (EapLm::Peer::EapMethodRuntime *)v11,
                                           &v13);
    }
    else
    {
      v11 = (volatile signed __int32 *)HeapAllocator::Alloc(0x180u);
      if ( v11 )
        v11 = (volatile signed __int32 *)EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(
                                           (EapLm::Peer::LegacyEapMethodRuntime *)v11,
                                           &v13);
    }
  }
  else if ( (unsigned __int8)EapLm::BaseEapLibraryManager::IsMicrosoftLegacyMethod(this, a3, a4) )
  {
    v11 = (volatile signed __int32 *)HeapAllocator::Alloc(0x180u);
    if ( v11 )
      v11 = (volatile signed __int32 *)EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(
                                         (EapLm::Peer::LegacyEapMethodRuntime *)v11,
                                         &v13);
  }
  else if ( (unsigned __int8)EapLm::BaseEapLibraryManager::IsMicrosoftNewMethod(v8, v9, v10) )
  {
    v11 = (volatile signed __int32 *)HeapAllocator::Alloc(0x200u);
    if ( v11 )
      v11 = (volatile signed __int32 *)EapLm::Peer::EapMethodRuntime::EapMethodRuntime(
                                         (EapLm::Peer::EapMethodRuntime *)v11,
                                         &v13);
  }
  else
  {
    v11 = (volatile signed __int32 *)EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(
                                       this,
                                       &v13,
                                       a5);
  }
  *a2 = v11;
  if ( v11 )
    _InterlockedIncrement(v11 + 2);
  return a2;
}

```

## disassembly

```asm
0x180010d10  mov     [rsp-8+arg_0], rbx
0x180010d15  mov     [rsp-8+arg_10], rdi
0x180010d1a  mov     [rsp-8+arg_8], rdx
0x180010d1f  push    rbp
0x180010d20  mov     rbp, rsp
0x180010d23  sub     rsp, 40h
0x180010d27  mov     r11d, r9d
0x180010d2a  mov     r10, r8
0x180010d2d  mov     rbx, rdx
0x180010d30  mov     rdi, rcx
0x180010d33  xor     eax, eax
0x180010d35  mov     word ptr [rbp+var_10.eapType+1], ax
0x180010d39  mov     byte ptr [rbp+var_10.eapType+3], al
0x180010d3c  mov     qword ptr [rbp+var_10.eapType.dwVendorId], rax
0x180010d40  mov     al, [r8+8]
0x180010d44  mov     [rbp+var_10.eapType.type], al
0x180010d47  mov     eax, [r8+0Ch]
0x180010d4b  mov     [rbp+var_10.eapType.dwVendorId], eax
0x180010d4e  mov     eax, [r8+10h]
0x180010d52  mov     [rbp+var_10.eapType.dwVendorType], eax
0x180010d55  mov     eax, [r8+18h]
0x180010d59  mov     [rbp+var_10.dwAuthorId], eax
0x180010d5c  cmp     dword ptr [rcx+4Ch], 0
0x180010d60  jnz     loc_180010DE6
0x180010d66  mov     r8d, r9d
0x180010d69  mov     rdx, r10
0x180010d6c  call    ?IsMicrosoftLegacyMethod@BaseEapLibraryManager@EapLm@@IEBA_NAEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsMicrosoftLegacyMethod(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180010d71  test    al, al
0x180010d73  jz      short loc_180010D9A
0x180010d75  mov     ecx, 180h; unsigned __int64
0x180010d7a  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180010d7f  mov     [rbp+arg_8], rax
0x180010d83  test    rax, rax
0x180010d86  jz      short loc_180010D95
0x180010d88  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180010d8c  mov     rcx, rax; this
0x180010d8f  call    ??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180010d94  nop
0x180010d95  jmp     loc_180010E2C
0x180010d9a  mov     r8d, r11d
0x180010d9d  mov     rdx, r10
0x180010da0  call    ?IsMicrosoftNewMethod@BaseEapLibraryManager@EapLm@@IEBA_NAEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsMicrosoftNewMethod(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180010da5  test    al, al
0x180010da7  jz      short loc_180010DCB
0x180010da9  mov     ecx, 200h; unsigned __int64
0x180010dae  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180010db3  mov     [rbp+arg_8], rax
0x180010db7  test    rax, rax
0x180010dba  jz      short loc_180010DC9
0x180010dbc  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180010dc0  mov     rcx, rax; this
0x180010dc3  call    ??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180010dc8  nop
0x180010dc9  jmp     short loc_180010E2C
0x180010dcb  movaps  xmm0, xmmword ptr [rbp+var_10.eapType.type]
0x180010dcf  movdqa  xmmword ptr [rbp+var_10.eapType.type], xmm0
0x180010dd4  mov     r8d, [rbp+arg_20]; unsigned int
0x180010dd8  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180010ddc  mov     rcx, rdi; this
0x180010ddf  call    ?CreateThirdPartyEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAAPEAUIEapMethodRuntime@23@U_EAP_METHOD_TYPE@@K@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE,ulong)
0x180010de4  jmp     short loc_180010E2C
0x180010de6  test    eax, eax
0x180010de8  jnz     short loc_180010E0C
0x180010dea  mov     ecx, 180h; unsigned __int64
0x180010def  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180010df4  mov     [rbp+arg_8], rax
0x180010df8  test    rax, rax
0x180010dfb  jz      short loc_180010E0A
0x180010dfd  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180010e01  mov     rcx, rax; this
0x180010e04  call    ??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180010e09  nop
0x180010e0a  jmp     short loc_180010E2C
0x180010e0c  mov     ecx, 200h; unsigned __int64
0x180010e11  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180010e16  mov     [rbp+arg_8], rax
0x180010e1a  test    rax, rax
0x180010e1d  jz      short loc_180010E2C
0x180010e1f  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180010e23  mov     rcx, rax; this
0x180010e26  call    ??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180010e2b  nop
0x180010e2c  mov     [rbx], rax
0x180010e2f  test    rax, rax
0x180010e32  jz      short loc_180010E38
0x180010e34  lock inc dword ptr [rax+8]
0x180010e38  mov     rax, rbx
0x180010e3b  mov     rbx, [rsp+40h+arg_0]
0x180010e40  mov     rdi, [rsp+40h+arg_10]
0x180010e45  add     rsp, 40h
0x180010e49  pop     rbp
0x180010e4a  retn
```
