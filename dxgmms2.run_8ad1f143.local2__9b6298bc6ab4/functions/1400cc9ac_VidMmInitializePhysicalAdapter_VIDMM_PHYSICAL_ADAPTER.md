# VidMmInitializePhysicalAdapter(VIDMM_PHYSICAL_ADAPTER *)

- ea: `0x1400cc9ac`
- end: `0x1400ccd0b`
- name: `?VidMmInitializePhysicalAdapter@@YAJPEAUVIDMM_PHYSICAL_ADAPTER@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b514c`

## callees

- `0x1400045ec`
- `0x140035bc8`
- `0x140058680`
- `0x140058760`
- `0x1400b6080`
- `0x1400cbb98`
- `0x1400cbd1c`
- `0x1400cc9ac`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400ccab3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ccb9b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ccab3`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400ccb9b`
- `ntoskrnl!PcwCreateInstance` at `0x1400ccaeb`
- `ntoskrnl!PcwCreateInstance` at `0x1400ccbd3`
- `ntoskrnl!PcwCreateInstance` at `0x1400ccaeb`
- `ntoskrnl!PcwCreateInstance` at `0x1400ccbd3`
- `watchdog!WdLogSingleEntry2` at `0x1400cca02`
- `watchdog!WdLogSingleEntry2` at `0x1400cca02`
- `watchdog!WdLogSingleEntry1` at `0x1400cca68`
- `watchdog!WdLogSingleEntry1` at `0x1400ccb0d`
- `watchdog!WdLogSingleEntry1` at `0x1400ccbf5`
- `watchdog!WdLogSingleEntry1` at `0x1400cca68`
- `watchdog!WdLogSingleEntry1` at `0x1400ccb0d`
- `watchdog!WdLogSingleEntry1` at `0x1400ccbf5`

## string_xrefs

- `0x1400ccc01`: `Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory, Status=0x%.8x`
- `0x1400ccb19`: `Failed to create CreateGpuPerformanceCounterSetAdapterMemory, Status=0x%.8x`

## pseudocode

