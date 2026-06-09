# MountMgrInitSiloDeviceExtension

- ea: `0x140001d04`
- end: `0x140001eb6`
- name: `MountMgrInitSiloDeviceExtension`
- size: `434`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140001ebc`

## callees

- `0x140001b30`
- `0x140001d04`
- `0x140002f80`
- `0x140003280`

## import_xrefs

- `ntoskrnl!KeInitializeMutex` at `0x140001d53`
- `ntoskrnl!KeInitializeMutex` at `0x140001d53`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001dd5`
- `ntoskrnl!KeInitializeSpinLock` at `0x140001dd5`
- `ntoskrnl!KeInitializeSemaphore` at `0x140001d6d`
- `ntoskrnl!KeInitializeSemaphore` at `0x140001db8`
- `ntoskrnl!KeInitializeSemaphore` at `0x140001d6d`
- `ntoskrnl!KeInitializeSemaphore` at `0x140001db8`
- `ntoskrnl!ExAllocatePool2` at `0x140001e31`
- `ntoskrnl!ExAllocatePool2` at `0x140001e31`
- `ntoskrnl!KeInitializeEvent` at `0x140001e01`
- `ntoskrnl!KeInitializeEvent` at `0x140001e01`

## pseudocode

```c
__int64 __fastcall MountMgrInitSiloDeviceExtension(__int64 a1, __int64 a2, __int64 a3, const void **a4)
{
  __int64 v4; // rsi
  unsigned __int16 v9; // ax
  void *Pool2; // rax
  __int64 result; // rax

  v4 = *(_QWORD *)(a2 + 64);
  memset((void *)(v4 + 48), 0, 0x148u);
  *(_QWORD *)v4 = a2;
  *(_QWORD *)(v4 + 8) = a1;
  *(_QWORD *)(v4 + 24) = v4 + 16;
  *(_QWORD *)(v4 + 16) = v4 + 16;
  *(_QWORD *)(v4 + 40) = v4 + 32;
  *(_QWORD *)(v4 + 32) = v4 + 32;
  KeInitializeMutex((PRKMUTEX)(v4 + 56), 0);
  KeInitializeSemaphore((PRKSEMAPHORE)(v4 + 112), 1, 1);
  *(_QWORD *)(v4 + 160) = v4 + 152;
  *(_QWORD *)(v4 + 152) = v4 + 152;
  *(_DWORD *)(v4 + 168) = 1;
  *(_QWORD *)(v4 + 184) = v4 + 176;
  *(_QWORD *)(v4 + 176) = v4 + 176;
  *(_QWORD *)(v4 + 208) = v4 + 200;
  *(_QWORD *)(v4 + 200) = v4 + 200;
  KeInitializeSemaphore((PRKSEMAPHORE)(v4 + 216), 0, 0x7FFFFFFF);
  *(_DWORD *)(v4 + 248) = -1;
  KeInitializeSpinLock((PKSPIN_LOCK)(v4 + 256));
  *(_QWORD *)(v4 + 296) = v4 + 288;
  *(_QWORD *)(v4 + 288) = v4 + 288;
  *(_DWORD *)(v4 + 308) = 1;
  KeInitializeEvent((PRKEVENT)(v4 + 344), NotificationEvent, 0);
  v9 = *(_WORD *)a4;
  *(_WORD *)(v4 + 264) = *(_WORD *)a4;
  v9 += 2;
  *(_WORD *)(v4 + 266) = v9;
  Pool2 = (void *)ExAllocatePool2(258, v9, 1098149453);
  *(_QWORD *)(v4 + 272) = Pool2;
  if ( Pool2 )
  {
    memmove(Pool2, a4[1], *(unsigned __int16 *)a4);
    result = 0;
    *(_WORD *)(*(_QWORD *)(v4 + 272) + 2 * ((unsigned __int64)*(unsigned __int16 *)a4 >> 1)) = 0;
    *(_QWORD *)(v4 + 336) = 1;
    *(_QWORD *)(v4 + 368) = a3;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 361);
    return 3221225626LL;
  }
  return result;
}

```

## disassembly

