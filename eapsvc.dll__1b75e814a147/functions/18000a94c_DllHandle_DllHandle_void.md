# DllHandle::~DllHandle(void)

- ea: `0x18000a94c`
- end: `0x18000a970`
- name: `??1DllHandle@@QEAA@XZ`
- size: `36`
- prototype: `void __fastcall(HMODULE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015312`
- `0x180015328`

## callees

- `0x18000a94c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a95d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a95d`

## pseudocode

```c
void __fastcall DllHandle::~DllHandle(HMODULE *this)
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
0x18000a94c  push    rbx
0x18000a94e  sub     rsp, 20h
0x18000a952  mov     rbx, rcx
0x18000a955  mov     rcx, [rcx]; hLibModule
0x18000a958  test    rcx, rcx
0x18000a95b  jz      short loc_18000A96A
0x18000a95d  call    cs:__imp_FreeLibrary
0x18000a963  mov     qword ptr [rbx], 0
0x18000a96a  add     rsp, 20h
0x18000a96e  pop     rbx
0x18000a96f  retn
```
