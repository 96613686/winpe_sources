# CdConvertBigToLittleEndian

- ea: `0x140015fac`
- end: `0x14001601e`
- name: `CdConvertBigToLittleEndian`
- size: `114`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140012a14`
- `0x140013c0c`
- `0x140015090`
- `0x140016dc0`

## callees

- `0x140001114`
- `0x140003000`
- `0x140015fac`

## pseudocode

```c
unsigned __int8 __fastcall CdConvertBigToLittleEndian(__int64 a1, unsigned __int8 *a2, int a3, unsigned __int8 *a4)
{
  int v5; // ebx
  unsigned __int8 *v6; // rdi
  unsigned __int8 result; // al
  unsigned __int8 *i; // rcx

  v5 = a3;
  v6 = a2;
  if ( (a3 & 1) != 0 )
    CdRaiseStatusEx(a1, -1073741774, 0, 1179648, 163);
  result = (unsigned __int8)memmove(a4, a2 + 1, (unsigned int)(a3 - 1));
  for ( i = a4 + 1; v5; v5 -= 2 )
  {
    result = *v6;
    v6 += 2;
    *i = result;
    i += 2;
  }
  return result;
}

```

## disassembly

```asm
0x140015fac  mov     [rsp+arg_0], rbx
0x140015fb1  mov     [rsp+arg_8], rsi
0x140015fb6  push    rdi
0x140015fb7  sub     rsp, 30h
0x140015fbb  mov     rsi, r9
0x140015fbe  mov     ebx, r8d
0x140015fc1  mov     rdi, rdx
0x140015fc4  test    r8b, 1
0x140015fc8  jnz     short loc_140016002
0x140015fca  dec     r8d; Size
0x140015fcd  inc     rdx; Src
0x140015fd0  mov     rcx, r9; void *
0x140015fd3  call    memmove
0x140015fd8  lea     rcx, [rsi+1]
0x140015fdc  test    ebx, ebx
0x140015fde  jz      short loc_140015FF1
0x140015fe0  mov     al, [rdi]
0x140015fe2  lea     rdi, [rdi+2]
0x140015fe6  mov     [rcx], al
0x140015fe8  lea     rcx, [rcx+2]
0x140015fec  add     ebx, 0FFFFFFFEh
0x140015fef  jnz     short loc_140015FE0
0x140015ff1  mov     rbx, [rsp+38h+arg_0]
0x140015ff6  mov     rsi, [rsp+38h+arg_8]
0x140015ffb  add     rsp, 30h
0x140015fff  pop     rdi
0x140016000  retn
0x140016002  mov     r9d, 120000h
0x140016008  mov     [rsp+38h+var_18], 0A3h
0x140016010  xor     r8d, r8d
0x140016013  mov     edx, 0C0000032h
0x140016018  call    CdRaiseStatusEx
```
