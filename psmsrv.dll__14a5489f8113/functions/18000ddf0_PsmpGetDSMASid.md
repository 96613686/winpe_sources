# PsmpGetDSMASid

- ea: `0x18000ddf0`
- end: `0x18000de3f`
- name: `PsmpGetDSMASid`
- size: `79`
- prototype: `__int64 __fastcall(PSID DestinationSid)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000dbd0`
- `0x18002a630`
- `0x18002a7d0`
- `0x18002b200`

## callees

- `0x18000ddf0`

## import_xrefs

- `ntdll!RtlCopySid` at `0x18000de2c`
- `ntdll!RtlCopySid` at `0x18000de2c`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000de11`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000de11`

## pseudocode

```c
__int64 __fastcall PsmpGetDSMASid(PSID DestinationSid)
{
  int v2; // ebx

  v2 = RtlRunOnceExecuteOnce(&PsmpIntializeDsmaSidRunOnce, PsmpIntializeDsmaSidRunOnceRoutine, 0, 0);
  if ( v2 >= 0 )
    RtlCopySid(0x44u, DestinationSid, PsmpDsmaSid);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000ddf0  mov     [rsp+arg_0], rbx
0x18000ddf5  push    rdi
0x18000ddf6  sub     rsp, 20h
0x18000ddfa  mov     rdi, rcx
0x18000ddfd  lea     rdx, PsmpIntializeDsmaSidRunOnceRoutine
0x18000de04  lea     rcx, PsmpIntializeDsmaSidRunOnce
0x18000de0b  xor     r9d, r9d
0x18000de0e  xor     r8d, r8d
0x18000de11  call    cs:__imp_RtlRunOnceExecuteOnce
0x18000de17  mov     ebx, eax
0x18000de19  test    eax, eax
0x18000de1b  js      short loc_18000DE32
0x18000de1d  lea     r8, PsmpDsmaSid; SourceSid
0x18000de24  mov     rdx, rdi; DestinationSid
0x18000de27  mov     ecx, 44h ; 'D'; DestinationSidLength
0x18000de2c  call    cs:__imp_RtlCopySid
0x18000de32  mov     eax, ebx
0x18000de34  mov     rbx, [rsp+28h+arg_0]
0x18000de39  add     rsp, 20h
0x18000de3d  pop     rdi
0x18000de3e  retn
```
