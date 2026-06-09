# CdDeleteInternalStream

- ea: `0x14000bc18`
- end: `0x14000bcf0`
- name: `CdDeleteInternalStream`
- size: `216`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000bcf8`
- `0x14001943c`

## callees

- `0x14000bc18`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x14000bc4d`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000bc4d`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bc97`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000bc97`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bcd3`
- `ntoskrnl!ObfDereferenceObject` at `0x14000bcd3`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14000bcb7`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14000bcb7`

## pseudocode

```c
void __fastcall CdDeleteInternalStream(__int64 a1, __int64 a2)
{
  struct _KTHREAD *CurrentThread; // rbx
  __int64 v3; // rsi
  int v5; // eax
  __int64 v6; // rbx
  struct _FAST_MUTEX *v7; // rcx

  CurrentThread = KeGetCurrentThread();
  v3 = a2 + 200;
  if ( CurrentThread != *(struct _KTHREAD **)(a2 + 184) )
  {
    ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)v3 + 136LL));
    *(_QWORD *)(a2 + 184) = CurrentThread;
  }
  v5 = *(_DWORD *)(a2 + 192);
  v6 = *(_QWORD *)(a2 + 472);
  *(_QWORD *)(a2 + 472) = 0;
  *(_DWORD *)(a2 + 192) = v5;
  if ( !v5 )
  {
    v7 = (struct _FAST_MUTEX *)(*(_QWORD *)v3 + 136LL);
    *(_QWORD *)(a2 + 184) = 0;
    ExReleaseFastMutex(v7);
  }
  if ( v6 )
  {
    if ( *(_QWORD *)(v6 + 48) )
      CcUninitializeCacheMap((PFILE_OBJECT)v6, 0, 0);
    *(_QWORD *)(v6 + 96) = 0;
    *(_DWORD *)(v6 + 88) = 0;
    ObfDereferenceObject((PVOID)v6);
  }
}

```

## disassembly

```asm
0x14000bc18  mov     [rsp+arg_0], rbx
0x14000bc1d  mov     [rsp+arg_8], rsi
0x14000bc22  push    rdi
0x14000bc23  sub     rsp, 20h
0x14000bc27  mov     rbx, gs:188h
0x14000bc30  lea     rsi, [rdx+0C8h]
0x14000bc37  mov     rdi, rdx
0x14000bc3a  cmp     rbx, [rdx+0B8h]
0x14000bc41  jz      short loc_14000BC60
0x14000bc43  mov     rcx, [rsi]
0x14000bc46  add     rcx, 88h; FastMutex
0x14000bc4d  call    cs:__imp_ExAcquireFastMutex
0x14000bc54  nop     dword ptr [rax+rax+00h]
0x14000bc59  mov     [rdi+0B8h], rbx
0x14000bc60  mov     eax, [rdi+0C0h]
0x14000bc66  mov     rbx, [rdi+1D8h]
0x14000bc6d  mov     qword ptr [rdi+1D8h], 0
0x14000bc78  mov     [rdi+0C0h], eax
0x14000bc7e  test    eax, eax
0x14000bc80  jnz     short loc_14000BCA3
0x14000bc82  mov     rcx, [rsi]
0x14000bc85  add     rcx, 88h; FastMutex
0x14000bc8c  mov     qword ptr [rdi+0B8h], 0
0x14000bc97  call    cs:__imp_ExReleaseFastMutex
0x14000bc9e  nop     dword ptr [rax+rax+00h]
0x14000bca3  test    rbx, rbx
0x14000bca6  jz      short loc_14000BCDF
0x14000bca8  cmp     qword ptr [rbx+30h], 0
0x14000bcad  jz      short loc_14000BCC3
0x14000bcaf  xor     r8d, r8d; UninitializeEvent
0x14000bcb2  xor     edx, edx; TruncateSize
0x14000bcb4  mov     rcx, rbx; FileObject
0x14000bcb7  call    cs:__imp_CcUninitializeCacheMap
0x14000bcbe  nop     dword ptr [rax+rax+00h]
0x14000bcc3  xor     eax, eax
0x14000bcc5  mov     qword ptr [rbx+60h], 0
0x14000bccd  mov     rcx, rbx; Object
0x14000bcd0  mov     [rbx+58h], eax
0x14000bcd3  call    cs:__imp_ObfDereferenceObject
0x14000bcda  nop     dword ptr [rax+rax+00h]
0x14000bcdf  mov     rbx, [rsp+28h+arg_0]
0x14000bce4  mov     rsi, [rsp+28h+arg_8]
0x14000bce9  add     rsp, 20h
0x14000bced  pop     rdi
0x14000bcee  retn
```
