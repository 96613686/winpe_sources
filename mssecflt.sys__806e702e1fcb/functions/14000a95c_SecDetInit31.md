# SecDetInit31

- ea: `0x14000a95c`
- end: `0x14000ab47`
- name: `SecDetInit31`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x140041a44`

## callees

- `0x14000a95c`
- `0x140010194`
- `0x140011610`
- `0x140011650`

## import_xrefs

- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000aa86`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14000aa86`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000aa9e`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14000aa9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a9d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000aa2c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000a9d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000aa2c`

## pseudocode

```c
PVOID SecDetInit31()
{
  _QWORD *v0; // rdi
  SIZE_T v1; // rdx
  PVOID result; // rax
  ULONG i; // r14d
  PVOID PoolWithTag; // rax
  __int64 v5; // rsi
  __int64 v6; // rbx
  unsigned __int16 *v7; // rbx
  __int64 v8; // r8
  __int64 *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  _TBYTE v12; // [rsp+20h] [rbp-40h] BYREF
  _PROCESSOR_NUMBER ProcNumber; // [rsp+30h] [rbp-30h] BYREF
  _GROUP_AFFINITY Affinity; // [rsp+38h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+48h] [rbp-18h] BYREF

  v0 = DetectionContext;
  v12 = 0.0;
  ProcNumber = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  v1 = 32LL * *((unsigned int *)DetectionContext + 20);
  if ( qword_140020008 )
    result = (PVOID)qword_140020008(256, v1, 1698980691);
  else
    result = ExAllocatePoolWithTag(PagedPool, v1, 0x65446353u);
  v0[1] = result;
  if ( result )
  {
    result = DetectionContext;
    for ( i = 0; i < *((_DWORD *)DetectionContext + 20); ++i )
    {
      if ( qword_140020008 )
        PoolWithTag = (PVOID)qword_140020008(256, 4096, 1698980691);
      else
        PoolWithTag = ExAllocatePoolWithTag(PagedPool, 0x1000u, 0x65446353u);
      v5 = 32LL * i;
      *(_QWORD *)(v5 + v0[1] + 24) = PoolWithTag;
      if ( *(_QWORD *)(v5 + v0[1] + 24) )
      {
        KeGetProcessorNumberFromIndex_0(i, &ProcNumber);
        Affinity.Group = ProcNumber.Group;
        Affinity.Mask = 1LL << ProcNumber.Number;
        KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
        __sidt(&v12);
        v6 = *(_QWORD *)((char *)&v12 + 2);
        KeRevertToUserGroupAffinityThread(&PreviousAffinity);
        v7 = (unsigned __int16 *)(v6 + 6);
        v8 = 256;
        v9 = *(__int64 **)(v0[1] + v5 + 24);
        do
        {
          v10 = *v7;
          v11 = *(unsigned int *)(v7 + 1);
          v7 += 8;
          *v9++ = *(v7 - 11) | ((v10 | (v11 << 16)) << 16);
          --v8;
        }
        while ( v8 );
        *(_DWORD *)(v5 + v0[1]) = 3;
        *(_QWORD *)(v0[1] + v5 + 8) = *(_QWORD *)((char *)&v12 + 2);
        *(_DWORD *)(v0[1] + v5 + 16) = LOWORD(v12) + 1;
      }
      result = DetectionContext;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a95c  mov     rax, rsp
0x14000a95f  mov     [rax+8], rbx
0x14000a963  mov     [rax+10h], rsi
0x14000a967  mov     [rax+18h], rdi
0x14000a96b  mov     [rax+20h], r14
0x14000a96f  push    rbp
0x14000a970  mov     rbp, rsp
0x14000a973  sub     rsp, 60h
0x14000a977  mov     rax, cs:__security_cookie
0x14000a97e  xor     rax, rsp
0x14000a981  mov     [rbp+var_8], rax
0x14000a985  mov     rdi, cs:DetectionContext
0x14000a98c  xor     eax, eax
0x14000a98e  mov     [rbp+var_40], rax
0x14000a992  xorps   xmm0, xmm0
0x14000a995  mov     [rbp+var_38], ax
0x14000a999  xorps   xmm1, xmm1
0x14000a99c  mov     rax, cs:qword_140020008
0x14000a9a3  mov     r8d, 65446353h; Tag
0x14000a9a9  mov     dword ptr [rbp+ProcNumber.Group], 0
0x14000a9b0  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14000a9b4  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x14000a9b8  mov     edx, [rdi+50h]
0x14000a9bb  shl     rdx, 5; NumberOfBytes
0x14000a9bf  test    rax, rax
0x14000a9c2  jz      short loc_14000A9D1
0x14000a9c4  mov     ecx, 100h
0x14000a9c9  call    cs:__guard_dispatch_icall_fptr
0x14000a9cf  jmp     short loc_14000A9E2
0x14000a9d1  mov     ecx, 1; PoolType
0x14000a9d6  call    cs:__imp_ExAllocatePoolWithTag
0x14000a9dd  nop     dword ptr [rax+rax+00h]
0x14000a9e2  mov     [rdi+8], rax
0x14000a9e6  test    rax, rax
0x14000a9e9  jz      loc_14000AB20
0x14000a9ef  mov     rax, cs:DetectionContext
0x14000a9f6  xor     r14d, r14d
0x14000a9f9  cmp     [rax+50h], r14d
0x14000a9fd  jbe     loc_14000AB20
0x14000aa03  mov     rax, cs:qword_140020008
0x14000aa0a  mov     edx, 1000h; NumberOfBytes
0x14000aa0f  mov     r8d, 65446353h; Tag
0x14000aa15  test    rax, rax
0x14000aa18  jz      short loc_14000AA27
0x14000aa1a  mov     ecx, 100h
0x14000aa1f  call    cs:__guard_dispatch_icall_fptr
0x14000aa25  jmp     short loc_14000AA38
0x14000aa27  mov     ecx, 1; PoolType
0x14000aa2c  call    cs:__imp_ExAllocatePoolWithTag
0x14000aa33  nop     dword ptr [rax+rax+00h]
0x14000aa38  mov     rcx, rax
0x14000aa3b  mov     esi, r14d
0x14000aa3e  mov     rax, [rdi+8]
0x14000aa42  shl     rsi, 5
0x14000aa46  mov     [rsi+rax+18h], rcx
0x14000aa4b  mov     rax, [rdi+8]
0x14000aa4f  cmp     qword ptr [rsi+rax+18h], 0
0x14000aa55  jz      loc_14000AB0C
0x14000aa5b  lea     rdx, [rbp+ProcNumber]; ProcNumber
0x14000aa5f  mov     ecx, r14d; ProcIndex
0x14000aa62  call    KeGetProcessorNumberFromIndex_0
0x14000aa67  movzx   eax, [rbp+ProcNumber.Group]
0x14000aa6b  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x14000aa6f  mov     cl, [rbp+ProcNumber.Number]
0x14000aa72  mov     [rbp+Affinity.Group], ax
0x14000aa76  mov     eax, 1
0x14000aa7b  shl     rax, cl
0x14000aa7e  lea     rcx, [rbp+Affinity]; Affinity
0x14000aa82  mov     [rbp+Affinity.Mask], rax
0x14000aa86  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14000aa8d  nop     dword ptr [rax+rax+00h]
0x14000aa92  sidt    fword ptr [rbp+var_40]
0x14000aa96  mov     rbx, [rbp+var_40+2]
0x14000aa9a  lea     rcx, [rbp+PreviousAffinity]; PreviousAffinity
0x14000aa9e  call    cs:__imp_KeRevertToUserGroupAffinityThread
0x14000aaa5  nop     dword ptr [rax+rax+00h]
0x14000aaaa  mov     rax, [rdi+8]
0x14000aaae  add     rbx, 6
0x14000aab2  mov     r8d, 100h
0x14000aab8  mov     rdx, [rax+rsi+18h]
0x14000aabd  movzx   eax, word ptr [rbx]
0x14000aac0  mov     ecx, [rbx+2]
0x14000aac3  lea     rbx, [rbx+10h]
0x14000aac7  shl     rcx, 10h
0x14000aacb  or      rcx, rax
0x14000aace  movzx   eax, word ptr [rbx-16h]
0x14000aad2  shl     rcx, 10h
0x14000aad6  or      rcx, rax
0x14000aad9  mov     [rdx], rcx
0x14000aadc  lea     rdx, [rdx+8]
0x14000aae0  sub     r8, 1
0x14000aae4  jnz     short loc_14000AABD
0x14000aae6  mov     rax, [rdi+8]
0x14000aaea  mov     dword ptr [rsi+rax], 3
0x14000aaf1  mov     rcx, [rdi+8]
0x14000aaf5  mov     rax, [rbp+var_40+2]
0x14000aaf9  mov     [rcx+rsi+8], rax
0x14000aafe  movzx   ecx, word ptr [rbp+var_40]
0x14000ab02  mov     rax, [rdi+8]
0x14000ab06  inc     ecx
0x14000ab08  mov     [rax+rsi+10h], ecx
0x14000ab0c  mov     rax, cs:DetectionContext
0x14000ab13  inc     r14d
0x14000ab16  cmp     r14d, [rax+50h]
0x14000ab1a  jb      loc_14000AA03
0x14000ab20  mov     rcx, [rbp+var_8]
0x14000ab24  xor     rcx, rsp; StackCookie
0x14000ab27  call    __security_check_cookie
0x14000ab2c  lea     r11, [rsp+60h+var_s0]
0x14000ab31  mov     rbx, [r11+10h]
0x14000ab35  mov     rsi, [r11+18h]
0x14000ab39  mov     rdi, [r11+20h]
0x14000ab3d  mov     r14, [r11+28h]
0x14000ab41  mov     rsp, r11
0x14000ab44  pop     rbp
0x14000ab45  retn
```
