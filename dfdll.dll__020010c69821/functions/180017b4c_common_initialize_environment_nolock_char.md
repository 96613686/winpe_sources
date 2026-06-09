# common_initialize_environment_nolock_char_

- ea: `0x180017b4c`
- end: `0x180017bb8`
- name: `common_initialize_environment_nolock_char_`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017d68`

## callees

- `0x180017b4c`
- `0x180017bb8`
- `0x180019608`
- `0x18001a300`
- `0x18001a748`

## pseudocode

```c
__int64 common_initialize_environment_nolock_char_()
{
  unsigned int v0; // edi
  char *narrow_environment_from_os; // rax
  char *v3; // rbx
  void *environment_char; // rax

  v0 = 0;
  if ( environ_table )
    return 0;
  _acrt_initialize_multibyte();
  narrow_environment_from_os = (char *)_dcrt_get_narrow_environment_from_os();
  v3 = narrow_environment_from_os;
  if ( narrow_environment_from_os )
  {
    environment_char = create_environment_char_(narrow_environment_from_os);
    if ( environment_char )
    {
      _dcrt_initial_narrow_environment = environment_char;
      environ_table = (__int64)environment_char;
    }
    else
    {
      v0 = -1;
    }
    free_base(0);
  }
  else
  {
    v0 = -1;
  }
  free_base(v3);
  return v0;
}

```

## disassembly

```asm
0x180017b4c  mov     [rsp+arg_0], rbx
0x180017b51  push    rdi
0x180017b52  sub     rsp, 20h
0x180017b56  xor     edi, edi
0x180017b58  cmp     cs:_environ_table, rdi
0x180017b5f  jz      short loc_180017B65
0x180017b61  xor     eax, eax
0x180017b63  jmp     short loc_180017BAD
0x180017b65  call    __acrt_initialize_multibyte
0x180017b6a  call    __dcrt_get_narrow_environment_from_os
0x180017b6f  mov     rbx, rax
0x180017b72  test    rax, rax
0x180017b75  jnz     short loc_180017B7C
0x180017b77  or      edi, 0FFFFFFFFh
0x180017b7a  jmp     short loc_180017BA3
0x180017b7c  mov     rcx, rax; Source
0x180017b7f  call    create_environment_char_
0x180017b84  test    rax, rax
0x180017b87  jnz     short loc_180017B8E
0x180017b89  or      edi, 0FFFFFFFFh
0x180017b8c  jmp     short loc_180017B9C
0x180017b8e  mov     cs:__dcrt_initial_narrow_environment, rax
0x180017b95  mov     cs:_environ_table, rax
0x180017b9c  xor     ecx, ecx; Block
0x180017b9e  call    _free_base
0x180017ba3  mov     rcx, rbx; Block
0x180017ba6  call    _free_base
0x180017bab  mov     eax, edi
0x180017bad  mov     rbx, [rsp+28h+arg_0]
0x180017bb2  add     rsp, 20h
0x180017bb6  pop     rdi
0x180017bb7  retn
```
