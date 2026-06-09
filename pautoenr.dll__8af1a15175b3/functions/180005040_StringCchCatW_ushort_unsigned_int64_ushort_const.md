# StringCchCatW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005040`
- end: `0x1800050a0`
- name: `?StringCchCatW@@YAJPEAG_KPEBG@Z`
- size: `96`
- prototype: `HRESULT __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180003ed0`
- `0x1800074b0`

## callees

- `0x180004970`
- `0x180005040`

## pseudocode

```c
HRESULT __fastcall StringCchCatW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  size_t v3; // r9
  unsigned __int16 *v4; // rax
  size_t v6; // [rsp+20h] [rbp-18h]

  if ( a2 - 1 > 0x7FFFFFFE )
    return -2147024809;
  v3 = a2;
  v4 = a1;
  do
  {
    if ( !*v4 )
      break;
    ++v4;
    --v3;
  }
  while ( v3 );
  if ( v3 )
    return StringCopyWorkerW(&a1[a2 - v3], v3, a3, (STRSAFE_PCNZWCH)a3, v6);
  else
    return -2147024809;
}

```

## disassembly

```asm
0x180005040  sub     rsp, 38h
0x180005044  lea     rax, [rdx-1]
0x180005048  cmp     rax, 7FFFFFFEh
0x18000504e  ja      short loc_180005092
0x180005050  mov     r9, rdx
0x180005053  mov     rax, rcx
0x180005056  cmp     word ptr [rax], 0
0x18000505a  jz      short loc_180005066
0x18000505c  add     rax, 2
0x180005060  sub     r9, 1
0x180005064  jnz     short loc_180005056
0x180005066  xor     eax, eax
0x180005068  mov     r11, rdx
0x18000506b  sub     r11, r9
0x18000506e  mov     r10d, 80070057h
0x180005074  test    r9, r9
0x180005077  cmovz   r11, rax
0x18000507b  cmovnz  r10d, eax
0x18000507f  jz      short loc_180005098
0x180005081  sub     rdx, r11; cchDest
0x180005084  lea     rcx, [rcx+r11*2]; pszDest
0x180005088  mov     r9, r8; pszSrc
0x18000508b  call    StringCopyWorkerW
0x180005090  jmp     short loc_18000509B
0x180005092  mov     r10d, 80070057h
0x180005098  mov     eax, r10d
0x18000509b  add     rsp, 38h
0x18000509f  retn
```
