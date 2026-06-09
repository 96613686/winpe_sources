# SetIkev2CustomPolicy

- ea: `0x18003472c`
- end: `0x1800347d8`
- name: `SetIkev2CustomPolicy`
- size: `172`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180034244`

## callees

- `0x180034130`
- `0x18003472c`

## import_xrefs

- `KERNEL32!RegDeleteKeyExW` at `0x180034768`
- `KERNEL32!RegDeleteKeyExW` at `0x180034768`
- `ADVAPI32!RegCloseKey` at `0x1800347c5`
- `ADVAPI32!RegCloseKey` at `0x1800347c5`
- `ADVAPI32!RegCreateKeyExW` at `0x1800347a0`
- `ADVAPI32!RegCreateKeyExW` at `0x1800347a0`

## pseudocode

```c
__int64 __fastcall SetIkev2CustomPolicy(HKEY a1, BYTE *a2)
{
  unsigned int v3; // ebx
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  hKey = 0;
  dwDisposition = 0;
  if ( a1 )
  {
    if ( a2 )
    {
      v3 = RegCreateKeyExW(a1, L"IKEv2CustomPolicy", 0, 0, 0, 0x3001Fu, 0, &hKey, &dwDisposition);
      if ( !v3 )
        v3 = SetCustomPolicyRegParams(hKey, a2);
    }
    else
    {
      v3 = 0;
      RegDeleteKeyExW(a1, L"IKEv2CustomPolicy", 0, 0);
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  else
  {
    return 87;
  }
  return v3;
}

```

## disassembly

```asm
0x18003472c  mov     [rsp+arg_8], rbx
0x180034731  push    rdi
0x180034732  sub     rsp, 50h
0x180034736  mov     [rsp+58h+hKey], 0
0x18003473f  mov     rdi, rdx
0x180034742  mov     [rsp+58h+dwDisposition], 0
0x18003474a  test    rcx, rcx
0x18003474d  jnz     short loc_180034754
0x18003474f  lea     ebx, [rcx+57h]
0x180034752  jmp     short loc_1800347CB
0x180034754  xor     r8d, r8d; Reserved
0x180034757  lea     rdx, aIkev2custompol; "IKEv2CustomPolicy"
0x18003475e  test    rdi, rdi
0x180034761  jnz     short loc_180034770
0x180034763  xor     ebx, ebx
0x180034765  xor     r9d, r9d; Reserved
0x180034768  call    cs:__imp_RegDeleteKeyExW
0x18003476e  jmp     short loc_1800347BB
0x180034770  lea     rax, [rsp+58h+dwDisposition]
0x180034775  xor     r9d, r9d; lpClass
0x180034778  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18003477d  lea     rax, [rsp+58h+hKey]
0x180034782  mov     [rsp+58h+phkResult], rax; phkResult
0x180034787  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180034790  mov     [rsp+58h+samDesired], 3001Fh; samDesired
0x180034798  mov     [rsp+58h+dwOptions], 0; dwOptions
0x1800347a0  call    cs:__imp_RegCreateKeyExW
0x1800347a6  mov     ebx, eax
0x1800347a8  test    eax, eax
0x1800347aa  jnz     short loc_1800347BB
0x1800347ac  mov     rcx, [rsp+58h+hKey]; hKey
0x1800347b1  mov     rdx, rdi; lpData
0x1800347b4  call    SetCustomPolicyRegParams
0x1800347b9  mov     ebx, eax
0x1800347bb  mov     rcx, [rsp+58h+hKey]; hKey
0x1800347c0  test    rcx, rcx
0x1800347c3  jz      short loc_1800347CB
0x1800347c5  call    cs:__imp_RegCloseKey
0x1800347cb  mov     eax, ebx
0x1800347cd  mov     rbx, [rsp+58h+arg_8]
0x1800347d2  add     rsp, 50h
0x1800347d6  pop     rdi
0x1800347d7  retn
```
