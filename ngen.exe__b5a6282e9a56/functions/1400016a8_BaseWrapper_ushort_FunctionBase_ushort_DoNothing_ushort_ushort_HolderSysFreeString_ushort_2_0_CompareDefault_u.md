# BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x1400016a8`
- end: `0x1400016ce`
- name: `??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140013fb6`
- `0x140014bef`
- `0x140014c07`
- `0x140014c1f`
- `0x140014c37`
- `0x140014c4f`
- `0x140014c67`
- `0x140014c7f`
- `0x140014c97`
- `0x140014d7f`
- `0x140014ec1`
- `0x140014f2b`

## callees

- `0x1400016a8`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1400016be`
- `OLEAUT32!__imp_SysFreeString` at `0x1400016be`

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
0x1400016a8  mov     [rsp+arg_0], rcx
0x1400016ad  push    rbx
0x1400016ae  sub     rsp, 20h
0x1400016b2  mov     rbx, rcx
0x1400016b5  cmp     dword ptr [rcx+8], 0
0x1400016b9  jz      short loc_1400016C8
0x1400016bb  mov     rcx, [rcx]; bstrString
0x1400016be  call    cs:__imp_SysFreeString
0x1400016c4  and     dword ptr [rbx+8], 0
0x1400016c8  add     rsp, 20h
0x1400016cc  pop     rbx
0x1400016cd  retn
```
