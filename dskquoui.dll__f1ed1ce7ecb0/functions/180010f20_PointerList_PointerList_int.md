# PointerList::PointerList(int)

- ea: `0x180010f20`
- end: `0x180010fbd`
- name: `??0PointerList@@QEAA@H@Z`
- size: `157`
- prototype: `PointerList *(PointerList *__hidden this, int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000729c`
- `0x18000e918`

## callees

- `0x180006ea4`
- `0x180010f20`
- `0x18001c49c`
- `0x18001ce34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f9b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010f9b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180010f4c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180010f4c`

## pseudocode

```c
PointerList *__fastcall PointerList::PointerList(PointerList *this, int a2)
{
  HDPA v4; // rax
  char pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = 0;
  *(_QWORD *)this = &PointerList::`vftable';
  if ( !InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)((char *)this + 16), 0) )
  {
    CAllocException::CAllocException((CAllocException *)&pExceptionObject);
    throw (CAllocException *)&pExceptionObject;
  }
  v4 = DPA_CreateEx(a2, 0);
  *((_QWORD *)this + 1) = v4;
  if ( !v4 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    CAllocException::CAllocException((CAllocException *)&pExceptionObject);
    throw (CAllocException *)&pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x180010f20  mov     [rsp+arg_8], rbx
0x180010f25  mov     [rsp+arg_10], rsi
0x180010f2a  push    rdi
0x180010f2b  sub     rsp, 20h
0x180010f2f  lea     rax, ??_7PointerList@@6B@; const PointerList::`vftable'
0x180010f36  mov     qword ptr [rcx+8], 0
0x180010f3e  mov     [rcx], rax
0x180010f41  mov     esi, edx
0x180010f43  mov     rbx, rcx
0x180010f46  xor     edx, edx; dwSpinCount
0x180010f48  add     rcx, 10h; lpCriticalSection
0x180010f4c  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180010f52  test    eax, eax
0x180010f54  jz      short loc_180010F7B
0x180010f56  xor     edx, edx; hheap
0x180010f58  mov     ecx, esi; cpGrow
0x180010f5a  call    DPA_CreateEx
0x180010f5f  mov     [rbx+8], rax
0x180010f63  test    rax, rax
0x180010f66  jz      short loc_180010F97
0x180010f68  mov     rsi, [rsp+28h+arg_10]
0x180010f6d  mov     rax, rbx
0x180010f70  mov     rbx, [rsp+28h+arg_8]
0x180010f75  add     rsp, 20h
0x180010f79  pop     rdi
0x180010f7a  retn
0x180010f7b  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180010f80  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x180010f85  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x180010f8c  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180010f91  call    _CxxThrowException_0
0x180010f97  lea     rcx, [rbx+10h]; lpCriticalSection
0x180010f9b  call    cs:__imp_DeleteCriticalSection
0x180010fa1  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180010fa6  call    ??0CAllocException@@QEAA@XZ; CAllocException::CAllocException(void)
0x180010fab  lea     rdx, _TI3?AVCAllocException@@; pThrowInfo
0x180010fb2  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180010fb7  call    _CxxThrowException_0
```
