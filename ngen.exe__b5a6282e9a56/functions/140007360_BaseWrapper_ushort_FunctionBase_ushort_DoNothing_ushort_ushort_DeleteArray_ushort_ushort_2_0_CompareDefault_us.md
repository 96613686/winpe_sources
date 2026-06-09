# BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x140007360`
- end: `0x140007385`
- name: `??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140014955`
- `0x14001499d`
- `0x1400149cd`
- `0x140014f7f`
- `0x140014f97`
- `0x140014faf`
- `0x140014fc7`
- `0x140014fdf`
- `0x140015af6`

## callees

- `0x140007360`
- `0x14000a10c`

## pseudocode

```c
void __fastcall BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
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
0x140007360  mov     [rsp+arg_0], rcx
0x140007365  push    rbx
0x140007366  sub     rsp, 20h
0x14000736a  mov     rbx, rcx
0x14000736d  cmp     dword ptr [rcx+8], 0
0x140007371  jz      short loc_14000737F
0x140007373  mov     rcx, [rcx]; lpMem
0x140007376  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000737b  and     dword ptr [rbx+8], 0
0x14000737f  add     rsp, 20h
0x140007383  pop     rbx
0x140007384  retn
```
