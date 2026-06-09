# TlsRegNotifyCallback(void *)

- ea: `0x18005efd0`
- end: `0x18005f0e0`
- name: `?TlsRegNotifyCallback@@YAXPEAX@Z`
- size: `272`
- prototype: `void __fastcall(struct TlsRegWatcher *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005f0e8`

## callees

- `0x18005ee3c`
- `0x18005ef24`
- `0x18005efd0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005f032`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005f032`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005f08d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005f08d`
- `ntoskrnl!PsIsHostSilo` at `0x18005f01f`
- `ntoskrnl!PsIsHostSilo` at `0x18005f07a`
- `ntoskrnl!PsIsHostSilo` at `0x18005f01f`
- `ntoskrnl!PsIsHostSilo` at `0x18005f07a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18005f054`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18005f054`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005eff4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005eff4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005f0a7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005f0a7`
- `ntoskrnl!KeSetEvent` at `0x18005f0c0`
- `ntoskrnl!KeSetEvent` at `0x18005f0c0`

## pseudocode

```c
void __fastcall TlsRegNotifyCallback(struct TlsRegWatcher *a1)
{
  bool v2; // zf
  struct _KEVENT *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // r14
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
  {
    ExAcquirePushLockExclusiveEx((char *)a1 + 8, 0);
    v2 = *((_BYTE *)a1 + 57) == 0;
    *((_BYTE *)a1 + 56) = 0;
    if ( v2 )
    {
      v4 = *((_QWORD *)a1 + 8);
      v3 = 0;
      v5 = 0;
      if ( !(unsigned __int8)PsIsHostSilo(v4) )
        v5 = PsAttachSiloToCurrentThread(v4);
      v6 = 0;
      if ( (int)PsGetPermanentSiloContext(v4, g_tlsCtxtSlot, &v6) >= 0 && v6 )
        TlsMessageSizeLimit::ReadValues((TlsMessageSizeLimit *)(v6 + 8));
      if ( !(unsigned __int8)PsIsHostSilo(v4) )
        PsDetachSiloFromCurrentThread(v5);
      RegisterRegWatcher(a1);
    }
    else
    {
      v3 = (struct _KEVENT *)*((_QWORD *)a1 + 6);
    }
    ExReleasePushLockExclusiveEx((char *)a1 + 8, 0);
    if ( v3 )
      KeSetEvent(v3, 0, 0);
  }
}

```

## disassembly

```asm
0x18005efd0  test    rcx, rcx
0x18005efd3  jz      locret_18005F0DE
0x18005efd9  mov     [rsp+arg_8], rbx
0x18005efde  mov     [rsp+arg_10], rbp
0x18005efe3  push    rsi
0x18005efe4  push    rdi
0x18005efe5  push    r14
0x18005efe7  sub     rsp, 20h
0x18005efeb  mov     rbx, rcx
0x18005efee  xor     edx, edx
0x18005eff0  add     rcx, 8
0x18005eff4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18005effb  nop     dword ptr [rax+rax+00h]
0x18005f000  cmp     byte ptr [rbx+39h], 0
0x18005f004  mov     byte ptr [rbx+38h], 0
0x18005f008  jz      short loc_18005F013
0x18005f00a  mov     rdi, [rbx+30h]
0x18005f00e  jmp     loc_18005F0A1
0x18005f013  mov     rsi, [rbx+40h]
0x18005f017  xor     edi, edi
0x18005f019  mov     rcx, rsi
0x18005f01c  xor     r14d, r14d
0x18005f01f  call    cs:__imp_PsIsHostSilo
0x18005f026  nop     dword ptr [rax+rax+00h]
0x18005f02b  test    al, al
0x18005f02d  jnz     short loc_18005F041
0x18005f02f  mov     rcx, rsi
0x18005f032  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005f039  nop     dword ptr [rax+rax+00h]
0x18005f03e  mov     r14, rax
0x18005f041  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005f047  lea     r8, [rsp+38h+arg_0]
0x18005f04c  mov     rcx, rsi
0x18005f04f  mov     [rsp+38h+arg_0], rdi
0x18005f054  call    cs:__imp_PsGetPermanentSiloContext
0x18005f05b  nop     dword ptr [rax+rax+00h]
0x18005f060  test    eax, eax
0x18005f062  js      short loc_18005F077
0x18005f064  mov     rcx, [rsp+38h+arg_0]
0x18005f069  test    rcx, rcx
0x18005f06c  jz      short loc_18005F077
0x18005f06e  add     rcx, 8; this
0x18005f072  call    ?ReadValues@TlsMessageSizeLimit@@QEAAXXZ; TlsMessageSizeLimit::ReadValues(void)
0x18005f077  mov     rcx, rsi
0x18005f07a  call    cs:__imp_PsIsHostSilo
0x18005f081  nop     dword ptr [rax+rax+00h]
0x18005f086  test    al, al
0x18005f088  jnz     short loc_18005F099
0x18005f08a  mov     rcx, r14
0x18005f08d  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005f094  nop     dword ptr [rax+rax+00h]
0x18005f099  mov     rcx, rbx; struct TlsRegWatcher *
0x18005f09c  call    ?RegisterRegWatcher@@YAJPEAUTlsRegWatcher@@@Z; RegisterRegWatcher(TlsRegWatcher *)
0x18005f0a1  xor     edx, edx
0x18005f0a3  lea     rcx, [rbx+8]
0x18005f0a7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18005f0ae  nop     dword ptr [rax+rax+00h]
0x18005f0b3  test    rdi, rdi
0x18005f0b6  jz      short loc_18005F0CC
0x18005f0b8  xor     r8d, r8d; Wait
0x18005f0bb  xor     edx, edx; Increment
0x18005f0bd  mov     rcx, rdi; Event
0x18005f0c0  call    cs:__imp_KeSetEvent
0x18005f0c7  nop     dword ptr [rax+rax+00h]
0x18005f0cc  mov     rbx, [rsp+38h+arg_8]
0x18005f0d1  mov     rbp, [rsp+38h+arg_10]
0x18005f0d6  add     rsp, 20h
0x18005f0da  pop     r14
0x18005f0dc  pop     rdi
0x18005f0dd  pop     rsi
0x18005f0de  retn
```
