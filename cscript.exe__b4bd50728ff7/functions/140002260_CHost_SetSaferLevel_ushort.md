# CHost::SetSaferLevel(ushort *)

- ea: `0x140002260`
- end: `0x140002628`
- name: `?SetSaferLevel@CHost@@IEAAJPEAG@Z`
- size: `968`
- prototype: `__int64 __fastcall(CHost *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1400014b0`

## callees

- `0x140002260`
- `0x140009c70`
- `0x140009cb0`
- `0x140010a20`
- `0x14001619a`
- `0x1400161d0`
- `0x140017010`

## import_xrefs

- `msvcrt!wcsrchr` at `0x14000243f`
- `msvcrt!wcsrchr` at `0x14000243f`
- `msvcrt!strcpy_s` at `0x140002387`
- `msvcrt!strcpy_s` at `0x14000239b`
- `msvcrt!strcpy_s` at `0x140002387`
- `msvcrt!strcpy_s` at `0x14000239b`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025ab`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025ab`
- `OLEAUT32!__imp_SysStringLen` at `0x14000242b`
- `OLEAUT32!__imp_SysStringLen` at `0x14000242b`
- `KERNEL32!CloseHandle` at `0x1400025d2`
- `KERNEL32!CloseHandle` at `0x1400025d2`
- `KERNEL32!GetProcAddress` at `0x1400023d6`
- `KERNEL32!GetProcAddress` at `0x1400023f2`
- `KERNEL32!GetProcAddress` at `0x14000240e`
- `KERNEL32!GetProcAddress` at `0x14000256a`
- `KERNEL32!GetProcAddress` at `0x1400023d6`
- `KERNEL32!GetProcAddress` at `0x1400023f2`
- `KERNEL32!GetProcAddress` at `0x14000240e`
- `KERNEL32!GetProcAddress` at `0x14000256a`
- `KERNEL32!GetSystemDirectoryA` at `0x14000230b`
- `KERNEL32!GetSystemDirectoryA` at `0x140002351`
- `KERNEL32!GetSystemDirectoryA` at `0x14000230b`
- `KERNEL32!GetSystemDirectoryA` at `0x140002351`
- `KERNEL32!GetLastError` at `0x140002317`
- `KERNEL32!GetLastError` at `0x14000235b`
- `KERNEL32!GetLastError` at `0x14000250c`
- `KERNEL32!GetLastError` at `0x14000254b`
- `KERNEL32!GetLastError` at `0x140002317`
- `KERNEL32!GetLastError` at `0x14000235b`
- `KERNEL32!GetLastError` at `0x14000250c`
- `KERNEL32!GetLastError` at `0x14000254b`
- `KERNEL32!FreeLibrary` at `0x1400025ff`
- `KERNEL32!FreeLibrary` at `0x1400025ff`
- `KERNEL32!LoadLibraryExA` at `0x1400023ac`
- `KERNEL32!LoadLibraryExA` at `0x1400023ac`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140002593`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140002593`

## string_xrefs

- `0x140002394`: `advapi32.dll`
- `0x1400023e8`: `SaferComputeTokenFromLevel`

## pseudocode

