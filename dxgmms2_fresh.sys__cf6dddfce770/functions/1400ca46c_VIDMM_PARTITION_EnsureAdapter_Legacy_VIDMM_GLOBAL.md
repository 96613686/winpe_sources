# VIDMM_PARTITION::EnsureAdapter_Legacy(VIDMM_GLOBAL *)

- ea: `0x1400ca46c`
- end: `0x1400ca756`
- name: `?EnsureAdapter_Legacy@VIDMM_PARTITION@@QEAAJPEAVVIDMM_GLOBAL@@@Z`
- size: `746`
- prototype: `__int64 __fastcall(VIDMM_PARTITION *__hidden this, struct VIDMM_GLOBAL *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400b8b50`
- `0x1400b996c`

## callees

- `0x140004268`
- `0x14002e6c0`
- `0x14002ed58`
- `0x1400349c0`
- `0x14004910c`
- `0x1400ca290`
- `0x1400ca46c`
- `0x14010aeb4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400ca5eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ca5eb`
- `ntoskrnl!PcwCreateInstance` at `0x1400ca62e`
- `ntoskrnl!PcwCreateInstance` at `0x1400ca6a3`
- `ntoskrnl!PcwCreateInstance` at `0x1400ca62e`
- `ntoskrnl!PcwCreateInstance` at `0x1400ca6a3`
- `watchdog!WdLogSingleEntry0` at `0x1400ca4c6`
- `watchdog!WdLogSingleEntry0` at `0x1400ca548`
- `watchdog!WdLogSingleEntry0` at `0x1400ca64c`
- `watchdog!WdLogSingleEntry0` at `0x1400ca6d1`
- `watchdog!WdLogSingleEntry0` at `0x1400ca6f3`
- `watchdog!WdLogSingleEntry0` at `0x1400ca4c6`
- `watchdog!WdLogSingleEntry0` at `0x1400ca548`
- `watchdog!WdLogSingleEntry0` at `0x1400ca64c`
- `watchdog!WdLogSingleEntry0` at `0x1400ca6d1`
- `watchdog!WdLogSingleEntry0` at `0x1400ca6f3`

## string_xrefs

- `0x1400ca559`: `Failed to create naming string for CreateGpuPerformanceCounterSetLocalAdapterMemory`
- `0x1400ca704`: `Failed to create naming string for Adapter Memory partitions`
- `0x1400ca6e2`: `Failed to create CreateGpuPerformanceCounterSetNonLocalAdapterMemory`
- `0x1400ca65d`: `Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory`

## pseudocode

