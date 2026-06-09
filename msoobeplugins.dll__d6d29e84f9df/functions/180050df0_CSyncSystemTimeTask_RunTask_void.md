# CSyncSystemTimeTask::RunTask(void)

- ea: `0x180050df0`
- end: `0x180050fb4`
- name: `?RunTask@CSyncSystemTimeTask@@UEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CSyncSystemTimeTask *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18000ac48`
- `0x180018a04`
- `0x180019140`
- `0x1800196f0`
- `0x180046c9c`
- `0x180050df0`
- `0x1800b8834`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050ea6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180050ea6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050ebb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180050ebb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050f0e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180050f0e`

## string_xrefs

- `0x180050e1a`: `System\CurrentControlSet\services\W32Time\Config`
- `0x180050e30`: `System\CurrentControlSet\services\W32Time\Config`
- `0x180050f21`: `Successfully attempted syncing the system clock with the w32time service.`
- `0x180050eeb`: `Failed to sync the system clock with the w32time service on attempt %d [dwResyncResult=0x%08X]`
- `0x180050e9a`: `w32time.dll`
- `0x180050f95`: `Failed to set the global settings cache timesync setting [hr=0x%08X]`
- `0x180050f34`: `Failed to sync the system clock with the w32time service [dwResyncResult=0x%08X, hr=0x%08X]`

## pseudocode

```c
// Hidden C++ exception states: #wind=29
__int64 __fastcall CSyncSystemTimeTask::RunTask(CSyncSystemTimeTask *this)
{
  int v2; // eax
  int Error; // edi
  bool v4; // r9
  unsigned int v5; // r14d
  HMODULE Library; // rax
  HMODULE v7; // rbp
  FARPROC ProcAddress; // r15
  unsigned int i; // esi
  unsigned int v10; // eax
  __int64 v11; // rcx
  int v12; // eax
  __int128 v14; // [rsp+30h] [rbp-58h] BYREF
  __int64 v15; // [rsp+40h] [rbp-48h]

  SHRegGetDWORD(
    HKEY_LOCAL_MACHINE,
    L"System\\CurrentControlSet\\services\\W32Time\\Config",
    L"SpikeWatchPeriod",
    (unsigned int *)this + 140);
  v2 = SHRegSetDWORD(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\services\\W32Time\\Config",
         L"SpikeWatchPeriod",
         0);
  Error = v2;
  if ( v2 < 0 )
  {
    UnattendLogW(1, L"Failed to set w32time spikewatchperiod to 0 [hr=0x%08X]", (unsigned int)v2);
    Error = 0;
  }
  else
  {
    *((_BYTE *)this + 564) = 1;
  }
  if ( (int)OOBEStartService(L"w32time", 0) < 0 )
  {
    OOBEServiceHelper::_ControlService(L"w32time", 1u, 1u, v4, 0);
    OOBEStartService(L"w32time", 1);
  }
  v5 = 0;
  Library = LoadLibraryExW(L"w32time.dll", 0, 0);
  v7 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      for ( i = 0;
            i < 5;
            UnattendLogW(
              2,
              L"Failed to sync the system clock with the w32time service on attempt %d [dwResyncResult=0x%08X]",
              i,
              v10) )
      {
        v10 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
        v5 = v10;
        if ( !v10 )
          break;
        ++i;
      }
    }
    else
    {
      Error = ResultFromKnownLastError();
    }
    FreeLibrary(v7);
  }
  else
  {
    Error = ResultFromKnownLastError();
  }
  if ( Error < 0 )
    UnattendLogW(
      2,
      L"Failed to sync the system clock with the w32time service [dwResyncResult=0x%08X, hr=0x%08X]",
      v5,
      (unsigned int)Error);
  else
    UnattendLogW(0, L"Successfully attempted syncing the system clock with the w32time service.");
  v11 = *((_QWORD *)this + 69);
  v15 = 0;
  v14 = 0;
  LOWORD(v14) = 19;
  DWORD2(v14) = ((Error >> 31) & 1) + 2;
  v12 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int128 *))(*(_QWORD *)v11 + 32LL))(
          v11,
          L"TIMESYNCSTATUS",
          &v14);
  if ( v12 < 0 )
    UnattendLogW(1, L"Failed to set the global settings cache timesync setting [hr=0x%08X]", (unsigned int)v12);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180050df0  push    rbx
