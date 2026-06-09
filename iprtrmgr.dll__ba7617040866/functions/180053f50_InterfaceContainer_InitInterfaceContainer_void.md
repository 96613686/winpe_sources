# InterfaceContainer::InitInterfaceContainer(void)

- ea: `0x180053f50`
- end: `0x180053fd0`
- name: `?InitInterfaceContainer@InterfaceContainer@@QEAAXXZ`
- size: `128`
- prototype: `void __fastcall(InterfaceContainer *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001fbc8`
- `0x1800546bc`

## callees

- `0x180053f50`

## import_xrefs

- `ntdll!RtlInitializeResource` at `0x180053f64`
- `ntdll!RtlInitializeResource` at `0x180053f64`
- `ntdll!RtlDeleteResource` at `0x180053fbb`
- `ntdll!RtlDeleteResource` at `0x180053fbb`
- `KERNEL32!InitializeCriticalSection` at `0x180053f72`
- `KERNEL32!InitializeCriticalSection` at `0x180053f7f`
- `KERNEL32!InitializeCriticalSection` at `0x180053f72`
- `KERNEL32!InitializeCriticalSection` at `0x180053f7f`

## pseudocode

```c
void __fastcall InterfaceContainer::InitInterfaceContainer(InterfaceContainer *this)
{
  if ( !dword_18008B5B8 )
  {
    RtlInitializeResource(&stru_18008B4D8);
    InitializeCriticalSection(&stru_18008B538);
    InitializeCriticalSection(&CriticalSection);
    dword_18008B588 = 1;
    dword_18008B58C = 1;
    qword_18008B5B0 = 0;
    icContainer = (HANDLE)-1LL;
    dword_18008B5B8 = 1;
  }
}

```

## disassembly

```asm
0x180053f50  sub     rsp, 28h
0x180053f54  cmp     cs:dword_18008B5B8, 0
0x180053f5b  jnz     short loc_180053FCB
0x180053f5d  lea     rcx, stru_18008B4D8; Resource
0x180053f64  call    cs:__imp_RtlInitializeResource
0x180053f6a  nop
0x180053f6b  lea     rcx, stru_18008B538; lpCriticalSection
0x180053f72  call    cs:__imp_InitializeCriticalSection
0x180053f78  lea     rcx, CriticalSection; lpCriticalSection
0x180053f7f  call    cs:__imp_InitializeCriticalSection
0x180053f85  mov     eax, 1
0x180053f8a  mov     cs:dword_18008B588, eax
0x180053f90  mov     cs:dword_18008B58C, eax
0x180053f96  mov     cs:qword_18008B5B0, 0
0x180053fa1  mov     cs:?icContainer@@3VInterfaceContainer@@A, 0FFFFFFFFFFFFFFFFh; InterfaceContainer icContainer
0x180053fac  mov     cs:dword_18008B5B8, eax
0x180053fb2  jmp     short loc_180053FCB
0x180053fb4  lea     rcx, stru_18008B4D8; Resource
0x180053fbb  call    cs:__imp_RtlDeleteResource
0x180053fc1  mov     cs:dword_18008B5B8, 0
0x180053fcb  add     rsp, 28h
0x180053fcf  retn
```
