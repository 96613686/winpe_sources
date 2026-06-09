# AslLogDebugVPrintf

- ea: `0x180013314`
- end: `0x180013ac8`
- name: `AslLogDebugVPrintf`
- size: `1972`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000ce90`

## callees

- `0x180002bf0`
- `0x1800038d0`
- `0x180003924`
- `0x18000398c`
- `0x1800039f0`
- `0x180003a20`
- `0x180003a40`
- `0x180003a70`
- `0x180003a7c`
- `0x180003a88`
- `0x180012674`
- `0x1800127f4`
- `0x1800129f8`
- `0x180012b04`
- `0x180012c10`
- `0x180012cd4`
- `0x180012d54`
- `0x180012f1c`
- `0x180013314`
- `0x1800ce770`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001341e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExA` at `0x18001341e`
- `ntdll!EtwEventWrite` at `0x180013a48`
- `ntdll!EtwEventWrite` at `0x180013a48`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013487`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180013487`

## string_xrefs

- `0x180013415`: `wdscore.dll`

## pseudocode

```c
void __fastcall AslLogDebugVPrintf(__int64 *a1, int a2, const char *a3, __int64 a4, char *a5, va_list a6)
{
  __int64 v9; // rax
  char v10; // r15
  int v11; // r14d
  int v12; // ecx
  FARPROC ConstructPartialMsgIfA; // rax
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
    if ( !a1[90] && qword_1800FEF20 )
    {
      dword_1800FEF34 = 0;
      qword_1800FEF20 = 0;
      WdsSetupLogMessageA = 0;
    }
    if ( !dword_1800FEF34 )
    {
      dword_1800FEF34 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ConstructPartialMsgIfA = GetProcAddress_0((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_1800FEF20 = (__int64)ConstructPartialMsgIfA;
        WdsSetupLogMessageA = (__int64)GetProcAddress_0(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError_0 = GetLastError_0();
        v12 = v74;
        if ( LastError_0 == 231 )
          dword_1800FEF18 = 1;
      }
      else
      {
        dword_1800FEF18 = 1;
        CloseHandle_0(FileW);
        v12 = v74;
      }
    }
    if ( !qword_1800FEF20 || (v17 = 1, !WdsSetupLogMessageA) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_1800FEF18 || v12 )
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
                  (&off_1800D38D8)[2 * v11],
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
        if ( dword_1800FEF18 )
          AslLogpWritePipe(WideCharStr, 2 * v48);
        if ( WideCharToMultiByte_0(0xFDE9u, 0, WideCharStr, -1, MultiByteStr, 1024, 0, 0) )
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
              SetLastError_0(dwErrCode);
              if ( v70 == 1 && (*(_BYTE *)(*(_QWORD *)v68 + 80LL) & 2) != 0 )
              {
                if ( IsDebuggerPresent_0() )
                  DebugBreak_0();
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
          v51 = (const char *)&word_1800D7582;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_1800D38D8)[v27], v51, v50) < 0 && v48 )
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
0x180013314  push    rbp
0x180013316  push    rbx
0x180013317  push    rsi
0x180013318  push    rdi
0x180013319  push    r12
0x18001331b  push    r13
0x18001331d  push    r14
0x18001331f  push    r15
0x180013321  lea     rbp, [rsp-13C8h]
0x180013329  mov     eax, 14C8h
0x18001332e  call    _alloca_probe
0x180013333  sub     rsp, rax
0x180013336  mov     rax, cs:__security_cookie
0x18001333d  xor     rax, rsp
0x180013340  mov     [rbp+1400h+var_50], rax
0x180013347  mov     r12, [rbp+1400h+arg_20]
0x18001334e  mov     r13, r9
0x180013351  mov     rax, [rbp+1400h+arg_28]
0x180013358  mov     esi, edx
0x18001335a  mov     [rbp+1400h+var_1468], r12
0x18001335e  mov     rbx, rcx
0x180013361  mov     [rbp+1400h+Args], rax
0x180013365  mov     [rbp+1400h+var_1470], r9
0x180013369  mov     [rsp+1500h+var_1498], r8
0x18001336e  mov     [rsp+1500h+var_14A4], edx
0x180013372  mov     [rbp+1400h+var_1478], rcx
0x180013376  test    rcx, rcx
0x180013379  jz      loc_180013AA5
0x18001337f  call    GetLastError_0
0x180013384  xor     edx, edx
0x180013386  mov     [rsp+1500h+dwErrCode], eax
0x18001338a  mov     [rbp+1400h+MultiByteStr], dl
0x18001338d  cmp     esi, 3
0x180013390  jnz     short loc_1800133A4
0x180013392  mov     rax, [rbx]
0x180013395  test    byte ptr [rax+50h], 10h
0x180013399  jnz     short loc_1800133A4
0x18001339b  mov     r15b, dl
0x18001339e  mov     [rsp+1500h+var_14B0], dl
0x1800133a2  jmp     short loc_1800133AF
0x1800133a4  mov     rax, [rbx]
0x1800133a7  mov     r15b, 1
0x1800133aa  mov     [rsp+1500h+var_14B0], r15b
0x1800133af  mov     ecx, [rax+50h]
0x1800133b2  mov     r14d, 3
0x1800133b8  and     ecx, 100h
0x1800133be  cmp     esi, r14d
0x1800133c1  mov     [rsp+1500h+var_14AC], ecx
0x1800133c5  cmovl   r14d, esi
0x1800133c9  mov     [rsp+1500h+var_14A8], r14d
0x1800133ce  cmp     [rbx+2D0h], rdx
0x1800133d5  jnz     short loc_1800133F4
0x1800133d7  cmp     cs:qword_1800FEF20, rdx
0x1800133de  jz      short loc_1800133F4
0x1800133e0  mov     cs:dword_1800FEF34, edx
0x1800133e6  mov     cs:qword_1800FEF20, rdx
0x1800133ed  mov     cs:WdsSetupLogMessageA, rdx
0x1800133f4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800133f8  cmp     cs:dword_1800FEF34, edx
0x1800133fe  jnz     loc_1800134C8
0x180013404  lea     r8, [rbx+2D0h]; phModule
0x18001340b  mov     cs:dword_1800FEF34, 1
0x180013415  lea     rdx, aWdscoreDll; "wdscore.dll"
0x18001341c  xor     ecx, ecx; dwFlags
0x18001341e  call    cs:__imp_GetModuleHandleExA
0x180013424  test    eax, eax
0x180013426  jz      short loc_18001345C
0x180013428  mov     rcx, [rbx+2D0h]; hModule
0x18001342f  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x180013436  call    GetProcAddress_0
0x18001343b  mov     rcx, [rbx+2D0h]; hModule
0x180013442  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x180013449  mov     cs:qword_1800FEF20, rax
0x180013450  call    GetProcAddress_0
0x180013455  mov     cs:WdsSetupLogMessageA, rax
0x18001345c  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x180013465  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x18001346c  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180013474  xor     r9d, r9d; lpSecurityAttributes
0x180013477  xor     r8d, r8d; dwShareMode
0x18001347a  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x180013482  mov     edx, 40000000h; dwDesiredAccess
0x180013487  call    cs:__imp_CreateFileW
0x18001348d  cmp     rax, rdi
0x180013490  jnz     short loc_1800134B0
0x180013492  call    GetLastError_0
0x180013497  mov     ecx, [rsp+1500h+var_14AC]
0x18001349b  xor     edx, edx
0x18001349d  cmp     eax, 0E7h
0x1800134a2  jnz     short loc_1800134C8
0x1800134a4  mov     cs:dword_1800FEF18, 1
0x1800134ae  jmp     short loc_1800134C8
0x1800134b0  mov     rcx, rax; hObject
0x1800134b3  mov     cs:dword_1800FEF18, 1
0x1800134bd  call    CloseHandle_0
0x1800134c2  mov     ecx, [rsp+1500h+var_14AC]
0x1800134c6  xor     edx, edx
0x1800134c8  cmp     cs:qword_1800FEF20, rdx
0x1800134cf  jz      short loc_1800134DC
0x1800134d1  cmp     cs:WdsSetupLogMessageA, rdx
0x1800134d8  mov     al, 1
0x1800134da  jnz     short loc_1800134DE
0x1800134dc  mov     al, dl
0x1800134de  mov     [rsp+1500h+var_14AF], al
0x1800134e2  test    r15b, r15b
0x1800134e5  jnz     short loc_180013500
0x1800134e7  cmp     esi, 1
0x1800134ea  jz      short loc_180013500
0x1800134ec  test    al, al
0x1800134ee  jnz     short loc_180013500
0x1800134f0  cmp     cs:dword_1800FEF18, edx
0x1800134f6  jnz     short loc_180013500
0x1800134f8  test    ecx, ecx
0x1800134fa  jz      loc_180013AA5
0x180013500  mov     r15d, 3FEh
0x180013506  lea     rax, [rbp+1400h+WideCharStr]
0x18001350d  mov     r9, r12
0x180013510  mov     [rsp+1500h+Buffer], rax
0x180013515  lea     r8, aHs_1; "%hs"
0x18001351c  mov     [rsp+1500h+var_1488], r15
0x180013521  lea     rcx, [rbp+1400h+Format]
0x180013528  lea     r12d, [r15+2]
0x18001352c  mov     edx, r12d
0x18001352f  call    RtlStringCchPrintfW
0x180013534  xor     r10d, r10d
0x180013537  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x18001353e  mov     esi, 7FFFFFFEh
0x180013543  test    eax, eax
0x180013545  jns     short loc_180013589
0x180013547  mov     ecx, esi
0x180013549  lea     rax, [rbp+1400h+Format]
0x180013550  mov     r8, rbx
0x180013553  mov     edx, r12d
0x180013556  test    rcx, rcx
0x180013559  jz      short loc_18001357A
0x18001355b  movzx   r9d, word ptr [r8]
0x18001355f  test    r9w, r9w
0x180013563  jz      short loc_18001357A
0x180013565  mov     [rax], r9w
0x180013569  add     r8, 2
0x18001356d  add     rax, 2
0x180013571  dec     rcx
0x180013574  sub     rdx, 1
0x180013578  jnz     short loc_180013556
0x18001357a  test    rdx, rdx
0x18001357d  lea     rcx, [rax-2]
0x180013581  cmovnz  rcx, rax
0x180013585  mov     [rcx], r10w
0x180013589  movzx   eax, [rbp+1400h+Format]
0x180013590  test    ax, ax
0x180013593  jz      short loc_1800135E2
0x180013595  mov     edx, 53h ; 'S'
0x18001359a  lea     rcx, [rbp+1400h+Format]
0x1800135a1  lea     r8d, [rdx+20h]
0x1800135a5  cmp     ax, 25h ; '%'
0x1800135a9  jnz     short loc_1800135D6
0x1800135ab  add     rcx, 2
0x1800135af  cmp     word ptr [rcx], 2Eh ; '.'
0x1800135b3  jz      short loc_1800135AB
0x1800135b5  movzx   eax, word ptr [rcx]
0x1800135b8  sub     ax, 30h ; '0'
0x1800135bc  cmp     ax, 9
0x1800135c0  jbe     short loc_1800135AB
0x1800135c2  cmp     [rcx], r8w
0x1800135c6  jnz     short loc_1800135CD
0x1800135c8  mov     [rcx], dx
0x1800135cb  jmp     short loc_1800135D6
0x1800135cd  cmp     [rcx], dx
0x1800135d0  jnz     short loc_1800135D6
0x1800135d2  mov     [rcx], r8w
0x1800135d6  add     rcx, 2
0x1800135da  movzx   eax, word ptr [rcx]
0x1800135dd  test    ax, ax
0x1800135e0  jnz     short loc_1800135A5
0x1800135e2  mov     eax, r13d
0x1800135e5  cmp     r13, rdi
0x1800135e8  jnz     short loc_1800135ED
0x1800135ea  mov     eax, r10d
0x1800135ed  mov     [rsp+1500h+var_14C0], eax
0x1800135f1  lea     rcx, off_1800D38D8; "PRINT"
0x1800135f8  mov     rax, [rsp+1500h+var_1498]
0x1800135fd  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x180013602  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x180013607  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x18001360c  movsxd  r13, r14d
0x18001360f  mov     rdx, r15; unsigned __int64
0x180013612  add     r13, r13
0x180013615  mov     rax, [rcx+r13*8]
0x180013619  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x180013620  mov     [rsp+1500h+hTemplateFile], rax
0x180013625  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x18001362c  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180013631  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x180013639  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x18001363e  xor     r9d, r9d
0x180013641  test    eax, eax
0x180013643  jns     short loc_180013685
0x180013645  mov     rcx, rsi
0x180013648  lea     rax, [rbp+1400h+WideCharStr]
0x18001364f  mov     rdx, r12
0x180013652  test    rcx, rcx
0x180013655  jz      short loc_180013676
0x180013657  movzx   r8d, word ptr [rbx]
0x18001365b  test    r8w, r8w
0x18001365f  jz      short loc_180013676
0x180013661  mov     [rax], r8w
0x180013665  add     rbx, 2
0x180013669  add     rax, 2
0x18001366d  dec     rcx
0x180013670  sub     rdx, 1
0x180013674  jnz     short loc_180013652
0x180013676  test    rdx, rdx
0x180013679  lea     rcx, [rax-2]
0x18001367d  cmovnz  rcx, rax
0x180013681  mov     [rcx], r9w
0x180013685  mov     r14, [rsp+1500h+Buffer]
0x18001368a  mov     r12d, 80000005h
0x180013690  mov     rsi, [rsp+1500h+var_1488]
0x180013695  mov     rdi, r14
0x180013698  mov     r15, rsi
0x18001369b  test    r14, r14
0x18001369e  jnz     short loc_1800136A5
0x1800136a0  test    rsi, rsi
0x1800136a3  jnz     short loc_1800136AE
0x1800136a5  cmp     r15, 7FFFFFFFh
0x1800136ac  jbe     short loc_1800136B7
0x1800136ae  mov     [r14], r9w
0x1800136b2  jmp     loc_180013744
0x1800136b7  test    r15, r15
0x1800136ba  jnz     short loc_1800136E0
0x1800136bc  mov     rdx, rdi
0x1800136bf  mov     rax, r15
0x1800136c2  mov     ecx, r9d
0x1800136c5  cmp     [rbp+1400h+Format], r9w
0x1800136cd  jz      short loc_18001372D
0x1800136cf  test    rdi, rdi
0x1800136d2  jnz     short loc_1800136DB
0x1800136d4  mov     ecx, 0C000000Dh
0x1800136d9  jmp     short loc_180013733
0x1800136db  mov     ecx, r12d
0x1800136de  jmp     short loc_18001372D
0x1800136e0  mov     r9, [rbp+1400h+Args]; Args
0x1800136e4  lea     rbx, [rsi-1]
0x1800136e8  mov     rdx, rbx; BufferCount
0x1800136eb  lea     r8, [rbp+1400h+Format]; Format
0x1800136f2  mov     rcx, rdi; Buffer
0x1800136f5  call    _vsnwprintf
0x1800136fa  xor     r9d, r9d
0x1800136fd  test    eax, eax
0x1800136ff  js      short loc_180013712
0x180013701  cdqe
0x180013703  cmp     rax, rbx
0x180013706  ja      short loc_180013712
0x180013708  mov     ecx, r9d
0x18001370b  jz      short loc_180013715
0x18001370d  mov     rbx, rax
0x180013710  jmp     short loc_18001371A
0x180013712  mov     ecx, r12d
0x180013715  mov     [r14+rbx*2], r9w
0x18001371a  mov     rax, r15
0x18001371d  lea     rdx, [r14+rbx*2]
0x180013721  sub     rax, rbx
0x180013724  test    ecx, ecx
0x180013726  jns     short loc_18001372D
0x180013728  cmp     ecx, r12d
0x18001372b  jnz     short loc_180013733
0x18001372d  mov     r14, rdx
0x180013730  mov     rsi, rax
0x180013733  mov     edx, 80000000h
0x180013738  lea     eax, [rcx+rdx]
0x18001373b  test    edx, eax
0x18001373d  jnz     short loc_18001379A
0x18001373f  cmp     ecx, r12d
0x180013742  jz      short loc_18001379A
0x180013744  test    rsi, rsi
0x180013747  jz      short loc_18001379A
0x180013749  cmp     rsi, 7FFFFFFFh
0x180013750  jbe     short loc_18001375A
0x180013752  xor     esi, esi
0x180013754  mov     [r14], si
0x180013758  jmp     short loc_18001379C
0x18001375a  mov     eax, 7FFFFFFEh
0x18001375f  lea     rdx, aMessageTooLong; "Message too long!"
0x180013766  test    rax, rax
0x180013769  jz      short loc_180013788
0x18001376b  movzx   ecx, word ptr [rdx]
0x18001376e  test    cx, cx
0x180013771  jz      short loc_180013788
0x180013773  mov     [r14], cx
0x180013777  add     rdx, 2
0x18001377b  add     r14, 2
0x18001377f  dec     rax
0x180013782  sub     rsi, 1
0x180013786  jnz     short loc_180013766
0x180013788  test    rsi, rsi
0x18001378b  lea     rcx, [r14-2]
0x18001378f  cmovnz  rcx, r14
0x180013793  xor     esi, esi
0x180013795  mov     [rcx], si
0x180013798  jmp     short loc_18001379C
  ... truncated ...
```
