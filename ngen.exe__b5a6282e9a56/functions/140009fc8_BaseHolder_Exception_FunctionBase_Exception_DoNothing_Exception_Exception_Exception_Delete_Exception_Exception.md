# BaseHolder<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseHolder<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)

- ea: `0x140009fc8`
- end: `0x14000a01a`
- name: `??1?$BaseHolder@PEAVException@@V?$FunctionBase@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVException@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `82`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400141de`
- `0x14001517f`
- `0x1400152d5`
- `0x1400155d1`
- `0x140015d48`

## callees

- `0x140009fc8`
- `0x140013f30`

## pseudocode

```c
void __fastcall BaseHolder<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseHolder<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(
        __int64 *a1)
{
  __int64 v2; // rdi

  if ( *((_DWORD *)a1 + 2) )
  {
    v2 = *a1;
    if ( *a1 )
    {
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(*(_QWORD *)v2 + 80LL))(*a1) )
        (**(void (__fastcall ***)(__int64, __int64))v2)(v2, 5);
    }
    *((_DWORD *)a1 + 2) = 0;
  }
}

```

## disassembly

```asm
0x140009fc8  mov     [rsp+arg_0], rbx
0x140009fcd  push    rdi
0x140009fce  sub     rsp, 20h
0x140009fd2  mov     rbx, rcx
0x140009fd5  cmp     dword ptr [rcx+8], 0
0x140009fd9  jz      short loc_14000A00F
0x140009fdb  mov     rdi, [rcx]
0x140009fde  test    rdi, rdi
0x140009fe1  jz      short loc_14000A00B
0x140009fe3  mov     rax, [rdi]
0x140009fe6  mov     rcx, rdi
0x140009fe9  mov     rax, [rax+50h]
0x140009fed  call    cs:__guard_dispatch_icall_fptr
0x140009ff3  test    eax, eax
0x140009ff5  jnz     short loc_14000A00B
0x140009ff7  mov     rax, [rdi]
0x140009ffa  mov     edx, 5
0x140009fff  mov     rcx, rdi
0x14000a002  mov     rax, [rax]
0x14000a005  call    cs:__guard_dispatch_icall_fptr
0x14000a00b  and     dword ptr [rbx+8], 0
0x14000a00f  mov     rbx, [rsp+28h+arg_0]
0x14000a014  add     rsp, 20h
0x14000a018  pop     rdi
0x14000a019  retn
```
