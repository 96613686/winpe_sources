# NpFsdWrite

- ea: `0x14000cf10`
- end: `0x14000cff1`
- name: `NpFsdWrite`
- size: `225`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000cf10`
- `0x14000cff8`

## import_xrefs

- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf40`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000cf40`
- `ntoskrnl!IofCompleteRequest` at `0x14000cf98`
- `ntoskrnl!IofCompleteRequest` at `0x14000cfd7`
- `ntoskrnl!IofCompleteRequest` at `0x14000cf98`
- `ntoskrnl!IofCompleteRequest` at `0x14000cfd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cfae`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000cfae`

## pseudocode

```c
__int64 __fastcall NpFsdWrite(__int64 a1, __int64 a2)
{
  __int64 v2; // rbx
  _QWORD *v4; // rbx
  IRP *v5; // rcx
  unsigned int v6; // ebx
  _QWORD v8[2]; // [rsp+40h] [rbp-28h] BYREF
  __int128 v9; // [rsp+50h] [rbp-18h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v8[1] = v8;
  v8[0] = v8;
  v9 = 0;
  KeEnterCriticalRegion();
  NpCommonWrite(
    *(_QWORD *)(v2 + 48),
    *(void **)(a2 + 112),
    *(unsigned int *)(v2 + 8),
    *(_QWORD *)(a2 + 152),
    (__int64)&v9,
    a2,
    (__int64)v8);
  v4 = (_QWORD *)v8[0];
  while ( v4 != v8 )
  {
    v5 = (IRP *)(v4 - 21);
    v4 = (_QWORD *)*v4;
    IofCompleteRequest(v5, 2);
  }
  KeLeaveCriticalRegion();
  v6 = v9;
  if ( (_DWORD)v9 != 259 )
  {
    *(_QWORD *)(a2 + 56) = *((_QWORD *)&v9 + 1);
    *(_DWORD *)(a2 + 48) = v6;
    IofCompleteRequest((PIRP)a2, 2);
  }
  return v6;
}

```

## disassembly

```asm
0x14000cf10  mov     [rsp+arg_0], rbx
0x14000cf15  push    rdi
0x14000cf16  sub     rsp, 60h
0x14000cf1a  mov     rbx, [rdx+0B8h]
0x14000cf21  lea     rax, [rsp+68h+var_28]
0x14000cf26  mov     [rsp+68h+var_20], rax
0x14000cf2b  xorps   xmm0, xmm0
0x14000cf2e  lea     rax, [rsp+68h+var_28]
0x14000cf33  mov     rdi, rdx
0x14000cf36  mov     [rsp+68h+var_28], rax
0x14000cf3b  movups  [rsp+68h+var_18], xmm0
0x14000cf40  call    cs:__imp_KeEnterCriticalRegion
0x14000cf47  nop     dword ptr [rax+rax+00h]
0x14000cf4c  mov     r9, [rdi+98h]
0x14000cf53  lea     rax, [rsp+68h+var_28]
0x14000cf58  mov     r8d, [rbx+8]
0x14000cf5c  mov     rdx, [rdi+70h]
0x14000cf60  mov     rcx, [rbx+30h]
0x14000cf64  mov     [rsp+68h+var_38], rax
0x14000cf69  lea     rax, [rsp+68h+var_18]
0x14000cf6e  mov     [rsp+68h+var_40], rdi
0x14000cf73  mov     [rsp+68h+var_48], rax
0x14000cf78  call    NpCommonWrite
0x14000cf7d  mov     rbx, [rsp+68h+var_28]
0x14000cf82  lea     rax, [rsp+68h+var_28]
0x14000cf87  cmp     rbx, rax
0x14000cf8a  jz      short loc_14000CFAE
0x14000cf8c  lea     rcx, [rbx-0A8h]; Irp
0x14000cf93  mov     dl, 2; PriorityBoost
0x14000cf95  mov     rbx, [rbx]
0x14000cf98  call    cs:__imp_IofCompleteRequest
0x14000cf9f  nop     dword ptr [rax+rax+00h]
0x14000cfa4  lea     rax, [rsp+68h+var_28]
0x14000cfa9  cmp     rbx, rax
0x14000cfac  jnz     short loc_14000CF8C
0x14000cfae  call    cs:__imp_KeLeaveCriticalRegion
0x14000cfb5  nop     dword ptr [rax+rax+00h]
0x14000cfba  mov     ebx, dword ptr [rsp+68h+var_18]
0x14000cfbe  cmp     ebx, 103h
0x14000cfc4  jz      short loc_14000CFE3
0x14000cfc6  mov     rcx, qword ptr [rsp+68h+var_18+8]
0x14000cfcb  mov     dl, 2; PriorityBoost
0x14000cfcd  mov     [rdi+38h], rcx
0x14000cfd1  mov     rcx, rdi; Irp
0x14000cfd4  mov     [rdi+30h], ebx
0x14000cfd7  call    cs:__imp_IofCompleteRequest
0x14000cfde  nop     dword ptr [rax+rax+00h]
0x14000cfe3  mov     eax, ebx
0x14000cfe5  mov     rbx, [rsp+68h+arg_0]
0x14000cfea  add     rsp, 60h
0x14000cfee  pop     rdi
0x14000cfef  retn
```
