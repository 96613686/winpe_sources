# ReadAndHash

- ea: `0x140090440`
- end: `0x140090495`
- name: `ReadAndHash`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14009049c`

## callees

- `0x140090440`
- `0x14009087c`
- `0x140098010`

## pseudocode

```c
__int64 __fastcall ReadAndHash(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  if ( (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, __int64, __int64))(a1 + 8))(*(_QWORD *)a1, a3, a4, 1, a2) == 1 )
    return fapriv_HashUpdate(a5, a3, a4);
  else
    return 4294967294LL;
}

```

## disassembly

```asm
0x140090440  mov     [rsp+arg_0], rbx
0x140090445  push    rdi
0x140090446  sub     rsp, 30h
0x14009044a  mov     rax, [rcx+8]
0x14009044e  mov     rdi, r8
0x140090451  mov     rcx, [rcx]
0x140090454  mov     r8d, r9d
0x140090457  mov     ebx, r9d
0x14009045a  mov     r9d, 1
0x140090460  mov     [rsp+38h+var_18], rdx
0x140090465  mov     rdx, rdi
0x140090468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009046d  cmp     rax, 1
0x140090471  jz      short loc_14009047A
0x140090473  mov     eax, 0FFFFFFFEh
0x140090478  jmp     short loc_14009048A
0x14009047a  mov     rcx, [rsp+38h+arg_20]
0x14009047f  mov     r8d, ebx
0x140090482  mov     rdx, rdi
0x140090485  call    fapriv_HashUpdate
0x14009048a  mov     rbx, [rsp+38h+arg_0]
0x14009048f  add     rsp, 30h
0x140090493  pop     rdi
0x140090494  retn
```
