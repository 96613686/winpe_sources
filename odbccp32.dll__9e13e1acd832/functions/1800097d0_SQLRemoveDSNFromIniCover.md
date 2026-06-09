# SQLRemoveDSNFromIniCover

- ea: `0x1800097d0`
- end: `0x180009956`
- name: `SQLRemoveDSNFromIniCover`
- size: `390`
- prototype: `__int64 __fastcall(LPCWSTR lpAppName)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180009960`
- `0x180009e8c`

## callees

- `0x180004bac`
- `0x180004d40`
- `0x1800097d0`
- `0x180009dc0`
- `0x18000a320`
- `0x180014ae0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180009813`
- `msvcrt!_wcsicmp` at `0x18000989f`
- `msvcrt!_wcsicmp` at `0x180009813`
- `msvcrt!_wcsicmp` at `0x18000989f`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800098fa`
- `KERNEL32!GetPrivateProfileStringW` at `0x1800098fa`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800098d1`
- `KERNEL32!WritePrivateProfileStringW` at `0x180009918`
- `KERNEL32!WritePrivateProfileStringW` at `0x1800098d1`
- `KERNEL32!WritePrivateProfileStringW` at `0x180009918`

## pseudocode

```c
__int64 __fastcall SQLRemoveDSNFromIniCover(LPCWSTR lpAppName)
{
  WORD v2; // di
  SQLRETURN v3; // ax
  int v4; // ecx
  const WCHAR *v5; // rdx
  DWORD pfErrorCode[4]; // [rsp+30h] [rbp-248h] BYREF
  WCHAR ReturnedString[264]; // [rsp+40h] [rbp-238h] BYREF

  if ( !(unsigned int)SQLValidDSNCover() || !_wcsicmp(lpAppName, L"ODBC Data Sources") )
  {
    v4 = 9;
    goto LABEL_16;
  }
  if ( !SQLWritePrivateProfileStringW(L"ODBC Data Sources", lpAppName, 0, L"ODBC.INI") )
  {
    pfErrorCode[0] = 0;
    v2 = 1;
    while ( pfErrorCode[0] != 6 )
    {
      v3 = SQLInstallerErrorW(v2++, pfErrorCode, 0, 0, 0);
      if ( (unsigned __int16)v3 >= 2u )
        goto LABEL_7;
    }
    goto LABEL_11;
  }
  if ( !SQLWritePrivateProfileStringW(lpAppName, 0, 0, L"ODBC.INI")
    || !_wcsicmp(lpAppName, L"Default") && !SQLWritePrivateProfileStringW(lpAppName, 0, 0, L"ODBCINST.INI") )
  {
LABEL_7:
    v4 = 20;
LABEL_16:
    PostInstError(v4);
    return 0;
  }
LABEL_11:
  WritePrivateProfileStringW(L"ODBC 32 bit Data Sources", lpAppName, 0, L"ODBC.INI");
  if ( GetPrivateProfileStringW(lpAppName, L"Driver", &SubKey, ReturnedString, 2u, L"ODBC.INI") )
    v5 = L"Driver32";
  else
    v5 = 0;
  WritePrivateProfileStringW(lpAppName, v5, 0, L"ODBC.INI");
  return 1;
}

```

## disassembly

