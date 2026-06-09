# DsIGetDcName(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_GUID *,ushort const *,ulong,ulong,void *,ulong,ushort *,ushort *,_GUID *,ushort *,ushort *,_DOMAIN_CONTROLLER_INFOW * *)

- ea: `0x18007e3bc`
- end: `0x18007e8b5`
- name: `?DsIGetDcName@@YAKPEBG0K00PEAU_GUID@@0KKPEAXKPEAG3133PEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z`
- size: `1273`
- prototype: `unsigned int(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int, unsigned __int16 *, unsigned __int16 *, struct _GUID *, unsigned __int16 *, unsigned __int16 *, struct _DOMAIN_CONTROLLER_INFOW **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800046b0`
- `0x18003b4b4`
- `0x18003b6c4`

## callees

- `0x180007518`
- `0x18001906c`
- `0x18007e3bc`
- `0x18007ea48`
- `0x18008919c`
- `0x1800892fc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007e694`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007e6b6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007e694`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18007e6b6`
- `netutils!NetpwNameCompare` at `0x18007e58d`
- `netutils!NetpwNameCompare` at `0x18007e5f0`
- `netutils!NetpwNameCompare` at `0x18007e58d`
- `netutils!NetpwNameCompare` at `0x18007e5f0`
- `netutils!NetpIsDomainNameValid` at `0x18007e555`
- `netutils!NetpIsDomainNameValid` at `0x18007e555`

## pseudocode

