# TeredoCreatePeer

- ea: `0x18000f840`
- end: `0x18000fd7e`
- name: `TeredoCreatePeer`
- size: `1342`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000f150`

## callees

- `0x18000d5d0`
- `0x18000d7c0`
- `0x18000f840`
- `0x1800190f0`
- `0x180040790`
- `0x180083010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f861`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000f861`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fb69`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000fb69`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa7a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcbf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fa7a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000fcbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd02`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000fab6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x18000fab6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fad8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fad8`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fb98`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fbb7`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fb98`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptGenRandom` at `0x18000fbb7`

## string_xrefs

- `0x18000f90c`: `onecoreuap\net\netio\iphlpsvc\service\peer.c`
- `0x18000fd51`: `TeredoCreatePeer`

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
0x18000f840  push    rbx
0x18000f842  push    rsi
0x18000f843  push    r14
0x18000f845  sub     rsp, 30h
0x18000f849  mov     r14, rdx
0x18000f84c  mov     rsi, rcx
0x18000f84f  mov     rcx, [rcx+2268h]; hHeap
0x18000f856  mov     edx, 8; dwFlags
0x18000f85b  mov     r8d, 0B00h; dwBytes
0x18000f861  call    cs:__imp_HeapAlloc
0x18000f868  nop     dword ptr [rax+rax+00h]
0x18000f86d  mov     rbx, rax
0x18000f870  test    rax, rax
0x18000f873  jz      loc_18000FCF8
0x18000f879  inc     dword ptr [rsi+2298h]
0x18000f87f  mov     rax, [r14]
0x18000f882  mov     [rsp+48h+arg_8], rdi
0x18000f887  mov     [rsp+48h+arg_10], r15
0x18000f88c  cmp     [rax+8], r14
0x18000f890  jnz     loc_18000FD77
0x18000f896  mov     [rbx], rax
0x18000f899  lea     rcx, [rbx+650h]
0x18000f8a0  mov     [rbx+8], r14
0x18000f8a4  lea     rdx, [rbx+2F0h]
0x18000f8ab  mov     [rax+8], rbx
0x18000f8af  lea     rdi, [rsi+1418h]
0x18000f8b6  mov     [r14], rbx
0x18000f8b9  lea     rax, TeredoPeerCompletePacket
0x18000f8c0  mov     dword ptr [rbx+10h], 1
0x18000f8c7  xor     r15d, r15d
0x18000f8ca  mov     [rbx+440h], r15d
0x18000f8d1  xorps   xmm0, xmm0
0x18000f8d4  mov     [rbx+110h], rax
0x18000f8db  xor     eax, eax
0x18000f8dd  mov     [rbx+0F8h], r15
0x18000f8e4  mov     [rbx+0F0h], r15
0x18000f8eb  mov     [rbx+100h], rdi
0x18000f8f2  mov     [rbx+108h], r15
0x18000f8f9  mov     [rbx+118h], rbx
0x18000f900  mov     [rbx+120h], r15b
0x18000f907  mov     [rsp+48h+arg_0], rbp
0x18000f90c  lea     rbp, aOnecoreuapNetN_24; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18000f913  mov     [rbx+2D8h], r15d
0x18000f91a  mov     r9, rbp
0x18000f91d  movups  xmmword ptr [rbx+1F0h], xmm0
0x18000f924  mov     [rsp+48h+var_28], 0D8h
0x18000f92c  movups  xmmword ptr [rbx+200h], xmm0
0x18000f933  mov     [rbx+210h], rax
0x18000f93a  mov     [rbx+218h], eax
0x18000f940  lea     rax, TeredoPeerPortPredictionCompletePacket
0x18000f947  movups  xmmword ptr [rbx+268h], xmm0
0x18000f94e  movups  xmmword ptr [rbx+278h], xmm0
0x18000f955  mov     [rbx+290h], rdx
0x18000f95c  mov     [rbx+470h], rax
0x18000f963  xor     eax, eax
0x18000f965  mov     [rbx+458h], r15
0x18000f96c  mov     [rbx+450h], r15
0x18000f973  mov     [rbx+460h], rdi
0x18000f97a  mov     [rbx+468h], r15
0x18000f981  mov     [rbx+478h], rbx
0x18000f988  mov     [rbx+480h], r15b
0x18000f98f  mov     [rbx+638h], r15d
0x18000f996  movups  xmmword ptr [rbx+550h], xmm0
0x18000f99d  movups  xmmword ptr [rbx+560h], xmm0
0x18000f9a4  mov     [rbx+570h], rax
0x18000f9ab  mov     [rbx+578h], eax
0x18000f9b1  movups  xmmword ptr [rbx+5C8h], xmm0
0x18000f9b8  movups  xmmword ptr [rbx+5D8h], xmm0
0x18000f9bf  mov     dword ptr [rdx+4], 153B0000h
0x18000f9c6  mov     dword ptr [rdx], 60h ; '`'
0x18000f9cc  lea     rdx, aTeredoreferenc_0; "TeredoReferenceClient: ++%d @ %ls:%u"
0x18000f9d3  mov     dword ptr [rcx+4], 153B0000h
0x18000f9da  mov     dword ptr [rcx], 60h ; '`'
0x18000f9e0  mov     [rbx+5F0h], rcx
0x18000f9e7  mov     ecx, 100000h
0x18000f9ec  mov     [rbx+420h], rsi
0x18000f9f3  mov     r8d, [rsi]
0x18000f9f6  call    EventWrite0
0x18000f9fb  mov     ecx, [rsi]
0x18000f9fd  mov     eax, 1
0x18000fa02  lock xadd [rsi+8], eax
0x18000fa07  and     eax, 3Fh
0x18000fa0a  lea     rax, [rax+rax*4]
0x18000fa0e  mov     [rsi+rax*8+10h], ecx
0x18000fa12  mov     dword ptr [rsi+rax*8+20h], 0D8h
0x18000fa1a  mov     [rsi+rax*8+18h], rbp
0x18000fa1f  mov     [rsi+rax*8+30h], r15d
0x18000fa24  mov     [rsi+rax*8+28h], r15
0x18000fa29  lock inc dword ptr [rsi]
0x18000fa2c  lea     r14, [rbx+338h]
0x18000fa33  xor     r9d, r9d; lpName
0x18000fa36  xor     r8d, r8d; bInitialState
0x18000fa39  mov     dword ptr [r14+80h], 1
0x18000fa44  xor     edx, edx; bManualReset
0x18000fa46  mov     [r14], rdi
0x18000fa49  xor     ecx, ecx; lpEventAttributes
0x18000fa4b  mov     [r14+10h], r15
0x18000fa4f  mov     qword ptr [r14+18h], 0FFFFFFFFFFFFFFFFh
0x18000fa57  mov     [r14+28h], r15
0x18000fa5b  mov     [r14+20h], r15
0x18000fa5f  mov     dword ptr [r14+78h], 1
0x18000fa67  mov     dword ptr [r14+7Ch], 1
0x18000fa6f  mov     dword ptr [r14+90h], 1
0x18000fa7a  call    cs:__imp_CreateEventW
0x18000fa81  nop     dword ptr [rax+rax+00h]
0x18000fa86  mov     rbp, [rsp+48h+arg_0]
0x18000fa8b  mov     [r14+20h], rax
0x18000fa8f  test    rax, rax
0x18000fa92  jz      loc_18000FD02
0x18000fa98  mov     eax, 1
0x18000fa9d  lea     r8, CallbackEnvironment; pcbe
0x18000faa4  xchg    eax, [r14+30h]
0x18000faa8  mov     rdi, [r14+20h]
0x18000faac  lea     rcx, TeredoPeerStopEventCallback; pfnwa
0x18000fab3  mov     rdx, r14; pv
0x18000fab6  call    cs:__imp_CreateThreadpoolWait
0x18000fabd  nop     dword ptr [rax+rax+00h]
0x18000fac2  mov     [r14+28h], rax
0x18000fac6  test    rax, rax
0x18000fac9  jz      loc_18000FD02
0x18000facf  xor     r8d, r8d; pftTimeout
0x18000fad2  mov     rdx, rdi; h
0x18000fad5  mov     rcx, rax; pwa
0x18000fad8  call    cs:__imp_SetThreadpoolWait
0x18000fadf  nop     dword ptr [rax+rax+00h]
0x18000fae4  lea     rax, DeviceStart
0x18000faeb  mov     [rbx+340h], rbx
0x18000faf2  mov     [rbx+370h], rax
0x18000faf9  xor     r8d, r8d; lpName
0x18000fafc  lea     rax, DeviceStop
0x18000fb03  mov     [rbx+0AE0h], r15d
0x18000fb0a  mov     [rbx+378h], rax
0x18000fb11  xor     edx, edx; bInitialOwner
0x18000fb13  lea     rax, TeredoPeerTransmitPacket
0x18000fb1a  xor     ecx, ecx; lpMutexAttributes
0x18000fb1c  mov     [rbx+380h], rax
0x18000fb23  lea     rax, DeviceTransmitComplete
0x18000fb2a  mov     [rbx+388h], rax
0x18000fb31  lea     rax, TeredoClientPeerReceive
0x18000fb38  mov     [rbx+390h], rax
0x18000fb3f  lea     rax, TeredoCreatePeerSocket
0x18000fb46  mov     [rbx+398h], rax
0x18000fb4d  lea     rax, TeredoDestroyPeerSocket
0x18000fb54  mov     [rbx+3A0h], rax
0x18000fb5b  lea     rax, TeredoPeerPostReceive
0x18000fb62  mov     [rbx+3A8h], rax
0x18000fb69  call    cs:__imp_CreateMutexW
0x18000fb70  nop     dword ptr [rax+rax+00h]
0x18000fb75  mov     [rbx+438h], rax
0x18000fb7c  test    rax, rax
0x18000fb7f  jz      loc_18000FCE1
0x18000fb85  mov     rcx, cs:hProv; hProv
0x18000fb8c  lea     r8, [rbx+8B8h]; pbBuffer
0x18000fb93  mov     edx, 8; dwLen
0x18000fb98  call    cs:__imp_CryptGenRandom
0x18000fb9f  nop     dword ptr [rax+rax+00h]
0x18000fba4  mov     rcx, cs:hProv; hProv
0x18000fbab  lea     r8, [rbx+0AD8h]; pbBuffer
0x18000fbb2  mov     edx, 8; dwLen
0x18000fbb7  call    cs:__imp_CryptGenRandom
0x18000fbbe  nop     dword ptr [rax+rax+00h]
0x18000fbc3  mov     rcx, [rbx+420h]
0x18000fbca  lea     rsi, AuthProvider
0x18000fbd1  movzx   eax, byte ptr [rbx+6A8h]
0x18000fbd8  lea     r9, [rbx+6A8h]
0x18000fbdf  and     al, 0FDh
0x18000fbe1  mov     [rbx+6A0h], rsi
0x18000fbe8  or      al, 1
0x18000fbea  mov     [rbx+8A8h], r15
0x18000fbf1  mov     [rbx+6A8h], al
0x18000fbf7  add     rcx, 1E4Ch
0x18000fbfe  mov     rax, qword ptr cs:xmmword_1800CC5B0
0x18000fc05  xor     r8d, r8d
0x18000fc08  xor     edx, edx
0x18000fc0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc0f  test    eax, eax
0x18000fc11  jnz     loc_18000FCE1
0x18000fc17  mov     rax, [rbx+6A0h]
0x18000fc1e  lea     rcx, [rbx+6A8h]
0x18000fc25  mov     rax, [rax+18h]
0x18000fc29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc2e  movzx   ecx, byte ptr [rbx+6A9h]
0x18000fc35  lea     r9, [rbx+8C8h]
0x18000fc3c  add     ecx, 0Dh
0x18000fc3f  xor     r8d, r8d
0x18000fc42  add     eax, ecx
0x18000fc44  xor     edx, edx
0x18000fc46  mov     rcx, [rbx+420h]
0x18000fc4d  mov     [rbx+8B0h], eax
0x18000fc53  add     rcx, 1E5Ch
0x18000fc5a  movzx   eax, byte ptr [rbx+8C8h]
0x18000fc61  and     al, 0FDh
0x18000fc63  mov     [rbx+8C0h], rsi
0x18000fc6a  or      al, 1
0x18000fc6c  mov     [rbx+0AC8h], r15
0x18000fc73  mov     [rbx+8C8h], al
0x18000fc79  mov     rax, qword ptr cs:xmmword_1800CC5B0
0x18000fc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc85  test    eax, eax
0x18000fc87  jnz     short loc_18000FCE1
0x18000fc89  mov     rax, [rbx+8C0h]
0x18000fc90  lea     rcx, [rbx+8C8h]
0x18000fc97  mov     rax, [rax+18h]
0x18000fc9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fca0  movzx   ecx, byte ptr [rbx+8C9h]
0x18000fca7  xor     r9d, r9d; lpName
0x18000fcaa  add     ecx, 0Dh
0x18000fcad  xor     r8d, r8d; bInitialState
0x18000fcb0  add     eax, ecx
0x18000fcb2  mov     edx, 1; bManualReset
0x18000fcb7  xor     ecx, ecx; lpEventAttributes
0x18000fcb9  mov     [rbx+0AD0h], eax
0x18000fcbf  call    cs:__imp_CreateEventW
0x18000fcc6  nop     dword ptr [rax+rax+00h]
0x18000fccb  mov     [rbx+698h], rax
0x18000fcd2  test    rax, rax
0x18000fcd5  jz      short loc_18000FCE1
0x18000fcd7  mov     dword ptr [rbx+0AE0h], 1
0x18000fce1  mov     rax, rbx
0x18000fce4  mov     rdi, [rsp+48h+arg_8]
0x18000fce9  mov     r15, [rsp+48h+arg_10]
0x18000fcee  add     rsp, 30h
0x18000fcf2  pop     r14
0x18000fcf4  pop     rsi
0x18000fcf5  pop     rbx
0x18000fcf6  retn
0x18000fcf8  add     rsp, 30h
0x18000fcfc  pop     r14
0x18000fcfe  pop     rsi
0x18000fcff  pop     rbx
0x18000fd00  retn
0x18000fd02  call    cs:__imp_GetLastError
0x18000fd09  nop     dword ptr [rax+rax+00h]
0x18000fd0e  mov     edi, eax
0x18000fd10  mov     rcx, r14
0x18000fd13  call    TeredoCleanupDevice
0x18000fd18  test    edi, edi
0x18000fd1a  jz      loc_18000FAE4
0x18000fd20  mov     r8d, edi
0x18000fd23  lea     rdx, aUnableToInitia_0; "Unable to initialize peer: %d"
0x18000fd2a  mov     ecx, 100000h
0x18000fd2f  call    EventWriteError0
0x18000fd34  mov     rcx, r14
0x18000fd37  call    TeredoCleanupDevice
0x18000fd3c  mov     rcx, [rbx]
0x18000fd3f  cmp     [rcx+8], rbx
0x18000fd43  jnz     short loc_18000FD77
0x18000fd45  mov     rax, [rbx+8]
0x18000fd49  cmp     [rax], rbx
0x18000fd4c  jnz     short loc_18000FD77
0x18000fd4e  mov     [rax], rcx
0x18000fd51  lea     rdx, aTeredocreatepe; "TeredoCreatePeer"
0x18000fd58  mov     [rcx+8], rax
0x18000fd5c  mov     r8d, 13Fh
0x18000fd62  dec     dword ptr [rsi+2298h]
0x18000fd68  mov     rcx, rbx; lpMem
0x18000fd6b  call    TeredoDereferencePeerEx
0x18000fd70  xor     eax, eax
0x18000fd72  jmp     loc_18000FCE4
0x18000fd77  mov     ecx, 3
0x18000fd7c  int     29h; Win8: RtlFailFast(ecx)
```
