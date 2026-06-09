# Scanner::ScanStringConstant(uint)

- ea: `0x18002d340`
- end: `0x18002d711`
- name: `?ScanStringConstant@Scanner@@AEAA?AW4tokens@@I@Z`
- size: `977`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001f400`

## callees

- `0x18002d340`
- `0x18002daa0`
- `0x18002f050`
- `0x18002f114`
- `0x18003a160`
- `0x18003e1d0`
- `0x180052840`
- `0x180074600`

## import_xrefs

- `msvcrt!free` at `0x18002d4b2`
- `msvcrt!free` at `0x18002d4b2`

## pseudocode

```c
__int64 __fastcall Scanner::ScanStringConstant(__int64 a1, int a2)
{
  unsigned __int16 *v4; // rdx
  unsigned int v5; // edi
  void *v6; // rcx
  unsigned __int8 BigCharType; // cl
  int v8; // eax
  bool v9; // zf
  _DWORD *v10; // rcx
  __int64 result; // rax
  unsigned __int16 *v12; // r8
  __int16 v13; // di
  unsigned __int16 v14; // cx
  unsigned __int16 v15; // cx
  __int16 v16; // r9
  unsigned __int16 v17; // cx
  unsigned __int16 v18; // cx
  __int16 v19; // r9
  int v20; // ecx
  unsigned __int16 *v21; // rdx
  int v22; // ecx
  int v23; // [rsp+48h] [rbp+10h] BYREF

  v23 = 0;
  *(_DWORD *)(a1 + 116) = 0;
  while ( 1 )
  {
    v4 = *(unsigned __int16 **)(a1 + 40);
    v5 = *v4;
    *(_QWORD *)(a1 + 40) = v4 + 1;
    if ( v5 == a2 )
      break;
    if ( !v5 || v5 == 10 || v5 == 13 )
    {
      *(_QWORD *)(a1 + 40) = v4;
LABEL_47:
      if ( (*(_BYTE *)(a1 + 96) & 0x10) == 0 )
        Scanner::Error((Scanner *)a1, 1015);
      Scanner::FreeTemp((Scanner *)a1);
      **(_DWORD **)(a1 + 8) = 126;
      return 126;
    }
    if ( v5 == 92 )
    {
      v5 = v4[1];
      v12 = v4 + 2;
      *(_QWORD *)(a1 + 40) = v4 + 2;
      if ( v5 == 98 )
      {
        LOWORD(v5) = 8;
      }
      else
      {
        switch ( v5 )
        {
          case 0u:
            *(_QWORD *)(a1 + 40) = v4 + 1;
            goto LABEL_47;
          case 0xAu:
          case 0xDu:
            Scanner::ScanNewLine((Scanner *)a1, v5);
            continue;
          case 0x30u:
          case 0x31u:
          case 0x32u:
          case 0x33u:
            v20 = *v12;
            v21 = v4 + 3;
            LOWORD(v5) = v5 - 48;
            *(_QWORD *)(a1 + 40) = v21;
            v23 = v20 - 48;
            if ( (unsigned __int16)(v20 - 48) <= 7u )
            {
              LOWORD(v5) = v20 + 8 * (v5 - 6);
LABEL_38:
              v22 = *v21;
              *(_QWORD *)(a1 + 40) = v21 + 1;
              v23 = v22 - 48;
              if ( (unsigned __int16)(v22 - 48) <= 7u )
                LOWORD(v5) = v22 + 8 * (v5 - 6);
              else
                *(_QWORD *)(a1 + 40) = v21;
            }
            else
            {
              *(_QWORD *)(a1 + 40) = v12;
            }
            break;
          case 0x34u:
          case 0x35u:
          case 0x36u:
          case 0x37u:
            LOWORD(v5) = v5 - 48;
            v21 = v4 + 2;
            goto LABEL_38;
          case 0x66u:
            LOWORD(v5) = 12;
            break;
          case 0x6Eu:
            LOWORD(v5) = 10;
            break;
          case 0x72u:
            LOWORD(v5) = 13;
            break;
          case 0x74u:
            LOWORD(v5) = 9;
            break;
          case 0x75u:
            v14 = *v12;
            *(_QWORD *)(a1 + 40) = v4 + 3;
            if ( !(unsigned int)FHexDigit(v14, &v23) )
              goto LABEL_42;
            v15 = *v12;
            *(_QWORD *)(a1 + 40) = v12 + 1;
            if ( !(unsigned int)FHexDigit(v15, &v23) )
              goto LABEL_42;
            v13 = v16 + ((_WORD)v23 << 8);
LABEL_31:
            v17 = *v12;
            *(_QWORD *)(a1 + 40) = v12 + 1;
            if ( !(unsigned int)FHexDigit(v17, &v23)
              || (v18 = *v12, *(_QWORD *)(a1 + 40) = v12 + 1, !(unsigned int)FHexDigit(v18, &v23)) )
            {
LABEL_42:
              v9 = (*(_BYTE *)(a1 + 96) & 0x10) == 0;
              *(_QWORD *)(a1 + 40) = v12 - 1;
              if ( v9 )
                Scanner::Error((Scanner *)a1, 1023);
              Scanner::FreeTemp((Scanner *)a1);
              result = 126;
              **(_DWORD **)(a1 + 8) = 126;
              return result;
            }
            LOWORD(v5) = v19 + v23 + v13;
            break;
          case 0x78u:
            v13 = 0;
            goto LABEL_31;
          default:
            break;
        }
      }
    }
    if ( *(_DWORD *)(a1 + 116) >= *(_DWORD *)(a1 + 112) )
      Scanner::GrowBuf((Scanner *)a1);
    *(_WORD *)(*(_QWORD *)(a1 + 120) + 2LL * (int)(*(_DWORD *)(a1 + 116))++) = v5;
  }
  if ( (*(_BYTE *)(a1 + 96) & 0x10) != 0 )
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = 0;
  else
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = HashTbl::PidHashNameLen(
                                               *(HashTbl **)a1,
                                               *(const unsigned __int16 **)(a1 + 120),
                                               *(_DWORD *)(a1 + 116),
                                               1);
  v6 = *(void **)(a1 + 72);
  if ( v6 )
  {
    free(v6);
    *(_QWORD *)(a1 + 72) = 0;
  }
  if ( (unsigned __int16)a2 >= 0x80u )
    BigCharType = GetBigCharType(a2);
  else
    BigCharType = *((_BYTE *)&qword_1800A0550 + (unsigned __int16)a2);
  *(_DWORD *)(a1 + 96) &= ~2u;
  v8 = 0;
  v9 = BigCharType == 12;
  v10 = *(_DWORD **)(a1 + 8);
  if ( v9 )
    v8 = 2;
  *(_DWORD *)(a1 + 96) |= v8;
  result = 130;
  *v10 = 130;
  return result;
}

