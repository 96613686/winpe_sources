# BaseHolder<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~BaseHolder<HKEY__ *,FunctionBase<HKEY__ *,&DoNothing<HKEY__ *>(HKEY__ *),&RegKeyRelease(HKEY__ *),2>,0,&CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(void)

- ea: `0x14000ee04`
- end: `0x14000ee26`
- name: `??1?$BaseHolder@PEAUHKEY__@@V?$FunctionBase@PEAUHKEY__@@$1??$DoNothing@PEAUHKEY__@@@@YAXPEAU1@@Z$1?RegKeyRelease@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAUHKEY__@@@@YAHPEAU1@0@Z$01@@QEAA@XZ`
- size: `34`
- prototype: `LSTATUS __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015938`
- `0x140015aa2`
- `0x140015aba`
- `0x140015ad2`

## callees

- `0x14000ee04`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x14000ee16`
- `ADVAPI32!RegCloseKey` at `0x14000ee16`

## pseudocode

```c
LSTATUS __fastcall BaseHolder<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>::~BaseHolder<HKEY__ *,FunctionBase<HKEY__ *,&void DoNothing<HKEY__ *>(HKEY__ *),&void RegKeyRelease(HKEY__ *),2>,0,&int CompareDefault<HKEY__ *>(HKEY__ *,HKEY__ *),2>(
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
0x14000ee04  push    rbx
0x14000ee06  sub     rsp, 20h
0x14000ee0a  mov     rbx, rcx
0x14000ee0d  cmp     dword ptr [rcx+8], 0
0x14000ee11  jz      short loc_14000EE20
0x14000ee13  mov     rcx, [rcx]; hKey
0x14000ee16  call    cs:__imp_RegCloseKey
0x14000ee1c  and     dword ptr [rbx+8], 0
0x14000ee20  add     rsp, 20h
0x14000ee24  pop     rbx
0x14000ee25  retn
```
