# WorkbookSetupLocalizedInfo(x)

- ea: `0x1001e690`
- end: `0x1001eb97`
- name: `_WorkbookSetupLocalizedInfo@4`
- size: `1287`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x10006bd0`

## callees

- `0x10006370`
- `0x10006400`
- `0x1001e690`
- `0x10032dda`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1001e92b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1001e93f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1001e92b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1001e93f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1001e6e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1001e6e9`

## string_xrefs

- `0x1001e6bf`: `MSJINT40.DLL`
- `0x1001e970`: `Auto_Open`

## pseudocode

```c
int __stdcall WorkbookSetupLocalizedInfo(int a1)
{
  HMODULE hModule; // [esp+18h] [ebp-90h]
  FARPROC CchLszOfId2; // [esp+1Ch] [ebp-8Ch]
  unsigned int i; // [esp+20h] [ebp-88h]
  unsigned int j; // [esp+20h] [ebp-88h]
  _WORD v6[64]; // [esp+24h] [ebp-84h] BYREF

  hModule = (HMODULE)JetLoadLibraryW(L"MSJINT40.DLL");
  if ( hModule )
  {
    CchLszOfId2 = GetProcAddress(hModule, "CchLszOfId2");
    if ( CchLszOfId2 )
    {
      for ( i = 0; i <= 0xC; ++i )
      {
        ((void (__thiscall *)(FARPROC, unsigned int, char *, int))CchLszOfId2)(
          CchLszOfId2,
          i + 10000,
          (char *)dword_1003B554 + 66 * i,
          32);
        if ( !WCSLEN((char *)dword_1003B554 + 66 * i) )
          goto LABEL_16;
      }
      for ( j = 0; j <= 6; ++j )
      {
        ((void (__thiscall *)(FARPROC, unsigned int, char *, int))CchLszOfId2)(
          CchLszOfId2,
          j + 10013,
          (char *)dword_1003B344 + 66 * j,
          32);
        if ( !WCSLEN((char *)dword_1003B344 + 66 * j) )
          goto LABEL_16;
      }
      ((void (__thiscall *)(FARPROC, int, int *, int))CchLszOfId2)(CchLszOfId2, 10020, WorkbookLocalizedInfo, 32);
      if ( WCSLEN(WorkbookLocalizedInfo) )
      {
        ((void (__thiscall *)(FARPROC, int, __int16 *, int))CchLszOfId2)(CchLszOfId2, 10021, &word_1003B302, 32);
        if ( WCSLEN(&word_1003B302) )
        {
          ((void (__thiscall *)(FARPROC, int, _WORD *, int))CchLszOfId2)(CchLszOfId2, 10098, v6, 128);
          if ( WCSLEN(v6) )
          {
            word_1003B8AE = v6[0];
            ((void (__thiscall *)(FARPROC, int, _WORD *, int))CchLszOfId2)(CchLszOfId2, 10099, v6, 128);
            if ( WCSLEN(v6) )
            {
              word_1003B8B0 = v6[0];
              FreeLibrary(hModule);
              return 0;
            }
          }
        }
      }
    }
LABEL_16:
    FreeLibrary(hModule);
  }
  WCSCPY2(dword_1003B554, L"Consolidate_Area", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[16] + 1, L"Auto_Open", 0x21u);
  WCSCPY2(&dword_1003B554[33], L"Auto_Close", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[49] + 1, L"Extract", 0x21u);
  WCSCPY2(&dword_1003B554[66], L"Database", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[82] + 1, L"Criteria", 0x21u);
  WCSCPY2(&dword_1003B554[99], L"Print_Area", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[115] + 1, L"Print_Titles", 0x21u);
  WCSCPY2(&dword_1003B554[132], L"Recorder", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[148] + 1, L"Data_Form", 0x21u);
  WCSCPY2(&dword_1003B554[165], L"Auto_Activate", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B554[181] + 1, L"Auto_Deactivate", 0x21u);
  WCSCPY2(&dword_1003B554[198], L"Sheet_Title", 0x21u);
  WCSCPY2(WorkbookLocalizedInfo, L"TRUE", 0x21u);
  WCSCPY2(&word_1003B302, L"FALSE", 0x21u);
  word_1003B8AE = 82;
  word_1003B8B0 = 67;
  WCSCPY2(dword_1003B344, L"#NULL!", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B344[16] + 1, L"#DIV/0!", 0x21u);
  WCSCPY2(&dword_1003B344[33], L"#VALUE!", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B344[49] + 1, L"#REF!", 0x21u);
  WCSCPY2(&dword_1003B344[66], L"#NAME?", 0x21u);
  WCSCPY2((_WORD *)&dword_1003B344[82] + 1, L"#NUM!", 0x21u);
  WCSCPY2(&dword_1003B344[99], L"#N/A", 0x21u);
  return 0;
}

```

