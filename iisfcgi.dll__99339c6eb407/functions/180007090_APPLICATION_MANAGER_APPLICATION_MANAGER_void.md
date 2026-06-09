# APPLICATION_MANAGER::~APPLICATION_MANAGER(void)

- ea: `0x180007090`
- end: `0x180007178`
- name: `??1APPLICATION_MANAGER@@AEAA@XZ`
- size: `232`
- prototype: `void __fastcall(APPLICATION_MANAGER *__hidden this)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800047ec`
- `0x180007180`
- `0x180009c00`
- `0x180009eb4`
- `0x18000d370`

## callees

- `0x180001048`
- `0x180003e1c`
- `0x180007090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800070b1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800070b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070dc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070dc`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007133`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000714d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000715a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007133`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000714d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000715a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180007171`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007140`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180007140`

## pseudocode

```c
void __fastcall APPLICATION_MANAGER::~APPLICATION_MANAGER(APPLICATION_MANAGER *this)
{
  bool v1; // zf
  __int64 v3; // rdi
  void *v4; // rcx
  volatile signed __int32 *v5; // rdi

  v1 = *((_DWORD *)this + 14) == 0;
  *(_QWORD *)this = &APPLICATION_MANAGER::`vftable';
  if ( !v1 )
  {
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    *((_DWORD *)this + 14) = 0;
  }
  v3 = *((_QWORD *)this + 59);
  if ( v3 )
  {
    _InterlockedExchange((volatile __int32 *)(v3 + 8), 1);
    v4 = *(void **)(v3 + 80);
    if ( v4 != (void *)-1LL )
    {
      CloseHandle(v4);
      *(_QWORD *)(v3 + 80) = -1;
    }
    v5 = (volatile signed __int32 *)*((_QWORD *)this + 59);
    if ( _InterlockedExchangeAdd(v5 + 1, 0xFFFFFFFF) == 1 && v5 )
    {
      FILE_LISTENER::~FILE_LISTENER((FILE_LISTENER *)v5);
      operator delete((void *)v5);
    }
    *((_QWORD *)this + 59) = 0;
  }
  _InterlockedDecrement(&APPLICATION_MANAGER::sm_lApplicationManagers);
  *((_DWORD *)this + 2) = 1835231078;
  STRU::~STRU((APPLICATION_MANAGER *)((char *)this + 392));
  MULTISZ::~MULTISZ((APPLICATION_MANAGER *)((char *)this + 336));
  STRU::~STRU((APPLICATION_MANAGER *)((char *)this + 272));
  STRU::~STRU((APPLICATION_MANAGER *)((char *)this + 216));
  STRU::~STRU((APPLICATION_MANAGER *)((char *)this + 160));
}

```

## disassembly

```asm
0x180007090  mov     [rsp+arg_0], rbx
0x180007095  push    rdi
0x180007096  sub     rsp, 20h
0x18000709a  cmp     dword ptr [rcx+38h], 0
0x18000709e  lea     rax, ??_7APPLICATION_MANAGER@@6B@; const APPLICATION_MANAGER::`vftable'
0x1800070a5  mov     [rcx], rax
0x1800070a8  mov     rbx, rcx
0x1800070ab  jz      short loc_1800070BE
0x1800070ad  add     rcx, 10h; lpCriticalSection
0x1800070b1  call    cs:__imp_DeleteCriticalSection
0x1800070b7  mov     dword ptr [rbx+38h], 0
0x1800070be  mov     rdi, [rbx+1D8h]
0x1800070c5  test    rdi, rdi
0x1800070c8  jz      short loc_18000711E
0x1800070ca  mov     eax, 1
0x1800070cf  xchg    eax, [rdi+8]
0x1800070d2  mov     rcx, [rdi+50h]; hObject
0x1800070d6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800070da  jz      short loc_1800070EA
0x1800070dc  call    cs:__imp_CloseHandle
0x1800070e2  mov     qword ptr [rdi+50h], 0FFFFFFFFFFFFFFFFh
0x1800070ea  mov     rdi, [rbx+1D8h]
0x1800070f1  or      eax, 0FFFFFFFFh
0x1800070f4  lock xadd [rdi+4], eax
0x1800070f9  cmp     eax, 1
0x1800070fc  jnz     short loc_180007113
0x1800070fe  test    rdi, rdi
0x180007101  jz      short loc_180007113
0x180007103  mov     rcx, rdi; this
0x180007106  call    ??1FILE_LISTENER@@QEAA@XZ; FILE_LISTENER::~FILE_LISTENER(void)
0x18000710b  mov     rcx, rdi; Block
0x18000710e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007113  mov     qword ptr [rbx+1D8h], 0
0x18000711e  lock dec cs:?sm_lApplicationManagers@APPLICATION_MANAGER@@0JA; long APPLICATION_MANAGER::sm_lApplicationManagers
0x180007125  lea     rcx, [rbx+188h]
0x18000712c  mov     dword ptr [rbx+8], 6D636766h
0x180007133  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007139  lea     rcx, [rbx+150h]
0x180007140  call    cs:__imp_??1MULTISZ@@QEAA@XZ; MULTISZ::~MULTISZ(void)
0x180007146  lea     rcx, [rbx+110h]
0x18000714d  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007153  lea     rcx, [rbx+0D8h]
0x18000715a  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180007160  lea     rcx, [rbx+0A0h]
0x180007167  mov     rbx, [rsp+28h+arg_0]
0x18000716c  add     rsp, 20h
0x180007170  pop     rdi
0x180007171  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
