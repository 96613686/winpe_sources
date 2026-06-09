# Reg_SetValue

- ea: `0x18008148c`
- end: `0x180081522`
- name: `Reg_SetValue`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180077700`

## callees

- `0x18003f31c`
- `0x18008148c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800814c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800814c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081503`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180081503`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800814f2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800814f2`

## pseudocode

```c
__int64 __fastcall Reg_SetValue(__int64 a1, unsigned __int64 a2, unsigned int a3, DWORD a4, BYTE *lpData, DWORD cbData)
{
  const WCHAR *v7; // rsi
  HKEY Key; // rdi
  unsigned int v9; // ebx

  v7 = (&RegPropertyTable)[2 * a3];
  Key = Reg_CreateKey(a2, 1);
  if ( Key )
  {
    v9 = RegSetValueExW(Key, v7, 0, a4, lpData, cbData);
    RegCloseKey(Key);
  }
  else
  {
    return GetLastError();
  }
  return v9;
}

```

## disassembly

```asm
0x18008148c  mov     [rsp+arg_0], rbx
0x180081491  mov     [rsp+arg_8], rsi
0x180081496  push    rdi
0x180081497  sub     rsp, 30h
0x18008149b  mov     eax, r8d
0x18008149e  lea     rsi, RegPropertyTable
0x1800814a5  add     rax, rax
0x1800814a8  mov     rcx, rdx
0x1800814ab  mov     edx, 1
0x1800814b0  mov     ebx, r9d
0x1800814b3  mov     rsi, [rsi+rax*8]
0x1800814b7  call    Reg_CreateKey
0x1800814bc  mov     rdi, rax
0x1800814bf  test    rax, rax
0x1800814c2  jnz     short loc_1800814D4
0x1800814c4  call    cs:__imp_GetLastError
0x1800814cb  nop     dword ptr [rax+rax+00h]
0x1800814d0  mov     ebx, eax
0x1800814d2  jmp     short loc_18008150F
0x1800814d4  mov     eax, [rsp+38h+arg_28]
0x1800814d8  mov     r9d, ebx; dwType
0x1800814db  mov     [rsp+38h+cbData], eax; cbData
0x1800814df  xor     r8d, r8d; Reserved
0x1800814e2  mov     rax, [rsp+38h+arg_20]
0x1800814e7  mov     rdx, rsi; lpValueName
0x1800814ea  mov     rcx, rdi; hKey
0x1800814ed  mov     [rsp+38h+lpData], rax; lpData
0x1800814f2  call    cs:__imp_RegSetValueExW
0x1800814f9  nop     dword ptr [rax+rax+00h]
0x1800814fe  mov     rcx, rdi; hKey
0x180081501  mov     ebx, eax
0x180081503  call    cs:__imp_RegCloseKey
0x18008150a  nop     dword ptr [rax+rax+00h]
0x18008150f  mov     rsi, [rsp+38h+arg_8]
0x180081514  mov     eax, ebx
0x180081516  mov     rbx, [rsp+38h+arg_0]
0x18008151b  add     rsp, 30h
0x18008151f  pop     rdi
0x180081520  retn
```
