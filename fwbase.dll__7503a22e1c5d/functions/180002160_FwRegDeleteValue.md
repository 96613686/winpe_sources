# FwRegDeleteValue

- ea: `0x180002160`
- end: `0x180002272`
- name: `FwRegDeleteValue`
- size: `274`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001720`
- `0x180002160`
- `0x1800028e0`
- `0x180004750`
- `0x1800047e0`
- `0x18001f5f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800021a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800021a2`

## string_xrefs

- `0x18000222f`: `FwRegDeleteValue`
- `0x18000224a`: `FwRegDeleteValue`
- `0x18000225f`: `FwRegDeleteValue`
- `0x180002243`: `RegDeleteValueW`

## pseudocode

```c
__int64 __fastcall FwRegDeleteValue(HKEY hKey, LPCWSTR lpSubKey, LPCWSTR lpValueName)
{
  int v3; // ebx
  unsigned int v7; // eax
  int v9; // eax
  __int64 v10; // [rsp+58h] [rbp+10h] BYREF
  HKEY v11; // [rsp+68h] [rbp+20h]

  v3 = 0;
  LODWORD(v10) = 1;
  v11 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      23,
      (unsigned int)WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids,
      (_DWORD)lpSubKey,
      (__int64)lpValueName);
  if ( lpSubKey )
  {
    v9 = FwRegOpenKey(hKey, lpSubKey, 2u, (__int64)&v10);
    v3 = v9;
    if ( v9 < 0 )
    {
      FwReportReturnError("FwRegDeleteValue", (unsigned int)v9);
      goto LABEL_5;
    }
    if ( !(_DWORD)v10 )
      goto LABEL_5;
    hKey = v11;
  }
  v7 = RegDeleteValueW(hKey, lpValueName);
  if ( (v7 & 0xFFFFFFFD) != 0 )
    v3 = FwReportErrorAsWinError("FwRegDeleteValue", "RegDeleteValueW", v7);
LABEL_5:
  FwRegCloseKey(v11);
  if ( v3 < 0 )
    return (unsigned int)FwReportReturnError("FwRegDeleteValue", (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180002160  mov     [rsp+arg_0], rbx
0x180002165  push    rbp
0x180002166  push    rsi
0x180002167  push    rdi
0x180002168  sub     rsp, 30h
0x18000216c  xor     ebx, ebx
0x18000216e  mov     dword ptr [rsp+48h+arg_8], 1
0x180002176  mov     [rsp+48h+arg_18], rbx
0x18000217b  mov     rbp, r8
0x18000217e  mov     rdi, rdx
0x180002181  mov     rsi, rcx
0x180002184  mov     rcx, cs:WPP_GLOBAL_Control
0x18000218b  lea     rax, WPP_GLOBAL_Control
0x180002192  cmp     rcx, rax
0x180002195  jnz     short loc_1800021D4
0x180002197  test    rdi, rdi
0x18000219a  jnz     short loc_180002207
0x18000219c  mov     rdx, rbp; lpValueName
0x18000219f  mov     rcx, rsi; hKey
0x1800021a2  call    cs:__imp_RegDeleteValueW
0x1800021a8  test    eax, 0FFFFFFFDh
0x1800021ad  jnz     loc_180002240
0x1800021b3  mov     rcx, [rsp+48h+arg_18]
0x1800021b8  call    FwRegCloseKey
0x1800021bd  test    ebx, ebx
0x1800021bf  js      loc_18000225D
0x1800021c5  mov     eax, ebx
0x1800021c7  mov     rbx, [rsp+48h+arg_0]
0x1800021cc  add     rsp, 30h
0x1800021d0  pop     rdi
0x1800021d1  pop     rsi
0x1800021d2  pop     rbp
0x1800021d3  retn
0x1800021d4  test    byte ptr [rcx+1Ch], 8
0x1800021d8  jz      short loc_180002197
0x1800021da  mov     rcx, [rcx+10h]
0x1800021de  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x1800021e5  mov     edx, 17h
0x1800021ea  mov     [rsp+48h+var_28], rbp
0x1800021ef  mov     r9, rdi
0x1800021f2  call    WPP_SF_SS
0x1800021f7  jmp     short loc_180002197
0x1800021f9  cmp     dword ptr [rsp+48h+arg_8], 0
0x1800021fe  jz      short loc_1800021B3
0x180002200  mov     rsi, [rsp+48h+arg_18]
0x180002205  jmp     short loc_18000219C
0x180002207  lea     rax, [rsp+48h+arg_8]
0x18000220c  mov     r8d, 2; samDesired
0x180002212  lea     r9, [rsp+48h+arg_18]
0x180002217  mov     [rsp+48h+var_28], rax; __int64
0x18000221c  mov     rdx, rdi; lpSubKey
0x18000221f  mov     rcx, rsi; hKey
0x180002222  call    FwRegOpenKey
0x180002227  mov     ebx, eax
0x180002229  test    eax, eax
0x18000222b  jns     short loc_1800021F9
0x18000222d  mov     edx, eax
0x18000222f  lea     rcx, aFwregdeleteval_0; "FwRegDeleteValue"
0x180002236  call    FwReportReturnError
0x18000223b  jmp     loc_1800021B3
0x180002240  mov     r8d, eax
0x180002243  lea     rdx, aRegdeletevalue_0; "RegDeleteValueW"
0x18000224a  lea     rcx, aFwregdeleteval_0; "FwRegDeleteValue"
0x180002251  call    FwReportErrorAsWinError
0x180002256  mov     ebx, eax
0x180002258  jmp     loc_1800021B3
0x18000225d  mov     edx, ebx
0x18000225f  lea     rcx, aFwregdeleteval_0; "FwRegDeleteValue"
0x180002266  call    FwReportReturnError
0x18000226b  mov     ebx, eax
0x18000226d  jmp     loc_1800021C5
```
