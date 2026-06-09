# IsManifestFile(ushort const *)

- ea: `0x1400592a4`
- end: `0x1400592db`
- name: `?IsManifestFile@@YA_NPEBG@Z`
- size: `55`
- prototype: `bool __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140059630`

## callees

- `0x140002be4`
- `0x1400592a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400592b2`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1400592b2`

## string_xrefs

- `0x1400592bd`: `-manifest.ini`

## pseudocode

```c
bool __fastcall IsManifestFile(const unsigned __int16 *a1)
{
  wchar_t *v1; // rax
  bool result; // al

  result = 0;
  if ( a1 )
  {
    v1 = wcsrchr(a1, 0x2Du);
    if ( v1 )
    {
      if ( !wcsicmp(v1, L"-manifest.ini") )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400592a4  sub     rsp, 28h
0x1400592a8  test    rcx, rcx
0x1400592ab  jz      short loc_1400592D4
0x1400592ad  mov     edx, 2Dh ; '-'; Ch
0x1400592b2  call    cs:__imp_wcsrchr
0x1400592b8  test    rax, rax
0x1400592bb  jz      short loc_1400592D4
0x1400592bd  lea     rdx, aManifestIni; "-manifest.ini"
0x1400592c4  mov     rcx, rax; String1
0x1400592c7  call    _wcsicmp
0x1400592cc  test    eax, eax
0x1400592ce  jnz     short loc_1400592D4
0x1400592d0  mov     al, 1
0x1400592d2  jmp     short loc_1400592D6
0x1400592d4  xor     al, al
0x1400592d6  add     rsp, 28h
0x1400592da  retn
```
