# ReportUnsafeExtensionViolation

- ea: `0x180093e34`
- end: `0x18009409c`
- name: `ReportUnsafeExtensionViolation`
- size: `616`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004d424`
- `0x18007f918`
- `0x180093d50`

## callees

- `0x180056804`
- `0x180059229`
- `0x180059241`
- `0x180093be8`
- `0x180093e34`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180093f1a`
- `ADVAPI32!RegGetValueW` at `0x180093f1a`
- `KERNEL32!WerGetFlags` at `0x18009401b`
- `KERNEL32!WerGetFlags` at `0x18009401b`
- `KERNEL32!WerSetFlags` at `0x180094035`
- `KERNEL32!WerSetFlags` at `0x180094058`
- `KERNEL32!WerSetFlags` at `0x180094035`
- `KERNEL32!WerSetFlags` at `0x180094058`
- `KERNEL32!LoadLibraryExW` at `0x180093f9a`
- `KERNEL32!LoadLibraryExW` at `0x180093f9a`
- `KERNEL32!FreeLibrary` at `0x180094067`
- `KERNEL32!FreeLibrary` at `0x180094067`
- `KERNEL32!GetProcAddress` at `0x180093fbc`
- `KERNEL32!GetProcAddress` at `0x180093fbc`

## string_xrefs

- `0x180093f00`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180093eeb`: `LastUnsafeExtensionReportTime`
- `0x180093f8d`: `FAULTREP.DLL`

## pseudocode

```c
int __fastcall ReportUnsafeExtensionViolation(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  HMODULE Library; // rax
  LSTATUS ValueW; // eax
  const unsigned __int16 *v10; // rdx
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r8
  __int64 v13; // r9
  bool v14; // sf
  HMODULE v15; // rbx
  FARPROC ProcAddress; // rdi
  HANDLE CurrentProcess_0; // rax
  DWORD pdwFlags; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int pvData[2]; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v23; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v24[4]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v25; // [rsp+80h] [rbp-80h]
  int v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  __int64 v28; // [rsp+98h] [rbp-68h]
  __int64 v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]

  v23 = 0;
  LODWORD(Library) = (unsigned int)memset_0(v24, 0, 0x98u);
  pdwFlags = 0;
  *(_QWORD *)pvData = 0;
  SystemTimeAsFileTime = 0;
  if ( dword_1800B8F20 < 1 )
  {
    LODWORD(Library) = _InterlockedIncrement(&dword_1800B8F20);
    if ( (int)Library <= 1 )
    {
      LODWORD(Library) = IsJITDebuggerPresent();
      if ( !(_DWORD)Library )
      {
        GetSystemTimeAsFileTime_0(&SystemTimeAsFileTime);
        pcbData[0] = 8;
        ValueW = RegGetValueW(
                   HKEY_CURRENT_USER,
                   L"Software\\Microsoft\\Internet Explorer\\LowRegistry",
                   L"LastUnsafeExtensionReportTime",
                   8u,
                   0,
                   pvData,
                   pcbData);
        v14 = ValueW < 0;
        if ( ValueW > 0 )
          v14 = 1;
        if ( v14 || pcbData[0] != 8 )
        {
          *(_QWORD *)pvData = 0;
        }
        else
        {
          *(_QWORD *)pcbData = *(_QWORD *)pvData;
          if ( *(unsigned __int64 *)&SystemTimeAsFileTime > *(_QWORD *)pvData )
          {
            LODWORD(Library) = SystemTimeAsFileTime.dwLowDateTime - pcbData[0];
            v11 = 604800000000000LL;
            if ( *(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)pcbData < 0x2260FF9290000uLL )
              return (int)Library;
          }
        }
        _RegSetKeyValueWithSDDL((HKEY)v11, v10, v12, v13, (BYTE *)&SystemTimeAsFileTime);
        Library = LoadLibraryExW(L"FAULTREP.DLL", 0, 0x800u);
        v15 = Library;
        if ( Library )
        {
          ProcAddress = GetProcAddress(Library, "ReportFault");
          if ( ProcAddress )
          {
            v24[0] = -1073740791;
            *(_QWORD *)&v23 = v24;
            v25 = 0;
            v26 = 4;
            v27 = 26;
            v28 = a2;
            v29 = a3;
            v30 = a4;
            *((_QWORD *)&v23 + 1) = a1;
            CurrentProcess_0 = GetCurrentProcess_0();
            if ( WerGetFlags(CurrentProcess_0, &pdwFlags) >= 0 && WerSetFlags(pdwFlags & 0xFFFFFFCB | 0x24) >= 0 )
            {
              ((void (__fastcall *)(__int128 *, _QWORD))ProcAddress)(&v23, 0);
              WerSetFlags(pdwFlags);
            }
          }
          LODWORD(Library) = FreeLibrary(v15);
        }
      }
    }
  }
  return (int)Library;
}

