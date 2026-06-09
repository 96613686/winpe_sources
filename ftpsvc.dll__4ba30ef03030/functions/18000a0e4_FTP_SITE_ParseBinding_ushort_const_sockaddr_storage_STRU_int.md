# FTP_SITE::ParseBinding(ushort const *,sockaddr_storage *,STRU *,int)

- ea: `0x18000a0e4`
- end: `0x18000a43a`
- name: `?ParseBinding@FTP_SITE@@SAJPEBGPEAUsockaddr_storage@@PEAVSTRU@@H@Z`
- size: `854`
- prototype: `__int64 __fastcall(wchar_t *Str, struct sockaddr_storage *, struct STRU *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a730`
- `0x180045730`

## callees

- `0x18000a0e4`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `msvcrt!wcstoul` at `0x18000a35f`
- `msvcrt!wcstoul` at `0x18000a35f`
- `msvcrt!wcschr` at `0x18000a193`
- `msvcrt!wcschr` at `0x18000a242`
- `msvcrt!wcschr` at `0x18000a193`
- `msvcrt!wcschr` at `0x18000a242`
- `WS2_32!WSAStringToAddressW` at `0x18000a296`
- `WS2_32!WSAStringToAddressW` at `0x18000a2c3`
- `WS2_32!WSAStringToAddressW` at `0x18000a296`
- `WS2_32!WSAStringToAddressW` at `0x18000a2c3`
- `WS2_32!__imp_htons` at `0x18000a373`
- `WS2_32!__imp_htons` at `0x18000a373`
- `WS2_32!__imp_WSAGetLastError` at `0x18000a2ce`
- `WS2_32!__imp_WSAGetLastError` at `0x18000a2ce`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a389`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000a389`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a1dc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a346`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a1dc`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x18000a346`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a14c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a16d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a14c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000a16d`
- `iisutil!PuDbgPrintError` at `0x18000a31c`
- `iisutil!PuDbgPrintError` at `0x18000a3f1`
- `iisutil!PuDbgPrintError` at `0x18000a31c`
- `iisutil!PuDbgPrintError` at `0x18000a3f1`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a3fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a408`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a3fc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000a408`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FTP_SITE::ParseBinding(wchar_t *Str, struct sockaddr *a2, struct STRU *a3, int a4)
{
  wchar_t *v7; // r15
  wchar_t *v8; // rsi
  const wchar_t *v9; // rcx
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  struct STRU *v12; // r14
  signed int v13; // ebx
  wchar_t *v14; // rax
  WCHAR *v15; // r10
  int Error; // eax
  unsigned int v17; // eax
  _WORD *v18; // rcx
  int AddressLength; // [rsp+40h] [rbp-C0h] BYREF
  struct STRU *v21; // [rsp+48h] [rbp-B8h]
  _BYTE v22[32]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *Stra; // [rsp+70h] [rbp-90h]
  int v24; // [rsp+80h] [rbp-80h]
  _BYTE v25[32]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String; // [rsp+A8h] [rbp-58h]
  unsigned __int16 v27[32]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v28[64]; // [rsp+100h] [rbp+0h] BYREF

  v21 = a3;
  v7 = 0;
  v8 = 0;
  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v22, v28, 0x40u);
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v25, v27, 0x20u);
  AddressLength = 128;
  memset_0(a2, 0, 0x80u);
  v9 = Str;
  do
  {
    v10 = v8;
    v11 = wcschr(v9, 0x3Au);
    if ( v11 )
      v8 = v11;
    v9 = v11 + 1;
    if ( !v11 )
    {
      v9 = 0;
      v10 = v7;
    }
    v7 = v10;
  }
  while ( v9 );
  v12 = v21;
  if ( !v10 || !v8 )
    goto LABEL_38;
  v13 = STRU::Copy((STRU *)v22, Str, v10 - Str);
  if ( v13 < 0 )
    goto LABEL_39;
  if ( *Stra == 42 && !Stra[1] )
  {
    *Stra = 0;
    v24 = 0;
LABEL_13:
    memset_0(a2, 0, 0x80u);
    if ( FTP_ASYNC_SOCKET::sm_pConnectExIp6 )
    {
      a2->sa_family = 23;
      *(IN6_ADDR *)&a2->sa_data[6] = in6addr_any;
    }
    else
    {
      a2->sa_family = 2;
    }
LABEL_30:
    v13 = STRU::Copy((STRU *)v25, v7 + 1, ((char *)v8 - (char *)v7 - 2) >> 1);
    if ( v13 < 0 )
      goto LABEL_39;
    v17 = wcstoul(String, 0, 10);
    if ( v17 - 1 <= 0xFFFE )
    {
      *(_WORD *)a2->sa_data = htons(v17);
      if ( !v12 )
      {
LABEL_37:
        v13 = 0;
        goto LABEL_41;
      }
      v13 = STRU::Copy(v12, v8 + 1);
      if ( v13 >= 0 )
      {
        v18 = (_WORD *)*((_QWORD *)v12 + 4);
        if ( *v18 == 42 && !v18[1] )
        {
          *v18 = 0;
          *((_DWORD *)v12 + 12) = 0;
        }
        goto LABEL_37;
      }
      goto LABEL_39;
    }
LABEL_38:
    v13 = -2147024883;
LABEL_39:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrintError(
        g_pDebug,
        "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site.cxx",
        1412,
        "FTP_SITE::ParseBinding",
        v13,
        "Failed to parse the binding: %S\n",
        Str);
    goto LABEL_41;
  }
  v14 = wcschr(Stra, 0x3Au);
  v15 = Stra;
  if ( v14 && (*Stra != 91 || Stra[v24 - 1] != 93) )
  {
    v13 = -2147015344;
    goto LABEL_39;
  }
  if ( !v24 || a4 )
    goto LABEL_13;
  a2->sa_family = 23;
  if ( WSAStringToAddressW(v15, 23, 0, a2, &AddressLength) != -1 )
    goto LABEL_30;
  a2->sa_family = 2;
  if ( WSAStringToAddressW(Stra, 2, 0, a2, &AddressLength) != -1 )
    goto LABEL_30;
  Error = WSAGetLastError();
  v13 = Error;
  if ( Error > 0 )
    v13 = (unsigned __int16)Error | 0x80070000;
  if ( (g_dwDebugFlags & 0xF) != 0 )
    PuDbgPrintError(
      g_pDebug,
      "inetsrv\\iis\\iisrearc\\ftp\\server\\core\\ftp_site.cxx",
      1349,
      "FTP_SITE::ParseBinding",
      v13,
      "Failed to translate address in binding %S\n",
      Str);
  if ( v13 < 0 )
    goto LABEL_39;
