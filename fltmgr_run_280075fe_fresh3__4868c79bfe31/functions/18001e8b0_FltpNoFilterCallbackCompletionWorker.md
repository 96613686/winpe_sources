# FltpNoFilterCallbackCompletionWorker

- ea: `0x18001e8b0`
- end: `0x18001ead8`
- name: `FltpNoFilterCallbackCompletionWorker`
- size: `552`
- prototype: `__int64 __fastcall(PVOID IoObject, PVOID Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e60`
- `0x1800785a0`

## callees

- `0x1800148b0`
- `0x180016f80`
- `0x180017fc0`
- `0x18001e8b0`
- `0x180060930`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001ea55`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18001ea55`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001e8da`
- `ntoskrnl!KeGetCurrentIrql` at `0x18001e8da`
- `ntoskrnl!IoInitializeWorkItem` at `0x18001ea9c`
- `ntoskrnl!IoInitializeWorkItem` at `0x18001ea9c`
- `ntoskrnl!IoQueueWorkItemEx` at `0x18001eab8`
- `ntoskrnl!IoQueueWorkItemEx` at `0x18001eab8`

## string_xrefs

- `0x18001ea83`: `FltpNoFilterCallbackCompletionWorker`

## pseudocode

```c
__int64 __fastcall FltpNoFilterCallbackCompletionWorker(
        _QWORD *IoObject,
        _QWORD *Context,
        PIO_WORKITEM IoWorkItem,
        unsigned __int8 a4)
{
  char *v5; // rdi
  _DWORD *v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // esi
  int v12; // ecx
  _BYTE *v13; // rax
  _DWORD *v14; // rax
  char v15; // al
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v19; // rax
  __int64 v20; // rcx

  v5 = (char *)Context[23];
  v9 = *(_DWORD **)(IoObject[8] + 80LL);
  if ( KeGetCurrentIrql() < 2u )
  {
    v11 = 0;
    if ( *((_BYTE *)Context + 65) )
      *(_BYTE *)(Context[23] + 3LL) |= 1u;
    if ( (v9[14] & 0x100) == 0 )
      goto LABEL_35;
    if ( *v5 == 6 )
    {
      v12 = *((_DWORD *)v5 + 4);
      if ( (unsigned int)(v12 - 19) <= 1 || v12 == 39 )
        goto LABEL_34;
      if ( v12 == 13 )
      {
        v13 = (_BYTE *)Context[3];
        if ( v13 && *v13 )
          goto LABEL_34;
      }
      else if ( v12 == 64 )
      {
        v14 = (_DWORD *)Context[3];
        if ( v14 )
        {
          if ( (*v14 & 1) != 0 )
            goto LABEL_34;
        }
      }
    }
    else if ( *v5 == 4 && ((Context[2] & 1) != 0 || (v9[14] & 1) != 0 || v9[15] == 27) && (Context[2] & 0x42) == 0 )
    {
      goto LABEL_34;
    }
    v15 = *v5;
    if ( *v5 )
    {
      if ( v15 == 13 )
      {
        v16 = *((_DWORD *)v5 + 6);
        if ( v16 != 622792 && v16 != 623208 && v16 != 1327346 && v16 != 1343730 && v16 != 590047 )
          goto LABEL_35;
      }
      else
      {
        if ( v15 != 14 )
          goto LABEL_35;
        v17 = *((_DWORD *)v5 + 6);
        if ( v17 != 1328152 && v17 != 1344540 )
          goto LABEL_35;
      }
    }
    else if ( *((_DWORD *)v5 + 4) >= 0x1000000u )
    {
      goto LABEL_35;
    }
LABEL_34:
    v11 = FltpDataScanConflictProcessing(Context, IoObject, 0, a4);
    if ( v11 == -1073741802 )
    {
LABEL_39:
      if ( IoWorkItem )
        ExFreeToNPagedLookasideList(&stru_18003ED40, IoWorkItem);
      return v11;
    }
LABEL_35:
    FltpPurgeAndReinstateNameCacheForPosixDelete(v9);
    v18 = Context[23];
    if ( *(_BYTE *)v18 == 6 )
    {
      v19 = (unsigned int)(*(_DWORD *)(v18 + 16) - 10);
      if ( (unsigned int)v19 <= 0x3E )
      {
        v20 = 0x4080000040000003LL;
        if ( _bittest64(&v20, v19) )
          FltpReinstateNameCachingAllFrames(v9, 0);
      }
    }
    goto LABEL_39;
  }
  if ( (byte_1800404C2 & 0x10) != 0 )
    McTemplateU0sp_EtwWriteTransfer(v10, fltmgr_c4858, "FltpNoFilterCallbackCompletionWorker", Context);
  IoInitializeWorkItem(IoObject, IoWorkItem);
  IoQueueWorkItemEx(IoWorkItem, (PIO_WORKITEM_ROUTINE_EX)FltpNoFilterCallbacksWorkerThread, CriticalWorkQueue, Context);
  return 3221225494LL;
}

