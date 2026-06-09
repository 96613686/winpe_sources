# CryptsvcDllCtrl(ulong,ulong,ulong,void *)

- ea: `0x180004e80`
- end: `0x180004ebf`
- name: `?CryptsvcDllCtrl@@YAKKKKPEAX@Z`
- size: `63`
- prototype: `RPC_STATUS __fastcall(int, __int64, __int64, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180004e80`
- `0x180007940`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x180004eaa`

## pseudocode

```c
RPC_STATUS __fastcall CryptsvcDllCtrl(int a1, __int64 a2, __int64 a3, void *a4)
{
  __int64 v5; // rcx

  if ( a1 == 3 )
    return 0;
  v5 = (unsigned int)(a1 - 1);
  if ( !(_DWORD)v5 )
    return TpmEndorsementKeyServiceStart(v5, a2, a3, a4);
  if ( (_DWORD)v5 == 1 )
    return RpcServerUnregisterIf(qword_18000C000, 0, 1u);
  return -2147418113;
}

```

## disassembly

```asm
0x180004e80  sub     rsp, 28h
0x180004e84  cmp     ecx, 3
0x180004e87  jnz     short loc_180004E90
0x180004e89  xor     eax, eax
0x180004e8b  add     rsp, 28h
0x180004e8f  retn
0x180004e90  sub     ecx, 1
0x180004e93  jz      short loc_180004EB8
0x180004e95  cmp     ecx, 1
0x180004e98  jnz     short loc_180004EB1
0x180004e9a  mov     r8d, ecx
0x180004e9d  xor     edx, edx
0x180004e9f  lea     rcx, qword_18000C000
0x180004ea6  add     rsp, 28h
0x180004eaa  jmp     cs:__imp_RpcServerUnregisterIf
0x180004eb1  mov     eax, 8000FFFFh
0x180004eb6  jmp     short loc_180004E8B
0x180004eb8  call    TpmEndorsementKeyServiceStart
0x180004ebd  jmp     short loc_180004E8B
```
