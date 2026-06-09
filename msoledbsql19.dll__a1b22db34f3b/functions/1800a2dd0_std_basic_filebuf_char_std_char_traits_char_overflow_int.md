# std::basic_filebuf<char,std::char_traits<char>>::overflow(int)

- ea: `0x1800a2dd0`
- end: `0x1800a2f96`
- name: `?overflow@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAAHH@Z`
- size: `454`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003d80`
- `0x1800a2dd0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800a2e8e`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800a2f0c`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800a2e8e`
- `api-ms-win-crt-stdio-l1-1-0!fputc` at `0x1800a2f0c`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800a2f46`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800a2f46`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e05`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e1f`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e05`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e1f`
- `MSVCP140!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x1800a2e74`
- `MSVCP140!?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z` at `0x1800a2e74`
- `MSVCP140!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e13`
- `MSVCP140!?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e13`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800a2e30`
- `MSVCP140!?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ` at `0x1800a2e30`
- `MSVCP140!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e51`
- `MSVCP140!?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800a2e51`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800a2eec`
- `MSVCP140!?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z` at `0x1800a2eec`

## pseudocode

```c
__int64 __fastcall std::filebuf::overflow(__int64 a1, unsigned int a2)
{
  unsigned __int64 v5; // rbx
  __int64 v6; // rcx
  int v7; // eax
  unsigned int v8; // ecx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ecx
  __int64 v13; // rbx
  unsigned int v14; // ecx
  _BYTE *v15; // [rsp+40h] [rbp-48h] BYREF
  char *v16; // [rsp+48h] [rbp-40h] BYREF
  char v17; // [rsp+50h] [rbp-38h] BYREF
  _BYTE v18[7]; // [rsp+51h] [rbp-37h] BYREF
  _BYTE Buffer[32]; // [rsp+58h] [rbp-30h] BYREF
  __int64 v20; // [rsp+78h] [rbp-10h] BYREF

  if ( a2 == -1 )
    return 0;
  if ( ((__int64 (*)(void))std::streambuf::pptr)() )
  {
    v5 = std::streambuf::epptr(a1);
    if ( std::streambuf::pptr(a1) < v5 )
    {
      _mm_lfence();
      *(_BYTE *)std::streambuf::_Pninc(a1) = a2;
      return a2;
    }
  }
  if ( !*(_QWORD *)(a1 + 128) )
    return 0xFFFFFFFFLL;
  if ( std::streambuf::eback(a1) == a1 + 112 )
    std::streambuf::setg(a1, *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 136), *(_QWORD *)(a1 + 144));
  v6 = *(_QWORD *)(a1 + 104);
  if ( !v6 )
  {
    v7 = fputc((char)a2, *(FILE **)(a1 + 128));
    v8 = -1;
    if ( v7 != -1 )
      return a2;
    return v8;
  }
  v17 = a2;
  v16 = 0;
  v15 = 0;
  v9 = std::codecvt<char,char,_Mbstatet>::out(v6, a1 + 116, &v17, v18, &v16, Buffer, &v20, &v15);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 == 2 )
      {
        v11 = fputc(v17, *(FILE **)(a1 + 128));
        v12 = -1;
        if ( v11 != -1 )
          return a2;
        return v12;
      }
      return 0xFFFFFFFFLL;
    }
  }
  if ( v15 != Buffer )
  {
    _mm_lfence();
    v13 = v15 - Buffer;
    if ( v13 != fwrite(Buffer, 1u, v15 - Buffer, *(FILE **)(a1 + 128)) )
      return 0xFFFFFFFFLL;
  }
  *(_BYTE *)(a1 + 113) = 1;
  v14 = -1;
  if ( v16 != &v17 )
    return a2;
  return v14;
}

