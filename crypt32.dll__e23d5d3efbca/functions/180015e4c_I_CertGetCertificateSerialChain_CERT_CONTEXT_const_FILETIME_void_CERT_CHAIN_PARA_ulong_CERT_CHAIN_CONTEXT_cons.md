# I_CertGetCertificateSerialChain(_CERT_CONTEXT const *,_FILETIME *,void *,_CERT_CHAIN_PARA *,ulong,_CERT_CHAIN_CONTEXT const * *)

- ea: `0x180015e4c`
- end: `0x1800161c7`
- name: `?I_CertGetCertificateSerialChain@@YAHPEBU_CERT_CONTEXT@@PEAU_FILETIME@@PEAXPEAU_CERT_CHAIN_PARA@@KPEAPEBU_CERT_CHAIN_CONTEXT@@@Z`
- size: `891`
- prototype: `__int64 __usercall@<rax>(PCCERT_CONTEXT pCertContext@<rcx>, FILETIME *lpFileTime1@<rdx>, void *@<r8>, struct _CERT_CHAIN_PARA *@<r9>, unsigned int, const struct _CERT_CHAIN_CONTEXT **)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001aec0`

## callees

- `0x1800126d0`
- `0x180014074`
- `0x180015554`
- `0x180015e4c`
- `0x1800161d0`
- `0x180016228`
- `0x18001641c`
- `0x180016444`
- `0x18001663c`
- `0x1800168a4`
- `0x18001768c`
- `0x1800178dc`
- `0x18001b5a0`
- `0x180028d60`
- `0x1800566c4`
- `0x18009bfe0`
- `0x1800bf63c`
- `0x1801150d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115ab4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180115ab4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015eaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180015eaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015ea9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180015ea9`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015eee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f20`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f35`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016116`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016139`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001615f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016174`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a81`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a94`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015eee`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f20`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180015f35`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016116`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016139`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001615f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180016174`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a63`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a81`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180115a94`

## string_xrefs

- `0x1800160d9`: `CacheEntry`

## pseudocode

