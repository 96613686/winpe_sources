# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1400543cc`
- end: `0x14005446d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14005463c`
- `0x1400549a0`

## callees

- `0x1400543cc`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x14005444f`
- `ntoskrnl!ExDeleteTimer` at `0x14005444f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054422`
- `ntoskrnl!KeWaitForSingleObject` at `0x140054422`

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
0x1400543cc  push    rbx
0x1400543ce  sub     rsp, 50h
0x1400543d2  cmp     qword ptr [rcx+168h], 0
0x1400543da  mov     rbx, rcx
0x1400543dd  jz      loc_140054466
0x1400543e3  xor     eax, eax
0x1400543e5  xorps   xmm0, xmm0
0x1400543e8  mov     [rsp+58h+var_18], rax
0x1400543ed  movups  [rsp+58h+var_28], xmm0
0x1400543f2  lea     edx, [rax+2]
0x1400543f5  mov     rax, [rcx+108h]
0x1400543fc  xchg    dx, [rax+38h]
0x140054400  cmp     dx, 1
0x140054404  jnz     short loc_14005442E
0x140054406  mov     rcx, [rcx+108h]
0x14005440d  xor     r9d, r9d; Alertable
0x140054410  add     rcx, 20h ; ' '; Object
0x140054414  mov     [rsp+58h+Timeout], 0; Timeout
0x14005441d  xor     r8d, r8d; WaitMode
0x140054420  xor     edx, edx; WaitReason
0x140054422  call    cs:__imp_KeWaitForSingleObject
0x140054429  nop     dword ptr [rax+rax+00h]
0x14005442e  mov     rcx, [rbx+168h]
0x140054435  lea     r9, [rsp+58h+var_28]
0x14005443a  mov     r8b, 1
0x14005443d  xorps   xmm0, xmm0
0x140054440  xor     eax, eax
0x140054442  mov     dl, r8b
0x140054445  movups  [rsp+58h+var_28], xmm0
0x14005444a  mov     [rsp+58h+var_18], rax
0x14005444f  call    cs:__imp_ExDeleteTimer
0x140054456  nop     dword ptr [rax+rax+00h]
0x14005445b  mov     qword ptr [rbx+168h], 0
0x140054466  add     rsp, 50h
0x14005446a  pop     rbx
0x14005446b  retn
```
