# BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x140009da0`
- end: `0x140009dc2`
- name: `??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `34`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013fc2`
- `0x140014bfb`
- `0x140014c13`
- `0x140014c2b`
- `0x140014c43`
- `0x140014c5b`
- `0x140014c73`
- `0x140014c8b`
- `0x140014ca3`
- `0x140014d8b`
- `0x140014ecd`
- `0x140014f37`

## callees

- `0x140009da0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140009db2`
- `OLEAUT32!__imp_SysFreeString` at `0x140009db2`

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
0x140009da0  push    rbx
0x140009da2  sub     rsp, 20h
0x140009da6  mov     rbx, rcx
0x140009da9  cmp     dword ptr [rcx+8], 0
0x140009dad  jz      short loc_140009DBC
0x140009daf  mov     rcx, [rcx]; bstrString
0x140009db2  call    cs:__imp_SysFreeString
0x140009db8  and     dword ptr [rbx+8], 0
0x140009dbc  add     rsp, 20h
0x140009dc0  pop     rbx
0x140009dc1  retn
```
