# CDtcConfig::StopTraceSession(void)

- ea: `0x18001c210`
- end: `0x18001c407`
- name: `?StopTraceSession@CDtcConfig@@UEAAJXZ`
- size: `503`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180018ba0`
- `0x18001a664`
- `0x18001c210`
- `0x18001c924`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c33c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001c33c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3b1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001c3bf`

## string_xrefs

- `0x18001c23c`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001c353`: `RegOpenKey (options) failed`
- `0x18001c254`: `CDtcConfig::StopTraceSession`
- `0x18001c37c`: `Failed to write session up value`

## pseudocode

```c
__int64 __fastcall CDtcConfig::StopTraceSession(CDtcConfig *this)
{
  HKEY v1; // rdi
  CTrace *v3; // rcx
  signed int HKLM; // ebx
  const wchar_t *v5; // rax
  __int64 v6; // r9
  LSTATUS v7; // eax
  CDtcConfig *v8; // rcx
  __int64 v10; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  phkResult = 0;
  hKey = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    996,
    L"CDtcConfig::StopTraceSession",
    0,
    L"In");
  if ( *((_DWORD *)this + 7) )
  {
    HKLM = CTrace::StopSession(v3);
    if ( HKLM >= 0 )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        1011,
        L"CDtcConfig::StopTraceSession",
        0,
        L"Trace session stopped.");
      HKLM = CDtcConfig::GetHKLM(this, &hKey);
      if ( HKLM < 0 )
      {
        LODWORD(v10) = HKLM;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
          1017,
          L"CDtcConfig::StopTraceSession",
          v10,
          L"GetHKLM failed.");
        v1 = hKey;
        goto LABEL_14;
      }
      v1 = hKey;
      v7 = RegOpenKeyExW(
             hKey,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\LoggingOptions",
             0,
             2u,
             &phkResult);
      HKLM = v7;
      if ( v7 )
      {
        if ( v7 > 0 )
          HKLM = (unsigned __int16)v7 | 0x80070000;
        v5 = L"RegOpenKey (options) failed";
        v6 = 1029;
      }
      else
      {
        HKLM = CDtcConfig::WriteRegDWORD(v8, phkResult, L"RequestSessionUp", 0);
        if ( HKLM >= 0 )
          goto LABEL_14;
        v5 = L"Failed to write session up value";
        v6 = 1036;
      }
    }
    else
    {
      v5 = L"StopSession failed";
      v6 = 1007;
    }
  }
  else
  {
    HKLM = -2147024846;
    v5 = L"StopTraceSession is not supported on a remote host";
    v6 = 1000;
  }
  LODWORD(v10) = HKLM;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    v6,
    L"CDtcConfig::StopTraceSession",
    v10,
    v5);
LABEL_14:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v1 )
    RegCloseKey(v1);
  LODWORD(v10) = HKLM;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1044,
    L"CDtcConfig::StopTraceSession",
    v10,
    L"Out");
  return (unsigned int)HKLM;
}

