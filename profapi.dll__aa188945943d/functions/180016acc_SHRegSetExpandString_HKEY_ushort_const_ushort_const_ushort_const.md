# SHRegSetExpandString(HKEY__ *,ushort const *,ushort const *,ushort const *)

- ea: `0x180016acc`
- end: `0x180016b28`
- name: `?SHRegSetExpandString@@YAJPEAUHKEY__@@PEBG11@Z`
- size: `92`
- prototype: `LSTATUS __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, const BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ebe0`

## callees

- `0x180016acc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b09`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180016b09`

## pseudocode

```c
LSTATUS __fastcall SHRegSetExpandString(
        HKEY a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const BYTE *lpData)
{
  unsigned __int64 v4; // rax
  LSTATUS result; // eax

  v4 = -1;
  do
    ++v4;
  while ( *(_WORD *)&lpData[2 * v4] );
  if ( v4 >= 0x7FFFFFFF )
  {
    LOWORD(result) = 534;
  }
  else
  {
    result = RegSetValueExW(a1, a3, 0, 2u, lpData, 2 * v4 + 2);
    if ( result <= 0 )
      return result;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x180016acc  push    rbx
0x180016ace  sub     rsp, 30h
0x180016ad2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016ad6  mov     r10, r8
0x180016ad9  xor     ebx, ebx
0x180016adb  inc     rax
0x180016ade  cmp     [r9+rax*2], bx
0x180016ae3  jnz     short loc_180016ADB
0x180016ae5  cmp     rax, 7FFFFFFFh
0x180016aeb  jnb     short loc_180016B15
0x180016aed  lea     eax, ds:2[rax*2]
0x180016af4  xor     r8d, r8d; Reserved
0x180016af7  mov     [rsp+38h+cbData], eax; cbData
0x180016afb  mov     rdx, r10; lpValueName
0x180016afe  mov     [rsp+38h+lpData], r9; lpData
0x180016b03  mov     r9d, 2; dwType
0x180016b09  call    cs:__imp_RegSetValueExW
0x180016b0f  test    eax, eax
0x180016b11  jle     short loc_180016B22
0x180016b13  jmp     short loc_180016B1A
0x180016b15  mov     eax, 216h
0x180016b1a  movzx   eax, ax
0x180016b1d  or      eax, 80070000h
0x180016b22  add     rsp, 30h
0x180016b26  pop     rbx
0x180016b27  retn
```
