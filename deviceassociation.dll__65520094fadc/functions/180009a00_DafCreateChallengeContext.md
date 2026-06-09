# DafCreateChallengeContext

- ea: `0x180009a00`
- end: `0x180009a8b`
- name: `DafCreateChallengeContext`
- size: `139`
- prototype: `__int64 __fastcall(__int64, struct _DAC_CLIENT_CONTEXT **)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009aa0`

## callees

- `0x180002284`
- `0x180002f10`
- `0x180009a00`
- `0x18000bbc2`

## pseudocode

```c
__int64 __fastcall DafCreateChallengeContext(__int64 a1, struct _DAC_CLIENT_CONTEXT **a2)
{
  int v5; // [rsp+20h] [rbp-48h] BYREF
  __int64 v6; // [rsp+28h] [rbp-40h]

  memset_0(&v5, 0, 0x40u);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids);
  if ( !a1 || !a2 )
    return 2147942487LL;
  *a2 = 0;
  v5 = 4;
  v6 = a1;
  return CreateContext((struct _DAC_CREATE_CONTEXT_PARAMS *)&v5, a2);
}

```

## disassembly

```asm
0x180009a00  mov     [rsp+arg_0], rbx
0x180009a05  push    rdi
0x180009a06  sub     rsp, 60h
0x180009a0a  mov     rbx, rdx
0x180009a0d  mov     rdi, rcx
0x180009a10  xor     edx, edx; Val
0x180009a12  lea     rcx, [rsp+68h+var_48]; void *
0x180009a17  lea     r8d, [rdx+40h]; Size
0x180009a1b  call    memset_0
0x180009a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a27  lea     rax, WPP_GLOBAL_Control
0x180009a2e  cmp     rcx, rax
0x180009a31  jz      short loc_180009A4E
0x180009a33  cmp     byte ptr [rcx+19h], 4
0x180009a37  jb      short loc_180009A4E
0x180009a39  mov     rcx, [rcx+10h]
0x180009a3d  lea     r8, WPP_303e45e916c7361cf38ffe655d6c194e_Traceguids
0x180009a44  mov     edx, 0Ah
0x180009a49  call    WPP_SF_s
0x180009a4e  test    rdi, rdi
0x180009a51  jz      short loc_180009A7B
0x180009a53  test    rbx, rbx
0x180009a56  jz      short loc_180009A7B
0x180009a58  mov     rdx, rbx; struct _DAC_CLIENT_CONTEXT **
0x180009a5b  mov     qword ptr [rbx], 0
0x180009a62  lea     rcx, [rsp+68h+var_48]; struct _DAC_CREATE_CONTEXT_PARAMS *
0x180009a67  mov     [rsp+68h+var_48], 4
0x180009a6f  mov     [rsp+68h+var_40], rdi
0x180009a74  call    ?CreateContext@@YAJPEAU_DAC_CREATE_CONTEXT_PARAMS@@PEAPEAU_DAC_CLIENT_CONTEXT@@@Z; CreateContext(_DAC_CREATE_CONTEXT_PARAMS *,_DAC_CLIENT_CONTEXT * *)
0x180009a79  jmp     short loc_180009A80
0x180009a7b  mov     eax, 80070057h
0x180009a80  mov     rbx, [rsp+68h+arg_0]
0x180009a85  add     rsp, 60h
0x180009a89  pop     rdi
0x180009a8a  retn
```
