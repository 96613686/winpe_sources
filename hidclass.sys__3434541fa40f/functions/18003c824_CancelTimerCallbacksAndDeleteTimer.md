# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18003c824`
- end: `0x18003c8c5`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180037f4c`
- `0x18003ca94`

## callees

- `0x18003c824`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x18003c87a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18003c87a`
- `ntoskrnl!ExDeleteTimer` at `0x18003c8a7`
- `ntoskrnl!ExDeleteTimer` at `0x18003c8a7`

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
0x18003c824  push    rbx
0x18003c826  sub     rsp, 50h
0x18003c82a  cmp     qword ptr [rcx+168h], 0
0x18003c832  mov     rbx, rcx
0x18003c835  jz      loc_18003C8BE
0x18003c83b  xor     eax, eax
0x18003c83d  xorps   xmm0, xmm0
0x18003c840  mov     [rsp+58h+var_18], rax
0x18003c845  movups  [rsp+58h+var_28], xmm0
0x18003c84a  lea     edx, [rax+2]
0x18003c84d  mov     rax, [rcx+108h]
0x18003c854  xchg    dx, [rax+38h]
0x18003c858  cmp     dx, 1
0x18003c85c  jnz     short loc_18003C886
0x18003c85e  mov     rcx, [rcx+108h]
0x18003c865  xor     r9d, r9d; Alertable
0x18003c868  add     rcx, 20h ; ' '; Object
0x18003c86c  mov     [rsp+58h+Timeout], 0; Timeout
0x18003c875  xor     r8d, r8d; WaitMode
0x18003c878  xor     edx, edx; WaitReason
0x18003c87a  call    cs:__imp_KeWaitForSingleObject
0x18003c881  nop     dword ptr [rax+rax+00h]
0x18003c886  mov     rcx, [rbx+168h]
0x18003c88d  lea     r9, [rsp+58h+var_28]
0x18003c892  mov     r8b, 1
0x18003c895  xorps   xmm0, xmm0
0x18003c898  xor     eax, eax
0x18003c89a  mov     dl, r8b
0x18003c89d  movups  [rsp+58h+var_28], xmm0
0x18003c8a2  mov     [rsp+58h+var_18], rax
0x18003c8a7  call    cs:__imp_ExDeleteTimer
0x18003c8ae  nop     dword ptr [rax+rax+00h]
0x18003c8b3  mov     qword ptr [rbx+168h], 0
0x18003c8be  add     rsp, 50h
0x18003c8c2  pop     rbx
0x18003c8c3  retn
```
