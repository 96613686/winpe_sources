# CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(void)

- ea: `0x1400052b0`
- end: `0x1400052f4`
- name: `?_CoInternetIsFeatureEnabledInternal@CFeatureControlKey@@QEAAJXZ`
- size: `68`
- prototype: `__int64 __fastcall(CFeatureControlKey *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140003260`
- `0x1400040c8`

## callees

- `0x1400052b0`

## import_xrefs

- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1400052c1`
- `iertutil!__imp_CoInternetIsFeatureEnabledInternal` at `0x1400052c1`

## pseudocode

```c
__int64 __fastcall CFeatureControlKey::_CoInternetIsFeatureEnabledInternal(CFeatureControlKey *this)
{
  int IsFeatureEnabledInternal; // eax
  unsigned int v3; // r8d

  if ( !*(_QWORD *)this )
    return *((_DWORD *)this + 2) == 0;
  IsFeatureEnabledInternal = CoInternetIsFeatureEnabledInternal();
  v3 = IsFeatureEnabledInternal;
  if ( IsFeatureEnabledInternal >= 0 )
  {
    *((_DWORD *)this + 2) = IsFeatureEnabledInternal == 0;
    *(_QWORD *)this = 0;
    return *((_DWORD *)this + 2) == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x1400052b0  push    rbx
0x1400052b2  sub     rsp, 20h
0x1400052b6  mov     rbx, rcx
0x1400052b9  mov     rcx, [rcx]
0x1400052bc  test    rcx, rcx
0x1400052bf  jz      short loc_1400052DF
0x1400052c1  call    cs:__imp_CoInternetIsFeatureEnabledInternal
0x1400052c7  mov     r8d, eax
0x1400052ca  test    eax, eax
0x1400052cc  js      short loc_1400052EB
0x1400052ce  xor     edx, edx
0x1400052d0  test    eax, eax
0x1400052d2  setz    dl
0x1400052d5  mov     [rbx+8], edx
0x1400052d8  mov     qword ptr [rbx], 0
0x1400052df  mov     eax, [rbx+8]
0x1400052e2  xor     r8d, r8d
0x1400052e5  test    eax, eax
0x1400052e7  setz    r8b
0x1400052eb  mov     eax, r8d
0x1400052ee  add     rsp, 20h
0x1400052f2  pop     rbx
0x1400052f3  retn
```
