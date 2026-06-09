# SetDWORDKeyValue

- ea: `0x180011b8c`
- end: `0x180011c0e`
- name: `SetDWORDKeyValue`
- size: `130`
- prototype: `__int64 __fastcall(LPCWSTR lpValueName)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800114c0`
- `0x180012cb0`

## callees

- `0x18000a364`
- `0x180011440`
- `0x180011b8c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180011bc3`
- `ADVAPI32!RegSetValueExW` at `0x180011bc3`

## pseudocode

```c
HKEY __fastcall SetDWORDKeyValue(LPCWSTR lpValueName, int a2)
{
  HKEY result; // rax
  int Data; // [rsp+48h] [rbp+10h] BYREF

  Data = a2;
  result = (HKEY)GetUserRegHandle();
  if ( result )
  {
    RegSetValueExW(result, lpValueName, 0, 4u, (const BYTE *)&Data, 4u);
    result = (HKEY)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
      return (HKEY)WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 32), Data);
  }
  return result;
}

```

## disassembly

```asm
0x180011b8c  mov     [rsp+Data], edx
0x180011b90  push    rbx
0x180011b91  sub     rsp, 30h
0x180011b95  mov     rbx, rcx
0x180011b98  call    GetUserRegHandle
0x180011b9d  test    rax, rax
0x180011ba0  jz      short loc_180011C08
0x180011ba2  lea     rcx, [rsp+38h+Data]
0x180011ba7  mov     [rsp+38h+cbData], 4; cbData
0x180011baf  mov     [rsp+38h+lpData], rcx; lpData
0x180011bb4  mov     r9d, 4; dwType
0x180011bba  mov     rcx, rax; hKey
0x180011bbd  xor     r8d, r8d; Reserved
0x180011bc0  mov     rdx, rbx; lpValueName
0x180011bc3  call    cs:__imp_RegSetValueExW
0x180011bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x180011bd0  lea     rax, WPP_GLOBAL_Control
0x180011bd7  cmp     rcx, rax
0x180011bda  jz      short loc_180011C08
0x180011bdc  test    byte ptr [rcx+10Ch], 4
0x180011be3  jz      short loc_180011C08
0x180011be5  mov     eax, [rsp+38h+Data]
0x180011be9  lea     r8, WPP_c9e6d7d0caca384cb3bfbf1e9bd143d7_Traceguids
0x180011bf0  mov     rcx, [rcx+100h]; LoggerHandle
0x180011bf7  mov     edx, 0Ah
0x180011bfc  mov     r9, rbx
0x180011bff  mov     dword ptr [rsp+38h+lpData], eax; char
0x180011c03  call    WPP_SF_Sd
0x180011c08  add     rsp, 30h
0x180011c0c  pop     rbx
0x180011c0d  retn
```
