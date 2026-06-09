# TlsRegNotifyCallback(void *)

- ea: `0x1800691a0`
- end: `0x1800692b0`
- name: `?TlsRegNotifyCallback@@YAXPEAX@Z`
- size: `272`
- prototype: `void __fastcall(struct TlsRegWatcher *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800692b8`

## callees

- `0x18006900c`
- `0x1800690f4`
- `0x1800691a0`

## import_xrefs

- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180069202`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180069202`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006925d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006925d`
- `ntoskrnl!PsIsHostSilo` at `0x1800691ef`
- `ntoskrnl!PsIsHostSilo` at `0x18006924a`
- `ntoskrnl!PsIsHostSilo` at `0x1800691ef`
- `ntoskrnl!PsIsHostSilo` at `0x18006924a`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180069224`
- `ntoskrnl!PsGetPermanentSiloContext` at `0x180069224`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800691c4`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1800691c4`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180069277`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x180069277`
- `ntoskrnl!KeSetEvent` at `0x180069290`
- `ntoskrnl!KeSetEvent` at `0x180069290`

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
0x1800691a0  test    rcx, rcx
0x1800691a3  jz      locret_1800692AE
0x1800691a9  mov     [rsp+arg_8], rbx
0x1800691ae  mov     [rsp+arg_10], rbp
0x1800691b3  push    rsi
0x1800691b4  push    rdi
0x1800691b5  push    r14
0x1800691b7  sub     rsp, 20h
0x1800691bb  mov     rbx, rcx
0x1800691be  xor     edx, edx
0x1800691c0  add     rcx, 8
0x1800691c4  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1800691cb  nop     dword ptr [rax+rax+00h]
0x1800691d0  cmp     byte ptr [rbx+39h], 0
0x1800691d4  mov     byte ptr [rbx+38h], 0
0x1800691d8  jz      short loc_1800691E3
0x1800691da  mov     rdi, [rbx+30h]
0x1800691de  jmp     loc_180069271
0x1800691e3  mov     rsi, [rbx+40h]
0x1800691e7  xor     edi, edi
0x1800691e9  mov     rcx, rsi
0x1800691ec  xor     r14d, r14d
0x1800691ef  call    cs:__imp_PsIsHostSilo
0x1800691f6  nop     dword ptr [rax+rax+00h]
0x1800691fb  test    al, al
0x1800691fd  jnz     short loc_180069211
0x1800691ff  mov     rcx, rsi
0x180069202  call    cs:__imp_PsAttachSiloToCurrentThread
0x180069209  nop     dword ptr [rax+rax+00h]
0x18006920e  mov     r14, rax
0x180069211  mov     edx, cs:?g_tlsCtxtSlot@@3KA; ulong g_tlsCtxtSlot
0x180069217  lea     r8, [rsp+38h+arg_0]
0x18006921c  mov     rcx, rsi
0x18006921f  mov     [rsp+38h+arg_0], rdi
0x180069224  call    cs:__imp_PsGetPermanentSiloContext
0x18006922b  nop     dword ptr [rax+rax+00h]
0x180069230  test    eax, eax
0x180069232  js      short loc_180069247
0x180069234  mov     rcx, [rsp+38h+arg_0]
0x180069239  test    rcx, rcx
0x18006923c  jz      short loc_180069247
0x18006923e  add     rcx, 8; this
0x180069242  call    ?ReadValues@TlsMessageSizeLimit@@QEAAXXZ; TlsMessageSizeLimit::ReadValues(void)
0x180069247  mov     rcx, rsi
0x18006924a  call    cs:__imp_PsIsHostSilo
0x180069251  nop     dword ptr [rax+rax+00h]
0x180069256  test    al, al
0x180069258  jnz     short loc_180069269
0x18006925a  mov     rcx, r14
0x18006925d  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180069264  nop     dword ptr [rax+rax+00h]
0x180069269  mov     rcx, rbx; struct TlsRegWatcher *
0x18006926c  call    ?RegisterRegWatcher@@YAJPEAUTlsRegWatcher@@@Z; RegisterRegWatcher(TlsRegWatcher *)
0x180069271  xor     edx, edx
0x180069273  lea     rcx, [rbx+8]
0x180069277  call    cs:__imp_ExReleasePushLockExclusiveEx
0x18006927e  nop     dword ptr [rax+rax+00h]
0x180069283  test    rdi, rdi
0x180069286  jz      short loc_18006929C
0x180069288  xor     r8d, r8d; Wait
0x18006928b  xor     edx, edx; Increment
0x18006928d  mov     rcx, rdi; Event
0x180069290  call    cs:__imp_KeSetEvent
0x180069297  nop     dword ptr [rax+rax+00h]
0x18006929c  mov     rbx, [rsp+38h+arg_8]
0x1800692a1  mov     rbp, [rsp+38h+arg_10]
0x1800692a6  add     rsp, 20h
0x1800692aa  pop     r14
0x1800692ac  pop     rdi
0x1800692ad  pop     rsi
0x1800692ae  retn
```
