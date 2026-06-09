# EnumUILanguagesProc_CountInstalledLangs(ushort *,__int64)

- ea: `0x140006d10`
- end: `0x140006d22`
- name: `?EnumUILanguagesProc_CountInstalledLangs@@YAHPEAG_J@Z`
- size: `18`
- prototype: `__int64 __fastcall(LPWSTR, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x140006d10`

## pseudocode

```c
__int64 __fastcall EnumUILanguagesProc_CountInstalledLangs(LPWSTR a1, _DWORD *a2)
{
  __int64 result; // rax

  result = 1;
  if ( a2 )
  {
    if ( a1 )
      ++*a2;
  }
  return result;
}

```

## disassembly

```asm
0x140006d10  mov     eax, 1
0x140006d15  test    rdx, rdx
0x140006d18  jz      short locret_140006D21
0x140006d1a  test    rcx, rcx
0x140006d1d  jz      short locret_140006D21
0x140006d1f  add     [rdx], eax
0x140006d21  retn
```
