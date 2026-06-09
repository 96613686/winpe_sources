# DsIGetDcName(ushort const *,ushort const *,ulong,ushort const *,ushort const *,_GUID *,ushort const *,ulong,ulong,void *,ulong,ushort *,ushort *,_GUID *,ushort *,ushort *,_DOMAIN_CONTROLLER_INFOW * *)

- ea: `0x1800788c0`
- end: `0x180078d96`
- name: `?DsIGetDcName@@YAKPEBG0K00PEAU_GUID@@0KKPEAXKPEAG3133PEAPEAU_DOMAIN_CONTROLLER_INFOW@@@Z`
- size: `1238`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, LPCWCH, struct _GUID *, const unsigned __int16 *, unsigned int, unsigned int, void *, unsigned int, unsigned __int16 *, unsigned __int16 *, struct _GUID *, unsigned __int16 *Str, unsigned __int16 *, struct _DOMAIN_CONTROLLER_INFOW **)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004420`
- `0x180039204`
- `0x1800393f4`

## callees

- `0x180007278`
- `0x18001852c`
- `0x1800788c0`
- `0x180078f00`
- `0x180083018`
- `0x18008315c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180078b82`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180078b9e`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180078b82`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180078b9e`
- `netutils!NetpwNameCompare` at `0x180078a8b`
- `netutils!NetpwNameCompare` at `0x180078ae4`
- `netutils!NetpwNameCompare` at `0x180078a8b`
- `netutils!NetpwNameCompare` at `0x180078ae4`
- `netutils!NetpIsDomainNameValid` at `0x180078a59`
- `netutils!NetpIsDomainNameValid` at `0x180078a59`

## pseudocode

```c
unsigned int __fastcall DsIGetDcName(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        LPCWCH a5,
        struct _GUID *a6,
        const unsigned __int16 *a7,
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
  struct _DOMAIN_CONTROLLER_INFOW **v17; // r11
  unsigned int v19; // r12d
  const unsigned __int16 *v20; // r13
  unsigned int v21; // ecx
  signed int v22; // ebp
  const WCHAR *SourceString; // r15
  const wchar_t *lpWideCharStr; // rsi
  unsigned int v25; // edi
  unsigned int v26; // ebx
  char v27; // al
  unsigned __int16 *hMem; // r9
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

  v17 = a17;
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
                v17 = a17;
                hMem = (unsigned __int16 *)a5;
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
                  if ( !dword_1800F1268 )
                  {
                    if ( dword_1800F126C )
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
                          &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
                          lpWideCharStr);
                    }
                    else
                    {
                      NlPrintRoutine(2u, L"DsIGetDcName: Ignore single label DNS domain name %ws\n", lpWideCharStr);
                      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                        WPP_SF_S(
                          *((_QWORD *)WPP_GLOBAL_Control + 2),
                          144,
                          &WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids,
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
  if ( (v22 & 0x40) == 0 || (hMem = (unsigned __int16 *)a5) == 0 )
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
  return NetpDcGetName(a10, a1, 0, v20, v38, SourceString, lpWideCharStr, hMem, 0, Buf1, a7, v26, v25, a11, 2u, v17, 0);
}

```

## disassembly

