# TcpListener::RetrieveConnectedSocket(ulong,_SOCKET_BROKER_RETRIEVE_SOCKET * *)

- ea: `0x1800277b4`
- end: `0x1800278d9`
- name: `?RetrieveConnectedSocket@TcpListener@@AEAAKKPEAPEAU_SOCKET_BROKER_RETRIEVE_SOCKET@@@Z`
- size: `293`
- prototype: `unsigned int __fastcall(TcpListener *__hidden this, unsigned int, struct _SOCKET_BROKER_RETRIEVE_SOCKET **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180026fb0`

## callees

- `0x18000a0a0`
- `0x180013f04`
- `0x18001cb0c`
- `0x1800277b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800277ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027810`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800277ce`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027810`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002784c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800278b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002784c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800278b7`

## string_xrefs

- `0x1800277eb`: `RetrieveConnectedSocket: WsaProtocolInfo is NULL`

## pseudocode

```c
__int64 __fastcall TcpListener::RetrieveConnectedSocket(
        TcpListener *this,
        DWORD a2,
        struct _SOCKET_BROKER_RETRIEVE_SOCKET **a3)
{
  __int64 v6; // rdx
  __int64 v7; // rcx
  SOCKET *v8; // rdi
  unsigned int v9; // ebx
  const wchar_t *v10; // r8
  TcpListener *i; // rax
  TcpListener *v12; // rcx
  TcpListener **v13; // rdx
  unsigned int DuplicatedSocketPrivate; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx

  EnterCriticalSection((LPCRITICAL_SECTION)this + 1);
  v8 = 0;
  if ( !a3 )
  {
    v9 = 87;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_22;
    v10 = L"RetrieveConnectedSocket: WsaProtocolInfo is NULL";
LABEL_4:
    McTemplateU0zq_EventWriteTransfer(v7, v6, v10, v9);
    goto LABEL_22;
  }
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  for ( i = (TcpListener *)*((_QWORD *)this + 38); i != (TcpListener *)((char *)this + 304); i = *(TcpListener **)i )
  {
    if ( *((_BYTE *)i + 28) )
    {
      v12 = *(TcpListener **)i;
      if ( *(TcpListener **)(*(_QWORD *)i + 8LL) != i || (v13 = (TcpListener **)*((_QWORD *)i + 1), *v13 != i) )
        __fastfail(3u);
      *v13 = v12;
      v8 = (SOCKET *)i;
      *((_QWORD *)v12 + 1) = v13;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( !v8 )
  {
    v9 = 4312;
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) == 0 )
      goto LABEL_22;
    v10 = L"RetrieveConnectedSocket: GetConnectedSocket (empty) failed with";
    goto LABEL_4;
  }
  DuplicatedSocketPrivate = SharedSocket::GetDuplicatedSocketPrivate(
                              (struct _RTL_CRITICAL_SECTION *)this,
                              v8[2],
                              a2,
                              a3);
  v9 = DuplicatedSocketPrivate;
  if ( DuplicatedSocketPrivate )
  {
    if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
      McTemplateU0zq_EventWriteTransfer(
        v16,
        v15,
        L"RetrieveConnectedSocket: GetDuplicatedSocketPrivate failed with",
        DuplicatedSocketPrivate);
  }
  else if ( *a3 )
  {
    *((_DWORD *)*a3 + 1) = *((_DWORD *)this + 29);
  }
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 1);
  if ( v8 )
    AcceptSocket::ReleaseRef((AcceptSocket *)v8);
  return v9;
}

