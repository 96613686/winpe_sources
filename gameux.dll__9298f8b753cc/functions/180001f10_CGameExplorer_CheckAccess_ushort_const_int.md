# CGameExplorer::CheckAccess(ushort const *,int *)

- ea: `0x180001f10`
- end: `0x180001f25`
- name: `?CheckAccess@CGameExplorer@@UEAAJPEBGPEAH@Z`
- size: `21`
- prototype: `__int64 __fastcall(CGameExplorer *__hidden this, const unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001f10`

## pseudocode

```c
__int64 __fastcall CGameExplorer::CheckAccess(CGameExplorer *this, const unsigned __int16 *a2, int *a3)
{
  if ( !a3 )
    return 2147942487LL;
  *a3 = 1;
  return 0;
}

```

## disassembly

```asm
0x180001f10  test    r8, r8
0x180001f13  jnz     short loc_180001F1B
0x180001f15  mov     eax, 80070057h
0x180001f1a  retn
0x180001f1b  mov     dword ptr [r8], 1
0x180001f22  xor     eax, eax
0x180001f24  retn
```
