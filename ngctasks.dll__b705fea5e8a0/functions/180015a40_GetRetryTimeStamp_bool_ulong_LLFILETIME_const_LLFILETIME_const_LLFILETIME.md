# GetRetryTimeStamp(bool,ulong,_LLFILETIME const *,_LLFILETIME const *,_LLFILETIME *)

- ea: `0x180015a40`
- end: `0x180015ab6`
- name: `?GetRetryTimeStamp@@YAJ_NKPEBU_LLFILETIME@@1PEAU1@@Z`
- size: `118`
- prototype: `__int64 __fastcall(char, int, const struct _LLFILETIME *, const struct _LLFILETIME *, struct _LLFILETIME *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001417c`

## callees

- `0x18000cc34`
- `0x1800152e8`
- `0x180015a40`

## string_xrefs

- `0x180015a95`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 __fastcall GetRetryTimeStamp(
        char a1,
        int a2,
        const struct _LLFILETIME *a3,
        const struct _LLFILETIME *a4,
        struct _LLFILETIME *a5)
{
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD v8[7]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+10h]
  char v10; // [rsp+70h] [rbp+18h] BYREF
  int v11; // [rsp+78h] [rbp+20h] BYREF
  const struct _LLFILETIME *v12; // [rsp+80h] [rbp+28h] BYREF
  const struct _LLFILETIME *v13; // [rsp+88h] [rbp+30h] BYREF

  v13 = a4;
  v12 = a3;
  v11 = a2;
  v10 = a1;
  v8[0] = &a5;
  v8[1] = &v10;
  v8[2] = &v11;
  v8[3] = &v13;
  v8[4] = &v12;
  v5 = HResultErrorContract__lambda_cd7731b57602146267a7816806e106a2_(v8);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9A,
    (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
    (const char *)(unsigned int)v5,
    v8[0]);
  return v6;
}

```

## disassembly

```asm
0x180015a40  mov     rax, rsp
0x180015a43  mov     [rax+20h], r9
0x180015a47  mov     [rax+18h], r8
0x180015a4b  mov     [rax+10h], edx
0x180015a4e  mov     [rax+8], cl
0x180015a51  push    rbp
0x180015a52  push    rbx
0x180015a53  mov     rbp, rsp
0x180015a56  sub     rsp, 58h
0x180015a5a  lea     rax, [rbp+arg_20]
0x180015a5e  mov     [rbp+var_38], rax
0x180015a62  lea     rcx, [rbp+var_38]
0x180015a66  lea     rax, [rbp+arg_0]
0x180015a6a  mov     [rbp+var_30], rax
0x180015a6e  lea     rax, [rbp+arg_8]
0x180015a72  mov     [rbp+var_28], rax
0x180015a76  lea     rax, [rbp+arg_18]
0x180015a7a  mov     [rbp+var_20], rax
0x180015a7e  lea     rax, [rbp+arg_10]
0x180015a82  mov     [rbp+var_18], rax
0x180015a86  call    HResultErrorContract__lambda_cd7731b57602146267a7816806e106a2___; HResultErrorContract__lambda_cd7731b57602146267a7816806e106a2_
0x180015a8b  mov     ebx, eax
0x180015a8d  test    eax, eax
0x180015a8f  jns     short loc_180015AAD
0x180015a91  mov     rcx, [rbp+10h]; this
0x180015a95  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180015a9c  mov     r9d, eax; char *
0x180015a9f  mov     edx, 9Ah; void *
0x180015aa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015aa9  mov     eax, ebx
0x180015aab  jmp     short loc_180015AAF
0x180015aad  xor     eax, eax
0x180015aaf  add     rsp, 58h
0x180015ab3  pop     rbx
0x180015ab4  pop     rbp
0x180015ab5  retn
```
