# _lsearch_s

- ea: `0x18002f400`
- end: `0x18002f4bb`
- name: `_lsearch_s`
- size: `187`
- prototype: `void *__cdecl(const void *Key, void *Base, unsigned int *NumOfElements, size_t SizeOfElements, _CoreCrtSecureSearchSortCompareFunction CompareFunction, void *Context)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180007f00`
- `0x18002f050`
- `0x18002f400`
- `0x180079c80`
- `0x18007d010`

## pseudocode

```c
void *__cdecl lsearch_s(
        const void *Key,
        void *Base,
        unsigned int *NumOfElements,
        size_t SizeOfElements,
        _CoreCrtSecureSearchSortCompareFunction CompareFunction,
        void *Context)
{
  char *v8; // rbx
  char *v10; // rdi

  v8 = (char *)Base;
  if ( !Key || !NumOfElements || !Base || !SizeOfElements || !CompareFunction )
  {
    *errno() = 22;
    invalid_parameter(0, 0, 0, 0, 0);
  }
  v10 = (char *)Base + SizeOfElements * *NumOfElements;
  while ( 1 )
  {
    if ( v8 == v10 )
    {
      memmove(v10, Key, SizeOfElements);
      ++*NumOfElements;
      return v10;
    }
    if ( !((unsigned int (__fastcall *)(void *, const void *, char *))CompareFunction)(Context, Key, v8) )
      break;
    v8 += SizeOfElements;
  }
  return v8;
}

```

## disassembly

```asm
0x18002f400  push    rbx
0x18002f402  push    rbp
0x18002f403  push    rsi
0x18002f404  push    rdi
0x18002f405  push    r15
0x18002f407  sub     rsp, 30h
0x18002f40b  mov     rsi, r9
0x18002f40e  mov     rbp, r8
0x18002f411  mov     rbx, rdx
0x18002f414  mov     r15, rcx
0x18002f417  test    rcx, rcx
0x18002f41a  jnz     short loc_18002F443
0x18002f41c  call    _errno
0x18002f421  xor     r9d, r9d; LineNo
0x18002f424  mov     [rsp+58h+Reserved], 0; Reserved
0x18002f42d  xor     r8d, r8d; FileName
0x18002f430  xor     edx, edx; FunctionName
0x18002f432  xor     ecx, ecx; Expression
0x18002f434  mov     dword ptr [rax], 16h
0x18002f43a  call    _invalid_parameter
0x18002f43f  xor     eax, eax
0x18002f441  jmp     short loc_18002F4AB
0x18002f443  test    rbp, rbp
0x18002f446  jz      short loc_18002F41C
0x18002f448  test    rbx, rbx
0x18002f44b  jz      short loc_18002F41C
0x18002f44d  test    rsi, rsi
0x18002f450  jz      short loc_18002F41C
0x18002f452  cmp     [rsp+58h+CompareFunction], 0
0x18002f45b  jz      short loc_18002F41C
0x18002f45d  mov     rcx, [rsp+58h+CompareFunction]; Target
0x18002f465  call    _guard_check_icall$thunk$15021643654165956172
0x18002f46a  mov     edi, [rbp+0]
0x18002f46d  imul    rdi, rsi
0x18002f471  add     rdi, rbx
0x18002f474  jmp     short loc_18002F492
0x18002f476  mov     rcx, [rsp+58h+Context]; void *
0x18002f47e  mov     r8, rbx; void *
0x18002f481  mov     rdx, r15; void *
0x18002f484  call    [rsp+58h+CompareFunction]
0x18002f48b  test    eax, eax
0x18002f48d  jz      short loc_18002F4B6
0x18002f48f  add     rbx, rsi
0x18002f492  cmp     rbx, rdi
0x18002f495  jnz     short loc_18002F476
0x18002f497  mov     r8, rsi; Size
0x18002f49a  mov     rdx, r15; Src
0x18002f49d  mov     rcx, rdi; void *
0x18002f4a0  call    memmove
0x18002f4a5  inc     dword ptr [rbp+0]
0x18002f4a8  mov     rax, rdi
0x18002f4ab  add     rsp, 30h
0x18002f4af  pop     r15
0x18002f4b1  pop     rdi
0x18002f4b2  pop     rsi
0x18002f4b3  pop     rbp
0x18002f4b4  pop     rbx
0x18002f4b5  retn
0x18002f4b6  mov     rax, rbx
0x18002f4b9  jmp     short loc_18002F4AB
```
