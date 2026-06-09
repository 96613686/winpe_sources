# SmbQuicProviderTerminate

- ea: `0x14008c1d4`
- end: `0x14008c2e1`
- name: `SmbQuicProviderTerminate`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140080ce4`

## callees

- `0x140059ea0`
- `0x14008c1d4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008c2be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c2be`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x14008c1ec`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x14008c1ec`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14008c2a3`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14008c2a3`
- `NETIO!NmrClientDetachProviderComplete` at `0x14008c279`
- `NETIO!NmrClientDetachProviderComplete` at `0x14008c279`
- `NETIO!NmrDeregisterClient` at `0x14008c28d`
- `NETIO!NmrDeregisterClient` at `0x14008c28d`

## pseudocode

```c
void SmbQuicProviderTerminate()
{
  PVOID v0; // rdi
  HANDLE *v1; // rbx

  if ( RtlRunOnceBeginInitialize(&SmbQUICInitOnce, 1u, 0) >= 0 )
  {
    (*(void (__fastcall **)(__int64))(MsQuic + 48))(Registration);
    Registration = 0;
    (*(void (__fastcall **)(__int64))(*((_QWORD *)QuicNmrHandle + 17) + 16LL))(MsQuic);
    v0 = QuicNmrHandle;
    MsQuic = 0;
    v1 = (HANDLE *)((char *)QuicNmrHandle + 80);
    _m_prefetchw((char *)QuicNmrHandle + 144);
    if ( _InterlockedOr8((volatile signed __int8 *)QuicNmrHandle + 144, 1u) )
      NmrClientDetachProviderComplete(*v1);
    if ( *v1 )
    {
      if ( NmrDeregisterClient(*v1) == 259 )
        NmrWaitForClientDeregisterComplete(*v1);
      *v1 = 0;
    }
    ExFreePoolWithTag(v0, 0x634E514Du);
    QuicNmrHandle = 0;
  }
}

```

## disassembly

```asm
0x14008c1d4  mov     [rsp+arg_0], rbx
0x14008c1d9  push    rdi
0x14008c1da  sub     rsp, 20h
0x14008c1de  xor     r8d, r8d; Context
0x14008c1e1  lea     rcx, SmbQUICInitOnce; RunOnce
0x14008c1e8  lea     edx, [r8+1]; Flags
0x14008c1ec  call    cs:__imp_RtlRunOnceBeginInitialize
0x14008c1f3  nop     dword ptr [rax+rax+00h]
0x14008c1f8  test    eax, eax
0x14008c1fa  js      loc_14008C2D5
0x14008c200  mov     rax, cs:MsQuic
0x14008c207  mov     rcx, cs:Registration
0x14008c20e  mov     rax, [rax+30h]
0x14008c212  call    _guard_dispatch_icall
0x14008c217  mov     rax, cs:QuicNmrHandle
0x14008c21e  mov     cs:Registration, 0
0x14008c229  mov     rcx, [rax+88h]
0x14008c230  mov     rax, [rcx+10h]
0x14008c234  mov     rcx, cs:MsQuic
0x14008c23b  call    _guard_dispatch_icall
0x14008c240  mov     rdi, cs:QuicNmrHandle
0x14008c247  mov     cs:MsQuic, 0
0x14008c252  lea     rbx, [rdi+50h]
0x14008c256  prefetchw byte ptr [rdi+90h]
0x14008c25d  mov     al, [rdi+90h]
0x14008c263  mov     cl, al
0x14008c265  or      cl, 1
0x14008c268  lock cmpxchg [rdi+90h], cl
0x14008c270  jnz     short loc_14008C263
0x14008c272  test    al, al
0x14008c274  jz      short loc_14008C285
0x14008c276  mov     rcx, [rbx]; NmrBindingHandle
0x14008c279  call    cs:__imp_NmrClientDetachProviderComplete
0x14008c280  nop     dword ptr [rax+rax+00h]
0x14008c285  mov     rcx, [rbx]; NmrClientHandle
0x14008c288  test    rcx, rcx
0x14008c28b  jz      short loc_14008C2B6
0x14008c28d  call    cs:__imp_NmrDeregisterClient
0x14008c294  nop     dword ptr [rax+rax+00h]
0x14008c299  cmp     eax, 103h
0x14008c29e  jnz     short loc_14008C2AF
0x14008c2a0  mov     rcx, [rbx]; NmrClientHandle
0x14008c2a3  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14008c2aa  nop     dword ptr [rax+rax+00h]
0x14008c2af  mov     qword ptr [rbx], 0
0x14008c2b6  mov     edx, 634E514Dh; Tag
0x14008c2bb  mov     rcx, rdi; P
0x14008c2be  call    cs:__imp_ExFreePoolWithTag
0x14008c2c5  nop     dword ptr [rax+rax+00h]
0x14008c2ca  mov     cs:QuicNmrHandle, 0
0x14008c2d5  mov     rbx, [rsp+28h+arg_0]
0x14008c2da  add     rsp, 20h
0x14008c2de  pop     rdi
0x14008c2df  retn
```
