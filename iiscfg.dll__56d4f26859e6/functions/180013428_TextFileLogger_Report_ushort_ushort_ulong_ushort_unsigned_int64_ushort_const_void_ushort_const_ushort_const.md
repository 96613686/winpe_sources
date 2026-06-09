# TextFileLogger::Report(ushort,ushort,ulong,ushort,unsigned __int64,ushort const * *,void *,ushort const *,ushort const *)

- ea: `0x180013428`
- end: `0x1800139b2`
- name: `?Report@TextFileLogger@@QEAAXGGKG_KPEAPEBGPEAXPEBG3@Z`
- size: `1418`
- prototype: `void __fastcall(TextFileLogger *this, unsigned __int16, unsigned __int16, DWORD, unsigned __int16, unsigned __int64, va_list *Arguments, unsigned __int8 *, WCHAR *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x1800125d0`
- `0x1800139c0`

## callees

- `0x180001b78`
- `0x1800117d4`
- `0x180013140`
- `0x180013428`
- `0x180013c78`
- `0x18002e110`
- `0x18002e1d0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1800137a0`
- `msvcrt!swprintf_s` at `0x18001383b`
- `msvcrt!swprintf_s` at `0x18001393e`
- `msvcrt!swprintf_s` at `0x1800137a0`
- `msvcrt!swprintf_s` at `0x18001383b`
- `msvcrt!swprintf_s` at `0x18001393e`
- `msvcrt!_snwprintf_s` at `0x1800135a5`
- `msvcrt!_snwprintf_s` at `0x18001363e`
- `msvcrt!_snwprintf_s` at `0x1800136b6`
- `msvcrt!_snwprintf_s` at `0x180013760`
- `msvcrt!_snwprintf_s` at `0x1800135a5`
- `msvcrt!_snwprintf_s` at `0x18001363e`
- `msvcrt!_snwprintf_s` at `0x1800136b6`
- `msvcrt!_snwprintf_s` at `0x180013760`
- `KERNEL32!lstrlenW` at `0x180013864`
- `KERNEL32!lstrlenW` at `0x180013864`
- `KERNEL32!GetLocalTime` at `0x1800135dd`
- `KERNEL32!GetLocalTime` at `0x1800135dd`
- `KERNEL32!WriteFile` at `0x1800135ca`
- `KERNEL32!WriteFile` at `0x180013663`
- `KERNEL32!WriteFile` at `0x1800136de`
- `KERNEL32!WriteFile` at `0x180013789`
- `KERNEL32!WriteFile` at `0x1800137bc`
- `KERNEL32!WriteFile` at `0x180013857`
- `KERNEL32!WriteFile` at `0x180013880`
- `KERNEL32!WriteFile` at `0x1800138a1`
- `KERNEL32!WriteFile` at `0x1800138c7`
- `KERNEL32!WriteFile` at `0x1800138e8`
- `KERNEL32!WriteFile` at `0x180013919`
- `KERNEL32!WriteFile` at `0x18001395a`
- `KERNEL32!WriteFile` at `0x180013984`
- `KERNEL32!WriteFile` at `0x1800135ca`
- `KERNEL32!WriteFile` at `0x180013663`
- `KERNEL32!WriteFile` at `0x1800136de`
- `KERNEL32!WriteFile` at `0x180013789`
- `KERNEL32!WriteFile` at `0x1800137bc`
- `KERNEL32!WriteFile` at `0x180013857`
- `KERNEL32!WriteFile` at `0x180013880`
- `KERNEL32!WriteFile` at `0x1800138a1`
- `KERNEL32!WriteFile` at `0x1800138c7`
- `KERNEL32!WriteFile` at `0x1800138e8`
- `KERNEL32!WriteFile` at `0x180013919`
- `KERNEL32!WriteFile` at `0x18001395a`
- `KERNEL32!WriteFile` at `0x180013984`
- `KERNEL32!SetFilePointer` at `0x180013582`
- `KERNEL32!SetFilePointer` at `0x180013582`
- `KERNEL32!CloseHandle` at `0x180013994`
- `KERNEL32!CloseHandle` at `0x180013994`
- `KERNEL32!FormatMessageW` at `0x180013710`
- `KERNEL32!FormatMessageW` at `0x1800137f7`
- `KERNEL32!FormatMessageW` at `0x180013710`
- `KERNEL32!FormatMessageW` at `0x1800137f7`
- `IisRTL!PuDbgPrint` at `0x1800134da`
- `IisRTL!PuDbgPrint` at `0x180013511`
- `IisRTL!PuDbgPrint` at `0x1800134da`
- `IisRTL!PuDbgPrint` at `0x180013511`

