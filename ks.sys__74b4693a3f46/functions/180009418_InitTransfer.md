# InitTransfer

- ea: `0x180009418`
- end: `0x1800095b7`
- name: `InitTransfer`
- size: `415`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180008e78`

## callees

- `0x180009418`
- `0x18000b7bc`
- `0x180016f7c`
- `0x180019fc0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000947e`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000947e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800094db`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1800094db`

## pseudocode

```c
__int64 __fastcall InitTransfer(__int64 a1, __int64 a2, char a3, char a4)
{
  PVOID v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  PVOID PoolWithTag; // r9
  unsigned __int64 v13; // rdx
  int BugCheckOnFailure; // [rsp+20h] [rbp-78h]

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      0,
      3,
      38,
      (__int64)WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids);
  *(_QWORD *)(a1 + 8) = a2;
  if ( (*(_BYTE *)(a2 + 10) & 5) != 0 )
    v8 = *(PVOID *)(a2 + 24);
  else
    v8 = MmMapLockedPagesSpecifyCache((PMDL)a2, 0, MmCached, 0, 0, 0x40000010u);
  *(_QWORD *)a1 = v8;
  if ( !v8 )
    return 3221225626LL;
  v9 = *(_QWORD *)(a1 + 8);
  v10 = (*(_DWORD *)a1 & 0xFFF) + 4095LL;
  v11 = *(unsigned int *)(v9 + 40);
  PoolWithTag = (PVOID)(v9 + 48);
  *(_DWORD *)(a1 + 96) = v11;
  v13 = (unsigned __int64)(v10 + v11) >> 12;
  *(_QWORD *)(a1 + 16) = v9 + 48;
  *(_BYTE *)(a1 + 92) = a3;
  *(_DWORD *)(a1 + 100) = v13;
  if ( a4 )
    PoolWithTag = ExAllocatePoolWithTag(NonPagedPoolNx, 8LL * (unsigned int)v13, 0x3436734Bu);
  *(_QWORD *)(a1 + 104) = PoolWithTag;
  if ( PoolWithTag && a4 )
    memset(PoolWithTag, 0, 8LL * *(unsigned int *)(a1 + 100));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      WPP_RECORDER_SF_qDDqqq(
        WPP_GLOBAL_Control->DeviceExtension,
        *(_DWORD *)a1 + *(_DWORD *)(a1 + 96) - 1,
        *(_QWORD *)a1,
        (_DWORD)PoolWithTag,
        BugCheckOnFailure,
        a2,
        a3,
        *(_DWORD *)(a1 + 100),
        *(_QWORD *)(a1 + 104),
        *(_QWORD *)a1,
        *(_BYTE *)a1 + *(_DWORD *)(a1 + 96) - 1);
  }
  return *(_QWORD *)(a1 + 104) == 0 ? 0xC000009A : 0;
}

