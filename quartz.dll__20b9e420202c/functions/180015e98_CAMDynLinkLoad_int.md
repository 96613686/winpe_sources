# CAMDynLinkLoad(int)

- ea: `0x180015e98`
- end: `0x180015f39`
- name: `?CAMDynLinkLoad@@YAXH@Z`
- size: `161`
- prototype: `void __fastcall(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015a90`

## callees

- `0x180015e98`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180015ef0`
- `KERNEL32!DeleteCriticalSection` at `0x180015f03`
- `KERNEL32!DeleteCriticalSection` at `0x180015f16`
- `KERNEL32!DeleteCriticalSection` at `0x180015ef0`
- `KERNEL32!DeleteCriticalSection` at `0x180015f03`
- `KERNEL32!DeleteCriticalSection` at `0x180015f16`
- `KERNEL32!DeleteCriticalSection` at `0x180015f2d`
- `KERNEL32!InitializeCriticalSection` at `0x180015ea7`
- `KERNEL32!InitializeCriticalSection` at `0x180015eba`
- `KERNEL32!InitializeCriticalSection` at `0x180015ecd`
- `KERNEL32!InitializeCriticalSection` at `0x180015ea7`
- `KERNEL32!InitializeCriticalSection` at `0x180015eba`
- `KERNEL32!InitializeCriticalSection` at `0x180015ecd`
- `KERNEL32!InitializeCriticalSection` at `0x180015ee4`

## pseudocode

```c
void __fastcall CAMDynLinkLoad(int a1)
{
  if ( a1 )
  {
    InitializeCriticalSection(&CAVIDynLink::m_LoadAVILock);
    InitializeCriticalSection(&CVFWDynLink::m_LoadVFWLock);
    InitializeCriticalSection(&CACMDynLink::m_LoadACMLock);
    InitializeCriticalSection(&CURLMonDynLink::m_LoadURLMonLock);
  }
  else
  {
    DeleteCriticalSection(&CAVIDynLink::m_LoadAVILock);
    DeleteCriticalSection(&CVFWDynLink::m_LoadVFWLock);
    DeleteCriticalSection(&CACMDynLink::m_LoadACMLock);
    DeleteCriticalSection(&CURLMonDynLink::m_LoadURLMonLock);
  }
}

```

## disassembly

```asm
0x180015e98  sub     rsp, 28h
0x180015e9c  test    ecx, ecx
0x180015e9e  lea     rcx, ?m_LoadAVILock@CAVIDynLink@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015ea5  jz      short loc_180015EF0
0x180015ea7  call    cs:__imp_InitializeCriticalSection
0x180015eae  nop     dword ptr [rax+rax+00h]
0x180015eb3  lea     rcx, ?m_LoadVFWLock@CVFWDynLink@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015eba  call    cs:__imp_InitializeCriticalSection
0x180015ec1  nop     dword ptr [rax+rax+00h]
0x180015ec6  lea     rcx, ?m_LoadACMLock@CACMDynLink@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015ecd  call    cs:__imp_InitializeCriticalSection
0x180015ed4  nop     dword ptr [rax+rax+00h]
0x180015ed9  lea     rcx, ?m_LoadURLMonLock@CURLMonDynLink@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CURLMonDynLink::m_LoadURLMonLock
0x180015ee0  add     rsp, 28h
0x180015ee4  jmp     cs:__imp_InitializeCriticalSection
0x180015ef0  call    cs:__imp_DeleteCriticalSection
0x180015ef7  nop     dword ptr [rax+rax+00h]
0x180015efc  lea     rcx, ?m_LoadVFWLock@CVFWDynLink@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015f03  call    cs:__imp_DeleteCriticalSection
0x180015f0a  nop     dword ptr [rax+rax+00h]
0x180015f0f  lea     rcx, ?m_LoadACMLock@CACMDynLink@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180015f16  call    cs:__imp_DeleteCriticalSection
0x180015f1d  nop     dword ptr [rax+rax+00h]
0x180015f22  lea     rcx, ?m_LoadURLMonLock@CURLMonDynLink@@0U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION CURLMonDynLink::m_LoadURLMonLock
0x180015f29  add     rsp, 28h
0x180015f2d  jmp     cs:__imp_DeleteCriticalSection
```
