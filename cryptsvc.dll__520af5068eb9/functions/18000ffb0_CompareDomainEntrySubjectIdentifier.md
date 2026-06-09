# _CompareDomainEntrySubjectIdentifier

- ea: `0x18000ffb0`
- end: `0x18000fffb`
- name: `_CompareDomainEntrySubjectIdentifier`
- size: `75`
- prototype: `int __fastcall(const void ***, unsigned int **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ffb0`
- `0x1800174f0`

## pseudocode

```c
int __fastcall CompareDomainEntrySubjectIdentifier(const void ***a1, unsigned int **a2)
{
  const void **v2; // rdi
  unsigned int *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int result; // eax

  v2 = *a1;
  v3 = *a2;
  v4 = *(_DWORD *)*a1;
  v5 = *v3;
  if ( v4 >= *v3 )
    v4 = *v3;
  if ( !v4 || (result = memcmp_0(v2[1], *((const void **)v3 + 1), v4)) == 0 )
  {
    if ( *(_DWORD *)v2 == v5 )
      return 0;
    else
      return *(_DWORD *)v2 < v5 ? -1 : 1;
  }
  return result;
}

```

## disassembly

```asm
0x18000ffb0  mov     [rsp+arg_0], rbx
0x18000ffb5  push    rdi
0x18000ffb6  sub     rsp, 20h
0x18000ffba  mov     rdi, [rcx]
0x18000ffbd  mov     rdx, [rdx]
0x18000ffc0  mov     eax, [rdi]
0x18000ffc2  mov     ebx, [rdx]
0x18000ffc4  cmp     eax, ebx
0x18000ffc6  cmovnb  eax, ebx
0x18000ffc9  test    eax, eax
0x18000ffcb  jz      short loc_18000FFE1
0x18000ffcd  mov     rdx, [rdx+8]; Buf2
0x18000ffd1  mov     rcx, [rdi+8]; Buf1
0x18000ffd5  mov     r8d, eax; Size
0x18000ffd8  call    memcmp_0
0x18000ffdd  test    eax, eax
0x18000ffdf  jnz     short loc_18000FFF0
0x18000ffe1  cmp     [rdi], ebx
0x18000ffe3  jnz     short loc_18000FFE9
0x18000ffe5  xor     eax, eax
0x18000ffe7  jmp     short loc_18000FFF0
0x18000ffe9  sbb     eax, eax
0x18000ffeb  and     eax, 0FFFFFFFEh
0x18000ffee  inc     eax
0x18000fff0  mov     rbx, [rsp+28h+arg_0]
0x18000fff5  add     rsp, 20h
0x18000fff9  pop     rdi
0x18000fffa  retn
```
