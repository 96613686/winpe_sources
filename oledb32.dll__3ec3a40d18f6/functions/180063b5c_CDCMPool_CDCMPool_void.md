# CDCMPool::~CDCMPool(void)

- ea: `0x180063b5c`
- end: `0x180063be1`
- name: `??1CDCMPool@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(CDCMPool *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005dac0`

## callees

- `0x180063b5c`
- `0x180087010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180063bbe`
- `KERNEL32!DeleteCriticalSection` at `0x180063bcb`
- `KERNEL32!DeleteCriticalSection` at `0x180063bbe`
- `KERNEL32!DeleteCriticalSection` at `0x180063bcb`
- `KERNEL32!DeleteCriticalSection` at `0x180063bda`

## pseudocode

```c
void __fastcall CDCMPool::~CDCMPool(CDCMPool *this)
{
  __int64 v2; // rcx

  _InterlockedIncrement(&dword_1800BEF1C);
  v2 = *((int *)this + 63);
  if ( (_DWORD)v2 && bidID != -1 )
    ((void (__fastcall *)(__int64, wchar_t *, __int64, __int64, _QWORD))off_1800BC118)(
      bidID,
      off_1800C96C8[0],
      7,
      v2,
      0);
  *((_DWORD *)this + 63) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 5);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 4);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
}

```

## disassembly

```asm
0x180063b5c  push    rbx
0x180063b5e  sub     rsp, 30h
0x180063b62  mov     rbx, rcx
0x180063b65  lock inc cs:dword_1800BEF1C
0x180063b6c  movsxd  rcx, dword ptr [rcx+0FCh]
0x180063b73  test    ecx, ecx
0x180063b75  jz      short loc_180063BAD
0x180063b77  cmp     cs:_bidID, 0FFFFFFFFFFFFFFFFh
0x180063b7f  jz      short loc_180063BAD
0x180063b81  mov     rax, cs:off_1800BC118
0x180063b88  mov     r9, rcx
0x180063b8b  mov     [rsp+38h+var_18], 0
0x180063b94  mov     r8d, 7
0x180063b9a  mov     rdx, cs:off_1800C96C8; "<CDCMPool::~CDCMPool|ID|OBJ|OLEDB> "
0x180063ba1  mov     rcx, cs:_bidID
0x180063ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063bad  mov     dword ptr [rbx+0FCh], 0
0x180063bb7  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x180063bbe  call    cs:__imp_DeleteCriticalSection
0x180063bc4  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180063bcb  call    cs:__imp_DeleteCriticalSection
0x180063bd1  lea     rcx, [rbx+18h]
0x180063bd5  add     rsp, 30h
0x180063bd9  pop     rbx
0x180063bda  jmp     cs:__imp_DeleteCriticalSection
```
