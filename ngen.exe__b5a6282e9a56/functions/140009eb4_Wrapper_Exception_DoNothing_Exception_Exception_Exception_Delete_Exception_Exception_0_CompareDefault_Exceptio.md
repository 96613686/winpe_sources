# Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete<Exception>(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2,1>(void)

- ea: `0x140009eb4`
- end: `0x140009f0b`
- name: `??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1??$Exception__Delete@VException@@@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01$00@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400141c6`
- `0x140015167`
- `0x1400152bd`
- `0x1400155b9`
- `0x140015d30`

## callees

- `0x140009eb4`
- `0x140013f30`

## pseudocode

```c
void __fastcall Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete<Exception>(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2,1>(
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
0x140009eb4  mov     [rsp+arg_8], rbx
0x140009eb9  mov     [rsp+arg_0], rcx
0x140009ebe  push    rdi
0x140009ebf  sub     rsp, 20h
0x140009ec3  mov     rbx, rcx
0x140009ec6  cmp     dword ptr [rcx+8], 0
0x140009eca  jz      short loc_140009F00
0x140009ecc  mov     rdi, [rcx]
0x140009ecf  test    rdi, rdi
0x140009ed2  jz      short loc_140009EFC
0x140009ed4  mov     rax, [rdi]
0x140009ed7  mov     rcx, rdi
0x140009eda  mov     rax, [rax+50h]
0x140009ede  call    cs:__guard_dispatch_icall_fptr
0x140009ee4  test    eax, eax
0x140009ee6  jnz     short loc_140009EFC
0x140009ee8  mov     rax, [rdi]
0x140009eeb  mov     edx, 5
0x140009ef0  mov     rcx, rdi
0x140009ef3  mov     rax, [rax]
0x140009ef6  call    cs:__guard_dispatch_icall_fptr
0x140009efc  and     dword ptr [rbx+8], 0
0x140009f00  mov     rbx, [rsp+28h+arg_8]
0x140009f05  add     rsp, 20h
0x140009f09  pop     rdi
0x140009f0a  retn
```
