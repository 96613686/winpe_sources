# ReadGuid

- ea: `0x180034d30`
- end: `0x180034d9b`
- name: `ReadGuid`
- size: `107`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180031918`
- `0x180035538`

## callees

- `0x1800327a8`
- `0x180034d30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034d5b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180034d5b`

## string_xrefs

- `0x180034d6d`: `Failed to ready the GUID from the registry`

## pseudocode

```c
__int64 __fastcall ReadGuid(HKEY a1, const WCHAR *a2, BYTE *a3)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  __int64 v6; // rcx
  DWORD v8[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8[0] = 16;
  v3 = RegQueryValueExW(a1, a2, 0, &v9, a3, v8);
  v4 = v3;
  if ( v3 )
  {
    v5 = L"Failed to ready the GUID from the registry";
    v6 = v3;
LABEL_5:
    LogError(v6, v5);
    return v4;
  }
  if ( v9 != 3 )
  {
    v4 = 1804;
    v5 = L"Expected REG_BINARY value, and got a different value type";
    v6 = 1804;
    goto LABEL_5;
  }
  return v4;
}

```

## disassembly

```asm
0x180034d30  mov     r11, rsp
0x180034d33  push    rbx
0x180034d34  sub     rsp, 40h
0x180034d38  lea     rax, [r11-18h]
0x180034d3c  mov     [rsp+48h+arg_18], 0
0x180034d44  mov     [r11-20h], rax
0x180034d48  lea     r9, [r11+20h]; lpType
0x180034d4c  mov     [r11-28h], r8
0x180034d50  xor     r8d, r8d; lpReserved
0x180034d53  mov     [rsp+48h+var_18], 10h
0x180034d5b  call    cs:__imp_RegQueryValueExW
0x180034d62  nop     dword ptr [rax+rax+00h]
0x180034d67  mov     ebx, eax
0x180034d69  test    eax, eax
0x180034d6b  jz      short loc_180034D78
0x180034d6d  lea     rdx, aFailedToReadyT; "Failed to ready the GUID from the regis"...
0x180034d74  mov     ecx, eax
0x180034d76  jmp     short loc_180034D8D
0x180034d78  cmp     [rsp+48h+arg_18], 3
0x180034d7d  jz      short loc_180034D92
0x180034d7f  mov     ebx, 70Ch
0x180034d84  lea     rdx, aExpectedRegBin; "Expected REG_BINARY value, and got a di"...
0x180034d8b  mov     ecx, ebx
0x180034d8d  call    LogError
0x180034d92  mov     eax, ebx
0x180034d94  add     rsp, 40h
0x180034d98  pop     rbx
0x180034d99  retn
```
