# Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)

- ea: `0x18000b1c4`
- end: `0x18000b1e9`
- name: `??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008f00`
- `0x18000a884`
- `0x18000aa50`
- `0x18000ac2c`
- `0x18000af8c`
- `0x180032c00`
- `0x180042eb6`
- `0x180042ec8`
- `0x180042f46`
- `0x180042f58`
- `0x180042f6a`
- `0x180043ada`

## callees

- `0x18000b1c4`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000b1d6`
- `ADVAPI32!RegCloseKey` at `0x18000b1d6`

## pseudocode

```c
LSTATUS __fastcall Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(
        __int64 a1)
{
  LSTATUS result; // eax

  if ( *(_DWORD *)(a1 + 8) )
  {
    result = RegCloseKey(*(HKEY *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b1c4  push    rbx
0x18000b1c6  sub     rsp, 20h
0x18000b1ca  cmp     dword ptr [rcx+8], 0
0x18000b1ce  mov     rbx, rcx
0x18000b1d1  jz      short loc_18000B1E3
0x18000b1d3  mov     rcx, [rcx]; hKey
0x18000b1d6  call    cs:__imp_RegCloseKey
0x18000b1dc  mov     dword ptr [rbx+8], 0
0x18000b1e3  add     rsp, 20h
0x18000b1e7  pop     rbx
0x18000b1e8  retn
```
