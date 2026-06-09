# BaseWrapper<void *,FunctionBase<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),2>,-1,&CompareDefault<void *>(void *,void *),2>::~BaseWrapper<void *,FunctionBase<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),2>,-1,&CompareDefault<void *>(void *,void *),2>(void)

- ea: `0x180005f24`
- end: `0x180005f4f`
- name: `??1?$BaseWrapper@PEAXV?$FunctionBase@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$01@@$0?0$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ`
- size: `43`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003f8bd`
- `0x18003faf0`
- `0x18004258b`
- `0x18004280f`
- `0x1800428fa`
- `0x180043cfc`
- `0x180043d2c`
- `0x180043f1d`
- `0x1800442b9`
- `0x1800442d1`
- `0x180045766`
- `0x180046347`
- `0x180046377`
- `0x18004638f`
- `0x1800463a7`
- `0x1800463bf`
- `0x180046581`
- `0x180046a7b`
- `0x180046a93`
- `0x180046fda`

## callees

- `0x180005f24`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005f3f`
- `KERNEL32!CloseHandle` at `0x180005f3f`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
BOOL __fastcall BaseWrapper<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),2>,-1,&int CompareDefault<void *>(void *,void *),2>::~BaseWrapper<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),2>,-1,&int CompareDefault<void *>(void *,void *),2>(
        __int64 a1)
{
  void *v2; // rcx
  BOOL result; // eax

  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(void **)a1;
    if ( v2 )
      result = CloseHandle(v2);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180005f24  mov     [rsp+arg_0], rcx
0x180005f29  push    rbx
0x180005f2a  sub     rsp, 20h
0x180005f2e  mov     rbx, rcx
0x180005f31  cmp     dword ptr [rcx+8], 0
0x180005f35  jz      short loc_180005F49
0x180005f37  mov     rcx, [rcx]; hObject
0x180005f3a  test    rcx, rcx
0x180005f3d  jz      short loc_180005F45
0x180005f3f  call    cs:__imp_CloseHandle
0x180005f45  and     dword ptr [rbx+8], 0
0x180005f49  add     rsp, 20h
0x180005f4d  pop     rbx
0x180005f4e  retn
```
