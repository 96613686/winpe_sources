# ScheduleRequestNew

- ea: `0x1400037ec`
- end: `0x140003930`
- name: `ScheduleRequestNew`
- size: `324`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140001430`

## callees

- `0x14000292c`
- `0x14000305c`
- `0x14000322c`
- `0x1400037ec`
- `0x1400039d4`
- `0x140003b38`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000381e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000381e`
- `ntoskrnl!KeQueryPriorityThread` at `0x140003805`
- `ntoskrnl!KeQueryPriorityThread` at `0x140003805`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003911`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003911`

## pseudocode

```c
char __fastcall ScheduleRequestNew(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v3; // al
  unsigned int v4; // edx
  KIRQL v5; // si
  char v6; // bl
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax

  v1 = *(_QWORD *)a1;
  *(_DWORD *)(a1 + 128) = KeQueryPriorityThread(*(PKTHREAD *)(a1 + 96));
  v3 = KeAcquireSpinLockRaiseToDpc(&g_spinlock);
  v4 = *(_DWORD *)(v1 + 8);
  v5 = v3;
  v6 = 1;
  if ( *(_DWORD *)(a1 + 32) < v4 )
    *(_DWORD *)(a1 + 92) |= 1u;
  if ( !(unsigned __int8)IsAllowedOnHardware(a1) || !TryRequestInHardware(a1, v7, v8) )
  {
    if ( (unsigned __int8)shouldRunInSoftware(a1) )
    {
      v9 = *(unsigned int *)(a1 + 128);
      *(_DWORD *)(a1 + 152) = 1;
      ++g_SwThreadsRunning[v9];
      if ( g_maxPrioritySoftware <= (unsigned int)v9 )
        g_maxPrioritySoftware = v9;
      ++g_nSwThreadsRunning;
      v6 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
          *(unsigned int *)(a1 + 156));
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids,
          *(unsigned int *)(a1 + 156));
      addRequestToPriorityQueue(a1);
    }
  }
  KeReleaseSpinLock(&g_spinlock, v5);
  return v6;
}

```

## disassembly

```asm
0x1400037ec  mov     [rsp+arg_0], rbx
0x1400037f1  mov     [rsp+arg_8], rsi
0x1400037f6  push    rdi
0x1400037f7  sub     rsp, 20h
0x1400037fb  mov     rbx, [rcx]
0x1400037fe  mov     rdi, rcx
0x140003801  mov     rcx, [rcx+60h]; Thread
0x140003805  call    cs:__imp_KeQueryPriorityThread
0x14000380c  nop     dword ptr [rax+rax+00h]
0x140003811  lea     rcx, g_spinlock; SpinLock
0x140003818  mov     [rdi+80h], eax
0x14000381e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003825  nop     dword ptr [rax+rax+00h]
0x14000382a  mov     edx, [rbx+8]
0x14000382d  mov     sil, al
0x140003830  mov     ebx, 1
0x140003835  cmp     [rdi+20h], edx
0x140003838  jnb     short loc_14000383D
0x14000383a  or      [rdi+5Ch], ebx
0x14000383d  mov     rcx, rdi
0x140003840  call    IsAllowedOnHardware
0x140003845  test    al, al
0x140003847  jz      short loc_140003859
0x140003849  mov     rcx, rdi
0x14000384c  call    TryRequestInHardware
0x140003851  test    al, al
0x140003853  jnz     loc_140003907
0x140003859  mov     rcx, rdi
0x14000385c  call    shouldRunInSoftware
0x140003861  test    al, al
0x140003863  jz      short loc_1400038C9
0x140003865  mov     eax, [rdi+80h]
0x14000386b  lea     rcx, g_SwThreadsRunning
0x140003872  mov     [rdi+98h], ebx
0x140003878  add     [rcx+rax*4], ebx
0x14000387b  cmp     cs:g_maxPrioritySoftware, eax
0x140003881  ja      short loc_140003889
0x140003883  mov     cs:g_maxPrioritySoftware, eax
0x140003889  add     cs:g_nSwThreadsRunning, ebx
0x14000388f  xor     bl, bl
0x140003891  mov     rcx, cs:WPP_GLOBAL_Control
0x140003898  lea     rax, WPP_GLOBAL_Control
0x14000389f  cmp     rcx, rax
0x1400038a2  jz      short loc_140003907
0x1400038a4  mov     eax, [rcx+2Ch]
0x1400038a7  test    al, 4
0x1400038a9  jz      short loc_140003907
0x1400038ab  mov     r9d, [rdi+9Ch]
0x1400038b2  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400038b9  mov     rcx, [rcx+18h]
0x1400038bd  mov     edx, 0Dh
0x1400038c2  call    WPP_SF_D
0x1400038c7  jmp     short loc_140003907
0x1400038c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400038d0  lea     rax, WPP_GLOBAL_Control
0x1400038d7  cmp     rcx, rax
0x1400038da  jz      short loc_1400038FF
0x1400038dc  mov     eax, [rcx+2Ch]
0x1400038df  test    al, 4
0x1400038e1  jz      short loc_1400038FF
0x1400038e3  mov     r9d, [rdi+9Ch]
0x1400038ea  lea     r8, WPP_5afc3381049b3d6e12f0c116e8be5d0a_Traceguids
0x1400038f1  mov     rcx, [rcx+18h]
0x1400038f5  mov     edx, 0Eh
0x1400038fa  call    WPP_SF_D
0x1400038ff  mov     rcx, rdi
0x140003902  call    addRequestToPriorityQueue
0x140003907  mov     dl, sil; NewIrql
0x14000390a  lea     rcx, g_spinlock; SpinLock
0x140003911  call    cs:__imp_KeReleaseSpinLock
0x140003918  nop     dword ptr [rax+rax+00h]
0x14000391d  mov     rsi, [rsp+28h+arg_8]
0x140003922  mov     al, bl
0x140003924  mov     rbx, [rsp+28h+arg_0]
0x140003929  add     rsp, 20h
0x14000392d  pop     rdi
0x14000392e  retn
```
