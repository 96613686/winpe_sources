# W3_CGI_HANDLER::CGIStartProcessing(void)

- ea: `0x180003088`
- end: `0x180003139`
- name: `?CGIStartProcessing@W3_CGI_HANDLER@@AEAAJXZ`
- size: `177`
- prototype: `__int64 __fastcall(W3_CGI_HANDLER *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000337c`

## callees

- `0x180002d28`
- `0x180003088`
- `0x180008010`

## import_xrefs

- `msvcrt!atol` at `0x1800030d3`
- `msvcrt!atol` at `0x1800030d3`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::CGIStartProcessing(W3_CGI_HANDLER *this)
{
  __int64 v2; // rcx
  __int64 v3; // rax
  const char *v4; // rax
  __int64 v5; // rax
  __int16 v7; // [rsp+30h] [rbp+8h] BYREF
  int v8; // [rsp+38h] [rbp+10h] BYREF

  *((_DWORD *)this + 2) = 1;
  v2 = *((_QWORD *)this + 6);
  v7 = 0;
  v3 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 24LL))(v2);
  v4 = (const char *)(*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v3 + 16LL))(v3, 11, 0);
  if ( v4 )
  {
    *((_DWORD *)this + 15) = atol(v4);
  }
  else
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 6) + 24LL))(*((_QWORD *)this + 6));
    if ( (*(__int64 (__fastcall **)(__int64, __int64, __int16 *))(*(_QWORD *)v5 + 16LL))(v5, 6, &v7) && v7 )
      *((_DWORD *)this + 15) = -1;
  }
  v8 = 0;
  return W3_CGI_HANDLER::CGIContinueOnPipeCompletion(this, &v8);
}

```

## disassembly

```asm
0x180003088  mov     [rsp+arg_10], rbx
0x18000308d  push    rdi
0x18000308e  sub     rsp, 20h
0x180003092  mov     dword ptr [rcx+8], 1
0x180003099  mov     rbx, rcx
0x18000309c  mov     rcx, [rcx+30h]
0x1800030a0  xor     edi, edi
0x1800030a2  mov     [rsp+28h+arg_0], di
0x1800030a7  mov     rax, [rcx]
0x1800030aa  mov     rax, [rax+18h]
0x1800030ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b3  mov     r9, rax
0x1800030b6  lea     edx, [rdi+0Bh]
0x1800030b9  xor     r8d, r8d
0x1800030bc  mov     rcx, [rax]
0x1800030bf  mov     rax, [rcx+10h]
0x1800030c3  mov     rcx, r9
0x1800030c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030cb  test    rax, rax
0x1800030ce  jz      short loc_1800030DE
0x1800030d0  mov     rcx, rax; String
0x1800030d3  call    cs:__imp_atol
0x1800030d9  mov     [rbx+3Ch], eax
0x1800030dc  jmp     short loc_18000311D
0x1800030de  mov     rcx, [rbx+30h]
0x1800030e2  mov     rax, [rcx]
0x1800030e5  mov     rax, [rax+18h]
0x1800030e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ee  mov     r9, rax
0x1800030f1  lea     r8, [rsp+28h+arg_0]
0x1800030f6  mov     edx, 6
0x1800030fb  mov     rcx, [rax]
0x1800030fe  mov     rax, [rcx+10h]
0x180003102  mov     rcx, r9
0x180003105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000310a  test    rax, rax
0x18000310d  jz      short loc_18000311D
0x18000310f  cmp     [rsp+28h+arg_0], di
0x180003114  jz      short loc_18000311D
0x180003116  mov     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x18000311d  lea     rdx, [rsp+28h+arg_8]; int *
0x180003122  mov     [rsp+28h+arg_8], edi
0x180003126  mov     rcx, rbx; this
0x180003129  call    ?CGIContinueOnPipeCompletion@W3_CGI_HANDLER@@AEAAJPEAH@Z; W3_CGI_HANDLER::CGIContinueOnPipeCompletion(int *)
0x18000312e  mov     rbx, [rsp+28h+arg_10]
0x180003133  add     rsp, 20h
0x180003137  pop     rdi
0x180003138  retn
```
