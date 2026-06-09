# FindStandardVersionValue(HKEY__ *,ushort const *,ulong,ushort * *)

- ea: `0x1800312a4`
- end: `0x180031315`
- name: `?FindStandardVersionValue@@YAJPEAUHKEY__@@PEBGKPEAPEAG@Z`
- size: `113`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180031008`

## callees

- `0x18003107c`
- `0x1800312a4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1800312dc`
- `ADVAPI32!RegOpenKeyExW` at `0x1800312dc`
- `ADVAPI32!RegCloseKey` at `0x1800312fd`
- `ADVAPI32!RegCloseKey` at `0x1800312fd`

## pseudocode

```c
__int64 __fastcall FindStandardVersionValue(HKEY a1, const unsigned __int16 *a2, REGSAM a3, unsigned __int16 **a4)
{
  unsigned int StandardVersionByKey; // ebx
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  StandardVersionByKey = -2147467259;
  if ( !RegOpenKeyExW(a1, L"Software\\Microsoft\\.NETFramework\\Policy\\Standards", 0, a3, &hKey) )
  {
    StandardVersionByKey = FindStandardVersionByKey(hKey, a2, a4);
    RegCloseKey(hKey);
  }
  return StandardVersionByKey;
}

```

## disassembly

```asm
0x1800312a4  mov     r11, rsp
0x1800312a7  mov     [r11+8], rbx
0x1800312ab  mov     [r11+10h], rsi
0x1800312af  push    rdi
0x1800312b0  sub     rsp, 40h
0x1800312b4  mov     rdi, r9
0x1800312b7  mov     qword ptr [r11-18h], 0
0x1800312bf  mov     r9d, r8d; samDesired
0x1800312c2  lea     rax, [r11-18h]
0x1800312c6  mov     rsi, rdx
0x1800312c9  mov     [r11-28h], rax
0x1800312cd  xor     r8d, r8d; ulOptions
0x1800312d0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\.NETFramework\\Pol"...
0x1800312d7  mov     ebx, 80004005h
0x1800312dc  call    cs:__imp_RegOpenKeyExW
0x1800312e2  test    eax, eax
0x1800312e4  jnz     short loc_180031303
0x1800312e6  mov     rcx, [rsp+48h+hKey]; HKEY
0x1800312eb  mov     r8, rdi; unsigned __int16 **
0x1800312ee  mov     rdx, rsi; unsigned __int16 *
0x1800312f1  call    ?FindStandardVersionByKey@@YAJPEAUHKEY__@@PEBGPEAPEAG@Z; FindStandardVersionByKey(HKEY__ *,ushort const *,ushort * *)
0x1800312f6  mov     rcx, [rsp+48h+hKey]; hKey
0x1800312fb  mov     ebx, eax
0x1800312fd  call    cs:__imp_RegCloseKey
0x180031303  mov     rsi, [rsp+48h+arg_8]
0x180031308  mov     eax, ebx
0x18003130a  mov     rbx, [rsp+48h+arg_0]
0x18003130f  add     rsp, 40h
0x180031313  pop     rdi
0x180031314  retn
```
