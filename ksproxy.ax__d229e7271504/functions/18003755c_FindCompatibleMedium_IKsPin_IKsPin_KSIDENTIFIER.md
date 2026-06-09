# FindCompatibleMedium(IKsPin *,IKsPin *,KSIDENTIFIER *)

- ea: `0x18003755c`
- end: `0x1800375b9`
- name: `?FindCompatibleMedium@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z`
- size: `93`
- prototype: `__int64 __fastcall(struct IKsPin *, struct IKsPin *, struct KSIDENTIFIER *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001aaf0`
- `0x180026de0`
- `0x180028584`
- `0x180029ad0`
- `0x180030890`

## callees

- `0x18003755c`
- `0x1800375c0`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall FindCompatibleMedium(struct IKsPin *a1, struct IKsPin *a2, struct KSIDENTIFIER *a3)
{
  __int64 result; // rax

  if ( !a2 )
    return FindCompatiblePinFactoryIdentifier(a1, a2, 6u, a3);
  result = ((__int64 (__fastcall *)(struct IKsPin *, _QWORD, _QWORD, struct KSIDENTIFIER *))a2->KsGetCurrentCommunication)(
             a2,
             0,
             0,
             a3);
  if ( (int)result < 0 )
    return FindCompatiblePinFactoryIdentifier(a1, a2, 6u, a3);
  return result;
}

```

## disassembly

```asm
0x18003755c  mov     [rsp+arg_0], rbx
0x180037561  mov     [rsp+arg_8], rsi
0x180037566  push    rdi
0x180037567  sub     rsp, 30h
0x18003756b  mov     rdi, r8
0x18003756e  mov     rbx, rdx
0x180037571  mov     rsi, rcx
0x180037574  test    rdx, rdx
0x180037577  jz      short loc_180037594
0x180037579  mov     rax, [rdx]
0x18003757c  mov     r9, r8
0x18003757f  xor     r8d, r8d
0x180037582  xor     edx, edx
0x180037584  mov     rcx, rbx
0x180037587  mov     rax, [rax+30h]
0x18003758b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037590  test    eax, eax
0x180037592  jns     short loc_1800375A8
0x180037594  mov     r9, rdi; struct KSIDENTIFIER *
0x180037597  mov     r8d, 6; unsigned int
0x18003759d  mov     rdx, rbx; struct IKsPin *
0x1800375a0  mov     rcx, rsi; struct IKsPin *
0x1800375a3  call    ?FindCompatiblePinFactoryIdentifier@@YAJPEAUIKsPin@@0KPEAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x1800375a8  mov     rbx, [rsp+38h+arg_0]
0x1800375ad  mov     rsi, [rsp+38h+arg_8]
0x1800375b2  add     rsp, 30h
0x1800375b6  pop     rdi
0x1800375b7  retn
```
