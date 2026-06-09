# Np::OpenPipe(ushort const *,ulong)

- ea: `0x1004223f8`
- end: `0x100422941`
- name: `?OpenPipe@Np@@AEAAKPEBGK@Z`
- size: `1353`
- prototype: `unsigned int(Np *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x100422150`

## callees

- `0x1004134a0`
- `0x100419c90`
- `0x1004223f8`
- `0x10043a7c4`
- `0x10043a930`
- `0x100545d84`
- `0x1005468d8`
- `0x100546aa8`

## import_xrefs

- `KERNEL32!SetNamedPipeHandleState` at `0x1004226ed`
- `KERNEL32!SetNamedPipeHandleState` at `0x1004226ed`
- `KERNEL32!WaitNamedPipeW` at `0x10042267b`
- `KERNEL32!WaitNamedPipeW` at `0x10042267b`
- `KERNEL32!GetLastError` at `0x10042265f`
- `KERNEL32!GetLastError` at `0x1004226fb`
- `KERNEL32!GetLastError` at `0x100422832`
- `KERNEL32!GetLastError` at `0x10042265f`
- `KERNEL32!GetLastError` at `0x1004226fb`
- `KERNEL32!GetLastError` at `0x100422832`
- `KERNEL32!GetTickCount` at `0x100422651`
- `KERNEL32!GetTickCount` at `0x100422689`
- `KERNEL32!GetTickCount` at `0x100422651`
- `KERNEL32!GetTickCount` at `0x100422689`
- `KERNEL32!CreateFileW` at `0x1004226c1`
- `KERNEL32!CreateFileW` at `0x1004226c1`
- `KERNEL32!CloseHandle` at `0x100422754`
- `KERNEL32!CloseHandle` at `0x100422754`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x1004225e3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100422606`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x1004225e3`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp_l` at `0x100422606`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Np::OpenPipe(Np *this, const unsigned __int16 *a2, unsigned int a3)
{
  char v6; // cl
  unsigned int v7; // ebp
  wchar_t *v8; // r8
  __int64 v9; // rdx
  DWORD LastError; // edi
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdi
  struct localeinfo_struct *v15; // rax
  __int64 v16; // rcx
  struct localeinfo_struct *v17; // rax
  DWORD TickCount; // r12d
  DWORD v19; // r14d
  HANDLE FileW; // rax
  wchar_t *v21; // r8
  __int64 v22; // rdx
  DWORD Mode; // [rsp+98h] [rbp+10h] BYREF
  __int64 v24; // [rsp+A8h] [rbp+20h] BYREF

  v24 = -1;
  v6 = bidGblFlags;
  if ( (bidGblFlags & 0x20004) == 0x20004 )
  {
    if ( off_1005E79E8[0] )
      bidScopeEnterW(&v24, off_1005E79E8[0], *((unsigned int *)this + 11));
    v6 = bidGblFlags;
  }
  v7 = 0;
  if ( *a2 != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) != 0 && off_1005E4CC0[0] )
    {
      SniErrorIdFromStringId(0xC3B9u);
      v8 = off_1005E4CC0[0];
      v9 = 221184;
LABEL_9:
      bidTraceW(0, v9, v8, *((unsigned int *)this + 18));
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  if ( a2[1] != 92 )
  {
    v7 = 87;
    if ( (v6 & 2) != 0 && off_1005E4CC8[0] )
    {
      SniErrorIdFromStringId(0xC3B9u);
      v8 = off_1005E4CC8[0];
      v9 = 230400;
      goto LABEL_9;
    }
LABEL_10:
    SNISetLastError(*((unsigned int *)this + 18), 87, 50105);
LABEL_11:
    if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4D20[0] )
      bidTraceW(0, 347136, off_1005E4D20[0], v7);
    LastError = v7;
    goto LABEL_15;
  }
  v12 = -1;
  do
    ++v12;
  while ( a2[v12 + 2] );
  v14 = StrChrW_SYS(a2 + 2);
  if ( !v14 )
  {
    v7 = 87;
    if ( (bidGblFlags & 2) != 0 && off_1005E4CD0[0] )
    {
      SniErrorIdFromStringId(0xC3B9u);
      v8 = off_1005E4CD0[0];
      v9 = 243712;
      goto LABEL_9;
    }
    goto LABEL_10;
  }
  v15 = (struct localeinfo_struct *)ImplBidTouch(v13);
  if ( _wcsnicmp_l(L"pipe\\", (const wchar_t *)(v14 + 2), 5u, v15) )
  {
    v17 = (struct localeinfo_struct *)ImplBidTouch(v16);
    if ( _wcsnicmp_l(L"HostPipe\\", (const wchar_t *)(v14 + 2), 9u, v17) )
    {
      v7 = 87;
      if ( (bidGblFlags & 2) != 0 && off_1005E4CD8[0] )
      {
        SniErrorIdFromStringId(0xC3B9u);
        v8 = off_1005E4CD8[0];
        v9 = 0x40000;
        goto LABEL_9;
      }
      goto LABEL_10;
    }
  }
  TickCount = GetTickCount();
  v19 = 0;
  while ( 1 )
  {
    FileW = CreateFileW(a2, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
    *((_QWORD *)this + 8) = FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      Mode = 2;
      if ( SetNamedPipeHandleState(FileW, &Mode, 0, 0) )
        goto LABEL_11;
      LastError = GetLastError();
      if ( (bidGblFlags & 2) != 0 && off_1005E4D10[0] )
      {
        SniErrorIdFromStringId(0xC3B4u);
        bidTraceW(0, 334848, off_1005E4D10[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50100);
      CloseHandle(*((HANDLE *)this + 8));
      *((_QWORD *)this + 8) = -1;
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4D18[0] )
      {
        v21 = off_1005E4D18[0];
        v22 = 340992;
LABEL_43:
        bidTraceW(0, v22, v21, LastError);
        goto LABEL_15;
      }
      goto LABEL_15;
    }
    LastError = GetLastError();
    if ( LastError != 231 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4CE0[0] )
      {
        SniErrorIdFromStringId(0xC3DCu);
        bidTraceW(0, 292864, off_1005E4CE0[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), LastError, 50140);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4CE8[0] )
      {
        v21 = off_1005E4CE8[0];
        v22 = 293888;
        goto LABEL_43;
      }
      goto LABEL_15;
    }
    if ( !WaitNamedPipeW(a2, a3 - v19) )
      break;
    v19 = GetTickCount() - TickCount;
    if ( a3 < v19 )
    {
      if ( (bidGblFlags & 2) != 0 && off_1005E4D00[0] )
      {
        SniErrorIdFromStringId(0xC3DCu);
        bidTraceW(0, 310272, off_1005E4D00[0], *((unsigned int *)this + 18));
      }
      SNISetLastError(*((unsigned int *)this + 18), 231, 50140);
      if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4D08[0] )
        bidTraceW(0, 311296, off_1005E4D08[0], 231);
      LastError = 1460;
      goto LABEL_15;
    }
  }
  LastError = GetLastError();
  if ( (bidGblFlags & 2) != 0 && off_1005E4CF0[0] )
  {
    SniErrorIdFromStringId(0xC3DCu);
    bidTraceW(0, 301056, off_1005E4CF0[0], *((unsigned int *)this + 18));
  }
  SNISetLastError(*((unsigned int *)this + 18), LastError, 50140);
  if ( (bidGblFlags & 0x20002) == 0x20002 && off_1005E4CF8[0] )
  {
    v21 = off_1005E4CF8[0];
    v22 = 302080;
    goto LABEL_43;
  }
LABEL_15:
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v24);
  return LastError;
}

```

