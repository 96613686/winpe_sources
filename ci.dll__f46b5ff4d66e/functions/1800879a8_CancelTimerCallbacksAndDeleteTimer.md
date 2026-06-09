# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800879a8`
- end: `0x180087a49`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180087c10`

## callees

- `0x1800879a8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800879fe`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800879fe`
- `ntoskrnl!ExDeleteTimer` at `0x180087a2b`
- `ntoskrnl!ExDeleteTimer` at `0x180087a2b`

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
0x1800879a8  push    rbx
0x1800879aa  sub     rsp, 50h
0x1800879ae  cmp     qword ptr [rcx+168h], 0
0x1800879b6  mov     rbx, rcx
0x1800879b9  jz      loc_180087A42
0x1800879bf  xor     eax, eax
0x1800879c1  xorps   xmm0, xmm0
0x1800879c4  mov     [rsp+58h+var_18], rax
0x1800879c9  movups  [rsp+58h+var_28], xmm0
0x1800879ce  lea     edx, [rax+2]
0x1800879d1  mov     rax, [rcx+108h]
0x1800879d8  xchg    dx, [rax+38h]
0x1800879dc  cmp     dx, 1
0x1800879e0  jnz     short loc_180087A0A
0x1800879e2  mov     rcx, [rcx+108h]
0x1800879e9  xor     r9d, r9d; Alertable
0x1800879ec  add     rcx, 20h ; ' '; Object
0x1800879f0  mov     [rsp+58h+Timeout], 0; Timeout
0x1800879f9  xor     r8d, r8d; WaitMode
0x1800879fc  xor     edx, edx; WaitReason
0x1800879fe  call    cs:__imp_KeWaitForSingleObject
0x180087a05  nop     dword ptr [rax+rax+00h]
0x180087a0a  mov     rcx, [rbx+168h]
0x180087a11  lea     r9, [rsp+58h+var_28]
0x180087a16  mov     r8b, 1
0x180087a19  xorps   xmm0, xmm0
0x180087a1c  xor     eax, eax
0x180087a1e  mov     dl, r8b
0x180087a21  movups  [rsp+58h+var_28], xmm0
0x180087a26  mov     [rsp+58h+var_18], rax
0x180087a2b  call    cs:__imp_ExDeleteTimer
0x180087a32  nop     dword ptr [rax+rax+00h]
0x180087a37  mov     qword ptr [rbx+168h], 0
0x180087a42  add     rsp, 50h
0x180087a46  pop     rbx
0x180087a47  retn
```
