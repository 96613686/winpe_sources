# SSI_REQUEST::SSI_REQUEST(IHttpContext *)

- ea: `0x180003304`
- end: `0x1800033c1`
- name: `??0SSI_REQUEST@@AEAA@PEAVIHttpContext@@@Z`
- size: `189`
- prototype: `SSI_REQUEST *__fastcall(SSI_REQUEST *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000231c`

## callees

- `0x180006010`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003337`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000334e`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003337`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000334e`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003366`
- `iisutil!??0STRA@@QEAA@PEADK@Z` at `0x180003366`
- `iisutil!?Initialize@CHUNK_BUFFER@@AEAAXXZ` at `0x18000337d`
- `iisutil!?Initialize@CHUNK_BUFFER@@AEAAXXZ` at `0x18000337d`

## pseudocode

```c
SSI_REQUEST *__fastcall SSI_REQUEST::SSI_REQUEST(SSI_REQUEST *this, struct IHttpContext *a2)
{
  *((_QWORD *)this + 1) = a2;
  *(_QWORD *)this = &SSI_REQUEST::`vftable';
  STRU::STRU((SSI_REQUEST *)((char *)this + 16), (unsigned __int16 *)this + 36, 0x81u);
  STRU::STRU((SSI_REQUEST *)((char *)this + 336), (unsigned __int16 *)this + 196, 0x81u);
  STRA::STRA((SSI_REQUEST *)((char *)this + 656), (char *)this + 712, 0x41u);
  *((_DWORD *)this + 196) = 0;
  CHUNK_BUFFER::Initialize((SSI_REQUEST *)((char *)this + 800));
  *((_QWORD *)this + 136) = a2;
  *((_QWORD *)this + 137) = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)a2 + 32LL))(a2);
  *((_QWORD *)this + 139) = (char *)this + 1104;
  *((_QWORD *)this + 138) = (char *)this + 1104;
  return this;
}

```

## disassembly

```asm
0x180003304  mov     [rsp+arg_0], rbx
0x180003309  mov     [rsp+arg_8], rsi
0x18000330e  push    rdi
0x18000330f  sub     rsp, 20h
0x180003313  mov     [rcx+8], rdx
0x180003317  lea     rax, ??_7SSI_REQUEST@@6B@; const SSI_REQUEST::`vftable'
0x18000331e  mov     rdi, rdx
0x180003321  mov     [rcx], rax
0x180003324  mov     rsi, rcx
0x180003327  lea     rdx, [rcx+48h]
0x18000332b  mov     ebx, 81h
0x180003330  add     rcx, 10h
0x180003334  mov     r8d, ebx
0x180003337  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000333d  lea     rdx, [rsi+188h]
0x180003344  mov     r8d, ebx
0x180003347  lea     rcx, [rsi+150h]
0x18000334e  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003354  lea     rdx, [rsi+2C8h]
0x18000335b  lea     rcx, [rsi+290h]
0x180003362  lea     r8d, [rbx-40h]
0x180003366  call    cs:__imp_??0STRA@@QEAA@PEADK@Z; STRA::STRA(char *,ulong)
0x18000336c  lea     rcx, [rsi+320h]
0x180003373  mov     dword ptr [rsi+310h], 0
0x18000337d  call    cs:__imp_?Initialize@CHUNK_BUFFER@@AEAAXXZ; CHUNK_BUFFER::Initialize(void)
0x180003383  mov     [rsi+440h], rdi
0x18000338a  mov     rcx, rdi
0x18000338d  mov     rax, [rdi]
0x180003390  mov     rax, [rax+20h]
0x180003394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003399  mov     rbx, [rsp+28h+arg_0]
0x18000339e  mov     [rsi+448h], rax
0x1800033a5  lea     rax, [rsi+450h]
0x1800033ac  mov     [rax+8], rax
0x1800033b0  mov     [rax], rax
0x1800033b3  mov     rax, rsi
0x1800033b6  mov     rsi, [rsp+28h+arg_8]
0x1800033bb  add     rsp, 20h
0x1800033bf  pop     rdi
0x1800033c0  retn
```
