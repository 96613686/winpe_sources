# Scanner::ScanStringConstant(uint)

- ea: `0x18002a5d0`
- end: `0x18002a9ad`
- name: `?ScanStringConstant@Scanner@@AEAA?AW4tokens@@I@Z`
- size: `989`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001c430`

## callees

- `0x18002a5d0`
- `0x18002ad40`
- `0x18002c310`
- `0x18002c3e8`
- `0x18002cb34`
- `0x18003b3e0`
- `0x1800535e8`
- `0x180075b08`

## import_xrefs

- `msvcrt!free` at `0x18002a747`
- `msvcrt!free` at `0x18002a747`

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
    BigCharType = *((_BYTE *)&qword_1800A2400 + (unsigned __int16)a2);
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
0x18002a5d0  mov     [rsp+arg_0], rbx
0x18002a5d5  mov     [rsp+arg_10], rbp
0x18002a5da  push    rsi
0x18002a5db  push    rdi
0x18002a5dc  push    r14
0x18002a5de  sub     rsp, 20h
0x18002a5e2  xor     ebp, ebp
0x18002a5e4  mov     esi, edx
0x18002a5e6  mov     [rsp+38h+arg_8], ebp
0x18002a5ea  lea     r14, __ImageBase
0x18002a5f1  mov     [rcx+74h], ebp
0x18002a5f4  mov     rbx, rcx
0x18002a5f7  nop     word ptr [rax+rax+00000000h]
0x18002a600  mov     rdx, [rbx+28h]
0x18002a604  movzx   edi, word ptr [rdx]
0x18002a607  lea     rax, [rdx+2]
0x18002a60b  mov     [rbx+28h], rax
0x18002a60f  cmp     edi, esi
0x18002a611  jz      short loc_18002A653
0x18002a613  test    edi, edi
0x18002a615  jz      loc_18002A8C9
0x18002a61b  cmp     edi, 0Ah
0x18002a61e  jz      loc_18002A8C9
0x18002a624  cmp     edi, 0Dh
0x18002a627  jz      loc_18002A8C9
0x18002a62d  cmp     edi, 5Ch ; '\'
0x18002a630  jz      loc_18002A6E6
0x18002a636  mov     eax, [rbx+70h]; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a639  cmp     [rbx+74h], eax
0x18002a63c  jge     loc_18002A6D9
0x18002a642  movsxd  rcx, dword ptr [rbx+74h]
0x18002a646  mov     rax, [rbx+78h]
0x18002a64a  mov     [rax+rcx*2], di
0x18002a64e  inc     dword ptr [rbx+74h]
0x18002a651  jmp     short loc_18002A600
0x18002a653  test    byte ptr [rbx+60h], 10h
0x18002a657  jnz     loc_18002A8FA
0x18002a65d  mov     r8d, [rbx+74h]; int
0x18002a661  mov     r9d, 1; int
0x18002a667  mov     rdx, [rbx+78h]; unsigned __int16 *
0x18002a66b  mov     rcx, [rbx]; this
0x18002a66e  call    ?PidHashNameLen@HashTbl@@QEAAPEAUIdent@@PEBGJH@Z; HashTbl::PidHashNameLen(ushort const *,long,int)
0x18002a673  mov     rcx, [rbx+8]
0x18002a677  mov     [rcx+8], rax
0x18002a67b  mov     rcx, [rbx+48h]; Block
0x18002a67f  test    rcx, rcx
0x18002a682  jnz     loc_18002A747
0x18002a688  mov     eax, 80h
0x18002a68d  cmp     si, ax
0x18002a690  jnb     loc_18002A737
0x18002a696  movzx   eax, si
0x18002a699  movzx   ecx, byte ptr [rax+r14+0A2400h]
0x18002a6a2  and     dword ptr [rbx+60h], 0FFFFFFFDh
0x18002a6a6  mov     eax, ebp
0x18002a6a8  cmp     cl, 0Ch
0x18002a6ab  mov     edx, 2
0x18002a6b0  mov     rcx, [rbx+8]
0x18002a6b4  cmovz   eax, edx
0x18002a6b7  or      [rbx+60h], eax
0x18002a6ba  mov     eax, 82h
0x18002a6bf  mov     dword ptr [rcx], 82h
0x18002a6c5  mov     rbx, [rsp+38h+arg_0]
0x18002a6ca  mov     rbp, [rsp+38h+arg_10]
0x18002a6cf  add     rsp, 20h
0x18002a6d3  pop     r14
0x18002a6d5  pop     rdi
0x18002a6d6  pop     rsi
0x18002a6d7  retn
0x18002a6d9  mov     rcx, rbx; this
0x18002a6dc  call    ?GrowBuf@Scanner@@AEAAXXZ; Scanner::GrowBuf(void)
0x18002a6e1  jmp     loc_18002A642
0x18002a6e6  movzx   edi, word ptr [rax]
0x18002a6e9  lea     r8, [rdx+4]
0x18002a6ed  mov     [rbx+28h], r8
0x18002a6f1  cmp     edi, 62h ; 'b'
0x18002a6f4  jnz     short loc_18002A700
0x18002a6f6  mov     edi, 8
0x18002a6fb  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a700  cmp     edi, 78h; switch 121 cases
0x18002a703  ja      def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a709  movzx   eax, ds:(byte_18002A934 - 180000000h)[r14+rdi]
0x18002a712  mov     ecx, ds:(jpt_18002A71D - 180000000h)[r14+rax*4]
0x18002a71a  add     rcx, r14
0x18002a71d  jmp     rcx; switch jump
0x18002a723  mov     edi, 0Ah; jumptable 000000018002A71D case 110
0x18002a728  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a72d  mov     edi, 0Dh; jumptable 000000018002A71D case 114
0x18002a732  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a737  movzx   ecx, si; unsigned __int16
0x18002a73a  call    ?GetBigCharType@@YAEG@Z; GetBigCharType(ushort)
0x18002a73f  movzx   ecx, al
0x18002a742  jmp     loc_18002A6A2
0x18002a747  call    cs:__imp_free
0x18002a74e  nop     dword ptr [rax+rax+00h]
0x18002a753  mov     [rbx+48h], rbp
0x18002a757  jmp     loc_18002A688
0x18002a75c  mov     edi, 9; jumptable 000000018002A71D case 116
0x18002a761  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a766  mov     edi, 0Ch; jumptable 000000018002A71D case 102
0x18002a76b  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a770  mov     edi, ebp; jumptable 000000018002A71D case 120
0x18002a772  jmp     short loc_18002A7C3
0x18002a774  movzx   ecx, word ptr [r8]; jumptable 000000018002A71D case 117
0x18002a778  lea     r8, [rdx+6]
0x18002a77c  lea     rdx, [rsp+38h+arg_8]; int *
0x18002a781  mov     [rbx+28h], r8
0x18002a785  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002a78a  test    eax, eax
0x18002a78c  jz      loc_18002A88A
0x18002a792  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002a796  lea     rdx, [rsp+38h+arg_8]; int *
0x18002a79b  mov     r9d, [rsp+38h+arg_8]
0x18002a7a0  add     r8, 2
0x18002a7a4  mov     [rbx+28h], r8
0x18002a7a8  shl     r9d, 0Ch
0x18002a7ac  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002a7b1  test    eax, eax
0x18002a7b3  jz      loc_18002A88A
0x18002a7b9  mov     edi, [rsp+38h+arg_8]
0x18002a7bd  shl     edi, 8
0x18002a7c0  add     edi, r9d
0x18002a7c3  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002a7c7  lea     rdx, [rsp+38h+arg_8]; int *
0x18002a7cc  add     r8, 2
0x18002a7d0  mov     [rbx+28h], r8
0x18002a7d4  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002a7d9  test    eax, eax
0x18002a7db  jz      loc_18002A88A
0x18002a7e1  movzx   ecx, word ptr [r8]; unsigned __int16
0x18002a7e5  lea     rdx, [rsp+38h+arg_8]; int *
0x18002a7ea  mov     r9d, [rsp+38h+arg_8]
0x18002a7ef  add     r8, 2
0x18002a7f3  mov     [rbx+28h], r8
0x18002a7f7  shl     r9d, 4
0x18002a7fb  call    ?FHexDigit@@YAHGPEAH@Z; FHexDigit(ushort,int *)
0x18002a800  test    eax, eax
0x18002a802  jz      loc_18002A88A
0x18002a808  mov     ecx, [rsp+38h+arg_8]
0x18002a80c  add     ecx, r9d
0x18002a80f  add     edi, ecx
0x18002a811  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a816  movzx   ecx, word ptr [r8]; jumptable 000000018002A71D cases 48-51
0x18002a81a  add     rdx, 6
0x18002a81e  add     edi, 0FFFFFFD0h
0x18002a821  mov     [rbx+28h], rdx
0x18002a825  lea     eax, [rcx-30h]
0x18002a828  mov     [rsp+38h+arg_8], eax
0x18002a82c  lea     eax, [rcx-30h]
0x18002a82f  cmp     ax, 7
0x18002a833  jbe     short loc_18002A83E
0x18002a835  mov     [rbx+28h], r8
0x18002a839  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a83e  add     edi, 0FFFFFFFAh
0x18002a841  lea     edi, [rcx+rdi*8]
0x18002a844  jmp     short loc_18002A84C
0x18002a846  add     edi, 0FFFFFFD0h; jumptable 000000018002A71D cases 52-55
0x18002a849  mov     rdx, r8
0x18002a84c  movzx   ecx, word ptr [rdx]
0x18002a84f  lea     rax, [rdx+2]
0x18002a853  mov     [rbx+28h], rax
0x18002a857  lea     eax, [rcx-30h]
0x18002a85a  mov     [rsp+38h+arg_8], eax
0x18002a85e  lea     eax, [rcx-30h]
0x18002a861  cmp     ax, 7
0x18002a865  jbe     short loc_18002A870
0x18002a867  mov     [rbx+28h], rdx
0x18002a86b  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a870  add     edi, 0FFFFFFFAh
0x18002a873  lea     edi, [rcx+rdi*8]
0x18002a876  jmp     def_18002A71D; jumptable 000000018002A71D default case, cases 1-9,11,12,14-47,56-101,103-109,111-113,115,118,119
0x18002a87b  mov     edx, edi; jumptable 000000018002A71D cases 10,13
0x18002a87d  mov     rcx, rbx; this
0x18002a880  call    ?ScanNewLine@Scanner@@AEAAXI@Z; Scanner::ScanNewLine(uint)
0x18002a885  jmp     loc_18002A600
0x18002a88a  test    byte ptr [rbx+60h], 10h
0x18002a88e  lea     rax, [r8-2]
0x18002a892  mov     [rbx+28h], rax
0x18002a896  mov     rcx, rbx; this
0x18002a899  jz      short loc_18002A8B4
0x18002a89b  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18002a8a0  mov     rcx, [rbx+8]
0x18002a8a4  mov     eax, 7Eh ; '~'
0x18002a8a9  mov     dword ptr [rcx], 7Eh ; '~'
0x18002a8af  jmp     loc_18002A6C5
0x18002a8b4  mov     edx, 3FFh; int
0x18002a8b9  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
0x18002a8bf  lea     rax, [r8-2]; jumptable 000000018002A71D case 0
0x18002a8c3  mov     [rbx+28h], rax
0x18002a8c7  jmp     short loc_18002A8CD
0x18002a8c9  mov     [rbx+28h], rdx
0x18002a8cd  test    byte ptr [rbx+60h], 10h
0x18002a8d1  mov     rcx, rbx; this
0x18002a8d4  jz      short loc_18002A8EF
0x18002a8d6  call    ?FreeTemp@Scanner@@AEAAXXZ; Scanner::FreeTemp(void)
0x18002a8db  mov     rax, [rbx+8]
0x18002a8df  mov     dword ptr [rax], 7Eh ; '~'
0x18002a8e5  mov     eax, 7Eh ; '~'
0x18002a8ea  jmp     loc_18002A6C5
0x18002a8ef  mov     edx, 3F7h; int
0x18002a8f4  call    ?Error@Scanner@@AEAAXH@Z; Scanner::Error(int)
0x18002a8fa  mov     rax, [rbx+8]
0x18002a8fe  mov     [rax+8], rbp
0x18002a902  jmp     loc_18002A67B
```
