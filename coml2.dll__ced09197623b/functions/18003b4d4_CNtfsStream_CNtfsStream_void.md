# CNtfsStream::~CNtfsStream(void)

- ea: `0x18003b4d4`
- end: `0x18003b55a`
- name: `??1CNtfsStream@@UEAA@XZ`
- size: `134`
- prototype: `void __fastcall(CNtfsStream *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180041f18`
- `0x180057ce0`

## callees

- `0x18003b4d4`
- `0x18003de00`
- `0x18003ea98`
- `0x180062010`

## import_xrefs

- `ntdll!NtClose` at `0x18003b509`
- `ntdll!NtClose` at `0x18003b509`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b51b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b51b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b52a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b52a`

## pseudocode

```c
void __fastcall CNtfsStream::~CNtfsStream(CNtfsStream *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &CNtfsStream::`vftable'{for `IStream'};
  *((_QWORD *)this + 1) = &CNtfsUpdateStreamForPropStg::`vftable'{for `ILockBytes'};
  CNFFMappedStream::ShutDown((CNtfsStream *)((char *)this + 24));
  v2 = (void *)*((_QWORD *)this + 12);
  if ( v2 != (void *)-1LL )
    NtClose(v2);
  v3 = (void *)*((_QWORD *)this + 22);
  if ( v3 )
    CloseHandle(v3);
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
    CoTaskMemFree(v4);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 13) + 16LL))(*((_QWORD *)this + 13));
  *((_DWORD *)this + 28) = 1951618126;
  CNFFMappedStream::~CNFFMappedStream((CNtfsStream *)((char *)this + 24));
}

```

## disassembly

```asm
0x18003b4d4  mov     [rsp+arg_0], rbx
0x18003b4d9  push    rdi
0x18003b4da  sub     rsp, 20h
0x18003b4de  lea     rax, ??_7CNtfsStream@@6BIStream@@@; const CNtfsStream::`vftable'{for `IStream'}
0x18003b4e5  mov     rbx, rcx
0x18003b4e8  mov     [rcx], rax
0x18003b4eb  lea     rax, ??_7CNtfsUpdateStreamForPropStg@@6BILockBytes@@@; const CNtfsUpdateStreamForPropStg::`vftable'{for `ILockBytes'}
0x18003b4f2  mov     [rcx+8], rax
0x18003b4f6  add     rcx, 18h; this
0x18003b4fa  call    ?ShutDown@CNFFMappedStream@@QEAAJXZ; CNFFMappedStream::ShutDown(void)
0x18003b4ff  mov     rcx, [rbx+60h]; Handle
0x18003b503  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003b507  jz      short loc_18003B50F
0x18003b509  call    cs:__imp_NtClose
0x18003b50f  mov     rcx, [rbx+0B0h]; hObject
0x18003b516  test    rcx, rcx
0x18003b519  jz      short loc_18003B521
0x18003b51b  call    cs:__imp_CloseHandle
0x18003b521  mov     rcx, [rbx+10h]; pv
0x18003b525  test    rcx, rcx
0x18003b528  jz      short loc_18003B530
0x18003b52a  call    cs:__imp_CoTaskMemFree
0x18003b530  mov     rcx, [rbx+68h]
0x18003b534  mov     rax, [rcx]
0x18003b537  mov     rax, [rax+10h]
0x18003b53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b540  lea     rcx, [rbx+18h]; this
0x18003b544  mov     dword ptr [rbx+70h], 7453544Eh
0x18003b54b  mov     rbx, [rsp+28h+arg_0]
0x18003b550  add     rsp, 20h
0x18003b554  pop     rdi
0x18003b555  jmp     ??1CNFFMappedStream@@QEAA@XZ; CNFFMappedStream::~CNFFMappedStream(void)
```
