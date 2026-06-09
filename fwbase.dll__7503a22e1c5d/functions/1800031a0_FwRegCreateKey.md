# FwRegCreateKey

- ea: `0x1800031a0`
- end: `0x180003298`
- name: `FwRegCreateKey`
- size: `248`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180001a58`
- `0x180002280`
- `0x180002440`
- `0x1800027a0`
- `0x180013140`

## callees

- `0x1800031a0`
- `0x180004750`
- `0x1800047e0`
- `0x1800130bc`
- `0x18001e1d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000321b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000321b`

## string_xrefs

- `0x180003274`: `FwRegCreateKey`
- `0x180003288`: `FwRegCreateKey`
- `0x18000326d`: `RegCreateKeyExW`

## pseudocode

```c
__int64 __fastcall FwRegCreateKey(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *a4)
{
  unsigned int v8; // eax
  unsigned int v9; // ecx
  int v11; // eax
  HKEY phkResult; // [rsp+50h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids, lpSubKey);
  phkResult = 0;
  *a4 = 0;
  v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &phkResult, 0);
  if ( v8 )
  {
    v11 = FwReportErrorAsWinError("FwRegCreateKey", "RegCreateKeyExW", v8);
    v9 = v11;
    if ( v11 < 0 )
      return (unsigned int)FwReportReturnError("FwRegCreateKey", (unsigned int)v11);
  }
  else
  {
    v9 = 0;
    *a4 = phkResult;
  }
  return v9;
}

```

## disassembly

```asm
0x1800031a0  push    rbx
0x1800031a2  push    rbp
0x1800031a3  push    rsi
0x1800031a4  push    rdi
0x1800031a5  sub     rsp, 68h
0x1800031a9  mov     rax, cs:__security_cookie
0x1800031b0  xor     rax, rsp
0x1800031b3  mov     [rsp+88h+var_30], rax
0x1800031b8  mov     rbx, r9
0x1800031bb  mov     ebp, r8d
0x1800031be  mov     rdi, rdx
0x1800031c1  mov     rsi, rcx
0x1800031c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031cb  lea     rax, WPP_GLOBAL_Control
0x1800031d2  cmp     rcx, rax
0x1800031d5  jnz     short loc_180003247
0x1800031d7  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800031e0  lea     rax, [rsp+88h+var_38]
0x1800031e5  mov     [rsp+88h+phkResult], rax; phkResult
0x1800031ea  xor     r9d, r9d; lpClass
0x1800031ed  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800031f6  xor     r8d, r8d; Reserved
0x1800031f9  mov     [rsp+88h+samDesired], ebp; samDesired
0x1800031fd  mov     rdx, rdi; lpSubKey
0x180003200  mov     rcx, rsi; hKey
0x180003203  mov     [rsp+88h+dwOptions], 0; dwOptions
0x18000320b  mov     [rsp+88h+var_38], 0
0x180003214  mov     qword ptr [rbx], 0
0x18000321b  call    cs:__imp_RegCreateKeyExW
0x180003221  test    eax, eax
0x180003223  jnz     short loc_18000326A
0x180003225  mov     rax, [rsp+88h+var_38]
0x18000322a  xor     ecx, ecx
0x18000322c  mov     [rbx], rax
0x18000322f  mov     eax, ecx
0x180003231  mov     rcx, [rsp+88h+var_30]
0x180003236  xor     rcx, rsp; StackCookie
0x180003239  call    __security_check_cookie
0x18000323e  add     rsp, 68h
0x180003242  pop     rdi
0x180003243  pop     rsi
0x180003244  pop     rbp
0x180003245  pop     rbx
0x180003246  retn
0x180003247  test    byte ptr [rcx+1Ch], 8
0x18000324b  jz      short loc_1800031D7
0x18000324d  mov     rcx, [rcx+10h]
0x180003251  lea     r8, WPP_ca8ecc87028c3f8cbe9deeea65f7fdbd_Traceguids
0x180003258  mov     edx, 0Ah
0x18000325d  mov     r9, rdi
0x180003260  call    WPP_SF_S
0x180003265  jmp     loc_1800031D7
0x18000326a  mov     r8d, eax
0x18000326d  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x180003274  lea     rcx, aFwregcreatekey_0; "FwRegCreateKey"
0x18000327b  call    FwReportErrorAsWinError
0x180003280  mov     ecx, eax
0x180003282  test    eax, eax
0x180003284  jns     short loc_18000322F
0x180003286  mov     edx, eax
0x180003288  lea     rcx, aFwregcreatekey_0; "FwRegCreateKey"
0x18000328f  call    FwReportReturnError
0x180003294  mov     ecx, eax
0x180003296  jmp     short loc_18000322F
```
