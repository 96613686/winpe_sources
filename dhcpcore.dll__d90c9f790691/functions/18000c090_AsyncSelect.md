# AsyncSelect

- ea: `0x18000c090`
- end: `0x18000c3ea`
- name: `AsyncSelect`
- size: `858`
- prototype: `__int64 __fastcall(SOCKET s, void *, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000bc40`
- `0x1800261d4`

## callees

- `0x18000c090`
- `0x18001cef0`
- `0x18001d826`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d9e8`

## import_xrefs

- `WS2_32!WSACreateEvent` at `0x18000c0fb`
- `WS2_32!WSACreateEvent` at `0x18000c0fb`
- `WS2_32!WSAEventSelect` at `0x18000c11b`
- `WS2_32!WSAEventSelect` at `0x18000c11b`
- `WS2_32!WSAWaitForMultipleEvents` at `0x18000c140`
- `WS2_32!WSAWaitForMultipleEvents` at `0x18000c140`
- `WS2_32!WSAEnumNetworkEvents` at `0x18000c185`
- `WS2_32!WSAEnumNetworkEvents` at `0x18000c185`
- `WS2_32!WSACloseEvent` at `0x18000c1b9`
- `WS2_32!WSACloseEvent` at `0x18000c1b9`
- `WS2_32!__imp_select` at `0x18000c37b`
- `WS2_32!__imp_select` at `0x18000c37b`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c19a`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c22e`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c263`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c3b7`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c19a`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c22e`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c263`
- `WS2_32!__imp_WSAGetLastError` at `0x18000c3b7`

## pseudocode

```c
__int64 __fastcall AsyncSelect(SOCKET s, void *a2, unsigned __int64 a3)
{
  HANDLE v6; // rax
  DWORD v7; // eax
  unsigned int v8; // ebx
  unsigned int Error; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  char v13; // r9
  int v14; // eax
  unsigned int v15; // eax
  HANDLE hEvents[2]; // [rsp+30h] [rbp-268h] BYREF
  _WSANETWORKEVENTS NetworkEvents; // [rsp+40h] [rbp-258h] BYREF
  fd_set readfds; // [rsp+70h] [rbp-228h] BYREF

  if ( a2 )
  {
    *(_OWORD *)hEvents = 0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 24, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, (unsigned int)a3 / 0x3E8);
    v6 = WSACreateEvent();
    hEvents[0] = v6;
    if ( v6 && !WSAEventSelect(s, v6, 1) )
    {
      hEvents[1] = a2;
      v7 = WSAWaitForMultipleEvents(2u, hEvents, 0, a3, 0);
      v8 = v7;
      switch ( v7 )
      {
        case 0xFFFFFFFF:
          Error = WSAGetLastError();
          v8 = Error;
          if ( (xmmword_1800616A0 & 2) == 0 )
            goto LABEL_13;
          v12 = 26;
          goto LABEL_28;
        case 0x102u:
          v8 = 121;
          if ( (xmmword_1800616A0 & 2) == 0 )
            goto LABEL_13;
          v11 = 27;
          break;
        case 1u:
          v8 = 1223;
          if ( (xmmword_1800616A0 & 2) == 0 )
            goto LABEL_13;
          v11 = 28;
          break;
        default:
          if ( v7 )
            goto LABEL_13;
          memset(&NetworkEvents, 0, sizeof(NetworkEvents));
          if ( WSAEnumNetworkEvents(s, 0, &NetworkEvents) != -1 )
          {
            v8 = NetworkEvents.iErrorCode[0];
            goto LABEL_13;
          }
          Error = WSAGetLastError();
          v8 = Error;
          if ( (xmmword_1800616A0 & 2) == 0 )
          {
LABEL_13:
            if ( hEvents[0] )
              WSACloseEvent(hEvents[0]);
            goto LABEL_15;
          }
          v12 = 29;
LABEL_28:
          WPP_SF_D(1025, v12, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, Error);
          goto LABEL_13;
      }
      WPP_SF_(1025, v11, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids);
      goto LABEL_13;
    }
    Error = WSAGetLastError();
    v8 = Error;
    if ( (xmmword_1800616A0 & 2) == 0 )
      goto LABEL_13;
    v12 = 25;
    goto LABEL_28;
  }
  v8 = 0;
  hEvents[0] = 0;
  *(&readfds.fd_count + 1) = 0;
  memset_0(&readfds, 0, 0x204u);
  v13 = xmmword_1800616A0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
  {
    WPP_SF_d(1028, 30, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, (unsigned int)a3 / 0x3E8);
    v13 = xmmword_1800616A0;
  }
  readfds.fd_array[0] = s;
  readfds.fd_count = 1;
  LODWORD(hEvents[0]) = a3 / 0x3E8;
  HIDWORD(hEvents[0]) = 1000 * (a3 % 0x3E8);
  if ( (v13 & 0x10) != 0 )
    WPP_SF_d(1028, 31, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, (unsigned int)a3 / 0x3E8);
  v14 = select(0, &readfds, 0, 0, (const struct timeval *)hEvents);
  if ( v14 )
  {
    if ( v14 == -1 )
    {
      v15 = WSAGetLastError();
      v8 = v15;
      if ( (xmmword_1800616A0 & 2) == 0 )
        return v8;
      WPP_SF_D(1025, 33, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v15);
    }
  }
  else
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_(1025, 32, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids);
    v8 = 121;
  }
LABEL_15:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 34, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v8);
  return v8;
}

```

