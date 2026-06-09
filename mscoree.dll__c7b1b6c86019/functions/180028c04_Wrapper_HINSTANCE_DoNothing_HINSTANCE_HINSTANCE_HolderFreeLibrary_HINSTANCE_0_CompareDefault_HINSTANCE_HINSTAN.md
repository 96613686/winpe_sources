# Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&HolderFreeLibrary(HINSTANCE__ *),0,&CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(void)

- ea: `0x180028c04`
- end: `0x180028c29`
- name: `??1?$Wrapper@PEAUHINSTANCE__@@$1??$DoNothing@PEAUHINSTANCE__@@@@YAXPEAU1@@Z$1?HolderFreeLibrary@@YAX0@Z$0A@$1??$CompareDefault@PEAUHINSTANCE__@@@@YAH00@Z$01@@QEAA@XZ`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b1f0`
- `0x180029210`
- `0x18002e680`
- `0x18002f908`
- `0x18002fa08`
- `0x180042fb2`
- `0x180043918`
- `0x180043a26`
- `0x180043a38`
- `0x180043a4a`

## callees

- `0x180028c04`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180028c16`
- `KERNEL32!FreeLibrary` at `0x180028c16`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
BOOL __fastcall Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>::~Wrapper<HINSTANCE__ *,&void DoNothing<HINSTANCE__ *>(HINSTANCE__ *),&void HolderFreeLibrary(HINSTANCE__ *),0,&int CompareDefault<HINSTANCE__ *>(HINSTANCE__ *,HINSTANCE__ *),2>(
        __int64 a1)
{
  BOOL result; // eax

  if ( *(_DWORD *)(a1 + 8) )
  {
    result = FreeLibrary(*(HMODULE *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180028c04  push    rbx
0x180028c06  sub     rsp, 20h
0x180028c0a  mov     rbx, rcx
0x180028c0d  cmp     dword ptr [rcx+8], 0
0x180028c11  jz      short loc_180028C23
0x180028c13  mov     rcx, [rcx]; hLibModule
0x180028c16  call    cs:__imp_FreeLibrary
0x180028c1c  mov     dword ptr [rbx+8], 0
0x180028c23  add     rsp, 20h
0x180028c27  pop     rbx
0x180028c28  retn
```
