# NhCreateMulticastDatagramSocket(sockaddr_storage *,ulong,_NH_RCSOCKET *)

- ea: `0x180041184`
- end: `0x1800417c5`
- name: `?NhCreateMulticastDatagramSocket@@YAKPEAUsockaddr_storage@@KPEAU_NH_RCSOCKET@@@Z`
- size: `1601`
- prototype: `__int64 __fastcall(struct sockaddr *name, __int64, struct _NH_RCSOCKET *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006ffd0`

## callees

- `0x18000ca20`
- `0x18000d090`
- `0x180034098`
- `0x180035894`
- `0x180041184`
- `0x180051f30`
- `0x180052bf4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041234`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180041234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041368`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041249`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041368`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800416f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800416f0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180041358`
- `api-ms-win-core-kernel32-legacy-l1-1-0!BindIoCompletionCallback` at `0x180041358`
- `WS2_32!WSASocketW` at `0x1800412b8`
- `WS2_32!WSASocketW` at `0x1800412b8`
- `WS2_32!WSAAddressToStringA` at `0x18004140d`
- `WS2_32!WSAAddressToStringA` at `0x1800414a9`
- `WS2_32!WSAAddressToStringA` at `0x18004140d`
- `WS2_32!WSAAddressToStringA` at `0x1800414a9`
- `WS2_32!WSAStringToAddressA` at `0x180041588`
- `WS2_32!WSAStringToAddressA` at `0x180041588`
- `WS2_32!__imp_bind` at `0x1800414fd`
- `WS2_32!__imp_bind` at `0x1800414fd`
- `WS2_32!__imp_closesocket` at `0x1800416cf`
- `WS2_32!__imp_closesocket` at `0x1800416cf`
- `WS2_32!__imp_htons` at `0x180041463`
- `WS2_32!__imp_htons` at `0x180041463`
- `WS2_32!__imp_setsockopt` at `0x1800415e4`
- `WS2_32!__imp_setsockopt` at `0x180041674`
- `WS2_32!__imp_setsockopt` at `0x1800415e4`
- `WS2_32!__imp_setsockopt` at `0x180041674`
- `WS2_32!__imp_WSAGetLastError` at `0x1800412cd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800412ff`
- `WS2_32!__imp_WSAGetLastError` at `0x18004139a`
- `WS2_32!__imp_WSAGetLastError` at `0x180041510`
- `WS2_32!__imp_WSAGetLastError` at `0x180041542`
- `WS2_32!__imp_WSAGetLastError` at `0x180041619`
- `WS2_32!__imp_WSAGetLastError` at `0x1800416a1`
- `WS2_32!__imp_WSAGetLastError` at `0x1800412cd`
- `WS2_32!__imp_WSAGetLastError` at `0x1800412ff`
- `WS2_32!__imp_WSAGetLastError` at `0x18004139a`
- `WS2_32!__imp_WSAGetLastError` at `0x180041510`
- `WS2_32!__imp_WSAGetLastError` at `0x180041542`
- `WS2_32!__imp_WSAGetLastError` at `0x180041619`
- `WS2_32!__imp_WSAGetLastError` at `0x1800416a1`

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
0x180041184  mov     [rsp-8+arg_8], rbx
0x180041189  mov     [rsp-8+arg_18], rsi
0x18004118e  push    rbp
0x18004118f  push    r12
0x180041191  push    r13
0x180041193  push    r14
0x180041195  push    r15
0x180041197  lea     rbp, [rsp-20h]
0x18004119c  sub     rsp, 120h
0x1800411a3  mov     rax, cs:__security_cookie
0x1800411aa  xor     rax, rsp
0x1800411ad  mov     [rbp+40h+var_30], rax
0x1800411b1  mov     r15d, cs:?NhpSharedPrivateLanIndex@@3KA; ulong NhpSharedPrivateLanIndex
0x1800411b8  mov     rsi, r8
0x1800411bb  mov     rbx, rcx
0x1800411be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800411c5  lea     r13, WPP_GLOBAL_Control
0x1800411cc  mov     r12b, 8
0x1800411cf  cmp     rcx, r13
0x1800411d2  jz      short loc_1800411FE
0x1800411d4  test    [rcx+1Ch], r12b
0x1800411d8  jz      short loc_1800411FE
0x1800411da  cmp     byte ptr [rcx+19h], 6
0x1800411de  jb      short loc_1800411FE
0x1800411e0  mov     rcx, [rcx+10h]
0x1800411e4  lea     r9, [r8+10h]
0x1800411e8  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x1800411ef  mov     [rsp+140h+g], r15d
0x1800411f4  mov     edx, 74h ; 't'
0x1800411f9  call    WPP_SF_qD
0x1800411fe  xorps   xmm0, xmm0
0x180041201  mov     [rsp+140h+AddressLength], 1Ch
0x180041209  xorps   xmm1, xmm1
0x18004120c  xor     eax, eax
0x18004120e  movups  xmmword ptr [rsp+140h+Address.sa_family], xmm0
0x180041213  xor     r9d, r9d; lpName
0x180041216  xor     r8d, r8d; bInitialState
0x180041219  movups  xmmword ptr [rsp+140h+saAddress], xmm1
0x18004121e  lea     r14d, [rax+1]
0x180041222  xor     edx, edx; bManualReset
0x180041224  xor     ecx, ecx; lpEventAttributes
0x180041226  mov     dword ptr [rsp+140h+var_108], r14d
0x18004122b  movups  xmmword ptr [rsp+140h+Address.sa_data+0Ah], xmm0
0x180041230  movups  xmmword ptr [rbp+40h+saAddress+0Ch], xmm1
0x180041234  call    cs:__imp_CreateEventW
0x18004123b  nop     dword ptr [rax+rax+00h]
0x180041240  mov     [rsi+8], rax
0x180041244  test    rax, rax
0x180041247  jnz     short loc_180041297
0x180041249  call    cs:__imp_GetLastError
0x180041250  nop     dword ptr [rax+rax+00h]
0x180041255  mov     ebx, eax
0x180041257  mov     rcx, cs:WPP_GLOBAL_Control
0x18004125e  cmp     rcx, r13
0x180041261  jz      loc_1800416E2
0x180041267  test    [rcx+1Ch], r12b
0x18004126b  jz      loc_1800416E2
0x180041271  cmp     byte ptr [rcx+19h], 2
0x180041275  jb      loc_1800416E2
0x18004127b  lea     edx, [r14+74h]
0x18004127f  mov     rcx, [rcx+10h]
0x180041283  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18004128a  mov     r9d, eax
0x18004128d  call    WPP_SF_d
0x180041292  jmp     loc_1800416DB
0x180041297  xor     r9d, r9d; lpProtocolInfo
0x18004129a  mov     [rsp+140h+dwFlags], r14d; dwFlags
0x18004129f  mov     dword ptr [rsi], 2
0x1800412a5  mov     [rsp+140h+g], 0; g
0x1800412ad  lea     edx, [r9+2]; type
0x1800412b1  lea     ecx, [rdx+15h]; af
0x1800412b4  lea     r8d, [r9+11h]; protocol
0x1800412b8  call    cs:__imp_WSASocketW
0x1800412bf  nop     dword ptr [rax+rax+00h]
0x1800412c4  mov     r14, rax
0x1800412c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800412cb  jnz     short loc_18004131B
0x1800412cd  call    cs:__imp_WSAGetLastError
0x1800412d4  nop     dword ptr [rax+rax+00h]
0x1800412d9  mov     ebx, eax
0x1800412db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800412e2  cmp     rcx, r13
0x1800412e5  jz      loc_1800416E2
0x1800412eb  test    [rcx+1Ch], r12b
0x1800412ef  jz      loc_1800416E2
0x1800412f5  cmp     byte ptr [rcx+19h], 2
0x1800412f9  jb      loc_1800416E2
0x1800412ff  call    cs:__imp_WSAGetLastError
0x180041306  nop     dword ptr [rax+rax+00h]
0x18004130b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041312  lea     edx, [r14+77h]
0x180041316  jmp     loc_18004127F
0x18004131b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041322  cmp     rcx, r13
0x180041325  jz      short loc_18004134B
0x180041327  test    [rcx+1Ch], r12b
0x18004132b  jz      short loc_18004134B
0x18004132d  cmp     byte ptr [rcx+19h], 4
0x180041331  jb      short loc_18004134B
0x180041333  mov     rcx, [rcx+10h]
0x180041337  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x18004133e  mov     r9d, r14d
0x180041341  mov     edx, 77h ; 'w'
0x180041346  call    WPP_SF_d
0x18004134b  xor     r8d, r8d; Flags
0x18004134e  lea     rdx, ?NhpIoMulticastCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; Function
0x180041355  mov     rcx, r14; FileHandle
0x180041358  call    cs:__imp_BindIoCompletionCallback
0x18004135f  nop     dword ptr [rax+rax+00h]
0x180041364  test    eax, eax
0x180041366  jnz     short loc_1800413B0
0x180041368  call    cs:__imp_GetLastError
0x18004136f  nop     dword ptr [rax+rax+00h]
0x180041374  mov     ebx, eax
0x180041376  mov     rax, cs:WPP_GLOBAL_Control
0x18004137d  cmp     rax, r13
0x180041380  jz      loc_1800416CC
0x180041386  test    [rax+1Ch], r12b
0x18004138a  jz      loc_1800416CC
0x180041390  cmp     byte ptr [rax+19h], 2
0x180041394  jb      loc_1800416CC
0x18004139a  call    cs:__imp_WSAGetLastError
0x1800413a1  nop     dword ptr [rax+rax+00h]
0x1800413a6  mov     edx, 78h ; 'x'
0x1800413ab  jmp     loc_1800416B2
0x1800413b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800413b7  cmp     rcx, r13
0x1800413ba  jz      short loc_1800413DD
0x1800413bc  test    [rcx+1Ch], r12b
0x1800413c0  jz      short loc_1800413DD
0x1800413c2  cmp     byte ptr [rcx+19h], 4
0x1800413c6  jb      short loc_1800413DD
0x1800413c8  mov     rcx, [rcx+10h]
0x1800413cc  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x1800413d3  mov     edx, 79h ; 'y'
0x1800413d8  call    WPP_SF_
0x1800413dd  mov     eax, 64h ; 'd'
0x1800413e2  lea     rcx, [rbp+40h+szAddressString]; void *
0x1800413e6  mov     r8d, eax; Size
0x1800413e9  mov     [rsp+140h+dwAddressStringLength], eax
0x1800413ed  xor     edx, edx; Val
0x1800413ef  call    memset_0
0x1800413f4  lea     rax, [rsp+140h+dwAddressStringLength]
0x1800413f9  xor     r8d, r8d; lpProtocolInfo
0x1800413fc  lea     r9, [rbp+40h+szAddressString]; lpszAddressString
0x180041400  mov     qword ptr [rsp+140h+g], rax; lpdwAddressStringLength
0x180041405  mov     edx, 80h; dwAddressLength
0x18004140a  mov     rcx, rbx; lpsaAddress
0x18004140d  call    cs:__imp_WSAAddressToStringA
0x180041414  nop     dword ptr [rax+rax+00h]
0x180041419  mov     rcx, cs:WPP_GLOBAL_Control
0x180041420  cmp     rcx, r13
0x180041423  jz      short loc_180041454
0x180041425  test    [rcx+1Ch], r12b
0x180041429  jz      short loc_180041454
0x18004142b  cmp     byte ptr [rcx+19h], 4
0x18004142f  jb      short loc_180041454
0x180041431  movzx   r9d, word ptr [rbx+2]
0x180041436  lea     rax, [rbp+40h+szAddressString]
0x18004143a  mov     rcx, [rcx+10h]
0x18004143e  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x180041445  mov     edx, 7Ah ; 'z'
0x18004144a  mov     qword ptr [rsp+140h+g], rax
0x18004144f  call    WPP_SF_ds
0x180041454  mov     eax, 17h
0x180041459  mov     ecx, 223h; hostshort
0x18004145e  mov     word ptr [rsp+140h+saAddress], ax
0x180041463  call    cs:__imp_htons
0x18004146a  nop     dword ptr [rax+rax+00h]
0x18004146f  movups  xmm0, xmmword ptr cs:in6addr_any.u
0x180041476  xor     edx, edx; Val
0x180041478  mov     word ptr [rsp+140h+saAddress+2], ax
0x18004147d  lea     rcx, [rbp+40h+szAddressString]; void *
0x180041481  movdqu  xmmword ptr [rbp+40h+saAddress+8], xmm0
0x180041486  lea     r8d, [rdx+64h]; Size
0x18004148a  call    memset_0
0x18004148f  xor     r8d, r8d; lpProtocolInfo
0x180041492  lea     rax, [rsp+140h+dwAddressStringLength]
0x180041497  lea     r9, [rbp+40h+szAddressString]; lpszAddressString
0x18004149b  mov     qword ptr [rsp+140h+g], rax; lpdwAddressStringLength
0x1800414a0  lea     rcx, [rsp+140h+saAddress]; lpsaAddress
0x1800414a5  lea     edx, [r8+1Ch]; dwAddressLength
0x1800414a9  call    cs:__imp_WSAAddressToStringA
0x1800414b0  nop     dword ptr [rax+rax+00h]
0x1800414b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800414bc  cmp     rcx, r13
0x1800414bf  jz      short loc_1800414F1
0x1800414c1  test    [rcx+1Ch], r12b
0x1800414c5  jz      short loc_1800414F1
0x1800414c7  cmp     byte ptr [rcx+19h], 4
0x1800414cb  jb      short loc_1800414F1
0x1800414cd  movzx   r9d, word ptr [rsp+140h+saAddress+2]
0x1800414d3  lea     rax, [rbp+40h+szAddressString]
0x1800414d7  mov     rcx, [rcx+10h]
0x1800414db  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x1800414e2  mov     edx, 7Bh ; '{'
0x1800414e7  mov     qword ptr [rsp+140h+g], rax
0x1800414ec  call    WPP_SF_ds
0x1800414f1  mov     r8d, 80h; namelen
0x1800414f7  mov     rdx, rbx; name
0x1800414fa  mov     rcx, r14; s
0x1800414fd  call    cs:__imp_bind
0x180041504  nop     dword ptr [rax+rax+00h]
0x180041509  mov     ebx, eax
0x18004150b  cmp     eax, 0FFFFFFFFh
0x18004150e  jnz     short loc_180041558
0x180041510  call    cs:__imp_WSAGetLastError
0x180041517  nop     dword ptr [rax+rax+00h]
0x18004151c  mov     ebx, eax
0x18004151e  mov     rax, cs:WPP_GLOBAL_Control
0x180041525  cmp     rax, r13
0x180041528  jz      loc_1800416CC
0x18004152e  test    [rax+1Ch], r12b
0x180041532  jz      loc_1800416CC
0x180041538  cmp     byte ptr [rax+19h], 2
0x18004153c  jb      loc_1800416CC
0x180041542  call    cs:__imp_WSAGetLastError
0x180041549  nop     dword ptr [rax+rax+00h]
0x18004154e  mov     edx, 7Ch ; '|'
0x180041553  jmp     loc_1800416B2
0x180041558  xor     eax, eax
0x18004155a  mov     [rsp+140h+optval], 0
0x18004155f  xorps   xmm0, xmm0
0x180041562  lea     r9, [rsp+140h+Address]; lpAddress
0x180041567  xor     r8d, r8d; lpProtocolInfo
0x18004156a  lea     rcx, AddressString; "FF02::1:2"
0x180041571  movups  xmmword ptr [rsp+140h+var_FF], xmm0
0x180041576  mov     dword ptr [rsp+140h+var_FF+0Fh], eax
0x18004157a  lea     rax, [rsp+140h+AddressLength]
0x18004157f  mov     qword ptr [rsp+140h+g], rax; lpAddressLength
0x180041584  lea     edx, [r8+17h]; AddressFamily
0x180041588  call    cs:__imp_WSAStringToAddressA
0x18004158f  nop     dword ptr [rax+rax+00h]
0x180041594  mov     al, [rsp+140h+Address.sa_data+6]
0x180041598  lea     r9, [rsp+140h+optval]; optval
0x18004159d  movsd   xmm0, qword ptr [rsp+140h+Address.sa_data+7]
0x1800415a3  mov     r8d, 0Ch; optname
0x1800415a9  mov     [rsp+140h+optval], al
0x1800415ad  mov     rcx, r14; s
0x1800415b0  mov     eax, [rsp+140h+var_D7]
0x1800415b4  mov     dword ptr [rsp+140h+var_FF+8], eax
0x1800415b8  movzx   eax, [rsp+140h+var_D3]
0x1800415bd  mov     dword ptr [rsp+140h+var_FF+0Fh], r15d
0x1800415c2  lea     r15d, [r8+1Dh]
0x1800415c6  mov     word ptr [rsp+140h+var_FF+0Ch], ax
0x1800415cb  mov     edx, r15d; level
0x1800415ce  mov     al, [rsp+140h+var_D1]
0x1800415d2  mov     [rsp+140h+var_FF+0Eh], al
0x1800415d6  movsd   qword ptr [rsp+140h+var_FF], xmm0
0x1800415dc  mov     [rsp+140h+g], 14h; optlen
0x1800415e4  call    cs:__imp_setsockopt
0x1800415eb  nop     dword ptr [rax+rax+00h]
0x1800415f0  cmp     eax, 0FFFFFFFFh
0x1800415f3  jnz     short loc_18004162E
0x1800415f5  mov     rax, cs:WPP_GLOBAL_Control
0x1800415fc  cmp     rax, r13
0x1800415ff  jz      loc_1800416CC
0x180041605  test    [rax+1Ch], r12b
0x180041609  jz      loc_1800416CC
0x18004160f  cmp     byte ptr [rax+19h], 2
0x180041613  jb      loc_1800416CC
0x180041619  call    cs:__imp_WSAGetLastError
0x180041620  nop     dword ptr [rax+rax+00h]
0x180041625  lea     edx, [r15+54h]
0x180041629  jmp     loc_1800416B2
0x18004162e  mov     rcx, cs:WPP_GLOBAL_Control
0x180041635  cmp     rcx, r13
0x180041638  jz      short loc_18004165B
0x18004163a  test    [rcx+1Ch], r12b
0x18004163e  jz      short loc_18004165B
0x180041640  cmp     byte ptr [rcx+19h], 4
0x180041644  jb      short loc_18004165B
0x180041646  mov     rcx, [rcx+10h]
0x18004164a  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x180041651  mov     edx, 7Eh ; '~'
0x180041656  call    WPP_SF_
0x18004165b  lea     r9, [rsp+140h+var_108]; optval
0x180041660  mov     [rsp+140h+g], 4; optlen
0x180041668  mov     r8d, 13h; optname
0x18004166e  mov     edx, r15d; level
0x180041671  mov     rcx, r14; s
0x180041674  call    cs:__imp_setsockopt
0x18004167b  nop     dword ptr [rax+rax+00h]
0x180041680  cmp     eax, 0FFFFFFFFh
0x180041683  jnz     loc_180041738
0x180041689  mov     rax, cs:WPP_GLOBAL_Control
0x180041690  cmp     rax, r13
0x180041693  jz      short loc_1800416CC
0x180041695  test    [rax+1Ch], r12b
0x180041699  jz      short loc_1800416CC
0x18004169b  cmp     byte ptr [rax+19h], 2
0x18004169f  jb      short loc_1800416CC
0x1800416a1  call    cs:__imp_WSAGetLastError
0x1800416a8  nop     dword ptr [rax+rax+00h]
0x1800416ad  mov     edx, 7Fh
0x1800416b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800416b9  lea     r8, WPP_9de80ca90e993f13ef5a426cd212a101_Traceguids
0x1800416c0  mov     r9d, eax
0x1800416c3  mov     rcx, [rcx+10h]
0x1800416c7  call    WPP_SF_d
  ... truncated ...
```