LABEL_41:
  STRU::~STRU(v25);
  STRU::~STRU(v22);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000a0e4  mov     [rsp-8+arg_18], rbx
0x18000a0e9  push    rbp
0x18000a0ea  push    rsi
0x18000a0eb  push    rdi
0x18000a0ec  push    r12
0x18000a0ee  push    r13
0x18000a0f0  push    r14
0x18000a0f2  push    r15
0x18000a0f4  lea     rbp, [rsp-90h]
0x18000a0fc  sub     rsp, 190h
0x18000a103  mov     rax, cs:__security_cookie
0x18000a10a  xor     rax, rsp
0x18000a10d  mov     [rbp+0C0h+var_40], rax
0x18000a114  mov     r13d, r9d
0x18000a117  mov     [rsp+1C0h+var_178], r8
0x18000a11c  mov     rdi, rdx
0x18000a11f  mov     r12, rcx
0x18000a122  xor     r14d, r14d
0x18000a125  mov     r15d, r14d
0x18000a128  mov     esi, r14d
0x18000a12b  xor     edx, edx; Val
0x18000a12d  mov     r8d, 80h; Size
0x18000a133  lea     rcx, [rbp+0C0h+var_C0]; void *
0x18000a137  call    memset_0
0x18000a13c  lea     ebx, [r14+40h]
0x18000a140  mov     r8d, ebx
0x18000a143  lea     rdx, [rbp+0C0h+var_C0]
0x18000a147  lea     rcx, [rsp+1C0h+var_170]
0x18000a14c  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a152  nop
0x18000a153  mov     r8d, ebx; Size
0x18000a156  xor     edx, edx; Val
0x18000a158  lea     rcx, [rbp+0C0h+var_100]; void *
0x18000a15c  call    memset_0
0x18000a161  lea     r8d, [r14+20h]
0x18000a165  lea     rdx, [rbp+0C0h+var_100]
0x18000a169  lea     rcx, [rbp+0C0h+var_138]
0x18000a16d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000a173  nop
0x18000a174  lea     eax, [rbx+40h]
0x18000a177  mov     [rsp+1C0h+AddressLength], eax
0x18000a17b  mov     r8d, eax; Size
0x18000a17e  xor     edx, edx; Val
0x18000a180  mov     rcx, rdi; void *
0x18000a183  call    memset_0
0x18000a188  mov     rcx, r12; Str
0x18000a18b  mov     rbx, rsi
0x18000a18e  mov     edx, 3Ah ; ':'; Ch
0x18000a193  call    cs:__imp_wcschr
0x18000a199  test    rax, rax
0x18000a19c  cmovnz  rsi, rax
0x18000a1a0  lea     rcx, [rax+2]
0x18000a1a4  cmovz   rcx, rax
0x18000a1a8  cmovz   rbx, r15
0x18000a1ac  mov     r15, rbx
0x18000a1af  test    rcx, rcx
0x18000a1b2  jnz     short loc_18000A18B
0x18000a1b4  test    rbx, rbx
0x18000a1b7  mov     r14, [rsp+1C0h+var_178]
0x18000a1bc  jz      loc_18000A3B3
0x18000a1c2  test    rsi, rsi
0x18000a1c5  jz      loc_18000A3B3
0x18000a1cb  mov     r8, rbx
0x18000a1ce  sub     r8, r12
0x18000a1d1  sar     r8, 1
0x18000a1d4  mov     rdx, r12
0x18000a1d7  lea     rcx, [rsp+1C0h+var_170]
0x18000a1dc  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000a1e2  mov     ebx, eax
0x18000a1e4  test    eax, eax
0x18000a1e6  js      loc_18000A3B8
0x18000a1ec  mov     rcx, [rsp+1C0h+Str]; Str
0x18000a1f1  xor     ebx, ebx
0x18000a1f3  cmp     word ptr [rcx], 2Ah ; '*'
0x18000a1f7  jnz     short loc_18000A23D
0x18000a1f9  cmp     [rcx+2], bx
0x18000a1fd  jnz     short loc_18000A23D
0x18000a1ff  mov     [rcx], bx
0x18000a202  mov     [rbp+0C0h+var_140], ebx
0x18000a205  xor     edx, edx; Val
0x18000a207  mov     r8d, 80h; Size
0x18000a20d  mov     rcx, rdi; void *
0x18000a210  call    memset_0
0x18000a215  cmp     cs:?sm_pConnectExIp6@FTP_ASYNC_SOCKET@@0P6AH_KPEBUsockaddr@@HPEAXKPEAKPEAU_OVERLAPPED@@@ZEA, rbx; int (*FTP_ASYNC_SOCKET::sm_pConnectExIp6)(unsigned __int64,sockaddr const *,int,void *,ulong,ulong *,_OVERLAPPED *)
0x18000a21c  mov     ebx, 2
0x18000a221  jz      loc_18000A32F
0x18000a227  mov     word ptr [rdi], 17h
0x18000a22c  movups  xmm0, xmmword ptr cs:in6addr_any.u
0x18000a233  movdqu  xmmword ptr [rdi+8], xmm0
0x18000a238  jmp     loc_18000A332
0x18000a23d  mov     edx, 3Ah ; ':'; Ch
0x18000a242  call    cs:__imp_wcschr
0x18000a248  mov     edx, [rbp+0C0h+var_140]
0x18000a24b  mov     r10, [rsp+1C0h+Str]
0x18000a250  test    rax, rax
0x18000a253  jz      short loc_18000A271
0x18000a255  cmp     word ptr [r10], 5Bh ; '['
0x18000a25a  jnz     short loc_18000A267
0x18000a25c  lea     eax, [rdx-1]
0x18000a25f  cmp     word ptr [r10+rax*2], 5Dh ; ']'
0x18000a265  jz      short loc_18000A271
0x18000a267  mov     ebx, 80072550h
0x18000a26c  jmp     loc_18000A3B8
0x18000a271  test    edx, edx
0x18000a273  jz      short loc_18000A205
0x18000a275  test    r13d, r13d
0x18000a278  jnz     short loc_18000A205
0x18000a27a  lea     eax, [r13+17h]
0x18000a27e  mov     [rdi], ax
0x18000a281  lea     rcx, [rsp+1C0h+AddressLength]
0x18000a286  mov     [rsp+1C0h+lpAddressLength], rcx; lpAddressLength
0x18000a28b  mov     r9, rdi; lpAddress
0x18000a28e  xor     r8d, r8d; lpProtocolInfo
0x18000a291  mov     edx, eax; AddressFamily
0x18000a293  mov     rcx, r10; AddressString
0x18000a296  call    cs:__imp_WSAStringToAddressW
0x18000a29c  lea     ebx, [r13+2]
0x18000a2a0  cmp     eax, 0FFFFFFFFh
0x18000a2a3  jnz     loc_18000A332
0x18000a2a9  mov     [rdi], bx
0x18000a2ac  lea     rax, [rsp+1C0h+AddressLength]
0x18000a2b1  mov     [rsp+1C0h+lpAddressLength], rax; lpAddressLength
0x18000a2b6  mov     r9, rdi; lpAddress
0x18000a2b9  xor     r8d, r8d; lpProtocolInfo
0x18000a2bc  mov     edx, ebx; AddressFamily
0x18000a2be  mov     rcx, [rsp+1C0h+Str]; AddressString
0x18000a2c3  call    cs:__imp_WSAStringToAddressW
0x18000a2c9  cmp     eax, 0FFFFFFFFh
0x18000a2cc  jnz     short loc_18000A332
0x18000a2ce  call    cs:__imp_WSAGetLastError
0x18000a2d4  mov     ebx, eax
0x18000a2d6  test    eax, eax
0x18000a2d8  jle     short loc_18000A2E3
0x18000a2da  movzx   ebx, ax
0x18000a2dd  or      ebx, 80070000h
0x18000a2e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a2ea  jz      short loc_18000A322
0x18000a2ec  mov     [rsp+1C0h+var_190], r12
0x18000a2f1  lea     rax, aFailedToTransl_0; "Failed to translate address in binding "...
0x18000a2f8  mov     [rsp+1C0h+var_198], rax
0x18000a2fd  mov     dword ptr [rsp+1C0h+lpAddressLength], ebx
0x18000a301  lea     r9, aFtpSiteParsebi; "FTP_SITE::ParseBinding"
0x18000a308  mov     r8d, 545h
0x18000a30e  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000a315  mov     rcx, cs:g_pDebug
0x18000a31c  call    cs:__imp_PuDbgPrintError
0x18000a322  test    ebx, ebx
0x18000a324  jns     loc_18000A3F8
0x18000a32a  jmp     loc_18000A3B8
0x18000a32f  mov     [rdi], bx
0x18000a332  mov     r8, rsi
0x18000a335  sub     r8, r15
0x18000a338  sub     r8, rbx
0x18000a33b  sar     r8, 1
0x18000a33e  lea     rdx, [r15+2]
0x18000a342  lea     rcx, [rbp+0C0h+var_138]
0x18000a346  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18000a34c  mov     ebx, eax
0x18000a34e  xor     r15d, r15d
0x18000a351  test    eax, eax
0x18000a353  js      short loc_18000A3B8
0x18000a355  xor     edx, edx; EndPtr
0x18000a357  lea     r8d, [r15+0Ah]; Radix
0x18000a35b  mov     rcx, [rbp+0C0h+String]; String
0x18000a35f  call    cs:__imp_wcstoul
0x18000a365  lea     ecx, [rax-1]
0x18000a368  cmp     ecx, 0FFFEh
0x18000a36e  ja      short loc_18000A3B3
0x18000a370  movzx   ecx, ax; hostshort
0x18000a373  call    cs:__imp_htons
0x18000a379  mov     [rdi+2], ax
0x18000a37d  test    r14, r14
0x18000a380  jz      short loc_18000A3AE
0x18000a382  lea     rdx, [rsi+2]
0x18000a386  mov     rcx, r14
0x18000a389  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000a38f  mov     ebx, eax
0x18000a391  test    eax, eax
0x18000a393  js      short loc_18000A3B8
0x18000a395  mov     rcx, [r14+20h]
0x18000a399  cmp     word ptr [rcx], 2Ah ; '*'
0x18000a39d  jnz     short loc_18000A3AE
0x18000a39f  cmp     [rcx+2], r15w
0x18000a3a4  jnz     short loc_18000A3AE
0x18000a3a6  mov     [rcx], r15w
0x18000a3aa  mov     [r14+30h], r15d
0x18000a3ae  mov     ebx, r15d
0x18000a3b1  jmp     short loc_18000A3F8
0x18000a3b3  mov     ebx, 8007000Dh
0x18000a3b8  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000a3bf  jz      short loc_18000A3F8
0x18000a3c1  mov     [rsp+1C0h+var_190], r12
0x18000a3c6  lea     rax, aFailedToParseT; "Failed to parse the binding: %S\n"
0x18000a3cd  mov     [rsp+1C0h+var_198], rax
0x18000a3d2  mov     dword ptr [rsp+1C0h+lpAddressLength], ebx
0x18000a3d6  lea     r9, aFtpSiteParsebi; "FTP_SITE::ParseBinding"
0x18000a3dd  mov     r8d, 584h
0x18000a3e3  lea     rdx, aInetsrvIisIisr_2; "inetsrv\\iis\\iisrearc\\ftp\\server\\co"...
0x18000a3ea  mov     rcx, cs:g_pDebug
0x18000a3f1  call    cs:__imp_PuDbgPrintError
0x18000a3f7  nop
0x18000a3f8  lea     rcx, [rbp+0C0h+var_138]
0x18000a3fc  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a402  nop
0x18000a403  lea     rcx, [rsp+1C0h+var_170]
0x18000a408  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000a40e  mov     eax, ebx
0x18000a410  mov     rcx, [rbp+0C0h+var_40]
0x18000a417  xor     rcx, rsp; StackCookie
0x18000a41a  call    __security_check_cookie
0x18000a41f  mov     rbx, [rsp+1C0h+arg_18]
0x18000a427  add     rsp, 190h
0x18000a42e  pop     r15
0x18000a430  pop     r14
0x18000a432  pop     r13
0x18000a434  pop     r12
0x18000a436  pop     rdi
0x18000a437  pop     rsi
0x18000a438  pop     rbp
0x18000a439  retn
```
