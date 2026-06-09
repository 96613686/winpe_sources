# CDirectMusicPortDownload::~CDirectMusicPortDownload(void)

- ea: `0x18000f340`
- end: `0x18000f45d`
- name: `??1CDirectMusicPortDownload@@UEAA@XZ`
- size: `285`
- prototype: `void __fastcall(CDirectMusicPortDownload *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f470`
- `0x180010fb8`
- `0x18001d7c8`
- `0x180021c08`

## callees

- `0x1800012c4`
- `0x180001af0`
- `0x18000d0e0`
- `0x18000f340`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3ec`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3d6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f3ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f38b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3c0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f38b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000f3c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f39b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f39b`

## pseudocode

```c
void __fastcall CDirectMusicPortDownload::~CDirectMusicPortDownload(CDirectMusicPortDownload *this)
{
  struct _RTL_CRITICAL_SECTION *v2; // rdi
  __int64 i; // rax
  _QWORD *v4; // rcx
  CDownloadedInstrument *v5; // rcx
  _QWORD *v6; // rcx

  *(_QWORD *)this = &CDirectMusicPortDownload::`vftable';
  if ( *((_DWORD *)this + 78) && *((_DWORD *)this + 92) )
  {
    v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 328);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
    if ( *((_QWORD *)this + 2) )
      *((_QWORD *)this + 2) = 0;
    LeaveCriticalSection(v2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
    for ( i = 0; i != 31; ++i )
    {
      if ( *((_QWORD *)this + i + 3) )
        *((_QWORD *)this + i + 3) = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  }
  if ( *((_DWORD *)this + 78) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 272));
  if ( *((_DWORD *)this + 92) )
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 328));
  `eh vector destructor iterator'((char *)this + 24, 8u, 0x1Fu, (void (*)(void *))CDLBufferList::~CDLBufferList);
  while ( 1 )
  {
    v4 = (_QWORD *)*((_QWORD *)this + 2);
    if ( !v4 )
      break;
    *((_QWORD *)this + 2) = *v4;
    *v4 = 0;
    v5 = (CDownloadedInstrument *)(v4 - 2);
    if ( v5 )
      CDownloadedInstrument::Release(v5);
  }
  while ( 1 )
  {
    v6 = (_QWORD *)*((_QWORD *)this + 1);
    if ( !v6 )
      break;
    *((_QWORD *)this + 1) = *v6;
    *v6 = 0;
    operator delete(v6, 0x20u);
  }
}

```

## disassembly

```asm
0x18000f340  mov     [rsp+arg_0], rbx
0x18000f345  push    rdi
0x18000f346  sub     rsp, 20h
0x18000f34a  mov     rbx, rcx
0x18000f34d  lea     rax, ??_7CDirectMusicPortDownload@@6B@; const CDirectMusicPortDownload::`vftable'
0x18000f354  mov     [rcx], rax
0x18000f357  cmp     dword ptr [rcx+138h], 0
0x18000f35e  jz      short loc_18000F3C6
0x18000f360  cmp     dword ptr [rcx+170h], 0
0x18000f367  jz      short loc_18000F3C6
0x18000f369  lea     rdi, [rcx+148h]
0x18000f370  mov     rcx, rdi; lpCriticalSection
0x18000f373  call    cs:__imp_EnterCriticalSection
0x18000f379  cmp     qword ptr [rbx+10h], 0
0x18000f37e  jz      short loc_18000F388
0x18000f380  mov     qword ptr [rbx+10h], 0
0x18000f388  mov     rcx, rdi; lpCriticalSection
0x18000f38b  call    cs:__imp_LeaveCriticalSection
0x18000f391  lea     rdi, [rbx+110h]
0x18000f398  mov     rcx, rdi; lpCriticalSection
0x18000f39b  call    cs:__imp_EnterCriticalSection
0x18000f3a1  xor     eax, eax
0x18000f3a3  cmp     qword ptr [rbx+rax*8+18h], 0
0x18000f3a9  jz      short loc_18000F3B4
0x18000f3ab  mov     qword ptr [rbx+rax*8+18h], 0
0x18000f3b4  inc     rax
0x18000f3b7  cmp     rax, 1Fh
0x18000f3bb  jnz     short loc_18000F3A3
0x18000f3bd  mov     rcx, rdi; lpCriticalSection
0x18000f3c0  call    cs:__imp_LeaveCriticalSection
0x18000f3c6  cmp     dword ptr [rbx+138h], 0
0x18000f3cd  jz      short loc_18000F3DC
0x18000f3cf  lea     rcx, [rbx+110h]; lpCriticalSection
0x18000f3d6  call    cs:__imp_DeleteCriticalSection
0x18000f3dc  cmp     dword ptr [rbx+170h], 0
0x18000f3e3  jz      short loc_18000F3F2
0x18000f3e5  lea     rcx, [rbx+148h]; lpCriticalSection
0x18000f3ec  call    cs:__imp_DeleteCriticalSection
0x18000f3f2  lea     rcx, [rbx+18h]; void *
0x18000f3f6  lea     r9, ??1CDLBufferList@@AEAA@XZ; void (*)(void *)
0x18000f3fd  mov     edx, 8; unsigned __int64
0x18000f402  lea     r8d, [rdx+17h]; unsigned __int64
0x18000f406  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000f40b  mov     rcx, [rbx+10h]
0x18000f40f  test    rcx, rcx
0x18000f412  jz      short loc_18000F42F
0x18000f414  mov     rax, [rcx]
0x18000f417  mov     [rbx+10h], rax
0x18000f41b  mov     qword ptr [rcx], 0
0x18000f422  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x18000f426  jz      short loc_18000F40B
0x18000f428  call    ?Release@CDownloadedInstrument@@UEAAKXZ; CDownloadedInstrument::Release(void)
0x18000f42d  jmp     short loc_18000F40B
0x18000f42f  mov     rcx, [rbx+8]; void *
0x18000f433  test    rcx, rcx
0x18000f436  jz      short loc_18000F452
0x18000f438  mov     rax, [rcx]
0x18000f43b  mov     [rbx+8], rax
0x18000f43f  mov     qword ptr [rcx], 0
0x18000f446  mov     edx, 20h ; ' '; unsigned __int64
0x18000f44b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f450  jmp     short loc_18000F42F
0x18000f452  mov     rbx, [rsp+28h+arg_0]
0x18000f457  add     rsp, 20h
0x18000f45b  pop     rdi
0x18000f45c  retn
```
