# CLogStorage::~CLogStorage(void)

- ea: `0x18000a088`
- end: `0x18000a19f`
- name: `??1CLogStorage@@QEAA@XZ`
- size: `279`
- prototype: `void __fastcall(CLogStorage *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006e80`

## callees

- `0x180001300`
- `0x180001c94`
- `0x18000a088`
- `0x18000c6b8`
- `0x18000d998`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a13e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a13e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a18d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a18d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a134`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a0fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000a134`

## string_xrefs

- `0x18000a110`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`
- `0x18000a14a`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogStorage::~CLogStorage(CLogStorage *this)
{
  struct CBuffer *v2; // rdx
  struct CBuffer *v3; // rdx
  char *v4; // rcx
  char *v5; // rbx
  void *v6; // rcx
  DWORD LastError; // eax
  void *v8; // rcx
  DWORD v9; // eax

  v2 = (struct CBuffer *)*((_QWORD *)this + 16);
  if ( v2 )
    CLogStorage::_UnmapBuffer(this, v2, 0);
  v3 = (struct CBuffer *)*((_QWORD *)this + 17);
  if ( v3 )
    CLogStorage::_UnmapBuffer(this, v3, 0);
  v4 = (char *)*((_QWORD *)this + 94);
  if ( v4 )
  {
    v5 = v4 - 8;
    `eh vector destructor iterator'(v4, 0x50u, *((_QWORD *)v4 - 1), (void (*)(void *))CBuffer::~CBuffer);
    operator delete(v5);
  }
  v6 = (void *)*((_QWORD *)this + 20);
  if ( v6 != (void *)-1LL && !CloseHandle(v6) )
  {
    LastError = GetLastError();
    TraceFile(LastError, "CloseHandle _hSection", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0xEBu);
    __int2c();
  }
  v8 = (void *)*((_QWORD *)this + 19);
  if ( v8 != (void *)-1LL && !CloseHandle(v8) )
  {
    v9 = GetLastError();
    TraceFile(v9, "CloseHandle _hFile", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0xF7u);
    __int2c();
  }
  operator delete(pulCRCTable);
  pulCRCTable = 0;
  *((_QWORD *)this + 86) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 696));
}

```

## disassembly

```asm
0x18000a088  mov     [rsp+arg_0], rbx
0x18000a08d  push    rdi
0x18000a08e  sub     rsp, 20h
0x18000a092  mov     rdi, rcx
0x18000a095  mov     rdx, [rcx+80h]; struct CBuffer *
0x18000a09c  test    rdx, rdx
0x18000a09f  jz      short loc_18000A0A9
0x18000a0a1  xor     r8d, r8d; int
0x18000a0a4  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a0a9  mov     rdx, [rdi+88h]; struct CBuffer *
0x18000a0b0  test    rdx, rdx
0x18000a0b3  jz      short loc_18000A0C0
0x18000a0b5  xor     r8d, r8d; int
0x18000a0b8  mov     rcx, rdi; this
0x18000a0bb  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x18000a0c0  mov     rcx, [rdi+2F0h]; void *
0x18000a0c7  test    rcx, rcx
0x18000a0ca  jz      short loc_18000A0ED
0x18000a0cc  lea     rbx, [rcx-8]
0x18000a0d0  lea     r9, ??1CBuffer@@QEAA@XZ; void (*)(void *)
0x18000a0d7  mov     r8, [rbx]; unsigned __int64
0x18000a0da  mov     edx, 50h ; 'P'; unsigned __int64
0x18000a0df  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18000a0e4  mov     rcx, rbx; Block
0x18000a0e7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a0ec  nop
0x18000a0ed  mov     rcx, [rdi+0A0h]; hObject
0x18000a0f4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a0f8  jz      short loc_18000A127
0x18000a0fa  call    cs:__imp_CloseHandle
0x18000a100  test    eax, eax
0x18000a102  jnz     short loc_18000A127
0x18000a104  call    cs:__imp_GetLastError
0x18000a10a  mov     r9d, 0EBh; unsigned int
0x18000a110  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000a117  lea     rdx, aClosehandleHse; "CloseHandle _hSection"
0x18000a11e  mov     ecx, eax; int
0x18000a120  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000a125  int     2Ch; Windows NT - assertion failure
0x18000a127  mov     rcx, [rdi+98h]; hObject
0x18000a12e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a132  jz      short loc_18000A161
0x18000a134  call    cs:__imp_CloseHandle
0x18000a13a  test    eax, eax
0x18000a13c  jnz     short loc_18000A161
0x18000a13e  call    cs:__imp_GetLastError
0x18000a144  mov     r9d, 0F7h; unsigned int
0x18000a14a  lea     r8, aComComplusDtcD_0; "com\\complus\\dtc\\dtc\\log\\logmgr\\sr"...
0x18000a151  lea     rdx, aClosehandleHfi; "CloseHandle _hFile"
0x18000a158  mov     ecx, eax; int
0x18000a15a  call    ?TraceFile@@YAXJPEADPEBDI@Z; TraceFile(long,char *,char const *,uint)
0x18000a15f  int     2Ch; Windows NT - assertion failure
0x18000a161  mov     rcx, cs:?pulCRCTable@@3PEAKEA; Block
0x18000a168  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a16d  mov     cs:?pulCRCTable@@3PEAKEA, 0; ulong * pulCRCTable
0x18000a178  lea     rax, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x18000a17f  mov     [rdi+2B0h], rax
0x18000a186  lea     rcx, [rdi+2B8h]; lpCriticalSection
0x18000a18d  call    cs:__imp_DeleteCriticalSection
0x18000a193  nop
0x18000a194  mov     rbx, [rsp+28h+arg_0]
0x18000a199  add     rsp, 20h
0x18000a19d  pop     rdi
0x18000a19e  retn
```
