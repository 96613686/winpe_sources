# FwRegSetDWord

- ea: `0x180002280`
- end: `0x1800023b4`
- name: `FwRegSetDWord`
- size: `308`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180002080`
- `0x1800020f0`

## callees

- `0x180002280`
- `0x1800028e0`
- `0x1800031a0`
- `0x180004750`
- `0x1800047e0`
- `0x18001e1d0`
- `0x18001f5f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800022ed`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800022ed`

## string_xrefs

- `0x180002362`: `FwRegSetDWord`
- `0x18000238c`: `FwRegSetDWord`
- `0x1800023a1`: `FwRegSetDWord`
- `0x180002385`: `RegSetValueExW`

## pseudocode

```c
__int64 __fastcall FwRegSetDWord(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName, int a4)
{
  int v4; // ebx
  unsigned int v8; // eax
  int Key; // eax
  BYTE Data[8]; // [rsp+38h] [rbp-40h] BYREF

  v4 = 0;
  *(_DWORD *)Data = a4;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      (unsigned int)WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids,
      (_DWORD)lpSubKey,
      (__int64)lpValueName);
  if ( lpSubKey )
  {
    Key = FwRegCreateKey(hKey, lpSubKey, 2u);
    v4 = Key;
    if ( Key < 0 )
    {
      FwReportReturnError("FwRegSetDWord", (unsigned int)Key);
      goto LABEL_7;
    }
    hKey = 0;
  }
  v8 = RegSetValueExW(hKey, lpValueName, 0, 4u, Data, 4u);
  if ( v8 )
    v4 = FwReportErrorAsWinError("FwRegSetDWord", "RegSetValueExW", v8);
LABEL_7:
  FwRegCloseKey(0);
  if ( v4 < 0 )
    return (unsigned int)FwReportReturnError("FwRegSetDWord", (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002280  push    rbx
0x180002282  push    rbp
0x180002283  push    rsi
0x180002284  push    rdi
0x180002285  push    r14
0x180002287  sub     rsp, 50h
0x18000228b  mov     rax, cs:__security_cookie
0x180002292  xor     rax, rsp
0x180002295  mov     [rsp+78h+var_38], rax
0x18000229a  xor     ebx, ebx
0x18000229c  mov     dword ptr [rsp+78h+Data], r9d
0x1800022a1  xor     edi, edi
0x1800022a3  mov     r14, r8
0x1800022a6  mov     [rsp+78h+var_48], rdi
0x1800022ab  mov     rsi, rdx
0x1800022ae  mov     rbp, rcx
0x1800022b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800022b8  lea     rax, WPP_GLOBAL_Control
0x1800022bf  cmp     rcx, rax
0x1800022c2  jz      short loc_1800022CA
0x1800022c4  test    byte ptr [rcx+1Ch], 8
0x1800022c8  jnz     short loc_180002325
0x1800022ca  test    rsi, rsi
0x1800022cd  jnz     short loc_180002344
0x1800022cf  mov     r9d, 4; dwType
0x1800022d5  lea     rax, [rsp+78h+Data]
0x1800022da  mov     [rsp+78h+cbData], r9d; cbData
0x1800022df  xor     r8d, r8d; Reserved
0x1800022e2  mov     rdx, r14; lpValueName
0x1800022e5  mov     [rsp+78h+lpData], rax; lpData
0x1800022ea  mov     rcx, rbp; hKey
0x1800022ed  call    cs:__imp_RegSetValueExW
0x1800022f3  test    eax, eax
0x1800022f5  jnz     loc_180002382
0x1800022fb  mov     rcx, rdi
0x1800022fe  call    FwRegCloseKey
0x180002303  test    ebx, ebx
0x180002305  js      loc_18000239F
0x18000230b  mov     eax, ebx
0x18000230d  mov     rcx, [rsp+78h+var_38]
0x180002312  xor     rcx, rsp; StackCookie
0x180002315  call    __security_check_cookie
0x18000231a  add     rsp, 50h
0x18000231e  pop     r14
0x180002320  pop     rdi
0x180002321  pop     rsi
0x180002322  pop     rbp
0x180002323  pop     rbx
0x180002324  retn
0x180002325  mov     rcx, [rcx+10h]
0x180002329  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x180002330  mov     edx, 11h
0x180002335  mov     [rsp+78h+lpData], r14
0x18000233a  mov     r9, rsi
0x18000233d  call    WPP_SF_SS
0x180002342  jmp     short loc_1800022CA
0x180002344  lea     r9, [rsp+78h+var_48]
0x180002349  mov     r8d, 2; samDesired
0x18000234f  mov     rdx, rsi; lpSubKey
0x180002352  mov     rcx, rbp; hKey
0x180002355  call    FwRegCreateKey
0x18000235a  mov     ebx, eax
0x18000235c  test    eax, eax
0x18000235e  jns     short loc_180002375
0x180002360  mov     edx, eax
0x180002362  lea     rcx, aFwregsetdword_0; "FwRegSetDWord"
0x180002369  call    FwReportReturnError
0x18000236e  mov     rdi, [rsp+78h+var_48]
0x180002373  jmp     short loc_1800022FB
0x180002375  mov     rdi, [rsp+78h+var_48]
0x18000237a  mov     rbp, rdi
0x18000237d  jmp     loc_1800022CF
0x180002382  mov     r8d, eax
0x180002385  lea     rdx, aRegsetvalueexw; "RegSetValueExW"
0x18000238c  lea     rcx, aFwregsetdword_0; "FwRegSetDWord"
0x180002393  call    FwReportErrorAsWinError
0x180002398  mov     ebx, eax
0x18000239a  jmp     loc_1800022FB
0x18000239f  mov     edx, ebx
0x1800023a1  lea     rcx, aFwregsetdword_0; "FwRegSetDWord"
0x1800023a8  call    FwReportReturnError
0x1800023ad  mov     ebx, eax
0x1800023af  jmp     loc_18000230B
```
