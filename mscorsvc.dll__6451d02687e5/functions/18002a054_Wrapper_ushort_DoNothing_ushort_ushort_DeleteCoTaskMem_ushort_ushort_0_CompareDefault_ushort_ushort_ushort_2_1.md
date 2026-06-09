# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteCoTaskMem<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)

- ea: `0x18002a054`
- end: `0x18002a07f`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteCoTaskMem@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180021810`
- `0x18004418f`
- `0x18004627b`

## callees

- `0x18002a054`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a06f`
- `ole32!CoTaskMemFree` at `0x18002a06f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteCoTaskMem<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(
        __int64 a1)
{
  void *v2; // rcx

  if ( *(_DWORD *)(a1 + 8) )
  {
    v2 = *(void **)a1;
    if ( v2 )
      CoTaskMemFree(v2);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18002a054  mov     [rsp+arg_0], rcx
0x18002a059  push    rbx
0x18002a05a  sub     rsp, 20h
0x18002a05e  mov     rbx, rcx
0x18002a061  cmp     dword ptr [rcx+8], 0
0x18002a065  jz      short loc_18002A079
0x18002a067  mov     rcx, [rcx]; pv
0x18002a06a  test    rcx, rcx
0x18002a06d  jz      short loc_18002A075
0x18002a06f  call    cs:__imp_CoTaskMemFree
0x18002a075  and     dword ptr [rbx+8], 0
0x18002a079  add     rsp, 20h
0x18002a07d  pop     rbx
0x18002a07e  retn
```
