# ASN1bitcpy

- ea: `0x180008dd4`
- end: `0x180008f14`
- name: `ASN1bitcpy`
- size: `320`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003be0`

## callees

- `0x180008dd4`
- `0x18000aadd`

## pseudocode

```c
void __fastcall ASN1bitcpy(char *a1, unsigned int a2, char *a3, unsigned int a4)
{
  __int64 v4; // rdi
  char *v5; // r15
  char *v6; // r14
  unsigned int v7; // eax
  __int64 v8; // rsi
  unsigned __int8 v9; // r8
  size_t v10; // rbx
  char v11; // al
  char v12; // dl
  char v13; // r8

  if ( a4 )
  {
    v4 = a4;
    v5 = a3;
    v6 = a1;
    if ( a4 + 7 > a4 )
    {
      v7 = a2 + a4;
      if ( a2 + a4 >= a4 && v7 + 7 > a4 && v7 + 7 > v7 )
      {
        LODWORD(v8) = 0;
        if ( a2 >= 8 )
        {
          v6 = &a1[(unsigned __int64)a2 >> 3];
          a2 &= 7u;
        }
        if ( a2 )
        {
          v9 = *a3;
          v8 = 8 - a2;
          if ( a4 < (unsigned int)v8 )
          {
            *v6 |= (*((_BYTE *)&qword_18000C760[2] + a4) & (unsigned __int8)(v9 >> (8 - a4))) << (8 - a2 - a4);
            return;
          }
          *v6++ |= *((_BYTE *)&qword_18000C760[2] + v8) & (v9 >> a2);
          v4 = a4 - (unsigned int)v8;
        }
        if ( (unsigned int)v4 >= 8 )
        {
          if ( (_DWORD)v8 )
          {
            do
            {
              v11 = *v5;
              v4 = (unsigned int)(v4 - 8);
              v12 = (unsigned __int8)*++v5 >> (8 - v8);
              *v6++ = (v11 << v8) | v12;
            }
            while ( (unsigned int)v4 >= 8 );
          }
          else
          {
            v10 = (unsigned __int64)(unsigned int)v4 >> 3;
            memcpy_0(v6, v5, v10);
            v6 += v10;
            v5 += v10;
            v4 &= 7u;
          }
        }
        if ( (_DWORD)v4 )
        {
          v13 = *((_BYTE *)qword_18000C760 + v4) & (*v5 << v8);
          *v6 = v13;
          if ( (unsigned int)(v8 + v4) > 8 )
            *v6 = v13
                | ((unsigned __int8)(v5[1] & *((_BYTE *)qword_18000C760 + (unsigned int)(v8 + v4 - 8))) >> (8 - v8));
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180008dd4  test    r9d, r9d
0x180008dd7  jz      locret_180008F13
0x180008ddd  push    rbx
0x180008dde  push    rbp
0x180008ddf  push    rsi
0x180008de0  push    rdi
0x180008de1  push    r12
0x180008de3  push    r14
0x180008de5  push    r15
0x180008de7  sub     rsp, 20h
0x180008deb  mov     edi, r9d
0x180008dee  mov     r15, r8
0x180008df1  mov     r14, rcx
0x180008df4  lea     eax, [rdi+7]
0x180008df7  cmp     eax, edi
0x180008df9  jbe     loc_180008F05
0x180008dff  lea     eax, [rdx+rdi]
0x180008e02  cmp     eax, edi
0x180008e04  jb      loc_180008F05
0x180008e0a  lea     ecx, [rax+7]
0x180008e0d  cmp     ecx, edi
0x180008e0f  jbe     loc_180008F05
0x180008e15  cmp     ecx, eax
0x180008e17  jbe     loc_180008F05
0x180008e1d  xor     esi, esi
0x180008e1f  lea     ebp, [rsi+8]
0x180008e22  cmp     edx, ebp
0x180008e24  jb      short loc_180008E32
0x180008e26  mov     eax, edx
0x180008e28  shr     rax, 3
0x180008e2c  add     r14, rax
0x180008e2f  and     edx, 7
0x180008e32  lea     r12, cs:180000000h
0x180008e39  test    edx, edx
0x180008e3b  jz      short loc_180008E5D
0x180008e3d  mov     r8b, [r8]
0x180008e40  mov     esi, ebp
0x180008e42  sub     esi, edx
0x180008e44  cmp     edi, esi
0x180008e46  jb      short loc_180008E84
0x180008e48  mov     cl, dl
0x180008e4a  shr     r8b, cl
0x180008e4d  and     r8b, [rsi+r12+0C770h]
0x180008e55  or      [r14], r8b
0x180008e58  inc     r14
0x180008e5b  sub     edi, esi
0x180008e5d  cmp     edi, ebp
0x180008e5f  jb      short loc_180008ECA
0x180008e61  test    esi, esi
0x180008e63  jnz     short loc_180008EA2
0x180008e65  mov     ebx, edi
0x180008e67  mov     rdx, r15; Src
0x180008e6a  shr     rbx, 3
0x180008e6e  mov     rcx, r14; void *
0x180008e71  mov     r8, rbx; Size
0x180008e74  call    memcpy_0
0x180008e79  add     r14, rbx
0x180008e7c  add     r15, rbx
0x180008e7f  and     edi, 7
0x180008e82  jmp     short loc_180008ECA
0x180008e84  sub     bpl, dil
0x180008e87  sub     esi, edi
0x180008e89  mov     cl, bpl
0x180008e8c  shr     r8b, cl
0x180008e8f  mov     cl, sil
0x180008e92  and     r8b, [rdi+r12+0C770h]
0x180008e9a  shl     r8b, cl
0x180008e9d  or      [r14], r8b
0x180008ea0  jmp     short loc_180008F05
0x180008ea2  mov     r9d, ebp
0x180008ea5  sub     r9b, sil
0x180008ea8  mov     dl, [r15+1]
0x180008eac  mov     cl, r9b
0x180008eaf  mov     al, [r15]
0x180008eb2  add     edi, 0FFFFFFF8h
0x180008eb5  shr     dl, cl
0x180008eb7  inc     r15
0x180008eba  mov     ecx, esi
0x180008ebc  shl     al, cl
0x180008ebe  or      dl, al
0x180008ec0  mov     [r14], dl
0x180008ec3  inc     r14
0x180008ec6  cmp     edi, ebp
0x180008ec8  jnb     short loc_180008EA8
0x180008eca  test    edi, edi
0x180008ecc  jz      short loc_180008F05
0x180008ece  mov     r8b, [r15]
0x180008ed1  lea     eax, [rsi+rdi]
0x180008ed4  mov     ecx, esi
0x180008ed6  shl     r8b, cl
0x180008ed9  and     r8b, [rdi+r12+0C760h]
0x180008ee1  mov     [r14], r8b
0x180008ee4  cmp     eax, ebp
0x180008ee6  jbe     short loc_180008F05
0x180008ee8  add     eax, 0FFFFFFF8h
0x180008eeb  sub     bpl, sil
0x180008eee  mov     cl, bpl
0x180008ef1  mov     al, [rax+r12+0C760h]
0x180008ef9  and     al, [r15+1]
0x180008efd  shr     al, cl
0x180008eff  or      al, r8b
0x180008f02  mov     [r14], al
0x180008f05  add     rsp, 20h
0x180008f09  pop     r15
0x180008f0b  pop     r14
0x180008f0d  pop     r12
0x180008f0f  pop     rdi
0x180008f10  pop     rsi
0x180008f11  pop     rbp
0x180008f12  pop     rbx
0x180008f13  retn
```
