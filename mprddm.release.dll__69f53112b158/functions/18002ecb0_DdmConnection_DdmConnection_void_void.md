# DdmConnection::DdmConnection(void *,void *)

- ea: `0x18002ecb0`
- end: `0x18002eda2`
- name: `??0DdmConnection@@QEAA@PEAX0@Z`
- size: `242`
- prototype: `DdmConnection *__fastcall(DdmConnection *__hidden this, void *, void *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f254`
- `0x180036080`
- `0x180043490`

## callees

- `0x180002ae8`
- `0x18002ecb0`

## import_xrefs

- `KERNEL32!InitializeCriticalSection` at `0x18002ecdf`
- `KERNEL32!InitializeCriticalSection` at `0x18002ecdf`
- `KERNEL32!HeapAlloc` at `0x18002ed0f`
- `KERNEL32!HeapAlloc` at `0x18002ed0f`
- `KERNEL32!HeapFree` at `0x18002ed80`
- `KERNEL32!HeapFree` at `0x18002ed80`
- `ole32!CoCreateGuid` at `0x18002ed42`
- `ole32!CoCreateGuid` at `0x18002ed42`

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
0x18002ecb0  mov     [rsp+arg_10], rbx
0x18002ecb5  mov     [rsp+arg_18], rsi
0x18002ecba  mov     [rsp+arg_0], rcx
0x18002ecbf  push    rdi
0x18002ecc0  sub     rsp, 20h
0x18002ecc4  mov     rbx, r8
0x18002ecc7  mov     rdi, rdx
0x18002ecca  mov     rsi, rcx
0x18002eccd  and     dword ptr [rcx+8], 0
0x18002ecd1  lea     rax, ??_7DdmConnection@@6B@; const DdmConnection::`vftable'
0x18002ecd8  mov     [rcx], rax
0x18002ecdb  add     rcx, 10h; lpCriticalSection
0x18002ecdf  call    cs:__imp_InitializeCriticalSection
0x18002ece6  nop     dword ptr [rax+rax+00h]
0x18002eceb  mov     [rsi+38h], rbx
0x18002ecef  mov     [rsi+48h], rdi
0x18002ecf3  mov     dword ptr [rsi+64h], 1
0x18002ecfa  and     dword ptr [rsi+60h], 0
0x18002ecfe  mov     ebx, 8
0x18002ed03  mov     r8d, ebx; dwBytes
0x18002ed06  mov     edx, ebx; dwFlags
0x18002ed08  mov     rcx, cs:hHeap; hHeap
0x18002ed0f  call    cs:__imp_HeapAlloc
0x18002ed16  nop     dword ptr [rax+rax+00h]
0x18002ed1b  mov     [rsi+68h], rax
0x18002ed1f  test    rax, rax
0x18002ed22  jz      short loc_18002ED6E
0x18002ed24  mov     eax, 2D0h
0x18002ed29  mov     [rsi+4DCh], eax
0x18002ed2f  mov     [rsi+560h], eax
0x18002ed35  mov     [rsi+514h], eax
0x18002ed3b  lea     rcx, [rsi+94h]; pguid
0x18002ed42  call    cs:__imp_CoCreateGuid
0x18002ed49  nop     dword ptr [rax+rax+00h]
0x18002ed4e  mov     ebx, eax
0x18002ed50  test    eax, eax
0x18002ed52  jnz     short loc_18002ED6E
0x18002ed54  and     [rsi+5BCh], eax
0x18002ed5a  mov     rax, rsi
0x18002ed5d  mov     rbx, [rsp+28h+arg_10]
0x18002ed62  mov     rsi, [rsp+28h+arg_18]
0x18002ed67  add     rsp, 20h
0x18002ed6b  pop     rdi
0x18002ed6c  retn
0x18002ed6e  mov     r8, [rsi+68h]; lpMem
0x18002ed72  test    r8, r8
0x18002ed75  jz      short loc_18002ED8C
0x18002ed77  xor     edx, edx; dwFlags
0x18002ed79  mov     rcx, cs:hHeap; hHeap
0x18002ed80  call    cs:__imp_HeapFree
0x18002ed87  nop     dword ptr [rax+rax+00h]
0x18002ed8c  mov     [rsp+28h+pExceptionObject], ebx
0x18002ed90  lea     rdx, _TI1K; pThrowInfo
0x18002ed97  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18002ed9c  call    _CxxThrowException_0
```
