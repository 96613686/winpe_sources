# InsertAcceptBypassCacheEntry

- ea: `0x14000a32c`
- end: `0x14000a603`
- name: `InsertAcceptBypassCacheEntry`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140009e70`

## callees

- `0x140006c40`
- `0x140009520`
- `0x140009e00`
- `0x14000a32c`
- `0x14000afa0`
- `0x14000ca00`
- `0x14001cfe0`
- `0x140033ad0`
- `0x14003a440`
- `0x140078100`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a561`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x14000a561`
- `ntoskrnl!RtlLengthSid` at `0x14000a414`
- `ntoskrnl!RtlLengthSid` at `0x14000a43f`
- `ntoskrnl!RtlLengthSid` at `0x14000a414`
- `ntoskrnl!RtlLengthSid` at `0x14000a43f`

## string_xrefs

- `0x14000a5d9`: `InsertAcceptBypassCacheEntry`

## pseudocode

```c
__int64 __fastcall InsertAcceptBypassCacheEntry(__int64 a1, unsigned int *a2, __int64 a3)
{
  int v3; // r9d
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v4; // rbx
  __int64 v6; // rax
  __int64 v9; // rdi
  ULONG_PTR v10; // r15
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
  v10 = ComputeAcceptBypassHash(a2, a1);
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
      v4[4].Linkage.Flink = (struct _LIST_ENTRY *)*((_QWORD *)a2 + 2);
      v12 = RtlLengthSid(*((PSID *)a2 + 9));
      v9 = WfpPoolAllocNonPaged(v12, 1282434647, &v4[6].Linkage.Blink);
      if ( !v9 )
      {
        v13 = RtlLengthSid(*((PSID *)a2 + 9));
        memmove(v4[6].Linkage.Blink, *((const void **)a2 + 9), v13);
        v4[7].Linkage.Flink = 0;
        LODWORD(v4[6].Signature) = a2[20];
        v14 = a2[20];
        if ( !v14 )
          goto LABEL_9;
        v9 = WfpPoolAllocNonPaged(v14, 1282434647, &v4[7]);
        if ( !v9 )
        {
          memmove(v4[7].Linkage.Flink, *((const void **)a2 + 11), LODWORD(v4[6].Signature));
LABEL_9:
          *(_OWORD *)((char *)&v4[4].Linkage.Blink + 4) = *(_OWORD *)(a2 + 7);
          v4[4].Linkage.Flink = (struct _LIST_ENTRY *)*((_QWORD *)a2 + 2);
          LOWORD(v4[4].Linkage.Blink) = *((_WORD *)a2 + 12);
          BYTE2(v4[4].Linkage.Blink) = *((_BYTE *)a2 + 26);
          BYTE3(v4[4].Linkage.Blink) = *((_BYTE *)a2 + 27);
          HIDWORD(v4[5].Linkage.Flink) = a2[11];
          v4[5].Linkage.Blink = (struct _LIST_ENTRY *)*((_QWORD *)a2 + 6);
          LODWORD(v4[5].Signature) = a2[14];
          HIDWORD(v4[5].Signature) = a2[15];
          LODWORD(v4[6].Linkage.Flink) = a2[16];
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
    WfpPoolFree(&v4[6].Linkage.Blink);
    WfpPoolFree(&v4[7]);
    WfpPoolFree(&Entry);
  }
  WfpReportError(v9, "InsertAcceptBypassCacheEntry");
  return v9;
}

```

## disassembly

```asm
0x14000a32c  mov     [rsp+arg_8], rbx
0x14000a331  mov     [rsp+arg_10], rbp
0x14000a336  push    rsi
0x14000a337  push    rdi
0x14000a338  push    r12
0x14000a33a  push    r14
0x14000a33c  push    r15
0x14000a33e  sub     rsp, 20h
0x14000a342  mov     r9d, [rcx+4]
0x14000a346  xor     eax, eax
0x14000a348  mov     [rsp+48h+arg_0], ax
0x14000a34d  xor     ebx, ebx
0x14000a34f  mov     [rsp+48h+arg_2], al
0x14000a353  mov     r12, r8
0x14000a356  mov     rax, [rcx+10h]
0x14000a35a  mov     rsi, rdx
0x14000a35d  mov     rbp, rcx
0x14000a360  mov     [rsp+48h+Entry], rbx
0x14000a365  cmp     r9d, [rax+4]
0x14000a369  jle     short loc_14000A389
0x14000a36b  lea     r9d, [rbx+1]
0x14000a36f  mov     r8d, 0C0000001h
0x14000a375  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x14000a37c  call    WfpReportSysErrorAsNtStatus
0x14000a381  mov     rdi, rax
0x14000a384  jmp     loc_14000A598
0x14000a389  mov     rdx, rbp
0x14000a38c  mov     rcx, rsi
0x14000a38f  call    ComputeAcceptBypassHash
0x14000a394  mov     ebx, 0B0h
0x14000a399  lea     r8, [rsp+48h+Entry]
0x14000a39e  mov     ecx, ebx
0x14000a3a0  mov     edx, 4C706657h
0x14000a3a5  mov     r15, rax
0x14000a3a8  call    WfpPoolAllocNonPaged
0x14000a3ad  mov     rdi, rax
0x14000a3b0  test    rax, rax
0x14000a3b3  jnz     loc_14000A59F
0x14000a3b9  mov     r8d, ebx; Size
0x14000a3bc  xor     edx, edx; Val
0x14000a3be  mov     rbx, [rsp+48h+Entry]
0x14000a3c3  mov     rcx, rbx; void *
0x14000a3c6  call    memset
0x14000a3cb  lea     r14, [rbx+58h]
0x14000a3cf  mov     edx, 4C706657h
0x14000a3d4  mov     [r14], rdi
0x14000a3d7  mov     r8, r14
0x14000a3da  mov     ecx, [rsi]
0x14000a3dc  call    WfpPoolAllocNonPaged
0x14000a3e1  mov     rdi, rax
0x14000a3e4  test    rax, rax
0x14000a3e7  jnz     loc_14000A5A4
0x14000a3ed  mov     eax, [rsi]
0x14000a3ef  mov     [rbx+50h], eax
0x14000a3f2  mov     r8d, eax; Size
0x14000a3f5  mov     rdx, [rsi+8]; Src
0x14000a3f9  mov     rcx, [r14]; void *
0x14000a3fc  call    memmove
0x14000a401  mov     rax, [rsi+10h]
0x14000a405  lea     r14, [rbx+98h]
0x14000a40c  mov     [rbx+60h], rax
0x14000a410  mov     rcx, [rsi+48h]; Sid
0x14000a414  call    cs:__imp_RtlLengthSid
0x14000a41b  nop     dword ptr [rax+rax+00h]
0x14000a420  mov     ecx, eax
0x14000a422  mov     r8, r14
0x14000a425  mov     edx, 4C706657h
0x14000a42a  call    WfpPoolAllocNonPaged
0x14000a42f  mov     rdi, rax
0x14000a432  test    rax, rax
0x14000a435  jnz     loc_14000A5A4
0x14000a43b  mov     rcx, [rsi+48h]; Sid
0x14000a43f  call    cs:__imp_RtlLengthSid
0x14000a446  nop     dword ptr [rax+rax+00h]
0x14000a44b  mov     rdx, [rsi+48h]; Src
0x14000a44f  mov     rcx, [r14]; void *
0x14000a452  mov     r8d, eax; Size
0x14000a455  call    memmove
0x14000a45a  lea     r14, [rbx+0A8h]
0x14000a461  mov     [r14], rdi
0x14000a464  mov     eax, [rsi+50h]
0x14000a467  mov     [rbx+0A0h], eax
0x14000a46d  mov     eax, [rsi+50h]
0x14000a470  test    eax, eax
0x14000a472  jz      short loc_14000A4A2
0x14000a474  mov     ecx, eax
0x14000a476  mov     r8, r14
0x14000a479  mov     edx, 4C706657h
0x14000a47e  call    WfpPoolAllocNonPaged
0x14000a483  mov     rdi, rax
0x14000a486  test    rax, rax
0x14000a489  jnz     loc_14000A5A4
0x14000a48f  mov     r8d, [rbx+0A0h]; Size
0x14000a496  mov     rdx, [rsi+58h]; Src
0x14000a49a  mov     rcx, [r14]; void *
0x14000a49d  call    memmove
0x14000a4a2  movups  xmm0, xmmword ptr [rsi+1Ch]
0x14000a4a6  lea     rdx, [rsp+48h+arg_0]
0x14000a4ab  movdqu  xmmword ptr [rbx+6Ch], xmm0
0x14000a4b0  mov     rax, [rsi+10h]
0x14000a4b4  mov     [rbx+60h], rax
0x14000a4b8  movzx   eax, word ptr [rsi+18h]
0x14000a4bc  mov     [rbx+68h], ax
0x14000a4c0  mov     al, [rsi+1Ah]
0x14000a4c3  mov     [rbx+6Ah], al
0x14000a4c6  mov     al, [rsi+1Bh]
0x14000a4c9  mov     [rbx+6Bh], al
0x14000a4cc  mov     eax, [rsi+2Ch]
0x14000a4cf  mov     [rbx+7Ch], eax
0x14000a4d2  mov     rax, [rsi+30h]
0x14000a4d6  mov     [rbx+80h], rax
0x14000a4dd  mov     eax, [rsi+38h]
0x14000a4e0  mov     [rbx+88h], eax
0x14000a4e6  mov     eax, [rsi+3Ch]
0x14000a4e9  mov     [rbx+8Ch], eax
0x14000a4ef  mov     eax, [rsi+40h]
0x14000a4f2  mov     [rbx+90h], eax
0x14000a4f8  mov     eax, [r12]
0x14000a4fc  mov     [rbx+40h], eax
0x14000a4ff  mov     rax, [r12+10h]
0x14000a504  mov     [rbx+48h], rax
0x14000a508  mov     [rbx+10h], r15
0x14000a50c  mov     eax, [rbp+24h]
0x14000a50f  mov     [rbx+18h], eax
0x14000a512  lea     rax, [rbx+20h]
0x14000a516  mov     [rax+8], rax
0x14000a51a  mov     [rax], rax
0x14000a51d  mov     rcx, cs:gWfpGlobal
0x14000a524  add     rcx, 6C0h
0x14000a52b  call    WfpAcquireFastWriteLock
0x14000a530  mov     esi, 1
0x14000a535  cmp     [rbp+0], esi
0x14000a538  jz      short loc_14000A554
0x14000a53a  mov     r9d, esi
0x14000a53d  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x14000a544  mov     r8d, 0C0000001h
0x14000a54a  call    WfpReportSysErrorAsNtStatus
0x14000a54f  mov     rdi, rax
0x14000a552  jmp     short loc_14000A580
0x14000a554  mov     rcx, [rbp+8]; HashTable
0x14000a558  xor     r9d, r9d; Context
0x14000a55b  mov     r8, r15; Signature
0x14000a55e  mov     rdx, rbx; Entry
0x14000a561  call    cs:__imp_RtlInsertEntryHashTable
0x14000a568  nop     dword ptr [rax+rax+00h]
0x14000a56d  test    al, al
0x14000a56f  jz      short loc_14000A53A
0x14000a571  lock add [rbp+4], esi
0x14000a575  mov     rdx, rbx
0x14000a578  mov     rcx, rbp
0x14000a57b  call    InsertCacheEntryLru
0x14000a580  mov     rcx, cs:gWfpGlobal
0x14000a587  lea     rdx, [rsp+48h+arg_0]
0x14000a58c  add     rcx, 6C0h
0x14000a593  call    WfpReleaseFastWriteLock
0x14000a598  test    rdi, rdi
0x14000a59b  jnz     short loc_14000A5A4
0x14000a59d  jmp     short loc_14000A5E8
0x14000a59f  mov     rbx, [rsp+48h+Entry]
0x14000a5a4  test    rbx, rbx
0x14000a5a7  jz      short loc_14000A5D4
0x14000a5a9  lea     rcx, [rbx+58h]
0x14000a5ad  call    WfpPoolFree
0x14000a5b2  lea     rcx, [rbx+98h]
0x14000a5b9  call    WfpPoolFree
0x14000a5be  lea     rcx, [rbx+0A8h]
0x14000a5c5  call    WfpPoolFree
0x14000a5ca  lea     rcx, [rsp+48h+Entry]
0x14000a5cf  call    WfpPoolFree
0x14000a5d4  test    rdi, rdi
0x14000a5d7  jz      short loc_14000A5E8
0x14000a5d9  lea     rdx, aInsertacceptby; "InsertAcceptBypassCacheEntry"
0x14000a5e0  mov     rcx, rdi
0x14000a5e3  call    WfpReportError
0x14000a5e8  mov     rbx, [rsp+48h+arg_8]
0x14000a5ed  mov     rax, rdi
0x14000a5f0  mov     rbp, [rsp+48h+arg_10]
0x14000a5f5  add     rsp, 20h
0x14000a5f9  pop     r15
0x14000a5fb  pop     r14
0x14000a5fd  pop     r12
0x14000a5ff  pop     rdi
0x14000a600  pop     rsi
0x14000a601  retn
```