```

## disassembly

```asm
0x1800277b4  push    rbx
0x1800277b6  push    rbp
0x1800277b7  push    rsi
0x1800277b8  push    rdi
0x1800277b9  push    r14
0x1800277bb  push    r15
0x1800277bd  sub     rsp, 28h
0x1800277c1  mov     rbp, rcx
0x1800277c4  mov     rsi, r8
0x1800277c7  add     rcx, 28h ; '('; lpCriticalSection
0x1800277cb  mov     r15d, edx
0x1800277ce  call    cs:__imp_EnterCriticalSection
0x1800277d4  xor     edi, edi
0x1800277d6  test    rsi, rsi
0x1800277d9  jnz     short loc_1800277FF
0x1800277db  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800277e2  lea     ebx, [rdi+57h]
0x1800277e5  jz      loc_1800278B3
0x1800277eb  lea     r8, aRetrieveconnec_0; "RetrieveConnectedSocket: WsaProtocolInf"...
0x1800277f2  mov     r9d, ebx
0x1800277f5  call    McTemplateU0zq_EventWriteTransfer
0x1800277fa  jmp     loc_1800278B3
0x1800277ff  lea     rbx, [rbp+108h]
0x180027806  mov     qword ptr [rsi], 0
0x18002780d  mov     rcx, rbx; lpCriticalSection
0x180027810  call    cs:__imp_EnterCriticalSection
0x180027816  lea     r8, [rbx+28h]
0x18002781a  mov     rax, [r8]
0x18002781d  jmp     short loc_180027844
0x18002781f  cmp     byte ptr [rax+1Ch], 0
0x180027823  jz      short loc_180027841
0x180027825  mov     rcx, [rax]
0x180027828  cmp     [rcx+8], rax
0x18002782c  jnz     short loc_18002786E
0x18002782e  mov     rdx, [rax+8]
0x180027832  cmp     [rdx], rax
0x180027835  jnz     short loc_18002786E
0x180027837  mov     [rdx], rcx
0x18002783a  mov     rdi, rax
0x18002783d  mov     [rcx+8], rdx
0x180027841  mov     rax, [rax]
0x180027844  cmp     rax, r8
0x180027847  jnz     short loc_18002781F
0x180027849  mov     rcx, rbx; lpCriticalSection
0x18002784c  call    cs:__imp_LeaveCriticalSection
0x180027852  test    rdi, rdi
0x180027855  jnz     short loc_180027875
0x180027857  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x18002785e  mov     ebx, 10D8h
0x180027863  jz      short loc_1800278B3
0x180027865  lea     r8, aRetrieveconnec_1; "RetrieveConnectedSocket: GetConnectedSo"...
0x18002786c  jmp     short loc_1800277F2
0x18002786e  mov     ecx, 3
0x180027873  int     29h; Win8: RtlFailFast(ecx)
0x180027875  mov     rdx, [rdi+10h]; s
0x180027879  mov     r9, rsi; struct _SOCKET_BROKER_RETRIEVE_SOCKET **
0x18002787c  mov     r8d, r15d; unsigned int
0x18002787f  mov     rcx, rbp; this
0x180027882  call    ?GetDuplicatedSocketPrivate@SharedSocket@@IEAAK_KKPEAPEAU_SOCKET_BROKER_RETRIEVE_SOCKET@@@Z; SharedSocket::GetDuplicatedSocketPrivate(unsigned __int64,ulong,_SOCKET_BROKER_RETRIEVE_SOCKET * *)
0x180027887  mov     ebx, eax
0x180027889  test    eax, eax
0x18002788b  jz      short loc_1800278A5
0x18002788d  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180027894  jz      short loc_1800278B3
0x180027896  mov     r9d, eax
0x180027899  lea     r8, aRetrieveconnec; "RetrieveConnectedSocket: GetDuplicatedS"...
0x1800278a0  jmp     loc_1800277F5
0x1800278a5  mov     rdx, [rsi]
0x1800278a8  test    rdx, rdx
0x1800278ab  jz      short loc_1800278B3
0x1800278ad  mov     eax, [rbp+74h]
0x1800278b0  mov     [rdx+4], eax
0x1800278b3  lea     rcx, [rbp+28h]; lpCriticalSection
0x1800278b7  call    cs:__imp_LeaveCriticalSection
0x1800278bd  test    rdi, rdi
0x1800278c0  jz      short loc_1800278CA
0x1800278c2  mov     rcx, rdi; this
0x1800278c5  call    ?ReleaseRef@AcceptSocket@@QEAAXXZ; AcceptSocket::ReleaseRef(void)
0x1800278ca  mov     eax, ebx
0x1800278cc  add     rsp, 28h
0x1800278d0  pop     r15
0x1800278d2  pop     r14
0x1800278d4  pop     rdi
0x1800278d5  pop     rsi
0x1800278d6  pop     rbp
0x1800278d7  pop     rbx
0x1800278d8  retn
```
