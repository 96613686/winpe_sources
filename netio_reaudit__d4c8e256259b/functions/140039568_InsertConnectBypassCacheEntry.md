# InsertConnectBypassCacheEntry

- ea: `0x140039568`
- end: `0x1400397f1`
- name: `InsertConnectBypassCacheEntry`
- size: `649`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400394b0`

## callees

- `0x140006c40`
- `0x140009520`
- `0x140009e00`
- `0x14000afa0`
- `0x14000ca00`
- `0x14001cfe0`
- `0x140039568`
- `0x140039c00`
- `0x14003a440`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140039752`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140039752`
- `ntoskrnl!RtlLengthSid` at `0x140039643`
- `ntoskrnl!RtlLengthSid` at `0x14003966f`
- `ntoskrnl!RtlLengthSid` at `0x140039643`
- `ntoskrnl!RtlLengthSid` at `0x14003966f`

## string_xrefs

- `0x1400397c7`: `InsertConnectBypassCacheEntry`

## pseudocode

```c
__int64 __fastcall InsertConnectBypassCacheEntry(__int64 a1, unsigned int *a2, __int64 a3)
{
  int v3; // r9d
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rbx
  __int64 v6; // rax
  __int64 v9; // rdi
  ULONG_PTR v10; // r12
  unsigned int v11; // eax
  ULONG v12; // eax
  ULONG v13; // eax
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int16 v17; // [rsp+50h] [rbp+8h] BYREF
  char v18; // [rsp+52h] [rbp+Ah]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+68h] [rbp+20h] BYREF

  v3 = *(_DWORD *)(a1 + 4);
  v17 = 0;
  v4 = 0;
  v18 = 0;
  v6 = *(_QWORD *)(a1 + 16);
  Entry = 0;
  if ( v3 > *(_DWORD *)(v6 + 4) )
  {
    v9 = WfpReportSysErrorAsNtStatus(a1, "RtlInsertEntryHashTable", 3221225473LL, 1);
    goto LABEL_14;
  }
  v10 = ComputeConnectBypassHash(a2, a1);
  v9 = WfpPoolAllocNonPaged(176, 1282434647, &Entry);
  if ( v9 )
  {
    v4 = Entry;
  }
  else
  {
    v4 = Entry;
    memset(Entry, 0, 0xB0u);
    v4[3].Signature = 0;
    v9 = WfpPoolAllocNonPaged(*a2, 1282434647, &v4[3].Signature);
    if ( !v9 )
    {
      v11 = *a2;
      LODWORD(v4[3].Linkage.Blink) = *a2;
      memmove((void *)v4[3].Signature, *((const void **)a2 + 1), v11);
      v12 = RtlLengthSid(*((PSID *)a2 + 4));
      v9 = WfpPoolAllocNonPaged(v12, 1282434647, &v4[4].Signature);
      if ( !v9 )
      {
        v13 = RtlLengthSid(*((PSID *)a2 + 4));
        memmove((void *)v4[4].Signature, *((const void **)a2 + 4), v13);
        v4[5].Linkage.Blink = 0;
        LODWORD(v4[5].Linkage.Flink) = a2[10];
        v14 = a2[10];
        if ( !v14 )
          goto LABEL_9;
        v9 = WfpPoolAllocNonPaged(v14, 1282434647, &v4[5].Linkage.Blink);
        if ( !v9 )
        {
          memmove(v4[5].Linkage.Blink, *((const void **)a2 + 6), LODWORD(v4[5].Linkage.Flink));
LABEL_9:
          v4[4].Linkage.Flink = (struct _LIST_ENTRY *)*((_QWORD *)a2 + 2);
          LOWORD(v4[4].Linkage.Blink) = *((_WORD *)a2 + 12);
          BYTE2(v4[4].Linkage.Blink) = *((_BYTE *)a2 + 26);
          LODWORD(v4[2].Signature) = *(_DWORD *)a3;
          v4[3].Linkage.Flink = *(struct _LIST_ENTRY **)(a3 + 16);
          v4->Signature = v10;
          LODWORD(v4[1].Linkage.Flink) = *(_DWORD *)(a1 + 36);
          v4[1].Signature = (ULONG_PTR)&v4[1].Linkage.Blink;
          v4[1].Linkage.Blink = (struct _LIST_ENTRY *)&v4[1].Linkage.Blink;
          WfpAcquireFastWriteLock(&gWfpGlobal[13].L.ListEntry, &v17);
          if ( *(_DWORD *)a1 == 1 && RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), v4, v10, 0) )
          {
            _InterlockedAdd((volatile signed __int32 *)(a1 + 4), 1u);
            InsertCacheEntryLru(a1, v4);
          }
          else
          {
            v9 = WfpReportSysErrorAsNtStatus(v15, "RtlInsertEntryHashTable", 3221225473LL, 1);
          }
          WfpReleaseFastWriteLock(&gWfpGlobal[13].L.ListEntry, &v17);
LABEL_14:
          if ( !v9 )
            return v9;
        }
      }
    }
  }
  if ( v4 )
  {
    WfpPoolFree(&v4[3].Signature);
    WfpPoolFree(&v4[4].Signature);
    WfpPoolFree(&v4[5].Linkage.Blink);
    WfpPoolFree(&Entry);
  }
  WfpReportError(v9, "InsertConnectBypassCacheEntry");
  return v9;
}

