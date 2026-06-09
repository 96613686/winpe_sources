# CreateKey(HKEY__ *,ushort const *,ushort const *,HKEY__ * *)

- ea: `0x18004050c`
- end: `0x1800405d6`
- name: `?CreateKey@@YAJPEAUHKEY__@@PEBG1PEAPEAU1@@Z`
- size: `202`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180040628`
- `0x180040908`

## callees

- `0x18000c910`
- `0x18004050c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040552`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180040552`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040587`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040587`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800405af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004596b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800405af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004596b`

## pseudocode

```c
__int64 __fastcall CreateKey(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, HKEY *a4)
{
  unsigned int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // cc
  int v9; // eax
  HKEY hKey; // [rsp+50h] [rbp-18h] BYREF

  hKey = 0;
  v6 = 0;
  v7 = RegCreateKeyExW(a1, a2, 0, 0, 0, 0x2001Fu, 0, &hKey, 0);
  v8 = v7 <= 0;
  if ( v7
    || a3
    && (v9 = safe_lstrlenW(a3), v7 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)a3, 2 * v9 + 2), v8 = v7 <= 0, v7) )
  {
    if ( v8 )
      v6 = v7;
    else
      v6 = (unsigned __int16)v7 | 0x80070000;
  }
  if ( a4 )
  {
    *a4 = hKey;
  }
  else if ( hKey )
  {
    RegCloseKey(hKey);
  }
  return v6;
}

```

## disassembly

```asm
0x18004050c  mov     r11, rsp
0x18004050f  mov     [r11+8], rbx
0x180040513  mov     [r11+10h], rsi
0x180040517  mov     [r11+20h], r9
0x18004051b  push    rdi
0x18004051c  sub     rsp, 60h
0x180040520  mov     rdi, r9
0x180040523  mov     rsi, r8
0x180040526  mov     qword ptr [r11-18h], 0
0x18004052e  xor     ebx, ebx
0x180040530  mov     [r11-28h], rbx
0x180040534  lea     rax, [r11-18h]
0x180040538  mov     [r11-30h], rax
0x18004053c  mov     [r11-38h], rbx
0x180040540  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180040548  mov     [rsp+68h+dwOptions], ebx; dwOptions
0x18004054c  xor     r9d, r9d; lpClass
0x18004054f  xor     r8d, r8d; Reserved
0x180040552  call    cs:__imp_RegCreateKeyExW
0x180040558  test    eax, eax
0x18004055a  jnz     short loc_180040591
0x18004055c  test    rsi, rsi
0x18004055f  jz      short loc_1800405A0
0x180040561  mov     rcx, rsi; unsigned __int16 *
0x180040564  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x180040569  lea     eax, ds:2[rax*2]
0x180040570  mov     [rsp+68h+samDesired], eax; cbData
0x180040574  mov     qword ptr [rsp+68h+dwOptions], rsi; lpData
0x180040579  lea     r9d, [rbx+1]; dwType
0x18004057d  xor     r8d, r8d; Reserved
0x180040580  xor     edx, edx; lpValueName
0x180040582  mov     rcx, [rsp+68h+hKey]; hKey
0x180040587  call    cs:__imp_RegSetValueExW
0x18004058d  test    eax, eax
0x18004058f  jz      short loc_1800405A0
0x180040591  jg      short loc_180040597
0x180040593  mov     ebx, eax
0x180040595  jmp     short loc_1800405A0
0x180040597  movzx   ebx, ax
0x18004059a  or      ebx, 80070000h
0x1800405a0  test    rdi, rdi
0x1800405a3  jnz     short loc_1800405BC
0x1800405a5  mov     rcx, [rsp+68h+hKey]; hKey
0x1800405aa  test    rcx, rcx
0x1800405ad  jz      short loc_1800405B7
0x1800405af  call    cs:__imp_RegCloseKey
0x1800405b5  jmp     short loc_1800405C4
0x1800405b7  test    rdi, rdi
0x1800405ba  jz      short loc_1800405C4
0x1800405bc  mov     rcx, [rsp+68h+hKey]
0x1800405c1  mov     [rdi], rcx
0x1800405c4  mov     eax, ebx
0x1800405c6  mov     rbx, [rsp+68h+arg_0]
0x1800405cb  mov     rsi, [rsp+68h+arg_8]
0x1800405d0  add     rsp, 60h
0x1800405d4  pop     rdi
0x1800405d5  retn
0x18004594d  push    rbp
0x18004594f  sub     rsp, 50h
0x180045953  mov     rbp, rdx
0x180045956  mov     rdx, [rbp+88h]
0x18004595d  test    rdx, rdx
0x180045960  jnz     short loc_180045978
0x180045962  mov     rcx, [rbp+50h]; hKey
0x180045966  test    rcx, rcx
0x180045969  jz      short loc_180045973
0x18004596b  call    cs:__imp_RegCloseKey
0x180045971  jmp     short loc_18004597F
0x180045973  test    rdx, rdx
0x180045976  jz      short loc_18004597F
0x180045978  mov     rax, [rbp+50h]
0x18004597c  mov     [rdx], rax
0x18004597f  add     rsp, 50h
0x180045983  pop     rbp
0x180045984  retn
```