```c
_BOOL8 __fastcall I_CertGetCertificateSerialChain(
        PCCERT_CONTEXT pCertContext,
        FILETIME *lpFileTime1,
        void *a3,
        struct _CERT_CHAIN_PARA *a4,
        unsigned int a5,
        const struct _CERT_CHAIN_CONTEXT **a6)
{
  __int64 v6; // rsi
  const CERT_CONTEXT *v8; // r14
  struct _CERT_SERIAL_CHAIN_ENGINE *Engine; // r12
  void *Property; // rax
  const FILETIME *v12; // r13
  struct _FILETIME *p_SystemTimeAsFileTime; // rbx
  int v14; // edi
  const wchar_t *v15; // rbx
  HLOCAL v16; // rbx
  __int64 CacheEntry; // rax
  __int64 v18; // rax
  int v19; // r14d
  struct _FILETIME v20; // rax
  size_t cbSize; // r8
  __int64 OfflineListHead; // r15
  __int64 v24; // rdx
  int TimeValidDisallowedAutoUpdateCtl; // ebx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 started; // rdi
  int updated; // ebx
  __int64 v30; // rax
  bool v31; // cc
  FILETIME v32; // rax
  const FILETIME *v33; // rbx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp-79h] BYREF
  ULONGLONG TickCount64; // [rsp+50h] [rbp-71h]
  __int64 v36; // [rsp+58h] [rbp-69h]
  HLOCAL hMem; // [rsp+60h] [rbp-61h]
  FILETIME v38; // [rsp+68h] [rbp-59h] BYREF
  int v39; // [rsp+78h] [rbp-49h] BYREF
  __int64 v40; // [rsp+7Ch] [rbp-45h] BYREF
  int v42; // [rsp+128h] [rbp+67h]
  FILETIME FileTime2; // [rsp+130h] [rbp+6Fh] BYREF

  v42 = (int)a3;
  v6 = 0;
  v8 = pCertContext;
  v36 = 0;
  SystemTimeAsFileTime = 0;
  Engine = 0;
  memset_0(&v40, 0, 0x5Cu);
  if ( a4 )
  {
    if ( a4->cbSize >= 0x60 )
      cbSize = 96;
    else
      cbSize = a4->cbSize;
    memcpy_0(&v39, a4, cbSize);
  }
  v39 = 96;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  TickCount64 = GetTickCount64();
  Property = (void *)SerialChainGetProperty(v8);
  hMem = Property;
  if ( !Property )
  {
    v15 = L"GetProperty";
    goto LABEL_28;
  }
  v12 = *(const FILETIME **)Property;
  FileTime2 = (FILETIME)(*(_QWORD *)(*(_QWORD *)Property + 80LL) + 36000000000LL);
  if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) > 0 )
    SerialChainLogEvent(v8, L"StaleSerialChain");
  p_SystemTimeAsFileTime = &SystemTimeAsFileTime;
  FileTime2.dwLowDateTime = v12[8].dwHighDateTime;
  if ( lpFileTime1 )
    p_SystemTimeAsFileTime = lpFileTime1;
  if ( CompareFileTime(p_SystemTimeAsFileTime, v12 + 5) >= 0 && CompareFileTime(p_SystemTimeAsFileTime, v12 + 6) <= 0 )
  {
    v14 = 0;
    goto LABEL_10;
  }
  if ( lpFileTime1 )
  {
    if ( CompareFileTime(&SystemTimeAsFileTime, lpFileTime1) < 0 )
      goto LABEL_49;
    v38 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime - 1200000000LL);
    if ( CompareFileTime(lpFileTime1, &v38) < 0 )
      goto LABEL_49;
  }
  if ( !v12[11].dwLowDateTime && !v12[11].dwHighDateTime )
  {
    if ( (FileTime2.dwLowDateTime & 1) != 0 )
    {
      v14 = 0x2000000;
      goto LABEL_10;
    }
LABEL_49:
    v15 = L"TimeInvalid";
    SetLastError(0x800B0101);
    goto LABEL_28;
  }
  if ( CompareFileTime(&SystemTimeAsFileTime, v12 + 11) >= 0 && CompareFileTime(&SystemTimeAsFileTime, v12 + 12) <= 0 )
    goto LABEL_49;
  v31 = CompareFileTime(v12 + 11, v12 + 5) <= 0;
  v32 = (FILETIME)&v12[5];
  if ( !v31 )
    v32 = (FILETIME)&v12[11];
  v33 = v12 + 6;
  FileTime2 = v32;
  if ( CompareFileTime(v12 + 12, v12 + 6) < 0 )
    v33 = v12 + 12;
  if ( CompareFileTime(v33, *(const FILETIME **)&FileTime2) < 0 )
    goto LABEL_49;
  v14 = 0x1000000;
LABEL_10:
  v15 = L"GetFailed";
  Engine = (struct _CERT_SERIAL_CHAIN_ENGINE *)SerialChainGetEngine();
  if ( !Engine )
    goto LABEL_28;
  v16 = hMem;
  CacheEntry = SerialChainGetCacheEntry((_DWORD)Engine, (_DWORD)hMem, (_DWORD)v8, v42, TickCount64);
  v36 = CacheEntry;
  if ( !CacheEntry )
  {
    v15 = L"CacheEntry";
    goto LABEL_28;
  }
  v18 = UnserializeCertificateChain(v16, v8, *(_QWORD *)(CacheEntry + 56), *(unsigned int *)(CacheEntry + 52));
  v6 = v18;
  if ( !v18 )
  {
    v15 = L"InvalidData";
    goto LABEL_28;
  }
  v19 = a5;
  *(_DWORD *)(v18 + 48) = a5;
  if ( lpFileTime1 )
    v20 = *lpFileTime1;
  else
    v20 = SystemTimeAsFileTime;
  *(struct _FILETIME *)(v6 + 112) = v20;
  if ( v14 )
  {
    v30 = *(_QWORD *)(v6 + 16);
    *(_DWORD *)(v6 + 8) |= v14;
    *(_DWORD *)(*(_QWORD *)v30 + 8LL) |= v14;
  }
  if ( (v19 & 0x70000000) != 0 )
  {
    OfflineListHead = 0;
    TimeValidDisallowedAutoUpdateCtl = SerialChainGetTimeValidDisallowedAutoUpdateCtl(
                                         (int)Engine,
                                         (int)v12,
                                         (int)pCertContext,
                                         (int)&v39,
                                         v19,
                                         &SystemTimeAsFileTime);
    if ( v19 >= 0 )
      OfflineListHead = CertDiagTraceCreateOfflineListHead();
    started = CertDiagTraceStartOfflineList(OfflineListHead, v24, v26, v27);
    updated = SerialChainUpdateRevocationStatus(
                (int)Engine,
                v6,
                (int)v12,
                v42,
                (__int64)&v39,
                v19,
                &SystemTimeAsFileTime,
                TimeValidDisallowedAutoUpdateCtl);
    I_CryptSetTls(g_hTlsOfflineList, started);
    *(_QWORD *)(v6 + 104) = OfflineListHead;
    if ( updated )
    {
      SerialChainTriggerPreFetch(Engine, (unsigned int)v19, TickCount64, &SystemTimeAsFileTime);
      goto LABEL_18;
    }
    v15 = L"RevocationError";
    SerialChainFreeInternalChainContext((HLOCAL)v6);
    v8 = pCertContext;
    v6 = 0;
LABEL_28:
    SerialChainLogEvent(v8, v15);
  }
LABEL_18:
  SerialChainReleaseCacheEntry(v36);
  _SerialChainReleaseEngine(Engine);
  PkiDefaultCryptFree(hMem);
  *a6 = (const struct _CERT_CHAIN_CONTEXT *)v6;
  return v6 != 0;
}

```

