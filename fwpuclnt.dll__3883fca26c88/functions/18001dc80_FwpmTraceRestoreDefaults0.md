# FwpmTraceRestoreDefaults0

- ea: `0x18001dc80`
- end: `0x18001df01`
- name: `FwpmTraceRestoreDefaults0`
- size: `641`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800030a8`
- `0x1800034e0`
- `0x180004540`
- `0x180012bd0`
- `0x18001dc80`
- `0x18001df08`
- `0x1800490dc`
- `0x1800493a4`
- `0x180049784`
- `0x1800498ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dd2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dea1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ded0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001ded0`
- `ktmw32!CommitTransaction` at `0x18001de91`
- `ktmw32!CommitTransaction` at `0x18001de91`
- `ktmw32!CreateTransaction` at `0x18001dd18`
- `ktmw32!CreateTransaction` at `0x18001dd18`

## string_xrefs

- `0x18001dd39`: `CreateTransaction`
- `0x18001ddb1`: `%SystemRoot%\System32\LogFiles\WMI\wfp.etl`
- `0x18001dead`: `CommitTransaction`

## pseudocode

```c
__int64 FwpmTraceRestoreDefaults0()
{
  __int64 v0; // rdi
  HANDLE Transaction; // rax
  void *v2; // rsi
  DWORD LastError; // eax
  __int64 v4; // rcx
  const char *v5; // rdx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // rdx
  unsigned int i; // r14d
  __int64 v16; // [rsp+40h] [rbp-79h] BYREF
  WCHAR SubKey[64]; // [rsp+50h] [rbp-69h] BYREF

  v0 = 0;
  wcscpy(SubKey, L"SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger\\WFP-IPsec Trace");
  v16 = 0;
  Transaction = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  v2 = Transaction;
  if ( Transaction == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v5 = "CreateTransaction";
LABEL_17:
    v6 = WfpReportSysErrorAsWinError(v4, v5, LastError);
    goto LABEL_18;
  }
  v6 = BfeRegDeleteKey(HKEY_LOCAL_MACHINE, SubKey, Transaction);
  if ( !v6 )
  {
    v7 = BfeRegCreateKey(HKEY_LOCAL_MACHINE, SubKey, 0xFu, v2, &v16);
    v0 = v16;
    v6 = v7;
    if ( !v7 )
    {
      v6 = BfeRegSetDWord(v16, v8, L"Start", 0);
      if ( !v6 )
      {
        v6 = BfeRegSetString(v0, v9, L"FileName", L"%SystemRoot%\\System32\\LogFiles\\WMI\\wfp.etl");
        if ( !v6 )
        {
          v6 = BfeRegSetDWord(v0, v10, L"ClockType", 2);
          if ( !v6 )
          {
            v6 = BfeRegSetDWord(v0, v11, L"MaxFileSize", 8);
            if ( !v6 )
            {
              v6 = BfeRegSetDWord(v0, v12, L"LogFileMode", 4610);
              if ( !v6 )
              {
                v6 = BfeRegSetString(v0, v13, L"Guid", L"{0762bd13-14d5-4928-9db0-6c4e96312988}");
                if ( !v6 )
                {
                  for ( i = 0; i < 4; ++i )
                  {
                    v6 = FwppTraceAddProvider(
                           v0,
                           FWPP_TRACE_PROVIDERS[2 * i + 1],
                           HIDWORD(FWPP_TRACE_PROVIDERS[2 * i]),
                           FWPP_TRACE_PROVIDERS[2 * i],
                           (__int64)v2);
                    if ( v6 )
                      goto LABEL_18;
                  }
                  if ( !CommitTransaction(v2) )
                  {
                    LastError = GetLastError();
                    v5 = "CommitTransaction";
                    goto LABEL_17;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_18:
  BfeRegCloseKey(v0);
  if ( v2 != (void *)-1LL )
    CloseHandle(v2);
  return WfpErrorToFwpErr(v6);
}

```

## disassembly

```asm
0x18001dc80  push    rbp
0x18001dc82  push    rbx
0x18001dc83  push    rsi
0x18001dc84  push    rdi
0x18001dc85  push    r12
0x18001dc87  push    r14
0x18001dc89  lea     rbp, [rsp-2Fh]
0x18001dc8e  sub     rsp, 0E8h
0x18001dc95  mov     rax, cs:__security_cookie
0x18001dc9c  xor     rax, rsp
0x18001dc9f  mov     [rbp+57h+var_40], rax
0x18001dca3  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_4; "SYSTEM\\CurrentControlSet\\Control\\WMI"...
0x18001dcaa  xor     edi, edi
0x18001dcac  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_4+10h; "urrentControlSet\\Control\\WMI\\Autolog"...
0x18001dcb3  xor     r9d, r9d; IsolationLevel
0x18001dcb6  movaps  xmmword ptr [rbp+57h+SubKey], xmm0
0x18001dcba  xor     r8d, r8d; CreateOptions
0x18001dcbd  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_4+20h; "ntrolSet\\Control\\WMI\\Autologger\\WFP"...
0x18001dcc4  xor     edx, edx; UOW
0x18001dcc6  movaps  [rbp+57h+var_B0], xmm1
0x18001dcca  xor     ecx, ecx; lpTransactionAttributes
0x18001dccc  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_4+30h; "\\Control\\WMI\\Autologger\\WFP-IPsec T"...
0x18001dcd3  movaps  [rbp+57h+var_A0], xmm0
0x18001dcd7  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_4+40h; "\\WMI\\Autologger\\WFP-IPsec Trace"
0x18001dcde  movaps  [rbp+57h+var_90], xmm1
0x18001dce2  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_4+50h; "ologger\\WFP-IPsec Trace"
0x18001dce9  movaps  [rbp+57h+var_80], xmm0
0x18001dced  movaps  xmm0, xmmword ptr cs:aSystemCurrentc_4+60h; "WFP-IPsec Trace"
0x18001dcf4  movaps  [rbp+57h+var_70], xmm1
0x18001dcf8  movaps  xmm1, xmmword ptr cs:aSystemCurrentc_4+70h; "c Trace"
0x18001dcff  mov     [rsp+110h+Description], rdi; Description
0x18001dd04  mov     [rsp+110h+Timeout], edi; Timeout
0x18001dd08  movaps  [rbp+57h+var_60], xmm0
0x18001dd0c  movaps  [rbp+57h+var_50], xmm1
0x18001dd10  mov     [rbp+57h+var_D0], rdi
0x18001dd14  mov     [rsp+110h+IsolationFlags], edi; IsolationFlags
0x18001dd18  call    cs:__imp_CreateTransaction
0x18001dd1f  nop     dword ptr [rax+rax+00h]
0x18001dd24  mov     rsi, rax
0x18001dd27  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001dd2b  jnz     short loc_18001DD45
0x18001dd2d  call    cs:__imp_GetLastError
0x18001dd34  nop     dword ptr [rax+rax+00h]
0x18001dd39  lea     rdx, aCreatetransact_0; "CreateTransaction"
0x18001dd40  jmp     loc_18001DEB4
0x18001dd45  mov     r14, 0FFFFFFFF80000002h
0x18001dd4c  lea     rdx, [rbp+57h+SubKey]; lpSubKey
0x18001dd50  mov     rcx, r14; hKey
0x18001dd53  mov     r8, rsi; hTransaction
0x18001dd56  call    BfeRegDeleteKey
0x18001dd5b  mov     rbx, rax
0x18001dd5e  test    rax, rax
0x18001dd61  jnz     loc_18001DEBF
0x18001dd67  lea     rax, [rbp+57h+var_D0]
0x18001dd6b  mov     r9, rsi
0x18001dd6e  lea     r8d, [rbx+0Fh]
0x18001dd72  mov     qword ptr [rsp+110h+IsolationFlags], rax
0x18001dd77  lea     rdx, [rbp+57h+SubKey]
0x18001dd7b  mov     rcx, r14
0x18001dd7e  call    BfeRegCreateKey
0x18001dd83  mov     rdi, [rbp+57h+var_D0]
0x18001dd87  mov     rbx, rax
0x18001dd8a  test    rax, rax
0x18001dd8d  jnz     loc_18001DEBF
0x18001dd93  xor     r9d, r9d
0x18001dd96  lea     r8, aStart; "Start"
0x18001dd9d  mov     rcx, rdi
0x18001dda0  call    BfeRegSetDWord
0x18001dda5  mov     rbx, rax
0x18001dda8  test    rax, rax
0x18001ddab  jnz     loc_18001DEBF
0x18001ddb1  lea     r9, aSystemrootSyst; "%SystemRoot%\\System32\\LogFiles\\WMI\\"...
0x18001ddb8  mov     rcx, rdi
0x18001ddbb  lea     r8, aFilename; "FileName"
0x18001ddc2  call    BfeRegSetString
0x18001ddc7  mov     rbx, rax
0x18001ddca  test    rax, rax
0x18001ddcd  jnz     loc_18001DEBF
0x18001ddd3  lea     r9d, [rax+2]
0x18001ddd7  mov     rcx, rdi
0x18001ddda  lea     r8, aClocktype; "ClockType"
0x18001dde1  call    BfeRegSetDWord
0x18001dde6  mov     rbx, rax
0x18001dde9  test    rax, rax
0x18001ddec  jnz     loc_18001DEBF
0x18001ddf2  lea     r9d, [rax+8]
0x18001ddf6  mov     rcx, rdi
0x18001ddf9  lea     r8, aMaxfilesize; "MaxFileSize"
0x18001de00  call    BfeRegSetDWord
0x18001de05  mov     rbx, rax
0x18001de08  test    rax, rax
0x18001de0b  jnz     loc_18001DEBF
0x18001de11  mov     r9d, 1202h
0x18001de17  lea     r8, aLogfilemode; "LogFileMode"
0x18001de1e  mov     rcx, rdi
0x18001de21  call    BfeRegSetDWord
0x18001de26  mov     rbx, rax
0x18001de29  test    rax, rax
0x18001de2c  jnz     loc_18001DEBF
0x18001de32  lea     r9, a0762bd1314d549; "{0762bd13-14d5-4928-9db0-6c4e96312988}"
0x18001de39  mov     rcx, rdi
0x18001de3c  lea     r8, aGuid; "Guid"
0x18001de43  call    BfeRegSetString
0x18001de48  mov     rbx, rax
0x18001de4b  test    rax, rax
0x18001de4e  jnz     short loc_18001DEBF
0x18001de50  xor     r14d, r14d
0x18001de53  lea     r12, FWPP_TRACE_PROVIDERS
0x18001de5a  cmp     r14d, 4
0x18001de5e  jnb     short loc_18001DE8E
0x18001de60  mov     edx, r14d
0x18001de63  mov     rcx, rdi
0x18001de66  add     rdx, rdx
0x18001de69  mov     qword ptr [rsp+110h+IsolationFlags], rsi
0x18001de6e  mov     r9d, [r12+rdx*8]
0x18001de72  mov     r8d, [r12+rdx*8+4]
0x18001de77  mov     rdx, [r12+rdx*8+8]
0x18001de7c  call    FwppTraceAddProvider
0x18001de81  mov     rbx, rax
0x18001de84  test    rax, rax
0x18001de87  jnz     short loc_18001DEBF
0x18001de89  inc     r14d
0x18001de8c  jmp     short loc_18001DE5A
0x18001de8e  mov     rcx, rsi; TransactionHandle
0x18001de91  call    cs:__imp_CommitTransaction
0x18001de98  nop     dword ptr [rax+rax+00h]
0x18001de9d  test    eax, eax
0x18001de9f  jnz     short loc_18001DEBF
0x18001dea1  call    cs:__imp_GetLastError
0x18001dea8  nop     dword ptr [rax+rax+00h]
0x18001dead  lea     rdx, aCommittransact_0; "CommitTransaction"
0x18001deb4  mov     r8d, eax
0x18001deb7  call    WfpReportSysErrorAsWinError
0x18001debc  mov     rbx, rax
0x18001debf  mov     rcx, rdi
0x18001dec2  call    BfeRegCloseKey
0x18001dec7  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001decb  jz      short loc_18001DEDC
0x18001decd  mov     rcx, rsi; hObject
0x18001ded0  call    cs:__imp_CloseHandle
0x18001ded7  nop     dword ptr [rax+rax+00h]
0x18001dedc  mov     rcx, rbx
0x18001dedf  call    WfpErrorToFwpErr
0x18001dee4  mov     rcx, [rbp+57h+var_40]
0x18001dee8  xor     rcx, rsp; StackCookie
0x18001deeb  call    __security_check_cookie
0x18001def0  add     rsp, 0E8h
0x18001def7  pop     r14
0x18001def9  pop     r12
0x18001defb  pop     rdi
0x18001defc  pop     rsi
0x18001defd  pop     rbx
0x18001defe  pop     rbp
0x18001deff  retn
```
