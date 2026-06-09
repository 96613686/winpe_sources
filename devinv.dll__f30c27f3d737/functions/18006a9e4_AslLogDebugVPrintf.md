# AslLogDebugVPrintf

- ea: `0x18006a9e4`
- end: `0x18006b1a1`
- name: `AslLogDebugVPrintf`
- size: `1981`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800608e0`

## callees

- `0x180005e40`
- `0x180006f60`
- `0x180007068`
- `0x18006855c`
- `0x180068990`
- `0x180069ef0`
- `0x18006a070`
- `0x18006a274`
- `0x18006a380`
- `0x18006a48c`
- `0x18006a550`
- `0x18006a9e4`
- `0x18010d870`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18006b11e`
- `ntdll!EtwEventWrite` at `0x18006b11e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006aaef`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18006aaef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ab07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ab22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ab07`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18006ab22`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b15a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006b15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ab65`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006b178`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18006b178`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006b16e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006b16e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ab91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ab91`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006af17`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18006af17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ab5a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ab5a`

## string_xrefs

- `0x18006aae6`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, const char *a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ProcAddress; // rax
  HMODULE v14; // rcx
  HANDLE FileW; // rax
  DWORD LastError; // eax
  char v17; // al
  const wchar_t *v18; // rbx
  __int64 v19; // rcx
  wchar_t *v20; // rax
  const wchar_t *v21; // r8
  __int64 v22; // rdx
  wchar_t *v23; // rcx
  wchar_t v24; // ax
  wchar_t *v25; // rcx
  int v26; // eax
  __int64 v27; // r13
  __int64 v28; // rcx
  WCHAR *v29; // rax
  __int64 v30; // rdx
  WCHAR *v31; // rcx
  wchar_t *v32; // r14
  int v33; // r12d
  unsigned __int64 v34; // rsi
  unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // r15
  wchar_t *v37; // rdx
  unsigned __int64 v38; // rax
  int v39; // ecx
  unsigned __int64 v40; // rbx
  int v41; // eax
  __int64 v42; // rax
  const wchar_t *v43; // rdx
  wchar_t *v44; // rcx
  unsigned __int64 i; // rax
  unsigned __int16 v46; // cx
  __int64 v47; // r14
  unsigned __int64 v48; // rbx
  CHAR v49; // al
  int v50; // ecx
  const char *v51; // rax
  __int64 v52; // r15
  __int64 v53; // rax
  const char *v54; // r8
  unsigned __int64 v55; // rdx
  CHAR *v56; // rcx
  CHAR *v57; // rax
  __int64 v58; // rax
  CHAR *v59; // rdi
  unsigned __int64 v60; // rbx
  unsigned __int64 v61; // rsi
  int v62; // eax
  const char *v63; // rax
  unsigned __int64 v64; // rdx
  CHAR *v65; // rcx
  CHAR *v66; // rax
  unsigned __int64 v67; // r8
  struct _ASL_LOG *v68; // rbx
  __int64 v69; // rcx
  unsigned int v70; // edi
  __int64 *v71; // rdx
  char v72; // [rsp+50h] [rbp-B0h]
  char v73; // [rsp+51h] [rbp-AFh]
  int v74; // [rsp+54h] [rbp-ACh]
  int v75; // [rsp+58h] [rbp-A8h]
  DWORD dwErrCode; // [rsp+60h] [rbp-A0h]
  wchar_t *Buffer; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v80; // [rsp+78h] [rbp-88h] BYREF
  va_list Args; // [rsp+80h] [rbp-80h]
  struct _ASL_LOG *v82; // [rsp+88h] [rbp-78h]
  __int64 v83; // [rsp+90h] [rbp-70h]
  char *v84; // [rsp+98h] [rbp-68h] BYREF
  int v85; // [rsp+A0h] [rbp-60h]
  int v86; // [rsp+A4h] [rbp-5Ch]
  CHAR MultiByteStr[1024]; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Format[1024]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR WideCharStr[1024]; // [rsp+CB0h] [rbp+BB0h] BYREF

  v84 = a5;
  Args = a6;
  v83 = a4;
  v82 = (struct _ASL_LOG *)a1;
  if ( a1 )
  {
    dwErrCode = GetLastError();
    MultiByteStr[0] = 0;
    if ( a2 != 3 || (v9 = *a1, (*(_BYTE *)(*a1 + 80) & 0x10) != 0) )
    {
      v9 = *a1;
      v10 = 1;
      v72 = 1;
    }
    else
    {
      v10 = 0;
      v72 = 0;
    }
    v11 = 3;
    v12 = *(_DWORD *)(v9 + 80) & 0x100;
    v74 = v12;
    if ( a2 < 3 )
      v11 = a2;
    v75 = v11;
    if ( !a1[90] && qword_180157A90 )
    {
      dword_180157A9C = 0;
      qword_180157A90 = 0;
      qword_180157AA8 = 0;
    }
    if ( !dword_180157A9C )
    {
      dword_180157A9C = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ProcAddress = GetProcAddress((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_180157A90 = (__int64)ProcAddress;
        qword_180157AA8 = (__int64)GetProcAddress(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v12 = v74;
        if ( LastError == 231 )
          dword_180157A88 = 1;
      }
      else
      {
        dword_180157A88 = 1;
        CloseHandle(FileW);
        v12 = v74;
      }
    }
    if ( !qword_180157A90 || (v17 = 1, !qword_180157AA8) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_180157A88 || v12 )
    {
      Buffer = WideCharStr;
      v80 = 1022;
      v18 = L"ASL_LOG FAIL: ";
      if ( (int)RtlStringCchPrintfW(Format, 1024, L"%hs", a5) < 0 )
      {
        v19 = 2147483646;
        v20 = Format;
        v21 = L"ASL_LOG FAIL: ";
        v22 = 1024;
        do
        {
          if ( !v19 )
            break;
          if ( !*v21 )
            break;
          *v20++ = *v21++;
          --v19;
          --v22;
        }
        while ( v22 );
        v23 = v20 - 1;
        if ( v22 )
          v23 = v20;
        *v23 = 0;
      }
      v24 = Format[0];
      if ( Format[0] )
      {
        v25 = Format;
        do
        {
          if ( v24 == 37 )
          {
            do
            {
              do
                ++v25;
              while ( *v25 == 46 );
            }
            while ( (unsigned __int16)(*v25 - 48) <= 9u );
            if ( *v25 == 115 )
            {
              *v25 = 83;
            }
            else if ( *v25 == 83 )
            {
              *v25 = 115;
            }
          }
          v24 = *++v25;
        }
        while ( *v25 );
      }
      v26 = a4;
      if ( a4 == -1 )
        v26 = 0;
      v27 = 2LL * v11;
      if ( (int)RtlStringCchPrintfExW(
                  WideCharStr,
                  0x3FEu,
                  &Buffer,
                  &v80,
                  0x100u,
                  L"%hs,%hs,%d,",
                  (&off_180119448)[2 * v11],
                  a3,
                  v26) < 0 )
      {
        v28 = 2147483646;
        v29 = WideCharStr;
        v30 = 1024;
        do
        {
          if ( !v28 )
            break;
          if ( !*v18 )
            break;
          *v29++ = *v18++;
          --v28;
          --v30;
        }
        while ( v30 );
        v31 = v29 - 1;
        if ( v30 )
          v31 = v29;
        *v31 = 0;
      }
      v32 = Buffer;
      v33 = -2147483643;
      v34 = v80;
      v35 = Buffer;
      v36 = v80;
      if ( !Buffer && v80 || v80 > 0x7FFFFFFF )
      {
        *Buffer = 0;
LABEL_73:
        if ( v34 )
        {
          if ( v34 <= 0x7FFFFFFF )
          {
            v42 = 2147483646;
            v43 = L"Message too long!";
            do
            {
              if ( !v42 )
                break;
              if ( !*v43 )
                break;
              *v32++ = *v43++;
              --v42;
              --v34;
            }
            while ( v34 );
            v44 = v32 - 1;
            if ( v34 )
              v44 = v32;
            *v44 = 0;
          }
          else
          {
            *v32 = 0;
          }
        }
LABEL_83:
        for ( i = 0; i < v36; ++i )
        {
          v46 = v35[i];
          if ( !v46 )
            break;
          if ( v46 == 10 || v46 == 13 )
          {
            v35[i] = 35;
          }
          else if ( v46 == 44 )
          {
            v35[i] = 95;
          }
        }
        RtlStringCchCatW(v35, v36, L"\r\n");
        v47 = -1;
        v48 = -1;
        do
          ++v48;
        while ( WideCharStr[v48] );
        if ( dword_180157A88 )
          AslLogpWritePipe(WideCharStr, 2 * v48);
        if ( WideCharToMultiByte(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
        {
          v49 = MultiByteStr[0];
        }
        else
        {
          v49 = 0;
          MultiByteStr[0] = 0;
        }
        if ( v49 )
        {
LABEL_136:
          v67 = -1;
          do
            ++v67;
          while ( MultiByteStr[v67] );
          if ( v72 || v74 )
          {
            v68 = v82;
            AslLogpWriteLog(v82, MultiByteStr, v67);
          }
          else
          {
            v68 = v82;
          }
          if ( a2 != 1 || (v69 = *((_QWORD *)v68 + 89)) == 0 )
          {
            v70 = v75;
            goto LABEL_152;
          }
          v84 = MultiByteStr;
          do
            ++v47;
          while ( MultiByteStr[v47] );
          v70 = v75;
          v85 = v47 + 1;
          v86 = 0;
          if ( v75 == 1 )
          {
            v71 = AE_DEBUG_EVENT;
          }
          else
          {
            if ( v75 != 2 )
            {
LABEL_152:
              if ( v73 )
                AslLogpWritePanther(v68, v70, a3, v83, MultiByteStr);
              SetLastError(dwErrCode);
              if ( v70 == 1 && (*(_BYTE *)(*(_QWORD *)v68 + 80LL) & 2) != 0 )
              {
                if ( IsDebuggerPresent() )
                  DebugBreak();
              }
              return;
            }
            v71 = AE_MARK_EVENT;
          }
          EtwEventWrite(v69, v71, 1, &v84);
          goto LABEL_152;
        }
        v50 = v83;
        if ( v83 == -1 )
          v50 = 0;
        v51 = a3;
        if ( !a3 )
          v51 = (const char *)&dword_18011E004;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_180119448)[v27], v51, v50) < 0 && v48 )
        {
          v52 = 2147483646;
          if ( v48 <= 0x7FFFFFFF )
          {
            v53 = 2147483646;
            v54 = "ASL_LOG FAIL: ";
            v55 = v48;
            v56 = MultiByteStr;
            do
            {
              if ( !v53 )
                break;
              if ( !*v54 )
                break;
              *v56++ = *v54++;
              --v53;
              --v55;
            }
            while ( v55 );
            v57 = v56 - 1;
            if ( v55 )
              v57 = v56;
            *v57 = 0;
          }
          else
          {
            MultiByteStr[0] = 0;
          }
        }
        else
        {
          v52 = 2147483646;
        }
        v58 = -1;
        do
          ++v58;
        while ( MultiByteStr[v58] );
        v59 = &MultiByteStr[v58];
        v60 = v48 - v58;
        if ( v60 )
        {
          if ( v60 > 0x7FFFFFFF )
          {
            *v59 = 0;
            goto LABEL_126;
          }
          v61 = v60 - 1;
          v62 = vsnprintf(&MultiByteStr[v58], v60 - 1, v84, Args);
          if ( v62 < 0 || v62 > v61 || (v33 = 0, v62 == v61) )
            v59[v61] = 0;
          if ( v33 >= 0 )
            goto LABEL_135;
        }
        if ( !v60 )
        {
LABEL_135:
          AslLogpFinalizeBuffer(v59, v60 + 2);
          goto LABEL_136;
        }
LABEL_126:
        if ( v60 <= 0x7FFFFFFF )
        {
          v63 = "Message too long!";
          v64 = v60;
          v65 = v59;
          do
          {
            if ( !v52 )
              break;
            if ( !*v63 )
              break;
            *v65++ = *v63++;
            --v52;
            --v64;
          }
          while ( v64 );
          v66 = v65 - 1;
          if ( v64 )
            v66 = v65;
          *v66 = 0;
        }
        else
        {
          *v59 = 0;
        }
        goto LABEL_135;
      }
      if ( !v80 )
      {
        v37 = Buffer;
        v38 = 0;
        v39 = 0;
        if ( Format[0] )
        {
          if ( !Buffer )
          {
            v39 = -1073741811;
LABEL_71:
            if ( (int)(v39 + 0x80000000) < 0 || v39 == -2147483643 )
              goto LABEL_83;
            goto LABEL_73;
          }
          v39 = -2147483643;
        }
LABEL_70:
        v32 = v37;
        v34 = v38;
        goto LABEL_71;
      }
      v40 = v80 - 1;
      v41 = vsnwprintf(Buffer, v80 - 1, Format, Args);
      if ( v41 < 0 || v41 > v40 )
      {
        v39 = -2147483643;
      }
      else
      {
        v39 = 0;
        if ( v41 != v40 )
        {
          v40 = v41;
LABEL_69:
          v37 = &v32[v40];
          v38 = v36 - v40;
          goto LABEL_70;
        }
      }
      v32[v40] = 0;
      goto LABEL_69;
    }
  }
}

