# RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)

- ea: `0x180014f98`
- end: `0x180015005`
- name: `?RegGetHKLMDword@@YA_NQEBG0PEAK@Z`
- size: `109`
- prototype: `bool(const unsigned __int16 *const, const unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014e94`

## callees

- `0x180014f1c`
- `0x180014f98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fd4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014fd4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ff2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180014ff2`

## pseudocode

```c
bool __fastcall RegGetHKLMDword(const unsigned __int16 *const a1, const unsigned __int16 *const a2, unsigned int *a3)
{
  bool Dword; // bl
  const unsigned __int16 *v5; // rdx
  HKEY hKey; // [rsp+48h] [rbp+10h] BYREF

  hKey = 0;
  Dword = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Avalon.Graphics", 0, 0x20019u, &hKey) )
  {
    Dword = RegGetDword(hKey, v5, a3);
    RegCloseKey(hKey);
  }
  return Dword;
}

```

## disassembly

```asm
0x180014f98  mov     r11, rsp
0x180014f9b  mov     [r11+8], rbx
0x180014f9f  mov     [r11+10h], rdx
0x180014fa3  push    rdi
0x180014fa4  sub     rsp, 30h
0x180014fa8  mov     rdi, r8
0x180014fab  mov     qword ptr [r11+10h], 0
0x180014fb3  lea     rax, [r11+10h]
0x180014fb7  xor     r8d, r8d; ulOptions
0x180014fba  mov     r9d, 20019h; samDesired
0x180014fc0  mov     [r11-18h], rax
0x180014fc4  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Avalon.Graphics"
0x180014fcb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014fd2  xor     bl, bl
0x180014fd4  call    cs:__imp_RegOpenKeyExW
0x180014fda  test    eax, eax
0x180014fdc  jnz     short loc_180014FF8
0x180014fde  mov     rcx, [rsp+38h+hKey]; HKEY
0x180014fe3  mov     r8, rdi; unsigned int *
0x180014fe6  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x180014feb  mov     rcx, [rsp+38h+hKey]; hKey
0x180014ff0  mov     bl, al
0x180014ff2  call    cs:__imp_RegCloseKey
0x180014ff8  mov     al, bl
0x180014ffa  mov     rbx, [rsp+38h+arg_0]
0x180014fff  add     rsp, 30h
0x180015003  pop     rdi
0x180015004  retn
```
