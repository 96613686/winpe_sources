# CILogWriteAsynch::Release(void)

- ea: `0x1800056a0`
- end: `0x180005707`
- name: `?Release@CILogWriteAsynch@@UEAAKXZ`
- size: `103`
- prototype: `__int64 __fastcall(CILogWriteAsynch *this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001300`
- `0x1800056a0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056e6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056d7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800056e6`

## pseudocode

```c
__int64 __fastcall CILogWriteAsynch::Release(CILogWriteAsynch *this)
{
  unsigned int v2; // edi

  v2 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 48LL))(*((_QWORD *)this + 1));
  if ( !v2 )
  {
    *((_QWORD *)this + 11) = &CSemExclusive::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
    *((_QWORD *)this + 4) = &CSemExclusive::`vftable';
    DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
    operator delete(this);
  }
  return v2;
}

```

## disassembly

```asm
0x1800056a0  mov     [rsp+arg_0], rbx
0x1800056a5  mov     [rsp+arg_8], rsi
0x1800056aa  push    rdi
0x1800056ab  sub     rsp, 20h
0x1800056af  mov     rbx, rcx
0x1800056b2  mov     rcx, [rcx+8]
0x1800056b6  mov     rax, [rcx]
0x1800056b9  mov     rax, [rax+30h]
0x1800056bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056c2  mov     edi, eax
0x1800056c4  test    eax, eax
0x1800056c6  jnz     short loc_1800056F5
0x1800056c8  lea     rsi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x1800056cf  mov     [rbx+58h], rsi
0x1800056d3  lea     rcx, [rbx+60h]; lpCriticalSection
0x1800056d7  call    cs:__imp_DeleteCriticalSection
0x1800056dd  nop
0x1800056de  mov     [rbx+20h], rsi
0x1800056e2  lea     rcx, [rbx+28h]; lpCriticalSection
0x1800056e6  call    cs:__imp_DeleteCriticalSection
0x1800056ec  nop
0x1800056ed  mov     rcx, rbx; Block
0x1800056f0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800056f5  mov     eax, edi
0x1800056f7  mov     rbx, [rsp+28h+arg_0]
0x1800056fc  mov     rsi, [rsp+28h+arg_8]
0x180005701  add     rsp, 20h
0x180005705  pop     rdi
0x180005706  retn
```
