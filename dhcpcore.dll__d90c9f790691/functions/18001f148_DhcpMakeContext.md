# DhcpMakeContext

- ea: `0x18001f148`
- end: `0x18001f596`
- name: `DhcpMakeContext`
- size: `1102`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `loader_planting`

## callers

- `0x1800159d0`

## callees

- `0x180002534`
- `0x1800048cc`
- `0x180005670`
- `0x180006440`
- `0x1800110a8`
- `0x180012554`
- `0x180014bd8`
- `0x180019248`
- `0x18001c0d8`
- `0x18001f148`
- `0x180035ef4`
- `0x180043e68`
- `0x18004d1a0`
- `0x18004d4c0`
- `0x18004d958`
- `0x18004d9e8`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18001f4fb`
- `ntdll!RtlFreeUnicodeString` at `0x18001f4fb`
- `ntdll!RtlStringFromGUID` at `0x18001f1a0`
- `ntdll!RtlStringFromGUID` at `0x18001f1a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f55a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f55a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f250`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18001f250`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f4c5`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x18001f4c5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f545`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f545`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001f29c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18001f29c`
- `RPCRT4!UuidCreate` at `0x18001f433`
- `RPCRT4!UuidCreate` at `0x18001f433`
- `WS2_32!WSACreateEvent` at `0x18001f464`
- `WS2_32!WSACreateEvent` at `0x18001f464`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f482`
- `WS2_32!__imp_WSAGetLastError` at `0x18001f482`

## pseudocode

```c
__int64 __fastcall DhcpMakeContext(__int64 a1, __int64 a2, __int64 *a3)
{
  unsigned int v6; // eax
  unsigned int AdapterKey; // esi
  rsize_t v8; // rbp
  unsigned int v9; // edi
  char *v10; // rax
  __int64 v11; // rdi
  char *v12; // rax
  char *v13; // rax
  unsigned int v14; // eax
  HANDLE v15; // rax
  int Error; // eax
  HANDLE Semaphore; // rbx
  HANDLE EventW; // rax
  struct _UNICODE_STRING GuidString; // [rsp+30h] [rbp-58h] BYREF
  int v21; // [rsp+98h] [rbp+10h] BYREF

  GuidString = 0;
  v21 = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_q(1028, 35, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, a1);
  *a3 = 0;
  v6 = RtlStringFromGUID((const GUID *const)(a2 + 12), &GuidString);
  AdapterKey = Win32FromNTSTATUS(v6);
  if ( !AdapterKey )
  {
    v8 = (GuidString.Length + 9) & 0xFFFFFFF8;
    v9 = v8 + 14472;
    if ( (unsigned int)v8 < 0xFFFFC778 )
      goto LABEL_8;
    v9 = -1;
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_d(1025, 36, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, 2147942934LL);
    AdapterKey = WX_WIN32_FROM_HR(2147942934LL);
    if ( !AdapterKey )
    {
LABEL_8:
      v10 = (char *)DhcpAlloc(v9);
      v11 = (__int64)v10;
      if ( !v10 )
      {
        AdapterKey = 8;
        goto LABEL_28;
      }
      v12 = v10 + 2176;
      *(_QWORD *)(v11 + 88) = v12;
      v12 += 8;
      *(_QWORD *)(v11 + 56) = v12;
      v13 = &v12[v8];
      *(_QWORD *)(v11 + 752) = v13;
      *(_QWORD *)(v11 + 2000) = v13 + 4096;
      InitializeCriticalSection((LPCRITICAL_SECTION)(v11 + 592));
      *(_QWORD *)(v11 + 8) = v11;
      *(_QWORD *)v11 = v11;
      *(_QWORD *)(v11 + 640) = v11 + 632;
      *(_QWORD *)(v11 + 632) = v11 + 632;
      *(_QWORD *)(v11 + 688) = v11 + 680;
      *(_QWORD *)(v11 + 680) = v11 + 680;
      *(_QWORD *)(v11 + 704) = v11 + 696;
      *(_QWORD *)(v11 + 696) = v11 + 696;
      *(_QWORD *)(v11 + 720) = v11 + 712;
      *(_QWORD *)(v11 + 712) = v11 + 712;
      InitializeSRWLock((PSRWLOCK)(v11 + 672));
      *(_DWORD *)(v11 + 16) = 1;
      AdapterKey = memcpy_s(
                     *(void *const *)(v11 + 88),
                     8u,
                     *(const void *const *)(a2 + 64),
                     *(unsigned __int16 *)(a2 + 60));
      if ( !AdapterKey )
      {
        AdapterKey = memcpy_s(*(void *const *)(v11 + 56), v8, GuidString.Buffer, GuidString.Length);
        if ( !AdapterKey )
        {
          *(_WORD *)(*(_QWORD *)(v11 + 56) + 2 * ((unsigned __int64)GuidString.Length >> 1)) = 0;
          if ( !g_fVelocityRemoveFTimersEnabled )
            *(_DWORD *)(v11 + 576) = 0;
          *(_QWORD *)(v11 + 72) = -1;
          *(_QWORD *)(v11 + 64) = -1;
          *(_DWORD *)(v11 + 1976) = 0;
          *(_QWORD *)(v11 + 2152) = 0;
          *(_QWORD *)(v11 + 24) = a1;
          *(_DWORD *)(v11 + 48) = *(_DWORD *)(a2 + 8);
          *(_OWORD *)(v11 + 32) = *(_OWORD *)(a2 + 12);
          *(_DWORD *)(v11 + 52) = *(_DWORD *)(a2 + 28);
          *(_BYTE *)(v11 + 84) = *(_BYTE *)(a2 + 40);
          *(_DWORD *)(v11 + 96) = *(unsigned __int16 *)(a2 + 60);
          *(_QWORD *)(v11 + 104) = *(_QWORD *)(a2 + 88);
          *(_DWORD *)(v11 + 820) = *(_DWORD *)(a2 + 36);
          *(_DWORD *)(v11 + 112) = *(_DWORD *)(a2 + 44);
          *(_DWORD *)(v11 + 116) = *(_DWORD *)(a2 + 48);
          *(_DWORD *)(v11 + 2028) = IsHardwareAddressRandomized(*(_QWORD *)(v11 + 88), *(_QWORD *)(v11 + 56));
          *(_QWORD *)(v11 + 2032) = 0;
          *(_QWORD *)(v11 + 2040) = 0;
          *(_DWORD *)(v11 + 2048) = 0;
          *(_DWORD *)(v11 + 580) = 0;
          *(_DWORD *)(v11 + 2128) = 0;
          *(_QWORD *)(v11 + 2132) = 4000;
          *(_DWORD *)(v11 + 2140) = 0x40000000;
          *(_DWORD *)(v11 + 2144) = 1036831949;
          *(_DWORD *)(v11 + 2148) = 4;
          if ( *(_DWORD *)&DhcpGlobalUseNetworkHint )
            GetNetworkHint(*(_QWORD *)(v11 + 24), v11 + 1888, &v21, 0);
          DhcpStandbyResetStatus(v11 + 2016);
          AdapterKey = DhcpCreateAdapterKey(*(LPCWSTR *)(v11 + 56), (HKEY *)(v11 + 728));
          if ( !AdapterKey )
          {
            AdapterKey = DhcpReadClientID(v11);
            if ( !AdapterKey )
            {
              v14 = UuidCreate((UUID *)(v11 + 2112));
              if ( v14 && (xmmword_1800616A0 & 2) != 0 )
                WPP_SF_d(1025, AdapterKey + 37, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, v14);
              *(_DWORD *)(v11 + 828) = 0;
              v15 = WSACreateEvent();
              *(_QWORD *)(v11 + 832) = v15;
              if ( !v15 && (xmmword_1800616A0 & 2) != 0 )
              {
                Error = WSAGetLastError();
                WPP_SF_qD(1025, 38, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, 0, Error);
              }
              *(_DWORD *)(v11 + 840) = 0;
              Semaphore = CreateSemaphoreExW(0, 1, 1, 0, 0, 0x1F0003u);
              if ( Semaphore )
              {
                EventW = CreateEventW(0, 1, 1, 0);
                if ( EventW )
                {
                  *(_DWORD *)(v11 + 856) = 1;
                  AdapterKey = 0;
                  *(_DWORD *)(v11 + 860) = 128;
                  *(_QWORD *)(v11 + 1896) = 0;
                  *(_QWORD *)(v11 + 664) = Semaphore;
                  *(_QWORD *)(v11 + 1984) = EventW;
                  *a3 = v11;
                  goto LABEL_28;
                }
                AdapterKey = GetLastErrorOrUnknown();
                CloseHandle(Semaphore);
              }
              else
              {
                AdapterKey = GetLastErrorOrUnknown();
              }
            }
          }
        }
      }
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 16), 0xFFFFFFFF) == 1 )
        DhcpDestroyContextEx(v11);
    }
  }
