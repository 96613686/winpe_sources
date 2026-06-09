# EdpToast::GetAction1Text(ushort * *)

- ea: `0x1800089b0`
- end: `0x1800089da`
- name: `?GetAction1Text@EdpToast@@UEAAJPEAPEAG@Z`
- size: `42`
- prototype: `__int64 __fastcall(EdpToast *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800056c4`

## string_xrefs

- `0x1800089b9`: `ds\security\efs\edptask\toast\edptoast.cpp`

## pseudocode

```c
__int64 __fastcall EdpToast::GetAction1Text(EdpToast *this, unsigned __int16 **a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x124,
    (unsigned int)"ds\\security\\efs\\edptask\\toast\\edptoast.cpp",
    (const char *)0x8000FFFFLL,
    v3);
  return 2147549183LL;
}

```

## disassembly

```asm
0x1800089b0  sub     rsp, 28h
0x1800089b4  mov     rcx, [rsp+28h]; this
0x1800089b9  lea     r8, aDsSecurityEfsE; "ds\\security\\efs\\edptask\\toast\\edpt"...
0x1800089c0  mov     r9d, 8000FFFFh; char *
0x1800089c6  mov     edx, 124h; void *
0x1800089cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800089d0  mov     eax, 8000FFFFh
0x1800089d5  add     rsp, 28h
0x1800089d9  retn
```
