# TeredoCreatePeer

- ea: `0x18000f830`
- end: `0x18000fd6e`
- name: `TeredoCreatePeer`
- size: `1342`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f140`

## callees

- `0x18000d5c0`
- `0x18000d7b0`
- `0x18000f830`
- `0x1800190e0`
- `0x1800407d0`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f851`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f851`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fb59`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fb59`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa6a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcaf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa6a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcf2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcf2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000faa6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000faa6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fac8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fac8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fb88`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fba7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fb88`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fba7`

## string_xrefs

- `0x18000f8fc`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000fd41`: `TeredoCreatePeer`

## pseudocode

```c
char *__fastcall TeredoCreatePeer(unsigned int *a1, char **a2)
{
  char *result; // rax
  char *v5; // rbx
  char *v6; // rax
  unsigned int v7; // ecx
  __int64 v8; // rax
  HANDLE EventW; // rax
  void *v10; // rdi
  struct _TP_WAIT *ThreadpoolWait; // rax
  HANDLE MutexW; // rax
  __int64 v13; // rcx
  char v14; // al
  int v15; // eax
  __int64 v16; // rcx
  HANDLE v17; // rax
  DWORD LastError; // edi
  _QWORD *v19; // rcx
  LPVOID *v20; // rax

  result = (char *)HeapAlloc(*((HANDLE *)a1 + 1101), 8u, 0xB00u);
  v5 = result;
  if ( !result )
    return result;
  ++a1[2214];
  v6 = *a2;
  if ( *((char ***)*a2 + 1) != a2 )
LABEL_17:
    __fastfail(3u);
  *(_QWORD *)v5 = v6;
  *((_QWORD *)v5 + 1) = a2;
  *((_QWORD *)v6 + 1) = v5;
  *a2 = v5;
  *((_DWORD *)v5 + 4) = 1;
  *((_DWORD *)v5 + 272) = 0;
  *((_QWORD *)v5 + 34) = TeredoPeerCompletePacket;
  *((_QWORD *)v5 + 31) = 0;
  *((_QWORD *)v5 + 30) = 0;
  *((_QWORD *)v5 + 32) = a1 + 1286;
  *((_QWORD *)v5 + 33) = 0;
  *((_QWORD *)v5 + 35) = v5;
  v5[288] = 0;
  *((_DWORD *)v5 + 182) = 0;
  *((_OWORD *)v5 + 31) = 0;
  *((_OWORD *)v5 + 32) = 0;
  *((_QWORD *)v5 + 66) = 0;
  *((_DWORD *)v5 + 134) = 0;
  *(_OWORD *)(v5 + 616) = 0;
  *(_OWORD *)(v5 + 632) = 0;
  *((_QWORD *)v5 + 82) = v5 + 752;
  *((_QWORD *)v5 + 142) = TeredoPeerPortPredictionCompletePacket;
  *((_QWORD *)v5 + 139) = 0;
  *((_QWORD *)v5 + 138) = 0;
  *((_QWORD *)v5 + 140) = a1 + 1286;
  *((_QWORD *)v5 + 141) = 0;
  *((_QWORD *)v5 + 143) = v5;
  v5[1152] = 0;
  *((_DWORD *)v5 + 398) = 0;
  *((_OWORD *)v5 + 85) = 0;
  *((_OWORD *)v5 + 86) = 0;
  *((_QWORD *)v5 + 174) = 0;
  *((_DWORD *)v5 + 350) = 0;
  *(_OWORD *)(v5 + 1480) = 0;
  *(_OWORD *)(v5 + 1496) = 0;
  *((_DWORD *)v5 + 189) = 356188160;
  *((_DWORD *)v5 + 188) = 96;
  *((_DWORD *)v5 + 405) = 356188160;
  *((_DWORD *)v5 + 404) = 96;
  *((_QWORD *)v5 + 190) = v5 + 1616;
  *((_QWORD *)v5 + 132) = a1;
  EventWrite0(
    0x100000,
    L"TeredoReferenceClient: ++%d @ %ls:%u",
    *a1,
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c",
    216);
  v7 = *a1;
  v8 = 5LL * (_InterlockedExchangeAdd((volatile signed __int32 *)a1 + 2, 1u) & 0x3F);
  a1[2 * v8 + 4] = v7;
  a1[2 * v8 + 8] = 216;
  *(_QWORD *)&a1[2 * v8 + 6] = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\peer.c";
  a1[2 * v8 + 12] = 0;
  *(_QWORD *)&a1[2 * v8 + 10] = 0;
  _InterlockedIncrement((volatile signed __int32 *)a1);
  *((_DWORD *)v5 + 238) = 1;
  *((_QWORD *)v5 + 103) = a1 + 1286;
  *((_QWORD *)v5 + 105) = 0;
  *((_QWORD *)v5 + 106) = -1;
  *((_QWORD *)v5 + 108) = 0;
  *((_QWORD *)v5 + 107) = 0;
  *((_DWORD *)v5 + 236) = 1;
  *((_DWORD *)v5 + 237) = 1;
  *((_DWORD *)v5 + 242) = 1;
  EventW = CreateEventW(0, 0, 0, 0);
  *((_QWORD *)v5 + 107) = EventW;
  if ( EventW )
  {
    _InterlockedExchange((volatile __int32 *)v5 + 218, 1);
    v10 = (void *)*((_QWORD *)v5 + 107);
    ThreadpoolWait = CreateThreadpoolWait(TeredoPeerStopEventCallback, v5 + 824, &CallbackEnvironment);
    *((_QWORD *)v5 + 108) = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, v10, 0);
      goto LABEL_6;
    }
  }
  LastError = GetLastError();
  TeredoCleanupDevice(v5 + 824);
  if ( LastError )
  {
    EventWriteError0(0x100000, L"Unable to initialize peer: %d", LastError);
    TeredoCleanupDevice(v5 + 824);
    v19 = *(_QWORD **)v5;
    if ( *(char **)(*(_QWORD *)v5 + 8LL) == v5 )
    {
      v20 = (LPVOID *)*((_QWORD *)v5 + 1);
      if ( *v20 == v5 )
      {
        *v20 = v19;
        v19[1] = v20;
        --a1[2214];
        TeredoDereferencePeerEx(v5);
        return 0;
      }
    }
    goto LABEL_17;
  }
