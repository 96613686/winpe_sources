# VIDMM_PARTITION::EnsureAdapter(VIDMM_GLOBAL *)

- ea: `0x1400c4a70`
- end: `0x1400c4d9b`
- name: `?EnsureAdapter@VIDMM_PARTITION@@QEAAJPEAVVIDMM_GLOBAL@@@Z`
- size: `811`
- prototype: `__int64 __fastcall(VIDMM_PARTITION *__hidden this, struct VIDMM_GLOBAL *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1400b514c`
- `0x1400b5f94`

## callees

- `0x1400045ec`
- `0x140030ae0`
- `0x140031178`
- `0x140032ae8`
- `0x140035bc8`
- `0x140058ac0`
- `0x1400c4894`
- `0x1400c4a70`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400c4c3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400c4c3f`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4ad4`
- `ntoskrnl!ExAllocatePool2` at `0x1400c4ad4`
- `ntoskrnl!PcwCreateInstance` at `0x1400c4c7f`
- `ntoskrnl!PcwCreateInstance` at `0x1400c4cf2`
- `ntoskrnl!PcwCreateInstance` at `0x1400c4c7f`
- `ntoskrnl!PcwCreateInstance` at `0x1400c4cf2`
- `watchdog!WdLogSingleEntry0` at `0x1400c4b19`
- `watchdog!WdLogSingleEntry0` at `0x1400c4b9c`
- `watchdog!WdLogSingleEntry0` at `0x1400c4c9e`
- `watchdog!WdLogSingleEntry0` at `0x1400c4d19`
- `watchdog!WdLogSingleEntry0` at `0x1400c4d36`
- `watchdog!WdLogSingleEntry0` at `0x1400c4b19`
- `watchdog!WdLogSingleEntry0` at `0x1400c4b9c`
- `watchdog!WdLogSingleEntry0` at `0x1400c4c9e`
- `watchdog!WdLogSingleEntry0` at `0x1400c4d19`
- `watchdog!WdLogSingleEntry0` at `0x1400c4d36`

## string_xrefs

- `0x1400c4bad`: `Failed to create naming string for CreateGpuPerformanceCounterSetLocalAdapterMemory`
- `0x1400c4caf`: `Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory`
- `0x1400c4d47`: `Failed to create naming string for Adapter Memory partitions`
- `0x1400c4d2a`: `Failed to create CreateGpuPerformanceCounterSetNonLocalAdapterMemory`

## pseudocode

