# _configure_narrow_argv

- ea: `0x1800179d4`
- end: `0x180017b4a`
- name: `_configure_narrow_argv`
- size: `374`
- prototype: `errno_t __cdecl(_crt_argv_mode mode)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012ccc`

## callees

- `0x1800177b4`
- `0x180017970`
- `0x1800179d4`
- `0x180019450`
- `0x180019570`
- `0x180019608`
- `0x180019bf4`
- `0x18001a300`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x180017a1f`
- `KERNEL32!GetModuleFileNameA` at `0x180017a1f`

## pseudocode

```c
errno_t __cdecl configure_narrow_argv(_crt_argv_mode mode)
{
  errno_t v2; // edi
  CHAR *v3; // rsi
  int v4; // r15d
  __int64 buffer_for_argv; // rax
  void *v6; // rbx
  void *v7; // rcx
  errno_t v8; // esi
  char **v9; // rdx
  int v10; // ecx
  _QWORD *i; // rax
  void *Block; // [rsp+68h] [rbp+38h] BYREF
  __int64 v14; // [rsp+70h] [rbp+40h] BYREF
  __int64 v15; // [rsp+78h] [rbp+48h] BYREF

  if ( (unsigned int)(mode - 1) <= 1 )
  {
    _acrt_initialize_multibyte();
    GetModuleFileNameA(0, Filename, 0x104u);
    LODWORD(v3) = (_DWORD)acmdln;
    v2 = 0;
    pgmptr = Filename;
    if ( !acmdln || !*acmdln )
      v3 = Filename;
    v14 = 0;
    v15 = 0;
    parse_command_line_char_((_DWORD)v3, 0, 0, (unsigned int)&v14, (__int64)&v15);
    v4 = v14;
    buffer_for_argv = _acrt_allocate_buffer_for_argv(v14, v15, 1);
    v6 = (void *)buffer_for_argv;
    if ( buffer_for_argv )
    {
      parse_command_line_char_((_DWORD)v3, buffer_for_argv, buffer_for_argv + 8 * v4, (unsigned int)&v14, (__int64)&v15);
      if ( mode != _crt_argv_unexpanded_arguments )
      {
        Block = 0;
        v8 = _acrt_expand_narrow_argv_wildcards(v6, &Block);
        if ( v8 )
        {
          free_base(Block);
          Block = 0;
          free_base(v6);
          return v8;
        }
        v9 = (char **)Block;
        v10 = 0;
        for ( i = Block; *i; ++v10 )
          ++i;
        _argc = v10;
        Block = 0;
        _argv = v9;
        free_base(0);
        v7 = v6;
        Block = 0;
LABEL_16:
        free_base(v7);
        return v2;
      }
      _argv = (char **)v6;
      _argc = v14 - 1;
    }
    else
    {
      v2 = 12;
      *errno() = 12;
    }
    v7 = 0;
    goto LABEL_16;
  }
  v2 = 22;
  *errno() = 22;
  invalid_parameter_noinfo();
  return v2;
}