LABEL_6:
  *((_QWORD *)v5 + 104) = v5;
  *((_QWORD *)v5 + 110) = DeviceStart;
  *((_DWORD *)v5 + 696) = 0;
  *((_QWORD *)v5 + 111) = DeviceStop;
  *((_QWORD *)v5 + 112) = TeredoPeerTransmitPacket;
  *((_QWORD *)v5 + 113) = DeviceTransmitComplete;
  *((_QWORD *)v5 + 114) = TeredoClientPeerReceive;
  *((_QWORD *)v5 + 115) = TeredoCreatePeerSocket;
  *((_QWORD *)v5 + 116) = TeredoDestroyPeerSocket;
  *((_QWORD *)v5 + 117) = &TeredoPeerPostReceive;
  MutexW = CreateMutexW(0, 0, 0);
  *((_QWORD *)v5 + 135) = MutexW;
  if ( MutexW )
  {
    CryptGenRandom(hProv, 8u, (BYTE *)v5 + 2232);
    CryptGenRandom(hProv, 8u, (BYTE *)v5 + 2776);
    v13 = *((_QWORD *)v5 + 132);
    v14 = v5[1704] & 0xFD;
    *((_QWORD *)v5 + 212) = AuthProvider;
    *((_QWORD *)v5 + 277) = 0;
    v5[1704] = v14 | 1;
    if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, char *))xmmword_1800CC5B0)(
                          v13 + 7756,
                          0,
                          0,
                          v5 + 1704) )
    {
      v15 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v5 + 212) + 24LL))(v5 + 1704);
      v16 = *((_QWORD *)v5 + 132);
      *((_DWORD *)v5 + 556) = (unsigned __int8)v5[1705] + 13 + v15;
      LOBYTE(v15) = v5[2248] & 0xFD;
      *((_QWORD *)v5 + 280) = AuthProvider;
      *((_QWORD *)v5 + 345) = 0;
      v5[2248] = v15 | 1;
      if ( !(unsigned int)((__int64 (__fastcall *)(__int64, _QWORD, _QWORD, char *))xmmword_1800CC5B0)(
                            v16 + 7772,
                            0,
                            0,
                            v5 + 2248) )
      {
        *((_DWORD *)v5 + 692) = (unsigned __int8)v5[2249]
                              + 13
                              + (*(__int64 (__fastcall **)(char *))(*((_QWORD *)v5 + 280) + 24LL))(v5 + 2248);
        v17 = CreateEventW(0, 1, 0, 0);
        *((_QWORD *)v5 + 211) = v17;
        if ( v17 )
          *((_DWORD *)v5 + 696) = 1;
      }
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000f830  push    rbx
0x18000f832  push    rsi
0x18000f833  push    r14
0x18000f835  sub     rsp, 30h
0x18000f839  mov     r14, rdx
0x18000f83c  mov     rsi, rcx
0x18000f83f  mov     rcx, [rcx+2268h]; hHeap
0x18000f846  mov     edx, 8; dwFlags
0x18000f84b  mov     r8d, 0B00h; dwBytes
0x18000f851  call    cs:__imp_HeapAlloc
0x18000f858  nop     dword ptr [rax+rax+00h]
0x18000f85d  mov     rbx, rax
0x18000f860  test    rax, rax
0x18000f863  jz      loc_18000FCE8
0x18000f869  inc     dword ptr [rsi+2298h]
0x18000f86f  mov     rax, [r14]
0x18000f872  mov     [rsp+48h+arg_8], rdi
0x18000f877  mov     [rsp+48h+arg_10], r15
0x18000f87c  cmp     [rax+8], r14
0x18000f880  jnz     loc_18000FD67
0x18000f886  mov     [rbx], rax
0x18000f889  lea     rcx, [rbx+650h]
0x18000f890  mov     [rbx+8], r14
0x18000f894  lea     rdx, [rbx+2F0h]
0x18000f89b  mov     [rax+8], rbx
0x18000f89f  lea     rdi, [rsi+1418h]
0x18000f8a6  mov     [r14], rbx
0x18000f8a9  lea     rax, TeredoPeerCompletePacket
0x18000f8b0  mov     dword ptr [rbx+10h], 1
0x18000f8b7  xor     r15d, r15d
0x18000f8ba  mov     [rbx+440h], r15d
0x18000f8c1  xorps   xmm0, xmm0
0x18000f8c4  mov     [rbx+110h], rax
0x18000f8cb  xor     eax, eax
0x18000f8cd  mov     [rbx+0F8h], r15
0x18000f8d4  mov     [rbx+0F0h], r15
0x18000f8db  mov     [rbx+100h], rdi
0x18000f8e2  mov     [rbx+108h], r15
0x18000f8e9  mov     [rbx+118h], rbx
0x18000f8f0  mov     [rbx+120h], r15b
0x18000f8f7  mov     [rsp+48h+arg_0], rbp
0x18000f8fc  lea     rbp, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000f903  mov     [rbx+2D8h], r15d
0x18000f90a  mov     r9, rbp
0x18000f90d  movups  xmmword ptr [rbx+1F0h], xmm0
0x18000f914  mov     [rsp+48h+var_28], 0D8h
0x18000f91c  movups  xmmword ptr [rbx+200h], xmm0
0x18000f923  mov     [rbx+210h], rax
0x18000f92a  mov     [rbx+218h], eax
0x18000f930  lea     rax, TeredoPeerPortPredictionCompletePacket
0x18000f937  movups  xmmword ptr [rbx+268h], xmm0
0x18000f93e  movups  xmmword ptr [rbx+278h], xmm0
0x18000f945  mov     [rbx+290h], rdx
0x18000f94c  mov     [rbx+470h], rax
0x18000f953  xor     eax, eax
0x18000f955  mov     [rbx+458h], r15
0x18000f95c  mov     [rbx+450h], r15
0x18000f963  mov     [rbx+460h], rdi
0x18000f96a  mov     [rbx+468h], r15
0x18000f971  mov     [rbx+478h], rbx
0x18000f978  mov     [rbx+480h], r15b
0x18000f97f  mov     [rbx+638h], r15d
0x18000f986  movups  xmmword ptr [rbx+550h], xmm0
0x18000f98d  movups  xmmword ptr [rbx+560h], xmm0
0x18000f994  mov     [rbx+570h], rax
0x18000f99b  mov     [rbx+578h], eax
0x18000f9a1  movups  xmmword ptr [rbx+5C8h], xmm0
0x18000f9a8  movups  xmmword ptr [rbx+5D8h], xmm0
0x18000f9af  mov     dword ptr [rdx+4], 153B0000h
0x18000f9b6  mov     dword ptr [rdx], 60h ; '`'
0x18000f9bc  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x18000f9c3  mov     dword ptr [rcx+4], 153B0000h
0x18000f9ca  mov     dword ptr [rcx], 60h ; '`'
0x18000f9d0  mov     [rbx+5F0h], rcx
0x18000f9d7  mov     ecx, 100000h
0x18000f9dc  mov     [rbx+420h], rsi
0x18000f9e3  mov     r8d, [rsi]
0x18000f9e6  call    EventWrite0
0x18000f9eb  mov     ecx, [rsi]
0x18000f9ed  mov     eax, 1
0x18000f9f2  lock xadd [rsi+8], eax
0x18000f9f7  and     eax, 3Fh
0x18000f9fa  lea     rax, [rax+rax*4]
0x18000f9fe  mov     [rsi+rax*8+10h], ecx
0x18000fa02  mov     dword ptr [rsi+rax*8+20h], 0D8h
0x18000fa0a  mov     [rsi+rax*8+18h], rbp
0x18000fa0f  mov     [rsi+rax*8+30h], r15d
0x18000fa14  mov     [rsi+rax*8+28h], r15
0x18000fa19  lock inc dword ptr [rsi]
0x18000fa1c  lea     r14, [rbx+338h]
0x18000fa23  xor     r9d, r9d; lpName
0x18000fa26  xor     r8d, r8d; bInitialState
0x18000fa29  mov     dword ptr [r14+80h], 1
0x18000fa34  xor     edx, edx; bManualReset
0x18000fa36  mov     [r14], rdi
0x18000fa39  xor     ecx, ecx; lpEventAttributes
0x18000fa3b  mov     [r14+10h], r15
0x18000fa3f  mov     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFFh
0x18000fa47  mov     [r14+28h], r15
0x18000fa4b  mov     [r14+20h], r15
0x18000fa4f  mov     dword ptr [r14+78h], 1
0x18000fa57  mov     dword ptr [r14+7Ch], 1
0x18000fa5f  mov     dword ptr [r14+90h], 1
0x18000fa6a  call    cs:__imp_CreateEventW
0x18000fa71  nop     dword ptr [rax+rax+00h]
0x18000fa76  mov     rbp, [rsp+48h+arg_0]
0x18000fa7b  mov     [r14+20h], rax
0x18000fa7f  test    rax, rax
0x18000fa82  jz      loc_18000FCF2
0x18000fa88  mov     eax, 1
0x18000fa8d  lea     r8, CallbackEnvironment; pcbe
0x18000fa94  xchg    eax, [r14+30h]
0x18000fa98  mov     rdi, [r14+20h]
0x18000fa9c  lea     rcx, TeredoPeerStopEventCallback; pfnwa
0x18000faa3  mov     rdx, r14; pv
0x18000faa6  call    cs:__imp_CreateThreadpoolWait
0x18000faad  nop     dword ptr [rax+rax+00h]
0x18000fab2  mov     [r14+28h], rax
0x18000fab6  test    rax, rax
0x18000fab9  jz      loc_18000FCF2
0x18000fabf  xor     r8d, r8d; pftTimeout
0x18000fac2  mov     rdx, rdi; h
0x18000fac5  mov     rcx, rax; pwa
0x18000fac8  call    cs:__imp_SetThreadpoolWait
0x18000facf  nop     dword ptr [rax+rax+00h]
0x18000fad4  lea     rax, DeviceStart
0x18000fadb  mov     [rbx+340h], rbx
0x18000fae2  mov     [rbx+370h], rax
0x18000fae9  xor     r8d, r8d; lpName
0x18000faec  lea     rax, DeviceStop
0x18000faf3  mov     [rbx+0AE0h], r15d
0x18000fafa  mov     [rbx+378h], rax
0x18000fb01  xor     edx, edx; bInitialOwner
0x18000fb03  lea     rax, TeredoPeerTransmitPacket
0x18000fb0a  xor     ecx, ecx; lpMutexAttributes
0x18000fb0c  mov     [rbx+380h], rax
0x18000fb13  lea     rax, DeviceTransmitComplete
0x18000fb1a  mov     [rbx+388h], rax
0x18000fb21  lea     rax, TeredoClientPeerReceive
0x18000fb28  mov     [rbx+390h], rax
0x18000fb2f  lea     rax, TeredoCreatePeerSocket
0x18000fb36  mov     [rbx+398h], rax
0x18000fb3d  lea     rax, TeredoDestroyPeerSocket
0x18000fb44  mov     [rbx+3A0h], rax
0x18000fb4b  lea     rax, TeredoPeerPostReceive
0x18000fb52  mov     [rbx+3A8h], rax
0x18000fb59  call    cs:__imp_CreateMutexW
0x18000fb60  nop     dword ptr [rax+rax+00h]
0x18000fb65  mov     [rbx+438h], rax
0x18000fb6c  test    rax, rax
0x18000fb6f  jz      loc_18000FCD1
0x18000fb75  mov     rcx, cs:hProv; hProv
0x18000fb7c  lea     r8, [rbx+8B8h]; pbBuffer
0x18000fb83  mov     edx, 8; dwLen
0x18000fb88  call    cs:__imp_CryptGenRandom
0x18000fb8f  nop     dword ptr [rax+rax+00h]
0x18000fb94  mov     rcx, cs:hProv; hProv
0x18000fb9b  lea     r8, [rbx+0AD8h]; pbBuffer
0x18000fba2  mov     edx, 8; dwLen
0x18000fba7  call    cs:__imp_CryptGenRandom
0x18000fbae  nop     dword ptr [rax+rax+00h]
0x18000fbb3  mov     rcx, [rbx+420h]
0x18000fbba  lea     rsi, AuthProvider
0x18000fbc1  movzx   eax, byte ptr [rbx+6A8h]
0x18000fbc8  lea     r9, [rbx+6A8h]
0x18000fbcf  and     al, 0FDh
0x18000fbd1  mov     [rbx+6A0h], rsi
0x18000fbd8  or      al, 1
0x18000fbda  mov     [rbx+8A8h], r15
0x18000fbe1  mov     [rbx+6A8h], al
0x18000fbe7  add     rcx, 1E4Ch
0x18000fbee  mov     rax, qword ptr cs:xmmword_1800CC5B0
0x18000fbf5  xor     r8d, r8d
0x18000fbf8  xor     edx, edx
0x18000fbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fbff  test    eax, eax
0x18000fc01  jnz     loc_18000FCD1
0x18000fc07  mov     rax, [rbx+6A0h]
0x18000fc0e  lea     rcx, [rbx+6A8h]
0x18000fc15  mov     rax, [rax+18h]
0x18000fc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc1e  movzx   ecx, byte ptr [rbx+6A9h]
0x18000fc25  lea     r9, [rbx+8C8h]
0x18000fc2c  add     ecx, 0Dh
0x18000fc2f  xor     r8d, r8d
0x18000fc32  add     eax, ecx
0x18000fc34  xor     edx, edx
0x18000fc36  mov     rcx, [rbx+420h]
0x18000fc3d  mov     [rbx+8B0h], eax
0x18000fc43  add     rcx, 1E5Ch
0x18000fc4a  movzx   eax, byte ptr [rbx+8C8h]
0x18000fc51  and     al, 0FDh
0x18000fc53  mov     [rbx+8C0h], rsi
0x18000fc5a  or      al, 1
0x18000fc5c  mov     [rbx+0AC8h], r15
0x18000fc63  mov     [rbx+8C8h], al
0x18000fc69  mov     rax, qword ptr cs:xmmword_1800CC5B0
0x18000fc70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc75  test    eax, eax
0x18000fc77  jnz     short loc_18000FCD1
0x18000fc79  mov     rax, [rbx+8C0h]
0x18000fc80  lea     rcx, [rbx+8C8h]
0x18000fc87  mov     rax, [rax+18h]
0x18000fc8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc90  movzx   ecx, byte ptr [rbx+8C9h]
0x18000fc97  xor     r9d, r9d; lpName
0x18000fc9a  add     ecx, 0Dh
0x18000fc9d  xor     r8d, r8d; bInitialState
0x18000fca0  add     eax, ecx
0x18000fca2  mov     edx, 1; bManualReset
0x18000fca7  xor     ecx, ecx; lpEventAttributes
0x18000fca9  mov     [rbx+0AD0h], eax
0x18000fcaf  call    cs:__imp_CreateEventW
0x18000fcb6  nop     dword ptr [rax+rax+00h]
0x18000fcbb  mov     [rbx+698h], rax
0x18000fcc2  test    rax, rax
0x18000fcc5  jz      short loc_18000FCD1
0x18000fcc7  mov     dword ptr [rbx+0AE0h], 1
0x18000fcd1  mov     rax, rbx
0x18000fcd4  mov     rdi, [rsp+48h+arg_8]
0x18000fcd9  mov     r15, [rsp+48h+arg_10]
0x18000fcde  add     rsp, 30h
0x18000fce2  pop     r14
0x18000fce4  pop     rsi
0x18000fce5  pop     rbx
0x18000fce6  retn
0x18000fce8  add     rsp, 30h
0x18000fcec  pop     r14
0x18000fcee  pop     rsi
0x18000fcef  pop     rbx
0x18000fcf0  retn
0x18000fcf2  call    cs:__imp_GetLastError
0x18000fcf9  nop     dword ptr [rax+rax+00h]
0x18000fcfe  mov     edi, eax
0x18000fd00  mov     rcx, r14
0x18000fd03  call    TeredoCleanupDevice
0x18000fd08  test    edi, edi
0x18000fd0a  jz      loc_18000FAD4
0x18000fd10  mov     r8d, edi
0x18000fd13  lea     rdx, aUnableToInitia_0; "Unable to initialize peer: %d"
0x18000fd1a  mov     ecx, 100000h
0x18000fd1f  call    EventWriteError0
0x18000fd24  mov     rcx, r14
0x18000fd27  call    TeredoCleanupDevice
0x18000fd2c  mov     rcx, [rbx]
0x18000fd2f  cmp     [rcx+8], rbx
0x18000fd33  jnz     short loc_18000FD67
0x18000fd35  mov     rax, [rbx+8]
0x18000fd39  cmp     [rax], rbx
0x18000fd3c  jnz     short loc_18000FD67
0x18000fd3e  mov     [rax], rcx
0x18000fd41  lea     rdx, aTeredocreatepe; "TeredoCreatePeer"
0x18000fd48  mov     [rcx+8], rax
0x18000fd4c  mov     r8d, 13Fh
0x18000fd52  dec     dword ptr [rsi+2298h]
0x18000fd58  mov     rcx, rbx; lpMem
0x18000fd5b  call    TeredoDereferencePeerEx
0x18000fd60  xor     eax, eax
0x18000fd62  jmp     loc_18000FCD4
0x18000fd67  mov     ecx, 3
0x18000fd6c  int     29h; Win8: RtlFailFast(ecx)
```
