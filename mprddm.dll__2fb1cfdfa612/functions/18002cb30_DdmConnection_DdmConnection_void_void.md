# DdmConnection::DdmConnection(void *,void *)

- ea: `0x18002cb30`
- end: `0x18002cc0f`
- name: `??0DdmConnection@@QEAA@PEAX0@Z`
- size: `223`
- prototype: `DdmConnection *__fastcall(DdmConnection *__hidden this, void *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ed5c`
- `0x1800342d0`
- `0x180041cb0`

## callees

- `0x180002aa8`
- `0x18002cb30`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18002cb62`
- `KERNEL32!InitializeCriticalSection` at `0x18002cb62`
- `KERNEL32!HeapAlloc` at `0x18002cb8f`
- `KERNEL32!HeapAlloc` at `0x18002cb8f`
- `KERNEL32!HeapFree` at `0x18002cbf3`
- `KERNEL32!HeapFree` at `0x18002cbf3`
- `ole32!CoCreateGuid` at `0x18002cbbc`
- `ole32!CoCreateGuid` at `0x18002cbbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DdmConnection *__fastcall DdmConnection::DdmConnection(DdmConnection *this, void *a2, void *a3)
{
  HRESULT Guid; // ebx
  LPVOID v7; // rax
  void *v9; // r8
  HRESULT pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  *((_DWORD *)this + 2) = 0;
  *(_QWORD *)this = &DdmConnection::`vftable';
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_QWORD *)this + 7) = a3;
  *((_QWORD *)this + 9) = a2;
  *((_DWORD *)this + 25) = 1;
  *((_DWORD *)this + 24) = 0;
  Guid = 8;
  v7 = HeapAlloc(hHeap, 8u, 8u);
  *((_QWORD *)this + 13) = v7;
  if ( !v7
    || (*((_DWORD *)this + 311) = 720,
        *((_DWORD *)this + 344) = 720,
        *((_DWORD *)this + 325) = 720,
        (Guid = CoCreateGuid((GUID *)((char *)this + 148))) != 0) )
  {
    v9 = (void *)*((_QWORD *)this + 13);
    if ( v9 )
      HeapFree(hHeap, 0, v9);
    pExceptionObject = Guid;
    throw (ulong *)&pExceptionObject;
  }
  *((_DWORD *)this + 367) = 0;
  return this;
}

```

## disassembly

```asm
0x18002cb30  mov     [rsp+arg_10], rbx
0x18002cb35  mov     [rsp+arg_18], rsi
0x18002cb3a  mov     [rsp+arg_0], rcx
0x18002cb3f  push    rdi
0x18002cb40  sub     rsp, 20h
0x18002cb44  mov     rbx, r8
0x18002cb47  mov     rdi, rdx
0x18002cb4a  mov     rsi, rcx
0x18002cb4d  mov     dword ptr [rcx+8], 0
0x18002cb54  lea     rax, ??_7DdmConnection@@6B@; const DdmConnection::`vftable'
0x18002cb5b  mov     [rcx], rax
0x18002cb5e  add     rcx, 10h; lpCriticalSection
0x18002cb62  call    cs:__imp_InitializeCriticalSection
0x18002cb68  mov     [rsi+38h], rbx
0x18002cb6c  mov     [rsi+48h], rdi
0x18002cb70  mov     dword ptr [rsi+64h], 1
0x18002cb77  mov     dword ptr [rsi+60h], 0
0x18002cb7e  mov     ebx, 8
0x18002cb83  mov     r8d, ebx; dwBytes
0x18002cb86  mov     edx, ebx; dwFlags
0x18002cb88  mov     rcx, cs:hHeap; hHeap
0x18002cb8f  call    cs:__imp_HeapAlloc
0x18002cb95  mov     [rsi+68h], rax
0x18002cb99  test    rax, rax
0x18002cb9c  jz      short loc_18002CBE1
0x18002cb9e  mov     eax, 2D0h
0x18002cba3  mov     [rsi+4DCh], eax
0x18002cba9  mov     [rsi+560h], eax
0x18002cbaf  mov     [rsi+514h], eax
0x18002cbb5  lea     rcx, [rsi+94h]; pguid
0x18002cbbc  call    cs:__imp_CoCreateGuid
0x18002cbc2  mov     ebx, eax
0x18002cbc4  test    eax, eax
0x18002cbc6  jnz     short loc_18002CBE1
0x18002cbc8  mov     [rsi+5BCh], eax
0x18002cbce  mov     rax, rsi
0x18002cbd1  mov     rbx, [rsp+28h+arg_10]
0x18002cbd6  mov     rsi, [rsp+28h+arg_18]
0x18002cbdb  add     rsp, 20h
0x18002cbdf  pop     rdi
0x18002cbe0  retn
0x18002cbe1  mov     r8, [rsi+68h]; lpMem
0x18002cbe5  test    r8, r8
0x18002cbe8  jz      short loc_18002CBF9
0x18002cbea  xor     edx, edx; dwFlags
0x18002cbec  mov     rcx, cs:hHeap; hHeap
0x18002cbf3  call    cs:__imp_HeapFree
0x18002cbf9  mov     [rsp+28h+pExceptionObject], ebx
0x18002cbfd  lea     rdx, _TI1K; pThrowInfo
0x18002cc04  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002cc09  call    _CxxThrowException_0
```
