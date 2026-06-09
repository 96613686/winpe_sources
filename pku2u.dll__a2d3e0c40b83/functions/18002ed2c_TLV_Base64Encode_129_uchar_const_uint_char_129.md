# TLV::Base64Encode<129>(uchar const *,uint,char (&)[129])

- ea: `0x18002ed2c`
- end: `0x18002edc5`
- name: `??$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002edcc`

## callees

- `0x18002ed2c`

## string_xrefs

- `0x18002ed34`: `ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789+/onecore\ds\security\protocols\pku2u\ctxtmgr.cxx`

## pseudocode

```c
char __fastcall TLV::Base64Encode<129>(unsigned __int8 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r11
  int v6; // esi
  unsigned int v7; // r8d
  unsigned int v8; // r9d
  unsigned int v9; // r10d
  __int64 v10; // r11
  __int64 v11; // r11
  __int64 v12; // r11
  char result; // al

  v3 = 0;
  v6 = 4;
  do
  {
    v7 = a1[2];
    v8 = *a1;
    v9 = a1[1];
    a1 += 3;
    *(_BYTE *)(v3 + a3) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[(unsigned __int64)v8 >> 2];
    v10 = (unsigned int)(v3 + 1);
    *(_BYTE *)(v10 + a3) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v9 >> 4)
                                                                      | (unsigned __int8)(16 * (v8 & 3))];
    v11 = (unsigned int)(v10 + 1);
    *(_BYTE *)(v11 + a3) = `TLV::Base64Encode<129>'::`2'::s_lookupTable[((unsigned __int64)v7 >> 6)
                                                                      | (unsigned __int8)(4 * (v9 & 0xF))];
    v12 = (unsigned int)(v11 + 1);
    result = `TLV::Base64Encode<129>'::`2'::s_lookupTable[v7 & 0x3F];
    *(_BYTE *)(v12 + a3) = result;
    v3 = (unsigned int)(v12 + 1);
    --v6;
  }
  while ( v6 );
  *(_BYTE *)(v3 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x18002ed2c  push    rbx
0x18002ed2e  push    rbp
0x18002ed2f  push    rsi
0x18002ed30  push    rdi
0x18002ed31  xor     r11d, r11d
0x18002ed34  lea     rbp, ?s_lookupTable@?1???$Base64Encode@$0IB@@TLV@@YAXPEBEIAEAY0IB@D@Z@4QBDB; "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklm"...
0x18002ed3b  mov     rbx, r8
0x18002ed3e  mov     rdi, rcx
0x18002ed41  lea     esi, [r11+4]
0x18002ed45  movzx   r8d, byte ptr [rdi+2]
0x18002ed4a  movzx   r9d, byte ptr [rdi]
0x18002ed4e  movzx   r10d, byte ptr [rdi+1]
0x18002ed53  lea     rdi, [rdi+3]
0x18002ed57  mov     eax, r9d
0x18002ed5a  and     r9b, 3
0x18002ed5e  shr     rax, 2
0x18002ed62  shl     r9b, 4
0x18002ed66  movzx   ecx, r9b
0x18002ed6a  mov     al, [rax+rbp]
0x18002ed6d  mov     [r11+rbx], al
0x18002ed71  inc     r11d
0x18002ed74  mov     eax, r10d
0x18002ed77  and     r10b, 0Fh
0x18002ed7b  shr     rax, 4
0x18002ed7f  or      rcx, rax
0x18002ed82  shl     r10b, 2
0x18002ed86  mov     al, [rcx+rbp]
0x18002ed89  mov     [r11+rbx], al
0x18002ed8d  inc     r11d
0x18002ed90  mov     eax, r8d
0x18002ed93  movzx   ecx, r10b
0x18002ed97  shr     rax, 6
0x18002ed9b  and     r8d, 3Fh
0x18002ed9f  or      rcx, rax
0x18002eda2  mov     al, [rcx+rbp]
0x18002eda5  mov     [r11+rbx], al
0x18002eda9  inc     r11d
0x18002edac  mov     al, [r8+rbp]
0x18002edb0  mov     [r11+rbx], al
0x18002edb4  inc     r11d
0x18002edb7  add     esi, 0FFFFFFFFh
0x18002edba  jnz     short loc_18002ED45
0x18002edbc  mov     [r11+rbx], sil
0x18002edc0  pop     rdi
0x18002edc1  pop     rsi
0x18002edc2  pop     rbp
0x18002edc3  pop     rbx
0x18002edc4  retn
```
