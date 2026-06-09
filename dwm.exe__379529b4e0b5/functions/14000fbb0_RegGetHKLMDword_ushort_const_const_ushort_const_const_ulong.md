# RegGetHKLMDword(ushort const * const,ushort const * const,ulong *)

- ea: `0x14000fbb0`
- end: `0x14000fc1d`
- name: `?RegGetHKLMDword@@YA_NQEBG0PEAK@Z`
- size: `109`
- prototype: `bool(const unsigned __int16 *const, const unsigned __int16 *const, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fa84`

## callees

- `0x14000fb34`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fc0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14000fc0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fbec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fbec`

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
0x14000fbb0  mov     r11, rsp
0x14000fbb3  mov     [r11+8], rbx
0x14000fbb7  mov     [r11+10h], rdx
0x14000fbbb  push    rdi
0x14000fbbc  sub     rsp, 30h
0x14000fbc0  mov     rdi, r8
0x14000fbc3  mov     qword ptr [r11+10h], 0
0x14000fbcb  lea     rax, [r11+10h]
0x14000fbcf  xor     r8d, r8d; ulOptions
0x14000fbd2  mov     r9d, 20019h; samDesired
0x14000fbd8  mov     [r11-18h], rax
0x14000fbdc  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Avalon.Graphics"
0x14000fbe3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fbea  xor     bl, bl
0x14000fbec  call    cs:__imp_RegOpenKeyExW
0x14000fbf2  test    eax, eax
0x14000fbf4  jnz     short loc_14000FC10
0x14000fbf6  mov     rcx, [rsp+38h+hKey]; HKEY
0x14000fbfb  mov     r8, rdi; unsigned int *
0x14000fbfe  call    ?RegGetDword@@YA_NQEAUHKEY__@@QEBGPEAK@Z; RegGetDword(HKEY__ * const,ushort const * const,ulong *)
0x14000fc03  mov     rcx, [rsp+38h+hKey]; hKey
0x14000fc08  mov     bl, al
0x14000fc0a  call    cs:__imp_RegCloseKey
0x14000fc10  mov     al, bl
0x14000fc12  mov     rbx, [rsp+38h+arg_0]
0x14000fc17  add     rsp, 30h
0x14000fc1b  pop     rdi
0x14000fc1c  retn
```