```

## disassembly

```asm
0x180009418  push    rbx
0x18000941a  push    rbp
0x18000941b  push    rsi
0x18000941c  push    rdi
0x18000941d  push    r14
0x18000941f  push    r15
0x180009421  sub     rsp, 68h
0x180009425  mov     sil, r9b
0x180009428  movzx   ebp, r8b
0x18000942c  mov     rdi, rdx
0x18000942f  mov     rbx, rcx
0x180009432  lea     r15, WPP_RECORDER_INITIALIZED
0x180009439  xor     r14d, r14d
0x18000943c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180009443  jz      short loc_180009457
0x180009445  mov     rcx, cs:WPP_GLOBAL_Control
0x18000944c  cmp     [rcx+48h], r14w
0x180009451  jnz     loc_180009587
0x180009457  mov     [rbx+8], rdi
0x18000945b  test    byte ptr [rdi+0Ah], 5
0x18000945f  jnz     loc_18000957E
0x180009465  xor     r9d, r9d; RequestedAddress
0x180009468  mov     [rsp+98h+Priority], 40000010h; Priority
0x180009470  xor     edx, edx; AccessMode
0x180009472  mov     [rsp+98h+BugCheckOnFailure], r14d; BugCheckOnFailure
0x180009477  mov     rcx, rdi; MemoryDescriptorList
0x18000947a  lea     r8d, [r9+1]; CacheType
0x18000947e  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180009485  nop     dword ptr [rax+rax+00h]
0x18000948a  mov     [rbx], rax
0x18000948d  test    rax, rax
0x180009490  jz      loc_1800095AD
0x180009496  mov     rax, [rbx+8]
0x18000949a  mov     ecx, [rbx]
0x18000949c  and     ecx, 0FFFh
0x1800094a2  add     rcx, 0FFFh
0x1800094a9  mov     edx, [rax+28h]
0x1800094ac  lea     r9, [rax+30h]
0x1800094b0  mov     [rbx+60h], edx
0x1800094b3  add     rdx, rcx
0x1800094b6  shr     rdx, 0Ch
0x1800094ba  mov     [rbx+10h], r9
0x1800094be  mov     [rbx+5Ch], bpl
0x1800094c2  mov     [rbx+64h], edx
0x1800094c5  test    sil, sil
0x1800094c8  jz      short loc_1800094EA
0x1800094ca  mov     edx, edx
0x1800094cc  mov     ecx, 200h; PoolType
0x1800094d1  shl     rdx, 3; NumberOfBytes
0x1800094d5  mov     r8d, 3436734Bh; Tag
0x1800094db  call    cs:__imp_ExAllocatePoolWithTag
0x1800094e2  nop     dword ptr [rax+rax+00h]
0x1800094e7  mov     r9, rax
0x1800094ea  mov     [rbx+68h], r9
0x1800094ee  test    r9, r9
0x1800094f1  jnz     short loc_180009562
0x1800094f3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800094fa  jnz     short loc_18000951A
0x1800094fc  mov     rax, [rbx+68h]
0x180009500  neg     rax
0x180009503  sbb     eax, eax
0x180009505  not     eax
0x180009507  and     eax, 0C000009Ah
0x18000950c  add     rsp, 68h
0x180009510  pop     r15
0x180009512  pop     r14
0x180009514  pop     rdi
0x180009515  pop     rsi
0x180009516  pop     rbp
0x180009517  pop     rbx
0x180009518  retn
0x18000951a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009521  cmp     [rcx+48h], r14w
0x180009526  jz      short loc_1800094FC
0x180009528  mov     r8, [rbx]
0x18000952b  mov     rax, [rbx+68h]
0x18000952f  mov     edx, [rbx+60h]
0x180009532  mov     rcx, [rcx+40h]
0x180009536  dec     rdx
0x180009539  add     rdx, r8
0x18000953c  mov     [rsp+98h+var_48], rdx
0x180009541  mov     [rsp+98h+var_50], r8
0x180009546  mov     [rsp+98h+var_58], rax
0x18000954b  mov     eax, [rbx+64h]
0x18000954e  mov     [rsp+98h+var_60], eax
0x180009552  mov     [rsp+98h+var_68], ebp
0x180009556  mov     qword ptr [rsp+98h+Priority], rdi
0x18000955b  call    WPP_RECORDER_SF_qDDqqq
0x180009560  jmp     short loc_1800094FC
0x180009562  test    sil, sil
0x180009565  jz      short loc_1800094F3
0x180009567  mov     r8d, [rbx+64h]
0x18000956b  xor     edx, edx; Val
0x18000956d  shl     r8, 3; Size
0x180009571  mov     rcx, r9; void *
0x180009574  call    memset
0x180009579  jmp     loc_1800094F3
0x18000957e  mov     rax, [rdi+18h]
0x180009582  jmp     loc_18000948A
0x180009587  mov     rcx, [rcx+40h]
0x18000958b  lea     rax, WPP_8d03f3cebf6b3270dc662b593865d526_Traceguids
0x180009592  mov     r9d, 26h ; '&'
0x180009598  mov     qword ptr [rsp+98h+BugCheckOnFailure], rax
0x18000959d  xor     edx, edx
0x18000959f  lea     r8d, [r9-23h]
0x1800095a3  call    WPP_RECORDER_SF_
0x1800095a8  jmp     loc_180009457
0x1800095ad  mov     eax, 0C000009Ah
0x1800095b2  jmp     loc_18000950C
```
