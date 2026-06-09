# WSTVerifySignature

- ea: `0x180034194`
- end: `0x18003452d`
- name: `WSTVerifySignature`
- size: `921`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180024b90`

## callees

- `0x1800210f0`
- `0x180023cb8`
- `0x180023ce0`
- `0x180023d9c`
- `0x18002b744`
- `0x180034194`
- `0x180034534`
- `0x180046010`

## import_xrefs

- `cryptdll!CDLocateCheckSum` at `0x180034378`
- `cryptdll!CDLocateCheckSum` at `0x180034378`

## string_xrefs

- `0x180034272`: `onecore\ds\security\protocols\pku2u\message.cxx`
- `0x1800342c6`: `onecore\ds\security\protocols\pku2u\message.cxx`

## pseudocode

```c
__int64 __fastcall WSTVerifySignature(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  __int64 v6; // rdx
  unsigned int v7; // r8d
  int v10; // eax
  int v11; // ebx
  int v12; // r9d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  unsigned int i; // edi
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rdi
  int v19; // eax
  char v20; // r8
  __int64 j; // rdx
  char v22; // cl
  char v23; // al
  __int64 v25; // [rsp+50h] [rbp-49h] BYREF
  __int64 v26; // [rsp+58h] [rbp-41h] BYREF
  unsigned int v27; // [rsp+60h] [rbp-39h] BYREF
  int v28; // [rsp+64h] [rbp-35h] BYREF
  __int64 v29; // [rsp+68h] [rbp-31h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h] BYREF
  _BYTE v31[64]; // [rsp+80h] [rbp-19h] BYREF

  v6 = 0;
  v26 = 0;
  v25 = 0;
  v7 = 0;
  v29 = 0;
  v27 = 0;
  v28 = 0;
  v30 = 0;
  while ( v7 < *(_DWORD *)(a2 + 4) )
  {
    v10 = *(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL * v7 + 4);
    if ( v10 < 0 && (v10 & 0x10000000) != 0 )
    {
      v11 = -2146893048;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        return (unsigned int)v11;
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
      goto LABEL_50;
    }
    if ( (v10 & 0xFFFFFFF) == 2 )
      v6 = *(_QWORD *)(a2 + 8) + 16LL * v7;
    ++v7;
  }
  if ( !v6 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        (unsigned int)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        45);
    v11 = -1073741811;
    goto LABEL_50;
  }
  v12 = *(_DWORD *)(a1 + 84);
  if ( (v12 & 0x1000C) == 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_dsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        30,
        (unsigned int)&WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids,
        v12,
        (__int64)"onecore\\ds\\security\\protocols\\pku2u\\message.cxx",
        56);
    v11 = -1073741637;
    goto LABEL_50;
  }
  v11 = WSTVerifySignatureToken(a1, v6, 0, a3, (__int64)&v29, (__int64)&v28, (__int64)&v27, 0, (__int64)&v30);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_50;
    v14 = 31;
LABEL_25:
    WPP_SF_d(v13[2], v14, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids, (unsigned int)v11);
    goto LABEL_50;
  }
  v11 = CDLocateCheckSum(v27, &v26);
  if ( v11 >= 0 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64 *))(v26 + 48))(
            *(_QWORD *)(a1 + 56),
            *(unsigned int *)(a1 + 48),
            (*(_DWORD *)(a1 + 80) & 4) != 0 ? 25 : 23,
            &v25);
    if ( v11 >= 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a2 + 4); ++i )
      {
        v16 = *(_QWORD *)(a2 + 8);
        if ( (*(_DWORD *)(v16 + 16LL * i + 4) & 0xFFFFFFF) != 2 && *(int *)(v16 + 16LL * i + 4) >= 0 )
        {
          v17 = *(unsigned int *)(v16 + 16LL * i);
          if ( (_DWORD)v17 )
          {
            v11 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(v26 + 24))(
                    v25,
                    v17,
                    *(_QWORD *)(v16 + 16LL * i + 8));
            if ( v11 < 0 )
              goto LABEL_50;
          }
        }
      }
      v18 = v29;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(v26 + 24))(v25, 16, v29 - 2);
      if ( v11 >= 0 )
      {
        v11 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(v26 + 32))(v25, v31);
        if ( v11 >= 0 )
        {
          v19 = (*(__int64 (__fastcall **)(__int64 *))(v26 + 40))(&v25);
          v25 = 0;
          v11 = v19;
          if ( v19 < 0 )
            return (unsigned int)v11;
          v20 = 0;
          for ( j = 0; j != 12; ++j )
          {
            v22 = *(_BYTE *)(j + v18 + 14);
            v23 = v31[j];
            v20 |= v23 ^ v22;
          }
          if ( v20 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids);
            v11 = -2146893041;
          }
          else if ( a4 )
          {
            *a4 = v28;
          }
        }
      }
    }
    goto LABEL_50;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v14 = 32;
    goto LABEL_25;
  }
