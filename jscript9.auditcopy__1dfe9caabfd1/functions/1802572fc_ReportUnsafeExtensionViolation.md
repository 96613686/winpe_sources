# ReportUnsafeExtensionViolation

- ea: `0x1802572fc`
- end: `0x18025756a`
- name: `ReportUnsafeExtensionViolation`
- size: `622`
- prototype: `int __fastcall(struct _FILETIME, __int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18022155c`
- `0x180224204`
- `0x180257210`

## callees

- `0x1801bf50c`
- `0x1801cc26b`
- `0x18025709c`
- `0x1802572fc`
- `0x1803481f0`
- `0x180364010`

## import_xrefs

- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1802573e5`
- `api-ms-win-downlevel-advapi32-l1-1-0!RegGetValueW` at `0x1802573e5`
- `KERNEL32!WerGetFlags` at `0x1802574f9`
- `KERNEL32!WerGetFlags` at `0x1802574f9`
- `KERNEL32!WerSetFlags` at `0x180257513`
- `KERNEL32!WerSetFlags` at `0x180257536`
- `KERNEL32!WerSetFlags` at `0x180257513`
- `KERNEL32!WerSetFlags` at `0x180257536`
- `KERNEL32!LoadLibraryExW` at `0x180257465`
- `KERNEL32!LoadLibraryExW` at `0x180257465`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18025739b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18025739b`
- `KERNEL32!GetCurrentProcess` at `0x1802574e5`
- `KERNEL32!GetCurrentProcess` at `0x1802574e5`
- `KERNEL32!FreeLibrary` at `0x180257545`
- `KERNEL32!FreeLibrary` at `0x180257545`
- `KERNEL32!GetProcAddress` at `0x180257487`
- `KERNEL32!GetProcAddress` at `0x180257487`

## string_xrefs

- `0x1802573cb`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x1802573b6`: `LastUnsafeExtensionReportTime`
- `0x180257458`: `FAULTREP.DLL`

## pseudocode

```c
int __fastcall ReportUnsafeExtensionViolation(struct _FILETIME a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE Library; // rax
  LSTATUS ValueW; // eax
  const unsigned __int16 *v7; // rdx
  __int64 v8; // rcx
  const unsigned __int16 *v9; // r8
  __int64 v10; // r9
  bool v11; // sf
  HMODULE v12; // rbx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess; // rax
  DWORD pdwFlags[2]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+50h] [rbp-B8h] BYREF
  unsigned int pvData[2]; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 SystemTimeAsFileTime; // [rsp+60h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime_8[2]; // [rsp+68h] [rbp-A0h] BYREF
  _DWORD v21[4]; // [rsp+78h] [rbp-90h] BYREF
  __int64 v22; // [rsp+88h] [rbp-80h]
  int v23; // [rsp+90h] [rbp-78h]
  __int64 v24; // [rsp+98h] [rbp-70h]
  __int64 v25; // [rsp+A0h] [rbp-68h]
  __int64 v26; // [rsp+A8h] [rbp-60h]
  __int64 v27; // [rsp+B0h] [rbp-58h]

  *(_OWORD *)&SystemTimeAsFileTime_8[0].dwLowDateTime = 0;
  LODWORD(Library) = (unsigned int)memset_0(v21, 0, 0x98u);
  pdwFlags[0] = 0;
  *(_QWORD *)pvData = 0;
  SystemTimeAsFileTime = 0;
  if ( dword_180443808 < 1 )
  {
    LODWORD(Library) = _InterlockedIncrement(&dword_180443808);
    if ( (int)Library <= 1 )
    {
      LODWORD(Library) = IsJITDebuggerPresent();
      if ( !(_DWORD)Library )
      {
        GetSystemTimeAsFileTime((LPFILETIME)&SystemTimeAsFileTime);
        pcbData[0] = 8;
        ValueW = RegGetValueW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
                   L"LastUnsafeExtensionReportTime",
                   8u,
                   0,
                   pvData,
                   pcbData);
        v11 = ValueW < 0;
        if ( ValueW > 0 )
          v11 = 1;
        if ( v11 || pcbData[0] != 8 )
        {
          *(_QWORD *)pvData = 0;
        }
        else
        {
          *(_QWORD *)pcbData = *(_QWORD *)pvData;
          if ( SystemTimeAsFileTime > *(_QWORD *)pvData )
          {
            LODWORD(Library) = SystemTimeAsFileTime - pcbData[0];
            v8 = 604800000000000LL;
            if ( SystemTimeAsFileTime - *(_QWORD *)pcbData < 0x2260FF9290000LL )
              return (int)Library;
          }
        }
        _RegSetKeyValueWithSDDL((HKEY)v8, v7, v9, v10, (BYTE *)&SystemTimeAsFileTime);
        Library = LoadLibraryExW(L"FAULTREP.DLL", 0, 0x800u);
        v12 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "ReportFault");
          if ( ProcAddress )
          {
            v25 = a2;
            v26 = a3;
            v27 = a4;
            v21[0] = -1073740791;
            v22 = 0;
            v23 = 4;
            v24 = 26;
            SystemTimeAsFileTime_8[0] = (struct _FILETIME)v21;
            SystemTimeAsFileTime_8[1] = a1;
            CurrentProcess = GetCurrentProcess();
            if ( WerGetFlags(CurrentProcess, pdwFlags) >= 0 && WerSetFlags(pdwFlags[0] & 0xFFFFFFCB | 0x24) >= 0 )
            {
              ((void (__fastcall *)(struct _FILETIME *, _QWORD))ProcAddress)(SystemTimeAsFileTime_8, 0);
              WerSetFlags(pdwFlags[0]);
            }
          }
          LODWORD(Library) = FreeLibrary(v12);
        }
      }
    }
  }
  return (int)Library;
}

