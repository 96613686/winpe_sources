# DiskIsManagedZonedDevice

- ea: `0x140003a78`
- end: `0x140003ab4`
- name: `DiskIsManagedZonedDevice`
- size: `60`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e798`
- `0x140015a90`

## callees

- `0x140003a78`

## pseudocode

```c
bool __fastcall DiskIsManagedZonedDevice(__int64 a1)
{
  __int64 v1; // rdx
  __int64 v2; // rcx
  bool result; // al

  v1 = *(_QWORD *)(a1 + 64);
  result = 0;
  if ( (*(_BYTE *)(v1 + 104) & 1) != 0 && *(_DWORD *)(a1 + 72) == 7 && (*(_DWORD *)(a1 + 52) & 4) == 0 )
  {
    v2 = *(_QWORD *)(v1 + 1152);
    if ( v2 )
    {
      if ( (*(_DWORD *)(v2 + 16) & 0xF8000000) == 0xA0000000 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140003a78  mov     rdx, [rcx+40h]
0x140003a7c  test    byte ptr [rdx+68h], 1
0x140003a80  jz      short loc_140003AB1
0x140003a82  cmp     dword ptr [rcx+48h], 7
0x140003a86  jnz     short loc_140003AB1
0x140003a88  mov     ecx, [rcx+34h]
0x140003a8b  test    cl, 4
0x140003a8e  jnz     short loc_140003AB1
0x140003a90  mov     rcx, [rdx+480h]
0x140003a97  test    rcx, rcx
0x140003a9a  jz      short loc_140003AB1
0x140003a9c  mov     ecx, [rcx+10h]
0x140003a9f  and     ecx, 0F8000000h
0x140003aa5  cmp     ecx, 0A0000000h
0x140003aab  jnz     short loc_140003AB1
0x140003aad  mov     al, 1
0x140003aaf  retn
0x140003ab1  xor     al, al
0x140003ab3  retn
```
