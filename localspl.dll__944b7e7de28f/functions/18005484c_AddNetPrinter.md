# AddNetPrinter

- ea: `0x18005484c`
- end: `0x180054a9f`
- name: `AddNetPrinter`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18004fe9c`

## callees

- `0x18000ea40`
- `0x18002db3c`
- `0x18003ea2c`
- `0x180054638`
- `0x18005484c`
- `0x180055a18`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a8c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a4d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a66`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a8c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054915`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054a58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054915`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180054a58`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180054a1d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180054a1d`
- `SPOOLSS!DllFreeSplStr` at `0x1800549ed`
- `SPOOLSS!DllFreeSplStr` at `0x1800549f7`
- `SPOOLSS!DllFreeSplStr` at `0x180054a01`
- `SPOOLSS!DllFreeSplStr` at `0x1800549ed`
- `SPOOLSS!DllFreeSplStr` at `0x1800549f7`
- `SPOOLSS!DllFreeSplStr` at `0x180054a01`
- `SPOOLSS!DllFreeSplMem` at `0x180054a0a`
- `SPOOLSS!DllFreeSplMem` at `0x180054a0a`
- `SPOOLSS!DllAllocSplMem` at `0x18005498b`
- `SPOOLSS!DllAllocSplMem` at `0x18005498b`
- `SPOOLSS!AllocSplStr` at `0x1800549a7`
- `SPOOLSS!AllocSplStr` at `0x1800549b5`
- `SPOOLSS!AllocSplStr` at `0x1800549c3`
- `SPOOLSS!AllocSplStr` at `0x1800549a7`
- `SPOOLSS!AllocSplStr` at `0x1800549b5`
- `SPOOLSS!AllocSplStr` at `0x1800549c3`

## string_xrefs

- `0x180054882`: `Trying to install printer %ws but installation of printer connections is not allowed in ContainerOS`

## pseudocode

```c
__int64 __fastcall AddNetPrinter(__int64 a1)
{
  struct _INISPOOLER *v1; // rbp
  const unsigned __int16 *v3; // r8
  DWORD v4; // ecx
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rsi
  __int64 v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax

  v1 = pLocalIniSpooler;
  if ( (unsigned int)RunningInContainerOS() )
  {
    if ( !a1 || (v3 = *(const unsigned __int16 **)(a1 + 16)) == 0 )
      v3 = &qword_1800EBF90;
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "AddNetPrinter",
      L"Trying to install printer %ws but installation of printer connections is not allowed in ContainerOS",
      v3);
    v4 = 50;
    goto LABEL_42;
  }
  v5 = *(_QWORD *)(a1 + 16);
  if ( !v5 )
    goto LABEL_41;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( *(_WORD *)(v5 + 2 * v7) );
  if ( v7 > 0x207 )
    goto LABEL_41;
  v8 = *(_QWORD *)(a1 + 24);
  if ( v8 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(v8 + 2 * v9) );
    if ( v9 > 0x104 )
      goto LABEL_41;
  }
  v10 = *(_QWORD *)(a1 + 8);
  if ( v10 )
  {
    do
      ++v6;
    while ( *(_WORD *)(v10 + 2 * v6) );
    if ( v6 > 0x411 )
    {
LABEL_41:
      LocalSpoolerTelemetry::WriteDbgTraceWarning("AddNetPrinter", L"Invalid PRINTER_INFO_1 data.  Failing call.");
      v4 = 123;
      goto LABEL_42;
    }
  }
  if ( !FirstAddNetPrinterTickCount )
    FirstAddNetPrinterTickCount = GetTickCount();
  RemoveOldNetPrinters(a1, v1);
  if ( (*(_DWORD *)a1 & 0x18) == 0x10 )
  {
    v4 = 1802;
LABEL_42:
    SetLastError(v4);
    return 0;
  }
  v11 = (__int64)v1 + 80;
  v12 = *((_QWORD *)v1 + 10);
  if ( v12 )
  {
    while ( *(_QWORD *)(v12 + 32) )
    {
      if ( (unsigned int)FastStrcmpi(*(LPCWSTR *)(a1 + 16)) )
      {
        v12 = *(_QWORD *)(v12 + 8);
        if ( v12 )
          continue;
      }
      if ( v12 )
        goto LABEL_40;
      goto LABEL_26;
    }
    goto LABEL_40;
  }
LABEL_26:
  if ( *((_DWORD *)v1 + 78) >= 0x100u )
  {
    SetLastError(0xEu);
    return 0;
  }
  v13 = DllAllocSplMem(48);
  v12 = v13;
  if ( v13 )
  {
    *(_DWORD *)v13 = 18767;
    *(_QWORD *)(v13 + 32) = AllocSplStr(*(_QWORD *)(a1 + 16));
    *(_QWORD *)(v12 + 24) = AllocSplStr(*(_QWORD *)(a1 + 8));
    v14 = AllocSplStr(*(_QWORD *)(a1 + 24));
    *(_QWORD *)(v12 + 40) = v14;
    if ( *(_QWORD *)(v12 + 32) && (!*(_QWORD *)(a1 + 8) || *(_QWORD *)(v12 + 24)) && (!*(_QWORD *)(a1 + 24) || v14) )
    {
      while ( *(_QWORD *)v11 && lstrcmpW(*(LPCWSTR *)(*(_QWORD *)v11 + 32LL), *(LPCWSTR *)(v12 + 32)) < 0 )
        v11 = *(_QWORD *)v11 + 8LL;
      *(_QWORD *)(v12 + 8) = *(_QWORD *)v11;
      *(_QWORD *)v11 = v12;
      ++*((_DWORD *)v1 + 78);
LABEL_40:
      *(_DWORD *)(v12 + 16) = GetTickCount();
      SetLastError(0x70Au);
      ++*((_DWORD *)v1 + 51);
      return 0;
    }
    DllFreeSplStr(v14);
    DllFreeSplStr(*(_QWORD *)(v12 + 24));
    DllFreeSplStr(*(_QWORD *)(v12 + 32));
    DllFreeSplMem(v12);
  }
  return 0;
}

```

