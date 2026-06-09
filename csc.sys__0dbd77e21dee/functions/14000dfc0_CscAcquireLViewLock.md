# CscAcquireLViewLock

- ea: `0x14000dfc0`
- end: `0x14000e01c`
- name: `CscAcquireLViewLock`
- size: `92`
- prototype: `struct _KTHREAD *__fastcall(__int64)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x14000dedc`
- `0x140020634`
- `0x14004cb40`
- `0x14004d450`
- `0x14004de28`
- `0x140062b70`
- `0x140070c70`
- `0x140075b10`
- `0x140075f70`
- `0x1400761e0`
- `0x140076458`
- `0x140076cb0`
- `0x14007f960`
- `0x140087fd8`
- `0x14008caec`

## callees

- `0x14000dfc0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000e00c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000e00c`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000dfce`
- `ntoskrnl!KeAreApcsDisabled` at `0x14000dfce`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000dfe2`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14000dfe2`

## pseudocode

```c
struct _KTHREAD *__fastcall CscAcquireLViewLock(__int64 a1)
{
  __int64 v1; // rbx
  BOOLEAN v2; // al
  struct _FAST_MUTEX *v3; // rcx
  char v4; // al
  struct _KTHREAD *result; // rax

  v1 = *(_QWORD *)(a1 + 48);
  v2 = KeAreApcsDisabled();
  v3 = (struct _FAST_MUTEX *)(v1 + 56);
  if ( v2 )
  {
    ExAcquireFastMutexUnsafe(v3);
    v4 = 1;
  }
  else
  {
    ExAcquireFastMutex(v3);
    v4 = 0;
  }
  *(_BYTE *)(v1 + 120) = v4;
  result = KeGetCurrentThread();
  *(_QWORD *)(v1 + 112) = result;
  return result;
}

```

## disassembly

```asm
0x14000dfc0  mov     [rsp+arg_0], rbx
0x14000dfc5  push    rdi
0x14000dfc6  sub     rsp, 20h
0x14000dfca  mov     rbx, [rcx+30h]
0x14000dfce  call    cs:__imp_KeAreApcsDisabled
0x14000dfd5  nop     dword ptr [rax+rax+00h]
0x14000dfda  lea     rcx, [rbx+38h]; FastMutex
0x14000dfde  test    al, al
0x14000dfe0  jz      short loc_14000E00C
0x14000dfe2  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000dfe9  nop     dword ptr [rax+rax+00h]
0x14000dfee  mov     al, 1
0x14000dff0  mov     [rbx+78h], al
0x14000dff3  mov     rax, gs:188h
0x14000dffc  mov     [rbx+70h], rax
0x14000e000  mov     rbx, [rsp+28h+arg_0]
0x14000e005  add     rsp, 20h
0x14000e009  pop     rdi
0x14000e00a  retn
0x14000e00c  call    cs:__imp_ExAcquireFastMutex
0x14000e013  nop     dword ptr [rax+rax+00h]
0x14000e018  xor     al, al
0x14000e01a  jmp     short loc_14000DFF0
```