LABEL_28:
  if ( GuidString.Buffer )
  {
    RtlFreeUnicodeString(&GuidString);
    GuidString.Buffer = 0;
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 39, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids, AdapterKey);
  return AdapterKey;
}

```

## disassembly

```asm
0x18001f148  mov     rax, rsp
0x18001f14b  push    rbx
0x18001f14c  push    rbp
0x18001f14d  push    rsi
0x18001f14e  push    rdi
0x18001f14f  push    r12
0x18001f151  push    r13
0x18001f153  push    r14
0x18001f155  push    r15
0x18001f157  sub     rsp, 48h
0x18001f15b  xorps   xmm0, xmm0
0x18001f15e  xor     r13d, r13d
0x18001f161  movups  xmmword ptr [rax-58h], xmm0
0x18001f165  mov     [rax+10h], r13d
0x18001f169  mov     r12, r8
0x18001f16c  mov     r14, rdx
0x18001f16f  mov     rbx, rcx
0x18001f172  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001f179  jz      short loc_18001F193
0x18001f17b  lea     edx, [r13+23h]
0x18001f17f  mov     ecx, 404h
0x18001f184  mov     r9, rbx
0x18001f187  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f18e  call    WPP_SF_q
0x18001f193  lea     rdx, [rsp+88h+GuidString]; GuidString
0x18001f198  mov     [r12], r13
0x18001f19c  lea     rcx, [r14+0Ch]; Guid
0x18001f1a0  call    cs:__imp_RtlStringFromGUID
0x18001f1a6  mov     ecx, eax
0x18001f1a8  call    Win32FromNTSTATUS
0x18001f1ad  mov     esi, eax
0x18001f1af  test    eax, eax
0x18001f1b1  jnz     loc_18001F4EF
0x18001f1b7  movzx   ebp, [rsp+88h+GuidString.Length]
0x18001f1bc  add     ebp, 9
0x18001f1bf  and     ebp, 0FFFFFFF8h
0x18001f1c2  lea     edi, [rbp+3888h]
0x18001f1c8  cmp     edi, 3888h
0x18001f1ce  jnb     short loc_18001F209
0x18001f1d0  or      edi, 0FFFFFFFFh
0x18001f1d3  test    byte ptr cs:xmmword_1800616A0, 2
0x18001f1da  mov     esi, 80070216h
0x18001f1df  jz      short loc_18001F1F8
0x18001f1e1  lea     edx, [rax+24h]
0x18001f1e4  mov     ecx, 401h
0x18001f1e9  mov     r9d, esi
0x18001f1ec  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f1f3  call    WPP_SF_d
0x18001f1f8  mov     ecx, esi
0x18001f1fa  call    WX_WIN32_FROM_HR
0x18001f1ff  mov     esi, eax
0x18001f201  test    eax, eax
0x18001f203  jnz     loc_18001F4EF
0x18001f209  mov     ecx, edi
0x18001f20b  call    DhcpAlloc
0x18001f210  mov     rdi, rax
0x18001f213  test    rax, rax
0x18001f216  jnz     short loc_18001F220
0x18001f218  lea     esi, [rax+8]
0x18001f21b  jmp     loc_18001F4EF
0x18001f220  add     rax, 880h
0x18001f226  lea     rcx, [rdi+250h]; lpCriticalSection
0x18001f22d  mov     [rdi+58h], rax
0x18001f231  add     rax, 8
0x18001f235  mov     [rdi+38h], rax
0x18001f239  add     rax, rbp
0x18001f23c  mov     [rdi+2F0h], rax
0x18001f243  add     rax, 1000h
0x18001f249  mov     [rdi+7D0h], rax
0x18001f250  call    cs:__imp_InitializeCriticalSection
0x18001f256  mov     [rdi+8], rdi
0x18001f25a  lea     rax, [rdi+278h]
0x18001f261  mov     [rdi], rdi
0x18001f264  lea     rcx, [rdi+2A0h]; SRWLock
0x18001f26b  mov     [rax+8], rax
0x18001f26f  mov     [rax], rax
0x18001f272  lea     rax, [rdi+2A8h]
0x18001f279  mov     [rax+8], rax
0x18001f27d  mov     [rax], rax
0x18001f280  lea     rax, [rdi+2B8h]
0x18001f287  mov     [rax+8], rax
0x18001f28b  mov     [rax], rax
0x18001f28e  lea     rax, [rdi+2C8h]
0x18001f295  mov     [rax+8], rax
0x18001f299  mov     [rax], rax
0x18001f29c  call    cs:__imp_InitializeSRWLock
0x18001f2a2  mov     dword ptr [rdi+10h], 1
0x18001f2a9  mov     edx, 8; DestinationSize
0x18001f2ae  movzx   r9d, word ptr [r14+3Ch]; SourceSize
0x18001f2b3  mov     r8, [r14+40h]; Source
0x18001f2b7  mov     rcx, [rdi+58h]; Destination
0x18001f2bb  call    memcpy_s
0x18001f2c0  mov     esi, eax
0x18001f2c2  test    eax, eax
0x18001f2c4  jnz     loc_18001F4DA
0x18001f2ca  movzx   r9d, [rsp+88h+GuidString.Length]; SourceSize
0x18001f2d0  mov     rdx, rbp; DestinationSize
0x18001f2d3  mov     r8, [rsp+88h+GuidString.Buffer]; Source
0x18001f2d8  mov     rcx, [rdi+38h]; Destination
0x18001f2dc  call    memcpy_s
0x18001f2e1  mov     esi, eax
0x18001f2e3  test    eax, eax
0x18001f2e5  jnz     loc_18001F4DA
0x18001f2eb  movzx   edx, [rsp+88h+GuidString.Length]
0x18001f2f0  mov     rcx, [rdi+38h]
0x18001f2f4  shr     rdx, 1
0x18001f2f7  mov     [rcx+rdx*2], r13w
0x18001f2fc  cmp     cs:g_fVelocityRemoveFTimersEnabled, r13d
0x18001f303  jnz     short loc_18001F30C
0x18001f305  mov     [rdi+240h], r13d
0x18001f30c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001f310  mov     [rdi+48h], rax
0x18001f314  mov     [rdi+40h], rax
0x18001f318  mov     [rdi+7B8h], r13d
0x18001f31f  mov     [rdi+868h], r13
0x18001f326  mov     [rdi+18h], rbx
0x18001f32a  mov     eax, [r14+8]
0x18001f32e  mov     [rdi+30h], eax
0x18001f331  movups  xmm0, xmmword ptr [r14+0Ch]
0x18001f336  movdqu  xmmword ptr [rdi+20h], xmm0
0x18001f33b  mov     eax, [r14+1Ch]
0x18001f33f  mov     [rdi+34h], eax
0x18001f342  mov     al, [r14+28h]
0x18001f346  mov     [rdi+54h], al
0x18001f349  movzx   eax, word ptr [r14+3Ch]
0x18001f34e  mov     [rdi+60h], eax
0x18001f351  mov     rax, [r14+58h]
0x18001f355  mov     [rdi+68h], rax
0x18001f359  mov     eax, [r14+24h]
0x18001f35d  mov     [rdi+334h], eax
0x18001f363  mov     eax, [r14+2Ch]
0x18001f367  mov     [rdi+70h], eax
0x18001f36a  mov     eax, [r14+30h]
0x18001f36e  mov     [rdi+74h], eax
0x18001f371  mov     rdx, [rdi+38h]
0x18001f375  mov     rcx, [rdi+58h]
0x18001f379  call    IsHardwareAddressRandomized
0x18001f37e  mov     [rdi+7ECh], eax
0x18001f384  mov     [rdi+7F0h], r13
0x18001f38b  mov     [rdi+7F8h], r13
0x18001f392  mov     [rdi+800h], r13d
0x18001f399  mov     [rdi+244h], r13d
0x18001f3a0  mov     [rdi+850h], r13d
0x18001f3a7  mov     qword ptr [rdi+854h], 0FA0h
0x18001f3b2  mov     dword ptr [rdi+85Ch], 40000000h
0x18001f3bc  mov     dword ptr [rdi+860h], 3DCCCCCDh
0x18001f3c6  mov     dword ptr [rdi+864h], 4
0x18001f3d0  cmp     cs:DhcpGlobalUseNetworkHint, r13d
0x18001f3d7  jz      short loc_18001F3F4
0x18001f3d9  mov     rcx, [rdi+18h]
0x18001f3dd  lea     rdx, [rdi+760h]
0x18001f3e4  xor     r9d, r9d
0x18001f3e7  lea     r8, [rsp+88h+arg_8]
0x18001f3ef  call    GetNetworkHint
0x18001f3f4  lea     rcx, [rdi+7E0h]
0x18001f3fb  call    DhcpStandbyResetStatus
0x18001f400  mov     rcx, [rdi+38h]; lpSubKey
0x18001f404  lea     rdx, [rdi+2D8h]
0x18001f40b  call    DhcpCreateAdapterKey
0x18001f410  mov     esi, eax
0x18001f412  test    eax, eax
0x18001f414  jnz     loc_18001F4DA
0x18001f41a  mov     rcx, rdi
0x18001f41d  call    DhcpReadClientID
0x18001f422  mov     esi, eax
0x18001f424  test    eax, eax
0x18001f426  jnz     loc_18001F4DA
0x18001f42c  lea     rcx, [rdi+840h]; Uuid
0x18001f433  call    cs:__imp_UuidCreate
0x18001f439  test    eax, eax
0x18001f43b  jz      short loc_18001F45D
0x18001f43d  test    byte ptr cs:xmmword_1800616A0, 2
0x18001f444  jz      short loc_18001F45D
0x18001f446  lea     edx, [rsi+25h]
0x18001f449  mov     ecx, 401h
0x18001f44e  mov     r9d, eax
0x18001f451  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f458  call    WPP_SF_d
0x18001f45d  mov     [rdi+33Ch], r13d
0x18001f464  call    cs:__imp_WSACreateEvent
0x18001f46a  mov     [rdi+340h], rax
0x18001f471  mov     rbx, rax
0x18001f474  test    rax, rax
0x18001f477  jnz     short loc_18001F4A3
0x18001f479  test    byte ptr cs:xmmword_1800616A0, 2
0x18001f480  jz      short loc_18001F4A3
0x18001f482  call    cs:__imp_WSAGetLastError
0x18001f488  lea     edx, [rbx+26h]
0x18001f48b  mov     ecx, 401h
0x18001f490  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f497  mov     [rsp+88h+dwFlags], eax
0x18001f49b  mov     r9, rbx
0x18001f49e  call    WPP_SF_qD
0x18001f4a3  xor     r9d, r9d; lpName
0x18001f4a6  mov     [rsp+88h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x18001f4ae  xor     ecx, ecx; lpSemaphoreAttributes
0x18001f4b0  mov     [rdi+348h], r13d
0x18001f4b7  mov     [rsp+88h+dwFlags], r13d; dwFlags
0x18001f4bc  lea     ebp, [r9+1]
0x18001f4c0  mov     r8d, ebp; lMaximumCount
0x18001f4c3  mov     edx, ebp; lInitialCount
0x18001f4c5  call    cs:__imp_CreateSemaphoreExW
0x18001f4cb  mov     rbx, rax
0x18001f4ce  test    rax, rax
0x18001f4d1  jnz     short loc_18001F53B
0x18001f4d3  call    GetLastErrorOrUnknown
0x18001f4d8  mov     esi, eax
0x18001f4da  or      eax, 0FFFFFFFFh
0x18001f4dd  lock xadd [rdi+10h], eax
0x18001f4e2  cmp     eax, 1
0x18001f4e5  jnz     short loc_18001F4EF
0x18001f4e7  mov     rcx, rdi
0x18001f4ea  call    DhcpDestroyContextEx
0x18001f4ef  cmp     [rsp+88h+GuidString.Buffer], r13
0x18001f4f4  jz      short loc_18001F506
0x18001f4f6  lea     rcx, [rsp+88h+GuidString]; UnicodeString
0x18001f4fb  call    cs:__imp_RtlFreeUnicodeString
0x18001f501  mov     [rsp+88h+GuidString.Buffer], r13
0x18001f506  test    byte ptr cs:xmmword_1800616A0, 10h
0x18001f50d  jz      short loc_18001F528
0x18001f50f  mov     edx, 27h ; '''
0x18001f514  lea     r8, WPP_646eea9290bc30ea90b2a64518d0ac7d_Traceguids
0x18001f51b  mov     ecx, 404h
0x18001f520  mov     r9d, esi
0x18001f523  call    WPP_SF_D
0x18001f528  mov     eax, esi
0x18001f52a  add     rsp, 48h
0x18001f52e  pop     r15
0x18001f530  pop     r14
0x18001f532  pop     r13
0x18001f534  pop     r12
0x18001f536  pop     rdi
0x18001f537  pop     rsi
0x18001f538  pop     rbp
0x18001f539  pop     rbx
0x18001f53a  retn
0x18001f53b  xor     r9d, r9d; lpName
0x18001f53e  mov     r8d, ebp; bInitialState
0x18001f541  mov     edx, ebp; bManualReset
0x18001f543  xor     ecx, ecx; lpEventAttributes
0x18001f545  call    cs:__imp_CreateEventW
0x18001f54b  test    rax, rax
0x18001f54e  jnz     short loc_18001F565
0x18001f550  call    GetLastErrorOrUnknown
0x18001f555  mov     rcx, rbx; hObject
0x18001f558  mov     esi, eax
0x18001f55a  call    cs:__imp_CloseHandle
0x18001f560  jmp     loc_18001F4DA
0x18001f565  mov     [rdi+358h], ebp
0x18001f56b  mov     esi, r13d
0x18001f56e  mov     dword ptr [rdi+35Ch], 80h
0x18001f578  mov     [rdi+768h], r13
0x18001f57f  mov     [rdi+298h], rbx
0x18001f586  mov     [rdi+7C0h], rax
0x18001f58d  mov     [r12], rdi
0x18001f591  jmp     loc_18001F4EF
```
