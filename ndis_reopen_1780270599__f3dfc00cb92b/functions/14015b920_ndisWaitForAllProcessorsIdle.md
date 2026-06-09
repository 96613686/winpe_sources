# ndisWaitForAllProcessorsIdle

- ea: `0x14015b920`
- end: `0x14015ba33`
- name: `ndisWaitForAllProcessorsIdle`
- size: `275`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14014d3a4`
- `0x14015bae0`

## callees

- `0x1400eb380`
- `0x14015b920`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14015b9c5`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14015b9c5`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14015ba09`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14015ba09`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14015b991`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x14015b991`
- `ntoskrnl!KeQueryActiveGroupCount` at `0x14015b950`
- `ntoskrnl!KeQueryActiveGroupCount` at `0x14015b950`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14015b96d`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14015b9f8`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14015b96d`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14015b9f8`

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
0x14015b920  mov     [rsp+arg_10], rbx
0x14015b925  push    rbp
0x14015b926  push    rsi
0x14015b927  push    rdi
0x14015b928  sub     rsp, 50h
0x14015b92c  mov     rax, cs:__security_cookie
0x14015b933  xor     rax, rsp
0x14015b936  mov     [rsp+68h+var_28], rax
0x14015b93b  xorps   xmm0, xmm0
0x14015b93e  lea     rbp, [rsp+68h+PreviousAffinity]
0x14015b943  xorps   xmm1, xmm1
0x14015b946  movups  xmmword ptr [rsp+68h+Affinity.Mask], xmm0
0x14015b94b  movups  xmmword ptr [rsp+68h+PreviousAffinity.Mask], xmm1
0x14015b950  call    cs:__imp_KeQueryActiveGroupCount
0x14015b957  nop     dword ptr [rax+rax+00h]
0x14015b95c  mov     rcx, gs:188h
0x14015b965  mov     edx, 2
0x14015b96a  movzx   edi, ax
0x14015b96d  call    cs:__imp_KeSetActualBasePriorityThread
0x14015b974  nop     dword ptr [rax+rax+00h]
0x14015b979  xor     ecx, ecx
0x14015b97b  xor     esi, esi
0x14015b97d  mov     ebx, eax
0x14015b97f  cmp     cx, di
0x14015b982  jnb     short loc_14015B9ED
0x14015b984  mov     [rsp+68h+arg_0], r14
0x14015b989  mov     [rsp+68h+arg_8], r15
0x14015b98e  movzx   ecx, si; GroupNumber
0x14015b991  call    cs:__imp_KeQueryActiveProcessorCountEx
0x14015b998  nop     dword ptr [rax+rax+00h]
0x14015b99d  xor     r14d, r14d
0x14015b9a0  mov     [rsp+68h+Affinity.Group], si
0x14015b9a5  mov     r15d, eax
0x14015b9a8  test    eax, eax
0x14015b9aa  jz      short loc_14015B9DB
0x14015b9ac  mov     ecx, r14d
0x14015b9af  mov     r8d, 1
0x14015b9b5  shl     r8, cl
0x14015b9b8  mov     rdx, rbp; PreviousAffinity
0x14015b9bb  lea     rcx, [rsp+68h+Affinity]; Affinity
0x14015b9c0  mov     [rsp+68h+Affinity.Mask], r8
0x14015b9c5  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14015b9cc  nop     dword ptr [rax+rax+00h]
0x14015b9d1  xor     ebp, ebp
0x14015b9d3  inc     r14d
0x14015b9d6  cmp     r14d, r15d
0x14015b9d9  jb      short loc_14015B9AC
0x14015b9db  inc     si
0x14015b9de  cmp     si, di
0x14015b9e1  jb      short loc_14015B98E
0x14015b9e3  mov     r15, [rsp+68h+arg_8]
0x14015b9e8  mov     r14, [rsp+68h+arg_0]
0x14015b9ed  mov     rcx, gs:188h
0x14015b9f6  mov     edx, ebx
0x14015b9f8  call    cs:__imp_KeSetActualBasePriorityThread
0x14015b9ff  nop     dword ptr [rax+rax+00h]
0x14015ba04  lea     rcx, [rsp+68h+PreviousAffinity]; PreviousAffinity
0x14015ba09  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14015ba10  nop     dword ptr [rax+rax+00h]
0x14015ba15  mov     rcx, [rsp+68h+var_28]
0x14015ba1a  xor     rcx, rsp; StackCookie
0x14015ba1d  call    __security_check_cookie
0x14015ba22  mov     rbx, [rsp+68h+arg_10]
0x14015ba2a  add     rsp, 50h
0x14015ba2e  pop     rdi
0x14015ba2f  pop     rsi
0x14015ba30  pop     rbp
0x14015ba31  retn
```
