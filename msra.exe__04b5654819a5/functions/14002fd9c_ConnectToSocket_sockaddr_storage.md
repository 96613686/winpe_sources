# ConnectToSocket(sockaddr_storage)

- ea: `0x14002fd9c`
- end: `0x14002ffba`
- name: `?ConnectToSocket@@YAJUsockaddr_storage@@@Z`
- size: `542`
- prototype: `__int64 __fastcall(struct sockaddr_storage *__struct_ptr)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1400311b8`

## callees

- `0x140002463`
- `0x14002fd9c`
- `0x140034ce4`
- `0x140034eac`
- `0x140034ee0`
- `0x14004ad80`

## import_xrefs

- `WS2_32!__imp_closesocket` at `0x14002ff5c`
- `WS2_32!__imp_closesocket` at `0x14002ff5c`
- `WS2_32!__imp_connect` at `0x14002ff08`
- `WS2_32!__imp_connect` at `0x14002ff08`
- `WS2_32!__imp_socket` at `0x14002fe85`
- `WS2_32!__imp_socket` at `0x14002fe85`
- `WS2_32!__imp_WSAGetLastError` at `0x14002fe34`
- `WS2_32!__imp_WSAGetLastError` at `0x14002fe9a`
- `WS2_32!__imp_WSAGetLastError` at `0x14002ff19`
- `WS2_32!__imp_WSAGetLastError` at `0x14002fe34`
- `WS2_32!__imp_WSAGetLastError` at `0x14002fe9a`
- `WS2_32!__imp_WSAGetLastError` at `0x14002ff19`
- `WS2_32!__imp_WSAStartup` at `0x14002fe24`
- `WS2_32!__imp_WSAStartup` at `0x14002fe24`
- `WS2_32!__imp_WSACleanup` at `0x14002feda`
- `WS2_32!__imp_WSACleanup` at `0x14002ff68`
- `WS2_32!__imp_WSACleanup` at `0x14002feda`
- `WS2_32!__imp_WSACleanup` at `0x14002ff68`

## pseudocode

