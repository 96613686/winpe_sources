# DbgkpWerDeferredWriteRoutine

- ea: `0x14074dc90`
- end: `0x14074dd8c`
- name: `DbgkpWerDeferredWriteRoutine`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x14020fe90`
- `0x140224f70`
- `0x1402d4060`
- `0x1402d6160`
- `0x1402f8270`
- `0x1405cf968`
- `0x14074daac`
- `0x14074dc90`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x14074dd46`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x14074dd46`

## string_xrefs

- `0x14074dca4`: `DBGK: DbgkpWerDeferredWriteRoutine entered, context 0x%p\n`
- `0x14074dd2d`: `DBGK: DbgkpWerDeferredWriteRoutine: dump write failed with status 0x%X\n`
- `0x14074dd59`: `DBGK: DbgkpWerDeferredWriteRoutine: WerLiveKernelSubmitReport failed with status 0x%X\n`

## pseudocode

```c
void __fastcall DbgkpWerDeferredWriteRoutine(__int64 a1)
{
  int v2; // edx
  struct _KTIMER *v3; // rdi
  int v4; // esi
  int v5; // eax

  DbgPrintEx(5u, 3u, "DBGK: DbgkpWerDeferredWriteRoutine entered, context 0x%p\n", (const void *)a1);
  KeEnterCriticalRegion();
  if ( *(_DWORD *)(a1 + 32) == 453 )
    v2 = 1769803776;
  else
    v2 = -10000000 * LODWORD(EmpParseLock.SchedulingGroup);
  v3 = *(struct _KTIMER **)(*(_QWORD *)(a1 + 120) + 16LL);
  if ( v3 )
    KiSetTimerEx((_DWORD)v3, v2, 0, 0, 0);
  v4 = IoWriteDeferredLiveDumpData(*(_QWORD *)(a1 + 128));
  KeCancelTimer(v3);
  *(_QWORD *)(a1 + 128) = 0;
  if ( v4 >= 0 )
  {
    v5 = WerLiveKernelSubmitReport(*(_QWORD *)(a1 + 96), 0);
    if ( v5 >= 0 )
      *(_DWORD *)(a1 + 104) |= 1u;
    else
      DbgPrintEx(
        5u,
        0,
        "DBGK: DbgkpWerDeferredWriteRoutine: WerLiveKernelSubmitReport failed with status 0x%X\n",
        (unsigned int)v5);
  }
  else
  {
    DbgPrintEx(5u, 0, "DBGK: DbgkpWerDeferredWriteRoutine: dump write failed with status 0x%X\n", (unsigned int)v4);
  }
  DbgkpWerCleanupContext(a1);
  _InterlockedExchange((_DWORD *)&EmpParseLock.SchedulingGroup + 1, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14074dc90  mov     [rsp+arg_0], rbx
0x14074dc95  mov     [rsp+arg_8], rsi
0x14074dc9a  push    rdi
0x14074dc9b  sub     rsp, 30h
0x14074dc9f  mov     edx, 3; Level
0x14074dca4  lea     r8, aDbgkDbgkpwerde_0; "DBGK: DbgkpWerDeferredWriteRoutine ente"...
0x14074dcab  mov     rbx, rcx
0x14074dcae  mov     r9, rcx
0x14074dcb1  lea     ecx, [rdx+2]; ComponentId
0x14074dcb4  call    DbgPrintEx
0x14074dcb9  call    KeEnterCriticalRegion
0x14074dcbe  cmp     dword ptr [rbx+20h], 1C5h
0x14074dcc5  jnz     short loc_14074DCD3
0x14074dcc7  mov     rdx, 0FFFFFFFA697D1000h
0x14074dcd1  jmp     short loc_14074DCE1
0x14074dcd3  movsxd  rax, dword ptr cs:EmpParseLock.SchedulingGroup
0x14074dcda  imul    rdx, rax, 0FFFFFFFFFF676980h
0x14074dce1  mov     rax, [rbx+78h]
0x14074dce5  mov     rdi, [rax+10h]
0x14074dce9  test    rdi, rdi
0x14074dcec  jz      short loc_14074DD05
0x14074dcee  xor     r9d, r9d
0x14074dcf1  mov     [rsp+38h+var_18], 0
0x14074dcfa  xor     r8d, r8d
0x14074dcfd  mov     rcx, rdi
0x14074dd00  call    KiSetTimerEx
0x14074dd05  mov     rcx, [rbx+80h]; __int64
0x14074dd0c  call    IoWriteDeferredLiveDumpData
0x14074dd11  mov     rcx, rdi; PKTIMER
0x14074dd14  mov     esi, eax
0x14074dd16  call    KeCancelTimer
0x14074dd1b  mov     qword ptr [rbx+80h], 0
0x14074dd26  test    esi, esi
0x14074dd28  jns     short loc_14074DD40
0x14074dd2a  mov     r9d, esi
0x14074dd2d  lea     r8, aDbgkDbgkpwerde_1; "DBGK: DbgkpWerDeferredWriteRoutine: dum"...
0x14074dd34  xor     edx, edx; Level
0x14074dd36  lea     ecx, [rdx+5]; ComponentId
0x14074dd39  call    DbgPrintEx
0x14074dd3e  jmp     short loc_14074DD66
0x14074dd40  mov     rcx, [rbx+60h]
0x14074dd44  xor     edx, edx
0x14074dd46  call    cs:__imp_WerLiveKernelSubmitReport
0x14074dd4d  nop     dword ptr [rax+rax+00h]
0x14074dd52  test    eax, eax
0x14074dd54  jns     short loc_14074DD62
0x14074dd56  mov     r9d, eax
0x14074dd59  lea     r8, aDbgkDbgkpwerde; "DBGK: DbgkpWerDeferredWriteRoutine: Wer"...
0x14074dd60  jmp     short loc_14074DD34
0x14074dd62  or      dword ptr [rbx+68h], 1
0x14074dd66  mov     rcx, rbx
0x14074dd69  call    DbgkpWerCleanupContext
0x14074dd6e  xor     eax, eax
0x14074dd70  xchg    eax, dword ptr cs:EmpParseLock.SchedulingGroup+4
0x14074dd76  call    KeLeaveCriticalRegion
0x14074dd7b  mov     rbx, [rsp+38h+arg_0]
0x14074dd80  mov     rsi, [rsp+38h+arg_8]
0x14074dd85  add     rsp, 30h
0x14074dd89  pop     rdi
0x14074dd8a  retn
```
