# BaseWrapper<void *,FunctionBase<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),2>,0,&CompareDefault<void *>(void *,void *),2>::~BaseWrapper<void *,FunctionBase<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),2>,0,&CompareDefault<void *>(void *,void *),2>(void)

- ea: `0x18002a714`
- end: `0x18002a73a`
- name: `??1?$BaseWrapper@PEAXV?$FunctionBase@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?DoFreeSid@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ`
- size: `38`
- prototype: `PVOID __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800462ab`
- `0x18004647d`

## callees

- `0x18002a714`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18002a72a`
- `ADVAPI32!FreeSid` at `0x18002a72a`

## pseudocode

```c
PVOID __fastcall BaseWrapper<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>::~BaseWrapper<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>(
        __int64 a1)
{
  PVOID result; // rax

  if ( *(_DWORD *)(a1 + 8) )
  {
    result = FreeSid(*(PSID *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002a714  mov     [rsp+arg_0], rcx
0x18002a719  push    rbx
0x18002a71a  sub     rsp, 20h
0x18002a71e  mov     rbx, rcx
0x18002a721  cmp     dword ptr [rcx+8], 0
0x18002a725  jz      short loc_18002A734
0x18002a727  mov     rcx, [rcx]; pSid
0x18002a72a  call    cs:__imp_FreeSid
0x18002a730  and     dword ptr [rbx+8], 0
0x18002a734  add     rsp, 20h
0x18002a738  pop     rbx
0x18002a739  retn
```
