# RegistryConfig::~RegistryConfig(void)

- ea: `0x140008370`
- end: `0x1400083a2`
- name: `??1RegistryConfig@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(RegistryConfig *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x14000693c`
- `0x140006e18`
- `0x14000a997`
- `0x14000aaf3`

## callees

- `0x140008370`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140008384`
- `msvcrt!??3@YAXPEAX@Z` at `0x140008384`

## pseudocode

```c
void __fastcall RegistryConfig::~RegistryConfig(void **this)
{
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x140008370  push    rbx
0x140008372  sub     rsp, 20h
0x140008376  cmp     qword ptr [rcx+20h], 8
0x14000837b  mov     rbx, rcx
0x14000837e  jb      short loc_14000838A
0x140008380  mov     rcx, [rcx+8]
0x140008384  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000838a  xor     eax, eax
0x14000838c  mov     qword ptr [rbx+20h], 7
0x140008394  mov     [rbx+18h], rax
0x140008398  mov     [rbx+8], ax
0x14000839c  add     rsp, 20h
0x1400083a0  pop     rbx
0x1400083a1  retn
```
