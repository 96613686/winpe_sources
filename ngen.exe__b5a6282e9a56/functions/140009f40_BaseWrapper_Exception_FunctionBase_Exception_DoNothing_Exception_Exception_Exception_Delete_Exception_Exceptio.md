# BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),2>,0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)

- ea: `0x140009f40`
- end: `0x140009f97`
- name: `??1?$BaseWrapper@PEAVException@@V?$FunctionBase@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAVException@@@@YAHPEAV1@0@Z$01@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400141d2`
- `0x140015173`
- `0x1400152c9`
- `0x1400155c5`
- `0x140015d3c`

## callees

- `0x140009f40`
- `0x140013f30`

## pseudocode

```c
void __fastcall BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~BaseWrapper<Exception *,FunctionBase<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),2>,0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(
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
0x140009f40  mov     [rsp+arg_8], rbx
0x140009f45  mov     [rsp+arg_0], rcx
0x140009f4a  push    rdi
0x140009f4b  sub     rsp, 20h
0x140009f4f  mov     rbx, rcx
0x140009f52  cmp     dword ptr [rcx+8], 0
0x140009f56  jz      short loc_140009F8C
0x140009f58  mov     rdi, [rcx]
0x140009f5b  test    rdi, rdi
0x140009f5e  jz      short loc_140009F88
0x140009f60  mov     rax, [rdi]
0x140009f63  mov     rcx, rdi
0x140009f66  mov     rax, [rax+50h]
0x140009f6a  call    cs:__guard_dispatch_icall_fptr
0x140009f70  test    eax, eax
0x140009f72  jnz     short loc_140009F88
0x140009f74  mov     rax, [rdi]
0x140009f77  mov     edx, 5
0x140009f7c  mov     rcx, rdi
0x140009f7f  mov     rax, [rax]
0x140009f82  call    cs:__guard_dispatch_icall_fptr
0x140009f88  and     dword ptr [rbx+8], 0
0x140009f8c  mov     rbx, [rsp+28h+arg_8]
0x140009f91  add     rsp, 20h
0x140009f95  pop     rdi
0x140009f96  retn
```