## disassembly

```asm
0x1001e690  mov     edi, edi
0x1001e692  push    ebp
0x1001e693  mov     ebp, esp
0x1001e695  sub     esp, 0A8h
0x1001e69b  mov     eax, ___security_cookie
0x1001e6a0  xor     eax, ebp
0x1001e6a2  mov     [ebp+var_4], eax
0x1001e6a5  mov     [ebp+var_8C], 0
0x1001e6af  mov     [ebp+hModule], 0
0x1001e6b9  mov     eax, [ebp+arg_0]
0x1001e6bc  mov     [ebp+arg_0], eax
0x1001e6bf  mov     ecx, offset LibFileName; "MSJINT40.DLL"
0x1001e6c4  call    _JetLoadLibraryW@4; JetLoadLibraryW(x)
0x1001e6c9  mov     [ebp+hModule], eax
0x1001e6cf  cmp     [ebp+hModule], 0
0x1001e6d6  jnz     short loc_1001E6DD
0x1001e6d8  jmp     loc_1001E946
0x1001e6dd  push    offset ProcName; "CchLszOfId2"
0x1001e6e2  mov     ecx, [ebp+hModule]
0x1001e6e8  push    ecx; hModule
0x1001e6e9  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x1001e6ef  mov     [ebp+var_8C], eax
0x1001e6f5  cmp     [ebp+var_8C], 0
0x1001e6fc  jnz     short loc_1001E703
0x1001e6fe  jmp     loc_1001E938
0x1001e703  mov     [ebp+var_88], 0
0x1001e70d  jmp     short loc_1001E71E
0x1001e70f  mov     edx, [ebp+var_88]
0x1001e715  add     edx, 1
0x1001e718  mov     [ebp+var_88], edx
0x1001e71e  cmp     [ebp+var_88], 0Ch
0x1001e725  ja      short loc_1001E77E
0x1001e727  push    20h ; ' '
0x1001e729  imul    eax, [ebp+var_88], 42h ; 'B'
0x1001e730  add     eax, offset dword_1003B554
0x1001e735  push    eax
0x1001e736  mov     ecx, [ebp+var_88]
0x1001e73c  add     ecx, 2710h
0x1001e742  push    ecx
0x1001e743  mov     edx, [ebp+var_8C]
0x1001e749  mov     [ebp+var_94], edx
0x1001e74f  mov     ecx, [ebp+var_94]
0x1001e755  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e75b  call    [ebp+var_94]
0x1001e761  imul    ecx, [ebp+var_88], 42h ; 'B'
0x1001e768  add     ecx, offset dword_1003B554
0x1001e76e  call    _WCSLEN@4; WCSLEN(x)
0x1001e773  test    eax, eax
0x1001e775  jnz     short loc_1001E77C
0x1001e777  jmp     loc_1001E938
0x1001e77c  jmp     short loc_1001E70F
0x1001e77e  mov     [ebp+var_88], 0
0x1001e788  jmp     short loc_1001E799
0x1001e78a  mov     eax, [ebp+var_88]
0x1001e790  add     eax, 1
0x1001e793  mov     [ebp+var_88], eax
0x1001e799  cmp     [ebp+var_88], 6
0x1001e7a0  ja      short loc_1001E7FA
0x1001e7a2  push    20h ; ' '
0x1001e7a4  imul    ecx, [ebp+var_88], 42h ; 'B'
0x1001e7ab  add     ecx, offset dword_1003B344
0x1001e7b1  push    ecx
0x1001e7b2  mov     edx, [ebp+var_88]
0x1001e7b8  add     edx, 271Dh
0x1001e7be  push    edx
0x1001e7bf  mov     eax, [ebp+var_8C]
0x1001e7c5  mov     [ebp+var_98], eax
0x1001e7cb  mov     ecx, [ebp+var_98]
0x1001e7d1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e7d7  call    [ebp+var_98]
0x1001e7dd  imul    ecx, [ebp+var_88], 42h ; 'B'
0x1001e7e4  add     ecx, offset dword_1003B344
0x1001e7ea  call    _WCSLEN@4; WCSLEN(x)
0x1001e7ef  test    eax, eax
0x1001e7f1  jnz     short loc_1001E7F8
0x1001e7f3  jmp     loc_1001E938
0x1001e7f8  jmp     short loc_1001E78A
0x1001e7fa  push    20h ; ' '
0x1001e7fc  push    offset _WorkbookLocalizedInfo
0x1001e801  push    2724h
0x1001e806  mov     ecx, [ebp+var_8C]
0x1001e80c  mov     [ebp+var_9C], ecx
0x1001e812  mov     ecx, [ebp+var_9C]
0x1001e818  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e81e  call    [ebp+var_9C]
0x1001e824  mov     ecx, offset _WorkbookLocalizedInfo
0x1001e829  call    _WCSLEN@4; WCSLEN(x)
0x1001e82e  test    eax, eax
0x1001e830  jnz     short loc_1001E837
0x1001e832  jmp     loc_1001E938
0x1001e837  push    20h ; ' '
0x1001e839  push    offset word_1003B302
0x1001e83e  push    2725h
0x1001e843  mov     edx, [ebp+var_8C]
0x1001e849  mov     [ebp+var_A0], edx
0x1001e84f  mov     ecx, [ebp+var_A0]
0x1001e855  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e85b  call    [ebp+var_A0]
0x1001e861  mov     ecx, offset word_1003B302
0x1001e866  call    _WCSLEN@4; WCSLEN(x)
0x1001e86b  test    eax, eax
0x1001e86d  jnz     short loc_1001E874
0x1001e86f  jmp     loc_1001E938
0x1001e874  push    80h
0x1001e879  lea     eax, [ebp+var_84]
0x1001e87f  push    eax
0x1001e880  push    2772h
0x1001e885  mov     ecx, [ebp+var_8C]
0x1001e88b  mov     [ebp+var_A4], ecx
0x1001e891  mov     ecx, [ebp+var_A4]
0x1001e897  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e89d  call    [ebp+var_A4]
0x1001e8a3  lea     ecx, [ebp+var_84]
0x1001e8a9  call    _WCSLEN@4; WCSLEN(x)
0x1001e8ae  test    eax, eax
0x1001e8b0  jnz     short loc_1001E8B7
0x1001e8b2  jmp     loc_1001E938
0x1001e8b7  mov     edx, 2
0x1001e8bc  imul    eax, edx, 0
0x1001e8bf  mov     cx, [ebp+eax+var_84]
0x1001e8c7  mov     word_1003B8AE, cx
0x1001e8ce  push    80h
0x1001e8d3  lea     edx, [ebp+var_84]
0x1001e8d9  push    edx
0x1001e8da  push    2773h
0x1001e8df  mov     eax, [ebp+var_8C]
0x1001e8e5  mov     [ebp+var_A8], eax
0x1001e8eb  mov     ecx, [ebp+var_A8]
0x1001e8f1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1001e8f7  call    [ebp+var_A8]
0x1001e8fd  lea     ecx, [ebp+var_84]
0x1001e903  call    _WCSLEN@4; WCSLEN(x)
0x1001e908  test    eax, eax
0x1001e90a  jnz     short loc_1001E90E
0x1001e90c  jmp     short loc_1001E938
0x1001e90e  mov     ecx, 2
0x1001e913  imul    edx, ecx, 0
0x1001e916  mov     ax, [ebp+edx+var_84]
0x1001e91e  mov     word_1003B8B0, ax
0x1001e924  mov     ecx, [ebp+hModule]
0x1001e92a  push    ecx; hLibModule
0x1001e92b  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001e931  xor     eax, eax
0x1001e933  jmp     loc_1001EB87
0x1001e938  mov     edx, [ebp+hModule]
0x1001e93e  push    edx; hLibModule
0x1001e93f  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x1001e945  nop
0x1001e946  push    21h ; '!'
0x1001e948  mov     eax, 42h ; 'B'
0x1001e94d  imul    ecx, eax, 0
0x1001e950  add     ecx, offset dword_1003B554
0x1001e956  mov     edx, offset aConsolidateAre; "Consolidate_Area"
0x1001e95b  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e960  push    21h ; '!'
0x1001e962  mov     ecx, 42h ; 'B'
0x1001e967  shl     ecx, 0
0x1001e96a  add     ecx, offset dword_1003B554
0x1001e970  mov     edx, offset aAutoOpen; "Auto_Open"
0x1001e975  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e97a  push    21h ; '!'
0x1001e97c  mov     ecx, 42h ; 'B'
0x1001e981  shl     ecx, 1
0x1001e983  add     ecx, offset dword_1003B554
0x1001e989  mov     edx, offset aAutoClose; "Auto_Close"
0x1001e98e  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e993  push    21h ; '!'
0x1001e995  mov     ecx, 42h ; 'B'
0x1001e99a  imul    ecx, 3
0x1001e99d  add     ecx, offset dword_1003B554
0x1001e9a3  mov     edx, offset aExtract; "Extract"
0x1001e9a8  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e9ad  push    21h ; '!'
0x1001e9af  mov     ecx, 42h ; 'B'
0x1001e9b4  shl     ecx, 2
0x1001e9b7  add     ecx, offset dword_1003B554
0x1001e9bd  mov     edx, offset aDatabase; "Database"
0x1001e9c2  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e9c7  push    21h ; '!'
0x1001e9c9  mov     edx, 42h ; 'B'
0x1001e9ce  imul    ecx, edx, 5
0x1001e9d1  add     ecx, offset dword_1003B554
0x1001e9d7  mov     edx, offset aCriteria; "Criteria"
0x1001e9dc  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e9e1  push    21h ; '!'
0x1001e9e3  mov     eax, 42h ; 'B'
0x1001e9e8  imul    ecx, eax, 6
0x1001e9eb  add     ecx, offset dword_1003B554
0x1001e9f1  mov     edx, offset aPrintArea; "Print_Area"
0x1001e9f6  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001e9fb  push    21h ; '!'
0x1001e9fd  mov     ecx, 42h ; 'B'
0x1001ea02  imul    ecx, 7
0x1001ea05  add     ecx, offset dword_1003B554
0x1001ea0b  mov     edx, offset aPrintTitles; "Print_Titles"
0x1001ea10  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea15  push    21h ; '!'
0x1001ea17  mov     ecx, 42h ; 'B'
0x1001ea1c  shl     ecx, 3
0x1001ea1f  add     ecx, offset dword_1003B554
0x1001ea25  mov     edx, offset aRecorder; "Recorder"
0x1001ea2a  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea2f  push    21h ; '!'
0x1001ea31  mov     edx, 42h ; 'B'
0x1001ea36  imul    ecx, edx, 9
0x1001ea39  add     ecx, offset dword_1003B554
0x1001ea3f  mov     edx, offset aDataForm; "Data_Form"
0x1001ea44  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea49  push    21h ; '!'
0x1001ea4b  mov     eax, 42h ; 'B'
0x1001ea50  imul    ecx, eax, 0Ah
0x1001ea53  add     ecx, offset dword_1003B554
0x1001ea59  mov     edx, offset aAutoActivate; "Auto_Activate"
0x1001ea5e  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea63  push    21h ; '!'
0x1001ea65  mov     ecx, 42h ; 'B'
0x1001ea6a  imul    ecx, 0Bh
0x1001ea6d  add     ecx, offset dword_1003B554
0x1001ea73  mov     edx, offset aAutoDeactivate; "Auto_Deactivate"
0x1001ea78  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea7d  push    21h ; '!'
0x1001ea7f  mov     edx, 42h ; 'B'
0x1001ea84  imul    ecx, edx, 0Ch
0x1001ea87  add     ecx, offset dword_1003B554
0x1001ea8d  mov     edx, offset aSheetTitle; "Sheet_Title"
0x1001ea92  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001ea97  push    21h ; '!'
0x1001ea99  mov     edx, offset aTrue; "TRUE"
0x1001ea9e  mov     ecx, offset _WorkbookLocalizedInfo
0x1001eaa3  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eaa8  push    21h ; '!'
0x1001eaaa  mov     edx, offset aFalse; "FALSE"
0x1001eaaf  mov     ecx, offset word_1003B302
0x1001eab4  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eab9  mov     eax, 52h ; 'R'
0x1001eabe  mov     word_1003B8AE, ax
0x1001eac4  mov     ecx, 43h ; 'C'
0x1001eac9  mov     word_1003B8B0, cx
0x1001ead0  push    21h ; '!'
0x1001ead2  mov     edx, 42h ; 'B'
0x1001ead7  imul    ecx, edx, 0
0x1001eada  add     ecx, offset dword_1003B344
0x1001eae0  mov     edx, offset aNull; "#NULL!"
0x1001eae5  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eaea  push    21h ; '!'
0x1001eaec  mov     ecx, 42h ; 'B'
0x1001eaf1  shl     ecx, 0
0x1001eaf4  add     ecx, offset dword_1003B344
0x1001eafa  mov     edx, offset aDiv0; "#DIV/0!"
0x1001eaff  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb04  push    21h ; '!'
0x1001eb06  mov     ecx, 42h ; 'B'
0x1001eb0b  shl     ecx, 1
0x1001eb0d  add     ecx, offset dword_1003B344
0x1001eb13  mov     edx, offset aValue; "#VALUE!"
0x1001eb18  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb1d  push    21h ; '!'
0x1001eb1f  mov     eax, 42h ; 'B'
0x1001eb24  imul    ecx, eax, 3
0x1001eb27  add     ecx, offset dword_1003B344
0x1001eb2d  mov     edx, offset aRef; "#REF!"
0x1001eb32  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb37  push    21h ; '!'
0x1001eb39  mov     ecx, 42h ; 'B'
0x1001eb3e  shl     ecx, 2
0x1001eb41  add     ecx, offset dword_1003B344
0x1001eb47  mov     edx, offset aName; "#NAME?"
0x1001eb4c  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb51  push    21h ; '!'
0x1001eb53  mov     ecx, 42h ; 'B'
0x1001eb58  imul    ecx, 5
0x1001eb5b  add     ecx, offset dword_1003B344
0x1001eb61  mov     edx, offset aNum; "#NUM!"
0x1001eb66  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb6b  push    21h ; '!'
0x1001eb6d  mov     edx, 42h ; 'B'
0x1001eb72  imul    ecx, edx, 6
0x1001eb75  add     ecx, offset dword_1003B344
0x1001eb7b  mov     edx, offset aNA; "#N/A"
0x1001eb80  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1001eb85  xor     eax, eax
0x1001eb87  mov     ecx, [ebp+var_4]
0x1001eb8a  xor     ecx, ebp; StackCookie
0x1001eb8c  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1001eb91  mov     esp, ebp
0x1001eb93  pop     ebp
0x1001eb94  retn    4
```
