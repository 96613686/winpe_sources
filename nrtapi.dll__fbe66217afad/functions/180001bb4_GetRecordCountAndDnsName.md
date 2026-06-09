# GetRecordCountAndDnsName

- ea: `0x180001bb4`
- end: `0x180001c8d`
- name: `GetRecordCountAndDnsName`
- size: `217`
- prototype: `__int64 __fastcall(__int64 *, _WORD *, __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001560`

## callees

- `0x180001bb4`

## pseudocode

```c
__int64 __fastcall GetRecordCountAndDnsName(__int64 *a1, _WORD *a2, __int16 *a3, _QWORD *a4)
{
  __int64 *v4; // r10
  char v5; // bl
  char v6; // di
  __int16 v7; // cx
  unsigned int v8; // ecx

  *a2 = 0;
  *a3 = 0;
  v4 = a1;
  *a4 = 0;
  v5 = 0;
  v6 = 0;
  if ( a1 )
  {
    v7 = 0;
    while ( 1 )
    {
      if ( *a2 == 0xFFFF || v7 == -1 )
      {
        v8 = -1073741811;
        *a2 = 0;
        *a3 = 0;
        return v8;
      }
      if ( *((_WORD *)v4 + 8) == 1 )
        goto LABEL_15;
      if ( *((_WORD *)v4 + 8) == 5 )
        break;
      if ( *((_WORD *)v4 + 8) == 28 )
      {
        if ( *((_WORD *)v4 + 16)
          || *((_WORD *)v4 + 17)
          || *((_WORD *)v4 + 18)
          || *((_WORD *)v4 + 19)
          || *((_WORD *)v4 + 20)
          || *((_WORD *)v4 + 21) != 0xFFFF )
        {
          *a3 = ++v7;
        }
        else
        {
          v7 = *a3;
LABEL_15:
          ++*a2;
        }
        if ( v5 || v6 )
          goto LABEL_20;
        v6 = 1;
LABEL_19:
        *a4 = v4[1];
      }
LABEL_20:
      v4 = (__int64 *)*v4;
      if ( !v4 )
        return 0;
    }
    if ( v5 )
      goto LABEL_20;
    v5 = 1;
    goto LABEL_19;
  }
  return 0;
}

```

## disassembly

```asm
0x180001bb4  push    rbx
0x180001bb6  push    rbp
0x180001bb7  push    rsi
0x180001bb8  push    rdi
0x180001bb9  push    r14
0x180001bbb  xor     ebp, ebp
0x180001bbd  mov     rsi, r8
0x180001bc0  mov     [rdx], bp
0x180001bc3  mov     r11, rdx
0x180001bc6  mov     [r8], bp
0x180001bca  mov     r10, rcx
0x180001bcd  mov     [r9], rbp
0x180001bd0  mov     bl, bpl
0x180001bd3  mov     dil, bpl
0x180001bd6  test    rcx, rcx
0x180001bd9  jz      loc_180001C63
0x180001bdf  mov     ecx, ebp
0x180001be1  mov     r14d, 0FFFFh
0x180001be7  movzx   r8d, word ptr [r11]
0x180001beb  cmp     r8w, r14w
0x180001bef  jz      loc_180001C7F
0x180001bf5  cmp     cx, r14w
0x180001bf9  jz      loc_180001C7F
0x180001bff  movzx   edx, word ptr [r10+10h]
0x180001c04  sub     edx, 1
0x180001c07  jz      short loc_180001C40
0x180001c09  sub     edx, 4
0x180001c0c  jz      short loc_180001C77
0x180001c0e  cmp     edx, 17h
0x180001c11  jnz     short loc_180001C5B
0x180001c13  cmp     [r10+20h], bp
0x180001c18  jnz     short loc_180001C6F
0x180001c1a  cmp     [r10+22h], bp
0x180001c1f  jnz     short loc_180001C6F
0x180001c21  cmp     [r10+24h], bp
0x180001c26  jnz     short loc_180001C6F
0x180001c28  cmp     [r10+26h], bp
0x180001c2d  jnz     short loc_180001C6F
0x180001c2f  cmp     [r10+28h], bp
0x180001c34  jnz     short loc_180001C6F
0x180001c36  cmp     [r10+2Ah], r14w
0x180001c3b  jnz     short loc_180001C6F
0x180001c3d  movzx   ecx, word ptr [rsi]
0x180001c40  inc     r8w
0x180001c44  mov     [r11], r8w
0x180001c48  test    bl, bl
0x180001c4a  jnz     short loc_180001C5B
0x180001c4c  test    dil, dil
0x180001c4f  jnz     short loc_180001C5B
0x180001c51  mov     dil, 1
0x180001c54  mov     rax, [r10+8]
0x180001c58  mov     [r9], rax
0x180001c5b  mov     r10, [r10]
0x180001c5e  test    r10, r10
0x180001c61  jnz     short loc_180001BE7
0x180001c63  mov     ecx, ebp
0x180001c65  mov     eax, ecx
0x180001c67  pop     r14
0x180001c69  pop     rdi
0x180001c6a  pop     rsi
0x180001c6b  pop     rbp
0x180001c6c  pop     rbx
0x180001c6d  retn
0x180001c6f  inc     cx
0x180001c72  mov     [rsi], cx
0x180001c75  jmp     short loc_180001C48
0x180001c77  test    bl, bl
0x180001c79  jnz     short loc_180001C5B
0x180001c7b  mov     bl, 1
0x180001c7d  jmp     short loc_180001C54
0x180001c7f  mov     ecx, 0C000000Dh
0x180001c84  mov     [r11], bp
0x180001c88  mov     [rsi], bp
0x180001c8b  jmp     short loc_180001C65
```
