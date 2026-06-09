# PcaUtilityGetProgramInfo(ushort *,ushort *,ushort *,ushort *,ushort *,uint *,int *,ushort const *)

- ea: `0x180005180`
- end: `0x180005558`
- name: `?PcaUtilityGetProgramInfo@@YAKPEAG0000PEAIPEAHPEBG@Z`
- size: `984`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned int *, int *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800162e0`
- `0x18001ee64`
- `0x18008f100`
- `0x1800a82f0`
- `0x1800a8640`
- `0x1800b1b24`
- `0x1800dc5f0`

## callees

- `0x180005180`
- `0x180005560`
- `0x18000c018`
- `0x180012920`
- `0x1800133c0`
- `0x1800f7010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005228`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000538a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180005228`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000538a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005263`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000527c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180005263`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000527c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800053bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000524f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000524f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800053ce`

## string_xrefs

- `0x180005221`: `aepic.dll`
- `0x1800052fe`: `StringCchCopyW failed [%#x]`
- `0x180005326`: `StringCchCopyW failed [%#x]`
- `0x180005452`: `StringCchCopyW failed [%#x]`
- `0x180005383`: `aeinv.dll`

## pseudocode

```c
__int64 __fastcall PcaUtilityGetProgramInfo(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int *a6,
        int *a7,
        const unsigned __int16 *a8)
{
  const unsigned __int16 **v9; // rsi
  HMODULE Library; // rbx
  HMODULE v11; // rcx
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rbx
  HRESULT v14; // edi
  size_t *v15; // r8
  const char *v16; // r9
  int v17; // r8d
  const wchar_t *v18; // r9
  size_t *v19; // r8
  size_t v20; // r11
  _WORD *v21; // rcx
  BOOL v22; // eax
  void (__fastcall *v23)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD); // rdi
  HMODULE v24; // rdi
  HMODULE v25; // rcx
  FARPROC v26; // rax
  const unsigned __int16 **v27; // rax
  unsigned __int64 v28; // r11
  int v29; // edi
  int v30; // r8d
  size_t v32; // [rsp+20h] [rbp-71h]
  size_t v33; // [rsp+20h] [rbp-71h]
  FARPROC v34; // [rsp+40h] [rbp-51h]
  STRSAFE_PCNZWCH *v35; // [rsp+48h] [rbp-49h] BYREF
  void **v36; // [rsp+50h] [rbp-41h] BYREF
  HMODULE hModule; // [rsp+58h] [rbp-39h]
  void **v38; // [rsp+60h] [rbp-31h] BYREF
  HMODULE v39; // [rsp+68h] [rbp-29h]
  FARPROC v40; // [rsp+70h] [rbp-21h]
  STRSAFE_LPWSTR pszDest; // [rsp+78h] [rbp-19h]
  STRSAFE_LPWSTR v42; // [rsp+80h] [rbp-11h]
  unsigned __int16 *v43; // [rsp+88h] [rbp-9h]

  v43 = a3;
  v42 = a2;
  pszDest = a1;
  v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  v39 = 0;
  v36 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = 0;
  *a1 = 0;
  *a2 = 0;
  v9 = 0;
  v35 = 0;
  v40 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0xFFFF;
  if ( a7 )
    *a7 = 0;
  Library = LoadLibraryExW(L"aepic.dll", 0, 0x800u);
  v11 = hModule;
  if ( Library != hModule )
  {
    Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(&v36);
    v11 = Library;
    hModule = Library;
  }
  if ( v11 )
  {
    ProcAddress = GetProcAddress(v11, "PicRetrieveFileInfo");
    if ( ProcAddress )
    {
      v40 = GetProcAddress(hModule, "PicFreeFileInfo");
      if ( v40 )
      {
        v14 = ((__int64 (__fastcall *)(const unsigned __int16 *, _QWORD, STRSAFE_PCNZWCH **))ProcAddress)(a8, 0, &v35);
        if ( v14 < 0 )
        {
          v16 = "PicRetrieveFileInfo failed [%#x]";
          v17 = 2713;
LABEL_19:
          AslLogCallPrintf(1, (unsigned int)"PcaUtilityGetProgramInfo", v17, (_DWORD)v16);
          LastError = (unsigned __int16)v14;
          goto LABEL_58;
        }
        if ( !v35 || (v18 = v35[1]) == 0 )
        {
          AslLogCallPrintf(1, (unsigned int)"PcaUtilityGetProgramInfo", 2720, (unsigned int)"Invalid ProgramId");
          LastError = 3;
          goto LABEL_58;
        }
        v14 = StringCopyWorkerW(pszDest, 0x2Du, v15, v18, v32);
        if ( v14 < 0 )
        {
          v16 = "StringCchCopyW failed [%#x]";
          v17 = 2728;
          goto LABEL_19;
        }
        v14 = StringCopyWorkerW(v42, v20, v19, *v35, v33);
        if ( v14 < 0 )
        {
          v16 = "StringCchCopyW failed [%#x]";
          v17 = 2736;
          goto LABEL_19;
        }
        v21 = v35[1];
        v22 = *v21 == 48 && v21[1] == 48 && v21[2] == 48 && v21[3] == 54;
        if ( a7 )
          *a7 = v22;
        if ( v22 )
        {
          LastError = 0;
          v23 = 0;
          goto LABEL_59;
        }
        v24 = LoadLibraryExW(L"aeinv.dll", 0, 0x800u);
        v25 = v39;
        if ( v24 != v39 )
        {
          Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(&v38);
          v25 = v24;
          v39 = v24;
        }
        if ( v25 )
        {
          v26 = GetProcAddress(v25, "GetAppInfo2");
          v23 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))v26;
          v34 = v26;
          if ( !v26 )
          {
            LastError = GetLastError();
            goto LABEL_59;
          }
          v27 = (const unsigned __int16 **)((__int64 (__fastcall *)(STRSAFE_PCNZWCH, _QWORD, _QWORD, _QWORD, int, _QWORD))v26)(
                                             v35[1],
                                             0,
                                             0,
                                             0,
                                             4,
                                             0);
          v9 = v27;
          if ( !v27 )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"PcaUtilityGetProgramInfo",
              2778,
              (unsigned int)"GetAppInfo2 returned NULL");
            LastError = 3;
            goto LABEL_59;
          }
          v28 = 260;
          if ( v43 && (v29 = StringCchCopyW(v43, 0x104u, *v27), v29 < 0) )
          {
            v30 = 2788;
          }
          else if ( a4 && (v29 = StringCchCopyW(a4, v28, v9[2]), v29 < 0) )
          {
            v30 = 2799;
          }
          else
          {
            if ( !a5 || (v29 = StringCchCopyW(a5, v28, v9[3]), v29 >= 0) )
            {
              if ( a6 )
                *a6 = *((_DWORD *)v9 + 27);
              LastError = 0;
              goto LABEL_47;
            }
            v30 = 2810;
          }
          AslLogCallPrintf(
            1,
            (unsigned int)"PcaUtilityGetProgramInfo",
            v30,
            (unsigned int)"StringCchCopyW failed [%#x]");
          LastError = (unsigned __int16)v29;
LABEL_47:
          v23 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD))v34;
          goto LABEL_59;
        }
      }
    }
  }
  LastError = GetLastError();
LABEL_58:
  v23 = 0;
LABEL_59:
  if ( v35 )
    ((void (__fastcall *)(STRSAFE_PCNZWCH *))v40)(v35);
  if ( v9 )
    v23(0, 0, 0, 0, 0, v9);
  v36 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(&v36);
  v38 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(&v38);
  return LastError;
}

```

## disassembly

```asm
0x180005180  push    rbp
0x180005182  push    rbx
0x180005183  push    rsi
0x180005184  push    rdi
0x180005185  push    r12
0x180005187  push    r13
0x180005189  push    r14
0x18000518b  push    r15
0x18000518d  lea     rbp, [rsp-7]
0x180005192  sub     rsp, 98h
0x180005199  mov     r12, r9
0x18000519c  mov     [rbp+3Fh+var_48], r8
0x1800051a0  mov     [rbp+3Fh+var_50], rdx
0x1800051a4  mov     [rbp+3Fh+pszDest], rcx
0x1800051a8  mov     r13, [rbp+3Fh+arg_20]
0x1800051ac  mov     r15, [rbp+3Fh+arg_28]
0x1800051b0  mov     r14, [rbp+3Fh+arg_30]
0x1800051b4  mov     rdi, [rbp+3Fh+arg_38]
0x1800051bb  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800051c2  mov     [rbp+3Fh+var_70], rax
0x1800051c6  xor     r9d, r9d
0x1800051c9  mov     [rbp+3Fh+var_68], r9
0x1800051cd  mov     [rbp+3Fh+var_80], rax
0x1800051d1  mov     [rbp+3Fh+hModule], r9
0x1800051d5  mov     [rcx], r9w
0x1800051d9  mov     [rdx], r9w
0x1800051dd  mov     esi, r9d
0x1800051e0  mov     [rbp+3Fh+var_88], r9
0x1800051e4  mov     [rbp+3Fh+var_60], r9
0x1800051e8  test    r8, r8
0x1800051eb  jz      short loc_1800051F1
0x1800051ed  mov     [r8], r9w
0x1800051f1  test    r12, r12
0x1800051f4  jz      short loc_1800051FB
0x1800051f6  mov     [r12], r9w
0x1800051fb  test    r13, r13
0x1800051fe  jz      short loc_180005205
0x180005200  mov     [r13+0], r9w
0x180005205  test    r15, r15
0x180005208  jz      short loc_180005211
0x18000520a  mov     dword ptr [r15], 0FFFFh
0x180005211  test    r14, r14
0x180005214  jz      short loc_180005219
0x180005216  mov     [r14], r9d
0x180005219  xor     edx, edx; hFile
0x18000521b  mov     r8d, 800h; dwFlags
0x180005221  lea     rcx, LibFileName; "aepic.dll"
0x180005228  call    cs:__imp_LoadLibraryExW
0x18000522e  mov     rbx, rax
0x180005231  mov     rcx, [rbp+3Fh+hModule]
0x180005235  cmp     rax, rcx
0x180005238  jz      short loc_18000524A
0x18000523a  lea     rcx, [rbp+3Fh+var_80]
0x18000523e  call    ?Close@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(void)
0x180005243  mov     rcx, rbx; hModule
0x180005246  mov     [rbp+3Fh+hModule], rbx
0x18000524a  test    rcx, rcx
0x18000524d  jnz     short loc_18000525C
0x18000524f  call    cs:__imp_GetLastError
0x180005255  mov     ebx, eax
0x180005257  jmp     loc_1800054E6
0x18000525c  lea     rdx, ProcName; "PicRetrieveFileInfo"
0x180005263  call    cs:__imp_GetProcAddress
0x180005269  mov     rbx, rax
0x18000526c  test    rax, rax
0x18000526f  jz      short loc_18000524F
0x180005271  lea     rdx, aPicfreefileinf_0; "PicFreeFileInfo"
0x180005278  mov     rcx, [rbp+3Fh+hModule]; hModule
0x18000527c  call    cs:__imp_GetProcAddress
0x180005282  mov     [rbp+3Fh+var_60], rax
0x180005286  test    rax, rax
0x180005289  jz      short loc_18000524F
0x18000528b  lea     r8, [rbp+3Fh+var_88]
0x18000528f  xor     edx, edx
0x180005291  mov     rcx, rdi
0x180005294  mov     rax, rbx
0x180005297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000529c  mov     edi, eax
0x18000529e  test    eax, eax
0x1800052a0  jns     short loc_1800052CC
0x1800052a2  lea     r9, aPicretrievefil_2; "PicRetrieveFileInfo failed [%#x]"
0x1800052a9  mov     r8d, 0A99h
0x1800052af  mov     dword ptr [rsp+0D0h+var_B0], edi
0x1800052b3  lea     rdx, aPcautilitygetp_1; "PcaUtilityGetProgramInfo"
0x1800052ba  mov     ecx, 1
0x1800052bf  call    AslLogCallPrintf
0x1800052c4  movzx   ebx, di
0x1800052c7  jmp     loc_1800054E6
0x1800052cc  mov     rax, [rbp+3Fh+var_88]
0x1800052d0  test    rax, rax
0x1800052d3  jz      loc_1800054C3
0x1800052d9  mov     r9, [rax+8]; pszSrc
0x1800052dd  test    r9, r9
0x1800052e0  jz      loc_1800054C3
0x1800052e6  mov     r11d, 2Dh ; '-'
0x1800052ec  mov     edx, r11d; cchDest
0x1800052ef  mov     rcx, [rbp+3Fh+pszDest]; pszDest
0x1800052f3  call    StringCopyWorkerW
0x1800052f8  mov     edi, eax
0x1800052fa  test    eax, eax
0x1800052fc  jns     short loc_18000530D
0x1800052fe  lea     r9, aStringcchcopyw_0; "StringCchCopyW failed [%#x]"
0x180005305  mov     r8d, 0AA8h
0x18000530b  jmp     short loc_1800052AF
0x18000530d  mov     r9, [rbp+3Fh+var_88]
0x180005311  mov     r9, [r9]; pszSrc
0x180005314  mov     rdx, r11; cchDest
0x180005317  mov     rcx, [rbp+3Fh+var_50]; pszDest
0x18000531b  call    StringCopyWorkerW
0x180005320  mov     edi, eax
0x180005322  test    eax, eax
0x180005324  jns     short loc_180005338
0x180005326  lea     r9, aStringcchcopyw_0; "StringCchCopyW failed [%#x]"
0x18000532d  mov     r8d, 0AB0h
0x180005333  jmp     loc_1800052AF
0x180005338  mov     rax, [rbp+3Fh+var_88]
0x18000533c  mov     rcx, [rax+8]
0x180005340  mov     ebx, 1
0x180005345  cmp     word ptr [rcx], 30h ; '0'
0x180005349  jnz     short loc_180005364
0x18000534b  cmp     word ptr [rcx+2], 30h ; '0'
0x180005350  jnz     short loc_180005364
0x180005352  cmp     word ptr [rcx+4], 30h ; '0'
0x180005357  jnz     short loc_180005364
0x180005359  cmp     word ptr [rcx+6], 36h ; '6'
0x18000535e  jnz     short loc_180005364
0x180005360  mov     eax, ebx
0x180005362  jmp     short loc_180005366
0x180005364  xor     eax, eax
0x180005366  test    r14, r14
0x180005369  jz      short loc_18000536E
0x18000536b  mov     [r14], eax
0x18000536e  test    eax, eax
0x180005370  jz      short loc_18000537B
0x180005372  xor     ebx, ebx
0x180005374  mov     edi, ebx
0x180005376  jmp     loc_1800054E9
0x18000537b  xor     edx, edx; hFile
0x18000537d  mov     r8d, 800h; dwFlags
0x180005383  lea     rcx, aAeinvDll; "aeinv.dll"
0x18000538a  call    cs:__imp_LoadLibraryExW
0x180005390  mov     rdi, rax
0x180005393  mov     rcx, [rbp+3Fh+var_68]
0x180005397  cmp     rax, rcx
0x18000539a  jz      short loc_1800053AC
0x18000539c  lea     rcx, [rbp+3Fh+var_70]
0x1800053a0  call    ?Close@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(void)
0x1800053a5  mov     rcx, rdi; hModule
0x1800053a8  mov     [rbp+3Fh+var_68], rcx
0x1800053ac  test    rcx, rcx
0x1800053af  jz      loc_18000524F
0x1800053b5  lea     rdx, aGetappinfo2; "GetAppInfo2"
0x1800053bc  call    cs:__imp_GetProcAddress
0x1800053c2  mov     rdi, rax
0x1800053c5  mov     [rbp+3Fh+var_90], rax
0x1800053c9  test    rax, rax
0x1800053cc  jnz     short loc_1800053DB
0x1800053ce  call    cs:__imp_GetLastError
0x1800053d4  mov     ebx, eax
0x1800053d6  jmp     loc_1800054E9
0x1800053db  mov     [rsp+0D0h+var_A8], rsi
0x1800053e0  mov     dword ptr [rsp+0D0h+var_B0], 4
0x1800053e8  xor     r9d, r9d
0x1800053eb  xor     r8d, r8d
0x1800053ee  xor     edx, edx
0x1800053f0  mov     rcx, [rbp+3Fh+var_88]
0x1800053f4  mov     rcx, [rcx+8]
0x1800053f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053fd  mov     rsi, rax
0x180005400  test    rax, rax
0x180005403  jnz     short loc_180005428
0x180005405  lea     r9, aGetappinfo2Ret; "GetAppInfo2 returned NULL"
0x18000540c  mov     r8d, 0ADAh
0x180005412  lea     rdx, aPcautilitygetp_1; "PcaUtilityGetProgramInfo"
0x180005419  mov     ecx, ebx
0x18000541b  call    AslLogCallPrintf
0x180005420  lea     ebx, [rsi+3]
0x180005423  jmp     loc_1800054E9
0x180005428  mov     r11d, 104h
0x18000542e  mov     rcx, [rbp+3Fh+var_48]; unsigned __int16 *
0x180005432  test    rcx, rcx
0x180005435  jz      short loc_180005470
0x180005437  mov     r8, [rax]; unsigned __int16 *
0x18000543a  mov     edx, r11d; unsigned __int64
0x18000543d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005442  mov     edi, eax
0x180005444  test    eax, eax
0x180005446  jns     short loc_180005470
0x180005448  mov     r8d, 0AE4h
0x18000544e  mov     dword ptr [rsp+0D0h+var_B0], edi
0x180005452  lea     r9, aStringcchcopyw_0; "StringCchCopyW failed [%#x]"
0x180005459  lea     rdx, aPcautilitygetp_1; "PcaUtilityGetProgramInfo"
0x180005460  mov     ecx, ebx
0x180005462  call    AslLogCallPrintf
0x180005467  movzx   ebx, di
0x18000546a  mov     rdi, [rbp+3Fh+var_90]
0x18000546e  jmp     short loc_1800054E9
0x180005470  test    r12, r12
0x180005473  jz      short loc_180005492
0x180005475  mov     r8, [rsi+10h]; unsigned __int16 *
0x180005479  mov     rdx, r11; unsigned __int64
0x18000547c  mov     rcx, r12; unsigned __int16 *
0x18000547f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005484  mov     edi, eax
0x180005486  test    eax, eax
0x180005488  jns     short loc_180005492
0x18000548a  mov     r8d, 0AEFh
0x180005490  jmp     short loc_18000544E
0x180005492  test    r13, r13
0x180005495  jz      short loc_1800054B4
0x180005497  mov     r8, [rsi+18h]; unsigned __int16 *
0x18000549b  mov     rdx, r11; unsigned __int64
0x18000549e  mov     rcx, r13; unsigned __int16 *
0x1800054a1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800054a6  mov     edi, eax
0x1800054a8  test    eax, eax
0x1800054aa  jns     short loc_1800054B4
0x1800054ac  mov     r8d, 0AFAh
0x1800054b2  jmp     short loc_18000544E
0x1800054b4  test    r15, r15
0x1800054b7  jz      short loc_1800054BF
0x1800054b9  mov     eax, [rsi+6Ch]
0x1800054bc  mov     [r15], eax
0x1800054bf  xor     ebx, ebx
0x1800054c1  jmp     short loc_18000546A
0x1800054c3  lea     r9, aInvalidProgram; "Invalid ProgramId"
0x1800054ca  mov     r8d, 0AA0h
0x1800054d0  lea     rdx, aPcautilitygetp_1; "PcaUtilityGetProgramInfo"
0x1800054d7  mov     ecx, 1
0x1800054dc  call    AslLogCallPrintf
0x1800054e1  mov     ebx, 3
0x1800054e6  mov     rdi, rsi
0x1800054e9  mov     rcx, [rbp+3Fh+var_88]
0x1800054ed  test    rcx, rcx
0x1800054f0  jz      short loc_1800054FB
0x1800054f2  mov     rax, [rbp+3Fh+var_60]
0x1800054f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fb  test    rsi, rsi
0x1800054fe  jz      short loc_180005520
0x180005500  mov     [rsp+0D0h+var_A8], rsi
0x180005505  mov     dword ptr [rsp+0D0h+var_B0], 0
0x18000550d  xor     r9d, r9d
0x180005510  xor     r8d, r8d
0x180005513  xor     edx, edx
0x180005515  xor     ecx, ecx
0x180005517  mov     rax, rdi
0x18000551a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551f  nop
0x180005520  lea     rdi, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x180005527  mov     [rbp+3Fh+var_80], rdi
0x18000552b  lea     rcx, [rbp+3Fh+var_80]
0x18000552f  call    ?Close@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(void)
0x180005534  nop
0x180005535  mov     [rbp+3Fh+var_70], rdi
0x180005539  lea     rcx, [rbp+3Fh+var_70]
0x18000553d  call    ?Close@?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::Close(void)
0x180005542  mov     eax, ebx
0x180005544  add     rsp, 98h
0x18000554b  pop     r15
0x18000554d  pop     r14
0x18000554f  pop     r13
0x180005551  pop     r12
0x180005553  pop     rdi
0x180005554  pop     rsi
0x180005555  pop     rbx
0x180005556  pop     rbp
0x180005557  retn
```
