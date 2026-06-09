# ReadProxySettings

- ea: `0x1800d1284`
- end: `0x1800d14c1`
- name: `ReadProxySettings`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180021080`

## callees

- `0x1800025f0`
- `0x180005310`
- `0x1800054c0`
- `0x180005730`
- `0x18000b0f4`
- `0x1800278a0`
- `0x180063dc8`
- `0x1800ce860`
- `0x1800d1284`
- `0x1800ded50`
- `0x1800e0010`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x1800d13ce`
- `rtutils!TracePrintfExA` at `0x1800d142b`
- `rtutils!TracePrintfExA` at `0x1800d1469`
- `rtutils!TracePrintfExA` at `0x1800d13ce`
- `rtutils!TracePrintfExA` at `0x1800d142b`
- `rtutils!TracePrintfExA` at `0x1800d1469`

## string_xrefs

- `0x1800d1300`: `AutoConfigScript`
- `0x1800d141f`: `Failed while reading proxy exclude list %d`
- `0x1800d13c2`: `Failed while getting AutoConfigScript`

## pseudocode

```c
__int64 __fastcall ReadProxySettings(unsigned int a1, __int64 (__fastcall *a2)(char *), __int64 a3)
{
  __int64 (__fastcall *v4)(char *); // r14
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 Line; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  int v11; // edx
  int v12; // r8d
  unsigned int MultiLineString; // eax
  unsigned int v15; // ebx
  __int64 v16; // rax
  char *v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+38h] [rbp-C8h] BYREF
  char String[1552]; // [rsp+40h] [rbp-C0h] BYREF

  v17 = 0;
  v4 = a2;
  v18 = 0;
  LOBYTE(a2) = 2;
  if ( !(unsigned int)rasFindLine(a1, (_DWORD)a2, 1, 3, 1)
    || (Line = RasfileGetLine(a1, v6, v7), !(unsigned int)IsProxySettingsLine(Line)) )
  {
    LOBYTE(v6) = 63;
    rasFindLine(a1, v6, 1, 4, 2);
    return 625;
  }
  if ( (unsigned int)RasfileFindNextKeyLine(a1, "AutoConfigScript", 2) )
  {
    if ( !(unsigned int)RasfileGetKeyValueFields(a1, 0, 0, String) )
      goto LABEL_11;
    v9 = v4(String);
    *(_QWORD *)(a3 + 568) = v9;
    if ( !v9 )
      goto LABEL_11;
  }
  if ( (unsigned int)RasfileFindNextKeyLine(a1, "Proxy", 2) )
  {
    if ( !(unsigned int)RasfileGetKeyValueFields(a1, 0, 0, String) )
      goto LABEL_11;
    v10 = v4(String);
    *(_QWORD *)(a3 + 576) = v10;
    if ( !v10 )
      goto LABEL_11;
  }
  if ( (unsigned int)RasfileFindNextKeyLine(a1, "ProxyFlags", 2) )
  {
    if ( !(unsigned int)RasfileGetKeyValueFields(a1, 0, 0, String) )
    {
LABEL_11:
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed while getting AutoConfigScript");
      return 8;
    }
    if ( String[0] )
      *(_DWORD *)(a3 + 560) = atol_0(String);
  }
  MultiLineString = ReadMultiLineString(a1, v11, v12, (unsigned int)&v17, (__int64)&v18);
  v15 = MultiLineString;
  if ( MultiLineString )
  {
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "Failed while reading proxy exclude list %d", MultiLineString);
  }
  else if ( v17 )
  {
    v16 = v4(v17);
    *(_QWORD *)(a3 + 584) = v16;
    if ( !v16 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "Failed while getting proxy exclude list");
      v15 = 8;
    }
  }
  Free0(v17);
  return v15;
}

```

## disassembly

