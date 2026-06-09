# LoadODBC32AndGetFunctions(void)

- ea: `0x1005429dc`
- end: `0x100542ad0`
- name: `?LoadODBC32AndGetFunctions@@YAHXZ`
- size: `244`
- prototype: `__int64(void)`
- caller_count: `19`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x100542ad8`
- `0x100542bdc`
- `0x100542cb0`
- `0x100542da0`
- `0x100542e70`
- `0x100542f30`
- `0x100543060`
- `0x100543190`
- `0x100543270`
- `0x100543350`
- `0x100543420`
- `0x100543620`
- `0x1005436e0`
- `0x1005437b0`
- `0x100543b40`
- `0x100543d10`
- `0x100543de0`
- `0x100543ec0`
- `0x100543fd0`

## callees

- `0x100416508`
- `0x1005429dc`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x100542a1d`
- `KERNEL32!GetSystemDirectoryW` at `0x100542a1d`
- `KERNEL32!LoadLibraryW` at `0x100542a4a`
- `KERNEL32!LoadLibraryW` at `0x100542a4a`
- `KERNEL32!GetProcAddress` at `0x100542a66`
- `KERNEL32!GetProcAddress` at `0x100542a81`
- `KERNEL32!GetProcAddress` at `0x100542a66`
- `KERNEL32!GetProcAddress` at `0x100542a81`
- `KERNEL32!FreeLibrary` at `0x100542aa8`
- `KERNEL32!FreeLibrary` at `0x100542aa8`

## string_xrefs

- `0x100542a2b`: `\odbc32.dll`

## pseudocode

```c
__int64 LoadODBC32AndGetFunctions(void)
{
  HMODULE LibraryW; // rax
  __int16 (*ProcAddress)(void *, unsigned __int16, void *, __int16, __int16 *); // rax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  if ( pfnSQLSetConnectAttr && pfnSQLGetInfo )
    return 1;
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    if ( (int)StringCchCatW(Buffer, 0x105u, L"\\odbc32.dll") >= 0 )
    {
      LibraryW = LoadLibraryW(Buffer);
      g_hODBC32Inst = LibraryW;
      if ( LibraryW )
      {
        pfnSQLSetConnectAttr = (__int16 (*)(void *, int, void *, int))GetProcAddress(LibraryW, "SQLSetConnectAttr");
        ProcAddress = (__int16 (*)(void *, unsigned __int16, void *, __int16, __int16 *))GetProcAddress(
                                                                                           g_hODBC32Inst,
                                                                                           "SQLGetInfo");
        pfnSQLGetInfo = ProcAddress;
        if ( pfnSQLSetConnectAttr && ProcAddress )
          return 1;
        FreeLibrary(g_hODBC32Inst);
        g_hODBC32Inst = 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1005429dc  sub     rsp, 248h
0x1005429e3  mov     rax, cs:__security_cookie
0x1005429ea  xor     rax, rsp
0x1005429ed  mov     [rsp+248h+var_18], rax
0x1005429f5  cmp     cs:?pfnSQLSetConnectAttr@@3P6AFPEAXJ0J@ZEA, 0; short (*pfnSQLSetConnectAttr)(void *,long,void *,long)
0x1005429fd  jz      short loc_100542A13
0x1005429ff  cmp     cs:?pfnSQLGetInfo@@3P6AFPEAXG0FPEAF@ZEA, 0; short (*pfnSQLGetInfo)(void *,ushort,void *,short,short *)
0x100542a07  jz      short loc_100542A13
0x100542a09  mov     eax, 1
0x100542a0e  jmp     loc_100542AB8
0x100542a13  mov     edx, 104h; uSize
0x100542a18  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x100542a1d  call    cs:__imp_GetSystemDirectoryW
0x100542a23  test    eax, eax
0x100542a25  jz      loc_100542AB6
0x100542a2b  lea     r8, aOdbc32Dll; "\\odbc32.dll"
0x100542a32  mov     edx, 105h; unsigned __int64
0x100542a37  lea     rcx, [rsp+248h+Buffer]; unsigned __int16 *
0x100542a3c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x100542a41  test    eax, eax
0x100542a43  js      short loc_100542AB6
0x100542a45  lea     rcx, [rsp+248h+Buffer]; lpLibFileName
0x100542a4a  call    cs:__imp_LoadLibraryW
0x100542a50  mov     cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hODBC32Inst
0x100542a57  test    rax, rax
0x100542a5a  jz      short loc_100542AB6
0x100542a5c  lea     rdx, aSqlsetconnecta_2; "SQLSetConnectAttr"
0x100542a63  mov     rcx, rax; hModule
0x100542a66  call    cs:__imp_GetProcAddress
0x100542a6c  mov     rcx, cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA; hModule
0x100542a73  lea     rdx, aSqlgetinfo; "SQLGetInfo"
0x100542a7a  mov     cs:?pfnSQLSetConnectAttr@@3P6AFPEAXJ0J@ZEA, rax; short (*pfnSQLSetConnectAttr)(void *,long,void *,long)
0x100542a81  call    cs:__imp_GetProcAddress
0x100542a87  cmp     cs:?pfnSQLSetConnectAttr@@3P6AFPEAXJ0J@ZEA, 0; short (*pfnSQLSetConnectAttr)(void *,long,void *,long)
0x100542a8f  mov     cs:?pfnSQLGetInfo@@3P6AFPEAXG0FPEAF@ZEA, rax; short (*pfnSQLGetInfo)(void *,ushort,void *,short,short *)
0x100542a96  jz      short loc_100542AA1
0x100542a98  test    rax, rax
0x100542a9b  jnz     loc_100542A09
0x100542aa1  mov     rcx, cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA; hLibModule
0x100542aa8  call    cs:__imp_FreeLibrary
0x100542aae  and     cs:?g_hODBC32Inst@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hODBC32Inst
0x100542ab6  xor     eax, eax
0x100542ab8  mov     rcx, [rsp+248h+var_18]
0x100542ac0  xor     rcx, rsp; StackCookie
0x100542ac3  call    __security_check_cookie
0x100542ac8  add     rsp, 248h
0x100542acf  retn
```