## disassembly

```asm
0x18000c090  mov     [rsp+arg_8], rbx
0x18000c095  mov     [rsp+arg_18], rsi
0x18000c09a  push    rdi
0x18000c09b  sub     rsp, 290h
0x18000c0a2  mov     rax, cs:__security_cookie
0x18000c0a9  xor     rax, rsp
0x18000c0ac  mov     [rsp+298h+var_18], rax
0x18000c0b4  mov     rdi, r8
0x18000c0b7  mov     rbx, rdx
0x18000c0ba  mov     rsi, rcx
0x18000c0bd  test    rdx, rdx
0x18000c0c0  jz      loc_18000C29D
0x18000c0c6  xorps   xmm0, xmm0
0x18000c0c9  movups  xmmword ptr [rsp+298h+hEvents], xmm0
0x18000c0ce  test    byte ptr cs:xmmword_1800616A0, 10h
0x18000c0d5  jz      short loc_18000C0FB
0x18000c0d7  mov     eax, 10624DD3h
0x18000c0dc  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c0e3  mul     edi
0x18000c0e5  mov     ecx, 404h
0x18000c0ea  mov     r9d, edx
0x18000c0ed  mov     edx, 18h
0x18000c0f2  shr     r9d, 6
0x18000c0f6  call    WPP_SF_d
0x18000c0fb  call    cs:__imp_WSACreateEvent
0x18000c101  mov     [rsp+298h+hEvents], rax
0x18000c106  test    rax, rax
0x18000c109  jz      loc_18000C19A
0x18000c10f  mov     r8d, 1; lNetworkEvents
0x18000c115  mov     rdx, rax; hEventObject
0x18000c118  mov     rcx, rsi; s
0x18000c11b  call    cs:__imp_WSAEventSelect
0x18000c121  test    eax, eax
0x18000c123  jnz     short loc_18000C19A
0x18000c125  mov     [rsp+298h+hEvents+8], rbx
0x18000c12a  lea     rdx, [rsp+298h+hEvents]; lphEvents
0x18000c12f  xor     ebx, ebx
0x18000c131  mov     r9d, edi; dwTimeout
0x18000c134  xor     r8d, r8d; fWaitAll
0x18000c137  mov     [rsp+298h+fAlertable], ebx; fAlertable
0x18000c13b  mov     ecx, 2; cEvents
0x18000c140  call    cs:__imp_WSAWaitForMultipleEvents
0x18000c146  mov     ebx, eax
0x18000c148  cmp     eax, 0FFFFFFFFh
0x18000c14b  jz      loc_18000C22E
0x18000c151  cmp     eax, 102h
0x18000c156  jz      loc_18000C208
0x18000c15c  cmp     eax, 1
0x18000c15f  jz      loc_18000C24A
0x18000c165  test    eax, eax
0x18000c167  jnz     short loc_18000C1AF
0x18000c169  xorps   xmm0, xmm0
0x18000c16c  lea     r8, [rsp+298h+NetworkEvents]; lpNetworkEvents
0x18000c171  movups  xmmword ptr [rsp+298h+NetworkEvents.iErrorCode+0Ch], xmm0
0x18000c176  xor     edx, edx; hEventObject
0x18000c178  mov     rcx, rsi; s
0x18000c17b  movups  xmmword ptr [rsp+298h+NetworkEvents.iErrorCode+18h], xmm0
0x18000c180  movups  xmmword ptr [rsp+298h+NetworkEvents.lNetworkEvents], xmm0
0x18000c185  call    cs:__imp_WSAEnumNetworkEvents
0x18000c18b  cmp     eax, 0FFFFFFFFh
0x18000c18e  jz      loc_18000C263
0x18000c194  mov     ebx, [rsp+298h+NetworkEvents.iErrorCode]
0x18000c198  jmp     short loc_18000C1AF
0x18000c19a  call    cs:__imp_WSAGetLastError
0x18000c1a0  mov     ebx, eax
0x18000c1a2  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c1a9  jnz     loc_18000C27F
0x18000c1af  mov     rcx, [rsp+298h+hEvents]; hEvent
0x18000c1b4  test    rcx, rcx
0x18000c1b7  jz      short loc_18000C1BF
0x18000c1b9  call    cs:__imp_WSACloseEvent
0x18000c1bf  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c1c6  jz      short loc_18000C1E1
0x18000c1c8  mov     edx, 22h ; '"'
0x18000c1cd  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c1d4  mov     ecx, 401h
0x18000c1d9  mov     r9d, ebx
0x18000c1dc  call    WPP_SF_D
0x18000c1e1  mov     eax, ebx
0x18000c1e3  mov     rcx, [rsp+298h+var_18]
0x18000c1eb  xor     rcx, rsp; StackCookie
0x18000c1ee  call    __security_check_cookie
0x18000c1f3  lea     r11, [rsp+298h+var_8]
0x18000c1fb  mov     rbx, [r11+18h]
0x18000c1ff  mov     rsi, [r11+28h]
0x18000c203  mov     rsp, r11
0x18000c206  pop     rdi
0x18000c207  retn
0x18000c208  mov     ebx, 79h ; 'y'
0x18000c20d  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c214  jz      short loc_18000C1AF
0x18000c216  mov     edx, 1Bh
0x18000c21b  mov     ecx, 401h
0x18000c220  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c227  call    WPP_SF_
0x18000c22c  jmp     short loc_18000C1AF
0x18000c22e  call    cs:__imp_WSAGetLastError
0x18000c234  mov     ebx, eax
0x18000c236  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c23d  jz      loc_18000C1AF
0x18000c243  mov     edx, 1Ah
0x18000c248  jmp     short loc_18000C284
0x18000c24a  mov     ebx, 4C7h
0x18000c24f  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c256  jz      loc_18000C1AF
0x18000c25c  mov     edx, 1Ch
0x18000c261  jmp     short loc_18000C21B
0x18000c263  call    cs:__imp_WSAGetLastError
0x18000c269  mov     ebx, eax
0x18000c26b  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c272  jz      loc_18000C1AF
0x18000c278  mov     edx, 1Dh
0x18000c27d  jmp     short loc_18000C284
0x18000c27f  mov     edx, 19h
0x18000c284  mov     r9d, eax
0x18000c287  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c28e  mov     ecx, 401h
0x18000c293  call    WPP_SF_D
0x18000c298  jmp     loc_18000C1AF
0x18000c29d  xor     ebx, ebx
0x18000c29f  lea     rcx, [rsp+298h+readfds]; void *
0x18000c2a4  xor     eax, eax
0x18000c2a6  mov     [rsp+298h+hEvents], rbx
0x18000c2ab  xor     edx, edx; Val
0x18000c2ad  mov     dword ptr [rsp+298h+readfds+4], eax
0x18000c2b1  mov     r8d, 204h; Size
0x18000c2b7  call    memset_0
0x18000c2bc  movzx   r9d, byte ptr cs:xmmword_1800616A0
0x18000c2c4  test    r9b, 10h
0x18000c2c8  jz      short loc_18000C2F6
0x18000c2ca  mov     eax, 10624DD3h
0x18000c2cf  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c2d6  mul     edi
0x18000c2d8  mov     ecx, 404h
0x18000c2dd  mov     r9d, edx
0x18000c2e0  mov     edx, 1Eh
0x18000c2e5  shr     r9d, 6
0x18000c2e9  call    WPP_SF_d
0x18000c2ee  movzx   r9d, byte ptr cs:xmmword_1800616A0
0x18000c2f6  mov     r8d, edi
0x18000c2f9  mov     [rsp+298h+readfds.fd_array], rsi
0x18000c2fe  mov     rax, 624DD2F1A9FBE77h
0x18000c308  mov     [rsp+298h+readfds.fd_count], 1
0x18000c310  mul     rdi
0x18000c313  mov     ecx, r8d
0x18000c316  sub     rdi, rdx
0x18000c319  shr     rdi, 1
0x18000c31c  add     rdi, rdx
0x18000c31f  shr     rdi, 9
0x18000c323  imul    eax, edi, 3E8h
0x18000c329  mov     dword ptr [rsp+298h+hEvents], edi
0x18000c32d  sub     ecx, eax
0x18000c32f  imul    eax, ecx, 3E8h
0x18000c335  mov     dword ptr [rsp+298h+hEvents+4], eax
0x18000c339  test    r9b, 10h
0x18000c33d  jz      short loc_18000C364
0x18000c33f  mov     eax, 10624DD3h
0x18000c344  mov     ecx, 404h
0x18000c349  mul     r8d
0x18000c34c  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c353  mov     r9d, edx
0x18000c356  mov     edx, 1Fh
0x18000c35b  shr     r9d, 6
0x18000c35f  call    WPP_SF_d
0x18000c364  lea     rax, [rsp+298h+hEvents]
0x18000c369  xor     r9d, r9d; exceptfds
0x18000c36c  xor     r8d, r8d; writefds
0x18000c36f  mov     qword ptr [rsp+298h+fAlertable], rax; timeout
0x18000c374  lea     rdx, [rsp+298h+readfds]; readfds
0x18000c379  xor     ecx, ecx; nfds
0x18000c37b  call    cs:__imp_select
0x18000c381  test    eax, eax
0x18000c383  jnz     short loc_18000C3AE
0x18000c385  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c38c  jz      short loc_18000C3A4
0x18000c38e  mov     edx, 20h ; ' '
0x18000c393  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c39a  mov     ecx, 401h
0x18000c39f  call    WPP_SF_
0x18000c3a4  mov     ebx, 79h ; 'y'
0x18000c3a9  jmp     loc_18000C1BF
0x18000c3ae  cmp     eax, 0FFFFFFFFh
0x18000c3b1  jnz     loc_18000C1BF
0x18000c3b7  call    cs:__imp_WSAGetLastError
0x18000c3bd  mov     ebx, eax
0x18000c3bf  test    byte ptr cs:xmmword_1800616A0, 2
0x18000c3c6  jz      loc_18000C1E1
0x18000c3cc  mov     edx, 21h ; '!'
0x18000c3d1  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18000c3d8  mov     ecx, 401h
0x18000c3dd  mov     r9d, eax
0x18000c3e0  call    WPP_SF_D
0x18000c3e5  jmp     loc_18000C1BF
```
