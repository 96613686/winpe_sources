# DfscpContainerTerminateNotify

- ea: `0x14001a4a0`
- end: `0x14001a620`
- name: `DfscpContainerTerminateNotify`
- size: `384`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x140001744`
- `0x140002fcc`
- `0x14001a4a0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14001a54b`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a54b`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a55c`
- `ntoskrnl!IoDeleteSymbolicLink` at `0x14001a55c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a530`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001a530`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a56b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001a56b`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001a4b9`
- `ntoskrnl!PsGetSiloMonitorContextSlot` at `0x14001a4b9`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001a4cf`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x14001a4cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a5da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001a5da`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a5ce`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001a5ce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a58c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14001a58c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a577`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001a577`

## pseudocode

```c
void __fastcall DfscpContainerTerminateNotify(__int64 a1)
{
  unsigned int SiloMonitorContextSlot; // eax
  __int64 v3; // rbx
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  struct _UNICODE_PREFIX_TABLE *v8; // rcx
  struct _UNICODE_PREFIX_TABLE *v9; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  _QWORD *v11; // [rsp+58h] [rbp+10h] BYREF

  v11 = 0;
  SiloMonitorContextSlot = PsGetSiloMonitorContextSlot(qword_14000C7F8);
  PsGetPermanentSiloContext(a1, SiloMonitorContextSlot, &v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200000) != 0 )
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids, a1, v11);
  if ( v11 )
  {
    DestinationString = 0;
    v3 = PsAttachSiloToCurrentThread(a1);
    RtlInitUnicodeString(&DestinationString, L"\\Dfs");
    IoDeleteSymbolicLink(&DestinationString);
    PsDetachSiloFromCurrentThread(v3);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement, 1u);
    v4 = *v11;
    if ( (_QWORD *)*v11 != v11 )
    {
      if ( *(_QWORD **)(v4 + 8) != v11 || (v5 = (_QWORD *)v11[1], (_QWORD *)*v5 != v11) )
        __fastfail(3u);
      *v5 = v4;
      *(_QWORD *)(v4 + 8) = v5;
      v6 = v11;
      v11[1] = v11;
      *v6 = v6;
    }
    ExReleaseResourceLite((PERESOURCE)&WPP_MAIN_CB.AlignmentRequirement);
    KeLeaveCriticalRegion();
    v7 = v11;
    v8 = (struct _UNICODE_PREFIX_TABLE *)v11[16];
    if ( v8 )
    {
      DfscCachePurge(v8);
      v7 = v11;
    }
    v9 = (struct _UNICODE_PREFIX_TABLE *)v7[17];
    if ( v9 )
      DfscCachePurge(v9);
  }
}

```

## disassembly

```asm
0x14001a4a0  push    rbx
0x14001a4a2  sub     rsp, 40h
0x14001a4a6  mov     rbx, rcx
0x14001a4a9  mov     [rsp+48h+arg_8], 0
0x14001a4b2  mov     rcx, cs:qword_14000C7F8
0x14001a4b9  call    cs:__imp_PsGetSiloMonitorContextSlot
0x14001a4c0  nop     dword ptr [rax+rax+00h]
0x14001a4c5  lea     r8, [rsp+48h+arg_8]
0x14001a4ca  mov     rcx, rbx
0x14001a4cd  mov     edx, eax
0x14001a4cf  call    cs:__imp_PsGetPermanentSiloContext
0x14001a4d6  nop     dword ptr [rax+rax+00h]
0x14001a4db  mov     rcx, cs:WPP_GLOBAL_Control
0x14001a4e2  lea     rax, WPP_GLOBAL_Control
0x14001a4e9  cmp     rcx, rax
0x14001a4ec  jz      short loc_14001A519
0x14001a4ee  test    dword ptr [rcx+2Ch], 200000h
0x14001a4f5  jz      short loc_14001A519
0x14001a4f7  mov     rax, [rsp+48h+arg_8]
0x14001a4fc  lea     r8, WPP_32bb75f7aa823fb724b87f7e3287c67a_Traceguids
0x14001a503  mov     rcx, [rcx+18h]
0x14001a507  mov     edx, 14h
0x14001a50c  mov     r9, rbx
0x14001a50f  mov     [rsp+48h+var_28], rax
0x14001a514  call    WPP_SF_qq
0x14001a519  cmp     [rsp+48h+arg_8], 0
0x14001a51f  jz      loc_14001A612
0x14001a525  xorps   xmm0, xmm0
0x14001a528  mov     rcx, rbx
0x14001a52b  movups  xmmword ptr [rsp+48h+DestinationString.Length], xmm0
0x14001a530  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001a537  nop     dword ptr [rax+rax+00h]
0x14001a53c  lea     rdx, aDfs; "\\Dfs"
0x14001a543  mov     rbx, rax
0x14001a546  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001a54b  call    cs:__imp_RtlInitUnicodeString
0x14001a552  nop     dword ptr [rax+rax+00h]
0x14001a557  lea     rcx, [rsp+48h+DestinationString]; SymbolicLinkName
0x14001a55c  call    cs:__imp_IoDeleteSymbolicLink
0x14001a563  nop     dword ptr [rax+rax+00h]
0x14001a568  mov     rcx, rbx
0x14001a56b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001a572  nop     dword ptr [rax+rax+00h]
0x14001a577  call    cs:__imp_KeEnterCriticalRegion
0x14001a57e  nop     dword ptr [rax+rax+00h]
0x14001a583  mov     dl, 1; Wait
0x14001a585  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001a58c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14001a593  nop     dword ptr [rax+rax+00h]
0x14001a598  mov     rax, [rsp+48h+arg_8]
0x14001a59d  mov     rdx, [rax]
0x14001a5a0  cmp     rdx, rax
0x14001a5a3  jz      short loc_14001A5C7
0x14001a5a5  cmp     [rdx+8], rax
0x14001a5a9  jnz     short loc_14001A619
0x14001a5ab  mov     rcx, [rax+8]
0x14001a5af  cmp     [rcx], rax
0x14001a5b2  jnz     short loc_14001A619
0x14001a5b4  mov     [rcx], rdx
0x14001a5b7  mov     [rdx+8], rcx
0x14001a5bb  mov     rax, [rsp+48h+arg_8]
0x14001a5c0  mov     [rax+8], rax
0x14001a5c4  mov     [rax], rax
0x14001a5c7  lea     rcx, WPP_MAIN_CB.AlignmentRequirement; Resource
0x14001a5ce  call    cs:__imp_ExReleaseResourceLite
0x14001a5d5  nop     dword ptr [rax+rax+00h]
0x14001a5da  call    cs:__imp_KeLeaveCriticalRegion
0x14001a5e1  nop     dword ptr [rax+rax+00h]
0x14001a5e6  mov     rax, [rsp+48h+arg_8]
0x14001a5eb  mov     rcx, [rax+80h]; PrefixTable
0x14001a5f2  test    rcx, rcx
0x14001a5f5  jz      short loc_14001A601
0x14001a5f7  call    DfscCachePurge
0x14001a5fc  mov     rax, [rsp+48h+arg_8]
0x14001a601  mov     rcx, [rax+88h]; PrefixTable
0x14001a608  test    rcx, rcx
0x14001a60b  jz      short loc_14001A612
0x14001a60d  call    DfscCachePurge
0x14001a612  add     rsp, 40h
0x14001a616  pop     rbx
0x14001a617  retn
0x14001a619  mov     ecx, 3
0x14001a61e  int     29h; Win8: RtlFailFast(ecx)
```
