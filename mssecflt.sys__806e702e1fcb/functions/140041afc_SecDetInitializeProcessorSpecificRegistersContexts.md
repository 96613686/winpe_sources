# SecDetInitializeProcessorSpecificRegistersContexts

- ea: `0x140041afc`
- end: `0x140041c9f`
- name: `SecDetInitializeProcessorSpecificRegistersContexts`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140041a44`

## callees

- `0x140010194`
- `0x140011610`
- `0x140011650`
- `0x140041afc`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140041c0d`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x140041c0d`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140041c7a`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x140041c7a`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140041b3c`
- `ntoskrnl!KeQueryActiveProcessorCountEx` at `0x140041b3c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041b93`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140041b93`

## pseudocode

```c
void SecDetInitializeProcessorSpecificRegistersContexts()
{
  _DWORD *v0; // rbx
  char v1; // di
  PVOID PoolWithTag; // rax
  __int64 i; // rbx
  unsigned __int64 v4; // rdx
  __int64 v5; // r9
  __int64 v6; // rcx
  unsigned __int64 v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rax
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+20h] [rbp-38h] BYREF
  struct _GROUP_AFFINITY Affinity; // [rsp+28h] [rbp-30h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+38h] [rbp-20h] BYREF

  v0 = DetectionContext;
  ProcNumber = 0;
  v1 = 1;
  Affinity = 0;
  PreviousAffinity = 0;
  v0[20] = KeQueryActiveProcessorCountEx(0xFFFFu);
  if ( qword_140020008 )
    PoolWithTag = (PVOID)qword_140020008(256, 24LL * *((unsigned int *)DetectionContext + 20), 1698980691);
  else
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, 24LL * *((unsigned int *)DetectionContext + 20), 0x65446353u);
  *((_QWORD *)DetectionContext + 11) = PoolWithTag;
  if ( *((_QWORD *)DetectionContext + 11) )
  {
    for ( i = 0;
          (unsigned int)i < *((_DWORD *)DetectionContext + 20);
          *(_QWORD *)(v8 + 8 * v5 + 16) = ((unsigned __int64)HIDWORD(v9) << 32) | (unsigned int)v9 )
    {
      KeGetProcessorNumberFromIndex_0(i, &ProcNumber);
      Affinity.Group = ProcNumber.Group;
      Affinity.Mask = 1LL << ProcNumber.Number;
      KeSetSystemGroupAffinityThread(
        &Affinity,
        (PGROUP_AFFINITY)((unsigned __int64)&PreviousAffinity & -(__int64)(v1 != 0)));
      v1 = 0;
      v4 = __readcr4();
      v5 = 3 * i;
      *(_QWORD *)(*((_QWORD *)DetectionContext + 11) + 8 * v5) = v4;
      v6 = *((_QWORD *)DetectionContext + 11);
      v7 = __readcr0();
      *(_QWORD *)(v6 + 8 * v5 + 8) = v7;
      v8 = *((_QWORD *)DetectionContext + 11);
      v9 = __readmsr(0xC0000082);
      i = (unsigned int)(i + 1);
    }
    KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  }
}

