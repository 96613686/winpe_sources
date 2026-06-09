# PrSend

- ea: `0x140015bb0`
- end: `0x140015ce3`
- name: `PrSend`
- size: `307`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1400035b8`
- `0x14000e7b0`
- `0x1400112e8`
- `0x140011560`
- `0x14001169c`
- `0x140016534`
- `0x140017a00`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x14000400c`
- `0x140006b80`
- `0x140015bb0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140015c30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015c72`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015c30`
- `ntoskrnl!KeReleaseSpinLock` at `0x140015c72`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015c00`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140015c00`
- `NDIS!NdisSendNetBufferLists` at `0x140015c62`
- `NDIS!NdisSendNetBufferLists` at `0x140015c62`

## pseudocode

```c
__int64 __fastcall PrSend(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  bool v5; // zf
  KSPIN_LOCK *v6; // rcx
  unsigned int v7; // esi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x5Fu,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v5 = *(_DWORD *)(a1 + 400) == 2;
  v6 = (KSPIN_LOCK *)(a1 + 384);
  *(_BYTE *)(a1 + 392) = v4;
  if ( v5 )
  {
    v7 = 259;
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 408));
    KeReleaseSpinLock(v6, *(_BYTE *)(a1 + 392));
    *(_QWORD *)(*(_QWORD *)(a2 + 136) + 120LL) = *(_QWORD *)(a1 + 344);
    NdisSendNetBufferLists(*(NDIS_HANDLE *)(a1 + 344), *(PNET_BUFFER_LIST *)(a2 + 136), 0, 0);
  }
  else
  {
    KeReleaseSpinLock(v6, v4);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(a2 + 8))(a2);
    DereferenceBinding(a1);
    v7 = -1073741823;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x60u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids,
      v7);
  }
  return v7;
}

```

## disassembly

```asm
0x140015bb0  push    rbx
0x140015bb2  push    rbp
0x140015bb3  push    rsi
0x140015bb4  push    rdi
0x140015bb5  push    r15
0x140015bb7  sub     rsp, 20h
0x140015bbb  mov     rdi, rdx
0x140015bbe  mov     rbx, rcx
0x140015bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x140015bc8  lea     r15, WPP_GLOBAL_Control
0x140015bcf  cmp     rcx, r15
0x140015bd2  jz      short loc_140015BF6
0x140015bd4  mov     eax, [rcx+2Ch]
0x140015bd7  test    al, 4
0x140015bd9  jz      short loc_140015BF6
0x140015bdb  cmp     byte ptr [rcx+29h], 4
0x140015bdf  jb      short loc_140015BF6
0x140015be1  mov     rcx, [rcx+18h]
0x140015be5  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015bec  mov     edx, 5Fh ; '_'
0x140015bf1  call    WPP_SF_
0x140015bf6  lea     rbp, [rbx+180h]
0x140015bfd  mov     rcx, rbp; SpinLock
0x140015c00  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140015c07  nop     dword ptr [rax+rax+00h]
0x140015c0c  cmp     dword ptr [rbx+190h], 2
0x140015c13  mov     rcx, rbp; SpinLock
0x140015c16  mov     [rbx+188h], al
0x140015c1c  jnz     short loc_140015C70
0x140015c1e  mov     esi, 103h
0x140015c23  lock inc dword ptr [rbx+198h]
0x140015c2a  mov     dl, [rbx+188h]; NewIrql
0x140015c30  call    cs:__imp_KeReleaseSpinLock
0x140015c37  nop     dword ptr [rax+rax+00h]
0x140015c3c  mov     rcx, [rdi+88h]
0x140015c43  xor     r9d, r9d; SendFlags
0x140015c46  mov     rax, [rbx+158h]
0x140015c4d  xor     r8d, r8d; PortNumber
0x140015c50  mov     [rcx+78h], rax
0x140015c54  mov     rdx, [rdi+88h]; NetBufferLists
0x140015c5b  mov     rcx, [rbx+158h]; NdisBindingHandle
0x140015c62  call    cs:__imp_NdisSendNetBufferLists
0x140015c69  nop     dword ptr [rax+rax+00h]
0x140015c6e  jmp     short loc_140015CA3
0x140015c70  mov     dl, al; NewIrql
0x140015c72  call    cs:__imp_KeReleaseSpinLock
0x140015c79  nop     dword ptr [rax+rax+00h]
0x140015c7e  or      eax, 0FFFFFFFFh
0x140015c81  lock xadd [rdi], eax
0x140015c85  cmp     eax, 1
0x140015c88  jnz     short loc_140015C96
0x140015c8a  mov     rax, [rdi+8]
0x140015c8e  mov     rcx, rdi
0x140015c91  call    _guard_dispatch_icall
0x140015c96  mov     rcx, rbx
0x140015c99  call    DereferenceBinding
0x140015c9e  mov     esi, 0C0000001h
0x140015ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x140015caa  cmp     rcx, r15
0x140015cad  jz      short loc_140015CD5
0x140015caf  mov     edx, [rcx+2Ch]
0x140015cb2  test    dl, 4
0x140015cb5  jz      short loc_140015CD5
0x140015cb7  cmp     byte ptr [rcx+29h], 4
0x140015cbb  jb      short loc_140015CD5
0x140015cbd  mov     rcx, [rcx+18h]
0x140015cc1  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140015cc8  mov     edx, 60h ; '`'
0x140015ccd  mov     r9d, esi
0x140015cd0  call    WPP_SF_d
0x140015cd5  mov     eax, esi
0x140015cd7  add     rsp, 20h
0x140015cdb  pop     r15
0x140015cdd  pop     rdi
0x140015cde  pop     rsi
0x140015cdf  pop     rbp
0x140015ce0  pop     rbx
0x140015ce1  retn
```
