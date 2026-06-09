# QuicWorkerProcessTimers

- ea: `0x14000fac0`
- end: `0x14000fbb8`
- name: `QuicWorkerProcessTimers`
- size: `248`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002e380`

## callees

- `0x14000f9c0`
- `0x14000fac0`
- `0x14001d7d0`
- `0x1400211bc`

## import_xrefs

- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000fb6a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000fb6a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000fb47`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000fb47`

## pseudocode

```c
_QWORD *__fastcall QuicWorkerProcessTimers(__int64 a1, __int64 a2, __int64 a3)
{
  _QWORD *v5; // rbx
  _QWORD *result; // rax
  _QWORD *v7; // rbx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rdi
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v11[1] = v11;
  v11[0] = v11;
  QuicTimerWheelGetExpired(a1 + 88, a3, v11);
  while ( 1 )
  {
    v5 = (_QWORD *)v11[0];
    result = v11;
    if ( (_QWORD *)v11[0] == v11 )
      break;
    v11[0] = *(_QWORD *)v11[0];
    *(_QWORD *)(v11[0] + 8LL) = v11;
    *v5 = 0;
    v7 = v5 - 6;
    v8 = v7[11];
    v7[32] = a2;
    if ( v8 && (v9 = *(_QWORD *)(v8 + 64)) != 0 )
    {
      v10 = PsAttachSiloToCurrentThread(v9);
      QuicConnTimerExpired(v7, a3);
      if ( v10 != -1 )
        PsDetachSiloFromCurrentThread(v10);
    }
    else
    {
      QuicConnTimerExpired(v7, a3);
    }
    v7[32] = 0;
    QuicConnRelease(v7, 3);
  }
  return result;
}

```

## disassembly

```asm
0x14000fac0  mov     r11, rsp
0x14000fac3  mov     [r11+10h], rbx
0x14000fac7  mov     [r11+18h], rbp
0x14000facb  mov     [r11+20h], rsi
0x14000facf  push    r14
0x14000fad1  sub     rsp, 30h
0x14000fad5  lea     rax, [r11-18h]
0x14000fad9  mov     rsi, r8
0x14000fadc  mov     [r11-10h], rax
0x14000fae0  lea     r8, [r11-18h]
0x14000fae4  lea     rax, [r11-18h]
0x14000fae8  mov     rbp, rdx
0x14000faeb  add     rcx, 58h ; 'X'
0x14000faef  mov     [r11-18h], rax
0x14000faf3  mov     rdx, rsi
0x14000faf6  call    QuicTimerWheelGetExpired
0x14000fafb  xor     r14d, r14d
0x14000fafe  mov     [rsp+38h+arg_0], rdi
0x14000fb03  mov     rbx, [rsp+38h+var_18]
0x14000fb08  lea     rax, [rsp+38h+var_18]
0x14000fb0d  cmp     rbx, rax
0x14000fb10  jz      loc_14000FB9C
0x14000fb16  mov     rax, [rbx]
0x14000fb19  lea     rcx, [rsp+38h+var_18]
0x14000fb1e  mov     [rsp+38h+var_18], rax
0x14000fb23  mov     [rax+8], rcx
0x14000fb27  mov     [rbx], r14
0x14000fb2a  add     rbx, 0FFFFFFFFFFFFFFD0h
0x14000fb2e  mov     rcx, [rbx+58h]
0x14000fb32  mov     [rbx+100h], rbp
0x14000fb39  test    rcx, rcx
0x14000fb3c  jz      short loc_14000FB78
0x14000fb3e  mov     rcx, [rcx+40h]
0x14000fb42  test    rcx, rcx
0x14000fb45  jz      short loc_14000FB78
0x14000fb47  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000fb4e  nop     dword ptr [rax+rax+00h]
0x14000fb53  mov     rdx, rsi
0x14000fb56  mov     rcx, rbx
0x14000fb59  mov     rdi, rax
0x14000fb5c  call    QuicConnTimerExpired
0x14000fb61  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x14000fb65  jz      short loc_14000FB83
0x14000fb67  mov     rcx, rdi
0x14000fb6a  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000fb71  nop     dword ptr [rax+rax+00h]
0x14000fb76  jmp     short loc_14000FB83
0x14000fb78  mov     rdx, rsi
0x14000fb7b  mov     rcx, rbx
0x14000fb7e  call    QuicConnTimerExpired
0x14000fb83  mov     edx, 3
0x14000fb88  mov     [rbx+100h], r14
0x14000fb8f  mov     rcx, rbx
0x14000fb92  call    QuicConnRelease
0x14000fb97  jmp     loc_14000FB03
0x14000fb9c  mov     rdi, [rsp+38h+arg_0]
0x14000fba1  mov     rbx, [rsp+38h+arg_8]
0x14000fba6  mov     rbp, [rsp+38h+arg_10]
0x14000fbab  mov     rsi, [rsp+38h+arg_18]
0x14000fbb0  add     rsp, 30h
0x14000fbb4  pop     r14
0x14000fbb6  retn
```
