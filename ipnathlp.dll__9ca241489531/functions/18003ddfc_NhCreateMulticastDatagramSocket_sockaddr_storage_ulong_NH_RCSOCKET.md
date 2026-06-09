# NhCreateMulticastDatagramSocket(sockaddr_storage *,ulong,_NH_RCSOCKET *)

- ea: `0x18003ddfc`
- end: `0x18003e3bb`
- name: `?NhCreateMulticastDatagramSocket@@YAKPEAUsockaddr_storage@@KPEAU_NH_RCSOCKET@@@Z`
- size: `1471`
- prototype: `unsigned int __fastcall(struct sockaddr_storage *name, unsigned int, struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006aba0`

## callees

- `0x18000c110`
- `0x18000c750`
- `0x1800319e8`
- `0x180033230`
- `0x18003ddfc`
- `0x18004e0c0`
- `0x18004ed64`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003deac`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003deac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003debb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003debb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003dfbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e2ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003e2ed`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18003dfb2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x18003dfb2`
- `WS2_32!WSASocketW` at `0x18003df24`
- `WS2_32!WSASocketW` at `0x18003df24`
- `WS2_32!WSAAddressToStringA` at `0x18003e055`
- `WS2_32!WSAAddressToStringA` at `0x18003e0e5`
- `WS2_32!WSAAddressToStringA` at `0x18003e055`
- `WS2_32!WSAAddressToStringA` at `0x18003e0e5`
- `WS2_32!WSAStringToAddressA` at `0x18003e1ac`
- `WS2_32!WSAStringToAddressA` at `0x18003e1ac`
- `WS2_32!__imp_bind` at `0x18003e133`
- `WS2_32!__imp_bind` at `0x18003e133`
- `WS2_32!__imp_closesocket` at `0x18003e2d2`
- `WS2_32!__imp_closesocket` at `0x18003e2d2`
- `WS2_32!__imp_htons` at `0x18003e0a5`
- `WS2_32!__imp_htons` at `0x18003e0a5`
- `WS2_32!__imp_setsockopt` at `0x18003e202`
- `WS2_32!__imp_setsockopt` at `0x18003e283`
- `WS2_32!__imp_setsockopt` at `0x18003e202`
- `WS2_32!__imp_setsockopt` at `0x18003e283`
- `WS2_32!__imp_WSAGetLastError` at `0x18003df33`
- `WS2_32!__imp_WSAGetLastError` at `0x18003df5f`
- `WS2_32!__imp_WSAGetLastError` at `0x18003dfe8`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e140`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e16c`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e231`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e2aa`
- `WS2_32!__imp_WSAGetLastError` at `0x18003df33`
- `WS2_32!__imp_WSAGetLastError` at `0x18003df5f`
- `WS2_32!__imp_WSAGetLastError` at `0x18003dfe8`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e140`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e16c`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e231`
- `WS2_32!__imp_WSAGetLastError` at `0x18003e2aa`

## pseudocode

