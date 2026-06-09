# Np::OpenPipe(wchar_t const *,ulong)

- ea: `0x18015eef0`
- end: `0x18015f4d2`
- name: `?OpenPipe@Np@@AEAAKPEB_WK@Z`
- size: `1506`
- prototype: `unsigned int(Np *__hidden this, const wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18015ebc0`

## callees

- `0x1800013e0`
- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180159da0`
- `0x18015a6f0`
- `0x18015a880`
- `0x18015eef0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x18015f0fa`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x18015f11d`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x18015f0fa`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x18015f11d`
- `KERNEL32!GetLastError` at `0x18015f1b0`
- `KERNEL32!GetLastError` at `0x18015f244`
- `KERNEL32!GetLastError` at `0x18015f397`
- `KERNEL32!GetLastError` at `0x18015f1b0`
- `KERNEL32!GetLastError` at `0x18015f244`
- `KERNEL32!GetLastError` at `0x18015f397`
- `KERNEL32!WaitNamedPipeW` at `0x18015f1cb`
- `KERNEL32!WaitNamedPipeW` at `0x18015f1cb`
- `KERNEL32!SetNamedPipeHandleState` at `0x18015f236`
- `KERNEL32!SetNamedPipeHandleState` at `0x18015f236`
- `KERNEL32!CreateFileW` at `0x18015f199`
- `KERNEL32!CreateFileW` at `0x18015f210`
- `KERNEL32!CreateFileW` at `0x18015f199`
- `KERNEL32!CreateFileW` at `0x18015f210`
- `KERNEL32!GetTickCount` at `0x18015f16b`
- `KERNEL32!GetTickCount` at `0x18015f1d9`
- `KERNEL32!GetTickCount` at `0x18015f16b`
- `KERNEL32!GetTickCount` at `0x18015f1d9`
- `KERNEL32!CloseHandle` at `0x18015f2a3`
- `KERNEL32!CloseHandle` at `0x18015f2a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Np::OpenPipe(Np *this, const wchar_t *a2, unsigned int a3)
{
  char v6; // r9
  unsigned int v7; // ebp
  wchar_t *v8; // r8
  __int64 v9; // rdx
  char *v10; // rcx
  DWORD LastError; // ebx
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rbx
  struct localeinfo_struct *v17; // rax
  __int64 v18; // rcx
  struct localeinfo_struct *v19; // rax
  DWORD TickCount; // r12d
  DWORD v21; // esi
  HANDLE FileW; // rax
  DWORD Mode; // [rsp+40h] [rbp-58h] BYREF
  __int64 v24; // [rsp+48h] [rbp-50h] BYREF

  v24 = -1;
  v6 = bidGblFlags;
  if ( (bidGblFlags & 0x20004) == 0x20004 )
  {
    if ( off_1802668D8[0] )
      bidScopeEnterW(&v24, off_1802668D8[0], *((unsigned int *)this + 11), a2);
    v6 = bidGblFlags;
  }
  v7 = 0;
  if ( *a2 != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) == 0 || !off_180264158[0] )
      goto LABEL_10;
    SniErrorIdFromStringId(0xC3B9u);
    v8 = off_180264158[0];
    v9 = 217088;
    v10 = off_180260E10[0];
LABEL_9:
    bidTraceW(v10, v9, v8, *((unsigned int *)this + 18));
LABEL_10:
    SNISetLastError(*((unsigned int *)this + 18), 87, 50105);
    goto LABEL_11;
  }
  if ( a2[1] != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) == 0 || !off_180264160[0] )
      goto LABEL_10;
    SniErrorIdFromStringId(0xC3B9u);
    v8 = off_180264160[0];
    v9 = 226304;
    v10 = off_180260E18[0];
    goto LABEL_9;
  }
  v13 = a2 + 2;
  v14 = -1;
  do
    ++v14;
  while ( v13[v14] );
  v16 = StrChrW_SYS(v13, v14, 92);
  if ( !v16 )
  {
    v7 = 87;
    if ( (bidGblFlags & 2) == 0 || !off_180264168[0] )
      goto LABEL_10;
    SniErrorIdFromStringId(0xC3B9u);
    v8 = off_180264168[0];
    v9 = 239616;
    v10 = off_180260E20[0];
    goto LABEL_9;
  }
  v17 = (struct localeinfo_struct *)ImplBidTouch(v15);
  if ( _wcsnicmp_l(L"pipe\\", (const wchar_t *)(v16 + 2), 5u, v17) )
  {
    v19 = (struct localeinfo_struct *)ImplBidTouch(v18);
    if ( _wcsnicmp_l(L"HostPipe\\", (const wchar_t *)(v16 + 2), 9u, v19) )
    {
      v7 = 87;
      if ( (bidGblFlags & 2) == 0 || !off_180264170[0] )
        goto LABEL_10;
      SniErrorIdFromStringId(0xC3B9u);
      v8 = off_180264170[0];
      v9 = 258048;
      v10 = off_180260E28[0];
      goto LABEL_9;
    }
  }
  TickCount = GetTickCount();
  v21 = 0;
  FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  *((_QWORD *)this + 8) = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    while ( 1 )
    {
      LastError = GetLastError();
      if ( LastError != 231 )
        break;
      if ( !WaitNamedPipeW(a2, a3 - v21) )
      {
        LastError = GetLastError();
        if ( (bidGblFlags & 2) != 0 && off_180264188[0] )
        {
          SniErrorIdFromStringId(0xC3DCu);
          bidTraceW(off_180260E40[0], 296960, off_180264188[0], *((unsigned int *)this + 18));
        }
        SNISetLastError(*((unsigned int *)this + 18), LastError, 50140);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264190[0] )
          bidTraceW(off_180260E48[0], 297984, off_180264190[0], LastError);
        goto LABEL_15;
      }
      v21 = GetTickCount() - TickCount;
      if ( a3 < v21 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180264198[0] )
        {
          SniErrorIdFromStringId(0xC3DCu);
          bidTraceW(off_180260E50[0], 306176, off_180264198[0], *((unsigned int *)this + 18));
        }
        SNISetLastError(*((unsigned int *)this + 18), 231, 50140);
        if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802641A0[0] )
          bidTraceW(off_180260E58[0], 307200, off_1802641A0[0], 231);
        LastError = 1460;
        goto LABEL_15;
      }
      FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
      *((_QWORD *)this + 8) = FileW;
      if ( FileW != (HANDLE)-1LL )
        goto LABEL_36;
    }
    if ( (bidGblFlags & 2) != 0 && off_180264178[0] )
    {
      SniErrorIdFromStringId(0xC3DCu);
      bidTraceW(off_180260E30[0], 288768, off_180264178[0], *((unsigned int *)this + 18));
    }
    SNISetLastError(*((unsigned int *)this + 18), LastError, 50140);
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_180264180[0] )
      bidTraceW(off_180260E38[0], 289792, off_180264180[0], LastError);
  }
  else
  {
LABEL_36:
    Mode = 2;
    if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
    {
LABEL_11:
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802641B8[0] )
        bidTraceW(off_180260E70[0], 343040, off_1802641B8[0], v7);
      LastError = v7;
      goto LABEL_15;
    }
    LastError = GetLastError();
    if ( (bidGblFlags & 2) != 0 && off_1802641A8[0] )
    {
      SniErrorIdFromStringId(0xC3B4u);
      bidTraceW(off_180260E60[0], 330752, off_1802641A8[0], *((unsigned int *)this + 18));
    }
    SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
    CloseHandle(*((HANDLE *)this + 8));
    *((_QWORD *)this + 8) = -1;
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1802641B0[0] )
      bidTraceW(off_180260E68[0], 336896, off_1802641B0[0], LastError);
  }
LABEL_15:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v24);
  return LastError;
}

```

