# FTP_SITE_MANAGER::~FTP_SITE_MANAGER(void)

- ea: `0x18000b308`
- end: `0x18000b3cf`
- name: `??1FTP_SITE_MANAGER@@QEAA@XZ`
- size: `199`
- prototype: `void __fastcall(FTP_SITE_MANAGER *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800029fc`
- `0x180004a18`

## callees

- `0x180001250`
- `0x180008f40`
- `0x18000b1ec`
- `0x18000b308`
- `0x180026528`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b39d`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b3aa`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b39d`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18000b3aa`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b390`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b3b4`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b390`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b3b4`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000b3c8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall FTP_SITE_MANAGER::~FTP_SITE_MANAGER(FTP_SITE_MANAGER *this)
{
  volatile signed __int32 *v1; // rdi
  void *v3; // rdi
  FTP_LOG_FILE_MANAGER *v4; // rcx

  v1 = (volatile signed __int32 *)*((_QWORD *)this + 21);
  if ( v1 )
  {
    if ( _InterlockedExchangeAdd(v1 + 44, 0xFFFFFFFF) == 1 )
    {
      FTP_SITE::~FTP_SITE((FTP_SITE *)v1);
      operator delete((void *)v1);
    }
    *((_QWORD *)this + 21) = 0;
  }
  v3 = (void *)*((_QWORD *)this + 10);
  if ( v3 )
  {
    FTP_ENDPOINT_MANAGER::~FTP_ENDPOINT_MANAGER(*((FTP_ENDPOINT_MANAGER **)this + 10));
    operator delete(v3);
    *((_QWORD *)this + 10) = 0;
  }
  v4 = (FTP_LOG_FILE_MANAGER *)*((_QWORD *)this + 23);
  if ( v4 )
  {
    FTP_LOG_FILE_MANAGER::DereferenceFtpLogFileManager(v4);
    *((_QWORD *)this + 23) = 0;
  }
  CLKRHashTable::~CLKRHashTable((FTP_SITE_MANAGER *)((char *)this + 200));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SITE_MANAGER *)((char *)this + 192));
  CReaderWriterLock3::~CReaderWriterLock3((FTP_SITE_MANAGER *)((char *)this + 176));
  CLKRHashTable::~CLKRHashTable((FTP_SITE_MANAGER *)((char *)this + 88));
  CLKRHashTable::~CLKRHashTable((FTP_SITE_MANAGER *)((char *)this + 8));
}

```

## disassembly

```asm
0x18000b308  mov     [rsp+arg_0], rbx
0x18000b30d  push    rdi
0x18000b30e  sub     rsp, 20h
0x18000b312  mov     rdi, [rcx+0A8h]
0x18000b319  mov     rbx, rcx
0x18000b31c  test    rdi, rdi
0x18000b31f  jz      short loc_18000B34C
0x18000b321  or      eax, 0FFFFFFFFh
0x18000b324  lock xadd [rdi+0B0h], eax
0x18000b32c  cmp     eax, 1
0x18000b32f  jnz     short loc_18000B341
0x18000b331  mov     rcx, rdi; this
0x18000b334  call    ??1FTP_SITE@@AEAA@XZ; FTP_SITE::~FTP_SITE(void)
0x18000b339  mov     rcx, rdi; Block
0x18000b33c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b341  mov     qword ptr [rbx+0A8h], 0
0x18000b34c  mov     rdi, [rbx+50h]
0x18000b350  test    rdi, rdi
0x18000b353  jz      short loc_18000B36D
0x18000b355  mov     rcx, rdi; this
0x18000b358  call    ??1FTP_ENDPOINT_MANAGER@@QEAA@XZ; FTP_ENDPOINT_MANAGER::~FTP_ENDPOINT_MANAGER(void)
0x18000b35d  mov     rcx, rdi; Block
0x18000b360  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b365  mov     qword ptr [rbx+50h], 0
0x18000b36d  mov     rcx, [rbx+0B8h]; this
0x18000b374  test    rcx, rcx
0x18000b377  jz      short loc_18000B389
0x18000b379  call    ?DereferenceFtpLogFileManager@FTP_LOG_FILE_MANAGER@@QEAAXXZ; FTP_LOG_FILE_MANAGER::DereferenceFtpLogFileManager(void)
0x18000b37e  mov     qword ptr [rbx+0B8h], 0
0x18000b389  lea     rcx, [rbx+0C8h]
0x18000b390  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18000b396  lea     rcx, [rbx+0C0h]
0x18000b39d  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000b3a3  lea     rcx, [rbx+0B0h]
0x18000b3aa  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18000b3b0  lea     rcx, [rbx+58h]
0x18000b3b4  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x18000b3ba  lea     rcx, [rbx+8]
0x18000b3be  mov     rbx, [rsp+28h+arg_0]
0x18000b3c3  add     rsp, 20h
0x18000b3c7  pop     rdi
0x18000b3c8  jmp     cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
```
