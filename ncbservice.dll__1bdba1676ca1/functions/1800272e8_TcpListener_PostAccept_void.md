# TcpListener::PostAccept(void)

- ea: `0x1800272e8`
- end: `0x18002753d`
- name: `?PostAccept@TcpListener@@AEAAKXZ`
- size: `597`
- prototype: `unsigned int __fastcall(TcpListener *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180026fc8`
- `0x180027150`

## callees

- `0x18000a0a0`
- `0x1800128a8`
- `0x18001cab4`
- `0x18001cb0c`
- `0x18001d8e0`
- `0x180026d80`
- `0x1800272e8`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800274a5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800274a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800274de`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002751d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002751d`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180027400`
- `api-ms-win-core-threadpool-l1-2-0!StartThreadpoolIo` at `0x180027400`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002749b`
- `api-ms-win-core-threadpool-l1-2-0!CancelThreadpoolIo` at `0x18002749b`
- `WS2_32!WSAIoctl` at `0x180027372`
- `WS2_32!WSAIoctl` at `0x180027372`
- `WS2_32!__imp_WSAGetLastError` at `0x18002737c`
- `WS2_32!__imp_WSAGetLastError` at `0x180027479`
- `WS2_32!__imp_WSAGetLastError` at `0x18002737c`
- `WS2_32!__imp_WSAGetLastError` at `0x180027479`

## string_xrefs

- `0x1800273c1`: `PostAccept: Impersonate failed`
- `0x1800273e8`: `PostAccept: CreateAcceptSocket failed`
- `0x1800274f0`: `PostAccept: CreateAcceptSocket failed`

## pseudocode

```c
__int64 __fastcall TcpListener::PostAccept(TcpListener *this)
{
  SOCKET v2; // rcx
  unsigned int Error; // eax
  __int64 v4; // rdx
  __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rcx
  unsigned int AcceptSocket; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  struct AcceptSocket *v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  DWORD v18; // [rsp+58h] [rbp+7h] BYREF
  unsigned int (__fastcall *vOutBuffer)(_QWORD, _QWORD, char *, _QWORD, int, int, char *, char *); // [rsp+60h] [rbp+Fh] BYREF
  _DWORD vInBuffer[4]; // [rsp+68h] [rbp+17h] BYREF

  v2 = *((_QWORD *)this + 4);
  v18 = 0;
  vOutBuffer = 0;
  vInBuffer[0] = -1254720015;
  vInBuffer[1] = 298830764;
  vInBuffer[2] = -2147431787;
  vInBuffer[3] = -1834923937;
  if ( WSAIoctl(v2, 0xC8000006, vInBuffer, 0x10u, &vOutBuffer, 8u, &v18, 0, 0) )
  {
    Error = WSAGetLastError();
    v6 = Error;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(v5, v4, L"PostAccept: WSAIoctl failed", Error);
  }
  else
  {
    v7 = SocketBrokerContext::Impersonate(*((SocketBrokerContext **)this + 10));
    v6 = v7;
    if ( v7 )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0zq_EventWriteTransfer(v9, v8, L"PostAccept: Impersonate failed", v7);
    }
    else
    {
      AcceptSocket = TcpListener::CreateAcceptSocket(this);
      v6 = AcceptSocket;
      if ( AcceptSocket )
      {
        if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
          McTemplateU0zq_EventWriteTransfer(v12, v11, L"PostAccept: CreateAcceptSocket failed", AcceptSocket);
      }
      else
      {
        StartThreadpoolIo(*((PTP_IO *)this + 104));
        (**(void (__fastcall ***)(TcpListener *))this)(this);
        *((_DWORD *)this + 219) = 1;
        *(_OWORD *)((char *)this + 840) = 0;
        *(_OWORD *)((char *)this + 856) = 0;
        if ( !vOutBuffer(
                *((_QWORD *)this + 4),
                *(_QWORD *)(*((_QWORD *)this + 40) + 16LL),
                (char *)this + 328,
                0,
                144,
                144,
                (char *)this + 828,
                (char *)this + 840) )
        {
          v13 = WSAGetLastError();
          v6 = v13;
          if ( v13 )
          {
            if ( v13 == 997 )
            {
              v6 = 0;
            }
            else
            {
              CancelThreadpoolIo(*((PTP_IO *)this + 104));
              EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
              v14 = (struct AcceptSocket *)*((_QWORD *)this + 40);
              if ( v14 )
              {
                AcceptSocketList::Remove((TcpListener *)((char *)this + 264), v14);
                AcceptSocket::ReleaseRef(*((AcceptSocket **)this + 40));
                *((_QWORD *)this + 40) = 0;
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
              if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
                McTemplateU0zq_EventWriteTransfer(v16, v15, L"PostAccept: CreateAcceptSocket failed", v6);
              (*(void (__fastcall **)(TcpListener *))(*(_QWORD *)this + 8LL))(this);
              *((_DWORD *)this + 219) = 0;
            }
          }
        }
      }
      SetThreadToken(0, 0);
    }
  }
  return v6;
}

```

