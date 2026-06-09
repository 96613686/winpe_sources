# CModule::RegisterServer(void)

- ea: `0x180003c8c`
- end: `0x180003e81`
- name: `?RegisterServer@CModule@@QEAAXXZ`
- size: `501`
- prototype: `void __fastcall(CModule *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000a610`

## callees

- `0x180003c8c`
- `0x180003e88`
- `0x180003f10`
- `0x18000a338`
- `0x18000a360`
- `0x18000ab3c`
- `0x18000ad30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003ccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003ccb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cd7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e46`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003e46`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003e57`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180003e57`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003da3`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180003da3`

## string_xrefs

- `0x180003e19`: `ThreadingModel`
- `0x180003daa`: `CLSID\{58fb76b9-ac85-4e55-ac04-427593b1d060}`

## pseudocode

```c
void __fastcall CModule::RegisterServer(CModule *this)
{
  DWORD ModuleFileNameW; // ebx
  signed int LastError; // ebx
  HKEY v3; // rdi
  int v4; // r9d
  int v5; // r9d
  HKEY pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey[3]; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Filename[264]; // [rsp+50h] [rbp-B0h] BYREF

  ModuleFileNameW = GetModuleFileNameW(hModule, Filename, 0x104u);
  if ( !ModuleFileNameW )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids,
        (unsigned int)LastError);
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(pExceptionObject) = LastError;
    throw (CExcept *)&pExceptionObject;
  }
  if ( ModuleFileNameW == 260 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids);
    LODWORD(pExceptionObject) = -2147417803;
    throw (CExcept *)&pExceptionObject;
  }
  v3 = (HKEY)((char *)&off_180011028 + SHIDWORD((*off_180011028)[1]));
  hKey[1] = v3;
  RtlAcquireSRWLockExclusive((char *)v3 + *(int *)(*(_QWORD *)v3 + 4LL));
  CRegKey::CRegKey((CRegKey *)hKey, HKEY_CLASSES_ROOT, L"CLSID\\{58fb76b9-ac85-4e55-ac04-427593b1d060}", v4);
  CRegKey::SetValue(hKey, 0, (const BYTE *)L"DIMS WMI.Job", 0x1Au);
  CRegKey::CRegKey((CRegKey *)&pExceptionObject, hKey[0], L"InprocServer32", v5);
  CRegKey::SetValue(&pExceptionObject, 0, (const BYTE *)Filename, 2 * ModuleFileNameW + 2);
  CRegKey::SetValue(&pExceptionObject, L"ThreadingModel", (const BYTE *)L"Free", 0xAu);
  if ( pExceptionObject )
    RegCloseKey(pExceptionObject);
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  RtlReleaseSRWLockExclusive((char *)v3 + *(int *)(*(_QWORD *)v3 + 4LL));
}

