# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&CLRConfig::FreeConfigString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&CLRConfig::FreeConfigString(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2,1>(void)

- ea: `0x140007338`
- end: `0x14000735d`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1?FreeConfigString@CLRConfig@@SAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01$00@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(__int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140014979`
- `0x1400149c1`
- `0x140014f43`
- `0x140014f4f`
- `0x140014f5b`
- `0x140014f67`
- `0x140014f73`
- `0x1400155e9`
- `0x140015aea`

## callees

- `0x140007338`
- `0x14000a10c`

## pseudocode

```c
void __fastcall Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&public: static void CLRConfig::FreeConfigString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&public: static void CLRConfig::FreeConfigString(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2,1>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    operator delete(*(void **)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x140007338  mov     [rsp+arg_0], rcx
0x14000733d  push    rbx
0x14000733e  sub     rsp, 20h
0x140007342  mov     rbx, rcx
0x140007345  cmp     dword ptr [rcx+8], 0
0x140007349  jz      short loc_140007357
0x14000734b  mov     rcx, [rcx]; lpMem
0x14000734e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140007353  and     dword ptr [rbx+8], 0
0x140007357  add     rsp, 20h
0x14000735b  pop     rbx
0x14000735c  retn
```
