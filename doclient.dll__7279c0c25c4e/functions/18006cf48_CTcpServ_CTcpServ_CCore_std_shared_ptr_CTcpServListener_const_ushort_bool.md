# CTcpServ::CTcpServ(CCore &,std::shared_ptr<CTcpServListener> const &,ushort,bool)

- ea: `0x18006cf48`
- end: `0x18006d4da`
- name: `??0CTcpServ@@QEAA@AEAVCCore@@AEBV?$shared_ptr@VCTcpServListener@@@std@@G_N@Z`
- size: `1426`
- prototype: `CTcpServ *__fastcall(CTcpServ *this, __int64, _QWORD *, u_short, char)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18004ae0c`

## callees

- `0x180008fb8`
- `0x18000cea4`
- `0x18006cf48`
- `0x18006d654`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800bddd8`
- `0x1800bde20`
- `0x1800f82f0`
- `0x1800f8314`
- `0x1800f8320`
- `0x180108e50`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cfdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006cfdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d052`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006d052`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d065`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006d065`
- `WS2_32!WSASocketW` at `0x18006d03f`
- `WS2_32!WSASocketW` at `0x18006d03f`
- `WS2_32!WSAIoctl` at `0x18006d0f1`
- `WS2_32!WSAIoctl` at `0x18006d32a`
- `WS2_32!WSAIoctl` at `0x18006d0f1`
- `WS2_32!WSAIoctl` at `0x18006d32a`
- `WS2_32!__imp_bind` at `0x18006d258`
- `WS2_32!__imp_bind` at `0x18006d258`
- `WS2_32!__imp_closesocket` at `0x18006d05d`
- `WS2_32!__imp_closesocket` at `0x18006d05d`
- `WS2_32!__imp_htons` at `0x18006d240`
- `WS2_32!__imp_htons` at `0x18006d240`
- `WS2_32!__imp_listen` at `0x18006d29c`
- `WS2_32!__imp_listen` at `0x18006d29c`
- `WS2_32!__imp_setsockopt` at `0x18006d16d`
- `WS2_32!__imp_setsockopt` at `0x18006d1c8`
- `WS2_32!__imp_setsockopt` at `0x18006d16d`
- `WS2_32!__imp_setsockopt` at `0x18006d1c8`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d06f`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d100`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d17c`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d1d7`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d267`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d2ab`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d339`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d06f`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d100`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d17c`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d1d7`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d267`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d2ab`
- `WS2_32!__imp_WSAGetLastError` at `0x18006d339`

## string_xrefs

