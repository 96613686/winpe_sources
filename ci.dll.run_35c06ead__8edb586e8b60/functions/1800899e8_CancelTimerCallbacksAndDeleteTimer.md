# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800899e8`
- end: `0x180089a89`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180089c50`

## callees

- `0x1800899e8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x180089a3e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089a3e`
- `ntoskrnl!ExDeleteTimer` at `0x180089a6b`
- `ntoskrnl!ExDeleteTimer` at `0x180089a6b`

## pseudocode

```c
__int64 __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 result; // rax
  __int128 v8; // [rsp+30h] [rbp-28h] BYREF
  __int64 v9; // [rsp+40h] [rbp-18h]

  if ( *(_QWORD *)(a1 + 360) )
  {
    v9 = 0;
    v8 = 0;
    v5 = 2;
    v4 = *(_QWORD *)(a1 + 264);
    LOWORD(v5) = *(_WORD *)(v4 + 56);
    *(_WORD *)(v4 + 56) = 2;
    if ( (_WORD)v5 == 1 )
      KeWaitForSingleObject((PVOID)(*(_QWORD *)(a1 + 264) + 32LL), Executive, 0, 0, 0);
    v6 = *(_QWORD *)(a1 + 360);
    LOBYTE(a3) = 1;
    LOBYTE(v5) = 1;
    v8 = 0;
    v9 = 0;
    result = ExDeleteTimer(v6, v5, a3, &v8);
    *(_QWORD *)(a1 + 360) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800899e8  push    rbx
0x1800899ea  sub     rsp, 50h
0x1800899ee  cmp     qword ptr [rcx+168h], 0
0x1800899f6  mov     rbx, rcx
0x1800899f9  jz      loc_180089A82
0x1800899ff  xor     eax, eax
0x180089a01  xorps   xmm0, xmm0
0x180089a04  mov     [rsp+58h+var_18], rax
0x180089a09  movups  [rsp+58h+var_28], xmm0
0x180089a0e  lea     edx, [rax+2]
0x180089a11  mov     rax, [rcx+108h]
0x180089a18  xchg    dx, [rax+38h]
0x180089a1c  cmp     dx, 1
0x180089a20  jnz     short loc_180089A4A
0x180089a22  mov     rcx, [rcx+108h]
0x180089a29  xor     r9d, r9d; Alertable
0x180089a2c  add     rcx, 20h ; ' '; Object
0x180089a30  mov     [rsp+58h+Timeout], 0; Timeout
0x180089a39  xor     r8d, r8d; WaitMode
0x180089a3c  xor     edx, edx; WaitReason
0x180089a3e  call    cs:__imp_KeWaitForSingleObject
0x180089a45  nop     dword ptr [rax+rax+00h]
0x180089a4a  mov     rcx, [rbx+168h]
0x180089a51  lea     r9, [rsp+58h+var_28]
0x180089a56  mov     r8b, 1
0x180089a59  xorps   xmm0, xmm0
0x180089a5c  xor     eax, eax
0x180089a5e  mov     dl, r8b
0x180089a61  movups  [rsp+58h+var_28], xmm0
0x180089a66  mov     [rsp+58h+var_18], rax
0x180089a6b  call    cs:__imp_ExDeleteTimer
0x180089a72  nop     dword ptr [rax+rax+00h]
0x180089a77  mov     qword ptr [rbx+168h], 0
0x180089a82  add     rsp, 50h
0x180089a86  pop     rbx
0x180089a87  retn
```
