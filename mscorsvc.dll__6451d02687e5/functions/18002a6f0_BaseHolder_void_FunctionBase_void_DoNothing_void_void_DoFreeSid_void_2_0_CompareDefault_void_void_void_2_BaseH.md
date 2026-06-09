# BaseHolder<void *,FunctionBase<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),2>,0,&CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),2>,0,&CompareDefault<void *>(void *,void *),2>(void)

- ea: `0x18002a6f0`
- end: `0x18002a712`
- name: `??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?DoFreeSid@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ`
- size: `34`
- prototype: `PVOID __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004629f`
- `0x180046489`

## callees

- `0x18002a6f0`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18002a702`
- `ADVAPI32!FreeSid` at `0x18002a702`

## pseudocode

```c
PVOID __fastcall BaseHolder<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),2>,0,&int CompareDefault<void *>(void *,void *),2>(
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
0x18002a6f0  push    rbx
0x18002a6f2  sub     rsp, 20h
0x18002a6f6  mov     rbx, rcx
0x18002a6f9  cmp     dword ptr [rcx+8], 0
0x18002a6fd  jz      short loc_18002A70C
0x18002a6ff  mov     rcx, [rcx]; pSid
0x18002a702  call    cs:__imp_FreeSid
0x18002a708  and     dword ptr [rbx+8], 0
0x18002a70c  add     rsp, 20h
0x18002a710  pop     rbx
0x18002a711  retn
```
