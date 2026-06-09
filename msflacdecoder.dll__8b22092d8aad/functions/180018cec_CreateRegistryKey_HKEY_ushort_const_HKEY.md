# CreateRegistryKey(HKEY__ *,ushort const *,HKEY__ * *)

- ea: `0x180018cec`
- end: `0x180018d32`
- name: `?CreateRegistryKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z`
- size: `70`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, HKEY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18001a540`

## callees

- `0x180018cec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018d1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018d1b`

## pseudocode

```c
LSTATUS __fastcall CreateRegistryKey(HKEY a1, const unsigned __int16 *a2, HKEY *a3)
{
  LSTATUS result; // eax

  result = RegCreateKeyExW(a1, a2, 0, 0, 0, 0xF003Fu, 0, a3, 0);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180018cec  mov     rax, rsp
0x180018cef  sub     rsp, 58h
0x180018cf3  mov     qword ptr [rax-18h], 0
0x180018cfb  xor     r9d, r9d; lpClass
0x180018cfe  mov     [rax-20h], r8
0x180018d02  xor     r8d, r8d; Reserved
0x180018d05  mov     qword ptr [rax-28h], 0
0x180018d0d  mov     dword ptr [rax-30h], 0F003Fh
0x180018d14  mov     dword ptr [rax-38h], 0
0x180018d1b  call    cs:__imp_RegCreateKeyExW
0x180018d21  test    eax, eax
0x180018d23  jle     short loc_180018D2D
0x180018d25  movzx   eax, ax
0x180018d28  or      eax, 80070000h
0x180018d2d  add     rsp, 58h
0x180018d31  retn
```
