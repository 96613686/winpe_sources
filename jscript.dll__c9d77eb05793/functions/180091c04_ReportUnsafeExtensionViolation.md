# ReportUnsafeExtensionViolation

- ea: `0x180091c04`
- end: `0x180091e3d`
- name: `ReportUnsafeExtensionViolation`
- size: `569`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004c764`
- `0x18007dfb8`
- `0x180091b28`

## callees

- `0x180055980`
- `0x1800582d9`
- `0x1800582f1`
- `0x1800919d0`
- `0x180091c04`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x180091cea`
- `ADVAPI32!RegGetValueW` at `0x180091cea`
- `KERNEL32!WerGetFlags` at `0x180091dd5`
- `KERNEL32!WerGetFlags` at `0x180091dd5`
- `KERNEL32!WerSetFlags` at `0x180091de9`
- `KERNEL32!WerSetFlags` at `0x180091e06`
- `KERNEL32!WerSetFlags` at `0x180091de9`
- `KERNEL32!WerSetFlags` at `0x180091e06`
- `KERNEL32!LoadLibraryExW` at `0x180091d64`
- `KERNEL32!LoadLibraryExW` at `0x180091d64`
- `KERNEL32!FreeLibrary` at `0x180091e0f`
- `KERNEL32!FreeLibrary` at `0x180091e0f`
- `KERNEL32!GetProcAddress` at `0x180091d80`
- `KERNEL32!GetProcAddress` at `0x180091d80`

## string_xrefs

