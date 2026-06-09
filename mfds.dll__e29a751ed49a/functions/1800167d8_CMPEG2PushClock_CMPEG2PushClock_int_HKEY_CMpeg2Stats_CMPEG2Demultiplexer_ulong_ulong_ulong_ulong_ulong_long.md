# CMPEG2PushClock::CMPEG2PushClock(int,HKEY__ *,CMpeg2Stats *,CMPEG2Demultiplexer *,ulong,ulong,ulong,ulong,ulong,long *)

- ea: `0x1800167d8`
- end: `0x180016c25`
- name: `??0CMPEG2PushClock@@QEAA@HPEAUHKEY__@@PEAVCMpeg2Stats@@PEAVCMPEG2Demultiplexer@@KKKKKPEAJ@Z`
- size: `1101`
- prototype: `CMPEG2PushClock *(CMPEG2PushClock *__hidden this, int, HKEY, struct CMpeg2Stats *, struct CMPEG2Demultiplexer *, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18004fa44`
- `0x1800a5e3c`

## callees

- `0x180002820`
- `0x18000b8c0`
- `0x1800167d8`
- `0x180016c2c`
- `0x180016d40`
- `0x180016e00`
- `0x180016e30`
- `0x180016ed0`
- `0x18002d514`
- `0x18004c0d0`
- `0x18004cc7c`
- `0x18004cdc8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800169b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800169cc`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800169b9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800169cc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800169f3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800169f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016a12`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016adb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016adb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b74`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016aa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b3c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016aa3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180016b3c`

## pseudocode

```c
CMPEG2PushClock *__fastcall CMPEG2PushClock::CMPEG2PushClock(
        CMPEG2PushClock *this,
        int a2,
        HKEY a3,
        struct CMpeg2Stats *a4,
        struct CMPEG2Demultiplexer *cbData,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int Data,
        int *Type)
{
  CMPEG2PushClock *v11; // r15
  unsigned int v14; // r9d
  unsigned int v17; // ecx
  unsigned int v18; // r8d
  unsigned int v19; // ebx
  int *v20; // rdi
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v23; // eax
  __int64 v24; // rcx
  unsigned int v25; // eax
  __int64 v26; // rax
  unsigned int v29; // [rsp+80h] [rbp+40h] BYREF
  unsigned int lpData; // [rsp+88h] [rbp+48h] BYREF

  v11 = (CMPEG2PushClock *)((char *)this + 16);
  *(_QWORD *)this = &CMPEG2PushClock::`vftable'{for `IReferenceClock'};
  v14 = a6;
  *((_QWORD *)this + 1) = &CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'};
  *((_QWORD *)this + 2) = &CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'};
  *((_QWORD *)this + 3) = &CMPEG2PushClock::`vftable'{for `CIPTSConvert'};
  CTClockSubordinate<__int64,__int64>::CTClockSubordinate<__int64,__int64>(
    (_DWORD)this + 32,
    this != 0 ? (_DWORD)this + 16 : 0,
    (_DWORD)a3,
    v14,
    a7,
    a8,
    a9,
    (__int64)a4);
  *((_QWORD *)this + 36) = cbData;
  *((_QWORD *)this + 60) = 0x3FF0000000000000LL;
  *((_QWORD *)this + 32) = 0;
  *((_QWORD *)this + 33) = 0;
  *((_QWORD *)this + 34) = 0;
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 51) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_QWORD *)this + 55) = 0;
  *((_QWORD *)this + 56) = 0;
  *((_DWORD *)this + 114) = 0;
  *((_QWORD *)this + 58) = 0;
  *((_DWORD *)this + 132) = 0;
  *((_QWORD *)this + 63) = -1;
  *((_QWORD *)this + 65) = -1;
  *((_DWORD *)this + 100) = a2;
  v17 = 330000 * Data;
  *((_QWORD *)this + 35) = a4;
  *((_QWORD *)this + 52) = 1;
  *((_QWORD *)this + 62) = 2000000;
  *((_QWORD *)this + 64) = 500000;
  CTSmoothingFilter<__int64>::CTSmoothingFilter<__int64>((char *)this + 536, v17 / 0x36EE80);
  CMpeg2Time::CMpeg2Time((CMPEG2PushClock *)((char *)this + 624), a4, v18);
  *((_DWORD *)this + 177) = 1;
  v19 = 0;
  *((_DWORD *)this + 176) = -1;
  *((_DWORD *)this + 178) = 0;
  v29 = 0;
  lpData = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&Data, "CMPEG2PushClock::CMPEG2PushClock", 931);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 21, &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids, this);
  v20 = Type;
  *Type = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 8);
  InitializeCriticalSection((LPCRITICAL_SECTION)this + 9);
  *((_OWORD *)this + 19) = 0;
  while ( v19 < 2 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + v19 + 38) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      *v20 = LastError;
      goto LABEL_21;
    }
    ++v19;
  }
  *((_QWORD *)this + 51) = -1;
  *((_QWORD *)this + 53) = 0;
  CTClockSubordinate<__int64,__int64>::Reset((char *)this + 32);
  *((_QWORD *)this + 52) = CMPEG2PushClock::GetFreq(v11);
  v23 = 50;
  lpData = 50;
  Data = 0;
  if ( a3 )
  {
    LODWORD(cbData) = 4;
    LODWORD(Type) = 4;
    if ( RegQueryValueExW(a3, L"OverPadMillis", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
    {
      RegSetValueExW(a3, L"OverPadMillis", 0, 4u, (const BYTE *)&lpData, 4u);
      v23 = lpData;
    }
    else
    {
      v23 = Data;
      lpData = Data;
    }
  }
  v24 = 10000 * v23;
  v25 = 200;
  Data = 0;
  v29 = 200;
  *((_QWORD *)this + 64) = v24;
  if ( a3 )
  {
    LODWORD(cbData) = 4;
    LODWORD(Type) = 4;
    if ( RegQueryValueExW(a3, L"MinDownstreamBufferingMillis", 0, (LPDWORD)&Type, (LPBYTE)&Data, (LPDWORD)&cbData) )
    {
      RegSetValueExW(a3, L"MinDownstreamBufferingMillis", 0, 4u, (const BYTE *)&v29, 4u);
      v25 = v29;
    }
    else
    {
      v25 = Data;
      v29 = Data;
    }
  }
  *((_QWORD *)this + 62) = 10000 * v25;
  RegGetValIfExist(a3, L"ClockSubordinateSettlingMillis", 0x2710u, 1, (unsigned int *)this + 178);
  v26 = -CMPEG2PushClock::SampleClock(v11);
  *((_QWORD *)this + 59) = v26;
  if ( (unsigned __int8)byte_1800EACCB >= 2u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 17), 22, &WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids, this, v26);
  _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)this + 35) + 32LL));
