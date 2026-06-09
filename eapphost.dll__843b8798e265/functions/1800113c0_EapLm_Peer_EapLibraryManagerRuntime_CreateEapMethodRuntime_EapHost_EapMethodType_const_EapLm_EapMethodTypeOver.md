# EapLm::Peer::EapLibraryManagerRuntime::CreateEapMethodRuntime(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType,ulong)

- ea: `0x1800113c0`
- end: `0x1800114fc`
- name: `?CreateEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@EEAA?AV?$SmartPointer@UIEapMethod@EapLm@@@@AEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@3@K@Z`
- size: `316`
- prototype: `__int64 __usercall@<rax>(EapLm::Peer::EapLibraryManagerRuntime *this@<rcx>, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000b248`
- `0x1800113c0`
- `0x18001177c`
- `0x180011aa4`
- `0x180012b74`
- `0x180015648`
- `0x18001c72c`

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
0x1800113c0  mov     [rsp-8+arg_0], rbx
0x1800113c5  mov     [rsp-8+arg_10], rdi
0x1800113ca  mov     [rsp-8+arg_8], rdx
0x1800113cf  push    rbp
0x1800113d0  mov     rbp, rsp
0x1800113d3  sub     rsp, 40h
0x1800113d7  mov     r11d, r9d
0x1800113da  mov     r10, r8
0x1800113dd  mov     rbx, rdx
0x1800113e0  mov     rdi, rcx
0x1800113e3  xor     eax, eax
0x1800113e5  mov     word ptr [rbp+var_10.eapType+1], ax
0x1800113e9  mov     byte ptr [rbp+var_10.eapType+3], al
0x1800113ec  mov     qword ptr [rbp+var_10.eapType.dwVendorId], rax
0x1800113f0  mov     al, [r8+8]
0x1800113f4  mov     [rbp+var_10.eapType.type], al
0x1800113f7  mov     eax, [r8+0Ch]
0x1800113fb  mov     [rbp+var_10.eapType.dwVendorId], eax
0x1800113fe  mov     eax, [r8+10h]
0x180011402  mov     [rbp+var_10.eapType.dwVendorType], eax
0x180011405  mov     eax, [r8+18h]
0x180011409  mov     [rbp+var_10.dwAuthorId], eax
0x18001140c  cmp     dword ptr [rcx+4Ch], 0
0x180011410  jnz     loc_180011496
0x180011416  mov     r8d, r9d
0x180011419  mov     rdx, r10
0x18001141c  call    ?IsMicrosoftLegacyMethod@BaseEapLibraryManager@EapLm@@IEBA_NAEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsMicrosoftLegacyMethod(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180011421  test    al, al
0x180011423  jz      short loc_18001144A
0x180011425  mov     ecx, 180h; unsigned __int64
0x18001142a  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x18001142f  mov     [rbp+arg_8], rax
0x180011433  test    rax, rax
0x180011436  jz      short loc_180011445
0x180011438  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x18001143c  mov     rcx, rax; this
0x18001143f  call    ??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180011444  nop
0x180011445  jmp     loc_1800114DC
0x18001144a  mov     r8d, r11d
0x18001144d  mov     rdx, r10
0x180011450  call    ?IsMicrosoftNewMethod@BaseEapLibraryManager@EapLm@@IEBA_NAEBVEapMethodType@EapHost@@W4EapMethodTypeOverrideType@EapMethodTypeOverrideValue@2@@Z; EapLm::BaseEapLibraryManager::IsMicrosoftNewMethod(EapHost::EapMethodType const &,EapLm::EapMethodTypeOverrideValue::EapMethodTypeOverrideType)
0x180011455  test    al, al
0x180011457  jz      short loc_18001147B
0x180011459  mov     ecx, 200h; unsigned __int64
0x18001145e  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x180011463  mov     [rbp+arg_8], rax
0x180011467  test    rax, rax
0x18001146a  jz      short loc_180011479
0x18001146c  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x180011470  mov     rcx, rax; this
0x180011473  call    ??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)
0x180011478  nop
0x180011479  jmp     short loc_1800114DC
0x18001147b  movaps  xmm0, xmmword ptr [rbp+var_10.eapType.type]
0x18001147f  movdqa  xmmword ptr [rbp+var_10.eapType.type], xmm0
0x180011484  mov     r8d, [rbp+arg_20]; unsigned int
0x180011488  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x18001148c  mov     rcx, rdi; this
0x18001148f  call    ?CreateThirdPartyEapMethodRuntime@EapLibraryManagerRuntime@Peer@EapLm@@QEAAPEAUIEapMethodRuntime@23@U_EAP_METHOD_TYPE@@K@Z; EapLm::Peer::EapLibraryManagerRuntime::CreateThirdPartyEapMethodRuntime(_EAP_METHOD_TYPE,ulong)
0x180011494  jmp     short loc_1800114DC
0x180011496  test    eax, eax
0x180011498  jnz     short loc_1800114BC
0x18001149a  mov     ecx, 180h; unsigned __int64
0x18001149f  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800114a4  mov     [rbp+arg_8], rax
0x1800114a8  test    rax, rax
0x1800114ab  jz      short loc_1800114BA
0x1800114ad  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x1800114b1  mov     rcx, rax; this
0x1800114b4  call    ??0LegacyEapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::LegacyEapMethodRuntime::LegacyEapMethodRuntime(_EAP_METHOD_TYPE const &)
0x1800114b9  nop
0x1800114ba  jmp     short loc_1800114DC
0x1800114bc  mov     ecx, 200h; unsigned __int64
0x1800114c1  call    ?Alloc@HeapAllocator@@SAPEAX_K@Z; HeapAllocator::Alloc(unsigned __int64)
0x1800114c6  mov     [rbp+arg_8], rax
0x1800114ca  test    rax, rax
0x1800114cd  jz      short loc_1800114DC
0x1800114cf  lea     rdx, [rbp+var_10]; struct _EAP_METHOD_TYPE *
0x1800114d3  mov     rcx, rax; this
0x1800114d6  call    ??0EapMethodRuntime@Peer@EapLm@@QEAA@AEBU_EAP_METHOD_TYPE@@@Z; EapLm::Peer::EapMethodRuntime::EapMethodRuntime(_EAP_METHOD_TYPE const &)
0x1800114db  nop
0x1800114dc  mov     [rbx], rax
0x1800114df  test    rax, rax
0x1800114e2  jz      short loc_1800114E8
0x1800114e4  lock inc dword ptr [rax+8]
0x1800114e8  mov     rax, rbx
0x1800114eb  mov     rbx, [rsp+40h+arg_0]
0x1800114f0  mov     rdi, [rsp+40h+arg_10]
0x1800114f5  add     rsp, 40h
0x1800114f9  pop     rbp
0x1800114fa  retn
```
