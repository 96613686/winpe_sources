# CClfsLogFcbCommon::~CClfsLogFcbCommon(void)

- ea: `0x14000e634`
- end: `0x14000e671`
- name: `??1CClfsLogFcbCommon@@UEAA@XZ`
- size: `61`
- prototype: `void __fastcall(CClfsLogFcbCommon *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14001500c`
- `0x140072afc`

## callees

- `0x14000e634`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x14000e644`
- `ntoskrnl!ExDeleteResourceLite` at `0x14000e644`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e663`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e663`

## pseudocode

```c
void __fastcall CClfsLogFcbCommon::~CClfsLogFcbCommon(CClfsLogFcbCommon *this)
{
  struct _IO_WORKITEM *v2; // rcx

  ExDeleteResourceLite((PERESOURCE)((char *)this + 200));
  v2 = (struct _IO_WORKITEM *)*((_QWORD *)this + 71);
  if ( v2 )
    IoFreeWorkItem(v2);
}

```

## disassembly

```asm
0x14000e634  push    rbx
0x14000e636  sub     rsp, 20h
0x14000e63a  mov     rbx, rcx
0x14000e63d  add     rcx, 0C8h; Resource
0x14000e644  call    cs:__imp_ExDeleteResourceLite
0x14000e64b  nop     dword ptr [rax+rax+00h]
0x14000e650  mov     rcx, [rbx+238h]; IoWorkItem
0x14000e657  test    rcx, rcx
0x14000e65a  jnz     short loc_14000E663
0x14000e65c  add     rsp, 20h
0x14000e660  pop     rbx
0x14000e661  retn
0x14000e663  call    cs:__imp_IoFreeWorkItem
0x14000e66a  nop     dword ptr [rax+rax+00h]
0x14000e66f  jmp     short loc_14000E65C
```
