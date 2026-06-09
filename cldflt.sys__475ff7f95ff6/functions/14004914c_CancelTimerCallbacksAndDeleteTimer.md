# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14004914c`
- end: `0x1400491ed`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400493bc`
- `0x1400496c0`

## callees

- `0x14004914c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400491a2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400491a2`
- `ntoskrnl!ExDeleteTimer` at `0x1400491cf`
- `ntoskrnl!ExDeleteTimer` at `0x1400491cf`

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
0x14004914c  push    rbx
0x14004914e  sub     rsp, 50h
0x140049152  cmp     qword ptr [rcx+168h], 0
0x14004915a  mov     rbx, rcx
0x14004915d  jz      loc_1400491E6
0x140049163  xor     eax, eax
0x140049165  xorps   xmm0, xmm0
0x140049168  mov     [rsp+58h+var_18], rax
0x14004916d  movups  [rsp+58h+var_28], xmm0
0x140049172  lea     edx, [rax+2]
0x140049175  mov     rax, [rcx+108h]
0x14004917c  xchg    dx, [rax+38h]
0x140049180  cmp     dx, 1
0x140049184  jnz     short loc_1400491AE
0x140049186  mov     rcx, [rcx+108h]
0x14004918d  xor     r9d, r9d; Alertable
0x140049190  add     rcx, 20h ; ' '; Object
0x140049194  mov     [rsp+58h+Timeout], 0; Timeout
0x14004919d  xor     r8d, r8d; WaitMode
0x1400491a0  xor     edx, edx; WaitReason
0x1400491a2  call    cs:__imp_KeWaitForSingleObject
0x1400491a9  nop     dword ptr [rax+rax+00h]
0x1400491ae  mov     rcx, [rbx+168h]
0x1400491b5  lea     r9, [rsp+58h+var_28]
0x1400491ba  mov     r8b, 1
0x1400491bd  xorps   xmm0, xmm0
0x1400491c0  xor     eax, eax
0x1400491c2  mov     dl, r8b
0x1400491c5  movups  [rsp+58h+var_28], xmm0
0x1400491ca  mov     [rsp+58h+var_18], rax
0x1400491cf  call    cs:__imp_ExDeleteTimer
0x1400491d6  nop     dword ptr [rax+rax+00h]
0x1400491db  mov     qword ptr [rbx+168h], 0
0x1400491e6  add     rsp, 50h
0x1400491ea  pop     rbx
0x1400491eb  retn
```
