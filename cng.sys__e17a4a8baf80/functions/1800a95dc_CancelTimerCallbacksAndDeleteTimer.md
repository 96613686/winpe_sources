# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800a95dc`
- end: `0x1800a967d`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `161`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a984c`
- `0x1800aa020`

## callees

- `0x1800a95dc`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x1800a9632`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800a9632`
- `ntoskrnl!ExDeleteTimer` at `0x1800a965f`
- `ntoskrnl!ExDeleteTimer` at `0x1800a965f`

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
0x1800a95dc  push    rbx
0x1800a95de  sub     rsp, 50h
0x1800a95e2  cmp     qword ptr [rcx+168h], 0
0x1800a95ea  mov     rbx, rcx
0x1800a95ed  jz      loc_1800A9676
0x1800a95f3  xor     eax, eax
0x1800a95f5  xorps   xmm0, xmm0
0x1800a95f8  mov     [rsp+58h+var_18], rax
0x1800a95fd  movups  [rsp+58h+var_28], xmm0
0x1800a9602  lea     edx, [rax+2]
0x1800a9605  mov     rax, [rcx+108h]
0x1800a960c  xchg    dx, [rax+38h]
0x1800a9610  cmp     dx, 1
0x1800a9614  jnz     short loc_1800A963E
0x1800a9616  mov     rcx, [rcx+108h]
0x1800a961d  xor     r9d, r9d; Alertable
0x1800a9620  add     rcx, 20h ; ' '; Object
0x1800a9624  mov     [rsp+58h+Timeout], 0; Timeout
0x1800a962d  xor     r8d, r8d; WaitMode
0x1800a9630  xor     edx, edx; WaitReason
0x1800a9632  call    cs:__imp_KeWaitForSingleObject
0x1800a9639  nop     dword ptr [rax+rax+00h]
0x1800a963e  mov     rcx, [rbx+168h]
0x1800a9645  lea     r9, [rsp+58h+var_28]
0x1800a964a  mov     r8b, 1
0x1800a964d  xorps   xmm0, xmm0
0x1800a9650  xor     eax, eax
0x1800a9652  mov     dl, r8b
0x1800a9655  movups  [rsp+58h+var_28], xmm0
0x1800a965a  mov     [rsp+58h+var_18], rax
0x1800a965f  call    cs:__imp_ExDeleteTimer
0x1800a9666  nop     dword ptr [rax+rax+00h]
0x1800a966b  mov     qword ptr [rbx+168h], 0
0x1800a9676  add     rsp, 50h
0x1800a967a  pop     rbx
0x1800a967b  retn
```
