# MupiContainerCreateNotify

- ea: `0x140016540`
- end: `0x140016752`
- name: `MupiContainerCreateNotify`
- size: `530`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x140002614`
- `0x140002754`
- `0x140002e74`
- `0x140016540`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001660f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016626`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001660f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016626`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400165f5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400166a4`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400165f5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400166a4`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001665b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400166c6`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001665b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400166c6`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x1400165e6`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x1400165e6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016636`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400166b7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016636`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400166b7`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001664a`
- `ntoskrnl!IoCreateSymbolicLink` at `0x14001664a`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016675`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016675`
- `ntoskrnl!PsCreateSiloContext` at `0x1400165b9`
- `ntoskrnl!PsCreateSiloContext` at `0x1400165b9`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001668a`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001668a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140016703`
- `ntoskrnl!PsDereferenceSiloContext` at `0x140016703`

## pseudocode

```c
__int64 __fastcall MupiContainerCreateNotify(__int64 a1)
{
  NTSTATUS v2; // eax
  NTSTATUS inserted; // edi
  PUNICODE_PREFIX_TABLE v4; // rax
  char v5; // r14
  __int64 v6; // rbx
  bool v7; // zf
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v9; // rbx
  struct _UNICODE_STRING SymbolicLinkName; // [rsp+30h] [rbp-28h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-18h] BYREF
  PUNICODE_PREFIX_TABLE PrefixTable; // [rsp+98h] [rbp+40h] BYREF

  PrefixTable = 0;
  DestinationString = 0;
  SymbolicLinkName = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids, a1);
  }
  v2 = PsCreateSiloContext(a1, 24, 1, MupiContainerCleanupNotify, &PrefixTable);
  inserted = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
    {
      WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids, a1, v2);
    }
  }
  else
  {
    v4 = PrefixTable;
    v5 = 0;
    *(_OWORD *)&PrefixTable->NodeTypeCode = 0;
    v4->LastNextEntry = 0;
    RtlInitializeUnicodePrefix(PrefixTable);
    v6 = PsAttachSiloToCurrentThread(a1);
    RtlInitUnicodeString(&DestinationString, L"\\Device\\Mup");
    RtlInitUnicodeString(&SymbolicLinkName, L"\\??\\UNC");
    IoDeleteSymbolicLink(&SymbolicLinkName);
    inserted = IoCreateSymbolicLink(&SymbolicLinkName, &DestinationString);
    PsDetachSiloFromCurrentThread(v6);
    v7 = inserted == 0;
    if ( inserted >= 0 )
    {
      v5 = 1;
      SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(ContainerMonitor);
      inserted = PsInsertPermanentSiloContext(a1, SiloMonitorContextSlot, PrefixTable);
      v7 = inserted == 0;
    }
    if ( !v7 )
    {
      if ( v5 )
      {
        v9 = PsAttachSiloToCurrentThread(a1);
        IoDeleteSymbolicLink(&SymbolicLinkName);
        PsDetachSiloFromCurrentThread(v9);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000000) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          11,
          WPP_c898274d75623dfd801520d1a3be50ef_Traceguids,
          (unsigned int)inserted);
      }
    }
    PsDereferenceSiloContext(PrefixTable);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x140016540  push    rbp
0x140016542  push    rbx
0x140016543  push    rsi
0x140016544  push    rdi
0x140016545  push    r14
0x140016547  push    r15
0x140016549  mov     rbp, rsp
0x14001654c  sub     rsp, 58h
0x140016550  xorps   xmm0, xmm0
0x140016553  mov     [rbp+PrefixTable], 0
0x14001655b  xorps   xmm1, xmm1
0x14001655e  mov     rsi, rcx
0x140016561  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140016565  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm1
0x140016569  mov     rcx, cs:WPP_GLOBAL_Control
0x140016570  lea     r15, WPP_GLOBAL_Control
0x140016577  cmp     rcx, r15
0x14001657a  jz      short loc_14001659D
0x14001657c  test    dword ptr [rcx+2Ch], 2000000h
0x140016583  jz      short loc_14001659D
0x140016585  mov     rcx, [rcx+18h]
0x140016589  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x140016590  mov     edx, 0Ah
0x140016595  mov     r9, rsi
0x140016598  call    WPP_SF_q
0x14001659d  mov     edx, 18h
0x1400165a2  lea     rax, [rbp+PrefixTable]
0x1400165a6  lea     r9, MupiContainerCleanupNotify
0x1400165ad  mov     [rsp+58h+var_38], rax
0x1400165b2  mov     rcx, rsi
0x1400165b5  lea     r8d, [rdx-17h]
0x1400165b9  call    cs:__imp_PsCreateSiloContext
0x1400165c0  nop     dword ptr [rax+rax+00h]
0x1400165c5  mov     edi, eax
0x1400165c7  test    eax, eax
0x1400165c9  jnz     loc_140016711
0x1400165cf  mov     rax, [rbp+PrefixTable]
0x1400165d3  xor     ecx, ecx
0x1400165d5  xorps   xmm0, xmm0
0x1400165d8  xor     r14b, r14b
0x1400165db  movups  xmmword ptr [rax], xmm0
0x1400165de  mov     [rax+10h], rcx
0x1400165e2  mov     rcx, [rbp+PrefixTable]; PrefixTable
0x1400165e6  call    cs:__imp_RtlInitializeUnicodePrefix
0x1400165ed  nop     dword ptr [rax+rax+00h]
0x1400165f2  mov     rcx, rsi
0x1400165f5  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400165fc  nop     dword ptr [rax+rax+00h]
0x140016601  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x140016608  mov     rbx, rax
0x14001660b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001660f  call    cs:__imp_RtlInitUnicodeString
0x140016616  nop     dword ptr [rax+rax+00h]
0x14001661b  lea     rdx, aUnc; "\\??\\UNC"
0x140016622  lea     rcx, [rbp+SymbolicLinkName]; DestinationString
0x140016626  call    cs:__imp_RtlInitUnicodeString
0x14001662d  nop     dword ptr [rax+rax+00h]
0x140016632  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x140016636  call    cs:__imp_IoDeleteSymbolicLink
0x14001663d  nop     dword ptr [rax+rax+00h]
0x140016642  lea     rdx, [rbp+DestinationString]; DeviceName
0x140016646  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x14001664a  call    cs:__imp_IoCreateSymbolicLink
0x140016651  nop     dword ptr [rax+rax+00h]
0x140016656  mov     rcx, rbx
0x140016659  mov     edi, eax
0x14001665b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140016662  nop     dword ptr [rax+rax+00h]
0x140016667  test    edi, edi
0x140016669  js      short loc_14001669A
0x14001666b  mov     rcx, cs:ContainerMonitor
0x140016672  mov     r14b, 1
0x140016675  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001667c  nop     dword ptr [rax+rax+00h]
0x140016681  mov     r8, [rbp+PrefixTable]
0x140016685  mov     rcx, rsi
0x140016688  mov     edx, eax
0x14001668a  call    cs:__imp_PsInsertPermanentSiloContext
0x140016691  nop     dword ptr [rax+rax+00h]
0x140016696  mov     edi, eax
0x140016698  test    eax, eax
0x14001669a  jz      short loc_1400166FF
0x14001669c  test    r14b, r14b
0x14001669f  jz      short loc_1400166D2
0x1400166a1  mov     rcx, rsi
0x1400166a4  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400166ab  nop     dword ptr [rax+rax+00h]
0x1400166b0  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400166b4  mov     rbx, rax
0x1400166b7  call    cs:__imp_IoDeleteSymbolicLink
0x1400166be  nop     dword ptr [rax+rax+00h]
0x1400166c3  mov     rcx, rbx
0x1400166c6  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400166cd  nop     dword ptr [rax+rax+00h]
0x1400166d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166d9  cmp     rcx, r15
0x1400166dc  jz      short loc_1400166FF
0x1400166de  test    dword ptr [rcx+2Ch], 1000000h
0x1400166e5  jz      short loc_1400166FF
0x1400166e7  mov     rcx, [rcx+18h]
0x1400166eb  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x1400166f2  mov     edx, 0Bh
0x1400166f7  mov     r9d, edi
0x1400166fa  call    WPP_SF_d
0x1400166ff  mov     rcx, [rbp+PrefixTable]
0x140016703  call    cs:__imp_PsDereferenceSiloContext
0x14001670a  nop     dword ptr [rax+rax+00h]
0x14001670f  jmp     short loc_140016742
0x140016711  mov     rcx, cs:WPP_GLOBAL_Control
0x140016718  cmp     rcx, r15
0x14001671b  jz      short loc_140016742
0x14001671d  test    dword ptr [rcx+2Ch], 1000000h
0x140016724  jz      short loc_140016742
0x140016726  mov     rcx, [rcx+18h]
0x14001672a  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x140016731  mov     edx, 0Ch
0x140016736  mov     dword ptr [rsp+58h+var_38], eax
0x14001673a  mov     r9, rsi
0x14001673d  call    WPP_SF_qD
0x140016742  mov     eax, edi
0x140016744  add     rsp, 58h
0x140016748  pop     r15
0x14001674a  pop     r14
0x14001674c  pop     rdi
0x14001674d  pop     rsi
0x14001674e  pop     rbx
0x14001674f  pop     rbp
0x140016750  retn
```
