# InterfaceContainer::UnInitInterfaceContainer(void)

- ea: `0x1800020d0`
- end: `0x180002129`
- name: `?UnInitInterfaceContainer@InterfaceContainer@@QEAAXXZ`
- size: `89`
- prototype: `void __fastcall(InterfaceContainer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000c054`

## callees

- `0x1800020d0`

## import_xrefs

- `ntdll!RtlDeleteResource` at `0x1800020e6`
- `ntdll!RtlDeleteResource` at `0x1800020e6`
- `ntdll!NtClose` at `0x18000210c`
- `ntdll!NtClose` at `0x18000210c`
- `KERNEL32!DeleteCriticalSection` at `0x1800020f0`
- `KERNEL32!DeleteCriticalSection` at `0x1800020fd`
- `KERNEL32!DeleteCriticalSection` at `0x1800020f0`
- `KERNEL32!DeleteCriticalSection` at `0x1800020fd`

## pseudocode

```c
void __fastcall InterfaceContainer::UnInitInterfaceContainer(InterfaceContainer *this)
{
  if ( *((_DWORD *)this + 58) )
  {
    RtlDeleteResource((PRTL_RESOURCE)((char *)this + 8));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
    if ( *(_QWORD *)this != -1 )
    {
      NtClose(*(HANDLE *)this);
      *(_QWORD *)this = -1;
    }
    *((_DWORD *)this + 58) = 0;
  }
}

```

## disassembly

```asm
0x1800020d0  push    rbx
0x1800020d2  sub     rsp, 20h
0x1800020d6  cmp     dword ptr [rcx+0E8h], 0
0x1800020dd  mov     rbx, rcx
0x1800020e0  jz      short loc_180002123
0x1800020e2  add     rcx, 8; Resource
0x1800020e6  call    cs:__imp_RtlDeleteResource
0x1800020ec  lea     rcx, [rbx+68h]; lpCriticalSection
0x1800020f0  call    cs:__imp_DeleteCriticalSection
0x1800020f6  lea     rcx, [rbx+90h]; lpCriticalSection
0x1800020fd  call    cs:__imp_DeleteCriticalSection
0x180002103  mov     rcx, [rbx]; Handle
0x180002106  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000210a  jz      short loc_180002119
0x18000210c  call    cs:__imp_NtClose
0x180002112  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180002119  mov     dword ptr [rbx+0E8h], 0
0x180002123  add     rsp, 20h
0x180002127  pop     rbx
0x180002128  retn
```
