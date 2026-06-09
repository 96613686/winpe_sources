# DsLogger::InitializeLogHelper(void)

- ea: `0x18038fc0c`
- end: `0x1803901d4`
- name: `?InitializeLogHelper@DsLogger@@AEAAKXZ`
- size: `1480`
- prototype: `__int64 __fastcall(DsLogger *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x1803907a4`

## callees

- `0x18000ed84`
- `0x18000ff94`
- `0x18001e090`
- `0x180030af8`
- `0x180030bd4`
- `0x1800a1694`
- `0x180192308`
- `0x18038fc0c`
- `0x18039088c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fe4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038ff51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039001f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803900e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039011c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fc71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fd38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fe4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038fef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18038ff51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039001f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803900e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18039011c`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18038fc67`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18038fd9d`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18038fc67`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x18038fd9d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18038fe23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180390090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180390191`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18038fe23`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180390090`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180390191`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180390015`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180390015`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18038fd25`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1803900be`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18038fd25`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1803900be`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18038fd71`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18038fd71`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1803900d2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1803900d2`
- `ntdll!RtlLeaveCriticalSection` at `0x1803901a1`
- `ntdll!RtlLeaveCriticalSection` at `0x1803901a1`
- `ntdll!RtlEnterCriticalSection` at `0x18038fc55`
- `ntdll!RtlEnterCriticalSection` at `0x18038fc55`
- `KERNEL32!MoveFileW` at `0x18038fe3c`
- `KERNEL32!MoveFileW` at `0x18038fe3c`

## pseudocode

