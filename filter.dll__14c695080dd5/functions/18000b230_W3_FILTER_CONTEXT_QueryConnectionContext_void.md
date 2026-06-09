# W3_FILTER_CONTEXT::QueryConnectionContext(void)

- ea: `0x18000b230`
- end: `0x18000b3a3`
- name: `?QueryConnectionContext@W3_FILTER_CONTEXT@@QEAAPEAVW3_FILTER_CONNECTION_CONTEXT@@XZ`
- size: `371`
- prototype: `struct W3_FILTER_CONNECTION_CONTEXT *__fastcall(W3_FILTER_CONTEXT *__hidden this)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180002fc0`
- `0x18000a710`
- `0x18000b1e8`
- `0x18000c648`

## callees

- `0x180006790`
- `0x1800088bc`
- `0x18000b230`
- `0x18000c614`
- `0x18000c91e`
- `0x18000d010`

## pseudocode

```c
struct W3_FILTER_CONNECTION_CONTEXT *__fastcall W3_FILTER_CONTEXT::QueryConnectionContext(W3_FILTER_CONTEXT *this)
{
  struct W3_FILTER_CONNECTION_CONTEXT *result; // rax
  __int64 v3; // rax
  __int64 v4; // r14
  __int64 (__fastcall ***v5)(_QWORD, void *); // rax
  __int64 v6; // rax
  _QWORD *v7; // rbx
  W3_FILTER_CONTEXT *v8; // rcx
  W3_FILTER_CONTEXT *v9; // rsi
  W3_FILTER_CONTEXT *v10; // rsi
  bool v11; // zf
  __int64 v12; // rax

  result = (struct W3_FILTER_CONNECTION_CONTEXT *)*((_QWORD *)this + 33);
  if ( !result )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 16LL))(*((_QWORD *)this + 3));
    v4 = v3;
    if ( v3 )
    {
      v5 = (__int64 (__fastcall ***)(_QWORD, void *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
      v6 = (**v5)(v5, g_pFilterModuleContext);
      v7 = (_QWORD *)v6;
      if ( v6 )
      {
        v8 = *(W3_FILTER_CONTEXT **)(v6 + 832);
        v9 = 0;
        if ( !*((_DWORD *)this + 4) )
          v9 = this;
        if ( v8 )
        {
          W3_FILTER_CONTEXT::DereferenceFilterContext(v8);
          v7[104] = 0;
        }
        if ( v9 )
        {
          W3_FILTER_CONTEXT::ReferenceFilterContext(v9);
          v7[104] = v9;
        }
LABEL_10:
        *((_QWORD *)this + 33) = v7;
        return (struct W3_FILTER_CONNECTION_CONTEXT *)v7;
      }
      v7 = operator new(0x348u);
      if ( v7 )
      {
        v10 = 0;
        v11 = *((_DWORD *)this + 4) == 0;
        *v7 = &W3_FILTER_CONNECTION_CONTEXT::`vftable';
        if ( v11 )
          v10 = this;
        *((_DWORD *)v7 + 2) = 1;
        if ( v10 )
          W3_FILTER_CONTEXT::ReferenceFilterContext(v10);
        v7[104] = v10;
        v7[103] = v7 + 102;
        v7[102] = v7 + 102;
        memset_0(v7 + 2, 0, 0x190u);
        memset_0(v7 + 52, 0, 0x190u);
        v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
        if ( (*(int (__fastcall **)(__int64, _QWORD *, void *))(*(_QWORD *)v12 + 8LL))(v12, v7, g_pFilterModuleContext) >= 0 )
          goto LABEL_10;
        (*(void (__fastcall **)(_QWORD *))*v7)(v7);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000b230  push    rbx
