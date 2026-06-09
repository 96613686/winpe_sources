# BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)

- ea: `0x14000ea68`
- end: `0x14000ea9e`
- name: `??1?$BaseWrapper@PEAVException@@V?$FunctionBase@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Delete@VException@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVException@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `54`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001573d`
- `0x1400157e8`

## callees

- `0x14000ea68`
- `0x140013f30`

## pseudocode

```c
__int64 __fastcall BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(
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
0x14000ea68  mov     [rsp+arg_0], rcx
0x14000ea6d  push    rbx
0x14000ea6e  sub     rsp, 20h
0x14000ea72  mov     rbx, rcx
0x14000ea75  cmp     dword ptr [rcx+8], 0
0x14000ea79  jz      short loc_14000EA98
0x14000ea7b  mov     rcx, [rcx]
0x14000ea7e  test    rcx, rcx
0x14000ea81  jz      short loc_14000EA94
0x14000ea83  mov     rax, [rcx]
0x14000ea86  mov     edx, 1
0x14000ea8b  mov     rax, [rax]
0x14000ea8e  call    cs:__guard_dispatch_icall_fptr
0x14000ea94  and     dword ptr [rbx+8], 0
0x14000ea98  add     rsp, 20h
0x14000ea9c  pop     rbx
0x14000ea9d  retn
```
