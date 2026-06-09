# BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~BaseHolder<ushort *,FunctionBase<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),2>,0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x14000c6dc`
- end: `0x14000c6fe`
- name: `??1?$BaseHolder@PEAGV?$FunctionBase@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DoLocalFree@G@@YAX0@Z$01@@$0A@$1??$CompareDefault@PEAG@@YAHPEAG0@Z$01@@QEAA@XZ`
- size: `34`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015619`
- `0x14001566f`

## callees

- `0x14000c6dc`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000c6ee`
- `KERNEL32!LocalFree` at `0x14000c6ee`

## pseudocode

```c
HLOCAL __fastcall BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~BaseHolder<unsigned short *,FunctionBase<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),2>,0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
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
0x14000c6dc  push    rbx
0x14000c6de  sub     rsp, 20h
0x14000c6e2  mov     rbx, rcx
0x14000c6e5  cmp     dword ptr [rcx+8], 0
0x14000c6e9  jz      short loc_14000C6F8
0x14000c6eb  mov     rcx, [rcx]; hMem
0x14000c6ee  call    cs:__imp_LocalFree
0x14000c6f4  and     dword ptr [rbx+8], 0
0x14000c6f8  add     rsp, 20h
0x14000c6fc  pop     rbx
0x14000c6fd  retn
```
