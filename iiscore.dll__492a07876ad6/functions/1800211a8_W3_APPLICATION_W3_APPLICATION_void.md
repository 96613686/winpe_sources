# W3_APPLICATION::~W3_APPLICATION(void)

- ea: `0x1800211a8`
- end: `0x180021296`
- name: `??1W3_APPLICATION@@UEAA@XZ`
- size: `238`
- prototype: `void __fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180021470`

## callees

- `0x18000e9c0`
- `0x18001be2c`
- `0x18001c5f0`
- `0x1800210f8`
- `0x1800211a8`

## import_xrefs

- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18002124f`
- `iisutil!??1CReaderWriterLock3@@QEAA@XZ` at `0x18002124f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021262`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021272`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021262`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180021272`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18002128a`

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
0x1800211a8  push    rbx
0x1800211aa  push    rbp
0x1800211ab  push    rsi
0x1800211ac  push    rdi
0x1800211ad  sub     rsp, 28h
0x1800211b1  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplication2@@@; const W3_APPLICATION::`vftable'{for `IHttpApplication2'}
0x1800211b8  mov     rbx, rcx
0x1800211bb  mov     [rcx], rax
0x1800211be  lea     rbp, [rcx+178h]
0x1800211c5  cmp     dword ptr [rbp+0B0h], 0
0x1800211cc  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplicationResolveModulesProvider@@@; const W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'}
0x1800211d3  mov     [rcx+8], rax
0x1800211d7  jz      short loc_1800211E1
0x1800211d9  mov     rcx, rbp; this
0x1800211dc  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x1800211e1  lea     rdi, [rbx+330h]
0x1800211e8  cmp     dword ptr [rdi+0B0h], 0
0x1800211ef  jz      short loc_1800211F9
0x1800211f1  mov     rcx, rdi; this
0x1800211f4  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x1800211f9  lea     rsi, [rbx+4E8h]
0x180021200  cmp     dword ptr [rsi+0B0h], 0
0x180021207  jz      short loc_180021211
0x180021209  mov     rcx, rsi; this
0x18002120c  call    ?FreeModules@MODULE_LIST@@QEAAXXZ; MODULE_LIST::FreeModules(void)
0x180021211  mov     rcx, rsi; this
0x180021214  mov     dword ptr [rbx+10h], 70613377h
0x18002121b  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x180021220  mov     rcx, rdi; this
0x180021223  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x180021228  mov     rcx, rbp; this
0x18002122b  call    ??1CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::~CACHED_MODULE_LIST(void)
0x180021230  lea     rcx, [rbx+128h]; this
0x180021237  call    ??1CONTEXT_CONTAINER@@UEAA@XZ; CONTEXT_CONTAINER::~CONTEXT_CONTAINER(void)
0x18002123c  lea     rcx, [rbx+0E0h]; this
0x180021243  call    ??1APPLICATION_MODULE_LIST@@UEAA@XZ; APPLICATION_MODULE_LIST::~APPLICATION_MODULE_LIST(void)
0x180021248  lea     rcx, [rbx+0C8h]
0x18002124f  call    cs:__imp_??1CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::~CReaderWriterLock3(void)
0x180021256  nop     dword ptr [rax+rax+00h]
0x18002125b  lea     rcx, [rbx+90h]
0x180021262  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021269  nop     dword ptr [rax+rax+00h]
0x18002126e  lea     rcx, [rbx+58h]
0x180021272  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180021279  nop     dword ptr [rax+rax+00h]
0x18002127e  lea     rcx, [rbx+20h]
0x180021282  add     rsp, 28h
0x180021286  pop     rdi
0x180021287  pop     rsi
0x180021288  pop     rbp
0x180021289  pop     rbx
0x18002128a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