## disassembly

```asm
0x180015e4c  mov     rax, rsp
0x180015e4f  mov     [rax+10h], rbx
0x180015e53  mov     [rax+18h], r8
0x180015e57  mov     [rax+8], rcx
0x180015e5b  push    rbp
0x180015e5c  push    rsi
0x180015e5d  push    rdi
0x180015e5e  push    r12
0x180015e60  push    r13
0x180015e62  push    r14
0x180015e64  push    r15
0x180015e66  lea     rbp, [rax-4Fh]
0x180015e6a  sub     rsp, 0D0h
0x180015e71  xor     esi, esi
0x180015e73  mov     r15, rdx
0x180015e76  mov     r14, rcx
0x180015e79  mov     [rbp+47h+var_B0], rsi
0x180015e7d  xor     edx, edx; Val
0x180015e7f  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180015e83  lea     rcx, [rbp+47h+var_90+4]; void *
0x180015e87  mov     rbx, r9
0x180015e8a  lea     r8d, [rsi+5Ch]; Size
0x180015e8e  xor     r12d, r12d
0x180015e91  call    memset_0
0x180015e96  lea     edi, [rsi+60h]
0x180015e99  test    rbx, rbx
0x180015e9c  jnz     loc_180016015
0x180015ea2  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180015ea6  mov     dword ptr [rbp+47h+var_90], edi
0x180015ea9  call    cs:__imp_GetSystemTimeAsFileTime
0x180015eaf  call    cs:__imp_GetTickCount64
0x180015eb5  mov     rcx, r14; pCertContext
0x180015eb8  mov     [rbp+47h+var_B8], rax
0x180015ebc  call    _SerialChainGetProperty
0x180015ec1  mov     [rbp+47h+hMem], rax
0x180015ec5  test    rax, rax
0x180015ec8  jz      loc_1800160F0
0x180015ece  mov     r13, [rax]
0x180015ed1  lea     rdx, [rbp+47h+FileTime2]; lpFileTime2
0x180015ed5  mov     rcx, 861C46800h
0x180015edf  mov     rax, [r13+50h]
0x180015ee3  add     rax, rcx
0x180015ee6  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x180015eea  mov     qword ptr [rbp+47h+FileTime2.dwLowDateTime], rax
0x180015eee  call    cs:__imp_CompareFileTime
0x180015ef4  test    eax, eax
0x180015ef6  jle     short loc_180015F07
0x180015ef8  lea     rdx, aStaleserialcha; "StaleSerialChain"
0x180015eff  mov     rcx, r14
0x180015f02  call    _SerialChainLogEvent
0x180015f07  mov     eax, [r13+44h]
0x180015f0b  lea     rbx, [rbp+47h+SystemTimeAsFileTime]
0x180015f0f  test    r15, r15
0x180015f12  mov     [rbp+47h+FileTime2.dwLowDateTime], eax
0x180015f15  lea     rdx, [r13+28h]; lpFileTime2
0x180015f19  cmovnz  rbx, r15
0x180015f1d  mov     rcx, rbx; lpFileTime1
0x180015f20  call    cs:__imp_CompareFileTime
0x180015f26  test    eax, eax
0x180015f28  js      loc_18001610A
0x180015f2e  lea     rdx, [r13+30h]; lpFileTime2
0x180015f32  mov     rcx, rbx; lpFileTime1
0x180015f35  call    cs:__imp_CompareFileTime
0x180015f3b  test    eax, eax
0x180015f3d  jg      loc_18001610A
0x180015f43  xor     edi, edi
0x180015f45  lea     rbx, aGetfailed; "GetFailed"
0x180015f4c  call    _SerialChainGetEngine
0x180015f51  mov     r12, rax
0x180015f54  test    rax, rax
0x180015f57  jz      loc_1800160E0
0x180015f5d  mov     rax, [rbp+47h+var_B8]
0x180015f61  mov     r8, r14
0x180015f64  mov     rbx, [rbp+47h+hMem]
0x180015f68  mov     rcx, r12
0x180015f6b  mov     r9, qword ptr [rbp+47h+arg_10]
0x180015f6f  mov     rdx, rbx
0x180015f72  mov     [rsp+100h+var_E0], rax
0x180015f77  call    _SerialChainGetCacheEntry
0x180015f7c  mov     [rbp+47h+var_B0], rax
0x180015f80  test    rax, rax
0x180015f83  jz      loc_1800160D9
0x180015f89  mov     r9d, [rax+34h]
0x180015f8d  mov     rdx, r14
0x180015f90  mov     r8, [rax+38h]
0x180015f94  mov     rcx, rbx
0x180015f97  call    _UnserializeCertificateChain
0x180015f9c  mov     rsi, rax
0x180015f9f  test    rax, rax
0x180015fa2  jz      loc_180016101
0x180015fa8  mov     r14d, [rbp+47h+arg_20]
0x180015fac  mov     [rax+30h], r14d
0x180015fb0  test    r15, r15
0x180015fb3  jz      loc_1800160D0
0x180015fb9  mov     rax, [r15]
0x180015fbc  mov     [rsi+70h], rax
0x180015fc0  test    edi, edi
0x180015fc2  jnz     loc_1800161B5
0x180015fc8  test    r14d, 70000000h
0x180015fcf  jnz     short loc_180016031
0x180015fd1  mov     rcx, [rbp+47h+var_B0]
0x180015fd5  call    _SerialChainReleaseCacheEntry
0x180015fda  mov     rcx, r12; struct _CERT_SERIAL_CHAIN_ENGINE *
0x180015fdd  call    ?_SerialChainReleaseEngine@@YAXPEAU_CERT_SERIAL_CHAIN_ENGINE@@@Z; _SerialChainReleaseEngine(_CERT_SERIAL_CHAIN_ENGINE *)
0x180015fe2  mov     rcx, [rbp+47h+hMem]; hMem
0x180015fe6  call    PkiDefaultCryptFree
0x180015feb  mov     rax, [rbp+47h+arg_28]
0x180015fef  mov     rbx, [rsp+100h+arg_8]
0x180015ff7  mov     [rax], rsi
0x180015ffa  xor     eax, eax
0x180015ffc  test    rsi, rsi
0x180015fff  setnz   al
0x180016002  add     rsp, 0D0h
0x180016009  pop     r15
0x18001600b  pop     r14
0x18001600d  pop     r13
0x18001600f  pop     r12
0x180016011  pop     rdi
0x180016012  pop     rsi
0x180016013  pop     rbp
0x180016014  retn
0x180016015  cmp     [rbx], edi
0x180016017  jnb     loc_1800160F9
0x18001601d  mov     r8d, [rbx]; Size
0x180016020  mov     rdx, rbx; Src
0x180016023  lea     rcx, [rbp+47h+var_90]; void *
0x180016027  call    memcpy_0
0x18001602c  jmp     loc_180015EA2
0x180016031  mov     r8, qword ptr [rbp+47h+arg_0]; int
0x180016035  lea     rax, [rbp+47h+SystemTimeAsFileTime]
0x180016039  mov     [rsp+100h+lpFileTime2], rax; lpFileTime2
0x18001603e  lea     r9, [rbp+47h+var_90]; int
0x180016042  mov     rdx, r13; int
0x180016045  mov     dword ptr [rsp+100h+var_E0], r14d; int
0x18001604a  mov     rcx, r12; int
0x18001604d  xor     r15d, r15d
0x180016050  call    _SerialChainGetTimeValidDisallowedAutoUpdateCtl
0x180016055  mov     ebx, eax
0x180016057  test    r14d, r14d
0x18001605a  js      short loc_180016064
0x18001605c  call    CertDiagTraceCreateOfflineListHead
0x180016061  mov     r15, rax
0x180016064  mov     rcx, r15
0x180016067  call    CertDiagTraceStartOfflineList
0x18001606c  mov     r9, qword ptr [rbp+47h+arg_10]; int
0x180016070  mov     rdi, rax
0x180016073  mov     [rsp+38h], ebx; int
0x180016077  lea     rax, [rbp+47h+SystemTimeAsFileTime]
0x18001607b  mov     [rsp+100h+var_D0], rax; FILETIME *
0x180016080  mov     r8, r13; int
0x180016083  lea     rax, [rbp+47h+var_90]
0x180016087  mov     dword ptr [rsp+100h+lpFileTime2], r14d; int
0x18001608c  mov     rdx, rsi; int
0x18001608f  mov     [rsp+100h+var_E0], rax; __int64
0x180016094  mov     rcx, r12; int
0x180016097  call    _SerialChainUpdateRevocationStatus
0x18001609c  mov     ecx, cs:?g_hTlsOfflineList@@3KA; ulong g_hTlsOfflineList
0x1800160a2  mov     rdx, rdi
0x1800160a5  mov     ebx, eax
0x1800160a7  call    I_CryptSetTls
0x1800160ac  mov     [rsi+68h], r15
0x1800160b0  test    ebx, ebx
0x1800160b2  jz      loc_180016187
0x1800160b8  mov     r8, [rbp+47h+var_B8]
0x1800160bc  lea     r9, [rbp+47h+SystemTimeAsFileTime]
0x1800160c0  mov     edx, r14d
0x1800160c3  mov     rcx, r12
0x1800160c6  call    _SerialChainTriggerPreFetch
0x1800160cb  jmp     loc_180015FD1
0x1800160d0  mov     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x1800160d4  jmp     loc_180015FBC
0x1800160d9  lea     rbx, aCacheentry; "CacheEntry"
0x1800160e0  mov     rdx, rbx
0x1800160e3  mov     rcx, r14
0x1800160e6  call    _SerialChainLogEvent
0x1800160eb  jmp     loc_180015FD1
0x1800160f0  lea     rbx, aGetproperty; "GetProperty"
0x1800160f7  jmp     short loc_1800160E0
0x1800160f9  mov     r8, rdi
0x1800160fc  jmp     loc_180016020
0x180016101  lea     rbx, aInvaliddata; "InvalidData"
0x180016108  jmp     short loc_1800160E0
0x18001610a  test    r15, r15
0x18001610d  jz      short loc_180016147
0x18001610f  mov     rdx, r15; lpFileTime2
0x180016112  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x180016116  call    cs:__imp_CompareFileTime
0x18001611c  test    eax, eax
0x18001611e  js      loc_180115AA8
0x180016124  mov     rax, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x180016128  lea     rdx, [rbp+47h+var_A0]; lpFileTime2
0x18001612c  add     rax, 0FFFFFFFFB8797400h
0x180016132  mov     rcx, r15; lpFileTime1
0x180016135  mov     qword ptr [rbp+47h+var_A0.dwLowDateTime], rax
0x180016139  call    cs:__imp_CompareFileTime
0x18001613f  test    eax, eax
0x180016141  js      loc_180115AA8
0x180016147  lea     rbx, [r13+58h]
0x18001614b  cmp     [rbx], esi
0x18001614d  jnz     short loc_180016154
0x18001614f  cmp     [rbx+4], esi
0x180016152  jz      short loc_1800161A1
0x180016154  mov     rdx, rbx; lpFileTime2
0x180016157  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x18001615b  lea     rdi, [r13+60h]
0x18001615f  call    cs:__imp_CompareFileTime
0x180016165  test    eax, eax
0x180016167  js      loc_180115A5C
0x18001616d  mov     rdx, rdi; lpFileTime2
0x180016170  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpFileTime1
0x180016174  call    cs:__imp_CompareFileTime
0x18001617a  test    eax, eax
0x18001617c  jg      loc_180115A5C
0x180016182  jmp     loc_180115AA8
0x180016187  mov     rcx, rsi; hMem
0x18001618a  lea     rbx, aRevocationerro; "RevocationError"
0x180016191  call    ?SerialChainFreeInternalChainContext@@YAXPEAU_INTERNAL_CERT_CHAIN_CONTEXT@@@Z; SerialChainFreeInternalChainContext(_INTERNAL_CERT_CHAIN_CONTEXT *)
0x180016196  mov     r14, qword ptr [rbp+47h+arg_0]
0x18001619a  xor     esi, esi
0x18001619c  jmp     loc_1800160E0
0x1800161a1  test    byte ptr [rbp+47h+FileTime2.dwLowDateTime], 1
0x1800161a5  jz      loc_180115AA8
0x1800161ab  mov     edi, 2000000h
0x1800161b0  jmp     loc_180015F45
0x1800161b5  mov     rax, [rsi+10h]
0x1800161b9  or      [rsi+8], edi
0x1800161bc  mov     rcx, [rax]
0x1800161bf  or      [rcx+8], edi
0x1800161c2  jmp     loc_180015FC8
0x180115a5c  lea     rdx, [r13+28h]; lpFileTime2
0x180115a60  mov     rcx, rbx; lpFileTime1
0x180115a63  call    cs:__imp_CompareFileTime
0x180115a69  test    eax, eax
0x180115a6b  mov     rcx, rdi; lpFileTime1
0x180115a6e  lea     rax, [r13+28h]
0x180115a72  cmovg   rax, rbx
0x180115a76  lea     rbx, [r13+30h]
0x180115a7a  mov     rdx, rbx; lpFileTime2
0x180115a7d  mov     qword ptr [rbp+47h+FileTime2.dwLowDateTime], rax
0x180115a81  call    cs:__imp_CompareFileTime
0x180115a87  mov     rdx, qword ptr [rbp+47h+FileTime2.dwLowDateTime]; lpFileTime2
0x180115a8b  test    eax, eax
0x180115a8d  cmovs   rbx, rdi
0x180115a91  mov     rcx, rbx; lpFileTime1
0x180115a94  call    cs:__imp_CompareFileTime
0x180115a9a  test    eax, eax
0x180115a9c  js      short loc_180115AA8
0x180115a9e  mov     edi, 1000000h
0x180115aa3  jmp     loc_180015F45
0x180115aa8  lea     rbx, aTimeinvalid; "TimeInvalid"
0x180115aaf  mov     ecx, 800B0101h; dwErrCode
0x180115ab4  call    cs:__imp_SetLastError
0x180115aba  nop
0x180115abb  jmp     loc_1800160E0
```
