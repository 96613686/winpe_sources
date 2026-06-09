# std::basic_filebuf<ushort,std::char_traits<ushort>>::overflow(ushort)

- ea: `0x1800271b0`
- end: `0x180027365`
- name: `?overflow@?$basic_filebuf@GU?$char_traits@G@std@@@std@@MEAAGG@Z`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800271b0`
- `0x18004ca90`

## import_xrefs

- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18002726d`
- `msvcp_win!?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z` at `0x18002726d`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x180027303`
- `msvcp_win!?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ` at `0x180027303`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800272e5`
- `msvcp_win!?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800272e5`
- `msvcp_win!?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z` at `0x180027322`
- `msvcp_win!?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z` at `0x180027322`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800271e6`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800272f1`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800271e6`
- `msvcp_win!?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x1800272f1`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x180027206`
- `msvcp_win!?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ` at `0x180027206`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x180027350`
- `api-ms-win-crt-private-l1-1-0!_o_fputwc` at `0x180027350`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18002729e`
- `api-ms-win-crt-private-l1-1-0!_o_fwrite` at `0x18002729e`

## pseudocode

```c
__int64 __fastcall std::basic_filebuf<unsigned short>::overflow(__int64 a1, unsigned __int16 a2)
{
  unsigned __int16 v2; // si
  unsigned __int16 v3; // bp
  __int64 v5; // rcx
  int v6; // eax
  __int64 v7; // rdi
  unsigned __int64 v9; // rdi
  __int64 v10; // rcx
  int v11; // eax
  unsigned __int16 v12; // [rsp+40h] [rbp-58h] BYREF
  char v13[6]; // [rsp+42h] [rbp-56h] BYREF
  _BYTE *v14; // [rsp+48h] [rbp-50h] BYREF
  unsigned __int16 *v15; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v16[32]; // [rsp+58h] [rbp-40h] BYREF
  __int64 v17[4]; // [rsp+78h] [rbp-20h] BYREF

  v2 = -1;
  v3 = a2;
  if ( a2 == 0xFFFF )
    return 0;
  if ( !((__int64 (*)(void))std::basic_streambuf<unsigned short>::pptr)()
    || (v9 = std::basic_streambuf<unsigned short>::epptr(a1), std::basic_streambuf<unsigned short>::pptr(a1) >= v9) )
  {
    if ( *(_QWORD *)(a1 + 128) )
    {
      if ( std::basic_streambuf<unsigned short>::eback(a1) == a1 + 112 )
        std::basic_streambuf<unsigned short>::setg(
          a1,
          *(_QWORD *)(a1 + 136),
          *(_QWORD *)(a1 + 136),
          *(_QWORD *)(a1 + 144));
      v5 = *(_QWORD *)(a1 + 104);
      if ( !v5 )
      {
        v10 = v3;
        goto LABEL_20;
      }
      v12 = v3;
      v15 = 0;
      v14 = 0;
      v6 = std::codecvt<unsigned short,char,_Mbstatet>::out(v5, a1 + 116, &v12, v13, &v15, v16, v17, &v14);
      if ( v6 && (v11 = v6 - 1) != 0 )
      {
        if ( v11 == 2 )
        {
          v10 = v12;
LABEL_20:
          if ( (unsigned __int16)_o_fputwc(v10, *(_QWORD *)(a1 + 128)) == 0xFFFF )
            return (unsigned __int16)-1;
          return v3;
        }
      }
      else if ( v14 == v16 || (v7 = v14 - v16, v7 == _o_fwrite(v16, 1, v14 - v16, *(_QWORD *)(a1 + 128))) )
      {
        *(_BYTE *)(a1 + 114) = 1;
        if ( v15 != &v12 )
          return v3;
      }
    }
    return v2;
  }
  *(_WORD *)std::basic_streambuf<unsigned short>::_Pninc(a1) = v3;
  return v3;
}

```

## disassembly