LABEL_50:
  if ( v25 && v26 )
    (*(void (__fastcall **)(__int64 *))(v26 + 40))(&v25);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180034194  push    rbp
0x180034196  push    rbx
0x180034197  push    rsi
0x180034198  push    rdi
0x180034199  push    r14
0x18003419b  lea     rbp, [rsp-37h]
0x1800341a0  sub     rsp, 0D0h
0x1800341a7  mov     rax, cs:__security_cookie
0x1800341ae  xor     rax, rsp
0x1800341b1  mov     [rbp+57h+var_30], rax
0x1800341b5  mov     rsi, rdx
0x1800341b8  mov     r10d, r8d
0x1800341bb  xor     edx, edx
0x1800341bd  mov     [rbp+57h+var_98], 0
0x1800341c5  mov     [rbp+57h+var_A0], rdx
0x1800341c9  xor     r8d, r8d
0x1800341cc  mov     [rbp+57h+var_88], rdx
0x1800341d0  mov     r14, r9
0x1800341d3  mov     [rbp+57h+var_90], edx
0x1800341d6  mov     rdi, rcx
0x1800341d9  mov     [rbp+57h+var_8C], edx
0x1800341dc  mov     [rbp+57h+var_80], rdx
0x1800341e0  cmp     r8d, [rsi+4]
0x1800341e4  jnb     short loc_180034250
0x1800341e6  mov     r9d, r8d
0x1800341e9  shl     r9, 4
0x1800341ed  add     r9, [rsi+8]
0x1800341f1  mov     eax, [r9+4]
0x1800341f5  test    eax, eax
0x1800341f7  jns     short loc_1800341FF
0x1800341f9  bt      eax, 1Ch
0x1800341fd  jb      short loc_180034210
0x1800341ff  and     eax, 0FFFFFFFh
0x180034204  cmp     eax, 2
0x180034207  cmovz   rdx, r9
0x18003420b  inc     r8d
0x18003420e  jmp     short loc_1800341E0
0x180034210  mov     ebx, 80090308h
0x180034215  mov     rcx, cs:WPP_GLOBAL_Control
0x18003421c  lea     rax, WPP_GLOBAL_Control
0x180034223  cmp     rcx, rax
0x180034226  jz      loc_180034511
0x18003422c  test    byte ptr [rcx+1Ch], 1
0x180034230  jz      loc_180034511
0x180034236  mov     rcx, [rcx+10h]
0x18003423a  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180034241  mov     edx, 1Ch
0x180034246  call    WPP_SF_
0x18003424b  jmp     loc_1800344F4
0x180034250  test    rdx, rdx
0x180034253  jnz     short loc_18003429C
0x180034255  mov     rcx, cs:WPP_GLOBAL_Control
0x18003425c  lea     rax, WPP_GLOBAL_Control
0x180034263  cmp     rcx, rax
0x180034266  jz      short loc_180034292
0x180034268  test    byte ptr [rcx+1Ch], 1
0x18003426c  jz      short loc_180034292
0x18003426e  mov     rcx, [rcx+10h]
0x180034272  lea     r9, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x180034279  mov     edx, 1Dh
0x18003427e  mov     dword ptr [rsp+0F0h+var_D0], 32Dh
0x180034286  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x18003428d  call    WPP_SF_sd
0x180034292  mov     ebx, 0C000000Dh
0x180034297  jmp     loc_1800344F4
0x18003429c  mov     r9d, [rcx+54h]
0x1800342a0  test    r9d, 1000Ch
0x1800342a7  jnz     short loc_1800342F5
0x1800342a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800342b0  lea     rax, WPP_GLOBAL_Control
0x1800342b7  cmp     rcx, rax
0x1800342ba  jz      short loc_1800342EB
0x1800342bc  test    byte ptr [rcx+1Ch], 1
0x1800342c0  jz      short loc_1800342EB
0x1800342c2  mov     rcx, [rcx+10h]
0x1800342c6  lea     rax, aOnecoreDsSecur; "onecore\\ds\\security\\protocols\\pku2u"...
0x1800342cd  mov     edx, 1Eh
0x1800342d2  mov     dword ptr [rsp+0F0h+var_C8], 338h
0x1800342da  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800342e1  mov     [rsp+0F0h+var_D0], rax
0x1800342e6  call    WPP_SF_dsd
0x1800342eb  mov     ebx, 0C00000BBh
0x1800342f0  jmp     loc_1800344F4
0x1800342f5  lea     rax, [rbp+57h+var_80]
0x1800342f9  mov     r9, r10
0x1800342fc  mov     [rsp+0F0h+var_B0], rax
0x180034301  xor     r8d, r8d
0x180034304  mov     [rsp+0F0h+var_B8], 0
0x18003430d  lea     rax, [rbp+57h+var_90]
0x180034311  mov     [rsp+0F0h+var_C0], rax
0x180034316  lea     rax, [rbp+57h+var_8C]
0x18003431a  mov     [rsp+0F0h+var_C8], rax
0x18003431f  lea     rax, [rbp+57h+var_88]
0x180034323  mov     [rsp+0F0h+var_D0], rax
0x180034328  call    WSTVerifySignatureToken
0x18003432d  mov     ebx, eax
0x18003432f  test    eax, eax
0x180034331  jns     short loc_180034371
0x180034333  mov     rcx, cs:WPP_GLOBAL_Control
0x18003433a  lea     rax, WPP_GLOBAL_Control
0x180034341  cmp     rcx, rax
0x180034344  jz      loc_1800344F4
0x18003434a  test    byte ptr [rcx+1Ch], 1
0x18003434e  jz      loc_1800344F4
0x180034354  mov     edx, 1Fh
0x180034359  mov     rcx, [rcx+10h]
0x18003435d  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x180034364  mov     r9d, ebx
0x180034367  call    WPP_SF_d
0x18003436c  jmp     loc_1800344F4
0x180034371  mov     ecx, [rbp+57h+var_90]
0x180034374  lea     rdx, [rbp+57h+var_98]
0x180034378  call    cs:__imp_CDLocateCheckSum
0x18003437e  mov     ebx, eax
0x180034380  test    eax, eax
0x180034382  jns     short loc_1800343AC
0x180034384  mov     rcx, cs:WPP_GLOBAL_Control
0x18003438b  lea     rax, WPP_GLOBAL_Control
0x180034392  cmp     rcx, rax
0x180034395  jz      loc_1800344F4
0x18003439b  test    byte ptr [rcx+1Ch], 1
0x18003439f  jz      loc_1800344F4
0x1800343a5  mov     edx, 20h ; ' '
0x1800343aa  jmp     short loc_180034359
0x1800343ac  mov     eax, [rdi+50h]
0x1800343af  lea     r9, [rbp+57h+var_A0]
0x1800343b3  mov     edx, [rdi+30h]
0x1800343b6  and     al, 4
0x1800343b8  mov     rcx, [rdi+38h]
0x1800343bc  neg     al
0x1800343be  mov     rax, [rbp+57h+var_98]
0x1800343c2  sbb     r8d, r8d
0x1800343c5  and     r8d, 2
0x1800343c9  add     r8d, 17h
0x1800343cd  mov     rax, [rax+30h]
0x1800343d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800343d6  mov     ebx, eax
0x1800343d8  test    eax, eax
0x1800343da  js      loc_1800344F4
0x1800343e0  xor     edi, edi
0x1800343e2  cmp     edi, [rsi+4]
0x1800343e5  jnb     short loc_180034432
0x1800343e7  mov     rcx, [rsi+8]
0x1800343eb  mov     r8d, edi
0x1800343ee  add     r8, r8
0x1800343f1  mov     edx, [rcx+r8*8+4]
0x1800343f6  mov     eax, edx
0x1800343f8  and     eax, 0FFFFFFFh
0x1800343fd  cmp     eax, 2
0x180034400  jz      short loc_18003442E
0x180034402  test    edx, edx
0x180034404  js      short loc_18003442E
0x180034406  mov     edx, [rcx+r8*8]
0x18003440a  test    edx, edx
0x18003440c  jz      short loc_18003442E
0x18003440e  mov     rax, [rbp+57h+var_98]
0x180034412  mov     r8, [rcx+r8*8+8]
0x180034417  mov     rcx, [rbp+57h+var_A0]
0x18003441b  mov     rax, [rax+18h]
0x18003441f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034424  mov     ebx, eax
0x180034426  test    eax, eax
0x180034428  js      loc_1800344F4
0x18003442e  inc     edi
0x180034430  jmp     short loc_1800343E2
0x180034432  mov     rax, [rbp+57h+var_98]
0x180034436  mov     edx, 10h
0x18003443b  mov     rdi, [rbp+57h+var_88]
0x18003443f  mov     rcx, [rbp+57h+var_A0]
0x180034443  mov     rax, [rax+18h]
0x180034447  lea     r8, [rdi-2]
0x18003444b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034450  mov     ebx, eax
0x180034452  test    eax, eax
0x180034454  js      loc_1800344F4
0x18003445a  mov     rax, [rbp+57h+var_98]
0x18003445e  lea     rdx, [rbp+57h+var_70]
0x180034462  mov     rcx, [rbp+57h+var_A0]
0x180034466  mov     rax, [rax+20h]
0x18003446a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003446f  mov     ebx, eax
0x180034471  test    eax, eax
0x180034473  js      short loc_1800344F4
0x180034475  mov     rax, [rbp+57h+var_98]
0x180034479  lea     rcx, [rbp+57h+var_A0]
0x18003447d  mov     rax, [rax+28h]
0x180034481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034486  mov     [rbp+57h+var_A0], 0
0x18003448e  mov     ebx, eax
0x180034490  test    eax, eax
0x180034492  js      short loc_180034511
0x180034494  xor     r8b, r8b
0x180034497  xor     edx, edx
0x180034499  mov     cl, [rdx+rdi+0Eh]
0x18003449d  mov     al, [rbp+rdx+57h+var_70]
0x1800344a1  inc     rdx
0x1800344a4  xor     cl, al
0x1800344a6  or      r8b, cl
0x1800344a9  cmp     rdx, 0Ch
0x1800344ad  jnz     short loc_180034499
0x1800344af  test    r8b, r8b
0x1800344b2  jnz     short loc_1800344C1
0x1800344b4  test    r14, r14
0x1800344b7  jz      short loc_1800344F4
0x1800344b9  mov     eax, [rbp+57h+var_8C]
0x1800344bc  mov     [r14], eax
0x1800344bf  jmp     short loc_1800344F4
0x1800344c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800344c8  lea     rax, WPP_GLOBAL_Control
0x1800344cf  cmp     rcx, rax
0x1800344d2  jz      short loc_1800344EF
0x1800344d4  test    byte ptr [rcx+1Ch], 1
0x1800344d8  jz      short loc_1800344EF
0x1800344da  mov     rcx, [rcx+10h]
0x1800344de  lea     r8, WPP_a44cb69e6a793afaaf72d5f0469b6394_Traceguids
0x1800344e5  mov     edx, 21h ; '!'
0x1800344ea  call    WPP_SF_
0x1800344ef  mov     ebx, 8009030Fh
0x1800344f4  cmp     [rbp+57h+var_A0], 0
0x1800344f9  jz      short loc_180034511
0x1800344fb  mov     rax, [rbp+57h+var_98]
0x1800344ff  test    rax, rax
0x180034502  jz      short loc_180034511
0x180034504  mov     rax, [rax+28h]
0x180034508  lea     rcx, [rbp+57h+var_A0]
0x18003450c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034511  mov     eax, ebx
0x180034513  mov     rcx, [rbp+57h+var_30]
0x180034517  xor     rcx, rsp; StackCookie
0x18003451a  call    __security_check_cookie
0x18003451f  add     rsp, 0D0h
0x180034526  pop     r14
0x180034528  pop     rdi
0x180034529  pop     rsi
0x18003452a  pop     rbx
0x18003452b  pop     rbp
0x18003452c  retn
```
