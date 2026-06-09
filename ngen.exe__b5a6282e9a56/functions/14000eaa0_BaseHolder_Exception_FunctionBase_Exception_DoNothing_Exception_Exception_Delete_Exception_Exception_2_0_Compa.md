# BaseHolder<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseHolder<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)

- ea: `0x14000eaa0`
- end: `0x14000ead2`
- name: `??1?$BaseHolder@PEAVException@@V?$FunctionBase@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Delete@VException@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVException@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `50`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140015749`
- `0x1400157f4`

## callees

- `0x14000eaa0`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall BaseHolder<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseHolder<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(
        __int64 a1)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // rcx
  __int64 result; // rax

  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(__int64 (__fastcall ****)(_QWORD, __int64))a1;
    if ( v2 )
      result = (**v2)(v2, 1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000eaa0  push    rbx
0x14000eaa2  sub     rsp, 20h
0x14000eaa6  cmp     dword ptr [rcx+8], 0
0x14000eaaa  mov     rbx, rcx
0x14000eaad  jz      short loc_14000EACC
0x14000eaaf  mov     rcx, [rcx]
0x14000eab2  test    rcx, rcx
0x14000eab5  jz      short loc_14000EAC8
0x14000eab7  mov     rax, [rcx]
0x14000eaba  mov     edx, 1
0x14000eabf  mov     rax, [rax]
0x14000eac2  call    cs:__guard_dispatch_icall_fptr
0x14000eac8  and     dword ptr [rbx+8], 0
0x14000eacc  add     rsp, 20h
0x14000ead0  pop     rbx
0x14000ead1  retn
```
