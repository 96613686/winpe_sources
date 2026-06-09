# NcaRegCreateKey

- ea: `0x18001a00c`
- end: `0x18001a0f3`
- name: `NcaRegCreateKey`
- size: `231`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180014188`
- `0x180019f50`

## callees

- `0x1800033bc`
- `0x1800199b4`
- `0x180019dac`
- `0x18001a00c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a09c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001a09c`

## string_xrefs

- `0x18001a0af`: `RegCreateKeyExW`
- `0x18001a0b6`: `NcaRegCreateKey`
- `0x18001a0ca`: `NcaRegCreateKey`

## pseudocode

```c
__int64 __fastcall NcaRegCreateKey(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, HKEY *a4)
{
  unsigned int v8; // eax
  int v9; // eax
  unsigned int v10; // ecx
  HKEY phkResult; // [rsp+98h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_149084e4aca63d179354f111bb13106e_Traceguids, lpSubKey);
  phkResult = 0;
  *a4 = 0;
  v8 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, &phkResult, 0);
  if ( v8 )
  {
    v9 = NcaReportErrorAsWinError("NcaRegCreateKey", "RegCreateKeyExW", v8);
    v10 = v9;
    if ( v9 < 0 )
      return (unsigned int)NcaReportReturnError("NcaRegCreateKey", (unsigned int)v9);
  }
  else
  {
    v10 = 0;
    *a4 = phkResult;
  }
  return v10;
}

```

## disassembly

```asm
0x18001a00c  push    rbx
0x18001a00e  push    rbp
0x18001a00f  push    rsi
0x18001a010  push    rdi
0x18001a011  sub     rsp, 58h
0x18001a015  mov     rbx, r9
0x18001a018  mov     esi, r8d
0x18001a01b  mov     rdi, rdx
0x18001a01e  mov     rbp, rcx
0x18001a021  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a028  lea     rax, WPP_GLOBAL_Control
0x18001a02f  cmp     rcx, rax
0x18001a032  jz      short loc_18001A052
0x18001a034  test    byte ptr [rcx+1Ch], 8
0x18001a038  jz      short loc_18001A052
0x18001a03a  mov     rcx, [rcx+10h]
0x18001a03e  lea     r8, WPP_149084e4aca63d179354f111bb13106e_Traceguids
0x18001a045  mov     edx, 0Ah
0x18001a04a  mov     r9, rdi
0x18001a04d  call    WPP_SF_S
0x18001a052  mov     [rsp+78h+lpdwDisposition], 0; lpdwDisposition
0x18001a05b  lea     rax, [rsp+78h+arg_18]
0x18001a063  mov     [rsp+78h+phkResult], rax; phkResult
0x18001a068  xor     r9d, r9d; lpClass
0x18001a06b  mov     [rsp+78h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18001a074  xor     r8d, r8d; Reserved
0x18001a077  mov     [rsp+78h+samDesired], esi; samDesired
0x18001a07b  mov     rdx, rdi; lpSubKey
0x18001a07e  mov     rcx, rbp; hKey
0x18001a081  mov     [rsp+78h+dwOptions], 0; dwOptions
0x18001a089  mov     [rsp+78h+arg_18], 0
0x18001a095  mov     qword ptr [rbx], 0
0x18001a09c  call    cs:__imp_RegCreateKeyExW
0x18001a0a3  nop     dword ptr [rax+rax+00h]
0x18001a0a8  test    eax, eax
0x18001a0aa  jz      short loc_18001A0DA
0x18001a0ac  mov     r8d, eax
0x18001a0af  lea     rdx, aRegcreatekeyex; "RegCreateKeyExW"
0x18001a0b6  lea     rcx, aNcaregcreateke; "NcaRegCreateKey"
0x18001a0bd  call    NcaReportErrorAsWinError
0x18001a0c2  mov     ecx, eax
0x18001a0c4  test    eax, eax
0x18001a0c6  jns     short loc_18001A0E7
0x18001a0c8  mov     edx, eax
0x18001a0ca  lea     rcx, aNcaregcreateke; "NcaRegCreateKey"
0x18001a0d1  call    NcaReportReturnError
0x18001a0d6  mov     ecx, eax
0x18001a0d8  jmp     short loc_18001A0E7
0x18001a0da  mov     rax, [rsp+78h+arg_18]
0x18001a0e2  xor     ecx, ecx
0x18001a0e4  mov     [rbx], rax
0x18001a0e7  mov     eax, ecx
0x18001a0e9  add     rsp, 58h
0x18001a0ed  pop     rdi
0x18001a0ee  pop     rsi
0x18001a0ef  pop     rbp
0x18001a0f0  pop     rbx
0x18001a0f1  retn
```
