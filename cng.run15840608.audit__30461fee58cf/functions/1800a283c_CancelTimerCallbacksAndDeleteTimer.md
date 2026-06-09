# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800a283c`
- end: `0x1800a28dd`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a2aac`
- `0x1800a3280`

## callees

- `0x1800a283c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800a2892`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800a2892`
- `ntoskrnl!ExDeleteTimer` at `0x1800a28bf`
- `ntoskrnl!ExDeleteTimer` at `0x1800a28bf`

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
0x1800a283c  push    rbx
0x1800a283e  sub     rsp, 50h
0x1800a2842  cmp     qword ptr [rcx+168h], 0
0x1800a284a  mov     rbx, rcx
0x1800a284d  jz      loc_1800A28D6
0x1800a2853  xor     eax, eax
0x1800a2855  xorps   xmm0, xmm0
0x1800a2858  mov     [rsp+58h+var_18], rax
0x1800a285d  movups  [rsp+58h+var_28], xmm0
0x1800a2862  lea     edx, [rax+2]
0x1800a2865  mov     rax, [rcx+108h]
0x1800a286c  xchg    dx, [rax+38h]
0x1800a2870  cmp     dx, 1
0x1800a2874  jnz     short loc_1800A289E
0x1800a2876  mov     rcx, [rcx+108h]
0x1800a287d  xor     r9d, r9d; Alertable
0x1800a2880  add     rcx, 20h ; ' '; Object
0x1800a2884  mov     [rsp+58h+Timeout], 0; Timeout
0x1800a288d  xor     r8d, r8d; WaitMode
0x1800a2890  xor     edx, edx; WaitReason
0x1800a2892  call    cs:__imp_KeWaitForSingleObject
0x1800a2899  nop     dword ptr [rax+rax+00h]
0x1800a289e  mov     rcx, [rbx+168h]
0x1800a28a5  lea     r9, [rsp+58h+var_28]
0x1800a28aa  mov     r8b, 1
0x1800a28ad  xorps   xmm0, xmm0
0x1800a28b0  xor     eax, eax
0x1800a28b2  mov     dl, r8b
0x1800a28b5  movups  [rsp+58h+var_28], xmm0
0x1800a28ba  mov     [rsp+58h+var_18], rax
0x1800a28bf  call    cs:__imp_ExDeleteTimer
0x1800a28c6  nop     dword ptr [rax+rax+00h]
0x1800a28cb  mov     qword ptr [rbx+168h], 0
0x1800a28d6  add     rsp, 50h
0x1800a28da  pop     rbx
0x1800a28db  retn
```
