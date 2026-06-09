# DetermineIfMetabaseCanBeRenamed(ushort *,ushort *,int,int *)

- ea: `0x18001d314`
- end: `0x18001d60c`
- name: `?DetermineIfMetabaseCanBeRenamed@@YAXPEAG0HPEAH@Z`
- size: `760`
- prototype: `void(unsigned __int16 *, unsigned __int16 *, int, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180023548`

## callees

- `0x18001d314`
- `0x180030982`
- `0x1800309d0`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001d39c`
- `KERNEL32!LeaveCriticalSection` at `0x18001d478`
- `KERNEL32!LeaveCriticalSection` at `0x18001d39c`
- `KERNEL32!LeaveCriticalSection` at `0x18001d478`
- `KERNEL32!EnterCriticalSection` at `0x18001d379`
- `KERNEL32!EnterCriticalSection` at `0x18001d460`
- `KERNEL32!EnterCriticalSection` at `0x18001d5f6`
- `KERNEL32!EnterCriticalSection` at `0x18001d379`
- `KERNEL32!EnterCriticalSection` at `0x18001d460`
- `KERNEL32!EnterCriticalSection` at `0x18001d5f6`
- `KERNEL32!CompareFileTime` at `0x18001d559`
- `KERNEL32!CompareFileTime` at `0x18001d56b`
- `KERNEL32!CompareFileTime` at `0x18001d559`
- `KERNEL32!CompareFileTime` at `0x18001d56b`
- `KERNEL32!GetLastError` at `0x18001d3f6`
- `KERNEL32!GetLastError` at `0x18001d3f6`
- `KERNEL32!GetFileAttributesExW` at `0x18001d3e8`
- `KERNEL32!GetFileAttributesExW` at `0x18001d3e8`
- `IisRTL!PuDbgPrint` at `0x18001d4c9`
- `IisRTL!PuDbgPrint` at `0x18001d50a`
- `IisRTL!PuDbgPrint` at `0x18001d54b`
- `IisRTL!PuDbgPrint` at `0x18001d5bd`
- `IisRTL!PuDbgPrint` at `0x18001d4c9`
- `IisRTL!PuDbgPrint` at `0x18001d50a`
- `IisRTL!PuDbgPrint` at `0x18001d54b`
- `IisRTL!PuDbgPrint` at `0x18001d5bd`
- `IisRTL!PuDbgPrintW` at `0x18001d444`
- `IisRTL!PuDbgPrintW` at `0x18001d444`

## string_xrefs

- `0x18001d41b`: `[DetermineIfMetabaseCanBeRenamed] Coud not fetch file attributes of the metabase file. GetFileAttributesEx on %s failed with hr = 0x%x.\n`
- `0x18001d426`: `DetermineIfMetabaseCanBeRenamed`
- `0x18001d489`: `DetermineIfMetabaseCanBeRenamed`
- `0x18001d4bd`: `[DetermineIfMetabaseCanBeRenamed] CURRENT TIMESTAMPS:\nMetabaseFileLastWrite low: %d\nMetabaseFileLastWrite high: %d\n`
- `0x18001d4fe`: `[DetermineIfMetabaseCanBeRenamed] LAST SAVE TIMESTAMPS:\nMetabaseFileLastWrite low: %d\nMetabaseFileLastWrite high: %d\n`
- `0x18001d53f`: `[DetermineIfMetabaseCanBeRenamed] LAST EWR PROCESSED TIMESTAMPS:\nMetabaseFileLastWrite low: %d\nMetabaseFileLastWrite high: %d\n`
- `0x18001d5a1`: `[DetermineIfMetabaseCanBeRenamed] Metabase timestamp did not match last saved or last EWR processed timestamp. Renaming anyway.\n`

## pseudocode

```c
void __fastcall DetermineIfMetabaseCanBeRenamed(unsigned __int16 *a1, unsigned __int16 *a2, int a3, int *a4)
{
  signed int LastError; // eax
  unsigned int v9; // ebx
  FILETIME Buf1; // [rsp+40h] [rbp-40h] BYREF
  FILETIME FileTime2; // [rsp+48h] [rbp-38h] BYREF
  __int128 FileInformation; // [rsp+50h] [rbp-30h] BYREF
  FILETIME FileTime1[2]; // [rsp+60h] [rbp-20h] BYREF
  int v14; // [rsp+70h] [rbp-10h]

  v14 = 0;
  Buf1 = 0;
  FileTime2 = 0;
  FileInformation = 0;
  *(_OWORD *)&FileTime1[0].dwLowDateTime = 0;
  if ( g_fcsEditWhileRunningInitialized )
  {
    qword_180048CC8 = 0;
    EnterCriticalSection(&g_csEditWhileRunning);
    Buf1 = g_MostRecentMetabaseFileLastWriteTimeStamp;
    FileTime2 = g_EWRProcessedMetabaseTimeStamp;
    LeaveCriticalSection(&g_csEditWhileRunning);
    if ( g_dwEnableEditWhileRunning )
    {
      if ( !a1 && memcmp_0(&Buf1, &qword_180048CC8, 8u) )
      {
        *a4 = 0;
        if ( GetFileAttributesExW(a2, GetFileExInfoStandard, &FileInformation) )
        {
          if ( (g_dwDebugFlags & 3) != 0 )
          {
            PuDbgPrint(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              8989,
              "DetermineIfMetabaseCanBeRenamed",
              "[DetermineIfMetabaseCanBeRenamed] CURRENT TIMESTAMPS:\n"
              "MetabaseFileLastWrite low: %d\n"
              "MetabaseFileLastWrite high: %d\n",
              FileTime1[0].dwHighDateTime,
              FileTime1[1].dwLowDateTime);
            if ( (g_dwDebugFlags & 3) != 0 )
            {
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                8994,
                "DetermineIfMetabaseCanBeRenamed",
                "[DetermineIfMetabaseCanBeRenamed] LAST SAVE TIMESTAMPS:\n"
                "MetabaseFileLastWrite low: %d\n"
                "MetabaseFileLastWrite high: %d\n",
                Buf1.dwLowDateTime,
                Buf1.dwHighDateTime);
              if ( (g_dwDebugFlags & 3) != 0 )
                PuDbgPrint(
                  g_pDebug,
                  "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                  8999,
                  "DetermineIfMetabaseCanBeRenamed",
                  "[DetermineIfMetabaseCanBeRenamed] LAST EWR PROCESSED TIMESTAMPS:\n"
                  "MetabaseFileLastWrite low: %d\n"
                  "MetabaseFileLastWrite high: %d\n",
                  FileTime2.dwLowDateTime,
                  FileTime2.dwHighDateTime);
            }
          }
          if ( CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, &Buf1)
            && CompareFileTime((const FILETIME *)&FileTime1[0].dwHighDateTime, &FileTime2)
            && memcmp_0(&FileTime2, &qword_180048CC8, 8u) )
          {
            if ( !a3 )
            {
              EnterCriticalSection(&g_csEditWhileRunning);
              g_EWRProcessedMetabaseTimeStamp = 0;
              goto LABEL_12;
            }
            if ( (g_dwDebugFlags & 3) != 0 )
              PuDbgPrint(
                g_pDebug,
                "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
                9029,
                "DetermineIfMetabaseCanBeRenamed",
                "[DetermineIfMetabaseCanBeRenamed] Metabase timestamp did not match last saved or last EWR processed time"
                "stamp. Renaming anyway.\n");
          }
        }
        else
        {
          LastError = GetLastError();
          v9 = LastError;
          if ( LastError > 0 )
            v9 = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlags & 3) != 0 )
            PuDbgPrintW(
              g_pDebug,
              "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
              8960,
              "DetermineIfMetabaseCanBeRenamed",
              L"[DetermineIfMetabaseCanBeRenamed] Coud not fetch file attributes of the metabase file. GetFileAttributesEx"
               " on %s failed with hr = 0x%x.\n",
              a2,
              v9);
          if ( v9 + 2147024894 > 1 )
          {
            EnterCriticalSection(&g_csEditWhileRunning);
            g_MostRecentMetabaseFileLastWriteTimeStamp = 0;
LABEL_12:
            LeaveCriticalSection(&g_csEditWhileRunning);
            return;
          }
        }
      }
    }
  }
  *a4 = 1;
}