```asm
0x1800788c0  mov     rax, rsp
0x1800788c3  mov     [rax+20h], rbx
0x1800788c7  mov     [rax+18h], r8d
0x1800788cb  mov     [rax+10h], rdx
0x1800788cf  mov     [rax+8], rcx
0x1800788d3  push    rbp
0x1800788d4  push    rsi
0x1800788d5  push    rdi
0x1800788d6  push    r12
0x1800788d8  push    r13
0x1800788da  push    r14
0x1800788dc  push    r15
0x1800788de  sub     rsp, 0A0h
0x1800788e5  mov     r11, [rsp+0D8h+arg_80]
0x1800788ed  xor     edi, edi
0x1800788ef  mov     ecx, 30000h
0x1800788f4  mov     r14, r9
0x1800788f7  mov     r9d, [rsp+0D8h+arg_38]
0x1800788ff  mov     r12d, r8d
0x180078902  mov     eax, r9d
0x180078905  mov     r13, rdx
0x180078908  and     eax, ecx
0x18007890a  mov     [r11], rdi
0x18007890d  cmp     eax, ecx
0x18007890f  mov     ecx, 0C0000000h
0x180078914  mov     eax, r9d
0x180078917  setnz   r10b
0x18007891b  and     eax, ecx
0x18007891d  cmp     eax, ecx
0x18007891f  setnz   al
0x180078922  test    al, r10b
0x180078925  jz      loc_180078D76
0x18007892b  mov     ebp, r9d
0x18007892e  mov     ecx, edi
0x180078930  bts     ebp, 9
0x180078934  mov     [rsp+0D8h+var_48], ecx
0x18007893b  bt      r9d, 1Eh
0x180078940  cmovnb  ebp, r9d
0x180078944  test    r14, r14
0x180078947  jz      loc_180078B05
0x18007894d  cmp     [r14], di
0x180078951  jz      loc_180078B05
0x180078957  mov     rbx, [rsp+0D8h+arg_78]
0x18007895f  mov     r15d, edi
0x180078962  mov     r12, [rsp+0D8h+Str]
0x18007896a  mov     esi, edi
0x18007896c  mov     r13, [rsp+0D8h+arg_58]
0x180078974  mov     byte ptr [rsp+0D8h+arg_38], 1
0x18007897c  bt      ebp, 10h
0x180078980  jb      loc_180078A43
0x180078986  mov     rcx, r14; unsigned __int16 *
0x180078989  call    ?NetpDcValidDnsDomain@@YAHPEBG@Z; NetpDcValidDnsDomain(ushort const *)
0x18007898e  mov     edi, [rsp+0D8h+arg_40]
0x180078995  test    eax, eax
0x180078997  jz      loc_180078A4A
0x18007899d  mov     [rsp+0D8h+var_48], 1
0x1800789a8  mov     rsi, r14
0x1800789ab  test    dil, 40h
0x1800789af  jnz     short loc_180078A05
0x1800789b1  cmp     [rsp+0D8h+arg_60], r15
0x1800789b9  jz      short loc_180078A05
0x1800789bb  mov     rcx, [rsp+0D8h+arg_60]; unsigned __int16 *
0x1800789c3  mov     rdx, r14; unsigned __int16 *
0x1800789c6  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800789cb  test    eax, eax
0x1800789cd  jz      short loc_180078A05
0x1800789cf  test    r13, r13
0x1800789d2  jz      short loc_1800789EA
0x1800789d4  mov     rcx, [rsp+0D8h+arg_60]; unsigned __int16 *
0x1800789dc  mov     rdx, r13; unsigned __int16 *
0x1800789df  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x1800789e4  test    eax, eax
0x1800789e6  cmovnz  r15, r13
0x1800789ea  mov     ebx, ebp
0x1800789ec  or      edi, 1001h
0x1800789f2  sar     ebx, 1Fh
0x1800789f5  and     ebx, 0C0000000h
0x1800789fb  add     ebx, 40020000h
0x180078a01  or      ebx, ebp
0x180078a03  jmp     short loc_180078A4C
0x180078a05  test    r12, r12
0x180078a08  jz      short loc_180078A4A
0x180078a0a  mov     rdx, r14; unsigned __int16 *
0x180078a0d  mov     rcx, r12; unsigned __int16 *
0x180078a10  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180078a15  test    eax, eax
0x180078a17  jz      short loc_180078A4A
0x180078a19  test    rbx, rbx
0x180078a1c  jz      short loc_180078A2F
0x180078a1e  mov     rdx, rbx; unsigned __int16 *
0x180078a21  mov     rcx, r12; unsigned __int16 *
0x180078a24  call    ?NlEqualDnsName@@YAHPEBG0@Z; NlEqualDnsName(ushort const *,ushort const *)
0x180078a29  test    eax, eax
0x180078a2b  cmovnz  r15, rbx
0x180078a2f  bts     edi, 0Ch
0x180078a33  mov     ebx, ebp
0x180078a35  or      ebx, 20000h
0x180078a3b  jl      short loc_180078A4C
0x180078a3d  bts     ebx, 1Eh
0x180078a41  jmp     short loc_180078A4C
0x180078a43  mov     edi, [rsp+0D8h+arg_40]
0x180078a4a  mov     ebx, ebp
0x180078a4c  bt      ebx, 11h
0x180078a50  jb      loc_180078B54
0x180078a56  mov     rcx, r14
0x180078a59  call    cs:__imp_NetpIsDomainNameValid
0x180078a5f  xor     ebp, ebp
0x180078a61  test    eax, eax
0x180078a63  jz      loc_180078B56
0x180078a69  inc     [rsp+0D8h+var_48]
0x180078a70  mov     r15, r14
0x180078a73  test    dil, 40h
0x180078a77  jnz     short loc_180078AC4
0x180078a79  test    r13, r13
0x180078a7c  jz      short loc_180078AC4
0x180078a7e  xor     r9d, r9d
0x180078a81  lea     r8d, [rbp+6]
0x180078a85  mov     rdx, r13
0x180078a88  mov     rcx, r14
0x180078a8b  call    cs:__imp_NetpwNameCompare
0x180078a91  test    eax, eax
0x180078a93  jnz     short loc_180078AC4
0x180078a95  mov     rsi, [rsp+0D8h+arg_60]
0x180078a9d  or      edi, 1001h
0x180078aa3  mov     al, byte ptr [rsp+0D8h+arg_38]
0x180078aaa  bt      ebx, 1Eh
0x180078aae  jb      short loc_180078ABB
0x180078ab0  or      ebx, 80010000h
0x180078ab6  jmp     loc_180078B5D
0x180078abb  bts     ebx, 10h
0x180078abf  jmp     loc_180078B5D
0x180078ac4  test    r12, r12
0x180078ac7  jz      loc_180078B56
0x180078acd  mov     rdx, [rsp+0D8h+arg_78]
0x180078ad5  test    rdx, rdx
0x180078ad8  jz      short loc_180078B56
0x180078ada  xor     r9d, r9d
0x180078add  mov     rcx, r14
0x180078ae0  lea     r8d, [r9+6]
0x180078ae4  call    cs:__imp_NetpwNameCompare
0x180078aea  test    eax, eax
0x180078aec  jnz     short loc_180078B56
0x180078aee  bts     edi, 0Ch
0x180078af2  bts     ebx, 10h
0x180078af6  mov     rsi, r12
0x180078af9  bt      ebx, 1Eh
0x180078afd  jb      short loc_180078B6E
0x180078aff  bts     ebx, 1Fh
0x180078b03  jmp     short loc_180078B6E
0x180078b05  test    bpl, 40h
0x180078b09  jz      short loc_180078B2E
0x180078b0b  mov     r9, [rsp+0D8h+arg_20]
0x180078b13  test    r9, r9
0x180078b16  jz      short loc_180078B2E
0x180078b18  mov     r15, rdi
0x180078b1b  mov     ebx, ebp
0x180078b1d  mov     edi, [rsp+0D8h+arg_40]
0x180078b24  xor     ebp, ebp
0x180078b26  mov     rsi, r9
0x180078b29  jmp     loc_180078C98
0x180078b2e  mov     r15, [rsp+0D8h+arg_58]
0x180078b36  mov     al, dil
0x180078b39  mov     edi, [rsp+0D8h+arg_40]
0x180078b40  mov     ebx, ebp
0x180078b42  mov     rsi, [rsp+0D8h+arg_60]
0x180078b4a  or      edi, 1001h
0x180078b50  xor     ebp, ebp
0x180078b52  jmp     short loc_180078B5D
0x180078b54  xor     ebp, ebp
0x180078b56  mov     al, byte ptr [rsp+0D8h+arg_38]
0x180078b5d  test    rsi, rsi
0x180078b60  jz      loc_180078C5D
0x180078b66  test    al, al
0x180078b68  jz      loc_180078C5D
0x180078b6e  bt      edi, 0Ch
0x180078b72  jb      loc_180078C5D
0x180078b78  lea     rdx, asc_18009B71C; "."
0x180078b7f  mov     rcx, rsi; Str
0x180078b82  call    cs:__imp_wcsstr
0x180078b88  mov     rbp, rax
0x180078b8b  test    rax, rax
0x180078b8e  jz      short loc_180078BC0
0x180078b90  lea     r14, [rax+2]
0x180078b94  mov     rcx, r14; Str
0x180078b97  lea     rdx, asc_18009B71C; "."
0x180078b9e  call    cs:__imp_wcsstr
0x180078ba4  test    rax, rax
0x180078ba7  jnz     loc_180078C5B
0x180078bad  cmp     rbp, rsi
0x180078bb0  jz      short loc_180078BC0
0x180078bb2  xor     ebp, ebp
0x180078bb4  cmp     [r14], bp
0x180078bb8  jnz     loc_180078C5D
0x180078bbe  jmp     short loc_180078BC2
0x180078bc0  xor     ebp, ebp
0x180078bc2  bts     edi, 11h
0x180078bc6  cmp     cs:dword_1800F1268, ebp
0x180078bcc  jnz     loc_180078C5D
0x180078bd2  cmp     cs:dword_1800F126C, ebp
0x180078bd8  mov     r8, rsi
0x180078bdb  mov     ecx, 2; unsigned int
0x180078be0  jz      short loc_180078C1F
0x180078be2  bts     edi, 10h
0x180078be6  lea     rdx, aDsigetdcnameDn; "DsIGetDcName: DNS suffix search list al"...
0x180078bed  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180078bf2  mov     rcx, cs:WPP_GLOBAL_Control
0x180078bf9  test    byte ptr [rcx+1Ch], 4
0x180078bfd  jz      short loc_180078C5D
0x180078bff  cmp     byte ptr [rcx+19h], 4
0x180078c03  jb      short loc_180078C5D
0x180078c05  mov     rcx, [rcx+10h]
0x180078c09  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x180078c10  mov     edx, 8Fh
0x180078c15  mov     r9, rsi
0x180078c18  call    WPP_SF_S
0x180078c1d  jmp     short loc_180078C5D
0x180078c1f  lea     rdx, aDsigetdcnameIg; "DsIGetDcName: Ignore single label DNS d"...
0x180078c26  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180078c2b  mov     rcx, cs:WPP_GLOBAL_Control
0x180078c32  test    byte ptr [rcx+1Ch], 4
0x180078c36  jz      short loc_180078C56
0x180078c38  cmp     byte ptr [rcx+19h], 4
0x180078c3c  jb      short loc_180078C56
0x180078c3e  mov     rcx, [rcx+10h]
0x180078c42  lea     r8, WPP_7b1f09d1eb443831f73a3215d4ae83fb_Traceguids
0x180078c49  mov     edx, 90h
0x180078c4e  mov     r9, rsi
0x180078c51  call    WPP_SF_S
0x180078c56  mov     rsi, rbp
0x180078c59  jmp     short loc_180078C5D
0x180078c5b  xor     ebp, ebp
0x180078c5d  test    r15, r15
0x180078c60  jnz     short loc_180078C71
0x180078c62  test    rsi, rsi
0x180078c65  jnz     short loc_180078C71
0x180078c67  mov     eax, 4BCh
0x180078c6c  jmp     loc_180078D7B
0x180078c71  mov     r13, [rsp+0D8h+arg_8]
0x180078c79  mov     r12d, [rsp+0D8h+arg_10]
0x180078c81  mov     r11, [rsp+0D8h+arg_80]
0x180078c89  mov     r9, [rsp+0D8h+arg_20]
0x180078c91  mov     ecx, [rsp+0D8h+var_48]
0x180078c98  mov     r8, [rsp+0D8h+arg_28]
0x180078ca0  test    dil, 1
0x180078ca4  jz      short loc_180078CB2
0x180078ca6  test    r8, r8
0x180078ca9  cmovz   r8, [rsp+0D8h+arg_68]
0x180078cb2  cmp     ecx, 1
0x180078cb5  jbe     short loc_180078CBA
0x180078cb7  or      edi, 2
0x180078cba  mov     eax, [rsp+0D8h+arg_50]
0x180078cc1  mov     ecx, r12d
0x180078cc4  shr     ecx, 5
0x180078cc7  and     ecx, 8
0x180078cca  mov     [rsp+0D8h+var_58], rbp; struct _NL_DC_CACHE_ENTRY **
0x180078cd2  mov     [rsp+0D8h+var_60], r11; struct _DOMAIN_CONTROLLER_INFOW **
0x180078cd7  mov     edx, ecx
0x180078cd9  or      edx, 10h
0x180078cdc  mov     [rsp+0D8h+var_68], 2; unsigned int
0x180078ce4  mov     [rsp+0D8h+var_70], eax; unsigned int
0x180078ce8  bt      r12d, 9
0x180078ced  mov     rax, [rsp+0D8h+arg_30]
0x180078cf5  cmovnb  edx, ecx
0x180078cf8  mov     [rsp+0D8h+var_78], edi; unsigned int
0x180078cfc  mov     ecx, edx
0x180078cfe  mov     [rsp+0D8h+var_80], ebx; unsigned int
0x180078d02  or      ecx, 40h
0x180078d05  mov     [rsp+0D8h+var_88], rax; unsigned __int16 *
0x180078d0a  mov     [rsp+0D8h+Buf1], r8; Buf1
0x180078d0f  bt      r12d, 0Bh
0x180078d14  mov     [rsp+0D8h+var_98], rbp; void *
0x180078d19  cmovnb  ecx, edx
0x180078d1c  mov     [rsp+0D8h+hMem], r9; hMem
0x180078d21  mov     edx, ecx
0x180078d23  mov     [rsp+0D8h+lpWideCharStr], rsi; lpWideCharStr
0x180078d28  bts     edx, 7
0x180078d2c  mov     [rsp+0D8h+SourceString], r15; SourceString
0x180078d31  bt      r12d, 0Ch
0x180078d36  mov     r9, r13; unsigned __int16 *
0x180078d39  cmovnb  edx, ecx
0x180078d3c  mov     ecx, edx
0x180078d3e  bts     ecx, 8
0x180078d42  bt      r12d, 0Dh
0x180078d47  cmovnb  ecx, edx
0x180078d4a  mov     edx, ecx
0x180078d4c  bts     edx, 14h
0x180078d50  bt      r12d, 1Ah
0x180078d55  cmovnb  edx, ecx
0x180078d58  mov     rcx, [rsp+0D8h+arg_48]; void *
0x180078d60  mov     [rsp+0D8h+var_B8], edx; unsigned int
0x180078d64  xor     r8d, r8d; unsigned __int16 *
0x180078d67  mov     rdx, [rsp+0D8h+arg_0]; unsigned __int16 *
0x180078d6f  call    ?NetpDcGetName@@YAKPEAXPEBG11K1110PEAU_GUID@@1KKKKPEAPEAU_DOMAIN_CONTROLLER_INFOW@@PEAPEAU_NL_DC_CACHE_ENTRY@@@Z; NetpDcGetName(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort const *,ushort const *,void *,_GUID *,ushort const *,ulong,ulong,ulong,ulong,_DOMAIN_CONTROLLER_INFOW * *,_NL_DC_CACHE_ENTRY * *)
0x180078d74  jmp     short loc_180078D7B
0x180078d76  mov     eax, 3ECh
0x180078d7b  mov     rbx, [rsp+0D8h+arg_18]
0x180078d83  add     rsp, 0A0h
0x180078d8a  pop     r15
0x180078d8c  pop     r14
0x180078d8e  pop     r13
  ... truncated ...
```
