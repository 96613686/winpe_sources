# MapKernelContextHandle

- ea: `0x1800017c4`
- end: `0x1800018a8`
- name: `MapKernelContextHandle`
- size: `228`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800218c0`
- `0x180024130`
- `0x180024910`

## callees

- `0x1800017c4`
- `0x180001c00`
- `0x180001cf0`
- `0x18002923c`

## import_xrefs

- `ntoskrnl!MmIsUserAddress` at `0x180001837`
- `ntoskrnl!MmIsUserAddress` at `0x180001837`

## pseudocode

```c
__int64 __fastcall MapKernelContextHandle(_QWORD *a1, _OWORD *a2)
{
  unsigned int v4; // ebx
  int v5; // esi
  __int128 v6; // xmm0
  __int64 v8; // [rsp+40h] [rbp+18h] BYREF

  KsecddLsaStateRef::KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
  if ( !v8 )
  {
    v4 = -1073741058;
LABEL_13:
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
    return v4;
  }
  if ( !*(_QWORD *)(v8 + 456) )
  {
    v4 = -1073741823;
    goto LABEL_13;
  }
  if ( a1 && a2 )
  {
    if ( *a1 || a1[1] )
    {
      if ( *a1 < (unsigned __int64)*(unsigned int *)(v8 + 464) && (unsigned __int8)MmIsUserAddress(a1[1]) )
      {
        v6 = *(_OWORD *)a1;
        v4 = 0;
        *a2 = v6;
        goto LABEL_13;
      }
      v5 = KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned __int64 *),24>::InvokeById(
             *a1,
             a1[1],
             (char *)a2 + 8);
      if ( v5 >= 0 )
        *(_QWORD *)a2 = *a1;
    }
    else
    {
      v5 = 0;
      *a2 = *(_OWORD *)a1;
    }
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
    return (unsigned int)v5;
  }
  else
  {
    KsecddLsaStateRef::~KsecddLsaStateRef((KsecddLsaStateRef *)&v8);
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x1800017c4  mov     [rsp+arg_0], rbx
0x1800017c9  mov     [rsp+arg_8], rsi
0x1800017ce  push    rdi
0x1800017cf  sub     rsp, 20h
0x1800017d3  mov     rbx, rcx
0x1800017d6  mov     rdi, rdx
0x1800017d9  lea     rcx, [rsp+28h+arg_10]; this
0x1800017de  call    ??0KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::KsecddLsaStateRef(void)
0x1800017e3  mov     rax, [rsp+28h+arg_10]
0x1800017e8  test    rax, rax
0x1800017eb  jnz     short loc_1800017F4
0x1800017ed  mov     ebx, 0C00002FEh
0x1800017f2  jmp     short loc_180001850
0x1800017f4  cmp     qword ptr [rax+1C8h], 0
0x1800017fc  jnz     short loc_180001805
0x1800017fe  mov     ebx, 0C0000001h
0x180001803  jmp     short loc_180001850
0x180001805  test    rbx, rbx
0x180001808  jz      short loc_180001888
0x18000180a  test    rdi, rdi
0x18000180d  jz      short loc_180001888
0x18000180f  mov     rdx, [rbx]
0x180001812  test    rdx, rdx
0x180001815  jnz     short loc_180001828
0x180001817  cmp     [rbx+8], rdx
0x18000181b  jnz     short loc_180001828
0x18000181d  movups  xmm0, xmmword ptr [rbx]
0x180001820  xor     esi, esi
0x180001822  movdqu  xmmword ptr [rdi], xmm0
0x180001826  jmp     short loc_18000187A
0x180001828  mov     ecx, [rax+1D0h]
0x18000182e  cmp     rdx, rcx
0x180001831  jnb     short loc_18000185E
0x180001833  mov     rcx, [rbx+8]
0x180001837  call    cs:__imp_MmIsUserAddress
0x18000183e  nop     dword ptr [rax+rax+00h]
0x180001843  test    al, al
0x180001845  jz      short loc_18000185E
0x180001847  movups  xmm0, xmmword ptr [rbx]
0x18000184a  xor     ebx, ebx
0x18000184c  movdqu  xmmword ptr [rdi], xmm0
0x180001850  lea     rcx, [rsp+28h+arg_10]; this
0x180001855  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x18000185a  mov     eax, ebx
0x18000185c  jmp     short loc_180001897
0x18000185e  mov     rdx, [rbx+8]
0x180001862  lea     r8, [rdi+8]
0x180001866  mov     rcx, [rbx]
0x180001869  call    ?InvokeById@?$CallValidator@PEQ_SECPKG_KERNEL_FUNCTION_TABLE@@P6AJ_KPEA_K@Z$0BI@@KernelPackageCallValidatorWorkers@@SAJ_K0PEA_K@Z; KernelPackageCallValidatorWorkers::CallValidator<long (*_SECPKG_KERNEL_FUNCTION_TABLE::*)(unsigned __int64,unsigned __int64 *),24>::InvokeById(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000186e  mov     esi, eax
0x180001870  test    eax, eax
0x180001872  js      short loc_18000187A
0x180001874  mov     rcx, [rbx]
0x180001877  mov     [rdi], rcx
0x18000187a  lea     rcx, [rsp+28h+arg_10]; this
0x18000187f  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180001884  mov     eax, esi
0x180001886  jmp     short loc_180001897
0x180001888  lea     rcx, [rsp+28h+arg_10]; this
0x18000188d  call    ??1KsecddLsaStateRef@@QEAA@XZ; KsecddLsaStateRef::~KsecddLsaStateRef(void)
0x180001892  mov     eax, 0C000000Dh
0x180001897  mov     rbx, [rsp+28h+arg_0]
0x18000189c  mov     rsi, [rsp+28h+arg_8]
0x1800018a1  add     rsp, 20h
0x1800018a5  pop     rdi
0x1800018a6  retn
```
