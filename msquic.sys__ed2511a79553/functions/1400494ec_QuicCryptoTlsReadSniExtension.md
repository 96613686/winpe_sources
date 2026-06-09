# QuicCryptoTlsReadSniExtension

- ea: `0x1400494ec`
- end: `0x14004961d`
- name: `QuicCryptoTlsReadSniExtension`
- size: `305`
- prototype: `__int64 __fastcall(__int64, unsigned __int8 *, unsigned __int16, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140020e98`

## callees

- `0x14003ec10`
- `0x1400494ec`

## string_xrefs

- `0x140049523`: `Parse error. ReadTlsSni #1`
- `0x140049557`: `Parse error. ReadTlsSni #2`
- `0x140049600`: `Parse error. ReadTlsSni #3`
- `0x1400495ee`: `Parse error. ReadTlsSni #4`

## pseudocode

```c
__int64 __fastcall QuicCryptoTlsReadSniExtension(__int64 a1, unsigned __int8 *a2, unsigned __int16 a3, __int64 a4)
{
  const char *v5; // r9
  unsigned __int8 *v6; // r10
  char v7; // r9
  __int16 v8; // r8
  unsigned __int8 v9; // di
  unsigned __int16 v10; // r8
  unsigned __int8 *v11; // r10
  __int16 v12; // dx
  unsigned __int16 v13; // r8
  __int16 v14; // ax
  unsigned __int8 *v15; // r10
  unsigned __int16 v16; // dx

  if ( a3 >= 2u )
  {
    if ( (unsigned __int16)(a2[1] + (*a2 << 8)) >= 3u )
    {
      v6 = a2 + 2;
      v7 = 0;
      v8 = a3 - 2;
      if ( !v8 )
        return 0;
      while ( 1 )
      {
        v9 = *v6;
        v10 = v8 - 1;
        v11 = v6 + 1;
        if ( v10 < 2u )
          break;
        v12 = *v11;
        v13 = v10 - 2;
        v14 = v11[1];
        v15 = v11 + 2;
        v16 = v14 + (v12 << 8);
        if ( v13 < v16 )
        {
          if ( (byte_14005C48B & 4) == 0 )
            return 3221225485LL;
          v5 = "Parse error. ReadTlsSni #4";
          goto LABEL_19;
        }
        if ( !v9 && !v7 )
        {
          *(_QWORD *)(a4 + 64) = v15;
          v7 = 1;
          *(_WORD *)(a4 + 30) = v16;
        }
        v6 = &v15[v16];
        v8 = v13 - v16;
        if ( !v8 )
          return 0;
      }
      if ( (byte_14005C48B & 4) == 0 )
        return 3221225485LL;
      v5 = "Parse error. ReadTlsSni #3";
      goto LABEL_19;
    }
    if ( (byte_14005C48B & 4) != 0 )
    {
      v5 = "Parse error. ReadTlsSni #2";
      goto LABEL_19;
    }
  }
  else if ( (byte_14005C48B & 4) != 0 )
  {
    v5 = "Parse error. ReadTlsSni #1";
LABEL_19:
    McTemplateU0ps_EtwWriteTransfer(a1, QuicConnError, a1, v5);
  }
  return 3221225485LL;
}

```

## disassembly

```asm
0x1400494ec  mov     rax, rsp
0x1400494ef  mov     [rax+8], rbx
0x1400494f3  mov     [rax+10h], rbp
0x1400494f7  mov     [rax+18h], rsi
0x1400494fb  mov     [rax+20h], rdi
0x1400494ff  push    r14
0x140049501  sub     rsp, 20h
0x140049505  mov     esi, 2
0x14004950a  mov     rbx, r9
0x14004950d  mov     r10, rdx
0x140049510  cmp     r8w, si
0x140049514  jnb     short loc_14004952F
0x140049516  test    cs:byte_14005C48B, 4
0x14004951d  jz      loc_140049616
0x140049523  lea     r9, aParseErrorRead_6; "Parse error. ReadTlsSni #1"
0x14004952a  jmp     loc_140049607
0x14004952f  movzx   edx, byte ptr [rdx]
0x140049532  mov     r14d, 100h
0x140049538  movzx   eax, byte ptr [r10+1]
0x14004953d  imul    edx, r14d
0x140049541  add     dx, ax
0x140049544  cmp     dx, 3
0x140049548  jnb     short loc_140049563
0x14004954a  test    cs:byte_14005C48B, 4
0x140049551  jz      loc_140049616
0x140049557  lea     r9, aParseErrorRead_2; "Parse error. ReadTlsSni #2"
0x14004955e  jmp     loc_140049607
0x140049563  mov     ebp, 0FFFEh
0x140049568  add     r10, rsi
0x14004956b  xor     r9b, r9b
0x14004956e  add     r8w, bp
0x140049572  jz      short loc_1400495C7
0x140049574  mov     dil, [r10]
0x140049577  mov     eax, 0FFFFh
0x14004957c  add     r8w, ax
0x140049580  inc     r10
0x140049583  cmp     r8w, si
0x140049587  jb      short loc_1400495F7
0x140049589  movzx   edx, byte ptr [r10]
0x14004958d  add     r8w, bp
0x140049591  movzx   eax, byte ptr [r10+1]
0x140049596  add     r10, rsi
0x140049599  imul    edx, r14d
0x14004959d  add     dx, ax
0x1400495a0  cmp     r8w, dx
0x1400495a4  jb      short loc_1400495E5
0x1400495a6  test    dil, dil
0x1400495a9  jnz     short loc_1400495BB
0x1400495ab  test    r9b, r9b
0x1400495ae  jnz     short loc_1400495BB
0x1400495b0  mov     [rbx+40h], r10
0x1400495b4  mov     r9b, 1
0x1400495b7  mov     [rbx+1Eh], dx
0x1400495bb  movzx   eax, dx
0x1400495be  add     r10, rax
0x1400495c1  sub     r8w, dx
0x1400495c5  jnz     short loc_140049574
0x1400495c7  xor     eax, eax
0x1400495c9  mov     rbx, [rsp+28h+arg_0]
0x1400495ce  mov     rbp, [rsp+28h+arg_8]
0x1400495d3  mov     rsi, [rsp+28h+arg_10]
0x1400495d8  mov     rdi, [rsp+28h+arg_18]
0x1400495dd  add     rsp, 20h
0x1400495e1  pop     r14
0x1400495e3  retn
0x1400495e5  test    cs:byte_14005C48B, 4
0x1400495ec  jz      short loc_140049616
0x1400495ee  lea     r9, aParseErrorRead_5; "Parse error. ReadTlsSni #4"
0x1400495f5  jmp     short loc_140049607
0x1400495f7  test    cs:byte_14005C48B, 4
0x1400495fe  jz      short loc_140049616
0x140049600  lea     r9, aParseErrorRead_11; "Parse error. ReadTlsSni #3"
0x140049607  mov     r8, rcx
0x14004960a  lea     rdx, QuicConnError
0x140049611  call    McTemplateU0ps_EtwWriteTransfer
0x140049616  mov     eax, 0C000000Dh
0x14004961b  jmp     short loc_1400495C9
```
