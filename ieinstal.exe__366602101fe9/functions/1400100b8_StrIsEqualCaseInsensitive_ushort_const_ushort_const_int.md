# StrIsEqualCaseInsensitive(ushort const *,ushort const *,int)

- ea: `0x1400100b8`
- end: `0x14001010b`
- name: `?StrIsEqualCaseInsensitive@@YA_NPEBG0H@Z`
- size: `83`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f9b4`
- `0x14000fa50`
- `0x1400105d8`

## callees

- `0x1400100b8`

## pseudocode

```c
bool __fastcall StrIsEqualCaseInsensitive(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  int v5; // r9d
  int v6; // edx
  int v7; // r10d
  int v8; // ecx

  do
  {
    v5 = *a1;
    v6 = *a2;
    v7 = v5 + 32;
    if ( (unsigned int)(v5 - 65) > 0x19 )
      v7 = *a1;
    v8 = v6 + 32;
    if ( (unsigned int)(v6 - 65) > 0x19 )
      v8 = *a2;
    if ( !--a3 )
      break;
    if ( !v7 )
      break;
    ++a1;
    ++a2;
  }
  while ( v7 == v8 );
  return v7 == v8;
}

```

## disassembly

```asm
0x1400100b8  mov     [rsp+arg_0], rbx
0x1400100bd  mov     r11, rdx
0x1400100c0  mov     rbx, rcx
0x1400100c3  movzx   r9d, word ptr [rbx]
0x1400100c7  movzx   edx, word ptr [r11]
0x1400100cb  lea     eax, [r9-41h]
0x1400100cf  cmp     eax, 19h
0x1400100d2  lea     r10d, [r9+20h]
0x1400100d6  lea     eax, [rdx-41h]
0x1400100d9  cmova   r10d, r9d
0x1400100dd  lea     ecx, [rdx+20h]
0x1400100e0  cmp     eax, 19h
0x1400100e3  cmova   ecx, edx
0x1400100e6  sub     r8d, 1
0x1400100ea  jz      short loc_1400100FE
0x1400100ec  test    r10d, r10d
0x1400100ef  jz      short loc_1400100FE
0x1400100f1  add     rbx, 2
0x1400100f5  add     r11, 2
0x1400100f9  cmp     r10d, ecx
0x1400100fc  jz      short loc_1400100C3
0x1400100fe  mov     rbx, [rsp+arg_0]
0x140010103  cmp     r10d, ecx
0x140010106  setz    al
0x140010109  retn
```