```asm
0x1800271b0  push    rbx
0x1800271b2  push    rbp
0x1800271b3  push    rsi
0x1800271b4  sub     rsp, 80h
0x1800271bb  mov     rax, cs:__security_cookie
0x1800271c2  xor     rax, rsp
0x1800271c5  mov     [rsp+98h+var_20], rax
0x1800271ca  mov     esi, 0FFFFh
0x1800271cf  movzx   ebp, dx
0x1800271d2  mov     rbx, rcx
0x1800271d5  cmp     si, dx
0x1800271d8  jz      loc_1800272DE
0x1800271de  mov     [rsp+98h+arg_10], rdi
0x1800271e6  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x1800271ec  test    rax, rax
0x1800271ef  jnz     loc_1800272E2
0x1800271f5  cmp     qword ptr [rbx+80h], 0
0x1800271fd  jz      loc_1800272BB
0x180027203  mov     rcx, rbx
0x180027206  call    cs:__imp_?eback@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::eback(void)
0x18002720c  lea     rcx, [rbx+70h]
0x180027210  cmp     rax, rcx
0x180027213  jz      loc_18002730E
0x180027219  mov     rcx, [rbx+68h]
0x18002721d  test    rcx, rcx
0x180027220  jz      loc_18002732D
0x180027226  xor     eax, eax
0x180027228  mov     [rsp+98h+var_58], bp
0x18002722d  mov     [rsp+98h+var_48], rax
0x180027232  lea     rdx, [rbx+74h]
0x180027236  mov     [rsp+98h+var_50], rax
0x18002723b  lea     r9, [rsp+98h+var_56]
0x180027240  lea     rax, [rsp+98h+var_50]
0x180027245  mov     [rsp+98h+var_60], rax
0x18002724a  lea     r8, [rsp+98h+var_58]
0x18002724f  lea     rax, [rsp+98h+var_20]
0x180027254  mov     [rsp+98h+var_68], rax
0x180027259  lea     rax, [rsp+98h+var_40]
0x18002725e  mov     [rsp+98h+var_70], rax
0x180027263  lea     rax, [rsp+98h+var_48]
0x180027268  mov     [rsp+98h+var_78], rax
0x18002726d  call    cs:__imp_?out@?$codecvt@GDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBG1AEAPEBGPEAD3AEAPEAD@Z; std::codecvt<ushort,char,_Mbstatet>::out(_Mbstatet &,ushort const *,ushort const *,ushort const * &,char *,char *,char * &)
0x180027273  test    eax, eax
0x180027275  jnz     loc_180027332
0x18002727b  mov     rdi, [rsp+98h+var_50]
0x180027280  lea     rax, [rsp+98h+var_40]
0x180027285  sub     rdi, rax
0x180027288  jz      short loc_1800272A9
0x18002728a  mov     r9, [rbx+80h]
0x180027291  lea     rcx, [rsp+98h+var_40]
0x180027296  mov     r8, rdi
0x180027299  mov     edx, 1
0x18002729e  call    cs:__imp__o_fwrite
0x1800272a4  cmp     rdi, rax
0x1800272a7  jnz     short loc_1800272BB
0x1800272a9  lea     rax, [rsp+98h+var_58]
0x1800272ae  mov     byte ptr [rbx+72h], 1
0x1800272b2  cmp     [rsp+98h+var_48], rax
0x1800272b7  cmovnz  si, bp
0x1800272bb  movzx   eax, si
0x1800272be  mov     rdi, [rsp+98h+arg_10]
0x1800272c6  mov     rcx, [rsp+98h+var_20]
0x1800272cb  xor     rcx, rsp; StackCookie
0x1800272ce  call    __security_check_cookie
0x1800272d3  add     rsp, 80h
0x1800272da  pop     rsi
0x1800272db  pop     rbp
0x1800272dc  pop     rbx
0x1800272dd  retn
0x1800272de  xor     eax, eax
0x1800272e0  jmp     short loc_1800272C6
0x1800272e2  mov     rcx, rbx
0x1800272e5  call    cs:__imp_?epptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::epptr(void)
0x1800272eb  mov     rcx, rbx
0x1800272ee  mov     rdi, rax
0x1800272f1  call    cs:__imp_?pptr@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEBAPEAGXZ; std::basic_streambuf<ushort>::pptr(void)
0x1800272f7  cmp     rax, rdi
0x1800272fa  jnb     loc_1800271F5
0x180027300  mov     rcx, rbx
0x180027303  call    cs:__imp_?_Pninc@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAPEAGXZ; std::basic_streambuf<ushort>::_Pninc(void)
0x180027309  mov     [rax], bp
0x18002730c  jmp     short loc_18002735D
0x18002730e  mov     rdx, [rbx+88h]
0x180027315  mov     rcx, rbx
0x180027318  mov     r9, [rbx+90h]
0x18002731f  mov     r8, rdx
0x180027322  call    cs:__imp_?setg@?$basic_streambuf@GU?$char_traits@G@std@@@std@@IEAAXPEAG00@Z; std::basic_streambuf<ushort>::setg(ushort *,ushort *,ushort *)
0x180027328  jmp     loc_180027219
0x18002732d  movzx   ecx, bp
0x180027330  jmp     short loc_180027349
0x180027332  sub     eax, 1
0x180027335  jz      loc_18002727B
0x18002733b  cmp     eax, 2
0x18002733e  jnz     loc_1800272BB
0x180027344  movzx   ecx, [rsp+98h+var_58]
0x180027349  mov     rdx, [rbx+80h]
0x180027350  call    cs:__imp__o_fputwc
0x180027356  cmp     ax, si
0x180027359  cmovz   bp, si
0x18002735d  movzx   eax, bp
0x180027360  jmp     loc_1800272BE
```