```

## disassembly

```asm
0x18001c210  mov     r11, rsp
0x18001c213  mov     [r11+18h], rbx
0x18001c217  push    rsi
0x18001c218  push    rdi
0x18001c219  push    r12
0x18001c21b  push    r14
0x18001c21d  push    r15
0x18001c21f  sub     rsp, 40h
0x18001c223  xor     edi, edi
0x18001c225  mov     qword ptr [r11+10h], 0
0x18001c22d  lea     rax, aIn_0; "In"
0x18001c234  mov     [r11+8], rdi
0x18001c238  mov     [r11-38h], rax
0x18001c23c  lea     r14, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001c243  mov     rsi, rcx
0x18001c246  mov     [r11-40h], rdi
0x18001c24a  lea     r15d, [rdi+0Fh]
0x18001c24e  mov     r9d, 3E4h
0x18001c254  lea     r12, aCdtcconfigStop; "CDtcConfig::StopTraceSession"
0x18001c25b  mov     ecx, r15d
0x18001c25e  mov     r8, r14
0x18001c261  mov     [r11-48h], r12
0x18001c265  lea     edx, [rdi+6]
0x18001c268  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c26d  cmp     [rsi+1Ch], edi
0x18001c270  jnz     short loc_18001C289
0x18001c272  mov     ebx, 80070032h
0x18001c277  lea     rax, aStoptracesessi; "StopTraceSession is not supported on a "...
0x18001c27e  mov     r9d, 3E8h
0x18001c284  jmp     loc_18001C389
0x18001c289  call    ?StopSession@CTrace@@QEAAJXZ; CTrace::StopSession(void)
0x18001c28e  mov     ebx, eax
0x18001c290  mov     r8, r14
0x18001c293  mov     ecx, r15d
0x18001c296  test    eax, eax
0x18001c298  jns     short loc_18001C2AC
0x18001c29a  lea     rax, aStopsessionFai; "StopSession failed"
0x18001c2a1  mov     r9d, 3EFh
0x18001c2a7  jmp     loc_18001C38F
0x18001c2ac  lea     rax, aTraceSessionSt; "Trace session stopped."
0x18001c2b3  mov     r9d, 3F3h
0x18001c2b9  mov     [rsp+68h+var_38], rax
0x18001c2be  mov     edx, 4
0x18001c2c3  mov     [rsp+68h+var_40], rdi
0x18001c2c8  mov     [rsp+68h+phkResult], r12
0x18001c2cd  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c2d2  lea     rdx, [rsp+68h+hKey]; HKEY *
0x18001c2d7  mov     rcx, rsi; this
0x18001c2da  call    ?GetHKLM@CDtcConfig@@AEAAJPEAPEAUHKEY__@@@Z; CDtcConfig::GetHKLM(HKEY__ * *)
0x18001c2df  mov     ebx, eax
0x18001c2e1  test    eax, eax
0x18001c2e3  jns     short loc_18001C31A
0x18001c2e5  lea     rax, aGethklmFailed_0; "GetHKLM failed."
0x18001c2ec  mov     r9d, 3F9h
0x18001c2f2  mov     [rsp+68h+var_38], rax
0x18001c2f7  mov     r8, r14
0x18001c2fa  mov     dword ptr [rsp+68h+var_40], ebx
0x18001c2fe  mov     edx, 1
0x18001c303  mov     ecx, r15d
0x18001c306  mov     [rsp+68h+phkResult], r12
0x18001c30b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c310  mov     rdi, [rsp+68h+hKey]
0x18001c315  jmp     loc_18001C3A7
0x18001c31a  mov     rdi, [rsp+68h+hKey]
0x18001c31f  lea     rax, [rsp+68h+arg_8]
0x18001c324  mov     rcx, rdi; hKey
0x18001c327  mov     [rsp+68h+phkResult], rax; phkResult
0x18001c32c  mov     r9d, 2; samDesired
0x18001c332  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001c339  xor     r8d, r8d; ulOptions
0x18001c33c  call    cs:__imp_RegOpenKeyExW
0x18001c342  mov     ebx, eax
0x18001c344  test    eax, eax
0x18001c346  jz      short loc_18001C362
0x18001c348  jle     short loc_18001C353
0x18001c34a  movzx   ebx, ax
0x18001c34d  or      ebx, 80070000h
0x18001c353  lea     rax, aRegopenkeyOpti; "RegOpenKey (options) failed"
0x18001c35a  mov     r9d, 405h
0x18001c360  jmp     short loc_18001C389
0x18001c362  mov     rdx, [rsp+68h+arg_8]; HKEY
0x18001c367  lea     r8, aRequestsession; "RequestSessionUp"
0x18001c36e  xor     r9d, r9d; unsigned int
0x18001c371  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x18001c376  mov     ebx, eax
0x18001c378  test    eax, eax
0x18001c37a  jns     short loc_18001C3A7
0x18001c37c  lea     rax, aFailedToWriteS; "Failed to write session up value"
0x18001c383  mov     r9d, 40Ch
0x18001c389  mov     ecx, r15d
0x18001c38c  mov     r8, r14
0x18001c38f  mov     [rsp+68h+var_38], rax
0x18001c394  mov     edx, 1
0x18001c399  mov     dword ptr [rsp+68h+var_40], ebx
0x18001c39d  mov     [rsp+68h+phkResult], r12
0x18001c3a2  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c3a7  mov     rcx, [rsp+68h+arg_8]; hKey
0x18001c3ac  test    rcx, rcx
0x18001c3af  jz      short loc_18001C3B7
0x18001c3b1  call    cs:__imp_RegCloseKey
0x18001c3b7  test    rdi, rdi
0x18001c3ba  jz      short loc_18001C3C5
0x18001c3bc  mov     rcx, rdi; hKey
0x18001c3bf  call    cs:__imp_RegCloseKey
0x18001c3c5  lea     rax, aOut; "Out"
0x18001c3cc  mov     r9d, 414h
0x18001c3d2  mov     [rsp+68h+var_38], rax
0x18001c3d7  mov     r8, r14
0x18001c3da  mov     dword ptr [rsp+68h+var_40], ebx
0x18001c3de  mov     edx, 6
0x18001c3e3  mov     ecx, r15d
0x18001c3e6  mov     [rsp+68h+phkResult], r12
0x18001c3eb  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001c3f0  mov     eax, ebx
0x18001c3f2  mov     rbx, [rsp+68h+arg_10]
0x18001c3fa  add     rsp, 40h
0x18001c3fe  pop     r15
0x18001c400  pop     r14
0x18001c402  pop     r12
0x18001c404  pop     rdi
0x18001c405  pop     rsi
0x18001c406  retn
```
