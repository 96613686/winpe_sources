# W3_APPLICATION::W3_APPLICATION(void)

- ea: `0x18001f29c`
- end: `0x18001f387`
- name: `??0W3_APPLICATION@@QEAA@XZ`
- size: `235`
- prototype: `W3_APPLICATION *__fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800095d0`
- `0x18002dcb8`

## callees

- `0x180016100`
- `0x18001a200`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001f2f7`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18001f2f7`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2d3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2dd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2ea`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2d3`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2dd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x18001f2ea`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001f326`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18001f326`

## pseudocode

```c
W3_APPLICATION *__fastcall W3_APPLICATION::W3_APPLICATION(W3_APPLICATION *this)
{
  W3_APPLICATION *result; // rax

  *((_DWORD *)this + 4) = 1346450263;
  *(_QWORD *)this = &W3_APPLICATION::`vftable'{for `IHttpApplication2'};
  *(_QWORD *)((char *)this + 20) = 1;
  *((_QWORD *)this + 1) = &W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'};
  STRU::STRU((W3_APPLICATION *)((char *)this + 32));
  STRU::STRU((W3_APPLICATION *)((char *)this + 88));
  STRU::STRU((W3_APPLICATION *)((char *)this + 144));
  CReaderWriterLock3::CReaderWriterLock3((W3_APPLICATION *)((char *)this + 200));
  *((_QWORD *)this + 26) = 0;
  *((_QWORD *)this + 27) = 0;
  *((_QWORD *)this + 28) = &APPLICATION_MODULE_LIST::`vftable';
  *((_DWORD *)this + 58) = 0;
  BUFFER::BUFFER((W3_APPLICATION *)((char *)this + 240));
  *((_DWORD *)this + 72) = 0;
  CONTEXT_CONTAINER::CONTEXT_CONTAINER((W3_APPLICATION *)((char *)this + 296), 1, 0);
  CACHED_MODULE_LIST::CACHED_MODULE_LIST((W3_APPLICATION *)((char *)this + 376));
  CACHED_MODULE_LIST::CACHED_MODULE_LIST((W3_APPLICATION *)((char *)this + 816));
  CACHED_MODULE_LIST::CACHED_MODULE_LIST((W3_APPLICATION *)((char *)this + 1256));
  result = this;
  *((_DWORD *)this + 138) = 0;
  *((_DWORD *)this + 248) = 0;
  *((_DWORD *)this + 358) = 0;
  return result;
}

```

## disassembly

```asm
0x18001f29c  mov     [rsp+arg_0], rbx
0x18001f2a1  push    rdi
0x18001f2a2  sub     rsp, 20h
0x18001f2a6  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplication2@@@; const W3_APPLICATION::`vftable'{for `IHttpApplication2'}
0x18001f2ad  mov     dword ptr [rcx+10h], 50413357h
0x18001f2b4  mov     [rcx], rax
0x18001f2b7  mov     rbx, rcx
0x18001f2ba  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplicationResolveModulesProvider@@@; const W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'}
0x18001f2c1  mov     qword ptr [rcx+14h], 1
0x18001f2c9  mov     [rcx+8], rax
0x18001f2cd  xor     edi, edi
0x18001f2cf  add     rcx, 20h ; ' '
0x18001f2d3  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f2d9  lea     rcx, [rbx+58h]
0x18001f2dd  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f2e3  lea     rcx, [rbx+90h]
0x18001f2ea  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18001f2f0  lea     rcx, [rbx+0C8h]
0x18001f2f7  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18001f2fd  mov     [rbx+0D0h], rdi
0x18001f304  lea     rax, ??_7APPLICATION_MODULE_LIST@@6B@; const APPLICATION_MODULE_LIST::`vftable'
0x18001f30b  mov     [rbx+0D8h], rdi
0x18001f312  lea     rcx, [rbx+0F0h]
0x18001f319  mov     [rbx+0E0h], rax
0x18001f320  mov     [rbx+0E8h], edi
0x18001f326  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18001f32c  lea     rcx, [rbx+128h]; this
0x18001f333  mov     [rbx+120h], edi
0x18001f339  xor     r8d, r8d; bool
0x18001f33c  mov     dl, 1; bool
0x18001f33e  call    ??0CONTEXT_CONTAINER@@QEAA@_N0@Z; CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)
0x18001f343  lea     rcx, [rbx+178h]; this
0x18001f34a  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x18001f34f  lea     rcx, [rbx+330h]; this
0x18001f356  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x18001f35b  lea     rcx, [rbx+4E8h]; this
0x18001f362  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x18001f367  mov     rax, rbx
0x18001f36a  mov     [rbx+228h], edi
0x18001f370  mov     [rbx+3E0h], edi
0x18001f376  mov     [rbx+598h], edi
0x18001f37c  mov     rbx, [rsp+28h+arg_0]
0x18001f381  add     rsp, 20h
0x18001f385  pop     rdi
0x18001f386  retn
```
