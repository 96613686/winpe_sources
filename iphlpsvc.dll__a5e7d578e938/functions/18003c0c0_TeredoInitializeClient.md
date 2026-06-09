# TeredoInitializeClient

- ea: `0x18003c0c0`
- end: `0x18003c5f0`
- name: `TeredoInitializeClient`
- size: `1328`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003be80`

## callees

- `0x180003cbc`
- `0x18000d7c0`
- `0x1800302e4`
- `0x180033914`
- `0x180036850`
- `0x18003794c`
- `0x18003c0c0`
- `0x180041f44`
- `0x180052304`
- `0x1800525f0`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18003c24f`
- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x18003c24f`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18003c4de`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x18003c4de`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c51d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18003c51d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003c4f6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c1f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c1f7`
- `WS2_32!__imp_htons` at `0x18003c336`
- `WS2_32!__imp_htons` at `0x18003c336`

## string_xrefs

- `0x18003c104`: `ReferenceService: ++%u (%hs) @ %ls:%u`
- `0x18003c0de`: `onecoreuap\net\netio\iphlpsvc\service\client.c`

## pseudocode

```c
__int64 __fastcall TeredoInitializeClient(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  int v4; // edx
  char v5; // al
  __int64 v6; // rcx
  DWORD LastError; // ebx
  SIZE_T MaximumPeerAllocationLimit; // rax
  HANDLE v9; // rax
  __int64 result; // rax
  HANDLE EventW; // rax
  __int64 v12; // [rsp+20h] [rbp-38h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp+8h] BYREF

  EventWrite0(
    0x40000,
    L"ReferenceService: ++%u (%hs) @ %ls:%u",
    ((unsigned int)g_Reference >> 1) & 0x3FFFFFFF,
    "TeredoInitializeClient",
    L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c",
    4479);
  while ( 1 )
  {
    v2 = g_Reference;
    if ( (g_Reference & 1) != 0 )
      break;
    if ( v2 == _InterlockedCompareExchange(&g_Reference, g_Reference + 2, g_Reference) )
    {
      v3 = a1 + 4960;
      ReferenceCompartmentEx(a1, L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c", 4486);
      v4 = *(_DWORD *)(a1 + 4960);
      *(_DWORD *)(a1 + 4968) = 0;
      v5 = _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 4968), 1u);
      SystemTimeAsFileTime = 0;
      v6 = 5LL * (v5 & 0x3F);
      *(_DWORD *)(v3 + 8 * v6 + 16) = v4;
      *(_DWORD *)(v3 + 8 * v6 + 32) = 4498;
      *(_QWORD *)(v3 + 8 * v6 + 24) = L"onecoreuap\\net\\netio\\iphlpsvc\\service\\client.c";
      *(_DWORD *)(v3 + 8 * v6 + 48) = 0;
      *(_QWORD *)(v3 + 8 * v6 + 40) = 0;
      *(_DWORD *)(a1 + 7536) = 0;
      *(_DWORD *)(a1 + 4960) = 1;
      *(_QWORD *)(a1 + 13544) = 0;
      *(_QWORD *)(a1 + 13632) = 8;
      *(_QWORD *)(a1 + 13640) = 0;
      *(_WORD *)(a1 + 13656) = 0;
      *(_BYTE *)(a1 + 13658) = 1;
      *(_QWORD *)(a1 + 19376) = 0;
      *(_QWORD *)(a1 + 13672) = a1 + 13664;
      *(_QWORD *)(a1 + 13664) = a1 + 13664;
      *(_DWORD *)(a1 + 13680) = 0;
      *(_WORD *)(a1 + 13552) = 0;
      *(IN6_ADDR *)(a1 + 13688) = in6addr_teredoinitiallinklocaladdress;
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      *(_QWORD *)(a1 + 13752) = *(unsigned __int64 *)&SystemTimeAsFileTime / 0x989680;
      *(_DWORD *)(a1 + 13760) = dword_1800CA098;
      *(_QWORD *)(a1 + 15928) = 0;
      *(_QWORD *)(a1 + 15920) = 0;
      *(_QWORD *)(a1 + 15912) = 0;
      *(_QWORD *)(a1 + 13768) = 0;
      InitializeSListHead((PSLIST_HEADER)(a1 + 19280));
      *(_QWORD *)(a1 + 15952) = 0;
      *(_QWORD *)(a1 + 15960) = 0;
      *(_DWORD *)(a1 + 16512) = 10;
      *(_DWORD *)(a1 + 17084) = 0;
      *(_QWORD *)(a1 + 19344) = 0;
      *(_BYTE *)(a1 + 19354) = 0;
      *(_QWORD *)(a1 + 19360) = 0;
      *(_QWORD *)(a1 + 19384) = 0;
      *(_DWORD *)(a1 + 19392) = 0;
      qword_1800CC818 = 0;
      *(_QWORD *)TeredoExternalPortMapping = 2;
      *(_QWORD *)(a1 + 13704) = 2;
      *(_QWORD *)(a1 + 13712) = 0;
      *(_QWORD *)(a1 + 16560) = TeredoClientCompletePacket;
      *(_QWORD *)(a1 + 16536) = 0;
      *(_QWORD *)(a1 + 16528) = 0;
      *(_QWORD *)(a1 + 16544) = a1 + 10104;
      *(_QWORD *)(a1 + 16552) = 0;
      *(_QWORD *)(a1 + 16568) = a1 + 4960;
      *(_BYTE *)(a1 + 16576) = 0;
      *(_DWORD *)(a1 + 17016) = 0;
      *(_OWORD *)(a1 + 16784) = 0;
      *(_OWORD *)(a1 + 16800) = 0;
      *(_QWORD *)(a1 + 16816) = 0;
      *(_DWORD *)(a1 + 16824) = 0;
      *(_OWORD *)(a1 + 16904) = 0;
      *(_OWORD *)(a1 + 16920) = 0;
      *(_WORD *)(a1 + 16906) = htons(0xDD8u);
      *(_WORD *)(a1 + 16904) = 2;
      *(IN_ADDR *)(a1 + 16908) = in4addr_allteredohostsonlink;
      *(_QWORD *)(a1 + 16912) = 0;
      *(_DWORD *)(a1 + 16936) = 40;
      *(_QWORD *)(a1 + 16944) = a1 + 17040;
      *(_DWORD *)(a1 + 17040) = 96;
      *(_DWORD *)(a1 + 17044) = 356188160;
      *(IN6_ADDR *)(a1 + 17048) = in6addr_any;
      *(IN6_ADDR *)(a1 + 17064) = in6addr_allnodesonlink;
      *(_QWORD *)(a1 + 17120) = TeredoClientCompleteRsPacket;
      *(_QWORD *)(a1 + 17096) = 0;
      *(_QWORD *)(a1 + 17088) = 0;
      *(_QWORD *)(a1 + 17104) = a1 + 10104;
      *(_QWORD *)(a1 + 17112) = 0;
      *(_QWORD *)(a1 + 17128) = a1 + 4960;
      *(_BYTE *)(a1 + 17136) = 0;
      *(_DWORD *)(a1 + 17576) = 0;
      *(_OWORD *)(a1 + 17344) = 0;
      *(_OWORD *)(a1 + 17360) = 0;
      *(_QWORD *)(a1 + 17376) = 0;
      *(_DWORD *)(a1 + 17384) = 0;
      *(_OWORD *)(a1 + 17464) = 0;
      *(_OWORD *)(a1 + 17480) = 0;
      *(_QWORD *)(a1 + 17504) = a1 + 17600;
      *(_DWORD *)(a1 + 17496) = 572;
      *(_QWORD *)(a1 + 18208) = TeredoClientCompletePortPredictionEchoPacket;
      *(_QWORD *)(a1 + 18184) = 0;
      *(_QWORD *)(a1 + 18176) = 0;
      *(_QWORD *)(a1 + 18192) = a1 + 10104;
      *(_QWORD *)(a1 + 18200) = 0;
      *(_QWORD *)(a1 + 18216) = a1 + 4960;
      *(_BYTE *)(a1 + 18224) = 0;
      *(_DWORD *)(a1 + 18664) = 0;
      *(_OWORD *)(a1 + 18432) = 0;
      *(_OWORD *)(a1 + 18448) = 0;
      *(_QWORD *)(a1 + 18464) = 0;
      *(_DWORD *)(a1 + 18472) = 0;
      *(_OWORD *)(a1 + 18552) = 0;
      *(_OWORD *)(a1 + 18568) = 0;
      *(_QWORD *)(a1 + 18592) = a1 + 18688;
      *(_DWORD *)(a1 + 18584) = 572;
      LastError = TeredoInitializeIo(
                    (int)a1 + 10104,
                    (int)a1 + 16904,
                    (int)a1 + 4960,
                    (unsigned int)TeredoClientStopIoComplete,
                    (__int64)TeredoClientDeviceReceive,
                    a1);
      if ( !LastError )
      {
        MaximumPeerAllocationLimit = TeredoGetMaximumPeerAllocationLimit();
        v9 = HeapCreate(0, 0, MaximumPeerAllocationLimit);
        *(_QWORD *)(a1 + 13768) = v9;
        if ( v9
          && (EventW = CreateEventW(0, 0, 0, 0), (*(_QWORD *)(a1 + 15920) = EventW) != 0)
          && (_InterlockedExchange((volatile __int32 *)(a1 + 15936), 1),
              (unsigned int)TpclRegisterWait(a1 + 15928, *(_QWORD *)(a1 + 15920), TeredoClientTimerCleanup, a1 + 4960)) )
        {
          LastError = HashTableInitialize(a1 + 13776);
          if ( !LastError )
          {
            LastError = TeredoRegisterCSNotification(a1 + 4960);
            if ( !LastError )
            {
              *(_QWORD *)(a1 + 19264) = 0;
              InitializeLock(a1 + 19264);
              LODWORD(v12) = *(_DWORD *)(a1 + 19328);
              EventWrite0(
                0x100000,
                L"TeredoResetBackOffStatemachine: old values are: In-Action: %u, Reset: %u, Failures: %u",
                *(unsigned int *)(a1 + 19332),
                *(unsigned int *)(a1 + 19336),
                v12);
              *(_DWORD *)(a1 + 19332) = 0;
              result = 0;
              *(_DWORD *)(a1 + 19336) = 1;
              *(_DWORD *)(a1 + 19328) = 0;
              *(_BYTE *)(a1 + 19353) = 1;
              return result;
            }
          }
        }
        else
        {
          LastError = GetLastError();
        }
      }
      TeredoUninitializeClient(a1 + 4960);
      return LastError;
    }
  }
  return 21;
}

```

