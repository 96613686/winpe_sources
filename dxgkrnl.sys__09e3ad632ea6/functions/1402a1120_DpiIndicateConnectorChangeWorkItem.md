# DpiIndicateConnectorChangeWorkItem

- ea: `0x1402a1120`
- end: `0x1402a130f`
- name: `DpiIndicateConnectorChangeWorkItem`
- size: `495`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x140022434`
- `0x14005b0f0`
- `0x14026ab38`
- `0x1402a1120`
- `0x140312414`
- `0x140367720`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a1184`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a121f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a1251`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a1184`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a121f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402a1251`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a1201`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a129e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a12cf`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a1201`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a129e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402a12cf`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a12f7`
- `ntoskrnl!IoFreeWorkItem` at `0x1402a12f7`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a11aa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a1245`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a11aa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402a1245`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a1269`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402a1269`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a11f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a1292`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a12c3`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a11f5`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a1292`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402a12c3`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402a1151`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1402a1151`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402a12e8`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1402a12e8`
- `watchdog!WdLogSingleEntry1` at `0x1402a1169`
- `watchdog!WdLogSingleEntry1` at `0x1402a1169`

## pseudocode

```c
void __fastcall DpiIndicateConnectorChangeWorkItem(_QWORD *IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v3; // rdi
  NTSTATUS v6; // eax
  unsigned int ConsoleSessionId; // ebx

  v3 = IoObject[8];
  v6 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v3 + 64), IoWorkItem, File, 1u, 0x20u);
  if ( v6 >= 0 )
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
    DxgkQueryConnectionChanges((__int64)IoObject, 0, 0, 0, 1, 0);
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
    WdLogSingleEntry1(2, v6);
    WdLogGlobalForLineNumber = 1583;
  }
  IoFreeWorkItem(IoWorkItem);
}