```c
__int64 __fastcall DsIGetDcName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        wchar_t *a4,
        LPCWCH a5,
        struct _GUID *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        unsigned int a9,
        void *a10,
        unsigned int a11,
        unsigned __int16 *a12,
        unsigned __int16 *a13,
        struct _GUID *a14,
        unsigned __int16 *Str,
        unsigned __int16 *a16,
        struct _DOMAIN_CONTROLLER_INFOW **a17)
{
  LPVOID *v17; // r11
  unsigned int v19; // r12d
  const unsigned __int16 *v20; // r13
  unsigned int v21; // ecx
  signed int v22; // ebp
  WCHAR *SourceString; // r15
  const wchar_t *lpWideCharStr; // rsi
  unsigned int v25; // edi
  unsigned int v26; // ebx
  char v27; // al
  const unsigned __int16 *hMem; // r9
  wchar_t *v29; // rax
  wchar_t *v30; // rbp
  _WORD *v31; // r14
  struct _GUID *Buf1; // r8
  int v34; // edx
  int v35; // ecx
  int v36; // edx
  int v37; // ecx
  unsigned int v38; // edx
  int v39; // [rsp+90h] [rbp-48h]

  v17 = (LPVOID *)a17;
  v19 = a3;
  v20 = a2;
  *a17 = 0;
  if ( (a8 & 0x30000) == 196608 || (a8 & 0xC0000000) == -1073741824 )
    return 1004;
  v21 = 0;
  v22 = a8 | 0x200;
  v39 = 0;
  if ( (a8 & 0x40000000) == 0 )
    v22 = a8;
  if ( a4 && *a4 )
  {
    SourceString = 0;
    lpWideCharStr = 0;
    if ( (v22 & 0x10000) != 0 )
    {
      v25 = a9;
    }
    else
    {
      v25 = a9;
      if ( (unsigned int)NetpDcValidDnsDomain(a4) )
      {
        v39 = 1;
        lpWideCharStr = a4;
        if ( (a9 & 0x40) == 0 && a13 && (unsigned int)NlEqualDnsName(a13, a4) )
        {
          if ( a12 && (unsigned int)NlEqualDnsName(a13, a12) )
            SourceString = a12;
          v25 = a9 | 0x1001;
          v26 = v22 | (((v22 >> 31) & 0xC0000000) + 1073872896);
          goto LABEL_24;
        }
        if ( Str && (unsigned int)NlEqualDnsName(Str, a4) )
        {
          if ( a16 && (unsigned int)NlEqualDnsName(Str, a16) )
            SourceString = a16;
          v25 = a9 | 0x1000;
          v26 = v22 | 0x20000;
          if ( v22 >= 0 )
            v26 = v22 | 0x40020000;
LABEL_24:
          if ( (v26 & 0x20000) == 0 && (unsigned int)NetpIsDomainNameValid(a4) )
          {
            ++v39;
            SourceString = a4;
            if ( (v25 & 0x40) == 0 && a12 && !(unsigned int)NetpwNameCompare(a4, a12, 6) )
            {
              lpWideCharStr = a13;
              v25 |= 0x1001u;
              v27 = 1;
              if ( (v26 & 0x40000000) != 0 )
                v26 |= 0x10000u;
              else
                v26 |= 0x80010000;
LABEL_42:
              if ( !lpWideCharStr || !v27 )
              {
LABEL_58:
                if ( !SourceString && !lpWideCharStr )
                  return 1212;
                v20 = a2;
                v19 = a3;
                v17 = (LPVOID *)a17;
                hMem = a5;
                v21 = v39;
                goto LABEL_62;
              }
LABEL_44:
              if ( (v25 & 0x1000) == 0 )
              {
                v29 = wcsstr(lpWideCharStr, L".");
                v30 = v29;
                if ( !v29 || (v31 = v29 + 1, !wcsstr(v29 + 1, L".")) && (v30 == lpWideCharStr || !*v31) )
                {
                  v25 |= 0x20000u;
                  if ( !dword_1800F8268 )
                  {
                    if ( dword_1800F826C )
                    {
                      v25 |= 0x10000u;
                      NlPrintRoutine(
                        2u,
                        L"DsIGetDcName: DNS suffix search list allowed but single label DNS disallowed for name %ws\n",
                        lpWideCharStr);
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          143,
                          &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                          lpWideCharStr);
                    }
                    else
                    {
                      NlPrintRoutine(2u, L"DsIGetDcName: Ignore single label DNS domain name %ws\n", lpWideCharStr);
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          144,
                          &WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids,
                          lpWideCharStr);
                      lpWideCharStr = 0;
                    }
                  }
                }
              }
              goto LABEL_58;
            }
            if ( Str && a16 && !(unsigned int)NetpwNameCompare(a4, a16, 6) )
            {
              v25 |= 0x1000u;
              v26 |= 0x10000u;
              lpWideCharStr = Str;
              if ( (v26 & 0x40000000) == 0 )
                v26 |= 0x80000000;
              goto LABEL_44;
            }
          }
          v27 = 1;
          goto LABEL_42;
        }
      }
    }
    v26 = v22;
    goto LABEL_24;
  }
  if ( (v22 & 0x40) == 0 || (hMem = a5) == 0 )
  {
    SourceString = a12;
    v27 = 0;
    v26 = v22;
    lpWideCharStr = a13;
    v25 = a9 | 0x1001;
    goto LABEL_42;
  }
  SourceString = 0;
  v26 = v22;
  v25 = a9;
  lpWideCharStr = a5;
LABEL_62:
  Buf1 = a6;
  if ( (v25 & 1) != 0 && !a6 )
    Buf1 = a14;
  if ( v21 > 1 )
    v25 |= 2u;
  v34 = (v19 >> 5) & 8 | 0x10;
  if ( (v19 & 0x200) == 0 )
    v34 = (v19 >> 5) & 8;
  v35 = v34 | 0x40;
  if ( (v19 & 0x800) == 0 )
    v35 = v34;
  v36 = v35 | 0x80;
  if ( (v19 & 0x1000) == 0 )
    v36 = v35;
  v37 = v36 | 0x100;
  if ( (v19 & 0x2000) == 0 )
    v37 = v36;
  v38 = v37 | 0x100000;
  if ( (v19 & 0x4000000) == 0 )
    v38 = v37;
  return NetpDcGetName(
           a10,
           a1,
           0,
           v20,
           v38,
           SourceString,
           lpWideCharStr,
           (unsigned __int64)hMem,
           0,
           Buf1,
           a7,
           v26,
           v25,
           a11,
           2u,
           v17,
           0);
}

```

## disassembly