## string_xrefs

- `0x180013505`: `inetsrv\iis\mb\config\src\shared\util\textfilelogger.cpp`
- `0x1800134d3`: `inetsrv\iis\mb\config\src\inc\TextFileLogger.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10 #try_helpers=1
void __fastcall TextFileLogger::Report(
        TextFileLogger *this,
        unsigned __int16 a2,
        unsigned __int16 a3,
        DWORD a4,
        unsigned __int16 a5,
        unsigned __int64 a6,
        va_list *Arguments,
        unsigned __int8 *a8,
        WCHAR *a9,
        const unsigned __int16 *a10)
{
  WCHAR *v11; // rdi
  DWORD v13; // r12d
  int v14; // r14d
  void *v15; // rcx
  int v16; // eax
  int v17; // eax
  const wchar_t *v18; // rax
  int v19; // eax
  void *v20; // rcx
  DWORD v21; // r14d
  unsigned __int64 v22; // rax
  const wchar_t *v23; // r9
  int v24; // eax
  void *v25; // rcx
  int v26; // eax
  const unsigned __int16 *v27; // rdx
  signed int v28; // eax
  unsigned __int64 v29; // rcx
  int v30; // eax
  __int64 i; // rdi
  int v32; // eax
  unsigned __int8 *v33; // r14
  unsigned int j; // edi
  int v35; // eax
  void *v36; // rcx
  LPOVERLAPPED lpOverlappeda; // [rsp+20h] [rbp-E0h]
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesWritten; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 *v40; // [rsp+68h] [rbp-98h]
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  WCHAR v42[80]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t Buffer[2047]; // [rsp+120h] [rbp+20h] BYREF
  __int16 v44; // [rsp+111Eh] [rbp+101Eh]

  v11 = a9;
  v40 = a8;
  v13 = a3;
  v14 = a2;
  NumberOfBytesWritten = 0;
  if ( CSafeAutoCriticalSection::Lock((CSafeAutoCriticalSection *)&TextFileLogger::_cs) )
  {
    if ( (g_dwDebugFlags & 0xF) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\inc\\TextFileLogger.h",
        235,
        "TextFileLogger::Lock",
        "Could not lock critical section\n");
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
          282,
          "TextFileLogger::Report",
          "Couldn't obtain critical section.  Not logging.\n");
    }
    return;
  }
  if ( *((_QWORD *)this + 3) == -1 )
    TextFileLogger::InitFile(this);
  v15 = (void *)*((_QWORD *)this + 3);
  if ( v15 == (void *)-1LL )
  {
    TextFileLogger::Unlock((TextFileLogger *)0xFFFFFFFFFFFFFFFFLL);
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\mb\\config\\src\\shared\\util\\textfilelogger.cpp",
        295,
        "TextFileLogger::Report",
        "Not logging due to error\n");
    return;
  }
  SetFilePointer(v15, 0, 0, 2u);
  v16 = _snwprintf_s(
          Buffer,
          0x800u,
          0x7FFu,
          L"===================== %s =====================\r\n",
          *((_QWORD *)this + 2));
  v44 = 0;
  WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v16, &NumberOfBytesWritten, 0);
  SystemTime = 0;
  GetLocalTime(&SystemTime);
  LODWORD(lpOverlappeda) = SystemTime.wMonth;
  v17 = _snwprintf_s(
          Buffer,
          0x800u,
          0x7FFu,
          L"Time:  %d/%d/%d  %02d:%02d:%02d.%03d\r\n",
          lpOverlappeda,
          SystemTime.wDay,
          SystemTime.wYear,
          SystemTime.wHour,
          SystemTime.wMinute,
          SystemTime.wSecond,
          SystemTime.wMilliseconds);
  v44 = 0;
  WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v17, &NumberOfBytesWritten, 0);
  switch ( v14 )
  {
    case 1:
      v18 = L"Error";
      break;
    case 2:
      v18 = L"Warning";
      break;
    case 4:
      v18 = L"Information";
      break;
    default:
      v18 = L"Unknown Type";
      break;
  }
  v19 = _snwprintf_s(Buffer, 0x800u, 0x7FFu, L"Type: %s\r\n", v18);
  v20 = (void *)*((_QWORD *)this + 3);
  v21 = v19;
  v44 = 0;
  WriteFile(v20, Buffer, 2 * v19, &NumberOfBytesWritten, 0);
  if ( a9 )
  {
    v22 = -1;
    do
      ++v22;
    while ( a9[v22] );
    if ( v22 > 0x50 )
      goto LABEL_25;
  }
  else
  {
    v21 = FormatMessageW(0x28FFu, *((LPCVOID *)this + 4), v13, 0, v42, 0x50u, Arguments);
    v11 = v42;
  }
  if ( !v21 )
  {
LABEL_25:
    LODWORD(lpOverlapped) = v13;
    v23 = L"Category: %hd\r\n";
    goto LABEL_26;
  }
  lpOverlapped = (LPOVERLAPPED)v11;
  v23 = L"Category: %s\r\n";
LABEL_26:
  v24 = _snwprintf_s(Buffer, 0x800u, 0x7FFu, v23, lpOverlapped);
  v25 = (void *)*((_QWORD *)this + 3);
  v44 = 0;
  WriteFile(v25, Buffer, 2 * v24, &NumberOfBytesWritten, 0);
  v26 = swprintf_s(Buffer, 0x800u, L"Event ID: %d\r\n", (unsigned __int16)a4);
  WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v26, &NumberOfBytesWritten, 0);
  v27 = a10;
  if ( !a10 )
    v27 = (const unsigned __int16 *)*((_QWORD *)this + 4);
  v28 = FormatMessageW(a10 != 0 ? 9471 : 10495, v27, a4, 0, Buffer, 0x800u, Arguments);
  if ( (unsigned __int64)v28 < 0x800 )
  {
    v29 = v28;
    if ( v29 >= 2048 )
      _report_rangecheckfailure();
  }
  else
  {
    v29 = 2047;
  }
  Buffer[v29] = 0;
  if ( v28 )
  {
    WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v28, &NumberOfBytesWritten, 0);
    WriteFile(*((HANDLE *)this + 3), L"\r\n", 4u, &NumberOfBytesWritten, 0);
  }
  else
  {
    v30 = swprintf_s(
            Buffer,
            0x800u,
            L"The description for this event could not be found. It contains the following insertion string(s):\r\n");
    WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v30, &NumberOfBytesWritten, 0);
    for ( i = 0; i != 5; ++i )
    {
      v32 = lstrlenW((LPCWSTR)Arguments[i]);
      WriteFile(*((HANDLE *)this + 3), Arguments[i], 2 * v32, &NumberOfBytesWritten, 0);
      WriteFile(*((HANDLE *)this + 3), L"\r\n", 4u, &NumberOfBytesWritten, 0);
    }
  }
  if ( a6 )
  {
    WriteFile(*((HANDLE *)this + 3), L"Raw data: ", 0x14u, &NumberOfBytesWritten, 0);
    v33 = v40;
    for ( j = 0; j < a6; ++j )
    {
      v35 = swprintf_s(Buffer, 0x800u, L"%02x ", v33[j]);
      WriteFile(*((HANDLE *)this + 3), Buffer, 2 * v35, &NumberOfBytesWritten, 0);
    }
    WriteFile(*((HANDLE *)this + 3), L"\r\n", 4u, &NumberOfBytesWritten, 0);
  }
  v36 = (void *)*((_QWORD *)this + 3);
  if ( v36 != (void *)-1LL )
  {
    CloseHandle(v36);
    *((_QWORD *)this + 3) = -1;
  }
  TextFileLogger::Unlock((TextFileLogger *)v36);
}

```