## disassembly

```asm
0x1004223f8  mov     r11, rsp
0x1004223fb  push    rbp
0x1004223fc  push    rsi
0x1004223fd  push    rdi
0x1004223fe  push    r12
0x100422400  push    r13
0x100422402  push    r14
0x100422404  push    r15
0x100422406  sub     rsp, 50h
0x10042240a  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x100422412  mov     [r11+8], rbx
0x100422416  mov     r15d, r8d
0x100422419  mov     rsi, rdx
0x10042241c  mov     rbx, rcx
0x10042241f  or      qword ptr [r11+20h], 0FFFFFFFFFFFFFFFFh
0x100422424  mov     ecx, cs:_bidGblFlags
0x10042242a  mov     eax, ecx
0x10042242c  mov     edx, 20004h
0x100422431  and     eax, edx
0x100422433  xor     r13d, r13d
0x100422436  cmp     eax, edx
0x100422438  jnz     short loc_100422467
0x10042243a  mov     rax, cs:off_1005E79E8; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x100422441  test    rax, rax
0x100422444  jz      short loc_100422461
0x100422446  mov     [r11-68h], r8d
0x10042244a  mov     r9, rsi
0x10042244d  mov     r8d, [rbx+2Ch]
0x100422451  mov     rdx, cs:off_1005E79E8; "<Np::OpenPipe|API|SNI> %u#, szPipeName:"...
0x100422458  lea     rcx, [r11+20h]
0x10042245c  call    _bidScopeEnterW
0x100422461  mov     ecx, cs:_bidGblFlags
0x100422467  mov     ebp, r13d
0x10042246a  mov     r8d, 5Ch ; '\'
0x100422470  cmp     r8w, [rsi]
0x100422474  jz      loc_100422525
0x10042247a  lea     edi, [r8-5]
0x10042247e  mov     ebp, edi
0x100422480  mov     esi, 0C3B9h
0x100422485  test    cl, 2
0x100422488  jz      short loc_1004224BC
0x10042248a  mov     rax, cs:off_1005E4CC0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422491  test    rax, rax
0x100422494  jz      short loc_1004224BC
0x100422496  mov     ecx, esi; unsigned int
0x100422498  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042249d  mov     r8, cs:off_1005E4CC0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004224a4  mov     edx, 36000h
0x1004224a9  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x1004224ad  mov     r9d, [rbx+48h]
0x1004224b1  mov     [rsp+88h+dwCreationDisposition], eax
0x1004224b5  xor     ecx, ecx
0x1004224b7  call    _bidTraceW
0x1004224bc  mov     r8d, esi
0x1004224bf  mov     edx, edi
0x1004224c1  mov     ecx, [rbx+48h]
0x1004224c4  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004224c9  mov     eax, cs:_bidGblFlags
0x1004224cf  mov     ecx, 20002h
0x1004224d4  and     eax, ecx
0x1004224d6  cmp     eax, ecx
0x1004224d8  jnz     short loc_1004224FC
0x1004224da  mov     rax, cs:off_1005E4D20; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x1004224e1  test    rax, rax
0x1004224e4  jz      short loc_1004224FC
0x1004224e6  mov     r9d, ebp
0x1004224e9  mov     r8, cs:off_1005E4D20; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x1004224f0  mov     edx, 54C00h
0x1004224f5  xor     ecx, ecx
0x1004224f7  call    _bidTraceW
0x1004224fc  mov     edi, ebp
0x1004224fe  lea     rcx, [rsp+88h+arg_18]; this
0x100422506  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x10042250b  mov     eax, edi
0x10042250d  mov     rbx, [rsp+88h+arg_0]
0x100422515  add     rsp, 50h
0x100422519  pop     r15
0x10042251b  pop     r14
0x10042251d  pop     r13
0x10042251f  pop     r12
0x100422521  pop     rdi
0x100422522  pop     rsi
0x100422523  pop     rbp
0x100422524  retn
0x100422525  cmp     r8w, [rsi+2]
0x10042252a  jz      short loc_100422569
0x10042252c  mov     edi, 57h ; 'W'
0x100422531  mov     ebp, edi
0x100422533  mov     esi, 0C3B9h
0x100422538  test    cl, 2
0x10042253b  jz      loc_1004224BC
0x100422541  mov     rax, cs:off_1005E4CC8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422548  test    rax, rax
0x10042254b  jz      loc_1004224BC
0x100422551  mov     ecx, esi; unsigned int
0x100422553  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422558  mov     r8, cs:off_1005E4CC8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x10042255f  mov     edx, 38400h
0x100422564  jmp     loc_1004224A9
0x100422569  or      rcx, 0FFFFFFFFFFFFFFFFh
0x10042256d  inc     rcx
0x100422570  cmp     [rsi+rcx*2+4], r13w
0x100422576  jnz     short loc_10042256D
0x100422578  mov     edx, ecx
0x10042257a  lea     rcx, [rsi+4]; lpsz
0x10042257e  call    StrChrW_SYS
0x100422583  mov     rdi, rax
0x100422586  test    rax, rax
0x100422589  jnz     short loc_1004225CA
0x10042258b  lea     edi, [rax+57h]
0x10042258e  mov     ebp, edi
0x100422590  mov     esi, 0C3B9h
0x100422595  test    byte ptr cs:_bidGblFlags, 2
0x10042259c  jz      loc_1004224BC
0x1004225a2  mov     rax, cs:off_1005E4CD0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004225a9  test    rax, rax
0x1004225ac  jz      loc_1004224BC
0x1004225b2  mov     ecx, esi; unsigned int
0x1004225b4  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004225b9  mov     r8, cs:off_1005E4CD0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004225c0  mov     edx, 3B800h
0x1004225c5  jmp     loc_1004224A9
0x1004225ca  call    ImplBidTouch
0x1004225cf  mov     r9, rax; Locale
0x1004225d2  mov     r8d, 5; MaxCount
0x1004225d8  lea     rdx, [rdi+2]; String2
0x1004225dc  lea     rcx, aPipe; "pipe\\"
0x1004225e3  call    cs:__imp__wcsnicmp_l
0x1004225e9  test    eax, eax
0x1004225eb  jz      short loc_100422651
0x1004225ed  call    ImplBidTouch
0x1004225f2  mov     r9, rax; Locale
0x1004225f5  mov     r8d, 9; MaxCount
0x1004225fb  lea     rdx, [rdi+2]; String2
0x1004225ff  lea     rcx, aHostpipe; "HostPipe\\"
0x100422606  call    cs:__imp__wcsnicmp_l
0x10042260c  test    eax, eax
0x10042260e  jz      short loc_100422651
0x100422610  mov     edi, 57h ; 'W'
0x100422615  mov     ebp, edi
0x100422617  mov     esi, 0C3B9h
0x10042261c  test    byte ptr cs:_bidGblFlags, 2
0x100422623  jz      loc_1004224BC
0x100422629  mov     rax, cs:off_1005E4CD8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422630  test    rax, rax
0x100422633  jz      loc_1004224BC
0x100422639  mov     ecx, esi; unsigned int
0x10042263b  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422640  mov     r8, cs:off_1005E4CD8; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422647  mov     edx, 40000h
0x10042264c  jmp     loc_1004224A9
0x100422651  call    cs:__imp_GetTickCount
0x100422657  mov     r12d, eax
0x10042265a  mov     r14d, r13d
0x10042265d  jmp     short loc_10042269E
0x10042265f  call    cs:__imp_GetLastError
0x100422665  mov     edi, eax
0x100422667  cmp     eax, 0E7h
0x10042266c  jnz     loc_1004228BD
0x100422672  mov     edx, r15d
0x100422675  sub     edx, r14d; nTimeOut
0x100422678  mov     rcx, rsi; lpNamedPipeName
0x10042267b  call    cs:__imp_WaitNamedPipeW
0x100422681  test    eax, eax
0x100422683  jz      loc_100422832
0x100422689  call    cs:__imp_GetTickCount
0x10042268f  mov     r14d, eax
0x100422692  sub     r14d, r12d
0x100422695  cmp     r15d, r14d
0x100422698  jb      loc_10042279F
0x10042269e  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x1004226a3  mov     [rsp+88h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1004226ab  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x1004226b3  xor     r9d, r9d; lpSecurityAttributes
0x1004226b6  xor     r8d, r8d; dwShareMode
0x1004226b9  mov     edx, 0C0000000h; dwDesiredAccess
0x1004226be  mov     rcx, rsi; lpFileName
0x1004226c1  call    cs:__imp_CreateFileW
0x1004226c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1004226cb  mov     [rbx+40h], rax
0x1004226cf  jz      short loc_10042265F
0x1004226d1  mov     [rsp+88h+Mode], 2
0x1004226dc  xor     r9d, r9d; lpCollectDataTimeout
0x1004226df  xor     r8d, r8d; lpMaxCollectionCount
0x1004226e2  lea     rdx, [rsp+88h+Mode]; lpMode
0x1004226ea  mov     rcx, rax; hNamedPipe
0x1004226ed  call    cs:__imp_SetNamedPipeHandleState
0x1004226f3  test    eax, eax
0x1004226f5  jnz     loc_1004224C9
0x1004226fb  call    cs:__imp_GetLastError
0x100422701  mov     edi, eax
0x100422703  mov     esi, 0C3B4h
0x100422708  test    byte ptr cs:_bidGblFlags, 2
0x10042270f  jz      short loc_100422743
0x100422711  mov     rax, cs:off_1005E4D10; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422718  test    rax, rax
0x10042271b  jz      short loc_100422743
0x10042271d  mov     ecx, esi; unsigned int
0x10042271f  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x100422724  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x100422728  mov     [rsp+88h+dwCreationDisposition], eax
0x10042272c  mov     r9d, [rbx+48h]
0x100422730  mov     r8, cs:off_1005E4D10; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x100422737  mov     edx, 51C00h
0x10042273c  xor     ecx, ecx
0x10042273e  call    _bidTraceW
0x100422743  mov     r8d, esi
0x100422746  mov     edx, edi
0x100422748  mov     ecx, [rbx+48h]
0x10042274b  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422750  mov     rcx, [rbx+40h]; hObject
0x100422754  call    cs:__imp_CloseHandle
0x10042275a  or      qword ptr [rbx+40h], 0FFFFFFFFFFFFFFFFh
0x10042275f  mov     eax, cs:_bidGblFlags
0x100422765  mov     ecx, 20002h
0x10042276a  and     eax, ecx
0x10042276c  cmp     eax, ecx
0x10042276e  jnz     loc_1004224FE
0x100422774  mov     rax, cs:off_1005E4D18; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x10042277b  test    rax, rax
0x10042277e  jz      loc_1004224FE
0x100422784  mov     r8, cs:off_1005E4D18; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x10042278b  mov     edx, 53400h
0x100422790  mov     r9d, edi
0x100422793  xor     ecx, ecx
0x100422795  call    _bidTraceW
0x10042279a  jmp     loc_1004224FE
0x10042279f  mov     esi, 0C3DCh
0x1004227a4  test    byte ptr cs:_bidGblFlags, 2
0x1004227ab  jz      short loc_1004227E3
0x1004227ad  mov     rax, cs:off_1005E4D00; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004227b4  test    rax, rax
0x1004227b7  jz      short loc_1004227E3
0x1004227b9  mov     ecx, esi; unsigned int
0x1004227bb  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x1004227c0  mov     [rsp+88h+dwFlagsAndAttributes], 0E7h
0x1004227c8  mov     [rsp+88h+dwCreationDisposition], eax
0x1004227cc  mov     r9d, [rbx+48h]
0x1004227d0  mov     r8, cs:off_1005E4D00; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004227d7  mov     edx, 4BC00h
0x1004227dc  xor     ecx, ecx
0x1004227de  call    _bidTraceW
0x1004227e3  mov     r8d, esi
0x1004227e6  mov     esi, 0E7h
0x1004227eb  mov     edx, esi
0x1004227ed  mov     ecx, [rbx+48h]
0x1004227f0  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x1004227f5  mov     eax, cs:_bidGblFlags
0x1004227fb  mov     ecx, 20002h
0x100422800  and     eax, ecx
0x100422802  cmp     eax, ecx
0x100422804  jnz     short loc_100422828
0x100422806  mov     rax, cs:off_1005E4D08; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x10042280d  test    rax, rax
0x100422810  jz      short loc_100422828
0x100422812  mov     r9d, esi
0x100422815  mov     r8, cs:off_1005E4D08; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x10042281c  mov     edx, 4C000h
0x100422821  xor     ecx, ecx
0x100422823  call    _bidTraceW
0x100422828  mov     edi, 5B4h
0x10042282d  jmp     loc_1004224FE
0x100422832  call    cs:__imp_GetLastError
0x100422838  mov     edi, eax
0x10042283a  mov     esi, 0C3DCh
0x10042283f  test    byte ptr cs:_bidGblFlags, 2
0x100422846  jz      short loc_10042287A
0x100422848  mov     rax, cs:off_1005E4CF0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x10042284f  test    rax, rax
0x100422852  jz      short loc_10042287A
0x100422854  mov     ecx, esi; unsigned int
0x100422856  call    ?SniErrorIdFromStringId@@YAKK@Z; SniErrorIdFromStringId(ulong)
0x10042285b  mov     [rsp+88h+dwFlagsAndAttributes], edi
0x10042285f  mov     [rsp+88h+dwCreationDisposition], eax
0x100422863  mov     r9d, [rbx+48h]
0x100422867  mov     r8, cs:off_1005E4CF0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x10042286e  mov     edx, 49800h
0x100422873  xor     ecx, ecx
0x100422875  call    _bidTraceW
0x10042287a  mov     r8d, esi
0x10042287d  mov     edx, edi
0x10042287f  mov     ecx, [rbx+48h]
0x100422882  call    ?SNISetLastError@@YAXW4ProviderNum@@KK@Z; SNISetLastError(ProviderNum,ulong,ulong)
0x100422887  mov     eax, cs:_bidGblFlags
0x10042288d  mov     ecx, 20002h
0x100422892  and     eax, ecx
0x100422894  cmp     eax, ecx
0x100422896  jnz     loc_1004224FE
0x10042289c  mov     rax, cs:off_1005E4CF8; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x1004228a3  test    rax, rax
0x1004228a6  jz      loc_1004224FE
0x1004228ac  mov     r8, cs:off_1005E4CF8; "<Np::OpenPipe|RET|SNI> %d{WINERR}\n"
0x1004228b3  mov     edx, 49C00h
0x1004228b8  jmp     loc_100422790
0x1004228bd  mov     esi, 0C3DCh
0x1004228c2  test    byte ptr cs:_bidGblFlags, 2
0x1004228c9  jz      short loc_1004228FD
0x1004228cb  mov     rax, cs:off_1005E4CE0; "<Np::OpenPipe|ERR|SNI> ProviderNum: %d{"...
0x1004228d2  test    rax, rax
0x1004228d5  jz      short loc_1004228FD
  ... truncated ...
```
