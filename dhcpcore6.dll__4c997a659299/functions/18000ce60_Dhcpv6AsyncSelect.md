# Dhcpv6AsyncSelect

- ea: `0x18000ce60`
- end: `0x18000d236`
- name: `Dhcpv6AsyncSelect`
- size: `982`
- prototype: `__int64 __fastcall(SOCKET s)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x180028b08`

## callees

- `0x18000ce60`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800338c0`
- `0x180033900`
- `0x180033de4`

## import_xrefs

- `WS2_32!WSAEnumNetworkEvents` at `0x18000d06f`
- `WS2_32!WSAEnumNetworkEvents` at `0x18000d06f`
- `WS2_32!WSAEventSelect` at `0x18000cedd`
- `WS2_32!WSAEventSelect` at `0x18000cedd`
- `WS2_32!WSACreateEvent` at `0x18000ceb4`
- `WS2_32!WSACreateEvent` at `0x18000ceb4`
- `WS2_32!WSAWaitForMultipleEvents` at `0x18000cf25`
- `WS2_32!WSAWaitForMultipleEvents` at `0x18000cf25`
- `WS2_32!WSACloseEvent` at `0x18000cf62`
- `WS2_32!WSACloseEvent` at `0x18000cf62`
- `WS2_32!__imp_select` at `0x18000d1bb`
- `WS2_32!__imp_select` at `0x18000d1bb`
- `WS2_32!__imp_WSAGetLastError` at `0x18000cfef`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d089`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d0d3`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d1fd`
- `WS2_32!__imp_WSAGetLastError` at `0x18000cfef`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d089`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d0d3`
- `WS2_32!__imp_WSAGetLastError` at `0x18000d1fd`

## pseudocode

