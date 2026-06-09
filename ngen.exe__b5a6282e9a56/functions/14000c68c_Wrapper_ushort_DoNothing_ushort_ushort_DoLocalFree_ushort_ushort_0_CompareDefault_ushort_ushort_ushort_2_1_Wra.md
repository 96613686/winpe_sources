# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DoLocalFree<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)

- ea: `0x14000c68c`
- end: `0x14000c6b2`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DoLocalFree@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ`
- size: `38`
- prototype: `HLOCAL __fastcall(__int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015601`
- `0x140015657`

## callees

- `0x14000c68c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14000c6a2`
- `KERNEL32!LocalFree` at `0x14000c6a2`

## pseudocode

```c
HLOCAL __fastcall Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DoLocalFree<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(
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
0x14000c68c  mov     [rsp+arg_0], rcx
0x14000c691  push    rbx
0x14000c692  sub     rsp, 20h
0x14000c696  mov     rbx, rcx
0x14000c699  cmp     dword ptr [rcx+8], 0
0x14000c69d  jz      short loc_14000C6AC
0x14000c69f  mov     rcx, [rcx]; hMem
0x14000c6a2  call    cs:__imp_LocalFree
0x14000c6a8  and     dword ptr [rbx+8], 0
0x14000c6ac  add     rsp, 20h
0x14000c6b0  pop     rbx
0x14000c6b1  retn
```
