# RegistrySerialization::s_SetValue(HKEY__ * const,wchar_t const * const,ulong,uchar * const,ulong)

- ea: `0x180018760`
- end: `0x180018797`
- name: `?s_SetValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_WKQEAEK@Z`
- size: `55`
- prototype: `static int(HKEY, const wchar_t *const, unsigned int, unsigned __int8 *const, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011f44`
- `0x1800175e4`
- `0x1800187a0`

## callees

- `0x180018760`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180018779`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180018779`

## pseudocode

```c
LSTATUS __fastcall RegistrySerialization::s_SetValue(
        HKEY a1,
        const WCHAR *a2,
        DWORD a3,
        unsigned __int8 *const lpData,
        DWORD cbData)
{
  LSTATUS result; // eax

  result = RegSetKeyValueW(a1, 0, a2, a3, lpData, cbData);
  if ( result > 0 )
    return (unsigned __int16)result | 0xC0070000;
  return result;
}

```

## disassembly

```asm
0x180018760  sub     rsp, 38h
0x180018764  mov     eax, [rsp+38h+arg_20]
0x180018768  mov     [rsp+38h+cbData], eax; cbData
0x18001876c  mov     [rsp+38h+lpData], r9; lpData
0x180018771  mov     r9d, r8d; dwType
0x180018774  mov     r8, rdx; lpValueName
0x180018777  xor     edx, edx; lpSubKey
0x180018779  call    cs:__imp_RegSetKeyValueW
0x180018780  nop     dword ptr [rax+rax+00h]
0x180018785  test    eax, eax
0x180018787  jle     short loc_180018791
0x180018789  movzx   eax, ax
0x18001878c  or      eax, 0C0070000h
0x180018791  add     rsp, 38h
0x180018795  retn
```
