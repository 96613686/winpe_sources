# SstpTimerPeriodicDpc

- ea: `0x140002700`
- end: `0x1400029c1`
- name: `SstpTimerPeriodicDpc`
- size: `705`
- prototype: `KDEFERRED_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x140002030`
- `0x140002700`
- `0x1400054c4`
- `0x140005ef0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000276b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002781`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400027f2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000289a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400028aa`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000294f`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000276b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140002781`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400027f2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000289a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400028aa`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000294f`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027a7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027ba`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002801`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000284e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000287c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002931`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002940`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002983`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002996`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027a7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400027ba`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002801`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000284e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000287c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002931`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002940`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002983`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002996`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400028bc`
- `NETIO!RtlReturnTimerWheelEntry` at `0x1400028bc`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140002921`
- `NETIO!RtlIndicateTimerWheelEntryTimerStart` at `0x140002921`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400028f0`
- `NETIO!RtlCleanupTimerWheelEntry` at `0x1400028f0`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140002758`
- `NETIO!RtlUpdateCurrentTimerWheelTick` at `0x140002758`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140002790`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000295e`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x140002790`
- `NETIO!RtlGetNextExpiredTimerWheelEntry` at `0x14000295e`

## pseudocode

```c
void __fastcall SstpTimerPeriodicDpc(
        struct _KDPC *Dpc,
        PVOID DeferredContext,
        PVOID SystemArgument1,
        PVOID SystemArgument2)
{
  __int64 v4; // rsi
  __int64 NextExpiredTimerWheelEntry; // r14
  __int64 v6; // r13
  int v7; // eax
  __int64 v8; // r12
  unsigned int v9; // eax
  char v10; // [rsp+20h] [rbp-38h]
  _BYTE v11[7]; // [rsp+21h] [rbp-37h] BYREF
  void (__fastcall *v12)(__int64, char *); // [rsp+28h] [rbp-30h]
  char v13; // [rsp+68h] [rbp+10h] BYREF

  v4 = *((_QWORD *)&SstpTimerGlobals + 1) + 984LL * (unsigned int)DeferredContext;
  RtlUpdateCurrentTimerWheelTick(v4 + 152, MEMORY[0xFFFFF78000000008] / 0x2710uLL / Period);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 976));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 128));
  NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(v4 + 152);
  if ( NextExpiredTimerWheelEntry )
  {
    v6 = 0;
    do
    {
      v13 = 0;
      v11[0] = 0;
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8));
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 128));
      v7 = *(_DWORD *)(NextExpiredTimerWheelEntry + 20);
      if ( v7 && v7 - *(_DWORD *)(NextExpiredTimerWheelEntry + 16) <= 0 )
      {
        v8 = *(_QWORD *)(NextExpiredTimerWheelEntry - 16);
        v12 = *(void (__fastcall **)(__int64, char *))(NextExpiredTimerWheelEntry - 24);
        if ( !v6 )
        {
          v6 = v8;
          _InterlockedIncrement((volatile signed __int32 *)(v8 + 32));
        }
        v10 = 1;
        *(_DWORD *)(NextExpiredTimerWheelEntry + 20) = 0;
        *(_BYTE *)(NextExpiredTimerWheelEntry - 31) = 0;
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8));
        if ( v12 )
          v12(v8, &v13);
      }
      else
      {
        v10 = 0;
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8));
      }
      if ( !v13 )
      {
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 128));
        KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8));
        RtlReturnTimerWheelEntry(v4 + 152, NextExpiredTimerWheelEntry);
        if ( v10 )
        {
          if ( (!*(_BYTE *)(NextExpiredTimerWheelEntry - 32) || *(_BYTE *)(NextExpiredTimerWheelEntry - 31))
            && (v9 = *(_DWORD *)(NextExpiredTimerWheelEntry - 28)) != 0 )
          {
            if ( (unsigned __int8)RtlStartTimerWheelEntryTimer(
                                    NextExpiredTimerWheelEntry,
                                    v9 % Period,
                                    *(_DWORD *)(v4 + 156) + v9 / Period) )
              RtlIndicateTimerWheelEntryTimerStart(v4 + 152, NextExpiredTimerWheelEntry);
          }
          else
          {
            RtlCleanupTimerWheelEntry(v4 + 152, NextExpiredTimerWheelEntry, v11);
          }
        }
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(NextExpiredTimerWheelEntry - 8));
        KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 128));
      }
      KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v4 + 128));
      NextExpiredTimerWheelEntry = RtlGetNextExpiredTimerWheelEntry(v4 + 152);
    }
    while ( NextExpiredTimerWheelEntry );
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 128));
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 976));
    if ( v6 )
      DereferenceRefCount(v6 + 32);
  }
  else
  {
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 128));
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v4 + 976));
  }
}

```

