# CClfsArchiveContext::~CClfsArchiveContext(void)

- ea: `0x18000dd64`
- end: `0x18000ddd0`
- name: `??1CClfsArchiveContext@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CClfsArchiveContext *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000be70`
- `0x180013c08`

## callees

- `0x18000dd64`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000dd71`
- `ntdll!RtlDeleteCriticalSection` at `0x18000dd71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddb5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000dd93`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ddb5`

## pseudocode

```c
void __fastcall CClfsArchiveContext::~CClfsArchiveContext(CClfsArchiveContext *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  char *v4; // rcx

  RtlDeleteCriticalSection((PRTL_CRITICAL_SECTION)((char *)this + 24));
  v2 = *((_QWORD *)this + 11);
  if ( (unsigned __int64)(v2 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    v3 = (void *)(v2 & 0xFFFFFFFFFFFFFFFEuLL);
    *((_QWORD *)this + 11) = v3;
    CloseHandle(v3);
    *((_QWORD *)this + 11) = -1;
  }
  v4 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 1) = -1;
  }
}

```

## disassembly

```asm
0x18000dd64  push    rbx
0x18000dd66  sub     rsp, 20h
0x18000dd6a  mov     rbx, rcx
0x18000dd6d  add     rcx, 18h; CriticalSection
0x18000dd71  call    cs:__imp_RtlDeleteCriticalSection
0x18000dd78  nop     dword ptr [rax+rax+00h]
0x18000dd7d  mov     rcx, [rbx+58h]
0x18000dd81  lea     rax, [rcx-1]
0x18000dd85  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000dd89  ja      short loc_18000DDA7
0x18000dd8b  and     rcx, 0FFFFFFFFFFFFFFFEh; hObject
0x18000dd8f  mov     [rbx+58h], rcx
0x18000dd93  call    cs:__imp_CloseHandle
0x18000dd9a  nop     dword ptr [rax+rax+00h]
0x18000dd9f  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x18000dda7  mov     rcx, [rbx+8]; hObject
0x18000ddab  lea     rax, [rcx-1]
0x18000ddaf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000ddb3  ja      short loc_18000DDC9
0x18000ddb5  call    cs:__imp_CloseHandle
0x18000ddbc  nop     dword ptr [rax+rax+00h]
0x18000ddc1  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x18000ddc9  add     rsp, 20h
0x18000ddcd  pop     rbx
0x18000ddce  retn
```
