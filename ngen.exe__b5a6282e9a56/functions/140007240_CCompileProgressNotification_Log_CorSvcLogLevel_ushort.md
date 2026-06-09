# CCompileProgressNotification::Log(CorSvcLogLevel,ushort *)

- ea: `0x140007240`
- end: `0x14000725e`
- name: `?Log@CCompileProgressNotification@@UEAAJW4CorSvcLogLevel@@PEAG@Z`
- size: `30`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1400072ec`

## pseudocode

```c
__int64 __fastcall CCompileProgressNotification::Log(__int64 a1, __int64 a2, __int64 a3)
{
  CCompileProgressNotification::LogWorker(a1 - 8, a2, L"%s", a3);
  return 0;
}

```

## disassembly

```asm
0x140007240  sub     rsp, 28h
0x140007244  mov     r9, r8
0x140007247  add     rcx, 0FFFFFFFFFFFFFFF8h
0x14000724b  lea     r8, aS; "%s"
0x140007252  call    ?LogWorker@CCompileProgressNotification@@AEAAXW4CorSvcLogLevel@@PEAGZZ; CCompileProgressNotification::LogWorker(CorSvcLogLevel,ushort *,...)
0x140007257  xor     eax, eax
0x140007259  add     rsp, 28h
0x14000725d  retn
```