## disassembly

```asm
0x18005484c  push    rbx
0x18005484e  push    rbp
0x18005484f  push    rsi
0x180054850  push    rdi
0x180054851  push    r14
0x180054853  sub     rsp, 20h
0x180054857  mov     rbp, cs:pLocalIniSpooler
0x18005485e  mov     rdi, rcx
0x180054861  call    ?RunningInContainerOS@@YAHXZ; RunningInContainerOS(void)
0x180054866  xor     r14d, r14d
0x180054869  test    eax, eax
0x18005486b  jz      short loc_18005489F
0x18005486d  test    rdi, rdi
0x180054870  jz      short loc_18005487B
0x180054872  mov     r8, [rdi+10h]
0x180054876  test    r8, r8
0x180054879  jnz     short loc_180054882
0x18005487b  lea     r8, qword_1800EBF90
0x180054882  lea     rdx, aTryingToInstal_0; "Trying to install printer %ws but insta"...
0x180054889  lea     rcx, aAddnetprinter; "AddNetPrinter"
0x180054890  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180054895  mov     ecx, 32h ; '2'
0x18005489a  jmp     loc_180054A8C
0x18005489f  mov     rdx, [rdi+10h]
0x1800548a3  test    rdx, rdx
0x1800548a6  jz      loc_180054A74
0x1800548ac  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800548b0  mov     rcx, rax
0x1800548b3  inc     rcx
0x1800548b6  cmp     [rdx+rcx*2], r14w
0x1800548bb  jnz     short loc_1800548B3
0x1800548bd  cmp     rcx, 207h
0x1800548c4  ja      loc_180054A74
0x1800548ca  mov     rdx, [rdi+18h]
0x1800548ce  test    rdx, rdx
0x1800548d1  jz      short loc_1800548ED
0x1800548d3  mov     rcx, rax
0x1800548d6  inc     rcx
0x1800548d9  cmp     [rdx+rcx*2], r14w
0x1800548de  jnz     short loc_1800548D6
0x1800548e0  cmp     rcx, 104h
0x1800548e7  ja      loc_180054A74
0x1800548ed  mov     rcx, [rdi+8]
0x1800548f1  test    rcx, rcx
0x1800548f4  jz      short loc_18005490C
0x1800548f6  inc     rax
0x1800548f9  cmp     [rcx+rax*2], r14w
0x1800548fe  jnz     short loc_1800548F6
0x180054900  cmp     rax, 411h
0x180054906  ja      loc_180054A74
0x18005490c  cmp     cs:FirstAddNetPrinterTickCount, r14d
0x180054913  jnz     short loc_180054921
0x180054915  call    cs:__imp_GetTickCount
0x18005491b  mov     cs:FirstAddNetPrinterTickCount, eax
0x180054921  mov     rdx, rbp
0x180054924  mov     rcx, rdi
0x180054927  call    RemoveOldNetPrinters
0x18005492c  mov     eax, [rdi]
0x18005492e  and     al, 18h
0x180054930  cmp     al, 10h
0x180054932  jnz     short loc_18005493E
0x180054934  mov     ecx, 70Ah
0x180054939  jmp     loc_180054A8C
0x18005493e  lea     rsi, [rbp+50h]
0x180054942  mov     rbx, [rsi]
0x180054945  test    rbx, rbx
0x180054948  jz      short loc_180054976
0x18005494a  mov     rdx, [rbx+20h]
0x18005494e  test    rdx, rdx
0x180054951  jz      loc_180054A58
0x180054957  mov     rcx, [rdi+10h]; lpString1
0x18005495b  call    FastStrcmpi
0x180054960  test    eax, eax
0x180054962  jz      short loc_18005496D
0x180054964  mov     rbx, [rbx+8]
0x180054968  test    rbx, rbx
0x18005496b  jnz     short loc_18005494A
0x18005496d  test    rbx, rbx
0x180054970  jnz     loc_180054A58
0x180054976  cmp     dword ptr [rbp+138h], 100h
0x180054980  jnb     loc_180054A48
0x180054986  mov     ecx, 30h ; '0'
0x18005498b  call    cs:__imp_DllAllocSplMem
0x180054991  mov     rbx, rax
0x180054994  test    rax, rax
0x180054997  jz      loc_180054A92
0x18005499d  mov     dword ptr [rax], 494Fh
0x1800549a3  mov     rcx, [rdi+10h]
0x1800549a7  call    cs:__imp_AllocSplStr
0x1800549ad  mov     [rbx+20h], rax
0x1800549b1  mov     rcx, [rdi+8]
0x1800549b5  call    cs:__imp_AllocSplStr
0x1800549bb  mov     [rbx+18h], rax
0x1800549bf  mov     rcx, [rdi+18h]
0x1800549c3  call    cs:__imp_AllocSplStr
0x1800549c9  mov     [rbx+28h], rax
0x1800549cd  cmp     [rbx+20h], r14
0x1800549d1  jz      short loc_1800549EA
0x1800549d3  cmp     [rdi+8], r14
0x1800549d7  jz      short loc_1800549DF
0x1800549d9  cmp     [rbx+18h], r14
0x1800549dd  jz      short loc_1800549EA
0x1800549df  cmp     [rdi+18h], r14
0x1800549e3  jz      short loc_180054A2E
0x1800549e5  test    rax, rax
0x1800549e8  jnz     short loc_180054A2E
0x1800549ea  mov     rcx, rax
0x1800549ed  call    cs:__imp_DllFreeSplStr
0x1800549f3  mov     rcx, [rbx+18h]
0x1800549f7  call    cs:__imp_DllFreeSplStr
0x1800549fd  mov     rcx, [rbx+20h]
0x180054a01  call    cs:__imp_DllFreeSplStr
0x180054a07  mov     rcx, rbx
0x180054a0a  call    cs:__imp_DllFreeSplMem
0x180054a10  mov     rbx, r14
0x180054a13  jmp     short loc_180054A53
0x180054a15  mov     rdx, [rbx+20h]; lpString2
0x180054a19  mov     rcx, [rax+20h]; lpString1
0x180054a1d  call    cs:__imp_lstrcmpW
0x180054a23  test    eax, eax
0x180054a25  jns     short loc_180054A36
0x180054a27  mov     rsi, [rsi]
0x180054a2a  add     rsi, 8
0x180054a2e  mov     rax, [rsi]
0x180054a31  test    rax, rax
0x180054a34  jnz     short loc_180054A15
0x180054a36  mov     rax, [rsi]
0x180054a39  mov     [rbx+8], rax
0x180054a3d  mov     [rsi], rbx
0x180054a40  inc     dword ptr [rbp+138h]
0x180054a46  jmp     short loc_180054A58
0x180054a48  mov     ecx, 0Eh; dwErrCode
0x180054a4d  call    cs:__imp_SetLastError
0x180054a53  test    rbx, rbx
0x180054a56  jz      short loc_180054A92
0x180054a58  call    cs:__imp_GetTickCount
0x180054a5e  mov     ecx, 70Ah; dwErrCode
0x180054a63  mov     [rbx+10h], eax
0x180054a66  call    cs:__imp_SetLastError
0x180054a6c  inc     dword ptr [rbp+0CCh]
0x180054a72  jmp     short loc_180054A92
0x180054a74  lea     rdx, aInvalidPrinter_0; "Invalid PRINTER_INFO_1 data.  Failing c"...
0x180054a7b  lea     rcx, aAddnetprinter; "AddNetPrinter"
0x180054a82  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180054a87  mov     ecx, 7Bh ; '{'; dwErrCode
0x180054a8c  call    cs:__imp_SetLastError
0x180054a92  xor     eax, eax
0x180054a94  add     rsp, 20h
0x180054a98  pop     r14
0x180054a9a  pop     rdi
0x180054a9b  pop     rsi
0x180054a9c  pop     rbp
0x180054a9d  pop     rbx
0x180054a9e  retn
```
