# SchannelMapLsaToKernelContext

- ea: `0x140023240`
- end: `0x14002341e`
- name: `SchannelMapLsaToKernelContext`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400230a0`

## callees

- `0x140010160`
- `0x140023240`

## import_xrefs

- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023391`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140023391`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002333a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14002333a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023320`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140023320`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140023364`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400233b7`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140023364`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x1400233b7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400233e5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400233e5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400233f1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400233f1`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140023310`
- `ntoskrnl!PsGetSiloIdentifier` at `0x140023310`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140023301`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x140023301`

## pseudocode

```c
__int64 __fastcall SchannelMapLsaToKernelContext(unsigned __int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned __int64 v4; // rbx
  __int64 CurrentServerSilo; // rax
  __int64 v6; // rsi
  __int64 v7; // rdi
  _QWORD *inserted; // rax
  unsigned int v9; // ebx
  struct _RTL_AVL_TABLE *v10; // rcx
  unsigned __int8 NewElement[8]; // [rsp+20h] [rbp-48h] BYREF
  unsigned __int64 v13; // [rsp+28h] [rbp-40h]
  _QWORD Buffer[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v15; // [rsp+40h] [rbp-28h]

  NewElement[0] = 0;
  v13 = a1 >> 4;
  v15 = 0;
  Buffer[0] = a1;
  Buffer[1] = a2;
  *a3 = 0;
  v4 = (HIBYTE(v13)
      + 37
      * (BYTE6(v13)
       + 37
       * (BYTE5(v13)
        + 37
        * (BYTE4(v13)
         + 37
         * (BYTE3(v13)
          + 37
          * (BYTE2(v13)
           + 37 * ((unsigned __int8)(a1 >> 12) + 37 * ((unsigned __int64)(unsigned __int8)(a1 >> 4) + 11623883))))))))
     % g_NumContextTableBuckets;
  CurrentServerSilo = PsGetCurrentServerSilo();
  LODWORD(v15) = PsGetSiloIdentifier(CurrentServerSilo);
  KeEnterCriticalRegion();
  v6 = 56 * v4;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)g_SchannelKernToLsaContextTableLockArray + v4);
  v7 = 104 * v4;
  inserted = RtlInsertElementGenericTableAvl(
               (PRTL_AVL_TABLE)g_SchannelKernToLsaContextTableArray + v4,
               Buffer,
               0x18u,
               NewElement);
  if ( !inserted )
    goto LABEL_4;
  v9 = 0;
  if ( !NewElement[0] )
  {
    v10 = (struct _RTL_AVL_TABLE *)((char *)g_SchannelKernToLsaContextTableArray + v7);
    *a3 = inserted[1];
    RtlDeleteElementGenericTableAvl(v10, inserted);
    if ( !RtlInsertElementGenericTableAvl(
            (PRTL_AVL_TABLE)((char *)g_SchannelKernToLsaContextTableArray + v7),
            Buffer,
            0x18u,
            NewElement) )
    {
LABEL_4:
      v9 = -1073741670;
      goto LABEL_7;
    }
    if ( !NewElement[0] )
      v9 = -1073741595;
  }
LABEL_7:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)((char *)g_SchannelKernToLsaContextTableLockArray + v6));
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x140023240  mov     [rsp+arg_18], rbx
0x140023245  push    rsi
0x140023246  push    rdi
0x140023247  push    r14
0x140023249  sub     rsp, 50h
0x14002324d  mov     rax, cs:__security_cookie
0x140023254  xor     rax, rsp
0x140023257  mov     [rsp+68h+var_20], rax
0x14002325c  mov     rax, rcx
0x14002325f  mov     [rsp+68h+NewElement], 0
0x140023264  shr     rax, 4
0x140023268  mov     r9, rcx
0x14002326b  mov     [rsp+68h+var_40], rax
0x140023270  mov     r10, rdx
0x140023273  mov     r14, r8
0x140023276  mov     [rsp+68h+var_28], 0
0x14002327f  lea     r8, [rsp+68h+var_40]
0x140023284  mov     [rsp+68h+Buffer], r9
0x140023289  movzx   eax, byte ptr [r8]
0x14002328d  add     rax, 0B15DCBh
0x140023293  mov     [rsp+68h+var_30], r10
0x140023298  imul    rcx, rax, 25h ; '%'
0x14002329c  movzx   eax, byte ptr [r8+1]
0x1400232a1  add     rcx, rax
0x1400232a4  mov     qword ptr [r14], 0
0x1400232ab  movzx   eax, byte ptr [r8+2]
0x1400232b0  imul    rdx, rcx, 25h ; '%'
0x1400232b4  add     rdx, rax
0x1400232b7  movzx   eax, byte ptr [r8+3]
0x1400232bc  imul    rcx, rdx, 25h ; '%'
0x1400232c0  add     rcx, rax
0x1400232c3  movzx   eax, byte ptr [r8+4]
0x1400232c8  imul    rdx, rcx, 25h ; '%'
0x1400232cc  add     rdx, rax
0x1400232cf  movzx   eax, byte ptr [r8+5]
0x1400232d4  imul    rcx, rdx, 25h ; '%'
0x1400232d8  add     rcx, rax
0x1400232db  movzx   eax, byte ptr [r8+6]
0x1400232e0  imul    rdx, rcx, 25h ; '%'
0x1400232e4  movzx   ecx, byte ptr [r8+7]
0x1400232e9  add     rdx, rax
0x1400232ec  imul    rax, rdx, 25h ; '%'
0x1400232f0  xor     edx, edx
0x1400232f2  add     rax, rcx
0x1400232f5  movzx   ecx, cs:?g_NumContextTableBuckets@@3GA; ushort g_NumContextTableBuckets
0x1400232fc  div     rcx
0x1400232ff  mov     ebx, edx
0x140023301  call    cs:__imp_PsGetCurrentServerSilo
0x140023308  nop     dword ptr [rax+rax+00h]
0x14002330d  mov     rcx, rax
0x140023310  call    cs:__imp_PsGetSiloIdentifier
0x140023317  nop     dword ptr [rax+rax+00h]
0x14002331c  mov     dword ptr [rsp+68h+var_28], eax
0x140023320  call    cs:__imp_KeEnterCriticalRegion
0x140023327  nop     dword ptr [rax+rax+00h]
0x14002332c  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x140023333  imul    rsi, rbx, 38h ; '8'
0x140023337  add     rcx, rsi; FastMutex
0x14002333a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140023341  nop     dword ptr [rax+rax+00h]
0x140023346  mov     rcx, cs:?g_SchannelKernToLsaContextTableArray@@3PEAU_RTL_AVL_TABLE@@EA; _RTL_AVL_TABLE * g_SchannelKernToLsaContextTableArray
0x14002334d  lea     r9, [rsp+68h+NewElement]; NewElement
0x140023352  imul    rdi, rbx, 68h ; 'h'
0x140023356  mov     r8d, 18h; BufferSize
0x14002335c  lea     rdx, [rsp+68h+Buffer]; Buffer
0x140023361  add     rcx, rdi; Table
0x140023364  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14002336b  nop     dword ptr [rax+rax+00h]
0x140023370  mov     rdx, rax; Buffer
0x140023373  test    rax, rax
0x140023376  jz      short loc_1400233C8
0x140023378  xor     ebx, ebx
0x14002337a  cmp     [rsp+68h+NewElement], bl
0x14002337e  jnz     short loc_1400233DB
0x140023380  mov     rcx, cs:?g_SchannelKernToLsaContextTableArray@@3PEAU_RTL_AVL_TABLE@@EA; _RTL_AVL_TABLE * g_SchannelKernToLsaContextTableArray
0x140023387  mov     rax, [rax+8]
0x14002338b  add     rcx, rdi; Table
0x14002338e  mov     [r14], rax
0x140023391  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140023398  nop     dword ptr [rax+rax+00h]
0x14002339d  mov     rcx, cs:?g_SchannelKernToLsaContextTableArray@@3PEAU_RTL_AVL_TABLE@@EA; _RTL_AVL_TABLE * g_SchannelKernToLsaContextTableArray
0x1400233a4  lea     r9, [rsp+68h+NewElement]; NewElement
0x1400233a9  add     rcx, rdi; Table
0x1400233ac  lea     rdx, [rsp+68h+Buffer]; Buffer
0x1400233b1  mov     r8d, 18h; BufferSize
0x1400233b7  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1400233be  nop     dword ptr [rax+rax+00h]
0x1400233c3  test    rax, rax
0x1400233c6  jnz     short loc_1400233CF
0x1400233c8  mov     ebx, 0C000009Ah
0x1400233cd  jmp     short loc_1400233DB
0x1400233cf  cmp     [rsp+68h+NewElement], bl
0x1400233d3  mov     eax, 0C00000E5h
0x1400233d8  cmovz   ebx, eax
0x1400233db  mov     rcx, cs:?g_SchannelKernToLsaContextTableLockArray@@3PEAU_FAST_MUTEX@@EA; _FAST_MUTEX * g_SchannelKernToLsaContextTableLockArray
0x1400233e2  add     rcx, rsi; FastMutex
0x1400233e5  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400233ec  nop     dword ptr [rax+rax+00h]
0x1400233f1  call    cs:__imp_KeLeaveCriticalRegion
0x1400233f8  nop     dword ptr [rax+rax+00h]
0x1400233fd  mov     eax, ebx
0x1400233ff  mov     rcx, [rsp+68h+var_20]
0x140023404  xor     rcx, rsp; StackCookie
0x140023407  call    __security_check_cookie
0x14002340c  mov     rbx, [rsp+68h+arg_18]
0x140023414  add     rsp, 50h
0x140023418  pop     r14
0x14002341a  pop     rdi
0x14002341b  pop     rsi
0x14002341c  retn
```
