# BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseWrapper<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x14000c6b4`
- end: `0x14000c6da`
- name: `??1?$BaseWrapper@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DoLocalFree@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `38`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001560d`
- `0x140015663`

## callees

- `0x14000c6b4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000c6ca`
- `KERNEL32!LocalFree` at `0x14000c6ca`

## pseudocode

```c
HLOCAL __fastcall BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseWrapper<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
        __int64 a1)
{
  HLOCAL result; // rax

  if ( *(_DWORD *)(a1 + 8) )
  {
    result = LocalFree(*(HLOCAL *)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000c6b4  mov     [rsp+arg_0], rcx
0x14000c6b9  push    rbx
0x14000c6ba  sub     rsp, 20h
0x14000c6be  mov     rbx, rcx
0x14000c6c1  cmp     dword ptr [rcx+8], 0
0x14000c6c5  jz      short loc_14000C6D4
0x14000c6c7  mov     rcx, [rcx]; hMem
0x14000c6ca  call    cs:__imp_LocalFree
0x14000c6d0  and     dword ptr [rbx+8], 0
0x14000c6d4  add     rsp, 20h
0x14000c6d8  pop     rbx
0x14000c6d9  retn
```
