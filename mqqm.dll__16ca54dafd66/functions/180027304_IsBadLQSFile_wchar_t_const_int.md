# IsBadLQSFile(wchar_t const *,int)

- ea: `0x180027304`
- end: `0x180027486`
- name: `?IsBadLQSFile@@YAJPEB_WH@Z`
- size: `386`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800287a4`

## callees

- `0x18000cb80`
- `0x18000e558`
- `0x180027304`
- `0x18002c61c`
- `0x1800d6ea0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002740a`
- `KERNEL32!GetLastError` at `0x18002740a`
- `KERNEL32!CompareStringW` at `0x180027392`
- `KERNEL32!CompareStringW` at `0x1800273cd`
- `KERNEL32!CompareStringW` at `0x180027392`
- `KERNEL32!CompareStringW` at `0x1800273cd`
- `KERNEL32!DeleteFileW` at `0x1800273f3`
- `KERNEL32!DeleteFileW` at `0x1800273f3`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002735a`
- `KERNEL32!GetPrivateProfileStringW` at `0x18002735a`

## pseudocode

```c
__int64 __fastcall IsBadLQSFile(LPCWSTR lpFileName)
{
  DWORD PrivateProfileStringW; // ebx
  unsigned __int16 v4; // r8
  unsigned int v5; // ebx
  char LastError; // al
  WCHAR ReturnedString[64]; // [rsp+30h] [rbp-98h] BYREF

  ReturnedString[0] = 0;
  PrivateProfileStringW = GetPrivateProfileStringW(
                            L"Properties",
                            L"Signature",
                            &ServiceName,
                            ReturnedString,
                            0x40u,
                            lpFileName);
  if ( PrivateProfileStringW == mqwcslen(L"DoronJ") && CompareStringW(0x7Fu, 1u, ReturnedString, -1, L"DoronJ", -1) == 2
    || PrivateProfileStringW == mqwcslen(L"MSMQStorage")
    && CompareStringW(0x7Fu, 1u, ReturnedString, -1, L"MSMQStorage", -1) == 2 )
  {
    return 0;
  }
  if ( PrivateProfileStringW )
  {
    if ( DeleteFileW(lpFileName) )
    {
      v4 = 350;
      v5 = -1072824216;
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), LastError);
      v4 = 360;
      v5 = -1072824319;
    }
  }
  else
  {
    v4 = 340;
    v5 = -1072824281;
  }
  LogMsgHR(v5, (wchar_t *)L"lqs", v4);
  return v5;
}

```

## disassembly

