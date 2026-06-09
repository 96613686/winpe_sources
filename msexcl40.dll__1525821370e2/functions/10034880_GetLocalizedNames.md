# GetLocalizedNames

- ea: `0x10034880`
- end: `0x10034b16`
- name: `GetLocalizedNames`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10034c94`

## callees

- `0x10006400`
- `0x10032d47`
- `0x10034880`
- `0x10035b40`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100348a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10034b0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100348a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x10034b0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1003499a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1003499a`

## string_xrefs

- `0x10034891`: `MSJINT40.DLL`

## pseudocode

```c
int __thiscall GetLocalizedNames(_WORD *this)
{
  HMODULE Library; // eax
  FARPROC CchLszOfId2; // eax
  void (__thiscall *v5)(_DWORD, _DWORD, _DWORD, _DWORD); // esi
  _WORD *v6; // edi
  _WORD *v8; // edi
  _WORD *v10; // edi
  _WORD *v12; // edi
  _WORD *v14; // edi
  int v16; // eax
  _WORD *v17; // ecx
  _WORD *v18; // edi
  _WORD *v19; // ecx
  HMODULE hLibModule; // [esp+10h] [ebp-8h]
  int v22; // [esp+14h] [ebp-4h]

  Library = JetLoadLibraryExW(L"MSJINT40.DLL", 0, 0);
  hLibModule = Library;
  if ( Library )
  {
    CchLszOfId2 = GetProcAddress(Library, "CchLszOfId2");
    v5 = (void (__thiscall *)(_DWORD, _DWORD, _DWORD, _DWORD))CchLszOfId2;
    if ( CchLszOfId2 )
    {
      v6 = this + 79;
      ((void (__thiscall *)(FARPROC, int, _WORD *, int))CchLszOfId2)(CchLszOfId2, 10060, this + 79, 130);
      while ( *v6++ )
        ;
      if ( v6 - (this + 80) )
      {
        v8 = this + 144;
        v5(v5, 10061, this + 144, 130);
        while ( *v8++ )
          ;
        if ( v8 - (this + 145) )
        {
          v10 = this + 209;
          v5(v5, 10062, this + 209, 130);
          while ( *v10++ )
            ;
          if ( v10 - (this + 210) )
          {
            v12 = this + 274;
            v5(v5, 10063, this + 274, 130);
            while ( *v12++ )
              ;
            if ( v12 - (this + 275) )
            {
              v14 = this + 339;
              v5(v5, 10064, this + 339, 130);
              while ( *v14++ )
                ;
              if ( v14 - (this + 340) )
              {
                v16 = 0;
                v17 = this + 404;
                v22 = 0;
                while ( 1 )
                {
                  v18 = &v17[65 * v16];
                  v5(v5, v16 + 10065, v18, 130);
                  v19 = v18 + 1;
                  while ( *v18++ )
                    ;
                  if ( !(v18 - v19) )
                    break;
                  v17 = this + 404;
                  v16 = v22 + 1;
                  v22 = v16;
                  if ( v16 > 7 )
                  {
                    FreeLibrary(hLibModule);
                    return 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    FreeLibrary(0);
  }
  WCSCPY2(this + 79, L"ImportErrors", 0x41u);
  WCSCPY2(this + 144, L"ExportErrors", 0x41u);
  WCSCPY2(this + 209, L"Error", 0x41u);
  WCSCPY2(this + 274, L"Field", 0x41u);
  WCSCPY2(this + 339, L"Row", 0x41u);
  WCSCPY2(this + 404, L"Unparsable Record", 0x41u);
  WCSCPY2(this + 469, L"Type Conversion Failure", 0x41u);
  WCSCPY2(this + 534, L"Row Truncation", 0x41u);
  WCSCPY2(this + 599, L"Field Truncation", 0x41u);
  WCSCPY2(this + 664, L"Date Out Of Range", 0x41u);
  WCSCPY2(this + 729, L"Rows dropped due to worksheet row limit", 0x41u);
  WCSCPY2(this + 794, L"Validation rule violation", 0x41u);
  WCSCPY2(this + 859, L"Null value in an auto-number field", 0x41u);
  return 0;
}

```

