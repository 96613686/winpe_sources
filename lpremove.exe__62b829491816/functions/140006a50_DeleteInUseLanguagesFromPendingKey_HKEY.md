# DeleteInUseLanguagesFromPendingKey(HKEY__ *)

- ea: `0x140006a50`
- end: `0x140006acc`
- name: `?DeleteInUseLanguagesFromPendingKey@@YAJPEAUHKEY__@@@Z`
- size: `124`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400065ac`

## callees

- `0x14000513c`
- `0x140006a50`
- `0x14000eeb8`

## import_xrefs

- `ADVAPI32!RegDeleteTreeW` at `0x140006a9a`
- `ADVAPI32!RegDeleteTreeW` at `0x140006a9a`

## pseudocode

```c
__int64 __fastcall DeleteInUseLanguagesFromPendingKey(HKEY hKey)
{
  LPCWSTR v2; // rbx
  LPCWSTR v3; // rdi
  const WCHAR *v4; // rdx
  LPCWSTR lpSubKey[5]; // [rsp+20h] [rbp-28h] BYREF

  memset(lpSubKey, 0, 24);
  GetLanguagesInUse(lpSubKey);
  v2 = lpSubKey[0];
  v3 = lpSubKey[1];
  while ( v2 != v3 )
  {
    if ( *((_QWORD *)v2 + 3) <= 7u )
      v4 = v2;
    else
      v4 = *(const WCHAR **)v2;
    RegDeleteTreeW(hKey, v4);
    v2 += 16;
  }
  std::vector<std::wstring>::~vector<std::wstring>(lpSubKey);
  return 0;
}

```

## disassembly

```asm
0x140006a50  mov     rax, rsp
0x140006a53  mov     [rax+8], rbx
0x140006a57  mov     [rax+18h], rsi
0x140006a5b  push    rdi
0x140006a5c  sub     rsp, 40h
0x140006a60  mov     rsi, rcx
0x140006a63  xorps   xmm0, xmm0
0x140006a66  movdqu  xmmword ptr [rax-28h], xmm0
0x140006a6b  mov     qword ptr [rax-18h], 0
0x140006a73  lea     rcx, [rax-28h]
0x140006a77  call    ?GetLanguagesInUse@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; GetLanguagesInUse(std::vector<std::wstring> &)
0x140006a7c  mov     rbx, [rsp+48h+lpSubKey]
0x140006a81  mov     rdi, [rsp+48h+var_20]
0x140006a86  jmp     short loc_140006AA4
0x140006a88  cmp     qword ptr [rbx+18h], 7
0x140006a8d  jbe     short loc_140006A94
0x140006a8f  mov     rdx, [rbx]
0x140006a92  jmp     short loc_140006A97
0x140006a94  mov     rdx, rbx; lpSubKey
0x140006a97  mov     rcx, rsi; hKey
0x140006a9a  call    cs:__imp_RegDeleteTreeW
0x140006aa0  add     rbx, 20h ; ' '
0x140006aa4  cmp     rbx, rdi
0x140006aa7  jnz     short loc_140006A88
0x140006aa9  lea     rcx, [rsp+48h+lpSubKey]
0x140006aae  call    ??1?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x140006ab3  xor     eax, eax
0x140006ab5  jmp     short loc_140006ABB
0x140006ab7  mov     eax, [rsp+48h+arg_8]
0x140006abb  mov     rbx, [rsp+48h+arg_0]
0x140006ac0  mov     rsi, [rsp+48h+arg_10]
0x140006ac5  add     rsp, 40h
0x140006ac9  pop     rdi
0x140006aca  retn
```
