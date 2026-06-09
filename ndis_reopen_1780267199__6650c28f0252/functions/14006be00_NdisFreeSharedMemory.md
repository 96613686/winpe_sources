# NdisFreeSharedMemory

- ea: `0x14006be00`
- end: `0x14006c0d3`
- name: `NdisFreeSharedMemory`
- size: `723`
- prototype: `void __stdcall(NDIS_HANDLE NdisHandle, NDIS_HANDLE AllocationHandle)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400110b0`
- `0x14001dbb0`
- `0x14001ddf0`
- `0x14002ab60`
- `0x14006be00`
- `0x14006c0e0`
- `0x14006c250`
- `0x1400eb380`
- `0x1400eb460`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14006bfc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006bfc4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006bfb3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14006bfb3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006bf40`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14006bf40`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x14006bf22`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x14006bf22`
- `HAL!KeQueryPerformanceCounter` at `0x14006be63`
- `HAL!KeQueryPerformanceCounter` at `0x14006be63`

## pseudocode

```c
void __stdcall NdisFreeSharedMemory(NDIS_HANDLE NdisHandle, NDIS_HANDLE AllocationHandle)
{
  struct _NDIS_SHARED_MEMORY_BLOCK *v2; // rbx
  int v4; // edx
  char v5; // al
  NDIS_HANDLE v6; // rsi
  unsigned int Flags; // ecx
  KIRQL v8; // r9
  _LIST_ENTRY *Flink; // rdx
  NDIS_HANDLE *p_Flink; // rcx
  _LIST_ENTRY *v11; // rdx
  NDIS_HANDLE *v12; // r8
  struct _NDIS_SG_DMA_BLOCK *v13; // rbp
  _DMA_ADAPTER *DmaAdapterObject; // rcx
  struct _NDIS_SHARED_MEMORY_BLOCK **v15; // rcx
  NDIS_HANDLE *v16; // rdx
  int v17; // [rsp+20h] [rbp-128h]
  char v18; // [rsp+28h] [rbp-120h]
  int v19; // [rsp+30h] [rbp-118h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+38h] [rbp-110h]
  _BYTE v21[208]; // [rsp+40h] [rbp-108h] BYREF

  v2 = (struct _NDIS_SHARED_MEMORY_BLOCK *)AllocationHandle;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v18 = (char)AllocationHandle;
    LOBYTE(AllocationHandle) = 4;
    WPP_RECORDER_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)AllocationHandle,
      21,
      71,
      (struct _GUID *)&WPP_2779bc3468263007f5ef77c40b63ca16_Traceguids,
      v18);
  }
  _InterlockedIncrement64(&qword_140122EB8);
  v19 = 6;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  NdisFreeSharedMemoryTelemetry::NdisFreeSharedMemoryTelemetry((NdisFreeSharedMemoryTelemetry *)v21, v2);
  if ( NdisHandle )
  {
    v5 = *(_BYTE *)NdisHandle;
    if ( *(_BYTE *)NdisHandle == 18 )
    {
      v6 = NdisHandle;
      NdisHandle = (NDIS_HANDLE)*((_QWORD *)NdisHandle + 2);
    }
    else
    {
      v6 = 0;
      if ( v5 != 17 )
      {
        if ( v5 != 1 )
          goto LABEL_4;
        NdisHandle = 0;
      }
    }
    if ( v2 && NdisHandle )
    {
      Flags = v2->Flags;
      if ( (Flags & 0x3F) == 1 )
      {
        v13 = (struct _NDIS_SG_DMA_BLOCK *)*((_QWORD *)NdisHandle + 63);
        if ( v13 )
        {
          DmaAdapterObject = v13->DmaAdapterObject;
          if ( DmaAdapterObject )
          {
            LOBYTE(v17) = 1;
            ((void (__fastcall *)(_DMA_ADAPTER *, _QWORD, _QWORD, _QWORD, _DWORD))DmaAdapterObject->DmaOperations->FreeCommonBuffer)(
              DmaAdapterObject,
              v2->SharedMemoryParameters.Length,
              (_LARGE_INTEGER)v2->PhysicalAddress.QuadPart,
              v2->SharedMemoryParameters.VirtualAddress,
              v17);
            ndisDereferenceDmaAdapter(v13);
            goto LABEL_14;
          }
        }
      }
      else
      {
        if ( (Flags & 0x3F) == 2 )
        {
          MmFreeContiguousMemorySpecifyCache(
            v2->SharedMemoryParameters.VirtualAddress,
            v2->SharedMemoryParameters.Length,
            MmCached);
LABEL_14:
          _InterlockedAdd64(&qword_140122EC8, v2->SharedMemoryParameters.Length);
          v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)NdisHandle + 12);
          *((_QWORD *)NdisHandle + 65) = KeGetCurrentThread();
          Flink = v2->MiniportLink.Flink;
          if ( (struct _NDIS_SHARED_MEMORY_BLOCK *)v2->MiniportLink.Flink->Blink == v2 )
          {
            p_Flink = (NDIS_HANDLE *)&v2->MiniportLink.Blink->Flink;
            if ( *p_Flink == v2 )
            {
              *p_Flink = Flink;
              Flink->Blink = (_LIST_ENTRY *)p_Flink;
              if ( v6 )
              {
                v15 = (struct _NDIS_SHARED_MEMORY_BLOCK **)v2->OpenLink.Flink;
                if ( v15[1] != (struct _NDIS_SHARED_MEMORY_BLOCK *)&v2->OpenLink )
                  goto LABEL_20;
                v16 = (NDIS_HANDLE *)&v2->OpenLink.Blink->Flink;
                if ( *v16 != &v2->OpenLink )
                  goto LABEL_20;
                *v16 = v15;
                v15[1] = (struct _NDIS_SHARED_MEMORY_BLOCK *)v16;
              }
              v11 = v2->QueueLink.Flink;
              if ( v11->Blink == &v2->QueueLink )
              {
                v12 = (NDIS_HANDLE *)&v2->QueueLink.Blink->Flink;
                if ( *v12 == &v2->QueueLink )
                {
                  *v12 = v11;
                  v11->Blink = (_LIST_ENTRY *)v12;
                  *((_QWORD *)NdisHandle + 65) = 0;
                  KeReleaseSpinLock((PKSPIN_LOCK)NdisHandle + 12, v8);
                  ExFreePoolWithTag(v2, 0);
                  goto LABEL_4;
                }
              }
            }
          }
LABEL_20:
          __fastfail(3u);
        }
        if ( (Flags & 4) != 0 )
        {
          if ( v6 )
            goto LABEL_14;
LABEL_34:
          v2->FreeSharedMemoryHandler(v2->SharedMemoryHandlerContext, v2->ProviderAllocationContext);
          goto LABEL_14;
        }
        if ( (Flags & 8) != 0 )
          goto LABEL_34;
      }
    }
  }
LABEL_4:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v4) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v4,
      21,
      72,
      (struct _GUID *)&WPP_2779bc3468263007f5ef77c40b63ca16_Traceguids);
  }
  NdisFreeSharedMemoryTelemetry::~NdisFreeSharedMemoryTelemetry((NdisFreeSharedMemoryTelemetry *)v21);
  NdisStatisticalStopwatch::~NdisStatisticalStopwatch((NdisStatisticalStopwatch *)&v19);
}

```

