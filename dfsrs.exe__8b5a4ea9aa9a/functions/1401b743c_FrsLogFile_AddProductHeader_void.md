# FrsLogFile::AddProductHeader(void)

- ea: `0x1401b743c`
- end: `0x1401b7863`
- name: `?AddProductHeader@FrsLogFile@@AEAAPEAVFrsStatus@@XZ`
- size: `1063`
- prototype: `struct FrsStatus *__fastcall(FrsLogFile *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1401b7dbc`

## callees

- `0x1400036a0`
- `0x1400046cc`
- `0x14000ee94`
- `0x1400173fc`
- `0x1401b743c`
- `0x1401b9494`
- `0x1401bf89c`
- `0x1402135d0`

## import_xrefs

- `KERNEL32!WideCharToMultiByte` at `0x1401b7721`
- `KERNEL32!WideCharToMultiByte` at `0x1401b7721`
- `KERNEL32!WriteFile` at `0x1401b77b0`
- `KERNEL32!WriteFile` at `0x1401b77b0`
- `KERNEL32!GetComputerNameW` at `0x1401b7514`
- `KERNEL32!GetComputerNameW` at `0x1401b7514`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x1401b7588`
- `KERNEL32!GetDynamicTimeZoneInformation` at `0x1401b7588`
- `KERNEL32!GetLastError` at `0x1401b7532`
- `KERNEL32!GetLastError` at `0x1401b7599`
- `KERNEL32!GetLastError` at `0x1401b7734`
- `KERNEL32!GetLastError` at `0x1401b77c0`
- `KERNEL32!GetLastError` at `0x1401b7532`
- `KERNEL32!GetLastError` at `0x1401b7599`
- `KERNEL32!GetLastError` at `0x1401b7734`
- `KERNEL32!GetLastError` at `0x1401b77c0`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7540`
- `KERNEL32!GetCurrentThreadId` at `0x1401b75a7`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7742`
- `KERNEL32!GetCurrentThreadId` at `0x1401b77ce`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7540`
- `KERNEL32!GetCurrentThreadId` at `0x1401b75a7`
- `KERNEL32!GetCurrentThreadId` at `0x1401b7742`
- `KERNEL32!GetCurrentThreadId` at `0x1401b77ce`

## string_xrefs

