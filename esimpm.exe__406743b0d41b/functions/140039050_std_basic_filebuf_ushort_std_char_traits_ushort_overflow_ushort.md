# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x140039050`
- end: `0x1400391e6`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140002f60`
- `0x140039050`

## import_xrefs

- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x14003916a`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x14003916a`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x14003911f`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x14003911f`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1400391a4`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x1400391a4`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // si
  unsigned __int16 v3; // di
  unsigned __int64 v6; // r8
  int *v7; // rax
  __int64 v8; // r9
  _WORD **v9; // rdx
  unsigned __int16 *v10; // r8
  _QWORD *v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // r14
  unsigned __int16 v19; // [rsp+40h] [rbp-40h] BYREF
  char v20[6]; // [rsp+42h] [rbp-3Eh] BYREF
  _BYTE *v21; // [rsp+48h] [rbp-38h] BYREF
  unsigned __int16 *v22; // [rsp+50h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-28h] BYREF
  __int64 v24; // [rsp+78h] [rbp-8h] BYREF

  v2 = -1;
  v3 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  v6 = **(_QWORD **)(a1 + 64);
  if ( v6 )
  {
    v7 = *(int **)(a1 + 88);
    v8 = *v7;
    if ( v6 < v6 + 2 * v8 )
    {
      *v7 = v8 - 1;
      v9 = *(_WORD ***)(a1 + 64);
      v10 = (*v9)++;
      *v10 = v3;
      return v3;
    }
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 144);
      v13 = *(_QWORD *)(a1 + 136);
      *v11 = v13;
      **(_QWORD **)(a1 + 56) = v13;
      **(_DWORD **)(a1 + 80) = (v12 - v13) >> 1;
    }
    v14 = *(_QWORD *)(a1 + 104);
    if ( !v14 )
    {
      v15 = v3;
      goto LABEL_12;
    }
    v19 = v3;
    v22 = 0;
    v21 = 0;
    v16 = std::codecvt<unsigned short,char,_Mbstatet>::out(v14, a1 + 116, &v19, v20, &v22, v23, &v24, &v21);
    if ( v16 && (v17 = v16 - 1) != 0 )
    {
      if ( v17 == 2 )
      {
        v15 = v19;
LABEL_12:
        if ( (unsigned __int16)_o_fputwc(v15, *(_QWORD *)(a1 + 128)) == 0xFFFF )
          return (unsigned __int16)-1;
        return v3;
      }
    }
    else if ( v21 == v23 || (v18 = v21 - v23, v18 == _o_fwrite(v23, 1, v21 - v23, *(_QWORD *)(a1 + 128))) )
    {
      *(_BYTE *)(a1 + 114) = 1;
      if ( v22 != &v19 )
        return v3;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140039050  mov     [rsp-18h+arg_10], rbx
0x140039055  mov     [rsp-18h+arg_18], rsi
0x14003905a  push    rbp
0x14003905b  push    rdi
0x14003905c  push    r14
0x14003905e  mov     rbp, rsp
0x140039061  sub     rsp, 80h
0x140039068  mov     rax, cs:__security_cookie
0x14003906f  xor     rax, rsp
0x140039072  mov     [rbp+var_8], rax
0x140039076  mov     esi, 0FFFFh
0x14003907b  xor     r14d, r14d
0x14003907e  movzx   edi, dx
0x140039081  mov     rbx, rcx
0x140039084  cmp     si, dx
0x140039087  jnz     short loc_140039092
0x140039089  movzx   eax, r14w
0x14003908d  jmp     loc_1400391C2
0x140039092  mov     rax, [rcx+40h]
0x140039096  mov     r8, [rax]
0x140039099  test    r8, r8
0x14003909c  jz      short loc_1400390CE
0x14003909e  mov     rax, [rcx+58h]
0x1400390a2  movsxd  r9, dword ptr [rax]
0x1400390a5  lea     rdx, [r8+r9*2]
0x1400390a9  cmp     r8, rdx
0x1400390ac  jnb     short loc_1400390CE
0x1400390ae  lea     ecx, [r9-1]
0x1400390b2  mov     [rax], ecx
0x1400390b4  mov     rdx, [rbx+40h]
0x1400390b8  mov     r8, [rdx]
0x1400390bb  lea     rcx, [r8+2]
0x1400390bf  mov     [rdx], rcx
0x1400390c2  mov     [r8], di
0x1400390c6  movzx   eax, di
0x1400390c9  jmp     loc_1400391C2
0x1400390ce  cmp     [rcx+80h], r14
0x1400390d5  jz      loc_1400391BF
0x1400390db  mov     r8, [rcx+18h]
0x1400390df  lea     rax, [rcx+70h]
0x1400390e3  cmp     [r8], rax
0x1400390e6  jnz     short loc_14003910C
0x1400390e8  mov     rdx, [rcx+90h]
0x1400390ef  mov     rcx, [rcx+88h]
0x1400390f6  mov     [r8], rcx
0x1400390f9  sub     rdx, rcx
0x1400390fc  mov     rax, [rbx+38h]
0x140039100  sar     rdx, 1
0x140039103  mov     [rax], rcx
0x140039106  mov     rax, [rbx+50h]
0x14003910a  mov     [rax], edx
0x14003910c  mov     rcx, [rbx+68h]
0x140039110  test    rcx, rcx
0x140039113  jnz     short loc_14003912E
0x140039115  movzx   ecx, di
0x140039118  mov     rdx, [rbx+80h]
0x14003911f  call    cs:__imp__o_fputwc
0x140039125  cmp     ax, si
0x140039128  cmovz   di, si
0x14003912c  jmp     short loc_1400390C6
0x14003912e  lea     rax, [rbp+var_38]
0x140039132  mov     [rbp+var_40], di
0x140039136  mov     [rsp+80h+var_48], rax
0x14003913b  lea     rdx, [rbx+74h]
0x14003913f  lea     rax, [rbp+var_8]
0x140039143  mov     [rbp+var_30], r14
0x140039147  mov     [rsp+80h+var_50], rax
0x14003914c  lea     r9, [rbp+var_3E]
0x140039150  lea     rax, [rbp+var_28]
0x140039154  mov     [rbp+var_38], r14
0x140039158  mov     [rsp+80h+var_58], rax
0x14003915d  lea     r8, [rbp+var_40]
0x140039161  lea     rax, [rbp+var_30]
0x140039165  mov     [rsp+80h+var_60], rax
0x14003916a  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x140039170  test    eax, eax
0x140039172  jz      short loc_140039184
0x140039174  sub     eax, 1
0x140039177  jz      short loc_140039184
0x140039179  cmp     eax, 2
0x14003917c  jnz     short loc_1400391BF
0x14003917e  movzx   ecx, [rbp+var_40]
0x140039182  jmp     short loc_140039118
0x140039184  mov     r14, [rbp+var_38]
0x140039188  lea     rax, [rbp+var_28]
0x14003918c  sub     r14, rax
0x14003918f  jz      short loc_1400391AF
0x140039191  mov     r9, [rbx+80h]
0x140039198  lea     rcx, [rbp+var_28]
0x14003919c  mov     r8, r14
0x14003919f  mov     edx, 1
0x1400391a4  call    cs:__imp__o_fwrite
0x1400391aa  cmp     r14, rax
0x1400391ad  jnz     short loc_1400391BF
0x1400391af  lea     rax, [rbp+var_40]
0x1400391b3  mov     byte ptr [rbx+72h], 1
0x1400391b7  cmp     [rbp+var_30], rax
0x1400391bb  cmovnz  si, di
0x1400391bf  movzx   eax, si
0x1400391c2  mov     rcx, [rbp+var_8]
0x1400391c6  xor     rcx, rsp; StackCookie
0x1400391c9  call    __security_check_cookie
0x1400391ce  lea     r11, [rsp+80h+var_s0]
0x1400391d6  mov     rbx, [r11+30h]
0x1400391da  mov     rsi, [r11+38h]
0x1400391de  mov     rsp, r11
0x1400391e1  pop     r14
0x1400391e3  pop     rdi
0x1400391e4  pop     rbp
0x1400391e5  retn
```
