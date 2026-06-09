# CSystemWriter::AddCoreCsiFiles(IVssCreateWriterMetadata *,void *)

- ea: `0x1800056f0`
- end: `0x180005b23`
- name: `?AddCoreCsiFiles@CSystemWriter@@AEAA_NPEAVIVssCreateWriterMetadata@@PEAX@Z`
- size: `1075`
- prototype: `bool __fastcall(CSystemWriter *__hidden this, struct IVssCreateWriterMetadata *, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e1d4`

## callees

- `0x1800056f0`
- `0x180005b30`
- `0x180005fc0`
- `0x180006e54`
- `0x18000be40`
- `0x18001fcc8`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057f2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057b2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057ce`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800057f2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005b0a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005b0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000599f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000599f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a6a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000578e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000578e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005a4f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b18`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005a3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005b18`

## string_xrefs

- `0x1800058ec`: `SystemShutdown initiated during AddCoreCsiFiles`
- `0x180005787`: `sfc_os.dll`
- `0x180005983`: `AddCoreCsiFiles : LoadLibrary failed on sfc_os.dll.`
- `0x180005aaa`: `AddCoreCsiFiles : RtlConvertNtFilePathToWin32Path() failed.`

## pseudocode

```c
__int64 __fastcall CSystemWriter::AddCoreCsiFiles(CSystemWriter *this, struct IVssCreateWriterMetadata *a2, void *a3)
{
  __int64 (*v4)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...); // rax
  HMODULE v5; // r12
  __int64 v7; // rdi
  _QWORD *v8; // rbx
  void (*v9)(void); // r13
  unsigned int v10; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // r14
  FARPROC v13; // r15
  SIZE_T v14; // r14
  __int64 v15; // rcx
  signed int v16; // eax
  unsigned __int8 v17; // si
  DWORD v19; // eax
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD LastError; // eax
  DWORD v25; // eax
  __int128 v26; // [rsp+50h] [rbp-88h] BYREF
  __int64 v27; // [rsp+60h] [rbp-78h]
  _QWORD v28[3]; // [rsp+68h] [rbp-70h] BYREF
  SIZE_T uBytes; // [rsp+80h] [rbp-58h] BYREF
  __int64 v30; // [rsp+88h] [rbp-50h] BYREF

  v4 = *(__int64 (**)(struct IVssCreateWriterMetadata *, _QWORD, const wchar_t *, const wchar_t *, ...))(*(_QWORD *)a2 + 40LL);
  v5 = 0;
  v26 = 0;
  v7 = 0;
  v30 = 0;
  v8 = 0;
  v27 = 0;
  v9 = 0;
  v10 = v4(a2, 0, L"System Files", L"%systemroot%\\winsxs", L"*.*", 1, 0, 3855);
  if ( v10 )
  {
    CSystemWriter::LogSystemErrorEvent(0x201u, L"AddCoreCsiFiles : AddFilesToFileGroup failed.", v10);
    v17 = 0;
  }
  else
  {
    LibraryW = LoadLibraryW(L"sfc_os.dll");
    v5 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "BeginFileMapEnumeration");
      if ( ProcAddress )
      {
        v9 = (void (*)(void))GetProcAddress(v5, "CloseFileMapEnumeration");
        if ( v9 )
        {
          v13 = GetProcAddress(v5, "GetNextFileMapContent");
          if ( v13 )
          {
            if ( ((unsigned int (__fastcall *)(_QWORD, _QWORD, __int64 *))ProcAddress)(0, 0, &v30) )
            {
              v14 = 0;
              while ( 1 )
              {
                while ( 1 )
                {
                  v15 = *((_QWORD *)this + 1);
                  uBytes = 0;
                  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 192LL))(v15) )
                  {
                    v17 = 0;
                    CSystemWriter::LogSystemErrorEvent(
                      0x201u,
                      L"SystemShutdown initiated during AddCoreCsiFiles",
                      0x281u);
                    goto LABEL_36;
                  }
                  if ( ((unsigned int (__fastcall *)(_QWORD, __int64, SIZE_T, _QWORD *, SIZE_T *))v13)(
                         0,
                         v30,
                         v14,
                         v8,
                         &uBytes) )
                  {
                    break;
                  }
                  LastError = GetLastError();
                  if ( LastError == 18 )
                  {
                    v17 = 1;
                    goto LABEL_36;
                  }
                  if ( LastError != 122 )
                  {
                    CSystemWriter::LogSystemErrorEvent(
                      0x201u,
                      L"AddCoreCsiFiles : GetNextFileMapContent() failed.",
                      LastError);
                    v17 = 0;
                    goto LABEL_36;
                  }
                  if ( v8 )
                    LocalFree(v8);
                  v8 = LocalAlloc(0, uBytes);
                  if ( !v8 )
                  {
                    v25 = GetLastError();
                    CSystemWriter::LogSystemErrorEvent(0x201u, L"AddCoreCsiFiles : LocalAlloc() failed.", v25);
                    v17 = 0;
                    goto LABEL_36;
                  }
                  v14 = uBytes;
                }
                v28[0] = *v8;
                v28[1] = v28[0];
                v28[2] = v8 + 1;
                v16 = RtlConvertNtFilePathToWin32FilePath(v28, &v26);
                if ( v16 < 0 )
                  break;
                v7 = v27;
                if ( (unsigned int)pSetupStringTableAddString(a3, v27) == -1 )
                {
                  CSystemWriter::LogSystemErrorEvent(
                    0x201u,
                    L"AddCoreCsiFiles : pSetupStringTableAddString() failed.",
                    0xEu);
                  v17 = 0;
                  goto LABEL_36;
                }
              }
              CSystemWriter::LogSystemErrorEvent(
                0x201u,
                L"AddCoreCsiFiles : RtlConvertNtFilePathToWin32Path() failed.",
                v16);
              v7 = v27;
              v17 = 0;
            }
            else
            {
              v23 = GetLastError();
              CSystemWriter::LogSystemErrorEvent(0x201u, L"AddCoreCsiFiles : BeginFileEnumeration() failed.", v23);
              v17 = 0;
            }
          }
          else
          {
            v22 = GetLastError();
            CSystemWriter::LogSystemErrorEvent(
              0x201u,
              L"AddCoreCsiFiles : GetProcAddress for GetNextFileMapContect failed.",
              v22);
            v17 = 0;
          }
        }
        else
        {
          v21 = GetLastError();
          CSystemWriter::LogSystemErrorEvent(
            0x201u,
            L"AddCoreCsiFiles : GetProcAddress for CloseFileMapEnumeration failed.",
            v21);
          v17 = 0;
        }
      }
      else
      {
        v20 = GetLastError();
        CSystemWriter::LogSystemErrorEvent(
          0x201u,
          L"AddCoreCsiFiles : GetProcAddress for BeginFileMapEnumeration failed.",
          v20);
        v17 = 0;
      }
    }
    else
    {
      v19 = GetLastError();
      CSystemWriter::LogSystemErrorEvent(0x201u, L"AddCoreCsiFiles : LoadLibrary failed on sfc_os.dll.", v19);
      v17 = 0;
    }
  }