```c
__int64 __fastcall NhCreateMulticastDatagramSocket(struct sockaddr *name, __int64 a2, struct _NH_RCSOCKET *a3)
{
  NET_IFINDEX v3; // r15d
  HANDLE EventW; // rax
  DWORD LastError; // eax
  DWORD Error; // ebx
  PVOID *v9; // rcx
  __int64 v10; // rdx
  SOCKET v11; // rax
  void *v12; // r14
  unsigned int v13; // eax
  __int64 v14; // rdx
  DWORD dwAddressStringLength; // [rsp+30h] [rbp-D0h] BYREF
  int AddressLength; // [rsp+34h] [rbp-CCh] BYREF
  char v18[8]; // [rsp+38h] [rbp-C8h] BYREF
  char optval[24]; // [rsp+40h] [rbp-C0h] BYREF
  struct sockaddr Address[2]; // [rsp+58h] [rbp-A8h] BYREF
  struct sockaddr saAddress[2]; // [rsp+78h] [rbp-88h] BYREF
  CHAR szAddressString[112]; // [rsp+A0h] [rbp-60h] BYREF

  v3 = NhpSharedPrivateLanIndex;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      116,
      &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
      (char *)a3 + 16,
      NhpSharedPrivateLanIndex);
  }
  AddressLength = 28;
  memset(Address, 0, 28);
  memset(saAddress, 0, 28);
  *(_DWORD *)v18 = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)a3 + 1) = EventW;
  if ( !EventW )
  {
    LastError = GetLastError();
    Error = LastError;
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    v10 = 117;
    goto LABEL_10;
  }
  *(_DWORD *)a3 = 2;
  v11 = WSASocketW(23, 2, 17, 0, 0, 1u);
  v12 = (void *)v11;
  if ( v11 == -1 )
  {
    Error = WSAGetLastError();
    v9 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_59;
    }
    LastError = WSAGetLastError();
    v9 = (PVOID *)WPP_GLOBAL_Control;
    v10 = 118;
LABEL_10:
    WPP_SF_d(v9[2], v10, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, LastError);
LABEL_58:
    v9 = (PVOID *)WPP_GLOBAL_Control;
LABEL_59:
    if ( *((_QWORD *)a3 + 1) )
    {
      _InterlockedDecrement((volatile signed __int32 *)a3);
      CloseHandle(*((HANDLE *)a3 + 1));
      *((_QWORD *)a3 + 1) = 0;
      v9 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 8) != 0 && *((_BYTE *)v9 + 25) >= 6u )
      WPP_SF_d(v9[2], 130, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, Error);
    return Error;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
      (unsigned int)v11);
  }
  if ( !BindIoCompletionCallback(v12, NhpIoMulticastCompletionRoutine, 0) )
  {
    Error = GetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v13 = WSAGetLastError();
    v14 = 120;
LABEL_56:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, v13);
LABEL_57:
    closesocket((SOCKET)v12);
    goto LABEL_58;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 121, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  dwAddressStringLength = 100;
  memset_0(szAddressString, 0, 0x64u);
  WSAAddressToStringA(name, 0x80u, 0, szAddressString, &dwAddressStringLength);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      122,
      (unsigned int)&WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
      *(unsigned __int16 *)name->sa_data,
      (__int64)szAddressString);
  }
  saAddress[0].sa_family = 23;
  *(_WORD *)saAddress[0].sa_data = htons(0x223u);
  *(IN6_ADDR *)&saAddress[0].sa_data[6] = in6addr_any;
  memset_0(szAddressString, 0, 0x64u);
  WSAAddressToStringA(saAddress, 0x1Cu, 0, szAddressString, &dwAddressStringLength);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      123,
      (unsigned int)&WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids,
      *(unsigned __int16 *)saAddress[0].sa_data,
      (__int64)szAddressString);
  }
  Error = bind((SOCKET)v12, name, 128);
  if ( Error == -1 )
  {
    Error = WSAGetLastError();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v13 = WSAGetLastError();
    v14 = 124;
    goto LABEL_56;
  }
  memset(optval, 0, 20);
  WSAStringToAddressA((LPSTR)"FF02::1:2", 23, 0, Address, &AddressLength);
  optval[0] = Address[0].sa_data[6];
  *(_DWORD *)&optval[9] = *(_DWORD *)((char *)&Address[1].sa_family + 1);
  *(_DWORD *)&optval[16] = v3;
  *(_WORD *)&optval[13] = *(_WORD *)&Address[1].sa_data[3];
  optval[15] = Address[1].sa_data[5];
  *(_QWORD *)&optval[1] = *(_QWORD *)&Address[0].sa_data[7];
  if ( setsockopt((SOCKET)v12, 41, 12, optval, 20) == -1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v13 = WSAGetLastError();
    v14 = 125;
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 126, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  if ( setsockopt((SOCKET)v12, 41, 19, v18, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_57;
    }
    v13 = WSAGetLastError();
    v14 = 127;
    goto LABEL_56;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids);
  }
  *((_QWORD *)a3 + 2) = v12;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x18003ddfc  mov     [rsp-8+arg_8], rbx
0x18003de01  mov     [rsp-8+arg_18], rsi
0x18003de06  push    rbp
0x18003de07  push    r12
0x18003de09  push    r13
0x18003de0b  push    r14
0x18003de0d  push    r15
0x18003de0f  lea     rbp, [rsp-20h]
0x18003de14  sub     rsp, 120h
0x18003de1b  mov     rax, cs:__security_cookie
0x18003de22  xor     rax, rsp
0x18003de25  mov     [rbp+40h+var_30], rax
0x18003de29  mov     r15d, cs:?NhpSharedPrivateLanIndex@@3KA; ulong NhpSharedPrivateLanIndex
0x18003de30  mov     rsi, r8
0x18003de33  mov     rbx, rcx
0x18003de36  mov     rcx, cs:WPP_GLOBAL_Control
0x18003de3d  lea     r13, WPP_GLOBAL_Control
0x18003de44  mov     r12b, 8
0x18003de47  cmp     rcx, r13
0x18003de4a  jz      short loc_18003DE76
0x18003de4c  test    [rcx+1Ch], r12b
0x18003de50  jz      short loc_18003DE76
0x18003de52  cmp     byte ptr [rcx+19h], 6
0x18003de56  jb      short loc_18003DE76
0x18003de58  mov     rcx, [rcx+10h]
0x18003de5c  lea     r9, [r8+10h]
0x18003de60  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003de67  mov     [rsp+140h+g], r15d
0x18003de6c  mov     edx, 74h ; 't'
0x18003de71  call    WPP_SF_qD
0x18003de76  xorps   xmm0, xmm0
0x18003de79  mov     [rsp+140h+AddressLength], 1Ch
0x18003de81  xorps   xmm1, xmm1
0x18003de84  xor     eax, eax
0x18003de86  movups  xmmword ptr [rsp+140h+Address.sa_family], xmm0
0x18003de8b  xor     r9d, r9d; lpName
0x18003de8e  xor     r8d, r8d; bInitialState
0x18003de91  movups  xmmword ptr [rsp+140h+saAddress], xmm1
0x18003de96  lea     r14d, [rax+1]
0x18003de9a  xor     edx, edx; bManualReset
0x18003de9c  xor     ecx, ecx; lpEventAttributes
0x18003de9e  mov     dword ptr [rsp+140h+var_108], r14d
0x18003dea3  movups  xmmword ptr [rsp+140h+Address.sa_data+0Ah], xmm0
0x18003dea8  movups  xmmword ptr [rbp+40h+saAddress+0Ch], xmm1
0x18003deac  call    cs:__imp_CreateEventW
0x18003deb2  mov     [rsi+8], rax
0x18003deb6  test    rax, rax
0x18003deb9  jnz     short loc_18003DF03
0x18003debb  call    cs:__imp_GetLastError
0x18003dec1  mov     ebx, eax
0x18003dec3  mov     rcx, cs:WPP_GLOBAL_Control
0x18003deca  cmp     rcx, r13
0x18003decd  jz      loc_18003E2DF
0x18003ded3  test    [rcx+1Ch], r12b
0x18003ded7  jz      loc_18003E2DF
0x18003dedd  cmp     byte ptr [rcx+19h], 2
0x18003dee1  jb      loc_18003E2DF
0x18003dee7  lea     edx, [r14+74h]
0x18003deeb  mov     rcx, [rcx+10h]
0x18003deef  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003def6  mov     r9d, eax
0x18003def9  call    WPP_SF_d
0x18003defe  jmp     loc_18003E2D8
0x18003df03  xor     r9d, r9d; lpProtocolInfo
0x18003df06  mov     [rsp+140h+dwFlags], r14d; dwFlags
0x18003df0b  mov     dword ptr [rsi], 2
0x18003df11  mov     [rsp+140h+g], 0; g
0x18003df19  lea     edx, [r9+2]; type
0x18003df1d  lea     ecx, [rdx+15h]; af
0x18003df20  lea     r8d, [r9+11h]; protocol
0x18003df24  call    cs:__imp_WSASocketW
0x18003df2a  mov     r14, rax
0x18003df2d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003df31  jnz     short loc_18003DF75
0x18003df33  call    cs:__imp_WSAGetLastError
0x18003df39  mov     ebx, eax
0x18003df3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df42  cmp     rcx, r13
0x18003df45  jz      loc_18003E2DF
0x18003df4b  test    [rcx+1Ch], r12b
0x18003df4f  jz      loc_18003E2DF
0x18003df55  cmp     byte ptr [rcx+19h], 2
0x18003df59  jb      loc_18003E2DF
0x18003df5f  call    cs:__imp_WSAGetLastError
0x18003df65  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df6c  lea     edx, [r14+77h]
0x18003df70  jmp     loc_18003DEEB
0x18003df75  mov     rcx, cs:WPP_GLOBAL_Control
0x18003df7c  cmp     rcx, r13
0x18003df7f  jz      short loc_18003DFA5
0x18003df81  test    [rcx+1Ch], r12b
0x18003df85  jz      short loc_18003DFA5
0x18003df87  cmp     byte ptr [rcx+19h], 4
0x18003df8b  jb      short loc_18003DFA5
0x18003df8d  mov     rcx, [rcx+10h]
0x18003df91  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003df98  mov     r9d, r14d
0x18003df9b  mov     edx, 77h ; 'w'
0x18003dfa0  call    WPP_SF_d
0x18003dfa5  xor     r8d, r8d; Flags
0x18003dfa8  lea     rdx, ?NhpIoMulticastCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x18003dfaf  mov     rcx, r14; FileHandle
0x18003dfb2  call    cs:__imp_BindIoCompletionCallback
0x18003dfb8  test    eax, eax
0x18003dfba  jnz     short loc_18003DFF8
0x18003dfbc  call    cs:__imp_GetLastError
0x18003dfc2  mov     ebx, eax
0x18003dfc4  mov     rax, cs:WPP_GLOBAL_Control
0x18003dfcb  cmp     rax, r13
0x18003dfce  jz      loc_18003E2CF
0x18003dfd4  test    [rax+1Ch], r12b
0x18003dfd8  jz      loc_18003E2CF
0x18003dfde  cmp     byte ptr [rax+19h], 2
0x18003dfe2  jb      loc_18003E2CF
0x18003dfe8  call    cs:__imp_WSAGetLastError
0x18003dfee  mov     edx, 78h ; 'x'
0x18003dff3  jmp     loc_18003E2B5
0x18003dff8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dfff  cmp     rcx, r13
0x18003e002  jz      short loc_18003E025
0x18003e004  test    [rcx+1Ch], r12b
0x18003e008  jz      short loc_18003E025
0x18003e00a  cmp     byte ptr [rcx+19h], 4
0x18003e00e  jb      short loc_18003E025
0x18003e010  mov     rcx, [rcx+10h]
0x18003e014  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e01b  mov     edx, 79h ; 'y'
0x18003e020  call    WPP_SF_
0x18003e025  mov     eax, 64h ; 'd'
0x18003e02a  lea     rcx, [rbp+40h+szAddressString]; void *
0x18003e02e  mov     r8d, eax; Size
0x18003e031  mov     [rsp+140h+dwAddressStringLength], eax
0x18003e035  xor     edx, edx; Val
0x18003e037  call    memset_0
0x18003e03c  lea     rax, [rsp+140h+dwAddressStringLength]
0x18003e041  xor     r8d, r8d; lpProtocolInfo
0x18003e044  lea     r9, [rbp+40h+szAddressString]; lpszAddressString
0x18003e048  mov     qword ptr [rsp+140h+g], rax; lpdwAddressStringLength
0x18003e04d  mov     edx, 80h; dwAddressLength
0x18003e052  mov     rcx, rbx; lpsaAddress
0x18003e055  call    cs:__imp_WSAAddressToStringA
0x18003e05b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e062  cmp     rcx, r13
0x18003e065  jz      short loc_18003E096
0x18003e067  test    [rcx+1Ch], r12b
0x18003e06b  jz      short loc_18003E096
0x18003e06d  cmp     byte ptr [rcx+19h], 4
0x18003e071  jb      short loc_18003E096
0x18003e073  movzx   r9d, word ptr [rbx+2]
0x18003e078  lea     rax, [rbp+40h+szAddressString]
0x18003e07c  mov     rcx, [rcx+10h]
0x18003e080  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e087  mov     edx, 7Ah ; 'z'
0x18003e08c  mov     qword ptr [rsp+140h+g], rax
0x18003e091  call    WPP_SF_ds
0x18003e096  mov     eax, 17h
0x18003e09b  mov     ecx, 223h; hostshort
0x18003e0a0  mov     word ptr [rsp+140h+saAddress], ax
0x18003e0a5  call    cs:__imp_htons
0x18003e0ab  movups  xmm0, xmmword ptr cs:in6addr_any.u
0x18003e0b2  xor     edx, edx; Val
0x18003e0b4  mov     word ptr [rsp+140h+saAddress+2], ax
0x18003e0b9  lea     rcx, [rbp+40h+szAddressString]; void *
0x18003e0bd  movdqu  xmmword ptr [rbp+40h+saAddress+8], xmm0
0x18003e0c2  lea     r8d, [rdx+64h]; Size
0x18003e0c6  call    memset_0
0x18003e0cb  xor     r8d, r8d; lpProtocolInfo
0x18003e0ce  lea     rax, [rsp+140h+dwAddressStringLength]
0x18003e0d3  lea     r9, [rbp+40h+szAddressString]; lpszAddressString
0x18003e0d7  mov     qword ptr [rsp+140h+g], rax; lpdwAddressStringLength
0x18003e0dc  lea     rcx, [rsp+140h+saAddress]; lpsaAddress
0x18003e0e1  lea     edx, [r8+1Ch]; dwAddressLength
0x18003e0e5  call    cs:__imp_WSAAddressToStringA
0x18003e0eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e0f2  cmp     rcx, r13
0x18003e0f5  jz      short loc_18003E127
0x18003e0f7  test    [rcx+1Ch], r12b
0x18003e0fb  jz      short loc_18003E127
0x18003e0fd  cmp     byte ptr [rcx+19h], 4
0x18003e101  jb      short loc_18003E127
0x18003e103  movzx   r9d, word ptr [rsp+140h+saAddress+2]
0x18003e109  lea     rax, [rbp+40h+szAddressString]
0x18003e10d  mov     rcx, [rcx+10h]
0x18003e111  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e118  mov     edx, 7Bh ; '{'
0x18003e11d  mov     qword ptr [rsp+140h+g], rax
0x18003e122  call    WPP_SF_ds
0x18003e127  mov     r8d, 80h; namelen
0x18003e12d  mov     rdx, rbx; name
0x18003e130  mov     rcx, r14; s
0x18003e133  call    cs:__imp_bind
0x18003e139  mov     ebx, eax
0x18003e13b  cmp     eax, 0FFFFFFFFh
0x18003e13e  jnz     short loc_18003E17C
0x18003e140  call    cs:__imp_WSAGetLastError
0x18003e146  mov     ebx, eax
0x18003e148  mov     rax, cs:WPP_GLOBAL_Control
0x18003e14f  cmp     rax, r13
0x18003e152  jz      loc_18003E2CF
0x18003e158  test    [rax+1Ch], r12b
0x18003e15c  jz      loc_18003E2CF
0x18003e162  cmp     byte ptr [rax+19h], 2
0x18003e166  jb      loc_18003E2CF
0x18003e16c  call    cs:__imp_WSAGetLastError
0x18003e172  mov     edx, 7Ch ; '|'
0x18003e177  jmp     loc_18003E2B5
0x18003e17c  xor     eax, eax
0x18003e17e  mov     [rsp+140h+optval], 0
0x18003e183  xorps   xmm0, xmm0
0x18003e186  lea     r9, [rsp+140h+Address]; lpAddress
0x18003e18b  xor     r8d, r8d; lpProtocolInfo
0x18003e18e  lea     rcx, AddressString; "FF02::1:2"
0x18003e195  movups  xmmword ptr [rsp+140h+var_FF], xmm0
0x18003e19a  mov     dword ptr [rsp+140h+var_FF+0Fh], eax
0x18003e19e  lea     rax, [rsp+140h+AddressLength]
0x18003e1a3  mov     qword ptr [rsp+140h+g], rax; lpAddressLength
0x18003e1a8  lea     edx, [r8+17h]; AddressFamily
0x18003e1ac  call    cs:__imp_WSAStringToAddressA
0x18003e1b2  mov     al, [rsp+140h+Address.sa_data+6]
0x18003e1b6  lea     r9, [rsp+140h+optval]; optval
0x18003e1bb  movsd   xmm0, qword ptr [rsp+140h+Address.sa_data+7]
0x18003e1c1  mov     r8d, 0Ch; optname
0x18003e1c7  mov     [rsp+140h+optval], al
0x18003e1cb  mov     rcx, r14; s
0x18003e1ce  mov     eax, [rsp+140h+var_D7]
0x18003e1d2  mov     dword ptr [rsp+140h+var_FF+8], eax
0x18003e1d6  movzx   eax, [rsp+140h+var_D3]
0x18003e1db  mov     dword ptr [rsp+140h+var_FF+0Fh], r15d
0x18003e1e0  lea     r15d, [r8+1Dh]
0x18003e1e4  mov     word ptr [rsp+140h+var_FF+0Ch], ax
0x18003e1e9  mov     edx, r15d; level
0x18003e1ec  mov     al, [rsp+140h+var_D1]
0x18003e1f0  mov     [rsp+140h+var_FF+0Eh], al
0x18003e1f4  movsd   qword ptr [rsp+140h+var_FF], xmm0
0x18003e1fa  mov     [rsp+140h+g], 14h; optlen
0x18003e202  call    cs:__imp_setsockopt
0x18003e208  cmp     eax, 0FFFFFFFFh
0x18003e20b  jnz     short loc_18003E23D
0x18003e20d  mov     rax, cs:WPP_GLOBAL_Control
0x18003e214  cmp     rax, r13
0x18003e217  jz      loc_18003E2CF
0x18003e21d  test    [rax+1Ch], r12b
0x18003e221  jz      loc_18003E2CF
0x18003e227  cmp     byte ptr [rax+19h], 2
0x18003e22b  jb      loc_18003E2CF
0x18003e231  call    cs:__imp_WSAGetLastError
0x18003e237  lea     edx, [r15+54h]
0x18003e23b  jmp     short loc_18003E2B5
0x18003e23d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e244  cmp     rcx, r13
0x18003e247  jz      short loc_18003E26A
0x18003e249  test    [rcx+1Ch], r12b
0x18003e24d  jz      short loc_18003E26A
0x18003e24f  cmp     byte ptr [rcx+19h], 4
0x18003e253  jb      short loc_18003E26A
0x18003e255  mov     rcx, [rcx+10h]
0x18003e259  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e260  mov     edx, 7Eh ; '~'
0x18003e265  call    WPP_SF_
0x18003e26a  lea     r9, [rsp+140h+var_108]; optval
0x18003e26f  mov     [rsp+140h+g], 4; optlen
0x18003e277  mov     r8d, 13h; optname
0x18003e27d  mov     edx, r15d; level
0x18003e280  mov     rcx, r14; s
0x18003e283  call    cs:__imp_setsockopt
0x18003e289  cmp     eax, 0FFFFFFFFh
0x18003e28c  jnz     loc_18003E32F
0x18003e292  mov     rax, cs:WPP_GLOBAL_Control
0x18003e299  cmp     rax, r13
0x18003e29c  jz      short loc_18003E2CF
0x18003e29e  test    [rax+1Ch], r12b
0x18003e2a2  jz      short loc_18003E2CF
0x18003e2a4  cmp     byte ptr [rax+19h], 2
0x18003e2a8  jb      short loc_18003E2CF
0x18003e2aa  call    cs:__imp_WSAGetLastError
0x18003e2b0  mov     edx, 7Fh
0x18003e2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2bc  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e2c3  mov     r9d, eax
0x18003e2c6  mov     rcx, [rcx+10h]
0x18003e2ca  call    WPP_SF_d
0x18003e2cf  mov     rcx, r14; s
0x18003e2d2  call    cs:__imp_closesocket
0x18003e2d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e2df  cmp     qword ptr [rsi+8], 0
0x18003e2e4  jz      short loc_18003E302
0x18003e2e6  lock dec dword ptr [rsi]
0x18003e2e9  mov     rcx, [rsi+8]; hObject
0x18003e2ed  call    cs:__imp_CloseHandle
0x18003e2f3  mov     qword ptr [rsi+8], 0
0x18003e2fb  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e302  cmp     rcx, r13
0x18003e305  jz      short loc_18003E32B
0x18003e307  test    [rcx+1Ch], r12b
0x18003e30b  jz      short loc_18003E32B
0x18003e30d  cmp     byte ptr [rcx+19h], 6
0x18003e311  jb      short loc_18003E32B
0x18003e313  mov     rcx, [rcx+10h]
0x18003e317  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18003e31e  mov     edx, 82h
  ... truncated ...
```