```

## disassembly

```asm
0x180093e34  mov     [rsp-8+arg_8], rbx
0x180093e39  mov     [rsp-8+arg_10], rsi
0x180093e3e  push    rbp
0x180093e3f  push    rdi
0x180093e40  push    r12
0x180093e42  push    r14
0x180093e44  push    r15
0x180093e46  lea     rbp, [rsp-20h]
0x180093e4b  sub     rsp, 120h
0x180093e52  mov     rax, cs:__security_cookie
0x180093e59  xor     rax, rsp
0x180093e5c  mov     [rbp+40h+var_30], rax
0x180093e60  mov     r14, r8
0x180093e63  mov     r15, rdx
0x180093e66  mov     r12, rcx
0x180093e69  xorps   xmm0, xmm0
0x180093e6c  xor     edx, edx; Val
0x180093e6e  lea     rcx, [rsp+140h+var_D0]; void *
0x180093e73  mov     r8d, 98h; Size
0x180093e79  mov     rsi, r9
0x180093e7c  movups  [rsp+140h+var_E0], xmm0
0x180093e81  call    memset_0
0x180093e86  mov     ecx, 1
0x180093e8b  mov     [rsp+140h+pdwFlags], 0
0x180093e93  cmp     cs:dword_1800B8F20, ecx
0x180093e99  mov     qword ptr [rsp+140h+var_F0], 0
0x180093ea2  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180093eab  jge     loc_180094073
0x180093eb1  mov     eax, ecx
0x180093eb3  lock xadd cs:dword_1800B8F20, eax
0x180093ebb  add     eax, ecx
0x180093ebd  cmp     eax, ecx
0x180093ebf  jg      loc_180094073
0x180093ec5  call    IsJITDebuggerPresent
0x180093eca  test    eax, eax
0x180093ecc  jnz     loc_180094073
0x180093ed2  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180093ed7  call    GetSystemTimeAsFileTime_0
0x180093edc  lea     rax, [rsp+140h+var_F8]
0x180093ee1  mov     ebx, 8
0x180093ee6  mov     [rsp+140h+pcbData], rax; struct _SECURITY_ATTRIBUTES *
0x180093eeb  lea     r8, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x180093ef2  lea     rax, [rsp+140h+var_F0]
0x180093ef7  mov     [rsp+140h+var_F8], ebx
0x180093efb  mov     [rsp+140h+pvData], rax; unsigned int
0x180093f00  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x180093f07  mov     r9d, ebx; dwFlags
0x180093f0a  mov     [rsp+140h+pdwType], 0; pdwType
0x180093f13  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180093f1a  call    cs:__imp_RegGetValueW
0x180093f21  nop     dword ptr [rax+rax+00h]
0x180093f26  test    eax, eax
0x180093f28  jle     short loc_180093F34
0x180093f2a  movzx   eax, ax
0x180093f2d  or      eax, 80070000h
0x180093f32  test    eax, eax
0x180093f34  js      short loc_180093F73
0x180093f36  cmp     [rsp+140h+var_F8], ebx
0x180093f3a  jnz     short loc_180093F73
0x180093f3c  mov     rax, qword ptr [rsp+140h+var_F0]
0x180093f41  mov     [rsp+140h+var_F8], eax
0x180093f45  shr     rax, 20h
0x180093f49  mov     [rsp+140h+var_F8+4], eax
0x180093f4d  mov     rax, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180093f52  cmp     rax, qword ptr [rsp+140h+var_F8]
0x180093f57  jbe     short loc_180093F7C
0x180093f59  sub     rax, qword ptr [rsp+140h+var_F8]
0x180093f5e  mov     rcx, 2260FF9290000h
0x180093f68  cmp     rax, rcx
0x180093f6b  jb      loc_180094073
0x180093f71  jmp     short loc_180093F7C
0x180093f73  mov     qword ptr [rsp+140h+var_F0], 0
0x180093f7c  lea     rax, [rsp+140h+SystemTimeAsFileTime]
0x180093f81  mov     [rsp+140h+pdwType], rax; lpData
0x180093f86  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x180093f8b  xor     edx, edx; hFile
0x180093f8d  lea     rcx, aFaultrepDll; "FAULTREP.DLL"
0x180093f94  mov     r8d, 800h; dwFlags
0x180093f9a  call    cs:__imp_LoadLibraryExW
0x180093fa1  nop     dword ptr [rax+rax+00h]
0x180093fa6  mov     rbx, rax
0x180093fa9  test    rax, rax
0x180093fac  jz      loc_180094073
0x180093fb2  lea     rdx, aReportfault; "ReportFault"
0x180093fb9  mov     rcx, rax; hModule
0x180093fbc  call    cs:__imp_GetProcAddress
0x180093fc3  nop     dword ptr [rax+rax+00h]
0x180093fc8  mov     rdi, rax
0x180093fcb  test    rax, rax
0x180093fce  jz      loc_180094064
0x180093fd4  lea     rax, [rsp+140h+var_D0]
0x180093fd9  mov     [rsp+140h+var_D0], 0C0000409h
0x180093fe1  mov     qword ptr [rsp+140h+var_E0], rax
0x180093fe6  mov     [rbp+40h+var_C0], 0
0x180093fee  mov     [rbp+40h+var_B8], 4
0x180093ff5  mov     [rbp+40h+var_B0], 1Ah
0x180093ffd  mov     [rbp+40h+var_A8], r15
0x180094001  mov     [rbp+40h+var_A0], r14
0x180094005  mov     [rbp+40h+var_98], rsi
0x180094009  mov     qword ptr [rsp+140h+var_E0+8], r12
0x18009400e  call    GetCurrentProcess_0
0x180094013  mov     rcx, rax; hProcess
0x180094016  lea     rdx, [rsp+140h+pdwFlags]; pdwFlags
0x18009401b  call    cs:__imp_WerGetFlags
0x180094022  nop     dword ptr [rax+rax+00h]
0x180094027  test    eax, eax
0x180094029  js      short loc_180094064
0x18009402b  mov     ecx, [rsp+140h+pdwFlags]
0x18009402f  and     ecx, 0FFFFFFEFh
0x180094032  or      ecx, 24h; dwFlags
0x180094035  call    cs:__imp_WerSetFlags
0x18009403c  nop     dword ptr [rax+rax+00h]
0x180094041  test    eax, eax
0x180094043  js      short loc_180094064
0x180094045  xor     edx, edx
0x180094047  lea     rcx, [rsp+140h+var_E0]
0x18009404c  mov     rax, rdi
0x18009404f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094054  mov     ecx, [rsp+140h+pdwFlags]; dwFlags
0x180094058  call    cs:__imp_WerSetFlags
0x18009405f  nop     dword ptr [rax+rax+00h]
0x180094064  mov     rcx, rbx; hLibModule
0x180094067  call    cs:__imp_FreeLibrary
0x18009406e  nop     dword ptr [rax+rax+00h]
0x180094073  mov     rcx, [rbp+40h+var_30]
0x180094077  xor     rcx, rsp; StackCookie
0x18009407a  call    __security_check_cookie
0x18009407f  lea     r11, [rsp+140h+var_20]
0x180094087  mov     rbx, [r11+38h]
0x18009408b  mov     rsi, [r11+40h]
0x18009408f  mov     rsp, r11
0x180094092  pop     r15
0x180094094  pop     r14
0x180094096  pop     r12
0x180094098  pop     rdi
0x180094099  pop     rbp
0x18009409a  retn
```