```

## disassembly

```asm
0x18002d340  mov     [rsp+arg_0], rbx
0x18002d345  mov     [rsp+arg_10], rbp
0x18002d34a  push    rsi
0x18002d34b  push    rdi
0x18002d34c  push    r14
0x18002d34e  sub     rsp, 20h
0x18002d352  xor     ebp, ebp
0x18002d354  mov     esi, edx
0x18002d356  mov     [rsp+38h+arg_8], ebp
0x18002d35a  lea     r14, __ImageBase
0x18002d361  mov     [rcx+74h], ebp
0x18002d364  mov     rbx, rcx
0x18002d367  nop     word ptr [rax+rax+00000000h]
0x18002d370  mov     rdx, [rbx+28h]
0x18002d374  movzx   edi, word ptr [rdx]
0x18002d377  lea     rax, [rdx+2]
0x18002d37b  mov     [rbx+28h], rax
0x18002d37f  cmp     edi, esi
0x18002d381  jz      short loc_18002D3C3
0x18002d383  test    edi, edi
0x18002d385  jz      loc_18002D62E
0x18002d38b  cmp     edi, 0Ah
0x18002d38e  jz      loc_18002D62E
0x18002d394  cmp     edi, 0Dh
0x18002d397  jz      loc_18002D62E
0x18002d39d  cmp     edi, 5Ch ; '\'
0x18002d3a0  jz      loc_18002D455
0x18002d3a6  mov     eax, [rbx+70h]; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d3a9  cmp     [rbx+74h], eax
0x18002d3ac  jge     loc_18002D448
0x18002d3b2  movsxd  rcx, dword ptr [rbx+74h]
0x18002d3b6  mov     rax, [rbx+78h]
0x18002d3ba  mov     [rax+rcx*2], di
0x18002d3be  inc     dword ptr [rbx+74h]
0x18002d3c1  jmp     short loc_18002D370
0x18002d3c3  test    byte ptr [rbx+60h], 10h
0x18002d3c7  jnz     loc_18002D65F
0x18002d3cd  mov     r8d, [rbx+74h]; int
0x18002d3d1  mov     r9d, 1; int
0x18002d3d7  mov     rdx, [rbx+78h]; unsigned __int16 *
0x18002d3db  mov     rcx, [rbx]; this
0x18002d3de  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18002d3e3  mov     rcx, [rbx+8]
0x18002d3e7  mov     [rcx+8], rax
0x18002d3eb  mov     rcx, [rbx+48h]; Block
0x18002d3ef  test    rcx, rcx
0x18002d3f2  jnz     loc_18002D4B2
0x18002d3f8  mov     eax, 80h
0x18002d3fd  cmp     si, ax
0x18002d400  jnb     loc_18002D4A2
0x18002d406  movzx   eax, si
0x18002d409  movzx   ecx, byte ptr [rax+r14+0A0550h]
0x18002d412  and     dword ptr [rbx+60h], 0FFFFFFFDh
0x18002d416  mov     eax, ebp
0x18002d418  cmp     cl, 0Ch
0x18002d41b  mov     edx, 2
0x18002d420  mov     rcx, [rbx+8]
0x18002d424  cmovz   eax, edx
0x18002d427  or      [rbx+60h], eax
0x18002d42a  mov     eax, 82h
0x18002d42f  mov     dword ptr [rcx], 82h
0x18002d435  mov     rbx, [rsp+38h+arg_0]
0x18002d43a  mov     rbp, [rsp+38h+arg_10]
0x18002d43f  add     rsp, 20h
0x18002d443  pop     r14
0x18002d445  pop     rdi
0x18002d446  pop     rsi
0x18002d447  retn
0x18002d448  mov     rcx, rbx; this
0x18002d44b  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18002d450  jmp     loc_18002D3B2
0x18002d455  movzx   edi, word ptr [rax]
0x18002d458  lea     r8, [rdx+4]
0x18002d45c  mov     [rbx+28h], r8
0x18002d460  cmp     edi, 62h ; 'b'
0x18002d463  jnz     short loc_18002D46F
0x18002d465  mov     edi, 8
0x18002d46a  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d46f  cmp     edi, 78h; switch 121 cases
0x18002d472  ja      def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d478  movzx   eax, ds:(byte_18002D698 - 180000000h)[r14+rdi]
0x18002d481  mov     ecx, ds:(jpt_18002D48C - 180000000h)[r14+rax*4]
0x18002d489  add     rcx, r14
0x18002d48c  jmp     rcx; switch jump
0x18002d48e  mov     edi, 0Ah; jumptable 000000018002D48C case 110
0x18002d493  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d498  mov     edi, 0Dh; jumptable 000000018002D48C case 114
0x18002d49d  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d4a2  movzx   ecx, si; unsigned __int16
0x18002d4a5  call    ?GetBigCharType@@YAEG@Z; GetBigCharType(ushort)
0x18002d4aa  movzx   ecx, al
0x18002d4ad  jmp     loc_18002D412
0x18002d4b2  call    cs:__imp_free
0x18002d4b8  mov     [rbx+48h], rbp
0x18002d4bc  jmp     loc_18002D3F8
0x18002d4c1  mov     edi, 9; jumptable 000000018002D48C case 116
0x18002d4c6  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d4cb  mov     edi, 0Ch; jumptable 000000018002D48C case 102
0x18002d4d0  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d4d5  mov     edi, ebp; jumptable 000000018002D48C case 120
0x18002d4d7  jmp     short loc_18002D528
0x18002d4d9  movzx   ecx, word ptr [r8]; jumptable 000000018002D48C case 117
0x18002d4dd  lea     r8, [rdx+6]
0x18002d4e1  lea     rdx, [rsp+38h+arg_8]; int *
0x18002d4e6  mov     [rbx+28h], r8
0x18002d4ea  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002d4ef  test    eax, eax
0x18002d4f1  jz      loc_18002D5EF
0x18002d4f7  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002d4fb  lea     rdx, [rsp+38h+arg_8]; int *
0x18002d500  mov     r9d, [rsp+38h+arg_8]
0x18002d505  add     r8, 2
0x18002d509  mov     [rbx+28h], r8
0x18002d50d  shl     r9d, 0Ch
0x18002d511  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002d516  test    eax, eax
0x18002d518  jz      loc_18002D5EF
0x18002d51e  mov     edi, [rsp+38h+arg_8]
0x18002d522  shl     edi, 8
0x18002d525  add     edi, r9d
0x18002d528  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002d52c  lea     rdx, [rsp+38h+arg_8]; int *
0x18002d531  add     r8, 2
0x18002d535  mov     [rbx+28h], r8
0x18002d539  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002d53e  test    eax, eax
0x18002d540  jz      loc_18002D5EF
0x18002d546  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002d54a  lea     rdx, [rsp+38h+arg_8]; int *
0x18002d54f  mov     r9d, [rsp+38h+arg_8]
0x18002d554  add     r8, 2
0x18002d558  mov     [rbx+28h], r8
0x18002d55c  shl     r9d, 4
0x18002d560  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002d565  test    eax, eax
0x18002d567  jz      loc_18002D5EF
0x18002d56d  mov     ecx, [rsp+38h+arg_8]
0x18002d571  add     ecx, r9d
0x18002d574  add     edi, ecx
0x18002d576  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d57b  movzx   ecx, word ptr [r8]; jumptable 000000018002D48C cases 48-51
0x18002d57f  add     rdx, 6
0x18002d583  add     edi, 0FFFFFFD0h
0x18002d586  mov     [rbx+28h], rdx
0x18002d58a  lea     eax, [rcx-30h]
0x18002d58d  mov     [rsp+38h+arg_8], eax
0x18002d591  lea     eax, [rcx-30h]
0x18002d594  cmp     ax, 7
0x18002d598  jbe     short loc_18002D5A3
0x18002d59a  mov     [rbx+28h], r8
0x18002d59e  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d5a3  add     edi, 0FFFFFFFAh
0x18002d5a6  lea     edi, [rcx+rdi*8]
0x18002d5a9  jmp     short loc_18002D5B1
0x18002d5ab  add     edi, 0FFFFFFD0h; jumptable 000000018002D48C cases 52-55
0x18002d5ae  mov     rdx, r8
0x18002d5b1  movzx   ecx, word ptr [rdx]
0x18002d5b4  lea     rax, [rdx+2]
0x18002d5b8  mov     [rbx+28h], rax
0x18002d5bc  lea     eax, [rcx-30h]
0x18002d5bf  mov     [rsp+38h+arg_8], eax
0x18002d5c3  lea     eax, [rcx-30h]
0x18002d5c6  cmp     ax, 7
0x18002d5ca  jbe     short loc_18002D5D5
0x18002d5cc  mov     [rbx+28h], rdx
0x18002d5d0  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d5d5  add     edi, 0FFFFFFFAh
0x18002d5d8  lea     edi, [rcx+rdi*8]
0x18002d5db  jmp     def_18002D48C; jumptable 000000018002D48C default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002d5e0  mov     edx, edi; jumptable 000000018002D48C cases 10,13
0x18002d5e2  mov     rcx, rbx; this
0x18002d5e5  call    ?ScanNewLine@Scanner@@AEAAXI@Z; Scanner::ScanNewLine(uint)
0x18002d5ea  jmp     loc_18002D370
0x18002d5ef  test    byte ptr [rbx+60h], 10h
0x18002d5f3  lea     rax, [r8-2]
0x18002d5f7  mov     [rbx+28h], rax
0x18002d5fb  mov     rcx, rbx; this
0x18002d5fe  jz      short loc_18002D619
0x18002d600  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18002d605  mov     rcx, [rbx+8]
0x18002d609  mov     eax, 7Eh ; '~'
0x18002d60e  mov     dword ptr [rcx], 7Eh ; '~'
0x18002d614  jmp     loc_18002D435
0x18002d619  mov     edx, 3FFh; int
0x18002d61e  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
0x18002d624  lea     rax, [r8-2]; jumptable 000000018002D48C case 0
0x18002d628  mov     [rbx+28h], rax
0x18002d62c  jmp     short loc_18002D632
0x18002d62e  mov     [rbx+28h], rdx
0x18002d632  test    byte ptr [rbx+60h], 10h
0x18002d636  mov     rcx, rbx; this
0x18002d639  jz      short loc_18002D654
0x18002d63b  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18002d640  mov     rax, [rbx+8]
0x18002d644  mov     dword ptr [rax], 7Eh ; '~'
0x18002d64a  mov     eax, 7Eh ; '~'
0x18002d64f  jmp     loc_18002D435
0x18002d654  mov     edx, 3F7h; int
0x18002d659  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
0x18002d65f  mov     rax, [rbx+8]
0x18002d663  mov     [rax+8], rbp
0x18002d667  jmp     loc_18002D3EB
```