```

## disassembly

```asm
0x1800a2dd0  mov     [rsp+arg_18], rsi
0x1800a2dd5  push    rdi
0x1800a2dd6  sub     rsp, 80h
0x1800a2ddd  mov     rax, cs:__security_cookie
0x1800a2de4  xor     rax, rsp
0x1800a2de7  mov     [rsp+88h+var_10], rax
0x1800a2dec  mov     esi, edx
0x1800a2dee  mov     rdi, rcx
0x1800a2df1  cmp     edx, 0FFFFFFFFh
0x1800a2df4  jnz     short loc_1800A2DFD
0x1800a2df6  xor     eax, eax
0x1800a2df8  jmp     loc_1800A2F78
0x1800a2dfd  mov     [rsp+88h+arg_10], rbx
0x1800a2e05  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800a2e0b  test    rax, rax
0x1800a2e0e  jz      short loc_1800A2E40
0x1800a2e10  mov     rcx, rdi
0x1800a2e13  call    cs:__imp_?epptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::epptr(void)
0x1800a2e19  mov     rcx, rdi
0x1800a2e1c  mov     rbx, rax
0x1800a2e1f  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800a2e25  cmp     rax, rbx
0x1800a2e28  jnb     short loc_1800A2E40
0x1800a2e2a  lfence
0x1800a2e2d  mov     rcx, rdi
0x1800a2e30  call    cs:__imp_?_Pninc@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAPEADXZ; std::streambuf::_Pninc(void)
0x1800a2e36  mov     [rax], sil
0x1800a2e39  mov     eax, esi
0x1800a2e3b  jmp     loc_1800A2F70
0x1800a2e40  cmp     qword ptr [rdi+80h], 0
0x1800a2e48  jz      loc_1800A2F6B
0x1800a2e4e  mov     rcx, rdi
0x1800a2e51  call    cs:__imp_?eback@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::eback(void)
0x1800a2e57  lea     rcx, [rdi+70h]
0x1800a2e5b  cmp     rax, rcx
0x1800a2e5e  jnz     short loc_1800A2E7A
0x1800a2e60  mov     rdx, [rdi+88h]
0x1800a2e67  mov     rcx, rdi
0x1800a2e6a  mov     r9, [rdi+90h]
0x1800a2e71  mov     r8, rdx
0x1800a2e74  call    cs:__imp_?setg@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXPEAD00@Z; std::streambuf::setg(char *,char *,char *)
0x1800a2e7a  mov     rcx, [rdi+68h]
0x1800a2e7e  test    rcx, rcx
0x1800a2e81  jnz     short loc_1800A2EA5
0x1800a2e83  mov     rdx, [rdi+80h]; Stream
0x1800a2e8a  movsx   ecx, sil; Character
0x1800a2e8e  call    cs:__imp_fputc
0x1800a2e94  mov     ecx, 0FFFFFFFFh
0x1800a2e99  cmp     eax, ecx
0x1800a2e9b  cmovnz  ecx, esi
0x1800a2e9e  mov     eax, ecx
0x1800a2ea0  jmp     loc_1800A2F70
0x1800a2ea5  xor     eax, eax
0x1800a2ea7  mov     [rsp+88h+var_38], sil
0x1800a2eac  mov     [rsp+88h+var_40], rax
0x1800a2eb1  lea     rdx, [rdi+74h]
0x1800a2eb5  mov     [rsp+88h+var_48], rax
0x1800a2eba  lea     r9, [rsp+88h+var_37]
0x1800a2ebf  lea     rax, [rsp+88h+var_48]
0x1800a2ec4  mov     [rsp+88h+var_50], rax
0x1800a2ec9  lea     r8, [rsp+88h+var_38]
0x1800a2ece  lea     rax, [rsp+88h+var_10]
0x1800a2ed3  mov     [rsp+88h+var_58], rax
0x1800a2ed8  lea     rax, [rsp+88h+Buffer]
0x1800a2edd  mov     [rsp+88h+var_60], rax
0x1800a2ee2  lea     rax, [rsp+88h+var_40]
0x1800a2ee7  mov     [rsp+88h+var_68], rax
0x1800a2eec  call    cs:__imp_?out@?$codecvt@DDU_Mbstatet@@@std@@QEBAHAEAU_Mbstatet@@PEBD1AEAPEBDPEAD3AEAPEAD@Z; std::codecvt<char,char,_Mbstatet>::out(_Mbstatet &,char const *,char const *,char const * &,char *,char *,char * &)
0x1800a2ef2  test    eax, eax
0x1800a2ef4  jz      short loc_1800A2F20
0x1800a2ef6  sub     eax, 1
0x1800a2ef9  jz      short loc_1800A2F20
0x1800a2efb  cmp     eax, 2
0x1800a2efe  jnz     short loc_1800A2F6B
0x1800a2f00  movsx   ecx, [rsp+88h+var_38]; Character
0x1800a2f05  mov     rdx, [rdi+80h]; Stream
0x1800a2f0c  call    cs:__imp_fputc
0x1800a2f12  mov     ecx, 0FFFFFFFFh
0x1800a2f17  cmp     eax, ecx
0x1800a2f19  cmovnz  ecx, esi
0x1800a2f1c  mov     eax, ecx
0x1800a2f1e  jmp     short loc_1800A2F70
0x1800a2f20  mov     rbx, [rsp+88h+var_48]
0x1800a2f25  lea     rax, [rsp+88h+Buffer]
0x1800a2f2a  sub     rbx, rax
0x1800a2f2d  jz      short loc_1800A2F51
0x1800a2f2f  lfence
0x1800a2f32  mov     r9, [rdi+80h]; Stream
0x1800a2f39  lea     rcx, [rsp+88h+Buffer]; Buffer
0x1800a2f3e  mov     r8, rbx; ElementCount
0x1800a2f41  mov     edx, 1; ElementSize
0x1800a2f46  call    cs:__imp_fwrite
0x1800a2f4c  cmp     rbx, rax
0x1800a2f4f  jnz     short loc_1800A2F6B
0x1800a2f51  lea     rax, [rsp+88h+var_38]
0x1800a2f56  mov     byte ptr [rdi+71h], 1
0x1800a2f5a  cmp     [rsp+88h+var_40], rax
0x1800a2f5f  mov     ecx, 0FFFFFFFFh
0x1800a2f64  cmovnz  ecx, esi
0x1800a2f67  mov     eax, ecx
0x1800a2f69  jmp     short loc_1800A2F70
0x1800a2f6b  mov     eax, 0FFFFFFFFh
0x1800a2f70  mov     rbx, [rsp+88h+arg_10]
0x1800a2f78  mov     rcx, [rsp+88h+var_10]
0x1800a2f7d  xor     rcx, rsp; StackCookie
0x1800a2f80  call    __security_check_cookie
0x1800a2f85  mov     rsi, [rsp+88h+arg_18]
0x1800a2f8d  add     rsp, 80h
0x1800a2f94  pop     rdi
0x1800a2f95  retn
```