0x18000b232  push    rsi
0x18000b233  push    rdi
0x18000b234  push    r14
0x18000b236  sub     rsp, 28h
0x18000b23a  mov     rax, [rcx+108h]
0x18000b241  mov     rdi, rcx
0x18000b244  test    rax, rax
0x18000b247  jnz     loc_18000B399
0x18000b24d  mov     rcx, [rcx+18h]
0x18000b251  mov     rax, [rcx]
0x18000b254  mov     rax, [rax+10h]
0x18000b258  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b25d  mov     r14, rax
0x18000b260  test    rax, rax
0x18000b263  jz      loc_18000B397
0x18000b269  mov     rcx, [rax]
0x18000b26c  mov     rax, [rcx+10h]
0x18000b270  mov     rcx, r14
0x18000b273  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b278  mov     rdx, cs:?g_pFilterModuleContext@@3PEAXEA; void * g_pFilterModuleContext
0x18000b27f  mov     r8, rax
0x18000b282  mov     rcx, [rax]
0x18000b285  mov     rax, [rcx]
0x18000b288  mov     rcx, r8
0x18000b28b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b290  mov     rbx, rax
0x18000b293  test    rax, rax
0x18000b296  jz      short loc_18000B2E0
0x18000b298  mov     rcx, [rax+340h]; this
0x18000b29f  xor     esi, esi
0x18000b2a1  cmp     [rdi+10h], esi
0x18000b2a4  cmovz   rsi, rdi
0x18000b2a8  test    rcx, rcx
0x18000b2ab  jz      short loc_18000B2BD
0x18000b2ad  call    ?DereferenceFilterContext@W3_FILTER_CONTEXT@@QEAAXXZ; W3_FILTER_CONTEXT::DereferenceFilterContext(void)
0x18000b2b2  mov     qword ptr [rbx+340h], 0
0x18000b2bd  test    rsi, rsi
0x18000b2c0  jz      short loc_18000B2D1
0x18000b2c2  mov     rcx, rsi; this
0x18000b2c5  call    ?ReferenceFilterContext@W3_FILTER_CONTEXT@@QEAAXXZ; W3_FILTER_CONTEXT::ReferenceFilterContext(void)
0x18000b2ca  mov     [rbx+340h], rsi
0x18000b2d1  mov     [rdi+108h], rbx
0x18000b2d8  mov     rax, rbx
0x18000b2db  jmp     loc_18000B399
0x18000b2e0  mov     ecx, 348h; Size
0x18000b2e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b2ea  mov     rbx, rax
0x18000b2ed  test    rax, rax
0x18000b2f0  jz      loc_18000B397
0x18000b2f6  xor     esi, esi
0x18000b2f8  lea     rax, ??_7W3_FILTER_CONNECTION_CONTEXT@@6B@; const W3_FILTER_CONNECTION_CONTEXT::`vftable'
0x18000b2ff  cmp     [rdi+10h], esi
0x18000b302  mov     [rbx], rax
0x18000b305  cmovz   rsi, rdi
0x18000b309  mov     dword ptr [rbx+8], 1
0x18000b310  test    rsi, rsi
0x18000b313  jz      short loc_18000B31D
0x18000b315  mov     rcx, rsi; this
0x18000b318  call    ?ReferenceFilterContext@W3_FILTER_CONTEXT@@QEAAXXZ; W3_FILTER_CONTEXT::ReferenceFilterContext(void)
0x18000b31d  mov     [rbx+340h], rsi
0x18000b324  lea     rax, [rbx+330h]
0x18000b32b  mov     esi, 190h
0x18000b330  mov     [rax+8], rax
0x18000b334  mov     r8d, esi; Size
0x18000b337  mov     [rax], rax
0x18000b33a  lea     rcx, [rbx+10h]; void *
0x18000b33e  xor     edx, edx; Val
0x18000b340  call    memset_0
0x18000b345  lea     rcx, [rbx+1A0h]; void *
0x18000b34c  mov     r8d, esi; Size
0x18000b34f  xor     edx, edx; Val
0x18000b351  call    memset_0
0x18000b356  mov     rax, [r14]
0x18000b359  mov     rcx, r14
0x18000b35c  mov     rax, [rax+10h]
0x18000b360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b365  mov     r8, cs:?g_pFilterModuleContext@@3PEAXEA; void * g_pFilterModuleContext
0x18000b36c  mov     r9, rax
0x18000b36f  mov     rdx, rbx
0x18000b372  mov     rcx, [rax]
0x18000b375  mov     rax, [rcx+8]
0x18000b379  mov     rcx, r9
0x18000b37c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b381  test    eax, eax
0x18000b383  jns     loc_18000B2D1
0x18000b389  mov     rax, [rbx]
0x18000b38c  mov     rcx, rbx
0x18000b38f  mov     rax, [rax]
0x18000b392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b397  xor     eax, eax
0x18000b399  add     rsp, 28h
0x18000b39d  pop     r14
0x18000b39f  pop     rdi
0x18000b3a0  pop     rsi
0x18000b3a1  pop     rbx
0x18000b3a2  retn
```