```c
__int64 __fastcall VIDMM_PARTITION::EnsureAdapter_Legacy(VIDMM_PARTITION *this, unsigned int **a2)
{
  __int64 v4; // rdx
  struct VIDMM_PARTITION_ADAPTER_INFO *v5; // rbx
  int v6; // ecx
  int v7; // r8d
  __int64 v8; // rax
  const wchar_t *v9; // r9
  __int64 result; // rax
  wchar_t *v11; // r15
  NTSTATUS v12; // ebx
  unsigned int v13; // esi
  unsigned int *v14; // r9
  __int64 v15; // r14
  PPCW_INSTANCE *v16; // r14
  int v17; // ecx
  int v18; // r8d
  __int64 v19; // rax
  const wchar_t *v20; // r9
  int v21; // edx
  PPCW_DATA Data; // [rsp+20h] [rbp-98h]
  __int64 v23; // [rsp+28h] [rbp-90h]
  __int64 v24; // [rsp+30h] [rbp-88h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-68h] BYREF
  struct _PCW_DATA v26; // [rsp+60h] [rbp-58h] BYREF
  struct _PCW_DATA v27; // [rsp+70h] [rbp-48h] BYREF

  v5 = (struct VIDMM_PARTITION_ADAPTER_INFO *)(*((_QWORD *)this + 5)
                                             + 384LL * VIDMM_GLOBAL::AdapterId((VIDMM_GLOBAL *)a2));
  if ( *((_QWORD *)v5 + 1) )
    return 0;
  if ( !NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::AllocateElements(
          (char *)v5 + 24,
          *(unsigned int *)(v4 + 3112)) )
  {
    _InterlockedIncrement(&dword_1400877F4);
    WdLogSingleEntry0(6);
    v8 = 470;
    v9 = L"Couldn't allocate memory for vidmmpartition.";
LABEL_4:
    WdLogGlobalForLineNumber = v8;
    DxgkLogInternalTriageEvent(v6, 262145, v7, (_DWORD)v9, v8, 0, 0, 0);
    return 3221225495LL;
  }
  *((_QWORD *)v5 + 1) = a2;
  *(_QWORD *)v5 = this;
  VIDMM_GLOBAL::CalculatePartitionAdapterBudgets((VIDMM_GLOBAL *)a2, this, v5);
  v11 = (wchar_t *)operator new[](520, 1265072196, 258);
  if ( !v11 )
  {
    _InterlockedIncrement(&dword_14008785C);
    WdLogSingleEntry0(6);
    v8 = 483;
    v9 = L"Failed to create naming string for CreateGpuPerformanceCounterSetLocalAdapterMemory";
    goto LABEL_4;
  }
  v12 = 0;
  v13 = 0;
  if ( *((_DWORD *)a2 + 778) )
  {
    while ( 1 )
    {
      v14 = a2[3];
      v15 = *(_QWORD *)(384LL * v14[60] + *((_QWORD *)this + 5) + 24);
      LODWORD(v24) = *((_DWORD *)this + 8);
      DestinationString = 0;
      LODWORD(v23) = v13;
      LODWORD(Data) = v14[103];
      v12 = RtlStringCbPrintfW(v11, 0x208u, L"luid_0x%08X_0x%08X_phys_%u_part_%u", v14[104], Data, v23, v24);
      if ( v12 < 0 )
        break;
      v16 = (PPCW_INSTANCE *)(344LL * v13 + v15);
      RtlInitUnicodeString(&DestinationString, v11);
      if ( *(_DWORD *)v16 )
      {
        if ( *(_DWORD *)v16 == 1 )
        {
          v27.Data = v16;
          v27.Size = 344;
          v12 = PcwCreateInstance(v16 + 42, GpuPerformanceCounterSetNonLocalAdapterMemory, &DestinationString, 1u, &v27);
          if ( v12 < 0 )
          {
            _InterlockedIncrement(&dword_14008785C);
            WdLogSingleEntry0(6);
            v19 = 522;
            v20 = L"Failed to create CreateGpuPerformanceCounterSetNonLocalAdapterMemory";
            goto LABEL_12;
          }
        }
      }
      else
      {
        v26.Data = v16;
        v26.Size = 344;
        v12 = PcwCreateInstance(v16 + 42, GpuPerformanceCounterSetLocalAdapterMemory, &DestinationString, 1u, &v26);
        if ( v12 < 0 )
        {
          _InterlockedIncrement(&dword_14008785C);
          WdLogSingleEntry0(6);
          v19 = 513;
          v20 = L"Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory";
LABEL_12:
          v21 = 262145;
          goto LABEL_19;
        }
      }
      if ( ++v13 >= *((_DWORD *)a2 + 778) )
        goto LABEL_20;
    }
    WdLogSingleEntry0(1);
    v19 = 503;
    v20 = L"Failed to create naming string for Adapter Memory partitions";
    v21 = 0x40000;
LABEL_19:
    WdLogGlobalForLineNumber = v19;
    DxgkLogInternalTriageEvent(v17, v21, v18, (_DWORD)v20, v19, 0, 0, 0);
  }
LABEL_20:
  operator delete(v11);
  result = 0;
  if ( v12 < 0 )
    return (unsigned int)v12;
  return result;
}

```

## disassembly

