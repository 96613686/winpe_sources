# PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET(void)

- ea: `0x14000ecc0`
- end: `0x14000ed04`
- name: `??1PCW_SILO_NEUTRAL_COUNTERSET@@AEAA@XZ`
- size: `68`
- prototype: `void __fastcall(PCW_SILO_NEUTRAL_COUNTERSET *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cf6c`
- `0x14000ed84`

## callees

- `0x14000ecc0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecd7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ecd7`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000ecf1`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x14000ecf1`

## pseudocode

```c
void __fastcall PCW_SILO_NEUTRAL_COUNTERSET::~PCW_SILO_NEUTRAL_COUNTERSET(PCW_SILO_NEUTRAL_COUNTERSET *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 17);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  v3 = *((_QWORD *)this + 12);
  if ( v3 )
    ObDereferenceSecurityDescriptor(v3, 1);
}

```

## disassembly

```asm
0x14000ecc0  push    rbx
0x14000ecc2  sub     rsp, 20h
0x14000ecc6  mov     rbx, rcx
0x14000ecc9  mov     rcx, [rcx+88h]; P
0x14000ecd0  test    rcx, rcx
0x14000ecd3  jz      short loc_14000ECE3
0x14000ecd5  xor     edx, edx; Tag
0x14000ecd7  call    cs:__imp_ExFreePoolWithTag
0x14000ecde  nop     dword ptr [rax+rax+00h]
0x14000ece3  mov     rcx, [rbx+60h]
0x14000ece7  test    rcx, rcx
0x14000ecea  jz      short loc_14000ECFD
0x14000ecec  mov     edx, 1
0x14000ecf1  call    cs:__imp_ObDereferenceSecurityDescriptor
0x14000ecf8  nop     dword ptr [rax+rax+00h]
0x14000ecfd  add     rsp, 20h
0x14000ed01  pop     rbx
0x14000ed02  retn
```
