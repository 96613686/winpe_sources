# SalvageRepository(void)

- ea: `0x180041230`
- end: `0x18004140d`
- name: `?SalvageRepository@@YAJXZ`
- size: `477`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x180013f90`
- `0x180029fbc`
- `0x1800405ec`
- `0x1800411c0`
- `0x180041230`
- `0x180048010`

## import_xrefs

- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800412c6`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x1800412c6`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041317`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004134c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800413e2`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x180041317`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x18004134c`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1800413e2`
- `wbemcomn!GetMemLogObject` at `0x180041257`
- `wbemcomn!GetMemLogObject` at `0x180041257`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041262`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x180041262`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800412f5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800412f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041385`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800413ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004136e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004136e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800413b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800412ab`

## pseudocode

```c
__int64 SalvageRepository(void)
{
  int MigrationHandle; // ebx
  CMemoryLog *MemLogObject; // rax
  __int64 result; // rax
  HMODULE v3; // rsi
  WCHAR *v4; // rax
  unsigned __int16 *v5; // rdi
  signed int v6; // eax
  int v7; // ebx
  FARPROC ProcAddress; // rax
  const unsigned __int16 *v9; // rcx
  signed int LastError; // eax
  FARPROC v11; // rax
  signed int v12; // eax
  CMemoryLog *v13; // rax
  _BYTE v14[8]; // [rsp+20h] [rbp-28h] BYREF
  BOOL (__stdcall *v15)(HMODULE); // [rsp+28h] [rbp-20h]
  HMODULE v16; // [rsp+30h] [rbp-18h]
  HMODULE hModule; // [rsp+50h] [rbp+8h] BYREF

  hModule = 0;
  try
  {
    MigrationHandle = GetMigrationHandle(&hModule);
    if ( MigrationHandle >= 0 )
    {
      v3 = hModule;
      v14[0] = 0;
      v15 = FreeLibrary;
      v16 = hModule;
      v4 = (WCHAR *)CWin32DefaultArena::WbemMemAlloc(0x214u);
      v5 = v4;
      if ( v4 )
      {
        hModule = (HMODULE)v4;
        if ( GetSystemDirectoryW(v4, 0x105u) )
        {
          v7 = StringCchCatW(v5, 0x10Au, L"\\WBEM");
          if ( v7 >= 0 )
          {
            ProcAddress = GetProcAddress(v3, "RebuildGather");
            if ( ProcAddress )
            {
              v7 = ((__int64 (__fastcall *)(unsigned __int16 *))ProcAddress)(v5);
            }
            else
            {
              LastError = GetLastError();
              v7 = LastError;
              if ( LastError > 0 )
                v7 = (unsigned __int16)LastError | 0x80070000;
            }
            if ( v7 >= 0 )
            {
              v7 = ResetRepository(v9);
              if ( v7 >= 0 )
              {
                v11 = GetProcAddress(v3, "RebuildApply");
                if ( v11 )
                {
                  v7 = ((__int64 (__fastcall *)(unsigned __int16 *))v11)(v5);
                }
                else
                {
                  v12 = GetLastError();
                  v7 = v12;
                  if ( v12 > 0 )
                    v7 = (unsigned __int16)v12 | 0x80070000;
                }
              }
            }
          }
        }
        else
        {
          v6 = GetLastError();
          v7 = v6;
          if ( v6 > 0 )
            v7 = (unsigned __int16)v6 | 0x80070000;
        }
        CWin32DefaultArena::WbemMemFree(v5);
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(v14);
        result = (unsigned int)v7;
      }
      else
      {
        ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(v14);
        result = 2147749894LL;
      }
    }
    else
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, MigrationHandle);
      if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_c47982387556333a241fa51fba0ef2c5_Traceguids,
          (unsigned int)MigrationHandle);
      }
      result = (unsigned int)MigrationHandle;
    }
  }
  catch ( CX_MemoryException )
  {
    v13 = GetMemLogObject();
    CMemoryLog::Write(v13, -2147217402);
    if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids, 2147749894LL);
    }
    return 2147749894LL;
  }
  MigrationHandle = GetMigrationHandle(&hModule);
}

```

## disassembly