```

## disassembly

```asm
0x1802572fc  mov     rax, rsp
0x1802572ff  mov     [rax+20h], r9
0x180257303  mov     [rax+18h], r8
0x180257307  mov     [rax+10h], rdx
0x18025730b  mov     [rax+8], rcx
0x18025730f  push    rbp
0x180257310  push    rbx
0x180257311  push    rsi
0x180257312  push    rdi
0x180257313  lea     rbp, [rax-48h]
0x180257317  sub     rsp, 128h
0x18025731e  mov     rax, cs:__security_cookie
0x180257325  xor     rax, rsp
0x180257328  mov     [rbp+40h+var_30], rax
0x18025732c  mov     rsi, [rbp+40h+arg_0]
0x180257330  lea     rcx, [rsp+140h+var_D0]; void *
0x180257335  xorps   xmm0, xmm0
0x180257338  xor     edx, edx; Val
0x18025733a  mov     r8d, 98h; Size
0x180257340  movups  xmmword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime+8], xmm0
0x180257345  call    memset_0
0x18025734a  mov     ecx, 1
0x18025734f  mov     [rsp+140h+pdwFlags], 0
0x180257357  cmp     cs:dword_180443808, ecx
0x18025735d  mov     qword ptr [rsp+140h+var_F0], 0
0x180257366  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18025736f  jge     loc_180257551
0x180257375  mov     eax, ecx
0x180257377  lock xadd cs:dword_180443808, eax
0x18025737f  add     eax, ecx
0x180257381  cmp     eax, ecx
0x180257383  jg      loc_180257551
0x180257389  call    IsJITDebuggerPresent
0x18025738e  test    eax, eax
0x180257390  jnz     loc_180257551
0x180257396  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18025739b  call    cs:__imp_GetSystemTimeAsFileTime
0x1802573a2  nop     dword ptr [rax+rax+00h]
0x1802573a7  lea     rax, [rsp+140h+pcbData]
0x1802573ac  mov     ebx, 8
0x1802573b1  mov     [rsp+30h], rax; struct _SECURITY_ATTRIBUTES *
0x1802573b6  lea     r8, ValueName; "LastUnsafeExtensionReportTime"
0x1802573bd  lea     rax, [rsp+140h+var_F0]
0x1802573c2  mov     [rsp+140h+pcbData], ebx
0x1802573c6  mov     [rsp+140h+pvData], rax; unsigned int
0x1802573cb  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Internet Explorer"...
0x1802573d2  mov     r9d, ebx; dwFlags
0x1802573d5  mov     [rsp+140h+pdwType], 0; pdwType
0x1802573de  mov     rcx, 0FFFFFFFF80000001h; hkey
0x1802573e5  call    cs:__imp_RegGetValueW
0x1802573ec  nop     dword ptr [rax+rax+00h]
0x1802573f1  test    eax, eax
0x1802573f3  jle     short loc_1802573FF
0x1802573f5  movzx   eax, ax
0x1802573f8  or      eax, 80070000h
0x1802573fd  test    eax, eax
0x1802573ff  js      short loc_18025743E
0x180257401  cmp     [rsp+140h+pcbData], ebx
0x180257405  jnz     short loc_18025743E
0x180257407  mov     rax, qword ptr [rsp+140h+var_F0]
0x18025740c  mov     [rsp+140h+pcbData], eax
0x180257410  shr     rax, 20h
0x180257414  mov     [rsp+140h+pcbData+4], eax
0x180257418  mov     rax, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x18025741d  cmp     rax, qword ptr [rsp+140h+pcbData]
0x180257422  jbe     short loc_180257447
0x180257424  sub     rax, qword ptr [rsp+140h+pcbData]
0x180257429  mov     rcx, 2260FF9290000h
0x180257433  cmp     rax, rcx
0x180257436  jb      loc_180257551
0x18025743c  jmp     short loc_180257447
0x18025743e  mov     qword ptr [rsp+140h+var_F0], 0
0x180257447  lea     rax, [rsp+140h+SystemTimeAsFileTime]
0x18025744c  mov     [rsp+140h+pdwType], rax; lpData
0x180257451  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x180257456  xor     edx, edx; hFile
0x180257458  lea     rcx, aFaultrepDll; "FAULTREP.DLL"
0x18025745f  mov     r8d, 800h; dwFlags
0x180257465  call    cs:__imp_LoadLibraryExW
0x18025746c  nop     dword ptr [rax+rax+00h]
0x180257471  mov     rbx, rax
0x180257474  test    rax, rax
0x180257477  jz      loc_180257551
0x18025747d  lea     rdx, aReportfault; "ReportFault"
0x180257484  mov     rcx, rax; hModule
0x180257487  call    cs:__imp_GetProcAddress
0x18025748e  nop     dword ptr [rax+rax+00h]
0x180257493  mov     rdi, rax
0x180257496  test    rax, rax
0x180257499  jz      loc_180257542
0x18025749f  mov     rcx, [rbp+40h+arg_8]
0x1802574a3  lea     rax, [rsp+140h+var_D0]
0x1802574a8  mov     [rbp+40h+var_A8], rcx
0x1802574ac  mov     rcx, [rbp+40h+arg_10]
0x1802574b0  mov     [rbp+40h+var_A0], rcx
0x1802574b4  mov     rcx, [rbp+40h+arg_18]
0x1802574b8  mov     [rbp+40h+var_98], rcx
0x1802574bc  mov     [rsp+140h+var_D0], 0C0000409h
0x1802574c4  mov     [rbp+40h+var_C0], 0
0x1802574cc  mov     [rbp+40h+var_B8], 4
0x1802574d3  mov     [rbp+40h+var_B0], 1Ah
0x1802574db  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime+8], rax
0x1802574e0  mov     qword ptr [rsp+140h+var_D8], rsi
0x1802574e5  call    cs:__imp_GetCurrentProcess
0x1802574ec  nop     dword ptr [rax+rax+00h]
0x1802574f1  mov     rcx, rax; hProcess
0x1802574f4  lea     rdx, [rsp+140h+pdwFlags]; pdwFlags
0x1802574f9  call    cs:__imp_WerGetFlags
0x180257500  nop     dword ptr [rax+rax+00h]
0x180257505  test    eax, eax
0x180257507  js      short loc_180257542
0x180257509  mov     ecx, [rsp+140h+pdwFlags]
0x18025750d  and     ecx, 0FFFFFFEFh
0x180257510  or      ecx, 24h; dwFlags
0x180257513  call    cs:__imp_WerSetFlags
0x18025751a  nop     dword ptr [rax+rax+00h]
0x18025751f  test    eax, eax
0x180257521  js      short loc_180257542
0x180257523  xor     edx, edx
0x180257525  lea     rcx, [rsp+140h+SystemTimeAsFileTime.dwLowDateTime+8]
0x18025752a  mov     rax, rdi
0x18025752d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180257532  mov     ecx, [rsp+140h+pdwFlags]; dwFlags
0x180257536  call    cs:__imp_WerSetFlags
0x18025753d  nop     dword ptr [rax+rax+00h]
0x180257542  mov     rcx, rbx; hLibModule
0x180257545  call    cs:__imp_FreeLibrary
0x18025754c  nop     dword ptr [rax+rax+00h]
0x180257551  mov     rcx, [rbp+40h+var_30]
0x180257555  xor     rcx, rsp; StackCookie
0x180257558  call    __security_check_cookie
0x18025755d  add     rsp, 128h
0x180257564  pop     rdi
0x180257565  pop     rsi
0x180257566  pop     rbx
0x180257567  pop     rbp
0x180257568  retn
```
