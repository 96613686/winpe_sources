# PushClient::~PushClient(void)

- ea: `0x180017ba0`
- end: `0x180017c43`
- name: `??1PushClient@@UEAA@XZ`
- size: `163`
- prototype: `void __fastcall(PushClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180017cb0`

## callees

- `0x180013b84`
- `0x18001420c`
- `0x180017ba0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017be9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017c10`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017c06`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180017c06`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bb7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bc1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bcb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017bdf`

## pseudocode

```c
void __fastcall PushClient::~PushClient(PushClient *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &PushClient::`vftable';
  LocalFree(*((HLOCAL *)this + 6));
  LocalFree(*((HLOCAL *)this + 7));
  LocalFree(*((HLOCAL *)this + 8));
  LocalFree(*((HLOCAL *)this + 9));
  LocalFree(*((HLOCAL *)this + 10));
  CloseHandle(*((HANDLE *)this + 4));
  *((_QWORD *)this + 4) = -1;
  *((_QWORD *)this + 29) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  CloseHandle(*((HANDLE *)this + 13));
  PersistList::~PersistList((struct _RTL_CRITICAL_SECTION *)((char *)this + 152));
  v2 = *((_QWORD *)this + 3);
  *(_QWORD *)this = &CObject<PushClient>::`vftable';
  if ( v2 )
    CTList<PushClient>::Disconnect(v2, this);
}

```

## disassembly

```asm
0x180017ba0  push    rbx
0x180017ba2  sub     rsp, 20h
0x180017ba6  lea     rax, ??_7PushClient@@6B@; const PushClient::`vftable'
0x180017bad  mov     rbx, rcx
0x180017bb0  mov     [rcx], rax
0x180017bb3  mov     rcx, [rcx+30h]; hMem
0x180017bb7  call    cs:__imp_LocalFree
0x180017bbd  mov     rcx, [rbx+38h]; hMem
0x180017bc1  call    cs:__imp_LocalFree
0x180017bc7  mov     rcx, [rbx+40h]; hMem
0x180017bcb  call    cs:__imp_LocalFree
0x180017bd1  mov     rcx, [rbx+48h]; hMem
0x180017bd5  call    cs:__imp_LocalFree
0x180017bdb  mov     rcx, [rbx+50h]; hMem
0x180017bdf  call    cs:__imp_LocalFree
0x180017be5  mov     rcx, [rbx+20h]; hObject
0x180017be9  call    cs:__imp_CloseHandle
0x180017bef  lea     rcx, [rbx+70h]; lpCriticalSection
0x180017bf3  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180017bfb  mov     qword ptr [rbx+0E8h], 0
0x180017c06  call    cs:__imp_DeleteCriticalSection
0x180017c0c  mov     rcx, [rbx+68h]; hObject
0x180017c10  call    cs:__imp_CloseHandle
0x180017c16  lea     rcx, [rbx+98h]; this
0x180017c1d  call    ??1PersistList@@UEAA@XZ; PersistList::~PersistList(void)
0x180017c22  mov     rcx, [rbx+18h]
0x180017c26  lea     rax, ??_7?$CObject@VPushClient@@@@6B@; const CObject<PushClient>::`vftable'
0x180017c2d  mov     [rbx], rax
0x180017c30  test    rcx, rcx
0x180017c33  jz      short loc_180017C3D
0x180017c35  mov     rdx, rbx
0x180017c38  call    ?Disconnect@?$CTList@VPushClient@@@@QEAAPEAVPushClient@@PEAV2@@Z; CTList<PushClient>::Disconnect(PushClient *)
0x180017c3d  add     rsp, 20h
0x180017c41  pop     rbx
0x180017c42  retn
```
