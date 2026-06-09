# RemoveVcFromClAfList

- ea: `0x140007254`
- end: `0x140007301`
- name: `RemoveVcFromClAfList`
- size: `173`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f630`
- `0x140015290`

## callees

- `0x140007254`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007274`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007274`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400072dd`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400072dd`

## pseudocode

```c
void __fastcall RemoveVcFromClAfList(__int64 a1)
{
  __int64 v1; // rdi
  _QWORD *v3; // rax
  __int64 v4; // rdx
  _QWORD *v5; // rcx
  _QWORD *v6; // rdx

  v1 = *(_QWORD *)(a1 + 56);
  *(_BYTE *)(v1 + 192) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 184));
  if ( *(_BYTE *)(a1 + 528) )
  {
    v3 = (_QWORD *)(a1 + 480);
    *(_BYTE *)(a1 + 528) = 0;
    v4 = *(_QWORD *)(a1 + 480);
    if ( *(_QWORD *)(v4 + 8) != a1 + 480
      || (v5 = *(_QWORD **)(a1 + 488), (_QWORD *)*v5 != v3)
      || (*v5 = v4, *(_QWORD *)(v4 + 8) = v5, v6 = *(_QWORD **)(v1 + 96), *v6 != v1 + 88) )
    {
      __fastfail(3u);
    }
    *v3 = v1 + 88;
    *(_QWORD *)(a1 + 488) = v6;
    *v6 = v3;
    *(_QWORD *)(v1 + 96) = v3;
    --*(_DWORD *)(a1 + 28);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 184), *(_BYTE *)(v1 + 192));
}

```

## disassembly

```asm
0x140007254  mov     [rsp+arg_0], rbx
0x140007259  mov     [rsp+arg_8], rsi
0x14000725e  push    rdi
0x14000725f  sub     rsp, 20h
0x140007263  mov     rdi, [rcx+38h]
0x140007267  mov     rbx, rcx
0x14000726a  lea     rsi, [rdi+0B8h]
0x140007271  mov     rcx, rsi; SpinLock
0x140007274  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000727b  nop     dword ptr [rax+rax+00h]
0x140007280  mov     [rdi+0C0h], al
0x140007286  cmp     byte ptr [rbx+210h], 0
0x14000728d  jz      short loc_1400072D4
0x14000728f  lea     rax, [rbx+1E0h]
0x140007296  mov     byte ptr [rbx+210h], 0
0x14000729d  mov     rdx, [rax]
0x1400072a0  cmp     [rdx+8], rax
0x1400072a4  jnz     short loc_1400072FA
0x1400072a6  mov     rcx, [rax+8]
0x1400072aa  cmp     [rcx], rax
0x1400072ad  jnz     short loc_1400072FA
0x1400072af  mov     [rcx], rdx
0x1400072b2  mov     [rdx+8], rcx
0x1400072b6  lea     rcx, [rdi+58h]
0x1400072ba  mov     rdx, [rcx+8]
0x1400072be  cmp     [rdx], rcx
0x1400072c1  jnz     short loc_1400072FA
0x1400072c3  mov     [rax], rcx
0x1400072c6  mov     [rax+8], rdx
0x1400072ca  mov     [rdx], rax
0x1400072cd  mov     [rcx+8], rax
0x1400072d1  dec     dword ptr [rbx+1Ch]
0x1400072d4  mov     dl, [rdi+0C0h]; NewIrql
0x1400072da  mov     rcx, rsi; SpinLock
0x1400072dd  call    cs:__imp_KeReleaseSpinLock
0x1400072e4  nop     dword ptr [rax+rax+00h]
0x1400072e9  mov     rbx, [rsp+28h+arg_0]
0x1400072ee  mov     rsi, [rsp+28h+arg_8]
0x1400072f3  add     rsp, 20h
0x1400072f7  pop     rdi
0x1400072f8  retn
0x1400072fa  mov     ecx, 3
0x1400072ff  int     29h; Win8: RtlFailFast(ecx)
```
