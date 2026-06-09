# EapNs::EapCriticalSection::~EapCriticalSection(void)

- ea: `0x18000cdfc`
- end: `0x18000ce2e`
- name: `??1EapCriticalSection@EapNs@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(EapNs::EapCriticalSection *__hidden this)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b8bc`
- `0x18000bd30`
- `0x18000bef4`
- `0x18000c280`
- `0x18000c720`
- `0x18000c7d0`
- `0x18000c88c`
- `0x18000cae8`
- `0x18000e2a1`
- `0x18000e2d7`
- `0x18000e2fb`

## callees

- `0x18000cdfc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce0e`

## pseudocode

```c
void __fastcall EapNs::EapCriticalSection::~EapCriticalSection(LPCRITICAL_SECTION *this)
{
  if ( *((_DWORD *)this + 2) )
  {
    do
      LeaveCriticalSection(*this);
    while ( (*((_DWORD *)this + 2))-- != 1 );
  }
  *this = 0;
}

```

## disassembly

```asm
0x18000cdfc  push    rbx
0x18000cdfe  sub     rsp, 20h
0x18000ce02  cmp     dword ptr [rcx+8], 0
0x18000ce06  mov     rbx, rcx
0x18000ce09  jbe     short loc_18000CE20
0x18000ce0b  mov     rcx, [rbx]; lpCriticalSection
0x18000ce0e  call    cs:__imp_LeaveCriticalSection
0x18000ce15  nop     dword ptr [rax+rax+00h]
0x18000ce1a  sub     dword ptr [rbx+8], 1
0x18000ce1e  jnz     short loc_18000CE0B
0x18000ce20  mov     qword ptr [rbx], 0
0x18000ce27  add     rsp, 20h
0x18000ce2b  pop     rbx
0x18000ce2c  retn
```
