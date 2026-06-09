# Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2,1>::~Wrapper<void *,&DoNothing<void *>(void *),&VoidCloseHandle(void *),-1,&CompareDefault<void *>(void *,void *),2,1>(void)

- ea: `0x180005ed0`
- end: `0x180005efb`
- name: `??1?$Wrapper@PEAX$1??$DoNothing@PEAX@@YAXPEAX@Z$1?VoidCloseHandle@@YAX0@Z$0?0$1??$CompareDefault@PEAX@@YAH00@Z$01$00@@QEAA@XZ`
- size: `43`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `18`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021810`
- `0x18003f8b1`
- `0x18004257f`
- `0x18004273d`
- `0x1800428d4`
- `0x180043ccc`
- `0x180043ce4`
- `0x180043e81`
- `0x180044271`
- `0x18004427d`
- `0x180045742`
- `0x1800462b7`
- `0x1800462cf`
- `0x1800462db`
- `0x1800462e7`
- `0x1800462f3`
- `0x180046575`
- `0x180046fc2`

## callees

- `0x180005ed0`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180005eeb`
- `KERNEL32!CloseHandle` at `0x180005eeb`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
BOOL __fastcall Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2,1>::~Wrapper<void *,&void DoNothing<void *>(void *),&void VoidCloseHandle(void *),-1,&int CompareDefault<void *>(void *,void *),2,1>(
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
0x180005ed0  mov     [rsp+arg_0], rcx
0x180005ed5  push    rbx
0x180005ed6  sub     rsp, 20h
0x180005eda  mov     rbx, rcx
0x180005edd  cmp     dword ptr [rcx+8], 0
0x180005ee1  jz      short loc_180005EF5
0x180005ee3  mov     rcx, [rcx]; hObject
0x180005ee6  test    rcx, rcx
0x180005ee9  jz      short loc_180005EF1
0x180005eeb  call    cs:__imp_CloseHandle
0x180005ef1  and     dword ptr [rbx+8], 0
0x180005ef5  add     rsp, 20h
0x180005ef9  pop     rbx
0x180005efa  retn
```
