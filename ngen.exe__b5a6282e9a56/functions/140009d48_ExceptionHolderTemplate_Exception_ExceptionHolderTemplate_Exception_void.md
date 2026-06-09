# ExceptionHolderTemplate<Exception>::~ExceptionHolderTemplate<Exception>(void)

- ea: `0x140009d48`
- end: `0x140009d9f`
- name: `??1?$ExceptionHolderTemplate@VException@@@@QEAA@XZ`
- size: `87`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x14001409a`
- `0x14001514f`
- `0x1400152a5`
- `0x140015d0c`

## callees

- `0x140009d48`
- `0x140013f30`

## pseudocode

```c
void __fastcall ExceptionHolderTemplate<Exception>::~ExceptionHolderTemplate<Exception>(__int64 *a1)
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
0x140009d48  mov     [rsp+arg_8], rbx
0x140009d4d  mov     [rsp+arg_0], rcx
0x140009d52  push    rdi
0x140009d53  sub     rsp, 20h
0x140009d57  mov     rbx, rcx
0x140009d5a  cmp     dword ptr [rcx+8], 0
0x140009d5e  jz      short loc_140009D94
0x140009d60  mov     rdi, [rcx]
0x140009d63  test    rdi, rdi
0x140009d66  jz      short loc_140009D90
0x140009d68  mov     rax, [rdi]
0x140009d6b  mov     rcx, rdi
0x140009d6e  mov     rax, [rax+50h]
0x140009d72  call    cs:__guard_dispatch_icall_fptr
0x140009d78  test    eax, eax
0x140009d7a  jnz     short loc_140009D90
0x140009d7c  mov     rax, [rdi]
0x140009d7f  mov     edx, 5
0x140009d84  mov     rcx, rdi
0x140009d87  mov     rax, [rax]
0x140009d8a  call    cs:__guard_dispatch_icall_fptr
0x140009d90  and     dword ptr [rbx+8], 0
0x140009d94  mov     rbx, [rsp+28h+arg_8]
0x140009d99  add     rsp, 20h
0x140009d9d  pop     rdi
0x140009d9e  retn
```
