# EtwpGenerateLogHeaderForRealtime(_EVENT_TRACE_PROPERTIES *,ulong,_TRACE_LOGFILE_HEADER *)

- ea: `0x18000f098`
- end: `0x18000f37e`
- name: `?EtwpGenerateLogHeaderForRealtime@@YAKPEAU_EVENT_TRACE_PROPERTIES@@KPEAU_TRACE_LOGFILE_HEADER@@@Z`
- size: `742`
- prototype: `unsigned int __fastcall(struct _EVENT_TRACE_PROPERTIES *, unsigned int, struct _TRACE_LOGFILE_HEADER *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006c60`
- `0x180007060`
- `0x180007500`

## callees

- `0x180001560`
- `0x180001eb2`
- `0x18000f098`

## import_xrefs

- `ntdll!NtQuerySystemInformation` at `0x18000f0fd`
- `ntdll!NtQuerySystemInformation` at `0x18000f113`
- `ntdll!NtQuerySystemInformation` at `0x18000f0fd`
- `ntdll!NtQuerySystemInformation` at `0x18000f113`
- `ntdll!RtlQueryTimeZoneInformation` at `0x18000f1d0`
- `ntdll!RtlQueryTimeZoneInformation` at `0x18000f1d0`
- `ntdll!EtwpGetCpuSpeed` at `0x18000f11e`
- `ntdll!EtwpGetCpuSpeed` at `0x18000f11e`
- `ntdll!RtlQueryPerformanceFrequency` at `0x18000f322`
- `ntdll!RtlQueryPerformanceFrequency` at `0x18000f322`

## pseudocode

