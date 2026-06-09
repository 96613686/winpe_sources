# NhCreateDatagramSocket(sockaddr_storage *,_NH_RCSOCKET *)

- ea: `0x18002aaa0`
- end: `0x18002af11`
- name: `?NhCreateDatagramSocket@@YAKPEAUsockaddr_storage@@PEAU_NH_RCSOCKET@@@Z`
- size: `1137`
- prototype: `unsigned int __fastcall(LPSOCKADDR lpsaAddress, struct _NH_RCSOCKET *)`
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180024c90`
- `0x180025dd8`
- `0x180029e34`
- `0x18002a1b8`
- `0x18002a53c`
- `0x180044020`
- `0x18007dad0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x18000f250`
- `0x18002aaa0`
- `0x18003b850`
- `0x18003e6ec`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ab10`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ab10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ace7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ad82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002aeab`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18002ab67`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18002ab67`
- `WS2_32!WSASocketW` at `0x18002ab47`
- `WS2_32!WSASocketW` at `0x18002ab47`
- `WS2_32!WSAIoctl` at `0x18002ac00`
- `WS2_32!WSAIoctl` at `0x18002ac00`
- `WS2_32!WSAAddressToStringA` at `0x18002ac5f`
- `WS2_32!WSAAddressToStringA` at `0x18002ae53`
- `WS2_32!WSAAddressToStringA` at `0x18002ac5f`
- `WS2_32!WSAAddressToStringA` at `0x18002ae53`
- `WS2_32!__imp_bind` at `0x18002ac1c`
- `WS2_32!__imp_bind` at `0x18002ac1c`
- `WS2_32!__imp_closesocket` at `0x18002ae92`
- `WS2_32!__imp_closesocket` at `0x18002ae92`
- `WS2_32!__imp_setsockopt` at `0x18002ab98`
- `WS2_32!__imp_setsockopt` at `0x18002abc1`
- `WS2_32!__imp_setsockopt` at `0x18002ab98`
- `WS2_32!__imp_setsockopt` at `0x18002abc1`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ad5c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ade7`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ad5c`
- `WS2_32!__imp_WSAGetLastError` at `0x18002ade7`

## pseudocode

```c
__int64 __fastcall NhCreateDatagramSocket(LPSOCKADDR lpsaAddress, struct _NH_RCSOCKET *a2)
{
  HANDLE EventW; // rax
  void *v5; // rax
  void *v6; // rbx
  DWORD v8; // eax
  unsigned int v9; // ebp
  PVOID *v10; // rcx
  __int64 v11; // rdx
  DWORD LastError; // eax
  unsigned int Error; // eax
  char optval[4]; // [rsp+50h] [rbp-98h] BYREF
  DWORD dwAddressStringLength; // [rsp+54h] [rbp-94h] BYREF
  DWORD cbBytesReturned; // [rsp+58h] [rbp-90h] BYREF
  CHAR szAddressString[80]; // [rsp+60h] [rbp-88h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  *(_DWORD *)optval = 0;
  cbBytesReturned = 0;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a2 + 1) = EventW;
  if ( EventW )
  {
    *(_DWORD *)a2 = 2;
    v5 = (void *)WSASocketW(lpsaAddress->sa_family, 2, 17, 0, 0, 1u);
    v6 = v5;
    if ( v5 != (void *)-1LL )
    {
      if ( BindIoCompletionCallback(v5, NhpIoCompletionRoutine, 0) )
      {
        *(_DWORD *)optval = 1;
        setsockopt((SOCKET)v6, 0xFFFF, 4, optval, 4);
        *(_DWORD *)optval = 1;
        setsockopt((SOCKET)v6, 0xFFFF, 32, optval, 4);
        *(_DWORD *)optval = 1;
        WSAIoctl((SOCKET)v6, 0x98000007, optval, 4u, 0, 0, &cbBytesReturned, 0, 0);
        if ( lpsaAddress->sa_family == 2 && *(_WORD *)lpsaAddress->sa_data == 13568 )
          SetSdOnDnsSocket(v6);
        if ( bind((SOCKET)v6, lpsaAddress, 128) != -1 )
        {
          dwAddressStringLength = 65;
          memset_0(szAddressString, 0, 0x41u);
          WSAAddressToStringA(lpsaAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            WPP_SF_s(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              133,
              &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
              szAddressString);
          }
          *((_QWORD *)a2 + 2) = v6;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
          }
          return 0;
        }
        Error = WSAGetLastError();
        v9 = Error;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
        }
        dwAddressStringLength = 65;
        memset_0(szAddressString, 0, 0x41u);
        WSAAddressToStringA(lpsaAddress, 0x80u, 0, szAddressString, &dwAddressStringLength);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            36,
            (unsigned int)&WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
            (unsigned int)szAddressString,
            v9);
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 34, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
        }
      }
      closesocket((SOCKET)v6);
      goto LABEL_47;
    }
    v8 = WSAGetLastError();
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v11 = 33;
  }
  else
  {
    v8 = GetLastError();
    v9 = v8;
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_20;
    }
    v11 = 32;
  }
  WPP_SF_d(v10[2], v11, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v8);