```asm
0x140001d04  push    rbx
0x140001d06  push    rbp
0x140001d07  push    rsi
0x140001d08  push    rdi
0x140001d09  push    r14
0x140001d0b  sub     rsp, 20h
0x140001d0f  mov     rsi, [rdx+40h]
0x140001d13  mov     rbp, r8
0x140001d16  mov     rbx, rdx
0x140001d19  mov     rdi, rcx
0x140001d1c  xor     edx, edx; Val
0x140001d1e  mov     r8d, 148h; Size
0x140001d24  mov     r14, r9
0x140001d27  lea     rcx, [rsi+30h]; void *
0x140001d2b  call    memset
0x140001d30  mov     [rsi], rbx
0x140001d33  lea     rax, [rsi+10h]
0x140001d37  mov     [rsi+8], rdi
0x140001d3b  lea     rcx, [rsi+38h]; Mutex
0x140001d3f  mov     [rax+8], rax
0x140001d43  xor     edx, edx; Level
0x140001d45  mov     [rax], rax
0x140001d48  lea     rax, [rsi+20h]
0x140001d4c  mov     [rax+8], rax
0x140001d50  mov     [rax], rax
0x140001d53  call    cs:__imp_KeInitializeMutex
0x140001d5a  nop     dword ptr [rax+rax+00h]
0x140001d5f  mov     ebx, 1
0x140001d64  lea     rcx, [rsi+70h]; Semaphore
0x140001d68  mov     r8d, ebx; Limit
0x140001d6b  mov     edx, ebx; Count
0x140001d6d  call    cs:__imp_KeInitializeSemaphore
0x140001d74  nop     dword ptr [rax+rax+00h]
0x140001d79  lea     rax, [rsi+98h]
0x140001d80  xor     edx, edx; Count
0x140001d82  mov     [rax+8], rax
0x140001d86  lea     rcx, [rsi+0D8h]; Semaphore
0x140001d8d  mov     [rax], rax
0x140001d90  mov     r8d, 7FFFFFFFh; Limit
0x140001d96  mov     [rsi+0A8h], ebx
0x140001d9c  lea     rax, [rsi+0B0h]
0x140001da3  mov     [rax+8], rax
0x140001da7  mov     [rax], rax
0x140001daa  lea     rax, [rsi+0C8h]
0x140001db1  mov     [rax+8], rax
0x140001db5  mov     [rax], rax
0x140001db8  call    cs:__imp_KeInitializeSemaphore
0x140001dbf  nop     dword ptr [rax+rax+00h]
0x140001dc4  lea     rcx, [rsi+100h]; SpinLock
0x140001dcb  mov     dword ptr [rsi+0F8h], 0FFFFFFFFh
0x140001dd5  call    cs:__imp_KeInitializeSpinLock
0x140001ddc  nop     dword ptr [rax+rax+00h]
0x140001de1  lea     rax, [rsi+120h]
0x140001de8  xor     r8d, r8d; State
0x140001deb  mov     [rax+8], rax
0x140001def  lea     rcx, [rsi+158h]; Event
0x140001df6  mov     [rax], rax
0x140001df9  xor     edx, edx; Type
0x140001dfb  mov     [rsi+134h], ebx
0x140001e01  call    cs:__imp_KeInitializeEvent
0x140001e08  nop     dword ptr [rax+rax+00h]
0x140001e0d  movzx   eax, word ptr [r14]
0x140001e11  mov     ecx, 102h
0x140001e16  mov     [rsi+108h], ax
0x140001e1d  mov     r8d, 41746E4Dh
0x140001e23  add     ax, 2
0x140001e27  movzx   edx, ax
0x140001e2a  mov     [rsi+10Ah], dx
0x140001e31  call    cs:__imp_ExAllocatePool2
0x140001e38  nop     dword ptr [rax+rax+00h]
0x140001e3d  mov     [rsi+110h], rax
0x140001e44  test    rax, rax
0x140001e47  jnz     short loc_140001E78
0x140001e49  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e50  lea     rax, WPP_GLOBAL_Control
0x140001e57  cmp     rcx, rax
0x140001e5a  jz      short loc_140001E71
0x140001e5c  mov     eax, [rcx+2Ch]
0x140001e5f  test    al, 4
0x140001e61  jz      short loc_140001E71
0x140001e63  mov     rcx, [rcx+18h]
0x140001e67  mov     edx, 169h
0x140001e6c  call    WPP_SF_
0x140001e71  mov     eax, 0C000009Ah
0x140001e76  jmp     short loc_140001EAA
0x140001e78  movzx   r8d, word ptr [r14]; Size
0x140001e7c  mov     rcx, rax; void *
0x140001e7f  mov     rdx, [r14+8]; Src
0x140001e83  call    memmove
0x140001e88  movzx   edx, word ptr [r14]
0x140001e8c  mov     rcx, [rsi+110h]
0x140001e93  shr     rdx, 1
0x140001e96  xor     eax, eax
0x140001e98  mov     [rcx+rdx*2], ax
0x140001e9c  mov     [rsi+150h], rbx
0x140001ea3  mov     [rsi+170h], rbp
0x140001eaa  add     rsp, 20h
0x140001eae  pop     r14
0x140001eb0  pop     rdi
0x140001eb1  pop     rsi
0x140001eb2  pop     rbp
0x140001eb3  pop     rbx
0x140001eb4  retn
```