## disassembly

```asm
0x18003c0c0  mov     rax, rsp
0x18003c0c3  mov     [rax+10h], rbx
0x18003c0c7  mov     [rax+18h], rbp
0x18003c0cb  push    rsi
0x18003c0cc  push    rdi
0x18003c0cd  push    r12
0x18003c0cf  push    r14
0x18003c0d1  push    r15
0x18003c0d3  sub     rsp, 30h
0x18003c0d7  mov     r8d, cs:g_Reference
0x18003c0de  lea     rbx, aOnecoreuapNetN_27; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003c0e5  shr     r8d, 1
0x18003c0e8  lea     r9, aTeredoinitiali_0; "TeredoInitializeClient"
0x18003c0ef  mov     rsi, rcx
0x18003c0f2  mov     dword ptr [rax-30h], 117Fh
0x18003c0f9  and     r8d, 3FFFFFFFh
0x18003c100  mov     [rax-38h], rbx
0x18003c104  lea     rdx, aReferenceservi; "ReferenceService: ++%u (%hs) @ %ls:%u"
0x18003c10b  mov     ecx, 40000h
0x18003c110  call    EventWrite0
0x18003c115  mov     r12d, 1
0x18003c11b  mov     eax, cs:g_Reference
0x18003c121  test    r12b, al
0x18003c124  jnz     loc_18003C5D3
0x18003c12a  lea     ecx, [rax+2]
0x18003c12d  lock cmpxchg cs:g_Reference, ecx
0x18003c135  jnz     short loc_18003C11B
0x18003c137  mov     r8d, 1186h
0x18003c13d  lea     rdi, [rsi+1360h]
0x18003c144  mov     rdx, rbx
0x18003c147  mov     rcx, rsi
0x18003c14a  call    ReferenceCompartmentEx
0x18003c14f  mov     edx, [rdi]
0x18003c151  xor     r15d, r15d
0x18003c154  mov     [rdi+8], r15d
0x18003c158  mov     eax, r12d
0x18003c15b  lock xadd [rdi+8], eax
0x18003c160  add     eax, r12d
0x18003c163  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], r15
0x18003c168  sub     eax, r12d
0x18003c16b  and     eax, 3Fh
0x18003c16e  lea     rcx, [rax+rax*4]
0x18003c172  mov     [rdi+rcx*8+10h], edx
0x18003c176  lea     rax, [rdi+2200h]
0x18003c17d  mov     dword ptr [rdi+rcx*8+20h], 1192h
0x18003c185  mov     [rdi+rcx*8+18h], rbx
0x18003c18a  mov     [rdi+rcx*8+30h], r15d
0x18003c18f  mov     [rdi+rcx*8+28h], r15
0x18003c194  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003c199  mov     [rdi+0A10h], r15d
0x18003c1a0  mov     [rdi], r12d
0x18003c1a3  mov     [rdi+2188h], r15
0x18003c1aa  mov     qword ptr [rdi+21E0h], 8
0x18003c1b5  mov     [rdi+21E8h], r15
0x18003c1bc  mov     [rdi+21F8h], r15w
0x18003c1c4  mov     [rdi+21FAh], r12b
0x18003c1cb  mov     [rdi+3850h], r15
0x18003c1d2  mov     [rax+8], rax
0x18003c1d6  mov     [rax], rax
0x18003c1d9  mov     [rdi+2210h], r15d
0x18003c1e0  mov     [rdi+2190h], r15w
0x18003c1e8  movups  xmm0, xmmword ptr cs:in6addr_teredoinitiallinklocaladdress.u
0x18003c1ef  movdqu  xmmword ptr [rdi+2218h], xmm0
0x18003c1f7  call    cs:__imp_GetSystemTimeAsFileTime
0x18003c1fe  nop     dword ptr [rax+rax+00h]
0x18003c203  mov     rax, 0D6BF94D5E57A42BDh
0x18003c20d  lea     r14, [rdi+2AD8h]
0x18003c214  mul     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x18003c219  lea     rcx, [rdi+37F0h]; ListHead
0x18003c220  shr     rdx, 17h
0x18003c224  mov     [rdi+2258h], rdx
0x18003c22b  mov     eax, cs:dword_1800CA098
0x18003c231  mov     [rdi+2260h], eax
0x18003c237  mov     [r14], r15
0x18003c23a  mov     [rdi+2AD0h], r15
0x18003c241  mov     [rdi+2AC8h], r15
0x18003c248  mov     [rdi+2268h], r15
0x18003c24f  call    cs:__imp_InitializeSListHead
0x18003c256  nop     dword ptr [rax+rax+00h]
0x18003c25b  mov     [rdi+2AF0h], r15
0x18003c262  lea     rbx, [rdi+1418h]
0x18003c269  mov     [rdi+2AF8h], r15
0x18003c270  xor     eax, eax
0x18003c272  mov     dword ptr [rdi+2D20h], 0Ah
0x18003c27c  xorps   xmm0, xmm0
0x18003c27f  mov     [rdi+2F5Ch], r15d
0x18003c286  mov     ecx, 0DD8h; hostshort
0x18003c28b  mov     [rdi+3830h], r15
0x18003c292  mov     [rdi+383Ah], r15b
0x18003c299  lea     ebp, [rax+2]
0x18003c29c  mov     [rdi+3840h], r15
0x18003c2a3  mov     [rdi+3858h], rax
0x18003c2aa  mov     [rdi+3860h], eax
0x18003c2b0  mov     cs:qword_1800CC818, rax
0x18003c2b7  mov     qword ptr cs:TeredoExternalPortMapping, rbp
0x18003c2be  mov     [rdi+2228h], rbp
0x18003c2c5  mov     [rdi+2230h], rax
0x18003c2cc  lea     rax, TeredoClientCompletePacket
0x18003c2d3  mov     [rdi+2D50h], rax
0x18003c2da  xor     eax, eax
0x18003c2dc  mov     [rdi+2D38h], r15
0x18003c2e3  mov     [rdi+2D30h], r15
0x18003c2ea  mov     [rdi+2D40h], rbx
0x18003c2f1  mov     [rdi+2D48h], r15
0x18003c2f8  mov     [rdi+2D58h], rdi
0x18003c2ff  mov     [rdi+2D60h], r15b
0x18003c306  mov     [rdi+2F18h], r15d
0x18003c30d  movups  xmmword ptr [rdi+2E30h], xmm0
0x18003c314  movups  xmmword ptr [rdi+2E40h], xmm0
0x18003c31b  mov     [rdi+2E50h], rax
0x18003c322  mov     [rdi+2E58h], eax
0x18003c328  movups  xmmword ptr [rdi+2EA8h], xmm0
0x18003c32f  movups  xmmword ptr [rdi+2EB8h], xmm0
0x18003c336  call    cs:__imp_htons
0x18003c33d  nop     dword ptr [rax+rax+00h]
0x18003c342  lea     rdx, [rdi+2EA8h]
0x18003c349  mov     [rdx+2], ax
0x18003c34d  mov     [rdx], bp
0x18003c350  mov     eax, dword ptr cs:in4addr_allteredohostsonlink.S_un
0x18003c356  mov     [rdx+4], eax
0x18003c359  xor     eax, eax
0x18003c35b  mov     [rdx+8], rax
0x18003c35f  lea     r9, TeredoClientStopIoComplete
0x18003c366  mov     dword ptr [rdi+2EC8h], 28h ; '('
0x18003c370  lea     rax, [rdi+2F30h]
0x18003c377  mov     [rdi+2ED0h], rax
0x18003c37e  mov     ecx, 23Ch
0x18003c383  mov     dword ptr [rax], 60h ; '`'
0x18003c389  mov     r8, rdi
0x18003c38c  mov     dword ptr [rdi+2F34h], 153B0000h
0x18003c396  lea     rax, TeredoClientCompleteRsPacket
0x18003c39d  movups  xmm0, xmmword ptr cs:in6addr_any.u
0x18003c3a4  mov     [rsp+58h+var_30], rsi
0x18003c3a9  movdqu  xmmword ptr [rdi+2F38h], xmm0
0x18003c3b1  movups  xmm1, xmmword ptr cs:in6addr_allnodesonlink.u
0x18003c3b8  xorps   xmm0, xmm0
0x18003c3bb  movdqu  xmmword ptr [rdi+2F48h], xmm1
0x18003c3c3  mov     [rdi+2F80h], rax
0x18003c3ca  xor     eax, eax
0x18003c3cc  mov     [rdi+2F68h], r15
0x18003c3d3  mov     [rdi+2F60h], r15
0x18003c3da  mov     [rdi+2F70h], rbx
0x18003c3e1  mov     [rdi+2F78h], r15
0x18003c3e8  mov     [rdi+2F88h], rdi
0x18003c3ef  mov     [rdi+2F90h], r15b
0x18003c3f6  mov     [rdi+3148h], r15d
0x18003c3fd  movups  xmmword ptr [rdi+3060h], xmm0
0x18003c404  movups  xmmword ptr [rdi+3070h], xmm0
0x18003c40b  mov     [rdi+3080h], rax
0x18003c412  mov     [rdi+3088h], eax
0x18003c418  lea     rax, [rdi+3160h]
0x18003c41f  movups  xmmword ptr [rdi+30D8h], xmm0
0x18003c426  movups  xmmword ptr [rdi+30E8h], xmm0
0x18003c42d  mov     [rdi+3100h], rax
0x18003c434  lea     rax, TeredoClientCompletePortPredictionEchoPacket
0x18003c43b  mov     [rdi+30F8h], ecx
0x18003c441  mov     [rdi+33C0h], rax
0x18003c448  xor     eax, eax
0x18003c44a  mov     [rdi+33A8h], r15
0x18003c451  mov     [rdi+33A0h], r15
0x18003c458  mov     [rdi+33B0h], rbx
0x18003c45f  mov     [rdi+33B8h], r15
0x18003c466  mov     [rdi+33C8h], rdi
0x18003c46d  mov     [rdi+33D0h], r15b
0x18003c474  mov     [rdi+3588h], r15d
0x18003c47b  movups  xmmword ptr [rdi+34A0h], xmm0
0x18003c482  movups  xmmword ptr [rdi+34B0h], xmm0
0x18003c489  mov     [rdi+34C0h], rax
0x18003c490  mov     [rdi+34C8h], eax
0x18003c496  lea     rax, [rdi+35A0h]
0x18003c49d  movups  xmmword ptr [rdi+3518h], xmm0
0x18003c4a4  movups  xmmword ptr [rdi+3528h], xmm0
0x18003c4ab  mov     [rdi+3540h], rax
0x18003c4b2  lea     rax, TeredoClientDeviceReceive
0x18003c4b9  mov     [rdi+3538h], ecx
0x18003c4bf  mov     rcx, rbx
0x18003c4c2  mov     [rsp+58h+var_38], rax
0x18003c4c7  call    TeredoInitializeIo
0x18003c4cc  mov     ebx, eax
0x18003c4ce  test    eax, eax
0x18003c4d0  jnz     short loc_18003C504
0x18003c4d2  call    TeredoGetMaximumPeerAllocationLimit
0x18003c4d7  mov     r8, rax; dwMaximumSize
0x18003c4da  xor     edx, edx; dwInitialSize
0x18003c4dc  xor     ecx, ecx; flOptions
0x18003c4de  call    cs:__imp_HeapCreate
0x18003c4e5  nop     dword ptr [rax+rax+00h]
0x18003c4ea  mov     [rdi+2268h], rax
0x18003c4f1  test    rax, rax
0x18003c4f4  jnz     short loc_18003C513
0x18003c4f6  call    cs:__imp_GetLastError
0x18003c4fd  nop     dword ptr [rax+rax+00h]
0x18003c502  mov     ebx, eax
0x18003c504  mov     rcx, rdi
0x18003c507  call    TeredoUninitializeClient
0x18003c50c  mov     eax, ebx
0x18003c50e  jmp     loc_18003C5D8
0x18003c513  xor     r9d, r9d; lpName
0x18003c516  xor     r8d, r8d; bInitialState
0x18003c519  xor     edx, edx; bManualReset
0x18003c51b  xor     ecx, ecx; lpEventAttributes
0x18003c51d  call    cs:__imp_CreateEventW
0x18003c524  nop     dword ptr [rax+rax+00h]
0x18003c529  mov     [rdi+2AD0h], rax
0x18003c530  test    rax, rax
0x18003c533  jz      short loc_18003C4F6
0x18003c535  mov     eax, r12d
0x18003c538  lea     r8, TeredoClientTimerCleanup
0x18003c53f  xchg    eax, [rdi+2AE0h]
0x18003c545  mov     rdx, [rdi+2AD0h]
0x18003c54c  mov     r9, rdi
0x18003c54f  mov     rcx, r14
0x18003c552  call    TpclRegisterWait
0x18003c557  test    eax, eax
0x18003c559  jz      short loc_18003C4F6
0x18003c55b  lea     rcx, [rdi+2270h]
0x18003c562  call    HashTableInitialize
0x18003c567  mov     ebx, eax
0x18003c569  test    eax, eax
0x18003c56b  jnz     short loc_18003C504
0x18003c56d  mov     rcx, rdi
0x18003c570  call    TeredoRegisterCSNotification
0x18003c575  mov     ebx, eax
0x18003c577  test    eax, eax
0x18003c579  jnz     short loc_18003C504
0x18003c57b  lea     rcx, [rdi+37E0h]
0x18003c582  mov     [rcx], r15
0x18003c585  call    InitializeLock
0x18003c58a  mov     eax, [rsi+4B80h]
0x18003c590  lea     rdx, aTeredoresetbac; "TeredoResetBackOffStatemachine: old val"...
0x18003c597  mov     r9d, [rsi+4B88h]
0x18003c59e  mov     ecx, 100000h
0x18003c5a3  mov     r8d, [rsi+4B84h]
0x18003c5aa  mov     dword ptr [rsp+58h+var_38], eax
0x18003c5ae  call    EventWrite0
0x18003c5b3  mov     [rsi+4B84h], r15d
0x18003c5ba  xor     eax, eax
0x18003c5bc  mov     [rsi+4B88h], r12d
0x18003c5c3  mov     [rsi+4B80h], r15d
0x18003c5ca  mov     [rdi+3839h], r12b
0x18003c5d1  jmp     short loc_18003C5D8
0x18003c5d3  mov     eax, 15h
0x18003c5d8  mov     rbx, [rsp+58h+arg_8]
0x18003c5dd  mov     rbp, [rsp+58h+arg_10]
0x18003c5e2  add     rsp, 30h
0x18003c5e6  pop     r15
0x18003c5e8  pop     r14
0x18003c5ea  pop     r12
0x18003c5ec  pop     rdi
0x18003c5ed  pop     rsi
0x18003c5ee  retn
```
