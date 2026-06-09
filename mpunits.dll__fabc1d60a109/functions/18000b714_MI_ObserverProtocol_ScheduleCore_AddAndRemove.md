# MI_ObserverProtocol_ScheduleCore_AddAndRemove

- ea: `0x18000b714`
- end: `0x18000b81a`
- name: `MI_ObserverProtocol_ScheduleCore_AddAndRemove`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b820`

## callees

- `0x18000b714`
- `0x18000b9f0`
- `0x18002d8a0`
- `0x180045010`

## import_xrefs

- `msvcrt!malloc` at `0x18000b730`
- `msvcrt!malloc` at `0x18000b730`

## pseudocode

```c
__int64 __fastcall MI_ObserverProtocol_ScheduleCore_AddAndRemove(
        __int64 a1,
        int a2,
        __int64 a3,
        void (__fastcall *a4)(__int64),
        __int64 a5,
        __int64 a6)
{
  char *v10; // rbx
  unsigned int v11; // edi
  _QWORD **v12; // rsi

  v10 = (char *)malloc(0x38u);
  if ( v10 )
  {
    ((void (__fastcall *)(__int64))ObserverProtocol_AddRef)(a1);
    *((_QWORD *)v10 + 4) = a3;
    *((_QWORD *)v10 + 6) = a5;
    v12 = (_QWORD **)(v10 + 16);
    *((_QWORD *)v10 + 1) = a1;
    *((_QWORD *)v10 + 5) = a4;
    v10[24] = 0;
    *((_QWORD *)v10 + 2) = 0;
    *(_QWORD *)v10 = 2;
    v11 = RxcScheduler_Schedule(
            a2,
            (unsigned int)ObserverProtocolScheduleClosure_InvokeWorkItem,
            (unsigned int)ObserverProtocolScheduleClosure_Release,
            (_DWORD)v10,
            a6,
            (__int64)(v10 + 16));
    if ( !v11 )
    {
      v11 = ((__int64 (__fastcall *)(__int64, _QWORD))ObserverProtocol_TrackDisposable)(a1, *v12);
      if ( v11 )
      {
        if ( *v12 )
          ((void (__fastcall *)(_QWORD))(*v12)[1])(**v12);
      }
      else
      {
        v10[24] = 1;
      }
    }
    ObserverProtocolScheduleClosure_Release(v10);
  }
  else
  {
    if ( a4 )
      a4(a5);
    return 27;
  }
  return v11;
}

```

## disassembly

```asm
0x18000b714  push    rbx
0x18000b716  push    rbp
0x18000b717  push    rsi
0x18000b718  push    rdi
0x18000b719  push    r14
0x18000b71b  sub     rsp, 30h
0x18000b71f  mov     rbp, rcx
0x18000b722  mov     rdi, r9
0x18000b725  mov     ecx, 38h ; '8'; Size
0x18000b72a  mov     rsi, r8
0x18000b72d  mov     r14, rdx
0x18000b730  call    cs:__imp_malloc
0x18000b736  mov     rbx, rax
0x18000b739  test    rax, rax
0x18000b73c  jnz     short loc_18000B75D
0x18000b73e  test    rdi, rdi
0x18000b741  jz      short loc_18000B753
0x18000b743  mov     rcx, [rsp+58h+arg_20]
0x18000b74b  mov     rax, rdi
0x18000b74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b753  mov     edi, 1Bh
0x18000b758  jmp     loc_18000B80D
0x18000b75d  mov     rax, cs:off_180047BB0
0x18000b764  mov     rcx, rbp
0x18000b767  mov     rax, [rax+8]
0x18000b76b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b770  mov     rax, [rsp+58h+arg_20]
0x18000b778  lea     r8, ObserverProtocolScheduleClosure_Release
0x18000b77f  mov     [rbx+20h], rsi
0x18000b783  lea     rdx, ObserverProtocolScheduleClosure_InvokeWorkItem
0x18000b78a  mov     [rbx+30h], rax
0x18000b78e  lea     rsi, [rbx+10h]
0x18000b792  mov     rax, [rsp+58h+arg_28]
0x18000b79a  mov     r9, rbx
0x18000b79d  mov     [rsp+58h+var_30], rsi
0x18000b7a2  mov     rcx, r14
0x18000b7a5  mov     [rsp+58h+var_38], rax
0x18000b7aa  mov     [rbx+8], rbp
0x18000b7ae  mov     [rbx+28h], rdi
0x18000b7b2  mov     byte ptr [rbx+18h], 0
0x18000b7b6  mov     qword ptr [rsi], 0
0x18000b7bd  mov     qword ptr [rbx], 2
0x18000b7c4  call    RxcScheduler_Schedule
0x18000b7c9  mov     edi, eax
0x18000b7cb  test    eax, eax
0x18000b7cd  jnz     short loc_18000B805
0x18000b7cf  mov     rax, cs:off_180047BB0
0x18000b7d6  mov     rcx, rbp
0x18000b7d9  mov     rdx, [rsi]
0x18000b7dc  mov     rax, [rax+70h]
0x18000b7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7e5  mov     edi, eax
0x18000b7e7  test    eax, eax
0x18000b7e9  jnz     short loc_18000B7F1
0x18000b7eb  mov     byte ptr [rbx+18h], 1
0x18000b7ef  jmp     short loc_18000B805
0x18000b7f1  mov     rax, [rsi]
0x18000b7f4  test    rax, rax
0x18000b7f7  jz      short loc_18000B805
0x18000b7f9  mov     rcx, [rax]
0x18000b7fc  mov     rax, [rax+8]
0x18000b800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b805  mov     rcx, rbx; Block
0x18000b808  call    ObserverProtocolScheduleClosure_Release
0x18000b80d  mov     eax, edi
0x18000b80f  add     rsp, 30h
0x18000b813  pop     r14
0x18000b815  pop     rdi
0x18000b816  pop     rsi
0x18000b817  pop     rbp
0x18000b818  pop     rbx
0x18000b819  retn
```
