# FindCompatibleInterface(IKsPin *,IKsPin *,KSIDENTIFIER *)

- ea: `0x1800374f8`
- end: `0x180037556`
- name: `?FindCompatibleInterface@@YAJPEAUIKsPin@@0PEAUKSIDENTIFIER@@@Z`
- size: `94`
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

- `0x1800374f8`
- `0x1800375c0`
- `0x180045010`

## pseudocode

```c
__int64 __fastcall FindCompatibleInterface(struct IKsPin *a1, struct IKsPin *a2, struct KSIDENTIFIER *a3)
{
  if ( a2 && a2->KsGetCurrentCommunication(a2, 0, a3, 0) >= 0 )
    return 0;
  else
    return FindCompatiblePinFactoryIdentifier(a1, a2, 5u, a3);
}

```

## disassembly

```asm
0x1800374f8  mov     [rsp+arg_0], rbx
0x1800374fd  mov     [rsp+arg_8], rsi
0x180037502  push    rdi
0x180037503  sub     rsp, 30h
0x180037507  mov     rdi, r8
0x18003750a  mov     rbx, rdx
0x18003750d  mov     rsi, rcx
0x180037510  test    rdx, rdx
0x180037513  jz      short loc_180037531
0x180037515  mov     rax, [rdx]
0x180037518  xor     r9d, r9d
0x18003751b  xor     edx, edx
0x18003751d  mov     rcx, rbx
0x180037520  mov     rax, [rax+30h]
0x180037524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037529  test    eax, eax
0x18003752b  js      short loc_180037531
0x18003752d  xor     eax, eax
0x18003752f  jmp     short loc_180037545
0x180037531  mov     r9, rdi; struct KSIDENTIFIER *
0x180037534  mov     r8d, 5; unsigned int
0x18003753a  mov     rdx, rbx; struct IKsPin *
0x18003753d  mov     rcx, rsi; struct IKsPin *
0x180037540  call    ?FindCompatiblePinFactoryIdentifier@@YAJPEAUIKsPin@@0KPEAUKSIDENTIFIER@@@Z; FindCompatiblePinFactoryIdentifier(IKsPin *,IKsPin *,ulong,KSIDENTIFIER *)
0x180037545  mov     rbx, [rsp+38h+arg_0]
0x18003754a  mov     rsi, [rsp+38h+arg_8]
0x18003754f  add     rsp, 30h
0x180037553  pop     rdi
0x180037554  retn
```
