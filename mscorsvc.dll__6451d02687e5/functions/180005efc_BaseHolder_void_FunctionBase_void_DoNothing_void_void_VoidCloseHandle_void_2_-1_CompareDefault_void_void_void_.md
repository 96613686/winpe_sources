# BaseHolder<void *,FunctionBase<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),2>,-1,&CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),2>,-1,&CompareDefault<void *>(void *,void *),2>(void)

- ea: `0x180005efc`
- end: `0x180005f23`
- name: `??1?$BaseHolder@PEAXV?$FunctionBase@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$01@@$0?0$1??$CompareDefault@PEAX@@YAHPEAX0@Z$01@@QEAA@XZ`
- size: `39`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003f8c9`
- `0x18003fafc`
- `0x180042597`
- `0x18004281b`
- `0x180042906`
- `0x180043d08`
- `0x180043d38`
- `0x180043f29`
- `0x1800442c5`
- `0x1800442dd`
- `0x180045772`
- `0x180046353`
- `0x180046383`
- `0x18004639b`
- `0x1800463b3`
- `0x1800463cb`
- `0x18004658d`
- `0x180046a87`
- `0x180046a9f`
- `0x180046fe6`

## callees

- `0x180005efc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005f13`
- `KERNEL32!CloseHandle` at `0x180005f13`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
BOOL __fastcall BaseHolder<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),2>,-1,&int CompareDefault<void *>(void *,void *),2>::~BaseHolder<void *,FunctionBase<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),2>,-1,&int CompareDefault<void *>(void *,void *),2>(
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
0x180005efc  push    rbx
0x180005efe  sub     rsp, 20h
0x180005f02  mov     rbx, rcx
0x180005f05  cmp     dword ptr [rcx+8], 0
0x180005f09  jz      short loc_180005F1D
0x180005f0b  mov     rcx, [rcx]; hObject
0x180005f0e  test    rcx, rcx
0x180005f11  jz      short loc_180005F19
0x180005f13  call    cs:__imp_CloseHandle
0x180005f19  and     dword ptr [rbx+8], 0
0x180005f1d  add     rsp, 20h
0x180005f21  pop     rbx
0x180005f22  retn
```
