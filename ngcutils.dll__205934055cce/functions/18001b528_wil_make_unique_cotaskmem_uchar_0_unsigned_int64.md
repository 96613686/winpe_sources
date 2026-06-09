# wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)

- ea: `0x18001b528`
- end: `0x18001b594`
- name: `??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `108`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b8f0`
- `0x18001bd40`
- `0x18001c130`
- `0x18001c300`
- `0x18001c4e0`
- `0x18001c6c0`

## callees

- `0x18001ae50`
- `0x18001b528`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b548`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001b548`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_cotaskmem<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  unsigned int v5; // r8d
  const char *v6; // r9
  _BYTE *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = CoTaskMemAlloc(a2);
  *a1 = v4;
  if ( v4 )
  {
    v7 = &v4[a2];
    while ( v4 != v7 )
      *v4++ = 0;
  }
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1854, v5, v6);
  return a1;
}

```

## disassembly

```asm
0x18001b528  mov     [rsp+arg_8], rbx
0x18001b52d  mov     [rsp+arg_0], rcx
0x18001b532  push    rdi
0x18001b533  sub     rsp, 30h
0x18001b537  mov     rdi, rdx
0x18001b53a  mov     rbx, rcx
0x18001b53d  mov     [rsp+38h+var_18], 0
0x18001b545  mov     rcx, rdx; cb
0x18001b548  call    cs:__imp_CoTaskMemAlloc
0x18001b54e  mov     [rbx], rax
0x18001b551  test    rax, rax
0x18001b554  jz      short loc_18001B568
0x18001b556  lea     rcx, [rax+rdi]
0x18001b55a  jmp     short loc_18001B563
0x18001b55c  xor     edx, edx
0x18001b55e  mov     [rax], dl
0x18001b560  inc     rax
0x18001b563  cmp     rax, rcx
0x18001b566  jnz     short loc_18001B55C
0x18001b568  mov     [rsp+38h+var_18], 1
0x18001b570  mov     rcx, [rsp+38h]; this
0x18001b575  cmp     qword ptr [rbx], 0
0x18001b579  jz      short loc_18001B589
0x18001b57b  mov     rax, rbx
0x18001b57e  mov     rbx, [rsp+38h+arg_8]
0x18001b583  add     rsp, 30h
0x18001b587  pop     rdi
0x18001b588  retn
0x18001b589  mov     edx, 1854h; void *
0x18001b58e  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
