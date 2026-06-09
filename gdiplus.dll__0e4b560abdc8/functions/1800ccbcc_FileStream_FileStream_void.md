# FileStream::~FileStream(void)

- ea: `0x1800ccbcc`
- end: `0x1800ccc27`
- name: `??1FileStream@@UEAA@XZ`
- size: `91`
- prototype: `void __fastcall(FileStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800ccb90`

## callees

- `0x1800ccbcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccc14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ccc14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccbe9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ccbe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ccbfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ccbfe`

## pseudocode

```c
void __fastcall FileStream::~FileStream(FileStream *this)
{
  void *v2; // rcx
  void *v3; // rcx

  *(_QWORD *)this = &FileStream::`vftable';
  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 != (void *)-1LL )
    CloseHandle(v2);
  v3 = (void *)*((_QWORD *)this + 7);
  if ( v3 )
    CoTaskMemFree(v3);
  if ( *((_DWORD *)this + 12) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800ccbcc  push    rbx
0x1800ccbce  sub     rsp, 20h
0x1800ccbd2  lea     rax, ??_7FileStream@@6B@; const FileStream::`vftable'
0x1800ccbd9  mov     rbx, rcx
0x1800ccbdc  mov     [rcx], rax
0x1800ccbdf  mov     rcx, [rcx+48h]; hObject
0x1800ccbe3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ccbe7  jz      short loc_1800CCBF5
0x1800ccbe9  call    cs:__imp_CloseHandle
0x1800ccbf0  nop     dword ptr [rax+rax+00h]
0x1800ccbf5  mov     rcx, [rbx+38h]; pv
0x1800ccbf9  test    rcx, rcx
0x1800ccbfc  jz      short loc_1800CCC0A
0x1800ccbfe  call    cs:__imp_CoTaskMemFree
0x1800ccc05  nop     dword ptr [rax+rax+00h]
0x1800ccc0a  cmp     dword ptr [rbx+30h], 0
0x1800ccc0e  jz      short loc_1800CCC20
0x1800ccc10  lea     rcx, [rbx+8]; lpCriticalSection
0x1800ccc14  call    cs:__imp_DeleteCriticalSection
0x1800ccc1b  nop     dword ptr [rax+rax+00h]
0x1800ccc20  add     rsp, 20h
0x1800ccc24  pop     rbx
0x1800ccc25  retn
```
