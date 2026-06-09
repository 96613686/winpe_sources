# DsRolepSetDcSecurity

- ea: `0x18001ff18`
- end: `0x18002007d`
- name: `DsRolepSetDcSecurity`
- size: `357`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180011240`
- `0x180012460`

## callees

- `0x180016374`
- `0x18001e204`
- `0x18001ff18`
- `0x180020dbc`
- `0x180020e50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002000c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002000c`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18001ff6f`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180020002`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x18001ff6f`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x180020002`
- `ntdll!RtlInitUnicodeString` at `0x18002004a`
- `ntdll!RtlInitUnicodeString` at `0x18002004a`
- `SCECLI!SceDcPromoteSecurityEx` at `0x18001ffd4`
- `SCECLI!SceDcPromoteSecurityEx` at `0x18001ffd4`

## string_xrefs

- `0x18001ffe8`: `Setting security on Dc files failed with %lu\n`
- `0x18002003b`: `%windir%\security\logs\scedcpro.log`

## pseudocode

```c
__int64 __fastcall DsRolepSetDcSecurity(
        __int64 a1,
        const WCHAR *a2,
        const WCHAR *a3,
        const WCHAR *a4,
        char a5,
        char a6)
{
  __int64 v7; // rbx
  const WCHAR *v8; // rsi
  const WCHAR *v9; // r14
  DWORD LastError; // edi
  __int64 i; // rbx
  DWORD v12; // eax
  __int64 v13; // r9
  LPCWSTR lpName[2]; // [rsp+30h] [rbp-38h] BYREF
  const wchar_t *v16; // [rsp+40h] [rbp-28h]
  LPCWSTR lpValue[4]; // [rsp+48h] [rbp-20h]

  lpValue[0] = a2;
  lpName[0] = L"SYSVOL";
  lpValue[1] = a3;
  lpName[1] = L"DSDIT";
  v7 = 0;
  lpValue[2] = a4;
  v16 = L"DSLOG";
  while ( (unsigned int)v7 < 3 )
  {
    v8 = lpValue[v7];
    v9 = lpName[v7];
    if ( !SetEnvironmentVariableW(v9, v8) )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(4, "SetEnvironmentVariable %ws = %ws failed with %lu\n", v9, v8, LastError);
      if ( LastError )
        goto LABEL_8;
      break;
    }
    v7 = (unsigned int)(v7 + 1);
  }
  DsRolepSetAndClearLog();
  DsRolepSetCurrentOperationStatus(28721, 0, 0);
  LastError = SceDcPromoteSecurityEx(
                a1,
                (a6 != 0 ? 2 : 0) | (unsigned int)(a5 != 0),
                DsRolepDfsrStringUpdateCallbackNoFlags);
  DsRolepSetAndClearLog();
  if ( LastError )
    DsRolepLogPrintRoutine(1, "Setting security on Dc files failed with %lu\n", LastError);
LABEL_8:
  for ( i = 0; i != 3; ++i )
  {
    if ( !SetEnvironmentVariableW(lpName[i], 0) )
    {
      v12 = GetLastError();
      DsRolepLogPrintRoutine(4, "SetEnvironmentVariable %ws = NULL failed with %lu\n", lpName[i], v12);
    }
  }
  if ( LastError )
  {
    *(_OWORD *)lpName = 0;
    RtlInitUnicodeString((PUNICODE_STRING)lpName, L"%windir%\\security\\logs\\scedcpro.log");
    DsRolepEventWrite(DSROLERES_FAIL_SET_SECURITY_EVENT, L"u", lpName, v13);
    dword_18004E218 |= 1u;
  }
  return 0;
}

