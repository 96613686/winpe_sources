# CDtcConfig::NewTraceSession(void)

- ea: `0x18001b150`
- end: `0x18001b34a`
- name: `?NewTraceSession@CDtcConfig@@UEAAJXZ`
- size: `506`
- prototype: `__int64 __fastcall(CDtcConfig *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003cf0`
- `0x18001430c`
- `0x180018ba0`
- `0x18001b150`
- `0x18001c924`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b27c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001b27c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b302`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b2f4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001b302`

## string_xrefs

- `0x18001b17c`: `com\complus\dtc\dtc\msdtcprx\src\dtcconfig.cpp`
- `0x18001b293`: `RegOpenKey failed`
- `0x18001b2bf`: `Failed to write session up value`
- `0x18001b194`: `CDtcConfig::NewTraceSession`

## pseudocode

```c
__int64 __fastcall CDtcConfig::NewTraceSession(CDtcConfig *this)
{
  HKEY v1; // rdi
  int v3; // edx
  CTrace *v4; // rcx
  signed int inited; // ebx
  const wchar_t *v6; // rax
  __int64 v7; // r9
  LSTATUS v8; // eax
  CDtcConfig *v9; // rcx
  __int64 v11; // [rsp+28h] [rbp-40h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp+10h] BYREF

  v1 = 0;
  phkResult = 0;
  hKey = 0;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1055,
    L"CDtcConfig::NewTraceSession",
    0,
    L"In");
  if ( *((_DWORD *)this + 7) )
  {
    inited = CTrace::InitSession(v4, v3);
    if ( inited >= 0 )
    {
      TraceStringInline(
        15,
        4,
        L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
        1072,
        L"CDtcConfig::NewTraceSession",
        0,
        L"A new trace session started.");
      inited = CDtcConfig::GetHKLM(this, &hKey);
      if ( inited < 0 )
      {
        LODWORD(v11) = inited;
        TraceStringInline(
          15,
          1,
          L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
          1077,
          L"CDtcConfig::NewTraceSession",
          v11,
          L"GetHKLM failed");
        v1 = hKey;
        goto LABEL_14;
      }
      v1 = hKey;
      v8 = RegOpenKeyExW(
             hKey,
             L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Tracing\\MSDTC\\LoggingOptions",
             0,
             2u,
             &phkResult);
      inited = v8;
      if ( v8 )
      {
        if ( v8 > 0 )
          inited = (unsigned __int16)v8 | 0x80070000;
        v6 = L"RegOpenKey failed";
        v7 = 1089;
      }
      else
      {
        inited = CDtcConfig::WriteRegDWORD(v9, phkResult, L"RequestSessionUp", 1u);
        if ( inited >= 0 )
          goto LABEL_14;
        v6 = L"Failed to write session up value";
        v7 = 1096;
      }
    }
    else
    {
      v6 = L"InitSession failed";
      v7 = 1068;
    }
  }
  else
  {
    inited = -2147024846;
    v6 = L"NewTraceSession is not supported on a remote host";
    v7 = 1061;
  }
  LODWORD(v11) = inited;
  TraceStringInline(
    15,
    1,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    v7,
    L"CDtcConfig::NewTraceSession",
    v11,
    v6);
LABEL_14:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v1 )
    RegCloseKey(v1);
  LODWORD(v11) = inited;
  TraceStringInline(
    15,
    6,
    L"com\\complus\\dtc\\dtc\\msdtcprx\\src\\dtcconfig.cpp",
    1103,
    L"CDtcConfig::NewTraceSession",
    v11,
    L"Out");
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18001b150  mov     r11, rsp
0x18001b153  mov     [r11+18h], rbx
0x18001b157  push    rsi
0x18001b158  push    rdi
0x18001b159  push    r12
0x18001b15b  push    r14
0x18001b15d  push    r15
0x18001b15f  sub     rsp, 40h
0x18001b163  xor     edi, edi
0x18001b165  mov     qword ptr [r11+10h], 0
0x18001b16d  lea     rax, aIn_0; "In"
0x18001b174  mov     [r11+8], rdi
0x18001b178  mov     [r11-38h], rax
0x18001b17c  lea     r14, aComComplusDtcD_19; "com\\complus\\dtc\\dtc\\msdtcprx\\src\\"...
0x18001b183  mov     rsi, rcx
0x18001b186  mov     [r11-40h], rdi
0x18001b18a  lea     r15d, [rdi+0Fh]
0x18001b18e  mov     r9d, 41Fh
0x18001b194  lea     r12, aCdtcconfigNewt; "CDtcConfig::NewTraceSession"
0x18001b19b  mov     ecx, r15d
0x18001b19e  mov     r8, r14
0x18001b1a1  mov     [r11-48h], r12
0x18001b1a5  lea     edx, [rdi+6]
0x18001b1a8  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b1ad  cmp     [rsi+1Ch], edi
0x18001b1b0  jnz     short loc_18001B1C9
0x18001b1b2  mov     ebx, 80070032h
0x18001b1b7  lea     rax, aNewtracesessio; "NewTraceSession is not supported on a r"...
0x18001b1be  mov     r9d, 425h
0x18001b1c4  jmp     loc_18001B2CC
0x18001b1c9  call    ?InitSession@CTrace@@QEAAJH@Z; CTrace::InitSession(int)
0x18001b1ce  mov     ebx, eax
0x18001b1d0  mov     r8, r14
0x18001b1d3  mov     ecx, r15d
0x18001b1d6  test    eax, eax
0x18001b1d8  jns     short loc_18001B1EC
0x18001b1da  lea     rax, aInitsessionFai; "InitSession failed"
0x18001b1e1  mov     r9d, 42Ch
0x18001b1e7  jmp     loc_18001B2D2
0x18001b1ec  lea     rax, aANewTraceSessi; "A new trace session started."
0x18001b1f3  mov     r9d, 430h
0x18001b1f9  mov     [rsp+68h+var_38], rax
0x18001b1fe  mov     edx, 4
0x18001b203  mov     [rsp+68h+var_40], rdi
0x18001b208  mov     [rsp+68h+phkResult], r12
0x18001b20d  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b212  lea     rdx, [rsp+68h+hKey]; HKEY *
0x18001b217  mov     rcx, rsi; this
0x18001b21a  call    ?GetHKLM@CDtcConfig@@AEAAJPEAPEAUHKEY__@@@Z; CDtcConfig::GetHKLM(HKEY__ * *)
0x18001b21f  mov     ebx, eax
0x18001b221  test    eax, eax
0x18001b223  jns     short loc_18001B25A
0x18001b225  lea     rax, aGethklmFailed; "GetHKLM failed"
0x18001b22c  mov     r9d, 435h
0x18001b232  mov     [rsp+68h+var_38], rax
0x18001b237  mov     r8, r14
0x18001b23a  mov     dword ptr [rsp+68h+var_40], ebx
0x18001b23e  mov     edx, 1
0x18001b243  mov     ecx, r15d
0x18001b246  mov     [rsp+68h+phkResult], r12
0x18001b24b  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b250  mov     rdi, [rsp+68h+hKey]
0x18001b255  jmp     loc_18001B2EA
0x18001b25a  mov     rdi, [rsp+68h+hKey]
0x18001b25f  lea     rax, [rsp+68h+arg_8]
0x18001b264  mov     rcx, rdi; hKey
0x18001b267  mov     [rsp+68h+phkResult], rax; phkResult
0x18001b26c  mov     r9d, 2; samDesired
0x18001b272  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001b279  xor     r8d, r8d; ulOptions
0x18001b27c  call    cs:__imp_RegOpenKeyExW
0x18001b282  mov     ebx, eax
0x18001b284  test    eax, eax
0x18001b286  jz      short loc_18001B2A2
0x18001b288  jle     short loc_18001B293
0x18001b28a  movzx   ebx, ax
0x18001b28d  or      ebx, 80070000h
0x18001b293  lea     rax, aRegopenkeyFail; "RegOpenKey failed"
0x18001b29a  mov     r9d, 441h
0x18001b2a0  jmp     short loc_18001B2CC
0x18001b2a2  mov     rdx, [rsp+68h+arg_8]; HKEY
0x18001b2a7  lea     r8, aRequestsession; "RequestSessionUp"
0x18001b2ae  mov     r9d, 1; unsigned int
0x18001b2b4  call    ?WriteRegDWORD@CDtcConfig@@AEAAJPEAUHKEY__@@PEBGK@Z; CDtcConfig::WriteRegDWORD(HKEY__ *,ushort const *,ulong)
0x18001b2b9  mov     ebx, eax
0x18001b2bb  test    eax, eax
0x18001b2bd  jns     short loc_18001B2EA
0x18001b2bf  lea     rax, aFailedToWriteS; "Failed to write session up value"
0x18001b2c6  mov     r9d, 448h
0x18001b2cc  mov     ecx, r15d
0x18001b2cf  mov     r8, r14
0x18001b2d2  mov     [rsp+68h+var_38], rax
0x18001b2d7  mov     edx, 1
0x18001b2dc  mov     dword ptr [rsp+68h+var_40], ebx
0x18001b2e0  mov     [rsp+68h+phkResult], r12
0x18001b2e5  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b2ea  mov     rcx, [rsp+68h+arg_8]; hKey
0x18001b2ef  test    rcx, rcx
0x18001b2f2  jz      short loc_18001B2FA
0x18001b2f4  call    cs:__imp_RegCloseKey
0x18001b2fa  test    rdi, rdi
0x18001b2fd  jz      short loc_18001B308
0x18001b2ff  mov     rcx, rdi; hKey
0x18001b302  call    cs:__imp_RegCloseKey
0x18001b308  lea     rax, aOut; "Out"
0x18001b30f  mov     r9d, 44Fh
0x18001b315  mov     [rsp+68h+var_38], rax
0x18001b31a  mov     r8, r14
0x18001b31d  mov     dword ptr [rsp+68h+var_40], ebx
0x18001b321  mov     edx, 6
0x18001b326  mov     ecx, r15d
0x18001b329  mov     [rsp+68h+phkResult], r12
0x18001b32e  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18001b333  mov     eax, ebx
0x18001b335  mov     rbx, [rsp+68h+arg_10]
0x18001b33d  add     rsp, 40h
0x18001b341  pop     r15
0x18001b343  pop     r14
0x18001b345  pop     r12
0x18001b347  pop     rdi
0x18001b348  pop     rsi
0x18001b349  retn
```
