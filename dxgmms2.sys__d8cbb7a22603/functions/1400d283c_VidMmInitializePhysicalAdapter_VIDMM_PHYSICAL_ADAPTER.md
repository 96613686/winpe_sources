# VidMmInitializePhysicalAdapter(VIDMM_PHYSICAL_ADAPTER *)

- ea: `0x1400d283c`
- end: `0x1400d2b9b`
- name: `?VidMmInitializePhysicalAdapter@@YAJPEAUVIDMM_PHYSICAL_ADAPTER@@@Z`
- size: `863`
- prototype: `__int64 __fastcall(struct VIDMM_PHYSICAL_ADAPTER *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400b8b50`

## callees

- `0x140004268`
- `0x1400349c0`
- `0x140058f50`
- `0x140059030`
- `0x1400b9a58`
- `0x1400d1aa8`
- `0x1400d1c2c`
- `0x1400d283c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2943`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a2b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2943`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400d2a2b`
- `ntoskrnl!PcwCreateInstance` at `0x1400d297b`
- `ntoskrnl!PcwCreateInstance` at `0x1400d2a63`
- `ntoskrnl!PcwCreateInstance` at `0x1400d297b`
- `ntoskrnl!PcwCreateInstance` at `0x1400d2a63`
- `watchdog!WdLogSingleEntry2` at `0x1400d2892`
- `watchdog!WdLogSingleEntry2` at `0x1400d2892`
- `watchdog!WdLogSingleEntry1` at `0x1400d28f8`
- `watchdog!WdLogSingleEntry1` at `0x1400d299d`
- `watchdog!WdLogSingleEntry1` at `0x1400d2a85`
- `watchdog!WdLogSingleEntry1` at `0x1400d28f8`
- `watchdog!WdLogSingleEntry1` at `0x1400d299d`
- `watchdog!WdLogSingleEntry1` at `0x1400d2a85`

## string_xrefs

- `0x1400d2a91`: `Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory, Status=0x%.8x`
- `0x1400d29a9`: `Failed to create CreateGpuPerformanceCounterSetAdapterMemory, Status=0x%.8x`

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
    WdLogGlobalForLineNumber = 1007;
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
    WdLogGlobalForLineNumber = 1036;
    v12 = 0x40000;