```c
__int64 __fastcall CHost::SetSaferLevel(CHost *this, unsigned __int16 *a2)
{
  bool v3; // zf
  OLECHAR *v4; // r15
  void (*v6)(void); // r13
  HMODULE v7; // r14
  UINT SystemDirectoryA; // eax
  UINT v9; // ebx
  signed int v10; // eax
  signed int v11; // ebx
  UINT v12; // edi
  CHAR *v13; // rax
  CHAR *v14; // r12
  UINT v15; // eax
  signed int LastError; // eax
  UINT v17; // ebx
  char *v18; // rdi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rdi
  FARPROC v21; // r12
  UINT v22; // ebx
  wchar_t *v23; // rax
  int v24; // eax
  unsigned int v25; // ebx
  signed int v26; // eax
  signed int v27; // eax
  FARPROC v28; // rax
  CHAR Buffer[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-C0h] BYREF
  BSTR v32; // [rsp+48h] [rbp-B8h]
  HANDLE hToken; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v34; // [rsp+58h] [rbp-A8h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-A0h]
  _DWORD v36[2]; // [rsp+70h] [rbp-90h] BYREF
  BSTR v37; // [rsp+78h] [rbp-88h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+88h] [rbp-78h]
  __int128 v40; // [rsp+8Ch] [rbp-74h]
  __int128 v41; // [rsp+9Ch] [rbp-64h]
  __int128 v42; // [rsp+ACh] [rbp-54h]
  __int128 v43; // [rsp+BCh] [rbp-44h]
  int v44; // [rsp+CCh] [rbp-34h]
  __int64 v45; // [rsp+D0h] [rbp-30h]
  int v46; // [rsp+D8h] [rbp-28h]
  __int128 v47; // [rsp+E0h] [rbp-20h]
  int v48; // [rsp+F0h] [rbp-10h]

  pbstr = a2;
  hToken = 0;
  memset_0(v36, 0, 0xB0u);
  v3 = *((_DWORD *)this + 2) == 1;
  v4 = 0;
  v30 = 0;
  v34 = 0;
  bstrString = 0;
  if ( v3 )
    return 2147946951LL;
  if ( !*((_BYTE *)this + 74) )
    return 1;
  v6 = 0;
  v7 = 0;
  v32 = (BSTR)*((_QWORD *)this + 76);
  SystemDirectoryA = GetSystemDirectoryA(Buffer, 0);
  v9 = SystemDirectoryA;
  if ( SystemDirectoryA )
  {
    v12 = SystemDirectoryA + 14;
    v13 = (CHAR *)operator new(SystemDirectoryA + 14);
    v14 = v13;
    if ( !v13 )
      goto LABEL_38;
    v15 = GetSystemDirectoryA(v13, v9 + 1);
    if ( v15
      && (v17 = v12 - v15,
          v18 = &v14[v15],
          strcpy_s(v18, v17, "\\"),
          strcpy_s(v18 + 1, v17 - 1, "advapi32.dll"),
          (Library = LoadLibraryExA(v14, 0, 0x800u)) != 0) )
    {
      v7 = Library;
      v11 = 0;
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
    }
    operator delete(v14);
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
  }
  if ( v11 >= 0 )
  {
    ProcAddress = GetProcAddress(v7, "SaferIdentifyLevel");
    if ( ProcAddress )
    {
      v21 = GetProcAddress(v7, "SaferComputeTokenFromLevel");
      if ( v21 )
      {
        v6 = (void (*)(void))GetProcAddress(v7, "SaferCloseLevel");
        if ( v6 )
        {
          if ( *((_BYTE *)this + 75) )
          {
            v22 = SysStringLen(pbstr);
            v23 = wcsrchr(*((const wchar_t **)this + 76), 0x2Eu);
            v24 = SafeCreateTempFile(v23, pbstr, v22, &v34, (CHAR *)&bstrString);
            v4 = bstrString;
            v25 = v24;
            if ( v24 < 0 )
              goto LABEL_36;
            v32 = bstrString;
          }
          memset_0(v36, 0, 0xB0u);
          v37 = v32;
          v38 = v34;
          v36[0] = 176;
          v36[1] = 13;
          v39 = 0;
          v40 = 0;
          v44 = 0;
          v41 = 0;
          v45 = 0;
          v42 = 0;
          v46 = 0;
          v43 = 0;
          v47 = 0;
          if ( *((_DWORD *)this + 19) != 1 || (v48 = 1, *((_BYTE *)this + 68)) )
            v48 = 2;
          if ( !((unsigned int (__fastcall *)(__int64, _DWORD *, __int64 *, const wchar_t *))ProcAddress)(
                  1,
                  v36,
                  &v30,
                  L"SCRIPT") )
            goto LABEL_26;
          if ( !((unsigned int (__fastcall *)(__int64, _QWORD, HANDLE *, __int64, _QWORD))v21)(v30, 0, &hToken, 1, 0) )
          {
            v27 = GetLastError();
            v25 = v27;
            if ( v27 > 0 )
              v25 = (unsigned __int16)v27 | 0x80070000;
            v28 = GetProcAddress(v7, "SaferRecordEventLogEntry");
            if ( v28 )
              ((void (__fastcall *)(__int64, BSTR, _QWORD))v28)(v30, v32, 0);
            goto LABEL_36;
          }
          if ( !hToken || ImpersonateLoggedOnUser(hToken) )
          {
            v25 = 0;
          }
          else
          {
LABEL_26:
            v26 = GetLastError();
            v25 = v26;
            if ( v26 > 0 )
              v25 = (unsigned __int16)v26 | 0x80070000;
          }
LABEL_36:
          if ( v4 )
            SysFreeString(v4);
          goto LABEL_39;
        }
      }
    }
  }
LABEL_38:
  v25 = 1;
LABEL_39:
  if ( hToken )
    CloseHandle(hToken);
  if ( v30 && v6 )
    v6();
  if ( v7 )
    FreeLibrary(v7);
  return v25;
}

```