```c
__int64 __fastcall EtwpGenerateLogHeaderForRealtime(
        struct _EVENT_TRACE_PROPERTIES *a1,
        ULONG a2,
        struct _TRACE_LOGFILE_HEADER *a3)
{
  struct _PEB *v6; // rcx
  ULONG v7; // ecx
  ULONG LogFileMode; // eax
  UCHAR v9; // al
  UCHAR v10; // cl
  __m128i v11; // xmm2
  __m128i v12; // xmm3
  __int128 v13; // xmm1
  __int128 v14; // xmm0
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __m128i v19; // xmm1
  __m128i v20; // xmm0
  __int64 result; // rax
  ULONG v22; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v23[7]; // [rsp+28h] [rbp-D8h] BYREF
  _RTL_TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE SystemInformation[4]; // [rsp+110h] [rbp+10h] BYREF
  ULONG v26; // [rsp+114h] [rbp+14h]

  v22 = 0;
  memset_0(SystemInformation, 0, 0x40u);
  memset(v23, 0, 48);
  NtQuerySystemInformation(SystemBasicInformation, SystemInformation, 0x40u, 0);
  NtQuerySystemInformation(SystemTimeOfDayInformation, v23, 0x30u, 0);
  EtwpGetCpuSpeed(&v22);
  v6 = NtCurrentPeb();
  a3->VersionDetail.MajorVersion = v6->OSMajorVersion;
  a3->VersionDetail.MinorVersion = v6->OSMinorVersion;
  a3->ProviderVersion = v6->OSBuildNumber;
  a3->ReservedFlags = a1->Wnode.ClientContext;
  a3->NumberOfProcessors = a2;
  a3->PointerSize = 8;
  v7 = a1->BufferSize << 10;
  a3->BufferSize = v7;
  a3->MaximumFileSize = a1->MaximumFileSize;
  LogFileMode = a1->LogFileMode;
  a3->LogFileMode = LogFileMode;
  if ( (LogFileMode & 0x4000000) != 0 || v7 > 0x100000 || a2 > 0x100 )
  {
    v9 = 0;
    v10 = 2;
  }
  else
  {
    v9 = 5;
    v10 = 1;
  }
  a3->VersionDetail.SubVersion = v10;
  a3->VersionDetail.SubMinorVersion = v9;
  a3->TimerResolution = v26;
  a3->BootTime.QuadPart = v23[0] - v23[4];
  a3->CpuSpeedInMHz = v22;
  memset_0(&TimeZoneInformation, 0, sizeof(TimeZoneInformation));
  if ( RtlQueryTimeZoneInformation(&TimeZoneInformation) < 0 )
  {
    memset_0(&a3->TimeZone, 0, sizeof(a3->TimeZone));
  }
  else
  {
    v11 = *(__m128i *)&TimeZoneInformation.StandardName[30];
    v12 = *(__m128i *)&TimeZoneInformation.StandardDate.Milliseconds;
    v13 = *(_OWORD *)&TimeZoneInformation.StandardName[6];
    *(_OWORD *)&a3->TimeZone.Bias = *(_OWORD *)&TimeZoneInformation.Bias;
    v14 = *(_OWORD *)&TimeZoneInformation.StandardName[14];
    *(_OWORD *)&a3->TimeZone.StandardName[6] = v13;
    v15 = *(_OWORD *)&TimeZoneInformation.StandardName[22];
    *(_OWORD *)&a3->TimeZone.StandardName[14] = v14;
    v16 = *(_OWORD *)&TimeZoneInformation.DaylightName[4];
    *(_OWORD *)&a3->TimeZone.StandardName[22] = v15;
    v17 = *(_OWORD *)&TimeZoneInformation.DaylightName[12];
    *(__m128i *)&a3->TimeZone.StandardName[30] = v11;
    *(__m128i *)&a3->TimeZone.StandardDate.wSecond = v12;
    *(_OWORD *)&a3->TimeZone.DaylightName[4] = v16;
    v18 = *(_OWORD *)&TimeZoneInformation.DaylightName[20];
    *(_OWORD *)&a3->TimeZone.DaylightName[12] = v17;
    v19 = *(__m128i *)&TimeZoneInformation.DaylightName[28];
    *(_OWORD *)&a3->TimeZone.DaylightName[20] = v18;
    v20 = *(__m128i *)&TimeZoneInformation.DaylightDate.Day;
    *(__m128i *)&a3->TimeZone.DaylightName[28] = v19;
    *(__m128i *)&a3->TimeZone.DaylightDate.wDayOfWeek = v20;
    a3->TimeZone.StandardDate.wYear = _mm_extract_epi16(v11, 2);
    a3->TimeZone.StandardDate.wMonth = _mm_extract_epi16(v11, 3);
    a3->TimeZone.StandardDate.wDay = _mm_extract_epi16(v11, 4);
    a3->TimeZone.StandardDate.wDayOfWeek = _mm_extract_epi16(v12, 1);
    a3->TimeZone.StandardDate.wHour = _mm_extract_epi16(v11, 5);
    a3->TimeZone.StandardDate.wMinute = _mm_extract_epi16(v11, 6);
    a3->TimeZone.StandardDate.wSecond = _mm_extract_epi16(v11, 7);
    a3->TimeZone.StandardDate.wMilliseconds = _mm_cvtsi128_si32(v12);
    a3->TimeZone.DaylightDate.wYear = _mm_extract_epi16(v19, 4);
    a3->TimeZone.DaylightDate.wMonth = _mm_extract_epi16(v19, 5);
    a3->TimeZone.DaylightDate.wDay = _mm_cvtsi128_si32(v20);
    a3->TimeZone.DaylightDate.wDayOfWeek = _mm_extract_epi16(v20, 5);
    a3->TimeZone.DaylightDate.wHour = _mm_extract_epi16(v20, 1);
    a3->TimeZone.DaylightDate.wMinute = _mm_extract_epi16(v20, 2);
    a3->TimeZone.DaylightDate.wSecond = _mm_extract_epi16(v20, 3);
    a3->TimeZone.DaylightDate.wMilliseconds = _mm_extract_epi16(v20, 4);
  }
  RtlQueryPerformanceFrequency(&a3->PerfFreq);
  result = 0;
  *(_QWORD *)&a3->BuffersWritten = 0;
  a3->EndTime.QuadPart = 0;
  a3->StartTime.QuadPart = 0;
  a3->EventsLost = 0;
  a3->BuffersLost = 0;
  a3->LoggerName = 0;
  a3->LogFileName = 0;
  return result;
}

```

## disassembly

