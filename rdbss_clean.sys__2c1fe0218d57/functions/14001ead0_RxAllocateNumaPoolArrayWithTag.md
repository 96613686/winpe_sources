# RxAllocateNumaPoolArrayWithTag

- ea: `0x14001ead0`
- end: `0x14001ec04`
- name: `RxAllocateNumaPoolArrayWithTag`
- size: `308`
- prototype: `__int64 __fastcall(int, int, int, int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14004c7b8`

## callees

- `0x14001ead0`
- `0x140025c20`
- `0x140026080`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001eb7b`
- `ntoskrnl!ExAllocatePool2` at `0x14001eb7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ebca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001ebca`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001eb47`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001eb47`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001eb64`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001eb64`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001eb99`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001eb99`

## pseudocode

```c
__int64 __fastcall RxAllocateNumaPoolArrayWithTag(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4, void *a5)
{
  unsigned int v9; // ebp
  unsigned int i; // ebx
  unsigned int v11; // ebx
  __int64 v12; // rsi
  void *v13; // rcx
  USHORT Count; // [rsp+20h] [rbp-78h] BYREF
  _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-70h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-60h] BYREF

  v9 = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  memset(a5, 0, 8LL * (a4 + 1));
  for ( i = 0; i <= a4; ++i )
  {
    Count = 0;
    KeQueryNodeActiveAffinity(i, &Affinity, &Count);
    if ( Count )
      KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
    *((_QWORD *)a5 + i) = ExAllocatePool2(a1, a2, a3);
    if ( Count )
      KeRevertToUserGroupAffinityThread(&PreviousAffinity);
    if ( !*((_QWORD *)a5 + i) )
    {
      v9 = -1073741670;
      v11 = 0;
      do
      {
        v12 = v11;
        v13 = (void *)*((_QWORD *)a5 + v11);
        if ( !v13 )
          break;
        ExFreePoolWithTag(v13, 0);
        ++v11;
        *((_QWORD *)a5 + v12) = 0;
      }
      while ( v11 <= a4 );
      return v9;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14001ead0  push    rbx
0x14001ead2  push    rbp
0x14001ead3  push    rsi
0x14001ead4  push    rdi
0x14001ead5  push    r12
0x14001ead7  push    r13
0x14001ead9  push    r14
0x14001eadb  push    r15
0x14001eadd  sub     rsp, 58h
0x14001eae1  mov     rax, cs:__security_cookie
0x14001eae8  xor     rax, rsp
0x14001eaeb  mov     [rsp+98h+var_50], rax
0x14001eaf0  mov     rdi, [rsp+98h+arg_20]
0x14001eaf8  mov     r13d, r8d
0x14001eafb  lea     r8d, [r9+1]
0x14001eaff  mov     r12, rdx
0x14001eb02  mov     r15, rcx
0x14001eb05  shl     r8, 3; Size
0x14001eb09  xor     esi, esi
0x14001eb0b  xorps   xmm0, xmm0
0x14001eb0e  xorps   xmm1, xmm1
0x14001eb11  xor     edx, edx; Val
0x14001eb13  mov     rcx, rdi; void *
0x14001eb16  mov     r14d, r9d
0x14001eb19  mov     ebp, esi
0x14001eb1b  movups  xmmword ptr [rsp+98h+Affinity.Mask], xmm0
0x14001eb20  movups  xmmword ptr [rsp+98h+PreviousAffinity.Mask], xmm1
0x14001eb25  call    memset
0x14001eb2a  mov     ebx, esi
0x14001eb2c  cmp     ebx, r14d
0x14001eb2f  ja      loc_14001EBE3
0x14001eb35  movzx   ecx, bx; NodeNumber
0x14001eb38  mov     [rsp+98h+Count], si
0x14001eb3d  lea     r8, [rsp+98h+Count]; Count
0x14001eb42  lea     rdx, [rsp+98h+Affinity]; Affinity
0x14001eb47  call    cs:__imp_KeQueryNodeActiveAffinity
0x14001eb4e  nop     dword ptr [rax+rax+00h]
0x14001eb53  cmp     [rsp+98h+Count], si
0x14001eb58  jz      short loc_14001EB70
0x14001eb5a  lea     rdx, [rsp+98h+PreviousAffinity]; PreviousAffinity
0x14001eb5f  lea     rcx, [rsp+98h+Affinity]; Affinity
0x14001eb64  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001eb6b  nop     dword ptr [rax+rax+00h]
0x14001eb70  mov     r8d, r13d
0x14001eb73  mov     esi, ebx
0x14001eb75  mov     rdx, r12
0x14001eb78  mov     rcx, r15
0x14001eb7b  call    cs:__imp_ExAllocatePool2
0x14001eb82  nop     dword ptr [rax+rax+00h]
0x14001eb87  mov     [rdi+rsi*8], rax
0x14001eb8b  xor     eax, eax
0x14001eb8d  cmp     [rsp+98h+Count], ax
0x14001eb92  jz      short loc_14001EBA7
0x14001eb94  lea     rcx, [rsp+98h+PreviousAffinity]; PreviousAffinity
0x14001eb99  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14001eba0  nop     dword ptr [rax+rax+00h]
0x14001eba5  xor     eax, eax
0x14001eba7  cmp     [rdi+rsi*8], rax
0x14001ebab  jz      short loc_14001EBB6
0x14001ebad  inc     ebx
0x14001ebaf  xor     esi, esi
0x14001ebb1  jmp     loc_14001EB2C
0x14001ebb6  mov     ebp, 0C000009Ah
0x14001ebbb  mov     ebx, eax
0x14001ebbd  mov     esi, ebx
0x14001ebbf  mov     rcx, [rdi+rsi*8]; P
0x14001ebc3  test    rcx, rcx
0x14001ebc6  jz      short loc_14001EBE3
0x14001ebc8  xor     edx, edx; Tag
0x14001ebca  call    cs:__imp_ExFreePoolWithTag
0x14001ebd1  nop     dword ptr [rax+rax+00h]
0x14001ebd6  xor     eax, eax
0x14001ebd8  inc     ebx
0x14001ebda  mov     [rdi+rsi*8], rax
0x14001ebde  cmp     ebx, r14d
0x14001ebe1  jbe     short loc_14001EBBD
0x14001ebe3  mov     eax, ebp
0x14001ebe5  mov     rcx, [rsp+98h+var_50]
0x14001ebea  xor     rcx, rsp; StackCookie
0x14001ebed  call    __security_check_cookie
0x14001ebf2  add     rsp, 58h
0x14001ebf6  pop     r15
0x14001ebf8  pop     r14
0x14001ebfa  pop     r13
0x14001ebfc  pop     r12
0x14001ebfe  pop     rdi
0x14001ebff  pop     rsi
0x14001ec00  pop     rbp
0x14001ec01  pop     rbx
0x14001ec02  retn
```