## disassembly

```asm
0x140002260  push    rbp
0x140002262  push    rbx
0x140002263  push    rsi
0x140002264  push    r15
0x140002266  lea     rbp, [rsp-48h]
0x14000226b  sub     rsp, 148h
0x140002272  mov     rax, cs:__security_cookie
0x140002279  xor     rax, rsp
0x14000227c  mov     [rbp+60h+var_40], rax
0x140002280  mov     [rsp+160h+pbstr], rdx
0x140002285  mov     rsi, rcx
0x140002288  xor     ebx, ebx
0x14000228a  lea     rcx, [rsp+160h+var_F0]; void *
0x14000228f  xor     edx, edx; Val
0x140002291  mov     [rsp+160h+hToken], rbx
0x140002296  mov     r8d, 0B0h; Size
0x14000229c  call    memset_0
0x1400022a1  cmp     dword ptr [rsi+8], 1
0x1400022a5  mov     r15d, ebx
0x1400022a8  mov     [rsp+160h+var_128], rbx
0x1400022ad  mov     [rsp+160h+var_108], rbx
0x1400022b2  mov     [rsp+160h+bstrString], rbx
0x1400022b7  jnz     short loc_1400022C3
0x1400022b9  mov     eax, 800711C7h
0x1400022be  jmp     loc_14000260F
0x1400022c3  cmp     [rsi+4Ah], bl
0x1400022c6  jnz     short loc_1400022D2
0x1400022c8  mov     eax, 1
0x1400022cd  jmp     loc_14000260F
0x1400022d2  mov     rax, [rsi+260h]
0x1400022d9  lea     rcx, [rsp+160h+Buffer]; lpBuffer
0x1400022de  mov     [rsp+160h+arg_10], rdi
0x1400022e6  xor     edx, edx; uSize
0x1400022e8  mov     [rsp+160h+var_20], r12
0x1400022f0  mov     [rsp+160h+var_28], r13
0x1400022f8  mov     r13, rbx
0x1400022fb  mov     [rsp+160h+var_30], r14
0x140002303  mov     r14, rbx
0x140002306  mov     [rsp+160h+var_118], rax
0x14000230b  call    cs:__imp_GetSystemDirectoryA
0x140002311  mov     ebx, eax
0x140002313  test    eax, eax
0x140002315  jnz     short loc_140002335
0x140002317  call    cs:__imp_GetLastError
0x14000231d  mov     ebx, eax
0x14000231f  test    eax, eax
0x140002321  jle     loc_1400023C4
0x140002327  movzx   ebx, ax
0x14000232a  or      ebx, 80070000h
0x140002330  jmp     loc_1400023C4
0x140002335  lea     edi, [rax+0Eh]
0x140002338  mov     ecx, edi; Size
0x14000233a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000233f  mov     r12, rax
0x140002342  test    rax, rax
0x140002345  jz      loc_1400025B3
0x14000234b  lea     edx, [rbx+1]; uSize
0x14000234e  mov     rcx, rax; lpBuffer
0x140002351  call    cs:__imp_GetSystemDirectoryA
0x140002357  test    eax, eax
0x140002359  jnz     short loc_140002372
0x14000235b  call    cs:__imp_GetLastError
0x140002361  mov     ebx, eax
0x140002363  test    eax, eax
0x140002365  jle     short loc_1400023BC
0x140002367  movzx   ebx, ax
0x14000236a  or      ebx, 80070000h
0x140002370  jmp     short loc_1400023BC
0x140002372  sub     edi, eax
0x140002374  lea     r8, asc_14001A1DC; "\\"
0x14000237b  mov     ebx, edi
0x14000237d  mov     edi, eax
0x14000237f  mov     edx, ebx; SizeInBytes
0x140002381  add     rdi, r12
0x140002384  mov     rcx, rdi; Destination
0x140002387  call    cs:__imp_strcpy_s
0x14000238d  lea     edx, [rbx-1]; SizeInBytes
0x140002390  lea     rcx, [rdi+1]; Destination
0x140002394  lea     r8, aAdvapi32Dll_0; "advapi32.dll"
0x14000239b  call    cs:__imp_strcpy_s
0x1400023a1  xor     edx, edx; hFile
0x1400023a3  mov     r8d, 800h; dwFlags
0x1400023a9  mov     rcx, r12; lpLibFileName
0x1400023ac  call    cs:__imp_LoadLibraryExA
0x1400023b2  test    rax, rax
0x1400023b5  jz      short loc_14000235B
0x1400023b7  mov     r14, rax
0x1400023ba  xor     ebx, ebx
0x1400023bc  mov     rcx, r12; Block
0x1400023bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400023c4  test    ebx, ebx
0x1400023c6  js      loc_1400025B3
0x1400023cc  lea     rdx, aSaferidentifyl; "SaferIdentifyLevel"
0x1400023d3  mov     rcx, r14; hModule
0x1400023d6  call    cs:__imp_GetProcAddress
0x1400023dc  mov     rdi, rax
0x1400023df  test    rax, rax
0x1400023e2  jz      loc_1400025B3
0x1400023e8  lea     rdx, aSafercomputeto; "SaferComputeTokenFromLevel"
0x1400023ef  mov     rcx, r14; hModule
0x1400023f2  call    cs:__imp_GetProcAddress
0x1400023f8  mov     r12, rax
0x1400023fb  test    rax, rax
0x1400023fe  jz      loc_1400025B3
0x140002404  lea     rdx, aSafercloseleve; "SaferCloseLevel"
0x14000240b  mov     rcx, r14; hModule
0x14000240e  call    cs:__imp_GetProcAddress
0x140002414  mov     r13, rax
0x140002417  test    rax, rax
0x14000241a  jz      loc_1400025B3
0x140002420  cmp     [rsi+4Bh], r15b
0x140002424  jz      short loc_140002478
0x140002426  mov     rcx, [rsp+160h+pbstr]; pbstr
0x14000242b  call    cs:__imp_SysStringLen
0x140002431  mov     rcx, [rsi+260h]; Str
0x140002438  mov     edx, 2Eh ; '.'; Ch
0x14000243d  mov     ebx, eax
0x14000243f  call    cs:__imp_wcsrchr
0x140002445  mov     rdx, [rsp+160h+pbstr]; lpBuffer
0x14000244a  lea     rcx, [rsp+160h+bstrString]
0x14000244f  mov     [rsp+160h+lpPathName], rcx; lpPathName
0x140002454  lea     r9, [rsp+160h+var_108]
0x140002459  mov     rcx, rax; lpWideCharStr
0x14000245c  mov     r8d, ebx
0x14000245f  call    SafeCreateTempFile
0x140002464  mov     r15, [rsp+160h+bstrString]
0x140002469  mov     ebx, eax
0x14000246b  test    eax, eax
0x14000246d  js      loc_1400025A3
0x140002473  mov     [rsp+160h+var_118], r15
0x140002478  xor     edx, edx; Val
0x14000247a  lea     rcx, [rsp+160h+var_F0]; void *
0x14000247f  mov     r8d, 0B0h; Size
0x140002485  call    memset_0
0x14000248a  mov     rax, [rsp+160h+var_118]
0x14000248f  xorps   xmm0, xmm0
0x140002492  mov     [rsp+160h+var_E8], rax
0x140002497  mov     ebx, 1
0x14000249c  mov     rax, [rsp+160h+var_108]
0x1400024a1  mov     [rbp+60h+var_E0], rax
0x1400024a5  xor     eax, eax
0x1400024a7  mov     [rsp+160h+var_F0], 0B0h
0x1400024af  mov     [rsp+160h+var_EC], 0Dh
0x1400024b7  mov     [rbp+60h+var_D8], eax
0x1400024ba  movups  [rbp+60h+var_D4], xmm0
0x1400024be  mov     [rbp+60h+var_94], eax
0x1400024c1  movups  [rbp+60h+var_C4], xmm0
0x1400024c5  mov     [rbp+60h+var_90], rax
0x1400024c9  movups  [rbp+60h+var_B4], xmm0
0x1400024cd  mov     [rbp+60h+var_88], eax
0x1400024d0  movups  [rbp+60h+var_A4], xmm0
0x1400024d4  movdqa  [rbp+60h+var_80], xmm0
0x1400024d9  cmp     [rsi+4Ch], ebx
0x1400024dc  jnz     short loc_1400024E6
0x1400024de  mov     [rbp+60h+var_70], ebx
0x1400024e1  cmp     [rsi+44h], al
0x1400024e4  jz      short loc_1400024ED
0x1400024e6  mov     [rbp+60h+var_70], 2
0x1400024ed  lea     r9, aScript; "SCRIPT"
0x1400024f4  mov     ecx, ebx
0x1400024f6  lea     r8, [rsp+160h+var_128]
0x1400024fb  mov     rax, rdi
0x1400024fe  lea     rdx, [rsp+160h+var_F0]
0x140002503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002508  test    eax, eax
0x14000250a  jnz     short loc_140002527
0x14000250c  call    cs:__imp_GetLastError
0x140002512  mov     ebx, eax
0x140002514  test    eax, eax
0x140002516  jle     loc_1400025A3
0x14000251c  movzx   ebx, ax
0x14000251f  or      ebx, 80070000h
0x140002525  jmp     short loc_1400025A3
0x140002527  mov     rcx, [rsp+160h+var_128]
0x14000252c  lea     r8, [rsp+160h+hToken]
0x140002531  mov     r9d, ebx
0x140002534  mov     [rsp+160h+lpPathName], 0
0x14000253d  xor     edx, edx
0x14000253f  mov     rax, r12
0x140002542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002547  test    eax, eax
0x140002549  jnz     short loc_140002589
0x14000254b  call    cs:__imp_GetLastError
0x140002551  mov     ebx, eax
0x140002553  test    eax, eax
0x140002555  jle     short loc_140002560
0x140002557  movzx   ebx, ax
0x14000255a  or      ebx, 80070000h
0x140002560  lea     rdx, aSaferrecordeve; "SaferRecordEventLogEntry"
0x140002567  mov     rcx, r14; hModule
0x14000256a  call    cs:__imp_GetProcAddress
0x140002570  test    rax, rax
0x140002573  jz      short loc_1400025A3
0x140002575  mov     rdx, [rsp+160h+var_118]
0x14000257a  xor     r8d, r8d
0x14000257d  mov     rcx, [rsp+160h+var_128]
0x140002582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002587  jmp     short loc_1400025A3
0x140002589  mov     rcx, [rsp+160h+hToken]; hToken
0x14000258e  test    rcx, rcx
0x140002591  jz      short loc_1400025A1
0x140002593  call    cs:__imp_ImpersonateLoggedOnUser
0x140002599  test    eax, eax
0x14000259b  jz      loc_14000250C
0x1400025a1  xor     ebx, ebx
0x1400025a3  test    r15, r15
0x1400025a6  jz      short loc_1400025B8
0x1400025a8  mov     rcx, r15; bstrString
0x1400025ab  call    cs:__imp_SysFreeString
0x1400025b1  jmp     short loc_1400025B8
0x1400025b3  mov     ebx, 1
0x1400025b8  mov     rcx, [rsp+160h+hToken]; hObject
0x1400025bd  mov     r12, [rsp+160h+var_20]
0x1400025c5  mov     rdi, [rsp+160h+arg_10]
0x1400025cd  test    rcx, rcx
0x1400025d0  jz      short loc_1400025D8
0x1400025d2  call    cs:__imp_CloseHandle
0x1400025d8  mov     rcx, [rsp+160h+var_128]
0x1400025dd  test    rcx, rcx
0x1400025e0  jz      short loc_1400025EF
0x1400025e2  test    r13, r13
0x1400025e5  jz      short loc_1400025EF
0x1400025e7  mov     rax, r13
0x1400025ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400025ef  mov     r13, [rsp+160h+var_28]
0x1400025f7  test    r14, r14
0x1400025fa  jz      short loc_140002605
0x1400025fc  mov     rcx, r14; hLibModule
0x1400025ff  call    cs:__imp_FreeLibrary
0x140002605  mov     r14, [rsp+160h+var_30]
0x14000260d  mov     eax, ebx
0x14000260f  mov     rcx, [rbp+60h+var_40]
0x140002613  xor     rcx, rsp; StackCookie
0x140002616  call    __security_check_cookie
0x14000261b  add     rsp, 148h
0x140002622  pop     r15
0x140002624  pop     rsi
0x140002625  pop     rbx
0x140002626  pop     rbp
0x140002627  retn
```