- `0x18006cff6`: `_core.GetTaskThread().IsCurrentThread()`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
CTcpServ *__fastcall CTcpServ::CTcpServ(CTcpServ *this, __int64 a2, _QWORD *a3, u_short a4, char a5)
{
  __int64 v7; // rax
  char *v8; // r12
  __int64 v9; // rbx
  SOCKET v10; // r14
  SOCKET v11; // rsi
  DWORD LastError; // ebx
  int Error; // eax
  signed int v14; // ebx
  __int64 v15; // r9
  __int64 v16; // r9
  int v17; // eax
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // r9
  int v21; // eax
  __int64 v22; // r9
  int v23; // eax
  __int64 v24; // r9
  int v25; // eax
  int v26; // eax
  int v27; // eax
  _OWORD *v28; // rax
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rdx
  int v32; // eax
  int g; // [rsp+20h] [rbp-E0h]
  int ga; // [rsp+20h] [rbp-E0h]
  int gb; // [rsp+20h] [rbp-E0h]
  int gc; // [rsp+20h] [rbp-E0h]
  const char *dwFlags; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsa; // [rsp+28h] [rbp-D8h]
  _QWORD v40[7]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v41; // [rsp+98h] [rbp-68h]
  DWORD lpcbBytesReturned; // [rsp+A0h] [rbp-60h] BYREF
  _DWORD v43[4]; // [rsp+A8h] [rbp-58h] BYREF
  DWORD cbBytesReturned; // [rsp+B8h] [rbp-48h] BYREF
  char optval[4]; // [rsp+BCh] [rbp-44h] BYREF
  char v46[8]; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD vInBuffer[3]; // [rsp+C8h] [rbp-38h] BYREF
  struct sockaddr name[8]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  v7 = a3[1];
  if ( v7 )
    _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
  *((_QWORD *)this + 1) = *a3;
  *((_QWORD *)this + 2) = a3[1];
  *((_QWORD *)this + 3) = -1;
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 5) = 0;
  v8 = (char *)this + 48;
  *((_QWORD *)this + 6) = 0;
  memset((char *)this + 56, 0, 0x120u);
  v9 = *(_QWORD *)(*(_QWORD *)this + 8LL);
  if ( *(_DWORD *)(v9 + 176) != GetCurrentThreadId() )
  {
    LogMessage(
      2u,
      "CTcpServ::CTcpServ",
      0x12u,
      "TelemetryAssert (%s): %s",
      "_core.GetTaskThread().IsCurrentThread()",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v10 = WSASocketW(23, 1, 6, 0, 0, 1u);
  v11 = *((_QWORD *)this + 3);
  if ( v11 != -1 )
  {
    LastError = GetLastError();
    closesocket(v11);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 3) = v10;
  Error = WSAGetLastError();
  v14 = -2147467259;
  if ( Error )
  {
    v15 = (unsigned __int16)Error | 0x80070000;
    if ( Error <= 0 )
      v15 = (unsigned int)Error;
  }
  else
  {
    v15 = 2147500037LL;
  }
  if ( v10 == -1 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v15,
      g);
  if ( a5 )
  {
    cbBytesReturned = 0;
    LODWORD(vInBuffer[0]) = 0;
    if ( WSAIoctl(*((_QWORD *)this + 3), 0x98000018, vInBuffer, 4u, 0, 0, &cbBytesReturned, 0, 0) )
    {
      v17 = WSAGetLastError();
      if ( v17 )
      {
        v16 = (unsigned __int16)v17 | 0x80070000;
        if ( v17 <= 0 )
          v16 = (unsigned int)v17;
      }
      else
      {
        v16 = 2147500037LL;
      }
    }
    else
    {
      v16 = 0;
    }
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0x26,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v16,
      (int)"Setting SIO_SET_PRIORITY_HINT on the listening socket failed; error ignored",
      dwFlagsa);
  }
  *(_DWORD *)optval = 0;
  if ( setsockopt(*((_QWORD *)this + 3), 41, 27, optval, 4) )
  {
    v19 = WSAGetLastError();
    if ( v19 )
    {
      v18 = (unsigned __int16)v19 | 0x80070000;
      if ( v19 <= 0 )
        v18 = (unsigned int)v19;
    }
    else
    {
      v18 = 2147500037LL;
    }
  }
  else
  {
    v18 = 0;
  }
  if ( (int)v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2C,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v18,
      ga);
  *(_DWORD *)v46 = 10;
  if ( setsockopt(*((_QWORD *)this + 3), 41, 23, v46, 4) )
  {
    v21 = WSAGetLastError();
    if ( v21 )
    {
      v20 = (unsigned __int16)v21 | 0x80070000;
      if ( v21 <= 0 )
        v20 = (unsigned int)v21;
    }
    else
    {
      v20 = 2147500037LL;
    }
  }
  else
  {
    v20 = 0;
  }
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x33,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
    (const char *)v20,
    (int)"Setting PROTECTION_LEVEL_UNRESTRICTED on the listening socket failed; error ignored",
    dwFlags);
  memset(name, 0, sizeof(name));
  name[0].sa_family = 23;
  *(_DWORD *)&name[0].sa_data[2] = 0;
  *(_OWORD *)&name[0].sa_data[6] = 0;
  *(_DWORD *)&name[1].sa_data[6] = 0;
  *(_WORD *)name[0].sa_data = htons(a4);
  if ( bind(*((_QWORD *)this + 3), name, 128) )
  {
    v23 = WSAGetLastError();
    if ( v23 )
    {
      v22 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v22 = (unsigned int)v23;
    }
    else
    {
      v22 = 2147500037LL;
    }
  }
  else
  {
    v22 = 0;
  }
  if ( (int)v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v22,
      gb);
  if ( listen(*((_QWORD *)this + 3), 0x7FFFFFFF) )
  {
    v25 = WSAGetLastError();
    if ( v25 )
    {
      v24 = (unsigned __int16)v25 | 0x80070000;
      if ( v25 <= 0 )
        v24 = (unsigned int)v25;
    }
    else
    {
      v24 = 2147500037LL;
    }
  }
  else
  {
    v24 = 0;
  }
  if ( (int)v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)v24,
      gb);
  lpcbBytesReturned = 0;
  v43[0] = -1254720015;
  v43[1] = 298830764;
  v43[2] = -2147431787;
  v43[3] = -1834923937;
  if ( WSAIoctl(*((_QWORD *)this + 3), 0xC8000006, v43, 0x10u, v8, 8u, &lpcbBytesReturned, 0, 0) )
  {
    v26 = WSAGetLastError();
    if ( v26 )
    {
      v14 = (unsigned __int16)v26 | 0x80070000;
      if ( v26 <= 0 )
        v14 = v26;
    }
  }
  else
  {
    v14 = 0;
  }
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4A,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)(unsigned int)v14,
      gc);
  v27 = CIoCompletionPort::AssociateHandle((CIoCompletionPort *)(*(_QWORD *)this + 24LL), *((void **)this + 3));
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4D,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)(unsigned int)v27,
      gc);
  v28 = operator new(0x30u);
  vInBuffer[0] = v28;
  *v28 = 0;
  v28[1] = 0;
  v28[2] = 0;
  *((_QWORD *)v28 + 4) = v28;
  *((_BYTE *)v28 + 40) = 0;
  *v28 = 0;
  v28[1] = 0;
  *((_BYTE *)v28 + 40) = 0;
  v29 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v28;
  if ( v29 )
    operator delete(v29);
  v30 = *(_QWORD *)this + 24LL;
  v40[0] = ___7___Func_impl_no_alloc_V_lambda_1___1___0CTcpServ__QEAA_AEAVCCore__AEBV__shared_ptr_VCTcpServListener___std__G_N_Z_XJIPEAVCOverlappedIoOp___std__6B_;
  v40[1] = this;
  v41 = v40;
  CIoCompletionPort::RegisterCallback(v30, *(_QWORD *)(*((_QWORD *)this + 5) + 32LL), v40);
  if ( v41 )
  {
    LOBYTE(v31) = v41 != v40;
    (*(void (__fastcall **)(_QWORD *, __int64))(*v41 + 32LL))(v41, v31);
  }
  vInBuffer[1] = 1;
  vInBuffer[0] = this;
  v32 = CTcpServ::_BeginAccept(this);
  if ( v32 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x58,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\TcpServ.cpp",
      (const char *)(unsigned int)v32,
      gc);
  return this;
}