```asm
0x1400ca46c  push    rbx
0x1400ca46e  push    rbp
0x1400ca46f  push    rsi
0x1400ca470  push    rdi
0x1400ca471  push    r12
0x1400ca473  push    r14
0x1400ca475  push    r15
0x1400ca477  sub     rsp, 80h
0x1400ca47e  mov     rbp, rcx
0x1400ca481  mov     rdi, rdx
0x1400ca484  mov     rcx, rdx; this
0x1400ca487  call    ?AdapterId@VIDMM_GLOBAL@@QEBAKXZ; VIDMM_GLOBAL::AdapterId(void)
0x1400ca48c  mov     r8d, eax
0x1400ca48f  xor     r12d, r12d
0x1400ca492  lea     rbx, [r8+r8*2]
0x1400ca496  shl     rbx, 7
0x1400ca49a  add     rbx, [rbp+28h]
0x1400ca49e  cmp     [rbx+8], r12
0x1400ca4a2  jnz     loc_1400CA741
0x1400ca4a8  mov     edx, [rdx+0C28h]
0x1400ca4ae  lea     rcx, [rbx+18h]
0x1400ca4b2  call    ?AllocateElements@?$NonPagedPoolZeroedArray@UVIDMM_SEGMENT_GROUP_STATE@@$00$0GCDBGJFG@@@QEAAPEAUVIDMM_SEGMENT_GROUP_STATE@@I@Z; NonPagedPoolZeroedArray<VIDMM_SEGMENT_GROUP_STATE,1,1647405398>::AllocateElements(uint)
0x1400ca4b7  test    rax, rax
0x1400ca4ba  jnz     short loc_1400CA50C
0x1400ca4bc  lock inc cs:dword_1400877F4
0x1400ca4c3  lea     ecx, [rax+6]
0x1400ca4c6  call    cs:__imp_WdLogSingleEntry0
0x1400ca4cd  nop     dword ptr [rax+rax+00h]
0x1400ca4d2  mov     eax, 1D6h
0x1400ca4d7  lea     r9, aCouldnTAllocat_61; "Couldn't allocate memory for vidmmparti"...
0x1400ca4de  mov     [rsp+0B8h+var_80], r12
0x1400ca4e3  mov     edx, 40001h
0x1400ca4e8  mov     [rsp+0B8h+var_88], r12
0x1400ca4ed  mov     [rsp+0B8h+var_90], r12
0x1400ca4f2  mov     [rsp+0B8h+Data], rax
0x1400ca4f7  mov     cs:WdLogGlobalForLineNumber, eax
0x1400ca4fd  call    DxgkLogInternalTriageEvent
0x1400ca502  mov     eax, 0C0000017h
0x1400ca507  jmp     loc_1400CA743
0x1400ca50c  mov     r8, rbx; struct VIDMM_PARTITION_ADAPTER_INFO *
0x1400ca50f  mov     [rbx+8], rdi
0x1400ca513  mov     rdx, rbp; struct VIDMM_PARTITION *
0x1400ca516  mov     [rbx], rbp
0x1400ca519  mov     rcx, rdi; this
0x1400ca51c  call    ?CalculatePartitionAdapterBudgets@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PARTITION@@PEAUVIDMM_PARTITION_ADAPTER_INFO@@@Z; VIDMM_GLOBAL::CalculatePartitionAdapterBudgets(VIDMM_PARTITION *,VIDMM_PARTITION_ADAPTER_INFO *)
0x1400ca521  mov     edx, 4B677844h
0x1400ca526  mov     ecx, 208h
0x1400ca52b  mov     r8d, 102h
0x1400ca531  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400ca536  mov     r15, rax
0x1400ca539  test    rax, rax
0x1400ca53c  jnz     short loc_1400CA565
0x1400ca53e  lock inc cs:dword_14008785C
0x1400ca545  lea     ecx, [rax+6]
0x1400ca548  call    cs:__imp_WdLogSingleEntry0
0x1400ca54f  nop     dword ptr [rax+rax+00h]
0x1400ca554  mov     eax, 1E3h
0x1400ca559  lea     r9, aFailedToCreate_23; "Failed to create naming string for Crea"...
0x1400ca560  jmp     loc_1400CA4DE
0x1400ca565  mov     ebx, r12d
0x1400ca568  mov     esi, r12d
0x1400ca56b  cmp     [rdi+0C28h], r12d
0x1400ca572  jbe     loc_1400CA72F
0x1400ca578  mov     r9, [rdi+18h]
0x1400ca57c  lea     r8, aLuid0x08x0x08x; "luid_0x%08X_0x%08X_phys_%u_part_%u"
0x1400ca583  xorps   xmm0, xmm0
0x1400ca586  mov     edx, 208h; cbDest
0x1400ca58b  mov     eax, [r9+0F0h]
0x1400ca592  lea     rcx, [rax+rax*2]
0x1400ca596  mov     rax, [rbp+28h]
0x1400ca59a  shl     rcx, 7
0x1400ca59e  mov     r14, [rcx+rax+18h]
0x1400ca5a3  mov     rcx, r15; pszDest
0x1400ca5a6  mov     eax, [rbp+20h]
0x1400ca5a9  mov     dword ptr [rsp+0B8h+var_88], eax
0x1400ca5ad  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x1400ca5b2  mov     eax, [r9+19Ch]
0x1400ca5b9  mov     r9d, [r9+1A0h]
0x1400ca5c0  mov     dword ptr [rsp+0B8h+var_90], esi
0x1400ca5c4  mov     dword ptr [rsp+0B8h+Data], eax
0x1400ca5c8  call    RtlStringCbPrintfW
0x1400ca5cd  mov     ebx, eax
0x1400ca5cf  test    eax, eax
0x1400ca5d1  js      loc_1400CA6EE
0x1400ca5d7  mov     ecx, esi
0x1400ca5d9  imul    rdx, rcx, 158h
0x1400ca5e0  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1400ca5e5  add     r14, rdx
0x1400ca5e8  mov     rdx, r15; SourceString
0x1400ca5eb  call    cs:__imp_RtlInitUnicodeString
0x1400ca5f2  nop     dword ptr [rax+rax+00h]
0x1400ca5f7  mov     eax, [r14]
0x1400ca5fa  test    eax, eax
0x1400ca5fc  jnz     short loc_1400CA66E
0x1400ca5fe  mov     rdx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400ca605  lea     rax, [rsp+0B8h+var_58]
0x1400ca60a  lea     rcx, [r14+150h]; Instance
0x1400ca611  mov     [rsp+0B8h+Data], rax; Data
0x1400ca616  mov     r9d, 1; Count
0x1400ca61c  mov     [rsp+0B8h+var_58.Data], r14
0x1400ca621  lea     r8, [rsp+0B8h+DestinationString]; Name
0x1400ca626  mov     [rsp+0B8h+var_58.Size], 158h
0x1400ca62e  call    cs:__imp_PcwCreateInstance
0x1400ca635  nop     dword ptr [rax+rax+00h]
0x1400ca63a  mov     ebx, eax
0x1400ca63c  test    eax, eax
0x1400ca63e  jns     short loc_1400CA6B5
0x1400ca640  lock inc cs:dword_14008785C
0x1400ca647  mov     ecx, 6
0x1400ca64c  call    cs:__imp_WdLogSingleEntry0
0x1400ca653  nop     dword ptr [rax+rax+00h]
0x1400ca658  mov     eax, 201h
0x1400ca65d  lea     r9, aFailedToCreate_22; "Failed to create CreateGpuPerformanceCo"...
0x1400ca664  mov     edx, 40001h
0x1400ca669  jmp     loc_1400CA710
0x1400ca66e  cmp     eax, 1
0x1400ca671  jnz     short loc_1400CA6B5
0x1400ca673  mov     rdx, cs:GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x1400ca67a  lea     rax, [rsp+0B8h+var_48]
0x1400ca67f  lea     rcx, [r14+150h]; Instance
0x1400ca686  mov     [rsp+0B8h+Data], rax; Data
0x1400ca68b  mov     r9d, 1; Count
0x1400ca691  mov     [rsp+0B8h+var_48.Data], r14
0x1400ca696  lea     r8, [rsp+0B8h+DestinationString]; Name
0x1400ca69b  mov     [rsp+0B8h+var_48.Size], 158h
0x1400ca6a3  call    cs:__imp_PcwCreateInstance
0x1400ca6aa  nop     dword ptr [rax+rax+00h]
0x1400ca6af  mov     ebx, eax
0x1400ca6b1  test    eax, eax
0x1400ca6b3  js      short loc_1400CA6C5
0x1400ca6b5  inc     esi
0x1400ca6b7  cmp     esi, [rdi+0C28h]
0x1400ca6bd  jb      loc_1400CA578
0x1400ca6c3  jmp     short loc_1400CA72F
0x1400ca6c5  lock inc cs:dword_14008785C
0x1400ca6cc  mov     ecx, 6
0x1400ca6d1  call    cs:__imp_WdLogSingleEntry0
0x1400ca6d8  nop     dword ptr [rax+rax+00h]
0x1400ca6dd  mov     eax, 20Ah
0x1400ca6e2  lea     r9, aFailedToCreate_21; "Failed to create CreateGpuPerformanceCo"...
0x1400ca6e9  jmp     loc_1400CA664
0x1400ca6ee  mov     ecx, 1
0x1400ca6f3  call    cs:__imp_WdLogSingleEntry0
0x1400ca6fa  nop     dword ptr [rax+rax+00h]
0x1400ca6ff  mov     eax, 1F7h
0x1400ca704  lea     r9, aFailedToCreate_27; "Failed to create naming string for Adap"...
0x1400ca70b  mov     edx, 40000h
0x1400ca710  mov     [rsp+0B8h+var_80], r12
0x1400ca715  mov     [rsp+0B8h+var_88], r12
0x1400ca71a  mov     [rsp+0B8h+var_90], r12
0x1400ca71f  mov     [rsp+0B8h+Data], rax
0x1400ca724  mov     cs:WdLogGlobalForLineNumber, eax
0x1400ca72a  call    DxgkLogInternalTriageEvent
0x1400ca72f  mov     rcx, r15; void *
0x1400ca732  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400ca737  test    ebx, ebx
0x1400ca739  mov     eax, r12d
0x1400ca73c  cmovs   eax, ebx
0x1400ca73f  jmp     short loc_1400CA743
0x1400ca741  xor     eax, eax
0x1400ca743  add     rsp, 80h
0x1400ca74a  pop     r15
0x1400ca74c  pop     r14
0x1400ca74e  pop     r12
0x1400ca750  pop     rdi
0x1400ca751  pop     rsi
0x1400ca752  pop     rbp
0x1400ca753  pop     rbx
0x1400ca754  retn
```
