# AikEnrollTask::RemoveTrigger(void)

- ea: `0x180016144`
- end: `0x1800161eb`
- name: `?RemoveTrigger@AikEnrollTask@@QEAAJXZ`
- size: `167`
- prototype: `__int64 __fastcall(AikEnrollTask *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180016570`

## callees

- `0x18000cc34`
- `0x180016144`
- `0x180022010`

## string_xrefs

- `0x18001615d`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`
- `0x1800161bf`: `onecore\ds\security\ngc\ngctask\dll\reschedule.cpp`

## pseudocode

```c
__int64 __fastcall AikEnrollTask::RemoveTrigger(AikEnrollTask *this)
{
  int v1; // eax
  int v4; // eax
  unsigned int v5; // edi
  int v6[4]; // [rsp+20h] [rbp-28h] BYREF
  __int64 v7; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *((_DWORD *)this + 8);
  if ( v1 )
  {
    *(_OWORD *)v6 = 0;
    v6[2] = v1;
    v7 = 0;
    LOWORD(v6[0]) = 3;
    v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)this + 3) + 88LL))(*((_QWORD *)this + 3), v6);
    v5 = v4;
    if ( v4 >= 0 )
    {
      *((_DWORD *)this + 8) = 0;
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
        (const char *)(unsigned int)v4,
        v6[0]);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x198,
      (unsigned int)"onecore\\ds\\security\\ngc\\ngctask\\dll\\reschedule.cpp",
      (const char *)0x8007139FLL,
      v6[0]);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x180016144  mov     [rsp+arg_0], rbx
0x180016149  push    rdi
0x18001614a  sub     rsp, 40h
0x18001614e  mov     eax, [rcx+20h]
0x180016151  mov     rbx, rcx
0x180016154  test    eax, eax
0x180016156  jnz     short loc_18001617A
0x180016158  mov     rcx, [rsp+48h]; this
0x18001615d  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x180016164  mov     ebx, 8007139Fh
0x180016169  mov     edx, 198h; void *
0x18001616e  mov     r9d, ebx; char *
0x180016171  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016176  mov     eax, ebx
0x180016178  jmp     short loc_1800161E0
0x18001617a  xor     edx, edx
0x18001617c  xorps   xmm0, xmm0
0x18001617f  movups  xmmword ptr [rsp+48h+var_28], xmm0
0x180016184  mov     [rsp+48h+var_28+8], eax
0x180016188  mov     [rsp+48h+var_18], rdx
0x18001618d  lea     ecx, [rdx+3]
0x180016190  mov     word ptr [rsp+48h+var_28], cx
0x180016195  lea     rdx, [rsp+48h+var_28]
0x18001619a  mov     rcx, [rbx+18h]
0x18001619e  movups  xmm0, xmmword ptr [rsp+48h+var_28]
0x1800161a3  mov     rax, [rcx]
0x1800161a6  movaps  xmmword ptr [rsp+48h+var_28], xmm0; int
0x1800161ab  mov     rax, [rax+58h]
0x1800161af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161b4  mov     edi, eax
0x1800161b6  test    eax, eax
0x1800161b8  jns     short loc_1800161D7
0x1800161ba  mov     rcx, [rsp+48h]; this
0x1800161bf  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\ngc\\ngctask\\dl"...
0x1800161c6  mov     r9d, eax; char *
0x1800161c9  mov     edx, 19Fh; void *
0x1800161ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800161d3  mov     eax, edi
0x1800161d5  jmp     short loc_1800161E0
0x1800161d7  mov     dword ptr [rbx+20h], 0
0x1800161de  xor     eax, eax
0x1800161e0  mov     rbx, [rsp+48h+arg_0]
0x1800161e5  add     rsp, 40h
0x1800161e9  pop     rdi
0x1800161ea  retn
```
