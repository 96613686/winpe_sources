# MupiContainerCreateNotify

- ea: `0x1400164f0`
- end: `0x140016702`
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
- `0x1400164f0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400165bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400165d6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400165bf`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400165d6`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400165a5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140016654`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400165a5`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x140016654`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001660b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140016676`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001660b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140016676`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140016596`
- `ntoskrnl!RtlInitializeUnicodePrefix` at `0x140016596`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400165e6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016667`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400165e6`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016667`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400165fa`
- `ntoskrnl!IoCreateSymbolicLink` at `0x1400165fa`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016625`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016625`
- `ntoskrnl!PsCreateSiloContext` at `0x140016569`
- `ntoskrnl!PsCreateSiloContext` at `0x140016569`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001663a`
- `ntoskrnl!PsInsertPermanentSiloContext` at `0x14001663a`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400166b3`
- `ntoskrnl!PsDereferenceSiloContext` at `0x1400166b3`

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
0x1400164f0  push    rbp
0x1400164f2  push    rbx
0x1400164f3  push    rsi
0x1400164f4  push    rdi
0x1400164f5  push    r14
0x1400164f7  push    r15
0x1400164f9  mov     rbp, rsp
0x1400164fc  sub     rsp, 58h
0x140016500  xorps   xmm0, xmm0
0x140016503  mov     [rbp+PrefixTable], 0
0x14001650b  xorps   xmm1, xmm1
0x14001650e  mov     rsi, rcx
0x140016511  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140016515  movups  xmmword ptr [rbp+SymbolicLinkName.Length], xmm1
0x140016519  mov     rcx, cs:WPP_GLOBAL_Control
0x140016520  lea     r15, WPP_GLOBAL_Control
0x140016527  cmp     rcx, r15
0x14001652a  jz      short loc_14001654D
0x14001652c  test    dword ptr [rcx+2Ch], 2000000h
0x140016533  jz      short loc_14001654D
0x140016535  mov     rcx, [rcx+18h]
0x140016539  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x140016540  mov     edx, 0Ah
0x140016545  mov     r9, rsi
0x140016548  call    WPP_SF_q
0x14001654d  mov     edx, 18h
0x140016552  lea     rax, [rbp+PrefixTable]
0x140016556  lea     r9, MupiContainerCleanupNotify
0x14001655d  mov     [rsp+58h+var_38], rax
0x140016562  mov     rcx, rsi
0x140016565  lea     r8d, [rdx-17h]
0x140016569  call    cs:__imp_PsCreateSiloContext
0x140016570  nop     dword ptr [rax+rax+00h]
0x140016575  mov     edi, eax
0x140016577  test    eax, eax
0x140016579  jnz     loc_1400166C1
0x14001657f  mov     rax, [rbp+PrefixTable]
0x140016583  xor     ecx, ecx
0x140016585  xorps   xmm0, xmm0
0x140016588  xor     r14b, r14b
0x14001658b  movups  xmmword ptr [rax], xmm0
0x14001658e  mov     [rax+10h], rcx
0x140016592  mov     rcx, [rbp+PrefixTable]; PrefixTable
0x140016596  call    cs:__imp_RtlInitializeUnicodePrefix
0x14001659d  nop     dword ptr [rax+rax+00h]
0x1400165a2  mov     rcx, rsi
0x1400165a5  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400165ac  nop     dword ptr [rax+rax+00h]
0x1400165b1  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x1400165b8  mov     rbx, rax
0x1400165bb  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400165bf  call    cs:__imp_RtlInitUnicodeString
0x1400165c6  nop     dword ptr [rax+rax+00h]
0x1400165cb  lea     rdx, aUnc; "\\??\\UNC"
0x1400165d2  lea     rcx, [rbp+SymbolicLinkName]; DestinationString
0x1400165d6  call    cs:__imp_RtlInitUnicodeString
0x1400165dd  nop     dword ptr [rax+rax+00h]
0x1400165e2  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400165e6  call    cs:__imp_IoDeleteSymbolicLink
0x1400165ed  nop     dword ptr [rax+rax+00h]
0x1400165f2  lea     rdx, [rbp+DestinationString]; DeviceName
0x1400165f6  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x1400165fa  call    cs:__imp_IoCreateSymbolicLink
0x140016601  nop     dword ptr [rax+rax+00h]
0x140016606  mov     rcx, rbx
0x140016609  mov     edi, eax
0x14001660b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x140016612  nop     dword ptr [rax+rax+00h]
0x140016617  test    edi, edi
0x140016619  js      short loc_14001664A
0x14001661b  mov     rcx, cs:ContainerMonitor
0x140016622  mov     r14b, 1
0x140016625  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001662c  nop     dword ptr [rax+rax+00h]
0x140016631  mov     r8, [rbp+PrefixTable]
0x140016635  mov     rcx, rsi
0x140016638  mov     edx, eax
0x14001663a  call    cs:__imp_PsInsertPermanentSiloContext
0x140016641  nop     dword ptr [rax+rax+00h]
0x140016646  mov     edi, eax
0x140016648  test    eax, eax
0x14001664a  jz      short loc_1400166AF
0x14001664c  test    r14b, r14b
0x14001664f  jz      short loc_140016682
0x140016651  mov     rcx, rsi
0x140016654  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001665b  nop     dword ptr [rax+rax+00h]
0x140016660  lea     rcx, [rbp+SymbolicLinkName]; SymbolicLinkName
0x140016664  mov     rbx, rax
0x140016667  call    cs:__imp_IoDeleteSymbolicLink
0x14001666e  nop     dword ptr [rax+rax+00h]
0x140016673  mov     rcx, rbx
0x140016676  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001667d  nop     dword ptr [rax+rax+00h]
0x140016682  mov     rcx, cs:WPP_GLOBAL_Control
0x140016689  cmp     rcx, r15
0x14001668c  jz      short loc_1400166AF
0x14001668e  test    dword ptr [rcx+2Ch], 1000000h
0x140016695  jz      short loc_1400166AF
0x140016697  mov     rcx, [rcx+18h]
0x14001669b  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x1400166a2  mov     edx, 0Bh
0x1400166a7  mov     r9d, edi
0x1400166aa  call    WPP_SF_d
0x1400166af  mov     rcx, [rbp+PrefixTable]
0x1400166b3  call    cs:__imp_PsDereferenceSiloContext
0x1400166ba  nop     dword ptr [rax+rax+00h]
0x1400166bf  jmp     short loc_1400166F2
0x1400166c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400166c8  cmp     rcx, r15
0x1400166cb  jz      short loc_1400166F2
0x1400166cd  test    dword ptr [rcx+2Ch], 1000000h
0x1400166d4  jz      short loc_1400166F2
0x1400166d6  mov     rcx, [rcx+18h]
0x1400166da  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x1400166e1  mov     edx, 0Ch
0x1400166e6  mov     dword ptr [rsp+58h+var_38], eax
0x1400166ea  mov     r9, rsi
0x1400166ed  call    WPP_SF_qD
0x1400166f2  mov     eax, edi
0x1400166f4  add     rsp, 58h
0x1400166f8  pop     r15
0x1400166fa  pop     r14
0x1400166fc  pop     rdi
0x1400166fd  pop     rsi
0x1400166fe  pop     rbx
0x1400166ff  pop     rbp
0x140016700  retn
```
