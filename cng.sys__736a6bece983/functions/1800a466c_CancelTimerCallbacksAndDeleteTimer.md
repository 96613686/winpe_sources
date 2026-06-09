# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800a466c`
- end: `0x1800a470d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a48dc`
- `0x1800a50b0`

## callees

- `0x1800a466c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800a46c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800a46c2`
- `ntoskrnl!ExDeleteTimer` at `0x1800a46ef`
- `ntoskrnl!ExDeleteTimer` at `0x1800a46ef`

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
0x1800a466c  push    rbx
0x1800a466e  sub     rsp, 50h
0x1800a4672  cmp     qword ptr [rcx+168h], 0
0x1800a467a  mov     rbx, rcx
0x1800a467d  jz      loc_1800A4706
0x1800a4683  xor     eax, eax
0x1800a4685  xorps   xmm0, xmm0
0x1800a4688  mov     [rsp+58h+var_18], rax
0x1800a468d  movups  [rsp+58h+var_28], xmm0
0x1800a4692  lea     edx, [rax+2]
0x1800a4695  mov     rax, [rcx+108h]
0x1800a469c  xchg    dx, [rax+38h]
0x1800a46a0  cmp     dx, 1
0x1800a46a4  jnz     short loc_1800A46CE
0x1800a46a6  mov     rcx, [rcx+108h]
0x1800a46ad  xor     r9d, r9d; Alertable
0x1800a46b0  add     rcx, 20h ; ' '; Object
0x1800a46b4  mov     [rsp+58h+Timeout], 0; Timeout
0x1800a46bd  xor     r8d, r8d; WaitMode
0x1800a46c0  xor     edx, edx; WaitReason
0x1800a46c2  call    cs:__imp_KeWaitForSingleObject
0x1800a46c9  nop     dword ptr [rax+rax+00h]
0x1800a46ce  mov     rcx, [rbx+168h]
0x1800a46d5  lea     r9, [rsp+58h+var_28]
0x1800a46da  mov     r8b, 1
0x1800a46dd  xorps   xmm0, xmm0
0x1800a46e0  xor     eax, eax
0x1800a46e2  mov     dl, r8b
0x1800a46e5  movups  [rsp+58h+var_28], xmm0
0x1800a46ea  mov     [rsp+58h+var_18], rax
0x1800a46ef  call    cs:__imp_ExDeleteTimer
0x1800a46f6  nop     dword ptr [rax+rax+00h]
0x1800a46fb  mov     qword ptr [rbx+168h], 0
0x1800a4706  add     rsp, 50h
0x1800a470a  pop     rbx
0x1800a470b  retn
```