- `0x1401b76c8`: `* DFSR Log Sequence:%u Index:%u Computer:%ws TimeZone:%ws Build:[%ls]\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct FrsStatus *__fastcall FrsLogFile::AddProductHeader(FrsLogFile *this)
{
  __int64 v2; // rbx
  DWORD v3; // esi
  DWORD v4; // ebx
  DWORD v5; // eax
  __int64 v6; // rcx
  DWORD DynamicTimeZoneInformation; // eax
  DWORD LastError; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  LONG Bias; // r9d
  WCHAR *StandardName; // r10
  int v14; // r8d
  int v15; // eax
  __int64 v16; // r9
  DWORD v17; // r14d
  DWORD v18; // ebx
  DWORD v19; // eax
  __int64 v20; // rcx
  DWORD v21; // ebx
  DWORD v22; // eax
  __int64 v23; // rcx
  LPSTR lpMultiByteStr; // [rsp+20h] [rbp-E0h]
  LPSTR lpMultiByteStra; // [rsp+20h] [rbp-E0h]
  int cbMultiByte[2]; // [rsp+28h] [rbp-D8h]
  LPCCH lpDefaultChar; // [rsp+30h] [rbp-D0h]
  DWORD NumberOfBytesWritten; // [rsp+50h] [rbp-B0h] BYREF
  DWORD nSize; // [rsp+54h] [rbp-ACh] BYREF
  unsigned __int16 *v31; // [rsp+58h] [rbp-A8h] BYREF
  _TIME_DYNAMIC_ZONE_INFORMATION pTimeZoneInformation; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[8]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v34; // [rsp+220h] [rbp+120h]
  unsigned __int16 v35[512]; // [rsp+230h] [rbp+130h] BYREF
  CHAR MultiByteStr[4112]; // [rsp+630h] [rbp+530h] BYREF
  WCHAR WideCharStr[4104]; // [rsp+1640h] [rbp+1540h] BYREF

  v2 = 0;
  memset_0(WideCharStr, 0, 0x2002u);
  NumberOfBytesWritten = 0;
  v3 = 0;
  memset_0(MultiByteStr, 0, 0x1001u);
  v31 = &FrsStringImpl<unsigned short,char>::s_Empty;
  if ( !byte_140315A80 )
    _InterlockedIncrement((volatile signed __int32 *)&FrsStringImpl<unsigned short,char>::s_Empty);
  memset_0(&pTimeZoneInformation, 0, sizeof(pTimeZoneInformation));
  memset_0(v35, 0, sizeof(v35));
  *(_OWORD *)Buffer = 0;
  v34 = 0;
  nSize = 16;
  if ( GetComputerNameW(Buffer, &nSize)
    || (v4 = GetLastError(),
        v5 = GetCurrentThreadId(),
        (v2 = FrsStatusList::PushNewError(
                v6,
                v4,
                0,
                1,
                "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                "FrsLogFile::AddProductHeader",
                519,
                v5,
                0)) == 0) )
  {
    DynamicTimeZoneInformation = GetDynamicTimeZoneInformation(&pTimeZoneInformation);
    if ( DynamicTimeZoneInformation == -1 )
    {
      LastError = GetLastError();
      CurrentThreadId = GetCurrentThreadId();
      v2 = FrsStatusList::PushNewError(
             v10,
             LastError,
             0,
             1,
             "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
             "FrsLogFile::AddProductHeader",
             530,
             CurrentThreadId,
             0);
LABEL_19:
      if ( !v2 )
      {
        GetVerProductBuildTimestampString(&v31);
        LODWORD(lpMultiByteStra) = *((_DWORD *)this + 3);
        StringCchPrintfW(
          WideCharStr,
          0x1000u,
          L"* DFSR Log Sequence:%u Index:%u Computer:%ws TimeZone:%ws Build:[%ls]\r\n",
          *((unsigned int *)this + 2),
          lpMultiByteStra,
          Buffer,
          v35,
          v31 + 9);
        v16 = -1;
        do
          ++v16;
        while ( WideCharStr[v16] );
        v17 = WideCharToMultiByte(0xFDE9u, 0, WideCharStr, v16, MultiByteStr, 4097, 0, 0);
        if ( v17
          || (v18 = GetLastError(),
              v19 = GetCurrentThreadId(),
              (v2 = FrsStatusList::PushNewError(
                      v20,
                      v18,
                      0,
                      1,
                      "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                      "FrsLogFile::AddProductHeader",
                      608,
                      v19,
                      0)) == 0) )
        {
          do
          {
            if ( v3 >= v17 )
              break;
            if ( WriteFile(*((HANDLE *)this + 3), &MultiByteStr[v3], v17, &NumberOfBytesWritten, 0) )
            {
              v3 += NumberOfBytesWritten;
              NumberOfBytesWritten = 0;
            }
            else
            {
              v21 = GetLastError();
              v22 = GetCurrentThreadId();
              v2 = FrsStatusList::PushNewError(
                     v23,
                     v21,
                     0,
                     1,
                     "base\\fs\\remotefs\\frs\\src\\util\\frslogger.cpp",
                     "FrsLogFile::AddProductHeader",
                     626,
                     v22,
                     0);
            }
          }
          while ( !v2 );
          if ( !v2 )
            ++*(_DWORD *)this;
        }
      }
      goto LABEL_31;
    }
    if ( DynamicTimeZoneInformation )
    {
      v11 = DynamicTimeZoneInformation - 1;
      if ( !v11 )
      {
        Bias = pTimeZoneInformation.Bias + pTimeZoneInformation.StandardBias;
LABEL_13:
        StandardName = pTimeZoneInformation.StandardName;
        goto LABEL_14;
      }
      if ( v11 == 1 )
      {
        Bias = pTimeZoneInformation.Bias + pTimeZoneInformation.DaylightBias;
        StandardName = pTimeZoneInformation.DaylightName;
LABEL_14:
        v14 = Bias / -60;
        if ( Bias / -60 < 0 )
          v14 = Bias / 60;
        v15 = 60 * (Bias / 60) - Bias;
        if ( v15 < 0 )
          v15 = Bias % 60;
        LODWORD(lpDefaultChar) = v15;
        cbMultiByte[0] = v14;
        LODWORD(lpMultiByteStr) = ((Bias >> 31) & 0xFFFFFFFE) + 45;
        StringCchPrintfW(
          v35,
          0x200u,
          L"%ws (GMT%wc%02d:%02d) (TzId>%ws<dIzT)",
          StandardName,
          lpMultiByteStr,
          *(_QWORD *)cbMultiByte,
          lpDefaultChar,
          pTimeZoneInformation.TimeZoneKeyName);
        goto LABEL_19;
      }
    }
    Bias = pTimeZoneInformation.Bias;
    goto LABEL_13;
  }
LABEL_31:
  FrsStringImpl<char,unsigned short>::ReleaseBody(&v31);
  return (struct FrsStatus *)v2;
}

```