```c
__int64 __fastcall DsLogger::InitializeLogHelper(DsLogger *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rsi
  DWORD LastError; // ebx
  char v4; // bl
  HANDLE FileW; // rax
  HANDLE v6; // rcx
  int v7; // eax
  bool v8; // zf
  int v9; // edx
  int v10; // eax
  bool v11; // zf
  int v12; // edx
  HANDLE v13; // rcx
  HANDLE v14; // rax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  int hTemplateFile; // [rsp+30h] [rbp-D0h]
  __int16 hTemplateFilea; // [rsp+30h] [rbp-D0h]
  __int16 hTemplateFileb; // [rsp+30h] [rbp-D0h]
  int v20; // [rsp+38h] [rbp-C8h]
  char v21; // [rsp+48h] [rbp-B8h]
  _WORD v22[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v23; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD NumberOfBytesRead; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Buffer[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR NewFileName[264]; // [rsp+280h] [rbp+180h] BYREF

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1056);
  v23 = -257;
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 1056));
  if ( GetWindowsDirectoryW(Buffer, 0x105u) )
  {
    if ( StringCchCatW(Buffer, 0x105u, (const unsigned __int16 *)this + 4) < 0 )
    {
      LastError = 161;
LABEL_32:
      if ( *(_QWORD *)this )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = 0;
      }
      goto LABEL_34;
    }
    v4 = 0;
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      352387246,
      4,
      3,
      1,
      gfTraceToSecondProvider != 0,
      10,
      &WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids,
      (__int64)Buffer);
    while ( 1 )
    {
      FileW = CreateFileW(Buffer, 0xC0000000, 3u, 0, 4u, 0x80u, 0);
      *(_QWORD *)this = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        IncrementWPPPerfCountersForLevel(2);
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          352387271,
          2,
          3,
          1,
          gfTraceToSecondProvider != 0,
          11,
          &WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids,
          (__int64)Buffer,
          LastError);
        *(_QWORD *)this = 0;
        goto LABEL_31;
      }
      if ( GetLastError() != 183 )
        break;
      if ( v4 )
      {
        IncrementWPPPerfCountersForLevel(2);
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          352387312,
          2,
          3,
          1,
          gfTraceToSecondProvider != 0,
          13,
          (__int64)&WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids);
        LastError = 31;
        goto LABEL_32;
      }
      v6 = *(HANDLE *)this;
      v22[0] = 0;
      NumberOfBytesRead = 0;
      if ( !ReadFile(v6, v22, 2u, &NumberOfBytesRead, 0) )
      {
        LastError = GetLastError();
        IncrementWPPPerfCountersForLevel(2);
        v10 = 0;
        v21 = LastError;
        v11 = gfTraceToSecondProvider == 0;
        v12 = 352387335;
        hTemplateFileb = 14;
LABEL_25:
        LOBYTE(v10) = !v11;
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          2,
          3,
          1,
          v10,
          hTemplateFileb,
          &WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids,
          (__int64)Buffer,
          v21);
        goto LABEL_31;
      }
      if ( v23 == v22[0] )
        goto LABEL_26;
      if ( !GetWindowsDirectoryW(NewFileName, 0x105u) )
      {
        LastError = GetLastError();
        IncrementWPPPerfCountersForLevel(2);
        v7 = 0;
        v8 = gfTraceToSecondProvider == 0;
        v9 = 352387358;
        hTemplateFilea = 15;
LABEL_20:
        LOBYTE(v7) = !v8;
        WPP_SF__ATTRTYP_LOG_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v9,
          2,
          3,
          1,
          v7,
          hTemplateFilea,
          (__int64)&WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids);
        goto LABEL_31;
      }
      if ( StringCchCatW(NewFileName, 0x105u, (const unsigned __int16 *)this + 265) < 0 )
      {
        LastError = 161;
        IncrementWPPPerfCountersForLevel(2);
        WPP_SF_(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          352387368,
          2,
          3,
          1,
          gfTraceToSecondProvider != 0,
          16,
          &WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids);
        goto LABEL_32;
      }
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        352387375,
        4,
        3,
        1,
        gfTraceToSecondProvider != 0,
        17,
        &WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids,
        (__int64)NewFileName);
      if ( *(_QWORD *)this )
      {
        CloseHandle(*(HANDLE *)this);
        *(_QWORD *)this = 0;
      }
      if ( !MoveFileW(Buffer, NewFileName) )
      {
        LastError = GetLastError();
        IncrementWPPPerfCountersForLevel(2);
        WPP_SF_SSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          dwCreationDisposition,
          gfTraceToSecondProvider != 0,
          hTemplateFile,
          v20,
          (__int64)Buffer,
          (__int64)NewFileName,
          LastError);
        goto LABEL_31;
      }
      v4 = 1;
    }
    v13 = *(HANDLE *)this;
    NumberOfBytesRead = 0;
    if ( !WriteFile(v13, &v23, 2u, &NumberOfBytesRead, 0) )
    {
      LastError = GetLastError();
      IncrementWPPPerfCountersForLevel(2);
      v10 = 0;
      v21 = LastError;
      v11 = gfTraceToSecondProvider == 0;
      v12 = 352387298;
      hTemplateFileb = 12;
      goto LABEL_25;
    }
LABEL_26:
    LastError = 0;
    if ( *(_QWORD *)this )
    {
      CloseHandle(*(HANDLE *)this);
      *(_QWORD *)this = 0;
    }
    v14 = CreateFileW(Buffer, 0x40000000u, 3u, 0, 4u, 0x80u, 0);
    *(_QWORD *)this = v14;
    if ( SetFilePointer(v14, 0, 0, 2u) == -1 )
    {
      LastError = GetLastError();
      IncrementWPPPerfCountersForLevel(2);
      v7 = 0;
      v8 = gfTraceToSecondProvider == 0;
      v9 = 352387436;
      hTemplateFilea = 19;
      goto LABEL_20;
    }
  }
  else
  {
    LastError = GetLastError();
LABEL_31:
    if ( LastError )
      goto LABEL_32;
  }
LABEL_34:
  RtlLeaveCriticalSection(v1);
  return LastError;
}

```

## disassembly