```

## disassembly

```asm
0x180003c8c  mov     [rsp-8+arg_0], rbx
0x180003c91  mov     [rsp-8+arg_8], rdi
0x180003c96  push    rbp
0x180003c97  lea     rbp, [rsp-170h]
0x180003c9f  sub     rsp, 270h
0x180003ca6  mov     rax, cs:__security_cookie
0x180003cad  xor     rax, rsp
0x180003cb0  mov     [rbp+170h+var_10], rax
0x180003cb7  mov     edi, 104h
0x180003cbc  mov     r8d, edi; nSize
0x180003cbf  lea     rdx, [rsp+270h+Filename]; lpFilename
0x180003cc4  mov     rcx, cs:hModule; hModule
0x180003ccb  call    cs:__imp_GetModuleFileNameW
0x180003cd1  mov     ebx, eax
0x180003cd3  test    eax, eax
0x180003cd5  jnz     short loc_180003D33
0x180003cd7  call    cs:__imp_GetLastError
0x180003cdd  mov     ebx, eax
0x180003cdf  lea     rax, WPP_GLOBAL_Control
0x180003ce6  mov     rcx, cs:WPP_GLOBAL_Control
0x180003ced  cmp     rcx, rax
0x180003cf0  jz      short loc_180003D10
0x180003cf2  test    byte ptr [rcx+1Ch], 2
0x180003cf6  jz      short loc_180003D10
0x180003cf8  mov     edx, 0Eh
0x180003cfd  mov     r9d, ebx
0x180003d00  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x180003d07  mov     rcx, [rcx+10h]
0x180003d0b  call    WPP_SF_D
0x180003d10  test    ebx, ebx
0x180003d12  jle     short loc_180003D1D
0x180003d14  movzx   ebx, bx
0x180003d17  or      ebx, 80070000h
0x180003d1d  mov     dword ptr [rsp+270h+pExceptionObject], ebx
0x180003d21  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180003d28  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180003d2d  call    _CxxThrowException_0
0x180003d33  cmp     ebx, edi
0x180003d35  jnz     short loc_180003D7F
0x180003d37  lea     rax, WPP_GLOBAL_Control
0x180003d3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d45  cmp     rcx, rax
0x180003d48  jz      short loc_180003D65
0x180003d4a  test    byte ptr [rcx+1Ch], 2
0x180003d4e  jz      short loc_180003D65
0x180003d50  mov     edx, 0Fh
0x180003d55  lea     r8, WPP_131b2a0d4f85352fb20a93dea1f15849_Traceguids
0x180003d5c  mov     rcx, [rcx+10h]
0x180003d60  call    WPP_SF_
0x180003d65  mov     dword ptr [rsp+270h+pExceptionObject], 80010135h
0x180003d6d  lea     rdx, _TI1?AVCExcept@@; pThrowInfo
0x180003d74  lea     rcx, [rsp+270h+pExceptionObject]; pExceptionObject
0x180003d79  call    _CxxThrowException_0
0x180003d7f  mov     rax, cs:off_180011028
0x180003d86  movsxd  rdi, dword ptr [rax+0Ch]
0x180003d8a  lea     rax, off_180011028
0x180003d91  add     rdi, rax
0x180003d94  mov     [rsp+270h+var_230], rdi
0x180003d99  mov     rax, [rdi]
0x180003d9c  movsxd  rcx, dword ptr [rax+4]
0x180003da0  add     rcx, rdi
0x180003da3  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180003da9  nop
0x180003daa  lea     r8, aClsid58fb76b9A; "CLSID\\{58fb76b9-ac85-4e55-ac04-427593b"...
0x180003db1  mov     rdx, 0FFFFFFFF80000000h; HKEY
0x180003db8  lea     rcx, [rsp+270h+hKey]; this
0x180003dbd  call    ??0CRegKey@@QEAA@PEAUHKEY__@@PEBGKKPEAK@Z; CRegKey::CRegKey(HKEY__ *,ushort const *,ulong,ulong,ulong *)
0x180003dc2  nop
0x180003dc3  mov     r9d, 1Ah; unsigned int
0x180003dc9  lea     r8, aDimsWmiJob; "DIMS WMI.Job"
0x180003dd0  xor     edx, edx; unsigned __int16 *
0x180003dd2  lea     rcx, [rsp+270h+hKey]; this
0x180003dd7  call    ?SetValue@CRegKey@@QEBAXPEBG0K@Z; CRegKey::SetValue(ushort const *,ushort const *,ulong)
0x180003ddc  lea     r8, aInprocserver32; "InprocServer32"
0x180003de3  mov     rdx, [rsp+270h+hKey]; HKEY
0x180003de8  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180003ded  call    ??0CRegKey@@QEAA@PEAUHKEY__@@PEBGKKPEAK@Z; CRegKey::CRegKey(HKEY__ *,ushort const *,ulong,ulong,ulong *)
0x180003df2  nop
0x180003df3  lea     r9d, ds:2[rbx*2]; unsigned int
0x180003dfb  lea     r8, [rsp+270h+Filename]; unsigned __int16 *
0x180003e00  xor     edx, edx; unsigned __int16 *
0x180003e02  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180003e07  call    ?SetValue@CRegKey@@QEBAXPEBG0K@Z; CRegKey::SetValue(ushort const *,ushort const *,ulong)
0x180003e0c  mov     r9d, 0Ah; unsigned int
0x180003e12  lea     r8, aFree; "Free"
0x180003e19  lea     rdx, aThreadingmodel; "ThreadingModel"
0x180003e20  lea     rcx, [rsp+270h+pExceptionObject]; this
0x180003e25  call    ?SetValue@CRegKey@@QEBAXPEBG0K@Z; CRegKey::SetValue(ushort const *,ushort const *,ulong)
0x180003e2a  nop
0x180003e2b  mov     rcx, [rsp+270h+pExceptionObject]; hKey
0x180003e30  test    rcx, rcx
0x180003e33  jz      short loc_180003E3C
0x180003e35  call    cs:__imp_RegCloseKey
0x180003e3b  nop
0x180003e3c  mov     rcx, [rsp+270h+hKey]; hKey
0x180003e41  test    rcx, rcx
0x180003e44  jz      short loc_180003E4D
0x180003e46  call    cs:__imp_RegCloseKey
0x180003e4c  nop
0x180003e4d  mov     rax, [rdi]
0x180003e50  movsxd  rcx, dword ptr [rax+4]
0x180003e54  add     rcx, rdi
0x180003e57  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180003e5d  mov     rcx, [rbp+170h+var_10]
0x180003e64  xor     rcx, rsp; StackCookie
0x180003e67  call    __security_check_cookie
0x180003e6c  lea     r11, [rsp+270h+var_s0]
0x180003e74  mov     rbx, [r11+10h]
0x180003e78  mov     rdi, [r11+18h]
0x180003e7c  mov     rsp, r11
0x180003e7f  pop     rbp
0x180003e80  retn
```
