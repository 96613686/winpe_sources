# std::list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::~list<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(void)

- ea: `0x14000c540`
- end: `0x14000c5a5`
- name: `??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ`
- size: `101`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14000ce64`
- `0x14000d2a4`
- `0x14000e9a8`
- `0x14000ebec`
- `0x140013445`
- `0x140013567`
- `0x14001358b`

## callees

- `0x140002624`
- `0x140004e30`
- `0x14000c540`

## pseudocode

```c
void __fastcall std::list<std::wstring>::~list<std::wstring>(void **a1)
{
  void **v1; // rdx
  char **v3; // rdi
  char *v4; // rbx

  v1 = (void **)*a1;
  **((_QWORD **)*a1 + 1) = 0;
  v3 = (char **)*v1;
  if ( *v1 )
  {
    do
    {
      v4 = *v3;
      std::wstring::~wstring(v3 + 2);
      operator delete(v3);
      v3 = (char **)v4;
    }
    while ( v4 );
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x14000c540  mov     [rsp+arg_0], rbx
0x14000c545  mov     [rsp+arg_8], rsi
0x14000c54a  push    rdi
0x14000c54b  sub     rsp, 20h
0x14000c54f  mov     rdx, [rcx]
0x14000c552  mov     rsi, rcx
0x14000c555  mov     rax, [rdx+8]
0x14000c559  mov     qword ptr [rax], 0
0x14000c560  mov     rdi, [rdx]
0x14000c563  test    rdi, rdi
0x14000c566  jz      short loc_14000C589
0x14000c568  mov     rbx, [rdi]
0x14000c56b  lea     rcx, [rdi+10h]
0x14000c56f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000c574  mov     edx, 30h ; '0'; unsigned __int64
0x14000c579  mov     rcx, rdi; void *
0x14000c57c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000c581  mov     rdi, rbx
0x14000c584  test    rbx, rbx
0x14000c587  jnz     short loc_14000C568
0x14000c589  mov     rcx, [rsi]; void *
0x14000c58c  mov     edx, 30h ; '0'; unsigned __int64
0x14000c591  mov     rbx, [rsp+28h+arg_0]
0x14000c596  mov     rsi, [rsp+28h+arg_8]
0x14000c59b  add     rsp, 20h
0x14000c59f  pop     rdi
0x14000c5a0  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
