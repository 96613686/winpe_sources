# ProcessCopyAndCoreDriverSection(_WPNP_INFO *,ushort const *)

- ea: `0x18002d300`
- end: `0x18002d504`
- name: `?ProcessCopyAndCoreDriverSection@@YAJPEAU_WPNP_INFO@@PEBG@Z`
- size: `516`
- prototype: `int(struct _WPNP_INFO *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x18002d6f4`

## callees

- `0x18000b200`
- `0x18001eed8`
- `0x18002c71c`
- `0x18002cb38`
- `0x18002cce8`
- `0x18002d300`
- `0x18002d50c`
- `0x18002d608`
- `0x18002e060`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d482`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4e4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d482`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002d4e4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d3b7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002d3b7`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002d4c0`
- `KERNEL32!WritePrivateProfileStringW` at `0x18002d4c0`
- `SETUPAPI!SetupFindFirstLineW` at `0x18002d407`
- `SETUPAPI!SetupFindFirstLineW` at `0x18002d407`
- `WINSPOOL!GetCorePrinterDriversW` at `0x18002d3e6`
- `WINSPOOL!GetCorePrinterDriversW` at `0x18002d3e6`

## string_xrefs

- `0x18002d4af`: `CopyFiles`

## pseudocode

```c
__int64 __fastcall ProcessCopyAndCoreDriverSection(struct _WPNP_INFO *a1, const unsigned __int16 *a2)
{
  HRESULT valid; // ebx
  _WORD *v5; // rax
  DWORD v6; // r14d
  __int64 v7; // rcx
  struct _WPNP_CORE_DRIVERS_LIST *v8; // rsi
  struct _CORE_PRINTER_DRIVERW *pCorePrinterDrivers; // r15
  NCoreLibrary *v10; // rcx
  int WpnpCoreDriversList; // eax
  const WCHAR *v12; // r9
  WCHAR *v13; // rdi
  NCoreLibrary *v14; // rcx
  struct _WPNP_CORE_DRIVERS_LIST *v16; // [rsp+30h] [rbp-20h] BYREF
  struct _INFCONTEXT Context; // [rsp+38h] [rbp-18h] BYREF
  LPCWSTR lpString; // [rsp+A8h] [rbp+58h] BYREF

  lpString = 0;
  valid = ValidWPNPInfo(a1);
  if ( valid >= 0 )
  {
    if ( a2 )
    {
      valid = ProcessCopyFiles(*(HINF *)a1, *((LPCWSTR *)a1 + 1), a2, (unsigned __int16 **)&lpString);
      if ( valid < 0 )
        goto LABEL_29;
      v5 = (_WORD *)*((_QWORD *)a1 + 5);
      v6 = 0;
      if ( v5 )
      {
        while ( *v5 )
        {
          v7 = -1;
          do
            ++v7;
          while ( v5[v7] );
          v5 += v7 + 1;
          ++v6;
        }
      }
      if ( !v6 )
        goto LABEL_26;
      memset(&Context, 0, sizeof(Context));
      v8 = 0;
      v16 = 0;
      pCorePrinterDrivers = (struct _CORE_PRINTER_DRIVERW *)LocalAlloc(0x40u, 552 * v6);
      if ( pCorePrinterDrivers )
      {
        valid = GetCorePrinterDriversW(
                  0,
                  (LPCWSTR)PlatformEnv[*((int *)a1 + 8)],
                  *((LPCWSTR *)a1 + 5),
                  v6,
                  pCorePrinterDrivers);
        if ( valid >= 0 )
        {
          if ( SetupFindFirstLineW(*(HINF *)a1, a2, L"CoreDriverSections", &Context)
            || (valid = NCoreLibrary::GetLastErrorAsFailHR(v10), valid >= 0) )
          {
            valid = InfGetMultiSz(&Context);
            if ( valid >= 0 )
            {
              WpnpCoreDriversList = GetWpnpCoreDriversList(0, pCorePrinterDrivers, v6, &v16);
              v8 = v16;
              valid = WpnpCoreDriversList;
              if ( WpnpCoreDriversList >= 0 )
              {
                valid = ProcessCoreDriversList(*(void **)a1, *((const unsigned __int16 **)a1 + 1), a2, v16);
                if ( valid >= 0 )
                  valid = GetUpdatedCopyFilesSection(v8, (unsigned __int16 **)&lpString);
              }
            }
          }
        }
      }
      else
      {
        valid = -2147024882;
      }
      if ( v8 )
        DestroyCoreDriversList(v8);
      if ( pCorePrinterDrivers )
        LocalFree(pCorePrinterDrivers);
      if ( valid < 0 )
      {
LABEL_29:
        v13 = (WCHAR *)lpString;
      }
      else
      {
LABEL_26:
        v12 = (const WCHAR *)*((_QWORD *)a1 + 1);
        v13 = (WCHAR *)lpString;
        if ( WritePrivateProfileStringW(a2, L"CopyFiles", lpString, v12) )
          valid = 0;
        else
          valid = NCoreLibrary::GetLastErrorAsFailHR(v14);
      }
      if ( v13 )
        LocalFree(v13);
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)valid;
}

```

