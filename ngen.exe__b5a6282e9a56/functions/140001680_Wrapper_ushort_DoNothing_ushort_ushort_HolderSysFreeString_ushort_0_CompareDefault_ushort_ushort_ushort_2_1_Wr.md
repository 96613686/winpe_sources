# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)

- ea: `0x140001680`
- end: `0x1400016a6`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `20`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140014b43`
- `0x140014b53`
- `0x140014b63`
- `0x140014b73`
- `0x140014b83`
- `0x140014b93`
- `0x140014bb6`
- `0x140014bc9`
- `0x140014bdc`
- `0x140014cd3`
- `0x140014ce3`
- `0x140014cf3`
- `0x140014d03`
- `0x140014d13`
- `0x140014d23`
- `0x140014d46`
- `0x140014d59`
- `0x140014d6c`
- `0x140014dc7`
- `0x140014ddf`

## callees

- `0x140001680`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x140001696`
- `OLEAUT32!__imp_SysFreeString` at `0x140001696`

## pseudocode

```c
void __fastcall Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void HolderSysFreeString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(
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
0x140001680  mov     [rsp+arg_0], rcx
0x140001685  push    rbx
0x140001686  sub     rsp, 20h
0x14000168a  mov     rbx, rcx
0x14000168d  cmp     dword ptr [rcx+8], 0
0x140001691  jz      short loc_1400016A0
0x140001693  mov     rcx, [rcx]; bstrString
0x140001696  call    cs:__imp_SysFreeString
0x14000169c  and     dword ptr [rbx+8], 0
0x1400016a0  add     rsp, 20h
0x1400016a4  pop     rbx
0x1400016a5  retn
```
