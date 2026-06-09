# CCreatePacketComplete::~CCreatePacketComplete(void)

- ea: `0x14000cde4`
- end: `0x14000ce03`
- name: `??1CCreatePacketComplete@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(CCreatePacketComplete *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000ce0c`

## callees

- `0x14000cde4`

## import_xrefs

- `ntoskrnl!IoFreeWorkItem` at `0x14000cdf1`
- `ntoskrnl!IoFreeWorkItem` at `0x14000cdf1`

## pseudocode

```c
void __fastcall CCreatePacketComplete::~CCreatePacketComplete(CCreatePacketComplete *this)
{
  struct _IO_WORKITEM *v1; // rcx

  v1 = (struct _IO_WORKITEM *)*((_QWORD *)this + 2);
  if ( v1 )
    IoFreeWorkItem(v1);
}

```

## disassembly

```asm
0x14000cde4  sub     rsp, 28h
0x14000cde8  mov     rcx, [rcx+10h]; IoWorkItem
0x14000cdec  test    rcx, rcx
0x14000cdef  jz      short loc_14000CDFD
0x14000cdf1  call    cs:__imp_IoFreeWorkItem
0x14000cdf8  nop     dword ptr [rax+rax+00h]
0x14000cdfd  add     rsp, 28h
0x14000ce01  retn
```
