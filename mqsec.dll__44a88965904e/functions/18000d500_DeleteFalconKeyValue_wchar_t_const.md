# DeleteFalconKeyValue(wchar_t const *)

- ea: `0x18000d500`
- end: `0x18000d53d`
- name: `?DeleteFalconKeyValue@@YAJPEB_W@Z`
- size: `61`
- prototype: `__int64 __fastcall(const wchar_t *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d500`
- `0x18000da54`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x18000d532`
- `ADVAPI32!RegDeleteValueW` at `0x18000d532`

## pseudocode

```c
LSTATUS __fastcall DeleteFalconKeyValue(const wchar_t *a1)
{
  LSTATUS result; // eax
  LPCWSTR lpValueName; // [rsp+38h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+40h] [rbp+18h] BYREF

  hKey = 0;
  lpValueName = 0;
  result = GetValueKey(a1, &lpValueName, &hKey);
  if ( !result )
    return RegDeleteValueW(hKey, lpValueName);
  return result;
}

```

## disassembly

```asm
0x18000d500  mov     rax, rsp
0x18000d503  sub     rsp, 28h
0x18000d507  lea     r8, [rax+18h]; HKEY *
0x18000d50b  mov     qword ptr [rax+18h], 0
0x18000d513  lea     rdx, [rax+10h]; wchar_t **
0x18000d517  mov     qword ptr [rax+10h], 0
0x18000d51f  call    ?GetValueKey@@YAJPEB_WPEAPEB_WPEAPEAUHKEY__@@@Z; GetValueKey(wchar_t const *,wchar_t const * *,HKEY__ * *)
0x18000d524  test    eax, eax
0x18000d526  jnz     short loc_18000D538
0x18000d528  mov     rdx, [rsp+28h+lpValueName]; lpValueName
0x18000d52d  mov     rcx, [rsp+28h+hKey]; hKey
0x18000d532  call    cs:__imp_RegDeleteValueW
0x18000d538  add     rsp, 28h
0x18000d53c  retn
```
