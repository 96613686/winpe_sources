# SchannelLookupKernelContextFromLsa

- ea: `0x140021804`
- end: `0x140021956`
- name: `SchannelLookupKernelContextFromLsa`
- size: `338`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000a6f0`
- `0x14000a780`
- `0x14000a8d0`

## callees

- `0x140010160`
- `0x140021804`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400218e3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400218e3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400218c9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400218c9`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400218ff`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400218ff`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021918`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140021918`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021924`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140021924`
- `ntoskrnl!PsGetSiloIdentifier` at `0x1400218b9`
- `ntoskrnl!PsGetSiloIdentifier` at `0x1400218b9`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400218aa`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1400218aa`

## pseudocode

```c
__int64 __fastcall SchannelLookupKernelContextFromLsa(unsigned __int64 a1)
{
  unsigned __int64 v1; // rdx
  __int64 v2; // rbx
  __int64 CurrentServerSilo; // rax
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  unsigned __int64 v7; // [rsp+20h] [rbp-38h] BYREF
  unsigned __int64 Buffer; // [rsp+28h] [rbp-30h] BYREF
  __int128 v9; // [rsp+30h] [rbp-28h]

  v7 = a1 >> 4;
  v9 = 0;
  Buffer = a1;
  v1 = (HIBYTE(v7)
      + 37
      * (BYTE6(v7)
       + 37
       * (BYTE5(v7)
        + 37
        * (BYTE4(v7)
         + 37
         * (BYTE3(v7)
          + 37
          * (BYTE2(v7)
           + 37 * ((unsigned __int8)(a1 >> 12) + 37 * ((unsigned __int64)(unsigned __int8)(a1 >> 4) + 11623883))))))))
     % g_NumContextTableBuckets;
  v2 = (unsigned int)v1;
  CurrentServerSilo = PsGetCurrentServerSilo(g_NumContextTableBuckets, v1, a1, &v7);
  DWORD2(v9) = PsGetSiloIdentifier(CurrentServerSilo);
  KeEnterCriticalRegion();
  v4 = 56 * v2;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)g_SchannelKernToLsaContextTableLockArray + v2);
  v5 = RtlLookupElementGenericTableAvl((PRTL_AVL_TABLE)g_SchannelKernToLsaContextTableArray + v2, &Buffer);
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)((char *)g_SchannelKernToLsaContextTableLockArray + v4));
  KeLeaveCriticalRegion();
  if ( v5 )
    return v5[1];
  else
    return 0;
}

```

## disassembly

```asm
0x140021804  mov     r11, rsp
0x140021807  mov     [r11+10h], rbx
0x14002180b  push    rdi
0x14002180c  sub     rsp, 50h
0x140021810  mov     rax, cs:__security_cookie
0x140021817  xor     rax, rsp
0x14002181a  mov     [rsp+58h+var_18], rax
0x14002181f  mov     rax, rcx
0x140021822  lea     r9, [r11-38h]
0x140021826  shr     rax, 4
0x14002182a  mov     r8, rcx
0x14002182d  mov     [r11-38h], rax
0x140021831  xorps   xmm0, xmm0
0x140021834  movzx   eax, byte ptr [r9]
0x140021838  add     rax, 0B15DCBh
0x14002183e  imul    rcx, rax, 25h ; '%'
0x140021842  movdqu  [rsp+58h+var_28], xmm0
0x140021848  movzx   eax, byte ptr [r9+1]
0x14002184d  add     rcx, rax
0x140021850  mov     [r11-30h], r8
0x140021854  movzx   eax, byte ptr [r9+2]
0x140021859  imul    rdx, rcx, 25h ; '%'
0x14002185d  add     rdx, rax
0x140021860  movzx   eax, byte ptr [r9+3]
0x140021865  imul    rcx, rdx, 25h ; '%'
0x140021869  add     rcx, rax
0x14002186c  movzx   eax, byte ptr [r9+4]
0x140021871  imul    rdx, rcx, 25h ; '%'
0x140021875  add     rdx, rax
0x140021878  movzx   eax, byte ptr [r9+5]
0x14002187d  imul    rcx, rdx, 25h ; '%'
0x140021881  add     rcx, rax
0x140021884  movzx   eax, byte ptr [r9+6]
0x140021889  imul    rdx, rcx, 25h ; '%'
0x14002188d  movzx   ecx, byte ptr [r9+7]
0x140021892  add     rdx, rax
0x140021895  imul    rax, rdx, 25h ; '%'
0x140021899  xor     edx, edx
0x14002189b  add     rax, rcx
0x14002189e  movzx   ecx, cs:?g_NumContextTableBuckets@@3GA; ushort g_NumContextTableBuckets
0x1400218a5  div     rcx
0x1400218a8  mov     ebx, edx
0x1400218aa  call    cs:__imp_PsGetCurrentServerSilo
0x1400218b1  nop     dword ptr [rax+rax+00h]
0x1400218b6  mov     rcx, rax
0x1400218b9  call    cs:__imp_PsGetSiloIdentifier
0x1400218c0  nop     dword ptr [rax+rax+00h]
0x1400218c5  mov     dword ptr [rsp+58h+var_28+8], eax
0x1400218c9  call    cs:__imp_KeEnterCriticalRegion
0x1400218d0  nop     dword ptr [rax+rax+00h]
0x1400218d5  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x1400218dc  imul    rdi, rbx, 38h ; '8'
0x1400218e0  add     rcx, rdi; FastMutex
0x1400218e3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400218ea  nop     dword ptr [rax+rax+00h]
0x1400218ef  imul    rcx, rbx, 68h ; 'h'
0x1400218f3  lea     rdx, [rsp+58h+Buffer]; Buffer
0x1400218f8  add     rcx, cs:?g_SchannelKernToLsaContextTableArray@@3PEAU_RTL_AVL_TABLE@@EA; Table
0x1400218ff  call    cs:__imp_RtlLookupElementGenericTableAvl
0x140021906  nop     dword ptr [rax+rax+00h]
0x14002190b  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x140021912  mov     rbx, rax
0x140021915  add     rcx, rdi; FastMutex
0x140021918  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002191f  nop     dword ptr [rax+rax+00h]
0x140021924  call    cs:__imp_KeLeaveCriticalRegion
0x14002192b  nop     dword ptr [rax+rax+00h]
0x140021930  test    rbx, rbx
0x140021933  jz      short loc_14002193B
0x140021935  mov     rax, [rbx+8]
0x140021939  jmp     short loc_14002193D
0x14002193b  xor     eax, eax
0x14002193d  mov     rcx, [rsp+58h+var_18]
0x140021942  xor     rcx, rsp; StackCookie
0x140021945  call    __security_check_cookie
0x14002194a  mov     rbx, [rsp+58h+arg_8]
0x14002194f  add     rsp, 50h
0x140021953  pop     rdi
0x140021954  retn
```
