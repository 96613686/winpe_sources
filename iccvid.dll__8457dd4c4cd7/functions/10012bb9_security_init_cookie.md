# ___security_init_cookie

- ea: `0x10012bb9`
- end: `0x10012c04`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10012b20`

## callees

- `0x10012b64`
- `0x10012bb9`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // ecx
  unsigned int entropy; // eax

  v0 = __security_cookie;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    entropy = _get_entropy();
    v0 = entropy;
    if ( entropy == -1153374642 )
    {
      v0 = -1153374641;
    }
    else if ( (entropy & 0xFFFF0000) == 0 )
    {
      v0 = ((entropy | 0x4711) << 16) | entropy;
    }
    __security_cookie = v0;
  }
  __security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x10012bb9  mov     ecx, ___security_cookie
0x10012bbf  push    esi
0x10012bc0  push    edi
0x10012bc1  mov     edi, 0BB40E64Eh
0x10012bc6  mov     esi, 0FFFF0000h
0x10012bcb  cmp     ecx, edi
0x10012bcd  jz      short loc_10012BD3
0x10012bcf  test    esi, ecx
0x10012bd1  jnz     short loc_10012BF9
0x10012bd3  call    __get_entropy
0x10012bd8  mov     ecx, eax
0x10012bda  cmp     ecx, edi
0x10012bdc  jnz     short loc_10012BE5
0x10012bde  mov     ecx, 0BB40E64Fh
0x10012be3  jmp     short loc_10012BF3
0x10012be5  test    esi, ecx
0x10012be7  jnz     short loc_10012BF3
0x10012be9  or      eax, 4711h
0x10012bee  shl     eax, 10h
0x10012bf1  or      ecx, eax
0x10012bf3  mov     ___security_cookie, ecx
0x10012bf9  not     ecx
0x10012bfb  pop     edi
0x10012bfc  mov     ___security_cookie_complement, ecx
0x10012c02  pop     esi
0x10012c03  retn
```
