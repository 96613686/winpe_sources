# FindCoreDriverSections(ushort const *,_CORE_DRIVER_INFO *,ulong,_CORE_SECTION_INFO * *,ulong *)

- ea: `0x18001825c`
- end: `0x1800187d9`
- name: `?FindCoreDriverSections@@YAHPEBGPEAU_CORE_DRIVER_INFO@@KPEAPEAU_CORE_SECTION_INFO@@PEAK@Z`
- size: `1405`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, struct _CORE_DRIVER_INFO *@<rdx>, unsigned int@<r8d>, struct _CORE_SECTION_INFO **@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a914`

## callees

- `0x18000d21c`
- `0x18000d57c`
- `0x18000d624`
- `0x18001825c`
- `0x180034bec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800182f1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001830a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018414`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800184be`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800182f1`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001830a`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180018414`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x1800184be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018728`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018467`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180018728`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001832a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018322`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001832a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180018503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800185a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800186c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800187ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018639`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018639`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800183de`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800183de`
- `KERNEL32!lstrcmpiW` at `0x18001844d`
- `KERNEL32!lstrcmpiW` at `0x18001844d`

## string_xrefs

- `0x180018359`: `One missing comma, see additional info for string`
- `0x1800185d8`: `One missing comma (2), see additional info for string`
- `0x180018520`: `StringCbCopy failed, see additional info for source string (not actual HRESULT)`

## pseudocode

```c
__int64 __fastcall FindCoreDriverSections(
        unsigned __int16 *a1,
        const WCHAR *a2,
        unsigned int a3,
        struct _CORE_SECTION_INFO **a4,
        unsigned int *a5)
{
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rsi
  unsigned int v11; // r12d
  wchar_t *v12; // rax
  int v13; // r14d
  signed int v14; // ebx
  DWORD v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  const wchar_t *v18; // r14
  wchar_t *v19; // rax
  wchar_t *v20; // rsi
  int v21; // r15d
  const unsigned __int16 *v22; // r12
  unsigned __int16 *v23; // r11
  signed int v24; // eax
  unsigned int v25; // ecx
  unsigned __int64 v26; // rax
  signed int v27; // esi
  DWORD v28; // eax
  unsigned int v29; // ecx
  __int64 v30; // rax
  signed int v31; // eax
  unsigned int v32; // ecx
  DWORD LastError; // eax
  unsigned int v35; // [rsp+60h] [rbp-58h]
  unsigned __int16 *hMem; // [rsp+68h] [rbp-50h]
  unsigned int v37; // [rsp+C0h] [rbp+8h]

  if ( !a1 || !*a1 || !a2 || !a3 || !a5 || !a4 )
  {
    SetLastError(0x57u);
    ClassInstallerTelemetry::WriteDbgTraceError(
      "FindCoreDriverSections",
      L"Invalid Argument: pszzCoreDriverDependencies=%p, pCoreDriverDependencies=%p, dwCoreDriverCount=%d, pdwSectionCount"
       "=%p, ppCoreSectionDependencies=%p",
      a1,
      a2,
      a3,
      a5,
      a4);
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"FindCoreDriverSections",
      L"Invalid argument(s)",
      0,
      0,
      0,
      0,
      0,
      1,
      a1,
      0x57u,
      0x80070057);
    v9 = 0;
LABEL_57:
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "FindCoreDriverSections",
      L"Error finding core driver sections: %d",
      LastError);
    return v9;
  }
  v35 = 0;
  v9 = 1;
  v10 = a1;
  v11 = 0;
  do
  {
    if ( !*v10 )
      break;
    v12 = wcschr(v10, 0x2Cu);
    if ( v12 )
    {
      v13 = 1;
      v9 = 1;
      do
      {
        v12 = wcschr(v12 + 1, 0x2Cu);
        ++v11;
      }
      while ( v12 );
      v35 = v11;
    }
    else
    {
      v13 = 0;
      v14 = GetLastError();
      v15 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "FindCoreDriverSections",
        L"String format for core driver dependencies invalid in %ws: %d",
        v10,
        v15);
      v16 = v14 > 0 ? (unsigned __int16)v14 | 0x80070000 : v14;
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"FindLatestCoreDrivers",
        L"One missing comma, see additional info for string",
        v10,
        0,
        0,
        0,
        0,
        1,
        a1,
        v14,
        v16);
      v9 = 0;
    }
    v17 = -1;
    do
      ++v17;
    while ( v10[v17] );
    v10 += v17 + 1;
  }
  while ( v13 );
  if ( !v9 )
    goto LABEL_57;
  ClassInstallerTelemetry::WriteDbgTraceInfo("FindCoreDriverSections", L"Driver requires %d core driver sections.", v11);
  hMem = (unsigned __int16 *)LocalAlloc(0x40u, v11 << 9);
  if ( !hMem )
  {
    v9 = 0;
    v31 = GetLastError();
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    else
      v32 = v31;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"FindLatestCoreDrivers",
      L"LocalAllocMem failed",
      0,
      0,
      0,
      0,
      0,
      1,
      a1,
      v31,
      v32);
    goto LABEL_57;
  }
  v9 = 1;
  v37 = 0;
  v18 = a1;
  while ( *v18 )
  {
    v19 = wcschr(v18, 0x2Cu);
    v20 = v19;
    if ( v19 )
    {
      v21 = 0;
      *v19 = 0;
      if ( a3 )
      {
        while ( lstrcmpiW(&a2[312 * v21], v18) )
        {
          if ( ++v21 >= a3 )
            goto LABEL_28;
        }
        ClassInstallerTelemetry::WriteDbgTraceInfo("FindCoreDriverSections", L"Found core driver section %ws", v18);
        v9 = 1;
        *v20 = 44;
        do
        {
          if ( !v20 )
            break;
          v22 = v20 + 1;
          v20 = wcschr(v20 + 1, 0x2Cu);
          if ( v20 )
            *v20 = 0;
          if ( (int)StringCbCopyW(&hMem[256 * (unsigned __int64)v37], 0x1FEu, v22) < 0 )
          {
            v9 = 0;
            v24 = GetLastError();
            v25 = v24 > 0 ? (unsigned __int16)v24 | 0x80070000 : v24;
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
              L"FindLatestCoreDrivers",
              L"StringCbCopy failed, see additional info for source string (not actual HRESULT)",
              v22,
              0,
              0,
              0,
              0,
              1,
              a1,
              v24,
              v25);
            v23 = hMem;
          }
          else
          {
            v9 = 1;
          }
          if ( v20 )
            *v20 = 44;
          v26 = (unsigned __int64)v37++ << 9;
          *(unsigned __int16 *)((char *)v23 + v26 + 510) = v21;
        }
        while ( v9 );
      }
      else
      {
LABEL_28:
        v9 = 0;
        SetLastError(0xE0000101);
        ClassInstallerTelemetry::WriteDbgTraceError(
          "FindCoreDriverSections",
          L"Couldn't find core driver section %ws",
          v18);
        *v20 = 44;
      }
    }
    else
    {
      v9 = 0;
      v27 = GetLastError();
      v28 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "FindCoreDriverSections",
        L"String format for core driver dependencies invalid in %ws: %d",
        v18,
        v28);
      if ( v27 > 0 )
        v29 = (unsigned __int16)v27 | 0x80070000;
      else
        v29 = v27;
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"FindLatestCoreDrivers",
        L"One missing comma (2), see additional info for string",
        v18,
        0,
        0,
        0,
        0,
        1,
        a1,
        v27,
        v29);
    }
    v30 = -1;
    do
      ++v30;
    while ( v18[v30] );
    v18 += v30 + 1;
    if ( !v9 )
    {
      LocalFree(hMem);
      goto LABEL_57;
    }
  }
  *a5 = v35;
  *a4 = (struct _CORE_SECTION_INFO *)hMem;
  ClassInstallerTelemetry::WriteDbgTraceInfo("FindCoreDriverSections", L"All core driver sections found.");
  SplLogPrinterSetupCoreDriverEvent(
    &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
    L"FindLatestCoreDrivers",
    0,
    0,
    0,
    0,
    0,
    0,
    1,
    a1,
    0,
    0);
  return v9;
}

