# Wrapper<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),0,&CompareDefault<void *>(void *,void *),2,1>::~Wrapper<void *,&DoNothing<void *>(void *),&DoFreeSid(void *),0,&CompareDefault<void *>(void *,void *),2,1>(void)

- ea: `0x18002a73c`
- end: `0x18002a762`
- name: `??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?DoFreeSid@@YAX0@Z$0A@$1??$CompareDefault@PEAX@@YAH00@Z$01$00@@QEAA@XZ`
- size: `38`
- prototype: `PVOID __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180046317`

## callees

- `0x18002a73c`

## import_xrefs

- `ADVAPI32!FreeSid` at `0x18002a752`
- `ADVAPI32!FreeSid` at `0x18002a752`

## pseudocode

```c
PVOID __fastcall Wrapper<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),0,&int CompareDefault<void *>(void *,void *),2,1>::~Wrapper<void *,&void DoNothing<void *>(void *),&void DoFreeSid(void *),0,&int CompareDefault<void *>(void *,void *),2,1>(
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
0x18002a73c  mov     [rsp+arg_0], rcx
0x18002a741  push    rbx
0x18002a742  sub     rsp, 20h
0x18002a746  mov     rbx, rcx
0x18002a749  cmp     dword ptr [rcx+8], 0
0x18002a74d  jz      short loc_18002A75C
0x18002a74f  mov     rcx, [rcx]; pSid
0x18002a752  call    cs:__imp_FreeSid
0x18002a758  and     dword ptr [rbx+8], 0
0x18002a75c  add     rsp, 20h
0x18002a760  pop     rbx
0x18002a761  retn
```
