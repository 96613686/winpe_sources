# ndisWaitForAllProcessorsIdle

- ea: `0x140154980`
- end: `0x140154a93`
- name: `ndisWaitForAllProcessorsIdle`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140146404`
- `0x140154b40`

## callees

- `0x1400e6160`
- `0x140154980`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140154a25`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140154a25`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140154a69`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140154a69`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1401549f1`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x1401549f1`
- `ntoskrnl!KeQueryActiveGroupCount` at `0x1401549b0`
- `ntoskrnl!KeQueryActiveGroupCount` at `0x1401549b0`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1401549cd`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140154a58`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1401549cd`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x140154a58`

## pseudocode

```c
void ndisWaitForAllProcessorsIdle()
{
  struct _GROUP_AFFINITY *p_PreviousAffinity; // rbp
  USHORT ActiveGroupCount; // di
  USHORT v2; // si
  unsigned int i; // ebx
  ULONG ActiveProcessorCount; // eax
  ULONG v5; // r14d
  ULONG j; // r15d
  struct _GROUP_AFFINITY Affinity; // [rsp+20h] [rbp-48h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+30h] [rbp-38h] BYREF

  p_PreviousAffinity = &PreviousAffinity;
  Affinity = 0;
  PreviousAffinity = 0;
  ActiveGroupCount = KeQueryActiveGroupCount();
  v2 = 0;
  for ( i = KeSetActualBasePriorityThread(KeGetCurrentThread(), 2); v2 < ActiveGroupCount; ++v2 )
  {
    ActiveProcessorCount = KeQueryActiveProcessorCountEx(v2);
    v5 = 0;
    Affinity.Group = v2;
    for ( j = ActiveProcessorCount; v5 < j; ++v5 )
    {
      Affinity.Mask = 1LL << v5;
      KeSetSystemGroupAffinityThread(&Affinity, p_PreviousAffinity);
      p_PreviousAffinity = 0;
    }
  }
  KeSetActualBasePriorityThread(KeGetCurrentThread(), i);
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
}

```

## disassembly

```asm
0x140154980  mov     [rsp+arg_10], rbx
0x140154985  push    rbp
0x140154986  push    rsi
0x140154987  push    rdi
0x140154988  sub     rsp, 50h
0x14015498c  mov     rax, cs:__security_cookie
0x140154993  xor     rax, rsp
0x140154996  mov     [rsp+68h+var_28], rax
0x14015499b  xorps   xmm0, xmm0
0x14015499e  lea     rbp, [rsp+68h+PreviousAffinity]
0x1401549a3  xorps   xmm1, xmm1
0x1401549a6  movups  xmmword ptr [rsp+68h+Affinity.Mask], xmm0
0x1401549ab  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm1
0x1401549b0  call    cs:__imp_KeQueryActiveGroupCount
0x1401549b7  nop     dword ptr [rax+rax+00h]
0x1401549bc  mov     rcx, gs:188h
0x1401549c5  mov     edx, 2
0x1401549ca  movzx   edi, ax
0x1401549cd  call    cs:__imp_KeSetActualBasePriorityThread
0x1401549d4  nop     dword ptr [rax+rax+00h]
0x1401549d9  xor     ecx, ecx
0x1401549db  xor     esi, esi
0x1401549dd  mov     ebx, eax
0x1401549df  cmp     cx, di
0x1401549e2  jnb     short loc_140154A4D
0x1401549e4  mov     [rsp+68h+arg_0], r14
0x1401549e9  mov     [rsp+68h+arg_8], r15
0x1401549ee  movzx   ecx, si; GroupNumber
0x1401549f1  call    cs:__imp_KeQueryActiveProcessorCountEx
0x1401549f8  nop     dword ptr [rax+rax+00h]
0x1401549fd  xor     r14d, r14d
0x140154a00  mov     [rsp+68h+Affinity.Group], si
0x140154a05  mov     r15d, eax
0x140154a08  test    eax, eax
0x140154a0a  jz      short loc_140154A3B
0x140154a0c  mov     ecx, r14d
0x140154a0f  mov     r8d, 1
0x140154a15  shl     r8, cl
0x140154a18  mov     rdx, rbp; PreviousAffinity
0x140154a1b  lea     rcx, [rsp+68h+Affinity]; Affinity
0x140154a20  mov     [rsp+68h+Affinity.Mask], r8
0x140154a25  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140154a2c  nop     dword ptr [rax+rax+00h]
0x140154a31  xor     ebp, ebp
0x140154a33  inc     r14d
0x140154a36  cmp     r14d, r15d
0x140154a39  jb      short loc_140154A0C
0x140154a3b  inc     si
0x140154a3e  cmp     si, di
0x140154a41  jb      short loc_1401549EE
0x140154a43  mov     r15, [rsp+68h+arg_8]
0x140154a48  mov     r14, [rsp+68h+arg_0]
0x140154a4d  mov     rcx, gs:188h
0x140154a56  mov     edx, ebx
0x140154a58  call    cs:__imp_KeSetActualBasePriorityThread
0x140154a5f  nop     dword ptr [rax+rax+00h]
0x140154a64  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x140154a69  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140154a70  nop     dword ptr [rax+rax+00h]
0x140154a75  mov     rcx, [rsp+68h+var_28]
0x140154a7a  xor     rcx, rsp; StackCookie
0x140154a7d  call    __security_check_cookie
0x140154a82  mov     rbx, [rsp+68h+arg_10]
0x140154a8a  add     rsp, 50h
0x140154a8e  pop     rdi
0x140154a8f  pop     rsi
0x140154a90  pop     rbp
0x140154a91  retn
```
