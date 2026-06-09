# InitializeThreadpools(ushort const *)

- ea: `0x1400107ec`
- end: `0x140010bb1`
- name: `?InitializeThreadpools@@YAJPEBG@Z`
- size: `965`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000abe0`

## callees

- `0x14000271f`
- `0x140002aa0`
- `0x140008504`
- `0x140008ea0`
- `0x14000b708`
- `0x14000cbf8`
- `0x1400107ec`
- `0x140015054`
- `0x140015140`
- `0x140015690`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14001082f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x14001082f`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400108dd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010913`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1400108dd`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x140010913`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010877`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140010877`

## string_xrefs

- `0x140010b44`: `onecoreuap\admin\dm\omadm\omadmprc\threadpoolmanager.cpp`

## pseudocode

```c
__int64 __fastcall InitializeThreadpools(const unsigned __int16 *a1)
{
  DWORD v2; // eax
  __int64 v3; // rcx
  bool v4; // zf
  const unsigned __int16 *v5; // r8
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int DWORD; // eax
  __int64 v9; // rdx
  unsigned int v11; // esi
  AutoThreadpool *v12; // rbx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  DWORD v14; // edi
  DWORD v15; // r14d
  AutoThreadpool *v16; // rax
  __int64 v17; // rdx
  void (__fastcall ***v18)(_QWORD, __int64); // rcx
  AutoThreadpool *v19; // rcx
  unsigned int v20; // ebx
  unsigned int v21; // edi
  int v22; // eax
  AutoThreadpool *v23; // rax
  __int64 v24; // rdx
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  AutoThreadpool *v26; // rcx
  AutoThreadpool *v27; // rax
  __int64 v28; // rdx
  void (__fastcall ***v29)(_QWORD, __int64); // rcx
  AutoThreadpool *v30; // rcx
  COmaDmPrcLogger *Logger; // rax
  int v32; // [rsp+20h] [rbp-E0h]
  int v33; // [rsp+20h] [rbp-E0h]
  unsigned int dwNumberOfProcessors; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v35; // [rsp+34h] [rbp-CCh] BYREF
  AutoThreadpool *v36; // [rsp+38h] [rbp-C8h]
  _SYSTEM_INFO SystemInfo; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v38[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.dwNumberOfProcessors >= 4 )
    v2 = SystemInfo.dwNumberOfProcessors >> 2;
  else
    v2 = 1;
  v35 = v2;
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  if ( a1 )
  {
    memset_0(v38, 0, 0x208u);
    v4 = (unsigned __int8)RtlIsStateSeparationEnabled(v3) == 0;
    v5 = L"OSData\\Software\\Microsoft\\Enrollments\\%s\\%s";
    if ( v4 )
      v5 = L"Software\\Microsoft\\Enrollments\\%s\\%s";
    v6 = StringCchPrintfW(v38, 0x104u, v5, a1, c_szEnrollmentsDBMultipleSession);
    if ( (v6 & 0x80000000) != 0 )
    {
      v7 = 1143;
LABEL_15:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)v6,
        v32);
      v9 = 1264;
LABEL_16:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
        (const char *)v6,
        v32);
      return v6;
    }
    DWORD = OmaDmRegistryGetDWORD(HKEY_LOCAL_MACHINE, v38, L"NumAllowedConcurrentUserSessionForBackgroundSync", &v35);
    v6 = DWORD;
    if ( DWORD != -2147024894 && DWORD < 0 )
    {
      v7 = 1150;
      goto LABEL_15;
    }
    v6 = OmaDmRegistryGetDWORD(
           HKEY_LOCAL_MACHINE,
           v38,
           L"NumAllowedConcurrentUserSessionAtUserLogonSync",
           &dwNumberOfProcessors);
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147024894 )
    {
      v7 = 1159;
      goto LABEL_15;
    }
  }
  v11 = 32;
  v36 = (AutoThreadpool *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
  v12 = v36;
  if ( v36 )
  {
    *(_QWORD *)v36 = &ThreadpoolManager::`vftable';
    *((_QWORD *)v12 + 1) = 0;
    *((_QWORD *)v12 + 2) = 0;
    *((_QWORD *)v12 + 3) = 0;
  }
  else
  {
    v12 = 0;
  }
  v13 = (void (__fastcall ***)(_QWORD, __int64))qword_140024308;
  qword_140024308 = (__int64)v12;
  if ( v13 )
  {
    (**v13)(v13, 1);
    v12 = (AutoThreadpool *)qword_140024308;
  }
  if ( !v12 )
  {
    v6 = -2147024882;
    v9 = 1268;
    goto LABEL_16;
  }
  v14 = dwNumberOfProcessors;
  v15 = v35;
  ThreadpoolManager::m_numberOfWorkQueued = 0;
  v16 = (AutoThreadpool *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v36 = v16;
  if ( v16 )
    v16 = AutoThreadpool::AutoThreadpool(v16);
  v18 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v12 + 2);
  *((_QWORD *)v12 + 2) = v16;
  if ( v18 )
    (**v18)(v18, 1);
  v19 = (AutoThreadpool *)*((_QWORD *)v12 + 2);
  if ( !v19 )
  {
    v20 = -2147024882;
    v11 = 28;
    v21 = -2147024882;
LABEL_49:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\threadpoolmanager.cpp",
      (const char *)v20,
      v32);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F5,
      (unsigned int)"onecoreuap\\admin\\dm\\omadm\\omadmprc\\omadmprc.cpp",
      (const char *)v21,
      v33);
    return v21;
  }
  v22 = AutoThreadpool::Initialize(v19, v17, v14);
  v21 = v22;
  if ( v22 < 0 )
  {
    v11 = 29;
LABEL_48:
    v20 = v22;
    goto LABEL_49;
  }
  v23 = (AutoThreadpool *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v36 = v23;
  if ( v23 )
    v23 = AutoThreadpool::AutoThreadpool(v23);
  v25 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v12 + 1);
  *((_QWORD *)v12 + 1) = v23;
  if ( v25 )
    (**v25)(v25, 1);
  v26 = (AutoThreadpool *)*((_QWORD *)v12 + 1);
  if ( !v26 )
  {
    v20 = -2147024882;
    v21 = -2147024882;
    goto LABEL_49;
  }
  v22 = AutoThreadpool::Initialize(v26, v24, v15);
  v21 = v22;
  if ( v22 < 0 )
  {
    v11 = 33;
    goto LABEL_48;
  }
  v27 = (AutoThreadpool *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v36 = v27;
  if ( v27 )
    v27 = AutoThreadpool::AutoThreadpool(v27);
  v29 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v12 + 3);
  *((_QWORD *)v12 + 3) = v27;
  if ( v29 )
    (**v29)(v29, 1);
  v30 = (AutoThreadpool *)*((_QWORD *)v12 + 3);
  if ( !v30 )
  {
    v20 = -2147024882;
    v11 = 36;
    v21 = -2147024882;
    goto LABEL_49;
  }
  v22 = AutoThreadpool::Initialize(v30, v28, 1u);
  v21 = v22;
  if ( v22 < 0 )
  {
    v11 = 37;
    goto LABEL_48;
  }
  Logger = COmaDmPrcLogger::GetLogger();
  COmaDmPrcLogger::LogOmaDmPrcWvdSessionInitialization(
    Logger,
    SystemInfo.dwNumberOfProcessors,
    v35,
    dwNumberOfProcessors);
  return 0;
}

```

## disassembly

```asm
0x1400107ec  push    rbp
0x1400107ee  push    rbx
0x1400107ef  push    rsi
0x1400107f0  push    rdi
0x1400107f1  push    r12
0x1400107f3  push    r14
0x1400107f5  lea     rbp, [rsp-198h]
0x1400107fd  sub     rsp, 298h
0x140010804  mov     rax, cs:__security_cookie
0x14001080b  xor     rax, rsp
0x14001080e  mov     [rbp+1C0h+var_40], rax
0x140010815  xorps   xmm0, xmm0
0x140010818  mov     rbx, rcx
0x14001081b  lea     rcx, [rsp+2C0h+SystemInfo]; lpSystemInfo
0x140010820  movups  xmmword ptr [rsp+2C0h+SystemInfo], xmm0
0x140010825  movups  xmmword ptr [rsp+2C0h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x14001082a  movups  xmmword ptr [rsp+2C0h+SystemInfo.dwNumberOfProcessors], xmm0
0x14001082f  call    cs:__imp_GetSystemInfo
0x140010836  nop     dword ptr [rax+rax+00h]
0x14001083b  mov     ecx, [rsp+2C0h+SystemInfo.dwNumberOfProcessors]
0x14001083f  mov     r12d, 1
0x140010845  cmp     ecx, 4
0x140010848  jnb     short loc_14001084F
0x14001084a  mov     eax, r12d
0x14001084d  jmp     short loc_140010854
0x14001084f  mov     eax, ecx
0x140010851  shr     eax, 2
0x140010854  mov     [rsp+2C0h+var_28C], eax
0x140010858  mov     [rsp+2C0h+var_290], ecx
0x14001085c  test    rbx, rbx
0x14001085f  jz      loc_14001096D
0x140010865  xor     edx, edx; Val
0x140010867  lea     rcx, [rsp+2C0h+var_250]; void *
0x14001086c  mov     r8d, 208h; Size
0x140010872  call    memset_0
0x140010877  call    cs:__imp_RtlIsStateSeparationEnabled
0x14001087e  nop     dword ptr [rax+rax+00h]
0x140010883  lea     rcx, aSoftwareMicros_2; "Software\\Microsoft\\Enrollments\\%s\\%"...
0x14001088a  mov     r9, rbx
0x14001088d  test    al, al
0x14001088f  lea     r8, aOsdataSoftware_0; "OSData\\Software\\Microsoft\\Enrollment"...
0x140010896  lea     rax, ?c_szEnrollmentsDBMultipleSession@@3PAGA; "MultipleSession"
0x14001089d  mov     edx, 104h; unsigned __int64
0x1400108a2  cmovz   r8, rcx; unsigned __int16 *
0x1400108a6  mov     qword ptr [rsp+2C0h+var_2A0], rax; int
0x1400108ab  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x1400108b0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400108b5  mov     ebx, eax
0x1400108b7  test    eax, eax
0x1400108b9  jns     short loc_1400108C2
0x1400108bb  mov     edx, 477h
0x1400108c0  jmp     short loc_140010935
0x1400108c2  mov     rsi, 0FFFFFFFF80000002h
0x1400108c9  lea     r9, [rsp+2C0h+var_28C]
0x1400108ce  mov     rcx, rsi
0x1400108d1  lea     r8, aNumallowedconc_0; "NumAllowedConcurrentUserSessionForBackg"...
0x1400108d8  lea     rdx, [rsp+2C0h+var_250]
0x1400108dd  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1400108e4  nop     dword ptr [rax+rax+00h]
0x1400108e9  mov     edi, 80070002h
0x1400108ee  mov     ebx, eax
0x1400108f0  cmp     eax, edi
0x1400108f2  jz      short loc_1400108FF
0x1400108f4  test    eax, eax
0x1400108f6  jns     short loc_1400108FF
0x1400108f8  mov     edx, 47Eh
0x1400108fd  jmp     short loc_140010935
0x1400108ff  lea     r9, [rsp+2C0h+var_290]
0x140010904  mov     rcx, rsi
0x140010907  lea     r8, aNumallowedconc; "NumAllowedConcurrentUserSessionAtUserLo"...
0x14001090e  lea     rdx, [rsp+2C0h+var_250]
0x140010913  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x14001091a  nop     dword ptr [rax+rax+00h]
0x14001091f  mov     ecx, 80000000h
0x140010924  mov     ebx, eax
0x140010926  add     eax, ecx
0x140010928  test    ecx, eax
0x14001092a  jnz     short loc_14001096D
0x14001092c  cmp     ebx, edi
0x14001092e  jz      short loc_14001096D
0x140010930  mov     edx, 487h; void *
0x140010935  mov     rcx, [rbp+1C8h]; this
0x14001093c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140010943  mov     r9d, ebx; char *
0x140010946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001094b  mov     edx, 4F0h; void *
0x140010950  mov     rcx, [rbp+1C8h]; this
0x140010957  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x14001095e  mov     r9d, ebx; char *
0x140010961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010966  mov     eax, ebx
0x140010968  jmp     loc_140010B91
0x14001096d  mov     esi, 20h ; ' '
0x140010972  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010979  mov     ecx, esi; unsigned __int64
0x14001097b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140010980  mov     [rsp+2C0h+var_288], rax
0x140010985  mov     rbx, rax
0x140010988  test    rax, rax
0x14001098b  jz      short loc_1400109B1
0x14001098d  lea     rax, ??_7ThreadpoolManager@@6B@; const ThreadpoolManager::`vftable'
0x140010994  mov     [rbx], rax
0x140010997  mov     qword ptr [rbx+8], 0
0x14001099f  mov     qword ptr [rbx+10h], 0
0x1400109a7  mov     qword ptr [rbx+18h], 0
0x1400109af  jmp     short loc_1400109B3
0x1400109b1  xor     ebx, ebx
0x1400109b3  mov     rcx, cs:qword_140024308
0x1400109ba  mov     cs:qword_140024308, rbx
0x1400109c1  test    rcx, rcx
0x1400109c4  jz      short loc_1400109DB
0x1400109c6  mov     rax, [rcx]
0x1400109c9  mov     edx, r12d
0x1400109cc  mov     rax, [rax]
0x1400109cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400109d4  mov     rbx, cs:qword_140024308
0x1400109db  test    rbx, rbx
0x1400109de  jnz     short loc_1400109EF
0x1400109e0  mov     ebx, 8007000Eh
0x1400109e5  mov     edx, 4F4h
0x1400109ea  jmp     loc_140010950
0x1400109ef  mov     edi, [rsp+2C0h+var_290]
0x1400109f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400109fa  mov     r14d, [rsp+2C0h+var_28C]
0x1400109ff  mov     ecx, 0B0h; unsigned __int64
0x140010a04  mov     cs:?m_numberOfWorkQueued@ThreadpoolManager@@0JC, 0; long volatile ThreadpoolManager::m_numberOfWorkQueued
0x140010a0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140010a13  mov     [rsp+2C0h+var_288], rax
0x140010a18  test    rax, rax
0x140010a1b  jz      short loc_140010A25
0x140010a1d  mov     rcx, rax; this
0x140010a20  call    ??0AutoThreadpool@@QEAA@XZ; AutoThreadpool::AutoThreadpool(void)
0x140010a25  mov     rcx, [rbx+10h]
0x140010a29  mov     [rbx+10h], rax
0x140010a2d  test    rcx, rcx
0x140010a30  jz      short loc_140010A40
0x140010a32  mov     rax, [rcx]
0x140010a35  mov     edx, r12d
0x140010a38  mov     rax, [rax]
0x140010a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010a40  mov     rcx, [rbx+10h]; this
0x140010a44  test    rcx, rcx
0x140010a47  jnz     short loc_140010A58
0x140010a49  mov     ebx, 8007000Eh
0x140010a4e  lea     esi, [rcx+1Ch]
0x140010a51  mov     edi, ebx
0x140010a53  jmp     loc_140010B3D
0x140010a58  mov     r8d, edi; unsigned int
0x140010a5b  call    ?Initialize@AutoThreadpool@@QEAAJKK@Z; AutoThreadpool::Initialize(ulong,ulong)
0x140010a60  mov     edi, eax
0x140010a62  test    eax, eax
0x140010a64  jns     short loc_140010A70
0x140010a66  mov     esi, 1Dh
0x140010a6b  jmp     loc_140010B3B
0x140010a70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010a77  mov     ecx, 0B0h; unsigned __int64
0x140010a7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140010a81  mov     [rsp+2C0h+var_288], rax
0x140010a86  test    rax, rax
0x140010a89  jz      short loc_140010A93
0x140010a8b  mov     rcx, rax; this
0x140010a8e  call    ??0AutoThreadpool@@QEAA@XZ; AutoThreadpool::AutoThreadpool(void)
0x140010a93  mov     rcx, [rbx+8]
0x140010a97  mov     [rbx+8], rax
0x140010a9b  test    rcx, rcx
0x140010a9e  jz      short loc_140010AAE
0x140010aa0  mov     rax, [rcx]
0x140010aa3  mov     edx, r12d
0x140010aa6  mov     rax, [rax]
0x140010aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010aae  mov     rcx, [rbx+8]; this
0x140010ab2  test    rcx, rcx
0x140010ab5  jnz     short loc_140010AC0
0x140010ab7  mov     ebx, 8007000Eh
0x140010abc  mov     edi, ebx
0x140010abe  jmp     short loc_140010B3D
0x140010ac0  mov     r8d, r14d; unsigned int
0x140010ac3  call    ?Initialize@AutoThreadpool@@QEAAJKK@Z; AutoThreadpool::Initialize(ulong,ulong)
0x140010ac8  mov     edi, eax
0x140010aca  test    eax, eax
0x140010acc  jns     short loc_140010AD5
0x140010ace  mov     esi, 21h ; '!'
0x140010ad3  jmp     short loc_140010B3B
0x140010ad5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010adc  mov     ecx, 0B0h; unsigned __int64
0x140010ae1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140010ae6  mov     [rsp+2C0h+var_288], rax
0x140010aeb  test    rax, rax
0x140010aee  jz      short loc_140010AF8
0x140010af0  mov     rcx, rax; this
0x140010af3  call    ??0AutoThreadpool@@QEAA@XZ; AutoThreadpool::AutoThreadpool(void)
0x140010af8  mov     rcx, [rbx+18h]
0x140010afc  mov     [rbx+18h], rax
0x140010b00  test    rcx, rcx
0x140010b03  jz      short loc_140010B13
0x140010b05  mov     rax, [rcx]
0x140010b08  mov     edx, r12d
0x140010b0b  mov     rax, [rax]
0x140010b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010b13  mov     rcx, [rbx+18h]; this
0x140010b17  test    rcx, rcx
0x140010b1a  jnz     short loc_140010B28
0x140010b1c  mov     ebx, 8007000Eh
0x140010b21  lea     esi, [rcx+24h]
0x140010b24  mov     edi, ebx
0x140010b26  jmp     short loc_140010B3D
0x140010b28  mov     r8d, r12d; unsigned int
0x140010b2b  call    ?Initialize@AutoThreadpool@@QEAAJKK@Z; AutoThreadpool::Initialize(ulong,ulong)
0x140010b30  mov     edi, eax
0x140010b32  test    eax, eax
0x140010b34  jns     short loc_140010B74
0x140010b36  mov     esi, 25h ; '%'
0x140010b3b  mov     ebx, eax
0x140010b3d  mov     rcx, [rbp+1C8h]; this
0x140010b44  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140010b4b  mov     r9d, ebx; char *
0x140010b4e  mov     edx, esi; void *
0x140010b50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010b55  mov     rcx, [rbp+1C8h]; this
0x140010b5c  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\omadm\\omadmprc"...
0x140010b63  mov     r9d, edi; char *
0x140010b66  mov     edx, 4F5h; void *
0x140010b6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010b70  mov     eax, edi
0x140010b72  jmp     short loc_140010B91
0x140010b74  call    ?GetLogger@COmaDmPrcLogger@@SAPEAV1@XZ; COmaDmPrcLogger::GetLogger(void)
0x140010b79  mov     r9d, [rsp+2C0h+var_290]; unsigned int
0x140010b7e  mov     rcx, rax; this
0x140010b81  mov     r8d, [rsp+2C0h+var_28C]; unsigned int
0x140010b86  mov     edx, [rsp+2C0h+SystemInfo.dwNumberOfProcessors]; unsigned int
0x140010b8a  call    ?LogOmaDmPrcWvdSessionInitialization@COmaDmPrcLogger@@QEAAXKKK@Z; COmaDmPrcLogger::LogOmaDmPrcWvdSessionInitialization(ulong,ulong,ulong)
0x140010b8f  xor     eax, eax
0x140010b91  mov     rcx, [rbp+1C0h+var_40]
0x140010b98  xor     rcx, rsp; StackCookie
0x140010b9b  call    __security_check_cookie
0x140010ba0  add     rsp, 298h
0x140010ba7  pop     r14
0x140010ba9  pop     r12
0x140010bab  pop     rdi
0x140010bac  pop     rsi
0x140010bad  pop     rbx
0x140010bae  pop     rbp
0x140010baf  retn
```
