# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&HolderSysFreeString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)

- ea: `0x18000a9cc`
- end: `0x18000a9f2`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?HolderSysFreeString@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `49`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180021810`
- `0x180040f31`
- `0x180040fb5`
- `0x180040fc5`
- `0x180040fd5`
- `0x180040fe5`
- `0x180040ff5`
- `0x180041005`
- `0x180041028`
- `0x18004103b`
- `0x18004104e`
- `0x1800411af`
- `0x1800411bf`
- `0x1800411cf`
- `0x1800411df`
- `0x1800411ef`
- `0x1800411ff`
- `0x180041222`
- `0x180041235`
- `0x180041248`
- `0x1800413db`
- `0x1800426cb`
- `0x1800426f1`
- `0x180042704`
- `0x180042717`
- `0x180042862`
- `0x180042888`
- `0x18004289b`
- `0x1800428ae`
- `0x180043c78`
- `0x180043c90`
- `0x180043d80`
- `0x180043d98`
- `0x180043da4`
- `0x180043eed`
- `0x180043ef9`
- `0x1800449ee`
- `0x1800449fa`
- `0x180044ad0`
- `0x180044e0f`
- `0x1800451f4`
- `0x18004554b`
- `0x180045557`
- `0x180045563`
- `0x180045587`
- `0x18004632f`
- `0x18004633b`
- `0x180046724`
- `0x180046730`

## callees

- `0x18000a9cc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000a9e2`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a9e2`

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
0x18000a9cc  mov     [rsp+arg_0], rcx
0x18000a9d1  push    rbx
0x18000a9d2  sub     rsp, 20h
0x18000a9d6  mov     rbx, rcx
0x18000a9d9  cmp     dword ptr [rcx+8], 0
0x18000a9dd  jz      short loc_18000A9EC
0x18000a9df  mov     rcx, [rcx]; bstrString
0x18000a9e2  call    cs:__imp_SysFreeString
0x18000a9e8  and     dword ptr [rbx+8], 0
0x18000a9ec  add     rsp, 20h
0x18000a9f0  pop     rbx
0x18000a9f1  retn
```
