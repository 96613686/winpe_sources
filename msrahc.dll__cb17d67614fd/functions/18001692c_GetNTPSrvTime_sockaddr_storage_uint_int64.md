# GetNTPSrvTime(sockaddr_storage *,uint,__int64 *)

- ea: `0x18001692c`
- end: `0x180016c2f`
- name: `?GetNTPSrvTime@@YAJPEAUsockaddr_storage@@IPEA_J@Z`
- size: `771`
- prototype: `__int64 __fastcall(const struct sockaddr *name, int namelen, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180016c38`

## callees

- `0x180014660`
- `0x18001692c`
- `0x1800171dc`
- `0x18001a5e0`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x180016a90`
- `WS2_32!WSAEventSelect` at `0x180016a90`
- `WS2_32!__imp_closesocket` at `0x180016bf9`
- `WS2_32!__imp_closesocket` at `0x180016bf9`
- `WS2_32!__imp_connect` at `0x18001699b`
- `WS2_32!__imp_connect` at `0x18001699b`
- `WS2_32!__imp_recv` at `0x180016acf`
- `WS2_32!__imp_recv` at `0x180016acf`
- `WS2_32!__imp_send` at `0x180016a47`
- `WS2_32!__imp_send` at `0x180016a47`
- `WS2_32!__imp_socket` at `0x180016974`
- `WS2_32!__imp_socket` at `0x180016974`
- `WS2_32!__imp_WSAGetLastError` at `0x180016bac`
- `WS2_32!__imp_WSAGetLastError` at `0x180016bac`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800169c6`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800169c6`
- `KERNEL32!CreateEventW` at `0x180016a6b`
- `KERNEL32!CreateEventW` at `0x180016a6b`
- `KERNEL32!CloseHandle` at `0x180016c07`
- `KERNEL32!CloseHandle` at `0x180016c07`
- `KERNEL32!WaitForSingleObject` at `0x180016aad`
- `KERNEL32!WaitForSingleObject` at `0x180016aad`

## string_xrefs

- `0x180016b96`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`
- `0x180016bbc`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`

## pseudocode

```c
__int64 __fastcall GetNTPSrvTime(const struct sockaddr *name, int namelen, unsigned __int64 *a3)
{
  void *v3; // rsi
  int sa_family; // ecx
  SOCKET v8; // rax
  const struct _EVENT_DESCRIPTOR *v9; // rdx
  CEventLogger *v10; // rcx
  SOCKET v11; // r14
  const struct _EVENT_DESCRIPTOR *v12; // rdx
  CEventLogger *v13; // rcx
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  CEventLogger *v15; // rcx
  HANDLE EventW; // rax
  unsigned __int64 v17; // rdx
  CEventLogger *v18; // rcx
  unsigned int v19; // r9d
  unsigned int v20; // ebx
  unsigned int Error; // eax
  const struct _EVENT_DESCRIPTOR *v22; // rdx
  CEventLogger *v23; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-40h] BYREF
  char buf[16]; // [rsp+38h] [rbp-38h] BYREF
  __int128 v27; // [rsp+48h] [rbp-28h]
  __int128 v28; // [rsp+58h] [rbp-18h]

  v3 = 0;
  *a3 = 0;
  sa_family = name->sa_family;
  *(_OWORD *)buf = 0;
  v27 = 0;
  v28 = 0;
  v8 = socket(sa_family, 2, 17);
  v11 = v8;
  if ( v8 == -1 )
  {
    CEventLogger::LogError(v10, v9, L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp", 0x150u, L"GetNTPSrvTime", 0);
    goto LABEL_18;
  }
  if ( connect(v8, name, namelen) )
  {
    CEventLogger::LogError(
      v13,
      v12,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x155u,
      L"GetNTPSrvTime",
      0);
    goto LABEL_18;
  }
  SystemTimeAsFileTime = 0;
  buf[0] = buf[0] & 0xC0 | 0xB;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((_QWORD *)&v28 + 1) = _byteswap_uint64(
                            ((((unsigned __int64)(2LL * *(_QWORD *)&SystemTimeAsFileTime - 188709696000000000LL) >> 8)
                            / 0x1312D) << 32)
                          | ((((unsigned __int64)(unsigned __int8)(2 * LOBYTE(SystemTimeAsFileTime.dwLowDateTime)) << 24)
                            | ((((unsigned __int64)(2LL * *(_QWORD *)&SystemTimeAsFileTime - 188709696000000000LL) >> 8)
                              % 0x1312D) << 32))
                           / 0x1312D));
  if ( send(v11, buf, 48, 0) == -1 )
  {
    CEventLogger::LogError(
      v15,
      v14,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x162u,
      L"GetNTPSrvTime",
      0);
    goto LABEL_18;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v3 = EventW;
  if ( !EventW )
  {
    v19 = 360;
LABEL_17:
    CEventLogger::LogError(
      v18,
      (const struct _EVENT_DESCRIPTOR *)v17,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      v19,
      L"GetNTPSrvTime",
      0);
LABEL_18:
    v20 = -2147467259;
    Error = WSAGetLastError();
    CEventLogger::LogError(
      v23,
      v22,
      L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
      0x18Cu,
      L"GetNTPSrvTime",
      Error);
    if ( v11 == -1 )
      goto LABEL_22;
    goto LABEL_21;
  }
  if ( WSAEventSelect(v11, EventW, 1) )
  {
    v19 = 368;
    goto LABEL_17;
  }
  if ( WaitForSingleObject(v3, 0x2710u) )
  {
    v19 = 372;
    goto LABEL_17;
  }
  if ( recv(v11, buf, 48, 0) == -1 )
  {
    v19 = 379;
    goto LABEL_17;
  }
  v17 = (*((_QWORD *)&v28 + 1) & 0xFF00000000LL
       | ((*((_QWORD *)&v28 + 1) & 0xFF0000000000LL
         | (((*((_QWORD *)&v28 + 1) >> 16) | *((_QWORD *)&v28 + 1) & 0xFF000000000000uLL) >> 16)) >> 16)) >> 8;
  v18 = (CEventLogger *)(78125
                       * (((_byteswap_uint64(*((unsigned __int64 *)&v28 + 1)) >> 25) & 0x7FFFFFFF80LL) + 0x11933094000LL)
                       + ((78125 * v17 + 0x1000000) >> 25));
  if ( (unsigned __int64)v18 <= 0x19DB1DED53E8000LL )
  {
    v19 = 383;
    goto LABEL_17;
  }
  v20 = 0;
  *a3 = ((unsigned __int64)v18 - 116444736000000000LL) / 0x989680;
  LogServerTime();
LABEL_21:
  closesocket(v11);
LABEL_22:
  if ( v3 )
    CloseHandle(v3);
  return v20;
}

```

## disassembly

```asm
0x18001692c  mov     [rsp-28h+arg_18], rbx
0x180016931  push    rbp
0x180016932  push    rsi
0x180016933  push    rdi
0x180016934  push    r14
0x180016936  push    r15
0x180016938  mov     rbp, rsp
0x18001693b  sub     rsp, 70h
0x18001693f  mov     rax, cs:__security_cookie
0x180016946  xor     rax, rsp
0x180016949  mov     [rbp+var_8], rax
0x18001694d  xorps   xmm0, xmm0
0x180016950  xor     esi, esi
0x180016952  mov     [r8], rsi
0x180016955  mov     rdi, r8
0x180016958  mov     r15d, edx
0x18001695b  mov     rbx, rcx
0x18001695e  movzx   ecx, word ptr [rcx]; af
0x180016961  lea     edx, [rsi+2]; type
0x180016964  lea     r8d, [rsi+11h]; protocol
0x180016968  movups  xmmword ptr [rbp+buf], xmm0
0x18001696c  movups  [rbp+var_28], xmm0
0x180016970  movups  [rbp+var_18], xmm0
0x180016974  call    cs:__imp_socket
0x18001697a  mov     r14, rax
0x18001697d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016981  jnz     short loc_180016992
0x180016983  mov     [rsp+70h+var_48], esi
0x180016987  mov     r9d, 150h
0x18001698d  jmp     loc_180016B8F
0x180016992  mov     r8d, r15d; namelen
0x180016995  mov     rdx, rbx; name
0x180016998  mov     rcx, r14; s
0x18001699b  call    cs:__imp_connect
0x1800169a1  test    eax, eax
0x1800169a3  jz      short loc_1800169B4
0x1800169a5  mov     [rsp+70h+var_48], esi
0x1800169a9  mov     r9d, 155h
0x1800169af  jmp     loc_180016B8F
0x1800169b4  mov     al, [rbp+buf]
0x1800169b7  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800169bb  and     al, 0CBh
0x1800169bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1800169c1  or      al, 0Bh
0x1800169c3  mov     [rbp+buf], al
0x1800169c6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800169cc  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800169cf  mov     r15, 0D6BF94D5E57A42BDh
0x1800169d9  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x1800169dc  shl     rcx, 20h
0x1800169e0  or      rcx, rax
0x1800169e3  mov     rax, 0FD619188043F8000h
0x1800169ed  lea     r8, [rax+rcx*2]
0x1800169f1  mov     rax, r15
0x1800169f4  mov     rcx, r8
0x1800169f7  shr     rcx, 8
0x1800169fb  mul     rcx
0x1800169fe  mov     r9, rdx
0x180016a01  shr     r9, 10h
0x180016a05  imul    rax, r9, 1312Dh
0x180016a0c  shl     r9, 20h
0x180016a10  sub     rcx, rax
0x180016a13  movzx   eax, r8b
0x180016a17  shl     rax, 18h
0x180016a1b  shl     rcx, 20h
0x180016a1f  or      rcx, rax
0x180016a22  mov     rax, r15
0x180016a25  mul     rcx
0x180016a28  mov     rcx, r14; s
0x180016a2b  shr     rdx, 10h
0x180016a2f  or      rdx, r9
0x180016a32  xor     r9d, r9d; flags
0x180016a35  bswap   rdx
0x180016a38  mov     qword ptr [rbp+var_18+8], rdx
0x180016a3c  lea     rdx, [rbp+buf]; buf
0x180016a40  lea     ebx, [r9+30h]
0x180016a44  mov     r8d, ebx; len
0x180016a47  call    cs:__imp_send
0x180016a4d  cmp     eax, 0FFFFFFFFh
0x180016a50  jnz     short loc_180016A61
0x180016a52  mov     [rsp+70h+var_48], esi
0x180016a56  mov     r9d, 162h
0x180016a5c  jmp     loc_180016B8F
0x180016a61  xor     r9d, r9d; lpName
0x180016a64  xor     r8d, r8d; bInitialState
0x180016a67  xor     edx, edx; bManualReset
0x180016a69  xor     ecx, ecx; lpEventAttributes
0x180016a6b  call    cs:__imp_CreateEventW
0x180016a71  mov     rsi, rax
0x180016a74  test    rax, rax
0x180016a77  jnz     short loc_180016A84
0x180016a79  mov     r9d, 168h
0x180016a7f  jmp     loc_180016B87
0x180016a84  mov     r8d, 1; lNetworkEvents
0x180016a8a  mov     rdx, rsi; hEventObject
0x180016a8d  mov     rcx, r14; s
0x180016a90  call    cs:__imp_WSAEventSelect
0x180016a96  test    eax, eax
0x180016a98  jz      short loc_180016AA5
0x180016a9a  mov     r9d, 170h
0x180016aa0  jmp     loc_180016B87
0x180016aa5  mov     edx, 2710h; dwMilliseconds
0x180016aaa  mov     rcx, rsi; hHandle
0x180016aad  call    cs:__imp_WaitForSingleObject
0x180016ab3  test    eax, eax
0x180016ab5  jz      short loc_180016AC2
0x180016ab7  mov     r9d, 174h
0x180016abd  jmp     loc_180016B87
0x180016ac2  xor     r9d, r9d; flags
0x180016ac5  lea     rdx, [rbp+buf]; buf
0x180016ac9  mov     r8d, ebx; len
0x180016acc  mov     rcx, r14; s
0x180016acf  call    cs:__imp_recv
0x180016ad5  cmp     eax, 0FFFFFFFFh
0x180016ad8  jnz     short loc_180016AE5
0x180016ada  mov     r9d, 17Bh
0x180016ae0  jmp     loc_180016B87
0x180016ae5  mov     rax, qword ptr [rbp+var_18+8]
0x180016ae9  mov     rdx, 7FFFFFFF80h
0x180016af3  mov     rcx, rax
0x180016af6  mov     r9, 0FF0000000000h
0x180016b00  bswap   rcx
0x180016b03  shr     rcx, 19h
0x180016b07  and     rcx, rdx
0x180016b0a  mov     rdx, 11933094000h
0x180016b14  add     rcx, rdx
0x180016b17  mov     rdx, rax
0x180016b1a  imul    r8, rcx, 1312Dh
0x180016b21  mov     rcx, 0FF000000000000h
0x180016b2b  and     rdx, rcx
0x180016b2e  mov     rcx, rax
0x180016b31  shr     rcx, 10h
0x180016b35  or      rdx, rcx
0x180016b38  mov     rcx, rax
0x180016b3b  and     rcx, r9
0x180016b3e  shr     rdx, 10h
0x180016b42  or      rdx, rcx
0x180016b45  mov     rcx, 0FF00000000h
0x180016b4f  and     rax, rcx
0x180016b52  shr     rdx, 10h
0x180016b56  or      rdx, rax
0x180016b59  mov     rax, 19DB1DED53E8000h
0x180016b63  shr     rdx, 8; struct _EVENT_DESCRIPTOR *
0x180016b67  imul    rcx, rdx, 1312Dh
0x180016b6e  add     rcx, 1000000h
0x180016b75  shr     rcx, 19h
0x180016b79  add     rcx, r8; this
0x180016b7c  cmp     rcx, rax
0x180016b7f  ja      short loc_180016BD5
0x180016b81  mov     r9d, 17Fh; unsigned int
0x180016b87  mov     [rsp+70h+var_48], 0; unsigned int
0x180016b8f  lea     rdi, aGetntpsrvtime; "GetNTPSrvTime"
0x180016b96  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016b9d  mov     [rsp+70h+var_50], rdi; unsigned __int16 *
0x180016ba2  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016ba7  mov     ebx, 80004005h
0x180016bac  call    cs:__imp_WSAGetLastError
0x180016bb2  mov     [rsp+70h+var_48], eax; unsigned int
0x180016bb6  mov     r9d, 18Ch; unsigned int
0x180016bbc  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x180016bc3  mov     [rsp+70h+var_50], rdi; unsigned __int16 *
0x180016bc8  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x180016bcd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180016bd1  jz      short loc_180016BFF
0x180016bd3  jmp     short loc_180016BF6
0x180016bd5  mov     rdx, 0FE624E212AC18000h
0x180016bdf  mov     rax, r15
0x180016be2  add     rdx, rcx
0x180016be5  xor     ebx, ebx
0x180016be7  mul     rdx
0x180016bea  shr     rdx, 17h
0x180016bee  mov     [rdi], rdx
0x180016bf1  call    ?LogServerTime@@YAJUNtTimeEpoch@@_J@Z; LogServerTime(NtTimeEpoch,__int64)
0x180016bf6  mov     rcx, r14; s
0x180016bf9  call    cs:__imp_closesocket
0x180016bff  test    rsi, rsi
0x180016c02  jz      short loc_180016C0D
0x180016c04  mov     rcx, rsi; hObject
0x180016c07  call    cs:__imp_CloseHandle
0x180016c0d  mov     eax, ebx
0x180016c0f  mov     rcx, [rbp+var_8]
0x180016c13  xor     rcx, rsp; StackCookie
0x180016c16  call    __security_check_cookie
0x180016c1b  mov     rbx, [rsp+70h+arg_18]
0x180016c23  add     rsp, 70h
0x180016c27  pop     r15
0x180016c29  pop     r14
0x180016c2b  pop     rdi
0x180016c2c  pop     rsi
0x180016c2d  pop     rbp
0x180016c2e  retn
```
