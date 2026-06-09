# CQueueBase::Validate(CQueueBase const *)

- ea: `0x14001a564`
- end: `0x14001a58f`
- name: `?Validate@CQueueBase@@SAJPEBV1@@Z`
- size: `43`
- prototype: `__int64 __fastcall(const struct CQueueBase *)`
- caller_count: `34`
- callee_count: `2`
- tags: ``

## callers

- `0x1400047fc`
- `0x140004990`
- `0x140004afc`
- `0x140004cb4`
- `0x1400057f4`
- `0x1400065d0`
- `0x140006808`
- `0x1400069c8`
- `0x140006bf0`
- `0x140006d50`
- `0x140006e88`
- `0x140006fd8`
- `0x14000713c`
- `0x1400075d8`
- `0x140007790`
- `0x140007840`
- `0x1400078f4`
- `0x140007a88`
- `0x140007cb8`
- `0x140007e3c`
- `0x14000881c`
- `0x140008d40`
- `0x140008dec`
- `0x140008ef0`
- `0x140009070`
- `0x140009110`
- `0x1400091b8`
- `0x140009258`
- `0x1400092f8`
- `0x1400093a0`
- `0x1400094a0`
- `0x140009540`
- `0x1400096b0`
- `0x14000a3b0`

## callees

- `0x14001a564`
- `0x140024bf0`

## pseudocode

```c
__int64 __fastcall CQueueBase::Validate(const struct CQueueBase *a1)
{
  if ( a1 )
    return (*(unsigned int (__fastcall **)(const struct CQueueBase *))(*(_QWORD *)a1 + 40LL))(a1) != 0 ? 0xC00E0056 : 0;
  else
    return 3221225480LL;
}

```

## disassembly

```asm
0x14001a564  sub     rsp, 28h
0x14001a568  test    rcx, rcx
0x14001a56b  jnz     short loc_14001A574
0x14001a56d  mov     eax, 0C0000008h
0x14001a572  jmp     short loc_14001A589
0x14001a574  mov     rax, [rcx]
0x14001a577  mov     rax, [rax+28h]
0x14001a57b  call    _guard_dispatch_icall
0x14001a580  neg     eax
0x14001a582  sbb     eax, eax
0x14001a584  and     eax, 0C00E0056h
0x14001a589  add     rsp, 28h
0x14001a58d  retn
```