```

## disassembly

```asm
0x18001d314  mov     [rsp-18h+arg_0], rbx
0x18001d319  mov     [rsp-18h+arg_10], rsi
0x18001d31e  push    rbp
0x18001d31f  push    r12
0x18001d321  push    r15
0x18001d323  mov     rbp, rsp
0x18001d326  sub     rsp, 80h
0x18001d32d  mov     rax, cs:__security_cookie
0x18001d334  xor     rax, rsp
0x18001d337  mov     [rbp+var_8], rax
0x18001d33b  xor     eax, eax
0x18001d33d  xorps   xmm0, xmm0
0x18001d340  cmp     cs:?g_fcsEditWhileRunningInitialized@@3HA, eax; int g_fcsEditWhileRunningInitialized
0x18001d346  mov     r15, r9
0x18001d349  mov     r12d, r8d
0x18001d34c  mov     [rbp+var_10], eax
0x18001d34f  mov     rsi, rdx
0x18001d352  mov     [rbp+Buf1], rax
0x18001d356  mov     rbx, rcx
0x18001d359  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18001d35d  movups  [rbp+FileInformation], xmm0
0x18001d361  movups  xmmword ptr [rbp+FileTime1.dwLowDateTime], xmm0
0x18001d365  jz      loc_18001D5C3
0x18001d36b  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d372  mov     cs:qword_180048CC8, rax
0x18001d379  call    cs:__imp_EnterCriticalSection
0x18001d37f  mov     rax, cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x18001d386  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d38d  mov     [rbp+Buf1], rax
0x18001d391  mov     rax, cs:?g_EWRProcessedMetabaseTimeStamp@@3U_FILETIME@@A; _FILETIME g_EWRProcessedMetabaseTimeStamp
0x18001d398  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x18001d39c  call    cs:__imp_LeaveCriticalSection
0x18001d3a2  cmp     cs:?g_dwEnableEditWhileRunning@@3KA, 0; ulong g_dwEnableEditWhileRunning
0x18001d3a9  jz      loc_18001D5C3
0x18001d3af  test    rbx, rbx
0x18001d3b2  jnz     loc_18001D5C3
0x18001d3b8  mov     ebx, 8
0x18001d3bd  lea     rdx, qword_180048CC8; Buf2
0x18001d3c4  mov     r8d, ebx; Size
0x18001d3c7  lea     rcx, [rbp+Buf1]; Buf1
0x18001d3cb  call    memcmp_0
0x18001d3d0  test    eax, eax
0x18001d3d2  jz      loc_18001D5C3
0x18001d3d8  lea     r8, [rbp+FileInformation]; lpFileInformation
0x18001d3dc  mov     dword ptr [r15], 0
0x18001d3e3  xor     edx, edx; fInfoLevelId
0x18001d3e5  mov     rcx, rsi; lpFileName
0x18001d3e8  call    cs:__imp_GetFileAttributesExW
0x18001d3ee  test    eax, eax
0x18001d3f0  jnz     loc_18001D483
0x18001d3f6  call    cs:__imp_GetLastError
0x18001d3fc  mov     ebx, eax
0x18001d3fe  test    eax, eax
0x18001d400  jle     short loc_18001D40B
0x18001d402  movzx   ebx, ax
0x18001d405  or      ebx, 80070000h
0x18001d40b  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d412  jz      short loc_18001D44A
0x18001d414  mov     rcx, cs:g_pDebug
0x18001d41b  lea     rax, aDetermineifmet_0; "[DetermineIfMetabaseCanBeRenamed] Coud "...
0x18001d422  mov     [rsp+80h+var_50], ebx
0x18001d426  lea     r9, aDetermineifmet_2; "DetermineIfMetabaseCanBeRenamed"
0x18001d42d  mov     [rsp+80h+var_58], rsi
0x18001d432  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d439  mov     r8d, 2300h
0x18001d43f  mov     [rsp+80h+var_60], rax
0x18001d444  call    cs:__imp_PuDbgPrintW
0x18001d44a  lea     eax, [rbx+7FF8FFFEh]
0x18001d450  cmp     eax, 1
0x18001d453  jbe     loc_18001D5C3
0x18001d459  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d460  call    cs:__imp_EnterCriticalSection
0x18001d466  mov     cs:?g_MostRecentMetabaseFileLastWriteTimeStamp@@3U_FILETIME@@A, 0; _FILETIME g_MostRecentMetabaseFileLastWriteTimeStamp
0x18001d471  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d478  call    cs:__imp_LeaveCriticalSection
0x18001d47e  jmp     loc_18001D5CA
0x18001d483  mov     eax, cs:g_dwDebugFlags
0x18001d489  lea     rsi, aDetermineifmet_2; "DetermineIfMetabaseCanBeRenamed"
0x18001d490  test    al, 3
0x18001d492  jz      loc_18001D551
0x18001d498  mov     eax, [rbp+FileTime1.dwLowDateTime+8]
0x18001d49b  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d4a2  mov     rcx, cs:g_pDebug
0x18001d4a9  mov     r9, rsi
0x18001d4ac  mov     [rsp+80h+var_50], eax
0x18001d4b0  mov     r8d, 231Dh
0x18001d4b6  mov     eax, [rbp+FileTime1.dwHighDateTime]
0x18001d4b9  mov     dword ptr [rsp+80h+var_58], eax
0x18001d4bd  lea     rax, aDetermineifmet_3; "[DetermineIfMetabaseCanBeRenamed] CURRE"...
0x18001d4c4  mov     [rsp+80h+var_60], rax
0x18001d4c9  call    cs:__imp_PuDbgPrint
0x18001d4cf  mov     eax, cs:g_dwDebugFlags
0x18001d4d5  test    al, 3
0x18001d4d7  jz      short loc_18001D551
0x18001d4d9  mov     eax, dword ptr [rbp+Buf1+4]
0x18001d4dc  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d4e3  mov     rcx, cs:g_pDebug
0x18001d4ea  mov     r9, rsi
0x18001d4ed  mov     [rsp+80h+var_50], eax
0x18001d4f1  mov     r8d, 2322h
0x18001d4f7  mov     eax, dword ptr [rbp+Buf1]
0x18001d4fa  mov     dword ptr [rsp+80h+var_58], eax
0x18001d4fe  lea     rax, aDetermineifmet_1; "[DetermineIfMetabaseCanBeRenamed] LAST "...
0x18001d505  mov     [rsp+80h+var_60], rax
0x18001d50a  call    cs:__imp_PuDbgPrint
0x18001d510  mov     eax, cs:g_dwDebugFlags
0x18001d516  test    al, 3
0x18001d518  jz      short loc_18001D551
0x18001d51a  mov     eax, [rbp+FileTime2.dwHighDateTime]
0x18001d51d  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d524  mov     rcx, cs:g_pDebug
0x18001d52b  mov     r9, rsi
0x18001d52e  mov     [rsp+80h+var_50], eax
0x18001d532  mov     r8d, 2327h
0x18001d538  mov     eax, [rbp+FileTime2.dwLowDateTime]
0x18001d53b  mov     dword ptr [rsp+80h+var_58], eax
0x18001d53f  lea     rax, aDetermineifmet; "[DetermineIfMetabaseCanBeRenamed] LAST "...
0x18001d546  mov     [rsp+80h+var_60], rax
0x18001d54b  call    cs:__imp_PuDbgPrint
0x18001d551  lea     rdx, [rbp+Buf1]; lpFileTime2
0x18001d555  lea     rcx, [rbp+FileTime1.dwHighDateTime]; lpFileTime1
0x18001d559  call    cs:__imp_CompareFileTime
0x18001d55f  test    eax, eax
0x18001d561  jz      short loc_18001D5C3
0x18001d563  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18001d567  lea     rcx, [rbp+FileTime1.dwHighDateTime]; lpFileTime1
0x18001d56b  call    cs:__imp_CompareFileTime
0x18001d571  test    eax, eax
0x18001d573  jz      short loc_18001D5C3
0x18001d575  mov     r8, rbx; Size
0x18001d578  lea     rdx, qword_180048CC8; Buf2
0x18001d57f  lea     rcx, [rbp+FileTime2]; Buf1
0x18001d583  call    memcmp_0
0x18001d588  test    eax, eax
0x18001d58a  jz      short loc_18001D5C3
0x18001d58c  test    r12d, r12d
0x18001d58f  jz      short loc_18001D5EF
0x18001d591  test    byte ptr cs:g_dwDebugFlags, 3
0x18001d598  jz      short loc_18001D5C3
0x18001d59a  mov     rcx, cs:g_pDebug
0x18001d5a1  lea     rax, aDetermineifmet_4; "[DetermineIfMetabaseCanBeRenamed] Metab"...
0x18001d5a8  mov     r9, rsi
0x18001d5ab  mov     [rsp+80h+var_60], rax
0x18001d5b0  mov     r8d, 2345h
0x18001d5b6  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001d5bd  call    cs:__imp_PuDbgPrint
0x18001d5c3  mov     dword ptr [r15], 1
0x18001d5ca  mov     rcx, [rbp+var_8]
0x18001d5ce  xor     rcx, rsp; StackCookie
0x18001d5d1  call    __security_check_cookie
0x18001d5d6  lea     r11, [rsp+80h+var_s0]
0x18001d5de  mov     rbx, [r11+20h]
0x18001d5e2  mov     rsi, [r11+30h]
0x18001d5e6  mov     rsp, r11
0x18001d5e9  pop     r15
0x18001d5eb  pop     r12
0x18001d5ed  pop     rbp
0x18001d5ee  retn
0x18001d5ef  lea     rcx, ?g_csEditWhileRunning@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001d5f6  call    cs:__imp_EnterCriticalSection
0x18001d5fc  mov     cs:?g_EWRProcessedMetabaseTimeStamp@@3U_FILETIME@@A, 0; _FILETIME g_EWRProcessedMetabaseTimeStamp
0x18001d607  jmp     loc_18001D471
```
