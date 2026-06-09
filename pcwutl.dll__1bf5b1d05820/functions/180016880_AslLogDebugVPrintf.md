# AslLogDebugVPrintf

- ea: `0x180016880`
- end: `0x18001703f`
- name: `AslLogDebugVPrintf`
- size: `1983`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180008e60`

## callees

- `0x180013f04`
- `0x18001403c`
- `0x18001515c`
- `0x1800152dc`
- `0x1800154e0`
- `0x1800155ec`
- `0x180015e60`
- `0x180015ee0`
- `0x180016880`
- `0x1800191f0`
- `0x1800192b0`

## import_xrefs

- `msvcrt!_vsnprintf` at `0x180016ebb`
- `msvcrt!_vsnprintf` at `0x180016ebb`
- `msvcrt!_vsnwprintf` at `0x180016c66`
- `msvcrt!_vsnwprintf` at `0x180016c66`
- `KERNEL32!SetLastError` at `0x180016ff8`
- `KERNEL32!SetLastError` at `0x180016ff8`
- `KERNEL32!GetModuleHandleExA` at `0x18001698b`
- `KERNEL32!GetModuleHandleExA` at `0x18001698b`
- `KERNEL32!WideCharToMultiByte` at `0x180016db4`
- `KERNEL32!WideCharToMultiByte` at `0x180016db4`
- `KERNEL32!DebugBreak` at `0x180017016`
- `KERNEL32!DebugBreak` at `0x180017016`
- `KERNEL32!IsDebuggerPresent` at `0x18001700c`
- `KERNEL32!IsDebuggerPresent` at `0x18001700c`
- `KERNEL32!GetLastError` at `0x1800168eb`
- `KERNEL32!GetLastError` at `0x180016a01`
- `KERNEL32!GetLastError` at `0x1800168eb`
- `KERNEL32!GetLastError` at `0x180016a01`
- `KERNEL32!CloseHandle` at `0x180016a2d`
- `KERNEL32!CloseHandle` at `0x180016a2d`
- `KERNEL32!GetProcAddress` at `0x1800169a3`
- `KERNEL32!GetProcAddress` at `0x1800169be`
- `KERNEL32!GetProcAddress` at `0x1800169a3`
- `KERNEL32!GetProcAddress` at `0x1800169be`
- `KERNEL32!CreateFileW` at `0x1800169f6`
- `KERNEL32!CreateFileW` at `0x1800169f6`
- `ntdll!EtwEventWrite` at `0x180016fbc`
- `ntdll!EtwEventWrite` at `0x180016fbc`

## string_xrefs

- `0x180016982`: `wdscore.dll`

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
  wchar_t WideCharStr[1024]; // [rsp+CB0h] [rbp+BB0h] BYREF

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
    if ( !a1[90] && qword_1800268D8 )
    {
      dword_1800268E4 = 0;
      qword_1800268D8 = 0;
      qword_1800268F0 = 0;
    }
    if ( !dword_1800268E4 )
    {
      dword_1800268E4 = 1;
      if ( GetModuleHandleExA(0, "wdscore.dll", (HMODULE *)a1 + 90) )
      {
        ProcAddress = GetProcAddress((HMODULE)a1[90], "ConstructPartialMsgIfA");
        v14 = (HMODULE)a1[90];
        qword_1800268D8 = (__int64)ProcAddress;
        qword_1800268F0 = (__int64)GetProcAddress(v14, "WdsSetupLogMessageA");
      }
      FileW = CreateFileW(L"\\\\.\\pipe\\GmdAslLogger", 0x40000000u, 0, 0, 3u, 0, 0);
      if ( FileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        v12 = v74;
        if ( LastError == 231 )
          dword_1800268D4 = 1;
      }
      else
      {
        dword_1800268D4 = 1;
        CloseHandle(FileW);
        v12 = v74;
      }
    }
    if ( !qword_1800268D8 || (v17 = 1, !qword_1800268F0) )
      v17 = 0;
    v73 = v17;
    if ( v10 || a2 == 1 || v17 || dword_1800268D4 || v12 )
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
                  (&off_18001BBF8)[2 * v11],
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
        if ( dword_1800268D4 )
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
          v51 = byte_1800216C9;
        if ( (int)RtlStringCchPrintfA(MultiByteStr, v48, "%s,%s,%d,", (&off_18001BBF8)[v27], v51, v50) < 0 && v48 )
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
0x180016880  push    rbp
0x180016882  push    rbx
0x180016883  push    rsi
0x180016884  push    rdi
0x180016885  push    r12
0x180016887  push    r13
0x180016889  push    r14
0x18001688b  push    r15
0x18001688d  lea     rbp, [rsp-13C8h]
0x180016895  mov     eax, 14C8h
0x18001689a  call    _alloca_probe
0x18001689f  sub     rsp, rax
0x1800168a2  mov     rax, cs:__security_cookie
0x1800168a9  xor     rax, rsp
0x1800168ac  mov     [rbp+1400h+var_50], rax
0x1800168b3  mov     r12, [rbp+1400h+arg_20]
0x1800168ba  mov     r13, r9
0x1800168bd  mov     rax, [rbp+1400h+arg_28]
0x1800168c4  mov     esi, edx
0x1800168c6  mov     [rbp+1400h+var_1468], r12
0x1800168ca  mov     rbx, rcx
0x1800168cd  mov     [rbp+1400h+Args], rax
0x1800168d1  mov     [rbp+1400h+var_1470], r9
0x1800168d5  mov     [rsp+1500h+var_1498], r8
0x1800168da  mov     [rsp+1500h+var_14A4], edx
0x1800168de  mov     [rbp+1400h+var_1478], rcx
0x1800168e2  test    rcx, rcx
0x1800168e5  jz      loc_18001701C
0x1800168eb  call    cs:__imp_GetLastError
0x1800168f1  xor     edx, edx
0x1800168f3  mov     [rsp+1500h+dwErrCode], eax
0x1800168f7  mov     [rbp+1400h+MultiByteStr], dl
0x1800168fa  cmp     esi, 3
0x1800168fd  jnz     short loc_180016911
0x1800168ff  mov     rax, [rbx]
0x180016902  test    byte ptr [rax+50h], 10h
0x180016906  jnz     short loc_180016911
0x180016908  mov     r15b, dl
0x18001690b  mov     [rsp+1500h+var_14B0], dl
0x18001690f  jmp     short loc_18001691C
0x180016911  mov     rax, [rbx]
0x180016914  mov     r15b, 1
0x180016917  mov     [rsp+1500h+var_14B0], r15b
0x18001691c  mov     ecx, [rax+50h]
0x18001691f  mov     r14d, 3
0x180016925  and     ecx, 100h
0x18001692b  cmp     esi, r14d
0x18001692e  mov     [rsp+1500h+var_14AC], ecx
0x180016932  cmovl   r14d, esi
0x180016936  mov     [rsp+1500h+var_14A8], r14d
0x18001693b  cmp     [rbx+2D0h], rdx
0x180016942  jnz     short loc_180016961
0x180016944  cmp     cs:qword_1800268D8, rdx
0x18001694b  jz      short loc_180016961
0x18001694d  mov     cs:dword_1800268E4, edx
0x180016953  mov     cs:qword_1800268D8, rdx
0x18001695a  mov     cs:qword_1800268F0, rdx
0x180016961  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016965  cmp     cs:dword_1800268E4, edx
0x18001696b  jnz     loc_180016A39
0x180016971  lea     r8, [rbx+2D0h]; phModule
0x180016978  mov     cs:dword_1800268E4, 1
0x180016982  lea     rdx, aWdscoreDll; "wdscore.dll"
0x180016989  xor     ecx, ecx; dwFlags
0x18001698b  call    cs:__imp_GetModuleHandleExA
0x180016991  test    eax, eax
0x180016993  jz      short loc_1800169CB
0x180016995  mov     rcx, [rbx+2D0h]; hModule
0x18001699c  lea     rdx, aConstructparti; "ConstructPartialMsgIfA"
0x1800169a3  call    cs:__imp_GetProcAddress
0x1800169a9  mov     rcx, [rbx+2D0h]; hModule
0x1800169b0  lea     rdx, aWdssetuplogmes; "WdsSetupLogMessageA"
0x1800169b7  mov     cs:qword_1800268D8, rax
0x1800169be  call    cs:__imp_GetProcAddress
0x1800169c4  mov     cs:qword_1800268F0, rax
0x1800169cb  mov     [rsp+1500h+hTemplateFile], 0; hTemplateFile
0x1800169d4  lea     rcx, FileName; "\\\\.\\pipe\\GmdAslLogger"
0x1800169db  mov     [rsp+1500h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1800169e3  xor     r9d, r9d; lpSecurityAttributes
0x1800169e6  xor     r8d, r8d; dwShareMode
0x1800169e9  mov     [rsp+1500h+dwCreationDisposition], 3; dwCreationDisposition
0x1800169f1  mov     edx, 40000000h; dwDesiredAccess
0x1800169f6  call    cs:__imp_CreateFileW
0x1800169fc  cmp     rax, rdi
0x1800169ff  jnz     short loc_180016A20
0x180016a01  call    cs:__imp_GetLastError
0x180016a07  mov     ecx, [rsp+1500h+var_14AC]
0x180016a0b  xor     edx, edx
0x180016a0d  cmp     eax, 0E7h
0x180016a12  jnz     short loc_180016A39
0x180016a14  mov     cs:dword_1800268D4, 1
0x180016a1e  jmp     short loc_180016A39
0x180016a20  mov     rcx, rax; hObject
0x180016a23  mov     cs:dword_1800268D4, 1
0x180016a2d  call    cs:__imp_CloseHandle
0x180016a33  mov     ecx, [rsp+1500h+var_14AC]
0x180016a37  xor     edx, edx
0x180016a39  cmp     cs:qword_1800268D8, rdx
0x180016a40  jz      short loc_180016A4D
0x180016a42  cmp     cs:qword_1800268F0, rdx
0x180016a49  mov     al, 1
0x180016a4b  jnz     short loc_180016A4F
0x180016a4d  mov     al, dl
0x180016a4f  mov     [rsp+1500h+var_14AF], al
0x180016a53  test    r15b, r15b
0x180016a56  jnz     short loc_180016A71
0x180016a58  cmp     esi, 1
0x180016a5b  jz      short loc_180016A71
0x180016a5d  test    al, al
0x180016a5f  jnz     short loc_180016A71
0x180016a61  cmp     cs:dword_1800268D4, edx
0x180016a67  jnz     short loc_180016A71
0x180016a69  test    ecx, ecx
0x180016a6b  jz      loc_18001701C
0x180016a71  mov     r15d, 3FEh
0x180016a77  lea     rax, [rbp+1400h+WideCharStr]
0x180016a7e  mov     r9, r12
0x180016a81  mov     [rsp+1500h+Buffer], rax
0x180016a86  lea     r8, aHs_0; "%hs"
0x180016a8d  mov     [rsp+1500h+var_1488], r15
0x180016a92  lea     rcx, [rbp+1400h+Format]
0x180016a99  lea     r12d, [r15+2]
0x180016a9d  mov     edx, r12d
0x180016aa0  call    RtlStringCchPrintfW
0x180016aa5  xor     r10d, r10d
0x180016aa8  lea     rbx, aAslLogFail; "ASL_LOG FAIL: "
0x180016aaf  mov     esi, 7FFFFFFEh
0x180016ab4  test    eax, eax
0x180016ab6  jns     short loc_180016AFA
0x180016ab8  mov     ecx, esi
0x180016aba  lea     rax, [rbp+1400h+Format]
0x180016ac1  mov     r8, rbx
0x180016ac4  mov     edx, r12d
0x180016ac7  test    rcx, rcx
0x180016aca  jz      short loc_180016AEB
0x180016acc  movzx   r9d, word ptr [r8]
0x180016ad0  test    r9w, r9w
0x180016ad4  jz      short loc_180016AEB
0x180016ad6  mov     [rax], r9w
0x180016ada  add     r8, 2
0x180016ade  add     rax, 2
0x180016ae2  dec     rcx
0x180016ae5  sub     rdx, 1
0x180016ae9  jnz     short loc_180016AC7
0x180016aeb  test    rdx, rdx
0x180016aee  lea     rcx, [rax-2]
0x180016af2  cmovnz  rcx, rax
0x180016af6  mov     [rcx], r10w
0x180016afa  movzx   eax, [rbp+1400h+Format]
0x180016b01  test    ax, ax
0x180016b04  jz      short loc_180016B53
0x180016b06  mov     edx, 53h ; 'S'
0x180016b0b  lea     rcx, [rbp+1400h+Format]
0x180016b12  lea     r8d, [rdx+20h]
0x180016b16  cmp     ax, 25h ; '%'
0x180016b1a  jnz     short loc_180016B47
0x180016b1c  add     rcx, 2
0x180016b20  cmp     word ptr [rcx], 2Eh ; '.'
0x180016b24  jz      short loc_180016B1C
0x180016b26  movzx   eax, word ptr [rcx]
0x180016b29  sub     ax, 30h ; '0'
0x180016b2d  cmp     ax, 9
0x180016b31  jbe     short loc_180016B1C
0x180016b33  cmp     [rcx], r8w
0x180016b37  jnz     short loc_180016B3E
0x180016b39  mov     [rcx], dx
0x180016b3c  jmp     short loc_180016B47
0x180016b3e  cmp     [rcx], dx
0x180016b41  jnz     short loc_180016B47
0x180016b43  mov     [rcx], r8w
0x180016b47  add     rcx, 2
0x180016b4b  movzx   eax, word ptr [rcx]
0x180016b4e  test    ax, ax
0x180016b51  jnz     short loc_180016B16
0x180016b53  mov     eax, r13d
0x180016b56  cmp     r13, rdi
0x180016b59  jnz     short loc_180016B5E
0x180016b5b  mov     eax, r10d
0x180016b5e  mov     [rsp+1500h+var_14C0], eax
0x180016b62  lea     rcx, off_18001BBF8; "PRINT"
0x180016b69  mov     rax, [rsp+1500h+var_1498]
0x180016b6e  lea     r9, [rsp+1500h+var_1488]; unsigned __int64 *
0x180016b73  mov     [rsp+1500h+lpUsedDefaultChar], rax
0x180016b78  lea     r8, [rsp+1500h+Buffer]; unsigned __int16 **
0x180016b7d  movsxd  r13, r14d
0x180016b80  mov     rdx, r15; unsigned __int64
0x180016b83  add     r13, r13
0x180016b86  mov     rax, [rcx+r13*8]
0x180016b8a  lea     rcx, [rbp+1400h+WideCharStr]; Buffer
0x180016b91  mov     [rsp+1500h+hTemplateFile], rax
0x180016b96  lea     rax, aHsHsD; "%hs,%hs,%d,"
0x180016b9d  mov     qword ptr [rsp+1500h+dwFlagsAndAttributes], rax; unsigned __int16 *
0x180016ba2  mov     [rsp+1500h+dwCreationDisposition], 100h; unsigned int
0x180016baa  call    ?RtlStringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; RtlStringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180016baf  xor     r9d, r9d
0x180016bb2  test    eax, eax
0x180016bb4  jns     short loc_180016BF6
0x180016bb6  mov     rcx, rsi
0x180016bb9  lea     rax, [rbp+1400h+WideCharStr]
0x180016bc0  mov     rdx, r12
0x180016bc3  test    rcx, rcx
0x180016bc6  jz      short loc_180016BE7
0x180016bc8  movzx   r8d, word ptr [rbx]
0x180016bcc  test    r8w, r8w
0x180016bd0  jz      short loc_180016BE7
0x180016bd2  mov     [rax], r8w
0x180016bd6  add     rbx, 2
0x180016bda  add     rax, 2
0x180016bde  dec     rcx
0x180016be1  sub     rdx, 1
0x180016be5  jnz     short loc_180016BC3
0x180016be7  test    rdx, rdx
0x180016bea  lea     rcx, [rax-2]
0x180016bee  cmovnz  rcx, rax
0x180016bf2  mov     [rcx], r9w
0x180016bf6  mov     r14, [rsp+1500h+Buffer]
0x180016bfb  mov     r12d, 80000005h
0x180016c01  mov     rsi, [rsp+1500h+var_1488]
0x180016c06  mov     rdi, r14
0x180016c09  mov     r15, rsi
0x180016c0c  test    r14, r14
0x180016c0f  jnz     short loc_180016C16
0x180016c11  test    rsi, rsi
0x180016c14  jnz     short loc_180016C1F
0x180016c16  cmp     r15, 7FFFFFFFh
0x180016c1d  jbe     short loc_180016C28
0x180016c1f  mov     [r14], r9w
0x180016c23  jmp     loc_180016CB6
0x180016c28  test    r15, r15
0x180016c2b  jnz     short loc_180016C51
0x180016c2d  mov     rdx, rdi
0x180016c30  mov     rax, r15
0x180016c33  mov     ecx, r9d
0x180016c36  cmp     [rbp+1400h+Format], r9w
0x180016c3e  jz      short loc_180016C9F
0x180016c40  test    rdi, rdi
0x180016c43  jnz     short loc_180016C4C
0x180016c45  mov     ecx, 0C000000Dh
0x180016c4a  jmp     short loc_180016CA5
0x180016c4c  mov     ecx, r12d
0x180016c4f  jmp     short loc_180016C9F
0x180016c51  mov     r9, [rbp+1400h+Args]; Args
0x180016c55  lea     rbx, [rsi-1]
0x180016c59  mov     rdx, rbx; BufferCount
0x180016c5c  lea     r8, [rbp+1400h+Format]; Format
0x180016c63  mov     rcx, rdi; Buffer
0x180016c66  call    cs:__imp__vsnwprintf
0x180016c6c  xor     r9d, r9d
0x180016c6f  test    eax, eax
0x180016c71  js      short loc_180016C84
0x180016c73  cdqe
0x180016c75  cmp     rax, rbx
0x180016c78  ja      short loc_180016C84
0x180016c7a  mov     ecx, r9d
0x180016c7d  jz      short loc_180016C87
0x180016c7f  mov     rbx, rax
0x180016c82  jmp     short loc_180016C8C
0x180016c84  mov     ecx, r12d
0x180016c87  mov     [r14+rbx*2], r9w
0x180016c8c  mov     rax, r15
0x180016c8f  lea     rdx, [r14+rbx*2]
0x180016c93  sub     rax, rbx
0x180016c96  test    ecx, ecx
0x180016c98  jns     short loc_180016C9F
0x180016c9a  cmp     ecx, r12d
0x180016c9d  jnz     short loc_180016CA5
0x180016c9f  mov     r14, rdx
0x180016ca2  mov     rsi, rax
0x180016ca5  mov     edx, 80000000h
0x180016caa  lea     eax, [rcx+rdx]
0x180016cad  test    edx, eax
0x180016caf  jnz     short loc_180016D0C
0x180016cb1  cmp     ecx, r12d
0x180016cb4  jz      short loc_180016D0C
0x180016cb6  test    rsi, rsi
0x180016cb9  jz      short loc_180016D0C
0x180016cbb  cmp     rsi, 7FFFFFFFh
0x180016cc2  jbe     short loc_180016CCC
0x180016cc4  xor     esi, esi
0x180016cc6  mov     [r14], si
0x180016cca  jmp     short loc_180016D0E
0x180016ccc  mov     eax, 7FFFFFFEh
0x180016cd1  lea     rdx, aMessageTooLong; "Message too long!"
0x180016cd8  test    rax, rax
0x180016cdb  jz      short loc_180016CFA
0x180016cdd  movzx   ecx, word ptr [rdx]
0x180016ce0  test    cx, cx
0x180016ce3  jz      short loc_180016CFA
0x180016ce5  mov     [r14], cx
0x180016ce9  add     rdx, 2
0x180016ced  add     r14, 2
0x180016cf1  dec     rax
0x180016cf4  sub     rsi, 1
0x180016cf8  jnz     short loc_180016CD8
0x180016cfa  test    rsi, rsi
0x180016cfd  lea     rcx, [r14-2]
0x180016d01  cmovnz  rcx, r14
0x180016d05  xor     esi, esi
0x180016d07  mov     [rcx], si
0x180016d0a  jmp     short loc_180016D0E
  ... truncated ...
```