```

## disassembly

```asm
0x1800179d4  mov     [rsp-28h+arg_0], rbx
0x1800179d9  push    rbp
0x1800179da  push    rsi
0x1800179db  push    rdi
0x1800179dc  push    r14
0x1800179de  push    r15
0x1800179e0  mov     rbp, rsp
0x1800179e3  sub     rsp, 30h
0x1800179e7  lea     eax, [rcx-1]
0x1800179ea  mov     r14d, ecx
0x1800179ed  cmp     eax, 1
0x1800179f0  jbe     short loc_180017A08
0x1800179f2  call    _errno
0x1800179f7  mov     edi, 16h
0x1800179fc  mov     [rax], edi
0x1800179fe  call    _invalid_parameter_noinfo
0x180017a03  jmp     loc_180017B37
0x180017a08  call    __acrt_initialize_multibyte
0x180017a0d  lea     rbx, Filename
0x180017a14  mov     r8d, 104h; nSize
0x180017a1a  mov     rdx, rbx; lpFilename
0x180017a1d  xor     ecx, ecx; hModule
0x180017a1f  call    cs:__imp_GetModuleFileNameA
0x180017a25  mov     rsi, cs:_acmdln
0x180017a2c  xor     edi, edi
0x180017a2e  mov     cs:_pgmptr, rbx
0x180017a35  test    rsi, rsi
0x180017a38  jz      short loc_180017A3F
0x180017a3a  cmp     [rsi], dil
0x180017a3d  jnz     short loc_180017A42
0x180017a3f  mov     rsi, rbx
0x180017a42  lea     rax, [rbp+arg_18]
0x180017a46  mov     [rbp+arg_10], rdi
0x180017a4a  lea     r9, [rbp+arg_10]
0x180017a4e  mov     [rsp+30h+var_10], rax
0x180017a53  xor     r8d, r8d
0x180017a56  mov     [rbp+arg_18], rdi
0x180017a5a  xor     edx, edx
0x180017a5c  mov     rcx, rsi
0x180017a5f  call    parse_command_line_char_
0x180017a64  mov     r15, [rbp+arg_10]
0x180017a68  mov     r8d, 1
0x180017a6e  mov     rdx, [rbp+arg_18]
0x180017a72  mov     rcx, r15
0x180017a75  call    __acrt_allocate_buffer_for_argv
0x180017a7a  mov     rbx, rax
0x180017a7d  test    rax, rax
0x180017a80  jnz     short loc_180017A93
0x180017a82  call    _errno
0x180017a87  lea     edi, [rbx+0Ch]
0x180017a8a  mov     [rax], edi
0x180017a8c  xor     ecx, ecx
0x180017a8e  jmp     loc_180017B32
0x180017a93  lea     r8, [rax+r15*8]
0x180017a97  mov     rdx, rbx
0x180017a9a  lea     rax, [rbp+arg_18]
0x180017a9e  mov     rcx, rsi
0x180017aa1  lea     r9, [rbp+arg_10]
0x180017aa5  mov     [rsp+30h+var_10], rax
0x180017aaa  call    parse_command_line_char_
0x180017aaf  cmp     r14d, 1
0x180017ab3  jnz     short loc_180017AC9
0x180017ab5  mov     eax, dword ptr [rbp+arg_10]
0x180017ab8  dec     eax
0x180017aba  mov     cs:__argv, rbx
0x180017ac1  mov     cs:__argc, eax
0x180017ac7  jmp     short loc_180017A8C
0x180017ac9  lea     rdx, [rbp+Block]
0x180017acd  mov     [rbp+Block], rdi
0x180017ad1  mov     rcx, rbx
0x180017ad4  call    __acrt_expand_narrow_argv_wildcards
0x180017ad9  mov     esi, eax
0x180017adb  test    eax, eax
0x180017add  jz      short loc_180017AF8
0x180017adf  mov     rcx, [rbp+Block]; Block
0x180017ae3  call    _free_base
0x180017ae8  mov     rcx, rbx; Block
0x180017aeb  mov     [rbp+Block], rdi
0x180017aef  call    _free_base
0x180017af4  mov     edi, esi
0x180017af6  jmp     short loc_180017B37
0x180017af8  mov     rdx, [rbp+Block]
0x180017afc  mov     rcx, rdi
0x180017aff  mov     rax, rdx
0x180017b02  cmp     [rdx], rdi
0x180017b05  jz      short loc_180017B13
0x180017b07  lea     rax, [rax+8]
0x180017b0b  inc     rcx
0x180017b0e  cmp     [rax], rdi
0x180017b11  jnz     short loc_180017B07
0x180017b13  mov     cs:__argc, ecx
0x180017b19  xor     ecx, ecx; Block
0x180017b1b  mov     [rbp+Block], rdi
0x180017b1f  mov     cs:__argv, rdx
0x180017b26  call    _free_base
0x180017b2b  mov     rcx, rbx; Block
0x180017b2e  mov     [rbp+Block], rdi
0x180017b32  call    _free_base
0x180017b37  mov     eax, edi
0x180017b39  mov     rbx, [rsp+30h+arg_0]
0x180017b3e  add     rsp, 30h
0x180017b42  pop     r15
0x180017b44  pop     r14
0x180017b46  pop     rdi
0x180017b47  pop     rsi
0x180017b48  pop     rbp
0x180017b49  retn
```
