# RegistrySerialization::s_DeleteValue(HKEY__ * const,wchar_t const * const)

- ea: `0x180018544`
- end: `0x18001857a`
- name: `?s_DeleteValue@RegistrySerialization@@SAJQEAUHKEY__@@QEB_W@Z`
- size: `54`
- prototype: `static int(HKEY, const wchar_t *const)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180011f44`
- `0x1800187a0`

## callees

- `0x180018544`

## import_xrefs

- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001854d`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18001854d`

## pseudocode

```c
__int64 __fastcall RegistrySerialization::s_DeleteValue(HKEY a1, const WCHAR *a2)
{
  LSTATUS v2; // ecx

  v2 = RegDeleteKeyValueW(a1, 0, a2);
  if ( v2 == 2 )
    return 0;
  if ( v2 > 0 )
    return (unsigned __int16)v2 | 0xC0070000;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180018544  sub     rsp, 28h
0x180018548  mov     r8, rdx; lpValueName
0x18001854b  xor     edx, edx; lpSubKey
0x18001854d  call    cs:__imp_RegDeleteKeyValueW
0x180018554  nop     dword ptr [rax+rax+00h]
0x180018559  mov     ecx, eax
0x18001855b  cmp     eax, 2
0x18001855e  jnz     short loc_180018564
0x180018560  xor     eax, eax
0x180018562  jmp     short loc_180018574
0x180018564  test    ecx, ecx
0x180018566  jg      short loc_18001856C
0x180018568  mov     eax, ecx
0x18001856a  jmp     short loc_180018574
0x18001856c  movzx   eax, cx
0x18001856f  or      eax, 0C0070000h
0x180018574  add     rsp, 28h
0x180018578  retn
```
