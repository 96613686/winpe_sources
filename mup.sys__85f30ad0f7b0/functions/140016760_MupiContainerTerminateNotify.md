# MupiContainerTerminateNotify

- ea: `0x140016760`
- end: `0x140016851`
- name: `MupiContainerTerminateNotify`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x140002700`
- `0x140010534`
- `0x140016760`
- `0x14001dacc`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140016807`
- `ntoskrnl!RtlInitUnicodeString` at `0x140016807`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400167ec`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1400167ec`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140016827`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x140016827`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016818`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x140016818`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001678f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001678f`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016779`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016779`

## pseudocode

```c
void __fastcall MupiContainerTerminateNotify(__int64 a1)
{
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v3; // rbx
  __int64 UncCachePrefixTable; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  __int64 v6; // [rsp+58h] [rbp+10h] BYREF

  v6 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(ContainerMonitor);
  PsGetPermanentSiloContext(a1, SiloMonitorContextSlot, &v6);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids, a1, v6);
  }
  if ( v6 )
  {
    DestinationString = 0;
    v3 = PsAttachSiloToCurrentThread(a1);
    RtlInitUnicodeString(&DestinationString, L"\\??\\UNC");
    IoDeleteSymbolicLink(&DestinationString);
    PsDetachSiloFromCurrentThread(v3);
    UncCachePrefixTable = MupGetUncCachePrefixTable(v6);
    MupFlushKnownPrefixTable(UncCachePrefixTable, 0, 1);
  }
}

```

## disassembly

```asm
0x140016760  push    rbx
0x140016762  sub     rsp, 40h
0x140016766  mov     rbx, rcx
0x140016769  mov     [rsp+48h+arg_8], 0
0x140016772  mov     rcx, cs:ContainerMonitor
0x140016779  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140016780  nop     dword ptr [rax+rax+00h]
0x140016785  lea     r8, [rsp+48h+arg_8]
0x14001678a  mov     rcx, rbx
0x14001678d  mov     edx, eax
0x14001678f  call    cs:__imp_PsGetPermanentSiloContext
0x140016796  nop     dword ptr [rax+rax+00h]
0x14001679b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400167a2  lea     rax, WPP_GLOBAL_Control
0x1400167a9  cmp     rcx, rax
0x1400167ac  jz      short loc_1400167D9
0x1400167ae  test    dword ptr [rcx+2Ch], 2000000h
0x1400167b5  jz      short loc_1400167D9
0x1400167b7  mov     rax, [rsp+48h+arg_8]
0x1400167bc  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x1400167c3  mov     rcx, [rcx+18h]
0x1400167c7  mov     edx, 0Dh
0x1400167cc  mov     r9, rbx
0x1400167cf  mov     [rsp+48h+var_28], rax
0x1400167d4  call    WPP_SF_qq
0x1400167d9  cmp     [rsp+48h+arg_8], 0
0x1400167df  jz      short loc_14001684A
0x1400167e1  xorps   xmm0, xmm0
0x1400167e4  mov     rcx, rbx
0x1400167e7  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x1400167ec  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400167f3  nop     dword ptr [rax+rax+00h]
0x1400167f8  lea     rdx, aUnc; "\\??\\UNC"
0x1400167ff  mov     rbx, rax
0x140016802  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x140016807  call    cs:__imp_RtlInitUnicodeString
0x14001680e  nop     dword ptr [rax+rax+00h]
0x140016813  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x140016818  call    cs:__imp_IoDeleteSymbolicLink
0x14001681f  nop     dword ptr [rax+rax+00h]
0x140016824  mov     rcx, rbx
0x140016827  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001682e  nop     dword ptr [rax+rax+00h]
0x140016833  mov     rcx, [rsp+48h+arg_8]
0x140016838  call    MupGetUncCachePrefixTable
0x14001683d  mov     rcx, rax
0x140016840  mov     r8b, 1
0x140016843  xor     edx, edx
0x140016845  call    MupFlushKnownPrefixTable
0x14001684a  add     rsp, 40h
0x14001684e  pop     rbx
0x14001684f  retn
```
