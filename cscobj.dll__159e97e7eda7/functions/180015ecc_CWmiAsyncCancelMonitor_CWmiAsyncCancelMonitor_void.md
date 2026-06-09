# CWmiAsyncCancelMonitor::~CWmiAsyncCancelMonitor(void)

- ea: `0x180015ecc`
- end: `0x180015f37`
- name: `??1CWmiAsyncCancelMonitor@@UEAA@XZ`
- size: `107`
- prototype: `void __fastcall(CWmiAsyncCancelMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180015f80`

## callees

- `0x1800084e0`
- `0x180015ecc`
- `0x1800164e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f1c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015f1c`

## pseudocode

```c
void __fastcall CWmiAsyncCancelMonitor::~CWmiAsyncCancelMonitor(CWmiAsyncCancelMonitor *this, void *a2)
{
  bool v2; // zf
  __int64 i; // rdi

  v2 = *((_QWORD *)this + 2) == 0;
  *(_QWORD *)this = &CWmiAsyncCancelMonitor::`vftable';
  if ( !v2 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)this + 6); i = (unsigned int)(i + 1) )
      CWmiAsyncCancelMonitor::_DestroyEntry(
        (CWmiAsyncCancelMonitor *)(3 * i),
        (struct CWmiAsyncCancelMonitor::ENTRY *)(*((_QWORD *)this + 2) + 24 * i));
    CscUtil_HeapFree(*((void **)this + 2), a2);
  }
  if ( *((_DWORD *)this + 18) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *(_QWORD *)this = &CRefCounted::`vftable';
}

```

## disassembly

```asm
0x180015ecc  mov     [rsp+arg_0], rbx
0x180015ed1  push    rdi
0x180015ed2  sub     rsp, 20h
0x180015ed6  cmp     qword ptr [rcx+10h], 0
0x180015edb  lea     rax, ??_7CWmiAsyncCancelMonitor@@6B@; const CWmiAsyncCancelMonitor::`vftable'
0x180015ee2  mov     [rcx], rax
0x180015ee5  mov     rbx, rcx
0x180015ee8  jz      short loc_180015F12
0x180015eea  xor     edi, edi
0x180015eec  cmp     [rcx+18h], edi
0x180015eef  jbe     short loc_180015F09
0x180015ef1  mov     rax, [rbx+10h]
0x180015ef5  lea     rcx, [rdi+rdi*2]; this
0x180015ef9  lea     rdx, [rax+rcx*8]; struct CWmiAsyncCancelMonitor::ENTRY *
0x180015efd  call    ?_DestroyEntry@CWmiAsyncCancelMonitor@@AEAAXPEAUENTRY@1@@Z; CWmiAsyncCancelMonitor::_DestroyEntry(CWmiAsyncCancelMonitor::ENTRY *)
0x180015f02  inc     edi
0x180015f04  cmp     edi, [rbx+18h]
0x180015f07  jb      short loc_180015EF1
0x180015f09  mov     rcx, [rbx+10h]; lpMem
0x180015f0d  call    ?CscUtil_HeapFree@@YAJPEAX0@Z; CscUtil_HeapFree(void *,void *)
0x180015f12  cmp     dword ptr [rbx+48h], 0
0x180015f16  jz      short loc_180015F22
0x180015f18  lea     rcx, [rbx+20h]; lpCriticalSection
0x180015f1c  call    cs:__imp_DeleteCriticalSection
0x180015f22  lea     rax, ??_7CRefCounted@@6B@; const CRefCounted::`vftable'
0x180015f29  mov     [rbx], rax
0x180015f2c  mov     rbx, [rsp+28h+arg_0]
0x180015f31  add     rsp, 20h
0x180015f35  pop     rdi
0x180015f36  retn
```