```

## disassembly

```asm
0x18006a9e4  push    rbp
0x18006a9e6  push    rbx
0x18006a9e7  push    rsi
0x18006a9e8  push    rdi
0x18006a9e9  push    r12
0x18006a9eb  push    r13
0x18006a9ed  push    r14
0x18006a9ef  push    r15
0x18006a9f1  lea     rbp, [rsp-13C8h]
0x18006a9f9  mov     eax, 14C8h
0x18006a9fe  call    _alloca_probe
0x18006aa03  sub     rsp, rax
0x18006aa06  mov     rax, cs:__security_cookie
0x18006aa0d  xor     rax, rsp
0x18006aa10  mov     [rbp+1400h+var_50], rax
0x18006aa17  mov     r12, [rbp+1400h+arg_20]
0x18006aa1e  mov     r13, r9
0x18006aa21  mov     rax, [rbp+1400h+arg_28]
0x18006aa28  mov     esi, edx
0x18006aa2a  mov     [rbp+1400h+var_1468], r12
0x18006aa2e  mov     rbx, rcx
0x18006aa31  mov     [rbp+1400h+Args], rax
0x18006aa35  mov     [rbp+1400h+var_1470], r9
0x18006aa39  mov     [rsp+1500h+var_1498], r8
0x18006aa3e  mov     [rsp+1500h+var_14A4], edx
0x18006aa42  mov     [rbp+1400h+var_1478], rcx
0x18006aa46  test    rcx, rcx
0x18006aa49  jz      loc_18006B17E
0x18006aa4f  call    cs:__imp_GetLastError
0x18006aa55  xor     edx, edx
0x18006aa57  mov     [rsp+1500h+dwErrCode], eax
0x18006aa5b  mov     [rbp+1400h+MultiByteStr], dl
0x18006aa5e  cmp     esi, 3
0x18006aa61  jnz     short loc_18006AA75
0x18006aa63  mov     rax, [rbx]
0x18006aa66  test    byte ptr [rax+50h], 10h
0x18006aa6a  jnz     short loc_18006AA75
0x18006aa6c  mov     r15b, dl
0x18006aa6f  mov     [rsp+1500h+var_14B0], dl
0x18006aa73  jmp     short loc_18006AA80
0x18006aa75  mov     rax, [rbx]
0x18006aa78  mov     r15b, 1
0x18006aa7b  mov     [rsp+1500h+var_14B0], r15b
0x18006aa80  mov     ecx, [rax+50h]
0x18006aa83  mov     r14d, 3
0x18006aa89  and     ecx, 100h
0x18006aa8f  cmp     esi, r14d
0x18006aa92  mov     [rsp+1500h+var_14AC], ecx
0x18006aa96  cmovl   r14d, esi
0x18006aa9a  mov     [rsp+1500h+var_14A8], r14d
0x18006aa9f  cmp     [rbx+2D0h], rdx
0x18006aaa6  jnz     short loc_18006AAC5
0x18006aaa8  cmp     cs:qword_180157A90, rdx
0x18006aaaf  jz      short loc_18006AAC5
0x18006aab1  mov     cs:dword_180157A9C, edx
0x18006aab7  mov     cs:qword_180157A90, rdx
0x18006aabe  mov     cs:qword_180157AA8, rdx
0x18006aac5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18006aac9  cmp     cs:dword_180157A9C, edx
0x18006aacf  jnz     loc_18006AB9D
0x18006aad5  lea     r8, [rbx+2D0h]; phModule
0x18006aadc  mov     cs:dword_180157A9C, 1
0x18006aae6  lea     rdx, aWdscoreDll; "wdscore.dll"
0x18006aaed  xor     ecx, ecx; dwFlags
0x18006aaef  call    cs:__imp_GetModuleHandleExA
0x18006aaf5  test    eax, eax
0x18006aaf7  jz      short loc_18006AB2F
0x18006aaf9  mov     rcx, [rbx+2D0h]; hModule
0x18006ab00  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x18006ab07  call    cs:__imp_GetProcAddress
0x18006ab0d  mov     rcx, [rbx+2D0h]; hModule
0x18006ab14  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x18006ab1b  mov     cs:qword_180157A90, rax
0x18006ab22  call    cs:__imp_GetProcAddress
0x18006ab28  mov     cs:qword_180157AA8, rax
0x18006ab2f  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x18006ab38  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18006ab3f  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18006ab47  xor     r9d, r9d; lpSecurityAttributes
0x18006ab4a  xor     r8d, r8d; dwShareMode
0x18006ab4d  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x18006ab55  mov     edx, 40000000h; dwDesiredAccess
0x18006ab5a  call    cs:__imp_CreateFileW
0x18006ab60  cmp     rax, rdi
0x18006ab63  jnz     short loc_18006AB84
0x18006ab65  call    cs:__imp_GetLastError
0x18006ab6b  mov     ecx, [rsp+1500h+var_14AC]
0x18006ab6f  xor     edx, edx
0x18006ab71  cmp     eax, 0E7h
0x18006ab76  jnz     short loc_18006AB9D
0x18006ab78  mov     cs:dword_180157A88, 1
0x18006ab82  jmp     short loc_18006AB9D
0x18006ab84  mov     rcx, rax; hObject
0x18006ab87  mov     cs:dword_180157A88, 1
0x18006ab91  call    cs:__imp_CloseHandle
0x18006ab97  mov     ecx, [rsp+1500h+var_14AC]
0x18006ab9b  xor     edx, edx
0x18006ab9d  cmp     cs:qword_180157A90, rdx
0x18006aba4  jz      short loc_18006ABB1
0x18006aba6  cmp     cs:qword_180157AA8, rdx
0x18006abad  mov     al, 1
0x18006abaf  jnz     short loc_18006ABB3
0x18006abb1  mov     al, dl
0x18006abb3  mov     [rsp+1500h+var_14AF], al
0x18006abb7  test    r15b, r15b
0x18006abba  jnz     short loc_18006ABD5
0x18006abbc  cmp     esi, 1
0x18006abbf  jz      short loc_18006ABD5
0x18006abc1  test    al, al
0x18006abc3  jnz     short loc_18006ABD5
0x18006abc5  cmp     cs:dword_180157A88, edx
0x18006abcb  jnz     short loc_18006ABD5
0x18006abcd  test    ecx, ecx
0x18006abcf  jz      loc_18006B17E
0x18006abd5  mov     r15d, 3FEh
0x18006abdb  lea     rax, [rbp+1400h+WideCharStr]
0x18006abe2  mov     r9, r12
0x18006abe5  mov     [rsp+1500h+Buffer], rax
0x18006abea  lea     r8, aHs_1; "%hs"
0x18006abf1  mov     [rsp+1500h+var_1488], r15
0x18006abf6  lea     rcx, [rbp+1400h+Format]
0x18006abfd  lea     r12d, [r15+2]
0x18006ac01  mov     edx, r12d
0x18006ac04  call    RtlStringCchPrintfW
0x18006ac09  xor     r10d, r10d
0x18006ac0c  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x18006ac13  mov     esi, 7FFFFFFEh
0x18006ac18  test    eax, eax
0x18006ac1a  jns     short loc_18006AC5E
0x18006ac1c  mov     ecx, esi
0x18006ac1e  lea     rax, [rbp+1400h+Format]
0x18006ac25  mov     r8, rbx
0x18006ac28  mov     edx, r12d
0x18006ac2b  test    rcx, rcx
0x18006ac2e  jz      short loc_18006AC4F
0x18006ac30  movzx   r9d, word ptr [r8]
0x18006ac34  test    r9w, r9w
0x18006ac38  jz      short loc_18006AC4F
0x18006ac3a  mov     [rax], r9w
0x18006ac3e  add     r8, 2
0x18006ac42  add     rax, 2
0x18006ac46  dec     rcx
0x18006ac49  sub     rdx, 1
0x18006ac4d  jnz     short loc_18006AC2B
0x18006ac4f  test    rdx, rdx
0x18006ac52  lea     rcx, [rax-2]
0x18006ac56  cmovnz  rcx, rax
0x18006ac5a  mov     [rcx], r10w
0x18006ac5e  movzx   eax, [rbp+1400h+Format]
0x18006ac65  test    ax, ax
0x18006ac68  jz      short loc_18006ACB7
0x18006ac6a  mov     edx, 53h ; 'S'
0x18006ac6f  lea     rcx, [rbp+1400h+Format]
0x18006ac76  lea     r8d, [rdx+20h]
0x18006ac7a  cmp     ax, 25h ; '%'
0x18006ac7e  jnz     short loc_18006ACAB
0x18006ac80  add     rcx, 2
0x18006ac84  cmp     word ptr [rcx], 2Eh ; '.'
0x18006ac88  jz      short loc_18006AC80
0x18006ac8a  movzx   eax, word ptr [rcx]
0x18006ac8d  sub     ax, 30h ; '0'
0x18006ac91  cmp     ax, 9
0x18006ac95  jbe     short loc_18006AC80
0x18006ac97  cmp     [rcx], r8w
0x18006ac9b  jnz     short loc_18006ACA2
0x18006ac9d  mov     [rcx], dx
0x18006aca0  jmp     short loc_18006ACAB
0x18006aca2  cmp     [rcx], dx
0x18006aca5  jnz     short loc_18006ACAB
0x18006aca7  mov     [rcx], r8w
0x18006acab  add     rcx, 2
0x18006acaf  movzx   eax, word ptr [rcx]
0x18006acb2  test    ax, ax
0x18006acb5  jnz     short loc_18006AC7A
0x18006acb7  mov     eax, r13d
0x18006acba  cmp     r13, rdi
0x18006acbd  jnz     short loc_18006ACC2
0x18006acbf  mov     eax, r10d
0x18006acc2  mov     [rsp+1500h+var_14C0], eax
0x18006acc6  lea     rcx, off_180119448; "PRINT"
0x18006accd  mov     rax, [rsp+1500h+var_1498]
0x18006acd2  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x18006acd7  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x18006acdc  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x18006ace1  movsxd  r13, r14d
0x18006ace4  mov     rdx, r15; unsigned __int64
0x18006ace7  add     r13, r13
0x18006acea  mov     rax, [rcx+r13*8]
0x18006acee  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x18006acf5  mov     [rsp+1500h+hTemplateFile], rax
0x18006acfa  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x18006ad01  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x18006ad06  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x18006ad0e  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18006ad13  xor     r9d, r9d
0x18006ad16  test    eax, eax
0x18006ad18  jns     short loc_18006AD5A
0x18006ad1a  mov     rcx, rsi
0x18006ad1d  lea     rax, [rbp+1400h+WideCharStr]
0x18006ad24  mov     rdx, r12
0x18006ad27  test    rcx, rcx
0x18006ad2a  jz      short loc_18006AD4B
0x18006ad2c  movzx   r8d, word ptr [rbx]
0x18006ad30  test    r8w, r8w
0x18006ad34  jz      short loc_18006AD4B
0x18006ad36  mov     [rax], r8w
0x18006ad3a  add     rbx, 2
0x18006ad3e  add     rax, 2
0x18006ad42  dec     rcx
0x18006ad45  sub     rdx, 1
0x18006ad49  jnz     short loc_18006AD27
0x18006ad4b  test    rdx, rdx
0x18006ad4e  lea     rcx, [rax-2]
0x18006ad52  cmovnz  rcx, rax
0x18006ad56  mov     [rcx], r9w
0x18006ad5a  mov     r14, [rsp+1500h+Buffer]
0x18006ad5f  mov     r12d, 80000005h
0x18006ad65  mov     rsi, [rsp+1500h+var_1488]
0x18006ad6a  mov     rdi, r14
0x18006ad6d  mov     r15, rsi
0x18006ad70  test    r14, r14
0x18006ad73  jnz     short loc_18006AD7A
0x18006ad75  test    rsi, rsi
0x18006ad78  jnz     short loc_18006AD83
0x18006ad7a  cmp     r15, 7FFFFFFFh
0x18006ad81  jbe     short loc_18006AD8C
0x18006ad83  mov     [r14], r9w
0x18006ad87  jmp     loc_18006AE19
0x18006ad8c  test    r15, r15
0x18006ad8f  jnz     short loc_18006ADB5
0x18006ad91  mov     rdx, rdi
0x18006ad94  mov     rax, r15
0x18006ad97  mov     ecx, r9d
0x18006ad9a  cmp     [rbp+1400h+Format], r9w
0x18006ada2  jz      short loc_18006AE02
0x18006ada4  test    rdi, rdi
0x18006ada7  jnz     short loc_18006ADB0
0x18006ada9  mov     ecx, 0C000000Dh
0x18006adae  jmp     short loc_18006AE08
0x18006adb0  mov     ecx, r12d
0x18006adb3  jmp     short loc_18006AE02
0x18006adb5  mov     r9, [rbp+1400h+Args]; Args
0x18006adb9  lea     rbx, [rsi-1]
0x18006adbd  mov     rdx, rbx; BufferCount
0x18006adc0  lea     r8, [rbp+1400h+Format]; Format
0x18006adc7  mov     rcx, rdi; Buffer
0x18006adca  call    _vsnwprintf
0x18006adcf  xor     r9d, r9d
0x18006add2  test    eax, eax
0x18006add4  js      short loc_18006ADE7
0x18006add6  cdqe
0x18006add8  cmp     rax, rbx
0x18006addb  ja      short loc_18006ADE7
0x18006addd  mov     ecx, r9d
0x18006ade0  jz      short loc_18006ADEA
0x18006ade2  mov     rbx, rax
0x18006ade5  jmp     short loc_18006ADEF
0x18006ade7  mov     ecx, r12d
0x18006adea  mov     [r14+rbx*2], r9w
0x18006adef  mov     rax, r15
0x18006adf2  lea     rdx, [r14+rbx*2]
0x18006adf6  sub     rax, rbx
0x18006adf9  test    ecx, ecx
0x18006adfb  jns     short loc_18006AE02
0x18006adfd  cmp     ecx, r12d
0x18006ae00  jnz     short loc_18006AE08
0x18006ae02  mov     r14, rdx
0x18006ae05  mov     rsi, rax
0x18006ae08  mov     edx, 80000000h
0x18006ae0d  lea     eax, [rcx+rdx]
0x18006ae10  test    edx, eax
0x18006ae12  jnz     short loc_18006AE6F
0x18006ae14  cmp     ecx, r12d
0x18006ae17  jz      short loc_18006AE6F
0x18006ae19  test    rsi, rsi
0x18006ae1c  jz      short loc_18006AE6F
0x18006ae1e  cmp     rsi, 7FFFFFFFh
0x18006ae25  jbe     short loc_18006AE2F
0x18006ae27  xor     esi, esi
0x18006ae29  mov     [r14], si
0x18006ae2d  jmp     short loc_18006AE71
0x18006ae2f  mov     eax, 7FFFFFFEh
0x18006ae34  lea     rdx, aMessageTooLong; "Message too long!"
0x18006ae3b  test    rax, rax
0x18006ae3e  jz      short loc_18006AE5D
0x18006ae40  movzx   ecx, word ptr [rdx]
0x18006ae43  test    cx, cx
0x18006ae46  jz      short loc_18006AE5D
0x18006ae48  mov     [r14], cx
0x18006ae4c  add     rdx, 2
0x18006ae50  add     r14, 2
0x18006ae54  dec     rax
0x18006ae57  sub     rsi, 1
0x18006ae5b  jnz     short loc_18006AE3B
0x18006ae5d  test    rsi, rsi
0x18006ae60  lea     rcx, [r14-2]
0x18006ae64  cmovnz  rcx, r14
0x18006ae68  xor     esi, esi
0x18006ae6a  mov     [rcx], si
0x18006ae6d  jmp     short loc_18006AE71
  ... truncated ...
```