## disassembly

```asm
0x14006be00  push    rbx
0x14006be02  push    rdi
0x14006be03  push    r14
0x14006be05  push    r15
0x14006be07  sub     rsp, 128h
0x14006be0e  mov     rax, cs:__security_cookie
0x14006be15  xor     rax, rsp
0x14006be18  mov     [rsp+148h+var_38], rax
0x14006be20  mov     rbx, rdx
0x14006be23  mov     rdi, rcx
0x14006be26  lea     r14, WPP_RECORDER_INITIALIZED
0x14006be2d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006be34  lea     r15, WPP_2779bc3468263007f5ef77c40b63ca16_Traceguids
0x14006be3b  jnz     loc_14006C04C
0x14006be41  mov     [rsp+148h+arg_10], rbp
0x14006be49  mov     [rsp+148h+var_28], rsi
0x14006be51  lock inc cs:qword_140122EB8
0x14006be59  xor     ecx, ecx; PerformanceFrequency
0x14006be5b  mov     [rsp+148h+var_118], 6
0x14006be63  call    cs:__imp_KeQueryPerformanceCounter
0x14006be6a  nop     dword ptr [rax+rax+00h]
0x14006be6f  mov     rdx, rbx; struct _NDIS_SHARED_MEMORY_BLOCK *
0x14006be72  lea     rcx, [rsp+148h+var_108]; this
0x14006be77  mov     [rsp+148h+var_110], rax
0x14006be7c  call    ??0NdisFreeSharedMemoryTelemetry@@QEAA@PEBU_NDIS_SHARED_MEMORY_BLOCK@@@Z; NdisFreeSharedMemoryTelemetry::NdisFreeSharedMemoryTelemetry(_NDIS_SHARED_MEMORY_BLOCK const *)
0x14006be81  test    rdi, rdi
0x14006be84  jnz     short loc_14006BED6
0x14006be86  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14006be8d  jnz     loc_14006C0AB
0x14006be93  lea     rcx, [rsp+148h+var_108]; this
0x14006be98  call    ??1NdisFreeSharedMemoryTelemetry@@QEAA@XZ; NdisFreeSharedMemoryTelemetry::~NdisFreeSharedMemoryTelemetry(void)
0x14006be9d  lea     rcx, [rsp+148h+var_118]; this
0x14006bea2  call    ??1NdisStatisticalStopwatch@@QEAA@XZ; NdisStatisticalStopwatch::~NdisStatisticalStopwatch(void)
0x14006bea7  mov     rsi, [rsp+148h+var_28]
0x14006beaf  mov     rbp, [rsp+148h+arg_10]
0x14006beb7  mov     rcx, [rsp+148h+var_38]
0x14006bebf  xor     rcx, rsp; StackCookie
0x14006bec2  call    __security_check_cookie
0x14006bec7  add     rsp, 128h
0x14006bece  pop     r15
0x14006bed0  pop     r14
0x14006bed2  pop     rdi
0x14006bed3  pop     rbx
0x14006bed4  retn
0x14006bed6  movzx   eax, byte ptr [rdi]
0x14006bed9  cmp     al, 12h
0x14006bedb  jz      loc_14006C079
0x14006bee1  xor     esi, esi
0x14006bee3  cmp     al, 11h
0x14006bee5  jnz     loc_14006C085
0x14006beeb  test    rbx, rbx
0x14006beee  jz      short loc_14006BE86
0x14006bef0  test    rdi, rdi
0x14006bef3  jz      short loc_14006BE86
0x14006bef5  mov     ecx, [rbx+30h]
0x14006bef8  mov     eax, ecx
0x14006befa  and     eax, 3Fh
0x14006befd  cmp     eax, 1
0x14006bf00  jz      loc_14006BFDC
0x14006bf06  cmp     eax, 2
0x14006bf09  jnz     loc_14006C094
0x14006bf0f  mov     edx, [rbx+90h]; NumberOfBytes
0x14006bf15  mov     r8d, 1; CacheType
0x14006bf1b  mov     rcx, [rbx+98h]; BaseAddress
0x14006bf22  call    cs:__imp_MmFreeContiguousMemorySpecifyCache
0x14006bf29  nop     dword ptr [rax+rax+00h]
0x14006bf2e  mov     eax, [rbx+90h]
0x14006bf34  lock add cs:qword_140122EC8, rax
0x14006bf3c  lea     rcx, [rdi+60h]; SpinLock
0x14006bf40  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14006bf47  nop     dword ptr [rax+rax+00h]
0x14006bf4c  mov     rcx, gs:188h
0x14006bf55  movzx   r9d, al
0x14006bf59  mov     [rdi+208h], rcx
0x14006bf60  mov     rdx, [rbx]
0x14006bf63  cmp     [rdx+8], rbx
0x14006bf67  jnz     short loc_14006BFD5
0x14006bf69  mov     rcx, [rbx+8]
0x14006bf6d  cmp     [rcx], rbx
0x14006bf70  jnz     short loc_14006BFD5
0x14006bf72  mov     [rcx], rdx
0x14006bf75  mov     [rdx+8], rcx
0x14006bf79  test    rsi, rsi
0x14006bf7c  jnz     loc_14006C029
0x14006bf82  mov     rdx, [rbx+20h]
0x14006bf86  lea     rax, [rbx+20h]
0x14006bf8a  cmp     [rdx+8], rax
0x14006bf8e  jnz     short loc_14006BFD5
0x14006bf90  mov     r8, [rax+8]
0x14006bf94  cmp     [r8], rax
0x14006bf97  jnz     short loc_14006BFD5
0x14006bf99  mov     [r8], rdx
0x14006bf9c  lea     rcx, [rdi+60h]; SpinLock
0x14006bfa0  mov     [rdx+8], r8
0x14006bfa4  movzx   edx, r9b; NewIrql
0x14006bfa8  mov     qword ptr [rdi+208h], 0
0x14006bfb3  call    cs:__imp_KeReleaseSpinLock
0x14006bfba  nop     dword ptr [rax+rax+00h]
0x14006bfbf  xor     edx, edx; Tag
0x14006bfc1  mov     rcx, rbx; P
0x14006bfc4  call    cs:__imp_ExFreePoolWithTag
0x14006bfcb  nop     dword ptr [rax+rax+00h]
0x14006bfd0  jmp     loc_14006BE86
0x14006bfd5  mov     ecx, 3
0x14006bfda  int     29h; Win8: RtlFailFast(ecx)
0x14006bfdc  mov     rbp, [rdi+1F8h]
0x14006bfe3  test    rbp, rbp
0x14006bfe6  jz      loc_14006BE86
0x14006bfec  mov     rcx, [rbp+28h]
0x14006bff0  test    rcx, rcx
0x14006bff3  jz      loc_14006BE86
0x14006bff9  mov     rax, [rcx+8]
0x14006bffd  mov     r9, [rbx+98h]
0x14006c004  mov     r8, [rbx+68h]
0x14006c008  mov     edx, [rbx+90h]
0x14006c00e  mov     rax, [rax+18h]
0x14006c012  mov     byte ptr [rsp+148h+var_128], 1
0x14006c017  call    _guard_dispatch_icall
0x14006c01c  mov     rcx, rbp; struct _NDIS_SG_DMA_BLOCK *
0x14006c01f  call    ?ndisDereferenceDmaAdapter@@YAXPEAU_NDIS_SG_DMA_BLOCK@@@Z; ndisDereferenceDmaAdapter(_NDIS_SG_DMA_BLOCK *)
0x14006c024  jmp     loc_14006BF2E
0x14006c029  mov     rcx, [rbx+10h]
0x14006c02d  lea     rax, [rbx+10h]
0x14006c031  cmp     [rcx+8], rax
0x14006c035  jnz     short loc_14006BFD5
0x14006c037  mov     rdx, [rax+8]
0x14006c03b  cmp     [rdx], rax
0x14006c03e  jnz     short loc_14006BFD5
0x14006c040  mov     [rdx], rcx
0x14006c043  mov     [rcx+8], rdx
0x14006c047  jmp     loc_14006BF82
0x14006c04c  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c053  mov     r9d, 47h ; 'G'; int
0x14006c059  mov     qword ptr [rsp+148h+var_120], rbx; char
0x14006c05e  mov     r8d, 15h; int
0x14006c064  mov     dl, 4; int
0x14006c066  mov     [rsp+148h+var_128], r15; struct _GUID *
0x14006c06b  mov     rcx, [rcx+40h]; int
0x14006c06f  call    WPP_RECORDER_SF_q
0x14006c074  jmp     loc_14006BE41
0x14006c079  mov     rsi, rdi
0x14006c07c  mov     rdi, [rdi+10h]
0x14006c080  jmp     loc_14006BEEB
0x14006c085  cmp     al, 1
0x14006c087  jnz     loc_14006BE86
0x14006c08d  xor     edi, edi
0x14006c08f  jmp     loc_14006BEEB
0x14006c094  test    cl, 4
0x14006c097  jz      loc_1400F333A
0x14006c09d  test    rsi, rsi
0x14006c0a0  jnz     loc_14006BF2E
0x14006c0a6  jmp     loc_1400F3343
0x14006c0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14006c0b2  mov     r9d, 48h ; 'H'; int
0x14006c0b8  mov     r8d, 15h; int
0x14006c0be  mov     [rsp+148h+var_128], r15; struct _GUID *
0x14006c0c3  mov     dl, 4; int
0x14006c0c5  mov     rcx, [rcx+40h]; int
0x14006c0c9  call    WPP_RECORDER_SF_
0x14006c0ce  jmp     loc_14006BE93
0x1400f333a  test    cl, 8
0x1400f333d  jz      loc_14006BE86
0x1400f3343  mov     rdx, [rbx+60h]
0x1400f3347  mov     rcx, [rbx+58h]
0x1400f334b  mov     rax, [rbx+50h]
0x1400f334f  call    _guard_dispatch_icall
0x1400f3354  nop
0x1400f3355  jmp     loc_14006BF2E
```
