# CMSDiscRecorderObj::~CMSDiscRecorderObj(void)

- ea: `0x18000e8d0`
- end: `0x18000e94f`
- name: `??1CMSDiscRecorderObj@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(CMSDiscRecorderObj *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180004970`
- `0x1800049d0`

## callees

- `0x18000e8d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18000e8e0`
- `KERNEL32!DeleteCriticalSection` at `0x18000e8ed`
- `KERNEL32!DeleteCriticalSection` at `0x18000e943`
- `KERNEL32!DeleteCriticalSection` at `0x18000e8e0`
- `KERNEL32!DeleteCriticalSection` at `0x18000e8ed`
- `KERNEL32!DeleteCriticalSection` at `0x18000e943`

## pseudocode

```c
void __fastcall CMSDiscRecorderObj::~CMSDiscRecorderObj(CMSDiscRecorderObj *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 152));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  v2 = *((_QWORD *)this + 17);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 10);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 11);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  if ( *((_BYTE *)this + 64) )
  {
    *((_BYTE *)this + 64) = 0;
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  }
}

```

## disassembly

```asm
0x18000e8d0  push    rbx
0x18000e8d2  sub     rsp, 20h
0x18000e8d6  mov     rbx, rcx
0x18000e8d9  add     rcx, 98h; lpCriticalSection
0x18000e8e0  call    cs:__imp_DeleteCriticalSection
0x18000e8e6  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18000e8ed  call    cs:__imp_DeleteCriticalSection
0x18000e8f3  mov     rcx, [rbx+88h]
0x18000e8fa  test    rcx, rcx
0x18000e8fd  jz      short loc_18000E90B
0x18000e8ff  mov     rax, [rcx]
0x18000e902  mov     rax, [rax+10h]
0x18000e906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e90b  mov     rcx, [rbx+50h]
0x18000e90f  test    rcx, rcx
0x18000e912  jz      short loc_18000E920
0x18000e914  mov     rax, [rcx]
0x18000e917  mov     rax, [rax+10h]
0x18000e91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e920  mov     rcx, [rbx+58h]
0x18000e924  test    rcx, rcx
0x18000e927  jz      short loc_18000E935
0x18000e929  mov     rax, [rcx]
0x18000e92c  mov     rax, [rax+10h]
0x18000e930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e935  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000e939  cmp     byte ptr [rcx+28h], 0
0x18000e93d  jz      short loc_18000E949
0x18000e93f  mov     byte ptr [rcx+28h], 0
0x18000e943  call    cs:__imp_DeleteCriticalSection
0x18000e949  add     rsp, 20h
0x18000e94d  pop     rbx
0x18000e94e  retn
```
