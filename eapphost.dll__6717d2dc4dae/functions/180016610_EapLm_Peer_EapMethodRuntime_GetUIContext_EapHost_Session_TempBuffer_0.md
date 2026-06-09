# EapLm::Peer::EapMethodRuntime::GetUIContext(EapHost::Session &,TempBuffer<0> &)

- ea: `0x180016610`
- end: `0x180016840`
- name: `?GetUIContext@EapMethodRuntime@Peer@EapLm@@UEAAXAEAVSession@EapHost@@AEAV?$TempBuffer@$0A@@@@Z`
- size: `560`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002a90`
- `0x1800072cc`
- `0x180009dc4`
- `0x180011578`
- `0x180011958`
- `0x180014d8c`
- `0x180016610`
- `0x18001dc64`
- `0x18002fd44`
- `0x180038010`

## import_xrefs

- `ntdll!EtwEventEnabled` at `0x18001667f`
- `ntdll!EtwEventEnabled` at `0x18001677b`
- `ntdll!EtwEventEnabled` at `0x18001667f`
- `ntdll!EtwEventEnabled` at `0x18001677b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EapLm::Peer::EapMethodRuntime::GetUIContext(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // eax
  const wchar_t *v7; // rdx
  __int64 result; // rax
  const wchar_t *v9; // rdx
  unsigned int v10; // [rsp+30h] [rbp-D0h] BYREF
  struct _EAP_ERROR *v11; // [rsp+38h] [rbp-C8h] BYREF
  const void *v12; // [rsp+40h] [rbp-C0h] BYREF
  char v13[96]; // [rsp+50h] [rbp-B0h] BYREF
  char v14[2048]; // [rsp+B0h] [rbp-50h] BYREF

  HeapAllocator::Free(*(void **)a3);
  *(_QWORD *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v12 = 0;
  v10 = 0;
  v11 = 0;
  if ( (unsigned __int8)EtwEventEnabled(eaphost_Context, DebugInfoEvent)
    && (int)StringCchPrintfA(v14, 0x800u, "EapPeerGetUIContext Entry") >= 0
    && Microsoft_Windows_EapHostEnableBits < 0 )
  {
    McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  v6 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, const void **, struct _EAP_ERROR **))(a1 + 376))(
         *(_QWORD *)(a2 + 64),
         &v10,
         &v12,
         &v11);
  if ( v6 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v13, v11, v6);
    (*(void (__fastcall **)(struct _EAP_ERROR *))(a1 + 424))(v11);
    EapHost::EapException::Throw(L"EapPeerGetUIContext", v7, (const struct EapHost::EapError *)v13);
  }
  if ( !v10 || !v12 )
  {
    EapHost::EapError::EapError((EapHost::EapError *)v13, v11, 0xDu);
    if ( v11 )
      (*(void (**)(void))(a1 + 424))();
    EapHost::EapException::Throw(L"EapPeerGetUIContext", v9, (const struct EapHost::EapError *)v13);
  }
  TempBuffer<0>::Assign(a3, v10, v12);
  result = EtwEventEnabled(eaphost_Context, DebugInfoEvent);
  if ( (_BYTE)result )
  {
    result = StringCchPrintfA(v14, 0x800u, "EapPeerGetUIContext Exit");
    if ( (int)result >= 0 && Microsoft_Windows_EapHostEnableBits < 0 )
      result = McTemplateU0s_EtwEventWriteTransfer(&eaphost_Context, (__int64)DebugInfoEvent, v14);
  }
  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    return WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180016610  push    rbp
