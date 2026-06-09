# sub_1400BAAF8

- ea: `0x1400baaf8`
- end: `0x1400baed0`
- name: `sub_1400BAAF8`
- size: `984`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `broker_com_uri`

## callers

- `0x1400ba856`

## callees

- `0x14003abe0`
- `0x140086090`
- `0x1400b9ab0`
- `0x1400baaf8`
- `0x1400baed0`
- `0x1400baeda`
- `0x1400baee0`
- `0x1400baef0`
- `0x1400baef4`
- `0x1400baf00`
- `0x1400baf10`
- `0x1400baf16`
- `0x1400baf1c`
- `0x1400baf22`
- `0x1400baf28`
- `0x1400baf30`
- `0x1400baf38`
- `0x1400bb0a6`
- `0x1400bb0d4`
- `0x1400bb120`
- `0x1400bb18c`
- `0x1400bb1dc`
- `0x1400bb23c`
- `0x1400bb2a2`
- `0x1400bb3ee`
- `0x1400bb4d4`
- `0x1400bb868`
- `0x1400bc12c`
- `0x1400c9d70`
- `0x1400f1cc8`
- `0x1400f1d0c`
- `0x1400f1d2a`
- `0x1400f1e30`
- `0x14011c8c4`
- `0x14011cc78`
- `0x14011ccf4`
- `0x14011fa70`
- `0x1401bac10`
- `0x1401bac14`
- `0x1401bac38`
- `0x1401bacbe`
- `0x1401bad63`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400bad6f`
- `KERNEL32!GetCurrentThreadId` at `0x1400bad6f`
- `KERNEL32!GetLastError` at `0x1401b9252`
- `KERNEL32!GetLastError` at `0x1401b92b6`
- `KERNEL32!GetLastError` at `0x1401b9252`
- `KERNEL32!GetLastError` at `0x1401b92b6`
- `KERNEL32!GetModuleHandleExW` at `0x1400bab36`
- `KERNEL32!GetModuleHandleExW` at `0x1400bab36`

## pseudocode

```c
__int64 __fastcall sub_1400BAAF8(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // r15
  void **v7; // rsi
  __int64 v8; // rcx
  _DWORD *v9; // rdi
  void *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  unsigned int v14; // eax
  __int64 v15; // rdi
  __int64 v16; // rax
  _QWORD *v17; // rax
  _QWORD *v18; // rdi
  _QWORD *v19; // r12
  _QWORD *v20; // rdi
  _QWORD *v21; // r12
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdi
  __int64 v26; // rax
  void *v27; // rax
  _DWORD *v29; // rdi
  _DWORD *v30; // rsi
  __int64 i; // rcx
  __int64 v32; // [rsp+0h] [rbp-178h] BYREF
  _BYTE v33[24]; // [rsp+20h] [rbp-158h] BYREF
  _BYTE v34[24]; // [rsp+38h] [rbp-140h] BYREF
  HMODULE phModule; // [rsp+50h] [rbp-128h] BYREF
  void *v36; // [rsp+58h] [rbp-120h] BYREF
  char v37[8]; // [rsp+60h] [rbp-118h] BYREF
  _BYTE v38[56]; // [rsp+68h] [rbp-110h] BYREF
  _DWORD v39[16]; // [rsp+A0h] [rbp-D8h] BYREF
  __int64 v40; // [rsp+E0h] [rbp-98h]
  _BYTE v41[80]; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v42; // [rsp+140h] [rbp-38h]

  phModule = 0;
  if ( !GetModuleHandleExW(2u, 0, &phModule) )
LABEL_41:
    __debugbreak();
  if ( phModule != &_ImageBase )
  {
    *(_BYTE *)a2 = 1;
    *(_DWORD *)(a2 + 8) = 64;
    goto LABEL_47;
  }
  if ( !a3 )
  {
    *(_BYTE *)a2 = 1;
    *(_DWORD *)(a2 + 8) = 2;
    goto LABEL_47;
  }
  v6 = sub_1400B9AB0(a3);
  if ( !(unsigned __int8)sub_1400C9D70(v6) && !(unsigned __int8)sub_1400BB2A2(v6) )
  {
    *(_BYTE *)a2 = 1;
    *(_DWORD *)(a2 + 8) = 69;
LABEL_47:
    *(_DWORD *)(a2 + 12) = GetLastError();
    *(_BYTE *)(a2 + 16) = 0;
    goto LABEL_39;
  }
  if ( dword_14043B940 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)TlsIndex)
                                   + 4LL) )
  {
    sub_14011CC78(&dword_14043B940);
    if ( dword_14043B940 == -1 )
    {
      GetCurrentThreadId();
      Init_thread_footer(&dword_14043B940);
    }
  }
  if ( !byte_14043B944 )
  {
    sub_1401BAD63(0x8000);
    byte_14043B944 = 1;
  }
  memset(v41, 0, sizeof(v41));
  sub_1400BC12C(a3, v41);
  if ( v41[0] >= 2u )
  {
    __debugbreak();
    BUG();
  }
  if ( v41[0] )
  {
    qmemcpy((void *)(a2 + 8), &v41[8], 0x48u);
    *(_BYTE *)a2 = 1;
  }
  else
  {
    memset(v39, 0, sizeof(v39));
    v40 = 0;
    sub_1400BB18C(a1, v39, *(unsigned int *)(v6 + 68), *(unsigned int *)(v6 + 24));
    if ( v39[0] )
      goto LABEL_48;
    v7 = &v36;
    sub_1400BB4D4(a3, &v36);
    v8 = 18;
    v9 = v39;
    while ( v8 )
    {
      *v9 = *(_DWORD *)v7;
      v7 = (void **)((char *)v7 + 4);
      ++v9;
      --v8;
    }
    if ( v39[0] )
    {
LABEL_48:
      v29 = (_DWORD *)(a2 + 8);
      v30 = v39;
      for ( i = 18; i; --i )
        *v29++ = *v30++;
      *(_BYTE *)a2 = 1;
    }
    else
    {
      v10 = operator new(0x140u);
      sub_1400BB3EE(v10);
      sub_1400BAEDA(v10, 128);
      sub_1400BB120(a1, v34, *(unsigned int *)(v6 + 68));
      sub_1400BB1DC(v10, v34);
      v11 = std::ios_base::precision((std::ios_base *)v6);
      sub_1400BB0D4(v10, v11);
      if ( (unsigned __int8)sub_1400BAEE0(v6) )
      {
        sub_1401BAC38(v33);
        sub_1401BAC14(v10, v33);
      }
      if ( !*(_BYTE *)(v6 + 75) && (int)sub_140086090(v12) >= 8 && (int)sub_1400BAEF0(v6) <= 1 )
      {
        LOBYTE(v13) = 1;
        sub_1400BAEF4(v10, v13);
      }
      v14 = sub_1400BAF00(a3);
      sub_1400BAF28(v10, v14);
      v15 = sub_1400BAF16(a3);
      v16 = __crt_win32_buffer<char,__crt_win32_buffer_public_dynamic_resizing>::capacity(a3);
      sub_1400BB0A6(v10, v16, v15);
      v17 = (_QWORD *)sub_1400BAF22(a3);
      v18 = (_QWORD *)*v17;
      v19 = (_QWORD *)v17[1];
      while ( v18 != v19 )
        sub_1400BAF38(v10, *v18++);
      v20 = *(_QWORD **)(v6 + 136);
      v21 = *(_QWORD **)(v6 + 144);
      while ( v20 != v21 )
        sub_1400BAF38(v10, *v20++);
      v22 = sub_1400BAF30(v6);
      if ( v22 )
      {
        v25 = v22;
        if ( !*(_BYTE *)(v6 + 50) && (unsigned int)sub_1401BAC10(v6) )
        {
          __debugbreak();
          BUG();
        }
        sub_1401BACBE(v10, v25);
      }
      v26 = sub_1400BAED0(a3, v23, v24);
      sub_1400BB23C(v10, v26);
      if ( (unsigned __int8)sub_1400BB868(v10) )
      {
        if ( v41[0] )
        {
          __debugbreak();
          BUG();
        }
        v36 = v10;
        sub_1400F1E30(v37, &v41[8]);
        sub_1400F1E30(v38, &v41[16]);
        *(_BYTE *)a2 = 0;
        v27 = v36;
        v36 = 0;
        *(_QWORD *)(a2 + 8) = v27;
        sub_1400F1E30(a2 + 16, v37);
        sub_1400F1E30(a2 + 24, v38);
        sub_1400F1CC8(&v36);
      }
      else
      {
        *(_BYTE *)a2 = 1;
        *(_DWORD *)(a2 + 8) = 17;
        *(_DWORD *)(a2 + 12) = GetLastError();
        *(_BYTE *)(a2 + 16) = 0;
        if ( v10 )
        {
          sub_1400F1D2A(v10);
          sub_14003ABE0(v10, 320);
        }
      }
    }
    if ( !v41[0] || v41[0] == 2 )
      sub_1400F1D0C(&v41[8]);
  }
