# NhCreateStreamSocket(sockaddr_storage *,_NH_RCSOCKET *)

- ea: `0x18005a310`
- end: `0x18005a691`
- name: `?NhCreateStreamSocket@@YAKPEAUsockaddr_storage@@PEAU_NH_RCSOCKET@@@Z`
- size: `897`
- prototype: `__int64 __fastcall(struct sockaddr_storage *, struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180059b60`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180051f30`
- `0x180052bf4`
- `0x18005a310`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a392`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005a392`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a3a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a483`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a5ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005a5ef`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18005a473`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18005a473`
- `WS2_32!WSASocketW` at `0x18005a417`
- `WS2_32!WSASocketW` at `0x18005a417`
- `WS2_32!__imp_bind` at `0x18005a579`
- `WS2_32!__imp_bind` at `0x18005a579`
- `WS2_32!__imp_closesocket` at `0x18005a5ce`
- `WS2_32!__imp_closesocket` at `0x18005a5ce`
- `WS2_32!__imp_setsockopt` at `0x18005a4e3`
- `WS2_32!__imp_setsockopt` at `0x18005a50d`
- `WS2_32!__imp_setsockopt` at `0x18005a4e3`
- `WS2_32!__imp_setsockopt` at `0x18005a50d`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a42c`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a58e`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a42c`
- `WS2_32!__imp_WSAGetLastError` at `0x18005a58e`

## pseudocode

