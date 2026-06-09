# GetSpecifiedDhcpMessageEx

- ea: `0x180026494`
- end: `0x1800267ac`
- name: `GetSpecifiedDhcpMessageEx`
- size: `792`
- prototype: `__int64 __fastcall(HANDLE *, int, int, DWORD, _BYTE *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1800261d4`

## callees

- `0x18000fb90`
- `0x18001d826`
- `0x180026494`
- `0x1800267b4`
- `0x180045f90`
- `0x180047e3c`
- `0x18004d4c0`
- `0x18004d9e8`
- `0x18004e790`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002673d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800265cf`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002673d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800265b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800265b9`
- `WS2_32!WSASetEvent` at `0x180026730`
- `WS2_32!WSASetEvent` at `0x180026730`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800265a9`
- `WS2_32!WSAWaitForMultipleEvents` at `0x1800265a9`
- `WS2_32!WSACloseEvent` at `0x18002678c`
- `WS2_32!WSACloseEvent` at `0x18002678c`
- `WS2_32!__imp_ntohl` at `0x180026523`
- `WS2_32!__imp_ntohl` at `0x180026581`
- `WS2_32!__imp_ntohl` at `0x1800265e7`
- `WS2_32!__imp_ntohl` at `0x18002664c`
- `WS2_32!__imp_ntohl` at `0x18002667b`
- `WS2_32!__imp_ntohl` at `0x1800266d2`
- `WS2_32!__imp_ntohl` at `0x180026710`
- `WS2_32!__imp_ntohl` at `0x180026523`
- `WS2_32!__imp_ntohl` at `0x180026581`
- `WS2_32!__imp_ntohl` at `0x1800265e7`
- `WS2_32!__imp_ntohl` at `0x18002664c`
- `WS2_32!__imp_ntohl` at `0x18002667b`
- `WS2_32!__imp_ntohl` at `0x1800266d2`
- `WS2_32!__imp_ntohl` at `0x180026710`
- `WS2_32!__imp_WSAGetLastError` at `0x180026752`
- `WS2_32!__imp_WSAGetLastError` at `0x180026752`

## pseudocode

```c
__int64 __fastcall GetSpecifiedDhcpMessageEx(HANDLE *a1, int a2, int a3, DWORD a4, _BYTE *a5, int a6)
{
  _BYTE *v10; // rbx
  unsigned int Error; // edi
  u_long v12; // eax
  __int64 v13; // rdx
  HANDLE v14; // rax
  BOOL v15; // esi
  u_long v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  DWORD v20; // r14d
  u_long v21; // eax
  BOOL v22; // r15d
  u_long v23; // eax
  __int64 v24; // rax
  _QWORD *v25; // rcx
  char v26; // al
  u_long v27; // eax
  HANDLE *v28; // r15
  u_long v29; // eax
  DWORD v30; // r14d
  HANDLE hEvents[2]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v33[136]; // [rsp+40h] [rbp-88h] BYREF

  memset_0(v33, 0, 0x48u);
  v10 = a5;
  *(_OWORD *)hEvents = 0;
  if ( a5 )
  {
LABEL_4:
    if ( a6 )
    {
      if ( (xmmword_1800616A0 & 0x10) == 0 )
        return (unsigned int)ProcessRecvFromSocket(v10);
      v12 = ntohl(*((_DWORD *)v10 + 10));
      v13 = 59;
LABEL_7:
      WPP_SF_d(1028, v13, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v12);
      return (unsigned int)ProcessRecvFromSocket(v10);
    }
    hEvents[0] = *((HANDLE *)v10 + 7);
    v14 = a1[104];
    if ( v14 )
      hEvents[1] = a1[104];
    v15 = v14 != 0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v16 = ntohl(*((_DWORD *)v10 + 10));
      WPP_SF_dL(v18, v17, v19, a4, v16);
    }
    v20 = WSAWaitForMultipleEvents(v15 + 1, hEvents, 0, a4, 0);
    EnterCriticalSection(&DhcpGlobalRecvFromCritSect);
    if ( v20 )
    {
      v22 = DhcpGlobalRecvFromList == (_UNKNOWN *)v10;
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v23 = ntohl(*((_DWORD *)v10 + 10));
        WPP_SF_d(1028, 63, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v23);
      }
      v24 = *(_QWORD *)v10;
      if ( *(_BYTE **)(*(_QWORD *)v10 + 8LL) != v10 || (v25 = (_QWORD *)*((_QWORD *)v10 + 1), (_BYTE *)*v25 != v10) )
        __fastfail(3u);
      *v25 = v24;
      *(_QWORD *)(v24 + 8) = v25;
      *((_QWORD *)v10 + 1) = v10;
      *(_QWORD *)v10 = v10;
      if ( v22 )
      {
        v26 = xmmword_1800616A0;
        if ( (xmmword_1800616A0 & 0x10) != 0 )
        {
          v27 = ntohl(*((_DWORD *)v10 + 10));
          WPP_SF_d(1028, 64, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v27);
          v26 = xmmword_1800616A0;
        }
        v28 = (HANDLE *)DhcpGlobalRecvFromList;
        if ( DhcpGlobalRecvFromList != (_UNKNOWN *)&DhcpGlobalRecvFromList )
        {
          if ( (v26 & 0x10) != 0 )
          {
            v29 = ntohl(*((_DWORD *)DhcpGlobalRecvFromList + 10));
            WPP_SF_d(1028, 65, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v29);
          }
          WSASetEvent(v28[7]);
        }
      }
      LeaveCriticalSection(&DhcpGlobalRecvFromCritSect);
      v30 = v20 - 1;
      if ( v30 )
      {
        if ( v30 == 257 )
          Error = 121;
        else
          Error = WSAGetLastError();
      }
      else
      {
        if ( (xmmword_1800616A0 & 0x10) != 0 )
          WPP_SF_q(1028, 66, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, a1[3]);
        Error = 1223;
      }
    }
    else
    {
      LeaveCriticalSection(&DhcpGlobalRecvFromCritSect);
      if ( !*((_DWORD *)v10 + 16) )
      {
        if ( (xmmword_1800616A0 & 0x10) == 0 )
          return (unsigned int)ProcessRecvFromSocket(v10);
        v12 = ntohl(*((_DWORD *)v10 + 10));
        v13 = 62;
        goto LABEL_7;
      }
      if ( (xmmword_1800616A0 & 0x10) != 0 )
      {
        v21 = ntohl(*((_DWORD *)v10 + 10));
        WPP_SF_d(1028, 61, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids, v21);
      }
      memcpy_0(
        *(void **)(*((_QWORD *)v10 + 2) + 752LL),
        *(const void **)(*((_QWORD *)v10 + 2) + 2000LL),
        **((unsigned int **)v10 + 4));
      DhcpLogMessageBytes(a1[94], **((unsigned int **)v10 + 4));
      Error = 0;
    }
    WSACloseEvent(*((HANDLE *)v10 + 7));
    return Error;
  }
  Error = PopulateAndInsertRecvCtxtInGlobalList((unsigned int)v33, (_DWORD)a1, a2, a3, a4, (__int64)&a6);
  if ( !Error )
  {
    v10 = v33;
    goto LABEL_4;
  }
  return Error;
}