```asm
0x1800d1284  mov     [rsp-8+arg_18], rbx
0x1800d1289  push    rbp
0x1800d128a  push    rsi
0x1800d128b  push    r14
0x1800d128d  lea     rbp, [rsp-560h]
0x1800d1295  sub     rsp, 660h
0x1800d129c  mov     rax, cs:__security_cookie
0x1800d12a3  xor     rax, rsp
0x1800d12a6  mov     [rbp+570h+var_20], rax
0x1800d12ad  mov     rsi, r8
0x1800d12b0  mov     [rsp+670h+var_640], 0
0x1800d12b9  mov     r14, rdx
0x1800d12bc  mov     [rsp+670h+var_638], 0
0x1800d12c4  mov     r8d, 1
0x1800d12ca  mov     byte ptr [rsp+670h+var_650], 1
0x1800d12cf  mov     dl, 2
0x1800d12d1  mov     r9b, 3
0x1800d12d4  mov     ebx, ecx
0x1800d12d6  call    rasFindLine
0x1800d12db  test    eax, eax
0x1800d12dd  jz      loc_1800D1482
0x1800d12e3  mov     ecx, ebx
0x1800d12e5  call    RasfileGetLine
0x1800d12ea  mov     rcx, rax
0x1800d12ed  call    IsProxySettingsLine
0x1800d12f2  test    eax, eax
0x1800d12f4  jz      loc_1800D1482
0x1800d12fa  mov     r8d, 2
0x1800d1300  lea     rdx, aAutoconfigscri; "AutoConfigScript"
0x1800d1307  mov     ecx, ebx
0x1800d1309  call    RasfileFindNextKeyLine
0x1800d130e  test    eax, eax
0x1800d1310  jz      short loc_1800D1344
0x1800d1312  lea     r9, [rsp+670h+String]
0x1800d1317  xor     r8d, r8d
0x1800d131a  xor     edx, edx
0x1800d131c  mov     ecx, ebx
0x1800d131e  call    RasfileGetKeyValueFields
0x1800d1323  test    eax, eax
0x1800d1325  jz      loc_1800D13B7
0x1800d132b  lea     rcx, [rsp+670h+String]
0x1800d1330  mov     rax, r14
0x1800d1333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1338  mov     [rsi+238h], rax
0x1800d133f  test    rax, rax
0x1800d1342  jz      short loc_1800D13B7
0x1800d1344  mov     r8d, 2
0x1800d134a  lea     rdx, aProxy; "Proxy"
0x1800d1351  mov     ecx, ebx
0x1800d1353  call    RasfileFindNextKeyLine
0x1800d1358  test    eax, eax
0x1800d135a  jz      short loc_1800D138A
0x1800d135c  lea     r9, [rsp+670h+String]
0x1800d1361  xor     r8d, r8d
0x1800d1364  xor     edx, edx
0x1800d1366  mov     ecx, ebx
0x1800d1368  call    RasfileGetKeyValueFields
0x1800d136d  test    eax, eax
0x1800d136f  jz      short loc_1800D13B7
0x1800d1371  lea     rcx, [rsp+670h+String]
0x1800d1376  mov     rax, r14
0x1800d1379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d137e  mov     [rsi+240h], rax
0x1800d1385  test    rax, rax
0x1800d1388  jz      short loc_1800D13B7
0x1800d138a  mov     r8d, 2
0x1800d1390  lea     rdx, aProxyflags; "ProxyFlags"
0x1800d1397  mov     ecx, ebx
0x1800d1399  call    RasfileFindNextKeyLine
0x1800d139e  test    eax, eax
0x1800d13a0  jz      short loc_1800D13F5
0x1800d13a2  lea     r9, [rsp+670h+String]
0x1800d13a7  xor     r8d, r8d
0x1800d13aa  xor     edx, edx
0x1800d13ac  mov     ecx, ebx
0x1800d13ae  call    RasfileGetKeyValueFields
0x1800d13b3  test    eax, eax
0x1800d13b5  jnz     short loc_1800D13DE
0x1800d13b7  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d13bd  cmp     ecx, 0FFFFFFFFh
0x1800d13c0  jz      short loc_1800D13D4
0x1800d13c2  lea     r8, aFailedWhileGet_0; "Failed while getting AutoConfigScript"
0x1800d13c9  mov     edx, 0Ch; dwFlags
0x1800d13ce  call    cs:__imp_TracePrintfExA
0x1800d13d4  mov     eax, 8
0x1800d13d9  jmp     loc_1800D149E
0x1800d13de  cmp     [rsp+670h+String], 0
0x1800d13e3  jz      short loc_1800D13F5
0x1800d13e5  lea     rcx, [rsp+670h+String]; String
0x1800d13ea  call    atol_0
0x1800d13ef  mov     [rsi+230h], eax
0x1800d13f5  lea     rax, [rsp+670h+var_638]
0x1800d13fa  mov     ecx, ebx
0x1800d13fc  lea     r9, [rsp+670h+var_640]
0x1800d1401  mov     [rsp+670h+var_650], rax
0x1800d1406  call    ReadMultiLineString
0x1800d140b  mov     ebx, eax
0x1800d140d  test    eax, eax
0x1800d140f  jz      short loc_1800D1433
0x1800d1411  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d1417  cmp     ecx, 0FFFFFFFFh
0x1800d141a  jz      short loc_1800D1474
0x1800d141c  mov     r9d, eax
0x1800d141f  lea     r8, aFailedWhileRea; "Failed while reading proxy exclude list"...
0x1800d1426  mov     edx, 0Ch; dwFlags
0x1800d142b  call    cs:__imp_TracePrintfExA
0x1800d1431  jmp     short loc_1800D1474
0x1800d1433  cmp     [rsp+670h+var_640], 0
0x1800d1439  jz      short loc_1800D1474
0x1800d143b  mov     rcx, [rsp+670h+var_640]
0x1800d1440  mov     rax, r14
0x1800d1443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1448  mov     [rsi+248h], rax
0x1800d144f  test    rax, rax
0x1800d1452  jnz     short loc_1800D1474
0x1800d1454  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800d145a  cmp     ecx, 0FFFFFFFFh
0x1800d145d  jz      short loc_1800D146F
0x1800d145f  lea     r8, aFailedWhileGet; "Failed while getting proxy exclude list"
0x1800d1466  lea     edx, [rax+0Ch]; dwFlags
0x1800d1469  call    cs:__imp_TracePrintfExA
0x1800d146f  mov     ebx, 8
0x1800d1474  mov     rcx, [rsp+670h+var_640]
0x1800d1479  call    Free0
0x1800d147e  mov     eax, ebx
0x1800d1480  jmp     short loc_1800D149E
0x1800d1482  mov     r9b, 4
0x1800d1485  mov     byte ptr [rsp+670h+var_650], 2
0x1800d148a  mov     r8d, 1
0x1800d1490  mov     dl, 3Fh ; '?'
0x1800d1492  mov     ecx, ebx
0x1800d1494  call    rasFindLine
0x1800d1499  mov     eax, 271h
0x1800d149e  mov     rcx, [rbp+570h+var_20]
0x1800d14a5  xor     rcx, rsp; StackCookie
0x1800d14a8  call    __security_check_cookie
0x1800d14ad  mov     rbx, [rsp+670h+arg_18]
0x1800d14b5  add     rsp, 660h
0x1800d14bc  pop     r14
0x1800d14be  pop     rsi
0x1800d14bf  pop     rbp
0x1800d14c0  retn
```