0x180050df2  push    rbp
0x180050df3  push    rsi
0x180050df4  push    rdi
0x180050df5  push    r13
0x180050df7  push    r14
0x180050df9  push    r15
0x180050dfb  sub     rsp, 50h
0x180050dff  mov     r13, rcx
0x180050e02  lea     r9, [rcx+230h]; unsigned int *
0x180050e09  mov     rbx, 0FFFFFFFF80000002h
0x180050e10  lea     r8, aSpikewatchperi; "SpikeWatchPeriod"
0x180050e17  mov     rcx, rbx; HKEY
0x180050e1a  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\services\\W3"...
0x180050e21  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180050e26  xor     r9d, r9d; unsigned int
0x180050e29  lea     r8, aSpikewatchperi; "SpikeWatchPeriod"
0x180050e30  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\services\\W3"...
0x180050e37  mov     rcx, rbx; HKEY
0x180050e3a  call    ?SHRegSetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; SHRegSetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x180050e3f  mov     edi, eax
0x180050e41  mov     ebx, 1
0x180050e46  test    eax, eax
0x180050e48  js      short loc_180050E53
0x180050e4a  mov     [r13+234h], bl
0x180050e51  jmp     short loc_180050E66
0x180050e53  mov     r8d, eax
0x180050e56  lea     rdx, aFailedToSetW32; "Failed to set w32time spikewatchperiod "...
0x180050e5d  mov     ecx, ebx
0x180050e5f  call    UnattendLogW
0x180050e64  xor     edi, edi
0x180050e66  lea     rsi, aW32time; "w32time"
0x180050e6d  xor     edx, edx; bool
0x180050e6f  mov     rcx, rsi; unsigned __int16 *
0x180050e72  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x180050e77  test    eax, eax
0x180050e79  jns     short loc_180050E97
0x180050e7b  mov     r8d, ebx; unsigned int
0x180050e7e  mov     [rsp+88h+var_68], 0; bool
0x180050e83  mov     edx, ebx; dwControl
0x180050e85  mov     rcx, rsi; unsigned __int16 *
0x180050e88  call    ?_ControlService@OOBEServiceHelper@@CAJPEBGKK_N1@Z; OOBEServiceHelper::_ControlService(ushort const *,ulong,ulong,bool,bool)
0x180050e8d  mov     dl, bl; bool
0x180050e8f  mov     rcx, rsi; unsigned __int16 *
0x180050e92  call    ?OOBEStartService@@YAJPEBG_N@Z; OOBEStartService(ushort const *,bool)
0x180050e97  xor     r8d, r8d; dwFlags
0x180050e9a  lea     rcx, aW32timeDll; "w32time.dll"
0x180050ea1  xor     edx, edx; hFile
0x180050ea3  xor     r14d, r14d
0x180050ea6  call    cs:__imp_LoadLibraryExW
0x180050eac  mov     rbp, rax
0x180050eaf  test    rax, rax
0x180050eb2  jz      short loc_180050F16
0x180050eb4  lea     edx, [r14+19h]; lpProcName
0x180050eb8  mov     rcx, rax; hModule
0x180050ebb  call    cs:__imp_GetProcAddress
0x180050ec1  mov     r15, rax
0x180050ec4  test    rax, rax
0x180050ec7  jz      short loc_180050F04
0x180050ec9  xor     esi, esi
0x180050ecb  cmp     esi, 5
0x180050ece  jnb     short loc_180050F0B
0x180050ed0  mov     r8d, 12h
0x180050ed6  mov     edx, ebx
0x180050ed8  xor     ecx, ecx
0x180050eda  mov     rax, r15
0x180050edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ee2  mov     r14d, eax
0x180050ee5  test    eax, eax
0x180050ee7  jz      short loc_180050F0B
0x180050ee9  add     esi, ebx
0x180050eeb  lea     rdx, aFailedToSyncTh_0; "Failed to sync the system clock with th"...
0x180050ef2  mov     r8d, esi
0x180050ef5  mov     r9d, eax
0x180050ef8  mov     ecx, 2
0x180050efd  call    UnattendLogW
0x180050f02  jmp     short loc_180050ECB
0x180050f04  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180050f09  mov     edi, eax
0x180050f0b  mov     rcx, rbp; hLibModule
0x180050f0e  call    cs:__imp_FreeLibrary
0x180050f14  jmp     short loc_180050F1D
0x180050f16  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180050f1b  mov     edi, eax
0x180050f1d  test    edi, edi
0x180050f1f  js      short loc_180050F31
0x180050f21  lea     rdx, aSuccessfullyAt; "Successfully attempted syncing the syst"...
0x180050f28  xor     ecx, ecx
0x180050f2a  call    UnattendLogW
0x180050f2f  jmp     short loc_180050F48
0x180050f31  mov     r9d, edi
0x180050f34  lea     rdx, aFailedToSyncTh; "Failed to sync the system clock with th"...
0x180050f3b  mov     r8d, r14d
0x180050f3e  mov     ecx, 2
0x180050f43  call    UnattendLogW
0x180050f48  mov     rcx, [r13+228h]
0x180050f4f  lea     r8, [rsp+88h+var_58]
0x180050f54  xor     eax, eax
0x180050f56  lea     rdx, aTimesyncstatus; "TIMESYNCSTATUS"
0x180050f5d  mov     [rsp+88h+var_48], rax
0x180050f62  xorps   xmm0, xmm0
0x180050f65  mov     eax, 13h
0x180050f6a  movups  [rsp+88h+var_58], xmm0
0x180050f6f  mov     word ptr [rsp+88h+var_58], ax
0x180050f74  mov     eax, edi
0x180050f76  sar     eax, 1Fh
0x180050f79  and     eax, ebx
0x180050f7b  add     eax, 2
0x180050f7e  mov     dword ptr [rsp+88h+var_58+8], eax
0x180050f82  mov     rax, [rcx]
0x180050f85  mov     rax, [rax+20h]
0x180050f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f8e  test    eax, eax
0x180050f90  jns     short loc_180050FA3
0x180050f92  mov     r8d, eax
0x180050f95  lea     rdx, aFailedToSetThe; "Failed to set the global settings cache"...
0x180050f9c  mov     ecx, ebx
0x180050f9e  call    UnattendLogW
0x180050fa3  mov     eax, edi
0x180050fa5  add     rsp, 50h
0x180050fa9  pop     r15
0x180050fab  pop     r14
0x180050fad  pop     r13
0x180050faf  pop     rdi
0x180050fb0  pop     rsi
0x180050fb1  pop     rbp
0x180050fb2  pop     rbx
0x180050fb3  retn
```