LABEL_36:
  if ( v7 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v7);
  if ( v30 && v9 )
    v9();
  if ( v5 )
    FreeLibrary(v5);
  if ( v8 )
    LocalFree(v8);
  return v17;
}

```

## disassembly

```asm
0x1800056f0  mov     r11, rsp
0x1800056f3  push    rbx
0x1800056f4  push    rsi
0x1800056f5  sub     rsp, 0C8h
0x1800056fc  mov     rax, cs:__security_cookie
0x180005703  xor     rax, rsp
0x180005706  mov     [rsp+0D8h+var_48], rax
0x18000570e  mov     rax, [rdx]
0x180005711  lea     r9, aSystemrootWins; "%systemroot%\\winsxs"
0x180005718  mov     [r11+20h], rbp
0x18000571c  mov     r10, rdx
0x18000571f  mov     [r11-18h], rdi
0x180005723  mov     rbp, rcx
0x180005726  mov     [r11-20h], r12
0x18000572a  lea     rcx, asc_180024ED8; "*.*"
0x180005731  mov     rax, [rax+28h]
0x180005735  xor     r12d, r12d
0x180005738  mov     [rsp+0D8h+var_A0], 0F0Fh
0x180005740  xorps   xmm0, xmm0
0x180005743  mov     [rsp+0D8h+var_A8], r12
0x180005748  mov     rsi, r8
0x18000574b  mov     [r11-28h], r13
0x18000574f  lea     r8, aSystemFiles; "System Files"
0x180005756  movups  [rsp+0D8h+var_88], xmm0
0x18000575b  mov     [rsp+0D8h+var_B0], 1
0x180005760  xor     edi, edi
0x180005762  mov     [rsp+0D8h+var_B8], rcx
0x180005767  xor     edx, edx
0x180005769  mov     rcx, r10
0x18000576c  mov     [r11-50h], r12
0x180005770  mov     ebx, r12d
0x180005773  mov     [r11-78h], rdi
0x180005777  mov     r13d, r12d
0x18000577a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577f  test    eax, eax
0x180005781  jnz     loc_180005961
0x180005787  lea     rcx, LibFileName; "sfc_os.dll"
0x18000578e  call    cs:__imp_LoadLibraryW
0x180005794  mov     r12, rax
0x180005797  test    rax, rax
0x18000579a  jz      loc_18000597D
0x1800057a0  lea     rdx, ProcName; "BeginFileMapEnumeration"
0x1800057a7  mov     [rsp+0D8h+var_30], r14
0x1800057af  mov     rcx, rax; hModule
0x1800057b2  call    cs:__imp_GetProcAddress
0x1800057b8  mov     r14, rax
0x1800057bb  test    rax, rax
0x1800057be  jz      loc_18000599F
0x1800057c4  lea     rdx, aClosefilemapen; "CloseFileMapEnumeration"
0x1800057cb  mov     rcx, r12; hModule
0x1800057ce  call    cs:__imp_GetProcAddress
0x1800057d4  mov     r13, rax
0x1800057d7  test    rax, rax
0x1800057da  jz      loc_1800059C1
0x1800057e0  lea     rdx, aGetnextfilemap; "GetNextFileMapContent"
0x1800057e7  mov     [rsp+0D8h+var_38], r15
0x1800057ef  mov     rcx, r12; hModule
0x1800057f2  call    cs:__imp_GetProcAddress
0x1800057f8  mov     r15, rax
0x1800057fb  test    rax, rax
0x1800057fe  jz      loc_1800059E3
0x180005804  lea     r8, [rsp+0D8h+var_50]
0x18000580c  xor     edx, edx
0x18000580e  xor     ecx, ecx
0x180005810  mov     rax, r14
0x180005813  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005818  test    eax, eax
0x18000581a  jz      loc_180005A05
0x180005820  xor     r14d, r14d
0x180005823  nop     dword ptr [rax+00h]
0x180005827  nop     word ptr [rax+rax+00000000h]
0x180005830  mov     rcx, [rbp+8]
0x180005834  mov     [rsp+0D8h+uBytes], 0
0x180005840  mov     rax, [rcx]
0x180005843  mov     rax, [rax+0C0h]
0x18000584a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000584f  test    al, al
0x180005851  jnz     loc_1800058E9
0x180005857  mov     rdx, [rsp+0D8h+var_50]
0x18000585f  lea     rax, [rsp+0D8h+uBytes]
0x180005867  mov     [rsp+0D8h+var_B8], rax
0x18000586c  mov     r9, rbx
0x18000586f  mov     rax, r15
0x180005872  mov     r8, r14
0x180005875  xor     ecx, ecx
0x180005877  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587c  test    eax, eax
0x18000587e  jz      loc_180005A27
0x180005884  mov     rax, [rbx]
0x180005887  lea     rdx, [rsp+0D8h+var_88]
0x18000588c  mov     [rsp+0D8h+var_70], rax
0x180005891  lea     rcx, [rsp+0D8h+var_70]
0x180005896  mov     [rsp+0D8h+var_68], rax
0x18000589b  lea     rax, [rbx+8]
0x18000589f  mov     [rsp+0D8h+var_60], rax
0x1800058a4  call    RtlConvertNtFilePathToWin32FilePath
0x1800058a9  test    eax, eax
0x1800058ab  js      loc_180005AA7
0x1800058b1  mov     rdi, [rsp+0D8h+var_78]
0x1800058b6  mov     rcx, rsi
0x1800058b9  mov     rdx, rdi
0x1800058bc  call    pSetupStringTableAddString
0x1800058c1  cmp     eax, 0FFFFFFFFh
0x1800058c4  jnz     loc_180005830
0x1800058ca  mov     r8d, 0Eh; unsigned int
0x1800058d0  lea     rdx, aAddcorecsifile; "AddCoreCsiFiles : pSetupStringTableAddS"...
0x1800058d7  mov     ecx, 201h; unsigned int
0x1800058dc  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800058e1  xor     sil, sil
0x1800058e4  jmp     loc_180005AC3
0x1800058e9  xor     sil, sil
0x1800058ec  lea     rdx, aSystemshutdown_0; "SystemShutdown initiated during AddCore"...
0x1800058f3  mov     r8d, 281h; unsigned int
0x1800058f9  mov     ecx, 201h; unsigned int
0x1800058fe  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005903  jmp     loc_180005AC3
0x180005908  mov     rcx, [rsp+0D8h+var_50]
0x180005910  mov     rdi, [rsp+0D8h+var_18]
0x180005918  test    rcx, rcx
0x18000591b  jnz     loc_180005AF1
0x180005921  mov     r13, [rsp+0D8h+var_28]
0x180005929  test    r12, r12
0x18000592c  jnz     loc_180005B07
0x180005932  mov     r12, [rsp+0D8h+var_20]
0x18000593a  test    rbx, rbx
0x18000593d  jnz     loc_180005B15
0x180005943  movzx   eax, sil
0x180005947  mov     rcx, [rsp+0D8h+var_48]
0x18000594f  xor     rcx, rsp; StackCookie
0x180005952  call    __security_check_cookie
0x180005957  add     rsp, 0C8h
0x18000595e  pop     rsi
0x18000595f  pop     rbx
0x180005960  retn
0x180005961  mov     r8d, eax; unsigned int
0x180005964  lea     rdx, aAddcorecsifile_7; "AddCoreCsiFiles : AddFilesToFileGroup f"...
0x18000596b  mov     ecx, 201h; unsigned int
0x180005970  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005975  xor     sil, sil
0x180005978  jmp     loc_180005AD3
0x18000597d  call    cs:__imp_GetLastError
0x180005983  lea     rdx, aAddcorecsifile_5; "AddCoreCsiFiles : LoadLibrary failed on"...
0x18000598a  mov     ecx, 201h; unsigned int
0x18000598f  mov     r8d, eax; unsigned int
0x180005992  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005997  xor     sil, sil
0x18000599a  jmp     loc_180005AD3
0x18000599f  call    cs:__imp_GetLastError
0x1800059a5  lea     rdx, aAddcorecsifile_3; "AddCoreCsiFiles : GetProcAddress for Be"...
0x1800059ac  mov     ecx, 201h; unsigned int
0x1800059b1  mov     r8d, eax; unsigned int
0x1800059b4  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800059b9  xor     sil, sil
0x1800059bc  jmp     loc_180005ACB
0x1800059c1  call    cs:__imp_GetLastError
0x1800059c7  lea     rdx, aAddcorecsifile_8; "AddCoreCsiFiles : GetProcAddress for Cl"...
0x1800059ce  mov     ecx, 201h; unsigned int
0x1800059d3  mov     r8d, eax; unsigned int
0x1800059d6  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800059db  xor     sil, sil
0x1800059de  jmp     loc_180005ACB
0x1800059e3  call    cs:__imp_GetLastError
0x1800059e9  lea     rdx, aAddcorecsifile_4; "AddCoreCsiFiles : GetProcAddress for Ge"...
0x1800059f0  mov     ecx, 201h; unsigned int
0x1800059f5  mov     r8d, eax; unsigned int
0x1800059f8  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x1800059fd  xor     sil, sil
0x180005a00  jmp     loc_180005AC3
0x180005a05  call    cs:__imp_GetLastError
0x180005a0b  lea     rdx, aAddcorecsifile_2; "AddCoreCsiFiles : BeginFileEnumeration("...
0x180005a12  mov     ecx, 201h; unsigned int
0x180005a17  mov     r8d, eax; unsigned int
0x180005a1a  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005a1f  xor     sil, sil
0x180005a22  jmp     loc_180005AC3
0x180005a27  call    cs:__imp_GetLastError
0x180005a2d  cmp     eax, 12h
0x180005a30  jz      short loc_180005AA2
0x180005a32  cmp     eax, 7Ah ; 'z'
0x180005a35  jnz     short loc_180005A89
0x180005a37  test    rbx, rbx
0x180005a3a  jz      short loc_180005A45
0x180005a3c  mov     rcx, rbx; hMem
0x180005a3f  call    cs:__imp_LocalFree
0x180005a45  mov     rdx, [rsp+0D8h+uBytes]; uBytes
0x180005a4d  xor     ecx, ecx; uFlags
0x180005a4f  call    cs:__imp_LocalAlloc
0x180005a55  mov     rbx, rax
0x180005a58  test    rax, rax
0x180005a5b  jz      short loc_180005A6A
0x180005a5d  mov     r14, [rsp+0D8h+uBytes]
0x180005a65  jmp     loc_180005830
0x180005a6a  call    cs:__imp_GetLastError
0x180005a70  lea     rdx, aAddcorecsifile_1; "AddCoreCsiFiles : LocalAlloc() failed."
0x180005a77  mov     ecx, 201h; unsigned int
0x180005a7c  mov     r8d, eax; unsigned int
0x180005a7f  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005a84  xor     sil, sil
0x180005a87  jmp     short loc_180005AC3
0x180005a89  mov     r8d, eax; unsigned int
0x180005a8c  lea     rdx, aAddcorecsifile_0; "AddCoreCsiFiles : GetNextFileMapContent"...
0x180005a93  mov     ecx, 201h; unsigned int
0x180005a98  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005a9d  xor     sil, sil
0x180005aa0  jmp     short loc_180005AC3
0x180005aa2  mov     sil, 1
0x180005aa5  jmp     short loc_180005AC3
0x180005aa7  mov     r8d, eax; unsigned int
0x180005aaa  lea     rdx, aAddcorecsifile_6; "AddCoreCsiFiles : RtlConvertNtFilePathT"...
0x180005ab1  mov     ecx, 201h; unsigned int
0x180005ab6  call    ?LogSystemErrorEvent@CSystemWriter@@CAXKPEBGK@Z; CSystemWriter::LogSystemErrorEvent(ulong,ushort const *,ulong)
0x180005abb  mov     rdi, [rsp+0D8h+var_78]
0x180005ac0  xor     sil, sil
0x180005ac3  mov     r15, [rsp+0D8h+var_38]
0x180005acb  mov     r14, [rsp+0D8h+var_30]
0x180005ad3  mov     rbp, [rsp+0D8h+arg_18]
0x180005adb  test    rdi, rdi
0x180005ade  jz      loc_180005908
0x180005ae4  mov     rcx, rdi
0x180005ae7  call    _anonymous_namespace___OurRtlFreeStringRoutine
0x180005aec  jmp     loc_180005908
0x180005af1  test    r13, r13
0x180005af4  jz      loc_180005921
0x180005afa  mov     rax, r13
0x180005afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b02  jmp     loc_180005921
0x180005b07  mov     rcx, r12; hLibModule
0x180005b0a  call    cs:__imp_FreeLibrary
0x180005b10  jmp     loc_180005932
0x180005b15  mov     rcx, rbx; hMem
0x180005b18  call    cs:__imp_LocalFree
0x180005b1e  jmp     loc_180005943
```