```

## disassembly

```asm
0x18001825c  mov     [rsp+arg_18], r9
0x180018261  mov     [rsp+arg_10], r8d
0x180018266  mov     [rsp+arg_8], rdx
0x18001826b  push    rbx
0x18001826c  push    rbp
0x18001826d  push    rsi
0x18001826e  push    rdi
0x18001826f  push    r12
0x180018271  push    r13
0x180018273  push    r14
0x180018275  push    r15
0x180018277  sub     rsp, 78h
0x18001827b  xor     r15d, r15d
0x18001827e  mov     rdi, r9
0x180018281  mov     ebx, r8d
0x180018284  mov     rsi, rdx
0x180018287  mov     rbp, rcx
0x18001828a  test    rcx, rcx
0x18001828d  jz      loc_18001871F
0x180018293  cmp     [rcx], r15w
0x180018297  jz      loc_18001871F
0x18001829d  test    rdx, rdx
0x1800182a0  jz      loc_18001871F
0x1800182a6  test    ebx, ebx
0x1800182a8  jz      loc_18001871F
0x1800182ae  cmp     [rsp+0B8h+arg_20], r15
0x1800182b6  jz      loc_18001871F
0x1800182bc  test    r9, r9
0x1800182bf  jz      loc_18001871F
0x1800182c5  lea     edi, [r15+1]
0x1800182c9  mov     [rsp+0B8h+var_58], r15d
0x1800182ce  mov     ebx, edi
0x1800182d0  lea     r13, aFindcoredriver_1; "FindCoreDriverSections"
0x1800182d7  mov     rsi, rcx
0x1800182da  mov     r12d, r15d
0x1800182dd  mov     eax, 2Ch ; ','
0x1800182e2  cmp     [rsi], r15w
0x1800182e6  jz      loc_1800183B9
0x1800182ec  mov     edx, eax; Ch
0x1800182ee  mov     rcx, rsi; Str
0x1800182f1  call    cs:__imp_wcschr
0x1800182f7  test    rax, rax
0x1800182fa  jz      short loc_18001831F
0x1800182fc  mov     r14d, edi
0x1800182ff  mov     ebx, edi
0x180018301  mov     edx, 2Ch ; ','; Ch
0x180018306  lea     rcx, [rax+2]; Str
0x18001830a  call    cs:__imp_wcschr
0x180018310  add     r12d, edi
0x180018313  test    rax, rax
0x180018316  jnz     short loc_180018301
0x180018318  mov     [rsp+0B8h+var_58], r12d
0x18001831d  jmp     short loc_18001839A
0x18001831f  mov     r14d, r15d
0x180018322  call    cs:__imp_GetLastError
0x180018328  mov     ebx, eax
0x18001832a  call    cs:__imp_GetLastError
0x180018330  mov     r8, rsi
0x180018333  lea     rdx, aStringFormatFo; "String format for core driver dependenc"...
0x18001833a  mov     r9d, eax
0x18001833d  mov     rcx, r13; char *
0x180018340  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180018345  test    ebx, ebx
0x180018347  jg      short loc_18001834D
0x180018349  mov     eax, ebx
0x18001834b  jmp     short loc_180018355
0x18001834d  movzx   eax, bx
0x180018350  or      eax, 80070000h
0x180018355  mov     [rsp+0B8h+var_60], eax; unsigned int
0x180018359  lea     r8, aOneMissingComm; "One missing comma, see additional info "...
0x180018360  mov     [rsp+0B8h+var_68], ebx; unsigned int
0x180018364  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x18001836b  mov     [rsp+0B8h+var_70], rbp; unsigned __int16 *
0x180018370  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180018377  mov     [rsp+0B8h+var_78], edi; int
0x18001837b  mov     r9, rsi; unsigned __int16 *
0x18001837e  mov     [rsp+0B8h+var_80], r15; unsigned __int16 *
0x180018383  mov     [rsp+0B8h+var_88], r15; unsigned __int16 *
0x180018388  mov     [rsp+0B8h+var_90], r15; unsigned __int16 *
0x18001838d  mov     [rsp+0B8h+var_98], r15; unsigned __int16 *
0x180018392  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180018397  mov     ebx, r15d
0x18001839a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001839e  inc     rax
0x1800183a1  cmp     [rsi+rax*2], r15w
0x1800183a6  jnz     short loc_18001839E
0x1800183a8  lea     rsi, [rsi+rax*2]
0x1800183ac  add     rsi, 2
0x1800183b0  test    r14d, r14d
0x1800183b3  jnz     loc_1800182DD
0x1800183b9  test    ebx, ebx
0x1800183bb  jz      loc_1800187AE
0x1800183c1  mov     r8d, r12d
0x1800183c4  lea     rdx, aDriverRequires; "Driver requires %d core driver sections"...
0x1800183cb  mov     rcx, r13; char *
0x1800183ce  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800183d3  mov     edx, r12d
0x1800183d6  mov     ecx, 40h ; '@'; uFlags
0x1800183db  shl     edx, 9; uBytes
0x1800183de  call    cs:__imp_LocalAlloc
0x1800183e4  xor     r12d, r12d
0x1800183e7  mov     [rsp+0B8h+hMem], rax
0x1800183ec  test    rax, rax
0x1800183ef  jz      loc_1800186BE
0x1800183f5  mov     ebx, edi
0x1800183f7  mov     [rsp+0B8h+arg_0], r12d
0x1800183ff  mov     r14, rbp
0x180018402  cmp     [r14], r12w
0x180018406  jz      loc_180018644
0x18001840c  mov     edx, 2Ch ; ','; Ch
0x180018411  mov     rcx, r14; Str
0x180018414  call    cs:__imp_wcschr
0x18001841a  mov     rsi, rax
0x18001841d  test    rax, rax
0x180018420  jz      loc_18001859D
0x180018426  mov     ebx, [rsp+0B8h+arg_10]
0x18001842d  mov     r15d, r12d
0x180018430  mov     [rax], r12w
0x180018434  test    ebx, ebx
0x180018436  jz      short loc_18001845F
0x180018438  mov     eax, r15d
0x18001843b  mov     rdx, r14; lpString2
0x18001843e  imul    rcx, rax, 270h
0x180018445  add     rcx, [rsp+0B8h+arg_8]; lpString1
0x18001844d  call    cs:__imp_lstrcmpiW
0x180018453  test    eax, eax
0x180018455  jz      short loc_180018489
0x180018457  add     r15d, edi
0x18001845a  cmp     r15d, ebx
0x18001845d  jb      short loc_180018438
0x18001845f  mov     ecx, 0E0000101h; dwErrCode
0x180018464  mov     ebx, r12d
0x180018467  call    cs:__imp_SetLastError
0x18001846d  mov     r8, r14
0x180018470  lea     rdx, aCouldnTFindCor; "Couldn't find core driver section %ws"
0x180018477  mov     rcx, r13; char *
0x18001847a  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001847f  mov     word ptr [rsi], 2Ch ; ','
0x180018484  jmp     loc_180018616
0x180018489  mov     r8, r14
0x18001848c  lea     rdx, aFoundCoreDrive; "Found core driver section %ws"
0x180018493  mov     rcx, r13; char *
0x180018496  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001849b  mov     eax, 2Ch ; ','
0x1800184a0  mov     ebx, edi
0x1800184a2  mov     [rsi], ax
0x1800184a5  jmp     short loc_1800184AC
0x1800184a7  mov     eax, 2Ch ; ','
0x1800184ac  test    rsi, rsi
0x1800184af  jz      loc_180018616
0x1800184b5  lea     r12, [rsi+2]
0x1800184b9  mov     edx, eax; Ch
0x1800184bb  mov     rcx, r12; Str
0x1800184be  call    cs:__imp_wcschr
0x1800184c4  mov     rsi, rax
0x1800184c7  test    rax, rax
0x1800184ca  jz      short loc_1800184D1
0x1800184cc  xor     eax, eax
0x1800184ce  mov     [rsi], ax
0x1800184d1  mov     r11, [rsp+0B8h+hMem]
0x1800184d6  test    ebx, ebx
0x1800184d8  jz      loc_180018563
0x1800184de  mov     ecx, [rsp+0B8h+arg_0]
0x1800184e5  mov     r8, r12; unsigned __int16 *
0x1800184e8  shl     rcx, 9
0x1800184ec  mov     edx, 1FEh; unsigned __int64
0x1800184f1  add     rcx, r11; unsigned __int16 *
0x1800184f4  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x1800184f9  test    eax, eax
0x1800184fb  js      short loc_180018501
0x1800184fd  mov     ebx, edi
0x1800184ff  jmp     short loc_180018563
0x180018501  xor     ebx, ebx
0x180018503  call    cs:__imp_GetLastError
0x180018509  xor     edx, edx
0x18001850b  test    eax, eax
0x18001850d  jg      short loc_180018513
0x18001850f  mov     ecx, eax
0x180018511  jmp     short loc_18001851C
0x180018513  movzx   ecx, ax
0x180018516  or      ecx, 80070000h
0x18001851c  mov     [rsp+0B8h+var_60], ecx; unsigned int
0x180018520  lea     r8, aStringcbcopyFa_0; "StringCbCopy failed, see additional inf"...
0x180018527  mov     [rsp+0B8h+var_68], eax; unsigned int
0x18001852b  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x180018532  mov     [rsp+0B8h+var_70], rbp; unsigned __int16 *
0x180018537  mov     r9, r12; unsigned __int16 *
0x18001853a  mov     [rsp+0B8h+var_78], edi; int
0x18001853e  mov     [rsp+0B8h+var_80], rdx; unsigned __int16 *
0x180018543  mov     [rsp+0B8h+var_88], rdx; unsigned __int16 *
0x180018548  mov     [rsp+0B8h+var_90], rdx; unsigned __int16 *
0x18001854d  mov     [rsp+0B8h+var_98], rdx; unsigned __int16 *
0x180018552  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x180018559  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001855e  mov     r11, [rsp+0B8h+hMem]
0x180018563  test    rsi, rsi
0x180018566  jz      short loc_18001856D
0x180018568  mov     word ptr [rsi], 2Ch ; ','
0x18001856d  mov     r12d, [rsp+0B8h+arg_0]
0x180018575  mov     eax, r12d
0x180018578  add     r12d, edi
0x18001857b  shl     rax, 9
0x18001857f  mov     [rsp+0B8h+arg_0], r12d
0x180018587  xor     r12d, r12d
0x18001858a  mov     [rax+r11+1FEh], r15w
0x180018593  test    ebx, ebx
0x180018595  jnz     loc_1800184A7
0x18001859b  jmp     short loc_180018616
0x18001859d  mov     ebx, r12d
0x1800185a0  call    cs:__imp_GetLastError
0x1800185a6  mov     esi, eax
0x1800185a8  call    cs:__imp_GetLastError
0x1800185ae  mov     r8, r14
0x1800185b1  lea     rdx, aStringFormatFo; "String format for core driver dependenc"...
0x1800185b8  mov     r9d, eax
0x1800185bb  mov     rcx, r13; char *
0x1800185be  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800185c3  test    esi, esi
0x1800185c5  jg      short loc_1800185CB
0x1800185c7  mov     ecx, esi
0x1800185c9  jmp     short loc_1800185D4
0x1800185cb  movzx   ecx, si
0x1800185ce  or      ecx, 80070000h
0x1800185d4  mov     [rsp+0B8h+var_60], ecx; unsigned int
0x1800185d8  lea     r8, aOneMissingComm_0; "One missing comma (2), see additional i"...
0x1800185df  mov     [rsp+0B8h+var_68], esi; unsigned int
0x1800185e3  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x1800185ea  mov     [rsp+0B8h+var_70], rbp; unsigned __int16 *
0x1800185ef  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800185f6  mov     [rsp+0B8h+var_78], edi; int
0x1800185fa  mov     r9, r14; unsigned __int16 *
0x1800185fd  mov     [rsp+0B8h+var_80], r12; unsigned __int16 *
0x180018602  mov     [rsp+0B8h+var_88], r12; unsigned __int16 *
0x180018607  mov     [rsp+0B8h+var_90], r12; unsigned __int16 *
0x18001860c  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x180018611  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180018616  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001861a  inc     rax
0x18001861d  cmp     [r14+rax*2], r12w
0x180018622  jnz     short loc_18001861A
0x180018624  lea     r14, [r14+rax*2]
0x180018628  add     r14, 2
0x18001862c  test    ebx, ebx
0x18001862e  jnz     loc_180018402
0x180018634  mov     rcx, [rsp+0B8h+hMem]; hMem
0x180018639  call    cs:__imp_LocalFree
0x18001863f  jmp     loc_1800187AE
0x180018644  mov     rcx, [rsp+0B8h+arg_20]
0x18001864c  mov     eax, [rsp+0B8h+var_58]
0x180018650  mov     [rcx], eax
0x180018652  mov     rcx, [rsp+0B8h+arg_18]
0x18001865a  mov     rax, [rsp+0B8h+hMem]
0x18001865f  mov     [rcx], rax
0x180018662  test    ebx, ebx
0x180018664  jz      loc_1800187AE
0x18001866a  lea     rdx, aAllCoreDriverS; "All core driver sections found."
0x180018671  mov     rcx, r13; char *
0x180018674  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180018679  mov     [rsp+0B8h+var_60], r12d; unsigned int
0x18001867e  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x180018685  mov     [rsp+0B8h+var_68], r12d; unsigned int
0x18001868a  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x180018691  mov     [rsp+0B8h+var_70], rbp; unsigned __int16 *
0x180018696  xor     r9d, r9d; unsigned __int16 *
0x180018699  mov     [rsp+0B8h+var_78], edi; int
0x18001869d  xor     r8d, r8d; unsigned __int16 *
0x1800186a0  mov     [rsp+0B8h+var_80], r12; unsigned __int16 *
0x1800186a5  mov     [rsp+0B8h+var_88], r12; unsigned __int16 *
0x1800186aa  mov     [rsp+0B8h+var_90], r12; unsigned __int16 *
0x1800186af  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x1800186b4  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x1800186b9  jmp     loc_1800187C6
0x1800186be  mov     ebx, r12d
0x1800186c1  call    cs:__imp_GetLastError
0x1800186c7  test    eax, eax
0x1800186c9  jg      short loc_1800186CF
0x1800186cb  mov     ecx, eax
0x1800186cd  jmp     short loc_1800186D8
0x1800186cf  movzx   ecx, ax
0x1800186d2  or      ecx, 80070000h
0x1800186d8  mov     [rsp+0B8h+var_60], ecx; unsigned int
0x1800186dc  lea     r8, aLocalallocmemF; "LocalAllocMem failed"
0x1800186e3  mov     [rsp+0B8h+var_68], eax; unsigned int
0x1800186e7  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x1800186ee  mov     [rsp+0B8h+var_70], rbp; unsigned __int16 *
0x1800186f3  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800186fa  mov     [rsp+0B8h+var_78], edi; int
0x1800186fe  xor     r9d, r9d; unsigned __int16 *
0x180018701  mov     [rsp+0B8h+var_80], r12; unsigned __int16 *
0x180018706  mov     [rsp+0B8h+var_88], r12; unsigned __int16 *
0x18001870b  mov     [rsp+0B8h+var_90], r12; unsigned __int16 *
0x180018710  mov     [rsp+0B8h+var_98], r12; unsigned __int16 *
0x180018715  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001871a  jmp     loc_1800187AE
0x18001871f  mov     r14d, 57h ; 'W'
0x180018725  mov     ecx, r14d; dwErrCode
0x180018728  call    cs:__imp_SetLastError
0x18001872e  mov     rax, [rsp+0B8h+arg_20]
0x180018736  lea     r13, aFindcoredriver_1; "FindCoreDriverSections"
0x18001873d  mov     [rsp+0B8h+var_88], rdi
  ... truncated ...
```
