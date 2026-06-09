# FwRemovePolicyAppIdFromSDDLString

- ea: `0x1800207f0`
- end: `0x1800209d3`
- name: `FwRemovePolicyAppIdFromSDDLString`
- size: `483`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1800209e0`

## callees

- `0x1800045f0`
- `0x1800047e0`
- `0x180004840`
- `0x1800207f0`
- `0x180020e00`
- `0x1800211e0`
- `0x18002f644`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002081f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020832`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002088d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020912`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020925`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002081f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020832`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18002088d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020912`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180020925`

## string_xrefs

- `0x180020860`: `FwRemovePolicyAppIdFromSDDLString`
- `0x1800209ac`: `FwRemovePolicyAppIdFromSDDLString`

## pseudocode

```c
__int64 __fastcall FwRemovePolicyAppIdFromSDDLString(wchar_t *Src, wchar_t **a2)
{
  int v2; // ebx
  wchar_t *v5; // r15
  wchar_t *v6; // rdi
  unsigned int v7; // eax
  wchar_t *v8; // rax
  wchar_t *v9; // r13
  __int64 v10; // rsi
  wchar_t *v11; // r13
  wchar_t *v12; // rax
  const wchar_t *v13; // rdx
  __int64 v14; // r8
  wchar_t *v15; // rdx
  wchar_t *v16; // rdi
  wchar_t *String1; // [rsp+58h] [rbp+38h] BYREF

  v2 = 0;
  *a2 = 0;
  String1 = 0;
  v5 = wcsstr(Src, L";(Exists POLICYAPPID://");
  v6 = wcsstr(Src, L"O");
  if ( !v5 )
  {
    if ( (int)FwStringCopy(Src, a2) >= 0 )
      goto LABEL_24;
    v7 = FwStringCopy(Src, a2);
    goto LABEL_4;
  }
  do
  {
    if ( !v6 || (v8 = wcsstr(v6, L"XA"), (v9 = v8) == 0) )
    {
      v2 = -2147024809;
      goto LABEL_24;
    }
    v10 = v8 - v6;
    if ( (int)FwStringPrefixConcat(&String1, v6, v10) < 0 )
    {
      v14 = v10;
      v15 = v6;
      goto LABEL_18;
    }
    if ( (int)FwStringConcat(&String1, L"A") < 0 )
    {
      v13 = L"A";
      goto LABEL_16;
    }
    v11 = v9 + 2;
    if ( (int)FwStringPrefixConcat(&String1, v11, v5 - v11) < 0 )
    {
      v14 = v5 - v11;
      v15 = v11;
LABEL_18:
      v7 = FwStringPrefixConcat(&String1, v15, v14);
LABEL_4:
      FwReportReturnError("FwRemovePolicyAppIdFromSDDLString", v7);
      goto LABEL_24;
    }
    if ( (int)FwStringConcat(&String1, L")") < 0 )
    {
      v13 = L")";
LABEL_16:
      v7 = FwStringConcat(&String1, v13);
      goto LABEL_4;
    }
    v6 = wcsstr(v5 + 23, L"(");
    v12 = wcsstr(v6, L";(Exists POLICYAPPID://");
    v5 = v12;
  }
  while ( v12 );
  v16 = String1;
  if ( String1 && !wcscmp_0(String1, L"O:SYG:SYD:(A;;CC;;;WD)") )
  {
    FwFree(v16);
    v16 = 0;
  }
  *a2 = v16;
  String1 = 0;
LABEL_24:
  FwFree(String1);
  if ( v2 < 0 )
    return (unsigned int)FwReportReturnError("FwRemovePolicyAppIdFromSDDLString", (unsigned int)v2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800207f0  mov     [rsp-28h+arg_0], rbx
0x1800207f5  mov     [rsp-28h+arg_10], rsi
0x1800207fa  push    rbp
0x1800207fb  push    rdi
0x1800207fc  push    r13
0x1800207fe  push    r14
0x180020800  push    r15
0x180020802  mov     rbp, rsp
0x180020805  sub     rsp, 20h
0x180020809  xor     ebx, ebx
0x18002080b  mov     r14, rdx
0x18002080e  mov     [rdx], rbx
0x180020811  mov     rsi, rcx
0x180020814  lea     rdx, aExistsPolicyap; ";(Exists POLICYAPPID://"
0x18002081b  mov     [rbp+String1], rbx
0x18002081f  call    cs:__imp_wcsstr
0x180020825  lea     rdx, aO; "O"
0x18002082c  mov     rcx, rsi; Str
0x18002082f  mov     r15, rax
0x180020832  call    cs:__imp_wcsstr
0x180020838  mov     rdi, rax
0x18002083b  test    r15, r15
0x18002083e  jnz     short loc_18002087A
0x180020840  mov     rdx, r14
0x180020843  mov     rcx, rsi; Src
0x180020846  call    FwStringCopy
0x18002084b  test    eax, eax
0x18002084d  jns     loc_18002099D
0x180020853  mov     rdx, r14
0x180020856  mov     rcx, rsi; Src
0x180020859  call    FwStringCopy
0x18002085e  mov     edx, eax
0x180020860  lea     rcx, aFwremovepolicy_0; "FwRemovePolicyAppIdFromSDDLString"
0x180020867  call    FwReportReturnError
0x18002086c  jmp     loc_18002099D
0x180020871  test    r15, r15
0x180020874  jz      loc_180020970
0x18002087a  test    rdi, rdi
0x18002087d  jz      loc_180020969
0x180020883  lea     rdx, aXa; "XA"
0x18002088a  mov     rcx, rdi; Str
0x18002088d  call    cs:__imp_wcsstr
0x180020893  mov     r13, rax
0x180020896  test    rax, rax
0x180020899  jz      loc_180020969
0x18002089f  mov     rsi, rax
0x1800208a2  lea     rcx, [rbp+String1]
0x1800208a6  sub     rsi, rdi
0x1800208a9  mov     rdx, rdi
0x1800208ac  sar     rsi, 1
0x1800208af  mov     r8, rsi
0x1800208b2  call    FwStringPrefixConcat
0x1800208b7  lea     rcx, [rbp+String1]
0x1800208bb  test    eax, eax
0x1800208bd  js      loc_180020959
0x1800208c3  lea     rdx, aA; "A"
0x1800208ca  call    FwStringConcat
0x1800208cf  lea     rcx, [rbp+String1]
0x1800208d3  test    eax, eax
0x1800208d5  js      short loc_180020948
0x1800208d7  add     r13, 4
0x1800208db  mov     rdi, r15
0x1800208de  sub     rdi, r13
0x1800208e1  mov     rdx, r13
0x1800208e4  sar     rdi, 1
0x1800208e7  mov     r8, rdi
0x1800208ea  call    FwStringPrefixConcat
0x1800208ef  lea     rcx, [rbp+String1]
0x1800208f3  test    eax, eax
0x1800208f5  js      short loc_180020940
0x1800208f7  lea     rdx, asc_1800340C8; ")"
0x1800208fe  call    FwStringConcat
0x180020903  test    eax, eax
0x180020905  js      short loc_180020933
0x180020907  lea     rcx, [r15+2Eh]; Str
0x18002090b  lea     rdx, asc_180034004; "("
0x180020912  call    cs:__imp_wcsstr
0x180020918  mov     rcx, rax; Str
0x18002091b  lea     rdx, aExistsPolicyap; ";(Exists POLICYAPPID://"
0x180020922  mov     rdi, rax
0x180020925  call    cs:__imp_wcsstr
0x18002092b  mov     r15, rax
0x18002092e  jmp     loc_180020871
0x180020933  lea     rdx, asc_1800340C8; ")"
0x18002093a  lea     rcx, [rbp+String1]
0x18002093e  jmp     short loc_18002094F
0x180020940  mov     r8, rdi
0x180020943  mov     rdx, r13
0x180020946  jmp     short loc_18002095F
0x180020948  lea     rdx, aA; "A"
0x18002094f  call    FwStringConcat
0x180020954  jmp     loc_18002085E
0x180020959  mov     r8, rsi
0x18002095c  mov     rdx, rdi
0x18002095f  call    FwStringPrefixConcat
0x180020964  jmp     loc_18002085E
0x180020969  mov     ebx, 80070057h
0x18002096e  jmp     short loc_18002099D
0x180020970  mov     rdi, [rbp+String1]
0x180020974  test    rdi, rdi
0x180020977  jz      short loc_180020996
0x180020979  lea     rdx, aOSygSydACcWd; "O:SYG:SYD:(A;;CC;;;WD)"
0x180020980  mov     rcx, rdi; String1
0x180020983  call    wcscmp_0
0x180020988  test    eax, eax
0x18002098a  jnz     short loc_180020996
0x18002098c  mov     rcx, rdi
0x18002098f  call    FwFree
0x180020994  xor     edi, edi
0x180020996  mov     [r14], rdi
0x180020999  mov     [rbp+String1], rbx
0x18002099d  mov     rcx, [rbp+String1]
0x1800209a1  call    FwFree
0x1800209a6  test    ebx, ebx
0x1800209a8  jns     short loc_1800209BA
0x1800209aa  mov     edx, ebx
0x1800209ac  lea     rcx, aFwremovepolicy_0; "FwRemovePolicyAppIdFromSDDLString"
0x1800209b3  call    FwReportReturnError
0x1800209b8  mov     ebx, eax
0x1800209ba  mov     rsi, [rsp+20h+arg_10]
0x1800209bf  mov     eax, ebx
0x1800209c1  mov     rbx, [rsp+20h+arg_0]
0x1800209c6  add     rsp, 20h
0x1800209ca  pop     r15
0x1800209cc  pop     r14
0x1800209ce  pop     r13
0x1800209d0  pop     rdi
0x1800209d1  pop     rbp
0x1800209d2  retn
```