```

## disassembly

```asm
0x18001ff18  push    rbp
0x18001ff1a  push    rbx
0x18001ff1b  push    rsi
0x18001ff1c  push    rdi
0x18001ff1d  push    r14
0x18001ff1f  push    r15
0x18001ff21  mov     rbp, rsp
0x18001ff24  sub     rsp, 68h
0x18001ff28  lea     rax, netname; "SYSVOL"
0x18001ff2f  mov     [rbp+lpValue], rdx
0x18001ff33  mov     [rbp+lpName], rax
0x18001ff37  mov     r15, rcx
0x18001ff3a  lea     rax, aDsdit; "DSDIT"
0x18001ff41  mov     [rbp+var_18], r8
0x18001ff45  mov     [rbp+lpName+8], rax
0x18001ff49  xor     ebx, ebx
0x18001ff4b  lea     rax, aDslog; "DSLOG"
0x18001ff52  mov     [rbp+var_10], r9
0x18001ff56  mov     [rbp+var_28], rax
0x18001ff5a  cmp     ebx, 3
0x18001ff5d  jnb     short loc_18001FFA4
0x18001ff5f  mov     rsi, [rbp+rbx*8+lpValue]
0x18001ff64  mov     r14, [rbp+rbx*8+lpName]
0x18001ff69  mov     rdx, rsi; lpValue
0x18001ff6c  mov     rcx, r14; lpName
0x18001ff6f  call    cs:__imp_SetEnvironmentVariableW
0x18001ff75  test    eax, eax
0x18001ff77  jz      short loc_18001FF7D
0x18001ff79  inc     ebx
0x18001ff7b  jmp     short loc_18001FF5A
0x18001ff7d  call    cs:__imp_GetLastError
0x18001ff83  mov     r9, rsi
0x18001ff86  lea     rdx, aSetenvironment; "SetEnvironmentVariable %ws = %ws failed"...
0x18001ff8d  mov     r8, r14
0x18001ff90  mov     [rsp+68h+var_48], eax
0x18001ff94  mov     ecx, 4
0x18001ff99  mov     edi, eax
0x18001ff9b  call    DsRolepLogPrintRoutine
0x18001ffa0  test    edi, edi
0x18001ffa2  jnz     short loc_18001FFF9
0x18001ffa4  call    DsRolepSetAndClearLog
0x18001ffa9  xor     r8d, r8d
0x18001ffac  xor     edx, edx
0x18001ffae  mov     ecx, 7031h
0x18001ffb3  call    DsRolepSetCurrentOperationStatus
0x18001ffb8  xor     edx, edx
0x18001ffba  lea     r8, DsRolepDfsrStringUpdateCallbackNoFlags
0x18001ffc1  cmp     [rbp+arg_20], dl
0x18001ffc4  mov     rcx, r15
0x18001ffc7  setnz   dl
0x18001ffca  neg     [rbp+arg_28]
0x18001ffcd  sbb     eax, eax
0x18001ffcf  and     eax, 2
0x18001ffd2  or      edx, eax
0x18001ffd4  call    cs:__imp_SceDcPromoteSecurityEx
0x18001ffda  mov     edi, eax
0x18001ffdc  call    DsRolepSetAndClearLog
0x18001ffe1  test    edi, edi
0x18001ffe3  jz      short loc_18001FFF9
0x18001ffe5  mov     r8d, edi
0x18001ffe8  lea     rdx, aSettingSecurit_1; "Setting security on Dc files failed wit"...
0x18001ffef  mov     ecx, 1
0x18001fff4  call    DsRolepLogPrintRoutine
0x18001fff9  xor     ebx, ebx
0x18001fffb  mov     rcx, [rbp+rbx*8+lpName]; lpName
0x180020000  xor     edx, edx; lpValue
0x180020002  call    cs:__imp_SetEnvironmentVariableW
0x180020008  test    eax, eax
0x18002000a  jnz     short loc_18002002B
0x18002000c  call    cs:__imp_GetLastError
0x180020012  mov     r8, [rbp+rbx*8+lpName]
0x180020017  lea     rdx, aSetenvironment_0; "SetEnvironmentVariable %ws = NULL faile"...
0x18002001e  mov     r9d, eax
0x180020021  mov     ecx, 4
0x180020026  call    DsRolepLogPrintRoutine
0x18002002b  inc     rbx
0x18002002e  cmp     rbx, 3
0x180020032  jnz     short loc_18001FFFB
0x180020034  test    edi, edi
0x180020036  jz      short loc_18002006E
0x180020038  xorps   xmm0, xmm0
0x18002003b  lea     rdx, aWindirSecurity; "%windir%\\security\\logs\\scedcpro.log"
0x180020042  lea     rcx, [rbp+lpName]; DestinationString
0x180020046  movups  xmmword ptr [rbp+lpName], xmm0
0x18002004a  call    cs:__imp_RtlInitUnicodeString
0x180020050  lea     r8, [rbp+lpName]
0x180020054  lea     rdx, aU; "u"
0x18002005b  lea     rcx, DSROLERES_FAIL_SET_SECURITY_EVENT
0x180020062  call    DsRolepEventWrite
0x180020067  or      cs:dword_18004E218, 1
0x18002006e  xor     eax, eax
0x180020070  add     rsp, 68h
0x180020074  pop     r15
0x180020076  pop     r14
0x180020078  pop     rdi
0x180020079  pop     rsi
0x18002007a  pop     rbx
0x18002007b  pop     rbp
0x18002007c  retn
```
