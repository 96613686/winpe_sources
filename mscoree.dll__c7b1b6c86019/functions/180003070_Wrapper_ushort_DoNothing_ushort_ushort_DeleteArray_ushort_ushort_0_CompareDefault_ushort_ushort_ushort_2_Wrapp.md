# Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)

- ea: `0x180003070`
- end: `0x180003094`
- name: `??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ`
- size: `36`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `34`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180002a90`
- `0x180003890`
- `0x180004660`
- `0x180008484`
- `0x180008f00`
- `0x180009028`
- `0x1800099b0`
- `0x18000a6a4`
- `0x18000af8c`
- `0x18000b3c4`
- `0x18000b5e8`
- `0x180028d98`
- `0x18002aec8`
- `0x18002d134`
- `0x180030578`
- `0x180030798`
- `0x18003145c`
- `0x1800325d4`
- `0x180032a80`
- `0x180032c00`
- `0x180033304`
- `0x180033604`
- `0x18003e334`
- `0x180042c80`
- `0x180042ca0`
- `0x180042cc0`
- `0x180042d40`
- `0x180042dc0`
- `0x180042e40`
- `0x180042eec`
- `0x180043906`
- `0x1800439de`
- `0x180043ab6`
- `0x180043ac8`

## callees

- `0x180003070`
- `0x180003840`

## pseudocode

```c
void __fastcall Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(
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
0x180003070  push    rbx
0x180003072  sub     rsp, 20h
0x180003076  cmp     dword ptr [rcx+8], 0
0x18000307a  mov     rbx, rcx
0x18000307d  jz      short loc_18000308E
0x18000307f  mov     rcx, [rcx]; void *
0x180003082  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003087  mov     dword ptr [rbx+8], 0
0x18000308e  add     rsp, 20h
0x180003092  pop     rbx
0x180003093  retn
```
