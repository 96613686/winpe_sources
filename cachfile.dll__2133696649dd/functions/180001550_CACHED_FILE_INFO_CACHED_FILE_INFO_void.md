# CACHED_FILE_INFO::CACHED_FILE_INFO(void)

- ea: `0x180001550`
- end: `0x18000162a`
- name: `??0CACHED_FILE_INFO@@QEAA@XZ`
- size: `218`
- prototype: `CACHED_FILE_INFO *__fastcall(CACHED_FILE_INFO *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800013f0`

## callees

- `0x180001550`

## import_xrefs

- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001580`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180001580`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800015e6`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800015e6`
- `iisutil!WriteRefTraceLog` at `0x180001622`
- `iisutil!WriteRefTraceLog` at `0x180001622`

## pseudocode

```c
CACHED_FILE_INFO *__fastcall CACHED_FILE_INFO::CACHED_FILE_INFO(CACHED_FILE_INFO *this)
{
  struct _TRACE_LOG *v2; // rcx

  *(_QWORD *)this = &CACHED_FILE_INFO::`vftable';
  *((_QWORD *)this + 1) = &CACHED_FILE_KEY::`vftable';
  STRU::STRU((CACHED_FILE_INFO *)((char *)this + 16), (unsigned __int16 *)this + 36, 0x5Cu);
  *((_DWORD *)this + 64) = 1279870531;
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *(_QWORD *)((char *)this + 260) = 1;
  *((_WORD *)this + 160) = 256;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = 0;
  *((_QWORD *)this + 45) = 0;
  *((_WORD *)this + 184) = 0;
  BUFFER::BUFFER((CACHED_FILE_INFO *)((char *)this + 432), (unsigned __int8 *)this + 480, 0x100u);
  v2 = g_pTraceLog;
  *((_DWORD *)this + 184) = 0;
  *((_QWORD *)this + 93) = 0;
  *((_QWORD *)this + 103) = 0;
  if ( v2 )
    WriteRefTraceLog(v2, 1, this);
  return this;
}

```

## disassembly

```asm
0x180001550  mov     [rsp+arg_0], rbx
0x180001555  push    rdi
0x180001556  sub     rsp, 20h
0x18000155a  lea     rax, ??_7CACHED_FILE_INFO@@6B@; const CACHED_FILE_INFO::`vftable'
0x180001561  mov     rbx, rcx
0x180001564  mov     [rcx], rax
0x180001567  lea     rdx, [rcx+48h]
0x18000156b  lea     rax, ??_7CACHED_FILE_KEY@@6B@; const CACHED_FILE_KEY::`vftable'
0x180001572  mov     r8d, 5Ch ; '\'
0x180001578  mov     [rcx+8], rax
0x18000157c  add     rcx, 10h
0x180001580  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180001586  xor     edi, edi
0x180001588  mov     dword ptr [rbx+100h], 4C494643h
0x180001592  xor     eax, eax
0x180001594  mov     [rbx+148h], rdi
0x18000159b  mov     [rbx+150h], rdi
0x1800015a2  lea     rdx, [rbx+1E0h]
0x1800015a9  mov     qword ptr [rbx+104h], 1
0x1800015b4  lea     rcx, [rbx+1B0h]
0x1800015bb  mov     word ptr [rbx+140h], 100h
0x1800015c4  mov     r8d, 100h
0x1800015ca  mov     [rbx+158h], rax
0x1800015d1  mov     [rbx+160h], rax
0x1800015d8  mov     [rbx+168h], rdi
0x1800015df  mov     [rbx+170h], di
0x1800015e6  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800015ec  mov     rcx, cs:?g_pTraceLog@@3PEAU_TRACE_LOG@@EA; _TRACE_LOG * g_pTraceLog
0x1800015f3  mov     [rbx+2E0h], edi
0x1800015f9  mov     [rbx+2E8h], rdi
0x180001600  mov     [rbx+338h], rdi
0x180001607  test    rcx, rcx
0x18000160a  jnz     short loc_18000161A
0x18000160c  mov     rax, rbx
0x18000160f  mov     rbx, [rsp+28h+arg_0]
0x180001614  add     rsp, 20h
0x180001618  pop     rdi
0x180001619  retn
0x18000161a  mov     r8, rbx
0x18000161d  mov     edx, 1
0x180001622  call    cs:__imp_WriteRefTraceLog
0x180001628  jmp     short loc_18000160C
```
