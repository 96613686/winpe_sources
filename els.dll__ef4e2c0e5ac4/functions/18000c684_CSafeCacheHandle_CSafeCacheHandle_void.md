# CSafeCacheHandle::~CSafeCacheHandle(void)

- ea: `0x18000c684`
- end: `0x18000c6a8`
- name: `??1CSafeCacheHandle@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(CSafeCacheHandle *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c6b0`
- `0x18000ca0c`
- `0x18000eb2c`
- `0x180022bba`

## callees

- `0x18000c684`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000c695`
- `KERNEL32!FreeLibrary` at `0x18000c695`

## pseudocode

```c
void __fastcall CSafeCacheHandle::~CSafeCacheHandle(HMODULE *this)
{
  HMODULE v2; // rcx

  v2 = *this;
  if ( v2 )
  {
    FreeLibrary(v2);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000c684  push    rbx
0x18000c686  sub     rsp, 20h
0x18000c68a  mov     rbx, rcx
0x18000c68d  mov     rcx, [rcx]; hLibModule
0x18000c690  test    rcx, rcx
0x18000c693  jz      short loc_18000C6A2
0x18000c695  call    cs:__imp_FreeLibrary
0x18000c69b  mov     qword ptr [rbx], 0
0x18000c6a2  add     rsp, 20h
0x18000c6a6  pop     rbx
0x18000c6a7  retn
```
