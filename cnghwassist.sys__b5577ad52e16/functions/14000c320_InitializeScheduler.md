# InitializeScheduler

- ea: `0x14000c320`
- end: `0x14000c3e8`
- name: `InitializeScheduler`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c078`

## callees

- `0x140003938`
- `0x1400041c0`
- `0x14000c320`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x14000c34e`
- `ntoskrnl!KeInitializeSpinLock` at `0x14000c34e`

## pseudocode

```c
__int64 *InitializeScheduler()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  __int64 *result; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice);
  KeInitializeSpinLock(&g_spinlock);
  memset(g_SwThreadsRunning, 0, 0x80u);
  v0 = 0;
  v1 = 0;
  do
  {
    ++v0;
    qword_140007230[v1] = (__int64)&qword_140007228[v1];
    qword_140007228[v1] = (__int64)&qword_140007228[v1];
    result = &qword_140007448[v1];
    qword_140007448[v1 + 1] = (__int64)&qword_140007448[v1];
    qword_140007448[v1] = (__int64)&qword_140007448[v1];
    v1 += 2;
  }
  while ( v0 != 32 );
  *(_QWORD *)g_priorityQueueHw = 0;
  *(_QWORD *)g_priorityQueueSw = 0;
  g_nBytesInQueues = 0;
  g_maxPrioritySoftware = 0;
  g_nSwThreadsRunning = 0;
  return result;
}

```

## disassembly

```asm
0x14000c320  sub     rsp, 28h
0x14000c324  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c32b  lea     rax, WPP_GLOBAL_Control
0x14000c332  cmp     rcx, rax
0x14000c335  jz      short loc_14000C347
0x14000c337  mov     eax, [rcx+2Ch]
0x14000c33a  test    al, 10h
0x14000c33c  jz      short loc_14000C347
0x14000c33e  mov     rcx, [rcx+18h]
0x14000c342  call    WPP_SF_
0x14000c347  lea     rcx, g_spinlock; SpinLock
0x14000c34e  call    cs:__imp_KeInitializeSpinLock
0x14000c355  nop     dword ptr [rax+rax+00h]
0x14000c35a  xor     edx, edx; Val
0x14000c35c  lea     rcx, g_SwThreadsRunning; void *
0x14000c363  mov     r8d, 80h; Size
0x14000c369  call    memset
0x14000c36e  xor     r8d, r8d
0x14000c371  lea     r9, cs:140000000h
0x14000c378  mov     edx, r8d
0x14000c37b  mov     ecx, r8d
0x14000c37e  lea     rax, rva qword_140007228[r9]
0x14000c385  inc     rdx
0x14000c388  add     rax, rcx
0x14000c38b  mov     [rcx+r9+7230h], rax
0x14000c393  mov     [rcx+r9+7228h], rax
0x14000c39b  lea     rax, rva qword_140007448[r9]
0x14000c3a2  add     rax, rcx
0x14000c3a5  mov     [rcx+r9+7450h], rax
0x14000c3ad  mov     [rcx+r9+7448h], rax
0x14000c3b5  add     rcx, 10h
0x14000c3b9  cmp     rdx, 20h ; ' '
0x14000c3bd  jnz     short loc_14000C37E
0x14000c3bf  mov     qword ptr cs:g_priorityQueueHw, r8
0x14000c3c6  mov     qword ptr cs:g_priorityQueueSw, r8
0x14000c3cd  mov     cs:g_nBytesInQueues, r8
0x14000c3d4  mov     cs:g_maxPrioritySoftware, r8d
0x14000c3db  mov     cs:g_nSwThreadsRunning, r8d
0x14000c3e2  add     rsp, 28h
0x14000c3e6  retn
```
