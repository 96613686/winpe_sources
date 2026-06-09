# SchannelUnMapLsaToKernelContext(unsigned __int64,unsigned __int64)

- ea: `0x140005170`
- end: `0x1400052bb`
- name: `?SchannelUnMapLsaToKernelContext@@YAX_K0@Z`
- size: `331`
- prototype: `void __fastcall(unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140023430`

## callees

- `0x140010160`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005274`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140005274`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005258`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140005258`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000523e`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000523e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000528a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14000528a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005296`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140005296`
- `ntoskrnl!PsGetSiloIdentifier` at `0x14000522e`
- `ntoskrnl!PsGetSiloIdentifier` at `0x14000522e`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000521f`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x14000521f`

## pseudocode

```c
void __fastcall SchannelUnMapLsaToKernelContext(unsigned __int64 a1, __int64 a2)
{
  unsigned __int64 v3; // rdx
  __int64 v4; // rbx
  __int64 CurrentServerSilo; // rax
  unsigned __int64 v6; // [rsp+20h] [rbp-38h]
  _QWORD Buffer[2]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v8; // [rsp+38h] [rbp-20h]

  v8 = 0;
  v6 = a1 >> 4;
  Buffer[0] = a1;
  Buffer[1] = a2;
  v3 = (HIBYTE(v6)
      + 37
      * (BYTE6(v6)
       + 37
       * (BYTE5(v6)
        + 37
        * (BYTE4(v6)
         + 37
         * (BYTE3(v6)
          + 37
          * (BYTE2(v6)
           + 37 * ((unsigned __int8)(a1 >> 12) + 37 * ((unsigned __int64)(unsigned __int8)(a1 >> 4) + 11623883))))))))
     % g_NumContextTableBuckets;
  v4 = (unsigned int)v3;
  CurrentServerSilo = PsGetCurrentServerSilo(g_NumContextTableBuckets, v3, a1, a2);
  LODWORD(v8) = PsGetSiloIdentifier(CurrentServerSilo);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)g_SchannelKernToLsaContextTableLockArray + v4);
  RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)g_SchannelKernToLsaContextTableArray + v4, Buffer);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)g_SchannelKernToLsaContextTableLockArray + v4);
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140005170  mov     [rsp+arg_10], rbx
0x140005175  push    rdi
0x140005176  sub     rsp, 50h
0x14000517a  mov     rax, cs:__security_cookie
0x140005181  xor     rax, rsp
0x140005184  mov     [rsp+58h+var_18], rax
0x140005189  mov     rax, rcx
0x14000518c  mov     [rsp+58h+var_20], 0
0x140005195  shr     rax, 4
0x140005199  lea     r10, [rsp+58h+var_38]
0x14000519e  mov     [rsp+58h+var_38], rax
0x1400051a3  mov     r8, rcx
0x1400051a6  movzx   eax, byte ptr [r10]
0x1400051aa  mov     r9, rdx
0x1400051ad  add     rax, 0B15DCBh
0x1400051b3  mov     [rsp+58h+Buffer], r8
0x1400051b8  imul    rcx, rax, 25h ; '%'
0x1400051bc  movzx   eax, byte ptr [r10+1]
0x1400051c1  add     rcx, rax
0x1400051c4  mov     [rsp+58h+var_28], r9
0x1400051c9  movzx   eax, byte ptr [r10+2]
0x1400051ce  imul    rdx, rcx, 25h ; '%'
0x1400051d2  add     rdx, rax
0x1400051d5  movzx   eax, byte ptr [r10+3]
0x1400051da  imul    rcx, rdx, 25h ; '%'
0x1400051de  add     rcx, rax
0x1400051e1  movzx   eax, byte ptr [r10+4]
0x1400051e6  imul    rdx, rcx, 25h ; '%'
0x1400051ea  add     rdx, rax
0x1400051ed  movzx   eax, byte ptr [r10+5]
0x1400051f2  imul    rcx, rdx, 25h ; '%'
0x1400051f6  add     rcx, rax
0x1400051f9  movzx   eax, byte ptr [r10+6]
0x1400051fe  imul    rdx, rcx, 25h ; '%'
0x140005202  movzx   ecx, byte ptr [r10+7]
0x140005207  add     rdx, rax
0x14000520a  imul    rax, rdx, 25h ; '%'
0x14000520e  xor     edx, edx
0x140005210  add     rax, rcx
0x140005213  movzx   ecx, cs:?g_NumContextTableBuckets@@3GA; ushort g_NumContextTableBuckets
0x14000521a  div     rcx
0x14000521d  mov     ebx, edx
0x14000521f  call    cs:__imp_PsGetCurrentServerSilo
0x140005226  nop     dword ptr [rax+rax+00h]
0x14000522b  mov     rcx, rax
0x14000522e  call    cs:__imp_PsGetSiloIdentifier
0x140005235  nop     dword ptr [rax+rax+00h]
0x14000523a  mov     dword ptr [rsp+58h+var_20], eax
0x14000523e  call    cs:__imp_KeEnterCriticalRegion
0x140005245  nop     dword ptr [rax+rax+00h]
0x14000524a  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x140005251  imul    rdi, rbx, 38h ; '8'
0x140005255  add     rcx, rdi; FastMutex
0x140005258  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14000525f  nop     dword ptr [rax+rax+00h]
0x140005264  imul    rcx, rbx, 68h ; 'h'
0x140005268  lea     rdx, [rsp+58h+Buffer]; Buffer
0x14000526d  add     rcx, cs:?g_SchannelKernToLsaContextTableArray@@3PEAU_RTL_AVL_TABLE@@EA; Table
0x140005274  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14000527b  nop     dword ptr [rax+rax+00h]
0x140005280  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x140005287  add     rcx, rdi; FastMutex
0x14000528a  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140005291  nop     dword ptr [rax+rax+00h]
0x140005296  call    cs:__imp_KeLeaveCriticalRegion
0x14000529d  nop     dword ptr [rax+rax+00h]
0x1400052a2  mov     rcx, [rsp+58h+var_18]
0x1400052a7  xor     rcx, rsp; StackCookie
0x1400052aa  call    __security_check_cookie
0x1400052af  mov     rbx, [rsp+58h+arg_10]
0x1400052b4  add     rsp, 50h
0x1400052b8  pop     rdi
0x1400052b9  retn
```
