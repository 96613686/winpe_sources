# BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x18002a0d4`
- end: `0x18002a0ff`
- name: `??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteCoTaskMem@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004419b`
- `0x180046287`

## callees

- `0x18002a0d4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a0ef`
- `ole32!CoTaskMemFree` at `0x18002a0ef`

## pseudocode

```c
void __fastcall BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
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
0x18002a0d4  mov     [rsp+arg_0], rcx
0x18002a0d9  push    rbx
0x18002a0da  sub     rsp, 20h
0x18002a0de  mov     rbx, rcx
0x18002a0e1  cmp     dword ptr [rcx+8], 0
0x18002a0e5  jz      short loc_18002A0F9
0x18002a0e7  mov     rcx, [rcx]; pv
0x18002a0ea  test    rcx, rcx
0x18002a0ed  jz      short loc_18002A0F5
0x18002a0ef  call    cs:__imp_CoTaskMemFree
0x18002a0f5  and     dword ptr [rbx+8], 0
0x18002a0f9  add     rsp, 20h
0x18002a0fd  pop     rbx
0x18002a0fe  retn
```
