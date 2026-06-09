# RemoveExtensionsList

- ea: `0x140028f98`
- end: `0x140029082`
- name: `RemoveExtensionsList`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140029b30`

## callees

- `0x140006080`
- `0x14001cc20`
- `0x140028f98`

## pseudocode

```c
WCHAR *__fastcall RemoveExtensionsList(__int64 a1)
{
  WCHAR *result; // rax
  _WORD *i; // rbx
  int v3; // eax
  unsigned int v4; // eax
  size_t v5; // r8
  const void *v6; // rdx
  void *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // eax
  char v10; // [rsp+30h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+38h] [rbp+10h] BYREF

  result = *(WCHAR **)(a1 + 8);
  v10 = 0;
  v11 = 0;
  do
  {
    for ( i = result + 1; *i; ++i )
      ;
    if ( IsExcludedExtension(result, i - result, &v10, (int *)&v11) )
    {
      if ( v10 )
      {
        v3 = qword_14000F2F0 - v11;
        LODWORD(qword_14000F2F0) = qword_14000F2F0 - 1;
        v4 = v3 - 1;
        if ( !v4 )
          goto LABEL_12;
        v5 = 8LL * v4;
        v6 = (const void *)(qword_14000F2E0 + 8LL * (v11 + 1));
        v7 = (void *)(qword_14000F2E0 + 8LL * v11);
      }
      else
      {
        v8 = HIDWORD(qword_14000F2F0) - v11;
        --HIDWORD(qword_14000F2F0);
        v9 = v8 - 1;
        if ( !v9 )
          goto LABEL_12;
        v6 = (const void *)(qword_14000F2E8 + 16LL * (v11 + 1));
        v5 = 16LL * v9;
        v7 = (void *)(qword_14000F2E8 + 16LL * v11);
      }
      memmove(v7, v6, v5);
    }
LABEL_12:
    result = i + 1;
  }
  while ( i[1] );
  return result;
}

```

## disassembly

```asm
0x140028f98  mov     [rsp+arg_10], rbx
0x140028f9d  push    rdi
0x140028f9e  sub     rsp, 20h
0x140028fa2  mov     rax, [rcx+8]
0x140028fa6  xor     edi, edi
0x140028fa8  mov     [rsp+28h+arg_0], dil
0x140028fad  mov     [rsp+28h+arg_8], edi
0x140028fb1  lea     rbx, [rax+2]
0x140028fb5  jmp     short loc_140028FBB
0x140028fb7  add     rbx, 2
0x140028fbb  cmp     [rbx], di
0x140028fbe  jnz     short loc_140028FB7
0x140028fc0  mov     rdx, rbx
0x140028fc3  lea     r9, [rsp+28h+arg_8]
0x140028fc8  sub     rdx, rax
0x140028fcb  lea     r8, [rsp+28h+arg_0]
0x140028fd0  sar     rdx, 1
0x140028fd3  mov     rcx, rax
0x140028fd6  call    IsExcludedExtension
0x140028fdb  test    al, al
0x140028fdd  jz      loc_140029069
0x140028fe3  cmp     [rsp+28h+arg_0], dil
0x140028fe8  jz      short loc_140029023
0x140028fea  mov     ecx, dword ptr cs:qword_14000F2F0
0x140028ff0  mov     eax, ecx
0x140028ff2  mov     r10d, [rsp+28h+arg_8]
0x140028ff7  dec     ecx
0x140028ff9  sub     eax, r10d
0x140028ffc  mov     dword ptr cs:qword_14000F2F0, ecx
0x140029002  sub     eax, 1
0x140029005  jz      short loc_140029069
0x140029007  mov     r9, cs:qword_14000F2E0
0x14002900e  mov     r8d, eax
0x140029011  lea     eax, [r10+1]
0x140029015  shl     r8, 3
0x140029019  lea     rdx, [r9+rax*8]
0x14002901d  lea     rcx, [r9+r10*8]
0x140029021  jmp     short loc_140029064
0x140029023  mov     ecx, dword ptr cs:qword_14000F2F0+4
0x140029029  mov     eax, ecx
0x14002902b  mov     r9d, [rsp+28h+arg_8]
0x140029030  dec     ecx
0x140029032  sub     eax, r9d
0x140029035  mov     dword ptr cs:qword_14000F2F0+4, ecx
0x14002903b  sub     eax, 1
0x14002903e  jz      short loc_140029069
0x140029040  lea     edx, [r9+1]
0x140029044  mov     r8d, eax
0x140029047  shl     rdx, 4
0x14002904b  mov     ecx, r9d
0x14002904e  add     rdx, cs:qword_14000F2E8; Src
0x140029055  shl     r8, 4; Size
0x140029059  shl     rcx, 4
0x14002905d  add     rcx, cs:qword_14000F2E8; void *
0x140029064  call    memmove
0x140029069  lea     rax, [rbx+2]
0x14002906d  cmp     [rax], di
0x140029070  jnz     loc_140028FB1
0x140029076  mov     rbx, [rsp+28h+arg_10]
0x14002907b  add     rsp, 20h
0x14002907f  pop     rdi
0x140029080  retn
```