0x180016612  push    rbx
0x180016613  push    rsi
0x180016614  push    rdi
0x180016615  push    r12
0x180016617  lea     rbp, [rsp-7C0h]
0x18001661f  sub     rsp, 8C0h
0x180016626  mov     rax, cs:__security_cookie
0x18001662d  xor     rax, rsp
0x180016630  mov     [rbp+7E0h+var_30], rax
0x180016637  mov     rdi, r8
0x18001663a  mov     rsi, rdx
0x18001663d  mov     rbx, rcx
0x180016640  mov     rcx, [r8]; void *
0x180016643  call    ?Free@HeapAllocator@@SAXPEAX@Z; HeapAllocator::Free(void *)
0x180016648  mov     qword ptr [rdi], 0
0x18001664f  mov     qword ptr [rdi+8], 0
0x180016657  mov     [rsp+8E0h+var_8A0], 0
0x180016660  mov     [rsp+8E0h+var_8B0], 0
0x180016668  mov     [rsp+8E0h+var_8A8], 0
0x180016671  lea     rdx, DebugInfoEvent
0x180016678  mov     rcx, cs:eaphost_Context
0x18001667f  call    cs:__imp_EtwEventEnabled
0x180016685  test    al, al
0x180016687  jz      short loc_1800166C2
0x180016689  lea     r8, aEappeergetuico_0; "EapPeerGetUIContext Entry"
0x180016690  mov     edx, 800h; unsigned __int64
0x180016695  lea     rcx, [rbp+7E0h+var_830]; char *
0x180016699  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001669e  test    eax, eax
0x1800166a0  js      short loc_1800166C2
0x1800166a2  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800166a9  jge     short loc_1800166C2
0x1800166ab  lea     r8, [rbp+7E0h+var_830]
0x1800166af  lea     rdx, DebugInfoEvent
0x1800166b6  lea     rcx, eaphost_Context
0x1800166bd  call    McTemplateU0s_EtwEventWriteTransfer
0x1800166c2  lea     r12, WPP_GLOBAL_Control
0x1800166c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800166d0  cmp     rcx, r12
0x1800166d3  jz      short loc_1800166F0
0x1800166d5  test    byte ptr [rcx+1Ch], 4
0x1800166d9  jz      short loc_1800166F0
0x1800166db  mov     edx, 1Eh
0x1800166e0  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800166e7  mov     rcx, [rcx+10h]
0x1800166eb  call    WPP_SF_
0x1800166f0  lea     r9, [rsp+8E0h+var_8A8]
0x1800166f5  lea     r8, [rsp+8E0h+var_8A0]
0x1800166fa  lea     rdx, [rsp+8E0h+var_8B0]
0x1800166ff  mov     rcx, [rsi+40h]
0x180016703  mov     rax, [rbx+178h]
0x18001670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001670f  test    eax, eax
0x180016711  jz      short loc_180016749
0x180016713  mov     r8d, eax; unsigned int
0x180016716  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x18001671b  lea     rcx, [rsp+8E0h+var_890]; this
0x180016720  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016725  nop
0x180016726  mov     rcx, [rsp+8E0h+var_8A8]
0x18001672b  mov     rax, [rbx+1A8h]
0x180016732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016737  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x18001673c  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x180016743  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
0x180016749  mov     eax, [rsp+8E0h+var_8B0]
0x18001674d  test    eax, eax
0x18001674f  jz      loc_180016802
0x180016755  mov     r8, [rsp+8E0h+var_8A0]
0x18001675a  test    r8, r8
0x18001675d  jz      loc_180016802
0x180016763  mov     edx, eax
0x180016765  mov     rcx, rdi
0x180016768  call    ?Assign@?$TempBuffer@$0A@@@QEAAX_KPEBX@Z; TempBuffer<0>::Assign(unsigned __int64,void const *)
0x18001676d  lea     rdx, DebugInfoEvent
0x180016774  mov     rcx, cs:eaphost_Context
0x18001677b  call    cs:__imp_EtwEventEnabled
0x180016781  test    al, al
0x180016783  jz      short loc_1800167BE
0x180016785  lea     r8, aEappeergetuico; "EapPeerGetUIContext Exit"
0x18001678c  mov     edx, 800h; unsigned __int64
0x180016791  lea     rcx, [rbp+7E0h+var_830]; char *
0x180016795  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18001679a  test    eax, eax
0x18001679c  js      short loc_1800167BE
0x18001679e  cmp     cs:Microsoft_Windows_EapHostEnableBits, 0
0x1800167a5  jge     short loc_1800167BE
0x1800167a7  lea     r8, [rbp+7E0h+var_830]
0x1800167ab  lea     rdx, DebugInfoEvent
0x1800167b2  lea     rcx, eaphost_Context
0x1800167b9  call    McTemplateU0s_EtwEventWriteTransfer
0x1800167be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800167c5  cmp     rcx, r12
0x1800167c8  jz      short loc_1800167E5
0x1800167ca  test    byte ptr [rcx+1Ch], 4
0x1800167ce  jz      short loc_1800167E5
0x1800167d0  mov     edx, 1Fh
0x1800167d5  lea     r8, WPP_c4aba25df3463aec091a109e3cb7d988_Traceguids
0x1800167dc  mov     rcx, [rcx+10h]
0x1800167e0  call    WPP_SF_
0x1800167e5  mov     rcx, [rbp+7E0h+var_30]
0x1800167ec  xor     rcx, rsp; StackCookie
0x1800167ef  call    __security_check_cookie
0x1800167f4  add     rsp, 8C0h
0x1800167fb  pop     r12
0x1800167fd  pop     rdi
0x1800167fe  pop     rsi
0x1800167ff  pop     rbx
0x180016800  pop     rbp
0x180016801  retn
0x180016802  mov     r8d, 0Dh; unsigned int
0x180016808  mov     rdx, [rsp+8E0h+var_8A8]; struct _EAP_ERROR *
0x18001680d  lea     rcx, [rsp+8E0h+var_890]; this
0x180016812  call    ??0EapError@EapHost@@QEAA@PEBU_EAP_ERROR@@K@Z; EapHost::EapError::EapError(_EAP_ERROR const *,ulong)
0x180016817  nop
0x180016818  mov     rcx, [rsp+8E0h+var_8A8]
0x18001681d  test    rcx, rcx
0x180016820  jz      short loc_18001682E
0x180016822  mov     rax, [rbx+1A8h]
0x180016829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682e  lea     r8, [rsp+8E0h+var_890]; struct EapHost::EapError *
0x180016833  lea     rcx, aEappeergetuico_1; "EapPeerGetUIContext"
0x18001683a  call    ?Throw@EapException@EapHost@@SAXPEB_W0AEBVEapError@2@@Z; EapHost::EapException::Throw(wchar_t const *,wchar_t const *,EapHost::EapError const &)
```
