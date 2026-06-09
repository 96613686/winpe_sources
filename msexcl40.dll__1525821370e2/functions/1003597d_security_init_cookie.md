# ___security_init_cookie

- ea: `0x1003597d`
- end: `0x100359c8`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100354e0`

## callees

- `0x10035928`
- `0x1003597d`

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
0x1003597d  mov     ecx, ___security_cookie
0x10035983  push    esi
0x10035984  push    edi
0x10035985  mov     edi, 0BB40E64Eh
0x1003598a  mov     esi, 0FFFF0000h
0x1003598f  cmp     ecx, edi
0x10035991  jz      short loc_10035997
0x10035993  test    esi, ecx
0x10035995  jnz     short loc_100359BD
0x10035997  call    __get_entropy
0x1003599c  mov     ecx, eax
0x1003599e  cmp     ecx, edi
0x100359a0  jnz     short loc_100359A9
0x100359a2  mov     ecx, 0BB40E64Fh
0x100359a7  jmp     short loc_100359B7
0x100359a9  test    esi, ecx
0x100359ab  jnz     short loc_100359B7
0x100359ad  or      eax, 4711h
0x100359b2  shl     eax, 10h
0x100359b5  or      ecx, eax
0x100359b7  mov     ___security_cookie, ecx
0x100359bd  not     ecx
0x100359bf  pop     edi
0x100359c0  mov     ___security_cookie_complement, ecx
0x100359c6  pop     esi
0x100359c7  retn
```
