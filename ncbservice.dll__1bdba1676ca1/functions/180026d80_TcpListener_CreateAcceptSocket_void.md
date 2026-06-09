# TcpListener::CreateAcceptSocket(void)

- ea: `0x180026d80`
- end: `0x180026e9f`
- name: `?CreateAcceptSocket@TcpListener@@AEAAKXZ`
- size: `287`
- prototype: `unsigned int __fastcall(TcpListener *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800272e8`

## callees

- `0x18000a0a0`
- `0x18001cb0c`
- `0x18001dd2c`
- `0x180026d80`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026d99`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180026e29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e7c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180026e7c`
- `WS2_32!WSASocketW` at `0x180026de9`
- `WS2_32!WSASocketW` at `0x180026de9`
- `WS2_32!__imp_WSAGetLastError` at `0x180026df5`
- `WS2_32!__imp_WSAGetLastError` at `0x180026df5`

## string_xrefs

- `0x180026e09`: `TcpListener: CreateSocket failed`

## pseudocode

```c
__int64 __fastcall TcpListener::CreateAcceptSocket(TcpListener *this)
{
  void *v2; // rbx
  SOCKET v3; // rax
  unsigned int Error; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  unsigned int v7; // edi
  TcpListener **v8; // rcx
  AcceptSocket *v9; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = operator new(0x20u);
  *((_QWORD *)v2 + 2) = -1;
  *((_DWORD *)v2 + 6) = 1;
  *((_BYTE *)v2 + 28) = 0;
  *((_QWORD *)v2 + 1) = v2;
  *(_QWORD *)v2 = v2;
  v3 = WSASocketW(*((_DWORD *)this + 22), 1, *((_DWORD *)this + 23), 0, 0, 1u);
  if ( v3 == -1 )
  {
    Error = WSAGetLastError();
    v7 = Error;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v6, v5, L"TcpListener: CreateSocket failed", Error);
  }
  else
  {
    *((_QWORD *)v2 + 2) = v3;
    _InterlockedIncrement((volatile signed __int32 *)v2 + 6);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    v8 = (TcpListener **)*((_QWORD *)this + 39);
    if ( *v8 != (TcpListener *)((char *)this + 304) )
      __fastfail(3u);
    *((_QWORD *)v2 + 1) = v8;
    v7 = 0;
    *(_QWORD *)v2 = (char *)this + 304;
    *v8 = (TcpListener *)v2;
    *((_QWORD *)this + 39) = v2;
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    v9 = (AcceptSocket *)*((_QWORD *)this + 40);
    if ( v9 )
      AcceptSocket::ReleaseRef(v9);
    *((_QWORD *)this + 40) = v2;
    _InterlockedIncrement((volatile signed __int32 *)v2 + 6);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  AcceptSocket::ReleaseRef((AcceptSocket *)v2);
  return v7;
}

```

## disassembly

```asm
0x180026d80  mov     [rsp+arg_8], rbx
0x180026d85  mov     [rsp+arg_10], rbp
0x180026d8a  push    rsi
0x180026d8b  push    rdi
0x180026d8c  push    r14
0x180026d8e  sub     rsp, 30h
0x180026d92  mov     rsi, rcx
0x180026d95  add     rcx, 28h ; '('; lpCriticalSection
0x180026d99  call    cs:__imp_EnterCriticalSection
0x180026d9f  mov     ecx, 20h ; ' '; Size
0x180026da4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026da9  xor     r9d, r9d; lpProtocolInfo
0x180026dac  mov     [rsp+48h+dwFlags], 1; dwFlags
0x180026db4  mov     rbx, rax
0x180026db7  mov     [rsp+48h+arg_0], rax
0x180026dbc  mov     [rsp+48h+g], 0; g
0x180026dc4  mov     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x180026dcc  mov     dword ptr [rax+18h], 1
0x180026dd3  lea     edx, [r9+1]; type
0x180026dd7  mov     byte ptr [rax+1Ch], 0
0x180026ddb  mov     [rax+8], rax
0x180026ddf  mov     [rax], rax
0x180026de2  mov     r8d, [rsi+5Ch]; protocol
0x180026de6  mov     ecx, [rsi+58h]; af
0x180026de9  call    cs:__imp_WSASocketW
0x180026def  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180026df3  jnz     short loc_180026E17
0x180026df5  call    cs:__imp_WSAGetLastError
0x180026dfb  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180026e02  mov     edi, eax
0x180026e04  jz      short loc_180026E78
0x180026e06  mov     r9d, eax
0x180026e09  lea     r8, aTcplistenerCre_0; "TcpListener: CreateSocket failed"
0x180026e10  call    McTemplateU0zq_EventWriteTransfer
0x180026e15  jmp     short loc_180026E78
0x180026e17  mov     [rbx+10h], rax
0x180026e1b  lea     rbp, [rsi+108h]
0x180026e22  lock inc dword ptr [rbx+18h]
0x180026e26  mov     rcx, rbp; lpCriticalSection
0x180026e29  call    cs:__imp_EnterCriticalSection
0x180026e2f  lea     rax, [rbp+28h]
0x180026e33  mov     rcx, [rax+8]
0x180026e37  cmp     [rcx], rax
0x180026e3a  jz      short loc_180026E43
0x180026e3c  mov     ecx, 3
0x180026e41  int     29h; Win8: RtlFailFast(ecx)
0x180026e43  mov     [rbx+8], rcx
0x180026e47  xor     edi, edi
0x180026e49  mov     [rbx], rax
0x180026e4c  mov     [rcx], rbx
0x180026e4f  mov     rcx, rbp; lpCriticalSection
0x180026e52  mov     [rax+8], rbx
0x180026e56  call    cs:__imp_LeaveCriticalSection
0x180026e5c  mov     rcx, [rsi+140h]; this
0x180026e63  test    rcx, rcx
0x180026e66  jz      short loc_180026E6D
0x180026e68  call    ?ReleaseRef@AcceptSocket@@QEAAXXZ; AcceptSocket::ReleaseRef(void)
0x180026e6d  mov     [rsi+140h], rbx
0x180026e74  lock inc dword ptr [rbx+18h]
0x180026e78  lea     rcx, [rsi+28h]; lpCriticalSection
0x180026e7c  call    cs:__imp_LeaveCriticalSection
0x180026e82  mov     rcx, rbx; this
0x180026e85  call    ?ReleaseRef@AcceptSocket@@QEAAXXZ; AcceptSocket::ReleaseRef(void)
0x180026e8a  mov     rbx, [rsp+48h+arg_8]
0x180026e8f  mov     eax, edi
0x180026e91  mov     rbp, [rsp+48h+arg_10]
0x180026e96  add     rsp, 30h
0x180026e9a  pop     r14
0x180026e9c  pop     rdi
0x180026e9d  pop     rsi
0x180026e9e  retn
```
