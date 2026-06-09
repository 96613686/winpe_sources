# AslLogDebugVPrintf

- ea: `0x1400050a0`
- end: `0x14000585c`
- name: `AslLogDebugVPrintf`
- size: `1980`
- prototype: `void __fastcall(__int64 *, int, __int64, __int64, char *, va_list)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x140002b70`

## callees

- `0x1400023a2`
- `0x1400023ae`
- `0x1400043fc`
- `0x14000457c`
- `0x140004780`
- `0x14000488c`
- `0x140004998`
- `0x140004a5c`
- `0x140004adc`
- `0x140004ca4`
- `0x1400050a0`
- `0x1400115f0`
- `0x1400116b0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140005483`
- `msvcrt!_vsnwprintf` at `0x140005483`
- `msvcrt!_vsnprintf` at `0x1400056d8`
- `msvcrt!_vsnprintf` at `0x1400056d8`
- `ntdll!EtwEventWrite` at `0x1400057d9`
- `ntdll!EtwEventWrite` at `0x1400057d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051c2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400051dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400051aa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x1400051aa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005815`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140005815`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005215`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140005215`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140005833`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140005833`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005829`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005829`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400055d1`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1400055d1`

## string_xrefs

- `0x1400051a1`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, __int64 a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ProcAddress; // rax
  HMODULE v14; // rcx
  HANDLE FileW; // rax
  DWORD LastError_0; // eax
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
  size_t v67; // r8
  struct _ASL_LOG *v68; // rbx
  __int64 v69; // rcx
  int v70; // edi
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
  wchar_t WideCharStr[1024]; // [rsp+CB0h] [rbp+BB0h] BYREF

  v84 = a5;
  Args = a6;
  v83 = a4;
  v82 = (struct _ASL_LOG *)a1;
  if ( a1 )
  {
    dwErrCode = GetLastError_0();
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
    if ( !a1[90] && qword_14001C8E8 )
    {
      dword_14001C8F4 = 0;
      qword_14001C8E8 = 0;
      qword_14001C900 = 0;
    }
    if ( !dword_14001C8F4 )
    {
      dword_14001C8F4 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ProcAddress = GetProcAddress((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_14001C8E8 = (__int64)ProcAddress;
        qword_14001C900 = (__int64)GetProcAddress(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v12 = v74;
        if ( LastError_0 == 231 )
          dword_14001C8E0 = 1;
      }
      else
      {
        dword_14001C8E0 = 1;
        CloseHandle_0(FileW);
        v12 = v74;
      }
    }
    if ( !qword_14001C8E8 || (v17 = 1, !qword_14001C900) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_14001C8E0 || v12 )
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
                  (&off_140013AB8)[2 * v11],
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
        if ( dword_14001C8E0 )
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
                AslLogpWritePanther((const char **)v68, v70, a3, v83, MultiByteStr);
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
        v51 = (const char *)a3;
        if ( !a3 )
          v51 = (const char *)&qword_1400157F8;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_140013AB8)[v27], v51, v50) < 0 && v48 )
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
          v62 = _vsnprintf(&MultiByteStr[v58], v60 - 1, v84, Args);
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
      v41 = _vsnwprintf(Buffer, v80 - 1, Format, Args);
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
0x1400050a0  push    rbp
0x1400050a2  push    rbx
0x1400050a3  push    rsi
0x1400050a4  push    rdi
0x1400050a5  push    r12
0x1400050a7  push    r13
0x1400050a9  push    r14
0x1400050ab  push    r15
0x1400050ad  lea     rbp, [rsp-13C8h]
0x1400050b5  mov     eax, 14C8h
0x1400050ba  call    _alloca_probe
0x1400050bf  sub     rsp, rax
0x1400050c2  mov     rax, cs:__security_cookie
0x1400050c9  xor     rax, rsp
0x1400050cc  mov     [rbp+1400h+var_50], rax
0x1400050d3  mov     r12, [rbp+1400h+arg_20]
0x1400050da  mov     r13, r9
0x1400050dd  mov     rax, [rbp+1400h+arg_28]
0x1400050e4  mov     esi, edx
0x1400050e6  mov     [rbp+1400h+var_1468], r12
0x1400050ea  mov     rbx, rcx
0x1400050ed  mov     [rbp+1400h+Args], rax
0x1400050f1  mov     [rbp+1400h+var_1470], r9
0x1400050f5  mov     [rsp+1500h+var_1498], r8
0x1400050fa  mov     [rsp+1500h+var_14A4], edx
0x1400050fe  mov     [rbp+1400h+var_1478], rcx
0x140005102  test    rcx, rcx
0x140005105  jz      loc_140005839
0x14000510b  call    GetLastError_0
0x140005110  xor     edx, edx
0x140005112  mov     [rsp+1500h+dwErrCode], eax
0x140005116  mov     [rbp+1400h+MultiByteStr], dl
0x140005119  cmp     esi, 3
0x14000511c  jnz     short loc_140005130
0x14000511e  mov     rax, [rbx]
0x140005121  test    byte ptr [rax+50h], 10h
0x140005125  jnz     short loc_140005130
0x140005127  mov     r15b, dl
0x14000512a  mov     [rsp+1500h+var_14B0], dl
0x14000512e  jmp     short loc_14000513B
0x140005130  mov     rax, [rbx]
0x140005133  mov     r15b, 1
0x140005136  mov     [rsp+1500h+var_14B0], r15b
0x14000513b  mov     ecx, [rax+50h]
0x14000513e  mov     r14d, 3
0x140005144  and     ecx, 100h
0x14000514a  cmp     esi, r14d
0x14000514d  mov     [rsp+1500h+var_14AC], ecx
0x140005151  cmovl   r14d, esi
0x140005155  mov     [rsp+1500h+var_14A8], r14d
0x14000515a  cmp     [rbx+2D0h], rdx
0x140005161  jnz     short loc_140005180
0x140005163  cmp     cs:qword_14001C8E8, rdx
0x14000516a  jz      short loc_140005180
0x14000516c  mov     cs:dword_14001C8F4, edx
0x140005172  mov     cs:qword_14001C8E8, rdx
0x140005179  mov     cs:qword_14001C900, rdx
0x140005180  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005184  cmp     cs:dword_14001C8F4, edx
0x14000518a  jnz     loc_140005256
0x140005190  lea     r8, [rbx+2D0h]; phModule
0x140005197  mov     cs:dword_14001C8F4, 1
0x1400051a1  lea     rdx, aWdscoreDll; "wdscore.dll"
0x1400051a8  xor     ecx, ecx; dwFlags
0x1400051aa  call    cs:__imp_GetModuleHandleExA
0x1400051b0  test    eax, eax
0x1400051b2  jz      short loc_1400051EA
0x1400051b4  mov     rcx, [rbx+2D0h]; hModule
0x1400051bb  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x1400051c2  call    cs:__imp_GetProcAddress
0x1400051c8  mov     rcx, [rbx+2D0h]; hModule
0x1400051cf  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1400051d6  mov     cs:qword_14001C8E8, rax
0x1400051dd  call    cs:__imp_GetProcAddress
0x1400051e3  mov     cs:qword_14001C900, rax
0x1400051ea  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x1400051f3  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1400051fa  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140005202  xor     r9d, r9d; lpSecurityAttributes
0x140005205  xor     r8d, r8d; dwShareMode
0x140005208  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x140005210  mov     edx, 40000000h; dwDesiredAccess
0x140005215  call    cs:__imp_CreateFileW
0x14000521b  cmp     rax, rdi
0x14000521e  jnz     short loc_14000523E
0x140005220  call    GetLastError_0
0x140005225  mov     ecx, [rsp+1500h+var_14AC]
0x140005229  xor     edx, edx
0x14000522b  cmp     eax, 0E7h
0x140005230  jnz     short loc_140005256
0x140005232  mov     cs:dword_14001C8E0, 1
0x14000523c  jmp     short loc_140005256
0x14000523e  mov     rcx, rax; hObject
0x140005241  mov     cs:dword_14001C8E0, 1
0x14000524b  call    CloseHandle_0
0x140005250  mov     ecx, [rsp+1500h+var_14AC]
0x140005254  xor     edx, edx
0x140005256  cmp     cs:qword_14001C8E8, rdx
0x14000525d  jz      short loc_14000526A
0x14000525f  cmp     cs:qword_14001C900, rdx
0x140005266  mov     al, 1
0x140005268  jnz     short loc_14000526C
0x14000526a  mov     al, dl
0x14000526c  mov     [rsp+1500h+var_14AF], al
0x140005270  test    r15b, r15b
0x140005273  jnz     short loc_14000528E
0x140005275  cmp     esi, 1
0x140005278  jz      short loc_14000528E
0x14000527a  test    al, al
0x14000527c  jnz     short loc_14000528E
0x14000527e  cmp     cs:dword_14001C8E0, edx
0x140005284  jnz     short loc_14000528E
0x140005286  test    ecx, ecx
0x140005288  jz      loc_140005839
0x14000528e  mov     r15d, 3FEh
0x140005294  lea     rax, [rbp+1400h+WideCharStr]
0x14000529b  mov     r9, r12
0x14000529e  mov     [rsp+1500h+Buffer], rax
0x1400052a3  lea     r8, aHs_0; "%hs"
0x1400052aa  mov     [rsp+1500h+var_1488], r15
0x1400052af  lea     rcx, [rbp+1400h+Format]
0x1400052b6  lea     r12d, [r15+2]
0x1400052ba  mov     edx, r12d
0x1400052bd  call    RtlStringCchPrintfW
0x1400052c2  xor     r10d, r10d
0x1400052c5  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x1400052cc  mov     esi, 7FFFFFFEh
0x1400052d1  test    eax, eax
0x1400052d3  jns     short loc_140005317
0x1400052d5  mov     ecx, esi
0x1400052d7  lea     rax, [rbp+1400h+Format]
0x1400052de  mov     r8, rbx
0x1400052e1  mov     edx, r12d
0x1400052e4  test    rcx, rcx
0x1400052e7  jz      short loc_140005308
0x1400052e9  movzx   r9d, word ptr [r8]
0x1400052ed  test    r9w, r9w
0x1400052f1  jz      short loc_140005308
0x1400052f3  mov     [rax], r9w
0x1400052f7  add     r8, 2
0x1400052fb  add     rax, 2
0x1400052ff  dec     rcx
0x140005302  sub     rdx, 1
0x140005306  jnz     short loc_1400052E4
0x140005308  test    rdx, rdx
0x14000530b  lea     rcx, [rax-2]
0x14000530f  cmovnz  rcx, rax
0x140005313  mov     [rcx], r10w
0x140005317  movzx   eax, [rbp+1400h+Format]
0x14000531e  test    ax, ax
0x140005321  jz      short loc_140005370
0x140005323  mov     edx, 53h ; 'S'
0x140005328  lea     rcx, [rbp+1400h+Format]
0x14000532f  lea     r8d, [rdx+20h]
0x140005333  cmp     ax, 25h ; '%'
0x140005337  jnz     short loc_140005364
0x140005339  add     rcx, 2
0x14000533d  cmp     word ptr [rcx], 2Eh ; '.'
0x140005341  jz      short loc_140005339
0x140005343  movzx   eax, word ptr [rcx]
0x140005346  sub     ax, 30h ; '0'
0x14000534a  cmp     ax, 9
0x14000534e  jbe     short loc_140005339
0x140005350  cmp     [rcx], r8w
0x140005354  jnz     short loc_14000535B
0x140005356  mov     [rcx], dx
0x140005359  jmp     short loc_140005364
0x14000535b  cmp     [rcx], dx
0x14000535e  jnz     short loc_140005364
0x140005360  mov     [rcx], r8w
0x140005364  add     rcx, 2
0x140005368  movzx   eax, word ptr [rcx]
0x14000536b  test    ax, ax
0x14000536e  jnz     short loc_140005333
0x140005370  mov     eax, r13d
0x140005373  cmp     r13, rdi
0x140005376  jnz     short loc_14000537B
0x140005378  mov     eax, r10d
0x14000537b  mov     [rsp+1500h+var_14C0], eax
0x14000537f  lea     rcx, off_140013AB8; "PRINT"
0x140005386  mov     rax, [rsp+1500h+var_1498]
0x14000538b  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x140005390  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x140005395  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x14000539a  movsxd  r13, r14d
0x14000539d  mov     rdx, r15; unsigned __int64
0x1400053a0  add     r13, r13
0x1400053a3  mov     rax, [rcx+r13*8]
0x1400053a7  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x1400053ae  mov     [rsp+1500h+hTemplateFile], rax
0x1400053b3  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x1400053ba  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x1400053bf  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x1400053c7  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1400053cc  xor     r9d, r9d
0x1400053cf  test    eax, eax
0x1400053d1  jns     short loc_140005413
0x1400053d3  mov     rcx, rsi
0x1400053d6  lea     rax, [rbp+1400h+WideCharStr]
0x1400053dd  mov     rdx, r12
0x1400053e0  test    rcx, rcx
0x1400053e3  jz      short loc_140005404
0x1400053e5  movzx   r8d, word ptr [rbx]
0x1400053e9  test    r8w, r8w
0x1400053ed  jz      short loc_140005404
0x1400053ef  mov     [rax], r8w
0x1400053f3  add     rbx, 2
0x1400053f7  add     rax, 2
0x1400053fb  dec     rcx
0x1400053fe  sub     rdx, 1
0x140005402  jnz     short loc_1400053E0
0x140005404  test    rdx, rdx
0x140005407  lea     rcx, [rax-2]
0x14000540b  cmovnz  rcx, rax
0x14000540f  mov     [rcx], r9w
0x140005413  mov     r14, [rsp+1500h+Buffer]
0x140005418  mov     r12d, 80000005h
0x14000541e  mov     rsi, [rsp+1500h+var_1488]
0x140005423  mov     rdi, r14
0x140005426  mov     r15, rsi
0x140005429  test    r14, r14
0x14000542c  jnz     short loc_140005433
0x14000542e  test    rsi, rsi
0x140005431  jnz     short loc_14000543C
0x140005433  cmp     r15, 7FFFFFFFh
0x14000543a  jbe     short loc_140005445
0x14000543c  mov     [r14], r9w
0x140005440  jmp     loc_1400054D3
0x140005445  test    r15, r15
0x140005448  jnz     short loc_14000546E
0x14000544a  mov     rdx, rdi
0x14000544d  mov     rax, r15
0x140005450  mov     ecx, r9d
0x140005453  cmp     [rbp+1400h+Format], r9w
0x14000545b  jz      short loc_1400054BC
0x14000545d  test    rdi, rdi
0x140005460  jnz     short loc_140005469
0x140005462  mov     ecx, 0C000000Dh
0x140005467  jmp     short loc_1400054C2
0x140005469  mov     ecx, r12d
0x14000546c  jmp     short loc_1400054BC
0x14000546e  mov     r9, [rbp+1400h+Args]; Args
0x140005472  lea     rbx, [rsi-1]
0x140005476  mov     rdx, rbx; BufferCount
0x140005479  lea     r8, [rbp+1400h+Format]; Format
0x140005480  mov     rcx, rdi; Buffer
0x140005483  call    cs:__imp__vsnwprintf
0x140005489  xor     r9d, r9d
0x14000548c  test    eax, eax
0x14000548e  js      short loc_1400054A1
0x140005490  cdqe
0x140005492  cmp     rax, rbx
0x140005495  ja      short loc_1400054A1
0x140005497  mov     ecx, r9d
0x14000549a  jz      short loc_1400054A4
0x14000549c  mov     rbx, rax
0x14000549f  jmp     short loc_1400054A9
0x1400054a1  mov     ecx, r12d
0x1400054a4  mov     [r14+rbx*2], r9w
0x1400054a9  mov     rax, r15
0x1400054ac  lea     rdx, [r14+rbx*2]
0x1400054b0  sub     rax, rbx
0x1400054b3  test    ecx, ecx
0x1400054b5  jns     short loc_1400054BC
0x1400054b7  cmp     ecx, r12d
0x1400054ba  jnz     short loc_1400054C2
0x1400054bc  mov     r14, rdx
0x1400054bf  mov     rsi, rax
0x1400054c2  mov     edx, 80000000h
0x1400054c7  lea     eax, [rcx+rdx]
0x1400054ca  test    edx, eax
0x1400054cc  jnz     short loc_140005529
0x1400054ce  cmp     ecx, r12d
0x1400054d1  jz      short loc_140005529
0x1400054d3  test    rsi, rsi
0x1400054d6  jz      short loc_140005529
0x1400054d8  cmp     rsi, 7FFFFFFFh
0x1400054df  jbe     short loc_1400054E9
0x1400054e1  xor     esi, esi
0x1400054e3  mov     [r14], si
0x1400054e7  jmp     short loc_14000552B
0x1400054e9  mov     eax, 7FFFFFFEh
0x1400054ee  lea     rdx, aMessageTooLong; "Message too long!"
0x1400054f5  test    rax, rax
0x1400054f8  jz      short loc_140005517
0x1400054fa  movzx   ecx, word ptr [rdx]
0x1400054fd  test    cx, cx
0x140005500  jz      short loc_140005517
0x140005502  mov     [r14], cx
0x140005506  add     rdx, 2
0x14000550a  add     r14, 2
0x14000550e  dec     rax
0x140005511  sub     rsi, 1
0x140005515  jnz     short loc_1400054F5
0x140005517  test    rsi, rsi
0x14000551a  lea     rcx, [r14-2]
0x14000551e  cmovnz  rcx, r14
0x140005522  xor     esi, esi
0x140005524  mov     [rcx], si
0x140005527  jmp     short loc_14000552B
  ... truncated ...
```
