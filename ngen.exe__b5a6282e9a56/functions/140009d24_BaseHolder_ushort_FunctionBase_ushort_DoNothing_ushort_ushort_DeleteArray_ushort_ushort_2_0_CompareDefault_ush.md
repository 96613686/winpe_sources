# BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x140009d24`
- end: `0x140009d45`
- name: `??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140014961`
- `0x1400149a9`
- `0x1400149d9`
- `0x140014f8b`
- `0x140014fa3`
- `0x140014fbb`
- `0x140014fd3`
- `0x140014feb`
- `0x140015b02`

## callees

- `0x140009d24`
- `0x14000a10c`

## pseudocode

```c
void __fastcall BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    operator delete(*(void **)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140009d24  push    rbx
0x140009d26  sub     rsp, 20h
0x140009d2a  cmp     dword ptr [rcx+8], 0
0x140009d2e  mov     rbx, rcx
0x140009d31  jz      short loc_140009D3F
0x140009d33  mov     rcx, [rcx]; lpMem
0x140009d36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140009d3b  and     dword ptr [rbx+8], 0
0x140009d3f  add     rsp, 20h
0x140009d43  pop     rbx
0x140009d44  retn
```