```asm
0x180041230  mov     rax, rsp
0x180041233  mov     [rax+10h], rbx
0x180041237  mov     [rax+18h], rsi
0x18004123b  push    rdi
0x18004123c  sub     rsp, 40h
0x180041240  mov     qword ptr [rax+8], 0
0x180041248  lea     rcx, [rax+8]; HINSTANCE *
0x18004124c  call    ?GetMigrationHandle@@YAJAEAPEAUHINSTANCE__@@@Z; GetMigrationHandle(HINSTANCE__ * &)
0x180041251  mov     ebx, eax
0x180041253  test    eax, eax
0x180041255  jns     short loc_1800412A6
0x180041257  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18004125d  mov     edx, ebx
0x18004125f  mov     rcx, rax
0x180041262  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x180041268  lea     rax, WPP_GLOBAL_Control
0x18004126f  mov     rcx, cs:WPP_GLOBAL_Control
0x180041276  cmp     rcx, rax
0x180041279  jz      short loc_18004129F
0x18004127b  test    byte ptr [rcx+1Ch], 1
0x18004127f  jz      short loc_18004129F
0x180041281  cmp     byte ptr [rcx+19h], 2
0x180041285  jb      short loc_18004129F
0x180041287  mov     edx, 3Ch ; '<'
0x18004128c  mov     r9d, ebx
0x18004128f  lea     r8, WPP_c47982387556333a241fa51fba0ef2c5_Traceguids
0x180041296  mov     rcx, [rcx+10h]
0x18004129a  call    WPP_SF_d
0x18004129f  mov     eax, ebx
0x1800412a1  jmp     loc_1800413FC
0x1800412a6  mov     rsi, [rsp+48h+hModule]
0x1800412ab  mov     rax, cs:__imp_FreeLibrary
0x1800412b2  mov     [rsp+48h+var_28], 0
0x1800412b7  mov     [rsp+48h+var_20], rax
0x1800412bc  mov     [rsp+48h+var_18], rsi
0x1800412c1  mov     ecx, 214h
0x1800412c6  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x1800412cc  mov     rdi, rax
0x1800412cf  test    rax, rax
0x1800412d2  jnz     short loc_1800412E8
0x1800412d4  lea     rcx, [rsp+48h+var_28]
0x1800412d9  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x1800412de  mov     eax, 80041006h
0x1800412e3  jmp     loc_1800413FC
0x1800412e8  mov     [rsp+48h+hModule], rdi
0x1800412ed  mov     edx, 105h; uSize
0x1800412f2  mov     rcx, rdi; lpBuffer
0x1800412f5  call    cs:__imp_GetSystemDirectoryW
0x1800412fb  test    eax, eax
0x1800412fd  jnz     short loc_18004132F
0x1800412ff  call    cs:__imp_GetLastError
0x180041305  mov     ebx, eax
0x180041307  test    eax, eax
0x180041309  jle     short loc_180041314
0x18004130b  movzx   ebx, ax
0x18004130e  or      ebx, 80070000h
0x180041314  mov     rcx, rdi
0x180041317  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x18004131d  nop
0x18004131e  lea     rcx, [rsp+48h+var_28]
0x180041323  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x180041328  mov     eax, ebx
0x18004132a  jmp     loc_1800413FC
0x18004132f  lea     r8, aWbem; "\\WBEM"
0x180041336  mov     edx, 10Ah; unsigned __int64
0x18004133b  mov     rcx, rdi; unsigned __int16 *
0x18004133e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180041343  mov     ebx, eax
0x180041345  test    eax, eax
0x180041347  jns     short loc_180041364
0x180041349  mov     rcx, rdi
0x18004134c  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x180041352  nop
0x180041353  lea     rcx, [rsp+48h+var_28]
0x180041358  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x18004135d  mov     eax, ebx
0x18004135f  jmp     loc_1800413FC
0x180041364  lea     rdx, aRebuildgather; "RebuildGather"
0x18004136b  mov     rcx, rsi; hModule
0x18004136e  call    cs:__imp_GetProcAddress
0x180041374  test    rax, rax
0x180041377  jz      short loc_180041385
0x180041379  mov     rcx, rdi
0x18004137c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041381  mov     ebx, eax
0x180041383  jmp     short loc_18004139A
0x180041385  call    cs:__imp_GetLastError
0x18004138b  mov     ebx, eax
0x18004138d  test    eax, eax
0x18004138f  jle     short loc_18004139A
0x180041391  movzx   ebx, ax
0x180041394  or      ebx, 80070000h
0x18004139a  test    ebx, ebx
0x18004139c  js      short loc_1800413DF
0x18004139e  call    ?ResetRepository@@YAJXZ; ResetRepository(void)
0x1800413a3  mov     ebx, eax
0x1800413a5  test    eax, eax
0x1800413a7  js      short loc_1800413DF
0x1800413a9  lea     rdx, aRebuildapply; "RebuildApply"
0x1800413b0  mov     rcx, rsi; hModule
0x1800413b3  call    cs:__imp_GetProcAddress
0x1800413b9  test    rax, rax
0x1800413bc  jz      short loc_1800413CA
0x1800413be  mov     rcx, rdi
0x1800413c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413c6  mov     ebx, eax
0x1800413c8  jmp     short loc_1800413DF
0x1800413ca  call    cs:__imp_GetLastError
0x1800413d0  mov     ebx, eax
0x1800413d2  test    eax, eax
0x1800413d4  jle     short loc_1800413DF
0x1800413d6  movzx   ebx, ax
0x1800413d9  or      ebx, 80070000h
0x1800413df  mov     rcx, rdi
0x1800413e2  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1800413e8  nop
0x1800413e9  lea     rcx, [rsp+48h+var_28]
0x1800413ee  call    ??1?$ScopeGuardImpl1@P6AXPEAU_RTL_CRITICAL_SECTION@@@ZPEAU1@@@QEAA@XZ; ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>::~ScopeGuardImpl1<void (*)(_RTL_CRITICAL_SECTION *),_RTL_CRITICAL_SECTION *>(void)
0x1800413f3  mov     eax, ebx
0x1800413f5  jmp     short loc_1800413FC
0x1800413f7  mov     eax, 80041006h
0x1800413fc  mov     rbx, [rsp+48h+arg_8]
0x180041401  mov     rsi, [rsp+48h+arg_10]
0x180041406  add     rsp, 40h
0x18004140a  pop     rdi
0x18004140b  retn
```
