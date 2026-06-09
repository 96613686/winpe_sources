# TlsRegNotifyCallback(void *)

- ea: `0x18005f8c0`
- end: `0x18005f9d0`
- name: `?TlsRegNotifyCallback@@YAXPEAX@Z`
- size: `272`
- prototype: `void __fastcall(struct TlsRegWatcher *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18005f9d8`

## callees

- `0x18005f72c`
- `0x18005f814`
- `0x18005f8c0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005f922`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005f922`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005f97d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005f97d`
- `ntoskrnl!PsIsHostSilo` at `0x18005f90f`
- `ntoskrnl!PsIsHostSilo` at `0x18005f96a`
- `ntoskrnl!PsIsHostSilo` at `0x18005f90f`
- `ntoskrnl!PsIsHostSilo` at `0x18005f96a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18005f944`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x18005f944`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005f8e4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x18005f8e4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005f997`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x18005f997`
- `ntoskrnl!KeSetEvent` at `0x18005f9b0`
- `ntoskrnl!KeSetEvent` at `0x18005f9b0`

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
0x18005f8c0  test    rcx, rcx
0x18005f8c3  jz      locret_18005F9CE
0x18005f8c9  mov     [rsp+arg_8], rbx
0x18005f8ce  mov     [rsp+arg_10], rbp
0x18005f8d3  push    rsi
0x18005f8d4  push    rdi
0x18005f8d5  push    r14
0x18005f8d7  sub     rsp, 20h
0x18005f8db  mov     rbx, rcx
0x18005f8de  xor     edx, edx
0x18005f8e0  add     rcx, 8
0x18005f8e4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x18005f8eb  nop     dword ptr [rax+rax+00h]
0x18005f8f0  cmp     byte ptr [rbx+39h], 0
0x18005f8f4  mov     byte ptr [rbx+38h], 0
0x18005f8f8  jz      short loc_18005F903
0x18005f8fa  mov     rdi, [rbx+30h]
0x18005f8fe  jmp     loc_18005F991
0x18005f903  mov     rsi, [rbx+40h]
0x18005f907  xor     edi, edi
0x18005f909  mov     rcx, rsi
0x18005f90c  xor     r14d, r14d
0x18005f90f  call    cs:__imp_PsIsHostSilo
0x18005f916  nop     dword ptr [rax+rax+00h]
0x18005f91b  test    al, al
0x18005f91d  jnz     short loc_18005F931
0x18005f91f  mov     rcx, rsi
0x18005f922  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005f929  nop     dword ptr [rax+rax+00h]
0x18005f92e  mov     r14, rax
0x18005f931  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x18005f937  lea     r8, [rsp+38h+arg_0]
0x18005f93c  mov     rcx, rsi
0x18005f93f  mov     [rsp+38h+arg_0], rdi
0x18005f944  call    cs:__imp_PsGetPermanentSiloContext
0x18005f94b  nop     dword ptr [rax+rax+00h]
0x18005f950  test    eax, eax
0x18005f952  js      short loc_18005F967
0x18005f954  mov     rcx, [rsp+38h+arg_0]
0x18005f959  test    rcx, rcx
0x18005f95c  jz      short loc_18005F967
0x18005f95e  add     rcx, 8; this
0x18005f962  call    ?ReadValues@TlsMessageSizeLimit@@QEAAXXZ; TlsMessageSizeLimit::ReadValues(void)
0x18005f967  mov     rcx, rsi
0x18005f96a  call    cs:__imp_PsIsHostSilo
0x18005f971  nop     dword ptr [rax+rax+00h]
0x18005f976  test    al, al
0x18005f978  jnz     short loc_18005F989
0x18005f97a  mov     rcx, r14
0x18005f97d  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005f984  nop     dword ptr [rax+rax+00h]
0x18005f989  mov     rcx, rbx; struct TlsRegWatcher *
0x18005f98c  call    ?RegisterRegWatcher@@YAJPEAUTlsRegWatcher@@@Z; RegisterRegWatcher(TlsRegWatcher *)
0x18005f991  xor     edx, edx
0x18005f993  lea     rcx, [rbx+8]
0x18005f997  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18005f99e  nop     dword ptr [rax+rax+00h]
0x18005f9a3  test    rdi, rdi
0x18005f9a6  jz      short loc_18005F9BC
0x18005f9a8  xor     r8d, r8d; Wait
0x18005f9ab  xor     edx, edx; Increment
0x18005f9ad  mov     rcx, rdi; Event
0x18005f9b0  call    cs:__imp_KeSetEvent
0x18005f9b7  nop     dword ptr [rax+rax+00h]
0x18005f9bc  mov     rbx, [rsp+38h+arg_8]
0x18005f9c1  mov     rbp, [rsp+38h+arg_10]
0x18005f9c6  add     rsp, 20h
0x18005f9ca  pop     r14
0x18005f9cc  pop     rdi
0x18005f9cd  pop     rsi
0x18005f9ce  retn
```
