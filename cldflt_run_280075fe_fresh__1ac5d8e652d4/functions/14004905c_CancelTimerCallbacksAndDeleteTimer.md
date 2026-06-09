# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14004905c`
- end: `0x1400490fd`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400492cc`
- `0x1400495d0`

## callees

- `0x14004905c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1400490b2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400490b2`
- `ntoskrnl!ExDeleteTimer` at `0x1400490df`
- `ntoskrnl!ExDeleteTimer` at `0x1400490df`

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
0x14004905c  push    rbx
0x14004905e  sub     rsp, 50h
0x140049062  cmp     qword ptr [rcx+168h], 0
0x14004906a  mov     rbx, rcx
0x14004906d  jz      loc_1400490F6
0x140049073  xor     eax, eax
0x140049075  xorps   xmm0, xmm0
0x140049078  mov     [rsp+58h+var_18], rax
0x14004907d  movups  [rsp+58h+var_28], xmm0
0x140049082  lea     edx, [rax+2]
0x140049085  mov     rax, [rcx+108h]
0x14004908c  xchg    dx, [rax+38h]
0x140049090  cmp     dx, 1
0x140049094  jnz     short loc_1400490BE
0x140049096  mov     rcx, [rcx+108h]
0x14004909d  xor     r9d, r9d; Alertable
0x1400490a0  add     rcx, 20h ; ' '; Object
0x1400490a4  mov     [rsp+58h+Timeout], 0; Timeout
0x1400490ad  xor     r8d, r8d; WaitMode
0x1400490b0  xor     edx, edx; WaitReason
0x1400490b2  call    cs:__imp_KeWaitForSingleObject
0x1400490b9  nop     dword ptr [rax+rax+00h]
0x1400490be  mov     rcx, [rbx+168h]
0x1400490c5  lea     r9, [rsp+58h+var_28]
0x1400490ca  mov     r8b, 1
0x1400490cd  xorps   xmm0, xmm0
0x1400490d0  xor     eax, eax
0x1400490d2  mov     dl, r8b
0x1400490d5  movups  [rsp+58h+var_28], xmm0
0x1400490da  mov     [rsp+58h+var_18], rax
0x1400490df  call    cs:__imp_ExDeleteTimer
0x1400490e6  nop     dword ptr [rax+rax+00h]
0x1400490eb  mov     qword ptr [rbx+168h], 0
0x1400490f6  add     rsp, 50h
0x1400490fa  pop     rbx
0x1400490fb  retn
```
