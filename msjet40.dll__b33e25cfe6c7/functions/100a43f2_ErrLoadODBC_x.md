# ErrLoadODBC(x)

- ea: `0x100a43f2`
- end: `0x100a44fe`
- name: `_ErrLoadODBC@4`
- size: `268`
- prototype: `int __thiscall(int)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1009813a`
- `0x1009c81c`
- `0x100a4913`
- `0x100a782a`
- `0x100d0df0`

## callees

- `0x1003e870`
- `0x1003eef0`
- `0x10046a9f`
- `0x10050000`
- `0x100a43f2`
- `0x100de7c9`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100a44ec`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x100a44ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a443c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a446f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a443c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x100a446f`

## string_xrefs

- `0x100a43f9`: `ODBC32.DLL`

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
      *(_DWORD *)off_10004A08[2 * v4] = ProcAddress;
      if ( !ProcAddress )
        break;
      if ( (unsigned int)++v4 >= 0x14 )
      {
        v6 = 0;
        while ( 1 )
        {
          v7 = GetProcAddress(hmodODBC, (&off_10004984)[2 * v6]);
          *(_DWORD *)off_10004980[2 * v6] = v7;
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
    UtilSetErrorInfoReal((int)this, L"ODBC32.DLL", 0, 0, -8132, 0, 0, 0);
    return -2006;
  }
}

```

## disassembly

```asm
0x100a43f2  mov     edi, edi
0x100a43f4  push    ebx
0x100a43f5  push    esi
0x100a43f6  push    edi
0x100a43f7  xor     ebx, ebx
0x100a43f9  mov     esi, offset _wszODBCDM; "ODBC32.DLL"
0x100a43fe  push    ebx; int
0x100a43ff  push    ebx; hFile
0x100a4400  push    esi; lpLibFileName
0x100a4401  mov     edi, ecx
0x100a4403  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x100a4408  mov     _hmodODBC, eax
0x100a440d  test    eax, eax
0x100a440f  jnz     short loc_100A4432
0x100a4411  push    ebx; int
0x100a4412  push    ebx; int
0x100a4413  push    ebx; int
0x100a4414  push    0FFFFE03Ch; int
0x100a4419  push    ebx; void *
0x100a441a  push    ebx; void *
0x100a441b  push    esi; Src
0x100a441c  push    edi; int
0x100a441d  mov     _hmodODBC, ebx
0x100a4423  call    _UtilSetErrorInfoReal@32; UtilSetErrorInfoReal(x,x,x,x,x,x,x,x)
0x100a4428  mov     eax, 0FFFFF82Ah
0x100a442d  jmp     loc_100A44FA
0x100a4432  mov     esi, ebx
0x100a4434  push    ds:lpProcName[esi*8]; lpProcName
0x100a443b  push    eax; hModule
0x100a443c  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100a4442  mov     ecx, ds:off_10004A08[esi*8]
0x100a4449  mov     [ecx], eax
0x100a444b  test    eax, eax
0x100a444d  jz      loc_100A44E1
0x100a4453  inc     esi
0x100a4454  cmp     esi, 14h
0x100a4457  jnb     short loc_100A4460
0x100a4459  mov     eax, _hmodODBC
0x100a445e  jmp     short loc_100A4434
0x100a4460  mov     esi, ebx
0x100a4462  push    ds:off_10004984[esi*8]; lpProcName
0x100a4469  push    _hmodODBC; hModule
0x100a446f  call    ds:__imp__GetProcAddress@8; GetProcAddress(x,x)
0x100a4475  mov     ecx, ds:off_10004980[esi*8]
0x100a447c  mov     [ecx], eax
0x100a447e  test    eax, eax
0x100a4480  jz      short loc_100A44E1
0x100a4482  inc     esi
0x100a4483  cmp     esi, 11h
0x100a4486  jb      short loc_100A4462
0x100a4488  test    byte ptr _wRmtTrace, 8
0x100a448f  jz      short loc_100A44CA
0x100a4491  mov     esi, _pfnSQLSetConnectOption
0x100a4497  mov     ecx, esi
0x100a4499  push    offset _szODBCTraceFile; "odbcapi.txt"
0x100a449e  push    69h ; 'i'; unsigned int
0x100a44a0  push    ebx; void *
0x100a44a1  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a44a7  call    esi ; _pfnSQLSetConnectOption
0x100a44a9  test    ax, ax
0x100a44ac  jz      short loc_100A44B5
0x100a44ae  mov     esi, 0FFFFFBF8h
0x100a44b3  jmp     short loc_100A44E6
0x100a44b5  mov     esi, _pfnSQLSetConnectOption
0x100a44bb  mov     ecx, esi
0x100a44bd  push    1
0x100a44bf  push    68h ; 'h'; unsigned int
0x100a44c1  push    ebx; void *
0x100a44c2  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x100a44c8  call    esi ; _pfnSQLSetConnectOption
0x100a44ca  push    edi
0x100a44cb  call    _UtilGetItibOfSesid@4; UtilGetItibOfSesid(x)
0x100a44d0  mov     ecx, eax
0x100a44d2  call    _ErrInitializeRgbif@4; ErrInitializeRgbif(x)
0x100a44d7  mov     esi, eax
0x100a44d9  test    esi, esi
0x100a44db  js      short loc_100A44E6
0x100a44dd  xor     eax, eax
0x100a44df  jmp     short loc_100A44FA
0x100a44e1  mov     esi, 0FFFFE1E3h
0x100a44e6  push    _hmodODBC; hLibModule
0x100a44ec  call    ds:__imp__FreeLibrary@4; FreeLibrary(x)
0x100a44f2  mov     _hmodODBC, ebx
0x100a44f8  mov     eax, esi
0x100a44fa  pop     edi
0x100a44fb  pop     esi
0x100a44fc  pop     ebx
0x100a44fd  retn
```
