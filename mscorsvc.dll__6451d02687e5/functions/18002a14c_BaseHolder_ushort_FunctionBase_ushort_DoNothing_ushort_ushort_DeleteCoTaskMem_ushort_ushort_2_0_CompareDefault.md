# BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x18002a14c`
- end: `0x18002a173`
- name: `??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteCoTaskMem@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800441a7`
- `0x180046293`

## callees

- `0x18002a14c`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a163`
- `ole32!CoTaskMemFree` at `0x18002a163`

## pseudocode

```c
void __fastcall BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
        __int64 a1)
{
  void *v2; // rcx

  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(void **)a1;
    if ( v2 )
      CoTaskMemFree(v2);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18002a14c  push    rbx
0x18002a14e  sub     rsp, 20h
0x18002a152  mov     rbx, rcx
0x18002a155  cmp     dword ptr [rcx+8], 0
0x18002a159  jz      short loc_18002A16D
0x18002a15b  mov     rcx, [rcx]; pv
0x18002a15e  test    rcx, rcx
0x18002a161  jz      short loc_18002A169
0x18002a163  call    cs:__imp_CoTaskMemFree
0x18002a169  and     dword ptr [rbx+8], 0
0x18002a16d  add     rsp, 20h
0x18002a171  pop     rbx
0x18002a172  retn
```