```c
__int64 __fastcall ConnectToSocket(struct sockaddr_storage *a1)
{
  __int128 v1; // xmm1
  sockaddr v2; // xmm2
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm0
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  unsigned int Error; // edi
  int v9; // ebx
  CEventLogger *v10; // rcx
  SOCKET v11; // rax
  SOCKET v12; // rsi
  int v13; // r8d
  const struct _EVENT_DESCRIPTOR *v14; // rdx
  sockaddr name; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v17; // [rsp+40h] [rbp-C0h]
  __int128 v18; // [rsp+50h] [rbp-B0h]
  __int128 v19; // [rsp+60h] [rbp-A0h]
  __int128 v20; // [rsp+70h] [rbp-90h]
  __int128 v21; // [rsp+80h] [rbp-80h]
  __int128 v22; // [rsp+90h] [rbp-70h]
  __int128 v23; // [rsp+A0h] [rbp-60h]
  WSAData WSAData; // [rsp+B0h] [rbp-50h] BYREF

  v1 = *(_OWORD *)&a1->__ss_pad2[16];
  v2 = *(sockaddr *)&a1->ss_family;
  v17 = *(_OWORD *)a1->__ss_pad2;
  v3 = *(_OWORD *)&a1->__ss_pad2[32];
  v18 = v1;
  v4 = *(_OWORD *)&a1->__ss_pad2[48];
  v19 = v3;
  v5 = *(_OWORD *)&a1->__ss_pad2[64];
  v20 = v4;
  v6 = *(_OWORD *)&a1->__ss_pad2[80];
  v21 = v5;
  v7 = *(_OWORD *)&a1->__ss_pad2[96];
  name = v2;
  v23 = v7;
  v22 = v6;
  memset_0(&WSAData, 0, sizeof(WSAData));
  if ( WSAStartup(0x202u, &WSAData) )
  {
    Error = WSAGetLastError();
    v9 = -2147467259;
    CEventLogger::LogError(
      (CEventLogger *)L"ConnectToSocket",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
      0x47Cu,
      L"ConnectToSocket",
      0x80004005);
  }
  else
  {
    v11 = socket(v2.sa_family, 1, 6);
    v12 = v11;
    if ( v11 == -1 )
    {
      Error = WSAGetLastError();
      v9 = -2147467259;
      CEventLogger::LogError(
        (CEventLogger *)L"ConnectToSocket",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
        0x488u,
        L"ConnectToSocket",
        0x80004005);
      WSACleanup();
    }
    else
    {
      v9 = 0;
      Error = 0;
      v13 = 28;
      if ( name.sa_family == 2 )
        v13 = 16;
      if ( connect(v11, &name, v13) == -1 )
      {
        Error = WSAGetLastError();
        v9 = -2147467259;
        CEventLogger::LogError(
          (CEventLogger *)L"ConnectToSocket",
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\radiagutils.cpp",
          0x495u,
          L"ConnectToSocket",
          0x80004005);
      }
      closesocket(v12);
      WSACleanup();
      if ( v9 >= 0 )
      {
        v14 = &RADIAG_Repro_Success;
        goto LABEL_12;
      }
    }
  }
  CEventLogger::LogEvent(v10, &RADIAG_Repro_Failure_code, Error);
  v14 = (const struct _EVENT_DESCRIPTOR *)RADIAG_Repro_Failed;
LABEL_12:
  CEventLogger::LogEvent(v10, v14);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14002fd9c  push    rbp
0x14002fd9e  push    rbx
0x14002fd9f  push    rsi
0x14002fda0  push    rdi
0x14002fda1  lea     rbp, [rsp-168h]
0x14002fda9  sub     rsp, 268h
0x14002fdb0  mov     rax, cs:__security_cookie
0x14002fdb7  xor     rax, rsp
0x14002fdba  mov     [rbp+180h+var_30], rax
0x14002fdc1  movups  xmm0, xmmword ptr [rcx+10h]
0x14002fdc5  xor     edx, edx; Val
0x14002fdc7  mov     r8d, 198h; Size
0x14002fdcd  movups  xmm1, xmmword ptr [rcx+20h]
0x14002fdd1  movups  xmm2, xmmword ptr [rcx]
0x14002fdd4  movaps  [rsp+280h+var_240], xmm0
0x14002fdd9  movups  xmm0, xmmword ptr [rcx+30h]
0x14002fddd  movaps  [rsp+280h+var_230], xmm1
0x14002fde2  movq    rbx, xmm2
0x14002fde7  movups  xmm1, xmmword ptr [rcx+40h]
0x14002fdeb  movaps  [rsp+280h+var_220], xmm0
0x14002fdf0  movups  xmm0, xmmword ptr [rcx+50h]
0x14002fdf4  movaps  [rsp+280h+var_210], xmm1
0x14002fdf9  movups  xmm1, xmmword ptr [rcx+60h]
0x14002fdfd  movaps  [rbp+180h+var_200], xmm0
0x14002fe01  movups  xmm0, xmmword ptr [rcx+70h]
0x14002fe05  lea     rcx, [rbp+180h+WSAData]; void *
0x14002fe09  movaps  xmmword ptr [rsp+280h+name.sa_family], xmm2
0x14002fe0e  movaps  [rbp+180h+var_1E0], xmm0
0x14002fe12  movaps  [rbp+180h+var_1F0], xmm1
0x14002fe16  call    memset_0
0x14002fe1b  mov     ecx, 202h; wVersionRequested
0x14002fe20  lea     rdx, [rbp+180h+WSAData]; lpWSAData
0x14002fe24  call    cs:__imp_WSAStartup
0x14002fe2b  nop     dword ptr [rax+rax+00h]
0x14002fe30  test    eax, eax
0x14002fe32  jz      short loc_14002FE79
0x14002fe34  call    cs:__imp_WSAGetLastError
0x14002fe3b  nop     dword ptr [rax+rax+00h]
0x14002fe40  lea     rcx, aConnecttosocke; "ConnectToSocket"
0x14002fe47  mov     [rsp+280h+var_258], 80004005h; unsigned int
0x14002fe4f  mov     r9d, 47Ch; unsigned int
0x14002fe55  mov     [rsp+280h+var_260], rcx; unsigned __int16 *
0x14002fe5a  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14002fe61  mov     edi, eax
0x14002fe63  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002fe6a  mov     ebx, 80004005h
0x14002fe6f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002fe74  jmp     loc_14002FF78
0x14002fe79  mov     edx, 1; type
0x14002fe7e  movzx   ecx, bx; af
0x14002fe81  lea     r8d, [rdx+5]; protocol
0x14002fe85  call    cs:__imp_socket
0x14002fe8c  nop     dword ptr [rax+rax+00h]
0x14002fe91  mov     rsi, rax
0x14002fe94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14002fe98  jnz     short loc_14002FEEB
0x14002fe9a  call    cs:__imp_WSAGetLastError
0x14002fea1  nop     dword ptr [rax+rax+00h]
0x14002fea6  lea     rcx, aConnecttosocke; "ConnectToSocket"
0x14002fead  mov     [rsp+280h+var_258], 80004005h; unsigned int
0x14002feb5  mov     r9d, 488h; unsigned int
0x14002febb  mov     [rsp+280h+var_260], rcx; unsigned __int16 *
0x14002fec0  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14002fec7  mov     edi, eax
0x14002fec9  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002fed0  mov     ebx, 80004005h
0x14002fed5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002feda  call    cs:__imp_WSACleanup
0x14002fee1  nop     dword ptr [rax+rax+00h]
0x14002fee6  jmp     loc_14002FF78
0x14002feeb  xor     ebx, ebx
0x14002feed  lea     rdx, [rsp+280h+name]; name
0x14002fef2  xor     edi, edi
0x14002fef4  mov     rcx, rsi; s
0x14002fef7  cmp     [rsp+280h+name.sa_family], 2
0x14002fefd  lea     eax, [rbx+10h]
0x14002ff00  lea     r8d, [rbx+1Ch]
0x14002ff04  cmovz   r8d, eax; namelen
0x14002ff08  call    cs:__imp_connect
0x14002ff0f  nop     dword ptr [rax+rax+00h]
0x14002ff14  cmp     eax, 0FFFFFFFFh
0x14002ff17  jnz     short loc_14002FF59
0x14002ff19  call    cs:__imp_WSAGetLastError
0x14002ff20  nop     dword ptr [rax+rax+00h]
0x14002ff25  lea     rcx, aConnecttosocke; "ConnectToSocket"
0x14002ff2c  mov     [rsp+280h+var_258], 80004005h; unsigned int
0x14002ff34  mov     r9d, 495h; unsigned int
0x14002ff3a  mov     [rsp+280h+var_260], rcx; unsigned __int16 *
0x14002ff3f  lea     r8, aBaseDiagnosisR_28; "base\\diagnosis\\ra\\ui\\radiagutils.cp"...
0x14002ff46  mov     edi, eax
0x14002ff48  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14002ff4f  mov     ebx, 80004005h
0x14002ff54  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002ff59  mov     rcx, rsi; s
0x14002ff5c  call    cs:__imp_closesocket
0x14002ff63  nop     dword ptr [rax+rax+00h]
0x14002ff68  call    cs:__imp_WSACleanup
0x14002ff6f  nop     dword ptr [rax+rax+00h]
0x14002ff74  test    ebx, ebx
0x14002ff76  jns     short loc_14002FF90
0x14002ff78  mov     r8d, edi; unsigned int
0x14002ff7b  lea     rdx, RADIAG_Repro_Failure_code; struct _EVENT_DESCRIPTOR *
0x14002ff82  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@I@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,uint)
0x14002ff87  lea     rdx, RADIAG_Repro_Failed
0x14002ff8e  jmp     short loc_14002FF97
0x14002ff90  lea     rdx, RADIAG_Repro_Success; struct _EVENT_DESCRIPTOR *
0x14002ff97  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *)
0x14002ff9c  mov     eax, ebx
0x14002ff9e  mov     rcx, [rbp+180h+var_30]
0x14002ffa5  xor     rcx, rsp; StackCookie
0x14002ffa8  call    __security_check_cookie
0x14002ffad  add     rsp, 268h
0x14002ffb4  pop     rdi
0x14002ffb5  pop     rsi
0x14002ffb6  pop     rbx
0x14002ffb7  pop     rbp
0x14002ffb8  retn
```
