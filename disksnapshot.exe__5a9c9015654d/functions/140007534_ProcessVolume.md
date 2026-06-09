# ProcessVolume

- ea: `0x140007534`
- end: `0x1400079a9`
- name: `ProcessVolume`
- size: `1141`
- prototype: `__int64 __fastcall(_DWORD *, const WCHAR *, const WCHAR *, __int64, unsigned int, FILE *, int, __int64, __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x140006b20`
- `0x140007c84`

## callees

- `0x1400011bc`
- `0x140001c50`
- `0x14000265e`
- `0x1400027d2`
- `0x14000281c`
- `0x140005e10`
- `0x140006c30`
- `0x140007534`
- `0x1400079b0`
- `0x1400082d0`
- `0x140008a38`

## import_xrefs

- `ntdll!RtlOsDeploymentState` at `0x140007689`
- `ntdll!RtlOsDeploymentState` at `0x140007689`
- `RPCRT4!UuidFromStringW` at `0x140007673`
- `RPCRT4!UuidFromStringW` at `0x140007673`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400075e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400075e1`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x14000761f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x14000761f`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140007657`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x140007657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400075f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007629`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007979`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140007979`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140007698`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140007698`

## pseudocode

```c
__int64 __fastcall ProcessVolume(
        _DWORD *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        __int64 a4,
        unsigned int a5,
        FILE *a6,
        int a7,
        __int64 a8,
        __int64 a9)
{
  FILE *v9; // rdi
  const WCHAR *v11; // r15
  void *v13; // r14
  signed int LastError; // eax
  signed int v15; // ebx
  signed int v16; // eax
  __int16 v17; // bx
  FILE *v18; // rax
  BOOL v19; // ebx
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-F0h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-E8h]
  HANDLE hTemplateFile; // [rsp+30h] [rbp-E0h]
  __int16 v24; // [rsp+90h] [rbp-80h] BYREF
  int v25; // [rsp+94h] [rbp-7Ch] BYREF
  int v26; // [rsp+98h] [rbp-78h] BYREF
  _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+A0h] [rbp-70h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+A8h] [rbp-68h] BYREF
  const WCHAR *v29; // [rsp+B0h] [rbp-60h] BYREF
  HANDLE FileW; // [rsp+B8h] [rbp-58h] BYREF
  FILE *Stream; // [rsp+C0h] [rbp-50h] BYREF
  union _ULARGE_INTEGER v32; // [rsp+C8h] [rbp-48h] BYREF
  _ULARGE_INTEGER v33; // [rsp+D0h] [rbp-40h] BYREF
  __int64 v34; // [rsp+D8h] [rbp-38h]
  __int64 v35; // [rsp+E0h] [rbp-30h]
  __int64 v36; // [rsp+E8h] [rbp-28h]
  _SYSTEMTIME SystemTime; // [rsp+F0h] [rbp-20h] BYREF
  UUID Uuid; // [rsp+100h] [rbp-10h] BYREF
  char v39[32]; // [rsp+110h] [rbp+0h] BYREF
  _SYSTEMTIME *p_SystemTime; // [rsp+130h] [rbp+20h]
  __int64 v41; // [rsp+138h] [rbp+28h]
  FILE **p_Stream; // [rsp+140h] [rbp+30h]
  __int64 v43; // [rsp+148h] [rbp+38h]
  UUID *p_Uuid; // [rsp+150h] [rbp+40h]
  __int64 v45; // [rsp+158h] [rbp+48h]
  _ULARGE_INTEGER *v46; // [rsp+160h] [rbp+50h]
  __int64 v47; // [rsp+168h] [rbp+58h]
  HANDLE *p_FileW; // [rsp+170h] [rbp+60h]
  __int64 v49; // [rsp+178h] [rbp+68h]
  union _ULARGE_INTEGER *v50; // [rsp+180h] [rbp+70h]
  __int64 v51; // [rsp+188h] [rbp+78h]
  const WCHAR **v52; // [rsp+190h] [rbp+80h]
  __int64 v53; // [rsp+198h] [rbp+88h]
  int *v54; // [rsp+1A0h] [rbp+90h]
  __int64 v55; // [rsp+1A8h] [rbp+98h]
  __int16 *v56; // [rsp+1B0h] [rbp+A0h]
  __int64 v57; // [rsp+1B8h] [rbp+A8h]
  WCHAR szVolumeName[11]; // [rsp+1C0h] [rbp+B0h] BYREF
  unsigned __int16 StringUuid[45]; // [rsp+1D6h] [rbp+C6h] BYREF

  v9 = a6;
  v36 = a8;
  v11 = a2;
  v29 = a2;
  v34 = a4;
  Stream = a6;
  v35 = a9;
  TotalNumberOfFreeBytes.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  SystemTime = 0;
  memset_0(szVolumeName, 0, 0x64u);
  v26 = 0;
  Uuid = 0;
  FileW = CreateFileW(v11, 0x100u, 3u, 0, 3u, 0x2000080u, 0);
  v13 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    if ( GetDiskFreeSpaceExW(a3, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes)
      && GetVolumeNameForVolumeMountPointW(a3, szVolumeName, 0x32u) )
    {
      StringUuid[36] = 0;
      if ( UuidFromStringW(StringUuid, &Uuid) )
      {
        v15 = -2147024809;
      }
      else
      {
        v25 = RtlOsDeploymentState(0);
        v17 = v25;
        GetSystemTime(&SystemTime);
        if ( a1[1] )
        {
          v9 = Stream;
          LODWORD(hTemplateFile) = SystemTime.wMinute;
          dwFlagsAndAttributes[0] = SystemTime.wHour;
          dwCreationDisposition[0] = SystemTime.wDay;
          fwprintf(
            Stream,
            L"VolumeSnapshot,%04d:%02d:%02d:%02d:%02d:%02d:%03d,%u,%s,%llu,%u,%llu,%u,%u,%u\n",
            SystemTime.wYear,
            SystemTime.wMonth,
            *(_QWORD *)dwCreationDisposition,
            *(_QWORD *)dwFlagsAndAttributes,
            hTemplateFile,
            SystemTime.wSecond,
            SystemTime.wMilliseconds,
            a5,
            StringUuid,
            TotalNumberOfBytes.QuadPart,
            TotalNumberOfBytes.QuadPart >> 20,
            TotalNumberOfFreeBytes.QuadPart,
            TotalNumberOfFreeBytes.QuadPart >> 20,
            (unsigned __int16)v25,
            9);
          v13 = FileW;
          v17 = v25;
          LODWORD(v11) = (_DWORD)v29;
        }
        if ( a7
          && (unsigned int)dword_140014000 > 5
          && (qword_140014010 & 0x400000000000LL) != 0
          && (qword_140014018 & 0x400000000000LL) == qword_140014018 )
        {
          v32 = TotalNumberOfFreeBytes;
          v33 = TotalNumberOfBytes;
          LODWORD(v29) = TotalNumberOfFreeBytes.QuadPart >> 20;
          v56 = &v24;
          v54 = &v25;
          v52 = &v29;
          v50 = &v32;
          p_FileW = &FileW;
          v46 = &v33;
          p_Uuid = &Uuid;
          p_Stream = &Stream;
          p_SystemTime = &SystemTime;
          v24 = 9;
          LODWORD(FileW) = TotalNumberOfBytes.QuadPart >> 20;
          LOWORD(v25) = v17;
          LODWORD(Stream) = a5;
          v57 = 2;
          v55 = 2;
          v53 = 4;
          v51 = 8;
          v49 = 4;
          v47 = 8;
          v45 = 16;
          v43 = 4;
          v41 = 16;
          tlgWriteTransfer_EventWriteTransfer(&dword_140014000, &byte_1400110F7, 0, 0, 11, v39);
        }
        if ( a1[3] || TotalNumberOfBytes.QuadPart - TotalNumberOfFreeBytes.QuadPart <= 0x4000000000LL )
        {
          v15 = ResetVolumeCounters(a5, &v26);
          if ( v15 >= 0 )
          {
            v15 = ProcessVolumeRecords(v13);
            if ( v15 >= 0 )
            {
              v15 = ProcessRecords((_DWORD)a1, (_DWORD)v11, a5, v34, (__int64)v9);
              if ( v15 >= 0 )
              {
                v19 = !v26 && a1[5];
                v15 = SummarizeResults((_DWORD)a1, a5, v19, (_DWORD)v9, a7, v36, v35);
                if ( v15 >= 0 )
                  v15 = 0;
              }
            }
          }
        }
        else
        {
          v18 = o___acrt_iob_func_0(2u);
          fwprintf(v18, L"Skipping detailed capture of large volume\n");
          v15 = 1;
        }
      }
    }
    else
    {
      v16 = GetLastError();
      v15 = v16;
      if ( v16 > 0 )
        v15 = (unsigned __int16)v16 | 0x80070000;
    }
    CloseHandle(v13);
  }
  FreeVolumeCounters();
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x140007534  push    rbp
0x140007536  push    rbx
0x140007537  push    rsi
0x140007538  push    rdi
0x140007539  push    r12
0x14000753b  push    r13
0x14000753d  push    r14
0x14000753f  push    r15
0x140007541  lea     rbp, [rsp-138h]
0x140007549  sub     rsp, 248h
0x140007550  mov     rax, cs:__security_cookie
0x140007557  xor     rax, rsp
0x14000755a  mov     [rbp+170h+var_50], rax
0x140007561  mov     rax, [rbp+170h+arg_38]
0x140007568  xor     esi, esi
0x14000756a  mov     rdi, [rbp+170h+arg_28]
0x140007571  mov     rbx, r8
0x140007574  mov     [rbp+170h+var_198], rax
0x140007578  mov     r15, rdx
0x14000757b  mov     rax, [rbp+170h+arg_40]
0x140007582  mov     r13, rcx
0x140007585  mov     [rbp+170h+var_1D0], rdx
0x140007589  lea     r8d, [rsi+64h]; Size
0x14000758d  xorps   xmm0, xmm0
0x140007590  mov     [rbp+170h+var_1A8], r9
0x140007594  xor     edx, edx; Val
0x140007596  mov     [rbp+170h+Stream], rdi
0x14000759a  lea     rcx, [rbp+170h+szVolumeName]; void *
0x1400075a1  mov     [rbp+170h+var_1A0], rax
0x1400075a5  mov     qword ptr [rbp+170h+TotalNumberOfFreeBytes], rsi
0x1400075a9  mov     qword ptr [rbp+170h+TotalNumberOfBytes], rsi
0x1400075ad  movups  xmmword ptr [rbp+170h+SystemTime.wYear], xmm0
0x1400075b1  call    memset_0
0x1400075b6  xorps   xmm0, xmm0
0x1400075b9  mov     [rsp+280h+hTemplateFile], rsi; hTemplateFile
0x1400075be  lea     r8d, [rsi+3]; dwShareMode
0x1400075c2  mov     [rsp+280h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x1400075ca  xor     r9d, r9d; lpSecurityAttributes
0x1400075cd  mov     [rsp+280h+dwCreationDisposition], r8d; dwCreationDisposition
0x1400075d2  mov     edx, 100h; dwDesiredAccess
0x1400075d7  mov     [rbp+170h+var_1E8], esi
0x1400075da  mov     rcx, r15; lpFileName
0x1400075dd  movups  xmmword ptr [rbp+170h+Uuid.Data1], xmm0
0x1400075e1  call    cs:__imp_CreateFileW
0x1400075e7  mov     [rbp+170h+var_1C8], rax
0x1400075eb  mov     r14, rax
0x1400075ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1400075f2  jnz     short loc_140007612
0x1400075f4  call    cs:__imp_GetLastError
0x1400075fa  mov     ebx, eax
0x1400075fc  test    eax, eax
0x1400075fe  jle     loc_14000797F
0x140007604  movzx   ebx, ax
0x140007607  or      ebx, 80070000h
0x14000760d  jmp     loc_14000797F
0x140007612  lea     r9, [rbp+170h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x140007616  xor     edx, edx; lpFreeBytesAvailableToCaller
0x140007618  lea     r8, [rbp+170h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x14000761c  mov     rcx, rbx; lpDirectoryName
0x14000761f  call    cs:__imp_GetDiskFreeSpaceExW
0x140007625  test    eax, eax
0x140007627  jnz     short loc_140007647
0x140007629  call    cs:__imp_GetLastError
0x14000762f  mov     ebx, eax
0x140007631  test    eax, eax
0x140007633  jle     loc_140007976
0x140007639  movzx   ebx, ax
0x14000763c  or      ebx, 80070000h
0x140007642  jmp     loc_140007976
0x140007647  mov     r8d, 32h ; '2'; cchBufferLength
0x14000764d  lea     rdx, [rbp+170h+szVolumeName]; lpszVolumeName
0x140007654  mov     rcx, rbx; lpszVolumeMountPoint
0x140007657  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x14000765d  test    eax, eax
0x14000765f  jz      short loc_140007629
0x140007661  lea     rdx, [rbp+170h+Uuid]; Uuid
0x140007665  mov     [rbp+170h+var_62], si
0x14000766c  lea     rcx, [rbp+170h+StringUuid]; StringUuid
0x140007673  call    cs:__imp_UuidFromStringW
0x140007679  test    eax, eax
0x14000767b  jz      short loc_140007687
0x14000767d  mov     ebx, 80070057h
0x140007682  jmp     loc_140007976
0x140007687  xor     ecx, ecx
0x140007689  call    cs:__imp_RtlOsDeploymentState
0x14000768f  lea     rcx, [rbp+170h+SystemTime]; lpSystemTime
0x140007693  mov     [rbp+170h+var_1EC], eax
0x140007696  mov     ebx, eax
0x140007698  call    cs:__imp_GetSystemTime
0x14000769e  mov     r9d, 9
0x1400076a4  mov     r12d, [rbp+170h+arg_20]
0x1400076ab  cmp     [r13+4], esi
0x1400076af  jz      loc_14000775C
0x1400076b5  mov     rdx, qword ptr [rbp+170h+TotalNumberOfFreeBytes]
0x1400076b9  mov     rcx, qword ptr [rbp+170h+TotalNumberOfBytes]
0x1400076bd  mov     r11, rdx
0x1400076c0  movzx   edi, [rbp+170h+SystemTime.wSecond]
0x1400076c4  mov     r10, rcx
0x1400076c7  movzx   eax, [rbp+170h+SystemTime.wMilliseconds]
0x1400076cb  movzx   esi, [rbp+170h+SystemTime.wMinute]
0x1400076cf  movzx   r14d, [rbp+170h+SystemTime.wHour]
0x1400076d4  movzx   r15d, [rbp+170h+SystemTime.wDay]
0x1400076d9  movzx   r9d, [rbp+170h+SystemTime.wMonth]
0x1400076de  movzx   r8d, [rbp+170h+SystemTime.wYear]
0x1400076e3  mov     [rsp+280h+var_200], 9
0x1400076ee  shr     r11, 14h
0x1400076f2  shr     r10, 14h
0x1400076f6  movzx   ebx, bx
0x1400076f9  mov     [rsp+280h+var_208], ebx
0x1400076fd  mov     [rsp+280h+var_210], r11d
0x140007702  mov     [rsp+280h+var_218], rdx
0x140007707  lea     rdx, aVolumesnapshot_0; "VolumeSnapshot,%04d:%02d:%02d:%02d:%02d"...
0x14000770e  mov     [rsp+280h+var_220], r10d
0x140007713  mov     [rsp+280h+var_228], rcx
0x140007718  lea     rcx, [rbp+170h+StringUuid]
0x14000771f  mov     [rsp+280h+var_230], rcx
0x140007724  mov     [rsp+280h+var_238], r12d
0x140007729  mov     [rsp+280h+var_240], eax
0x14000772d  mov     [rsp+280h+var_248], edi
0x140007731  mov     rdi, [rbp+170h+Stream]
0x140007735  mov     dword ptr [rsp+280h+hTemplateFile], esi
0x140007739  mov     rcx, rdi; Stream
0x14000773c  mov     [rsp+280h+dwFlagsAndAttributes], r14d
0x140007741  mov     [rsp+280h+dwCreationDisposition], r15d
0x140007746  call    fwprintf
0x14000774b  mov     r14, [rbp+170h+var_1C8]
0x14000774f  mov     r9d, 9
0x140007755  mov     ebx, [rbp+170h+var_1EC]
0x140007758  mov     r15, [rbp+170h+var_1D0]
0x14000775c  mov     esi, [rbp+170h+arg_30]
0x140007762  xor     r8d, r8d
0x140007765  test    esi, esi
0x140007767  jz      loc_1400078A9
0x14000776d  mov     eax, cs:dword_140014000
0x140007773  cmp     eax, 5
0x140007776  jbe     loc_1400078A9
0x14000777c  mov     rcx, cs:qword_140014018
0x140007783  mov     rdx, 400000000000h
0x14000778d  mov     rax, cs:qword_140014010
0x140007794  test    rdx, rax
0x140007797  jz      loc_1400078A9
0x14000779d  mov     rax, rcx
0x1400077a0  and     rax, rdx
0x1400077a3  cmp     rax, rcx
0x1400077a6  jnz     loc_1400078A9
0x1400077ac  mov     rax, qword ptr [rbp+170h+TotalNumberOfFreeBytes]
0x1400077b0  lea     rdx, byte_1400110F7
0x1400077b7  mov     rcx, rax
0x1400077ba  mov     [rbp+170h+var_1B8], rax
0x1400077be  mov     rax, qword ptr [rbp+170h+TotalNumberOfBytes]
0x1400077c2  mov     [rbp+170h+var_1B0], rax
0x1400077c6  shr     rcx, 14h
0x1400077ca  mov     dword ptr [rbp+170h+var_1D0], ecx
0x1400077cd  mov     rcx, rax
0x1400077d0  shr     rcx, 14h
0x1400077d4  lea     rax, [rbp+170h+var_1F0]
0x1400077d8  mov     [rbp+170h+var_D0], rax
0x1400077df  lea     rax, [rbp+170h+var_1EC]
0x1400077e3  mov     [rbp+170h+var_E0], rax
0x1400077ea  lea     rax, [rbp+170h+var_1D0]
0x1400077ee  mov     [rbp+170h+var_F0], rax
0x1400077f5  lea     rax, [rbp+170h+var_1B8]
0x1400077f9  mov     [rbp+170h+var_100], rax
0x1400077fd  lea     rax, [rbp+170h+var_1C8]
0x140007801  mov     [rbp+170h+var_110], rax
0x140007805  lea     rax, [rbp+170h+var_1B0]
0x140007809  mov     [rbp+170h+var_120], rax
0x14000780d  lea     rax, [rbp+170h+Uuid]
0x140007811  mov     [rbp+170h+var_130], rax
0x140007815  lea     rax, [rbp+170h+Stream]
0x140007819  mov     [rbp+170h+var_140], rax
0x14000781d  lea     rax, [rbp+170h+SystemTime]
0x140007821  mov     [rbp+170h+var_150], rax
0x140007825  lea     rax, [rbp+170h+var_170]
0x140007829  mov     [rbp+170h+var_1F0], r9w
0x14000782e  xor     r9d, r9d
0x140007831  mov     dword ptr [rbp+170h+var_1C8], ecx
0x140007834  lea     rcx, dword_140014000
0x14000783b  mov     qword ptr [rsp+280h+dwFlagsAndAttributes], rax
0x140007840  mov     [rsp+280h+dwCreationDisposition], 0Bh
0x140007848  mov     word ptr [rbp+170h+var_1EC], bx
0x14000784c  mov     dword ptr [rbp+170h+Stream], r12d
0x140007850  mov     [rbp+170h+var_C8], 2
0x14000785b  mov     [rbp+170h+var_D8], 2
0x140007866  mov     [rbp+170h+var_E8], 4
0x140007871  mov     [rbp+170h+var_F8], 8
0x140007879  mov     [rbp+170h+var_108], 4
0x140007881  mov     [rbp+170h+var_118], 8
0x140007889  mov     [rbp+170h+var_128], 10h
0x140007891  mov     [rbp+170h+var_138], 4
0x140007899  mov     [rbp+170h+var_148], 10h
0x1400078a1  call    _tlgWriteTransfer_EventWriteTransfer
0x1400078a6  xor     r8d, r8d
0x1400078a9  cmp     [r13+0Ch], r8d
0x1400078ad  jnz     short loc_1400078E9
0x1400078af  mov     rax, qword ptr [rbp+170h+TotalNumberOfBytes]
0x1400078b3  mov     rdx, 4000000000h
0x1400078bd  sub     rax, qword ptr [rbp+170h+TotalNumberOfFreeBytes]
0x1400078c1  cmp     rax, rdx
0x1400078c4  jbe     short loc_1400078E9
0x1400078c6  mov     ecx, 2; Ix
0x1400078cb  call    _o___acrt_iob_func_0
0x1400078d0  mov     rcx, rax; Stream
0x1400078d3  lea     rdx, aSkippingDetail; "Skipping detailed capture of large volu"...
0x1400078da  call    fwprintf
0x1400078df  mov     ebx, 1
0x1400078e4  jmp     loc_140007976
0x1400078e9  lea     rdx, [rbp+170h+var_1E8]; int *
0x1400078ed  mov     ecx, r12d; unsigned int
0x1400078f0  call    ResetVolumeCounters
0x1400078f5  mov     ebx, eax
0x1400078f7  test    eax, eax
0x1400078f9  js      short loc_140007976
0x1400078fb  mov     r8d, [r13+4]
0x1400078ff  mov     r9, rdi
0x140007902  mov     edx, r12d
0x140007905  mov     rcx, r14; hDevice
0x140007908  call    ProcessVolumeRecords
0x14000790d  mov     ebx, eax
0x14000790f  test    eax, eax
0x140007911  js      short loc_140007976
0x140007913  mov     r9, [rbp+170h+var_1A8]
0x140007917  mov     r8d, r12d
0x14000791a  mov     rdx, r15
0x14000791d  mov     qword ptr [rsp+280h+dwCreationDisposition], rdi
0x140007922  mov     rcx, r13
0x140007925  call    ProcessRecords
0x14000792a  mov     ebx, eax
0x14000792c  test    eax, eax
0x14000792e  js      short loc_140007976
0x140007930  cmp     [rbp+170h+var_1E8], 0
0x140007934  jnz     short loc_140007944
0x140007936  cmp     dword ptr [r13+14h], 0
0x14000793b  jz      short loc_140007944
0x14000793d  mov     ebx, 1
0x140007942  jmp     short loc_140007946
0x140007944  xor     ebx, ebx
0x140007946  mov     rax, [rbp+170h+var_1A0]
0x14000794a  mov     r9, rdi
0x14000794d  mov     [rsp+280h+hTemplateFile], rax
0x140007952  mov     r8d, ebx
0x140007955  mov     rax, [rbp+170h+var_198]
0x140007959  mov     edx, r12d
0x14000795c  mov     qword ptr [rsp+280h+dwFlagsAndAttributes], rax
0x140007961  mov     rcx, r13
0x140007964  mov     [rsp+280h+dwCreationDisposition], esi
0x140007968  call    SummarizeResults
0x14000796d  mov     ebx, eax
0x14000796f  xor     eax, eax
0x140007971  test    ebx, ebx
0x140007973  cmovns  ebx, eax
0x140007976  mov     rcx, r14; hObject
0x140007979  call    cs:__imp_CloseHandle
0x14000797f  call    FreeVolumeCounters
0x140007984  mov     eax, ebx
0x140007986  mov     rcx, [rbp+170h+var_50]
0x14000798d  xor     rcx, rsp; StackCookie
0x140007990  call    __security_check_cookie
0x140007995  add     rsp, 248h
0x14000799c  pop     r15
0x14000799e  pop     r14
0x1400079a0  pop     r13
0x1400079a2  pop     r12
0x1400079a4  pop     rdi
0x1400079a5  pop     rsi
0x1400079a6  pop     rbx
0x1400079a7  pop     rbp
0x1400079a8  retn
```