```

## disassembly

```asm
0x140041afc  mov     [rsp+arg_0], rbx
0x140041b01  push    rdi
0x140041b02  sub     rsp, 50h
0x140041b06  mov     rax, cs:__security_cookie
0x140041b0d  xor     rax, rsp
0x140041b10  mov     [rsp+58h+var_10], rax
0x140041b15  mov     rbx, cs:DetectionContext
0x140041b1c  xorps   xmm0, xmm0
0x140041b1f  xorps   xmm1, xmm1
0x140041b22  mov     dword ptr [rsp+58h+ProcNumber.Group], 0
0x140041b2a  mov     ecx, 0FFFFh; GroupNumber
0x140041b2f  mov     dil, 1
0x140041b32  movups  xmmword ptr [rsp+58h+Affinity.Mask], xmm0
0x140041b37  movups  xmmword ptr [rsp+58h+PreviousAffinity.Mask], xmm1
0x140041b3c  call    cs:__imp_KeQueryActiveProcessorCountEx
0x140041b43  nop     dword ptr [rax+rax+00h]
0x140041b48  mov     [rbx+50h], eax
0x140041b4b  mov     r8d, 65446353h; Tag
0x140041b51  mov     rax, cs:qword_140020008
0x140041b58  test    rax, rax
0x140041b5b  jz      short loc_140041B7C
0x140041b5d  mov     rcx, cs:DetectionContext
0x140041b64  mov     edx, [rcx+50h]
0x140041b67  mov     ecx, 100h
0x140041b6c  lea     rdx, [rdx+rdx*2]
0x140041b70  shl     rdx, 3
0x140041b74  call    cs:__guard_dispatch_icall_fptr
0x140041b7a  jmp     short loc_140041B9F
0x140041b7c  mov     rax, cs:DetectionContext
0x140041b83  mov     ecx, [rax+50h]
0x140041b86  lea     rdx, [rcx+rcx*2]
0x140041b8a  mov     ecx, 1; PoolType
0x140041b8f  shl     rdx, 3; NumberOfBytes
0x140041b93  call    cs:__imp_ExAllocatePoolWithTag
0x140041b9a  nop     dword ptr [rax+rax+00h]
0x140041b9f  mov     rcx, rax
0x140041ba2  mov     rax, cs:DetectionContext
0x140041ba9  mov     [rax+58h], rcx
0x140041bad  mov     rax, cs:DetectionContext
0x140041bb4  mov     rcx, [rax+58h]
0x140041bb8  test    rcx, rcx
0x140041bbb  jz      loc_140041C86
0x140041bc1  mov     rax, cs:DetectionContext
0x140041bc8  xor     ebx, ebx
0x140041bca  cmp     [rax+50h], ebx
0x140041bcd  jbe     loc_140041C75
0x140041bd3  lea     rdx, [rsp+58h+ProcNumber]; ProcNumber
0x140041bd8  mov     ecx, ebx; ProcIndex
0x140041bda  call    KeGetProcessorNumberFromIndex_0
0x140041bdf  movzx   eax, [rsp+58h+ProcNumber.Group]
0x140041be4  mov     cl, [rsp+58h+ProcNumber.Number]
0x140041be8  mov     [rsp+58h+Affinity.Group], ax
0x140041bed  mov     eax, 1
0x140041bf2  shl     rax, cl
0x140041bf5  lea     rcx, [rsp+58h+Affinity]; Affinity
0x140041bfa  mov     [rsp+58h+Affinity.Mask], rax
0x140041bff  neg     dil
0x140041c02  lea     rax, [rsp+58h+PreviousAffinity]
0x140041c07  sbb     rdx, rdx
0x140041c0a  and     rdx, rax; PreviousAffinity
0x140041c0d  call    cs:__imp_KeSetSystemGroupAffinityThread
0x140041c14  nop     dword ptr [rax+rax+00h]
0x140041c19  xor     dil, dil
0x140041c1c  mov     rdx, cr4
0x140041c1f  mov     rax, cs:DetectionContext
0x140041c26  lea     r9, [rbx+rbx*2]
0x140041c2a  mov     rcx, [rax+58h]
0x140041c2e  mov     [rcx+r9*8], rdx
0x140041c32  mov     rax, cs:DetectionContext
0x140041c39  mov     rcx, [rax+58h]
0x140041c3d  mov     rax, cr0
0x140041c40  mov     [rcx+r9*8+8], rax
0x140041c45  mov     ecx, 0C0000082h
0x140041c4a  mov     rax, cs:DetectionContext
0x140041c51  mov     r8, [rax+58h]
0x140041c55  rdmsr
0x140041c57  shl     rdx, 20h
0x140041c5b  inc     ebx
0x140041c5d  or      rax, rdx
0x140041c60  mov     [r8+r9*8+10h], rax
0x140041c65  mov     rax, cs:DetectionContext
0x140041c6c  cmp     ebx, [rax+50h]
0x140041c6f  jb      loc_140041BD3
0x140041c75  lea     rcx, [rsp+58h+PreviousAffinity]; PreviousAffinity
0x140041c7a  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x140041c81  nop     dword ptr [rax+rax+00h]
0x140041c86  mov     rcx, [rsp+58h+var_10]
0x140041c8b  xor     rcx, rsp; StackCookie
0x140041c8e  call    __security_check_cookie
0x140041c93  mov     rbx, [rsp+58h+arg_0]
0x140041c98  add     rsp, 50h
0x140041c9c  pop     rdi
0x140041c9d  retn
```