```

## disassembly

```asm
0x180026494  push    rbx
0x180026496  push    rsi
0x180026497  push    rdi
0x180026498  push    r13
0x18002649a  push    r14
0x18002649c  push    r15
0x18002649e  sub     rsp, 98h
0x1800264a5  mov     rsi, rdx
0x1800264a8  mov     edi, r8d
0x1800264ab  xor     edx, edx; Val
0x1800264ad  mov     r13, rcx
0x1800264b0  lea     rcx, [rsp+0C8h+var_88]; void *
0x1800264b5  mov     r14d, r9d
0x1800264b8  lea     r8d, [rdx+48h]; Size
0x1800264bc  call    memset_0
0x1800264c1  mov     rbx, [rsp+0C8h+arg_20]
0x1800264c9  xorps   xmm0, xmm0
0x1800264cc  movups  xmmword ptr [rsp+0C8h+hEvents], xmm0
0x1800264d1  test    rbx, rbx
0x1800264d4  jnz     short loc_18002650A
0x1800264d6  lea     rax, [rsp+0C8h+arg_28]
0x1800264de  mov     r9d, edi
0x1800264e1  mov     [rsp+0C8h+var_A0], rax
0x1800264e6  lea     rcx, [rsp+0C8h+var_88]
0x1800264eb  mov     r8, rsi
0x1800264ee  mov     [rsp+0C8h+fAlertable], r14d
0x1800264f3  mov     rdx, r13
0x1800264f6  call    PopulateAndInsertRecvCtxtInGlobalList
0x1800264fb  mov     edi, eax
0x1800264fd  test    eax, eax
0x1800264ff  jnz     loc_180026792
0x180026505  lea     rbx, [rsp+0C8h+var_88]
0x18002650a  cmp     [rsp+0C8h+arg_28], 0
0x180026512  jz      short loc_180026551
0x180026514  mov     dil, 10h
0x180026517  test    byte ptr cs:xmmword_1800616A0, dil
0x18002651e  jz      short loc_180026542
0x180026520  mov     ecx, [rbx+28h]; netlong
0x180026523  call    cs:__imp_ntohl
0x180026529  mov     edx, 3Bh ; ';'
0x18002652e  mov     r9d, eax
0x180026531  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026538  mov     ecx, 404h
0x18002653d  call    WPP_SF_d
0x180026542  mov     rcx, rbx
0x180026545  call    ProcessRecvFromSocket
0x18002654a  mov     edi, eax
0x18002654c  jmp     loc_180026792
0x180026551  mov     rax, [rbx+38h]
0x180026555  mov     [rsp+0C8h+hEvents], rax
0x18002655a  mov     rax, [r13+340h]
0x180026561  test    rax, rax
0x180026564  jz      short loc_18002656B
0x180026566  mov     [rsp+0C8h+hEvents+8], rax
0x18002656b  neg     rax
0x18002656e  mov     dil, 10h
0x180026571  sbb     esi, esi
0x180026573  neg     esi
0x180026575  test    byte ptr cs:xmmword_1800616A0, dil
0x18002657c  jz      short loc_180026593
0x18002657e  mov     ecx, [rbx+28h]; netlong
0x180026581  call    cs:__imp_ntohl
0x180026587  mov     r9d, r14d
0x18002658a  mov     [rsp+0C8h+fAlertable], eax
0x18002658e  call    WPP_SF_dL
0x180026593  mov     r9d, r14d; dwTimeout
0x180026596  mov     [rsp+0C8h+fAlertable], 0; fAlertable
0x18002659e  xor     r8d, r8d; fWaitAll
0x1800265a1  lea     rdx, [rsp+0C8h+hEvents]; lphEvents
0x1800265a6  lea     ecx, [rsi+1]; cEvents
0x1800265a9  call    cs:__imp_WSAWaitForMultipleEvents
0x1800265af  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x1800265b6  mov     r14d, eax
0x1800265b9  call    cs:__imp_EnterCriticalSection
0x1800265bf  test    r14d, r14d
0x1800265c2  jnz     loc_18002665C
0x1800265c8  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x1800265cf  call    cs:__imp_LeaveCriticalSection
0x1800265d5  cmp     [rbx+40h], r14d
0x1800265d9  jz      short loc_18002663C
0x1800265db  test    byte ptr cs:xmmword_1800616A0, dil
0x1800265e2  jz      short loc_180026605
0x1800265e4  mov     ecx, [rbx+28h]; netlong
0x1800265e7  call    cs:__imp_ntohl
0x1800265ed  lea     edx, [r14+3Dh]
0x1800265f1  mov     ecx, 404h
0x1800265f6  mov     r9d, eax
0x1800265f9  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026600  call    WPP_SF_d
0x180026605  mov     rcx, [rbx+10h]
0x180026609  mov     rax, [rbx+20h]
0x18002660d  mov     rdx, [rcx+7D0h]; Src
0x180026614  mov     rcx, [rcx+2F0h]; void *
0x18002661b  mov     r8d, [rax]; Size
0x18002661e  call    memcpy_0
0x180026623  mov     rdx, [rbx+20h]
0x180026627  mov     rcx, [r13+2F0h]
0x18002662e  mov     edx, [rdx]
0x180026630  call    DhcpLogMessageBytes
0x180026635  xor     edi, edi
0x180026637  jmp     loc_180026788
0x18002663c  test    byte ptr cs:xmmword_1800616A0, dil
0x180026643  jz      loc_180026542
0x180026649  mov     ecx, [rbx+28h]; netlong
0x18002664c  call    cs:__imp_ntohl
0x180026652  mov     edx, 3Eh ; '>'
0x180026657  jmp     loc_18002652E
0x18002665c  xor     r15d, r15d
0x18002665f  cmp     cs:DhcpGlobalRecvFromList, rbx
0x180026666  setz    r15b
0x18002666a  test    byte ptr cs:xmmword_1800616A0, dil
0x180026671  mov     esi, 404h
0x180026676  jz      short loc_180026697
0x180026678  mov     ecx, [rbx+28h]; netlong
0x18002667b  call    cs:__imp_ntohl
0x180026681  mov     edx, 3Fh ; '?'
0x180026686  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x18002668d  mov     r9d, eax
0x180026690  mov     ecx, esi
0x180026692  call    WPP_SF_d
0x180026697  mov     rax, [rbx]
0x18002669a  cmp     [rax+8], rbx
0x18002669e  jnz     loc_1800267A5
0x1800266a4  mov     rcx, [rbx+8]
0x1800266a8  cmp     [rcx], rbx
0x1800266ab  jnz     loc_1800267A5
0x1800266b1  mov     [rcx], rax
0x1800266b4  mov     [rax+8], rcx
0x1800266b8  mov     [rbx+8], rbx
0x1800266bc  mov     [rbx], rbx
0x1800266bf  test    r15d, r15d
0x1800266c2  jz      short loc_180026736
0x1800266c4  mov     al, byte ptr cs:xmmword_1800616A0
0x1800266ca  test    dil, al
0x1800266cd  jz      short loc_1800266F4
0x1800266cf  mov     ecx, [rbx+28h]; netlong
0x1800266d2  call    cs:__imp_ntohl
0x1800266d8  mov     edx, 40h ; '@'
0x1800266dd  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x1800266e4  mov     r9d, eax
0x1800266e7  mov     ecx, esi
0x1800266e9  call    WPP_SF_d
0x1800266ee  mov     al, byte ptr cs:xmmword_1800616A0
0x1800266f4  mov     r15, cs:DhcpGlobalRecvFromList
0x1800266fb  lea     rcx, DhcpGlobalRecvFromList
0x180026702  cmp     r15, rcx
0x180026705  jz      short loc_180026736
0x180026707  test    dil, al
0x18002670a  jz      short loc_18002672C
0x18002670c  mov     ecx, [r15+28h]; netlong
0x180026710  call    cs:__imp_ntohl
0x180026716  mov     edx, 41h ; 'A'
0x18002671b  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026722  mov     r9d, eax
0x180026725  mov     ecx, esi
0x180026727  call    WPP_SF_d
0x18002672c  mov     rcx, [r15+38h]; hEvent
0x180026730  call    cs:__imp_WSASetEvent
0x180026736  lea     rcx, DhcpGlobalRecvFromCritSect; lpCriticalSection
0x18002673d  call    cs:__imp_LeaveCriticalSection
0x180026743  sub     r14d, 1
0x180026747  jz      short loc_180026763
0x180026749  cmp     r14d, 101h
0x180026750  jz      short loc_18002675C
0x180026752  call    cs:__imp_WSAGetLastError
0x180026758  mov     edi, eax
0x18002675a  jmp     short loc_180026788
0x18002675c  mov     edi, 79h ; 'y'
0x180026761  jmp     short loc_180026788
0x180026763  test    byte ptr cs:xmmword_1800616A0, dil
0x18002676a  jz      short loc_180026783
0x18002676c  mov     r9, [r13+18h]
0x180026770  lea     r8, WPP_e939dd388dec3ffbd0e5e439fb696181_Traceguids
0x180026777  mov     edx, 42h ; 'B'
0x18002677c  mov     ecx, esi
0x18002677e  call    WPP_SF_q
0x180026783  mov     edi, 4C7h
0x180026788  mov     rcx, [rbx+38h]; hEvent
0x18002678c  call    cs:__imp_WSACloseEvent
0x180026792  mov     eax, edi
0x180026794  add     rsp, 98h
0x18002679b  pop     r15
0x18002679d  pop     r14
0x18002679f  pop     r13
0x1800267a1  pop     rdi
0x1800267a2  pop     rsi
0x1800267a3  pop     rbx
0x1800267a4  retn
0x1800267a5  mov     ecx, 3
0x1800267aa  int     29h; Win8: RtlFailFast(ecx)
```