LABEL_5:
    DxgkLogInternalTriageEvent(v9, v12, v10, (_DWORD)v11, v8, 0, 0, 0);
    return (unsigned int)v8;
  }
  RtlInitUnicodeString(&DestinationString, pszDest);
  v23.Data = a1;
  v23.Size = 2656;
  v13 = PcwCreateInstance(
          (PPCW_INSTANCE *)a1 + 317,
          GpuPerformanceCounterSetAdapterMemory,
          &DestinationString,
          1u,
          &v23);
  v8 = v13;
  if ( v13 < 0 )
  {
    _InterlockedIncrement(&dword_14008785C);
    WdLogSingleEntry1(6, v13);
    v11 = L"Failed to create CreateGpuPerformanceCounterSetAdapterMemory, Status=0x%.8x";
    WdLogGlobalForLineNumber = 1047;
LABEL_8:
    v12 = 262145;
    goto LABEL_5;
  }
  v14 = *((_BYTE *)a1 + 1350);
  if ( (v14 & 6) == 6 )
  {
    v14 |= 0x80u;
    *((_BYTE *)a1 + 1350) = v14;
  }
  *((_BYTE *)a1 + 1424) |= 2u;
  if ( (v14 & 1) != 0 )
  {
    *((_DWORD *)a1 + 352) = dword_140087514;
    VIDMM_GLOBAL::InitializeSegmentGroupState(
      (VIDMM_GLOBAL *)v2,
      *((unsigned __int16 *)a1 + 36),
      (struct VIDMM_PHYSICAL_ADAPTER *)((char *)a1 + 1456),
      0);
    v15 = dword_140087518;
    *((_BYTE *)a1 + 1448) |= 3u;
    *((_DWORD *)a1 + 358) = v15;
    RtlInitUnicodeString(&DestinationString, pszDest);
    v23.Data = (char *)a1 + 1456;
    v23.Size = 344;
    v16 = PcwCreateInstance(
            (PPCW_INSTANCE *)a1 + 224,
            GpuPerformanceCounterSetLocalAdapterMemory,
            &DestinationString,
            1u,
            &v23);
    v8 = v16;
    if ( v16 < 0 )
    {
      _InterlockedIncrement(&dword_14008785C);
      WdLogSingleEntry1(6, v16);
      v11 = L"Failed to create CreateGpuPerformanceCounterSetLocalAdapterMemory, Status=0x%.8x";
      WdLogGlobalForLineNumber = 1088;
      goto LABEL_8;
    }
  }
  else
  {
    v17 = dword_140087518;
    *((_BYTE *)a1 + 1424) |= 1u;
    *((_BYTE *)a1 + 1448) &= ~2u;
    *((_DWORD *)a1 + 352) = v17;
  }
  v18 = *(_QWORD *)(v2 + 3256);
  if ( (*(_DWORD *)(*(_QWORD *)(v2 + 24) + 444LL) & 8) != 0 )
  {
    *(_BYTE *)(v2 + 3265) = v18 != 0;
    *((_BYTE *)a1 + 1348) |= 2u;
  }
  else
  {
    *(_BYTE *)(v2 + 3265) = v18 >= qword_1400872C0;
  }
  if ( (*(_BYTE *)(v2 + 37224) & 0x10) == 0 || (result = InitializeGpuVaState(a1), (int)result >= 0) )
  {
    if ( (*(_BYTE *)(*(_QWORD *)(v2 + 24) + 5172LL) & 1) != 0 )
    {
      for ( i = 0; i < 3; ++i )
      {
        for ( j = 0; j < 3; ++j )
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
0x1400d283c  mov     [rsp-8+arg_8], rbx
0x1400d2841  mov     [rsp-8+arg_10], rdi
0x1400d2846  push    rbp
0x1400d2847  push    r12
0x1400d2849  push    r13
0x1400d284b  push    r14
0x1400d284d  push    r15
0x1400d284f  lea     rbp, [rsp-37h]
0x1400d2854  sub     rsp, 0D0h
0x1400d285b  mov     rax, cs:__security_cookie
0x1400d2862  xor     rax, rsp
0x1400d2865  mov     [rbp+57h+var_30], rax
0x1400d2869  mov     rax, [rcx]
0x1400d286c  mov     rdi, rcx
0x1400d286f  mov     r14, [rcx+38h]
0x1400d2873  mov     rax, [rax+8]
0x1400d2877  call    _guard_dispatch_icall
0x1400d287c  xor     r12d, r12d
0x1400d287f  movsxd  rbx, eax
0x1400d2882  test    eax, eax
0x1400d2884  jns     short loc_1400D28AF
0x1400d2886  movzx   edx, word ptr [rdi+48h]
0x1400d288a  lea     ecx, [r12+3]
0x1400d288f  mov     r8, rbx
0x1400d2892  call    cs:__imp_WdLogSingleEntry2
0x1400d2899  nop     dword ptr [rax+rax+00h]
0x1400d289e  mov     eax, ebx
0x1400d28a0  mov     cs:WdLogGlobalForLineNumber, 3EFh
0x1400d28aa  jmp     loc_1400D2B71
0x1400d28af  mov     rax, [r14+18h]
0x1400d28b3  lea     r8, aLuid0x08x0x08x_0; "luid_0x%08X_0x%08X_phys_%u"
0x1400d28ba  movzx   ecx, word ptr [rdi+48h]
0x1400d28be  xorps   xmm0, xmm0
0x1400d28c1  mov     dword ptr [rsp+0F0h+var_C8], ecx
0x1400d28c5  mov     edx, 208h; cbDest
0x1400d28ca  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1400d28ce  mov     rax, [rax+19Ch]
0x1400d28d5  mov     r9, rax
0x1400d28d8  mov     dword ptr [rsp+0F0h+Data], eax
0x1400d28dc  shr     r9, 20h
0x1400d28e0  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400d28e4  call    RtlStringCbPrintfW
0x1400d28e9  movsxd  r15, eax
0x1400d28ec  test    eax, eax
0x1400d28ee  jns     short loc_1400D293B
0x1400d28f0  mov     rdx, r15
0x1400d28f3  mov     ecx, 1
0x1400d28f8  call    cs:__imp_WdLogSingleEntry1
0x1400d28ff  nop     dword ptr [rax+rax+00h]
0x1400d2904  lea     r9, aFailedToConstr; "Failed to construct perf counter name s"...
0x1400d290b  mov     cs:WdLogGlobalForLineNumber, 40Ch
0x1400d2915  mov     edx, 40000h
0x1400d291a  mov     [rsp+0F0h+var_B8], r12
0x1400d291f  mov     [rsp+0F0h+var_C0], r12
0x1400d2924  mov     [rsp+0F0h+var_C8], r12
0x1400d2929  mov     [rsp+0F0h+Data], r15
0x1400d292e  call    DxgkLogInternalTriageEvent
0x1400d2933  mov     eax, r15d
0x1400d2936  jmp     loc_1400D2B71
0x1400d293b  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400d293f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d2943  call    cs:__imp_RtlInitUnicodeString
0x1400d294a  nop     dword ptr [rax+rax+00h]
0x1400d294f  mov     rdx, cs:GpuPerformanceCounterSetAdapterMemory; Registration
0x1400d2956  lea     rax, [rbp+57h+var_A0]
0x1400d295a  lea     rcx, [rdi+9E8h]; Instance
0x1400d2961  mov     [rsp+0F0h+Data], rax; Data
0x1400d2966  mov     r9d, 1; Count
0x1400d296c  mov     [rbp+57h+var_A0.Data], rdi
0x1400d2970  lea     r8, [rbp+57h+DestinationString]; Name
0x1400d2974  mov     [rbp+57h+var_A0.Size], 0A60h
0x1400d297b  call    cs:__imp_PcwCreateInstance
0x1400d2982  nop     dword ptr [rax+rax+00h]
0x1400d2987  movsxd  r15, eax
0x1400d298a  test    eax, eax
0x1400d298c  jns     short loc_1400D29C4
0x1400d298e  lock inc cs:dword_14008785C
0x1400d2995  mov     rdx, r15
0x1400d2998  mov     ecx, 6
0x1400d299d  call    cs:__imp_WdLogSingleEntry1
0x1400d29a4  nop     dword ptr [rax+rax+00h]
0x1400d29a9  lea     r9, aFailedToCreate_10; "Failed to create CreateGpuPerformanceCo"...
0x1400d29b0  mov     cs:WdLogGlobalForLineNumber, 417h
0x1400d29ba  mov     edx, 40001h
0x1400d29bf  jmp     loc_1400D291A
0x1400d29c4  mov     cl, [rdi+546h]
0x1400d29ca  mov     al, cl
0x1400d29cc  and     al, 6
0x1400d29ce  cmp     al, 6
0x1400d29d0  jnz     short loc_1400D29DB
0x1400d29d2  or      cl, 80h
0x1400d29d5  mov     [rdi+546h], cl
0x1400d29db  or      byte ptr [rdi+590h], 2
0x1400d29e2  test    cl, 1
0x1400d29e5  jz      loc_1400D2AA7
0x1400d29eb  mov     eax, cs:dword_140087514
0x1400d29f1  lea     rbx, [rdi+5B0h]
0x1400d29f8  mov     [rdi+580h], eax
0x1400d29fe  mov     r8, rbx; struct VIDMM_SEGMENT_GROUP_STATE *
0x1400d2a01  movzx   edx, word ptr [rdi+48h]; unsigned int
0x1400d2a05  xor     r9d, r9d; unsigned __int64
0x1400d2a08  mov     rcx, r14; this
0x1400d2a0b  call    ?InitializeSegmentGroupState@VIDMM_GLOBAL@@QEAAXIPEAUVIDMM_SEGMENT_GROUP_STATE@@_K@Z; VIDMM_GLOBAL::InitializeSegmentGroupState(uint,VIDMM_SEGMENT_GROUP_STATE *,unsigned __int64)
0x1400d2a10  mov     eax, cs:dword_140087518
0x1400d2a16  lea     rdx, [rbp+57h+pszDest]; SourceString
0x1400d2a1a  or      byte ptr [rdi+5A8h], 3
0x1400d2a21  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400d2a25  mov     [rdi+598h], eax
0x1400d2a2b  call    cs:__imp_RtlInitUnicodeString
0x1400d2a32  nop     dword ptr [rax+rax+00h]
0x1400d2a37  mov     rdx, cs:GpuPerformanceCounterSetLocalAdapterMemory; Registration
0x1400d2a3e  lea     rax, [rbp+57h+var_A0]
0x1400d2a42  lea     rcx, [rbx+150h]; Instance
0x1400d2a49  mov     [rsp+0F0h+Data], rax; Data
0x1400d2a4e  mov     r9d, 1; Count
0x1400d2a54  mov     [rbp+57h+var_A0.Data], rbx
0x1400d2a58  lea     r8, [rbp+57h+DestinationString]; Name
0x1400d2a5c  mov     [rbp+57h+var_A0.Size], 158h
0x1400d2a63  call    cs:__imp_PcwCreateInstance
0x1400d2a6a  nop     dword ptr [rax+rax+00h]
0x1400d2a6f  movsxd  r15, eax
0x1400d2a72  test    eax, eax
0x1400d2a74  jns     short loc_1400D2AC1
0x1400d2a76  lock inc cs:dword_14008785C
0x1400d2a7d  mov     rdx, r15
0x1400d2a80  mov     ecx, 6
0x1400d2a85  call    cs:__imp_WdLogSingleEntry1
0x1400d2a8c  nop     dword ptr [rax+rax+00h]
0x1400d2a91  lea     r9, aFailedToCreate_3; "Failed to create CreateGpuPerformanceCo"...
0x1400d2a98  mov     cs:WdLogGlobalForLineNumber, 440h
0x1400d2aa2  jmp     loc_1400D29BA
0x1400d2aa7  mov     eax, cs:dword_140087518
0x1400d2aad  or      byte ptr [rdi+590h], 1
0x1400d2ab4  and     byte ptr [rdi+5A8h], 0FDh
0x1400d2abb  mov     [rdi+580h], eax
0x1400d2ac1  mov     rax, [r14+18h]
0x1400d2ac5  mov     rdx, [r14+0CB8h]
0x1400d2acc  mov     ecx, [rax+1BCh]
0x1400d2ad2  test    cl, 8
0x1400d2ad5  jz      short loc_1400D2AED
0x1400d2ad7  test    rdx, rdx
0x1400d2ada  setnz   al
0x1400d2add  mov     [r14+0CC1h], al
0x1400d2ae4  or      byte ptr [rdi+544h], 2
0x1400d2aeb  jmp     short loc_1400D2AFE
0x1400d2aed  cmp     rdx, cs:qword_1400872C0
0x1400d2af4  setnb   al
0x1400d2af7  mov     [r14+0CC1h], al
0x1400d2afe  test    byte ptr [r14+9168h], 10h
0x1400d2b06  jz      short loc_1400D2B14
0x1400d2b08  mov     rcx, rdi; struct VIDMM_PHYSICAL_ADAPTER *
0x1400d2b0b  call    InitializeGpuVaState
0x1400d2b10  test    eax, eax
0x1400d2b12  js      short loc_1400D2B71
0x1400d2b14  mov     rax, [r14+18h]
0x1400d2b18  test    byte ptr [rax+1434h], 1
0x1400d2b1f  jz      short loc_1400D2B6F
0x1400d2b21  mov     ebx, r12d
0x1400d2b24  lea     r13, [rdi+88h]
0x1400d2b2b  mov     r15d, r12d
0x1400d2b2e  mov     r12d, ebx
0x1400d2b31  movzx   r9d, word ptr [rdi+48h]
0x1400d2b36  mov     r8d, r15d
0x1400d2b39  mov     ecx, r15d
0x1400d2b3c  mov     edx, ebx
0x1400d2b3e  lea     rax, [r12+rcx*2]
0x1400d2b42  add     rcx, rax
0x1400d2b45  imul    rax, rcx, 58h ; 'X'
0x1400d2b49  mov     rcx, r14; this
0x1400d2b4c  add     rax, r13
0x1400d2b4f  mov     [rsp+0F0h+Data], rax; __int64
0x1400d2b54  call    GetFenceStorageAllocInfo_0
0x1400d2b59  inc     r15d
0x1400d2b5c  cmp     r15d, 3
0x1400d2b60  jb      short loc_1400D2B31
0x1400d2b62  inc     ebx
0x1400d2b64  mov     r12d, 0
0x1400d2b6a  cmp     ebx, 3
0x1400d2b6d  jb      short loc_1400D2B2B
0x1400d2b6f  xor     eax, eax
0x1400d2b71  mov     rcx, [rbp+57h+var_30]
0x1400d2b75  xor     rcx, rsp; StackCookie
0x1400d2b78  call    __security_check_cookie
0x1400d2b7d  lea     r11, [rsp+0F0h+var_20]
0x1400d2b85  mov     rbx, [r11+38h]
0x1400d2b89  mov     rdi, [r11+40h]
0x1400d2b8d  mov     rsp, r11
0x1400d2b90  pop     r15
0x1400d2b92  pop     r14
0x1400d2b94  pop     r13
0x1400d2b96  pop     r12
0x1400d2b98  pop     rbp
0x1400d2b99  retn
```
