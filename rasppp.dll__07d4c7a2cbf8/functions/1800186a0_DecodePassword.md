# DecodePassword

- ea: `0x1800186a0`
- end: `0x180018735`
- name: `DecodePassword`
- size: `149`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180001e00`
- `0x180014d00`
- `0x180016d40`
- `0x180017790`
- `0x180029a2c`

## callees

- `0x1800186a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018704`
- `CRYPT32!CryptUnprotectData` at `0x1800186fa`
- `CRYPT32!CryptUnprotectData` at `0x1800186fa`

## pseudocode

```c
__int64 __fastcall DecodePassword(DATA_BLOB *a1, DWORD *a2, BYTE **a3)
{
  unsigned int v5; // ebx
  DATA_BLOB v7; // [rsp+40h] [rbp-18h] BYREF

  if ( a1 && a2 && a3 )
  {
    v5 = 0;
    *a2 = 0;
    *a3 = 0;
    if ( a1->pbData && a1->cbData )
    {
      v7 = 0;
      if ( CryptUnprotectData(a1, 0, 0, 0, 0, 5u, &v7) )
      {
        *a2 = v7.cbData;
        *a3 = v7.pbData;
      }
      else
      {
        return GetLastError();
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x1800186a0  mov     r11, rsp
0x1800186a3  mov     [r11+8], rbx
0x1800186a7  mov     [r11+10h], rsi
0x1800186ab  push    rdi
0x1800186ac  sub     rsp, 50h
0x1800186b0  mov     rdi, r8
0x1800186b3  mov     rsi, rdx
0x1800186b6  test    rcx, rcx
0x1800186b9  jz      short loc_18001871E
0x1800186bb  test    rdx, rdx
0x1800186be  jz      short loc_18001871E
0x1800186c0  test    r8, r8
0x1800186c3  jz      short loc_18001871E
0x1800186c5  xor     ebx, ebx
0x1800186c7  mov     [rdx], ebx
0x1800186c9  mov     [r8], rbx
0x1800186cc  cmp     [rcx+8], rbx
0x1800186d0  jz      short loc_180018723
0x1800186d2  cmp     [rcx], ebx
0x1800186d4  jz      short loc_180018723
0x1800186d6  lea     rax, [r11-18h]
0x1800186da  xorps   xmm0, xmm0
0x1800186dd  mov     [r11-28h], rax
0x1800186e1  xor     r9d, r9d; pvReserved
0x1800186e4  mov     [rsp+58h+dwFlags], 5; dwFlags
0x1800186ec  xor     r8d, r8d; pOptionalEntropy
0x1800186ef  xor     edx, edx; ppszDataDescr
0x1800186f1  mov     [r11-38h], rbx
0x1800186f5  movups  xmmword ptr [rsp+58h+var_18.cbData], xmm0
0x1800186fa  call    cs:__imp_CryptUnprotectData
0x180018700  test    eax, eax
0x180018702  jnz     short loc_18001870E
0x180018704  call    cs:__imp_GetLastError
0x18001870a  mov     ebx, eax
0x18001870c  jmp     short loc_180018723
0x18001870e  mov     eax, [rsp+58h+var_18.cbData]
0x180018712  mov     [rsi], eax
0x180018714  mov     rax, [rsp+58h+var_18.pbData]
0x180018719  mov     [rdi], rax
0x18001871c  jmp     short loc_180018723
0x18001871e  mov     ebx, 80070057h
0x180018723  mov     rsi, [rsp+58h+arg_8]
0x180018728  mov     eax, ebx
0x18001872a  mov     rbx, [rsp+58h+arg_0]
0x18001872f  add     rsp, 50h
0x180018733  pop     rdi
0x180018734  retn
```
