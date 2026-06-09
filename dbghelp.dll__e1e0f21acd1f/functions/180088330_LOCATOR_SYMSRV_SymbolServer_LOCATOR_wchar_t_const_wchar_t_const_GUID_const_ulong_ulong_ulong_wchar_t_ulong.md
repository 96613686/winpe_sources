# LOCATOR::SYMSRV::SymbolServer(LOCATOR *,wchar_t const *,wchar_t const *,_GUID const *,ulong,ulong,ulong,wchar_t *,ulong *)

- ea: `0x180088330`
- end: `0x180088586`
- name: `?SymbolServer@SYMSRV@LOCATOR@@QEAA_NPEAV2@PEB_W1PEBU_GUID@@KKKPEA_WPEAK@Z`
- size: `598`
- prototype: `bool(LOCATOR::SYMSRV *__hidden this, struct LOCATOR *, const wchar_t *, const wchar_t *, const struct _GUID *, unsigned int, unsigned int, unsigned int, wchar_t *, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180085360`
- `0x1800859f0`
- `0x180086bc0`

## callees

- `0x180029d00`
- `0x180088330`
- `0x1801d6350`
- `0x1801d63b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800883aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800883aa`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800884d3`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1800884d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008854c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008854c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800883d7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800883d7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008844a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008844a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800883f6`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800883f6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180088410`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180088425`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008843a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180088410`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180088425`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18008843a`

## string_xrefs

- `0x1800883ef`: `SYMSRV.DLL`
- `0x1800883a3`: `SYMSRV.DLL*`

## pseudocode

```c
char __fastcall LOCATOR::SYMSRV::SymbolServer(
        LOCATOR::SYMSRV *this,
        struct LOCATOR *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const struct _GUID *a5,
        unsigned int a6,
        unsigned int a7,
        unsigned int a8,
        wchar_t *a9,
        unsigned int *a10)
{
  const struct _GUID *v11; // rbp
  __int64 v14; // rsi
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  HMODULE v17; // rcx
  FARPROC v18; // rax
  HMODULE v19; // rcx
  void (__fastcall *v20)(__int64, __int64); // rax
  wchar_t Ext[256]; // [rsp+50h] [rbp-848h] BYREF
  wchar_t Filename[256]; // [rsp+250h] [rbp-648h] BYREF
  wchar_t Buffer[512]; // [rsp+450h] [rbp-448h] BYREF

  v11 = a5;
  if ( a3[3] == 42 )
  {
    v14 = 4;
  }
  else if ( a3[6] == 42 )
  {
    if ( (unsigned int)_o__wcsnicmp(a3 + 7, L"SYMSRV.DLL*", 11) )
      return 0;
    v14 = 18;
  }
  else
  {
    if ( a3[5] != 42 )
      return 0;
    v14 = 6;
  }
  EnterCriticalSection(&LOCATOR::SYMSRV::m_cs);
  if ( !*((_BYTE *)this + 8) )
  {
    *((_BYTE *)this + 8) = 1;
    Library = LoadLibraryExW(L"SYMSRV.DLL", 0, 0x1000u);
    if ( (unsigned __int64)Library >= 0x20 )
    {
      *((_QWORD *)this + 2) = Library;
      ProcAddress = GetProcAddress(Library, "SymbolServerW");
      v17 = (HMODULE)*((_QWORD *)this + 2);
      *((_QWORD *)this + 3) = ProcAddress;
      v18 = GetProcAddress(v17, "SymbolServerSetOptions");
      v19 = (HMODULE)*((_QWORD *)this + 2);
      *((_QWORD *)this + 4) = v18;
      *(_QWORD *)this = GetProcAddress(v19, "SymbolServerStoreFileW");
    }
  }
  LeaveCriticalSection(&LOCATOR::SYMSRV::m_cs);
  if ( !*((_QWORD *)this + 3) )
    return 0;
  v20 = (void (__fastcall *)(__int64, __int64))*((_QWORD *)this + 4);
  if ( a5 )
  {
    if ( !v20 )
      return 0;
    v20(8, 1);
  }
  else
  {
    if ( v20 )
      v20(2, 1);
    v11 = (const struct _GUID *)a6;
  }
  _wsplitpath_s(a4, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  snwprintf_s(Buffer, 0x1FFu, 0xFFFFFFFFFFFFFFFFuLL, L"%s%s", Filename, Ext);
  if ( (*((unsigned int (__fastcall **)(const wchar_t *, wchar_t *, const struct _GUID *, _QWORD, unsigned int, wchar_t *))this
        + 3))(
         &a3[v14],
         Buffer,
         v11,
         a7,
         a8,
         a9) )
  {
    *a10 = 0;
    return 1;
  }
  *a10 = GetLastError();
  *a9 = 0;
  return 0;
}

```

## disassembly

```asm
0x180088330  mov     [rsp+arg_8], rbx
0x180088335  push    rbp
0x180088336  push    rsi
0x180088337  push    rdi
0x180088338  push    r12
0x18008833a  push    r13
0x18008833c  push    r14
0x18008833e  push    r15
0x180088340  sub     rsp, 860h
0x180088347  mov     rax, cs:__security_cookie
0x18008834e  xor     rax, rsp
0x180088351  mov     [rsp+898h+var_48], rax
0x180088359  cmp     word ptr [r8+6], 2Ah ; '*'
0x18008835f  mov     r13, r9
0x180088362  mov     rbp, [rsp+898h+arg_20]
0x18008836a  mov     rdi, r8
0x18008836d  mov     r12d, [rsp+898h+arg_28]
0x180088375  mov     rbx, rcx
0x180088378  mov     r15, [rsp+898h+arg_40]
0x180088380  mov     r14, [rsp+898h+arg_48]
0x180088388  jnz     short loc_180088391
0x18008838a  mov     esi, 8
0x18008838f  jmp     short loc_1800883D0
0x180088391  cmp     word ptr [r8+0Ch], 2Ah ; '*'
0x180088397  jnz     short loc_1800883BF
0x180088399  lea     rcx, [r8+0Eh]
0x18008839d  mov     r8d, 0Bh
0x1800883a3  lea     rdx, aSymsrvDll_0; "SYMSRV.DLL*"
0x1800883aa  call    cs:__imp__o__wcsnicmp
0x1800883b0  test    eax, eax
0x1800883b2  jnz     loc_180088559
0x1800883b8  mov     esi, 24h ; '$'
0x1800883bd  jmp     short loc_1800883D0
0x1800883bf  cmp     word ptr [r8+0Ah], 2Ah ; '*'
0x1800883c5  jnz     loc_180088559
0x1800883cb  mov     esi, 0Ch
0x1800883d0  lea     rcx, ?m_cs@SYMSRV@LOCATOR@@0VCriticalSectionNoLog@@A; lpCriticalSection
0x1800883d7  call    cs:__imp_EnterCriticalSection
0x1800883dd  cmp     byte ptr [rbx+8], 0
0x1800883e1  jnz     short loc_180088443
0x1800883e3  xor     edx, edx; hFile
0x1800883e5  mov     byte ptr [rbx+8], 1
0x1800883e9  mov     r8d, 1000h; dwFlags
0x1800883ef  lea     rcx, aSymsrvDll; "SYMSRV.DLL"
0x1800883f6  call    cs:__imp_LoadLibraryExW
0x1800883fc  cmp     rax, 20h ; ' '
0x180088400  jb      short loc_180088443
0x180088402  lea     rdx, aSymbolserverw; "SymbolServerW"
0x180088409  mov     [rbx+10h], rax
0x18008840d  mov     rcx, rax; hModule
0x180088410  call    cs:__imp_GetProcAddress
0x180088416  mov     rcx, [rbx+10h]; hModule
0x18008841a  lea     rdx, aSymbolserverse_0; "SymbolServerSetOptions"
0x180088421  mov     [rbx+18h], rax
0x180088425  call    cs:__imp_GetProcAddress
0x18008842b  mov     rcx, [rbx+10h]; hModule
0x18008842f  lea     rdx, aSymbolserverst; "SymbolServerStoreFileW"
0x180088436  mov     [rbx+20h], rax
0x18008843a  call    cs:__imp_GetProcAddress
0x180088440  mov     [rbx], rax
0x180088443  lea     rcx, ?m_cs@SYMSRV@LOCATOR@@0VCriticalSectionNoLog@@A; lpCriticalSection
0x18008844a  call    cs:__imp_LeaveCriticalSection
0x180088450  cmp     qword ptr [rbx+18h], 0
0x180088455  jz      loc_180088559
0x18008845b  mov     rax, [rbx+20h]
0x18008845f  test    rbp, rbp
0x180088462  jz      short loc_18008847F
0x180088464  test    rax, rax
0x180088467  jz      loc_180088559
0x18008846d  mov     edx, 1
0x180088472  mov     ecx, 8
0x180088477  call    cs:__guard_dispatch_icall_fptr
0x18008847d  jmp     short loc_180088497
0x18008847f  test    rax, rax
0x180088482  jz      short loc_180088494
0x180088484  mov     edx, 1
0x180088489  mov     ecx, 2
0x18008848e  call    cs:__guard_dispatch_icall_fptr
0x180088494  mov     rbp, r12
0x180088497  mov     [rsp+898h+ExtCount], 100h; ExtCount
0x1800884a0  lea     rax, [rsp+898h+var_848]
0x1800884a5  mov     [rsp+898h+Ext], rax; Ext
0x1800884aa  xor     r12d, r12d
0x1800884ad  lea     rax, [rsp+898h+var_648]
0x1800884b5  mov     [rsp+898h+FilenameCount], 100h; FilenameCount
0x1800884be  mov     [rsp+898h+Filename], rax; Filename
0x1800884c3  xor     r9d, r9d; Dir
0x1800884c6  xor     r8d, r8d; DriveCount
0x1800884c9  mov     [rsp+898h+DirCount], r12; DirCount
0x1800884ce  xor     edx, edx; Drive
0x1800884d0  mov     rcx, r13; FullPath
0x1800884d3  call    cs:__imp__wsplitpath_s
0x1800884d9  lea     rax, [rsp+898h+var_848]
0x1800884de  mov     edx, 1FFh; BufferCount
0x1800884e3  mov     [rsp+898h+Filename], rax
0x1800884e8  lea     r9, aSS_3; "%s%s"
0x1800884ef  lea     rax, [rsp+898h+var_648]
0x1800884f7  mov     r8, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800884fe  lea     rcx, [rsp+898h+Buffer]; Buffer
0x180088506  mov     [rsp+898h+DirCount], rax
0x18008850b  call    _snwprintf_s
0x180088510  mov     edx, [rsp+898h+arg_38]
0x180088517  lea     rcx, [rsi+rdi]
0x18008851b  mov     r9d, [rsp+898h+arg_30]
0x180088523  mov     r8, rbp
0x180088526  mov     rax, [rbx+18h]
0x18008852a  mov     [rsp+898h+Filename], r15
0x18008852f  mov     dword ptr [rsp+898h+DirCount], edx
0x180088533  lea     rdx, [rsp+898h+Buffer]
0x18008853b  call    cs:__guard_dispatch_icall_fptr
0x180088541  test    eax, eax
0x180088543  jz      short loc_18008854C
0x180088545  mov     [r14], r12d
0x180088548  mov     al, 1
0x18008854a  jmp     short loc_18008855B
0x18008854c  call    cs:__imp_GetLastError
0x180088552  mov     [r14], eax
0x180088555  mov     [r15], r12w
0x180088559  xor     al, al
0x18008855b  mov     rcx, [rsp+898h+var_48]
0x180088563  xor     rcx, rsp; StackCookie
0x180088566  call    __security_check_cookie
0x18008856b  mov     rbx, [rsp+898h+arg_8]
0x180088573  add     rsp, 860h
0x18008857a  pop     r15
0x18008857c  pop     r14
0x18008857e  pop     r13
0x180088580  pop     r12
0x180088582  pop     rdi
0x180088583  pop     rsi
0x180088584  pop     rbp
0x180088585  retn
```
