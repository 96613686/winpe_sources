# MupiContainerTerminateNotify

- ea: `0x140016710`
- end: `0x140016801`
- name: `MupiContainerTerminateNotify`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path`

## callees

- `0x140002700`
- `0x140010534`
- `0x140016710`
- `0x14001da7c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400167b7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400167b7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001679c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001679c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400167d7`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1400167d7`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400167c8`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x1400167c8`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001673f`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001673f`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016729`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x140016729`

## pseudocode

```c
PDEVICE_OBJECT *__fastcall MupiContainerTerminateNotify(__int64 a1)
{
  unsigned int SiloMonitorContextSlot; // eax
  PDEVICE_OBJECT *result; // rax
  __int64 v4; // rbx
  __int64 UncCachePrefixTable; // rax
  __int64 v6; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  __int64 v8; // [rsp+58h] [rbp+10h] BYREF

  v8 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(ContainerMonitor);
  PsGetPermanentSiloContext(a1, SiloMonitorContextSlot, &v8);
  result = &WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000000) != 0 )
  {
    result = (PDEVICE_OBJECT *)WPP_SF_qq(
                                 WPP_GLOBAL_Control->AttachedDevice,
                                 13,
                                 WPP_c898274d75623dfd801520d1a3be50ef_Traceguids,
                                 a1,
                                 v8);
  }
  if ( v8 )
  {
    DestinationString = 0;
    v4 = PsAttachSiloToCurrentThread(a1);
    RtlInitUnicodeString(&DestinationString, L"\\??\\UNC");
    IoDeleteSymbolicLink(&DestinationString);
    PsDetachSiloFromCurrentThread(v4);
    UncCachePrefixTable = MupGetUncCachePrefixTable(v8);
    LOBYTE(v6) = 1;
    return (PDEVICE_OBJECT *)MupFlushKnownPrefixTable(UncCachePrefixTable, 0, v6);
  }
  return result;
}

```

## disassembly

```asm
0x140016710  push    rbx
0x140016712  sub     rsp, 40h
0x140016716  mov     rbx, rcx
0x140016719  mov     [rsp+48h+arg_8], 0
0x140016722  mov     rcx, cs:ContainerMonitor
0x140016729  call    cs:__imp_PsGetSiloMonitorContextSlot
0x140016730  nop     dword ptr [rax+rax+00h]
0x140016735  lea     r8, [rsp+48h+arg_8]
0x14001673a  mov     rcx, rbx
0x14001673d  mov     edx, eax
0x14001673f  call    cs:__imp_PsGetPermanentSiloContext
0x140016746  nop     dword ptr [rax+rax+00h]
0x14001674b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016752  lea     rax, WPP_GLOBAL_Control
0x140016759  cmp     rcx, rax
0x14001675c  jz      short loc_140016789
0x14001675e  test    dword ptr [rcx+2Ch], 2000000h
0x140016765  jz      short loc_140016789
0x140016767  mov     rax, [rsp+48h+arg_8]
0x14001676c  lea     r8, WPP_c898274d75623dfd801520d1a3be50ef_Traceguids
0x140016773  mov     rcx, [rcx+18h]
0x140016777  mov     edx, 0Dh
0x14001677c  mov     r9, rbx
0x14001677f  mov     [rsp+48h+var_28], rax
0x140016784  call    WPP_SF_qq
0x140016789  cmp     [rsp+48h+arg_8], 0
0x14001678f  jz      short loc_1400167FA
0x140016791  xorps   xmm0, xmm0
0x140016794  mov     rcx, rbx
0x140016797  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001679c  call    cs:__imp_PsAttachSiloToCurrentThread
0x1400167a3  nop     dword ptr [rax+rax+00h]
0x1400167a8  lea     rdx, aUnc; "\\??\\UNC"
0x1400167af  mov     rbx, rax
0x1400167b2  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x1400167b7  call    cs:__imp_RtlInitUnicodeString
0x1400167be  nop     dword ptr [rax+rax+00h]
0x1400167c3  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x1400167c8  call    cs:__imp_IoDeleteSymbolicLink
0x1400167cf  nop     dword ptr [rax+rax+00h]
0x1400167d4  mov     rcx, rbx
0x1400167d7  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1400167de  nop     dword ptr [rax+rax+00h]
0x1400167e3  mov     rcx, [rsp+48h+arg_8]
0x1400167e8  call    MupGetUncCachePrefixTable
0x1400167ed  mov     rcx, rax
0x1400167f0  mov     r8b, 1
0x1400167f3  xor     edx, edx
0x1400167f5  call    MupFlushKnownPrefixTable
0x1400167fa  add     rsp, 40h
0x1400167fe  pop     rbx
0x1400167ff  retn
```
