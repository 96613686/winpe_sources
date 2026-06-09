# SmbQuicProviderTerminate

- ea: `0x14008c184`
- end: `0x14008c291`
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
- `0x14008c184`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14008c26e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14008c26e`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x14008c19c`
- `ntoskrnl!RtlRunOnceBeginInitialize` at `0x14008c19c`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14008c253`
- `NETIO!NmrWaitForClientDeregisterComplete` at `0x14008c253`
- `NETIO!NmrClientDetachProviderComplete` at `0x14008c229`
- `NETIO!NmrClientDetachProviderComplete` at `0x14008c229`
- `NETIO!NmrDeregisterClient` at `0x14008c23d`
- `NETIO!NmrDeregisterClient` at `0x14008c23d`

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
0x14008c184  mov     [rsp+arg_0], rbx
0x14008c189  push    rdi
0x14008c18a  sub     rsp, 20h
0x14008c18e  xor     r8d, r8d; Context
0x14008c191  lea     rcx, SmbQUICInitOnce; RunOnce
0x14008c198  lea     edx, [r8+1]; Flags
0x14008c19c  call    cs:__imp_RtlRunOnceBeginInitialize
0x14008c1a3  nop     dword ptr [rax+rax+00h]
0x14008c1a8  test    eax, eax
0x14008c1aa  js      loc_14008C285
0x14008c1b0  mov     rax, cs:MsQuic
0x14008c1b7  mov     rcx, cs:Registration
0x14008c1be  mov     rax, [rax+30h]
0x14008c1c2  call    _guard_dispatch_icall
0x14008c1c7  mov     rax, cs:QuicNmrHandle
0x14008c1ce  mov     cs:Registration, 0
0x14008c1d9  mov     rcx, [rax+88h]
0x14008c1e0  mov     rax, [rcx+10h]
0x14008c1e4  mov     rcx, cs:MsQuic
0x14008c1eb  call    _guard_dispatch_icall
0x14008c1f0  mov     rdi, cs:QuicNmrHandle
0x14008c1f7  mov     cs:MsQuic, 0
0x14008c202  lea     rbx, [rdi+50h]
0x14008c206  prefetchw byte ptr [rdi+90h]
0x14008c20d  mov     al, [rdi+90h]
0x14008c213  mov     cl, al
0x14008c215  or      cl, 1
0x14008c218  lock cmpxchg [rdi+90h], cl
0x14008c220  jnz     short loc_14008C213
0x14008c222  test    al, al
0x14008c224  jz      short loc_14008C235
0x14008c226  mov     rcx, [rbx]; NmrBindingHandle
0x14008c229  call    cs:__imp_NmrClientDetachProviderComplete
0x14008c230  nop     dword ptr [rax+rax+00h]
0x14008c235  mov     rcx, [rbx]; NmrClientHandle
0x14008c238  test    rcx, rcx
0x14008c23b  jz      short loc_14008C266
0x14008c23d  call    cs:__imp_NmrDeregisterClient
0x14008c244  nop     dword ptr [rax+rax+00h]
0x14008c249  cmp     eax, 103h
0x14008c24e  jnz     short loc_14008C25F
0x14008c250  mov     rcx, [rbx]; NmrClientHandle
0x14008c253  call    cs:__imp_NmrWaitForClientDeregisterComplete
0x14008c25a  nop     dword ptr [rax+rax+00h]
0x14008c25f  mov     qword ptr [rbx], 0
0x14008c266  mov     edx, 634E514Dh; Tag
0x14008c26b  mov     rcx, rdi; P
0x14008c26e  call    cs:__imp_ExFreePoolWithTag
0x14008c275  nop     dword ptr [rax+rax+00h]
0x14008c27a  mov     cs:QuicNmrHandle, 0
0x14008c285  mov     rbx, [rsp+28h+arg_0]
0x14008c28a  add     rsp, 20h
0x14008c28e  pop     rdi
0x14008c28f  retn
```