```c
__int64 __fastcall NhCreateStreamSocket(struct sockaddr_storage *a1, struct _NH_RCSOCKET *a2)
{
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD v6; // ebx
  PVOID *v7; // rcx
  __int64 v8; // rdx
  void *v9; // rax
  SOCKET v10; // rsi
  DWORD Error; // eax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  char optval[16]; // [rsp+30h] [rbp-69h] BYREF
  struct sockaddr name; // [rsp+40h] [rbp-59h] BYREF
  __int128 v25; // [rsp+50h] [rbp-49h]
  __int128 v26; // [rsp+60h] [rbp-39h]
  __int128 v27; // [rsp+70h] [rbp-29h]
  __int128 v28; // [rsp+80h] [rbp-19h]
  __int128 v29; // [rsp+90h] [rbp-9h]
  __int128 v30; // [rsp+A0h] [rbp+7h]
  __int128 v31; // [rsp+B0h] [rbp+17h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  *(_DWORD *)optval = 0;
  memset_0(&name, 0, 0x80u);
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a2 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    v6 = LastError;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v8 = 47;
    goto LABEL_10;
  }
  *(_DWORD *)a2 = 2;
  v9 = (void *)WSASocketW(2, 1, 6, 0, 0, 1u);
  v10 = (SOCKET)v9;
  if ( v9 == (void *)-1LL )
  {
    LastError = WSAGetLastError();
    v6 = LastError;
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_32;
    }
    v8 = 48;
LABEL_10:
    WPP_SF_d(v7[2], v8, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
LABEL_31:
    v7 = (PVOID *)WPP_GLOBAL_Control;
LABEL_32:
    if ( *((_QWORD *)a2 + 1) )
    {
      _InterlockedDecrement((volatile signed __int32 *)a2);
      CloseHandle(*((HANDLE *)a2 + 1));
      *((_QWORD *)a2 + 1) = 0;
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 8) != 0 && *((_BYTE *)v7 + 25) >= 6u )
      WPP_SF_d(v7[2], 52, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v6);
    return v6;
  }
  if ( !BindIoCompletionCallback(v9, NhpIoCompletionRoutine, 0) )
  {
    Error = GetLastError();
    v6 = Error;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    v13 = 49;
LABEL_29:
    WPP_SF_d(v12[2], v13, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
LABEL_30:
    closesocket(v10);
    goto LABEL_31;
  }
  *(_DWORD *)optval = 0;
  setsockopt(v10, 0xFFFF, 4097, optval, 4);
  *(_DWORD *)optval = 0;
  setsockopt(v10, 0xFFFF, 4098, optval, 4);
  v14 = 8;
  if ( a1->ss_family != 23 )
    v14 = 4;
  if ( *(_DWORD *)((char *)&a1->ss_family + v14) != -1 )
  {
    v15 = *(_OWORD *)a1->__ss_pad2;
    name = *(struct sockaddr *)&a1->ss_family;
    v16 = *(_OWORD *)&a1->__ss_pad2[16];
    v25 = v15;
    v17 = *(_OWORD *)&a1->__ss_pad2[32];
    v26 = v16;
    v18 = *(_OWORD *)&a1->__ss_pad2[48];
    v27 = v17;
    v19 = *(_OWORD *)&a1->__ss_pad2[64];
    v28 = v18;
    v20 = *(_OWORD *)&a1->__ss_pad2[80];
    v29 = v19;
    v21 = *(_OWORD *)&a1->__ss_pad2[96];
    v30 = v20;
    v31 = v21;
    if ( bind(v10, &name, 128) == -1 )
    {
      Error = WSAGetLastError();
      v6 = Error;
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_30;
      }
      v13 = 50;
      goto LABEL_29;
    }
  }
  *((_QWORD *)a2 + 2) = v10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18005a310  mov     [rsp-8+arg_10], rbx
0x18005a315  push    rbp
0x18005a316  push    rsi
0x18005a317  push    rdi
0x18005a318  push    r13
0x18005a31a  push    r15
0x18005a31c  lea     rbp, [rsp-37h]
0x18005a321  sub     rsp, 0D0h
0x18005a328  mov     rax, cs:__security_cookie
0x18005a32f  xor     rax, rsp
0x18005a332  mov     [rbp+57h+var_30], rax
0x18005a336  mov     rdi, rdx
0x18005a339  mov     rbx, rcx
0x18005a33c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a343  lea     r13, WPP_GLOBAL_Control
0x18005a34a  cmp     rcx, r13
0x18005a34d  jz      short loc_18005A370
0x18005a34f  test    byte ptr [rcx+1Ch], 8
0x18005a353  jz      short loc_18005A370
0x18005a355  cmp     byte ptr [rcx+19h], 6
0x18005a359  jb      short loc_18005A370
0x18005a35b  mov     rcx, [rcx+10h]
0x18005a35f  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a366  mov     edx, 2Eh ; '.'
0x18005a36b  call    WPP_SF_
0x18005a370  xor     edx, edx; Val
0x18005a372  mov     dword ptr [rbp+57h+optval], 0
0x18005a379  mov     r8d, 80h; Size
0x18005a37f  lea     rcx, [rbp+57h+name]; void *
0x18005a383  call    memset_0
0x18005a388  xor     r9d, r9d; lpName
0x18005a38b  xor     r8d, r8d; bInitialState
0x18005a38e  xor     edx, edx; bManualReset
0x18005a390  xor     ecx, ecx; lpEventAttributes
0x18005a392  call    cs:__imp_CreateEventW
0x18005a399  nop     dword ptr [rax+rax+00h]
0x18005a39e  mov     [rdi+8], rax
0x18005a3a2  test    rax, rax
0x18005a3a5  jnz     short loc_18005A3F6
0x18005a3a7  call    cs:__imp_GetLastError
0x18005a3ae  nop     dword ptr [rax+rax+00h]
0x18005a3b3  mov     ebx, eax
0x18005a3b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a3bc  cmp     rcx, r13
0x18005a3bf  jz      loc_18005A5E1
0x18005a3c5  test    byte ptr [rcx+1Ch], 8
0x18005a3c9  jz      loc_18005A5E1
0x18005a3cf  cmp     byte ptr [rcx+19h], 2
0x18005a3d3  jb      loc_18005A5E1
0x18005a3d9  mov     edx, 2Fh ; '/'
0x18005a3de  mov     rcx, [rcx+10h]
0x18005a3e2  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a3e9  mov     r9d, eax
0x18005a3ec  call    WPP_SF_d
0x18005a3f1  jmp     loc_18005A5DA
0x18005a3f6  mov     edx, 1; type
0x18005a3fb  mov     dword ptr [rdi], 2
0x18005a401  mov     [rsp+0F0h+dwFlags], edx; dwFlags
0x18005a405  xor     r9d, r9d; lpProtocolInfo
0x18005a408  mov     [rsp+0F0h+g], 0; g
0x18005a410  lea     ecx, [rdx+1]; af
0x18005a413  lea     r8d, [rdx+5]; protocol
0x18005a417  call    cs:__imp_WSASocketW
0x18005a41e  nop     dword ptr [rax+rax+00h]
0x18005a423  mov     rsi, rax
0x18005a426  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005a42a  jnz     short loc_18005A466
0x18005a42c  call    cs:__imp_WSAGetLastError
0x18005a433  nop     dword ptr [rax+rax+00h]
0x18005a438  mov     ebx, eax
0x18005a43a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a441  cmp     rcx, r13
0x18005a444  jz      loc_18005A5E1
0x18005a44a  test    byte ptr [rcx+1Ch], 8
0x18005a44e  jz      loc_18005A5E1
0x18005a454  cmp     byte ptr [rcx+19h], 2
0x18005a458  jb      loc_18005A5E1
0x18005a45e  lea     edx, [rsi+31h]
0x18005a461  jmp     loc_18005A3DE
0x18005a466  xor     r8d, r8d; Flags
0x18005a469  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x18005a470  mov     rcx, rsi; FileHandle
0x18005a473  call    cs:__imp_BindIoCompletionCallback
0x18005a47a  nop     dword ptr [rax+rax+00h]
0x18005a47f  test    eax, eax
0x18005a481  jnz     short loc_18005A4BF
0x18005a483  call    cs:__imp_GetLastError
0x18005a48a  nop     dword ptr [rax+rax+00h]
0x18005a48f  mov     ebx, eax
0x18005a491  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a498  cmp     rcx, r13
0x18005a49b  jz      loc_18005A5CB
0x18005a4a1  test    byte ptr [rcx+1Ch], 8
0x18005a4a5  jz      loc_18005A5CB
0x18005a4ab  cmp     byte ptr [rcx+19h], 2
0x18005a4af  jb      loc_18005A5CB
0x18005a4b5  mov     edx, 31h ; '1'
0x18005a4ba  jmp     loc_18005A5B8
0x18005a4bf  mov     r15d, 4
0x18005a4c5  mov     dword ptr [rbp+57h+optval], 0
0x18005a4cc  lea     r9, [rbp+57h+optval]; optval
0x18005a4d0  mov     [rsp+0F0h+g], r15d; optlen
0x18005a4d5  mov     edx, 0FFFFh; level
0x18005a4da  mov     r8d, 1001h; optname
0x18005a4e0  mov     rcx, rsi; s
0x18005a4e3  call    cs:__imp_setsockopt
0x18005a4ea  nop     dword ptr [rax+rax+00h]
0x18005a4ef  lea     r9, [rbp+57h+optval]; optval
0x18005a4f3  mov     dword ptr [rbp+57h+optval], 0
0x18005a4fa  mov     edx, 0FFFFh; level
0x18005a4ff  mov     [rsp+0F0h+g], r15d; optlen
0x18005a504  mov     r8d, 1002h; optname
0x18005a50a  mov     rcx, rsi; s
0x18005a50d  call    cs:__imp_setsockopt
0x18005a514  nop     dword ptr [rax+rax+00h]
0x18005a519  cmp     word ptr [rbx], 17h
0x18005a51d  lea     eax, [r15+4]
0x18005a521  cmovnz  eax, r15d
0x18005a525  cmp     dword ptr [rax+rbx], 0FFFFFFFFh
0x18005a529  jz      loc_18005A637
0x18005a52f  movups  xmm0, xmmword ptr [rbx]
0x18005a532  lea     r8d, [r15+7Ch]; namelen
0x18005a536  mov     rcx, rsi; s
0x18005a539  movups  xmm1, xmmword ptr [rbx+10h]
0x18005a53d  lea     rdx, [rbp+57h+name]; name
0x18005a541  movaps  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x18005a545  movups  xmm0, xmmword ptr [rbx+20h]
0x18005a549  movaps  [rbp+57h+var_A0], xmm1
0x18005a54d  movups  xmm1, xmmword ptr [rbx+30h]
0x18005a551  movaps  [rbp+57h+var_90], xmm0
0x18005a555  movups  xmm0, xmmword ptr [rbx+40h]
0x18005a559  movaps  [rbp+57h+var_80], xmm1
0x18005a55d  movups  xmm1, xmmword ptr [rbx+50h]
0x18005a561  movaps  [rbp+57h+var_70], xmm0
0x18005a565  movups  xmm0, xmmword ptr [rbx+60h]
0x18005a569  movaps  [rbp+57h+var_60], xmm1
0x18005a56d  movups  xmm1, xmmword ptr [rbx+70h]
0x18005a571  movaps  [rbp+57h+var_50], xmm0
0x18005a575  movaps  [rbp+57h+var_40], xmm1
0x18005a579  call    cs:__imp_bind
0x18005a580  nop     dword ptr [rax+rax+00h]
0x18005a585  cmp     eax, 0FFFFFFFFh
0x18005a588  jnz     loc_18005A637
0x18005a58e  call    cs:__imp_WSAGetLastError
0x18005a595  nop     dword ptr [rax+rax+00h]
0x18005a59a  mov     ebx, eax
0x18005a59c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5a3  cmp     rcx, r13
0x18005a5a6  jz      short loc_18005A5CB
0x18005a5a8  test    byte ptr [rcx+1Ch], 8
0x18005a5ac  jz      short loc_18005A5CB
0x18005a5ae  cmp     byte ptr [rcx+19h], 2
0x18005a5b2  jb      short loc_18005A5CB
0x18005a5b4  lea     edx, [r15+2Eh]
0x18005a5b8  mov     rcx, [rcx+10h]
0x18005a5bc  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a5c3  mov     r9d, eax
0x18005a5c6  call    WPP_SF_d
0x18005a5cb  mov     rcx, rsi; s
0x18005a5ce  call    cs:__imp_closesocket
0x18005a5d5  nop     dword ptr [rax+rax+00h]
0x18005a5da  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a5e1  cmp     qword ptr [rdi+8], 0
0x18005a5e6  jz      short loc_18005A60A
0x18005a5e8  lock dec dword ptr [rdi]
0x18005a5eb  mov     rcx, [rdi+8]; hObject
0x18005a5ef  call    cs:__imp_CloseHandle
0x18005a5f6  nop     dword ptr [rax+rax+00h]
0x18005a5fb  mov     qword ptr [rdi+8], 0
0x18005a603  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a60a  cmp     rcx, r13
0x18005a60d  jz      short loc_18005A633
0x18005a60f  test    byte ptr [rcx+1Ch], 8
0x18005a613  jz      short loc_18005A633
0x18005a615  cmp     byte ptr [rcx+19h], 6
0x18005a619  jb      short loc_18005A633
0x18005a61b  mov     rcx, [rcx+10h]
0x18005a61f  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a626  mov     edx, 34h ; '4'
0x18005a62b  mov     r9d, ebx
0x18005a62e  call    WPP_SF_d
0x18005a633  mov     eax, ebx
0x18005a635  jmp     short loc_18005A66D
0x18005a637  mov     [rdi+10h], rsi
0x18005a63b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a642  cmp     rcx, r13
0x18005a645  jz      short loc_18005A66B
0x18005a647  test    byte ptr [rcx+1Ch], 8
0x18005a64b  jz      short loc_18005A66B
0x18005a64d  cmp     byte ptr [rcx+19h], 6
0x18005a651  jb      short loc_18005A66B
0x18005a653  mov     rcx, [rcx+10h]
0x18005a657  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18005a65e  mov     edx, 33h ; '3'
0x18005a663  xor     r9d, r9d
0x18005a666  call    WPP_SF_d
0x18005a66b  xor     eax, eax
0x18005a66d  mov     rcx, [rbp+57h+var_30]
0x18005a671  xor     rcx, rsp; StackCookie
0x18005a674  call    __security_check_cookie
0x18005a679  mov     rbx, [rsp+0F0h+arg_10]
0x18005a681  add     rsp, 0D0h
0x18005a688  pop     r15
0x18005a68a  pop     r13
0x18005a68c  pop     rdi
0x18005a68d  pop     rsi
0x18005a68e  pop     rbp
0x18005a68f  retn
```