```asm
0x18000f098  push    rbp
0x18000f09a  push    rbx
0x18000f09b  push    rsi
0x18000f09c  push    rdi
0x18000f09d  lea     rbp, [rsp-68h]
0x18000f0a2  sub     rsp, 168h
0x18000f0a9  mov     rax, cs:__security_cookie
0x18000f0b0  xor     rax, rsp
0x18000f0b3  mov     [rbp+80h+var_30], rax
0x18000f0b7  mov     esi, edx
0x18000f0b9  mov     [rsp+180h+var_160], 0
0x18000f0c1  xor     edx, edx; Val
0x18000f0c3  mov     rdi, r8
0x18000f0c6  mov     rbx, rcx
0x18000f0c9  lea     rcx, [rbp+80h+SystemInformation]; void *
0x18000f0cd  lea     r8d, [rdx+40h]; Size
0x18000f0d1  call    memset_0
0x18000f0d6  xorps   xmm0, xmm0
0x18000f0d9  mov     dword ptr [rsp+180h+var_158], 0
0x18000f0e1  xor     r9d, r9d; ReturnLength
0x18000f0e4  lea     rdx, [rbp+80h+SystemInformation]; SystemInformation
0x18000f0e8  movups  xmmword ptr [rsp+180h+var_144], xmm0
0x18000f0ed  xor     ecx, ecx; SystemInformationClass
0x18000f0ef  movups  xmmword ptr [rsp+180h+var_158+4], xmm0
0x18000f0f4  lea     r8d, [r9+40h]; SystemInformationLength
0x18000f0f8  movups  xmmword ptr [rsp+180h+var_144+0Ch], xmm0
0x18000f0fd  call    cs:__imp_NtQuerySystemInformation
0x18000f103  xor     r9d, r9d; ReturnLength
0x18000f106  lea     rdx, [rsp+180h+var_158]; SystemInformation
0x18000f10b  lea     r8d, [r9+30h]; SystemInformationLength
0x18000f10f  lea     ecx, [r9+3]; SystemInformationClass
0x18000f113  call    cs:__imp_NtQuerySystemInformation
0x18000f119  lea     rcx, [rsp+180h+var_160]
0x18000f11e  call    cs:__imp_EtwpGetCpuSpeed
0x18000f124  mov     rcx, gs:60h
0x18000f12d  mov     al, [rcx+118h]
0x18000f133  mov     [rdi+4], al
0x18000f136  mov     al, [rcx+11Ch]
0x18000f13c  mov     [rdi+5], al
0x18000f13f  movzx   eax, word ptr [rcx+120h]
0x18000f146  mov     [rdi+8], eax
0x18000f149  mov     eax, [rbx+28h]
0x18000f14c  mov     [rdi+110h], eax
0x18000f152  mov     [rdi+0Ch], esi
0x18000f155  mov     dword ptr [rdi+2Ch], 8
0x18000f15c  mov     ecx, [rbx+30h]
0x18000f15f  shl     ecx, 0Ah
0x18000f162  mov     [rdi], ecx
0x18000f164  mov     eax, [rbx+3Ch]
0x18000f167  mov     [rdi+1Ch], eax
0x18000f16a  mov     eax, [rbx+40h]
0x18000f16d  mov     [rdi+20h], eax
0x18000f170  bt      eax, 1Ah
0x18000f174  jb      short loc_18000F18C
0x18000f176  cmp     ecx, 100000h
0x18000f17c  ja      short loc_18000F18C
0x18000f17e  cmp     esi, 100h
0x18000f184  ja      short loc_18000F18C
0x18000f186  mov     al, 5
0x18000f188  mov     cl, 1
0x18000f18a  jmp     short loc_18000F190
0x18000f18c  xor     al, al
0x18000f18e  mov     cl, 2
0x18000f190  lea     rdx, [rdi+6]
0x18000f194  mov     esi, 0ACh
0x18000f199  mov     [rdx], cl
0x18000f19b  mov     r8d, esi; Size
0x18000f19e  mov     [rdi+7], al
0x18000f1a1  lea     rcx, [rsp+180h+TimeZoneInformation]; void *
0x18000f1a6  mov     eax, [rbp+80h+var_6C]
0x18000f1a9  xor     edx, edx; Val
0x18000f1ab  mov     [rdi+18h], eax
0x18000f1ae  mov     rax, qword ptr [rsp+180h+var_158]
0x18000f1b3  sub     rax, qword ptr [rsp+180h+var_144+0Ch]
0x18000f1b8  mov     [rdi+0F8h], rax
0x18000f1bf  mov     eax, [rsp+180h+var_160]
0x18000f1c3  mov     [rdi+34h], eax
0x18000f1c6  call    memset_0
0x18000f1cb  lea     rcx, [rsp+180h+TimeZoneInformation]; TimeZoneInformation
0x18000f1d0  call    cs:__imp_RtlQueryTimeZoneInformation
0x18000f1d6  test    eax, eax
0x18000f1d8  js      loc_18000F30D
0x18000f1de  movaps  xmm2, xmmword ptr [rbp+80h+TimeZoneInformation.StandardName+3Ch]
0x18000f1e2  movaps  xmm3, xmmword ptr [rbp+80h+TimeZoneInformation.StandardDate.Milliseconds]
0x18000f1e6  movaps  xmm0, xmmword ptr [rsp+180h+TimeZoneInformation.Bias]
0x18000f1eb  movaps  xmm1, xmmword ptr [rsp+180h+TimeZoneInformation.StandardName+0Ch]
0x18000f1f0  movups  xmmword ptr [rdi+48h], xmm0
0x18000f1f4  movaps  xmm0, xmmword ptr [rbp+80h+TimeZoneInformation.StandardName+1Ch]
0x18000f1f8  movups  xmmword ptr [rdi+58h], xmm1
0x18000f1fc  movaps  xmm1, xmmword ptr [rbp+80h+TimeZoneInformation.StandardName+2Ch]
0x18000f200  movups  xmmword ptr [rdi+68h], xmm0
0x18000f204  movaps  xmm0, xmmword ptr [rbp+80h+TimeZoneInformation.DaylightName+8]
0x18000f208  movups  xmmword ptr [rdi+78h], xmm1
0x18000f20c  movaps  xmm1, xmmword ptr [rbp+80h+TimeZoneInformation.DaylightName+18h]
0x18000f210  movups  xmmword ptr [rdi+88h], xmm2
0x18000f217  movups  xmmword ptr [rdi+98h], xmm3
0x18000f21e  movups  xmmword ptr [rdi+0A8h], xmm0
0x18000f225  movaps  xmm0, xmmword ptr [rbp+80h+TimeZoneInformation.DaylightName+28h]
0x18000f229  movups  xmmword ptr [rdi+0B8h], xmm1
0x18000f230  movaps  xmm1, xmmword ptr [rbp+80h+TimeZoneInformation.DaylightName+38h]
0x18000f234  movups  xmmword ptr [rdi+0C8h], xmm0
0x18000f23b  movups  xmm0, xmmword ptr [rbp+80h+TimeZoneInformation.DaylightDate.Day]
0x18000f23f  movups  xmmword ptr [rdi+0D8h], xmm1
0x18000f246  movups  xmmword ptr [rdi+0E4h], xmm0
0x18000f24d  pextrw  eax, xmm2, 2
0x18000f252  mov     [rdi+8Ch], ax
0x18000f259  pextrw  eax, xmm2, 3
0x18000f25e  mov     [rdi+8Eh], ax
0x18000f265  pextrw  eax, xmm2, 4
0x18000f26a  mov     [rdi+92h], ax
0x18000f271  pextrw  eax, xmm3, 1
0x18000f276  mov     [rdi+90h], ax
0x18000f27d  pextrw  eax, xmm2, 5
0x18000f282  mov     [rdi+94h], ax
0x18000f289  pextrw  eax, xmm2, 6
0x18000f28e  mov     [rdi+96h], ax
0x18000f295  pextrw  eax, xmm2, 7
0x18000f29a  mov     [rdi+98h], ax
0x18000f2a1  movd    eax, xmm3
0x18000f2a5  mov     [rdi+9Ah], ax
0x18000f2ac  pextrw  eax, xmm1, 4
0x18000f2b1  mov     [rdi+0E0h], ax
0x18000f2b8  pextrw  eax, xmm1, 5
0x18000f2bd  mov     [rdi+0E2h], ax
0x18000f2c4  movd    eax, xmm0
0x18000f2c8  mov     [rdi+0E6h], ax
0x18000f2cf  pextrw  eax, xmm0, 5
0x18000f2d4  mov     [rdi+0E4h], ax
0x18000f2db  pextrw  eax, xmm0, 1
0x18000f2e0  mov     [rdi+0E8h], ax
0x18000f2e7  pextrw  eax, xmm0, 2
0x18000f2ec  mov     [rdi+0EAh], ax
0x18000f2f3  pextrw  eax, xmm0, 3
0x18000f2f8  mov     [rdi+0ECh], ax
0x18000f2ff  pextrw  eax, xmm0, 4
0x18000f304  mov     [rdi+0EEh], ax
0x18000f30b  jmp     short loc_18000F31B
0x18000f30d  mov     r8, rsi; Size
0x18000f310  lea     rcx, [rdi+48h]; void *
0x18000f314  xor     edx, edx; Val
0x18000f316  call    memset_0
0x18000f31b  lea     rcx, [rdi+100h]
0x18000f322  call    cs:__imp_RtlQueryPerformanceFrequency
0x18000f328  xor     eax, eax
0x18000f32a  mov     qword ptr [rdi+24h], 0
0x18000f332  mov     qword ptr [rdi+10h], 0
0x18000f33a  mov     qword ptr [rdi+108h], 0
0x18000f345  mov     dword ptr [rdi+30h], 0
0x18000f34c  mov     dword ptr [rdi+114h], 0
0x18000f356  mov     qword ptr [rdi+38h], 0
0x18000f35e  mov     qword ptr [rdi+40h], 0
0x18000f366  mov     rcx, [rbp+80h+var_30]
0x18000f36a  xor     rcx, rsp; StackCookie
0x18000f36d  call    __security_check_cookie
0x18000f372  add     rsp, 168h
0x18000f379  pop     rdi
0x18000f37a  pop     rsi
0x18000f37b  pop     rbx
0x18000f37c  pop     rbp
0x18000f37d  retn
```
