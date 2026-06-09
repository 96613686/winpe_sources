# STATIC_WSTRING_HASH::FindKey(ushort const *,int)

- ea: `0x180009cb0`
- end: `0x180009d6c`
- name: `?FindKey@STATIC_WSTRING_HASH@@QEAAPEAUSTATIC_WSTRING_HASH_RECORD@@PEBGH@Z`
- size: `188`
- prototype: `struct STATIC_WSTRING_HASH_RECORD *(STATIC_WSTRING_HASH *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d74`
- `0x18000abfc`

## callees

- `0x180009cb0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009d4d`
- `msvcrt!_wcsicmp` at `0x180009d4d`

## pseudocode

```c
struct STATIC_WSTRING_HASH_RECORD *__fastcall STATIC_WSTRING_HASH::FindKey(STATIC_WSTRING_HASH *this, wchar_t *a2)
{
  wchar_t v2; // ax
  const wchar_t *v3; // rdi
  unsigned int v5; // r8d
  wchar_t v6; // cx
  __int64 i; // rbx
  const wchar_t *v8; // rdx
  const wchar_t *v9; // rax
  signed __int64 v10; // rdx
  int v11; // r8d
  int v12; // ecx
  bool v13; // zf

  v2 = *a2;
  v3 = a2;
  v5 = 0;
  if ( *((_DWORD *)this + 262) )
  {
    while ( v2 )
    {
      ++a2;
      v5 = v2 + 101 * v5;
      v2 = *a2;
    }
  }
  else
  {
    while ( v2 )
    {
      v6 = v2;
      v2 = *++a2;
      v5 = (v6 & 0xFFDF) + 101 * v5;
    }
  }
  for ( i = *((_QWORD *)this + v5 % 0x83); i; i = *(_QWORD *)(i + 8) )
  {
    v8 = *(const wchar_t **)i;
    if ( *((_DWORD *)this + 262) )
    {
      v9 = v3;
      v10 = (char *)v8 - (char *)v3;
      do
      {
        v11 = *(const wchar_t *)((char *)v9 + v10);
        v12 = *v9 - v11;
        if ( v12 )
          break;
        ++v9;
      }
      while ( v11 );
      v13 = v12 == 0;
    }
    else
    {
      v13 = _wcsicmp(v3, v8) == 0;
    }
    if ( v13 )
      break;
  }
  return (struct STATIC_WSTRING_HASH_RECORD *)i;
}

```

## disassembly

```asm
0x180009cb0  push    rbx
0x180009cb2  push    rbp
0x180009cb3  push    rsi
0x180009cb4  push    rdi
0x180009cb5  sub     rsp, 28h
0x180009cb9  movzx   eax, word ptr [rdx]
0x180009cbc  xor     ebp, ebp
0x180009cbe  mov     rdi, rdx
0x180009cc1  mov     rsi, rcx
0x180009cc4  mov     r8d, ebp
0x180009cc7  cmp     [rcx+418h], ebp
0x180009ccd  jz      short loc_180009D00
0x180009ccf  jmp     short loc_180009CE2
0x180009cd1  movzx   eax, ax
0x180009cd4  lea     rdx, [rdx+2]
0x180009cd8  imul    r8d, 65h ; 'e'
0x180009cdc  add     r8d, eax
0x180009cdf  movzx   eax, word ptr [rdx]
0x180009ce2  test    ax, ax
0x180009ce5  jnz     short loc_180009CD1
0x180009ce7  jmp     short loc_180009D05
0x180009ce9  movzx   ecx, ax
0x180009cec  lea     rdx, [rdx+2]
0x180009cf0  movzx   eax, word ptr [rdx]
0x180009cf3  and     ecx, 0FFDFh
0x180009cf9  imul    r8d, 65h ; 'e'
0x180009cfd  add     r8d, ecx
0x180009d00  test    ax, ax
0x180009d03  jnz     short loc_180009CE9
0x180009d05  mov     eax, 0FA232CF3h
0x180009d0a  mul     r8d
0x180009d0d  shr     edx, 7
0x180009d10  imul    eax, edx, 83h
0x180009d16  sub     r8d, eax
0x180009d19  mov     rbx, [rsi+r8*8]
0x180009d1d  jmp     short loc_180009D5B
0x180009d1f  mov     rdx, [rbx]; String2
0x180009d22  cmp     [rsi+418h], ebp
0x180009d28  jz      short loc_180009D4A
0x180009d2a  mov     rax, rdi
0x180009d2d  sub     rdx, rdi
0x180009d30  movzx   ecx, word ptr [rax]
0x180009d33  movzx   r8d, word ptr [rax+rdx]
0x180009d38  sub     ecx, r8d
0x180009d3b  jnz     short loc_180009D46
0x180009d3d  add     rax, 2
0x180009d41  test    r8d, r8d
0x180009d44  jnz     short loc_180009D30
0x180009d46  test    ecx, ecx
0x180009d48  jmp     short loc_180009D55
0x180009d4a  mov     rcx, rdi; String1
0x180009d4d  call    cs:__imp__wcsicmp
0x180009d53  test    eax, eax
0x180009d55  jz      short loc_180009D60
0x180009d57  mov     rbx, [rbx+8]
0x180009d5b  test    rbx, rbx
0x180009d5e  jnz     short loc_180009D1F
0x180009d60  mov     rax, rbx
0x180009d63  add     rsp, 28h
0x180009d67  pop     rdi
0x180009d68  pop     rsi
0x180009d69  pop     rbp
0x180009d6a  pop     rbx
0x180009d6b  retn
```