```

## disassembly

```asm
0x1402a1120  push    rbx
0x1402a1122  push    rbp
0x1402a1123  push    rsi
0x1402a1124  push    rdi
0x1402a1125  push    r14
0x1402a1127  sub     rsp, 30h
0x1402a112b  mov     rdi, [rcx+40h]
0x1402a112f  mov     rsi, r8
0x1402a1132  mov     r14, rcx
0x1402a1135  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x1402a113d  mov     r9d, 1; Line
0x1402a1143  lea     r8, File; File
0x1402a114a  mov     rdx, rsi; Tag
0x1402a114d  lea     rcx, [rdi+40h]; RemoveLock
0x1402a1151  call    cs:__imp_IoAcquireRemoveLockEx
0x1402a1158  nop     dword ptr [rax+rax+00h]
0x1402a115d  test    eax, eax
0x1402a115f  jns     short loc_1402A1184
0x1402a1161  movsxd  rdx, eax
0x1402a1164  mov     ecx, 2
0x1402a1169  call    cs:__imp_WdLogSingleEntry1
0x1402a1170  nop     dword ptr [rax+rax+00h]
0x1402a1175  mov     cs:WdLogGlobalForLineNumber, 62Fh
0x1402a117f  jmp     loc_1402A12F4
0x1402a1184  call    cs:__imp_KeEnterCriticalRegion
0x1402a118b  nop     dword ptr [rax+rax+00h]
0x1402a1190  cmp     byte ptr [rdi+1E4h], 0
0x1402a1197  jz      short loc_1402A11A1
0x1402a1199  mov     rcx, rdi
0x1402a119c  call    DpiCheckForOutstandingD3Requests
0x1402a11a1  mov     rcx, [rdi+0A8h]; Resource
0x1402a11a8  mov     dl, 1; Wait
0x1402a11aa  call    cs:__imp_ExAcquireResourceSharedLite
0x1402a11b1  nop     dword ptr [rax+rax+00h]
0x1402a11b6  cmp     byte ptr [rdi+486h], 0
0x1402a11bd  jz      loc_1402A1251
0x1402a11c3  cmp     byte ptr [rdi+0B1Fh], 0
0x1402a11ca  jnz     loc_1402A1251
0x1402a11d0  call    DxgkGetConsoleSessionId
0x1402a11d5  mov     ebx, eax
0x1402a11d7  cmp     eax, 0FFFFFFFFh
0x1402a11da  jz      short loc_1402A1251
0x1402a11dc  cmp     byte ptr [rdi+1E4h], 0
0x1402a11e3  jz      short loc_1402A11EE
0x1402a11e5  mov     rcx, [rdi+18h]
0x1402a11e9  call    DpiEnableD3Requests
0x1402a11ee  mov     rcx, [rdi+0A8h]; Resource
0x1402a11f5  call    cs:__imp_ExReleaseResourceLite
0x1402a11fc  nop     dword ptr [rax+rax+00h]
0x1402a1201  call    cs:__imp_KeLeaveCriticalRegion
0x1402a1208  nop     dword ptr [rax+rax+00h]
0x1402a120d  mov     r9d, 1
0x1402a1213  mov     r8d, ebx
0x1402a1216  xor     edx, edx
0x1402a1218  xor     ecx, ecx
0x1402a121a  call    DxgkWaitForPnPTransitionDone
0x1402a121f  call    cs:__imp_KeEnterCriticalRegion
0x1402a1226  nop     dword ptr [rax+rax+00h]
0x1402a122b  cmp     byte ptr [rdi+1E4h], 0
0x1402a1232  jz      short loc_1402A123C
0x1402a1234  mov     rcx, rdi
0x1402a1237  call    DpiCheckForOutstandingD3Requests
0x1402a123c  mov     rcx, [rdi+0A8h]; Resource
0x1402a1243  mov     dl, 1; Wait
0x1402a1245  call    cs:__imp_ExAcquireResourceSharedLite
0x1402a124c  nop     dword ptr [rax+rax+00h]
0x1402a1251  call    cs:__imp_KeEnterCriticalRegion
0x1402a1258  nop     dword ptr [rax+rax+00h]
0x1402a125d  lea     rbx, [rdi+0D70h]
0x1402a1264  mov     dl, 1; Wait
0x1402a1266  mov     rcx, rbx; Resource
0x1402a1269  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402a1270  nop     dword ptr [rax+rax+00h]
0x1402a1275  xor     r9d, r9d
0x1402a1278  mov     [rsp+58h+var_30], 0
0x1402a127d  xor     r8d, r8d
0x1402a1280  mov     byte ptr [rsp+58h+RemlockSize], 1
0x1402a1285  xor     edx, edx
0x1402a1287  mov     rcx, r14
0x1402a128a  call    DxgkQueryConnectionChanges
0x1402a128f  mov     rcx, rbx; Resource
0x1402a1292  call    cs:__imp_ExReleaseResourceLite
0x1402a1299  nop     dword ptr [rax+rax+00h]
0x1402a129e  call    cs:__imp_KeLeaveCriticalRegion
0x1402a12a5  nop     dword ptr [rax+rax+00h]
0x1402a12aa  cmp     byte ptr [rdi+1E4h], 0
0x1402a12b1  jz      short loc_1402A12BC
0x1402a12b3  mov     rcx, [rdi+18h]
0x1402a12b7  call    DpiEnableD3Requests
0x1402a12bc  mov     rcx, [rdi+0A8h]; Resource
0x1402a12c3  call    cs:__imp_ExReleaseResourceLite
0x1402a12ca  nop     dword ptr [rax+rax+00h]
0x1402a12cf  call    cs:__imp_KeLeaveCriticalRegion
0x1402a12d6  nop     dword ptr [rax+rax+00h]
0x1402a12db  mov     r8d, 20h ; ' '; RemlockSize
0x1402a12e1  lea     rcx, [rdi+40h]; RemoveLock
0x1402a12e5  mov     rdx, rsi; Tag
0x1402a12e8  call    cs:__imp_IoReleaseRemoveLockEx
0x1402a12ef  nop     dword ptr [rax+rax+00h]
0x1402a12f4  mov     rcx, rsi; IoWorkItem
0x1402a12f7  call    cs:__imp_IoFreeWorkItem
0x1402a12fe  nop     dword ptr [rax+rax+00h]
0x1402a1303  add     rsp, 30h
0x1402a1307  pop     r14
0x1402a1309  pop     rdi
0x1402a130a  pop     rsi
0x1402a130b  pop     rbp
0x1402a130c  pop     rbx
0x1402a130d  retn
```
