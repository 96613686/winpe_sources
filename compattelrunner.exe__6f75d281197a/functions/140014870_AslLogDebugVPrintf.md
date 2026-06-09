# AslLogDebugVPrintf

- ea: `0x140014870`
- end: `0x14001502d`
- name: `AslLogDebugVPrintf`
- size: `1981`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x14000bb50`

## callees

- `0x140001ba0`
- `0x14000272c`
- `0x1400027d4`
- `0x1400113b4`
- `0x140013c4c`
- `0x140013dcc`
- `0x140013fd0`
- `0x1400140dc`
- `0x1400141e8`
- `0x1400142ac`
- `0x140014474`
- `0x140014870`
- `0x1400a7290`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x140014faa`
- `ntdll!EtwEventWrite` at `0x140014faa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14001497b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x14001497b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014993`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400149ae`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014993`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400149ae`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014fe6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140014fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400148db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400149f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400148db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400149f1`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140015004`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x140015004`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140014ffa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140014ffa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014a1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140014a1d`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140014da3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x140014da3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400149e6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1400149e6`

## string_xrefs

- `0x140014972`: `wdscore.dll`

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
    if ( !a1[90] && qword_1400C90D0 )
    {
      dword_1400C90DC = 0;
      qword_1400C90D0 = 0;
      qword_1400C90E8 = 0;
    }
    if ( !dword_1400C90DC )
    {
      dword_1400C90DC = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ProcAddress = GetProcAddress((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_1400C90D0 = (__int64)ProcAddress;
        qword_1400C90E8 = (__int64)GetProcAddress(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v12 = v74;
        if ( LastError == 231 )
          dword_1400C90CC = 1;
      }
      else
      {
        dword_1400C90CC = 1;
        CloseHandle(FileW);
        v12 = v74;
      }
    }
    if ( !qword_1400C90D0 || (v17 = 1, !qword_1400C90E8) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_1400C90CC || v12 )
    {
      Buffer = WideCharStr;
      v80 = 1022;
      v18 = L"ASL_LOG FAIL: ";
      if ( (int)RtlStringCchPrintfW(Format, 0x400u, L"%hs", a5) < 0 )
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
                  (&off_1400AA0A8)[2 * v11],
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
        if ( dword_1400C90CC )
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
          v51 = (const char *)&dword_1400ACDEC;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_1400AA0A8)[v27], v51, v50) < 0 && v48 )
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
0x140014870  push    rbp
0x140014872  push    rbx
0x140014873  push    rsi
0x140014874  push    rdi
0x140014875  push    r12
0x140014877  push    r13
0x140014879  push    r14
0x14001487b  push    r15
0x14001487d  lea     rbp, [rsp-13C8h]
0x140014885  mov     eax, 14C8h
0x14001488a  call    _alloca_probe
0x14001488f  sub     rsp, rax
0x140014892  mov     rax, cs:__security_cookie
0x140014899  xor     rax, rsp
0x14001489c  mov     [rbp+1400h+var_50], rax
0x1400148a3  mov     r12, [rbp+1400h+arg_20]
0x1400148aa  mov     r13, r9
0x1400148ad  mov     rax, [rbp+1400h+arg_28]
0x1400148b4  mov     esi, edx
0x1400148b6  mov     [rbp+1400h+var_1468], r12
0x1400148ba  mov     rbx, rcx
0x1400148bd  mov     [rbp+1400h+Args], rax
0x1400148c1  mov     [rbp+1400h+var_1470], r9
0x1400148c5  mov     [rsp+1500h+var_1498], r8
0x1400148ca  mov     [rsp+1500h+var_14A4], edx
0x1400148ce  mov     [rbp+1400h+var_1478], rcx
0x1400148d2  test    rcx, rcx
0x1400148d5  jz      loc_14001500A
0x1400148db  call    cs:__imp_GetLastError
0x1400148e1  xor     edx, edx
0x1400148e3  mov     [rsp+1500h+dwErrCode], eax
0x1400148e7  mov     [rbp+1400h+MultiByteStr], dl
0x1400148ea  cmp     esi, 3
0x1400148ed  jnz     short loc_140014901
0x1400148ef  mov     rax, [rbx]
0x1400148f2  test    byte ptr [rax+50h], 10h
0x1400148f6  jnz     short loc_140014901
0x1400148f8  mov     r15b, dl
0x1400148fb  mov     [rsp+1500h+var_14B0], dl
0x1400148ff  jmp     short loc_14001490C
0x140014901  mov     rax, [rbx]
0x140014904  mov     r15b, 1
0x140014907  mov     [rsp+1500h+var_14B0], r15b
0x14001490c  mov     ecx, [rax+50h]
0x14001490f  mov     r14d, 3
0x140014915  and     ecx, 100h
0x14001491b  cmp     esi, r14d
0x14001491e  mov     [rsp+1500h+var_14AC], ecx
0x140014922  cmovl   r14d, esi
0x140014926  mov     [rsp+1500h+var_14A8], r14d
0x14001492b  cmp     [rbx+2D0h], rdx
0x140014932  jnz     short loc_140014951
0x140014934  cmp     cs:qword_1400C90D0, rdx
0x14001493b  jz      short loc_140014951
0x14001493d  mov     cs:dword_1400C90DC, edx
0x140014943  mov     cs:qword_1400C90D0, rdx
0x14001494a  mov     cs:qword_1400C90E8, rdx
0x140014951  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140014955  cmp     cs:dword_1400C90DC, edx
0x14001495b  jnz     loc_140014A29
0x140014961  lea     r8, [rbx+2D0h]; phModule
0x140014968  mov     cs:dword_1400C90DC, 1
0x140014972  lea     rdx, aWdscoreDll; "wdscore.dll"
0x140014979  xor     ecx, ecx; dwFlags
0x14001497b  call    cs:__imp_GetModuleHandleExA
0x140014981  test    eax, eax
0x140014983  jz      short loc_1400149BB
0x140014985  mov     rcx, [rbx+2D0h]; hModule
0x14001498c  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x140014993  call    cs:__imp_GetProcAddress
0x140014999  mov     rcx, [rbx+2D0h]; hModule
0x1400149a0  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1400149a7  mov     cs:qword_1400C90D0, rax
0x1400149ae  call    cs:__imp_GetProcAddress
0x1400149b4  mov     cs:qword_1400C90E8, rax
0x1400149bb  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x1400149c4  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1400149cb  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1400149d3  xor     r9d, r9d; lpSecurityAttributes
0x1400149d6  xor     r8d, r8d; dwShareMode
0x1400149d9  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x1400149e1  mov     edx, 40000000h; dwDesiredAccess
0x1400149e6  call    cs:__imp_CreateFileW
0x1400149ec  cmp     rax, rdi
0x1400149ef  jnz     short loc_140014A10
0x1400149f1  call    cs:__imp_GetLastError
0x1400149f7  mov     ecx, [rsp+1500h+var_14AC]
0x1400149fb  xor     edx, edx
0x1400149fd  cmp     eax, 0E7h
0x140014a02  jnz     short loc_140014A29
0x140014a04  mov     cs:dword_1400C90CC, 1
0x140014a0e  jmp     short loc_140014A29
0x140014a10  mov     rcx, rax; hObject
0x140014a13  mov     cs:dword_1400C90CC, 1
0x140014a1d  call    cs:__imp_CloseHandle
0x140014a23  mov     ecx, [rsp+1500h+var_14AC]
0x140014a27  xor     edx, edx
0x140014a29  cmp     cs:qword_1400C90D0, rdx
0x140014a30  jz      short loc_140014A3D
0x140014a32  cmp     cs:qword_1400C90E8, rdx
0x140014a39  mov     al, 1
0x140014a3b  jnz     short loc_140014A3F
0x140014a3d  mov     al, dl
0x140014a3f  mov     [rsp+1500h+var_14AF], al
0x140014a43  test    r15b, r15b
0x140014a46  jnz     short loc_140014A61
0x140014a48  cmp     esi, 1
0x140014a4b  jz      short loc_140014A61
0x140014a4d  test    al, al
0x140014a4f  jnz     short loc_140014A61
0x140014a51  cmp     cs:dword_1400C90CC, edx
0x140014a57  jnz     short loc_140014A61
0x140014a59  test    ecx, ecx
0x140014a5b  jz      loc_14001500A
0x140014a61  mov     r15d, 3FEh
0x140014a67  lea     rax, [rbp+1400h+WideCharStr]
0x140014a6e  mov     r9, r12
0x140014a71  mov     [rsp+1500h+Buffer], rax
0x140014a76  lea     r8, aHs_3; "%hs"
0x140014a7d  mov     [rsp+1500h+var_1488], r15
0x140014a82  lea     rcx, [rbp+1400h+Format]; unsigned __int16 *
0x140014a89  lea     r12d, [r15+2]
0x140014a8d  mov     edx, r12d; unsigned __int64
0x140014a90  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140014a95  xor     r10d, r10d
0x140014a98  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x140014a9f  mov     esi, 7FFFFFFEh
0x140014aa4  test    eax, eax
0x140014aa6  jns     short loc_140014AEA
0x140014aa8  mov     ecx, esi
0x140014aaa  lea     rax, [rbp+1400h+Format]
0x140014ab1  mov     r8, rbx
0x140014ab4  mov     edx, r12d
0x140014ab7  test    rcx, rcx
0x140014aba  jz      short loc_140014ADB
0x140014abc  movzx   r9d, word ptr [r8]
0x140014ac0  test    r9w, r9w
0x140014ac4  jz      short loc_140014ADB
0x140014ac6  mov     [rax], r9w
0x140014aca  add     r8, 2
0x140014ace  add     rax, 2
0x140014ad2  dec     rcx
0x140014ad5  sub     rdx, 1
0x140014ad9  jnz     short loc_140014AB7
0x140014adb  test    rdx, rdx
0x140014ade  lea     rcx, [rax-2]
0x140014ae2  cmovnz  rcx, rax
0x140014ae6  mov     [rcx], r10w
0x140014aea  movzx   eax, [rbp+1400h+Format]
0x140014af1  test    ax, ax
0x140014af4  jz      short loc_140014B43
0x140014af6  mov     edx, 53h ; 'S'
0x140014afb  lea     rcx, [rbp+1400h+Format]
0x140014b02  lea     r8d, [rdx+20h]
0x140014b06  cmp     ax, 25h ; '%'
0x140014b0a  jnz     short loc_140014B37
0x140014b0c  add     rcx, 2
0x140014b10  cmp     word ptr [rcx], 2Eh ; '.'
0x140014b14  jz      short loc_140014B0C
0x140014b16  movzx   eax, word ptr [rcx]
0x140014b19  sub     ax, 30h ; '0'
0x140014b1d  cmp     ax, 9
0x140014b21  jbe     short loc_140014B0C
0x140014b23  cmp     [rcx], r8w
0x140014b27  jnz     short loc_140014B2E
0x140014b29  mov     [rcx], dx
0x140014b2c  jmp     short loc_140014B37
0x140014b2e  cmp     [rcx], dx
0x140014b31  jnz     short loc_140014B37
0x140014b33  mov     [rcx], r8w
0x140014b37  add     rcx, 2
0x140014b3b  movzx   eax, word ptr [rcx]
0x140014b3e  test    ax, ax
0x140014b41  jnz     short loc_140014B06
0x140014b43  mov     eax, r13d
0x140014b46  cmp     r13, rdi
0x140014b49  jnz     short loc_140014B4E
0x140014b4b  mov     eax, r10d
0x140014b4e  mov     [rsp+1500h+var_14C0], eax
0x140014b52  lea     rcx, off_1400AA0A8; "PRINT"
0x140014b59  mov     rax, [rsp+1500h+var_1498]
0x140014b5e  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x140014b63  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x140014b68  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x140014b6d  movsxd  r13, r14d
0x140014b70  mov     rdx, r15; unsigned __int64
0x140014b73  add     r13, r13
0x140014b76  mov     rax, [rcx+r13*8]
0x140014b7a  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x140014b81  mov     [rsp+1500h+hTemplateFile], rax
0x140014b86  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x140014b8d  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x140014b92  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x140014b9a  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x140014b9f  xor     r9d, r9d
0x140014ba2  test    eax, eax
0x140014ba4  jns     short loc_140014BE6
0x140014ba6  mov     rcx, rsi
0x140014ba9  lea     rax, [rbp+1400h+WideCharStr]
0x140014bb0  mov     rdx, r12
0x140014bb3  test    rcx, rcx
0x140014bb6  jz      short loc_140014BD7
0x140014bb8  movzx   r8d, word ptr [rbx]
0x140014bbc  test    r8w, r8w
0x140014bc0  jz      short loc_140014BD7
0x140014bc2  mov     [rax], r8w
0x140014bc6  add     rbx, 2
0x140014bca  add     rax, 2
0x140014bce  dec     rcx
0x140014bd1  sub     rdx, 1
0x140014bd5  jnz     short loc_140014BB3
0x140014bd7  test    rdx, rdx
0x140014bda  lea     rcx, [rax-2]
0x140014bde  cmovnz  rcx, rax
0x140014be2  mov     [rcx], r9w
0x140014be6  mov     r14, [rsp+1500h+Buffer]
0x140014beb  mov     r12d, 80000005h
0x140014bf1  mov     rsi, [rsp+1500h+var_1488]
0x140014bf6  mov     rdi, r14
0x140014bf9  mov     r15, rsi
0x140014bfc  test    r14, r14
0x140014bff  jnz     short loc_140014C06
0x140014c01  test    rsi, rsi
0x140014c04  jnz     short loc_140014C0F
0x140014c06  cmp     r15, 7FFFFFFFh
0x140014c0d  jbe     short loc_140014C18
0x140014c0f  mov     [r14], r9w
0x140014c13  jmp     loc_140014CA5
0x140014c18  test    r15, r15
0x140014c1b  jnz     short loc_140014C41
0x140014c1d  mov     rdx, rdi
0x140014c20  mov     rax, r15
0x140014c23  mov     ecx, r9d
0x140014c26  cmp     [rbp+1400h+Format], r9w
0x140014c2e  jz      short loc_140014C8E
0x140014c30  test    rdi, rdi
0x140014c33  jnz     short loc_140014C3C
0x140014c35  mov     ecx, 0C000000Dh
0x140014c3a  jmp     short loc_140014C94
0x140014c3c  mov     ecx, r12d
0x140014c3f  jmp     short loc_140014C8E
0x140014c41  mov     r9, [rbp+1400h+Args]; Args
0x140014c45  lea     rbx, [rsi-1]
0x140014c49  mov     rdx, rbx; BufferCount
0x140014c4c  lea     r8, [rbp+1400h+Format]; Format
0x140014c53  mov     rcx, rdi; Buffer
0x140014c56  call    _vsnwprintf
0x140014c5b  xor     r9d, r9d
0x140014c5e  test    eax, eax
0x140014c60  js      short loc_140014C73
0x140014c62  cdqe
0x140014c64  cmp     rax, rbx
0x140014c67  ja      short loc_140014C73
0x140014c69  mov     ecx, r9d
0x140014c6c  jz      short loc_140014C76
0x140014c6e  mov     rbx, rax
0x140014c71  jmp     short loc_140014C7B
0x140014c73  mov     ecx, r12d
0x140014c76  mov     [r14+rbx*2], r9w
0x140014c7b  mov     rax, r15
0x140014c7e  lea     rdx, [r14+rbx*2]
0x140014c82  sub     rax, rbx
0x140014c85  test    ecx, ecx
0x140014c87  jns     short loc_140014C8E
0x140014c89  cmp     ecx, r12d
0x140014c8c  jnz     short loc_140014C94
0x140014c8e  mov     r14, rdx
0x140014c91  mov     rsi, rax
0x140014c94  mov     edx, 80000000h
0x140014c99  lea     eax, [rcx+rdx]
0x140014c9c  test    edx, eax
0x140014c9e  jnz     short loc_140014CFB
0x140014ca0  cmp     ecx, r12d
0x140014ca3  jz      short loc_140014CFB
0x140014ca5  test    rsi, rsi
0x140014ca8  jz      short loc_140014CFB
0x140014caa  cmp     rsi, 7FFFFFFFh
0x140014cb1  jbe     short loc_140014CBB
0x140014cb3  xor     esi, esi
0x140014cb5  mov     [r14], si
0x140014cb9  jmp     short loc_140014CFD
0x140014cbb  mov     eax, 7FFFFFFEh
0x140014cc0  lea     rdx, aMessageTooLong; "Message too long!"
0x140014cc7  test    rax, rax
0x140014cca  jz      short loc_140014CE9
0x140014ccc  movzx   ecx, word ptr [rdx]
0x140014ccf  test    cx, cx
0x140014cd2  jz      short loc_140014CE9
0x140014cd4  mov     [r14], cx
0x140014cd8  add     rdx, 2
0x140014cdc  add     r14, 2
0x140014ce0  dec     rax
0x140014ce3  sub     rsi, 1
0x140014ce7  jnz     short loc_140014CC7
0x140014ce9  test    rsi, rsi
0x140014cec  lea     rcx, [r14-2]
0x140014cf0  cmovnz  rcx, r14
0x140014cf4  xor     esi, esi
0x140014cf6  mov     [rcx], si
0x140014cf9  jmp     short loc_140014CFD
  ... truncated ...
```
