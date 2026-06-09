# copy_environ

- ea: `0x1800374d0`
- end: `0x180037554`
- name: `copy_environ`
- size: `132`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18003714c`

## callees

- `0x18001d50c`
- `0x1800374d0`
- `0x18003d7e0`
- `0x18005f6d0`

## pseudocode

```c
wchar_t **__fastcall copy_environ(const wchar_t **a1)
{
  const wchar_t **v1; // rbx
  int v3; // ecx
  const wchar_t **i; // rax
  wchar_t **v5; // rdi
  wchar_t **v6; // rsi

  v1 = a1;
  if ( !a1 )
    return 0;
  v3 = 0;
  for ( i = v1; *i; ++v3 )
    ++i;
  v5 = (wchar_t **)calloc_crt(v3 + 1, 8);
  v6 = v5;
  if ( !v5 )
    amsg_exit(9);
  while ( *v1 )
    *v5++ = wcsdup(*v1++);
  *v5 = 0;
  return v6;
}

```

## disassembly

```asm
0x1800374d0  mov     [rsp+arg_0], rbx
0x1800374d5  mov     [rsp+arg_8], rsi
0x1800374da  push    rdi
0x1800374db  sub     rsp, 20h
0x1800374df  mov     rbx, rcx
0x1800374e2  test    rcx, rcx
0x1800374e5  jnz     short loc_1800374EB
0x1800374e7  xor     eax, eax
0x1800374e9  jmp     short loc_180037544
0x1800374eb  xor     ecx, ecx
0x1800374ed  mov     rax, rbx
0x1800374f0  cmp     [rbx], rcx
0x1800374f3  jz      short loc_180037501
0x1800374f5  lea     rax, [rax+8]
0x1800374f9  inc     ecx
0x1800374fb  cmp     qword ptr [rax], 0
0x1800374ff  jnz     short loc_1800374F5
0x180037501  lea     eax, [rcx+1]
0x180037504  mov     edx, 8
0x180037509  movsxd  rcx, eax
0x18003750c  call    _calloc_crt
0x180037511  mov     rdi, rax
0x180037514  mov     rsi, rax
0x180037517  test    rax, rax
0x18003751a  jnz     short loc_180037536
0x18003751c  lea     ecx, [rax+9]
0x18003751f  call    _amsg_exit
0x180037524  jmp     short loc_180037536
0x180037526  call    _wcsdup
0x18003752b  mov     [rdi], rax
0x18003752e  lea     rbx, [rbx+8]
0x180037532  add     rdi, 8
0x180037536  mov     rcx, [rbx]; String
0x180037539  test    rcx, rcx
0x18003753c  jnz     short loc_180037526
0x18003753e  mov     [rdi], rcx
0x180037541  mov     rax, rsi
0x180037544  mov     rbx, [rsp+28h+arg_0]
0x180037549  mov     rsi, [rsp+28h+arg_8]
0x18003754e  add     rsp, 20h
0x180037552  pop     rdi
0x180037553  retn
```
