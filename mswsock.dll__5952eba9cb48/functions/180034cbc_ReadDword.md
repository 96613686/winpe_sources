# ReadDword

- ea: `0x180034cbc`
- end: `0x180034d27`
- name: `ReadDword`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031b4c`
- `0x1800326d0`
- `0x180034690`

## callees

- `0x1800327a8`
- `0x180034cbc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ce7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034ce7`

## pseudocode

```c
__int64 __fastcall ReadDword(HKEY a1, const WCHAR *a2, BYTE *a3)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  __int64 v6; // rcx
  DWORD v8[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8[0] = 4;
  v3 = RegQueryValueExW(a1, a2, 0, &v9, a3, v8);
  v4 = v3;
  if ( v3 )
  {
    v5 = L"Failed to get value";
    v6 = v3;
LABEL_5:
    LogError(v6, v5);
    return v4;
  }
  if ( v9 != 4 )
  {
    v4 = 1804;
    v5 = L"Expected DWORD value, and got a different value type";
    v6 = 1804;
    goto LABEL_5;
  }
  return v4;
}

```

## disassembly

```asm
0x180034cbc  mov     r11, rsp
0x180034cbf  push    rbx
0x180034cc0  sub     rsp, 40h
0x180034cc4  lea     rax, [r11-18h]
0x180034cc8  mov     [rsp+48h+arg_18], 0
0x180034cd0  mov     [r11-20h], rax
0x180034cd4  lea     r9, [r11+20h]; lpType
0x180034cd8  mov     [r11-28h], r8
0x180034cdc  xor     r8d, r8d; lpReserved
0x180034cdf  mov     [rsp+48h+var_18], 4
0x180034ce7  call    cs:__imp_RegQueryValueExW
0x180034cee  nop     dword ptr [rax+rax+00h]
0x180034cf3  mov     ebx, eax
0x180034cf5  test    eax, eax
0x180034cf7  jz      short loc_180034D04
0x180034cf9  lea     rdx, aFailedToGetVal; "Failed to get value"
0x180034d00  mov     ecx, eax
0x180034d02  jmp     short loc_180034D19
0x180034d04  cmp     [rsp+48h+arg_18], 4
0x180034d09  jz      short loc_180034D1E
0x180034d0b  mov     ebx, 70Ch
0x180034d10  lea     rdx, aExpectedDwordV; "Expected DWORD value, and got a differe"...
0x180034d17  mov     ecx, ebx
0x180034d19  call    LogError
0x180034d1e  mov     eax, ebx
0x180034d20  add     rsp, 40h
0x180034d24  pop     rbx
0x180034d25  retn
```
