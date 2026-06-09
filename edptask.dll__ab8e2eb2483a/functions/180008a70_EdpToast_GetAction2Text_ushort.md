# EdpToast::GetAction2Text(ushort * *)

- ea: `0x180008a70`
- end: `0x180008a9a`
- name: `?GetAction2Text@EdpToast@@UEAAJPEAPEAG@Z`
- size: `42`
- prototype: `__int64 __fastcall(EdpToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`

## string_xrefs

- `0x180008a79`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpToast::GetAction2Text(EdpToast *this, unsigned __int16 **a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x125,
    (unsigned int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
    (const char *)0x8000FFFFLL,
    v3);
  return 2147549183LL;
}

```

## disassembly

```asm
0x180008a70  sub     rsp, 28h
0x180008a74  mov     rcx, [rsp+28h]; this
0x180008a79  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x180008a80  mov     r9d, 8000FFFFh; char *
0x180008a86  mov     edx, 125h; void *
0x180008a8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a90  mov     eax, 8000FFFFh
0x180008a95  add     rsp, 28h
0x180008a99  retn
```
