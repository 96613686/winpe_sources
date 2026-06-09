# CFontRegistry::Delete(CFontRegValue &)

- ea: `0x180025b58`
- end: `0x180025bb9`
- name: `?Delete@CFontRegistry@@SAJAEAVCFontRegValue@@@Z`
- size: `97`
- prototype: `__int64 __fastcall(struct CFontRegValue *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callers

- `0x180026004`
- `0x18002614c`

## callees

- `0x180025b58`
- `0x180025e80`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025b8c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180025b8c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ba6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180025ba6`

## pseudocode

```c
__int64 __fastcall CFontRegistry::Delete(struct CFontRegValue *a1)
{
  unsigned int v2; // ebx
  LSTATUS v3; // eax
  HKEY hKey; // [rsp+38h] [rbp+10h] BYREF

  hKey = 0;
  v2 = CFontRegistry::OpenKey(a1, 0x20006u, &hKey);
  if ( !v2 )
  {
    v3 = RegDeleteValueW(hKey, (LPCWSTR)a1 + 6);
    v2 = v3;
    if ( v3 > 0 )
      v2 = (unsigned __int16)v3 | 0x80070000;
    RegCloseKey(hKey);
  }
  return v2;
}

```

## disassembly

```asm
0x180025b58  mov     [rsp+arg_0], rbx
0x180025b5d  push    rdi
0x180025b5e  sub     rsp, 20h
0x180025b62  lea     r8, [rsp+28h+hKey]; HKEY *
0x180025b67  mov     [rsp+28h+hKey], 0
0x180025b70  mov     edx, 20006h; unsigned int
0x180025b75  mov     rdi, rcx
0x180025b78  call    ?OpenKey@CFontRegistry@@SAJAEBVCFontRegValue@@KPEAPEAUHKEY__@@@Z; CFontRegistry::OpenKey(CFontRegValue const &,ulong,HKEY__ * *)
0x180025b7d  mov     ebx, eax
0x180025b7f  test    eax, eax
0x180025b81  jnz     short loc_180025BAC
0x180025b83  mov     rcx, [rsp+28h+hKey]; hKey
0x180025b88  lea     rdx, [rdi+0Ch]; lpValueName
0x180025b8c  call    cs:__imp_RegDeleteValueW
0x180025b92  mov     ebx, eax
0x180025b94  test    eax, eax
0x180025b96  jle     short loc_180025BA1
0x180025b98  movzx   ebx, ax
0x180025b9b  or      ebx, 80070000h
0x180025ba1  mov     rcx, [rsp+28h+hKey]; hKey
0x180025ba6  call    cs:__imp_RegCloseKey
0x180025bac  mov     eax, ebx
0x180025bae  mov     rbx, [rsp+28h+arg_0]
0x180025bb3  add     rsp, 20h
0x180025bb7  pop     rdi
0x180025bb8  retn
```
