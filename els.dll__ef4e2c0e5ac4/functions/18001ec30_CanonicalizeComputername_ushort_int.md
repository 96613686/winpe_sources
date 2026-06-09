# CanonicalizeComputername(ushort *,int)

- ea: `0x18001ec30`
- end: `0x18001ed21`
- name: `?CanonicalizeComputername@@YAJPEAGH@Z`
- size: `241`
- prototype: `__int64 __fastcall(wchar_t *Destination, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800146dc`

## callees

- `0x1800036b2`
- `0x18001ec30`
- `0x180022292`
- `0x1800222d0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18001ecfd`
- `msvcrt!wcscpy_s` at `0x18001ecfd`
- `netutils!NetpwNameValidate` at `0x18001ecbf`
- `netutils!NetpwNameValidate` at `0x18001ecbf`
- `netutils!NetpwNameCanonicalize` at `0x18001ece8`
- `netutils!NetpwNameCanonicalize` at `0x18001ece8`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001ec6f`
- `SHLWAPI!PathRemoveBlanksW` at `0x18001ec6f`

## pseudocode

```c
__int64 __fastcall CanonicalizeComputername(wchar_t *Destination)
{
  unsigned int v2; // edi
  rsize_t v3; // rsi
  wchar_t Source; // [rsp+30h] [rbp-248h] BYREF
  _BYTE v6[526]; // [rsp+32h] [rbp-246h] BYREF

  Source = 0;
  v2 = 0;
  memset_0(v6, 0, 0x206u);
  PathRemoveBlanksW(Destination);
  if ( *Destination )
  {
    v3 = -1;
    do
      ++v3;
    while ( Destination[v3] );
    if ( v3 >= 2 && *Destination == 92 && Destination[1] == 92 )
      memmove_0(Destination, Destination + 2, 2 * v3 - 2);
    if ( (unsigned int)NetpwNameValidate(Destination, 4)
      || (unsigned int)NetpwNameCanonicalize(Destination, &Source, 520, 4, 0) )
    {
      return (unsigned int)-2147024809;
    }
    else
    {
      wcscpy_s(Destination, v3, &Source);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001ec30  push    rbx
0x18001ec32  push    rbp
0x18001ec33  push    rsi
0x18001ec34  push    rdi
0x18001ec35  sub     rsp, 258h
0x18001ec3c  mov     rax, cs:__security_cookie
0x18001ec43  xor     rax, rsp
0x18001ec46  mov     [rsp+278h+var_38], rax
0x18001ec4e  mov     rbx, rcx
0x18001ec51  xor     ebp, ebp
0x18001ec53  lea     rcx, [rsp+278h+var_246]; void *
0x18001ec58  mov     [rsp+278h+Source], bp
0x18001ec5d  xor     edx, edx; Val
0x18001ec5f  mov     r8d, 206h; Size
0x18001ec65  mov     edi, ebp
0x18001ec67  call    memset_0
0x18001ec6c  mov     rcx, rbx; pszPath
0x18001ec6f  call    cs:__imp_PathRemoveBlanksW
0x18001ec75  cmp     [rbx], bp
0x18001ec78  jz      loc_18001ED03
0x18001ec7e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001ec82  inc     rsi
0x18001ec85  cmp     [rbx+rsi*2], bp
0x18001ec89  jnz     short loc_18001EC82
0x18001ec8b  cmp     rsi, 2
0x18001ec8f  jb      short loc_18001ECB5
0x18001ec91  mov     eax, 5Ch ; '\'
0x18001ec96  cmp     ax, [rbx]
0x18001ec99  jnz     short loc_18001ECB5
0x18001ec9b  cmp     ax, [rbx+2]
0x18001ec9f  jnz     short loc_18001ECB5
0x18001eca1  lea     r8, ds:0FFFFFFFFFFFFFFFEh[rsi*2]; Size
0x18001eca9  mov     rcx, rbx; void *
0x18001ecac  lea     rdx, [rbx+4]; Src
0x18001ecb0  call    memmove_0
0x18001ecb5  xor     r8d, r8d
0x18001ecb8  mov     rcx, rbx
0x18001ecbb  lea     edx, [r8+4]
0x18001ecbf  call    cs:__imp_NetpwNameValidate
0x18001ecc5  test    eax, eax
0x18001ecc7  jz      short loc_18001ECD0
0x18001ecc9  mov     edi, 80070057h
0x18001ecce  jmp     short loc_18001ED03
0x18001ecd0  mov     r9d, 4
0x18001ecd6  mov     [rsp+278h+var_258], ebp
0x18001ecda  mov     r8d, 208h
0x18001ece0  lea     rdx, [rsp+278h+Source]
0x18001ece5  mov     rcx, rbx
0x18001ece8  call    cs:__imp_NetpwNameCanonicalize
0x18001ecee  test    eax, eax
0x18001ecf0  jnz     short loc_18001ECC9
0x18001ecf2  lea     r8, [rsp+278h+Source]; Source
0x18001ecf7  mov     rdx, rsi; SizeInWords
0x18001ecfa  mov     rcx, rbx; Destination
0x18001ecfd  call    cs:__imp_wcscpy_s
0x18001ed03  mov     eax, edi
0x18001ed05  mov     rcx, [rsp+278h+var_38]
0x18001ed0d  xor     rcx, rsp; StackCookie
0x18001ed10  call    __security_check_cookie
0x18001ed15  add     rsp, 258h
0x18001ed1c  pop     rdi
0x18001ed1d  pop     rsi
0x18001ed1e  pop     rbp
0x18001ed1f  pop     rbx
0x18001ed20  retn
```