## disassembly

```asm
0x180013428  mov     [rsp-8+arg_8], rbx
0x18001342d  push    rbp
0x18001342e  push    rsi
0x18001342f  push    rdi
0x180013430  push    r12
0x180013432  push    r13
0x180013434  push    r14
0x180013436  push    r15
0x180013438  lea     rbp, [rsp-1030h]
0x180013440  mov     eax, 1130h
0x180013445  call    _alloca_probe
0x18001344a  sub     rsp, rax
0x18001344d  mov     rax, cs:__security_cookie
0x180013454  xor     rax, rsp
0x180013457  mov     [rbp+1060h+var_40], rax
0x18001345e  mov     rax, [rbp+1060h+arg_38]
0x180013465  mov     rbx, rcx
0x180013468  mov     r15, [rbp+1060h+arg_30]
0x18001346f  lea     rcx, ?_cs@TextFileLogger@@0VCSafeAutoCriticalSection@@A; this
0x180013476  mov     rdi, [rbp+1060h+arg_40]
0x18001347d  mov     r13d, r9d
0x180013480  mov     rsi, [rbp+1060h+arg_48]
0x180013487  mov     [rsp+1160h+var_10F8], rax
0x18001348c  movzx   r12d, r8w
0x180013490  movzx   r14d, dx
0x180013494  mov     [rsp+1160h+NumberOfBytesWritten], 0
0x18001349c  call    ?Lock@CSafeAutoCriticalSection@@QEAAKXZ; CSafeAutoCriticalSection::Lock(void)
0x1800134a1  test    eax, eax
0x1800134a3  jz      loc_180013541
0x1800134a9  mov     eax, cs:g_dwDebugFlags
0x1800134af  test    al, 0Fh
0x1800134b1  jz      short loc_180013517
0x1800134b3  mov     rcx, cs:g_pDebug
0x1800134ba  lea     rax, aCouldNotLockCr; "Could not lock critical section\n"
0x1800134c1  lea     r9, aTextfilelogger_0; "TextFileLogger::Lock"
0x1800134c8  mov     [rsp+1160h+lpOverlapped], rax
0x1800134cd  mov     r8d, 0EBh
0x1800134d3  lea     rdx, aInetsrvIisMbCo_8; "inetsrv\\iis\\mb\\config\\src\\inc\\Tex"...
0x1800134da  call    cs:__imp_PuDbgPrint
0x1800134e0  mov     eax, cs:g_dwDebugFlags
0x1800134e6  test    al, 0Fh
0x1800134e8  jz      short loc_180013517
0x1800134ea  lea     rax, aCouldnTObtainC; "Couldn't obtain critical section.  Not "...
0x1800134f1  mov     r8d, 11Ah
0x1800134f7  mov     rcx, cs:g_pDebug
0x1800134fe  lea     r9, aTextfilelogger_3; "TextFileLogger::Report"
0x180013505  lea     rdx, aInetsrvIisMbCo_2; "inetsrv\\iis\\mb\\config\\src\\shared\\"...
0x18001350c  mov     [rsp+1160h+lpOverlapped], rax
0x180013511  call    cs:__imp_PuDbgPrint
0x180013517  mov     rcx, [rbp+1060h+var_40]
0x18001351e  xor     rcx, rsp; StackCookie
0x180013521  call    __security_check_cookie
0x180013526  mov     rbx, [rsp+1160h+arg_8]
0x18001352e  add     rsp, 1130h
0x180013535  pop     r15
0x180013537  pop     r14
0x180013539  pop     r13
0x18001353b  pop     r12
0x18001353d  pop     rdi
0x18001353e  pop     rsi
0x18001353f  pop     rbp
0x180013540  retn
0x180013541  cmp     qword ptr [rbx+18h], 0FFFFFFFFFFFFFFFFh
0x180013546  jnz     short loc_180013550
0x180013548  mov     rcx, rbx; this
0x18001354b  call    ?InitFile@TextFileLogger@@AEAAXXZ; TextFileLogger::InitFile(void)
0x180013550  mov     rcx, [rbx+18h]; this
0x180013554  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013558  jnz     short loc_180013577
0x18001355a  call    ?Unlock@TextFileLogger@@AEAAJXZ; TextFileLogger::Unlock(void)
0x18001355f  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180013566  jz      short loc_180013517
0x180013568  lea     rax, aNotLoggingDueT; "Not logging due to error\n"
0x18001356f  mov     r8d, 127h
0x180013575  jmp     short loc_1800134F7
0x180013577  mov     r9d, 2; dwMoveMethod
0x18001357d  xor     r8d, r8d; lpDistanceToMoveHigh
0x180013580  xor     edx, edx; lDistanceToMove
0x180013582  call    cs:__imp_SetFilePointer
0x180013588  mov     rax, [rbx+10h]
0x18001358c  lea     r9, aS; "===================== %s =============="...
0x180013593  mov     edx, 800h; BufferCount
0x180013598  mov     [rsp+1160h+lpOverlapped], rax
0x18001359d  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x1800135a1  lea     r8d, [rdx-1]; MaxCount
0x1800135a5  call    cs:__imp__snwprintf_s
0x1800135ab  xor     ecx, ecx
0x1800135ad  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800135b2  mov     [rbp+1060h+var_42], cx
0x1800135b9  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x1800135bd  mov     [rsp+1160h+lpOverlapped], rcx; lpOverlapped
0x1800135c2  mov     rcx, [rbx+18h]; hFile
0x1800135c6  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x1800135ca  call    cs:__imp_WriteFile
0x1800135d0  xorps   xmm0, xmm0
0x1800135d3  lea     rcx, [rsp+1160h+SystemTime]; lpSystemTime
0x1800135d8  movups  xmmword ptr [rsp+1160h+SystemTime.wYear], xmm0
0x1800135dd  call    cs:__imp_GetLocalTime
0x1800135e3  movzx   ecx, [rsp+1160h+SystemTime.wSecond]
0x1800135e8  movzx   edx, [rsp+1160h+SystemTime.wMinute]
0x1800135ed  movzx   r8d, [rsp+1160h+SystemTime.wHour]
0x1800135f3  movzx   r9d, [rsp+1160h+SystemTime.wYear]
0x1800135f9  movzx   eax, [rsp+1160h+SystemTime.wMilliseconds]
0x1800135fe  movzx   r10d, [rsp+1160h+SystemTime.wDay]
0x180013604  movzx   r11d, [rsp+1160h+SystemTime.wMonth]
0x18001360a  mov     [rsp+1160h+var_1110], eax
0x18001360e  mov     [rsp+1160h+var_1118], ecx
0x180013612  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x180013616  mov     [rsp+1160h+var_1120], edx
0x18001361a  mov     edx, 800h; BufferCount
0x18001361f  mov     [rsp+1160h+var_1128], r8d
0x180013624  mov     dword ptr [rsp+1160h+Arguments], r9d
0x180013629  lea     r9, aTimeDDD02d02d0; "Time:  %d/%d/%d  %02d:%02d:%02d.%03d\r"...
0x180013630  mov     [rsp+1160h+nSize], r10d
0x180013635  lea     r8d, [rdx-1]; MaxCount
0x180013639  mov     dword ptr [rsp+1160h+lpOverlapped], r11d
0x18001363e  call    cs:__imp__snwprintf_s
0x180013644  xor     ecx, ecx
0x180013646  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001364b  mov     [rbp+1060h+var_42], cx
0x180013652  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x180013656  mov     [rsp+1160h+lpOverlapped], rcx; lpOverlapped
0x18001365b  mov     rcx, [rbx+18h]; hFile
0x18001365f  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180013663  call    cs:__imp_WriteFile
0x180013669  mov     ecx, r14d
0x18001366c  sub     ecx, 1
0x18001366f  jz      short loc_180013696
0x180013671  sub     ecx, 1
0x180013674  jz      short loc_18001368D
0x180013676  cmp     ecx, 2
0x180013679  jz      short loc_180013684
0x18001367b  lea     rax, aUnknownType; "Unknown Type"
0x180013682  jmp     short loc_18001369D
0x180013684  lea     rax, aInformation; "Information"
0x18001368b  jmp     short loc_18001369D
0x18001368d  lea     rax, aWarning; "Warning"
0x180013694  jmp     short loc_18001369D
0x180013696  lea     rax, aError; "Error"
0x18001369d  mov     edx, 800h; BufferCount
0x1800136a2  mov     [rsp+1160h+lpOverlapped], rax
0x1800136a7  lea     r9, aTypeS; "Type: %s\r\n"
0x1800136ae  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x1800136b2  lea     r8d, [rdx-1]; MaxCount
0x1800136b6  call    cs:__imp__snwprintf_s
0x1800136bc  mov     rcx, [rbx+18h]; hFile
0x1800136c0  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800136c5  mov     r14d, eax
0x1800136c8  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x1800136cc  xor     eax, eax
0x1800136ce  mov     [rbp+1060h+var_42], ax
0x1800136d5  mov     [rsp+1160h+lpOverlapped], rax; lpOverlapped
0x1800136da  lea     r8d, [r14+r14]; nNumberOfBytesToWrite
0x1800136de  call    cs:__imp_WriteFile
0x1800136e4  xor     ecx, ecx
0x1800136e6  test    rdi, rdi
0x1800136e9  jnz     short loc_18001371F
0x1800136eb  mov     rdx, [rbx+20h]; lpSource
0x1800136ef  lea     rax, [rbp+1060h+var_10E0]
0x1800136f3  mov     [rsp+1160h+Arguments], r15; Arguments
0x1800136f8  mov     r8d, r12d; dwMessageId
0x1800136fb  mov     [rsp+1160h+nSize], 50h ; 'P'; nSize
0x180013703  xor     r9d, r9d; dwLanguageId
0x180013706  mov     ecx, 28FFh; dwFlags
0x18001370b  mov     [rsp+1160h+lpOverlapped], rax; lpBuffer
0x180013710  call    cs:__imp_FormatMessageW
0x180013716  mov     r14d, eax
0x180013719  lea     rdi, [rbp+1060h+var_10E0]
0x18001371d  jmp     short loc_180013732
0x18001371f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013723  inc     rax
0x180013726  cmp     [rdi+rax*2], cx
0x18001372a  jnz     short loc_180013723
0x18001372c  cmp     rax, 50h ; 'P'
0x180013730  ja      short loc_180013745
0x180013732  test    r14d, r14d
0x180013735  jz      short loc_180013745
0x180013737  mov     [rsp+1160h+lpOverlapped], rdi
0x18001373c  lea     r9, aCategoryS; "Category: %s\r\n"
0x180013743  jmp     short loc_180013751
0x180013745  mov     dword ptr [rsp+1160h+lpOverlapped], r12d
0x18001374a  lea     r9, aCategoryHd; "Category: %hd\r\n"
0x180013751  mov     edi, 800h
0x180013756  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x18001375a  mov     edx, edi; BufferCount
0x18001375c  lea     r8d, [rdi-1]; MaxCount
0x180013760  call    cs:__imp__snwprintf_s
0x180013766  mov     rcx, [rbx+18h]; hFile
0x18001376a  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001376f  mov     r8d, eax
0x180013772  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x180013776  xor     r12d, r12d
0x180013779  add     r8d, r8d; nNumberOfBytesToWrite
0x18001377c  mov     [rbp+1060h+var_42], r12w
0x180013784  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x180013789  call    cs:__imp_WriteFile
0x18001378f  movzx   r9d, r13w
0x180013793  lea     r8, aEventIdD; "Event ID: %d\r\n"
0x18001379a  mov     edx, edi; BufferCount
0x18001379c  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x1800137a0  call    cs:__imp_swprintf_s
0x1800137a6  mov     rcx, [rbx+18h]; hFile
0x1800137aa  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800137af  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x1800137b3  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x1800137b8  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x1800137bc  call    cs:__imp_WriteFile
0x1800137c2  mov     rdx, rsi
0x1800137c5  test    rsi, rsi
0x1800137c8  jnz     short loc_1800137CE
0x1800137ca  mov     rdx, [rbx+20h]; lpSource
0x1800137ce  mov     [rsp+1160h+Arguments], r15; Arguments
0x1800137d3  lea     rax, [rbp+1060h+Buffer]
0x1800137d7  neg     rsi
0x1800137da  mov     [rsp+1160h+nSize], edi; nSize
0x1800137de  mov     r8d, r13d; dwMessageId
0x1800137e1  mov     [rsp+1160h+lpOverlapped], rax; lpBuffer
0x1800137e6  sbb     ecx, ecx
0x1800137e8  xor     r9d, r9d; dwLanguageId
0x1800137eb  and     ecx, 0FFFFFC00h
0x1800137f1  add     ecx, 28FFh; dwFlags
0x1800137f7  call    cs:__imp_FormatMessageW
0x1800137fd  movsxd  r8, eax
0x180013800  mov     rcx, r8
0x180013803  cmp     r8, rdi
0x180013806  jb      short loc_18001380F
0x180013808  mov     ecx, 0FFEh
0x18001380d  jmp     short loc_18001381F
0x18001380f  add     rcx, rcx
0x180013812  cmp     rcx, 1000h
0x180013819  jnb     loc_1800139AC
0x18001381f  mov     [rbp+rcx+1060h+Buffer], r12w
0x180013825  test    eax, eax
0x180013827  jnz     loc_1800138B2
0x18001382d  lea     r8, aTheDescription_0; "The description for this event could no"...
0x180013834  mov     rdx, rdi; BufferCount
0x180013837  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x18001383b  call    cs:__imp_swprintf_s
0x180013841  mov     rcx, [rbx+18h]; hFile
0x180013845  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001384a  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x18001384e  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x180013853  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180013857  call    cs:__imp_WriteFile
0x18001385d  mov     rdi, r12
0x180013860  mov     rcx, [r15+rdi*8]; lpString
0x180013864  call    cs:__imp_lstrlenW
0x18001386a  mov     rdx, [r15+rdi*8]; lpBuffer
0x18001386e  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180013873  mov     rcx, [rbx+18h]; hFile
0x180013877  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x18001387c  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x180013880  call    cs:__imp_WriteFile
0x180013886  mov     rcx, [rbx+18h]; hFile
0x18001388a  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001388f  mov     r8d, 4; nNumberOfBytesToWrite
0x180013895  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x18001389a  lea     rdx, asc_1800347E8; "\r\n"
0x1800138a1  call    cs:__imp_WriteFile
0x1800138a7  inc     rdi
0x1800138aa  cmp     rdi, 5
0x1800138ae  jnz     short loc_180013860
0x1800138b0  jmp     short loc_1800138EE
0x1800138b2  mov     rcx, [rbx+18h]; hFile
0x1800138b6  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800138bb  add     r8d, r8d; nNumberOfBytesToWrite
0x1800138be  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x1800138c3  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x1800138c7  call    cs:__imp_WriteFile
0x1800138cd  mov     rcx, [rbx+18h]; hFile
0x1800138d1  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800138d6  mov     r8d, 4; nNumberOfBytesToWrite
0x1800138dc  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x1800138e1  lea     rdx, asc_1800347E8; "\r\n"
0x1800138e8  call    cs:__imp_WriteFile
0x1800138ee  mov     rsi, [rbp+1060h+arg_28]
0x1800138f5  test    rsi, rsi
0x1800138f8  jz      loc_18001398A
0x1800138fe  mov     rcx, [rbx+18h]; hFile
0x180013902  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180013907  mov     r8d, 14h; nNumberOfBytesToWrite
0x18001390d  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x180013912  lea     rdx, aRawData; "Raw data: "
0x180013919  call    cs:__imp_WriteFile
0x18001391f  mov     r14, [rsp+1160h+var_10F8]
0x180013924  mov     edi, r12d
0x180013927  mov     eax, edi
0x180013929  lea     r8, a02x; "%02x "
0x180013930  mov     edx, 800h; BufferCount
0x180013935  lea     rcx, [rbp+1060h+Buffer]; Buffer
0x180013939  movzx   r9d, byte ptr [rax+r14]
0x18001393e  call    cs:__imp_swprintf_s
0x180013944  mov     rcx, [rbx+18h]; hFile
0x180013948  lea     r9, [rsp+1160h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001394d  lea     rdx, [rbp+1060h+Buffer]; lpBuffer
0x180013951  mov     [rsp+1160h+lpOverlapped], r12; lpOverlapped
0x180013956  lea     r8d, [rax+rax]; nNumberOfBytesToWrite
0x18001395a  call    cs:__imp_WriteFile
0x180013960  inc     edi
0x180013962  mov     eax, edi
  ... truncated ...
```
