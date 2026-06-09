# CancelTimerCallbacksAndDeleteTimer

- ea: `0x14005a204`
- end: `0x14005a2a5`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14005a474`
- `0x14005ac24`

## callees

- `0x14005a204`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14005a25a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14005a25a`
- `ntoskrnl!ExDeleteTimer` at `0x14005a287`
- `ntoskrnl!ExDeleteTimer` at `0x14005a287`

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
0x14005a204  push    rbx
0x14005a206  sub     rsp, 50h
0x14005a20a  cmp     qword ptr [rcx+168h], 0
0x14005a212  mov     rbx, rcx
0x14005a215  jz      loc_14005A29E
0x14005a21b  xor     eax, eax
0x14005a21d  xorps   xmm0, xmm0
0x14005a220  mov     [rsp+58h+var_18], rax
0x14005a225  movups  [rsp+58h+var_28], xmm0
0x14005a22a  lea     edx, [rax+2]
0x14005a22d  mov     rax, [rcx+108h]
0x14005a234  xchg    dx, [rax+38h]
0x14005a238  cmp     dx, 1
0x14005a23c  jnz     short loc_14005A266
0x14005a23e  mov     rcx, [rcx+108h]
0x14005a245  xor     r9d, r9d; Alertable
0x14005a248  add     rcx, 20h ; ' '; Object
0x14005a24c  mov     [rsp+58h+Timeout], 0; Timeout
0x14005a255  xor     r8d, r8d; WaitMode
0x14005a258  xor     edx, edx; WaitReason
0x14005a25a  call    cs:__imp_KeWaitForSingleObject
0x14005a261  nop     dword ptr [rax+rax+00h]
0x14005a266  mov     rcx, [rbx+168h]
0x14005a26d  lea     r9, [rsp+58h+var_28]
0x14005a272  mov     r8b, 1
0x14005a275  xorps   xmm0, xmm0
0x14005a278  xor     eax, eax
0x14005a27a  mov     dl, r8b
0x14005a27d  movups  [rsp+58h+var_28], xmm0
0x14005a282  mov     [rsp+58h+var_18], rax
0x14005a287  call    cs:__imp_ExDeleteTimer
0x14005a28e  nop     dword ptr [rax+rax+00h]
0x14005a293  mov     qword ptr [rbx+168h], 0
0x14005a29e  add     rsp, 50h
0x14005a2a2  pop     rbx
0x14005a2a3  retn
```