```asm
0x18007e3bc  mov     rax, rsp
0x18007e3bf  mov     [rax+20h], rbx
0x18007e3c3  mov     [rax+18h], r8d
0x18007e3c7  mov     [rax+10h], rdx
0x18007e3cb  mov     [rax+8], rcx
0x18007e3cf  push    rbp
0x18007e3d0  push    rsi
0x18007e3d1  push    rdi
0x18007e3d2  push    r12
0x18007e3d4  push    r13
0x18007e3d6  push    r14
0x18007e3d8  push    r15
0x18007e3da  sub     rsp, 0A0h
0x18007e3e1  mov     r11, [rsp+0D8h+arg_80]
0x18007e3e9  xor     edi, edi
0x18007e3eb  mov     ecx, 30000h
0x18007e3f0  mov     r14, r9
0x18007e3f3  mov     r9d, [rsp+0D8h+arg_38]
0x18007e3fb  mov     r12d, r8d
0x18007e3fe  mov     eax, r9d
0x18007e401  mov     r13, rdx
0x18007e404  and     eax, ecx
0x18007e406  mov     [r11], rdi
0x18007e409  cmp     eax, ecx
0x18007e40b  mov     ecx, 0C0000000h
0x18007e410  mov     eax, r9d
0x18007e413  setnz   r10b
0x18007e417  and     eax, ecx
0x18007e419  cmp     eax, ecx
0x18007e41b  setnz   al
0x18007e41e  test    al, r10b
0x18007e421  jz      loc_18007E894
0x18007e427  mov     ebp, r9d
0x18007e42a  mov     ecx, edi
0x18007e42c  bts     ebp, 9
0x18007e430  mov     [rsp+0D8h+var_48], ecx
0x18007e437  bt      r9d, 1Eh
0x18007e43c  cmovnb  ebp, r9d
0x18007e440  test    r14, r14
0x18007e443  jz      loc_18007E617
0x18007e449  cmp     [r14], di
0x18007e44d  jz      loc_18007E617
0x18007e453  mov     rbx, [rsp+0D8h+arg_78]
0x18007e45b  mov     r15d, edi
0x18007e45e  mov     r12, [rsp+0D8h+Str]
0x18007e466  mov     esi, edi
0x18007e468  mov     r13, [rsp+0D8h+arg_58]
0x18007e470  mov     byte ptr [rsp+0D8h+arg_38], 1
0x18007e478  bt      ebp, 10h
0x18007e47c  jb      loc_18007E53F
0x18007e482  mov     rcx, r14; unsigned __int16 *
0x18007e485  call    ?NetpDcValidDnsDomain@@YAHPEBG@Z; NetpDcValidDnsDomain(ushort const *)
0x18007e48a  mov     edi, [rsp+0D8h+arg_40]
0x18007e491  test    eax, eax
0x18007e493  jz      loc_18007E546
0x18007e499  mov     [rsp+0D8h+var_48], 1
0x18007e4a4  mov     rsi, r14
0x18007e4a7  test    dil, 40h
0x18007e4ab  jnz     short loc_18007E501
0x18007e4ad  cmp     [rsp+0D8h+arg_60], r15
0x18007e4b5  jz      short loc_18007E501
0x18007e4b7  mov     rcx, [rsp+0D8h+arg_60]; unsigned __int16 *
0x18007e4bf  mov     rdx, r14; unsigned __int16 *
0x18007e4c2  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007e4c7  test    eax, eax
0x18007e4c9  jz      short loc_18007E501
0x18007e4cb  test    r13, r13
0x18007e4ce  jz      short loc_18007E4E6
0x18007e4d0  mov     rcx, [rsp+0D8h+arg_60]; unsigned __int16 *
0x18007e4d8  mov     rdx, r13; unsigned __int16 *
0x18007e4db  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007e4e0  test    eax, eax
0x18007e4e2  cmovnz  r15, r13
0x18007e4e6  mov     ebx, ebp
0x18007e4e8  or      edi, 1001h
0x18007e4ee  sar     ebx, 1Fh
0x18007e4f1  and     ebx, 0C0000000h
0x18007e4f7  add     ebx, 40020000h
0x18007e4fd  or      ebx, ebp
0x18007e4ff  jmp     short loc_18007E548
0x18007e501  test    r12, r12
0x18007e504  jz      short loc_18007E546
0x18007e506  mov     rdx, r14; unsigned __int16 *
0x18007e509  mov     rcx, r12; unsigned __int16 *
0x18007e50c  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007e511  test    eax, eax
0x18007e513  jz      short loc_18007E546
0x18007e515  test    rbx, rbx
0x18007e518  jz      short loc_18007E52B
0x18007e51a  mov     rdx, rbx; unsigned __int16 *
0x18007e51d  mov     rcx, r12; unsigned __int16 *
0x18007e520  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x18007e525  test    eax, eax
0x18007e527  cmovnz  r15, rbx
0x18007e52b  bts     edi, 0Ch
0x18007e52f  mov     ebx, ebp
0x18007e531  or      ebx, 20000h
0x18007e537  jl      short loc_18007E548
0x18007e539  bts     ebx, 1Eh
0x18007e53d  jmp     short loc_18007E548
0x18007e53f  mov     edi, [rsp+0D8h+arg_40]
0x18007e546  mov     ebx, ebp
0x18007e548  bt      ebx, 11h
0x18007e54c  jb      loc_18007E666
0x18007e552  mov     rcx, r14
0x18007e555  call    cs:__imp_NetpIsDomainNameValid
0x18007e55c  nop     dword ptr [rax+rax+00h]
0x18007e561  xor     ebp, ebp
0x18007e563  test    eax, eax
0x18007e565  jz      loc_18007E668
0x18007e56b  inc     [rsp+0D8h+var_48]
0x18007e572  mov     r15, r14
0x18007e575  test    dil, 40h
0x18007e579  jnz     short loc_18007E5CC
0x18007e57b  test    r13, r13
0x18007e57e  jz      short loc_18007E5CC
0x18007e580  xor     r9d, r9d
0x18007e583  lea     r8d, [rbp+6]
0x18007e587  mov     rdx, r13
0x18007e58a  mov     rcx, r14
0x18007e58d  call    cs:__imp_NetpwNameCompare
0x18007e594  nop     dword ptr [rax+rax+00h]
0x18007e599  test    eax, eax
0x18007e59b  jnz     short loc_18007E5CC
0x18007e59d  mov     rsi, [rsp+0D8h+arg_60]
0x18007e5a5  or      edi, 1001h
0x18007e5ab  mov     al, byte ptr [rsp+0D8h+arg_38]
0x18007e5b2  bt      ebx, 1Eh
0x18007e5b6  jb      short loc_18007E5C3
0x18007e5b8  or      ebx, 80010000h
0x18007e5be  jmp     loc_18007E66F
0x18007e5c3  bts     ebx, 10h
0x18007e5c7  jmp     loc_18007E66F
0x18007e5cc  test    r12, r12
0x18007e5cf  jz      loc_18007E668
0x18007e5d5  mov     rdx, [rsp+0D8h+arg_78]
0x18007e5dd  test    rdx, rdx
0x18007e5e0  jz      loc_18007E668
0x18007e5e6  xor     r9d, r9d
0x18007e5e9  mov     rcx, r14
0x18007e5ec  lea     r8d, [r9+6]
0x18007e5f0  call    cs:__imp_NetpwNameCompare
0x18007e5f7  nop     dword ptr [rax+rax+00h]
0x18007e5fc  test    eax, eax
0x18007e5fe  jnz     short loc_18007E668
0x18007e600  bts     edi, 0Ch
0x18007e604  bts     ebx, 10h
0x18007e608  mov     rsi, r12
0x18007e60b  bt      ebx, 1Eh
0x18007e60f  jb      short loc_18007E680
0x18007e611  bts     ebx, 1Fh
0x18007e615  jmp     short loc_18007E680
0x18007e617  test    bpl, 40h
0x18007e61b  jz      short loc_18007E640
0x18007e61d  mov     r9, [rsp+0D8h+arg_20]
0x18007e625  test    r9, r9
0x18007e628  jz      short loc_18007E640
0x18007e62a  mov     r15, rdi
0x18007e62d  mov     ebx, ebp
0x18007e62f  mov     edi, [rsp+0D8h+arg_40]
0x18007e636  xor     ebp, ebp
0x18007e638  mov     rsi, r9
0x18007e63b  jmp     loc_18007E7B6
0x18007e640  mov     r15, [rsp+0D8h+arg_58]
0x18007e648  mov     al, dil
0x18007e64b  mov     edi, [rsp+0D8h+arg_40]
0x18007e652  mov     ebx, ebp
0x18007e654  mov     rsi, [rsp+0D8h+arg_60]
0x18007e65c  or      edi, 1001h
0x18007e662  xor     ebp, ebp
0x18007e664  jmp     short loc_18007E66F
0x18007e666  xor     ebp, ebp
0x18007e668  mov     al, byte ptr [rsp+0D8h+arg_38]
0x18007e66f  test    rsi, rsi
0x18007e672  jz      loc_18007E77B
0x18007e678  test    al, al
0x18007e67a  jz      loc_18007E77B
0x18007e680  bt      edi, 0Ch
0x18007e684  jb      loc_18007E77B
0x18007e68a  lea     rdx, asc_1800A272C; "."
0x18007e691  mov     rcx, rsi; Str
0x18007e694  call    cs:__imp_wcsstr
0x18007e69b  nop     dword ptr [rax+rax+00h]
0x18007e6a0  mov     rbp, rax
0x18007e6a3  test    rax, rax
0x18007e6a6  jz      short loc_18007E6DE
0x18007e6a8  lea     r14, [rax+2]
0x18007e6ac  mov     rcx, r14; Str
0x18007e6af  lea     rdx, asc_1800A272C; "."
0x18007e6b6  call    cs:__imp_wcsstr
0x18007e6bd  nop     dword ptr [rax+rax+00h]
0x18007e6c2  test    rax, rax
0x18007e6c5  jnz     loc_18007E779
0x18007e6cb  cmp     rbp, rsi
0x18007e6ce  jz      short loc_18007E6DE
0x18007e6d0  xor     ebp, ebp
0x18007e6d2  cmp     [r14], bp
0x18007e6d6  jnz     loc_18007E77B
0x18007e6dc  jmp     short loc_18007E6E0
0x18007e6de  xor     ebp, ebp
0x18007e6e0  bts     edi, 11h
0x18007e6e4  cmp     cs:dword_1800F8268, ebp
0x18007e6ea  jnz     loc_18007E77B
0x18007e6f0  cmp     cs:dword_1800F826C, ebp
0x18007e6f6  mov     r8, rsi
0x18007e6f9  mov     ecx, 2; unsigned int
0x18007e6fe  jz      short loc_18007E73D
0x18007e700  bts     edi, 10h
0x18007e704  lea     rdx, aDsigetdcnameDn; "DsIGetDcName: DNS suffix search list al"...
0x18007e70b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007e710  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e717  test    byte ptr [rcx+1Ch], 4
0x18007e71b  jz      short loc_18007E77B
0x18007e71d  cmp     byte ptr [rcx+19h], 4
0x18007e721  jb      short loc_18007E77B
0x18007e723  mov     rcx, [rcx+10h]
0x18007e727  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18007e72e  mov     edx, 8Fh
0x18007e733  mov     r9, rsi
0x18007e736  call    WPP_SF_S
0x18007e73b  jmp     short loc_18007E77B
0x18007e73d  lea     rdx, aDsigetdcnameIg; "DsIGetDcName: Ignore single label DNS d"...
0x18007e744  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18007e749  mov     rcx, cs:WPP_GLOBAL_Control
0x18007e750  test    byte ptr [rcx+1Ch], 4
0x18007e754  jz      short loc_18007E774
0x18007e756  cmp     byte ptr [rcx+19h], 4
0x18007e75a  jb      short loc_18007E774
0x18007e75c  mov     rcx, [rcx+10h]
0x18007e760  lea     r8, WPP_13c6b6bed2ee3fe9aa34f445fb686d14_Traceguids
0x18007e767  mov     edx, 90h
0x18007e76c  mov     r9, rsi
0x18007e76f  call    WPP_SF_S
0x18007e774  mov     rsi, rbp
0x18007e777  jmp     short loc_18007E77B
0x18007e779  xor     ebp, ebp
0x18007e77b  test    r15, r15
0x18007e77e  jnz     short loc_18007E78F
0x18007e780  test    rsi, rsi
0x18007e783  jnz     short loc_18007E78F
0x18007e785  mov     eax, 4BCh
0x18007e78a  jmp     loc_18007E899
0x18007e78f  mov     r13, [rsp+0D8h+arg_8]
0x18007e797  mov     r12d, [rsp+0D8h+arg_10]
0x18007e79f  mov     r11, [rsp+0D8h+arg_80]
0x18007e7a7  mov     r9, [rsp+0D8h+arg_20]
0x18007e7af  mov     ecx, [rsp+0D8h+var_48]
0x18007e7b6  mov     r8, [rsp+0D8h+arg_28]
0x18007e7be  test    dil, 1
0x18007e7c2  jz      short loc_18007E7D0
0x18007e7c4  test    r8, r8
0x18007e7c7  cmovz   r8, [rsp+0D8h+arg_68]
0x18007e7d0  cmp     ecx, 1
0x18007e7d3  jbe     short loc_18007E7D8
0x18007e7d5  or      edi, 2
0x18007e7d8  mov     eax, [rsp+0D8h+arg_50]
0x18007e7df  mov     ecx, r12d
0x18007e7e2  shr     ecx, 5
0x18007e7e5  and     ecx, 8
0x18007e7e8  mov     [rsp+0D8h+var_58], rbp; struct _NL_DC_CACHE_ENTRY **
0x18007e7f0  mov     [rsp+0D8h+var_60], r11; struct _DOMAIN_CONTROLLER_INFOW **
0x18007e7f5  mov     edx, ecx
0x18007e7f7  or      edx, 10h
0x18007e7fa  mov     [rsp+0D8h+var_68], 2; unsigned int
0x18007e802  mov     [rsp+0D8h+var_70], eax; unsigned int
0x18007e806  bt      r12d, 9
0x18007e80b  mov     rax, [rsp+0D8h+arg_30]
0x18007e813  cmovnb  edx, ecx
0x18007e816  mov     [rsp+0D8h+var_78], edi; unsigned int
0x18007e81a  mov     ecx, edx
0x18007e81c  mov     [rsp+0D8h+var_80], ebx; unsigned int
0x18007e820  or      ecx, 40h
0x18007e823  mov     [rsp+0D8h+var_88], rax; unsigned __int16 *
0x18007e828  mov     [rsp+0D8h+Buf1], r8; Buf1
0x18007e82d  bt      r12d, 0Bh
0x18007e832  mov     [rsp+0D8h+var_98], rbp; void *
0x18007e837  cmovnb  ecx, edx
0x18007e83a  mov     [rsp+0D8h+hMem], r9; hMem
0x18007e83f  mov     edx, ecx
0x18007e841  mov     [rsp+0D8h+lpWideCharStr], rsi; lpWideCharStr
0x18007e846  bts     edx, 7
0x18007e84a  mov     [rsp+0D8h+SourceString], r15; SourceString
0x18007e84f  bt      r12d, 0Ch
0x18007e854  mov     r9, r13; unsigned __int16 *
0x18007e857  cmovnb  edx, ecx
0x18007e85a  mov     ecx, edx
0x18007e85c  bts     ecx, 8
0x18007e860  bt      r12d, 0Dh
0x18007e865  cmovnb  ecx, edx
0x18007e868  mov     edx, ecx
0x18007e86a  bts     edx, 14h
0x18007e86e  bt      r12d, 1Ah
0x18007e873  cmovnb  edx, ecx
0x18007e876  mov     rcx, [rsp+0D8h+arg_48]; void *
0x18007e87e  mov     [rsp+0D8h+var_B8], edx; unsigned int
0x18007e882  xor     r8d, r8d; unsigned __int16 *
0x18007e885  mov     rdx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x18007e88d  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x18007e892  jmp     short loc_18007E899
0x18007e894  mov     eax, 3ECh
  ... truncated ...
```
