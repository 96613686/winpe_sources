# CPerContext::~CPerContext(void)

- ea: `0x18001e0f8`
- end: `0x18001e173`
- name: `??1CPerContext@@QEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CPerContext *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180019ee0`
- `0x18001c2ac`
- `0x18001eaa0`
- `0x18001f080`
- `0x180036c90`
- `0x18003b588`
- `0x1800405dc`

## callees

- `0x18001b1c0`
- `0x18001b840`
- `0x18001e0f8`
- `0x18001e17c`
- `0x18001e6b0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e163`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e163`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e13f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e13f`

## pseudocode

```c
void __fastcall CPerContext::~CPerContext(CPerContext *this)
{
  _DWORD *v1; // rbx
  void *v3; // rcx

  v1 = (_DWORD *)*((_QWORD *)this + 6);
  if ( v1 )
  {
    CContextList::Remove(*((CContextList **)this + 6), this);
    if ( v1 != (_DWORD *)-64LL && v1[18] == GetCurrentThreadId() )
      CDfMutex::Release((HANDLE *)this + 14);
    if ( v1[2]-- == 1 )
      CMallocBased::operator delete(v1);
  }
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 != (void *)-1LL )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 10) = -1;
  }
  CDfMutex::~CDfMutex((CPerContext *)((char *)this + 112));
}

```

## disassembly

```asm
0x18001e0f8  mov     [rsp+arg_8], rbx
0x18001e0fd  push    rdi
0x18001e0fe  sub     rsp, 20h
0x18001e102  mov     rbx, [rcx+30h]
0x18001e106  mov     rdi, rcx
0x18001e109  test    rbx, rbx
0x18001e10c  jnz     short loc_18001E12B
0x18001e10e  mov     rcx, [rdi+50h]; hObject
0x18001e112  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001e116  jnz     short loc_18001E163
0x18001e118  lea     rcx, [rdi+70h]; this
0x18001e11c  mov     rbx, [rsp+28h+arg_8]
0x18001e121  add     rsp, 20h
0x18001e125  pop     rdi
0x18001e126  jmp     ??1CDfMutex@@QEAA@XZ; CDfMutex::~CDfMutex(void)
0x18001e12b  mov     rdx, rdi; struct CContext *
0x18001e12e  mov     rcx, rbx; this
0x18001e131  call    ?Remove@CContextList@@QEAAXPEAVCContext@@@Z; CContextList::Remove(CContext *)
0x18001e136  lea     rdx, [rbx+40h]
0x18001e13a  test    rdx, rdx
0x18001e13d  jz      short loc_18001E153
0x18001e13f  call    cs:__imp_GetCurrentThreadId
0x18001e145  cmp     [rbx+48h], eax
0x18001e148  jnz     short loc_18001E153
0x18001e14a  lea     rcx, [rdi+70h]; this
0x18001e14e  call    ?Release@CDfMutex@@QEAAXXZ; CDfMutex::Release(void)
0x18001e153  sub     dword ptr [rbx+8], 1
0x18001e157  jnz     short loc_18001E10E
0x18001e159  mov     rcx, rbx; void *
0x18001e15c  call    ??3CMallocBased@@SAXPEAX@Z; CMallocBased::operator delete(void *)
0x18001e161  jmp     short loc_18001E10E
0x18001e163  call    cs:__imp_CloseHandle
0x18001e169  mov     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x18001e171  jmp     short loc_18001E118
```
