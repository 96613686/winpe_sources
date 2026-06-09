# UnwindCompressBegin(x)

- ea: `0x10004a67`
- end: `0x10004b35`
- name: `_UnwindCompressBegin@4`
- size: `206`
- prototype: `int __thiscall(HLOCAL hMem)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10004695`
- `0x1000fdf3`

## callees

- `0x10004a67`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ad5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b2a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a7e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004a9c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004aa5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ab7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ac6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ad5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004ae6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004af7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b08`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b19`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10004b2a`

## pseudocode

```c
int __thiscall UnwindCompressBegin(HLOCAL hMem)
{
  HLOCAL *v2; // edi
  HLOCAL *v4; // [esp-4h] [ebp-Ch]

  v2 = (HLOCAL *)*((_DWORD *)hMem + 49);
  while ( v2 )
  {
    if ( v2[4] )
      LocalFree(v2[4]);
    if ( v2[5] )
      LocalFree(v2[5]);
    if ( v2[7] )
      LocalFree(v2[7]);
    v4 = v2;
    v2 = (HLOCAL *)*v2;
    LocalFree(v4);
  }
  if ( *((_DWORD *)hMem + 27) )
    LocalFree(*((HLOCAL *)hMem + 27));
  if ( *((_DWORD *)hMem + 28) )
    LocalFree(*((HLOCAL *)hMem + 28));
  if ( *((_DWORD *)hMem + 31) )
    LocalFree(*((HLOCAL *)hMem + 31));
  if ( *((_DWORD *)hMem + 32) )
    LocalFree(*((HLOCAL *)hMem + 32));
  if ( *((_DWORD *)hMem + 37) )
    LocalFree(*((HLOCAL *)hMem + 37));
  if ( *((_DWORD *)hMem + 38) )
    LocalFree(*((HLOCAL *)hMem + 38));
  if ( *((_DWORD *)hMem + 48) )
  {
    LocalFree(*((HLOCAL *)hMem + 48));
    *((_DWORD *)hMem + 48) = 0;
  }
  LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x10004a67  mov     edi, edi
0x10004a69  push    esi
0x10004a6a  mov     esi, ecx
0x10004a6c  push    edi
0x10004a6d  mov     edi, [esi+0C4h]
0x10004a73  jmp     short loc_10004AAB
0x10004a75  cmp     dword ptr [edi+10h], 0
0x10004a79  jz      short loc_10004A84
0x10004a7b  push    dword ptr [edi+10h]; hMem
0x10004a7e  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004a84  cmp     dword ptr [edi+14h], 0
0x10004a88  jz      short loc_10004A93
0x10004a8a  push    dword ptr [edi+14h]; hMem
0x10004a8d  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004a93  cmp     dword ptr [edi+1Ch], 0
0x10004a97  jz      short loc_10004AA2
0x10004a99  push    dword ptr [edi+1Ch]; hMem
0x10004a9c  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004aa2  push    edi; hMem
0x10004aa3  mov     edi, [edi]
0x10004aa5  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004aab  test    edi, edi
0x10004aad  jnz     short loc_10004A75
0x10004aaf  cmp     [esi+6Ch], edi
0x10004ab2  jz      short loc_10004ABD
0x10004ab4  push    dword ptr [esi+6Ch]; hMem
0x10004ab7  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004abd  cmp     dword ptr [esi+70h], 0
0x10004ac1  jz      short loc_10004ACC
0x10004ac3  push    dword ptr [esi+70h]; hMem
0x10004ac6  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004acc  cmp     dword ptr [esi+7Ch], 0
0x10004ad0  jz      short loc_10004ADB
0x10004ad2  push    dword ptr [esi+7Ch]; hMem
0x10004ad5  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004adb  mov     eax, [esi+80h]
0x10004ae1  test    eax, eax
0x10004ae3  jz      short loc_10004AEC
0x10004ae5  push    eax; hMem
0x10004ae6  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004aec  mov     eax, [esi+94h]
0x10004af2  test    eax, eax
0x10004af4  jz      short loc_10004AFD
0x10004af6  push    eax; hMem
0x10004af7  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004afd  mov     eax, [esi+98h]
0x10004b03  test    eax, eax
0x10004b05  jz      short loc_10004B0E
0x10004b07  push    eax; hMem
0x10004b08  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004b0e  mov     eax, [esi+0C0h]
0x10004b14  test    eax, eax
0x10004b16  jz      short loc_10004B29
0x10004b18  push    eax; hMem
0x10004b19  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004b1f  mov     dword ptr [esi+0C0h], 0
0x10004b29  push    esi; hMem
0x10004b2a  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10004b30  pop     edi
0x10004b31  xor     eax, eax
0x10004b33  pop     esi
0x10004b34  retn
```
