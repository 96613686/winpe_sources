# SetAikTimeTrigger(_FILETIME const *)

- ea: `0x180016440`
- end: `0x180016488`
- name: `?SetAikTimeTrigger@@YAJPEBU_FILETIME@@@Z`
- size: `72`
- prototype: `int(const struct _FILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001417c`

## callees

- `0x18000cc34`
- `0x180015310`
- `0x180016440`

## string_xrefs

- `0x180016468`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 __fastcall SetAikTimeTrigger(const struct _FILETIME *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  const struct _FILETIME *v6; // [rsp+30h] [rbp+8h] BYREF
  const struct _FILETIME **v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = a1;
  v7 = &v6;
  v1 = HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942_(&v7);
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x245,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180016440  mov     r11, rsp
0x180016443  mov     [r11+8], rcx
0x180016447  push    rbx; int
0x180016448  sub     rsp, 20h
0x18001644c  lea     rax, [r11+8]
0x180016450  lea     rcx, [r11+10h]
0x180016454  mov     [r11+10h], rax
0x180016458  call    HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942___; HResultErrorContract__lambda_f6a8150e6f06a07b5fbe280d1ddcf942_
0x18001645d  mov     ebx, eax
0x18001645f  test    eax, eax
0x180016461  jns     short loc_180016480
0x180016463  mov     rcx, [rsp+28h]; this
0x180016468  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x18001646f  mov     r9d, eax; char *
0x180016472  mov     edx, 245h; void *
0x180016477  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001647c  mov     eax, ebx
0x18001647e  jmp     short loc_180016482
0x180016480  xor     eax, eax
0x180016482  add     rsp, 20h
0x180016486  pop     rbx
0x180016487  retn
```
