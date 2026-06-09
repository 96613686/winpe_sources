# BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x18000aa18`
- end: `0x18000aa3e`
- name: `??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `36`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800401a3`
- `0x180040f3d`
- `0x180041061`
- `0x180041079`
- `0x180041091`
- `0x1800410a9`
- `0x1800410c1`
- `0x1800410d9`
- `0x1800410f1`
- `0x180041109`
- `0x180041121`
- `0x18004125b`
- `0x180041543`
- `0x1800427c7`
- `0x1800427df`
- `0x1800427f7`
- `0x180043c9c`
- `0x180043cb4`
- `0x180043dec`
- `0x180043e39`
- `0x180043e51`
- `0x1800441eb`
- `0x180044203`
- `0x180044a06`
- `0x180044a1e`
- `0x180044adc`
- `0x180044ee7`
- `0x18004520c`
- `0x1800455cf`
- `0x1800455e7`
- `0x1800455ff`
- `0x18004565f`
- `0x1800464ca`
- `0x18004655d`
- `0x180046881`
- `0x1800468ce`

## callees

- `0x18000aa18`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000aa2e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000aa2e`

## pseudocode

```c
void __fastcall BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
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
0x18000aa18  mov     [rsp+arg_0], rcx
0x18000aa1d  push    rbx
0x18000aa1e  sub     rsp, 20h
0x18000aa22  mov     rbx, rcx
0x18000aa25  cmp     dword ptr [rcx+8], 0
0x18000aa29  jz      short loc_18000AA38
0x18000aa2b  mov     rcx, [rcx]; bstrString
0x18000aa2e  call    cs:__imp_SysFreeString
0x18000aa34  and     dword ptr [rbx+8], 0
0x18000aa38  add     rsp, 20h
0x18000aa3c  pop     rbx
0x18000aa3d  retn
```