- `0x180091cd0`: `Software\Microsoft\Internet Explorer\LowRegistry`
- `0x180091cbb`: `LastUnsafeExtensionReportTime`
- `0x180091d57`: `FAULTREP.DLL`

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
  if ( dword_1800B6F20 < 1 )
  {
    LODWORD(Library) = _InterlockedIncrement(&dword_1800B6F20);
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
0x180091c04  mov     [rsp-8+arg_8], rbx
0x180091c09  mov     [rsp-8+arg_10], rsi
0x180091c0e  push    rbp
0x180091c0f  push    rdi
0x180091c10  push    r12
0x180091c12  push    r14
0x180091c14  push    r15
0x180091c16  lea     rbp, [rsp-20h]
0x180091c1b  sub     rsp, 120h
0x180091c22  mov     rax, cs:__security_cookie
0x180091c29  xor     rax, rsp
0x180091c2c  mov     [rbp+40h+var_30], rax
0x180091c30  mov     r14, r8
0x180091c33  mov     r15, rdx
0x180091c36  mov     r12, rcx
0x180091c39  xorps   xmm0, xmm0
0x180091c3c  xor     edx, edx; Val
0x180091c3e  lea     rcx, [rsp+140h+var_D0]; void *
0x180091c43  mov     r8d, 98h; Size
0x180091c49  mov     rsi, r9
0x180091c4c  movups  [rsp+140h+var_E0], xmm0
0x180091c51  call    memset_0
0x180091c56  mov     ecx, 1
0x180091c5b  mov     [rsp+140h+pdwFlags], 0
0x180091c63  cmp     cs:dword_1800B6F20, ecx
0x180091c69  mov     qword ptr [rsp+140h+var_F0], 0
0x180091c72  mov     qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180091c7b  jge     loc_180091E15
0x180091c81  mov     eax, ecx
0x180091c83  lock xadd cs:dword_1800B6F20, eax
0x180091c8b  add     eax, ecx
0x180091c8d  cmp     eax, ecx
0x180091c8f  jg      loc_180091E15
0x180091c95  call    IsJITDebuggerPresent
0x180091c9a  test    eax, eax
0x180091c9c  jnz     loc_180091E15
0x180091ca2  lea     rcx, [rsp+140h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180091ca7  call    GetSystemTimeAsFileTime_0
0x180091cac  lea     rax, [rsp+140h+var_F8]
0x180091cb1  mov     ebx, 8
0x180091cb6  mov     [rsp+140h+pcbData], rax; struct _SECURITY_ATTRIBUTES *
0x180091cbb  lea     r8, aLastunsafeexte; "LastUnsafeExtensionReportTime"
0x180091cc2  lea     rax, [rsp+140h+var_F0]
0x180091cc7  mov     [rsp+140h+var_F8], ebx
0x180091ccb  mov     [rsp+140h+pvData], rax; unsigned int
0x180091cd0  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Internet Explorer"...
0x180091cd7  mov     r9d, ebx; dwFlags
0x180091cda  mov     [rsp+140h+pdwType], 0; pdwType
0x180091ce3  mov     rcx, 0FFFFFFFF80000001h; hkey
0x180091cea  call    cs:__imp_RegGetValueW
0x180091cf0  test    eax, eax
0x180091cf2  jle     short loc_180091CFE
0x180091cf4  movzx   eax, ax
0x180091cf7  or      eax, 80070000h
0x180091cfc  test    eax, eax
0x180091cfe  js      short loc_180091D3D
0x180091d00  cmp     [rsp+140h+var_F8], ebx
0x180091d04  jnz     short loc_180091D3D
0x180091d06  mov     rax, qword ptr [rsp+140h+var_F0]
0x180091d0b  mov     [rsp+140h+var_F8], eax
0x180091d0f  shr     rax, 20h
0x180091d13  mov     [rsp+140h+var_F8+4], eax
0x180091d17  mov     rax, qword ptr [rsp+140h+SystemTimeAsFileTime.dwLowDateTime]
0x180091d1c  cmp     rax, qword ptr [rsp+140h+var_F8]
0x180091d21  jbe     short loc_180091D46
0x180091d23  sub     rax, qword ptr [rsp+140h+var_F8]
0x180091d28  mov     rcx, 2260FF9290000h
0x180091d32  cmp     rax, rcx
0x180091d35  jb      loc_180091E15
0x180091d3b  jmp     short loc_180091D46
0x180091d3d  mov     qword ptr [rsp+140h+var_F0], 0
0x180091d46  lea     rax, [rsp+140h+SystemTimeAsFileTime]
0x180091d4b  mov     [rsp+140h+pdwType], rax; lpData
0x180091d50  call    ?_RegSetKeyValueWithSDDL@@YAKPEAUHKEY__@@PEBG1KPEBXKPEAU_SECURITY_ATTRIBUTES@@@Z; _RegSetKeyValueWithSDDL(HKEY__ *,ushort const *,ushort const *,ulong,void const *,ulong,_SECURITY_ATTRIBUTES *)
0x180091d55  xor     edx, edx; hFile
0x180091d57  lea     rcx, aFaultrepDll; "FAULTREP.DLL"
0x180091d5e  mov     r8d, 800h; dwFlags
0x180091d64  call    cs:__imp_LoadLibraryExW
0x180091d6a  mov     rbx, rax
0x180091d6d  test    rax, rax
0x180091d70  jz      loc_180091E15
0x180091d76  lea     rdx, aReportfault; "ReportFault"
0x180091d7d  mov     rcx, rax; hModule
0x180091d80  call    cs:__imp_GetProcAddress
0x180091d86  mov     rdi, rax
0x180091d89  test    rax, rax
0x180091d8c  jz      short loc_180091E0C
0x180091d8e  lea     rax, [rsp+140h+var_D0]
0x180091d93  mov     [rsp+140h+var_D0], 0C0000409h
0x180091d9b  mov     qword ptr [rsp+140h+var_E0], rax
0x180091da0  mov     [rbp+40h+var_C0], 0
0x180091da8  mov     [rbp+40h+var_B8], 4
0x180091daf  mov     [rbp+40h+var_B0], 1Ah
0x180091db7  mov     [rbp+40h+var_A8], r15
0x180091dbb  mov     [rbp+40h+var_A0], r14
0x180091dbf  mov     [rbp+40h+var_98], rsi
0x180091dc3  mov     qword ptr [rsp+140h+var_E0+8], r12
0x180091dc8  call    GetCurrentProcess_0
0x180091dcd  mov     rcx, rax; hProcess
0x180091dd0  lea     rdx, [rsp+140h+pdwFlags]; pdwFlags
0x180091dd5  call    cs:__imp_WerGetFlags
0x180091ddb  test    eax, eax
0x180091ddd  js      short loc_180091E0C
0x180091ddf  mov     ecx, [rsp+140h+pdwFlags]
0x180091de3  and     ecx, 0FFFFFFEFh
0x180091de6  or      ecx, 24h; dwFlags
0x180091de9  call    cs:__imp_WerSetFlags
0x180091def  test    eax, eax
0x180091df1  js      short loc_180091E0C
0x180091df3  xor     edx, edx
0x180091df5  lea     rcx, [rsp+140h+var_E0]
0x180091dfa  mov     rax, rdi
0x180091dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180091e02  mov     ecx, [rsp+140h+pdwFlags]; dwFlags
0x180091e06  call    cs:__imp_WerSetFlags
0x180091e0c  mov     rcx, rbx; hLibModule
0x180091e0f  call    cs:__imp_FreeLibrary
0x180091e15  mov     rcx, [rbp+40h+var_30]
0x180091e19  xor     rcx, rsp; StackCookie
0x180091e1c  call    __security_check_cookie
0x180091e21  lea     r11, [rsp+140h+var_20]
0x180091e29  mov     rbx, [r11+38h]
0x180091e2d  mov     rsi, [r11+40h]
0x180091e31  mov     rsp, r11
0x180091e34  pop     r15
0x180091e36  pop     r14
0x180091e38  pop     r12
0x180091e3a  pop     rdi
0x180091e3b  pop     rbp
0x180091e3c  retn
```