```

## disassembly

```asm
0x18001e8b0  push    rbx
0x18001e8b2  push    rbp
0x18001e8b3  push    rdi
0x18001e8b4  push    r12
0x18001e8b6  push    r14
0x18001e8b8  push    r15
0x18001e8ba  sub     rsp, 38h
0x18001e8be  mov     rax, [rcx+40h]
0x18001e8c2  movzx   r12d, r9b
0x18001e8c6  mov     rdi, [rdx+0B8h]
0x18001e8cd  mov     rbp, r8
0x18001e8d0  mov     rbx, rdx
0x18001e8d3  mov     r15, rcx
0x18001e8d6  mov     r14, [rax+50h]
0x18001e8da  call    cs:__imp_KeGetCurrentIrql
0x18001e8e1  nop     dword ptr [rax+rax+00h]
0x18001e8e6  cmp     al, 2
0x18001e8e8  jnb     loc_18001EA77
0x18001e8ee  mov     [rsp+68h+arg_0], rsi
0x18001e8f3  xor     esi, esi
0x18001e8f5  cmp     [rbx+41h], sil
0x18001e8f9  jz      short loc_18001E906
0x18001e8fb  mov     rax, [rbx+0B8h]
0x18001e902  or      byte ptr [rax+3], 1
0x18001e906  mov     eax, [r14+38h]
0x18001e90a  bt      eax, 8
0x18001e90e  jnb     loc_18001E9F1
0x18001e914  movzx   eax, byte ptr [rdi]
0x18001e917  cmp     al, 6
0x18001e919  jnz     short loc_18001E962
0x18001e91b  mov     ecx, [rdi+10h]
0x18001e91e  lea     eax, [rcx-13h]
0x18001e921  cmp     eax, 1
0x18001e924  jbe     loc_18001E9D6
0x18001e92a  cmp     ecx, 27h ; '''
0x18001e92d  jz      loc_18001E9D6
0x18001e933  cmp     ecx, 0Dh
0x18001e936  jnz     short loc_18001E94C
0x18001e938  mov     rax, [rbx+18h]
0x18001e93c  test    rax, rax
0x18001e93f  jz      short loc_18001E983
0x18001e941  cmp     [rax], sil
0x18001e944  jnz     loc_18001E9D6
0x18001e94a  jmp     short loc_18001E983
0x18001e94c  cmp     ecx, 40h ; '@'
0x18001e94f  jnz     short loc_18001E983
0x18001e951  mov     rax, [rbx+18h]
0x18001e955  test    rax, rax
0x18001e958  jz      short loc_18001E983
0x18001e95a  mov     eax, [rax]
0x18001e95c  test    al, 1
0x18001e95e  jz      short loc_18001E983
0x18001e960  jmp     short loc_18001E9D6
0x18001e962  cmp     al, 4
0x18001e964  jnz     short loc_18001E983
0x18001e966  mov     eax, [rbx+10h]
0x18001e969  test    al, 1
0x18001e96b  jnz     short loc_18001E97C
0x18001e96d  mov     eax, [r14+38h]
0x18001e971  test    al, 1
0x18001e973  jnz     short loc_18001E97C
0x18001e975  cmp     dword ptr [r14+3Ch], 1Bh
0x18001e97a  jnz     short loc_18001E983
0x18001e97c  mov     eax, [rbx+10h]
0x18001e97f  test    al, 42h
0x18001e981  jz      short loc_18001E9D6
0x18001e983  movzx   eax, byte ptr [rdi]
0x18001e986  test    al, al
0x18001e988  jnz     short loc_18001E995
0x18001e98a  cmp     dword ptr [rdi+10h], 1000000h
0x18001e991  jb      short loc_18001E9D6
0x18001e993  jmp     short loc_18001E9F1
0x18001e995  cmp     al, 0Dh
0x18001e997  jnz     short loc_18001E9C1
0x18001e999  mov     eax, [rdi+18h]
0x18001e99c  cmp     eax, 980C8h
0x18001e9a1  jz      short loc_18001E9D6
0x18001e9a3  cmp     eax, 98268h
0x18001e9a8  jz      short loc_18001E9D6
0x18001e9aa  cmp     eax, 1440F2h
0x18001e9af  jz      short loc_18001E9D6
0x18001e9b1  cmp     eax, 1480F2h
0x18001e9b6  jz      short loc_18001E9D6
0x18001e9b8  cmp     eax, 900DFh
0x18001e9bd  jz      short loc_18001E9D6
0x18001e9bf  jmp     short loc_18001E9F1
0x18001e9c1  cmp     al, 0Eh
0x18001e9c3  jnz     short loc_18001E9F1
0x18001e9c5  mov     eax, [rdi+18h]
0x18001e9c8  cmp     eax, 144418h
0x18001e9cd  jz      short loc_18001E9D6
0x18001e9cf  cmp     eax, 14841Ch
0x18001e9d4  jnz     short loc_18001E9F1
0x18001e9d6  movzx   r9d, r12b
0x18001e9da  xor     r8d, r8d
0x18001e9dd  mov     rdx, r15
0x18001e9e0  mov     rcx, rbx
0x18001e9e3  call    FltpDataScanConflictProcessing
0x18001e9e8  mov     esi, eax
0x18001e9ea  cmp     eax, 0C0000016h
0x18001e9ef  jz      short loc_18001EA46
0x18001e9f1  mov     rdx, [rdi+30h]
0x18001e9f5  xor     r9d, r9d
0x18001e9f8  mov     r8, rbx
0x18001e9fb  mov     rcx, r14; OwnerId
0x18001e9fe  call    FltpPurgeAndReinstateNameCacheForPosixDelete
0x18001ea03  mov     rax, [rbx+0B8h]
0x18001ea0a  cmp     byte ptr [rax], 6
0x18001ea0d  jnz     short loc_18001EA46
0x18001ea0f  mov     eax, [rax+10h]
0x18001ea12  add     eax, 0FFFFFFF6h
0x18001ea15  cmp     eax, 3Eh ; '>'
0x18001ea18  ja      short loc_18001EA46
0x18001ea1a  mov     rcx, 4080000040000003h
0x18001ea24  bt      rcx, rax
0x18001ea28  jnb     short loc_18001EA46
0x18001ea2a  mov     r8d, [rbx+30h]
0x18001ea2e  mov     r9, rbx
0x18001ea31  mov     rdx, [rdi+30h]
0x18001ea35  mov     rcx, r14; OwnerId
0x18001ea38  mov     [rsp+68h+var_48], 0; __int64
0x18001ea41  call    FltpReinstateNameCachingAllFrames
0x18001ea46  test    rbp, rbp
0x18001ea49  jz      short loc_18001EA61
0x18001ea4b  mov     rdx, rbp; Entry
0x18001ea4e  lea     rcx, stru_18003ED40; Lookaside
0x18001ea55  call    cs:__imp_ExFreeToNPagedLookasideList
0x18001ea5c  nop     dword ptr [rax+rax+00h]
0x18001ea61  mov     eax, esi
0x18001ea63  mov     rsi, [rsp+68h+arg_0]
0x18001ea68  add     rsp, 38h
0x18001ea6c  pop     r15
0x18001ea6e  pop     r14
0x18001ea70  pop     r12
0x18001ea72  pop     rdi
0x18001ea73  pop     rbp
0x18001ea74  pop     rbx
0x18001ea75  retn
0x18001ea77  test    cs:byte_1800404C2, 10h
0x18001ea7e  jz      short loc_18001EA96
0x18001ea80  mov     r9, rbx
0x18001ea83  lea     r8, aFltpnofilterca; "FltpNoFilterCallbackCompletionWorker"
0x18001ea8a  lea     rdx, fltmgr_c4858
0x18001ea91  call    McTemplateU0sp_EtwWriteTransfer
0x18001ea96  mov     rdx, rbp; IoWorkItem
0x18001ea99  mov     rcx, r15; IoObject
0x18001ea9c  call    cs:__imp_IoInitializeWorkItem
0x18001eaa3  nop     dword ptr [rax+rax+00h]
0x18001eaa8  mov     r9, rbx; Context
0x18001eaab  lea     rdx, FltpNoFilterCallbacksWorkerThread; WorkerRoutine
0x18001eab2  xor     r8d, r8d; QueueType
0x18001eab5  mov     rcx, rbp; IoWorkItem
0x18001eab8  call    cs:__imp_IoQueueWorkItemEx
0x18001eabf  nop     dword ptr [rax+rax+00h]
0x18001eac4  mov     eax, 0C0000016h
0x18001eac9  add     rsp, 38h
0x18001eacd  pop     r15
0x18001eacf  pop     r14
0x18001ead1  pop     r12
0x18001ead3  pop     rdi
0x18001ead4  pop     rbp
0x18001ead5  pop     rbx
0x18001ead6  retn
```
