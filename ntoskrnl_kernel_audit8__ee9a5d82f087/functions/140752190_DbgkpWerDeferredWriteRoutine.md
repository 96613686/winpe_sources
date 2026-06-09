# DbgkpWerDeferredWriteRoutine

- ea: `0x140752190`
- end: `0x14075228c`
- name: `DbgkpWerDeferredWriteRoutine`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x140214b10`
- `0x1402a2f90`
- `0x1402fcf10`
- `0x1402fece0`
- `0x14036f270`
- `0x1405d6548`
- `0x140751fac`
- `0x140752190`

## import_xrefs

- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140752246`
- `ext-ms-win-ntos-werkernel-l1-1-1!WerLiveKernelSubmitReport` at `0x140752246`

## string_xrefs

- `0x1407521a4`: `DBGK: DbgkpWerDeferredWriteRoutine entered, context 0x%p\n`
- `0x14075222d`: `DBGK: DbgkpWerDeferredWriteRoutine: dump write failed with status 0x%X\n`
- `0x140752259`: `DBGK: DbgkpWerDeferredWriteRoutine: WerLiveKernelSubmitReport failed with status 0x%X\n`

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
    v2 = -10000000 * DbgkpWerDeferredWriteTimeoutSeconds;
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
  _InterlockedExchange(&DbgkpBusy, 0);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140752190  mov     [rsp+arg_0], rbx
0x140752195  mov     [rsp+arg_8], rsi
0x14075219a  push    rdi
0x14075219b  sub     rsp, 30h
0x14075219f  mov     edx, 3; Level
0x1407521a4  lea     r8, aDbgkDbgkpwerde_0; "DBGK: DbgkpWerDeferredWriteRoutine ente"...
0x1407521ab  mov     rbx, rcx
0x1407521ae  mov     r9, rcx
0x1407521b1  lea     ecx, [rdx+2]; ComponentId
0x1407521b4  call    DbgPrintEx
0x1407521b9  call    KeEnterCriticalRegion
0x1407521be  cmp     dword ptr [rbx+20h], 1C5h
0x1407521c5  jnz     short loc_1407521D3
0x1407521c7  mov     rdx, 0FFFFFFFA697D1000h
0x1407521d1  jmp     short loc_1407521E1
0x1407521d3  movsxd  rax, cs:DbgkpWerDeferredWriteTimeoutSeconds
0x1407521da  imul    rdx, rax, 0FFFFFFFFFF676980h
0x1407521e1  mov     rax, [rbx+78h]
0x1407521e5  mov     rdi, [rax+10h]
0x1407521e9  test    rdi, rdi
0x1407521ec  jz      short loc_140752205
0x1407521ee  xor     r9d, r9d
0x1407521f1  mov     [rsp+38h+var_18], 0
0x1407521fa  xor     r8d, r8d
0x1407521fd  mov     rcx, rdi
0x140752200  call    KiSetTimerEx
0x140752205  mov     rcx, [rbx+80h]; __int64
0x14075220c  call    IoWriteDeferredLiveDumpData
0x140752211  mov     rcx, rdi; PKTIMER
0x140752214  mov     esi, eax
0x140752216  call    KeCancelTimer
0x14075221b  mov     qword ptr [rbx+80h], 0
0x140752226  test    esi, esi
0x140752228  jns     short loc_140752240
0x14075222a  mov     r9d, esi
0x14075222d  lea     r8, aDbgkDbgkpwerde_1; "DBGK: DbgkpWerDeferredWriteRoutine: dum"...
0x140752234  xor     edx, edx; Level
0x140752236  lea     ecx, [rdx+5]; ComponentId
0x140752239  call    DbgPrintEx
0x14075223e  jmp     short loc_140752266
0x140752240  mov     rcx, [rbx+60h]
0x140752244  xor     edx, edx
0x140752246  call    cs:__imp_WerLiveKernelSubmitReport
0x14075224d  nop     dword ptr [rax+rax+00h]
0x140752252  test    eax, eax
0x140752254  jns     short loc_140752262
0x140752256  mov     r9d, eax
0x140752259  lea     r8, aDbgkDbgkpwerde; "DBGK: DbgkpWerDeferredWriteRoutine: Wer"...
0x140752260  jmp     short loc_140752234
0x140752262  or      dword ptr [rbx+68h], 1
0x140752266  mov     rcx, rbx
0x140752269  call    DbgkpWerCleanupContext
0x14075226e  xor     eax, eax
0x140752270  xchg    eax, cs:DbgkpBusy
0x140752276  call    KeLeaveCriticalRegion
0x14075227b  mov     rbx, [rsp+38h+arg_0]
0x140752280  mov     rsi, [rsp+38h+arg_8]
0x140752285  add     rsp, 30h
0x140752289  pop     rdi
0x14075228a  retn
```