## disassembly

```asm
0x140002700  push    rbx
0x140002702  push    rbp
0x140002703  push    rsi
0x140002704  push    rdi
0x140002705  push    r14
0x140002707  sub     rsp, 30h
0x14000270b  mov     r8, rdx
0x14000270e  mov     rcx, 0FFFFF78000000008h
0x140002718  mov     rax, 346DC5D63886594Bh
0x140002722  mov     rcx, [rcx]
0x140002725  mul     rcx
0x140002728  mov     ecx, r8d
0x14000272b  mov     rax, rdx
0x14000272e  xor     edx, edx
0x140002730  imul    rsi, rcx, 3D8h
0x140002737  mov     ecx, dword ptr cs:Period
0x14000273d  add     rsi, qword ptr cs:SstpTimerGlobals+8
0x140002744  shr     rax, 0Bh
0x140002748  div     rcx
0x14000274b  lea     rbp, [rsi+98h]
0x140002752  mov     rdx, rax
0x140002755  mov     rcx, rbp
0x140002758  call    cs:__imp_RtlUpdateCurrentTimerWheelTick
0x14000275f  nop     dword ptr [rax+rax+00h]
0x140002764  lea     rcx, [rsi+3D0h]; SpinLock
0x14000276b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002772  nop     dword ptr [rax+rax+00h]
0x140002777  lea     rbx, [rsi+80h]
0x14000277e  mov     rcx, rbx; SpinLock
0x140002781  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002788  nop     dword ptr [rax+rax+00h]
0x14000278d  mov     rcx, rbp
0x140002790  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x140002797  nop     dword ptr [rax+rax+00h]
0x14000279c  mov     r14, rax
0x14000279f  test    rax, rax
0x1400027a2  jnz     short loc_1400027D2
0x1400027a4  mov     rcx, rbx; SpinLock
0x1400027a7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400027ae  nop     dword ptr [rax+rax+00h]
0x1400027b3  lea     rcx, [rsi+3D0h]; SpinLock
0x1400027ba  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400027c1  nop     dword ptr [rax+rax+00h]
0x1400027c6  add     rsp, 30h
0x1400027ca  pop     r14
0x1400027cc  pop     rdi
0x1400027cd  pop     rsi
0x1400027ce  pop     rbp
0x1400027cf  pop     rbx
0x1400027d0  retn
0x1400027d2  mov     [rsp+58h+arg_10], r13
0x1400027d7  xor     r13d, r13d
0x1400027da  mov     [rsp+58h+arg_18], r15
0x1400027df  mov     [rsp+58h+arg_0], r12
0x1400027e4  lea     rcx, [r14-8]; SpinLock
0x1400027e8  mov     [rsp+58h+arg_8], 0
0x1400027ed  mov     [rsp+58h+var_37], 0
0x1400027f2  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400027f9  nop     dword ptr [rax+rax+00h]
0x1400027fe  mov     rcx, rbx; SpinLock
0x140002801  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002808  nop     dword ptr [rax+rax+00h]
0x14000280d  mov     eax, [r14+14h]
0x140002811  test    eax, eax
0x140002813  jz      short loc_140002873
0x140002815  sub     eax, [r14+10h]
0x140002819  test    eax, eax
0x14000281b  jg      short loc_140002873
0x14000281d  mov     rax, [r14-18h]
0x140002821  mov     r12, [r14-10h]
0x140002825  mov     [rsp+58h+var_30], rax
0x14000282a  test    r13, r13
0x14000282d  jnz     short loc_140002838
0x14000282f  mov     r13, r12
0x140002832  lock inc dword ptr [r12+20h]
0x140002838  lea     rcx, [r14-8]; SpinLock
0x14000283c  mov     [rsp+58h+var_38], 1
0x140002841  mov     dword ptr [r14+14h], 0
0x140002849  mov     byte ptr [r14-1Fh], 0
0x14000284e  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002855  nop     dword ptr [rax+rax+00h]
0x14000285a  mov     rax, [rsp+58h+var_30]
0x14000285f  test    rax, rax
0x140002862  jz      short loc_140002888
0x140002864  lea     rdx, [rsp+58h+arg_8]
0x140002869  mov     rcx, r12
0x14000286c  call    _guard_dispatch_icall
0x140002871  jmp     short loc_140002888
0x140002873  lea     rcx, [r14-8]; SpinLock
0x140002877  mov     [rsp+58h+var_38], 0
0x14000287c  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002883  nop     dword ptr [rax+rax+00h]
0x140002888  cmp     [rsp+58h+arg_8], 0
0x14000288d  lea     r12, [r14-1Fh]
0x140002891  jnz     loc_14000294C
0x140002897  mov     rcx, rbx; SpinLock
0x14000289a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400028a1  nop     dword ptr [rax+rax+00h]
0x1400028a6  lea     rcx, [r14-8]; SpinLock
0x1400028aa  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400028b1  nop     dword ptr [rax+rax+00h]
0x1400028b6  mov     rdx, r14
0x1400028b9  mov     rcx, rbp
0x1400028bc  call    cs:__imp_RtlReturnTimerWheelEntry
0x1400028c3  nop     dword ptr [rax+rax+00h]
0x1400028c8  cmp     [rsp+58h+var_38], 0
0x1400028cd  jz      short loc_14000292D
0x1400028cf  cmp     byte ptr [r14-20h], 0
0x1400028d4  jz      short loc_1400028DD
0x1400028d6  cmp     byte ptr [r12], 0
0x1400028db  jz      short loc_1400028E5
0x1400028dd  mov     eax, [r14-1Ch]
0x1400028e1  test    eax, eax
0x1400028e3  jnz     short loc_1400028FE
0x1400028e5  lea     r8, [rsp+58h+var_37]
0x1400028ea  mov     rdx, r14
0x1400028ed  mov     rcx, rbp
0x1400028f0  call    cs:__imp_RtlCleanupTimerWheelEntry
0x1400028f7  nop     dword ptr [rax+rax+00h]
0x1400028fc  jmp     short loc_14000292D
0x1400028fe  xor     edx, edx
0x140002900  mov     rcx, r14
0x140002903  div     dword ptr cs:Period
0x140002909  add     eax, [rsi+9Ch]
0x14000290f  mov     r8d, eax
0x140002912  call    RtlStartTimerWheelEntryTimer
0x140002917  test    al, al
0x140002919  jz      short loc_14000292D
0x14000291b  mov     rdx, r14
0x14000291e  mov     rcx, rbp
0x140002921  call    cs:__imp_RtlIndicateTimerWheelEntryTimerStart
0x140002928  nop     dword ptr [rax+rax+00h]
0x14000292d  lea     rcx, [r14-8]; SpinLock
0x140002931  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002938  nop     dword ptr [rax+rax+00h]
0x14000293d  mov     rcx, rbx; SpinLock
0x140002940  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140002947  nop     dword ptr [rax+rax+00h]
0x14000294c  mov     rcx, rbx; SpinLock
0x14000294f  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140002956  nop     dword ptr [rax+rax+00h]
0x14000295b  mov     rcx, rbp
0x14000295e  call    cs:__imp_RtlGetNextExpiredTimerWheelEntry
0x140002965  nop     dword ptr [rax+rax+00h]
0x14000296a  mov     r14, rax
0x14000296d  test    rax, rax
0x140002970  jnz     loc_1400027E4
0x140002976  mov     r15, [rsp+58h+arg_18]
0x14000297b  mov     rcx, rbx; SpinLock
0x14000297e  mov     r12, [rsp+58h+arg_0]
0x140002983  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000298a  nop     dword ptr [rax+rax+00h]
0x14000298f  lea     rcx, [rsi+3D0h]; SpinLock
0x140002996  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000299d  nop     dword ptr [rax+rax+00h]
0x1400029a2  test    r13, r13
0x1400029a5  jz      short loc_1400029B0
0x1400029a7  lea     rcx, [r13+20h]
0x1400029ab  call    DereferenceRefCount
0x1400029b0  mov     r13, [rsp+58h+arg_10]
0x1400029b5  add     rsp, 30h
0x1400029b9  pop     r14
0x1400029bb  pop     rdi
0x1400029bc  pop     rsi
0x1400029bd  pop     rbp
0x1400029be  pop     rbx
0x1400029bf  retn
```
