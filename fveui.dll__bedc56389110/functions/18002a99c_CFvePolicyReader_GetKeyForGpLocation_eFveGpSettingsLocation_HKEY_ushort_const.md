# CFvePolicyReader::GetKeyForGpLocation(eFveGpSettingsLocation,HKEY__ * *,ushort const * *)

- ea: `0x18002a99c`
- end: `0x18002a9e4`
- name: `?GetKeyForGpLocation@CFvePolicyReader@@AEBAJW4eFveGpSettingsLocation@@PEAPEAUHKEY__@@PEAPEBG@Z`
- size: `72`
- prototype: `__int64 __fastcall(__int64, int, _QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002aae0`
- `0x18002ab90`
- `0x18002add0`

## callees

- `0x18002a99c`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::GetKeyForGpLocation(__int64 a1, int a2, _QWORD *a3, _QWORD *a4)
{
  unsigned int v4; // r10d
  int v5; // edx
  int v6; // edx
  int v7; // edx

  v4 = 0;
  *a4 = off_18002FD60[a2];
  if ( a2 && (v5 = a2 - 1) != 0 && (v6 = v5 - 1) != 0 && (v7 = v6 - 1) != 0 )
  {
    if ( v7 == 1 )
      *a3 = *(_QWORD *)(a1 + 24);
    else
      return (unsigned int)-2147024809;
  }
  else
  {
    *a3 = *(_QWORD *)(a1 + 16);
  }
  return v4;
}

```

## disassembly

```asm
0x18002a99c  movsxd  rax, edx
0x18002a99f  lea     r11, off_18002FD60; "Policies\\Microsoft\\FVE"
0x18002a9a6  xor     r10d, r10d
0x18002a9a9  mov     rax, [r11+rax*8]
0x18002a9ad  mov     [r9], rax
0x18002a9b0  test    edx, edx
0x18002a9b2  jz      short loc_18002A9D9
0x18002a9b4  sub     edx, 1
0x18002a9b7  jz      short loc_18002A9D9
0x18002a9b9  sub     edx, 1
0x18002a9bc  jz      short loc_18002A9D9
0x18002a9be  sub     edx, 1
0x18002a9c1  jz      short loc_18002A9D9
0x18002a9c3  cmp     edx, 1
0x18002a9c6  jz      short loc_18002A9D0
0x18002a9c8  mov     r10d, 80070057h
0x18002a9ce  jmp     short loc_18002A9E0
0x18002a9d0  mov     rax, [rcx+18h]
0x18002a9d4  mov     [r8], rax
0x18002a9d7  jmp     short loc_18002A9E0
0x18002a9d9  mov     rcx, [rcx+10h]
0x18002a9dd  mov     [r8], rcx
0x18002a9e0  mov     eax, r10d
0x18002a9e3  retn
```