```c
__int64 __fastcall VIDMM_PARTITION::EnsureAdapter(VIDMM_PARTITION *this, unsigned int **a2)
{
  struct VIDMM_PARTITION_ADAPTER_INFO *AdapterInfo; // rax
  struct VIDMM_PARTITION_ADAPTER_INFO *v5; // rbx
  unsigned __int64 v6; // rdi
  int v7; // ecx
  int v8; // r8d
  __int64 v9; // rax
  const wchar_t *v10; // r9
  __int64 result; // rax
  wchar_t *v12; // rbp
  NTSTATUS v13; // ebx
  unsigned int i; // edi
  unsigned int *v15; // r9
  __int64 v16; // r14
  PPCW_INSTANCE *v17; // r14
  int v18; // ecx
  int v19; // r8d
  __int64 v20; // rax
  const wchar_t *v21; // r9
  int v22; // edx
  PPCW_DATA Data; // [rsp+20h] [rbp-A8h]
  __int64 v24; // [rsp+28h] [rbp-A0h]
  __int64 v25; // [rsp+30h] [rbp-98h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-78h] BYREF
  struct _PCW_DATA v27; // [rsp+60h] [rbp-68h] BYREF
  struct _PCW_DATA v28; // [rsp+70h] [rbp-58h] BYREF

  AdapterInfo = VIDMM_PARTITION::GetAdapterInfo(this, (struct VIDMM_GLOBAL *)a2);
  v5 = AdapterInfo;
  if ( *((_QWORD *)AdapterInfo + 1) )
    return 0;
  v6 = *((unsigned int *)a2 + 778);
  if ( (unsigned int)v6 <= 1 )
  {
    *((_QWORD *)AdapterInfo + 3) = (char *)AdapterInfo + 32;
    if ( (_DWORD)v6 )
      memset((char *)AdapterInfo + 32, 0, 344 * v6);
  }
  else
  {
    if ( 0xFFFFFFFFFFFFFFFFuLL / v6 < 0x158 )
    {
LABEL_8:
      _InterlockedAdd(&dword_140086814, 1u);
      WdLogSingleEntry0(6);
      v9 = 459;
      v10 = L"Couldn't allocate memory for vidmmpartition.";
LABEL_9:
      WdLogGlobalForLineNumber = v9;
      DxgkLogInternalTriageEvent(v7, 262145, v8, (_DWORD)v10, v9, 0, 0, 0);
      return 3221225495LL;
    }
    *((_QWORD *)AdapterInfo + 3) = ExAllocatePool2(64, 344LL * (unsigned int)v6, 1647405398);
  }
  *((_DWORD *)v5 + 94) = v6;
  if ( !*((_QWORD *)v5 + 3) )
    goto LABEL_8;
  *((_QWORD *)v5 + 1) = a2;
  *(_QWORD *)v5 = this;
  VIDMM_GLOBAL::CalculatePartitionAdapterBudgets((VIDMM_GLOBAL *)a2, this, v5);
  v12 = (wchar_t *)operator new[](520, 1265072196, 258);
  if ( !v12 )
  {
    _InterlockedAdd(&dword_14008687C, 1u);
    WdLogSingleEntry0(6);
    v9 = 472;
    v10 = L"Failed to create naming string for CreateGpuPerformanceCounterSetLocalAdapterMemory";
    goto LABEL_9;
  }
  v13 = 0;
  for ( i = 0; i < *((_DWORD *)a2 + 778); ++i )
  {
    v15 = a2[3];
    v16 = *(_QWORD *)(384LL * v15[60] + *((_QWORD *)this + 5) + 24);
    LODWORD(v25) = *((_DWORD *)this + 8);
    DestinationString = 0;
    LODWORD(v24) = i;
    LODWORD(Data) = v15[103];
    v13 = RtlStringCbPrintfW(v12, 0x208u, L"luid_0x%08X_0x%08X_phys_%u_part_%u", v15[104], Data, v24, v25);
    if ( v13 < 0 )
    {
      WdLogSingleEntry0(1);
      v20 = 492;
      v21 = L"Failed to create naming string for Adapter Memory partitions";
      v22 = 0x40000;
      goto LABEL_24;
    }
    v17 = (PPCW_INSTANCE *)(344LL * i + v16);
    RtlInitUnicodeString(&DestinationString, v12);
    if ( *(_DWORD *)v17 )
    {
      if ( *(_DWORD *)v17 == 1 )
      {
        v28.Data = v17;
        v28.Size = 344;
        v13 = PcwCreateInstance(v17 + 42, GpuPerformanceCounterSetNonLocalAdapterMemory, &DestinationString, 1u, &v28);
        if ( v13 < 0 )
        {
          _InterlockedAdd(&dword_14008687C, 1u);
          WdLogSingleEntry0(6);
          v20 = 511;
          v21 = L"Failed to create CreateGpuPerformanceCounterSetNonLocalAdapterMemory";
LABEL_18:
          v22 = 262145;
LABEL_24:
          WdLogGlobalForLineNumber = v20;
          DxgkLogInternalTriageEvent(v18, v22, v19, (_DWORD)v21, v20, 0, 0, 0);
          break;
        }
      }
    }
    else
    {
      v27.Data = v17;
      v27.Size = 344;
      v13 = PcwCreateInstance(v17 + 42, GpuPerformanceCounterSetLocalAdapterMemory, &DestinationString, 1u, &v27);
      if ( v13 < 0 )
      {
        _InterlockedAdd(&dword_14008687C, 1u);
        WdLogSingleEntry0(6);
        v20 = 502;
        v21 = L"Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory";
        goto LABEL_18;
      }
    }
  }
  operator delete(v12);
  result = 0;
  if ( v13 < 0 )
    return (unsigned int)v13;
  return result;
}

```

