# CWMDeColorConvDMO::UnregisterThreads(void)

- ea: `0x18000e4c0`
- end: `0x18000e50e`
- name: `?UnregisterThreads@CWMDeColorConvDMO@@UEAAJXZ`
- size: `78`
- prototype: `__int64 __fastcall(CWMDeColorConvDMO *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000e4c0`
- `0x180014a18`

## pseudocode

```c
__int64 __fastcall CWMDeColorConvDMO::UnregisterThreads(CWMDeColorConvDMO *this)
{
  CWMDeColorConvDMO *v1; // r9
  void *v2; // rcx
  unsigned int v3; // r8d
  unsigned int v4; // r10d
  void *v5; // rcx
  unsigned int v6; // r10d

  v1 = this;
  *((_DWORD *)this + 183) = 0;
  v2 = (void *)*((_QWORD *)this + 4);
  v3 = 0;
  if ( v2 && (unsigned int)setMMCSSRegisterCC(v2, 0) )
    v3 = v4;
  v5 = (void *)*((_QWORD *)v1 + 6);
  if ( v5 && (unsigned int)setMMCSSRegisterCC(v5, 0) )
    return v6;
  return v3;
}

```

## disassembly

```asm
0x18000e4c0  sub     rsp, 28h
0x18000e4c4  mov     r9, rcx
0x18000e4c7  mov     dword ptr [rcx+2DCh], 0
0x18000e4d1  mov     rcx, [rcx+20h]; void *
0x18000e4d5  xor     r8d, r8d
0x18000e4d8  mov     r10d, 80004005h
0x18000e4de  test    rcx, rcx
0x18000e4e1  jz      short loc_18000E4F0
0x18000e4e3  xor     edx, edx; int
0x18000e4e5  call    ?setMMCSSRegisterCC@@YAJPEAXH@Z; setMMCSSRegisterCC(void *,int)
0x18000e4ea  test    eax, eax
0x18000e4ec  cmovnz  r8d, r10d
0x18000e4f0  mov     rcx, [r9+30h]; void *
0x18000e4f4  test    rcx, rcx
0x18000e4f7  jz      short loc_18000E506
0x18000e4f9  xor     edx, edx; int
0x18000e4fb  call    ?setMMCSSRegisterCC@@YAJPEAXH@Z; setMMCSSRegisterCC(void *,int)
0x18000e500  test    eax, eax
0x18000e502  cmovnz  r8d, r10d
0x18000e506  mov     eax, r8d
0x18000e509  add     rsp, 28h
0x18000e50d  retn
```
