# PopulatePackagePaths(_FILELIST_CALLBACK_CONTEXT *)

- ea: `0x18003325c`
- end: `0x180033392`
- name: `?PopulatePackagePaths@@YAJPEAU_FILELIST_CALLBACK_CONTEXT@@@Z`
- size: `310`
- prototype: `__int64 __fastcall(struct _FILELIST_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180033398`

## callees

- `0x1800078f0`
- `0x18000b200`
- `0x18000d57c`
- `0x18001c914`
- `0x18003325c`

## import_xrefs

- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180033293`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800332e6`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x180033293`
- `SETUPAPI!SetupGetInfDriverStoreLocationW` at `0x1800332e6`

## string_xrefs

- `0x1800332ac`: `PopulatePackagePaths`
- `0x1800332ff`: `PopulatePackagePaths`
- `0x180033375`: `PopulatePackagePaths`
- `0x1800332a5`: `Error retrieving path to ntprint package: hr: 0x%x`
- `0x1800332f8`: `Error retrieving path to ntprint4 package: hr: 0x%x`
- `0x180033365`: `Could not determine length of path to ntprint4 package`
- `0x18003336e`: `Could not determine length of path to ntprint package`

## pseudocode

```c
__int64 __fastcall PopulatePackagePaths(WCHAR *a1)
{
  wchar_t *v1; // rsi
  NCoreLibrary *v3; // rcx
  __int64 LastErrorAsFailHR; // rbx
  wchar_t *v5; // rdi
  NCoreLibrary *v6; // rcx
  _WORD *v7; // rax
  _WORD *v8; // rax
  unsigned __int16 *v9; // rdx

  v1 = a1 + 576;
  if ( SetupGetInfDriverStoreLocationW(L"ntprint.inf", 0, 0, a1 + 576, 0x104u, 0)
    || (LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v3),
        ClassInstallerTelemetry::WriteDbgTraceError(
          "PopulatePackagePaths",
          L"Error retrieving path to ntprint package: hr: 0x%x",
          LastErrorAsFailHR),
        (int)LastErrorAsFailHR >= 0) )
  {
    v5 = a1 + 836;
    if ( SetupGetInfDriverStoreLocationW(L"ntprint4.inf", 0, 0, v5, 0x104u, 0)
      || (LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v6),
          ClassInstallerTelemetry::WriteDbgTraceError(
            "PopulatePackagePaths",
            L"Error retrieving path to ntprint4 package: hr: 0x%x",
            LastErrorAsFailHR),
          (int)LastErrorAsFailHR >= 0) )
    {
      v7 = (_WORD *)FileNamePart(v1);
      if ( v7 )
      {
        *v7 = 0;
        v8 = (_WORD *)FileNamePart(v5);
        if ( v8 )
        {
          *v8 = 0;
          LODWORD(LastErrorAsFailHR) = StringCchCatW(v1, 0x104u, L"Amd64\\");
          if ( (int)LastErrorAsFailHR >= 0 )
            LODWORD(LastErrorAsFailHR) = StringCchCatW(v5, 0x104u, L"Amd64\\");
          return (unsigned int)LastErrorAsFailHR;
        }
        v9 = L"Could not determine length of path to ntprint4 package";
      }
      else
      {
        v9 = L"Could not determine length of path to ntprint package";
      }
      LODWORD(LastErrorAsFailHR) = -2147418113;
      ClassInstallerTelemetry::WriteDbgTraceError("PopulatePackagePaths", v9);
    }
  }
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x18003325c  push    rbx
0x18003325e  push    rsi
0x18003325f  push    rdi
0x180033260  push    r14
0x180033262  sub     rsp, 38h
0x180033266  lea     rsi, [rcx+480h]
0x18003326d  mov     [rsp+58h+RequiredSize], 0; RequiredSize
0x180033276  mov     rdi, rcx
0x180033279  mov     r14d, 104h
0x18003327f  mov     r9, rsi; ReturnBuffer
0x180033282  mov     [rsp+58h+ReturnBufferSize], r14d; ReturnBufferSize
0x180033287  xor     r8d, r8d; LocaleName
0x18003328a  lea     rcx, FileName; "ntprint.inf"
0x180033291  xor     edx, edx; AlternatePlatformInfo
0x180033293  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x180033299  test    eax, eax
0x18003329b  jnz     short loc_1800332C2
0x18003329d  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800332a2  mov     r8d, eax
0x1800332a5  lea     rdx, aErrorRetrievin_13; "Error retrieving path to ntprint packag"...
0x1800332ac  lea     rcx, aPopulatepackag; "PopulatePackagePaths"
0x1800332b3  mov     ebx, eax
0x1800332b5  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800332ba  test    ebx, ebx
0x1800332bc  js      loc_180033386
0x1800332c2  add     rdi, 688h
0x1800332c9  mov     [rsp+58h+RequiredSize], 0; RequiredSize
0x1800332d2  mov     r9, rdi; ReturnBuffer
0x1800332d5  mov     [rsp+58h+ReturnBufferSize], r14d; ReturnBufferSize
0x1800332da  xor     r8d, r8d; LocaleName
0x1800332dd  lea     rcx, aNtprint4Inf; "ntprint4.inf"
0x1800332e4  xor     edx, edx; AlternatePlatformInfo
0x1800332e6  call    cs:__imp_SetupGetInfDriverStoreLocationW
0x1800332ec  test    eax, eax
0x1800332ee  jnz     short loc_180033311
0x1800332f0  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800332f5  mov     r8d, eax
0x1800332f8  lea     rdx, aErrorRetrievin_11; "Error retrieving path to ntprint4 packa"...
0x1800332ff  lea     rcx, aPopulatepackag; "PopulatePackagePaths"
0x180033306  mov     ebx, eax
0x180033308  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003330d  test    ebx, ebx
0x18003330f  js      short loc_180033386
0x180033311  mov     rcx, rsi; Str
0x180033314  call    FileNamePart
0x180033319  test    rax, rax
0x18003331c  jz      short loc_18003336E
0x18003331e  xor     edx, edx
0x180033320  mov     rcx, rdi; Str
0x180033323  mov     [rax], dx
0x180033326  call    FileNamePart
0x18003332b  test    rax, rax
0x18003332e  jz      short loc_180033365
0x180033330  xor     r8d, r8d
0x180033333  mov     rdx, r14; unsigned __int64
0x180033336  mov     [rax], r8w
0x18003333a  mov     rcx, rsi; unsigned __int16 *
0x18003333d  lea     r8, aAmd64_3; "Amd64\\"
0x180033344  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033349  mov     ebx, eax
0x18003334b  test    eax, eax
0x18003334d  js      short loc_180033386
0x18003334f  lea     r8, aAmd64_3; "Amd64\\"
0x180033356  mov     rdx, r14; unsigned __int64
0x180033359  mov     rcx, rdi; unsigned __int16 *
0x18003335c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180033361  mov     ebx, eax
0x180033363  jmp     short loc_180033386
0x180033365  lea     rdx, aCouldNotDeterm; "Could not determine length of path to n"...
0x18003336c  jmp     short loc_180033375
0x18003336e  lea     rdx, aCouldNotDeterm_0; "Could not determine length of path to n"...
0x180033375  lea     rcx, aPopulatepackag; "PopulatePackagePaths"
0x18003337c  mov     ebx, 8000FFFFh
0x180033381  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180033386  mov     eax, ebx
0x180033388  add     rsp, 38h
0x18003338c  pop     r14
0x18003338e  pop     rdi
0x18003338f  pop     rsi
0x180033390  pop     rbx
0x180033391  retn
```