```asm
0x1800097d0  mov     [rsp+arg_8], rbx
0x1800097d5  mov     [rsp+arg_10], rbp
0x1800097da  push    rsi
0x1800097db  push    rdi
0x1800097dc  push    r14
0x1800097de  sub     rsp, 260h
0x1800097e5  mov     rax, cs:__security_cookie
0x1800097ec  xor     rax, rsp
0x1800097ef  mov     [rsp+278h+var_28], rax
0x1800097f7  mov     rbx, rcx
0x1800097fa  call    SQLValidDSNCover
0x1800097ff  xor     esi, esi
0x180009801  test    eax, eax
0x180009803  jz      loc_180009922
0x180009809  lea     rdx, aOdbcDataSource; "ODBC Data Sources"
0x180009810  mov     rcx, rbx; String1
0x180009813  call    cs:__imp__wcsicmp
0x180009819  test    eax, eax
0x18000981b  jz      loc_180009922
0x180009821  lea     r14, aOdbcIni; "ODBC.INI"
0x180009828  xor     r8d, r8d; lpszString
0x18000982b  mov     r9, r14; lpszFilename
0x18000982e  lea     rcx, aOdbcDataSource; "ODBC Data Sources"
0x180009835  mov     rdx, rbx; lpszEntry
0x180009838  call    SQLWritePrivateProfileStringW
0x18000983d  lea     ebp, [rsi+1]
0x180009840  test    eax, eax
0x180009842  jnz     short loc_180009881
0x180009844  mov     [rsp+278h+pfErrorCode], esi
0x180009848  movzx   edi, bp
0x18000984b  cmp     [rsp+278h+pfErrorCode], 6
0x180009850  jz      short loc_1800098C1
0x180009852  xor     r9d, r9d; cchErrorMsgMax
0x180009855  mov     [rsp+278h+pcchErrorMsg], rsi; pcchErrorMsg
0x18000985a  xor     r8d, r8d; lpszErrorMsg
0x18000985d  lea     rdx, [rsp+278h+pfErrorCode]; pfErrorCode
0x180009862  movzx   ecx, di; iError
0x180009865  call    SQLInstallerErrorW
0x18000986a  add     di, bp
0x18000986d  test    ax, ax
0x180009870  jz      short loc_18000984B
0x180009872  cmp     ax, bp
0x180009875  jz      short loc_18000984B
0x180009877  mov     ecx, 14h
0x18000987c  jmp     loc_180009927
0x180009881  mov     r9, r14; lpszFilename
0x180009884  xor     r8d, r8d; lpszString
0x180009887  xor     edx, edx; lpszEntry
0x180009889  mov     rcx, rbx; lpszSection
0x18000988c  call    SQLWritePrivateProfileStringW
0x180009891  test    eax, eax
0x180009893  jz      short loc_180009877
0x180009895  lea     rdx, aDefault; "Default"
0x18000989c  mov     rcx, rbx; String1
0x18000989f  call    cs:__imp__wcsicmp
0x1800098a5  test    eax, eax
0x1800098a7  jnz     short loc_1800098C1
0x1800098a9  lea     r9, aOdbcinstIni; "ODBCINST.INI"
0x1800098b0  xor     r8d, r8d; lpszString
0x1800098b3  xor     edx, edx; lpszEntry
0x1800098b5  mov     rcx, rbx; lpszSection
0x1800098b8  call    SQLWritePrivateProfileStringW
0x1800098bd  test    eax, eax
0x1800098bf  jz      short loc_180009877
0x1800098c1  mov     r9, r14; lpFileName
0x1800098c4  lea     rcx, aOdbc32BitDataS; "ODBC 32 bit Data Sources"
0x1800098cb  xor     r8d, r8d; lpString
0x1800098ce  mov     rdx, rbx; lpKeyName
0x1800098d1  call    cs:__imp_WritePrivateProfileStringW
0x1800098d7  lea     r9, [rsp+278h+ReturnedString]; lpReturnedString
0x1800098dc  mov     [rsp+278h+lpFileName], r14; lpFileName
0x1800098e1  lea     r8, SubKey; lpDefault
0x1800098e8  mov     dword ptr [rsp+278h+pcchErrorMsg], 2; nSize
0x1800098f0  lea     rdx, aDriver_0; "Driver"
0x1800098f7  mov     rcx, rbx; lpAppName
0x1800098fa  call    cs:__imp_GetPrivateProfileStringW
0x180009900  xor     r8d, r8d; lpString
0x180009903  mov     r9, r14; lpFileName
0x180009906  mov     rcx, rbx; lpAppName
0x180009909  test    eax, eax
0x18000990b  jz      short loc_180009916
0x18000990d  lea     rdx, aDriver32; "Driver32"
0x180009914  jmp     short loc_180009918
0x180009916  xor     edx, edx; lpKeyName
0x180009918  call    cs:__imp_WritePrivateProfileStringW
0x18000991e  mov     eax, ebp
0x180009920  jmp     short loc_18000992E
0x180009922  mov     ecx, 9
0x180009927  call    PostInstError
0x18000992c  xor     eax, eax
0x18000992e  mov     rcx, [rsp+278h+var_28]
0x180009936  xor     rcx, rsp; StackCookie
0x180009939  call    __security_check_cookie
0x18000993e  lea     r11, [rsp+278h+var_18]
0x180009946  mov     rbx, [r11+28h]
0x18000994a  mov     rbp, [r11+30h]
0x18000994e  mov     rsp, r11
0x180009951  pop     r14
0x180009953  pop     rdi
0x180009954  pop     rsi
0x180009955  retn
```
