# Smb2StartResilientHandleDatabase

- ea: `0x140035e54`
- end: `0x140035e95`
- name: `Smb2StartResilientHandleDatabase`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x140027e90`

## import_xrefs

- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x140035e83`
- `mrxsmb!MRxSmbInitializeRecurrentService` at `0x140035e83`

## pseudocode

```c
__int64 __fastcall Smb2StartResilientHandleDatabase(__int64 a1)
{
  __int64 v1; // r8
  __int64 v3; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 2336);
  v3 = 50000000;
  return MRxSmbInitializeRecurrentService(v1 + 136, Smb2ProbeAndReconnectResilientHandles, v1, &v3, a1);
}

```

## disassembly

```asm
0x140035e54  sub     rsp, 38h
0x140035e58  mov     r8, [rcx+920h]
0x140035e5f  lea     r9, [rsp+38h+arg_0]
0x140035e64  mov     rax, rcx
0x140035e67  mov     [rsp+38h+arg_0], 2FAF080h
0x140035e70  lea     rdx, Smb2ProbeAndReconnectResilientHandles
0x140035e77  mov     [rsp+38h+var_18], rax
0x140035e7c  lea     rcx, [r8+88h]
0x140035e83  call    cs:__imp_MRxSmbInitializeRecurrentService
0x140035e8a  nop     dword ptr [rax+rax+00h]
0x140035e8f  add     rsp, 38h
0x140035e93  retn
```
