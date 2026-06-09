# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180088fd8`
- end: `0x180089079`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180089240`

## callees

- `0x180088fd8`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18008902e`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008902e`
- `ntoskrnl!ExDeleteTimer` at `0x18008905b`
- `ntoskrnl!ExDeleteTimer` at `0x18008905b`

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
0x180088fd8  push    rbx
0x180088fda  sub     rsp, 50h
0x180088fde  cmp     qword ptr [rcx+168h], 0
0x180088fe6  mov     rbx, rcx
0x180088fe9  jz      loc_180089072
0x180088fef  xor     eax, eax
0x180088ff1  xorps   xmm0, xmm0
0x180088ff4  mov     [rsp+58h+var_18], rax
0x180088ff9  movups  [rsp+58h+var_28], xmm0
0x180088ffe  lea     edx, [rax+2]
0x180089001  mov     rax, [rcx+108h]
0x180089008  xchg    dx, [rax+38h]
0x18008900c  cmp     dx, 1
0x180089010  jnz     short loc_18008903A
0x180089012  mov     rcx, [rcx+108h]
0x180089019  xor     r9d, r9d; Alertable
0x18008901c  add     rcx, 20h ; ' '; Object
0x180089020  mov     [rsp+58h+Timeout], 0; Timeout
0x180089029  xor     r8d, r8d; WaitMode
0x18008902c  xor     edx, edx; WaitReason
0x18008902e  call    cs:__imp_KeWaitForSingleObject
0x180089035  nop     dword ptr [rax+rax+00h]
0x18008903a  mov     rcx, [rbx+168h]
0x180089041  lea     r9, [rsp+58h+var_28]
0x180089046  mov     r8b, 1
0x180089049  xorps   xmm0, xmm0
0x18008904c  xor     eax, eax
0x18008904e  mov     dl, r8b
0x180089051  movups  [rsp+58h+var_28], xmm0
0x180089056  mov     [rsp+58h+var_18], rax
0x18008905b  call    cs:__imp_ExDeleteTimer
0x180089062  nop     dword ptr [rax+rax+00h]
0x180089067  mov     qword ptr [rbx+168h], 0
0x180089072  add     rsp, 50h
0x180089076  pop     rbx
0x180089077  retn
```