```

## disassembly

```asm
0x140039568  mov     [rsp+arg_8], rbx
0x14003956d  mov     [rsp+arg_10], rbp
0x140039572  push    rsi
0x140039573  push    rdi
0x140039574  push    r12
0x140039576  push    r14
0x140039578  push    r15
0x14003957a  sub     rsp, 20h
0x14003957e  mov     r9d, [rcx+4]
0x140039582  xor     eax, eax
0x140039584  mov     [rsp+48h+arg_0], ax
0x140039589  xor     ebx, ebx
0x14003958b  mov     [rsp+48h+arg_2], al
0x14003958f  mov     rbp, r8
0x140039592  mov     rax, [rcx+10h]
0x140039596  mov     r14, rdx
0x140039599  mov     rsi, rcx
0x14003959c  mov     [rsp+48h+Entry], rbx
0x1400395a1  cmp     r9d, [rax+4]
0x1400395a5  jle     short loc_1400395C5
0x1400395a7  lea     r9d, [rbx+1]
0x1400395ab  mov     r8d, 0C0000001h
0x1400395b1  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x1400395b8  call    WfpReportSysErrorAsNtStatus
0x1400395bd  mov     rdi, rax
0x1400395c0  jmp     loc_140039789
0x1400395c5  mov     rdx, rsi
0x1400395c8  mov     rcx, r14
0x1400395cb  call    ComputeConnectBypassHash
0x1400395d0  mov     ebx, 0B0h
0x1400395d5  lea     r8, [rsp+48h+Entry]
0x1400395da  mov     ecx, ebx
0x1400395dc  mov     edx, 4C706657h
0x1400395e1  mov     r12, rax
0x1400395e4  call    WfpPoolAllocNonPaged
0x1400395e9  mov     rdi, rax
0x1400395ec  test    rax, rax
0x1400395ef  jnz     loc_140039790
0x1400395f5  mov     r8d, ebx; Size
0x1400395f8  xor     edx, edx; Val
0x1400395fa  mov     rbx, [rsp+48h+Entry]
0x1400395ff  mov     rcx, rbx; void *
0x140039602  call    memset
0x140039607  lea     r15, [rbx+58h]
0x14003960b  mov     edx, 4C706657h
0x140039610  mov     [r15], rdi
0x140039613  mov     r8, r15
0x140039616  mov     ecx, [r14]
0x140039619  call    WfpPoolAllocNonPaged
0x14003961e  mov     rdi, rax
0x140039621  test    rax, rax
0x140039624  jnz     loc_140039795
0x14003962a  mov     eax, [r14]
0x14003962d  mov     [rbx+50h], eax
0x140039630  mov     r8d, eax; Size
0x140039633  mov     rdx, [r14+8]; Src
0x140039637  mov     rcx, [r15]; void *
0x14003963a  call    memmove
0x14003963f  mov     rcx, [r14+20h]; Sid
0x140039643  call    cs:__imp_RtlLengthSid
0x14003964a  nop     dword ptr [rax+rax+00h]
0x14003964f  mov     ecx, eax
0x140039651  lea     r8, [rbx+70h]
0x140039655  mov     edx, 4C706657h
0x14003965a  call    WfpPoolAllocNonPaged
0x14003965f  mov     rdi, rax
0x140039662  test    rax, rax
0x140039665  jnz     loc_140039795
0x14003966b  mov     rcx, [r14+20h]; Sid
0x14003966f  call    cs:__imp_RtlLengthSid
0x140039676  nop     dword ptr [rax+rax+00h]
0x14003967b  mov     rdx, [r14+20h]; Src
0x14003967f  mov     rcx, [rbx+70h]; void *
0x140039683  mov     r8d, eax; Size
0x140039686  call    memmove
0x14003968b  lea     r15, [rbx+80h]
0x140039692  mov     [r15], rdi
0x140039695  mov     eax, [r14+28h]
0x140039699  mov     [rbx+78h], eax
0x14003969c  mov     eax, [r14+28h]
0x1400396a0  test    eax, eax
0x1400396a2  jz      short loc_1400396CF
0x1400396a4  mov     ecx, eax
0x1400396a6  mov     r8, r15
0x1400396a9  mov     edx, 4C706657h
0x1400396ae  call    WfpPoolAllocNonPaged
0x1400396b3  mov     rdi, rax
0x1400396b6  test    rax, rax
0x1400396b9  jnz     loc_140039795
0x1400396bf  mov     r8d, [rbx+78h]; Size
0x1400396c3  mov     rdx, [r14+30h]; Src
0x1400396c7  mov     rcx, [r15]; void *
0x1400396ca  call    memmove
0x1400396cf  mov     rax, [r14+10h]
0x1400396d3  lea     rdx, [rsp+48h+arg_0]
0x1400396d8  mov     [rbx+60h], rax
0x1400396dc  movzx   eax, word ptr [r14+18h]
0x1400396e1  mov     [rbx+68h], ax
0x1400396e5  mov     al, [r14+1Ah]
0x1400396e9  mov     [rbx+6Ah], al
0x1400396ec  mov     eax, [rbp+0]
0x1400396ef  mov     [rbx+40h], eax
0x1400396f2  mov     rax, [rbp+10h]
0x1400396f6  mov     [rbx+48h], rax
0x1400396fa  mov     [rbx+10h], r12
0x1400396fe  mov     eax, [rsi+24h]
0x140039701  mov     [rbx+18h], eax
0x140039704  lea     rax, [rbx+20h]
0x140039708  mov     [rax+8], rax
0x14003970c  mov     [rax], rax
0x14003970f  mov     rcx, cs:gWfpGlobal
0x140039716  add     rcx, 6C0h
0x14003971d  call    WfpAcquireFastWriteLock
0x140039722  mov     ebp, 1
0x140039727  cmp     [rsi], ebp
0x140039729  jz      short loc_140039745
0x14003972b  mov     r9d, ebp
0x14003972e  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x140039735  mov     r8d, 0C0000001h
0x14003973b  call    WfpReportSysErrorAsNtStatus
0x140039740  mov     rdi, rax
0x140039743  jmp     short loc_140039771
0x140039745  mov     rcx, [rsi+8]; HashTable
0x140039749  xor     r9d, r9d; Context
0x14003974c  mov     r8, r12; Signature
0x14003974f  mov     rdx, rbx; Entry
0x140039752  call    cs:__imp_RtlInsertEntryHashTable
0x140039759  nop     dword ptr [rax+rax+00h]
0x14003975e  test    al, al
0x140039760  jz      short loc_14003972B
0x140039762  lock add [rsi+4], ebp
0x140039766  mov     rdx, rbx
0x140039769  mov     rcx, rsi
0x14003976c  call    InsertCacheEntryLru
0x140039771  mov     rcx, cs:gWfpGlobal
0x140039778  lea     rdx, [rsp+48h+arg_0]
0x14003977d  add     rcx, 6C0h
0x140039784  call    WfpReleaseFastWriteLock
0x140039789  test    rdi, rdi
0x14003978c  jnz     short loc_140039795
0x14003978e  jmp     short loc_1400397D6
0x140039790  mov     rbx, [rsp+48h+Entry]
0x140039795  test    rbx, rbx
0x140039798  jz      short loc_1400397C2
0x14003979a  lea     rcx, [rbx+58h]
0x14003979e  call    WfpPoolFree
0x1400397a3  lea     rcx, [rbx+70h]
0x1400397a7  call    WfpPoolFree
0x1400397ac  lea     rcx, [rbx+80h]
0x1400397b3  call    WfpPoolFree
0x1400397b8  lea     rcx, [rsp+48h+Entry]
0x1400397bd  call    WfpPoolFree
0x1400397c2  test    rdi, rdi
0x1400397c5  jz      short loc_1400397D6
0x1400397c7  lea     rdx, aInsertconnectb; "InsertConnectBypassCacheEntry"
0x1400397ce  mov     rcx, rdi
0x1400397d1  call    WfpReportError
0x1400397d6  mov     rbx, [rsp+48h+arg_8]
0x1400397db  mov     rax, rdi
0x1400397de  mov     rbp, [rsp+48h+arg_10]
0x1400397e3  add     rsp, 20h
0x1400397e7  pop     r15
0x1400397e9  pop     r14
0x1400397eb  pop     r12
0x1400397ed  pop     rdi
0x1400397ee  pop     rsi
0x1400397ef  retn
```
