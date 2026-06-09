# CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::`vector deleting destructor'(uint)

- ea: `0x180013100`
- end: `0x180013130`
- name: `??_E?$CEventSource@VCComObjectObserver@@VCVoid@@V2@V2@V2@@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005590`
- `0x180013100`

## import_xrefs

- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001311c`
- `MFC42u!__imp_??3@YAXPEAX@Z` at `0x18001311c`

## pseudocode

```c
struct CEventSourceBase *__fastcall CEventSource<CComObjectObserver,CVoid,CVoid,CVoid,CVoid>::`vector deleting destructor'(
        struct CEventSourceBase *a1,
        char a2)
{
  _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180013100  mov     [rsp+arg_0], rbx
0x180013105  push    rdi
0x180013106  sub     rsp, 20h
0x18001310a  mov     ebx, edx
0x18001310c  mov     rdi, rcx
0x18001310f  call    ??1?$_CEventSource@VCComObjectObserver@@@@UEAA@XZ; _CEventSource<CComObjectObserver>::~_CEventSource<CComObjectObserver>(void)
0x180013114  test    bl, 1
0x180013117  jz      short loc_180013122
0x180013119  mov     rcx, rdi
0x18001311c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013122  mov     rbx, [rsp+28h+arg_0]
0x180013127  mov     rax, rdi
0x18001312a  add     rsp, 20h
0x18001312e  pop     rdi
0x18001312f  retn
```