```c
__int64 __fastcall Dhcpv6AsyncSelect(SOCKET s, __int64 a2, __int64 a3, __int64 a4)
{
  HANDLE v8; // rax
  DWORD v9; // eax
  unsigned int v10; // ebx
  __int64 v12; // rdx
  unsigned int Error; // eax
  __int64 v14; // rdx
  char v15; // r8
  __int64 v16; // r9
  int v17; // eax
  unsigned int v18; // eax
  timeval timeout; // [rsp+30h] [rbp-288h] BYREF
  _WSANETWORKEVENTS NetworkEvents; // [rsp+38h] [rbp-280h] BYREF
  fd_set readfds; // [rsp+70h] [rbp-248h] BYREF
  __int128 hEvents; // [rsp+280h] [rbp-38h] BYREF
  __int64 v23; // [rsp+290h] [rbp-28h]

  if ( a2 )
  {
    v23 = 0;
    hEvents = 0;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
      WPP_SF_d(1028, 13, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, a4);
    v8 = WSACreateEvent();
    *(_QWORD *)&hEvents = v8;
    if ( !v8 || WSAEventSelect(s, v8, 1) )
    {
      Error = WSAGetLastError();
      v10 = Error;
      if ( (xmmword_1800423E0 & 2) == 0 )
        goto LABEL_11;
      v14 = 14;
      goto LABEL_20;
    }
    *((_QWORD *)&hEvents + 1) = a2;
    if ( a3 )
      v23 = a3;
    v9 = WSAWaitForMultipleEvents((a3 != 0) + 2, (const HANDLE *)&hEvents, 0, a4, 0);
    v10 = v9;
    if ( v9 != -1 )
    {
      switch ( v9 )
      {
        case 0x102u:
          v10 = 121;
          if ( (xmmword_1800423E0 & 2) == 0 )
            break;
          v12 = 16;
          goto LABEL_17;
        case 1u:
          v10 = 1223;
          if ( (xmmword_1800423E0 & 2) != 0 )
          {
            v12 = 17;
LABEL_17:
            WPP_SF_(1025, v12, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids);
            break;
          }
          break;
        case 2u:
          if ( a3 )
          {
            v10 = 1223;
            if ( (xmmword_1800423E0 & 2) != 0 )
            {
              v12 = 18;
              goto LABEL_17;
            }
          }
          break;
        default:
          if ( v9 )
            break;
          memset(&NetworkEvents, 0, sizeof(NetworkEvents));
          if ( WSAEnumNetworkEvents(s, 0, &NetworkEvents) != -1 )
          {
            v10 = NetworkEvents.iErrorCode[0];
            break;
          }
          Error = WSAGetLastError();
          v10 = Error;
          if ( (xmmword_1800423E0 & 2) != 0 )
          {
            v14 = 19;
            goto LABEL_20;
          }
          break;
      }
LABEL_11:
      if ( (_QWORD)hEvents )
        WSACloseEvent((HANDLE)hEvents);
      goto LABEL_13;
    }
    Error = WSAGetLastError();
    v10 = Error;
    if ( (xmmword_1800423E0 & 2) == 0 )
      goto LABEL_11;
    v14 = 15;
LABEL_20:
    WPP_SF_D(1025, v14, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, Error);
    goto LABEL_11;
  }
  v10 = 0;
  *(&readfds.fd_count + 1) = 0;
  timeout = 0;
  memset_0(&readfds, 0, 0x204u);
  v15 = xmmword_1800423E0;
  v16 = (unsigned int)a4;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_d(1028, 20, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, (unsigned int)a4);
    v15 = xmmword_1800423E0;
    v16 = (unsigned int)a4;
  }
  readfds.fd_array[0] = s;
  readfds.fd_count = 1;
  timeout.tv_sec = a4 / 1000;
  timeout.tv_usec = 1000 * (v16 - 1000 * timeout.tv_sec);
  if ( (v15 & 0x10) != 0 )
    WPP_SF_d(1028, 21, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, v16);
  v17 = select(0, &readfds, 0, 0, &timeout);
  if ( v17 )
  {
    if ( v17 == -1 )
    {
      v18 = WSAGetLastError();
      v10 = v18;
      if ( (xmmword_1800423E0 & 2) == 0 )
        return v10;
      WPP_SF_D(1025, 23, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, v18);
    }
  }
  else
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_(1025, 22, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids);
    v10 = 121;
  }
LABEL_13:
  if ( (xmmword_1800423E0 & 2) != 0 )
    WPP_SF_D(1025, 24, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18000ce60  mov     r11, rsp
0x18000ce63  mov     [r11+10h], rbx
0x18000ce67  push    rsi
0x18000ce68  push    rdi
0x18000ce69  push    r14
0x18000ce6b  sub     rsp, 2A0h
0x18000ce72  mov     rax, cs:__security_cookie
0x18000ce79  xor     rax, rsp
0x18000ce7c  mov     [rsp+2B8h+var_20], rax
0x18000ce84  xor     eax, eax
0x18000ce86  mov     rsi, r9
0x18000ce89  mov     rdi, r8
0x18000ce8c  mov     rbx, rdx
0x18000ce8f  mov     r14, rcx
0x18000ce92  test    rdx, rdx
0x18000ce95  jz      loc_18000D0F8
0x18000ce9b  xorps   xmm0, xmm0
0x18000ce9e  mov     [r11-28h], rax
0x18000cea2  movups  xmmword ptr [r11-38h], xmm0
0x18000cea7  test    byte ptr cs:xmmword_1800423E0, 10h
0x18000ceae  jnz     loc_18000CFB9
0x18000ceb4  call    cs:__imp_WSACreateEvent
0x18000cebb  nop     dword ptr [rax+rax+00h]
0x18000cec0  mov     [rsp+2B8h+hEvents], rax
0x18000cec8  test    rax, rax
0x18000cecb  jz      loc_18000CFEF
0x18000ced1  mov     r8d, 1; lNetworkEvents
0x18000ced7  mov     rdx, rax; hEventObject
0x18000ceda  mov     rcx, r14; s
0x18000cedd  call    cs:__imp_WSAEventSelect
0x18000cee4  nop     dword ptr [rax+rax+00h]
0x18000cee9  test    eax, eax
0x18000ceeb  jnz     loc_18000CFEF
0x18000cef1  mov     [rsp+2B8h+var_30], rbx
0x18000cef9  test    rdi, rdi
0x18000cefc  jz      short loc_18000CF06
0x18000cefe  mov     [rsp+2B8h+var_28], rdi
0x18000cf06  xor     ebx, ebx
0x18000cf08  lea     rdx, [rsp+2B8h+hEvents]; lphEvents
0x18000cf10  mov     ecx, ebx
0x18000cf12  mov     [rsp+2B8h+fAlertable], ebx; fAlertable
0x18000cf16  test    rdi, rdi
0x18000cf19  mov     r9d, esi; dwTimeout
0x18000cf1c  setnz   cl
0x18000cf1f  xor     r8d, r8d; fWaitAll
0x18000cf22  add     ecx, 2; cEvents
0x18000cf25  call    cs:__imp_WSAWaitForMultipleEvents
0x18000cf2c  nop     dword ptr [rax+rax+00h]
0x18000cf31  mov     ebx, eax
0x18000cf33  cmp     eax, 0FFFFFFFFh
0x18000cf36  jz      loc_18000D089
0x18000cf3c  cmp     eax, 102h
0x18000cf41  jnz     loc_18000D028
0x18000cf47  mov     ebx, 79h ; 'y'
0x18000cf4c  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cf53  jnz     short loc_18000CFD4
0x18000cf55  mov     rcx, [rsp+2B8h+hEvents]; hEvent
0x18000cf5d  test    rcx, rcx
0x18000cf60  jz      short loc_18000CF6E
0x18000cf62  call    cs:__imp_WSACloseEvent
0x18000cf69  nop     dword ptr [rax+rax+00h]
0x18000cf6e  test    byte ptr cs:xmmword_1800423E0, 2
0x18000cf75  jnz     short loc_18000CF9E
0x18000cf77  mov     eax, ebx
0x18000cf79  mov     rcx, [rsp+2B8h+var_20]
0x18000cf81  xor     rcx, rsp; StackCookie
0x18000cf84  call    __security_check_cookie
0x18000cf89  mov     rbx, [rsp+2B8h+arg_8]
0x18000cf91  add     rsp, 2A0h
0x18000cf98  pop     r14
0x18000cf9a  pop     rdi
0x18000cf9b  pop     rsi
0x18000cf9c  retn
0x18000cf9e  mov     edx, 18h
0x18000cfa3  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000cfaa  mov     ecx, 401h
0x18000cfaf  mov     r9d, ebx
0x18000cfb2  call    WPP_SF_D
0x18000cfb7  jmp     short loc_18000CF77
0x18000cfb9  mov     edx, 0Dh
0x18000cfbe  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000cfc5  mov     ecx, 404h
0x18000cfca  call    WPP_SF_d
0x18000cfcf  jmp     loc_18000CEB4
0x18000cfd4  mov     edx, 10h
0x18000cfd9  mov     ecx, 401h
0x18000cfde  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000cfe5  call    WPP_SF_
0x18000cfea  jmp     loc_18000CF55
0x18000cfef  call    cs:__imp_WSAGetLastError
0x18000cff6  nop     dword ptr [rax+rax+00h]
0x18000cffb  mov     ebx, eax
0x18000cffd  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d004  jz      loc_18000CF55
0x18000d00a  mov     edx, 0Eh
0x18000d00f  mov     r9d, eax
0x18000d012  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000d019  mov     ecx, 401h
0x18000d01e  call    WPP_SF_D
0x18000d023  jmp     loc_18000CF55
0x18000d028  cmp     eax, 1
0x18000d02b  jnz     short loc_18000D046
0x18000d02d  mov     ebx, 4C7h
0x18000d032  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d039  jz      loc_18000CF55
0x18000d03f  mov     edx, 11h
0x18000d044  jmp     short loc_18000CFD9
0x18000d046  cmp     eax, 2
0x18000d049  jz      short loc_18000D0AE
0x18000d04b  test    eax, eax
0x18000d04d  jnz     loc_18000CF55
0x18000d053  xorps   xmm0, xmm0
0x18000d056  lea     r8, [rsp+2B8h+NetworkEvents]; lpNetworkEvents
0x18000d05b  movups  xmmword ptr [rsp+2B8h+NetworkEvents.iErrorCode+0Ch], xmm0
0x18000d060  xor     edx, edx; hEventObject
0x18000d062  mov     rcx, r14; s
0x18000d065  movups  xmmword ptr [rsp+2B8h+NetworkEvents.iErrorCode+18h], xmm0
0x18000d06a  movups  xmmword ptr [rsp+2B8h+NetworkEvents.lNetworkEvents], xmm0
0x18000d06f  call    cs:__imp_WSAEnumNetworkEvents
0x18000d076  nop     dword ptr [rax+rax+00h]
0x18000d07b  cmp     eax, 0FFFFFFFFh
0x18000d07e  jz      short loc_18000D0D3
0x18000d080  mov     ebx, [rsp+2B8h+NetworkEvents.iErrorCode]
0x18000d084  jmp     loc_18000CF55
0x18000d089  call    cs:__imp_WSAGetLastError
0x18000d090  nop     dword ptr [rax+rax+00h]
0x18000d095  mov     ebx, eax
0x18000d097  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d09e  jz      loc_18000CF55
0x18000d0a4  mov     edx, 0Fh
0x18000d0a9  jmp     loc_18000D00F
0x18000d0ae  test    rdi, rdi
0x18000d0b1  jz      loc_18000CF55
0x18000d0b7  mov     ebx, 4C7h
0x18000d0bc  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d0c3  jz      loc_18000CF55
0x18000d0c9  mov     edx, 12h
0x18000d0ce  jmp     loc_18000CFD9
0x18000d0d3  call    cs:__imp_WSAGetLastError
0x18000d0da  nop     dword ptr [rax+rax+00h]
0x18000d0df  mov     ebx, eax
0x18000d0e1  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d0e8  jz      loc_18000CF55
0x18000d0ee  mov     edx, 13h
0x18000d0f3  jmp     loc_18000D00F
0x18000d0f8  xor     ebx, ebx
0x18000d0fa  mov     dword ptr [rsp+2B8h+readfds+4], eax
0x18000d0fe  xor     edx, edx; Val
0x18000d100  mov     qword ptr [rsp+2B8h+timeout.tv_sec], rbx
0x18000d105  mov     r8d, 204h; Size
0x18000d10b  lea     rcx, [rsp+2B8h+readfds]; void *
0x18000d110  call    memset_0
0x18000d115  movzx   r8d, byte ptr cs:xmmword_1800423E0
0x18000d11d  mov     r9d, esi
0x18000d120  test    r8b, 10h
0x18000d124  jz      short loc_18000D147
0x18000d126  mov     edx, 14h
0x18000d12b  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000d132  mov     ecx, 404h
0x18000d137  call    WPP_SF_d
0x18000d13c  movzx   r8d, byte ptr cs:xmmword_1800423E0
0x18000d144  mov     r9d, esi
0x18000d147  mov     rax, 20C49BA5E353F7CFh
0x18000d151  mov     [rsp+2B8h+readfds.fd_array], r14
0x18000d156  imul    rsi
0x18000d159  mov     ecx, r9d
0x18000d15c  mov     [rsp+2B8h+readfds.fd_count], 1
0x18000d164  sar     rdx, 7
0x18000d168  mov     rax, rdx
0x18000d16b  shr     rax, 3Fh
0x18000d16f  add     rdx, rax
0x18000d172  imul    eax, edx, 3E8h
0x18000d178  mov     [rsp+2B8h+timeout.tv_sec], edx
0x18000d17c  sub     ecx, eax
0x18000d17e  imul    eax, ecx, 3E8h
0x18000d184  mov     [rsp+2B8h+timeout.tv_usec], eax
0x18000d188  test    r8b, 10h
0x18000d18c  jz      short loc_18000D1A4
0x18000d18e  mov     edx, 15h
0x18000d193  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000d19a  mov     ecx, 404h
0x18000d19f  call    WPP_SF_d
0x18000d1a4  lea     rax, [rsp+2B8h+timeout]
0x18000d1a9  xor     r9d, r9d; exceptfds
0x18000d1ac  xor     r8d, r8d; writefds
0x18000d1af  mov     qword ptr [rsp+2B8h+fAlertable], rax; timeout
0x18000d1b4  lea     rdx, [rsp+2B8h+readfds]; readfds
0x18000d1b9  xor     ecx, ecx; nfds
0x18000d1bb  call    cs:__imp_select
0x18000d1c2  nop     dword ptr [rax+rax+00h]
0x18000d1c7  test    eax, eax
0x18000d1c9  jnz     short loc_18000D1F4
0x18000d1cb  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d1d2  jz      short loc_18000D1EA
0x18000d1d4  mov     edx, 16h
0x18000d1d9  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000d1e0  mov     ecx, 401h
0x18000d1e5  call    WPP_SF_
0x18000d1ea  mov     ebx, 79h ; 'y'
0x18000d1ef  jmp     loc_18000CF6E
0x18000d1f4  cmp     eax, 0FFFFFFFFh
0x18000d1f7  jnz     loc_18000CF6E
0x18000d1fd  call    cs:__imp_WSAGetLastError
0x18000d204  nop     dword ptr [rax+rax+00h]
0x18000d209  mov     ebx, eax
0x18000d20b  test    byte ptr cs:xmmword_1800423E0, 2
0x18000d212  jz      loc_18000CF77
0x18000d218  mov     edx, 17h
0x18000d21d  lea     r8, WPP_47aa4825a08c3bf45f218732aa18bd06_Traceguids
0x18000d224  mov     ecx, 401h
0x18000d229  mov     r9d, eax
0x18000d22c  call    WPP_SF_D
0x18000d231  jmp     loc_18000CF6E
```
