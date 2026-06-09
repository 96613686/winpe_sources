# RegIsKey

- ea: `0x14000d9ac`
- end: `0x14000da04`
- name: `RegIsKey`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007c74`

## callees

- `0x14000d9ac`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x14000d9d8`
- `ADVAPI32!RegOpenKeyExA` at `0x14000d9d8`
- `ADVAPI32!RegCloseKey` at `0x14000d9e9`
- `ADVAPI32!RegCloseKey` at `0x14000d9e9`

## pseudocode

```c
__int64 __fastcall RegIsKey(HKEY a1)
{
  LSTATUS v1; // eax
  unsigned int v2; // ebx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  v1 = RegOpenKeyExA(a1, "ScriptEngine", 0, 0x20019u, &hKey);
  v2 = v1;
  if ( v1 )
  {
    if ( v1 > 0 )
      return (unsigned __int16)v1 | 0x80070000;
  }
  else
  {
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x14000d9ac  mov     r11, rsp
0x14000d9af  mov     [r11+10h], rdx
0x14000d9b3  push    rbx
0x14000d9b4  sub     rsp, 30h
0x14000d9b8  lea     rax, [r11+10h]
0x14000d9bc  mov     qword ptr [r11+10h], 0
0x14000d9c4  mov     r9d, 20019h; samDesired
0x14000d9ca  mov     [r11-18h], rax
0x14000d9ce  xor     r8d, r8d; ulOptions
0x14000d9d1  lea     rdx, SubKey; "ScriptEngine"
0x14000d9d8  call    cs:__imp_RegOpenKeyExA
0x14000d9de  mov     ebx, eax
0x14000d9e0  test    eax, eax
0x14000d9e2  jnz     short loc_14000D9F1
0x14000d9e4  mov     rcx, [rsp+38h+hKey]; hKey
0x14000d9e9  call    cs:__imp_RegCloseKey
0x14000d9ef  jmp     short loc_14000D9FC
0x14000d9f1  jle     short loc_14000D9FC
0x14000d9f3  movzx   ebx, ax
0x14000d9f6  or      ebx, 80070000h
0x14000d9fc  mov     eax, ebx
0x14000d9fe  add     rsp, 30h
0x14000da02  pop     rbx
0x14000da03  retn
```
