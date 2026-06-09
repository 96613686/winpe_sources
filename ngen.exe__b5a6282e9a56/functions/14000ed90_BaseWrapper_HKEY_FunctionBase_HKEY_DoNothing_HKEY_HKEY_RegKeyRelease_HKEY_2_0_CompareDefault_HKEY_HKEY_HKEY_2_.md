# BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)

- ea: `0x14000ed90`
- end: `0x14000edb6`
- name: `??1?$BaseWrapper@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `38`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001592c`
- `0x140015a96`
- `0x140015aae`
- `0x140015ac6`

## callees

- `0x14000ed90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000eda6`
- `ADVAPI32!RegCloseKey` at `0x14000eda6`

## pseudocode

```c
LSTATUS __fastcall BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~BaseWrapper<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(
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
0x14000ed90  mov     [rsp+arg_0], rcx
0x14000ed95  push    rbx
0x14000ed96  sub     rsp, 20h
0x14000ed9a  mov     rbx, rcx
0x14000ed9d  cmp     dword ptr [rcx+8], 0
0x14000eda1  jz      short loc_14000EDB0
0x14000eda3  mov     rcx, [rcx]; hKey
0x14000eda6  call    cs:__imp_RegCloseKey
0x14000edac  and     dword ptr [rbx+8], 0
0x14000edb0  add     rsp, 20h
0x14000edb4  pop     rbx
0x14000edb5  retn
```
