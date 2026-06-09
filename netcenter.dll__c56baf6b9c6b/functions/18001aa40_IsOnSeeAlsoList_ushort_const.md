# IsOnSeeAlsoList(ushort const *)

- ea: `0x18001aa40`
- end: `0x18001aac1`
- name: `?IsOnSeeAlsoList@@YAHPEBG@Z`
- size: `129`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001a5e8`

## callees

- `0x18001aa40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001aa5b`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18001aa5b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aa9c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001aa9c`

## pseudocode

```c
__int64 __fastcall IsOnSeeAlsoList(const unsigned __int16 *a1)
{
  wchar_t *v3; // rax
  const WCHAR *v4; // rbx
  unsigned int i; // edi

  if ( !a1 )
    return 0;
  v3 = wcsrchr(a1, 0x5Cu);
  if ( v3 )
    v4 = v3 + 1;
  else
    v4 = a1;
  for ( i = 0; i < 0xA; ++i )
  {
    if ( CompareStringOrdinal(v4, -1, (&off_180025DD0)[2 * (int)i], -1, 1) == 2 )
      return *((unsigned int *)&off_180025DD0 + 4 * (int)i + 2);
  }
  return 1;
}

```

## disassembly

```asm
0x18001aa40  push    rbx
0x18001aa42  push    rsi
0x18001aa43  push    rdi
0x18001aa44  push    r14
0x18001aa46  sub     rsp, 38h
0x18001aa4a  mov     rdi, rcx
0x18001aa4d  test    rcx, rcx
0x18001aa50  jnz     short loc_18001AA56
0x18001aa52  xor     eax, eax
0x18001aa54  jmp     short loc_18001AAB7
0x18001aa56  mov     edx, 5Ch ; '\'; Ch
0x18001aa5b  call    cs:__imp_wcsrchr
0x18001aa61  mov     rbx, rax
0x18001aa64  test    rax, rax
0x18001aa67  jz      short loc_18001AA6F
0x18001aa69  add     rbx, 2
0x18001aa6d  jmp     short loc_18001AA72
0x18001aa6f  mov     rbx, rdi
0x18001aa72  xor     edi, edi
0x18001aa74  lea     r14, off_180025DD0; "{76F3B348-95E1-4B1E-BD1B-E0026D615651}"
0x18001aa7b  cmp     edi, 0Ah
0x18001aa7e  jnb     short loc_18001AAB2
0x18001aa80  or      r9d, 0FFFFFFFFh; cchCount2
0x18001aa84  movsxd  rsi, edi
0x18001aa87  add     rsi, rsi
0x18001aa8a  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x18001aa92  or      edx, r9d; cchCount1
0x18001aa95  mov     rcx, rbx; lpString1
0x18001aa98  mov     r8, [r14+rsi*8]; lpString2
0x18001aa9c  call    cs:__imp_CompareStringOrdinal
0x18001aaa2  cmp     eax, 2
0x18001aaa5  jz      short loc_18001AAAB
0x18001aaa7  inc     edi
0x18001aaa9  jmp     short loc_18001AA7B
0x18001aaab  mov     eax, [r14+rsi*8+8]
0x18001aab0  jmp     short loc_18001AAB7
0x18001aab2  mov     eax, 1
0x18001aab7  add     rsp, 38h
0x18001aabb  pop     r14
0x18001aabd  pop     rdi
0x18001aabe  pop     rsi
0x18001aabf  pop     rbx
0x18001aac0  retn
```
