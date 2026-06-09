# ScavengerThreadRoutine

- ea: `0x1400018b0`
- end: `0x1400019a5`
- name: `ScavengerThreadRoutine`
- size: `245`
- prototype: `BOOLEAN()`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1400018b0`
- `0x14001d524`
- `0x140024a8c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001905`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001905`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001927`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001927`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400018cd`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14000193a`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x1400018cd`
- `ntoskrnl!IoSetThreadHardErrorMode` at `0x14000193a`
- `ntoskrnl!KeSetEvent` at `0x140001984`
- `ntoskrnl!KeSetEvent` at `0x140001984`

## pseudocode

```c
BOOLEAN ScavengerThreadRoutine()
{
  char v0; // bl
  BOOLEAN v1; // si
  KIRQL v2; // di
  BOOLEAN result; // al

  v0 = 1;
  _InterlockedAdd(&ScavengerCount, 1u);
  v1 = IoSetThreadHardErrorMode(0);
  do
  {
    if ( RunFileTableAlgorithm )
    {
      RunFileTableAlgorithm = 0;
      LuafvScavengeFileTable();
    }
    if ( RunUserAlgorithm )
    {
      RunUserAlgorithm = 0;
      LuafvScavengeUserList(0);
    }
    v2 = KeAcquireSpinLockRaiseToDpc(&ScavengerSpinLock);
    if ( !RunFileTableAlgorithm && !RunUserAlgorithm )
    {
      v0 = 0;
      ScavengerRunning = 0;
      if ( !ScavengerInitialized )
        KeSetEvent(&ScavengerThreadTerminationEvent, 0, 0);
    }
    KeReleaseSpinLock(&ScavengerSpinLock, v2);
  }
  while ( v0 );
  result = IoSetThreadHardErrorMode(v1);
  _InterlockedDecrement(&ScavengerCount);
  return result;
}

```

## disassembly

```asm
0x1400018b0  mov     [rsp+arg_0], rbx
0x1400018b5  mov     [rsp+arg_8], rsi
0x1400018ba  push    rdi
0x1400018bb  sub     rsp, 20h
0x1400018bf  mov     ebx, 1
0x1400018c4  lock add cs:ScavengerCount, ebx
0x1400018cb  xor     ecx, ecx; EnableHardErrors
0x1400018cd  call    cs:__imp_IoSetThreadHardErrorMode
0x1400018d4  nop     dword ptr [rax+rax+00h]
0x1400018d9  mov     sil, al
0x1400018dc  cmp     cs:RunFileTableAlgorithm, 0
0x1400018e3  jz      short loc_1400018F1
0x1400018e5  mov     cs:RunFileTableAlgorithm, 0
0x1400018ec  call    LuafvScavengeFileTable
0x1400018f1  cmp     cs:RunUserAlgorithm, 0
0x1400018f8  jnz     loc_140001992
0x1400018fe  lea     rcx, ScavengerSpinLock; SpinLock
0x140001905  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000190c  nop     dword ptr [rax+rax+00h]
0x140001911  cmp     cs:RunFileTableAlgorithm, 0
0x140001918  mov     dil, al
0x14000191b  jz      short loc_14000195E
0x14000191d  mov     dl, dil; NewIrql
0x140001920  lea     rcx, ScavengerSpinLock; SpinLock
0x140001927  call    cs:__imp_KeReleaseSpinLock
0x14000192e  nop     dword ptr [rax+rax+00h]
0x140001933  test    bl, bl
0x140001935  jnz     short loc_1400018DC
0x140001937  mov     cl, sil; EnableHardErrors
0x14000193a  call    cs:__imp_IoSetThreadHardErrorMode
0x140001941  nop     dword ptr [rax+rax+00h]
0x140001946  lock dec cs:ScavengerCount
0x14000194d  mov     rbx, [rsp+28h+arg_0]
0x140001952  mov     rsi, [rsp+28h+arg_8]
0x140001957  add     rsp, 20h
0x14000195b  pop     rdi
0x14000195c  retn
0x14000195e  cmp     cs:RunUserAlgorithm, 0
0x140001965  jnz     short loc_14000191D
0x140001967  xor     bl, bl
0x140001969  mov     cs:ScavengerRunning, 0
0x140001970  cmp     cs:ScavengerInitialized, bl
0x140001976  jnz     short loc_14000191D
0x140001978  xor     r8d, r8d; Wait
0x14000197b  lea     rcx, ScavengerThreadTerminationEvent; Event
0x140001982  xor     edx, edx; Increment
0x140001984  call    cs:__imp_KeSetEvent
0x14000198b  nop     dword ptr [rax+rax+00h]
0x140001990  jmp     short loc_14000191D
0x140001992  xor     ecx, ecx
0x140001994  mov     cs:RunUserAlgorithm, 0
0x14000199b  call    LuafvScavengeUserList
0x1400019a0  jmp     loc_1400018FE
```
