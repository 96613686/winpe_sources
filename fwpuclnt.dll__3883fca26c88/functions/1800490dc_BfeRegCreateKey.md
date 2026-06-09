# BfeRegCreateKey

- ea: `0x1800490dc`
- end: `0x1800491e3`
- name: `BfeRegCreateKey`
- size: `263`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001dc80`
- `0x18001df08`
- `0x18001f9a0`

## callees

- `0x1800034e0`
- `0x180007e38`
- `0x180012bd0`
- `0x1800490dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049189`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180049189`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180049146`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180049146`

## string_xrefs

- `0x180049199`: `RegCreateKeyExW`
- `0x1800491b0`: `BfeRegCreateKey`
- `0x180049156`: `RegCreateKeyTransactedW`

## pseudocode

```c
__int64 __fastcall BfeRegCreateKey(HKEY a1, const WCHAR *a2, REGSAM samDesired, void *a4, _QWORD *a5)
{
  unsigned int v5; // eax
  __int64 v6; // rcx
  const char *v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rbx
  HKEY phkResult; // [rsp+60h] [rbp-28h] BYREF

  phkResult = 0;
  *a5 = 0;
  if ( a4 )
  {
    v5 = RegCreateKeyTransactedW(a1, a2, 0, 0, 0, samDesired, 0, &phkResult, 0, a4, 0);
    if ( v5 )
    {
      v7 = "RegCreateKeyTransactedW";
      goto LABEL_6;
    }
LABEL_8:
    v9 = 0;
    *a5 = phkResult;
    return v9;
  }
  v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, samDesired, 0, &phkResult, 0);
  if ( !v5 )
    goto LABEL_8;
  v7 = "RegCreateKeyExW";
LABEL_6:
  v8 = WfpReportSysErrorAsWinError(v6, v7, v5);
  v9 = v8;
  if ( v8 )
    WfpReportError(v8, "BfeRegCreateKey");
  return v9;
}

```

## disassembly

```asm
0x1800490dc  mov     r11, rsp
0x1800490df  push    rbx
0x1800490e0  push    rdi
0x1800490e1  sub     rsp, 78h
0x1800490e5  mov     rax, cs:__security_cookie
0x1800490ec  xor     rax, rsp
0x1800490ef  mov     [rsp+88h+var_20], rax
0x1800490f4  mov     rdi, [rsp+88h+arg_20]
0x1800490fc  lea     rax, [r11-28h]
0x180049100  mov     qword ptr [r11-28h], 0
0x180049108  mov     qword ptr [rdi], 0
0x18004910f  test    r9, r9
0x180049112  jz      short loc_18004915F
0x180049114  mov     qword ptr [r11-38h], 0
0x18004911c  mov     [r11-40h], r9
0x180049120  xor     r9d, r9d; lpClass
0x180049123  mov     qword ptr [r11-48h], 0
0x18004912b  mov     [r11-50h], rax
0x18004912f  mov     qword ptr [r11-58h], 0
0x180049137  mov     [r11-60h], r8d
0x18004913b  xor     r8d, r8d; Reserved
0x18004913e  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180049146  call    cs:__imp_RegCreateKeyTransactedW
0x18004914d  nop     dword ptr [rax+rax+00h]
0x180049152  test    eax, eax
0x180049154  jz      short loc_1800491C1
0x180049156  lea     rdx, aRegcreatekeytr_0; "RegCreateKeyTransactedW"
0x18004915d  jmp     short loc_1800491A0
0x18004915f  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180049168  xor     r9d, r9d; lpClass
0x18004916b  mov     [rsp+88h+phkResult], rax; phkResult
0x180049170  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180049179  mov     [rsp+88h+samDesired], r8d; samDesired
0x18004917e  xor     r8d, r8d; Reserved
0x180049181  mov     [rsp+88h+dwOptions], 0; dwOptions
0x180049189  call    cs:__imp_RegCreateKeyExW
0x180049190  nop     dword ptr [rax+rax+00h]
0x180049195  test    eax, eax
0x180049197  jz      short loc_1800491C1
0x180049199  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x1800491a0  mov     r8d, eax
0x1800491a3  call    WfpReportSysErrorAsWinError
0x1800491a8  mov     rbx, rax
0x1800491ab  test    rax, rax
0x1800491ae  jz      short loc_1800491CB
0x1800491b0  lea     rdx, aBferegcreateke; "BfeRegCreateKey"
0x1800491b7  mov     rcx, rax
0x1800491ba  call    WfpReportError
0x1800491bf  jmp     short loc_1800491CB
0x1800491c1  mov     rax, [rsp+88h+var_28]
0x1800491c6  xor     ebx, ebx
0x1800491c8  mov     [rdi], rax
0x1800491cb  mov     rax, rbx
0x1800491ce  mov     rcx, [rsp+88h+var_20]
0x1800491d3  xor     rcx, rsp; StackCookie
0x1800491d6  call    __security_check_cookie
0x1800491db  add     rsp, 78h
0x1800491df  pop     rdi
0x1800491e0  pop     rbx
0x1800491e1  retn
```
