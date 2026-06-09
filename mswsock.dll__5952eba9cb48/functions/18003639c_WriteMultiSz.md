# WriteMultiSz

- ea: `0x18003639c`
- end: `0x18003640c`
- name: `WriteMultiSz`
- size: `112`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180031528`
- `0x1800328c0`

## callees

- `0x18003639c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363fa`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800363fa`

## pseudocode

```c
LSTATUS __fastcall WriteMultiSz(HKEY hKey, const WCHAR *a2, const BYTE *lpData)
{
  int v4; // r9d
  const BYTE *i; // rcx
  __int64 v6; // rax
  __int64 v7; // rax

  v4 = 0;
  if ( lpData )
  {
    for ( i = lpData; *(_WORD *)i; i += 2 * v7 )
    {
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)&i[2 * v6] );
      v7 = (unsigned int)(v6 + 1);
      v4 += v7;
    }
  }
  else
  {
    lpData = (const BYTE *)&Data;
  }
  return RegSetValueExW(hKey, a2, 0, 7u, lpData, 2 * v4 + 2);
}

```

## disassembly

```asm
0x18003639c  sub     rsp, 38h
0x1800363a0  xor     r11d, r11d
0x1800363a3  mov     r10, rcx
0x1800363a6  mov     r9d, r11d
0x1800363a9  test    r8, r8
0x1800363ac  jnz     short loc_1800363B7
0x1800363ae  lea     r8, Data
0x1800363b5  jmp     short loc_1800363DD
0x1800363b7  mov     rcx, r8
0x1800363ba  cmp     [r8], r11w
0x1800363be  jz      short loc_1800363DD
0x1800363c0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800363c4  inc     rax
0x1800363c7  cmp     [rcx+rax*2], r11w
0x1800363cc  jnz     short loc_1800363C4
0x1800363ce  inc     eax
0x1800363d0  add     r9d, eax
0x1800363d3  lea     rcx, [rcx+rax*2]
0x1800363d7  cmp     [rcx], r11w
0x1800363db  jnz     short loc_1800363C0
0x1800363dd  lea     eax, ds:2[r9*2]
0x1800363e5  mov     rcx, r10; hKey
0x1800363e8  mov     [rsp+38h+cbData], eax; cbData
0x1800363ec  mov     r9d, 7; dwType
0x1800363f2  mov     [rsp+38h+lpData], r8; lpData
0x1800363f7  xor     r8d, r8d; Reserved
0x1800363fa  call    cs:__imp_RegSetValueExW
0x180036401  nop     dword ptr [rax+rax+00h]
0x180036406  add     rsp, 38h
0x18003640a  retn
```
