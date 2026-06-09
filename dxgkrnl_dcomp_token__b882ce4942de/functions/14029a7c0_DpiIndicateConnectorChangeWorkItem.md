# DpiIndicateConnectorChangeWorkItem

- ea: `0x14029a7c0`
- end: `0x14029a9af`
- name: `DpiIndicateConnectorChangeWorkItem`
- size: `495`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140022264`
- `0x14005ad60`
- `0x140265578`
- `0x14029a7c0`
- `0x14030b6a4`
- `0x1403676e0`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a824`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a8bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a8f1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a824`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a8bf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14029a8f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a8a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a93e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a96f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a8a1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a93e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14029a96f`
- `ntoskrnl!IoFreeWorkItem` at `0x14029a997`
- `ntoskrnl!IoFreeWorkItem` at `0x14029a997`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14029a84a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14029a8e5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14029a84a`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14029a8e5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029a909`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14029a909`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a895`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a932`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a963`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a895`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a932`
- `ntoskrnl!ExReleaseResourceLite` at `0x14029a963`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14029a7f1`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14029a7f1`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14029a988`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14029a988`
- `watchdog!WdLogSingleEntry1` at `0x14029a809`
- `watchdog!WdLogSingleEntry1` at `0x14029a809`

## pseudocode

```c
void __fastcall DpiIndicateConnectorChangeWorkItem(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v3; // rdi
  int v5; // r14d
  unsigned int ConsoleSessionId; // ebx

  v3 = IoObject[8];
  v5 = (int)IoObject;
  if ( IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 64), IoWorkItem, File, 1u, 0x20u) >= 0 )
  {
    KeEnterCriticalRegion();
    if ( *(_BYTE *)(v3 + 484) )
      DpiCheckForOutstandingD3Requests(v3);
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v3 + 168), 1u);
    if ( *(_BYTE *)(v3 + 1158) )
    {
      if ( !*(_BYTE *)(v3 + 2847) )
      {
        ConsoleSessionId = DxgkGetConsoleSessionId();
        if ( ConsoleSessionId != -1 )
        {
          if ( *(_BYTE *)(v3 + 484) )
            DpiEnableD3Requests(*(_QWORD *)(v3 + 24));
          ExReleaseResourceLite(*(PERESOURCE *)(v3 + 168));
          KeLeaveCriticalRegion();
          DxgkWaitForPnPTransitionDone(0, 0, ConsoleSessionId, 1);
          KeEnterCriticalRegion();
          if ( *(_BYTE *)(v3 + 484) )
            DpiCheckForOutstandingD3Requests(v3);
          ExAcquireResourceSharedLite(*(PERESOURCE *)(v3 + 168), 1u);
        }
      }
    }
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v3 + 3440), 1u);
    DxgkQueryConnectionChanges(v5, 0, 0, 0, 1, 0);
    ExReleaseResourceLite((PERESOURCE)(v3 + 3440));
    KeLeaveCriticalRegion();
    if ( *(_BYTE *)(v3 + 484) )
      DpiEnableD3Requests(*(_QWORD *)(v3 + 24));
    ExReleaseResourceLite(*(PERESOURCE *)(v3 + 168));
    KeLeaveCriticalRegion();
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 64), IoWorkItem, 0x20u);
  }
  else
  {
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 1583;
  }
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x14029a7c0  push    rbx
0x14029a7c2  push    rbp
0x14029a7c3  push    rsi
0x14029a7c4  push    rdi
0x14029a7c5  push    r14
0x14029a7c7  sub     rsp, 30h
0x14029a7cb  mov     rdi, [rcx+40h]
0x14029a7cf  mov     rsi, r8
0x14029a7d2  mov     r14, rcx
0x14029a7d5  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x14029a7dd  mov     r9d, 1; Line
0x14029a7e3  lea     r8, File; File
0x14029a7ea  mov     rdx, rsi; Tag
0x14029a7ed  lea     rcx, [rdi+40h]; RemoveLock
0x14029a7f1  call    cs:__imp_IoAcquireRemoveLockEx
0x14029a7f8  nop     dword ptr [rax+rax+00h]
0x14029a7fd  test    eax, eax
0x14029a7ff  jns     short loc_14029A824
0x14029a801  movsxd  rdx, eax
0x14029a804  mov     ecx, 2
0x14029a809  call    cs:__imp_WdLogSingleEntry1
0x14029a810  nop     dword ptr [rax+rax+00h]
0x14029a815  mov     cs:WdLogGlobalForLineNumber, 62Fh
0x14029a81f  jmp     loc_14029A994
0x14029a824  call    cs:__imp_KeEnterCriticalRegion
0x14029a82b  nop     dword ptr [rax+rax+00h]
0x14029a830  cmp     byte ptr [rdi+1E4h], 0
0x14029a837  jz      short loc_14029A841
0x14029a839  mov     rcx, rdi
0x14029a83c  call    DpiCheckForOutstandingD3Requests
0x14029a841  mov     rcx, [rdi+0A8h]; Resource
0x14029a848  mov     dl, 1; Wait
0x14029a84a  call    cs:__imp_ExAcquireResourceSharedLite
0x14029a851  nop     dword ptr [rax+rax+00h]
0x14029a856  cmp     byte ptr [rdi+486h], 0
0x14029a85d  jz      loc_14029A8F1
0x14029a863  cmp     byte ptr [rdi+0B1Fh], 0
0x14029a86a  jnz     loc_14029A8F1
0x14029a870  call    DxgkGetConsoleSessionId
0x14029a875  mov     ebx, eax
0x14029a877  cmp     eax, 0FFFFFFFFh
0x14029a87a  jz      short loc_14029A8F1
0x14029a87c  cmp     byte ptr [rdi+1E4h], 0
0x14029a883  jz      short loc_14029A88E
0x14029a885  mov     rcx, [rdi+18h]
0x14029a889  call    DpiEnableD3Requests
0x14029a88e  mov     rcx, [rdi+0A8h]; Resource
0x14029a895  call    cs:__imp_ExReleaseResourceLite
0x14029a89c  nop     dword ptr [rax+rax+00h]
0x14029a8a1  call    cs:__imp_KeLeaveCriticalRegion
0x14029a8a8  nop     dword ptr [rax+rax+00h]
0x14029a8ad  mov     r9d, 1
0x14029a8b3  mov     r8d, ebx
0x14029a8b6  xor     edx, edx
0x14029a8b8  xor     ecx, ecx
0x14029a8ba  call    DxgkWaitForPnPTransitionDone
0x14029a8bf  call    cs:__imp_KeEnterCriticalRegion
0x14029a8c6  nop     dword ptr [rax+rax+00h]
0x14029a8cb  cmp     byte ptr [rdi+1E4h], 0
0x14029a8d2  jz      short loc_14029A8DC
0x14029a8d4  mov     rcx, rdi
0x14029a8d7  call    DpiCheckForOutstandingD3Requests
0x14029a8dc  mov     rcx, [rdi+0A8h]; Resource
0x14029a8e3  mov     dl, 1; Wait
0x14029a8e5  call    cs:__imp_ExAcquireResourceSharedLite
0x14029a8ec  nop     dword ptr [rax+rax+00h]
0x14029a8f1  call    cs:__imp_KeEnterCriticalRegion
0x14029a8f8  nop     dword ptr [rax+rax+00h]
0x14029a8fd  lea     rbx, [rdi+0D70h]
0x14029a904  mov     dl, 1; Wait
0x14029a906  mov     rcx, rbx; Resource
0x14029a909  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14029a910  nop     dword ptr [rax+rax+00h]
0x14029a915  xor     r9d, r9d
0x14029a918  mov     [rsp+58h+var_30], 0
0x14029a91d  xor     r8d, r8d
0x14029a920  mov     byte ptr [rsp+58h+RemlockSize], 1
0x14029a925  xor     edx, edx
0x14029a927  mov     rcx, r14
0x14029a92a  call    DxgkQueryConnectionChanges
0x14029a92f  mov     rcx, rbx; Resource
0x14029a932  call    cs:__imp_ExReleaseResourceLite
0x14029a939  nop     dword ptr [rax+rax+00h]
0x14029a93e  call    cs:__imp_KeLeaveCriticalRegion
0x14029a945  nop     dword ptr [rax+rax+00h]
0x14029a94a  cmp     byte ptr [rdi+1E4h], 0
0x14029a951  jz      short loc_14029A95C
0x14029a953  mov     rcx, [rdi+18h]
0x14029a957  call    DpiEnableD3Requests
0x14029a95c  mov     rcx, [rdi+0A8h]; Resource
0x14029a963  call    cs:__imp_ExReleaseResourceLite
0x14029a96a  nop     dword ptr [rax+rax+00h]
0x14029a96f  call    cs:__imp_KeLeaveCriticalRegion
0x14029a976  nop     dword ptr [rax+rax+00h]
0x14029a97b  mov     r8d, 20h ; ' '; RemlockSize
0x14029a981  lea     rcx, [rdi+40h]; RemoveLock
0x14029a985  mov     rdx, rsi; Tag
0x14029a988  call    cs:__imp_IoReleaseRemoveLockEx
0x14029a98f  nop     dword ptr [rax+rax+00h]
0x14029a994  mov     rcx, rsi; IoWorkItem
0x14029a997  call    cs:__imp_IoFreeWorkItem
0x14029a99e  nop     dword ptr [rax+rax+00h]
0x14029a9a3  add     rsp, 30h
0x14029a9a7  pop     r14
0x14029a9a9  pop     rdi
0x14029a9aa  pop     rsi
0x14029a9ab  pop     rbp
0x14029a9ac  pop     rbx
0x14029a9ad  retn
```
