# LogRemoveDirectoryTreeError(ushort const *,ActionType,long,void *)

- ea: `0x1800064b0`
- end: `0x180006513`
- name: `?LogRemoveDirectoryTreeError@@YAJPEBGW4ActionType@@JPEAX@Z`
- size: `99`
- prototype: `int __high(const unsigned __int16 *, enum ActionType, int, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005174`
- `0x180006520`

## string_xrefs

- `0x1800064d7`: `onecore\ds\security\gina\profile\profext\appcontainer.cpp`
- `0x1800064f4`: `RemoveDirectoryTree %ls %u`

## pseudocode

```c
__int64 __fastcall LogRemoveDirectoryTreeError(const WCHAR *a1, int a2, unsigned int a3)
{
  int v6; // [rsp+30h] [rbp-28h]
  char *v7; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v7 = 0;
  GetPostProfilePathIfExists(a1, (const unsigned __int16 **)&v7);
  v6 = a2;
  wil::details::in1diag3::Log_IfWin32ErrorMsg(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\appcontainer.cpp",
    (const char *)a3,
    (unsigned int)"RemoveDirectoryTree %ls %u",
    v7,
    v6);
  return a3;
}

```

## disassembly

```asm
0x1800064b0  mov     [rsp+arg_0], rbx
0x1800064b5  push    rdi
0x1800064b6  sub     rsp, 50h
0x1800064ba  mov     ebx, edx
0x1800064bc  mov     [rsp+58h+var_18], 0
0x1800064c5  lea     rdx, [rsp+58h+var_18]; unsigned __int16 **
0x1800064ca  mov     edi, r8d
0x1800064cd  call    ?GetPostProfilePathIfExists@@YAXPEBGPEAPEBG@Z; GetPostProfilePathIfExists(ushort const *,ushort const * *)
0x1800064d2  mov     rax, [rsp+58h+var_18]
0x1800064d7  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800064de  mov     rcx, [rsp+58h]; this
0x1800064e3  mov     r9d, edi; char *
0x1800064e6  mov     [rsp+58h+var_28], ebx
0x1800064ea  mov     edx, 5Dh ; ']'; void *
0x1800064ef  mov     [rsp+58h+var_30], rax; char *
0x1800064f4  lea     rax, aRemovedirector; "RemoveDirectoryTree %ls %u"
0x1800064fb  mov     qword ptr [rsp+58h+var_38], rax; unsigned int
0x180006500  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x180006505  mov     rbx, [rsp+58h+arg_0]
0x18000650a  mov     eax, edi
0x18000650c  add     rsp, 50h
0x180006510  pop     rdi
0x180006511  retn
```
