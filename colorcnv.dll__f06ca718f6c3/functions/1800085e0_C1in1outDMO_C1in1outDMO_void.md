# C1in1outDMO::~C1in1outDMO(void)

- ea: `0x1800085e0`
- end: `0x18000863f`
- name: `??1C1in1outDMO@@QEAA@XZ`
- size: `95`
- prototype: `void __fastcall(C1in1outDMO *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800084e4`

## callees

- `0x1800085e0`
- `0x180008648`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008605`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180008605`
- `msdmo!MoFreeMediaType` at `0x180008628`
- `msdmo!MoFreeMediaType` at `0x180008637`
- `msdmo!MoFreeMediaType` at `0x180008628`
- `msdmo!MoFreeMediaType` at `0x180008637`

## pseudocode

```c
void __fastcall C1in1outDMO::~C1in1outDMO(C1in1outDMO *this)
{
  *(_QWORD *)this = &C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'};
  *((_QWORD *)this + 6) = &C1in1outDMO::`vftable'{for `IMediaObject'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  if ( *((_DWORD *)this + 14) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 64));
  if ( *((_DWORD *)this + 15) )
    MoFreeMediaType((DMO_MEDIA_TYPE *)((char *)this + 152));
  CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(this);
}

```

## disassembly

```asm
0x1800085e0  push    rbx
0x1800085e2  sub     rsp, 20h
0x1800085e6  lea     rax, ??_7C1in1outDMO@@6B?$CMFTtoDMOImpl@VCMFTtoDMO@@@@@; const C1in1outDMO::`vftable'{for `CMFTtoDMOImpl<CMFTtoDMO>'}
0x1800085ed  mov     rbx, rcx
0x1800085f0  mov     [rcx], rax
0x1800085f3  lea     rax, ??_7C1in1outDMO@@6BIMediaObject@@@; const C1in1outDMO::`vftable'{for `IMediaObject'}
0x1800085fa  mov     [rcx+30h], rax
0x1800085fe  add     rcx, 108h; lpCriticalSection
0x180008605  call    cs:__imp_DeleteCriticalSection
0x18000860b  cmp     dword ptr [rbx+38h], 0
0x18000860f  jnz     short loc_180008624
0x180008611  cmp     dword ptr [rbx+3Ch], 0
0x180008615  jnz     short loc_180008630
0x180008617  mov     rcx, rbx
0x18000861a  add     rsp, 20h
0x18000861e  pop     rbx
0x18000861f  jmp     ??1?$CMFTtoDMOImpl@VCMFTtoDMO@@@@QEAA@XZ; CMFTtoDMOImpl<CMFTtoDMO>::~CMFTtoDMOImpl<CMFTtoDMO>(void)
0x180008624  lea     rcx, [rbx+40h]; pmt
0x180008628  call    cs:__imp_MoFreeMediaType
0x18000862e  jmp     short loc_180008611
0x180008630  lea     rcx, [rbx+98h]; pmt
0x180008637  call    cs:__imp_MoFreeMediaType
0x18000863d  jmp     short loc_180008617
```
