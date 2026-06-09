# IP_RESTRICTION_LIST::AddEntry(int,ushort const *,ushort const *,ushort const *)

- ea: `0x1800034fc`
- end: `0x180003674`
- name: `?AddEntry@IP_RESTRICTION_LIST@@QEAAJHPEBG00@Z`
- size: `376`
- prototype: `int __fastcall(IP_RESTRICTION_LIST *this, int, const unsigned __int16 *, IP_RESTRICTION_LIST_ENTRY *, LPCWSTR lpUnicodeCharStr)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800030a0`

## callees

- `0x1800034fc`
- `0x180003ce8`
- `0x180004608`
- `0x180004ad0`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x1800035c7`
- `WS2_32!FreeAddrInfoW` at `0x1800035c7`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180003628`
- `api-ms-win-core-localization-l1-2-0!IdnToAscii` at `0x180003628`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000363e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000363e`

## pseudocode

```c
int __fastcall IP_RESTRICTION_LIST::AddEntry(
        IP_RESTRICTION_LIST *this,
        int a2,
        const unsigned __int16 *a3,
        IP_RESTRICTION_LIST_ENTRY *a4,
        LPCWSTR lpUnicodeCharStr)
{
  __int64 v5; // rax
  int result; // eax
  __int64 v9; // rbx
  int AddrInfoHelper; // edi
  struct addrinfoW *v11; // rdx
  int v12; // eax
  struct sockaddr *ai_addr; // rcx
  const WCHAR *v14; // rdx
  WCHAR *p_ASCIICharStr; // r9
  int v16; // eax
  WCHAR *v17; // rdx
  PADDRINFOW pAddrInfo; // [rsp+30h] [rbp-258h] BYREF
  WCHAR ASCIICharStr; // [rsp+40h] [rbp-248h] BYREF
  char v20; // [rsp+42h] [rbp-246h] BYREF

  v5 = *((unsigned int *)this + 1);
  if ( (unsigned int)v5 >= *(_DWORD *)this )
    return -2147024637;
  v9 = *((_QWORD *)this + 1) + (v5 << 8);
  pAddrInfo = 0;
  *(_DWORD *)v9 = a2;
  if ( !a3 || !*a3 )
  {
    *(_OWORD *)(v9 + 4) = 0;
    *(_OWORD *)(v9 + 16) = 0;
    *(_DWORD *)(v9 + 64) = 0;
    goto LABEL_17;
  }
  AddrInfoHelper = IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(this, a3, &pAddrInfo);
  if ( AddrInfoHelper < 0 )
    return AddrInfoHelper;
  v11 = pAddrInfo;
  v12 = 2;
  ai_addr = pAddrInfo->ai_addr;
  if ( ai_addr->sa_family == 2 )
  {
    *(struct sockaddr *)(v9 + 4) = *ai_addr;
LABEL_10:
    *(_DWORD *)(v9 + 68) = v12;
    AddrInfoHelper = 0;
    *(_DWORD *)(v9 + 64) = 1;
    goto LABEL_12;
  }
  v12 = 23;
  if ( ai_addr->sa_family == 23 )
  {
    *(struct sockaddr *)(v9 + 4) = *ai_addr;
    *(struct sockaddr *)(v9 + 16) = *(struct sockaddr *)&ai_addr->sa_data[10];
    goto LABEL_10;
  }
  AddrInfoHelper = -2147024809;
LABEL_12:
  if ( v11 )
    FreeAddrInfoW(v11);
  if ( AddrInfoHelper < 0 )
    return AddrInfoHelper;
LABEL_17:
  result = IP_RESTRICTION_LIST_ENTRY::SetIpMask((IP_RESTRICTION_LIST_ENTRY *)v9, a4);
  if ( result >= 0 )
  {
    if ( !lpUnicodeCharStr
      || (*lpUnicodeCharStr != 42
        ? (p_ASCIICharStr = &ASCIICharStr, v14 = lpUnicodeCharStr)
        : (ASCIICharStr = 42, v14 = lpUnicodeCharStr + 1, p_ASCIICharStr = (WCHAR *)&v20),
          v16 = IdnToAscii(0, v14, -1, p_ASCIICharStr, 260),
          v17 = &ASCIICharStr,
          !v16) )
    {
      v17 = (WCHAR *)lpUnicodeCharStr;
    }
    result = STRU::Copy((STRU *)(v9 + 72), v17);
    if ( result >= 0 )
    {
      ++*((_DWORD *)this + 1);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800034fc  mov     [rsp+arg_8], rbx
0x180003501  push    rbp
0x180003502  push    rsi
0x180003503  push    rdi
0x180003504  push    r14
0x180003506  push    r15
0x180003508  sub     rsp, 260h
0x18000350f  mov     rax, cs:__security_cookie
0x180003516  xor     rax, rsp
0x180003519  mov     [rsp+288h+var_38], rax
0x180003521  mov     eax, [rcx+4]
0x180003524  mov     r14, r9
0x180003527  mov     r9, r8
0x18000352a  mov     rsi, [rsp+288h+lpUnicodeCharStr]
0x180003532  mov     rbp, rcx
0x180003535  cmp     eax, [rcx]
0x180003537  jb      short loc_180003543
0x180003539  mov     eax, 80070103h
0x18000353e  jmp     loc_18000364D
0x180003543  xor     r15d, r15d
0x180003546  mov     rbx, rax
0x180003549  shl     rbx, 8
0x18000354d  add     rbx, [rcx+8]
0x180003551  mov     [rsp+288h+pAddrInfo], r15
0x180003556  mov     [rbx], edx
0x180003558  test    r9, r9
0x18000355b  jz      short loc_1800035D5
0x18000355d  cmp     [r8], r15w
0x180003561  jz      short loc_1800035D5
0x180003563  lea     r8, [rsp+288h+pAddrInfo]; struct addrinfoW **
0x180003568  mov     rdx, r9; unsigned __int16 *
0x18000356b  call    ?GetAddrInfoHelper@IP_RESTRICTION_LIST_ENTRY@@AEAAJPEBGPEAPEAUaddrinfoW@@@Z; IP_RESTRICTION_LIST_ENTRY::GetAddrInfoHelper(ushort const *,addrinfoW * *)
0x180003570  mov     edi, eax
0x180003572  test    eax, eax
0x180003574  js      short loc_1800035D1
0x180003576  mov     rdx, [rsp+288h+pAddrInfo]
0x18000357b  lea     eax, [r15+2]
0x18000357f  mov     rcx, [rdx+20h]
0x180003583  cmp     [rcx], ax
0x180003586  jnz     short loc_180003592
0x180003588  movups  xmm0, xmmword ptr [rcx]
0x18000358b  movdqu  xmmword ptr [rbx+4], xmm0
0x180003590  jmp     short loc_1800035AB
0x180003592  mov     eax, 17h
0x180003597  cmp     [rcx], ax
0x18000359a  jnz     short loc_1800035BA
0x18000359c  movups  xmm0, xmmword ptr [rcx]
0x18000359f  movups  xmmword ptr [rbx+4], xmm0
0x1800035a3  movups  xmm1, xmmword ptr [rcx+0Ch]
0x1800035a7  movups  xmmword ptr [rbx+10h], xmm1
0x1800035ab  mov     [rbx+44h], eax
0x1800035ae  mov     edi, r15d
0x1800035b1  mov     dword ptr [rbx+40h], 1
0x1800035b8  jmp     short loc_1800035BF
0x1800035ba  mov     edi, 80070057h
0x1800035bf  test    rdx, rdx
0x1800035c2  jz      short loc_1800035CD
0x1800035c4  mov     rcx, rdx; pAddrInfo
0x1800035c7  call    cs:__imp_FreeAddrInfoW
0x1800035cd  test    edi, edi
0x1800035cf  jns     short loc_1800035E4
0x1800035d1  mov     eax, edi
0x1800035d3  jmp     short loc_18000364D
0x1800035d5  xorps   xmm0, xmm0
0x1800035d8  movups  xmmword ptr [rbx+4], xmm0
0x1800035dc  movups  xmmword ptr [rbx+10h], xmm0
0x1800035e0  mov     [rbx+40h], r15d
0x1800035e4  mov     rdx, r14; IP_RESTRICTION_LIST_ENTRY *
0x1800035e7  mov     rcx, rbx; this
0x1800035ea  call    ?SetIpMask@IP_RESTRICTION_LIST_ENTRY@@QEAAJPEBG@Z; IP_RESTRICTION_LIST_ENTRY::SetIpMask(ushort const *)
0x1800035ef  test    eax, eax
0x1800035f1  js      short loc_18000364D
0x1800035f3  test    rsi, rsi
0x1800035f6  jz      short loc_180003637
0x1800035f8  mov     eax, 2Ah ; '*'
0x1800035fd  mov     [rsp+288h+cchASCIIChar], 104h; cchASCIIChar
0x180003605  or      r8d, 0FFFFFFFFh; cchUnicodeChar
0x180003609  xor     ecx, ecx; dwFlags
0x18000360b  cmp     [rsi], ax
0x18000360e  jnz     short loc_180003620
0x180003610  mov     [rsp+288h+ASCIICharStr], ax
0x180003615  lea     rdx, [rsi+2]
0x180003619  lea     r9, [rsp+288h+var_246]
0x18000361e  jmp     short loc_180003628
0x180003620  lea     r9, [rsp+288h+ASCIICharStr]; lpASCIICharStr
0x180003625  mov     rdx, rsi; lpUnicodeCharStr
0x180003628  call    cs:__imp_IdnToAscii
0x18000362e  lea     rdx, [rsp+288h+ASCIICharStr]
0x180003633  test    eax, eax
0x180003635  jnz     short loc_18000363A
0x180003637  mov     rdx, rsi
0x18000363a  lea     rcx, [rbx+48h]
0x18000363e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003644  test    eax, eax
0x180003646  js      short loc_18000364D
0x180003648  inc     dword ptr [rbp+4]
0x18000364b  xor     eax, eax
0x18000364d  mov     rcx, [rsp+288h+var_38]
0x180003655  xor     rcx, rsp; StackCookie
0x180003658  call    __security_check_cookie
0x18000365d  mov     rbx, [rsp+288h+arg_8]
0x180003665  add     rsp, 260h
0x18000366c  pop     r15
0x18000366e  pop     r14
0x180003670  pop     rdi
0x180003671  pop     rsi
0x180003672  pop     rbp
0x180003673  retn
```
