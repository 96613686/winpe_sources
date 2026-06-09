# FltpAllocateStreamListCtrl

- ea: `0x180066590`
- end: `0x1800666ec`
- name: `FltpAllocateStreamListCtrl`
- size: `348`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180009f80`

## callees

- `0x180014c10`
- `0x180024c00`
- `0x180066590`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800665a9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1800665a9`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x1800665fe`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180066649`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x1800665fe`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x180066649`

## pseudocode

```c
__int64 __fastcall FltpAllocateStreamListCtrl(__int64 a1, __int64 a2, _QWORD *a3)
{
  _DWORD *v6; // rax
  _DWORD *v7; // rbx
  __int64 v8; // rcx

  v6 = ExAllocateFromNPagedLookasideList(&stru_18003EB40);
  v7 = v6;
  if ( !v6 )
    return 3221225626LL;
  *v6 = 28897793;
  v6[17] = 1;
  *((_QWORD *)v6 + 3) = a1;
  v6[16] = 0;
  *((_QWORD *)v6 + 6) = 0;
  *((_QWORD *)v6 + 4) = *(_QWORD *)(a2 + 24);
  *((_QWORD *)v6 + 5) = DeleteStreamListCtrlCallback;
  ExInitializeAutoExpandPushLock(v6 + 18, 1);
  memset(v7 + 22, 0, 0x80u);
  *((_QWORD *)v7 + 27) = 0;
  memset(v7 + 56, 0, 0x80u);
  *((_QWORD *)v7 + 44) = 0;
  ExInitializeAutoExpandPushLock(v7 + 92, 1);
  v7[1] = 0;
  *((_QWORD *)v7 + 48) = 0;
  *((_QWORD *)v7 + 50) = 0;
  v7[98] = 1;
  *((_QWORD *)v7 + 52) = 0;
  v7[102] = 3;
  *((_QWORD *)v7 + 54) = 0;
  v7[106] = 2;
  *((_QWORD *)v7 + 45) = 0;
  if ( (byte_1800404C2 & 1) != 0 )
    McTemplateU0spdd_EtwWriteTransfer(
      v8,
      (__int64)StreamListCtrlSup_c715,
      "FltpAllocateStreamListCtrl",
      v7,
      v7[16],
      v7[17]);
  *a3 = v7;
  return 0;
}

```

## disassembly

```asm
0x180066590  push    rbx
0x180066592  push    rbp
0x180066593  push    rsi
0x180066594  push    rdi
0x180066595  sub     rsp, 38h
0x180066599  mov     rbp, rcx
0x18006659c  mov     rsi, r8
0x18006659f  lea     rcx, stru_18003EB40; Lookaside
0x1800665a6  mov     rdi, rdx
0x1800665a9  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1800665b0  nop     dword ptr [rax+rax+00h]
0x1800665b5  mov     rbx, rax
0x1800665b8  test    rax, rax
0x1800665bb  jz      loc_1800666B7
0x1800665c1  mov     dword ptr [rax], 1B8F201h
0x1800665c7  lea     rcx, [rbx+48h]
0x1800665cb  mov     dword ptr [rax+44h], 1
0x1800665d2  mov     edx, 1
0x1800665d7  mov     [rax+18h], rbp
0x1800665db  mov     [rsp+58h+arg_0], r14
0x1800665e0  xor     r14d, r14d
0x1800665e3  mov     [rax+40h], r14d
0x1800665e7  mov     [rax+30h], r14
0x1800665eb  mov     rax, [rdi+18h]
0x1800665ef  mov     [rbx+20h], rax
0x1800665f3  lea     rax, DeleteStreamListCtrlCallback
0x1800665fa  mov     [rbx+28h], rax
0x1800665fe  call    cs:__imp_ExInitializeAutoExpandPushLock
0x180066605  nop     dword ptr [rax+rax+00h]
0x18006660a  xor     edx, edx; Val
0x18006660c  lea     rcx, [rbx+58h]; void *
0x180066610  mov     r8d, 80h; Size
0x180066616  call    memset
0x18006661b  xor     edx, edx; Val
0x18006661d  mov     [rbx+0D8h], r14
0x180066624  mov     r8d, 80h; Size
0x18006662a  lea     rcx, [rbx+0E0h]; void *
0x180066631  call    memset
0x180066636  lea     rcx, [rbx+170h]
0x18006663d  mov     [rbx+160h], r14
0x180066644  mov     edx, 1
0x180066649  call    cs:__imp_ExInitializeAutoExpandPushLock
0x180066650  nop     dword ptr [rax+rax+00h]
0x180066655  mov     [rbx+4], r14d
0x180066659  mov     [rbx+180h], r14
0x180066660  mov     [rbx+190h], r14
0x180066667  mov     dword ptr [rbx+188h], 1
0x180066671  mov     [rbx+1A0h], r14
0x180066678  mov     dword ptr [rbx+198h], 3
0x180066682  mov     [rbx+1B0h], r14
0x180066689  mov     dword ptr [rbx+1A8h], 2
0x180066693  mov     [rbx+168h], r14
0x18006669a  test    cs:byte_1800404C2, 1
0x1800666a1  mov     r14, [rsp+58h+arg_0]
0x1800666a6  jnz     short loc_1800666C6
0x1800666a8  mov     [rsi], rbx
0x1800666ab  xor     eax, eax
0x1800666ad  add     rsp, 38h
0x1800666b1  pop     rdi
0x1800666b2  pop     rsi
0x1800666b3  pop     rbp
0x1800666b4  pop     rbx
0x1800666b5  retn
0x1800666b7  mov     eax, 0C000009Ah
0x1800666bc  add     rsp, 38h
0x1800666c0  pop     rdi
0x1800666c1  pop     rsi
0x1800666c2  pop     rbp
0x1800666c3  pop     rbx
0x1800666c4  retn
0x1800666c6  mov     eax, [rbx+44h]
0x1800666c9  lea     r8, aFltpallocatest_0; "FltpAllocateStreamListCtrl"
0x1800666d0  mov     [rsp+58h+var_30], eax
0x1800666d4  lea     rdx, StreamListCtrlSup_c715
0x1800666db  mov     eax, [rbx+40h]
0x1800666de  mov     r9, rbx
0x1800666e1  mov     [rsp+58h+var_38], eax
0x1800666e5  call    McTemplateU0spdd_EtwWriteTransfer
0x1800666ea  jmp     short loc_1800666A8
```