```

## disassembly

```asm
0x18006cf48  mov     [rsp-8+arg_8], rbx
0x18006cf4d  push    rbp
0x18006cf4e  push    rsi
0x18006cf4f  push    rdi
0x18006cf50  push    r12
0x18006cf52  push    r13
0x18006cf54  push    r14
0x18006cf56  push    r15
0x18006cf58  lea     rbp, [rsp-70h]
0x18006cf5d  sub     rsp, 170h
0x18006cf64  mov     rax, cs:__security_cookie
0x18006cf6b  xor     rax, rsp
0x18006cf6e  mov     [rbp+0A0h+var_40], rax
0x18006cf72  movzx   r15d, r9w
0x18006cf76  mov     rdi, rcx
0x18006cf79  mov     [rsp+1A0h+var_150], rcx
0x18006cf7e  xor     r13d, r13d
0x18006cf81  mov     [rcx], rdx
0x18006cf84  mov     [rcx+8], r13
0x18006cf88  mov     [rcx+10h], r13
0x18006cf8c  mov     rax, [r8+8]
0x18006cf90  lea     esi, [r13+1]
0x18006cf94  test    rax, rax
0x18006cf97  jz      short loc_18006CF9D
0x18006cf99  lock add [rax+8], esi
0x18006cf9d  mov     rax, [r8]
0x18006cfa0  mov     [rcx+8], rax
0x18006cfa4  mov     rax, [r8+8]
0x18006cfa8  mov     [rcx+10h], rax
0x18006cfac  or      rax, 0FFFFFFFFFFFFFFFFh
0x18006cfb0  mov     [rcx+18h], rax
0x18006cfb4  mov     [rcx+20h], rax
0x18006cfb8  mov     [rcx+28h], r13
0x18006cfbc  lea     r12, [rcx+30h]
0x18006cfc0  mov     [r12], r13
0x18006cfc4  add     rcx, 38h ; '8'; void *
0x18006cfc8  xor     edx, edx; Val
0x18006cfca  mov     r8d, 120h; Size
0x18006cfd0  call    memset
0x18006cfd5  mov     rax, [rdi]
0x18006cfd8  mov     rbx, [rax+8]
0x18006cfdc  call    cs:__imp_GetCurrentThreadId
0x18006cfe2  cmp     [rbx+0B0h], eax
0x18006cfe8  jz      short loc_18006D029
0x18006cfea  lea     rax, aFailed; "Failed"
0x18006cff1  mov     qword ptr [rsp+1A0h+dwFlags], rax
0x18006cff6  lea     rax, aCoreGettaskthr; "_core.GetTaskThread().IsCurrentThread()"
0x18006cffd  mov     qword ptr [rsp+1A0h+g], rax
0x18006d002  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x18006d009  mov     r8d, 12h; unsigned int
0x18006d00f  lea     rdx, aCtcpservCtcpse; "CTcpServ::CTcpServ"
0x18006d016  lea     ecx, [r8-10h]; unsigned __int8
0x18006d01a  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x18006d01f  or      ecx, 0FFFFFFFFh; unsigned int
0x18006d022  mov     edx, ecx; unsigned int
0x18006d024  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18006d029  mov     [rsp+1A0h+dwFlags], esi; char *
0x18006d02d  mov     [rsp+1A0h+g], r13d; int
0x18006d032  xor     r9d, r9d; lpProtocolInfo
0x18006d035  lea     r8d, [r9+6]; protocol
0x18006d039  mov     edx, esi; type
0x18006d03b  lea     ecx, [r9+17h]; af
0x18006d03f  call    cs:__imp_WSASocketW
0x18006d045  mov     r14, rax
0x18006d048  mov     rsi, [rdi+18h]
0x18006d04c  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18006d050  jz      short loc_18006D06B
0x18006d052  call    cs:__imp_GetLastError
0x18006d058  mov     ebx, eax
0x18006d05a  mov     rcx, rsi; s
0x18006d05d  call    cs:__imp_closesocket
0x18006d063  mov     ecx, ebx; dwErrCode
0x18006d065  call    cs:__imp_SetLastError
0x18006d06b  mov     [rdi+18h], r14
0x18006d06f  call    cs:__imp_WSAGetLastError
0x18006d075  mov     ebx, 80004005h
0x18006d07a  test    eax, eax
0x18006d07c  jz      short loc_18006D091
0x18006d07e  movzx   r9d, ax
0x18006d082  or      r9d, 80070000h
0x18006d089  test    eax, eax
0x18006d08b  cmovle  r9d, eax
0x18006d08f  jmp     short loc_18006D094
0x18006d091  mov     r9d, ebx; char *
0x18006d094  mov     rcx, [rbp+0A8h]; this
0x18006d09b  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x18006d09f  jz      loc_18006D47C
0x18006d0a5  lea     rsi, aCW1SSrcDeliver_12; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x18006d0ac  cmp     [rbp+0A0h+arg_20], r13b
0x18006d0b3  jz      loc_18006D14A
0x18006d0b9  mov     [rbp+0A0h+cbBytesReturned], r13d
0x18006d0bd  mov     dword ptr [rbp+0A0h+vInBuffer], r13d
0x18006d0c1  mov     [rsp+1A0h+lpCompletionRoutine], r13; lpCompletionRoutine
0x18006d0c6  mov     [rsp+1A0h+lpOverlapped], r13; lpOverlapped
0x18006d0cb  lea     rax, [rbp+0A0h+cbBytesReturned]
0x18006d0cf  mov     [rsp+1A0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18006d0d4  mov     [rsp+1A0h+dwFlags], r13d; char *
0x18006d0d9  mov     qword ptr [rsp+1A0h+g], r13; lpvOutBuffer
0x18006d0de  mov     r9d, 4; cbInBuffer
0x18006d0e4  lea     r8, [rbp+0A0h+vInBuffer]; lpvInBuffer
0x18006d0e8  mov     edx, 98000018h; dwIoControlCode
0x18006d0ed  mov     rcx, [rdi+18h]; s
0x18006d0f1  call    cs:__imp_WSAIoctl
0x18006d0f7  test    eax, eax
0x18006d0f9  jnz     short loc_18006D100
0x18006d0fb  mov     r9d, r13d
0x18006d0fe  jmp     short loc_18006D122
0x18006d100  call    cs:__imp_WSAGetLastError
0x18006d106  test    eax, eax
0x18006d108  jz      short loc_18006D11F
0x18006d10a  movzx   r9d, ax
0x18006d10e  mov     r14d, 80070000h
0x18006d114  or      r9d, r14d
0x18006d117  test    eax, eax
0x18006d119  cmovle  r9d, eax
0x18006d11d  jmp     short loc_18006D128
0x18006d11f  mov     r9d, ebx; char *
0x18006d122  mov     r14d, 80070000h
0x18006d128  mov     rcx, [rbp+0A8h]; this
0x18006d12f  lea     rax, aSettingSioSetP_0; "Setting SIO_SET_PRIORITY_HINT on the li"...
0x18006d136  mov     qword ptr [rsp+1A0h+g], rax; int
0x18006d13b  mov     r8, rsi; unsigned int
0x18006d13e  mov     edx, 26h ; '&'; void *
0x18006d143  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006d148  jmp     short loc_18006D150
0x18006d14a  mov     r14d, 80070000h
0x18006d150  mov     dword ptr [rbp+0A0h+optval], r13d
0x18006d154  mov     [rsp+1A0h+g], 4; int
0x18006d15c  lea     r9, [rbp+0A0h+optval]; optval
0x18006d160  mov     edx, 29h ; ')'; level
0x18006d165  lea     r8d, [rdx-0Eh]; optname
0x18006d169  mov     rcx, [rdi+18h]; s
0x18006d16d  call    cs:__imp_setsockopt
0x18006d173  test    eax, eax
0x18006d175  jnz     short loc_18006D17C
0x18006d177  mov     r9d, r13d
0x18006d17a  jmp     short loc_18006D198
0x18006d17c  call    cs:__imp_WSAGetLastError
0x18006d182  test    eax, eax
0x18006d184  jz      short loc_18006D195
0x18006d186  movzx   r9d, ax
0x18006d18a  or      r9d, r14d
0x18006d18d  test    eax, eax
0x18006d18f  cmovle  r9d, eax
0x18006d193  jmp     short loc_18006D198
0x18006d195  mov     r9d, ebx; char *
0x18006d198  mov     rcx, [rbp+0A8h]; this
0x18006d19f  test    r9d, r9d
0x18006d1a2  js      loc_18006D48E
0x18006d1a8  mov     dword ptr [rbp+0A0h+var_E0], 0Ah
0x18006d1af  mov     [rsp+1A0h+g], 4; optlen
0x18006d1b7  lea     r9, [rbp+0A0h+var_E0]; optval
0x18006d1bb  mov     edx, 29h ; ')'; level
0x18006d1c0  lea     r8d, [rdx-12h]; optname
0x18006d1c4  mov     rcx, [rdi+18h]; s
0x18006d1c8  call    cs:__imp_setsockopt
0x18006d1ce  test    eax, eax
0x18006d1d0  jnz     short loc_18006D1D7
0x18006d1d2  mov     r9d, r13d
0x18006d1d5  jmp     short loc_18006D1F3
0x18006d1d7  call    cs:__imp_WSAGetLastError
0x18006d1dd  test    eax, eax
0x18006d1df  jz      short loc_18006D1F0
0x18006d1e1  movzx   r9d, ax
0x18006d1e5  or      r9d, r14d
0x18006d1e8  test    eax, eax
0x18006d1ea  cmovle  r9d, eax
0x18006d1ee  jmp     short loc_18006D1F3
0x18006d1f0  mov     r9d, ebx; char *
0x18006d1f3  mov     rcx, [rbp+0A8h]; this
0x18006d1fa  lea     rax, aSettingProtect; "Setting PROTECTION_LEVEL_UNRESTRICTED o"...
0x18006d201  mov     qword ptr [rsp+1A0h+g], rax; int
0x18006d206  mov     r8, rsi; unsigned int
0x18006d209  mov     edx, 33h ; '3'; void *
0x18006d20e  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18006d213  xor     edx, edx; Val
0x18006d215  mov     r8d, 80h; Size
0x18006d21b  lea     rcx, [rbp+0A0h+name]; void *
0x18006d21f  call    memset
0x18006d224  mov     eax, 17h
0x18006d229  mov     [rbp+0A0h+name.sa_family], ax
0x18006d22d  mov     dword ptr [rbp+0A0h+name.sa_data+2], r13d
0x18006d231  xorps   xmm0, xmm0
0x18006d234  movups  xmmword ptr [rbp+0A0h+name.sa_data+6], xmm0
0x18006d238  mov     [rbp+0A0h+var_A8], r13d
0x18006d23c  movzx   ecx, r15w; hostshort
0x18006d240  call    cs:__imp_htons
0x18006d246  mov     word ptr [rbp+0A0h+name.sa_data], ax
0x18006d24a  mov     r8d, 80h; namelen
0x18006d250  lea     rdx, [rbp+0A0h+name]; name
0x18006d254  mov     rcx, [rdi+18h]; s
0x18006d258  call    cs:__imp_bind
0x18006d25e  test    eax, eax
0x18006d260  jnz     short loc_18006D267
0x18006d262  mov     r9d, r13d
0x18006d265  jmp     short loc_18006D283
0x18006d267  call    cs:__imp_WSAGetLastError
0x18006d26d  test    eax, eax
0x18006d26f  jz      short loc_18006D280
0x18006d271  movzx   r9d, ax
0x18006d275  or      r9d, r14d
0x18006d278  test    eax, eax
0x18006d27a  cmovle  r9d, eax
0x18006d27e  jmp     short loc_18006D283
0x18006d280  mov     r9d, ebx; char *
0x18006d283  mov     rcx, [rbp+0A8h]; this
0x18006d28a  test    r9d, r9d
0x18006d28d  js      loc_18006D49C
0x18006d293  mov     edx, 7FFFFFFFh; backlog
0x18006d298  mov     rcx, [rdi+18h]; s
0x18006d29c  call    cs:__imp_listen
0x18006d2a2  test    eax, eax
0x18006d2a4  jnz     short loc_18006D2AB
0x18006d2a6  mov     r9d, r13d
0x18006d2a9  jmp     short loc_18006D2C7
0x18006d2ab  call    cs:__imp_WSAGetLastError
0x18006d2b1  test    eax, eax
0x18006d2b3  jz      short loc_18006D2C4
0x18006d2b5  movzx   r9d, ax
0x18006d2b9  or      r9d, r14d
0x18006d2bc  test    eax, eax
0x18006d2be  cmovle  r9d, eax
0x18006d2c2  jmp     short loc_18006D2C7
0x18006d2c4  mov     r9d, ebx; char *
0x18006d2c7  mov     rcx, [rbp+0A8h]; this
0x18006d2ce  test    r9d, r9d
0x18006d2d1  js      loc_18006D4AA
0x18006d2d7  mov     [rbp+0A0h+var_100], r13d
0x18006d2db  mov     [rbp+0A0h+var_F8], 0B5367DF1h
0x18006d2e2  mov     [rbp+0A0h+var_F4], 11CFCBACh
0x18006d2e9  mov     [rbp+0A0h+var_F0], 8000CA95h
0x18006d2f0  mov     [rbp+0A0h+var_EC], 92A1485Fh
0x18006d2f7  mov     [rsp+1A0h+lpCompletionRoutine], r13; lpCompletionRoutine
0x18006d2fc  mov     [rsp+1A0h+lpOverlapped], r13; lpOverlapped
0x18006d301  lea     rax, [rbp+0A0h+var_100]
0x18006d305  mov     [rsp+1A0h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18006d30a  mov     [rsp+1A0h+dwFlags], 8; cbOutBuffer
0x18006d312  mov     qword ptr [rsp+1A0h+g], r12; int
0x18006d317  mov     r9d, 10h; cbInBuffer
0x18006d31d  lea     r8, [rbp+0A0h+var_F8]; lpvInBuffer
0x18006d321  mov     edx, 0C8000006h; dwIoControlCode
0x18006d326  mov     rcx, [rdi+18h]; s
0x18006d32a  call    cs:__imp_WSAIoctl
0x18006d330  test    eax, eax
0x18006d332  jnz     short loc_18006D339
0x18006d334  mov     ebx, r13d
0x18006d337  jmp     short loc_18006D34E
0x18006d339  call    cs:__imp_WSAGetLastError
0x18006d33f  test    eax, eax
0x18006d341  jz      short loc_18006D34E
0x18006d343  movzx   ebx, ax
0x18006d346  or      ebx, r14d
0x18006d349  test    eax, eax
0x18006d34b  cmovle  ebx, eax
0x18006d34e  mov     rcx, [rbp+0A8h]; this
0x18006d355  test    ebx, ebx
0x18006d357  js      loc_18006D4B8
0x18006d35d  mov     rcx, [rdi]
0x18006d360  add     rcx, 18h; this
0x18006d364  mov     rdx, [rdi+18h]; void *
0x18006d368  call    ?AssociateHandle@CIoCompletionPort@@QEBAJPEAX@Z; CIoCompletionPort::AssociateHandle(void *)
0x18006d36d  mov     rcx, [rbp+0A8h]; this
0x18006d374  test    eax, eax
0x18006d376  js      loc_18006D4C9
0x18006d37c  mov     ebx, 30h ; '0'
0x18006d381  mov     ecx, ebx; Size
0x18006d383  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006d388  mov     r8, rax
0x18006d38b  mov     [rbp+0A0h+vInBuffer], rax
0x18006d38f  xorps   xmm0, xmm0
0x18006d392  movups  xmmword ptr [rax], xmm0
0x18006d395  movups  xmmword ptr [rax+10h], xmm0
0x18006d399  movups  xmmword ptr [rax+20h], xmm0
0x18006d39d  mov     [rax+20h], rax
0x18006d3a1  xor     eax, eax
0x18006d3a3  mov     [r8+28h], al
0x18006d3a7  movups  xmmword ptr [r8], xmm0
0x18006d3ab  movups  xmmword ptr [r8+10h], xmm0
0x18006d3b0  mov     eax, r13d
0x18006d3b3  xchg    al, [r8+28h]
0x18006d3b7  mov     rcx, [rdi+28h]; Block
0x18006d3bb  mov     [rdi+28h], r8
0x18006d3bf  test    rcx, rcx
0x18006d3c2  jz      short loc_18006D3CB
0x18006d3c4  mov     edx, ebx
0x18006d3c6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006d3cb  mov     rcx, [rdi]
0x18006d3ce  add     rcx, 18h
0x18006d3d2  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_1_@?1???0CTcpServ@@QEAA@AEAVCCore@@AEBV?$shared_ptr@VCTcpServListener@@@std@@G_N@Z@XJIPEAVCOverlappedIoOp@@@std@@6B@; const std::_Func_impl_no_alloc<`CTcpServ::CTcpServ(CCore &,std::shared_ptr<CTcpServListener> const &,ushort,bool)'::`2'::_lambda_1_,void,long,uint,COverlappedIoOp *>::`vftable'
0x18006d3d9  mov     [rsp+1A0h+var_140], rax
0x18006d3de  mov     [rsp+1A0h+var_138], rdi
0x18006d3e3  lea     rax, [rsp+1A0h+var_140]
0x18006d3e8  mov     [rbp+0A0h+var_108], rax
0x18006d3ec  mov     rdx, [rdi+28h]
0x18006d3f0  lea     r8, [rsp+1A0h+var_140]
0x18006d3f5  mov     rdx, [rdx+20h]
0x18006d3f9  call    ?RegisterCallback@CIoCompletionPort@@QEAAXPEBX$$QEBV?$function@$$A6AXJIPEAVCOverlappedIoOp@@@Z@std@@@Z; CIoCompletionPort::RegisterCallback(void const *,std::function<void (long,uint,COverlappedIoOp *)> const &&)
0x18006d3fe  nop
0x18006d3ff  mov     rcx, [rbp+0A0h+var_108]
0x18006d403  test    rcx, rcx
  ... truncated ...
```