## disassembly

```asm
0x1800272e8  mov     r11, rsp
0x1800272eb  push    rbp
0x1800272ec  push    rbx
0x1800272ed  push    rsi
0x1800272ee  push    rdi
0x1800272ef  lea     rbp, [r11-5Fh]
0x1800272f3  sub     rsp, 88h
0x1800272fa  mov     rax, cs:__security_cookie
0x180027301  xor     rax, rsp
0x180027304  mov     [rbp+57h+var_30], rax
0x180027308  mov     qword ptr [r11-68h], 0
0x180027310  lea     rax, [rbp+57h+var_50]
0x180027314  mov     qword ptr [r11-70h], 0
0x18002731c  lea     r8, [rbp+57h+vInBuffer]; lpvInBuffer
0x180027320  mov     [r11-78h], rax
0x180027324  mov     rdi, rcx
0x180027327  mov     rcx, [rcx+20h]; s
0x18002732b  lea     rax, [rbp+57h+vOutBuffer]
0x18002732f  mov     [rsp+0A0h+cbOutBuffer], 8; cbOutBuffer
0x180027337  mov     r9d, 10h; cbInBuffer
0x18002733d  mov     edx, 0C8000006h; dwIoControlCode
0x180027342  mov     [rsp+0A0h+lpvOutBuffer], rax; lpvOutBuffer
0x180027347  mov     [rbp+57h+var_50], 0
0x18002734e  mov     [rbp+57h+vOutBuffer], 0
0x180027356  mov     [rbp+57h+vInBuffer], 0B5367DF1h
0x18002735d  mov     [rbp+57h+var_3C], 11CFCBACh
0x180027364  mov     [rbp+57h+var_38], 8000CA95h
0x18002736b  mov     [rbp+57h+var_34], 92A1485Fh
0x180027372  call    cs:__imp_WSAIoctl
0x180027378  test    eax, eax
0x18002737a  jz      short loc_1800273A5
0x18002737c  call    cs:__imp_WSAGetLastError
0x180027382  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027389  mov     ebx, eax
0x18002738b  jz      loc_180027523
0x180027391  lea     r8, aPostacceptWsai; "PostAccept: WSAIoctl failed"
0x180027398  mov     r9d, eax
0x18002739b  call    McTemplateU0zq_EventWriteTransfer
0x1800273a0  jmp     loc_180027523
0x1800273a5  mov     rcx, [rdi+50h]; this
0x1800273a9  call    ?Impersonate@SocketBrokerContext@@QEAAKXZ; SocketBrokerContext::Impersonate(void)
0x1800273ae  mov     ebx, eax
0x1800273b0  test    eax, eax
0x1800273b2  jz      short loc_1800273CA
0x1800273b4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800273bb  jz      loc_180027523
0x1800273c1  lea     r8, aPostacceptImpe; "PostAccept: Impersonate failed"
0x1800273c8  jmp     short loc_180027398
0x1800273ca  mov     rcx, rdi; this
0x1800273cd  call    ?CreateAcceptSocket@TcpListener@@AEAAKXZ; TcpListener::CreateAcceptSocket(void)
0x1800273d2  mov     ebx, eax
0x1800273d4  test    eax, eax
0x1800273d6  jz      short loc_1800273F9
0x1800273d8  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800273df  jz      loc_180027519
0x1800273e5  mov     r9d, eax
0x1800273e8  lea     r8, aPostacceptCrea; "PostAccept: CreateAcceptSocket failed"
0x1800273ef  call    McTemplateU0zq_EventWriteTransfer
0x1800273f4  jmp     loc_180027519
0x1800273f9  mov     rcx, [rdi+340h]; pio
0x180027400  call    cs:__imp_StartThreadpoolIo
0x180027406  mov     rax, [rdi]
0x180027409  mov     rcx, rdi
0x18002740c  mov     rax, [rax]
0x18002740f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027414  lea     r9, [rdi+348h]
0x18002741b  mov     dword ptr [rdi+36Ch], 1
0x180027425  mov     [rsp+38h], r9
0x18002742a  lea     rcx, [rdi+33Ch]
0x180027431  mov     [rsp+0A0h+var_70], rcx
0x180027436  lea     r8, [rdi+148h]
0x18002743d  xorps   xmm0, xmm0
0x180027440  mov     eax, 90h
0x180027445  movups  xmmword ptr [r9], xmm0
0x180027449  mov     [rsp+0A0h+cbOutBuffer], eax
0x18002744d  movups  xmmword ptr [r9+10h], xmm0
0x180027452  mov     rdx, [rdi+140h]
0x180027459  xor     r9d, r9d
0x18002745c  mov     rcx, [rdi+20h]
0x180027460  mov     dword ptr [rsp+0A0h+lpvOutBuffer], eax
0x180027464  mov     rax, [rbp+57h+vOutBuffer]
0x180027468  mov     rdx, [rdx+10h]
0x18002746c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027471  test    eax, eax
0x180027473  jnz     loc_180027519
0x180027479  call    cs:__imp_WSAGetLastError
0x18002747f  mov     ebx, eax
0x180027481  test    eax, eax
0x180027483  jz      loc_180027519
0x180027489  cmp     eax, 3E5h
0x18002748e  jz      loc_180027517
0x180027494  mov     rcx, [rdi+340h]; pio
0x18002749b  call    cs:__imp_CancelThreadpoolIo
0x1800274a1  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800274a5  call    cs:__imp_EnterCriticalSection
0x1800274ab  mov     rdx, [rdi+140h]; struct AcceptSocket *
0x1800274b2  test    rdx, rdx
0x1800274b5  jz      short loc_1800274DA
0x1800274b7  lea     rcx, [rdi+108h]; this
0x1800274be  call    ?Remove@AcceptSocketList@@QEAAXPEAVAcceptSocket@@@Z; AcceptSocketList::Remove(AcceptSocket *)
0x1800274c3  mov     rcx, [rdi+140h]; this
0x1800274ca  call    ?ReleaseRef@AcceptSocket@@QEAAXXZ; AcceptSocket::ReleaseRef(void)
0x1800274cf  mov     qword ptr [rdi+140h], 0
0x1800274da  lea     rcx, [rdi+28h]; lpCriticalSection
0x1800274de  call    cs:__imp_LeaveCriticalSection
0x1800274e4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800274eb  jz      short loc_1800274FC
0x1800274ed  mov     r9d, ebx
0x1800274f0  lea     r8, aPostacceptCrea; "PostAccept: CreateAcceptSocket failed"
0x1800274f7  call    McTemplateU0zq_EventWriteTransfer
0x1800274fc  mov     rax, [rdi]
0x1800274ff  mov     rcx, rdi
0x180027502  mov     rax, [rax+8]
0x180027506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002750b  mov     dword ptr [rdi+36Ch], 0
0x180027515  jmp     short loc_180027519
0x180027517  xor     ebx, ebx
0x180027519  xor     edx, edx; Token
0x18002751b  xor     ecx, ecx; Thread
0x18002751d  call    cs:__imp_SetThreadToken
0x180027523  mov     eax, ebx
0x180027525  mov     rcx, [rbp+57h+var_30]
0x180027529  xor     rcx, rsp; StackCookie
0x18002752c  call    __security_check_cookie
0x180027531  add     rsp, 88h
0x180027538  pop     rdi
0x180027539  pop     rsi
0x18002753a  pop     rbx
0x18002753b  pop     rbp
0x18002753c  retn
```
