# SslpValidateProvHandle

- ea: `0x1800068e0`
- end: `0x1800068fe`
- name: `SslpValidateProvHandle`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `27`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x1800058e0`
- `0x180005ec0`
- `0x180006070`
- `0x180006720`
- `0x18000dea0`
- `0x18000e320`
- `0x1800105e0`
- `0x1800113a0`
- `0x180011a40`
- `0x180011f10`
- `0x180012b30`
- `0x1800133f0`
- `0x180013740`
- `0x18001e480`
- `0x18001e5c0`
- `0x18001e8c0`
- `0x18001eae0`
- `0x18001eb90`
- `0x18001ec10`
- `0x18001ece0`
- `0x18001edb0`
- `0x18001f180`
- `0x18001f230`
- `0x18001f2c0`
- `0x18001f3b0`
- `0x18001f4e0`

## callees

- `0x1800068e0`

## pseudocode

```c
_DWORD *__fastcall SslpValidateProvHandle(_DWORD *a1)
{
  _DWORD *result; // rax

  if ( !a1 || *a1 < 0x310u )
    return 0;
  result = 0;
  if ( a1[1] == 1936944177 )
    return a1;
  return result;
}

```

## disassembly

```asm
0x1800068e0  test    rcx, rcx
0x1800068e3  jz      short loc_1800068FB
0x1800068e5  cmp     dword ptr [rcx], 310h
0x1800068eb  jb      short loc_1800068FB
0x1800068ed  xor     eax, eax
0x1800068ef  cmp     dword ptr [rcx+4], 73736C31h
0x1800068f6  cmovz   rax, rcx
0x1800068fa  retn
0x1800068fb  xor     eax, eax
0x1800068fd  retn
```
