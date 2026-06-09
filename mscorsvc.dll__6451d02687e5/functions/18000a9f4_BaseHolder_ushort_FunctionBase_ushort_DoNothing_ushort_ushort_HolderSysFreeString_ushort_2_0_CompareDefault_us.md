# BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x18000a9f4`
- end: `0x18000aa16`
- name: `??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `36`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800401af`
- `0x180040f49`
- `0x18004106d`
- `0x180041085`
- `0x18004109d`
- `0x1800410b5`
- `0x1800410cd`
- `0x1800410e5`
- `0x1800410fd`
- `0x180041115`
- `0x18004112d`
- `0x180041267`
- `0x18004154f`
- `0x1800427d3`
- `0x1800427eb`
- `0x180042803`
- `0x180043ca8`
- `0x180043cc0`
- `0x180043df8`
- `0x180043e45`
- `0x180043e5d`
- `0x1800441f7`
- `0x18004420f`
- `0x180044a12`
- `0x180044a2a`
- `0x180044ae8`
- `0x180044ef3`
- `0x180045218`
- `0x1800455db`
- `0x1800455f3`
- `0x18004560b`
- `0x18004566b`
- `0x1800464d6`
- `0x180046569`
- `0x18004688d`
- `0x1800468da`

## callees

- `0x18000a9f4`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000aa06`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa06`

## pseudocode

```c
void __fastcall BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    SysFreeString(*(BSTR *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000a9f4  push    rbx
0x18000a9f6  sub     rsp, 20h
0x18000a9fa  mov     rbx, rcx
0x18000a9fd  cmp     dword ptr [rcx+8], 0
0x18000aa01  jz      short loc_18000AA10
0x18000aa03  mov     rcx, [rcx]; bstrString
0x18000aa06  call    cs:__imp_SysFreeString
0x18000aa0c  and     dword ptr [rbx+8], 0
0x18000aa10  add     rsp, 20h
0x18000aa14  pop     rbx
0x18000aa15  retn
```