## disassembly

```asm
0x18015eef0  push    rbx
0x18015eef2  push    rbp
0x18015eef3  push    rsi
0x18015eef4  push    rdi
0x18015eef5  push    r12
0x18015eef7  push    r14
0x18015eef9  push    r15
0x18015eefb  sub     rsp, 60h
0x18015eeff  mov     rax, cs:__security_cookie
0x18015ef06  xor     rax, rsp
0x18015ef09  mov     [rsp+98h+var_48], rax
0x18015ef0e  mov     r15d, r8d
0x18015ef11  mov     r14, rdx
0x18015ef14  mov     rdi, rcx
0x18015ef17  mov     [rsp+98h+var_50], 0FFFFFFFFFFFFFFFFh
0x18015ef20  mov     r9d, cs:_bidGblFlags
0x18015ef27  mov     eax, r9d
0x18015ef2a  and     eax, 20004h
0x18015ef2f  cmp     eax, 20004h
0x18015ef34  jnz     short loc_18015EF66
0x18015ef36  mov     rax, cs:off_1802668D8; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x18015ef3d  test    rax, rax
0x18015ef40  jz      short loc_18015EF5F
0x18015ef42  mov     [rsp+98h+dwCreationDisposition], r8d
0x18015ef47  mov     r9, rdx
0x18015ef4a  mov     r8d, [rcx+2Ch]
0x18015ef4e  mov     rdx, cs:off_1802668D8; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x18015ef55  lea     rcx, [rsp+98h+var_50]
0x18015ef5a  call    _bidScopeEnterW
0x18015ef5f  mov     r9d, cs:_bidGblFlags
0x18015ef66  xor     ebp, ebp
0x18015ef68  mov     r8d, 5Ch ; '\'
0x18015ef6e  cmp     r8w, [r14]
0x18015ef72  jz      loc_18015F031
0x18015ef78  mov     ebp, 57h ; 'W'
0x18015ef7d  test    r9b, 2
0x18015ef81  jz      short loc_18015EFBD
0x18015ef83  mov     rax, cs:off_180264158; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015ef8a  test    rax, rax
0x18015ef8d  jz      short loc_18015EFBD
0x18015ef8f  mov     ecx, 0C3B9h; unsigned int
0x18015ef94  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015ef99  mov     r8, cs:off_180264158; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015efa0  mov     edx, 35000h
0x18015efa5  mov     rcx, cs:off_180260E10; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015efac  mov     [rsp+98h+dwFlagsAndAttributes], ebp
0x18015efb0  mov     r9d, [rdi+48h]
0x18015efb4  mov     [rsp+98h+dwCreationDisposition], eax
0x18015efb8  call    _bidTraceW
0x18015efbd  mov     edx, ebp
0x18015efbf  mov     r8d, 0C3B9h
0x18015efc5  mov     ecx, [rdi+48h]
0x18015efc8  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015efcd  mov     eax, cs:_bidGblFlags
0x18015efd3  and     eax, 20002h
0x18015efd8  cmp     eax, 20002h
0x18015efdd  jnz     short loc_18015F006
0x18015efdf  mov     rax, cs:off_1802641B8; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015efe6  test    rax, rax
0x18015efe9  jz      short loc_18015F006
0x18015efeb  mov     r9d, ebp
0x18015efee  mov     r8, cs:off_1802641B8; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015eff5  mov     edx, 53C00h
0x18015effa  mov     rcx, cs:off_180260E70; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f001  call    _bidTraceW
0x18015f006  mov     ebx, ebp
0x18015f008  lea     rcx, [rsp+98h+var_50]; this
0x18015f00d  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x18015f012  nop
0x18015f013  mov     eax, ebx
0x18015f015  mov     rcx, [rsp+98h+var_48]
0x18015f01a  xor     rcx, rsp; StackCookie
0x18015f01d  call    __security_check_cookie
0x18015f022  add     rsp, 60h
0x18015f026  pop     r15
0x18015f028  pop     r14
0x18015f02a  pop     r12
0x18015f02c  pop     rdi
0x18015f02d  pop     rsi
0x18015f02e  pop     rbp
0x18015f02f  pop     rbx
0x18015f030  retn
0x18015f031  lea     rcx, [r14+2]
0x18015f035  cmp     r8w, [rcx]
0x18015f039  jz      short loc_18015F07C
0x18015f03b  mov     ebp, 57h ; 'W'
0x18015f040  test    r9b, 2
0x18015f044  jz      loc_18015EFBD
0x18015f04a  mov     rax, cs:off_180264160; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f051  test    rax, rax
0x18015f054  jz      loc_18015EFBD
0x18015f05a  mov     ecx, 0C3B9h; unsigned int
0x18015f05f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f064  mov     r8, cs:off_180264160; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f06b  mov     edx, 37400h
0x18015f070  mov     rcx, cs:off_180260E18; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f077  jmp     loc_18015EFAC
0x18015f07c  add     rcx, 2
0x18015f080  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18015f087  inc     rdx
0x18015f08a  cmp     [rcx+rdx*2], bp
0x18015f08e  jnz     short loc_18015F087
0x18015f090  call    StrChrW_SYS
0x18015f095  mov     rbx, rax
0x18015f098  test    rax, rax
0x18015f09b  jnz     short loc_18015F0E1
0x18015f09d  mov     ebp, 57h ; 'W'
0x18015f0a2  test    byte ptr cs:_bidGblFlags, 2
0x18015f0a9  jz      loc_18015EFBD
0x18015f0af  mov     rax, cs:off_180264168; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f0b6  test    rax, rax
0x18015f0b9  jz      loc_18015EFBD
0x18015f0bf  mov     ecx, 0C3B9h; unsigned int
0x18015f0c4  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f0c9  mov     r8, cs:off_180264168; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f0d0  mov     edx, 3A800h
0x18015f0d5  mov     rcx, cs:off_180260E20; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f0dc  jmp     loc_18015EFAC
0x18015f0e1  call    ImplBidTouch
0x18015f0e6  mov     r9, rax; Locale
0x18015f0e9  mov     r8d, 5; MaxCount
0x18015f0ef  lea     rdx, [rbx+2]; String2
0x18015f0f3  lea     rcx, aPipe; "pipe\\"
0x18015f0fa  call    cs:__imp__wcsnicmp_l
0x18015f100  test    eax, eax
0x18015f102  jz      short loc_18015F16B
0x18015f104  call    ImplBidTouch
0x18015f109  mov     r9, rax; Locale
0x18015f10c  mov     r8d, 9; MaxCount
0x18015f112  lea     rdx, [rbx+2]; String2
0x18015f116  lea     rcx, aHostpipe; "HostPipe\\"
0x18015f11d  call    cs:__imp__wcsnicmp_l
0x18015f123  test    eax, eax
0x18015f125  jz      short loc_18015F16B
0x18015f127  mov     ebp, 57h ; 'W'
0x18015f12c  test    byte ptr cs:_bidGblFlags, 2
0x18015f133  jz      loc_18015EFBD
0x18015f139  mov     rax, cs:off_180264170; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f140  test    rax, rax
0x18015f143  jz      loc_18015EFBD
0x18015f149  mov     ecx, 0C3B9h; unsigned int
0x18015f14e  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f153  mov     r8, cs:off_180264170; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f15a  mov     edx, 3F000h
0x18015f15f  mov     rcx, cs:off_180260E28; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f166  jmp     loc_18015EFAC
0x18015f16b  call    cs:__imp_GetTickCount
0x18015f171  mov     r12d, eax
0x18015f174  mov     esi, ebp
0x18015f176  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x18015f17b  mov     [rsp+98h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18015f183  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18015f18b  xor     r9d, r9d; lpSecurityAttributes
0x18015f18e  xor     r8d, r8d; dwShareMode
0x18015f191  mov     edx, 0C0000000h; dwDesiredAccess
0x18015f196  mov     rcx, r14; lpFileName
0x18015f199  call    cs:__imp_CreateFileW
0x18015f19f  mov     [rdi+40h], rax
0x18015f1a3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015f1a7  jnz     short loc_18015F220
0x18015f1a9  nop     dword ptr [rax+00000000h]
0x18015f1b0  call    cs:__imp_GetLastError
0x18015f1b6  mov     ebx, eax
0x18015f1b8  cmp     eax, 0E7h
0x18015f1bd  jnz     loc_18015F438
0x18015f1c3  mov     edx, r15d
0x18015f1c6  sub     edx, esi; nTimeOut
0x18015f1c8  mov     rcx, r14; lpNamedPipeName
0x18015f1cb  call    cs:__imp_WaitNamedPipeW
0x18015f1d1  test    eax, eax
0x18015f1d3  jz      loc_18015F397
0x18015f1d9  call    cs:__imp_GetTickCount
0x18015f1df  mov     esi, eax
0x18015f1e1  sub     esi, r12d
0x18015f1e4  cmp     r15d, esi
0x18015f1e7  jb      loc_18015F2F7
0x18015f1ed  mov     [rsp+98h+hTemplateFile], rbp; hTemplateFile
0x18015f1f2  mov     [rsp+98h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x18015f1fa  mov     [rsp+98h+dwCreationDisposition], 3; dwCreationDisposition
0x18015f202  xor     r9d, r9d; lpSecurityAttributes
0x18015f205  xor     r8d, r8d; dwShareMode
0x18015f208  mov     edx, 0C0000000h; dwDesiredAccess
0x18015f20d  mov     rcx, r14; lpFileName
0x18015f210  call    cs:__imp_CreateFileW
0x18015f216  mov     [rdi+40h], rax
0x18015f21a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18015f21e  jz      short loc_18015F1B0
0x18015f220  mov     [rsp+98h+Mode], 2
0x18015f228  xor     r9d, r9d; lpCollectDataTimeout
0x18015f22b  xor     r8d, r8d; lpMaxCollectionCount
0x18015f22e  lea     rdx, [rsp+98h+Mode]; lpMode
0x18015f233  mov     rcx, rax; hNamedPipe
0x18015f236  call    cs:__imp_SetNamedPipeHandleState
0x18015f23c  test    eax, eax
0x18015f23e  jnz     loc_18015EFCD
0x18015f244  call    cs:__imp_GetLastError
0x18015f24a  mov     ebx, eax
0x18015f24c  test    byte ptr cs:_bidGblFlags, 2
0x18015f253  jz      short loc_18015F28F
0x18015f255  mov     rax, cs:off_1802641A8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f25c  test    rax, rax
0x18015f25f  jz      short loc_18015F28F
0x18015f261  mov     ecx, 0C3B4h; unsigned int
0x18015f266  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f26b  mov     [rsp+98h+dwFlagsAndAttributes], ebx
0x18015f26f  mov     [rsp+98h+dwCreationDisposition], eax
0x18015f273  mov     r9d, [rdi+48h]
0x18015f277  mov     r8, cs:off_1802641A8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f27e  mov     edx, 50C00h
0x18015f283  mov     rcx, cs:off_180260E60; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f28a  call    _bidTraceW
0x18015f28f  mov     r8d, 0C3B4h
0x18015f295  mov     edx, ebx
0x18015f297  mov     ecx, [rdi+48h]
0x18015f29a  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015f29f  mov     rcx, [rdi+40h]; hObject
0x18015f2a3  call    cs:__imp_CloseHandle
0x18015f2a9  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x18015f2b1  mov     eax, cs:_bidGblFlags
0x18015f2b7  and     eax, 20002h
0x18015f2bc  cmp     eax, 20002h
0x18015f2c1  jnz     loc_18015F008
0x18015f2c7  mov     rax, cs:off_1802641B0; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f2ce  test    rax, rax
0x18015f2d1  jz      loc_18015F008
0x18015f2d7  mov     r9d, ebx
0x18015f2da  mov     r8, cs:off_1802641B0; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f2e1  mov     edx, 52400h
0x18015f2e6  mov     rcx, cs:off_180260E68; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f2ed  call    _bidTraceW
0x18015f2f2  jmp     loc_18015F008
0x18015f2f7  test    byte ptr cs:_bidGblFlags, 2
0x18015f2fe  jz      short loc_18015F33E
0x18015f300  mov     rax, cs:off_180264198; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f307  test    rax, rax
0x18015f30a  jz      short loc_18015F33E
0x18015f30c  mov     ecx, 0C3DCh; unsigned int
0x18015f311  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f316  mov     [rsp+98h+dwFlagsAndAttributes], 0E7h
0x18015f31e  mov     [rsp+98h+dwCreationDisposition], eax
0x18015f322  mov     r9d, [rdi+48h]
0x18015f326  mov     r8, cs:off_180264198; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f32d  mov     edx, 4AC00h
0x18015f332  mov     rcx, cs:off_180260E50; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f339  call    _bidTraceW
0x18015f33e  mov     edx, 0E7h
0x18015f343  mov     r8d, 0C3DCh
0x18015f349  mov     ecx, [rdi+48h]
0x18015f34c  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015f351  mov     eax, cs:_bidGblFlags
0x18015f357  and     eax, 20002h
0x18015f35c  cmp     eax, 20002h
0x18015f361  jnz     short loc_18015F38D
0x18015f363  mov     rax, cs:off_1802641A0; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f36a  test    rax, rax
0x18015f36d  jz      short loc_18015F38D
0x18015f36f  mov     r9d, 0E7h
0x18015f375  mov     r8, cs:off_1802641A0; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f37c  mov     edx, 4B000h
0x18015f381  mov     rcx, cs:off_180260E58; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f388  call    _bidTraceW
0x18015f38d  mov     ebx, 5B4h
0x18015f392  jmp     loc_18015F008
0x18015f397  call    cs:__imp_GetLastError
0x18015f39d  mov     ebx, eax
0x18015f39f  test    byte ptr cs:_bidGblFlags, 2
0x18015f3a6  jz      short loc_18015F3E2
0x18015f3a8  mov     rax, cs:off_180264188; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f3af  test    rax, rax
0x18015f3b2  jz      short loc_18015F3E2
0x18015f3b4  mov     ecx, 0C3DCh; unsigned int
0x18015f3b9  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x18015f3be  mov     [rsp+98h+dwFlagsAndAttributes], ebx
0x18015f3c2  mov     [rsp+98h+dwCreationDisposition], eax
0x18015f3c6  mov     r9d, [rdi+48h]
0x18015f3ca  mov     r8, cs:off_180264188; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f3d1  mov     edx, 48800h
0x18015f3d6  mov     rcx, cs:off_180260E40; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f3dd  call    _bidTraceW
0x18015f3e2  mov     r8d, 0C3DCh
0x18015f3e8  mov     edx, ebx
0x18015f3ea  mov     ecx, [rdi+48h]
0x18015f3ed  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x18015f3f2  mov     eax, cs:_bidGblFlags
0x18015f3f8  and     eax, 20002h
0x18015f3fd  cmp     eax, 20002h
0x18015f402  jnz     loc_18015F008
0x18015f408  mov     rax, cs:off_180264190; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f40f  test    rax, rax
0x18015f412  jz      loc_18015F008
0x18015f418  mov     r9d, ebx
0x18015f41b  mov     r8, cs:off_180264190; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x18015f422  mov     edx, 48C00h
0x18015f427  mov     rcx, cs:off_180260E48; "C:\\__w\\1\\s\\Sql\\Common\\DK\\sni\\sr"...
0x18015f42e  call    _bidTraceW
0x18015f433  jmp     loc_18015F008
0x18015f438  test    byte ptr cs:_bidGblFlags, 2
0x18015f43f  jz      short loc_18015F47B
0x18015f441  mov     rax, cs:off_180264178; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x18015f448  test    rax, rax
  ... truncated ...
```
