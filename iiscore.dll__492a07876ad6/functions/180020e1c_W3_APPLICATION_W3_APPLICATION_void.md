# W3_APPLICATION::W3_APPLICATION(void)

- ea: `0x180020e1c`
- end: `0x180020f26`
- name: `??0W3_APPLICATION@@QEAA@XZ`
- size: `266`
- prototype: `W3_APPLICATION *__fastcall(W3_APPLICATION *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009e50`
- `0x180030738`

## callees

- `0x180017384`
- `0x18001b7f0`

## import_xrefs

- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180020e89`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x180020e89`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e53`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e76`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e53`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e63`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180020e76`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180020ebe`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180020ebe`

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
0x180020e1c  mov     [rsp+arg_0], rbx
0x180020e21  push    rdi
0x180020e22  sub     rsp, 20h
0x180020e26  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplication2@@@; const W3_APPLICATION::`vftable'{for `IHttpApplication2'}
0x180020e2d  mov     dword ptr [rcx+10h], 50413357h
0x180020e34  mov     [rcx], rax
0x180020e37  mov     rbx, rcx
0x180020e3a  lea     rax, ??_7W3_APPLICATION@@6BIHttpApplicationResolveModulesProvider@@@; const W3_APPLICATION::`vftable'{for `IHttpApplicationResolveModulesProvider'}
0x180020e41  mov     qword ptr [rcx+14h], 1
0x180020e49  mov     [rcx+8], rax
0x180020e4d  xor     edi, edi
0x180020e4f  add     rcx, 20h ; ' '
0x180020e53  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180020e5a  nop     dword ptr [rax+rax+00h]
0x180020e5f  lea     rcx, [rbx+58h]
0x180020e63  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180020e6a  nop     dword ptr [rax+rax+00h]
0x180020e6f  lea     rcx, [rbx+90h]
0x180020e76  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180020e7d  nop     dword ptr [rax+rax+00h]
0x180020e82  lea     rcx, [rbx+0C8h]
0x180020e89  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x180020e90  nop     dword ptr [rax+rax+00h]
0x180020e95  mov     [rbx+0D0h], rdi
0x180020e9c  lea     rax, ??_7APPLICATION_MODULE_LIST@@6B@; const APPLICATION_MODULE_LIST::`vftable'
0x180020ea3  mov     [rbx+0D8h], rdi
0x180020eaa  lea     rcx, [rbx+0F0h]
0x180020eb1  mov     [rbx+0E0h], rax
0x180020eb8  mov     [rbx+0E8h], edi
0x180020ebe  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180020ec5  nop     dword ptr [rax+rax+00h]
0x180020eca  lea     rcx, [rbx+128h]; this
0x180020ed1  mov     [rbx+120h], edi
0x180020ed7  xor     r8d, r8d; bool
0x180020eda  mov     dl, 1; bool
0x180020edc  call    ??0CONTEXT_CONTAINER@@QEAA@_N0@Z; CONTEXT_CONTAINER::CONTEXT_CONTAINER(bool,bool)
0x180020ee1  lea     rcx, [rbx+178h]; this
0x180020ee8  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x180020eed  lea     rcx, [rbx+330h]; this
0x180020ef4  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x180020ef9  lea     rcx, [rbx+4E8h]; this
0x180020f00  call    ??0CACHED_MODULE_LIST@@QEAA@XZ; CACHED_MODULE_LIST::CACHED_MODULE_LIST(void)
0x180020f05  mov     rax, rbx
0x180020f08  mov     [rbx+228h], edi
0x180020f0e  mov     [rbx+3E0h], edi
0x180020f14  mov     [rbx+598h], edi
0x180020f1a  mov     rbx, [rsp+28h+arg_0]
0x180020f1f  add     rsp, 20h
0x180020f23  pop     rdi
0x180020f24  retn
```
