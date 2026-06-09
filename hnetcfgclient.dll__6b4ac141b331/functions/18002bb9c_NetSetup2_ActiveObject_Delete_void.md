# NetSetup2::ActiveObject::Delete(void)

- ea: `0x18002bb9c`
- end: `0x18002bbe1`
- name: `?Delete@ActiveObject@NetSetup2@@QEAAXXZ`
- size: `69`
- prototype: `void __fastcall(NetSetup2::ActiveObject *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callers

- `0x180025484`
- `0x180025e80`

## callees

- `0x180026c18`
- `0x18002bb9c`

## import_xrefs

- `NetSetupApi!NetSetupDeleteObject` at `0x18002bbb8`
- `NetSetupApi!NetSetupDeleteObject` at `0x18002bbb8`

## pseudocode

```c
void __fastcall NetSetup2::ActiveObject::Delete(NetSetup2::ActiveObject *this)
{
  __int128 v1; // xmm0
  __int64 v2; // rdx
  _QWORD *v3; // rcx
  int v4; // eax
  int v5[6]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v1 = *(_OWORD *)((char *)this + 20);
  v2 = *((unsigned int *)this + 4);
  v3 = *(_QWORD **)this;
  *(_OWORD *)v5 = v1;
  v4 = NetSetupDeleteObject(*v3, v2, v5);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4BA,
      (unsigned int)"onecore\\internal\\net\\inc\\NetSetupCxx.cpp",
      (const char *)(unsigned int)v4,
      v5[0]);
}

```

## disassembly

```asm
0x18002bb9c  sub     rsp, 38h
0x18002bba0  movups  xmm0, xmmword ptr [rcx+14h]
0x18002bba4  mov     edx, [rcx+10h]
0x18002bba7  lea     r8, [rsp+38h+var_18]
0x18002bbac  mov     rcx, [rcx]
0x18002bbaf  movdqu  xmmword ptr [rsp+38h+var_18], xmm0; int
0x18002bbb5  mov     rcx, [rcx]
0x18002bbb8  call    cs:__imp_NetSetupDeleteObject
0x18002bbbe  test    eax, eax
0x18002bbc0  jns     short loc_18002BBDC
0x18002bbc2  mov     rcx, [rsp+38h]; this
0x18002bbc7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\net\\inc\\NetSetupCx"...
0x18002bbce  mov     r9d, eax; char *
0x18002bbd1  mov     edx, 4BAh; void *
0x18002bbd6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002bbdc  add     rsp, 38h
0x18002bbe0  retn
```
