# ObserverProtocol_New

- ea: `0x18000a520`
- end: `0x18000a65b`
- name: `ObserverProtocol_New`
- size: `315`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180035d00`
- `0x180035ed0`
- `0x1800378a0`

## callees

- `0x18000a520`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18000a543`
- `msvcrt!malloc` at `0x18000a543`

## pseudocode

```c
__int64 __fastcall ObserverProtocol_New(_QWORD *a1, __int64 a2, __int64 a3, _QWORD *a4, __int64 a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  void (__fastcall *v11)(_QWORD, __int64, _QWORD); // rax
  void (__fastcall *v12)(_QWORD); // rax
  __int64 result; // rax

  v9 = malloc(a5 + 152);
  v10 = v9;
  if ( v9 )
  {
    *v9 = a2;
    v9[1] = a3;
    v9[2] = v9;
    v9[4] = ObserverProtocol_Disposable_OnAddRef;
    v9[5] = ObserverProtocol_Disposable_OnRelease;
    v9[3] = ObserverProtocol_Disposable_OnDispose;
    *((_OWORD *)v9 + 3) = *(_OWORD *)a1;
    *((_OWORD *)v9 + 4) = *((_OWORD *)a1 + 1);
    v9[10] = a1[4];
    v9[15] = 0;
    v9[11] = 0;
    ((void (__fastcall *)(_QWORD *))s_compositeDisposableFT[0])(v9 + 16);
    if ( !v10[7] )
      v10[7] = BufferPostNotificationTrapMethod;
    if ( !v10[8] )
      v10[8] = BufferPostNotificationTrapMethod;
    if ( !v10[9] )
      v10[9] = TerminatedOnError;
    if ( !v10[10] )
      v10[10] = BufferPostNotificationTrapMethod;
    v10[12] = 1;
    v10[13] = 1;
    result = 0;
    *a4 = v10;
  }
  else
  {
    v11 = (void (__fastcall *)(_QWORD, __int64, _QWORD))a1[3];
    if ( v11 )
      v11(*a1, 27, 0);
    v12 = (void (__fastcall *)(_QWORD))a1[4];
    if ( v12 )
      v12(*a1);
    *a4 = 0;
    return 27;
  }
  return result;
}

```

## disassembly

```asm
0x18000a520  push    rbx
0x18000a522  push    rbp
0x18000a523  push    rsi
0x18000a524  push    rdi
0x18000a525  push    r14
0x18000a527  sub     rsp, 20h
0x18000a52b  mov     rdi, rcx
0x18000a52e  mov     rsi, r9
0x18000a531  mov     rcx, [rsp+48h+arg_20]
0x18000a536  mov     rbp, r8
0x18000a539  add     rcx, 98h; Size
0x18000a540  mov     r14, rdx
0x18000a543  call    cs:__imp_malloc
0x18000a549  mov     rbx, rax
0x18000a54c  test    rax, rax
0x18000a54f  jnz     short loc_18000A58B
0x18000a551  mov     rax, [rdi+18h]
0x18000a555  mov     ebx, 1Bh
0x18000a55a  test    rax, rax
0x18000a55d  jz      short loc_18000A56C
0x18000a55f  mov     rcx, [rdi]
0x18000a562  xor     r8d, r8d
0x18000a565  mov     edx, ebx
0x18000a567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a56c  mov     rax, [rdi+20h]
0x18000a570  test    rax, rax
0x18000a573  jz      short loc_18000A57D
0x18000a575  mov     rcx, [rdi]
0x18000a578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57d  mov     qword ptr [rsi], 0
0x18000a584  mov     eax, ebx
0x18000a586  jmp     loc_18000A650
0x18000a58b  mov     [rax], r14
0x18000a58e  lea     rcx, [rbx+80h]
0x18000a595  mov     [rax+8], rbp
0x18000a599  mov     [rax+10h], rbx
0x18000a59d  lea     rax, ObserverProtocol_Disposable_OnAddRef
0x18000a5a4  mov     [rbx+20h], rax
0x18000a5a8  lea     rax, ObserverProtocol_Disposable_OnRelease
0x18000a5af  mov     [rbx+28h], rax
0x18000a5b3  lea     rax, ObserverProtocol_Disposable_OnDispose
0x18000a5ba  mov     [rbx+18h], rax
0x18000a5be  movups  xmm0, xmmword ptr [rdi]
0x18000a5c1  movups  xmmword ptr [rbx+30h], xmm0
0x18000a5c5  movups  xmm1, xmmword ptr [rdi+10h]
0x18000a5c9  movups  xmmword ptr [rbx+40h], xmm1
0x18000a5cd  movsd   xmm0, qword ptr [rdi+20h]
0x18000a5d2  movsd   qword ptr [rbx+50h], xmm0
0x18000a5d7  mov     qword ptr [rbx+78h], 0
0x18000a5df  mov     qword ptr [rbx+58h], 0
0x18000a5e7  mov     rax, cs:off_180047BA8
0x18000a5ee  mov     rax, [rax]
0x18000a5f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f6  cmp     qword ptr [rbx+38h], 0
0x18000a5fb  jnz     short loc_18000A608
0x18000a5fd  lea     rax, BufferPostNotificationTrapMethod
0x18000a604  mov     [rbx+38h], rax
0x18000a608  cmp     qword ptr [rbx+40h], 0
0x18000a60d  jnz     short loc_18000A61A
0x18000a60f  lea     rax, BufferPostNotificationTrapMethod
0x18000a616  mov     [rbx+40h], rax
0x18000a61a  cmp     qword ptr [rbx+48h], 0
0x18000a61f  jnz     short loc_18000A62C
0x18000a621  lea     rax, TerminatedOnError
0x18000a628  mov     [rbx+48h], rax
0x18000a62c  cmp     qword ptr [rbx+50h], 0
0x18000a631  jnz     short loc_18000A63E
0x18000a633  lea     rax, BufferPostNotificationTrapMethod
0x18000a63a  mov     [rbx+50h], rax
0x18000a63e  mov     eax, 1
0x18000a643  mov     [rbx+60h], rax
0x18000a647  mov     [rbx+68h], rax
0x18000a64b  xor     eax, eax
0x18000a64d  mov     [rsi], rbx
0x18000a650  add     rsp, 20h
0x18000a654  pop     r14
0x18000a656  pop     rdi
0x18000a657  pop     rsi
0x18000a658  pop     rbp
0x18000a659  pop     rbx
0x18000a65a  retn
```
