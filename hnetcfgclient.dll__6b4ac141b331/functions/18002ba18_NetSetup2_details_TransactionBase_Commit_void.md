# NetSetup2::details::TransactionBase::Commit(void)

- ea: `0x18002ba18`
- end: `0x18002ba48`
- name: `?Commit@TransactionBase@details@NetSetup2@@QEAAXXZ`
- size: `48`
- prototype: `void __fastcall(NetSetup2::details::TransactionBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180025484`
- `0x180025e80`
- `0x180026144`

## callees

- `0x180026c18`
- `0x18002ba18`

## import_xrefs

- `NetSetupApi!NetSetupCommit` at `0x18002ba1f`
- `NetSetupApi!NetSetupCommit` at `0x18002ba1f`

## pseudocode

```c
void __fastcall NetSetup2::details::TransactionBase::Commit(NetSetup2::details::TransactionBase *this)
{
  int v1; // eax
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = NetSetupCommit(*(_QWORD *)this);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61C,
      (unsigned int)"onecore\\internal\\net\\inc\\NetSetupCxx.cpp",
      (const char *)(unsigned int)v1,
      v2);
}

```

## disassembly

```asm
0x18002ba18  sub     rsp, 28h
0x18002ba1c  mov     rcx, [rcx]
0x18002ba1f  call    cs:__imp_NetSetupCommit
0x18002ba25  test    eax, eax
0x18002ba27  jns     short loc_18002BA43
0x18002ba29  mov     rcx, [rsp+28h]; this
0x18002ba2e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\net\\inc\\NetSetupCx"...
0x18002ba35  mov     r9d, eax; char *
0x18002ba38  mov     edx, 61Ch; void *
0x18002ba3d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba43  add     rsp, 28h
0x18002ba47  retn
```