```asm
0x18038fc0c  mov     [rsp-8+arg_8], rbx
0x18038fc11  mov     [rsp-8+arg_10], rsi
0x18038fc16  push    rbp
0x18038fc17  push    rdi
0x18038fc18  push    r12
0x18038fc1a  push    r13
0x18038fc1c  push    r15
0x18038fc1e  lea     rbp, [rsp-3A0h]
0x18038fc26  sub     rsp, 4A0h
0x18038fc2d  mov     rax, cs:__security_cookie
0x18038fc34  xor     rax, rsp
0x18038fc37  mov     [rbp+3C0h+var_30], rax
0x18038fc3e  lea     rsi, [rcx+420h]
0x18038fc45  mov     rdi, rcx
0x18038fc48  mov     eax, 0FEFFh
0x18038fc4d  mov     rcx, rsi; CriticalSection
0x18038fc50  mov     [rsp+4C0h+var_45C], ax
0x18038fc55  call    cs:__imp_RtlEnterCriticalSection
0x18038fc5b  mov     ebx, 105h
0x18038fc60  lea     rcx, [rsp+4C0h+Buffer]; lpBuffer
0x18038fc65  mov     edx, ebx; uSize
0x18038fc67  call    cs:__imp_GetWindowsDirectoryW
0x18038fc6d  test    eax, eax
0x18038fc6f  jnz     short loc_18038FC7E
0x18038fc71  call    cs:__imp_GetLastError
0x18038fc77  mov     ebx, eax
0x18038fc79  jmp     loc_180390185
0x18038fc7e  lea     r8, [rdi+8]; unsigned __int16 *
0x18038fc82  mov     rdx, rbx; unsigned __int64
0x18038fc85  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x18038fc8a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18038fc8f  test    eax, eax
0x18038fc91  jns     short loc_18038FC9D
0x18038fc93  mov     ebx, 0A1h
0x18038fc98  jmp     loc_180390189
0x18038fc9d  mov     eax, cs:gfTraceToSecondProvider
0x18038fca3  xor     ecx, ecx
0x18038fca5  mov     r13d, 1
0x18038fcab  xor     bl, bl
0x18038fcad  test    eax, eax
0x18038fcaf  mov     edx, 150100AEh; int
0x18038fcb4  lea     rax, [rsp+4C0h+Buffer]
0x18038fcb9  mov     [rsp+4C0h+var_480], rax; __int64
0x18038fcbe  setnz   cl
0x18038fcc1  lea     rax, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038fcc8  mov     [rsp+4C0h+var_488], rax; LPCGUID
0x18038fccd  lea     r12d, [r13+2]
0x18038fcd1  mov     word ptr [rsp+4C0h+hTemplateFile], 0Ah; __int16
0x18038fcd8  lea     r8d, [r13+3]; int
0x18038fcdc  mov     [rsp+4C0h+dwFlagsAndAttributes], ecx; int
0x18038fce0  mov     r9d, r12d; int
0x18038fce3  mov     rcx, cs:WPP_GLOBAL_Control
0x18038fcea  mov     [rsp+4C0h+dwCreationDisposition], r13d; int
0x18038fcef  mov     rcx, [rcx+10h]; int
0x18038fcf3  call    WPP_SF_S
0x18038fcf8  lea     r15d, [r13+1]
0x18038fcfc  mov     [rsp+4C0h+hTemplateFile], 0; hTemplateFile
0x18038fd05  lea     rcx, [rsp+4C0h+Buffer]; lpFileName
0x18038fd0a  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18038fd12  xor     r9d, r9d; lpSecurityAttributes
0x18038fd15  mov     r8d, r12d; dwShareMode
0x18038fd18  mov     [rsp+4C0h+dwCreationDisposition], 4; dwCreationDisposition
0x18038fd20  mov     edx, 0C0000000h; dwDesiredAccess
0x18038fd25  call    cs:__imp_CreateFileW
0x18038fd2b  mov     [rdi], rax
0x18038fd2e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18038fd32  jz      loc_18039011C
0x18038fd38  call    cs:__imp_GetLastError
0x18038fd3e  cmp     eax, 0B7h
0x18038fd43  jnz     loc_18038FFF4
0x18038fd49  test    bl, bl
0x18038fd4b  jnz     loc_18038FF96
0x18038fd51  mov     rcx, [rdi]; hFile
0x18038fd54  lea     r9, [rsp+4C0h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18038fd59  xor     eax, eax
0x18038fd5b  lea     rdx, [rsp+4C0h+var_460]; lpBuffer
0x18038fd60  mov     r8d, r15d; nNumberOfBytesToRead
0x18038fd63  mov     [rsp+4C0h+var_460], ax
0x18038fd68  mov     [rsp+4C0h+NumberOfBytesRead], eax
0x18038fd6c  mov     qword ptr [rsp+4C0h+dwCreationDisposition], rax; lpOverlapped
0x18038fd71  call    cs:__imp_ReadFile
0x18038fd77  test    eax, eax
0x18038fd79  jz      loc_18038FF51
0x18038fd7f  movzx   eax, [rsp+4C0h+var_460]
0x18038fd84  cmp     [rsp+4C0h+var_45C], ax
0x18038fd89  jz      loc_180390086
0x18038fd8f  mov     ebx, 105h
0x18038fd94  lea     rcx, [rbp+3C0h+NewFileName]; lpBuffer
0x18038fd9b  mov     edx, ebx; uSize
0x18038fd9d  call    cs:__imp_GetWindowsDirectoryW
0x18038fda3  test    eax, eax
0x18038fda5  jz      loc_18038FEF4
0x18038fdab  lea     r8, [rdi+212h]; unsigned __int16 *
0x18038fdb2  mov     edx, ebx; unsigned __int64
0x18038fdb4  lea     rcx, [rbp+3C0h+NewFileName]; unsigned __int16 *
0x18038fdbb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18038fdc0  test    eax, eax
0x18038fdc2  js      loc_18038FE9E
0x18038fdc8  mov     eax, cs:gfTraceToSecondProvider
0x18038fdce  xor     ecx, ecx
0x18038fdd0  test    eax, eax
0x18038fdd2  mov     r9d, r12d; int
0x18038fdd5  lea     rax, [rbp+3C0h+NewFileName]
0x18038fddc  mov     edx, 1501012Fh; int
0x18038fde1  mov     [rsp+4C0h+var_480], rax; __int64
0x18038fde6  setnz   cl
0x18038fde9  lea     rax, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038fdf0  mov     r8d, 4; int
0x18038fdf6  mov     [rsp+4C0h+var_488], rax; int
0x18038fdfb  mov     word ptr [rsp+4C0h+hTemplateFile], 11h; int
0x18038fe02  mov     [rsp+4C0h+dwFlagsAndAttributes], ecx; int
0x18038fe06  mov     rcx, cs:WPP_GLOBAL_Control
0x18038fe0d  mov     [rsp+4C0h+dwCreationDisposition], r13d; int
0x18038fe12  mov     rcx, [rcx+10h]; int
0x18038fe16  call    WPP_SF_S
0x18038fe1b  mov     rcx, [rdi]; hObject
0x18038fe1e  test    rcx, rcx
0x18038fe21  jz      short loc_18038FE30
0x18038fe23  call    cs:__imp_CloseHandle
0x18038fe29  mov     qword ptr [rdi], 0
0x18038fe30  lea     rdx, [rbp+3C0h+NewFileName]; lpNewFileName
0x18038fe37  lea     rcx, [rsp+4C0h+Buffer]; lpExistingFileName
0x18038fe3c  call    cs:__imp_MoveFileW
0x18038fe42  test    eax, eax
0x18038fe44  jz      short loc_18038FE4E
0x18038fe46  mov     bl, r13b
0x18038fe49  jmp     loc_18038FCFC
0x18038fe4e  call    cs:__imp_GetLastError
0x18038fe54  mov     ebx, eax
0x18038fe56  mov     ecx, r15d
0x18038fe59  call    IncrementWPPPerfCountersForLevel
0x18038fe5e  mov     ecx, cs:gfTraceToSecondProvider
0x18038fe64  xor     eax, eax
0x18038fe66  test    ecx, ecx
0x18038fe68  mov     dword ptr [rsp+4C0h+var_470], ebx; char
0x18038fe6c  lea     rcx, [rbp+3C0h+NewFileName]
0x18038fe73  mov     qword ptr [rsp+4C0h+var_478], rcx; __int64
0x18038fe78  setnz   al
0x18038fe7b  lea     rcx, [rsp+4C0h+Buffer]
0x18038fe80  mov     [rsp+4C0h+var_480], rcx; __int64
0x18038fe85  mov     rcx, cs:WPP_GLOBAL_Control
0x18038fe8c  mov     [rsp+4C0h+dwFlagsAndAttributes], eax; int
0x18038fe90  mov     rcx, [rcx+10h]; int
0x18038fe94  call    WPP_SF_SSD
0x18038fe99  jmp     loc_180390185
0x18038fe9e  mov     ebx, 0A1h
0x18038fea3  mov     ecx, r15d
0x18038fea6  call    IncrementWPPPerfCountersForLevel
0x18038feab  mov     ecx, cs:gfTraceToSecondProvider
0x18038feb1  xor     eax, eax
0x18038feb3  test    ecx, ecx
0x18038feb5  mov     r9d, r12d; int
0x18038feb8  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038febf  mov     r8d, r15d; int
0x18038fec2  mov     [rsp+4C0h+var_488], rcx; LPCGUID
0x18038fec7  setnz   al
0x18038feca  mov     rcx, cs:WPP_GLOBAL_Control
0x18038fed1  mov     edx, 15010128h; int
0x18038fed6  mov     word ptr [rsp+4C0h+hTemplateFile], 10h; __int16
0x18038fedd  mov     [rsp+4C0h+dwFlagsAndAttributes], eax; int
0x18038fee1  mov     [rsp+4C0h+dwCreationDisposition], r13d; int
0x18038fee6  mov     rcx, [rcx+10h]; int
0x18038feea  call    WPP_SF_
0x18038feef  jmp     loc_180390189
0x18038fef4  call    cs:__imp_GetLastError
0x18038fefa  mov     ebx, eax
0x18038fefc  mov     ecx, r15d
0x18038feff  call    IncrementWPPPerfCountersForLevel
0x18038ff04  mov     ecx, cs:gfTraceToSecondProvider
0x18038ff0a  xor     eax, eax
0x18038ff0c  mov     dword ptr [rsp+4C0h+var_480], ebx
0x18038ff10  test    ecx, ecx
0x18038ff12  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038ff19  mov     edx, 1501011Eh
0x18038ff1e  mov     [rsp+4C0h+var_488], rcx
0x18038ff23  mov     word ptr [rsp+4C0h+hTemplateFile], 0Fh
0x18038ff2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18038ff31  setnz   al
0x18038ff34  mov     [rsp+4C0h+dwFlagsAndAttributes], eax
0x18038ff38  mov     r8d, r15d
0x18038ff3b  mov     r9d, r12d
0x18038ff3e  mov     [rsp+4C0h+dwCreationDisposition], r13d
0x18038ff43  mov     rcx, [rcx+10h]
0x18038ff47  call    WPP_SF__ATTRTYP_LOG_
0x18038ff4c  jmp     loc_180390185
0x18038ff51  call    cs:__imp_GetLastError
0x18038ff57  mov     ebx, eax
0x18038ff59  mov     ecx, r15d
0x18038ff5c  call    IncrementWPPPerfCountersForLevel
0x18038ff61  mov     ecx, cs:gfTraceToSecondProvider
0x18038ff67  xor     eax, eax
0x18038ff69  mov     dword ptr [rsp+4C0h+var_478], ebx
0x18038ff6d  test    ecx, ecx
0x18038ff6f  lea     rcx, [rsp+4C0h+Buffer]
0x18038ff74  mov     edx, 15010107h
0x18038ff79  mov     [rsp+4C0h+var_480], rcx
0x18038ff7e  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038ff85  mov     [rsp+4C0h+var_488], rcx
0x18038ff8a  mov     word ptr [rsp+4C0h+hTemplateFile], 0Eh
0x18038ff91  jmp     loc_18039005F
0x18038ff96  mov     ecx, r15d
0x18038ff99  call    IncrementWPPPerfCountersForLevel
0x18038ff9e  mov     ecx, cs:gfTraceToSecondProvider
0x18038ffa4  xor     eax, eax
0x18038ffa6  test    ecx, ecx
0x18038ffa8  mov     dword ptr [rsp+4C0h+var_480], 0
0x18038ffb0  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x18038ffb7  mov     r9d, r12d
0x18038ffba  mov     [rsp+4C0h+var_488], rcx
0x18038ffbf  setnz   al
0x18038ffc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18038ffc9  mov     r8d, r15d
0x18038ffcc  mov     word ptr [rsp+4C0h+hTemplateFile], 0Dh
0x18038ffd3  mov     edx, 150100F0h
0x18038ffd8  mov     [rsp+4C0h+dwFlagsAndAttributes], eax
0x18038ffdc  mov     [rsp+4C0h+dwCreationDisposition], r13d
0x18038ffe1  mov     rcx, [rcx+10h]
0x18038ffe5  call    WPP_SF__ATTRTYP_LOG_
0x18038ffea  mov     ebx, 1Fh
0x18038ffef  jmp     loc_180390189
0x18038fff4  mov     rcx, [rdi]; hFile
0x18038fff7  lea     r9, [rsp+4C0h+NumberOfBytesRead]; lpNumberOfBytesWritten
0x18038fffc  mov     r8d, r15d; nNumberOfBytesToWrite
0x18038ffff  mov     [rsp+4C0h+NumberOfBytesRead], 0
0x180390007  lea     rdx, [rsp+4C0h+var_45C]; lpBuffer
0x18039000c  mov     qword ptr [rsp+4C0h+dwCreationDisposition], 0; lpOverlapped
0x180390015  call    cs:__imp_WriteFile
0x18039001b  test    eax, eax
0x18039001d  jnz     short loc_180390086
0x18039001f  call    cs:__imp_GetLastError
0x180390025  mov     ebx, eax
0x180390027  mov     ecx, r15d
0x18039002a  call    IncrementWPPPerfCountersForLevel
0x18039002f  mov     ecx, cs:gfTraceToSecondProvider
0x180390035  xor     eax, eax
0x180390037  mov     dword ptr [rsp+4C0h+var_478], ebx; char
0x18039003b  test    ecx, ecx
0x18039003d  lea     rcx, [rsp+4C0h+Buffer]
0x180390042  mov     edx, 150100E2h; int
0x180390047  mov     [rsp+4C0h+var_480], rcx; __int64
0x18039004c  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x180390053  mov     [rsp+4C0h+var_488], rcx; LPCGUID
0x180390058  mov     word ptr [rsp+4C0h+hTemplateFile], 0Ch; __int16
0x18039005f  mov     rcx, cs:WPP_GLOBAL_Control
0x180390066  setnz   al
0x180390069  mov     [rsp+4C0h+dwFlagsAndAttributes], eax; int
0x18039006d  mov     r8d, r15d; int
0x180390070  mov     r9d, r12d; int
0x180390073  mov     [rsp+4C0h+dwCreationDisposition], r13d; int
0x180390078  mov     rcx, [rcx+10h]; int
0x18039007c  call    WPP_SF_Sd
0x180390081  jmp     loc_180390185
0x180390086  mov     rcx, [rdi]; hObject
0x180390089  xor     ebx, ebx
0x18039008b  test    rcx, rcx
0x18039008e  jz      short loc_180390099
0x180390090  call    cs:__imp_CloseHandle
0x180390096  mov     [rdi], rbx
0x180390099  mov     [rsp+4C0h+hTemplateFile], rbx; hTemplateFile
0x18039009e  lea     rcx, [rsp+4C0h+Buffer]; lpFileName
0x1803900a3  mov     [rsp+4C0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1803900ab  xor     r9d, r9d; lpSecurityAttributes
0x1803900ae  mov     r8d, r12d; dwShareMode
0x1803900b1  mov     [rsp+4C0h+dwCreationDisposition], 4; dwCreationDisposition
0x1803900b9  mov     edx, 40000000h; dwDesiredAccess
0x1803900be  call    cs:__imp_CreateFileW
0x1803900c4  mov     r9d, r15d; dwMoveMethod
0x1803900c7  xor     r8d, r8d; lpDistanceToMoveHigh
0x1803900ca  mov     rcx, rax; hFile
0x1803900cd  mov     [rdi], rax
0x1803900d0  xor     edx, edx; lDistanceToMove
0x1803900d2  call    cs:__imp_SetFilePointer
0x1803900d8  cmp     eax, 0FFFFFFFFh
0x1803900db  jnz     loc_18039019E
0x1803900e1  call    cs:__imp_GetLastError
0x1803900e7  mov     ebx, eax
0x1803900e9  mov     ecx, r15d
0x1803900ec  call    IncrementWPPPerfCountersForLevel
0x1803900f1  mov     ecx, cs:gfTraceToSecondProvider
0x1803900f7  xor     eax, eax
0x1803900f9  mov     dword ptr [rsp+4C0h+var_480], ebx
0x1803900fd  test    ecx, ecx
0x1803900ff  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
0x180390106  mov     edx, 1501016Ch
0x18039010b  mov     [rsp+4C0h+var_488], rcx
0x180390110  mov     word ptr [rsp+4C0h+hTemplateFile], 13h
0x180390117  jmp     loc_18038FF2A
0x18039011c  call    cs:__imp_GetLastError
0x180390122  mov     ebx, eax
0x180390124  mov     ecx, r15d
0x180390127  call    IncrementWPPPerfCountersForLevel
0x18039012c  mov     ecx, cs:gfTraceToSecondProvider
0x180390132  xor     eax, eax
0x180390134  test    ecx, ecx
0x180390136  mov     dword ptr [rsp+4C0h+var_478], ebx; char
0x18039013a  lea     rcx, [rsp+4C0h+Buffer]
0x18039013f  mov     r9d, r12d; int
0x180390142  mov     [rsp+4C0h+var_480], rcx; __int64
0x180390147  setnz   al
0x18039014a  lea     rcx, WPP_7bda94fd2d9f3af7368c896a472d9660_Traceguids
  ... truncated ...
```