## disassembly

```asm
0x1400c4a70  push    rbx
0x1400c4a72  push    rbp
0x1400c4a73  push    rsi
0x1400c4a74  push    rdi
0x1400c4a75  push    r12
0x1400c4a77  push    r13
0x1400c4a79  push    r14
0x1400c4a7b  push    r15
0x1400c4a7d  sub     rsp, 88h
0x1400c4a84  mov     rsi, rdx
0x1400c4a87  mov     r15, rcx
0x1400c4a8a  call    ?GetAdapterInfo@VIDMM_PARTITION@@QEAAPEAUVIDMM_PARTITION_ADAPTER_INFO@@PEAVVIDMM_GLOBAL@@@Z; VIDMM_PARTITION::GetAdapterInfo(VIDMM_GLOBAL *)
0x1400c4a8f  xor     r12d, r12d
0x1400c4a92  mov     rbx, rax
0x1400c4a95  cmp     [rax+8], r12
0x1400c4a99  jnz     loc_1400C4D84
0x1400c4a9f  mov     edi, [rsi+0C28h]
0x1400c4aa5  lea     r13d, [r12+1]
0x1400c4aaa  cmp     edi, r13d
0x1400c4aad  jbe     short loc_1400C4AE6
0x1400c4aaf  xor     edx, edx
0x1400c4ab1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400c4ab5  div     rdi
0x1400c4ab8  mov     ecx, edi
0x1400c4aba  cmp     rax, 158h
0x1400c4ac0  jb      short loc_1400C4B0C
0x1400c4ac2  imul    rdx, rcx, 158h
0x1400c4ac9  lea     ecx, [r12+40h]
0x1400c4ace  mov     r8d, 62316956h
0x1400c4ad4  call    cs:__imp_ExAllocatePool2
0x1400c4adb  nop     dword ptr [rax+rax+00h]
0x1400c4ae0  mov     [rbx+18h], rax
0x1400c4ae4  jmp     short loc_1400C4B00
0x1400c4ae6  lea     rcx, [rax+20h]; void *
0x1400c4aea  mov     [rax+18h], rcx
0x1400c4aee  test    edi, edi
0x1400c4af0  jz      short loc_1400C4B00
0x1400c4af2  imul    r8, rdi, 158h; Size
0x1400c4af9  xor     edx, edx; Val
0x1400c4afb  call    memset
0x1400c4b00  mov     [rbx+178h], edi
0x1400c4b06  cmp     [rbx+18h], r12
0x1400c4b0a  jnz     short loc_1400C4B5F
0x1400c4b0c  lock add cs:dword_140086814, r13d
0x1400c4b14  mov     ecx, 6
0x1400c4b19  call    cs:__imp_WdLogSingleEntry0
0x1400c4b20  nop     dword ptr [rax+rax+00h]
0x1400c4b25  mov     eax, 1CBh
0x1400c4b2a  lea     r9, aCouldnTAllocat_56; "Couldn't allocate memory for vidmmparti"...
0x1400c4b31  mov     [rsp+0C8h+var_90], r12
0x1400c4b36  mov     edx, 40001h
0x1400c4b3b  mov     [rsp+0C8h+var_98], r12
0x1400c4b40  mov     [rsp+0C8h+var_A0], r12
0x1400c4b45  mov     [rsp+0C8h+Data], rax
0x1400c4b4a  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c4b50  call    DxgkLogInternalTriageEvent
0x1400c4b55  mov     eax, 0C0000017h
0x1400c4b5a  jmp     loc_1400C4D86
0x1400c4b5f  mov     r8, rbx; struct VIDMM_PARTITION_ADAPTER_INFO *
0x1400c4b62  mov     [rbx+8], rsi
0x1400c4b66  mov     rdx, r15; struct VIDMM_PARTITION *
0x1400c4b69  mov     [rbx], r15
0x1400c4b6c  mov     rcx, rsi; this
0x1400c4b6f  call    ?CalculatePartitionAdapterBudgets@VIDMM_GLOBAL@@QEAAXPEAUVIDMM_PARTITION@@PEAUVIDMM_PARTITION_ADAPTER_INFO@@@Z; VIDMM_GLOBAL::CalculatePartitionAdapterBudgets(VIDMM_PARTITION *,VIDMM_PARTITION_ADAPTER_INFO *)
0x1400c4b74  mov     edx, 4B677844h
0x1400c4b79  mov     ecx, 208h
0x1400c4b7e  mov     r8d, 102h
0x1400c4b84  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1400c4b89  mov     rbp, rax
0x1400c4b8c  test    rax, rax
0x1400c4b8f  jnz     short loc_1400C4BB9
0x1400c4b91  lock add cs:dword_14008687C, r13d
0x1400c4b99  lea     ecx, [rax+6]
0x1400c4b9c  call    cs:__imp_WdLogSingleEntry0
0x1400c4ba3  nop     dword ptr [rax+rax+00h]
0x1400c4ba8  mov     eax, 1D8h
0x1400c4bad  lea     r9, aFailedToCreate_23; "Failed to create naming string for Crea"...
0x1400c4bb4  jmp     loc_1400C4B31
0x1400c4bb9  mov     ebx, r12d
0x1400c4bbc  mov     edi, r12d
0x1400c4bbf  cmp     edi, [rsi+0C28h]
0x1400c4bc5  jnb     loc_1400C4D72
0x1400c4bcb  mov     r9, [rsi+18h]
0x1400c4bcf  lea     r8, aLuid0x08x0x08x; "luid_0x%08X_0x%08X_phys_%u_part_%u"
0x1400c4bd6  xorps   xmm0, xmm0
0x1400c4bd9  mov     edx, 208h; cbDest
0x1400c4bde  mov     eax, [r9+0F0h]
0x1400c4be5  lea     rcx, [rax+rax*2]
0x1400c4be9  mov     rax, [r15+28h]
0x1400c4bed  shl     rcx, 7
0x1400c4bf1  mov     r14, [rcx+rax+18h]
0x1400c4bf6  mov     rcx, rbp; pszDest
0x1400c4bf9  mov     eax, [r15+20h]
0x1400c4bfd  mov     dword ptr [rsp+0C8h+var_98], eax
0x1400c4c01  movups  xmmword ptr [rsp+0C8h+DestinationString.Length], xmm0
0x1400c4c06  mov     eax, [r9+19Ch]
0x1400c4c0d  mov     r9d, [r9+1A0h]
0x1400c4c14  mov     dword ptr [rsp+0C8h+var_A0], edi
0x1400c4c18  mov     dword ptr [rsp+0C8h+Data], eax
0x1400c4c1c  call    RtlStringCbPrintfW
0x1400c4c21  mov     ebx, eax
0x1400c4c23  test    eax, eax
0x1400c4c25  js      loc_1400C4D33
0x1400c4c2b  mov     ecx, edi
0x1400c4c2d  imul    rdx, rcx, 158h
0x1400c4c34  lea     rcx, [rsp+0C8h+DestinationString]; DestinationString
0x1400c4c39  add     r14, rdx
0x1400c4c3c  mov     rdx, rbp; SourceString
0x1400c4c3f  call    cs:__imp_RtlInitUnicodeString
0x1400c4c46  nop     dword ptr [rax+rax+00h]
0x1400c4c4b  mov     eax, [r14]
0x1400c4c4e  test    eax, eax
0x1400c4c50  jnz     short loc_1400C4CC0
0x1400c4c52  mov     rdx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400c4c59  lea     rax, [rsp+0C8h+var_68]
0x1400c4c5e  lea     rcx, [r14+150h]; Instance
0x1400c4c65  mov     [rsp+0C8h+Data], rax; Data
0x1400c4c6a  mov     r9d, r13d; Count
0x1400c4c6d  mov     [rsp+0C8h+var_68.Data], r14
0x1400c4c72  lea     r8, [rsp+0C8h+DestinationString]; Name
0x1400c4c77  mov     [rsp+0C8h+var_68.Size], 158h
0x1400c4c7f  call    cs:__imp_PcwCreateInstance
0x1400c4c86  nop     dword ptr [rax+rax+00h]
0x1400c4c8b  mov     ebx, eax
0x1400c4c8d  test    eax, eax
0x1400c4c8f  jns     short loc_1400C4D04
0x1400c4c91  lock add cs:dword_14008687C, r13d
0x1400c4c99  mov     ecx, 6
0x1400c4c9e  call    cs:__imp_WdLogSingleEntry0
0x1400c4ca5  nop     dword ptr [rax+rax+00h]
0x1400c4caa  mov     eax, 1F6h
0x1400c4caf  lea     r9, aFailedToCreate_22; "Failed to create CreateGpuPerformanceCo"...
0x1400c4cb6  mov     edx, 40001h
0x1400c4cbb  jmp     loc_1400C4D53
0x1400c4cc0  cmp     eax, r13d
0x1400c4cc3  jnz     short loc_1400C4D04
0x1400c4cc5  mov     rdx, cs:GpuPerformanceCounterSetNonLocalAdapterMemory; Registration
0x1400c4ccc  lea     rax, [rsp+0C8h+var_58]
0x1400c4cd1  lea     rcx, [r14+150h]; Instance
0x1400c4cd8  mov     [rsp+0C8h+Data], rax; Data
0x1400c4cdd  mov     r9d, r13d; Count
0x1400c4ce0  mov     [rsp+0C8h+var_58.Data], r14
0x1400c4ce5  lea     r8, [rsp+0C8h+DestinationString]; Name
0x1400c4cea  mov     [rsp+0C8h+var_58.Size], 158h
0x1400c4cf2  call    cs:__imp_PcwCreateInstance
0x1400c4cf9  nop     dword ptr [rax+rax+00h]
0x1400c4cfe  mov     ebx, eax
0x1400c4d00  test    eax, eax
0x1400c4d02  js      short loc_1400C4D0C
0x1400c4d04  add     edi, r13d
0x1400c4d07  jmp     loc_1400C4BBF
0x1400c4d0c  lock add cs:dword_14008687C, r13d
0x1400c4d14  mov     ecx, 6
0x1400c4d19  call    cs:__imp_WdLogSingleEntry0
0x1400c4d20  nop     dword ptr [rax+rax+00h]
0x1400c4d25  mov     eax, 1FFh
0x1400c4d2a  lea     r9, aFailedToCreate_21; "Failed to create CreateGpuPerformanceCo"...
0x1400c4d31  jmp     short loc_1400C4CB6
0x1400c4d33  mov     ecx, r13d
0x1400c4d36  call    cs:__imp_WdLogSingleEntry0
0x1400c4d3d  nop     dword ptr [rax+rax+00h]
0x1400c4d42  mov     eax, 1ECh
0x1400c4d47  lea     r9, aFailedToCreate_27; "Failed to create naming string for Adap"...
0x1400c4d4e  mov     edx, 40000h
0x1400c4d53  mov     [rsp+0C8h+var_90], r12
0x1400c4d58  mov     [rsp+0C8h+var_98], r12
0x1400c4d5d  mov     [rsp+0C8h+var_A0], r12
0x1400c4d62  mov     [rsp+0C8h+Data], rax
0x1400c4d67  mov     cs:WdLogGlobalForLineNumber, eax
0x1400c4d6d  call    DxgkLogInternalTriageEvent
0x1400c4d72  mov     rcx, rbp; void *
0x1400c4d75  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400c4d7a  test    ebx, ebx
0x1400c4d7c  mov     eax, r12d
0x1400c4d7f  cmovs   eax, ebx
0x1400c4d82  jmp     short loc_1400C4D86
0x1400c4d84  xor     eax, eax
0x1400c4d86  add     rsp, 88h
0x1400c4d8d  pop     r15
0x1400c4d8f  pop     r14
0x1400c4d91  pop     r13
0x1400c4d93  pop     r12
0x1400c4d95  pop     rdi
0x1400c4d96  pop     rsi
0x1400c4d97  pop     rbp
0x1400c4d98  pop     rbx
0x1400c4d99  retn
```
