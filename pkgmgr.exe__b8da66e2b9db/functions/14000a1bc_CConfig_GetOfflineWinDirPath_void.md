# CConfig::GetOfflineWinDirPath(void)

- ea: `0x14000a1bc`
- end: `0x14000a1d5`
- name: `?GetOfflineWinDirPath@CConfig@@QEAAPEB_WXZ`
- size: `25`
- prototype: `const wchar_t *__fastcall(CConfig *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000a1dc`
- `0x14000b454`

## callees

- `0x14000a1bc`

## pseudocode

```c
const wchar_t *__fastcall CConfig::GetOfflineWinDirPath(CConfig *this)
{
  if ( *((_QWORD *)this + 35) == 2 )
    return *(const wchar_t **)(*((_QWORD *)this + 37) + 8LL);
  else
    return 0;
}

```

## disassembly

```asm
0x14000a1bc  cmp     qword ptr [rcx+118h], 2
0x14000a1c4  jnz     short loc_14000A1D2
0x14000a1c6  mov     rax, [rcx+128h]
0x14000a1cd  mov     rax, [rax+8]
0x14000a1d1  retn
0x14000a1d2  xor     eax, eax
0x14000a1d4  retn
```