LABEL_47:
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_20:
  if ( *((_QWORD *)a2 + 1) )
  {
    _InterlockedDecrement((volatile signed __int32 *)a2);
    CloseHandle(*((HANDLE *)a2 + 1));
    *((_QWORD *)a2 + 1) = 0;
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 8) != 0 && *((_BYTE *)v10 + 25) >= 6u )
    WPP_SF_d(v10[2], 38, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v9);
  return v9;
}

```

## disassembly

```asm
0x18002aaa0  push    rsi
0x18002aaa2  push    rdi
0x18002aaa3  push    r14
0x18002aaa5  push    r15
0x18002aaa7  sub     rsp, 0C8h
0x18002aaae  mov     rax, cs:__security_cookie
0x18002aab5  xor     rax, rsp
0x18002aab8  mov     [rsp+0E8h+var_38], rax
0x18002aac0  mov     rdi, rdx
0x18002aac3  mov     rsi, rcx
0x18002aac6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aacd  lea     r15, WPP_GLOBAL_Control
0x18002aad4  cmp     rcx, r15
0x18002aad7  jz      short loc_18002AAE9
0x18002aad9  test    byte ptr [rcx+1Ch], 8
0x18002aadd  jz      short loc_18002AAE9
0x18002aadf  cmp     byte ptr [rcx+19h], 6
0x18002aae3  jnb     loc_18002AD12
0x18002aae9  xor     r14d, r14d
0x18002aaec  mov     [rsp+0E8h+arg_10], rbx
0x18002aaf4  xor     r9d, r9d; lpName
0x18002aaf7  mov     dword ptr [rsp+0E8h+optval], r14d
0x18002aafc  xor     r8d, r8d; bInitialState
0x18002aaff  mov     [rsp+0E8h+cbBytesReturned], r14d
0x18002ab04  xor     edx, edx; bManualReset
0x18002ab06  mov     [rsp+0E8h+var_28], rbp
0x18002ab0e  xor     ecx, ecx; lpEventAttributes
0x18002ab10  call    cs:__imp_CreateEventW
0x18002ab16  mov     [rdi+8], rax
0x18002ab1a  test    rax, rax
0x18002ab1d  jz      loc_18002ACE7
0x18002ab23  mov     dword ptr [rdi], 2
0x18002ab29  xor     r9d, r9d; lpProtocolInfo
0x18002ab2c  movzx   ecx, word ptr [rsi]; af
0x18002ab2f  mov     edx, 2; type
0x18002ab34  mov     [rsp+0E8h+dwFlags], 1; dwFlags
0x18002ab3c  mov     r8d, 11h; protocol
0x18002ab42  mov     [rsp+0E8h+g], r14d; g
0x18002ab47  call    cs:__imp_WSASocketW
0x18002ab4d  mov     rbx, rax
0x18002ab50  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002ab54  jz      loc_18002AD5C
0x18002ab5a  xor     r8d, r8d; Flags
0x18002ab5d  lea     rdx, ?NhpIoCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x18002ab64  mov     rcx, rax; FileHandle
0x18002ab67  call    cs:__imp_BindIoCompletionCallback
0x18002ab6d  test    eax, eax
0x18002ab6f  jz      loc_18002AD82
0x18002ab75  lea     r9, [rsp+0E8h+optval]; optval
0x18002ab7a  mov     dword ptr [rsp+0E8h+optval], 1
0x18002ab82  mov     edx, 0FFFFh; level
0x18002ab87  mov     [rsp+0E8h+g], 4; optlen
0x18002ab8f  mov     r8d, 4; optname
0x18002ab95  mov     rcx, rbx; s
0x18002ab98  call    cs:__imp_setsockopt
0x18002ab9e  lea     r9, [rsp+0E8h+optval]; optval
0x18002aba3  mov     dword ptr [rsp+0E8h+optval], 1
0x18002abab  mov     edx, 0FFFFh; level
0x18002abb0  mov     [rsp+0E8h+g], 4; optlen
0x18002abb8  mov     r8d, 20h ; ' '; optname
0x18002abbe  mov     rcx, rbx; s
0x18002abc1  call    cs:__imp_setsockopt
0x18002abc7  mov     [rsp+0E8h+lpCompletionRoutine], r14; lpCompletionRoutine
0x18002abcc  lea     rax, [rsp+0E8h+cbBytesReturned]
0x18002abd1  mov     [rsp+0E8h+lpOverlapped], r14; lpOverlapped
0x18002abd6  lea     r8, [rsp+0E8h+optval]; lpvInBuffer
0x18002abdb  mov     [rsp+0E8h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18002abe0  mov     r9d, 4; cbInBuffer
0x18002abe6  mov     [rsp+0E8h+dwFlags], r14d; cbOutBuffer
0x18002abeb  mov     edx, 98000007h; dwIoControlCode
0x18002abf0  mov     rcx, rbx; s
0x18002abf3  mov     qword ptr [rsp+0E8h+g], r14; lpvOutBuffer
0x18002abf8  mov     dword ptr [rsp+0E8h+optval], 1
0x18002ac00  call    cs:__imp_WSAIoctl
0x18002ac06  cmp     word ptr [rsi], 2
0x18002ac0a  jz      loc_18002ADCB
0x18002ac10  mov     r8d, 80h; namelen
0x18002ac16  mov     rdx, rsi; name
0x18002ac19  mov     rcx, rbx; s
0x18002ac1c  call    cs:__imp_bind
0x18002ac22  cmp     eax, 0FFFFFFFFh
0x18002ac25  jz      loc_18002ADE7
0x18002ac2b  xor     edx, edx; Val
0x18002ac2d  mov     [rsp+0E8h+dwAddressStringLength], 41h ; 'A'
0x18002ac35  mov     r8d, 41h ; 'A'; Size
0x18002ac3b  lea     rcx, [rsp+0E8h+szAddressString]; void *
0x18002ac40  call    memset_0
0x18002ac45  lea     rax, [rsp+0E8h+dwAddressStringLength]
0x18002ac4a  xor     r8d, r8d; lpProtocolInfo
0x18002ac4d  lea     r9, [rsp+0E8h+szAddressString]; lpszAddressString
0x18002ac52  mov     qword ptr [rsp+0E8h+g], rax; lpdwAddressStringLength
0x18002ac57  mov     edx, 80h; dwAddressLength
0x18002ac5c  mov     rcx, rsi; lpsaAddress
0x18002ac5f  call    cs:__imp_WSAAddressToStringA
0x18002ac65  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac6c  cmp     rcx, r15
0x18002ac6f  jz      short loc_18002AC81
0x18002ac71  test    byte ptr [rcx+1Ch], 8
0x18002ac75  jz      short loc_18002AC81
0x18002ac77  cmp     byte ptr [rcx+19h], 5
0x18002ac7b  jnb     loc_18002AEF2
0x18002ac81  mov     [rdi+10h], rbx
0x18002ac85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ac8c  cmp     rcx, r15
0x18002ac8f  jnz     short loc_18002ACC1
0x18002ac91  xor     eax, eax
0x18002ac93  mov     rbp, [rsp+0E8h+var_28]
0x18002ac9b  mov     rbx, [rsp+0E8h+arg_10]
0x18002aca3  mov     rcx, [rsp+0E8h+var_38]
0x18002acab  xor     rcx, rsp; StackCookie
0x18002acae  call    __security_check_cookie
0x18002acb3  add     rsp, 0C8h
0x18002acba  pop     r15
0x18002acbc  pop     r14
0x18002acbe  pop     rdi
0x18002acbf  pop     rsi
0x18002acc0  retn
0x18002acc1  test    byte ptr [rcx+1Ch], 8
0x18002acc5  jz      short loc_18002AC91
0x18002acc7  cmp     byte ptr [rcx+19h], 6
0x18002accb  jb      short loc_18002AC91
0x18002accd  mov     rcx, [rcx+10h]
0x18002acd1  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002acd8  mov     edx, 25h ; '%'
0x18002acdd  xor     r9d, r9d
0x18002ace0  call    WPP_SF_d
0x18002ace5  jmp     short loc_18002AC91
0x18002ace7  call    cs:__imp_GetLastError
0x18002aced  mov     ebp, eax
0x18002acef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002acf6  cmp     rcx, r15
0x18002acf9  jnz     short loc_18002AD2C
0x18002acfb  cmp     [rdi+8], r14
0x18002acff  jnz     loc_18002AEA4
0x18002ad05  cmp     rcx, r15
0x18002ad08  jnz     loc_18002AEC1
0x18002ad0e  mov     eax, ebp
0x18002ad10  jmp     short loc_18002AC93
0x18002ad12  mov     rcx, [rcx+10h]
0x18002ad16  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002ad1d  mov     edx, 1Fh
0x18002ad22  call    WPP_SF_
0x18002ad27  jmp     loc_18002AAE9
0x18002ad2c  test    byte ptr [rcx+1Ch], 8
0x18002ad30  jz      short loc_18002ACFB
0x18002ad32  cmp     byte ptr [rcx+19h], 2
0x18002ad36  jb      short loc_18002ACFB
0x18002ad38  mov     edx, 20h ; ' '
0x18002ad3d  jmp     short loc_18002AD44
0x18002ad3f  mov     edx, 21h ; '!'
0x18002ad44  mov     rcx, [rcx+10h]
0x18002ad48  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002ad4f  mov     r9d, eax
0x18002ad52  call    WPP_SF_d
0x18002ad57  jmp     loc_18002AE98
0x18002ad5c  call    cs:__imp_WSAGetLastError
0x18002ad62  mov     ebp, eax
0x18002ad64  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad6b  cmp     rcx, r15
0x18002ad6e  jz      short loc_18002ACFB
0x18002ad70  test    byte ptr [rcx+1Ch], 8
0x18002ad74  jz      short loc_18002ACFB
0x18002ad76  cmp     byte ptr [rcx+19h], 2
0x18002ad7a  jb      loc_18002ACFB
0x18002ad80  jmp     short loc_18002AD3F
0x18002ad82  call    cs:__imp_GetLastError
0x18002ad88  mov     ebp, eax
0x18002ad8a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad91  cmp     rcx, r15
0x18002ad94  jz      loc_18002AE8F
0x18002ad9a  test    byte ptr [rcx+1Ch], 8
0x18002ad9e  jz      loc_18002AE8F
0x18002ada4  cmp     byte ptr [rcx+19h], 2
0x18002ada8  jb      loc_18002AE8F
0x18002adae  mov     rcx, [rcx+10h]
0x18002adb2  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002adb9  mov     edx, 22h ; '"'
0x18002adbe  mov     r9d, eax
0x18002adc1  call    WPP_SF_d
0x18002adc6  jmp     loc_18002AE8F
0x18002adcb  mov     eax, 3500h
0x18002add0  cmp     [rsi+2], ax
0x18002add4  jnz     loc_18002AC10
0x18002adda  mov     rcx, rbx; Handle
0x18002addd  call    ?SetSdOnDnsSocket@@YAK_K@Z; SetSdOnDnsSocket(unsigned __int64)
0x18002ade2  jmp     loc_18002AC10
0x18002ade7  call    cs:__imp_WSAGetLastError
0x18002aded  mov     ebp, eax
0x18002adef  mov     rcx, cs:WPP_GLOBAL_Control
0x18002adf6  cmp     rcx, r15
0x18002adf9  jz      short loc_18002AE1F
0x18002adfb  test    byte ptr [rcx+1Ch], 8
0x18002adff  jz      short loc_18002AE1F
0x18002ae01  cmp     byte ptr [rcx+19h], 2
0x18002ae05  jb      short loc_18002AE1F
0x18002ae07  mov     rcx, [rcx+10h]
0x18002ae0b  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002ae12  mov     edx, 23h ; '#'
0x18002ae17  mov     r9d, eax
0x18002ae1a  call    WPP_SF_d
0x18002ae1f  xor     edx, edx; Val
0x18002ae21  mov     [rsp+0E8h+dwAddressStringLength], 41h ; 'A'
0x18002ae29  mov     r8d, 41h ; 'A'; Size
0x18002ae2f  lea     rcx, [rsp+0E8h+szAddressString]; void *
0x18002ae34  call    memset_0
0x18002ae39  lea     rax, [rsp+0E8h+dwAddressStringLength]
0x18002ae3e  xor     r8d, r8d; lpProtocolInfo
0x18002ae41  lea     r9, [rsp+0E8h+szAddressString]; lpszAddressString
0x18002ae46  mov     qword ptr [rsp+0E8h+g], rax; lpdwAddressStringLength
0x18002ae4b  mov     edx, 80h; dwAddressLength
0x18002ae50  mov     rcx, rsi; lpsaAddress
0x18002ae53  call    cs:__imp_WSAAddressToStringA
0x18002ae59  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae60  cmp     rcx, r15
0x18002ae63  jz      short loc_18002AE8F
0x18002ae65  test    byte ptr [rcx+1Ch], 8
0x18002ae69  jz      short loc_18002AE8F
0x18002ae6b  cmp     byte ptr [rcx+19h], 2
0x18002ae6f  jb      short loc_18002AE8F
0x18002ae71  mov     rcx, [rcx+10h]
0x18002ae75  lea     r9, [rsp+0E8h+szAddressString]
0x18002ae7a  mov     edx, 24h ; '$'
0x18002ae7f  mov     [rsp+0E8h+g], ebp
0x18002ae83  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002ae8a  call    WPP_SF_sD
0x18002ae8f  mov     rcx, rbx; s
0x18002ae92  call    cs:__imp_closesocket
0x18002ae98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ae9f  jmp     loc_18002ACFB
0x18002aea4  lock dec dword ptr [rdi]
0x18002aea7  mov     rcx, [rdi+8]; hObject
0x18002aeab  call    cs:__imp_CloseHandle
0x18002aeb1  mov     [rdi+8], r14
0x18002aeb5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aebc  jmp     loc_18002AD05
0x18002aec1  test    byte ptr [rcx+1Ch], 8
0x18002aec5  jz      loc_18002AD0E
0x18002aecb  cmp     byte ptr [rcx+19h], 6
0x18002aecf  jb      loc_18002AD0E
0x18002aed5  mov     rcx, [rcx+10h]
0x18002aed9  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002aee0  mov     edx, 26h ; '&'
0x18002aee5  mov     r9d, ebp
0x18002aee8  call    WPP_SF_d
0x18002aeed  jmp     loc_18002AD0E
0x18002aef2  mov     rcx, [rcx+10h]
0x18002aef6  lea     r9, [rsp+0E8h+szAddressString]
0x18002aefb  mov     edx, 85h
0x18002af00  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18002af07  call    WPP_SF_s
0x18002af0c  jmp     loc_18002AC81
```
