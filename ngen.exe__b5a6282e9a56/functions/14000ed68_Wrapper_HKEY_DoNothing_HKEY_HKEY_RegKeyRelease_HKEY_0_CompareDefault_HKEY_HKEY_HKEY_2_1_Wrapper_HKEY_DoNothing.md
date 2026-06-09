# Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2,1>::~Wrapper<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2,1>(void)

- ea: `0x14000ed68`
- end: `0x14000ed8e`
- name: `??1?$Wrapper@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAH00@Z$01$00@@QEAA@XZ`
- size: `38`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400159f4`
- `0x140015a00`
- `0x140015a0c`

## callees

- `0x14000ed68`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000ed7e`
- `ADVAPI32!RegCloseKey` at `0x14000ed7e`

## pseudocode

```c
LSTATUS __fastcall Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2,1>::~Wrapper<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2,1>(
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
0x14000ed68  mov     [rsp+arg_0], rcx
0x14000ed6d  push    rbx
0x14000ed6e  sub     rsp, 20h
0x14000ed72  mov     rbx, rcx
0x14000ed75  cmp     dword ptr [rcx+8], 0
0x14000ed79  jz      short loc_14000ED88
0x14000ed7b  mov     rcx, [rcx]; hKey
0x14000ed7e  call    cs:__imp_RegCloseKey
0x14000ed84  and     dword ptr [rbx+8], 0
0x14000ed88  add     rsp, 20h
0x14000ed8c  pop     rbx
0x14000ed8d  retn
```
