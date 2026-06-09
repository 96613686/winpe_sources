# HandleBackslash

- ea: `0x180001d88`
- end: `0x180001e09`
- name: `HandleBackslash`
- size: `129`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c04`

## callees

- `0x180001d88`
- `0x180001e10`

## pseudocode

```c
__int64 __fastcall HandleBackslash(const unsigned __int16 **a1, const unsigned __int16 **a2, HLOCAL *a3)
{
  const unsigned __int16 *v3; // r9
  __int64 result; // rax
  unsigned __int16 v7; // r10
  unsigned int v8; // ecx

  v3 = *a1;
  result = 0;
  v7 = **a1;
  if ( v7 )
  {
    v8 = 0;
    while ( v7 == 92 )
    {
      if ( v8 + 1 < v8 )
        return 2147942934LL;
      if ( v8 + 1 > 0x7FFFFFFF )
        return 2147500037LL;
      ++v3;
      ++v8;
      *a1 = v3;
      result = 0;
      v7 = *v3;
      if ( !*v3 )
        return result;
    }
    if ( *v3 == 34 )
      return HandleDoubleQuote(v8, a1, a2, a3);
  }
  return result;
}

```

## disassembly

```asm
0x180001d88  push    rbx
0x180001d8a  sub     rsp, 20h
0x180001d8e  mov     r9, [rcx]
0x180001d91  xor     ebx, ebx
0x180001d93  mov     r11, rdx
0x180001d96  mov     eax, ebx
0x180001d98  mov     rdx, rcx
0x180001d9b  movzx   r10d, word ptr [r9]
0x180001d9f  test    r10w, r10w
0x180001da3  jz      short loc_180001E02
0x180001da5  mov     ecx, ebx
0x180001da7  cmp     r10w, 5Ch ; '\'
0x180001dac  jnz     short loc_180001DF0
0x180001dae  lea     eax, [rcx+1]
0x180001db1  cmp     eax, ecx
0x180001db3  jb      short loc_180001DE4
0x180001db5  cmp     eax, 7FFFFFFFh
0x180001dba  ja      short loc_180001DD8
0x180001dbc  add     r9, 2
0x180001dc0  mov     ecx, eax
0x180001dc2  mov     [rdx], r9
0x180001dc5  mov     eax, ebx
0x180001dc7  movzx   r10d, word ptr [r9]
0x180001dcb  test    r10w, r10w
0x180001dcf  jnz     short loc_180001DA7
0x180001dd1  add     rsp, 20h
0x180001dd5  pop     rbx
0x180001dd6  retn
0x180001dd8  mov     eax, 80004005h
0x180001ddd  add     rsp, 20h
0x180001de1  pop     rbx
0x180001de2  retn
0x180001de4  mov     eax, 80070216h
0x180001de9  add     rsp, 20h
0x180001ded  pop     rbx
0x180001dee  retn
0x180001df0  cmp     word ptr [r9], 22h ; '"'
0x180001df5  jnz     short loc_180001E02
0x180001df7  mov     r9, r8
0x180001dfa  mov     r8, r11
0x180001dfd  call    HandleDoubleQuote
0x180001e02  add     rsp, 20h
0x180001e06  pop     rbx
0x180001e07  retn
```
