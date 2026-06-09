# HasDriveLetter

- ea: `0x14000bbe4`
- end: `0x14000bc3f`
- name: `HasDriveLetter`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000be4c`
- `0x14000fcc0`
- `0x14001a190`

## callees

- `0x14000bbe4`
- `0x140019ca0`

## pseudocode

```c
char __fastcall HasDriveLetter(__int64 a1, _BYTE *a2)
{
  char v2; // si
  __int64 *v4; // r14
  __int64 *i; // rbx

  v2 = 0;
  if ( a2 )
    *a2 = 0;
  v4 = (__int64 *)(a1 + 16);
  for ( i = *(__int64 **)(a1 + 16); i != v4; i = (__int64 *)*i )
  {
    if ( *((_BYTE *)i + 16) && IsDriveLetter((PCUNICODE_STRING)(i + 3)) )
    {
      v2 = 1;
      if ( a2 )
        *a2 = *(_BYTE *)(i[4] + 24);
      return v2;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x14000bbe4  push    rbx
0x14000bbe6  push    rsi
0x14000bbe7  push    rdi
0x14000bbe8  push    r14
0x14000bbea  sub     rsp, 28h
0x14000bbee  xor     sil, sil
0x14000bbf1  mov     rdi, rdx
0x14000bbf4  test    rdx, rdx
0x14000bbf7  jz      short loc_14000BBFC
0x14000bbf9  mov     [rdx], sil
0x14000bbfc  lea     r14, [rcx+10h]
0x14000bc00  mov     rbx, [r14]
0x14000bc03  cmp     rbx, r14
0x14000bc06  jz      short loc_14000BC31
0x14000bc08  cmp     [rbx+10h], sil
0x14000bc0c  jz      short loc_14000BC1B
0x14000bc0e  lea     rcx, [rbx+18h]; String2
0x14000bc12  call    IsDriveLetter
0x14000bc17  test    al, al
0x14000bc19  jnz     short loc_14000BC20
0x14000bc1b  mov     rbx, [rbx]
0x14000bc1e  jmp     short loc_14000BC03
0x14000bc20  mov     sil, 1
0x14000bc23  test    rdi, rdi
0x14000bc26  jz      short loc_14000BC31
0x14000bc28  mov     rcx, [rbx+20h]
0x14000bc2c  mov     dl, [rcx+18h]
0x14000bc2f  mov     [rdi], dl
0x14000bc31  mov     al, sil
0x14000bc34  add     rsp, 28h
0x14000bc38  pop     r14
0x14000bc3a  pop     rdi
0x14000bc3b  pop     rsi
0x14000bc3c  pop     rbx
0x14000bc3d  retn
```
