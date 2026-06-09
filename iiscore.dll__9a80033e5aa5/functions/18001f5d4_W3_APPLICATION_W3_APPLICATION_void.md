# W3_APPLICATION::~W3_APPLICATION(void)

- ea: `0x18001f5d4`
- end: `0x18001f6ab`
- name: `??1W3_APPLICATION@@UEAA@XZ`
- size: `215`
- prototype: `void __fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f870`

## callees

- `0x18000de40`
- `0x18001a7a8`
- `0x18001aed0`
- `0x18001f534`
- `0x18001f5d4`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001f67b`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18001f67b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f688`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f692`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f688`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f692`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18001f6a4`

## pseudocode

```c
void __fastcall W3_APPLICATION::~W3_APPLICATION(W3_APPLICATION *this)
{
  CACHED_MODULE_LIST *v2; // rbp
  bool v3; // zf

  *(_QWORD *)this = &W3_APPLICATION::`vftable'{for `IHttpApplication2'};
  v2 = (W3_APPLICATION *)((char *)this + 376);
  v3 = *((_DWORD *)this + 138) == 0;
  *((_QWORD *)this + 1) = &W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'};
  if ( !v3 )
    MODULE_LIST::FreeModules((W3_APPLICATION *)((char *)this + 376));
  if ( *((_DWORD *)this + 248) )
    MODULE_LIST::FreeModules((W3_APPLICATION *)((char *)this + 816));
  if ( *((_DWORD *)this + 358) )
    MODULE_LIST::FreeModules((W3_APPLICATION *)((char *)this + 1256));
  *((_DWORD *)this + 4) = 1885418359;
  CACHED_MODULE_LIST::~CACHED_MODULE_LIST((W3_APPLICATION *)((char *)this + 1256));
  CACHED_MODULE_LIST::~CACHED_MODULE_LIST((W3_APPLICATION *)((char *)this + 816));
  CACHED_MODULE_LIST::~CACHED_MODULE_LIST(v2);
  CONTEXT_CONTAINER::~CONTEXT_CONTAINER((W3_APPLICATION *)((char *)this + 296));
  APPLICATION_MODULE_LIST::~APPLICATION_MODULE_LIST((W3_APPLICATION *)((char *)this + 224));
  CReaderWriterLock3::~CReaderWriterLock3((W3_APPLICATION *)((char *)this + 200));
  STRU::~STRU((W3_APPLICATION *)((char *)this + 144));
  STRU::~STRU((W3_APPLICATION *)((char *)this + 88));
  STRU::~STRU((W3_APPLICATION *)((char *)this + 32));
}

```

## disassembly

```asm
0x18001f5d4  push    rbx
0x18001f5d6  push    rbp
0x18001f5d7  push    rsi
0x18001f5d8  push    rdi
0x18001f5d9  sub     rsp, 28h
0x18001f5dd  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplication2@@@; const W3_APPLICATION::`vftable'{for `IHttpApplication2'}
0x18001f5e4  mov     rbx, rcx
0x18001f5e7  mov     [rcx], rax
0x18001f5ea  lea     rbp, [rcx+178h]
0x18001f5f1  cmp     dword ptr [rbp+0B0h], 0
0x18001f5f8  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplicationResolveModulesProvider@@@; const W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'}
0x18001f5ff  mov     [rcx+8], rax
0x18001f603  jz      short loc_18001F60D
0x18001f605  mov     rcx, rbp; this
0x18001f608  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001f60d  lea     rdi, [rbx+330h]
0x18001f614  cmp     dword ptr [rdi+0B0h], 0
0x18001f61b  jz      short loc_18001F625
0x18001f61d  mov     rcx, rdi; this
0x18001f620  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001f625  lea     rsi, [rbx+4E8h]
0x18001f62c  cmp     dword ptr [rsi+0B0h], 0
0x18001f633  jz      short loc_18001F63D
0x18001f635  mov     rcx, rsi; this
0x18001f638  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x18001f63d  mov     rcx, rsi; this
0x18001f640  mov     dword ptr [rbx+10h], 70613377h
0x18001f647  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x18001f64c  mov     rcx, rdi; this
0x18001f64f  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x18001f654  mov     rcx, rbp; this
0x18001f657  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x18001f65c  lea     rcx, [rbx+128h]; this
0x18001f663  call    ??1CONTEXT_CONTAINER@@UEAA@XZ; CONTEXT_CONTAINER::~CONTEXT_CONTAINER(void)
0x18001f668  lea     rcx, [rbx+0E0h]; this
0x18001f66f  call    ??1APPLICATION_MODULE_LIST@@UEAA@XZ; APPLICATION_MODULE_LIST::~APPLICATION_MODULE_LIST(void)
0x18001f674  lea     rcx, [rbx+0C8h]
0x18001f67b  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x18001f681  lea     rcx, [rbx+90h]
0x18001f688  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f68e  lea     rcx, [rbx+58h]
0x18001f692  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18001f698  lea     rcx, [rbx+20h]
0x18001f69c  add     rsp, 28h
0x18001f6a0  pop     rdi
0x18001f6a1  pop     rsi
0x18001f6a2  pop     rbp
0x18001f6a3  pop     rbx
0x18001f6a4  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