LABEL_21:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&Data);
  return this;
}

```

## disassembly

```asm
0x1800167d8  mov     [rsp-38h+arg_10], rbx
0x1800167dd  push    rbp
0x1800167de  push    rsi
0x1800167df  push    rdi
0x1800167e0  push    r12
0x1800167e2  push    r13
0x1800167e4  push    r14
0x1800167e6  push    r15
0x1800167e8  mov     rbp, rsp
0x1800167eb  sub     rsp, 40h
0x1800167ef  mov     [rsp+40h+var_8], r9
0x1800167f4  lea     r15, [rcx+10h]
0x1800167f8  mov     ebx, edx
0x1800167fa  lea     rax, ??_7CMPEG2PushClock@@6BIReferenceClock@@@; const CMPEG2PushClock::`vftable'{for `IReferenceClock'}
0x180016801  mov     [rcx], rax
0x180016804  mov     rdi, r9
0x180016807  mov     r9d, [rbp+arg_28]
0x18001680b  lea     rax, ??_7CMPEG2PushClock@@6BCIPCRValueNotify@@@; const CMPEG2PushClock::`vftable'{for `CIPCRValueNotify'}
0x180016812  mov     [rcx+8], rax
0x180016816  mov     rsi, rcx
0x180016819  lea     rax, ??_7CMPEG2PushClock@@6B?$CTIGetTime@_J@@@; const CMPEG2PushClock::`vftable'{for `CTIGetTime<__int64>'}
0x180016820  mov     r14, r8
0x180016823  mov     [r15], rax
0x180016826  lea     rax, ??_7CMPEG2PushClock@@6BCIPTSConvert@@@; const CMPEG2PushClock::`vftable'{for `CIPTSConvert'}
0x18001682d  mov     [rcx+18h], rax
0x180016831  mov     rax, rcx
0x180016834  neg     rax
0x180016837  mov     eax, [rbp+arg_40]
0x18001683d  mov     [rsp+40h+var_10], eax
0x180016841  sbb     rdx, rdx
0x180016844  mov     eax, [rbp+arg_38]
0x180016847  and     rdx, r15
0x18001684a  mov     dword ptr [rsp+40h+lpcbData], eax
0x18001684e  add     rcx, 20h ; ' '
0x180016852  mov     eax, [rbp+arg_30]
0x180016855  mov     dword ptr [rsp+40h+lpData], eax
0x180016859  call    ??0?$CTClockSubordinate@_J_J@@QEAA@PEAV?$CTIGetTime@_J@@_JKKKKPEAVCMpeg2Stats@@@Z; CTClockSubordinate<__int64,__int64>::CTClockSubordinate<__int64,__int64>(CTIGetTime<__int64> *,__int64,ulong,ulong,ulong,ulong,CMpeg2Stats *)
0x18001685e  mov     rax, [rbp+cbData]
0x180016862  xor     ecx, ecx
0x180016864  movsd   xmm2, cs:__real@3fe999999999999a
0x18001686c  mov     [rsi+120h], rax
0x180016873  mov     rax, 3FF0000000000000h
0x18001687d  mov     [rsi+1E0h], rax
0x180016884  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016888  mov     [rsi+100h], rcx
0x18001688f  mov     [rsi+108h], rcx
0x180016896  mov     [rsi+110h], rcx
0x18001689d  mov     [rsi+128h], rcx
0x1800168a4  mov     [rsi+198h], rcx
0x1800168ab  mov     [rsi+1A8h], rcx
0x1800168b2  mov     [rsi+1B0h], rcx
0x1800168b9  mov     [rsi+1B8h], rcx
0x1800168c0  mov     [rsi+1C0h], rcx
0x1800168c7  mov     [rsi+1C8h], ecx
0x1800168cd  mov     [rsi+1D0h], rcx
0x1800168d4  mov     [rsi+210h], ecx
0x1800168da  mov     [rsi+1F8h], rax
0x1800168e1  mov     [rsi+208h], rax
0x1800168e8  mov     eax, 95217CB1h
0x1800168ed  mov     [rsi+190h], ebx
0x1800168f3  lea     ebx, [rcx+1]
0x1800168f6  imul    ecx, dword ptr [rbp+Data], 50910h
0x180016900  mov     [rsi+118h], rdi
0x180016907  mov     [rsi+1A0h], rbx
0x18001690e  mov     qword ptr [rsi+1F0h], 1E8480h
0x180016919  mov     qword ptr [rsi+200h], 7A120h
0x180016924  mul     ecx
0x180016926  lea     rcx, [rsi+218h]
0x18001692d  shr     edx, 15h
0x180016930  call    ??0?$CTSmoothingFilter@_J@@QEAA@_JNK@Z; CTSmoothingFilter<__int64>::CTSmoothingFilter<__int64>(__int64,double,ulong)
0x180016935  lea     rcx, [rsi+270h]; this
0x18001693c  mov     rdx, rdi; struct CMpeg2Stats *
0x18001693f  call    ??0CMpeg2Time@@QEAA@PEAVCMpeg2Stats@@K@Z; CMpeg2Time::CMpeg2Time(CMpeg2Stats *,ulong)
0x180016944  mov     [rsi+2C4h], ebx
0x18001694a  lea     r13, [rsi+2C8h]
0x180016951  xor     ebx, ebx
0x180016953  mov     dword ptr [rsi+2C0h], 0FFFFFFFFh
0x18001695d  mov     r8d, 3A3h; int
0x180016963  mov     [r13+0], ebx
0x180016967  lea     rdx, aCmpeg2pushcloc_5; "CMPEG2PushClock::CMPEG2PushClock"
0x18001696e  mov     [rbp+arg_0], ebx
0x180016971  lea     rcx, [rbp+Data]; this
0x180016978  mov     [rbp+arg_8], ebx
0x18001697b  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180016980  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180016987  jb      short loc_1800169A9
0x180016989  mov     rcx, cs:WPP_GLOBAL_Control
0x180016990  lea     edx, [rbx+15h]
0x180016993  mov     r9, rsi
0x180016996  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x18001699d  mov     rcx, [rcx+88h]
0x1800169a4  call    WPP_SF_q
0x1800169a9  mov     rdi, qword ptr [rbp+Type]
0x1800169b0  lea     rcx, [rsi+140h]; lpCriticalSection
0x1800169b7  mov     [rdi], ebx
0x1800169b9  call    cs:__imp_InitializeCriticalSection
0x1800169c0  nop     dword ptr [rax+rax+00h]
0x1800169c5  lea     rcx, [rsi+168h]; lpCriticalSection
0x1800169cc  call    cs:__imp_InitializeCriticalSection
0x1800169d3  nop     dword ptr [rax+rax+00h]
0x1800169d8  xorps   xmm0, xmm0
0x1800169db  movups  xmmword ptr [rsi+130h], xmm0
0x1800169e2  cmp     ebx, 2
0x1800169e5  jnb     short loc_180016A31
0x1800169e7  xor     r9d, r9d; lpName
0x1800169ea  xor     r8d, r8d; bInitialState
0x1800169ed  xor     ecx, ecx; lpEventAttributes
0x1800169ef  lea     edx, [r9+1]; bManualReset
0x1800169f3  call    cs:__imp_CreateEventW
0x1800169fa  nop     dword ptr [rax+rax+00h]
0x1800169ff  mov     ecx, ebx
0x180016a01  mov     [rsi+rcx*8+130h], rax
0x180016a09  test    rax, rax
0x180016a0c  jz      short loc_180016A12
0x180016a0e  inc     ebx
0x180016a10  jmp     short loc_1800169E2
0x180016a12  call    cs:__imp_GetLastError
0x180016a19  nop     dword ptr [rax+rax+00h]
0x180016a1e  test    eax, eax
0x180016a20  jle     short loc_180016A2A
0x180016a22  movzx   eax, ax
0x180016a25  or      eax, 80070000h
0x180016a2a  mov     [rdi], eax
0x180016a2c  jmp     loc_180016BFD
0x180016a31  xor     ebx, ebx
0x180016a33  mov     qword ptr [rsi+198h], 0FFFFFFFFFFFFFFFFh
0x180016a3e  lea     rcx, [rsi+20h]
0x180016a42  mov     [rsi+1A8h], rbx
0x180016a49  call    ?Reset@?$CTClockSubordinate@_J_J@@QEAAXH@Z; CTClockSubordinate<__int64,__int64>::Reset(int)
0x180016a4e  mov     rcx, r15; this
0x180016a51  call    ?GetFreq@CMPEG2PushClock@@UEAA_JXZ; CMPEG2PushClock::GetFreq(void)
0x180016a56  mov     [rsi+1A0h], rax
0x180016a5d  lea     eax, [rbx+32h]
0x180016a60  mov     [rbp+arg_8], eax
0x180016a63  lea     edi, [rbx+4]
0x180016a66  mov     dword ptr [rbp+Data], ebx
0x180016a6c  test    r14, r14
0x180016a6f  jz      short loc_180016AEA
0x180016a71  lea     rax, [rbp+cbData]
0x180016a75  mov     dword ptr [rbp+cbData], edi
0x180016a78  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016a7d  lea     r9, [rbp+Type]; lpType
0x180016a84  lea     rax, [rbp+Data]
0x180016a8b  mov     [rbp+Type], edi
0x180016a91  xor     r8d, r8d; lpReserved
0x180016a94  mov     [rsp+40h+lpData], rax; lpData
0x180016a99  lea     rdx, ValueName; "OverPadMillis"
0x180016aa0  mov     rcx, r14; hKey
0x180016aa3  call    cs:__imp_RegQueryValueExW
0x180016aaa  nop     dword ptr [rax+rax+00h]
0x180016aaf  test    eax, eax
0x180016ab1  jnz     short loc_180016ABE
0x180016ab3  mov     eax, dword ptr [rbp+Data]
0x180016ab9  mov     [rbp+arg_8], eax
0x180016abc  jmp     short loc_180016AEA
0x180016abe  lea     rax, [rbp+arg_8]
0x180016ac2  mov     dword ptr [rsp+40h+lpcbData], edi; cbData
0x180016ac6  mov     r9d, edi; dwType
0x180016ac9  mov     [rsp+40h+lpData], rax; lpData
0x180016ace  xor     r8d, r8d; Reserved
0x180016ad1  lea     rdx, ValueName; "OverPadMillis"
0x180016ad8  mov     rcx, r14; hKey
0x180016adb  call    cs:__imp_RegSetValueExW
0x180016ae2  nop     dword ptr [rax+rax+00h]
0x180016ae7  mov     eax, [rbp+arg_8]
0x180016aea  imul    ecx, eax, 2710h
0x180016af0  mov     eax, 0C8h
0x180016af5  mov     dword ptr [rbp+Data], ebx
0x180016afb  mov     [rbp+arg_0], eax
0x180016afe  mov     [rsi+200h], rcx
0x180016b05  test    r14, r14
0x180016b08  jz      short loc_180016B83
0x180016b0a  lea     rax, [rbp+cbData]
0x180016b0e  mov     dword ptr [rbp+cbData], edi
0x180016b11  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180016b16  lea     r9, [rbp+Type]; lpType
0x180016b1d  lea     rax, [rbp+Data]
0x180016b24  mov     [rbp+Type], edi
0x180016b2a  xor     r8d, r8d; lpReserved
0x180016b2d  mov     [rsp+40h+lpData], rax; lpData
0x180016b32  lea     rdx, aMindownstreamb; "MinDownstreamBufferingMillis"
0x180016b39  mov     rcx, r14; hKey
0x180016b3c  call    cs:__imp_RegQueryValueExW
0x180016b43  nop     dword ptr [rax+rax+00h]
0x180016b48  test    eax, eax
0x180016b4a  jnz     short loc_180016B57
0x180016b4c  mov     eax, dword ptr [rbp+Data]
0x180016b52  mov     [rbp+arg_0], eax
0x180016b55  jmp     short loc_180016B83
0x180016b57  lea     rax, [rbp+arg_0]
0x180016b5b  mov     dword ptr [rsp+40h+lpcbData], edi; cbData
0x180016b5f  mov     r9d, edi; dwType
0x180016b62  mov     [rsp+40h+lpData], rax; lpData
0x180016b67  xor     r8d, r8d; Reserved
0x180016b6a  lea     rdx, aMindownstreamb; "MinDownstreamBufferingMillis"
0x180016b71  mov     rcx, r14; hKey
0x180016b74  call    cs:__imp_RegSetValueExW
0x180016b7b  nop     dword ptr [rax+rax+00h]
0x180016b80  mov     eax, [rbp+arg_0]
0x180016b83  imul    edx, eax, 2710h
0x180016b89  mov     r9d, 1; int
0x180016b8f  mov     r8d, 2710h; unsigned int
0x180016b95  mov     [rsp+40h+lpData], r13; unsigned int *
0x180016b9a  mov     rcx, r14; hKey
0x180016b9d  mov     [rsi+1F0h], rdx
0x180016ba4  lea     rdx, aClocksubordina_2; "ClockSubordinateSettlingMillis"
0x180016bab  call    ?RegGetValIfExist@@YAJPEAUHKEY__@@PEBGKHPEAK@Z; RegGetValIfExist(HKEY__ *,ushort const *,ulong,int,ulong *)
0x180016bb0  mov     rcx, r15; this
0x180016bb3  call    ?SampleClock@CMPEG2PushClock@@UEAA_JXZ; CMPEG2PushClock::SampleClock(void)
0x180016bb8  neg     rax
0x180016bbb  mov     [rsi+1D8h], rax
0x180016bc2  cmp     cs:byte_1800EACCB, 2
0x180016bc9  jb      short loc_180016BF2
0x180016bcb  mov     rcx, cs:WPP_GLOBAL_Control
0x180016bd2  lea     r8, WPP_feb469ac278e3fc9f6d14c8f070275a6_Traceguids
0x180016bd9  mov     edx, 16h
0x180016bde  mov     [rsp+40h+lpData], rax
0x180016be3  mov     r9, rsi
0x180016be6  mov     rcx, [rcx+88h]
0x180016bed  call    WPP_SF_qq
0x180016bf2  mov     rax, [rsi+118h]
0x180016bf9  lock inc dword ptr [rax+20h]
0x180016bfd  lea     rcx, [rbp+Data]; this
0x180016c04  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180016c09  mov     rbx, [rsp+40h+arg_10]
0x180016c11  mov     rax, rsi
0x180016c14  add     rsp, 40h
0x180016c18  pop     r15
0x180016c1a  pop     r14
0x180016c1c  pop     r13
0x180016c1e  pop     r12
0x180016c20  pop     rdi
0x180016c21  pop     rsi
0x180016c22  pop     rbp
0x180016c23  retn
```