## disassembly

```asm
0x10034880  mov     edi, edi
0x10034882  push    ebp
0x10034883  mov     ebp, esp
0x10034885  sub     esp, 0Ch
0x10034888  push    ebx
0x10034889  push    esi
0x1003488a  push    edi
0x1003488b  xor     esi, esi
0x1003488d  mov     ebx, ecx
0x1003488f  push    esi; int
0x10034890  push    esi; hFile
0x10034891  push    offset LibFileName; "MSJINT40.DLL"
0x10034896  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x1003489b  mov     [ebp+hLibModule], eax
0x1003489e  test    eax, eax
0x100348a0  jnz     loc_10034994
0x100348a6  push    esi; hLibModule
0x100348a7  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100348ad  push    41h ; 'A'
0x100348af  pop     esi
0x100348b0  push    esi
0x100348b1  lea     ecx, [ebx+9Eh]
0x100348b7  mov     edx, offset aImporterrors; "ImportErrors"
0x100348bc  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100348c1  push    esi
0x100348c2  lea     ecx, [ebx+120h]
0x100348c8  mov     edx, offset aExporterrors; "ExportErrors"
0x100348cd  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100348d2  push    esi
0x100348d3  lea     ecx, [ebx+1A2h]
0x100348d9  mov     edx, offset aError; "Error"
0x100348de  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100348e3  push    esi
0x100348e4  lea     ecx, [ebx+224h]
0x100348ea  mov     edx, offset aField; "Field"
0x100348ef  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100348f4  push    esi
0x100348f5  lea     ecx, [ebx+2A6h]
0x100348fb  mov     edx, offset aRow; "Row"
0x10034900  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034905  push    esi
0x10034906  lea     ecx, [ebx+328h]
0x1003490c  mov     edx, offset aUnparsableReco; "Unparsable Record"
0x10034911  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034916  push    esi
0x10034917  lea     ecx, [ebx+3AAh]
0x1003491d  mov     edx, offset aTypeConversion; "Type Conversion Failure"
0x10034922  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034927  push    esi
0x10034928  lea     ecx, [ebx+42Ch]
0x1003492e  mov     edx, offset aRowTruncation; "Row Truncation"
0x10034933  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034938  push    esi
0x10034939  lea     ecx, [ebx+4AEh]
0x1003493f  mov     edx, offset aFieldTruncatio; "Field Truncation"
0x10034944  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10034949  push    esi
0x1003494a  lea     ecx, [ebx+530h]
0x10034950  mov     edx, offset aDateOutOfRange; "Date Out Of Range"
0x10034955  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1003495a  push    esi
0x1003495b  lea     ecx, [ebx+5B2h]
0x10034961  mov     edx, offset aRowsDroppedDue; "Rows dropped due to worksheet row limit"
0x10034966  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1003496b  push    esi
0x1003496c  lea     ecx, [ebx+634h]
0x10034972  mov     edx, offset aValidationRule; "Validation rule violation"
0x10034977  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1003497c  push    esi
0x1003497d  lea     ecx, [ebx+6B6h]
0x10034983  mov     edx, offset aNullValueInAnA; "Null value in an auto-number field"
0x10034988  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1003498d  pop     edi
0x1003498e  pop     esi
0x1003498f  xor     eax, eax
0x10034991  pop     ebx
0x10034992  leave
0x10034993  retn
0x10034994  push    offset ProcName; "CchLszOfId2"
0x10034999  push    eax; hModule
0x1003499a  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100349a0  mov     esi, eax
0x100349a2  test    esi, esi
0x100349a4  jz      loc_100348AD
0x100349aa  push    82h
0x100349af  lea     edi, [ebx+9Eh]
0x100349b5  mov     ecx, esi
0x100349b7  push    edi
0x100349b8  push    274Ch
0x100349bd  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100349c3  call    esi
0x100349c5  lea     ecx, [edi+2]
0x100349c8  xor     edx, edx
0x100349ca  mov     ax, [edi]
0x100349cd  add     edi, 2
0x100349d0  cmp     ax, dx
0x100349d3  jnz     short loc_100349CA
0x100349d5  sub     edi, ecx
0x100349d7  sar     edi, 1
0x100349d9  jz      loc_100348AD
0x100349df  push    82h
0x100349e4  lea     edi, [ebx+120h]
0x100349ea  mov     ecx, esi
0x100349ec  push    edi
0x100349ed  push    274Dh
0x100349f2  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100349f8  call    esi
0x100349fa  lea     ecx, [edi+2]
0x100349fd  xor     edx, edx
0x100349ff  mov     ax, [edi]
0x10034a02  add     edi, 2
0x10034a05  cmp     ax, dx
0x10034a08  jnz     short loc_100349FF
0x10034a0a  sub     edi, ecx
0x10034a0c  sar     edi, 1
0x10034a0e  jz      loc_100348AD
0x10034a14  push    82h
0x10034a19  lea     edi, [ebx+1A2h]
0x10034a1f  mov     ecx, esi
0x10034a21  push    edi
0x10034a22  push    274Eh
0x10034a27  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10034a2d  call    esi
0x10034a2f  lea     ecx, [edi+2]
0x10034a32  xor     edx, edx
0x10034a34  mov     ax, [edi]
0x10034a37  add     edi, 2
0x10034a3a  cmp     ax, dx
0x10034a3d  jnz     short loc_10034A34
0x10034a3f  sub     edi, ecx
0x10034a41  sar     edi, 1
0x10034a43  jz      loc_100348AD
0x10034a49  push    82h
0x10034a4e  lea     edi, [ebx+224h]
0x10034a54  mov     ecx, esi
0x10034a56  push    edi
0x10034a57  push    274Fh
0x10034a5c  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10034a62  call    esi
0x10034a64  lea     ecx, [edi+2]
0x10034a67  xor     edx, edx
0x10034a69  mov     ax, [edi]
0x10034a6c  add     edi, 2
0x10034a6f  cmp     ax, dx
0x10034a72  jnz     short loc_10034A69
0x10034a74  sub     edi, ecx
0x10034a76  sar     edi, 1
0x10034a78  jz      loc_100348AD
0x10034a7e  push    82h
0x10034a83  lea     edi, [ebx+2A6h]
0x10034a89  mov     ecx, esi
0x10034a8b  push    edi
0x10034a8c  push    2750h
0x10034a91  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10034a97  call    esi
0x10034a99  lea     ecx, [edi+2]
0x10034a9c  xor     edx, edx
0x10034a9e  mov     ax, [edi]
0x10034aa1  add     edi, 2
0x10034aa4  cmp     ax, dx
0x10034aa7  jnz     short loc_10034A9E
0x10034aa9  sub     edi, ecx
0x10034aab  sar     edi, 1
0x10034aad  jz      loc_100348AD
0x10034ab3  mov     eax, edx
0x10034ab5  lea     ecx, [ebx+328h]
0x10034abb  mov     [ebp+var_4], eax
0x10034abe  imul    edi, eax, 82h
0x10034ac4  add     eax, 2751h
0x10034ac9  push    82h
0x10034ace  add     edi, ecx
0x10034ad0  mov     ecx, esi
0x10034ad2  push    edi
0x10034ad3  push    eax
0x10034ad4  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10034ada  call    esi
0x10034adc  lea     ecx, [edi+2]
0x10034adf  xor     edx, edx
0x10034ae1  mov     ax, [edi]
0x10034ae4  add     edi, 2
0x10034ae7  cmp     ax, dx
0x10034aea  jnz     short loc_10034AE1
0x10034aec  sub     edi, ecx
0x10034aee  sar     edi, 1
0x10034af0  jz      loc_100348AD
0x10034af6  mov     eax, [ebp+var_4]
0x10034af9  lea     ecx, [ebx+328h]
0x10034aff  inc     eax
0x10034b00  mov     [ebp+var_4], eax
0x10034b03  cmp     eax, 7
0x10034b06  jle     short loc_10034ABE
0x10034b08  push    [ebp+hLibModule]; hLibModule
0x10034b0b  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x10034b11  jmp     loc_1003498D
```
