# Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2>::~Wrapper<Exception *,&DoNothing<Exception *>(Exception *),&Exception__Delete(Exception *),0,&CompareDefault<Exception *>(Exception *,Exception *),2>(void)

- ea: `0x180028c5c`
- end: `0x180028c80`
- name: `??1?$Wrapper@PEAVException@@$1??$DoNothing@PEAVException@@@@YAXPEAV1@@Z$1?Exception__Delete@@YAX0@Z$0A@$1??$CompareDefault@PEAVException@@@@YAH00@Z$01@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028bec`
- `0x180042fec`
- `0x180043b6e`
- `0x180043c36`
- `0x180043e73`
- `0x180043f6c`
- `0x180044091`
- `0x1800441a9`

## callees

- `0x180028c5c`
- `0x18003b2ac`

## pseudocode

```c
void __fastcall Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>::~Wrapper<Exception *,&void DoNothing<Exception *>(Exception *),&void Exception__Delete(Exception *),0,&int CompareDefault<Exception *>(Exception *,Exception *),2>(
        __int64 a1)
{
  if ( *(_DWORD *)(a1 + 8) )
  {
    Exception::Delete(*(struct Exception **)a1);
    *(_DWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x180028c5c  push    rbx
0x180028c5e  sub     rsp, 20h
0x180028c62  mov     rbx, rcx
0x180028c65  cmp     dword ptr [rcx+8], 0
0x180028c69  jz      short loc_180028C7A
0x180028c6b  mov     rcx, [rcx]; struct Exception *
0x180028c6e  call    ?Delete@Exception@@SAXPEAV1@@Z; Exception::Delete(Exception *)
0x180028c73  mov     dword ptr [rbx+8], 0
0x180028c7a  add     rsp, 20h
0x180028c7e  pop     rbx
0x180028c7f  retn
```
