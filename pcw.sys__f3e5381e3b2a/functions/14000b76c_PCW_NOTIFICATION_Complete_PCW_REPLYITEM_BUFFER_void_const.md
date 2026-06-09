# PCW_NOTIFICATION::Complete(PCW_REPLYITEM_BUFFER *,void const *)

- ea: `0x14000b76c`
- end: `0x14000b819`
- name: `?Complete@PCW_NOTIFICATION@@QEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z`
- size: `173`
- prototype: `__int64 __fastcall(PCW_NOTIFICATION *__hidden this, struct PCW_REPLYITEM_BUFFER *, const void *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b654`
- `0x14000b820`
- `0x14000c08c`

## callees

- `0x14000b76c`
- `0x14000ba08`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b784`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b784`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b7fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b7fa`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b795`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b795`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b7ee`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b7ee`
- `ntoskrnl!KeSetEvent` at `0x14000b7dd`
- `ntoskrnl!KeSetEvent` at `0x14000b7dd`

## pseudocode

```c
__int64 __fastcall PCW_NOTIFICATION::Complete(PCW_NOTIFICATION *this, struct PCW_REPLYITEM_BUFFER *a2, const void *a3)
{
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(this, 0);
  if ( *((_BYTE *)this + 68) )
  {
    LODWORD(a2) = 0;
  }
  else
  {
    if ( a2 )
    {
      LODWORD(a2) = PCW_NOTIFICATION::CopyToNotificationBuffer(this, a2, a3);
      if ( (int)a2 >= 0 )
        ++*((_DWORD *)this + 18);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 7, 0xFFFFFFFF) == 1 )
      KeSetEvent(*((PRKEVENT *)this + 1), 0, 0);
  }
  ExReleasePushLockExclusiveEx(this, 0);
  KeLeaveCriticalRegion();
  return (unsigned int)a2;
}

```

## disassembly

```asm
0x14000b76c  mov     [rsp+arg_0], rbx
0x14000b771  mov     [rsp+arg_8], rsi
0x14000b776  push    rdi
0x14000b777  sub     rsp, 20h
0x14000b77b  mov     rsi, r8
0x14000b77e  mov     rdi, rdx
0x14000b781  mov     rbx, rcx
0x14000b784  call    cs:__imp_KeEnterCriticalRegion
0x14000b78b  nop     dword ptr [rax+rax+00h]
0x14000b790  xor     edx, edx
0x14000b792  mov     rcx, rbx
0x14000b795  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b79c  nop     dword ptr [rax+rax+00h]
0x14000b7a1  cmp     byte ptr [rbx+44h], 0
0x14000b7a5  jz      short loc_14000B7AB
0x14000b7a7  xor     edi, edi
0x14000b7a9  jmp     short loc_14000B7E9
0x14000b7ab  test    rdi, rdi
0x14000b7ae  jz      short loc_14000B7C7
0x14000b7b0  mov     r8, rsi; void *
0x14000b7b3  mov     rdx, rdi; struct PCW_REPLYITEM_BUFFER *
0x14000b7b6  mov     rcx, rbx; this
0x14000b7b9  call    ?CopyToNotificationBuffer@PCW_NOTIFICATION@@AEAAJPEAUPCW_REPLYITEM_BUFFER@@PEBX@Z; PCW_NOTIFICATION::CopyToNotificationBuffer(PCW_REPLYITEM_BUFFER *,void const *)
0x14000b7be  mov     edi, eax
0x14000b7c0  test    eax, eax
0x14000b7c2  js      short loc_14000B7C7
0x14000b7c4  inc     dword ptr [rbx+48h]
0x14000b7c7  or      ecx, 0FFFFFFFFh
0x14000b7ca  lock xadd [rbx+1Ch], ecx
0x14000b7cf  cmp     ecx, 1
0x14000b7d2  jnz     short loc_14000B7E9
0x14000b7d4  mov     rcx, [rbx+8]; Event
0x14000b7d8  xor     r8d, r8d; Wait
0x14000b7db  xor     edx, edx; Increment
0x14000b7dd  call    cs:__imp_KeSetEvent
0x14000b7e4  nop     dword ptr [rax+rax+00h]
0x14000b7e9  xor     edx, edx
0x14000b7eb  mov     rcx, rbx
0x14000b7ee  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b7f5  nop     dword ptr [rax+rax+00h]
0x14000b7fa  call    cs:__imp_KeLeaveCriticalRegion
0x14000b801  nop     dword ptr [rax+rax+00h]
0x14000b806  mov     rbx, [rsp+28h+arg_0]
0x14000b80b  mov     eax, edi
0x14000b80d  mov     rsi, [rsp+28h+arg_8]
0x14000b812  add     rsp, 20h
0x14000b816  pop     rdi
0x14000b817  retn
```
