# CreateFiberEx

- ea: `0x1800f1950`
- end: `0x1800f1be4`
- name: `CreateFiberEx`
- size: `660`
- prototype: `LPVOID __stdcall(SIZE_T dwStackCommitSize, SIZE_T dwStackReserveSize, DWORD dwFlags, LPFIBER_START_ROUTINE lpStartAddress, LPVOID lpParameter)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800f1920`

## callees

- `0x18004b9d0`
- `0x1800f1950`
- `0x1800f1bec`
- `0x1800f1c3c`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800f1b14`
- `ntdll!RtlSetLastWin32Error` at `0x1800f1b14`
- `ntdll!RtlFreeHeap` at `0x1800f1b6f`
- `ntdll!RtlFreeHeap` at `0x1800f1bbd`
- `ntdll!RtlFreeHeap` at `0x1800f1b6f`
- `ntdll!RtlFreeHeap` at `0x1800f1bbd`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800f19a9`
- `ntdll!RtlAllocateActivationContextStack` at `0x1800f19a9`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b03`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b51`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b9f`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b03`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b51`
- `ntdll!RtlFreeActivationContextStack` at `0x1800f1b9f`
- `ntdll!RtlCreateUserStack` at `0x1800f1a12`
- `ntdll!RtlCreateUserStack` at `0x1800f1a12`
- `ntdll!RtlCreateUserFiberShadowStack` at `0x1800f1b32`
- `ntdll!RtlCreateUserFiberShadowStack` at `0x1800f1b32`
- `ntdll!RtlFreeUserStack` at `0x1800f1b7f`
- `ntdll!RtlFreeUserStack` at `0x1800f1b7f`
- `ntdll!RtlAllocateHeap` at `0x1800f19d6`
- `ntdll!RtlAllocateHeap` at `0x1800f19d6`

## pseudocode

```c
LPVOID __stdcall CreateFiberEx(
        SIZE_T dwStackCommitSize,
        SIZE_T dwStackReserveSize,
        DWORD dwFlags,
        LPFIBER_START_ROUTINE lpStartAddress,
        LPVOID lpParameter)
{
  int v5; // r12d
  char v6; // si
  __int64 NtdllRtlUserFiberStartAddress; // r14
  NTSTATUS v10; // eax
  unsigned __int64 Heap; // rdi
  int v12; // eax
  __int64 v14; // r8
  __int64 v15; // r8
  ULONG v17; // ecx
  int v18; // eax
  PACTIVATION_CONTEXT_STACK Stack; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  __int128 v21; // [rsp+40h] [rbp-30h] BYREF
  __int128 v22; // [rsp+50h] [rbp-20h]
  __int64 v23; // [rsp+60h] [rbp-10h]

  v23 = 0;
  v5 = (int)lpStartAddress;
  v20 = 0;
  v6 = dwFlags;
  Stack = 0;
  v21 = 0;
  v22 = 0;
  if ( (dwFlags & 0xFFFFFFFE) != 0 )
  {
    v17 = 87;
    goto LABEL_9;
  }
  NtdllRtlUserFiberStartAddress = BasepGetNtdllRtlUserFiberStartAddress();
  if ( !NtdllRtlUserFiberStartAddress )
  {
    v17 = 50;
    goto LABEL_9;
  }
  v10 = RtlAllocateActivationContextStack(&Stack);
  if ( v10 < 0 )
  {
    BaseSetLastNTError((unsigned int)v10);
    return 0;
  }
  Heap = (unsigned __int64)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x530u);
  if ( !Heap )
  {
    RtlFreeActivationContextStack(Stack);
    v17 = 8;
LABEL_9:
    RtlSetLastWin32Error(v17);
    return 0;
  }
  v12 = RtlCreateUserStack(
          dwStackCommitSize,
          dwStackReserveSize,
          0,
          (unsigned int)dword_1803AAE28,
          (unsigned int)dword_1803AAE38,
          &v21);
  if ( v12 < 0 )
  {
    BaseSetLastNTError((unsigned int)v12);
    RtlFreeActivationContextStack(Stack);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
  }
  else
  {
    v20 = 0;
    __asm { rdsspq  rax }
    if ( !_RAX || (v18 = RtlCreateUserFiberShadowStack(&v21, (unsigned int)dword_1803AAE28, &v20), v18 >= 0) )
    {
      memset_0((void *)(Heap + 48), 0, 0x4D0u);
      *(_QWORD *)Heap = lpParameter;
      v14 = v22;
      *(_QWORD *)(Heap + 16) = v22;
      v15 = BasepFiberCookie ^ Heap ^ v14;
      *(_QWORD *)(Heap + 24) = *((_QWORD *)&v22 + 1);
      *(_QWORD *)(Heap + 32) = v23;
      *(_WORD *)(Heap + 1308) = 0;
      *(_QWORD *)(Heap + 8) = -1;
      *(_QWORD *)(Heap + 1280) = 0;
      *(_QWORD *)(Heap + 1296) = 0;
      *(_DWORD *)(Heap + 1304) = 0;
      *(_QWORD *)(Heap + 1288) = Stack;
      *(_QWORD *)(Heap + 1312) = v15;
      *(_QWORD *)(Heap + 1320) = v20;
      *(_DWORD *)(Heap + 96) = (v6 & 1) != 0 ? 0x100008 : 0;
      BaseInitializeFiberContext(Heap + 48, (_DWORD)lpParameter, v5, v22, NtdllRtlUserFiberStartAddress);
      return (LPVOID)Heap;
    }
    BaseSetLastNTError((unsigned int)v18);
    RtlFreeActivationContextStack(Stack);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, (PVOID)Heap);
    RtlFreeUserStack(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x1800f1950  push    rbp
0x1800f1952  push    rbx
0x1800f1953  push    rsi
0x1800f1954  push    rdi
0x1800f1955  push    r12
0x1800f1957  push    r14
0x1800f1959  push    r15
0x1800f195b  mov     rbp, rsp
0x1800f195e  sub     rsp, 70h
0x1800f1962  xor     eax, eax
0x1800f1964  xorps   xmm0, xmm0
0x1800f1967  mov     [rbp+var_10], rax
0x1800f196b  mov     r12, r9
0x1800f196e  mov     [rbp+var_38], rax
0x1800f1972  mov     esi, r8d
0x1800f1975  mov     [rbp+Stack], rax
0x1800f1979  mov     rbx, rdx
0x1800f197c  mov     r15, rcx
0x1800f197f  movups  [rbp+var_30], xmm0
0x1800f1983  movups  [rbp+var_20], xmm0
0x1800f1987  test    r8d, 0FFFFFFFEh
0x1800f198e  jnz     loc_1800F1B8D
0x1800f1994  call    BasepGetNtdllRtlUserFiberStartAddress
0x1800f1999  mov     r14, rax
0x1800f199c  test    rax, rax
0x1800f199f  jz      loc_1800F1BCE
0x1800f19a5  lea     rcx, [rbp+Stack]; Stack
0x1800f19a9  call    cs:__imp_RtlAllocateActivationContextStack
0x1800f19b0  nop     dword ptr [rax+rax+00h]
0x1800f19b5  test    eax, eax
0x1800f19b7  js      loc_1800F1BD8
0x1800f19bd  mov     rcx, gs:60h
0x1800f19c6  mov     r8d, 530h; Size
0x1800f19cc  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800f19d2  mov     rcx, [rcx+30h]; HeapHandle
0x1800f19d6  call    cs:__imp_RtlAllocateHeap
0x1800f19dd  nop     dword ptr [rax+rax+00h]
0x1800f19e2  mov     rdi, rax
0x1800f19e5  test    rax, rax
0x1800f19e8  jz      loc_1800F1AFF
0x1800f19ee  mov     eax, cs:dword_1803AAE38
0x1800f19f4  lea     rcx, [rbp+var_30]
0x1800f19f8  mov     r9d, cs:dword_1803AAE28
0x1800f19ff  xor     r8d, r8d
0x1800f1a02  mov     [rsp+70h+var_48], rcx
0x1800f1a07  mov     rdx, rbx
0x1800f1a0a  mov     rcx, r15
0x1800f1a0d  mov     [rsp+70h+var_50], rax
0x1800f1a12  call    cs:__imp_RtlCreateUserStack
0x1800f1a19  nop     dword ptr [rax+rax+00h]
0x1800f1a1e  test    eax, eax
0x1800f1a20  js      loc_1800F1B94
0x1800f1a26  xor     eax, eax
0x1800f1a28  mov     [rbp+var_38], 0
0x1800f1a30  rdsspq  rax
0x1800f1a35  test    rax, rax
0x1800f1a38  jnz     loc_1800F1B24
0x1800f1a3e  xor     edx, edx; Val
0x1800f1a40  lea     rcx, [rdi+30h]; void *
0x1800f1a44  mov     r8d, 4D0h; Size
0x1800f1a4a  call    memset_0
0x1800f1a4f  mov     rdx, [rbp+lpParameter]
0x1800f1a53  lea     rcx, [rdi+30h]
0x1800f1a57  mov     [rdi], rdx
0x1800f1a5a  and     sil, 1
0x1800f1a5e  mov     r8, qword ptr [rbp+var_20]
0x1800f1a62  mov     [rdi+10h], r8
0x1800f1a66  xor     r8, rdi
0x1800f1a69  mov     rax, qword ptr [rbp+var_20+8]
0x1800f1a6d  xor     r8, cs:BasepFiberCookie
0x1800f1a74  mov     [rdi+18h], rax
0x1800f1a78  mov     rax, [rbp+var_10]
0x1800f1a7c  mov     [rdi+20h], rax
0x1800f1a80  xor     eax, eax
0x1800f1a82  mov     [rdi+51Ch], ax
0x1800f1a89  neg     sil
0x1800f1a8c  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x1800f1a94  mov     qword ptr [rdi+500h], 0
0x1800f1a9f  mov     qword ptr [rdi+510h], 0
0x1800f1aaa  mov     dword ptr [rdi+518h], 0
0x1800f1ab4  mov     rax, [rbp+Stack]
0x1800f1ab8  mov     [rdi+508h], rax
0x1800f1abf  mov     [rdi+520h], r8
0x1800f1ac6  mov     r8, r12
0x1800f1ac9  mov     rax, [rbp+var_38]
0x1800f1acd  mov     [rdi+528h], rax
0x1800f1ad4  sbb     eax, eax
0x1800f1ad6  and     eax, 100008h
0x1800f1adb  mov     [rsp+70h+var_50], r14
0x1800f1ae0  mov     [rdi+60h], eax
0x1800f1ae3  mov     r9, qword ptr [rbp+var_20]
0x1800f1ae7  call    BaseInitializeFiberContext
0x1800f1aec  mov     rax, rdi
0x1800f1aef  add     rsp, 70h
0x1800f1af3  pop     r15
0x1800f1af5  pop     r14
0x1800f1af7  pop     r12
0x1800f1af9  pop     rdi
0x1800f1afa  pop     rsi
0x1800f1afb  pop     rbx
0x1800f1afc  pop     rbp
0x1800f1afd  retn
0x1800f1aff  mov     rcx, [rbp+Stack]; Stack
0x1800f1b03  call    cs:__imp_RtlFreeActivationContextStack
0x1800f1b0a  nop     dword ptr [rax+rax+00h]
0x1800f1b0f  mov     ecx, 8; LastError
0x1800f1b14  call    cs:__imp_RtlSetLastWin32Error
0x1800f1b1b  nop     dword ptr [rax+rax+00h]
0x1800f1b20  xor     eax, eax
0x1800f1b22  jmp     short loc_1800F1AEF
0x1800f1b24  mov     edx, cs:dword_1803AAE28
0x1800f1b2a  lea     r8, [rbp+var_38]
0x1800f1b2e  lea     rcx, [rbp+var_30]
0x1800f1b32  call    cs:__imp_RtlCreateUserFiberShadowStack
0x1800f1b39  nop     dword ptr [rax+rax+00h]
0x1800f1b3e  test    eax, eax
0x1800f1b40  jns     loc_1800F1A3E
0x1800f1b46  mov     ecx, eax
0x1800f1b48  call    BaseSetLastNTError
0x1800f1b4d  mov     rcx, [rbp+Stack]; Stack
0x1800f1b51  call    cs:__imp_RtlFreeActivationContextStack
0x1800f1b58  nop     dword ptr [rax+rax+00h]
0x1800f1b5d  mov     rcx, gs:60h
0x1800f1b66  mov     r8, rdi; P
0x1800f1b69  xor     edx, edx; Flags
0x1800f1b6b  mov     rcx, [rcx+30h]; HeapHandle
0x1800f1b6f  call    cs:__imp_RtlFreeHeap
0x1800f1b76  nop     dword ptr [rax+rax+00h]
0x1800f1b7b  mov     rcx, [rbp+var_10]
0x1800f1b7f  call    cs:__imp_RtlFreeUserStack
0x1800f1b86  nop     dword ptr [rax+rax+00h]
0x1800f1b8b  jmp     short loc_1800F1B20
0x1800f1b8d  mov     ecx, 57h ; 'W'
0x1800f1b92  jmp     short loc_1800F1B14
0x1800f1b94  mov     ecx, eax
0x1800f1b96  call    BaseSetLastNTError
0x1800f1b9b  mov     rcx, [rbp+Stack]; Stack
0x1800f1b9f  call    cs:__imp_RtlFreeActivationContextStack
0x1800f1ba6  nop     dword ptr [rax+rax+00h]
0x1800f1bab  mov     rcx, gs:60h
0x1800f1bb4  mov     r8, rdi; P
0x1800f1bb7  xor     edx, edx; Flags
0x1800f1bb9  mov     rcx, [rcx+30h]; HeapHandle
0x1800f1bbd  call    cs:__imp_RtlFreeHeap
0x1800f1bc4  nop     dword ptr [rax+rax+00h]
0x1800f1bc9  jmp     loc_1800F1B20
0x1800f1bce  mov     ecx, 32h ; '2'
0x1800f1bd3  jmp     loc_1800F1B14
0x1800f1bd8  mov     ecx, eax
0x1800f1bda  call    BaseSetLastNTError
0x1800f1bdf  jmp     loc_1800F1B20
```