LABEL_39:
  if ( _security_cookie != ((unsigned __int64)&v32 ^ v42) )
    goto LABEL_41;
  return a2;
}

```

## disassembly

```asm
0x1400baaf8  push    r15
0x1400baafa  push    r14
0x1400baafc  push    r12
0x1400baafe  push    rsi
0x1400baaff  push    rdi
0x1400bab00  push    rbx
0x1400bab01  sub     rsp, 148h
0x1400bab08  mov     r14, r8
0x1400bab0b  mov     rbx, rdx
0x1400bab0e  mov     r12, rcx
0x1400bab11  mov     rax, cs:__security_cookie
0x1400bab18  xor     rax, rsp
0x1400bab1b  mov     [rsp+178h+var_38], rax
0x1400bab23  lea     r8, [rsp+178h+phModule]; phModule
0x1400bab28  mov     qword ptr [r8], 0
0x1400bab2f  mov     ecx, 2; dwFlags
0x1400bab34  xor     edx, edx; lpModuleName
0x1400bab36  call    cs:GetModuleHandleExW
0x1400bab3c  test    eax, eax
0x1400bab3e  jz      loc_1401B9227
0x1400bab44  lea     rax, __ImageBase
0x1400bab4b  cmp     [rsp+178h+phModule], rax
0x1400bab50  jnz     loc_1401B923C
0x1400bab56  test    r14, r14
0x1400bab59  jz      loc_1401B9248
0x1400bab5f  mov     rcx, r14
0x1400bab62  call    sub_1400B9AB0
0x1400bab67  mov     r15, rax
0x1400bab6a  mov     rcx, rax
0x1400bab6d  call    sub_1400C9D70
0x1400bab72  test    al, al
0x1400bab74  jnz     short loc_1400BAB86
0x1400bab76  mov     rcx, r15
0x1400bab79  call    sub_1400BB2A2
0x1400bab7e  test    al, al
0x1400bab80  jz      loc_1401B9230
0x1400bab86  mov     eax, cs:dword_14043B940
0x1400bab8c  mov     ecx, cs:TlsIndex
0x1400bab92  mov     rdx, gs:58h
0x1400bab9b  mov     rcx, [rdx+rcx*8]
0x1400bab9f  cmp     eax, [rcx+4]
0x1400baba5  jg      loc_1400BAD56
0x1400babab  cmp     cs:byte_14043B944, 0
0x1400babb2  jz      loc_1400BAD40
0x1400babb8  xorps   xmm0, xmm0
0x1400babbb  lea     rsi, [rsp+178h+var_88]
0x1400babc3  movaps  xmmword ptr [rsi+40h], xmm0
0x1400babc7  movaps  xmmword ptr [rsi+30h], xmm0
0x1400babcb  movaps  xmmword ptr [rsi+20h], xmm0
0x1400babcf  movaps  xmmword ptr [rsi+10h], xmm0
0x1400babd3  movaps  xmmword ptr [rsi], xmm0
0x1400babd6  mov     rcx, r14
0x1400babd9  mov     rdx, rsi
0x1400babdc  call    sub_1400BC12C
0x1400babe1  mov     al, [rsi]
0x1400babe3  cmp     al, 2
0x1400babe5  jnb     loc_1401B922A
0x1400babeb  test    al, al
0x1400babed  jnz     loc_1401B9290
0x1400babf3  xorps   xmm0, xmm0
0x1400babf6  lea     rsi, [rsp+178h+var_D8]
0x1400babfe  movaps  xmmword ptr [rsi+30h], xmm0
0x1400bac02  movaps  xmmword ptr [rsi+20h], xmm0
0x1400bac06  movaps  xmmword ptr [rsi+10h], xmm0
0x1400bac0a  movaps  xmmword ptr [rsi], xmm0
0x1400bac0d  mov     qword ptr [rsi+40h], 0
0x1400bac15  mov     r9d, [r15+18h]
0x1400bac19  mov     r8d, [r15+44h]
0x1400bac1d  mov     rcx, r12
0x1400bac20  mov     rdx, rsi
0x1400bac23  call    sub_1400BB18C
0x1400bac28  cmp     dword ptr [rsi], 0
0x1400bac2b  jnz     loc_1401B9264
0x1400bac31  lea     rsi, [rsp+178h+var_120]
0x1400bac36  mov     rcx, r14
0x1400bac39  mov     rdx, rsi
0x1400bac3c  call    sub_1400BB4D4
0x1400bac41  lea     rax, [rsp+178h+var_D8]
0x1400bac49  mov     ecx, 12h
0x1400bac4e  mov     rdi, rax
0x1400bac51  rep movsd
0x1400bac53  cmp     dword ptr [rax], 0
0x1400bac56  jnz     loc_1401B9264
0x1400bac5c  mov     ecx, 140h; unsigned __int64
0x1400bac61  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400bac66  mov     rsi, rax
0x1400bac69  mov     rcx, rax
0x1400bac6c  call    sub_1400BB3EE
0x1400bac71  mov     rcx, rsi
0x1400bac74  mov     edx, 80h
0x1400bac79  call    sub_1400BAEDA
0x1400bac7e  mov     r8d, [r15+44h]
0x1400bac82  lea     rdi, [rsp+178h+var_140]
0x1400bac87  mov     rcx, r12
0x1400bac8a  mov     rdx, rdi
0x1400bac8d  call    sub_1400BB120
0x1400bac92  mov     rcx, rsi
0x1400bac95  mov     rdx, rdi
0x1400bac98  call    sub_1400BB1DC
0x1400bac9d  mov     rcx, r15; this
0x1400baca0  call    ?precision@ios_base@std@@QEBA_JXZ; std::ios_base::precision(void)
0x1400baca5  mov     rcx, rsi
0x1400baca8  mov     rdx, rax
0x1400bacab  call    sub_1400BB0D4
0x1400bacb0  mov     rcx, r15
0x1400bacb3  call    sub_1400BAEE0
0x1400bacb8  test    al, al
0x1400bacba  jz      short loc_1400BACD4
0x1400bacbc  lea     rdi, [rsp+178h+var_158]
0x1400bacc1  mov     rcx, rdi
0x1400bacc4  call    sub_1401BAC38
0x1400bacc9  mov     rcx, rsi
0x1400baccc  mov     rdx, rdi
0x1400baccf  call    sub_1401BAC14
0x1400bacd4  cmp     byte ptr [r15+4Bh], 0
0x1400bacd9  jnz     short loc_1400BACFC
0x1400bacdb  call    sub_140086090
0x1400bace0  cmp     eax, 8
0x1400bace3  jl      short loc_1400BACFC
0x1400bace5  mov     rcx, r15
0x1400bace8  call    sub_1400BAEF0
0x1400baced  cmp     eax, 1
0x1400bacf0  jg      short loc_1400BACFC
0x1400bacf2  mov     rcx, rsi
0x1400bacf5  mov     dl, 1
0x1400bacf7  call    sub_1400BAEF4
0x1400bacfc  mov     rcx, r14
0x1400bacff  call    sub_1400BAF00
0x1400bad04  mov     rcx, rsi
0x1400bad07  mov     edx, eax
0x1400bad09  call    sub_1400BAF28
0x1400bad0e  mov     rcx, r14
0x1400bad11  call    sub_1400BAF16
0x1400bad16  mov     rdi, rax
0x1400bad19  mov     rcx, r14
0x1400bad1c  call    ?capacity@?$__crt_win32_buffer@DU__crt_win32_buffer_public_dynamic_resizing@@@@QEBA_KXZ; __crt_win32_buffer<char,__crt_win32_buffer_public_dynamic_resizing>::capacity(void)
0x1400bad21  mov     rcx, rsi
0x1400bad24  mov     rdx, rax
0x1400bad27  mov     r8, rdi
0x1400bad2a  call    sub_1400BB0A6
0x1400bad2f  mov     rcx, r14
0x1400bad32  call    sub_1400BAF22
0x1400bad37  mov     rdi, [rax]
0x1400bad3a  mov     r12, [rax+8]
0x1400bad3e  jmp     short loc_1400BAD95
0x1400bad40  mov     ecx, 8000h
0x1400bad45  call    sub_1401BAD63
0x1400bad4a  mov     cs:byte_14043B944, 1
0x1400bad51  jmp     loc_1400BABB8
0x1400bad56  lea     rcx, dword_14043B940
0x1400bad5d  call    sub_14011CC78
0x1400bad62  cmp     cs:dword_14043B940, 0FFFFFFFFh
0x1400bad69  jnz     loc_1400BABAB
0x1400bad6f  call    cs:__imp_GetCurrentThreadId
0x1400bad75  lea     rcx, dword_14043B940
0x1400bad7c  call    _Init_thread_footer
0x1400bad81  jmp     loc_1400BABAB
0x1400bad86  mov     rdx, [rdi]
0x1400bad89  mov     rcx, rsi
0x1400bad8c  call    sub_1400BAF38
0x1400bad91  add     rdi, 8
0x1400bad95  cmp     rdi, r12
0x1400bad98  jnz     short loc_1400BAD86
0x1400bad9a  mov     rdi, [r15+88h]
0x1400bada1  mov     r12, [r15+90h]
0x1400bada8  jmp     short loc_1400BADB9
0x1400badaa  mov     rdx, [rdi]
0x1400badad  mov     rcx, rsi
0x1400badb0  call    sub_1400BAF38
0x1400badb5  add     rdi, 8
0x1400badb9  cmp     rdi, r12
0x1400badbc  jnz     short loc_1400BADAA
0x1400badbe  mov     rcx, r15
0x1400badc1  call    sub_1400BAF30
0x1400badc6  test    rax, rax
0x1400badc9  jz      short loc_1400BADF0
0x1400badcb  mov     rdi, rax
0x1400badce  cmp     byte ptr [r15+32h], 0
0x1400badd3  jnz     short loc_1400BADE5
0x1400badd5  mov     rcx, r15
0x1400badd8  call    sub_1401BAC10
0x1400baddd  test    eax, eax
0x1400baddf  jnz     loc_1401B928D
0x1400bade5  mov     rcx, rsi
0x1400bade8  mov     rdx, rdi
0x1400badeb  call    sub_1401BACBE
0x1400badf0  mov     rcx, r14
0x1400badf3  call    sub_1400BAED0
0x1400badf8  mov     rcx, rsi
0x1400badfb  mov     rdx, rax
0x1400badfe  call    sub_1400BB23C
0x1400bae03  mov     rcx, rsi
0x1400bae06  call    sub_1400BB868
0x1400bae0b  test    al, al
0x1400bae0d  jz      loc_1401B92AC
0x1400bae13  cmp     [rsp+178h+var_88], 0
0x1400bae1b  jnz     loc_1401B922D
0x1400bae21  lea     rdx, [rsp+178h+var_80]
0x1400bae29  lea     rdi, [rsp+178h+var_118]
0x1400bae2e  mov     [rdi-8], rsi
0x1400bae32  mov     rcx, rdi
0x1400bae35  call    sub_1400F1E30
0x1400bae3a  lea     rsi, [rsp+178h+var_110]
0x1400bae3f  lea     rdx, [rsp+178h+var_78]
0x1400bae47  mov     rcx, rsi
0x1400bae4a  call    sub_1400F1E30
0x1400bae4f  mov     byte ptr [rbx], 0
0x1400bae52  mov     rax, [rsi-10h]
0x1400bae56  mov     qword ptr [rsi-10h], 0
0x1400bae5e  mov     [rbx+8], rax
0x1400bae62  lea     rcx, [rbx+10h]
0x1400bae66  mov     rdx, rdi
0x1400bae69  call    sub_1400F1E30
0x1400bae6e  lea     rcx, [rbx+18h]
0x1400bae72  mov     rdx, rsi
0x1400bae75  call    sub_1400F1E30
0x1400bae7a  lea     rcx, [rsp+178h+var_120]
0x1400bae7f  call    sub_1400F1CC8
0x1400bae84  movzx   eax, [rsp+178h+var_88]
0x1400bae8c  test    eax, eax
0x1400bae8e  jnz     loc_1401B927F
0x1400bae94  lea     rcx, [rsp+178h+var_80]
0x1400bae9c  call    sub_1400F1D0C
0x1400baea1  mov     rax, [rsp+178h+var_38]
0x1400baea9  xor     rax, rsp
0x1400baeac  mov     rcx, cs:__security_cookie
0x1400baeb3  cmp     rcx, rax
0x1400baeb6  jnz     loc_1401B9217
0x1400baebc  mov     rax, rbx
0x1400baebf  add     rsp, 148h
0x1400baec6  pop     rbx
0x1400baec7  pop     rdi
0x1400baec8  pop     rsi
0x1400baec9  pop     r12
0x1400baecb  pop     r14
0x1400baecd  pop     r15
0x1400baecf  retn
0x1401b9217  mov     rcx, [rsp+178h+var_38]
0x1401b921f  xor     rcx, rsp; StackCookie
0x1401b9222  call    __security_check_cookie
0x1401b9227  int     3; Trap to Debugger
0x1401b9228  ud2
0x1401b922a  int     3; Trap to Debugger
0x1401b922b  ud2
0x1401b922d  int     3; Trap to Debugger
0x1401b922e  ud2
0x1401b9230  mov     byte ptr [rbx], 1
0x1401b9233  mov     dword ptr [rbx+8], 45h ; 'E'
0x1401b923a  jmp     short loc_1401B9252
0x1401b923c  mov     byte ptr [rbx], 1
0x1401b923f  mov     dword ptr [rbx+8], 40h ; '@'
0x1401b9246  jmp     short loc_1401B9252
0x1401b9248  mov     byte ptr [rbx], 1
0x1401b924b  mov     dword ptr [rbx+8], 2
0x1401b9252  call    cs:__imp_GetLastError
0x1401b9258  mov     [rbx+0Ch], eax
0x1401b925b  mov     byte ptr [rbx+10h], 0
0x1401b925f  jmp     loc_1400BAEA1
0x1401b9264  lea     rdi, [rbx+8]
0x1401b9268  lea     rsi, [rsp+178h+var_D8]
0x1401b9270  mov     ecx, 12h
0x1401b9275  rep movsd
0x1401b9277  mov     byte ptr [rbx], 1
0x1401b927a  jmp     loc_1400BAE84
0x1401b927f  cmp     eax, 2
0x1401b9282  jz      loc_1400BAE94
0x1401b9288  jmp     loc_1400BAEA1
0x1401b928d  int     3; Trap to Debugger
0x1401b928e  ud2
0x1401b9290  lea     rsi, [rsp+178h+var_80]
0x1401b9298  lea     rdi, [rbx+8]
0x1401b929c  mov     ecx, 9
0x1401b92a1  rep movsq
0x1401b92a4  mov     byte ptr [rbx], 1
0x1401b92a7  jmp     loc_1400BAEA1
0x1401b92ac  mov     byte ptr [rbx], 1
0x1401b92af  mov     dword ptr [rbx+8], 11h
0x1401b92b6  call    cs:__imp_GetLastError
0x1401b92bc  mov     [rbx+0Ch], eax
0x1401b92bf  mov     byte ptr [rbx+10h], 0
0x1401b92c3  test    rsi, rsi
0x1401b92c6  jz      loc_1400BAE84
0x1401b92cc  mov     rcx, rsi
0x1401b92cf  call    sub_1400F1D2A
0x1401b92d4  mov     edx, 140h
0x1401b92d9  mov     rcx, rsi
0x1401b92dc  call    sub_14003ABE0
0x1401b92e1  jmp     loc_1400BAE84
```