## disassembly

```asm
0x18002d300  mov     [rsp-38h+arg_0], rbx
0x18002d305  push    rbp
0x18002d306  push    rsi
0x18002d307  push    rdi
0x18002d308  push    r12
0x18002d30a  push    r13
0x18002d30c  push    r14
0x18002d30e  push    r15
0x18002d310  mov     rbp, rsp
0x18002d313  sub     rsp, 50h
0x18002d317  xor     r13d, r13d
0x18002d31a  mov     r12, rdx
0x18002d31d  mov     [rbp+lpString], r13
0x18002d321  mov     rdi, rcx
0x18002d324  call    ?ValidWPNPInfo@@YAJPEAU_WPNP_INFO@@@Z; ValidWPNPInfo(_WPNP_INFO *)
0x18002d329  mov     ebx, eax
0x18002d32b  test    eax, eax
0x18002d32d  js      loc_18002D4EA
0x18002d333  test    r12, r12
0x18002d336  jnz     short loc_18002D342
0x18002d338  mov     ebx, 80070057h
0x18002d33d  jmp     loc_18002D4EA
0x18002d342  mov     rdx, [rdi+8]; lpFileName
0x18002d346  lea     r9, [rbp+lpString]; unsigned __int16 **
0x18002d34a  mov     rcx, [rdi]; InfHandle
0x18002d34d  mov     r8, r12; unsigned __int16 *
0x18002d350  call    ?ProcessCopyFiles@@YAJPEAXPEBG1PEAPEAG@Z; ProcessCopyFiles(void *,ushort const *,ushort const *,ushort * *)
0x18002d355  mov     ebx, eax
0x18002d357  test    eax, eax
0x18002d359  js      loc_18002D4D8
0x18002d35f  mov     rax, [rdi+28h]
0x18002d363  mov     r14d, r13d
0x18002d366  test    rax, rax
0x18002d369  jz      short loc_18002D38C
0x18002d36b  jmp     short loc_18002D386
0x18002d36d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002d371  inc     rcx
0x18002d374  cmp     [rax+rcx*2], r13w
0x18002d379  jnz     short loc_18002D371
0x18002d37b  lea     rax, [rax+rcx*2]
0x18002d37f  add     rax, 2
0x18002d383  inc     r14d
0x18002d386  cmp     [rax], r13w
0x18002d38a  jnz     short loc_18002D36D
0x18002d38c  test    r14d, r14d
0x18002d38f  jz      loc_18002D4AB
0x18002d395  xor     eax, eax
0x18002d397  imul    edx, r14d, 228h; uBytes
0x18002d39e  xorps   xmm0, xmm0
0x18002d3a1  mov     qword ptr [rbp+Context.Section], rax
0x18002d3a5  movups  xmmword ptr [rbp+Context.Inf], xmm0
0x18002d3a9  mov     [rbp+hMem], r13
0x18002d3ad  mov     rsi, r13
0x18002d3b0  lea     ecx, [rax+40h]; uFlags
0x18002d3b3  mov     [rbp+var_20], r13
0x18002d3b7  call    cs:__imp_LocalAlloc
0x18002d3bd  mov     r15, rax
0x18002d3c0  test    rax, rax
0x18002d3c3  jz      loc_18002D474
0x18002d3c9  movsxd  rdx, dword ptr [rdi+20h]
0x18002d3cd  lea     rax, PlatformEnv
0x18002d3d4  mov     r8, [rdi+28h]; pszzCoreDriverDependencies
0x18002d3d8  mov     r9d, r14d; cCorePrinterDrivers
0x18002d3db  xor     ecx, ecx; pszServer
0x18002d3dd  mov     [rsp+50h+pCorePrinterDrivers], r15; pCorePrinterDrivers
0x18002d3e2  mov     rdx, [rax+rdx*8]; pszEnvironment
0x18002d3e6  call    cs:__imp_GetCorePrinterDriversW
0x18002d3ec  mov     ebx, eax
0x18002d3ee  test    eax, eax
0x18002d3f0  js      loc_18002D479
0x18002d3f6  mov     rcx, [rdi]; InfHandle
0x18002d3f9  lea     r9, [rbp+Context]; Context
0x18002d3fd  lea     r8, cszCoreDriverSections; "CoreDriverSections"
0x18002d404  mov     rdx, r12; Section
0x18002d407  call    cs:__imp_SetupFindFirstLineW
0x18002d40d  test    eax, eax
0x18002d40f  jnz     short loc_18002D41C
0x18002d411  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002d416  mov     ebx, eax
0x18002d418  test    eax, eax
0x18002d41a  js      short loc_18002D479
0x18002d41c  lea     r8, [rbp+hMem]
0x18002d420  lea     rcx, [rbp+Context]; Context
0x18002d424  call    InfGetMultiSz
0x18002d429  mov     ebx, eax
0x18002d42b  test    eax, eax
0x18002d42d  js      short loc_18002D479
0x18002d42f  mov     rcx, [rbp+hMem]; unsigned __int16 *
0x18002d433  lea     r9, [rbp+var_20]; struct _WPNP_CORE_DRIVERS_LIST **
0x18002d437  mov     r8d, r14d; unsigned int
0x18002d43a  mov     rdx, r15; struct _CORE_PRINTER_DRIVERW *
0x18002d43d  call    ?GetWpnpCoreDriversList@@YAJPEAGPEAU_CORE_PRINTER_DRIVERW@@KPEAPEAU_WPNP_CORE_DRIVERS_LIST@@@Z; GetWpnpCoreDriversList(ushort *,_CORE_PRINTER_DRIVERW *,ulong,_WPNP_CORE_DRIVERS_LIST * *)
0x18002d442  mov     rsi, [rbp+var_20]
0x18002d446  mov     ebx, eax
0x18002d448  test    eax, eax
0x18002d44a  js      short loc_18002D479
0x18002d44c  mov     rdx, [rdi+8]; unsigned __int16 *
0x18002d450  mov     r9, rsi; struct _WPNP_CORE_DRIVERS_LIST *
0x18002d453  mov     rcx, [rdi]; void *
0x18002d456  mov     r8, r12; unsigned __int16 *
0x18002d459  call    ?ProcessCoreDriversList@@YAJPEAXPEBG1PEAU_WPNP_CORE_DRIVERS_LIST@@@Z; ProcessCoreDriversList(void *,ushort const *,ushort const *,_WPNP_CORE_DRIVERS_LIST *)
0x18002d45e  mov     ebx, eax
0x18002d460  test    eax, eax
0x18002d462  js      short loc_18002D479
0x18002d464  lea     rdx, [rbp+lpString]; unsigned __int16 **
0x18002d468  mov     rcx, rsi; struct _WPNP_CORE_DRIVERS_LIST *
0x18002d46b  call    ?GetUpdatedCopyFilesSection@@YAJPEAU_WPNP_CORE_DRIVERS_LIST@@PEAPEAG@Z; GetUpdatedCopyFilesSection(_WPNP_CORE_DRIVERS_LIST *,ushort * *)
0x18002d470  mov     ebx, eax
0x18002d472  jmp     short loc_18002D479
0x18002d474  mov     ebx, 8007000Eh
0x18002d479  mov     rcx, [rbp+hMem]; hMem
0x18002d47d  test    rcx, rcx
0x18002d480  jz      short loc_18002D48C
0x18002d482  call    cs:__imp_LocalFree
0x18002d488  mov     [rbp+hMem], r13
0x18002d48c  test    rsi, rsi
0x18002d48f  jz      short loc_18002D499
0x18002d491  mov     rcx, rsi; hMem
0x18002d494  call    ?DestroyCoreDriversList@@YAXPEAU_WPNP_CORE_DRIVERS_LIST@@@Z; DestroyCoreDriversList(_WPNP_CORE_DRIVERS_LIST *)
0x18002d499  test    r15, r15
0x18002d49c  jz      short loc_18002D4A7
0x18002d49e  mov     rcx, r15; hMem
0x18002d4a1  call    cs:__imp_LocalFree
0x18002d4a7  test    ebx, ebx
0x18002d4a9  js      short loc_18002D4D8
0x18002d4ab  mov     r9, [rdi+8]; lpFileName
0x18002d4af  lea     rdx, KeyName; "CopyFiles"
0x18002d4b6  mov     rdi, [rbp+lpString]
0x18002d4ba  mov     rcx, r12; lpAppName
0x18002d4bd  mov     r8, rdi; lpString
0x18002d4c0  call    cs:__imp_WritePrivateProfileStringW
0x18002d4c6  test    eax, eax
0x18002d4c8  jz      short loc_18002D4CF
0x18002d4ca  mov     ebx, r13d
0x18002d4cd  jmp     short loc_18002D4DC
0x18002d4cf  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18002d4d4  mov     ebx, eax
0x18002d4d6  jmp     short loc_18002D4DC
0x18002d4d8  mov     rdi, [rbp+lpString]
0x18002d4dc  test    rdi, rdi
0x18002d4df  jz      short loc_18002D4EA
0x18002d4e1  mov     rcx, rdi; hMem
0x18002d4e4  call    cs:__imp_LocalFree
0x18002d4ea  mov     eax, ebx
0x18002d4ec  mov     rbx, [rsp+50h+arg_0]
0x18002d4f4  add     rsp, 50h
0x18002d4f8  pop     r15
0x18002d4fa  pop     r14
0x18002d4fc  pop     r13
0x18002d4fe  pop     r12
0x18002d500  pop     rdi
0x18002d501  pop     rsi
0x18002d502  pop     rbp
0x18002d503  retn
```
