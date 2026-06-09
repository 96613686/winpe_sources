# EscapeString(ushort const *,ushort *,ulong)

- ea: `0x180002930`
- end: `0x180002a34`
- name: `?EscapeString@@YAJPEBGPEAGK@Z`
- size: `260`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800022b4`
- `0x180003ae8`

## callees

- `0x180002930`
- `0x180005246`

## pseudocode

```c
__int64 __fastcall EscapeString(const unsigned __int16 *a1, unsigned __int16 *a2, unsigned int a3)
{
  unsigned int v3; // ebx
  unsigned __int16 *v4; // rsi
  const unsigned __int16 *v5; // rdi
  unsigned __int16 v6; // r8
  _WORD *v7; // rdx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx

  v3 = a3;
  v4 = a2;
  v5 = a1;
  if ( !a1 || !a2 || !a3 )
    return 2147942487LL;
  memset_0(a2, 0, 2LL * a3);
  if ( *v5 )
  {
    while ( 1 )
    {
      if ( v3 <= 2 )
        return 0;
      v6 = *v5;
      v7 = v4 + 1;
      v8 = *v5++;
      v9 = v8 - 9;
      if ( !v9 )
      {
        *v4 = 92;
        *v7 = 116;
        goto LABEL_21;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        *v4 = 92;
        *v7 = 110;
        goto LABEL_21;
      }
      v11 = v10 - 3;
      if ( !v11 )
      {
        *v4 = 92;
        *v7 = 114;
        goto LABEL_21;
      }
      v12 = v11 - 19;
      if ( !v12 )
      {
        *v4 = 92;
        *v7 = 115;
        goto LABEL_21;
      }
      v13 = v12 - 6;
      if ( !v13 )
      {
        *v4 = 92;
        *v7 = 97;
        goto LABEL_21;
      }
      v14 = v13 - 22;
      if ( !v14 )
        break;
      if ( v14 == 32 )
      {
        *v4 = 92;
        *v7 = 92;
LABEL_21:
        v4 += 2;
        v3 -= 2;
        goto LABEL_22;
      }
      *v4 = v6;
      --v3;
      ++v4;
LABEL_22:
      if ( !*v5 )
        return 0;
    }
    *v4 = 92;
    *v7 = 108;
    goto LABEL_21;
  }
  return 0;
}

```

## disassembly

```asm
0x180002930  push    rbx
0x180002932  push    rbp
0x180002933  push    rsi
0x180002934  push    rdi
0x180002935  sub     rsp, 28h
0x180002939  xor     ebp, ebp
0x18000293b  mov     ebx, r8d
0x18000293e  mov     rsi, rdx
0x180002941  mov     rdi, rcx
0x180002944  test    rcx, rcx
0x180002947  jz      loc_180002A26
0x18000294d  test    rdx, rdx
0x180002950  jz      loc_180002A26
0x180002956  test    r8d, r8d
0x180002959  jz      loc_180002A26
0x18000295f  mov     r8d, ebx
0x180002962  xor     edx, edx; Val
0x180002964  add     r8, r8; Size
0x180002967  mov     rcx, rsi; void *
0x18000296a  call    memset_0
0x18000296f  cmp     [rdi], bp
0x180002972  jz      loc_180002A22
0x180002978  lea     r9d, [rbp+5Ch]
0x18000297c  mov     r10d, 0FFFFFFFEh
0x180002982  cmp     ebx, 2
0x180002985  jbe     loc_180002A22
0x18000298b  movzx   r8d, word ptr [rdi]
0x18000298f  lea     rdx, [rsi+2]
0x180002993  mov     ecx, r8d
0x180002996  add     rdi, 2
0x18000299a  sub     ecx, 9
0x18000299d  jz      short loc_180002A09
0x18000299f  sub     ecx, 1
0x1800029a2  jz      short loc_1800029FE
0x1800029a4  sub     ecx, 3
0x1800029a7  jz      short loc_1800029F3
0x1800029a9  sub     ecx, 13h
0x1800029ac  jz      short loc_1800029E8
0x1800029ae  sub     ecx, 6
0x1800029b1  jz      short loc_1800029DD
0x1800029b3  sub     ecx, 16h
0x1800029b6  jz      short loc_1800029D2
0x1800029b8  cmp     ecx, 20h ; ' '
0x1800029bb  jz      short loc_1800029C8
0x1800029bd  mov     [rsi], r8w
0x1800029c1  dec     ebx
0x1800029c3  mov     rsi, rdx
0x1800029c6  jmp     short loc_180002A19
0x1800029c8  mov     [rsi], r9w
0x1800029cc  mov     [rdx], r9w
0x1800029d0  jmp     short loc_180002A12
0x1800029d2  mov     [rsi], r9w
0x1800029d6  mov     word ptr [rdx], 6Ch ; 'l'
0x1800029db  jmp     short loc_180002A12
0x1800029dd  mov     [rsi], r9w
0x1800029e1  mov     word ptr [rdx], 61h ; 'a'
0x1800029e6  jmp     short loc_180002A12
0x1800029e8  mov     [rsi], r9w
0x1800029ec  mov     word ptr [rdx], 73h ; 's'
0x1800029f1  jmp     short loc_180002A12
0x1800029f3  mov     [rsi], r9w
0x1800029f7  mov     word ptr [rdx], 72h ; 'r'
0x1800029fc  jmp     short loc_180002A12
0x1800029fe  mov     [rsi], r9w
0x180002a02  mov     word ptr [rdx], 6Eh ; 'n'
0x180002a07  jmp     short loc_180002A12
0x180002a09  mov     [rsi], r9w
0x180002a0d  mov     word ptr [rdx], 74h ; 't'
0x180002a12  lea     rsi, [rdx+2]
0x180002a16  add     ebx, r10d
0x180002a19  cmp     [rdi], bp
0x180002a1c  jnz     loc_180002982
0x180002a22  xor     eax, eax
0x180002a24  jmp     short loc_180002A2B
0x180002a26  mov     eax, 80070057h
0x180002a2b  add     rsp, 28h
0x180002a2f  pop     rdi
0x180002a30  pop     rsi
0x180002a31  pop     rbp
0x180002a32  pop     rbx
0x180002a33  retn
```
