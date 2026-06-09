# CLogFileCtrl::InitializeLog(char const *,char const *,char *)

- ea: `0x180002a20`
- end: `0x180002a7d`
- name: `?InitializeLog@CLogFileCtrl@@UEAAJPEBD0PEAD@Z`
- size: `93`
- prototype: `__int64 __fastcall(CLogFileCtrl *__hidden this, const char *, const char *, char *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180004c70`

## callees

- `0x180010010`

## import_xrefs

- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180002a3c`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180002a4c`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180002a3c`
- `IisRTL!?Copy@STR@@QEAAHPEBD@Z` at `0x180002a4c`

## pseudocode

```c
__int64 __fastcall CLogFileCtrl::InitializeLog(CLogFileCtrl *this, const char *a2, const char *a3, char *a4)
{
  __int64 v7; // rax

  STR::Copy((CLogFileCtrl *)((char *)this + 128), a2);
  STR::Copy((CLogFileCtrl *)((char *)this + 184), a3);
  v7 = *(_QWORD *)this;
  *((_QWORD *)this + 8) = a4;
  (*(void (__fastcall **)(CLogFileCtrl *, const char *, char *))(v7 + 88))(this, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x180002a20  mov     [rsp+arg_0], rbx
0x180002a25  mov     [rsp+arg_8], rsi
0x180002a2a  push    rdi
0x180002a2b  sub     rsp, 20h
0x180002a2f  mov     rbx, rcx
0x180002a32  mov     rdi, r9
0x180002a35  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180002a39  mov     rsi, r8
0x180002a3c  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180002a42  lea     rcx, [rbx+0B8h]
0x180002a49  mov     rdx, rsi
0x180002a4c  call    cs:__imp_?Copy@STR@@QEAAHPEBD@Z; STR::Copy(char const *)
0x180002a52  mov     rax, [rbx]
0x180002a55  mov     r8, rdi
0x180002a58  mov     rdx, rsi
0x180002a5b  mov     [rbx+40h], rdi
0x180002a5f  mov     rcx, rbx
0x180002a62  mov     rax, [rax+58h]
0x180002a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6b  mov     rbx, [rsp+28h+arg_0]
0x180002a70  xor     eax, eax
0x180002a72  mov     rsi, [rsp+28h+arg_8]
0x180002a77  add     rsp, 20h
0x180002a7b  pop     rdi
0x180002a7c  retn
```
