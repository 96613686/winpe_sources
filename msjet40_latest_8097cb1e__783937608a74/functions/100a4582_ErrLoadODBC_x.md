# ErrLoadODBC(x)

- ea: `0x100a4582`
- end: `0x100a468e`
- name: `_ErrLoadODBC@4`
- size: `268`
- prototype: `int __thiscall(int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x100982ca`
- `0x1009c9ac`
- `0x100a4aa3`
- `0x100a79ba`
- `0x100d0f80`

## callees

- `0x1003ea00`
- `0x1003f080`
- `0x10046c1f`
- `0x10050190`
- `0x100a4582`
- `0x100de959`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100a467c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100a467c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a45cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a45ff`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a45cc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a45ff`

## string_xrefs

- `0x100a4589`: `ODBC32.DLL`

## pseudocode

```c
int __thiscall ErrLoadODBC(void *this)
{
  HMODULE Library; // eax
  int v4; // esi
  FARPROC ProcAddress; // eax
  int v6; // esi
  FARPROC v7; // eax
  int v8; // esi
  int ItibOfSesid; // eax

  Library = JetLoadLibraryExW(L"ODBC32.DLL", 0, 0);
  hmodODBC = Library;
  if ( Library )
  {
    v4 = 0;
    while ( 1 )
    {
      ProcAddress = GetProcAddress(Library, (&lpProcName)[2 * v4]);
      *(_DWORD *)off_10004A50[2 * v4] = ProcAddress;
      if ( !ProcAddress )
        break;
      if ( (unsigned int)++v4 >= 0x14 )
      {
        v6 = 0;
        while ( 1 )
        {
          v7 = GetProcAddress(hmodODBC, (&off_100049C4)[2 * v6]);
          *(_DWORD *)off_100049C0[2 * v6] = v7;
          if ( !v7 )
            goto LABEL_16;
          if ( (unsigned int)++v6 >= 0x11 )
          {
            if ( (wRmtTrace & 8) != 0 )
            {
              if ( (unsigned __int16)pfnSQLSetConnectOption(pfnSQLSetConnectOption, 0, 105, "odbcapi.txt") )
              {
                v8 = -1032;
                goto LABEL_17;
              }
              pfnSQLSetConnectOption(pfnSQLSetConnectOption, 0, 104, 1);
            }
            ItibOfSesid = UtilGetItibOfSesid(this);
            v8 = ErrInitializeRgbif(ItibOfSesid);
            if ( v8 >= 0 )
              return 0;
            goto LABEL_17;
          }
        }
      }
      Library = hmodODBC;
    }
LABEL_16:
    v8 = -7709;
LABEL_17:
    FreeLibrary(hmodODBC);
    hmodODBC = 0;
    return v8;
  }
  else
  {
    hmodODBC = 0;
    UtilSetErrorInfoReal((int)this, (void *)L"ODBC32.DLL", 0, 0, -8132, 0, 0, 0);
    return -2006;
  }
}

```

## disassembly

```asm
0x100a4582  mov     edi, edi
0x100a4584  push    ebx
0x100a4585  push    esi
0x100a4586  push    edi
0x100a4587  xor     ebx, ebx
0x100a4589  mov     esi, offset _wszODBCDM; "ODBC32.DLL"
0x100a458e  push    ebx; int
0x100a458f  push    ebx; hFile
0x100a4590  push    esi; lpLibFileName
0x100a4591  mov     edi, ecx
0x100a4593  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x100a4598  mov     _hmodODBC, eax
0x100a459d  test    eax, eax
0x100a459f  jnz     short loc_100A45C2
0x100a45a1  push    ebx; int
0x100a45a2  push    ebx; int
0x100a45a3  push    ebx; int
0x100a45a4  push    0FFFFE03Ch; int
0x100a45a9  push    ebx; void *
0x100a45aa  push    ebx; void *
0x100a45ab  push    esi; Src
0x100a45ac  push    edi; int
0x100a45ad  mov     _hmodODBC, ebx
0x100a45b3  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100a45b8  mov     eax, 0FFFFF82Ah
0x100a45bd  jmp     loc_100A468A
0x100a45c2  mov     esi, ebx
0x100a45c4  push    ds:lpProcName[esi*8]; lpProcName
0x100a45cb  push    eax; hModule
0x100a45cc  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100a45d2  mov     ecx, ds:off_10004A50[esi*8]
0x100a45d9  mov     [ecx], eax
0x100a45db  test    eax, eax
0x100a45dd  jz      loc_100A4671
0x100a45e3  inc     esi
0x100a45e4  cmp     esi, 14h
0x100a45e7  jnb     short loc_100A45F0
0x100a45e9  mov     eax, _hmodODBC
0x100a45ee  jmp     short loc_100A45C4
0x100a45f0  mov     esi, ebx
0x100a45f2  push    ds:off_100049C4[esi*8]; lpProcName
0x100a45f9  push    _hmodODBC; hModule
0x100a45ff  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100a4605  mov     ecx, ds:off_100049C0[esi*8]
0x100a460c  mov     [ecx], eax
0x100a460e  test    eax, eax
0x100a4610  jz      short loc_100A4671
0x100a4612  inc     esi
0x100a4613  cmp     esi, 11h
0x100a4616  jb      short loc_100A45F2
0x100a4618  test    byte ptr _wRmtTrace, 8
0x100a461f  jz      short loc_100A465A
0x100a4621  mov     esi, _pfnSQLSetConnectOption
0x100a4627  mov     ecx, esi
0x100a4629  push    offset _szODBCTraceFile; "odbcapi.txt"
0x100a462e  push    69h ; 'i'; unsigned int
0x100a4630  push    ebx; void *
0x100a4631  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a4637  call    esi ; _pfnSQLSetConnectOption
0x100a4639  test    ax, ax
0x100a463c  jz      short loc_100A4645
0x100a463e  mov     esi, 0FFFFFBF8h
0x100a4643  jmp     short loc_100A4676
0x100a4645  mov     esi, _pfnSQLSetConnectOption
0x100a464b  mov     ecx, esi
0x100a464d  push    1
0x100a464f  push    68h ; 'h'; unsigned int
0x100a4651  push    ebx; void *
0x100a4652  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a4658  call    esi ; _pfnSQLSetConnectOption
0x100a465a  push    edi
0x100a465b  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x100a4660  mov     ecx, eax
0x100a4662  call    _ErrInitializeRgbif@4; ErrInitializeRgbif(x)
0x100a4667  mov     esi, eax
0x100a4669  test    esi, esi
0x100a466b  js      short loc_100A4676
0x100a466d  xor     eax, eax
0x100a466f  jmp     short loc_100A468A
0x100a4671  mov     esi, 0FFFFE1E3h
0x100a4676  push    _hmodODBC; hLibModule
0x100a467c  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100a4682  mov     _hmodODBC, ebx
0x100a4688  mov     eax, esi
0x100a468a  pop     edi
0x100a468b  pop     esi
0x100a468c  pop     ebx
0x100a468d  retn
```