```asm
0x180027304  mov     [rsp+arg_8], rbx
0x180027309  mov     [rsp+arg_10], rdi
0x18002730e  push    r14
0x180027310  sub     rsp, 0C0h
0x180027317  mov     rax, cs:__security_cookie
0x18002731e  xor     rax, rsp
0x180027321  mov     [rsp+0C8h+var_18], rax
0x180027329  mov     [rsp+0C8h+lpFileName], rcx; lpFileName
0x18002732e  lea     r9, [rsp+0C8h+ReturnedString]; lpReturnedString
0x180027333  mov     rdi, rcx
0x180027336  mov     [rsp+0C8h+nSize], 40h ; '@'; nSize
0x18002733e  xor     eax, eax
0x180027340  lea     rcx, AppName; "Properties"
0x180027347  lea     r8, ServiceName; lpDefault
0x18002734e  mov     [rsp+0C8h+ReturnedString], ax
0x180027353  lea     rdx, KeyName; "Signature"
0x18002735a  call    cs:__imp_GetPrivateProfileStringW
0x180027360  lea     r14, aDoronj; "DoronJ"
0x180027367  mov     ebx, eax
0x180027369  mov     rcx, r14; wchar_t *
0x18002736c  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180027371  cmp     ebx, eax
0x180027373  jnz     short loc_18002739D
0x180027375  or      r9d, 0FFFFFFFFh; cchCount1
0x180027379  mov     dword ptr [rsp+0C8h+lpFileName], 0FFFFFFFFh; cchCount2
0x180027381  lea     r8, [rsp+0C8h+ReturnedString]; lpString1
0x180027386  mov     qword ptr [rsp+0C8h+nSize], r14; lpString2
0x18002738b  lea     edx, [r9+2]; dwCmpFlags
0x18002738f  lea     ecx, [rdx+7Eh]; Locale
0x180027392  call    cs:__imp_CompareStringW
0x180027398  cmp     eax, 2
0x18002739b  jz      short loc_1800273D8
0x18002739d  lea     r14, aMsmqstorage; "MSMQStorage"
0x1800273a4  mov     rcx, r14; wchar_t *
0x1800273a7  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x1800273ac  cmp     ebx, eax
0x1800273ae  jnz     short loc_1800273DF
0x1800273b0  or      r9d, 0FFFFFFFFh; cchCount1
0x1800273b4  mov     dword ptr [rsp+0C8h+lpFileName], 0FFFFFFFFh; cchCount2
0x1800273bc  lea     r8, [rsp+0C8h+ReturnedString]; lpString1
0x1800273c1  mov     qword ptr [rsp+0C8h+nSize], r14; lpString2
0x1800273c6  lea     edx, [r9+2]; dwCmpFlags
0x1800273ca  lea     ecx, [rdx+7Eh]; Locale
0x1800273cd  call    cs:__imp_CompareStringW
0x1800273d3  cmp     eax, 2
0x1800273d6  jnz     short loc_1800273DF
0x1800273d8  xor     eax, eax
0x1800273da  jmp     loc_180027460
0x1800273df  test    ebx, ebx
0x1800273e1  jnz     short loc_1800273F0
0x1800273e3  mov     r8d, 154h
0x1800273e9  mov     ebx, 0C00E0027h
0x1800273ee  jmp     short loc_180027450
0x1800273f0  mov     rcx, rdi; lpFileName
0x1800273f3  call    cs:__imp_DeleteFileW
0x1800273f9  test    eax, eax
0x1800273fb  jz      short loc_18002740A
0x1800273fd  mov     r8d, 15Eh
0x180027403  mov     ebx, 0C00E0068h
0x180027408  jmp     short loc_180027450
0x18002740a  call    cs:__imp_GetLastError
0x180027410  mov     rcx, cs:WPP_GLOBAL_Control
0x180027417  lea     rdx, WPP_GLOBAL_Control
0x18002741e  cmp     rcx, rdx
0x180027421  jz      short loc_180027445
0x180027423  test    byte ptr [rcx+1Ch], 1
0x180027427  jz      short loc_180027445
0x180027429  mov     rcx, [rcx+10h]; LoggerHandle
0x18002742d  lea     r8, WPP_d0e956cc0cdd39a36b297795c14e9c92_Traceguids
0x180027434  mov     edx, 29h ; ')'
0x180027439  mov     [rsp+0C8h+nSize], eax; char
0x18002743d  mov     r9, rdi
0x180027440  call    WPP_SF_Sd
0x180027445  mov     r8d, 168h; unsigned __int16
0x18002744b  mov     ebx, 0C00E0001h
0x180027450  lea     rdx, aLqs_0; "lqs"
0x180027457  mov     ecx, ebx; int
0x180027459  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x18002745e  mov     eax, ebx
0x180027460  mov     rcx, [rsp+0C8h+var_18]
0x180027468  xor     rcx, rsp; StackCookie
0x18002746b  call    __security_check_cookie
0x180027470  lea     r11, [rsp+0C8h+var_8]
0x180027478  mov     rbx, [r11+18h]
0x18002747c  mov     rdi, [r11+20h]
0x180027480  mov     rsp, r11
0x180027483  pop     r14
0x180027485  retn
```