## disassembly

```asm
0x1401b743c  mov     [rsp-8+arg_8], rbx
0x1401b7441  mov     [rsp-8+arg_10], rsi
0x1401b7446  push    rbp
0x1401b7447  push    rdi
0x1401b7448  push    r13
0x1401b744a  push    r14
0x1401b744c  push    r15
0x1401b744e  lea     rbp, [rsp-3560h]
0x1401b7456  mov     eax, 3660h
0x1401b745b  call    _alloca_probe
0x1401b7460  sub     rsp, rax
0x1401b7463  mov     rax, cs:__security_cookie
0x1401b746a  xor     rax, rsp
0x1401b746d  mov     [rbp+3580h+var_30], rax
0x1401b7474  mov     rdi, rcx
0x1401b7477  xor     r15d, r15d
0x1401b747a  mov     ebx, r15d
0x1401b747d  xor     edx, edx; Val
0x1401b747f  mov     r8d, 2002h; Size
0x1401b7485  lea     rcx, [rbp+3580h+WideCharStr]; void *
0x1401b748c  call    memset_0
0x1401b7491  mov     [rsp+3680h+NumberOfBytesWritten], r15d
0x1401b7496  mov     esi, r15d
0x1401b7499  xor     edx, edx; Val
0x1401b749b  mov     r8d, 1001h; Size
0x1401b74a1  lea     rcx, [rbp+3580h+MultiByteStr]; void *
0x1401b74a8  call    memset_0
0x1401b74ad  lea     rax, ?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401b74b4  mov     [rsp+3680h+var_3628], rax
0x1401b74b9  cmp     cs:byte_140315A80, r15b
0x1401b74c0  jnz     short loc_1401B74C9
0x1401b74c2  lock inc cs:?s_Empty@?$FrsStringImpl@GD@@0UCBody@1@A; FrsStringImpl<ushort,char>::CBody FrsStringImpl<ushort,char>::s_Empty
0x1401b74c9  xor     edx, edx; Val
0x1401b74cb  mov     r8d, 1B0h; Size
0x1401b74d1  lea     rcx, [rsp+3680h+pTimeZoneInformation]; void *
0x1401b74d6  call    memset_0
0x1401b74db  xor     edx, edx; Val
0x1401b74dd  mov     r8d, 400h; Size
0x1401b74e3  lea     rcx, [rbp+3580h+var_3450]; void *
0x1401b74ea  call    memset_0
0x1401b74ef  xorps   xmm0, xmm0
0x1401b74f2  movups  xmmword ptr [rbp+3580h+Buffer], xmm0
0x1401b74f9  movups  [rbp+3580h+var_3460], xmm0
0x1401b7500  mov     [rsp+3680h+nSize], 10h
0x1401b7508  lea     rdx, [rsp+3680h+nSize]; nSize
0x1401b750d  lea     rcx, [rbp+3580h+Buffer]; lpBuffer
0x1401b7514  call    cs:__imp_GetComputerNameW
0x1401b751b  nop     dword ptr [rax+rax+00h]
0x1401b7520  lea     r13, aFrslogfileAddp; "FrsLogFile::AddProductHeader"
0x1401b7527  lea     r14, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b752e  test    eax, eax
0x1401b7530  jnz     short loc_1401B7583
0x1401b7532  call    cs:__imp_GetLastError
0x1401b7539  nop     dword ptr [rax+rax+00h]
0x1401b753e  mov     ebx, eax
0x1401b7540  call    cs:__imp_GetCurrentThreadId
0x1401b7547  nop     dword ptr [rax+rax+00h]
0x1401b754c  mov     [rsp+3680h+var_3640], r15
0x1401b7551  mov     dword ptr [rsp+3680h+lpUsedDefaultChar], eax
0x1401b7555  mov     dword ptr [rsp+3680h+lpDefaultChar], 207h
0x1401b755d  mov     qword ptr [rsp+3680h+cbMultiByte], r13
0x1401b7562  mov     [rsp+3680h+lpMultiByteStr], r14
0x1401b7567  mov     r9d, 1
0x1401b756d  xor     r8d, r8d
0x1401b7570  mov     edx, ebx
0x1401b7572  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b7577  mov     rbx, rax
0x1401b757a  test    rax, rax
0x1401b757d  jnz     loc_1401B782A
0x1401b7583  lea     rcx, [rsp+3680h+pTimeZoneInformation]; pTimeZoneInformation
0x1401b7588  call    cs:__imp_GetDynamicTimeZoneInformation
0x1401b758f  nop     dword ptr [rax+rax+00h]
0x1401b7594  cmp     eax, 0FFFFFFFFh
0x1401b7597  jnz     short loc_1401B75E6
0x1401b7599  call    cs:__imp_GetLastError
0x1401b75a0  nop     dword ptr [rax+rax+00h]
0x1401b75a5  mov     ebx, eax
0x1401b75a7  call    cs:__imp_GetCurrentThreadId
0x1401b75ae  nop     dword ptr [rax+rax+00h]
0x1401b75b3  mov     [rsp+3680h+var_3640], r15
0x1401b75b8  mov     dword ptr [rsp+3680h+lpUsedDefaultChar], eax
0x1401b75bc  mov     dword ptr [rsp+3680h+lpDefaultChar], 212h
0x1401b75c4  mov     qword ptr [rsp+3680h+cbMultiByte], r13
0x1401b75c9  mov     [rsp+3680h+lpMultiByteStr], r14
0x1401b75ce  mov     r9d, 1
0x1401b75d4  xor     r8d, r8d
0x1401b75d7  mov     edx, ebx
0x1401b75d9  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b75de  mov     rbx, rax
0x1401b75e1  jmp     loc_1401B7684
0x1401b75e6  test    eax, eax
0x1401b75e8  jz      short loc_1401B760E
0x1401b75ea  sub     eax, 1
0x1401b75ed  jz      short loc_1401B7603
0x1401b75ef  cmp     eax, 1
0x1401b75f2  jnz     short loc_1401B760E
0x1401b75f4  mov     r9d, [rbp+3580h+pTimeZoneInformation.DaylightBias]
0x1401b75f8  add     r9d, [rsp+3680h+pTimeZoneInformation.Bias]
0x1401b75fd  lea     r10, [rbp+3580h+pTimeZoneInformation.DaylightName]
0x1401b7601  jmp     short loc_1401B7618
0x1401b7603  mov     r9d, [rbp+3580h+pTimeZoneInformation.StandardBias]
0x1401b7607  add     r9d, [rsp+3680h+pTimeZoneInformation.Bias]
0x1401b760c  jmp     short loc_1401B7613
0x1401b760e  mov     r9d, [rsp+3680h+pTimeZoneInformation.Bias]
0x1401b7613  lea     r10, [rsp+3680h+pTimeZoneInformation.StandardName]
0x1401b7618  mov     eax, 88888889h
0x1401b761d  imul    r9d
0x1401b7620  add     edx, r9d
0x1401b7623  sar     edx, 5
0x1401b7626  mov     eax, edx
0x1401b7628  shr     eax, 1Fh
0x1401b762b  add     edx, eax
0x1401b762d  mov     r8d, edx
0x1401b7630  neg     r8d
0x1401b7633  cmovs   r8d, edx
0x1401b7637  imul    eax, edx, 3Ch ; '<'
0x1401b763a  mov     ecx, r9d
0x1401b763d  sub     ecx, eax
0x1401b763f  mov     eax, ecx
0x1401b7641  neg     eax
0x1401b7643  cmovs   eax, ecx
0x1401b7646  sar     r9d, 1Fh
0x1401b764a  and     r9d, 0FFFFFFFEh
0x1401b764e  add     r9d, 2Dh ; '-'
0x1401b7652  lea     rcx, [rbp+3580h+pTimeZoneInformation.TimeZoneKeyName]
0x1401b7656  mov     [rsp+3680h+lpUsedDefaultChar], rcx
0x1401b765b  mov     dword ptr [rsp+3680h+lpDefaultChar], eax
0x1401b765f  mov     [rsp+3680h+cbMultiByte], r8d
0x1401b7664  mov     dword ptr [rsp+3680h+lpMultiByteStr], r9d
0x1401b7669  mov     r9, r10
0x1401b766c  lea     r8, aWsGmtWc02d02dT; "%ws (GMT%wc%02d:%02d) (TzId>%ws<dIzT)"
0x1401b7673  mov     edx, 200h; unsigned __int64
0x1401b7678  lea     rcx, [rbp+3580h+var_3450]; unsigned __int16 *
0x1401b767f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b7684  test    rbx, rbx
0x1401b7687  jnz     loc_1401B782A
0x1401b768d  lea     rcx, [rsp+3680h+var_3628]
0x1401b7692  call    ?GetVerProductBuildTimestampString@@YAXAEAV?$FrsStringImpl@GD@@@Z; GetVerProductBuildTimestampString(FrsStringImpl<ushort,char> &)
0x1401b7697  mov     rax, [rsp+3680h+var_3628]
0x1401b769c  add     rax, 12h
0x1401b76a0  mov     ecx, [rdi+0Ch]
0x1401b76a3  mov     [rsp+3680h+lpUsedDefaultChar], rax
0x1401b76a8  lea     rax, [rbp+3580h+var_3450]
0x1401b76af  mov     [rsp+3680h+lpDefaultChar], rax
0x1401b76b4  lea     rax, [rbp+3580h+Buffer]
0x1401b76bb  mov     qword ptr [rsp+3680h+cbMultiByte], rax
0x1401b76c0  mov     dword ptr [rsp+3680h+lpMultiByteStr], ecx
0x1401b76c4  mov     r9d, [rdi+8]
0x1401b76c8  lea     r8, aDfsrLogSequenc; "* DFSR Log Sequence:%u Index:%u Compute"...
0x1401b76cf  mov     edx, 1000h; unsigned __int64
0x1401b76d4  lea     rcx, [rbp+3580h+WideCharStr]; unsigned __int16 *
0x1401b76db  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1401b76e0  lea     rax, [rbp+3580h+WideCharStr]
0x1401b76e7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1401b76eb  inc     r9; cchWideChar
0x1401b76ee  cmp     [rax+r9*2], r15w
0x1401b76f3  jnz     short loc_1401B76EB
0x1401b76f5  mov     [rsp+3680h+lpUsedDefaultChar], r15; lpUsedDefaultChar
0x1401b76fa  mov     [rsp+3680h+lpDefaultChar], r15; lpDefaultChar
0x1401b76ff  mov     [rsp+3680h+cbMultiByte], 1001h; cbMultiByte
0x1401b7707  lea     rax, [rbp+3580h+MultiByteStr]
0x1401b770e  mov     [rsp+3680h+lpMultiByteStr], rax; lpMultiByteStr
0x1401b7713  lea     r8, [rbp+3580h+WideCharStr]; lpWideCharStr
0x1401b771a  xor     edx, edx; dwFlags
0x1401b771c  mov     ecx, 0FDE9h; CodePage
0x1401b7721  call    cs:__imp_WideCharToMultiByte
0x1401b7728  nop     dword ptr [rax+rax+00h]
0x1401b772d  mov     r14d, eax
0x1401b7730  test    eax, eax
0x1401b7732  jnz     short loc_1401B778A
0x1401b7734  call    cs:__imp_GetLastError
0x1401b773b  nop     dword ptr [rax+rax+00h]
0x1401b7740  mov     ebx, eax
0x1401b7742  call    cs:__imp_GetCurrentThreadId
0x1401b7749  nop     dword ptr [rax+rax+00h]
0x1401b774e  mov     [rsp+3680h+var_3640], r15
0x1401b7753  mov     dword ptr [rsp+3680h+lpUsedDefaultChar], eax
0x1401b7757  mov     dword ptr [rsp+3680h+lpDefaultChar], 260h
0x1401b775f  mov     qword ptr [rsp+3680h+cbMultiByte], r13
0x1401b7764  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b776b  mov     [rsp+3680h+lpMultiByteStr], rax
0x1401b7770  lea     r9d, [r14+1]
0x1401b7774  xor     r8d, r8d
0x1401b7777  mov     edx, ebx
0x1401b7779  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b777e  mov     rbx, rax
0x1401b7781  test    rax, rax
0x1401b7784  jnz     loc_1401B782A
0x1401b778a  cmp     esi, r14d
0x1401b778d  jnb     loc_1401B7823
0x1401b7793  mov     eax, esi
0x1401b7795  lea     rdx, [rbp+3580h+MultiByteStr]
0x1401b779c  add     rdx, rax; lpBuffer
0x1401b779f  mov     [rsp+3680h+lpMultiByteStr], r15; lpOverlapped
0x1401b77a4  lea     r9, [rsp+3680h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1401b77a9  mov     r8d, r14d; nNumberOfBytesToWrite
0x1401b77ac  mov     rcx, [rdi+18h]; hFile
0x1401b77b0  call    cs:__imp_WriteFile
0x1401b77b7  nop     dword ptr [rax+rax+00h]
0x1401b77bc  test    eax, eax
0x1401b77be  jnz     short loc_1401B7811
0x1401b77c0  call    cs:__imp_GetLastError
0x1401b77c7  nop     dword ptr [rax+rax+00h]
0x1401b77cc  mov     ebx, eax
0x1401b77ce  call    cs:__imp_GetCurrentThreadId
0x1401b77d5  nop     dword ptr [rax+rax+00h]
0x1401b77da  mov     [rsp+3680h+var_3640], r15
0x1401b77df  mov     dword ptr [rsp+3680h+lpUsedDefaultChar], eax
0x1401b77e3  mov     dword ptr [rsp+3680h+lpDefaultChar], 272h
0x1401b77eb  mov     qword ptr [rsp+3680h+cbMultiByte], r13
0x1401b77f0  lea     rax, aBaseFsRemotefs_92; "base\\fs\\remotefs\\frs\\src\\util\\frs"...
0x1401b77f7  mov     [rsp+3680h+lpMultiByteStr], rax
0x1401b77fc  mov     r9d, 1
0x1401b7802  xor     r8d, r8d
0x1401b7805  mov     edx, ebx
0x1401b7807  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401b780c  mov     rbx, rax
0x1401b780f  jmp     short loc_1401B781A
0x1401b7811  add     esi, [rsp+3680h+NumberOfBytesWritten]
0x1401b7815  mov     [rsp+3680h+NumberOfBytesWritten], r15d
0x1401b781a  test    rbx, rbx
0x1401b781d  jz      loc_1401B778A
0x1401b7823  test    rbx, rbx
0x1401b7826  jnz     short loc_1401B782A
0x1401b7828  inc     dword ptr [rdi]
0x1401b782a  lea     rcx, [rsp+3680h+var_3628]
0x1401b782f  call    ?ReleaseBody@?$FrsStringImpl@DG@@AEAAXXZ; FrsStringImpl<char,ushort>::ReleaseBody(void)
0x1401b7834  mov     rax, rbx
0x1401b7837  mov     rcx, [rbp+3580h+var_30]
0x1401b783e  xor     rcx, rsp; StackCookie
0x1401b7841  call    __security_check_cookie
0x1401b7846  lea     r11, [rsp+3680h+var_20]
0x1401b784e  mov     rbx, [r11+38h]
0x1401b7852  mov     rsi, [r11+40h]
0x1401b7856  mov     rsp, r11
0x1401b7859  pop     r15
0x1401b785b  pop     r14
0x1401b785d  pop     r13
0x1401b785f  pop     rdi
0x1401b7860  pop     rbp
0x1401b7861  retn
```