```c
__int64 __fastcall VidMmInitializePhysicalAdapter(struct VIDMM_PHYSICAL_ADAPTER *a1)
{
  __int64 v2; // r14
  int v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  __int64 v6; // r9
  NTSTATUS v7; // eax
  __int64 v8; // r15
  int v9; // ecx
  int v10; // r8d
  const wchar_t *v11; // r9
  int v12; // edx
  NTSTATUS v13; // eax
  char v14; // cl
  int v15; // eax
  NTSTATUS v16; // eax
  int v17; // eax
  unsigned __int64 v18; // rdx
  unsigned int i; // ebx
  unsigned int j; // r15d
  int Data; // [rsp+20h] [rbp-79h]
  int v22; // [rsp+28h] [rbp-71h]
  struct _PCW_DATA v23; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-39h] BYREF
  wchar_t pszDest[40]; // [rsp+70h] [rbp-29h] BYREF

  v2 = *((_QWORD *)a1 + 7);
  v3 = (*(__int64 (__fastcall **)(struct VIDMM_PHYSICAL_ADAPTER *))(*(_QWORD *)a1 + 8LL))(a1);
  v4 = v3;
  if ( v3 < 0 )
  {
    WdLogSingleEntry2(3, *((unsigned __int16 *)a1 + 36), v3);
    result = v4;
    WdLogGlobalForLineNumber = 985;
    return result;
  }
  v22 = *((unsigned __int16 *)a1 + 36);
  Data = *(_QWORD *)(*(_QWORD *)(v2 + 24) + 412LL);
  v6 = HIDWORD(*(_QWORD *)(*(_QWORD *)(v2 + 24) + 412LL));
  DestinationString = 0;
  v7 = RtlStringCbPrintfW(pszDest, 0x208u, L"luid_0x%08X_0x%08X_phys_%u", v6, Data, v22);
  v8 = v7;
  if ( v7 < 0 )
  {
    WdLogSingleEntry1(1, v7);
    v11 = L"Failed to construct perf counter name string, Status=0x%.8x";
    WdLogGlobalForLineNumber = 1014;
    v12 = 0x40000;
LABEL_5:
    DxgkLogInternalTriageEvent(v9, v12, v10, (_DWORD)v11, v8, 0, 0, 0);
    return (unsigned int)v8;
  }
  RtlInitUnicodeString(&DestinationString, pszDest);
  v23.Data = a1;
  v23.Size = 2392;
  v13 = PcwCreateInstance(
          (PPCW_INSTANCE *)a1 + 284,
          GpuPerformanceCounterSetAdapterMemory,
          &DestinationString,
          1u,
          &v23);
  v8 = v13;
  if ( v13 < 0 )
  {
    _InterlockedIncrement(&dword_14008687C);
    WdLogSingleEntry1(6, v13);
    v11 = L"Failed to create CreateGpuPerformanceCounterSetAdapterMemory, Status=0x%.8x";
    WdLogGlobalForLineNumber = 1025;
LABEL_8:
    v12 = 262145;
    goto LABEL_5;
  }
  v14 = *((_BYTE *)a1 + 1086);
  if ( (v14 & 6) == 6 )
  {
    v14 |= 0x80u;
    *((_BYTE *)a1 + 1086) = v14;
  }
  *((_BYTE *)a1 + 1160) |= 2u;
  if ( (v14 & 1) != 0 )
  {
    *((_DWORD *)a1 + 286) = dword_140086544;
    VIDMM_GLOBAL::InitializeSegmentGroupState(
      (VIDMM_GLOBAL *)v2,
      *((unsigned __int16 *)a1 + 36),
      (struct VIDMM_PHYSICAL_ADAPTER *)((char *)a1 + 1192),
      0);
    v15 = dword_140086548;
    *((_BYTE *)a1 + 1184) |= 3u;
    *((_DWORD *)a1 + 292) = v15;
    RtlInitUnicodeString(&DestinationString, pszDest);
    v23.Data = (char *)a1 + 1192;
    v23.Size = 344;
    v16 = PcwCreateInstance(
            (PPCW_INSTANCE *)a1 + 191,
            GpuPerformanceCounterSetLocalAdapterMemory,
            &DestinationString,
            1u,
            &v23);
    v8 = v16;
    if ( v16 < 0 )
    {
      _InterlockedIncrement(&dword_14008687C);
      WdLogSingleEntry1(6, v16);
      v11 = L"Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory, Status=0x%.8x";
      WdLogGlobalForLineNumber = 1066;
      goto LABEL_8;
    }
  }
  else
  {
    v17 = dword_140086548;
    *((_BYTE *)a1 + 1160) |= 1u;
    *((_BYTE *)a1 + 1184) &= ~2u;
    *((_DWORD *)a1 + 286) = v17;
  }
  v18 = *(_QWORD *)(v2 + 3256);
  if ( (*(_DWORD *)(*(_QWORD *)(v2 + 24) + 444LL) & 8) != 0 )
  {
    *(_BYTE *)(v2 + 3265) = v18 != 0;
    *((_BYTE *)a1 + 1084) |= 2u;
  }
  else
  {
    *(_BYTE *)(v2 + 3265) = v18 >= qword_1400862F0;
  }
  if ( (*(_BYTE *)(v2 + 37224) & 0x10) == 0 || (result = InitializeGpuVaState(a1), (int)result >= 0) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(v2 + 24) + 5156LL) & 1) != 0 )
    {
      for ( i = 0; i < 3; ++i )
      {
        for ( j = 0; j < 2; ++j )
          GetFenceStorageAllocInfo_0((VIDMM_GLOBAL *)v2, (__int64)a1 + 176 * j + 88 * i + 88 * j + 136);
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400cc9ac  mov     [rsp-8+arg_8], rbx
0x1400cc9b1  mov     [rsp-8+arg_10], rdi
0x1400cc9b6  push    rbp
0x1400cc9b7  push    r12
0x1400cc9b9  push    r13
0x1400cc9bb  push    r14
0x1400cc9bd  push    r15
0x1400cc9bf  lea     rbp, [rsp-37h]
0x1400cc9c4  sub     rsp, 0D0h
0x1400cc9cb  mov     rax, cs:__security_cookie
0x1400cc9d2  xor     rax, rsp
0x1400cc9d5  mov     [rbp+57h+var_30], rax
0x1400cc9d9  mov     rax, [rcx]
0x1400cc9dc  mov     rdi, rcx
0x1400cc9df  mov     r14, [rcx+38h]
0x1400cc9e3  mov     rax, [rax+8]
0x1400cc9e7  call    _guard_dispatch_icall
0x1400cc9ec  xor     r12d, r12d
0x1400cc9ef  movsxd  rbx, eax
0x1400cc9f2  test    eax, eax
0x1400cc9f4  jns     short loc_1400CCA1F
0x1400cc9f6  movzx   edx, word ptr [rdi+48h]
0x1400cc9fa  lea     ecx, [r12+3]
0x1400cc9ff  mov     r8, rbx
0x1400cca02  call    cs:__imp_WdLogSingleEntry2
0x1400cca09  nop     dword ptr [rax+rax+00h]
0x1400cca0e  mov     eax, ebx
0x1400cca10  mov     cs:WdLogGlobalForLineNumber, 3D9h
0x1400cca1a  jmp     loc_1400CCCE1
0x1400cca1f  mov     rax, [r14+18h]
0x1400cca23  lea     r8, aLuid0x08x0x08x_0; "luid_0x%08X_0x%08X_phys_%u"
0x1400cca2a  movzx   ecx, word ptr [rdi+48h]
0x1400cca2e  xorps   xmm0, xmm0
0x1400cca31  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x1400cca35  mov     edx, 208h; cbDest
0x1400cca3a  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400cca3e  mov     rax, [rax+19Ch]
0x1400cca45  mov     r9, rax
0x1400cca48  mov     dword ptr [rsp+0F0h+Data], eax
0x1400cca4c  shr     r9, 20h
0x1400cca50  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400cca54  call    RtlStringCbPrintfW
0x1400cca59  movsxd  r15, eax
0x1400cca5c  test    eax, eax
0x1400cca5e  jns     short loc_1400CCAAB
0x1400cca60  mov     rdx, r15
0x1400cca63  mov     ecx, 1
0x1400cca68  call    cs:__imp_WdLogSingleEntry1
0x1400cca6f  nop     dword ptr [rax+rax+00h]
0x1400cca74  lea     r9, aFailedToConstr; "Failed to construct perf counter name s"...
0x1400cca7b  mov     cs:WdLogGlobalForLineNumber, 3F6h
0x1400cca85  mov     edx, 40000h
0x1400cca8a  mov     [rsp+0F0h+var_B8], r12
0x1400cca8f  mov     [rsp+0F0h+var_C0], r12
0x1400cca94  mov     [rsp+0F0h+var_C8], r12
0x1400cca99  mov     [rsp+0F0h+Data], r15
0x1400cca9e  call    DxgkLogInternalTriageEvent
0x1400ccaa3  mov     eax, r15d
0x1400ccaa6  jmp     loc_1400CCCE1
0x1400ccaab  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400ccaaf  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400ccab3  call    cs:__imp_RtlInitUnicodeString
0x1400ccaba  nop     dword ptr [rax+rax+00h]
0x1400ccabf  mov     rdx, cs:GpuPerformanceCounterSetAdapterMemory; Registration
0x1400ccac6  lea     rax, [rbp+57h+var_A0]
0x1400ccaca  lea     rcx, [rdi+8E0h]; Instance
0x1400ccad1  mov     [rsp+0F0h+Data], rax; Data
0x1400ccad6  mov     r9d, 1; Count
0x1400ccadc  mov     [rbp+57h+var_A0.Data], rdi
0x1400ccae0  lea     r8, [rbp+57h+DestinationString]; Name
0x1400ccae4  mov     [rbp+57h+var_A0.Size], 958h
0x1400ccaeb  call    cs:__imp_PcwCreateInstance
0x1400ccaf2  nop     dword ptr [rax+rax+00h]
0x1400ccaf7  movsxd  r15, eax
0x1400ccafa  test    eax, eax
0x1400ccafc  jns     short loc_1400CCB34
0x1400ccafe  lock inc cs:dword_14008687C
0x1400ccb05  mov     rdx, r15
0x1400ccb08  mov     ecx, 6
0x1400ccb0d  call    cs:__imp_WdLogSingleEntry1
0x1400ccb14  nop     dword ptr [rax+rax+00h]
0x1400ccb19  lea     r9, aFailedToCreate_10; "Failed to create CreateGpuPerformanceCo"...
0x1400ccb20  mov     cs:WdLogGlobalForLineNumber, 401h
0x1400ccb2a  mov     edx, 40001h
0x1400ccb2f  jmp     loc_1400CCA8A
0x1400ccb34  mov     cl, [rdi+43Eh]
0x1400ccb3a  mov     al, cl
0x1400ccb3c  and     al, 6
0x1400ccb3e  cmp     al, 6
0x1400ccb40  jnz     short loc_1400CCB4B
0x1400ccb42  or      cl, 80h
0x1400ccb45  mov     [rdi+43Eh], cl
0x1400ccb4b  or      byte ptr [rdi+488h], 2
0x1400ccb52  test    cl, 1
0x1400ccb55  jz      loc_1400CCC17
0x1400ccb5b  mov     eax, cs:dword_140086544
0x1400ccb61  lea     rbx, [rdi+4A8h]
0x1400ccb68  mov     [rdi+478h], eax
0x1400ccb6e  mov     r8, rbx; struct VIDMM_SEGMENT_GROUP_STATE *
0x1400ccb71  movzx   edx, word ptr [rdi+48h]; unsigned int
0x1400ccb75  xor     r9d, r9d; unsigned __int64
0x1400ccb78  mov     rcx, r14; this
0x1400ccb7b  call    ?InitializeSegmentGroupState@VIDMM_GLOBAL@@QEAAXIPEAUVIDMM_SEGMENT_GROUP_STATE@@_K@Z; VIDMM_GLOBAL::InitializeSegmentGroupState(uint,VIDMM_SEGMENT_GROUP_STATE *,unsigned __int64)
0x1400ccb80  mov     eax, cs:dword_140086548
0x1400ccb86  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400ccb8a  or      byte ptr [rdi+4A0h], 3
0x1400ccb91  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400ccb95  mov     [rdi+490h], eax
0x1400ccb9b  call    cs:__imp_RtlInitUnicodeString
0x1400ccba2  nop     dword ptr [rax+rax+00h]
0x1400ccba7  mov     rdx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400ccbae  lea     rax, [rbp+57h+var_A0]
0x1400ccbb2  lea     rcx, [rbx+150h]; Instance
0x1400ccbb9  mov     [rsp+0F0h+Data], rax; Data
0x1400ccbbe  mov     r9d, 1; Count
0x1400ccbc4  mov     [rbp+57h+var_A0.Data], rbx
0x1400ccbc8  lea     r8, [rbp+57h+DestinationString]; Name
0x1400ccbcc  mov     [rbp+57h+var_A0.Size], 158h
0x1400ccbd3  call    cs:__imp_PcwCreateInstance
0x1400ccbda  nop     dword ptr [rax+rax+00h]
0x1400ccbdf  movsxd  r15, eax
0x1400ccbe2  test    eax, eax
0x1400ccbe4  jns     short loc_1400CCC31
0x1400ccbe6  lock inc cs:dword_14008687C
0x1400ccbed  mov     rdx, r15
0x1400ccbf0  mov     ecx, 6
0x1400ccbf5  call    cs:__imp_WdLogSingleEntry1
0x1400ccbfc  nop     dword ptr [rax+rax+00h]
0x1400ccc01  lea     r9, aFailedToCreate_3; "Failed to create CreateGpuPerformanceCo"...
0x1400ccc08  mov     cs:WdLogGlobalForLineNumber, 42Ah
0x1400ccc12  jmp     loc_1400CCB2A
0x1400ccc17  mov     eax, cs:dword_140086548
0x1400ccc1d  or      byte ptr [rdi+488h], 1
0x1400ccc24  and     byte ptr [rdi+4A0h], 0FDh
0x1400ccc2b  mov     [rdi+478h], eax
0x1400ccc31  mov     rax, [r14+18h]
0x1400ccc35  mov     rdx, [r14+0CB8h]
0x1400ccc3c  mov     ecx, [rax+1BCh]
0x1400ccc42  test    cl, 8
0x1400ccc45  jz      short loc_1400CCC5D
0x1400ccc47  test    rdx, rdx
0x1400ccc4a  setnz   al
0x1400ccc4d  mov     [r14+0CC1h], al
0x1400ccc54  or      byte ptr [rdi+43Ch], 2
0x1400ccc5b  jmp     short loc_1400CCC6E
0x1400ccc5d  cmp     rdx, cs:qword_1400862F0
0x1400ccc64  setnb   al
0x1400ccc67  mov     [r14+0CC1h], al
0x1400ccc6e  test    byte ptr [r14+9168h], 10h
0x1400ccc76  jz      short loc_1400CCC84
0x1400ccc78  mov     rcx, rdi; struct VIDMM_PHYSICAL_ADAPTER *
0x1400ccc7b  call    InitializeGpuVaState
0x1400ccc80  test    eax, eax
0x1400ccc82  js      short loc_1400CCCE1
0x1400ccc84  mov     rax, [r14+18h]
0x1400ccc88  test    byte ptr [rax+1424h], 1
0x1400ccc8f  jz      short loc_1400CCCDF
0x1400ccc91  mov     ebx, r12d
0x1400ccc94  lea     r13, [rdi+88h]
0x1400ccc9b  mov     r15d, r12d
0x1400ccc9e  mov     r12d, ebx
0x1400ccca1  movzx   r9d, word ptr [rdi+48h]
0x1400ccca6  mov     r8d, r15d
0x1400ccca9  mov     ecx, r15d
0x1400cccac  mov     edx, ebx
0x1400cccae  lea     rax, [r12+rcx*2]
0x1400cccb2  add     rcx, rax
0x1400cccb5  imul    rax, rcx, 58h ; 'X'
0x1400cccb9  mov     rcx, r14; this
0x1400cccbc  add     rax, r13
0x1400cccbf  mov     [rsp+0F0h+Data], rax; __int64
0x1400cccc4  call    GetFenceStorageAllocInfo_0
0x1400cccc9  inc     r15d
0x1400ccccc  cmp     r15d, 2
0x1400cccd0  jb      short loc_1400CCCA1
0x1400cccd2  inc     ebx
0x1400cccd4  mov     r12d, 0
0x1400cccda  cmp     ebx, 3
0x1400cccdd  jb      short loc_1400CCC9B
0x1400cccdf  xor     eax, eax
0x1400ccce1  mov     rcx, [rbp+57h+var_30]
0x1400ccce5  xor     rcx, rsp; StackCookie
0x1400ccce8  call    __security_check_cookie
0x1400ccced  lea     r11, [rsp+0F0h+var_20]
0x1400cccf5  mov     rbx, [r11+38h]
0x1400cccf9  mov     rdi, [r11+40h]
0x1400cccfd  mov     rsp, r11
0x1400ccd00  pop     r15
0x1400ccd02  pop     r14
0x1400ccd04  pop     r13
0x1400ccd06  pop     r12
0x1400ccd08  pop     rbp
0x1400ccd09  retn
```
