# CThreadErrorMode::~CThreadErrorMode(void)

- ea: `0x18000891c`
- end: `0x180008935`
- name: `??1CThreadErrorMode@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(ULONG *this)`
- caller_count: `8`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800090a4`
- `0x18000d9bc`
- `0x18000ea80`
- `0x180017eac`
- `0x180018130`
- `0x18001860c`
- `0x18001ce8c`
- `0x180038539`

## callees

- `0x18000891c`

## import_xrefs

- `ntdll!RtlSetThreadErrorMode` at `0x18000892a`
- `ntdll!RtlSetThreadErrorMode` at `0x18000892a`

## pseudocode

```c
void __fastcall CThreadErrorMode::~CThreadErrorMode(ULONG *this)
{
  if ( *((_BYTE *)this + 4) )
    RtlSetThreadErrorMode(*this, 0);
}

```

## disassembly

```asm
0x18000891c  sub     rsp, 28h
0x180008920  cmp     byte ptr [rcx+4], 0
0x180008924  jz      short loc_180008930
0x180008926  mov     ecx, [rcx]; NewMode
0x180008928  xor     edx, edx; OldMode
0x18000892a  call    cs:__imp_RtlSetThreadErrorMode
0x180008930  add     rsp, 28h
0x180008934  retn
```
