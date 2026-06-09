# PROTOCOL_BINDING_ENTRY::GetKey(_HTTP_REQUEST_V2 *,STRU *)

- ea: `0x180058208`
- end: `0x18005839f`
- name: `?GetKey@PROTOCOL_BINDING_ENTRY@@SAJPEAU_HTTP_REQUEST_V2@@PEAVSTRU@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(struct _HTTP_REQUEST_V2 *, struct STRU *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180057b64`

## callees

- `0x180058208`
- `0x18006101a`
- `0x180061060`

## import_xrefs

- `WS2_32!GetNameInfoW` at `0x1800582ba`
- `WS2_32!GetNameInfoW` at `0x1800582ba`
- `WS2_32!__imp_WSAGetLastError` at `0x1800582c4`
- `WS2_32!__imp_WSAGetLastError` at `0x1800582c4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058378`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180058378`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800582f8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800582f8`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005830d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005832f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005830d`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18005832f`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005825e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18005825e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180058275`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180058275`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058323`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058343`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005836b`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058323`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x180058343`
- `iisutil!?Append@STRU@@QEAAJG@Z` at `0x18005836b`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180058357`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180058357`

## pseudocode

```c
__int64 __fastcall PROTOCOL_BINDING_ENTRY::GetKey(struct _HTTP_REQUEST_V2 *a1, struct STRU *a2)
{
  signed int v4; // ebx
  PSOCKADDR pLocalAddress; // rcx
  socklen_t v6; // edx
  int Error; // eax
  int v8; // eax
  _BYTE v10[64]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pNodeBuffer[48]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v12[48]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(pNodeBuffer, 0, 0x54u);
  memset_0(v12, 0, 0x54u);
  STRU::STRU((STRU *)v10, v12, 0x2Au);
  v4 = STRU::Copy(a2, a1->CookedUrl.pFullUrl, a1->CookedUrl.pAbsPath - a1->CookedUrl.pFullUrl);
  if ( v4 >= 0 )
  {
    pLocalAddress = a1->Address.pLocalAddress;
    v6 = 16;
    if ( pLocalAddress->sa_family != 2 )
      v6 = 28;
    if ( GetNameInfoW(pLocalAddress, v6, pNodeBuffer, 0x2Au, 0, 0, 2) )
    {
      Error = WSAGetLastError();
      v4 = Error;
      if ( Error > 0 )
        v4 = (unsigned __int16)Error | 0x80070000;
    }
    else
    {
      if ( a1->Address.pLocalAddress->sa_family == 23 )
      {
        v4 = STRU::Copy((STRU *)v10, L"[");
        if ( v4 < 0 )
          goto LABEL_16;
        v4 = STRU::Append((STRU *)v10, pNodeBuffer);
        if ( v4 < 0 )
          goto LABEL_16;
        v8 = STRU::Append((STRU *)v10, 0x5Du);
      }
      else
      {
        v8 = STRU::Append((STRU *)v10, pNodeBuffer);
      }
      v4 = v8;
      if ( v8 >= 0 )
      {
        v4 = STRU::Append(a2, 0x3Au);
        if ( v4 >= 0 )
        {
          v4 = STRU::Append(a2, (const struct STRU *)v10);
          if ( v4 >= 0 )
            v4 = STRU::Append(a2, 0x2Fu);
        }
      }
    }
  }
LABEL_16:
  STRU::~STRU((STRU *)v10);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180058208  mov     [rsp-8+arg_10], rbx
0x18005820d  push    rbp
0x18005820e  push    rsi
0x18005820f  push    rdi
0x180058210  lea     rbp, [rsp-50h]
0x180058215  sub     rsp, 150h
0x18005821c  mov     rax, cs:__security_cookie
0x180058223  xor     rax, rsp
0x180058226  mov     [rbp+60h+var_20], rax
0x18005822a  mov     rdi, rdx
0x18005822d  mov     rsi, rcx
0x180058230  mov     ebx, 54h ; 'T'
0x180058235  lea     rcx, [rbp+60h+pNodeBuffer]; void *
0x180058239  mov     r8d, ebx; Size
0x18005823c  xor     edx, edx; Val
0x18005823e  call    memset_0
0x180058243  mov     r8d, ebx; Size
0x180058246  lea     rcx, [rbp+60h+var_80]; void *
0x18005824a  xor     edx, edx; Val
0x18005824c  call    memset_0
0x180058251  lea     r8d, [rbx-2Ah]
0x180058255  lea     rdx, [rbp+60h+var_80]
0x180058259  lea     rcx, [rsp+160h+var_120]
0x18005825e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180058264  mov     rdx, [rsi+48h]
0x180058268  mov     rcx, rdi
0x18005826b  mov     r8, [rsi+58h]
0x18005826f  sub     r8, rdx
0x180058272  sar     r8, 1
0x180058275  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x18005827b  mov     ebx, eax
0x18005827d  test    eax, eax
0x18005827f  js      loc_180058373
0x180058285  mov     rcx, [rsi+70h]; pSockaddr
0x180058289  mov     edx, 10h
0x18005828e  lea     r8d, [rdx-0Eh]
0x180058292  cmp     [rcx], r8w
0x180058296  lea     eax, [rdx+0Ch]
0x180058299  mov     [rsp+160h+Flags], r8d; Flags
0x18005829e  lea     r9d, [rax+0Eh]; NodeBufferSize
0x1800582a2  cmovnz  edx, eax; SockaddrLength
0x1800582a5  mov     [rsp+160h+ServiceBufferSize], 0; ServiceBufferSize
0x1800582ad  lea     r8, [rbp+60h+pNodeBuffer]; pNodeBuffer
0x1800582b1  mov     [rsp+160h+pServiceBuffer], 0; pServiceBuffer
0x1800582ba  call    cs:__imp_GetNameInfoW
0x1800582c0  test    eax, eax
0x1800582c2  jz      short loc_1800582E2
0x1800582c4  call    cs:__imp_WSAGetLastError
0x1800582ca  mov     ebx, eax
0x1800582cc  test    eax, eax
0x1800582ce  jle     loc_180058373
0x1800582d4  movzx   ebx, ax
0x1800582d7  or      ebx, 80070000h
0x1800582dd  jmp     loc_180058373
0x1800582e2  mov     rax, [rsi+70h]
0x1800582e6  lea     rcx, [rsp+160h+var_120]
0x1800582eb  cmp     word ptr [rax], 17h
0x1800582ef  jnz     short loc_18005832B
0x1800582f1  lea     rdx, asc_18007D3F8; "["
0x1800582f8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800582fe  mov     ebx, eax
0x180058300  test    eax, eax
0x180058302  js      short loc_180058373
0x180058304  lea     rdx, [rbp+60h+pNodeBuffer]
0x180058308  lea     rcx, [rsp+160h+var_120]
0x18005830d  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058313  mov     ebx, eax
0x180058315  test    eax, eax
0x180058317  js      short loc_180058373
0x180058319  mov     edx, 5Dh ; ']'
0x18005831e  lea     rcx, [rsp+160h+var_120]
0x180058323  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180058329  jmp     short loc_180058335
0x18005832b  lea     rdx, [rbp+60h+pNodeBuffer]
0x18005832f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180058335  mov     ebx, eax
0x180058337  test    eax, eax
0x180058339  js      short loc_180058373
0x18005833b  mov     edx, 3Ah ; ':'
0x180058340  mov     rcx, rdi
0x180058343  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180058349  mov     ebx, eax
0x18005834b  test    eax, eax
0x18005834d  js      short loc_180058373
0x18005834f  lea     rdx, [rsp+160h+var_120]
0x180058354  mov     rcx, rdi
0x180058357  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x18005835d  mov     ebx, eax
0x18005835f  test    eax, eax
0x180058361  js      short loc_180058373
0x180058363  mov     edx, 2Fh ; '/'
0x180058368  mov     rcx, rdi
0x18005836b  call    cs:__imp_?Append@STRU@@QEAAJG@Z; STRU::Append(ushort)
0x180058371  mov     ebx, eax
0x180058373  lea     rcx, [rsp+160h+var_120]
0x180058378  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18005837e  mov     eax, ebx
0x180058380  mov     rcx, [rbp+60h+var_20]
0x180058384  xor     rcx, rsp; StackCookie
0x180058387  call    __security_check_cookie
0x18005838c  mov     rbx, [rsp+160h+arg_10]
0x180058394  add     rsp, 150h
0x18005839b  pop     rdi
0x18005839c  pop     rsi
0x18005839d  pop     rbp
0x18005839e  retn
```
