# NdisFreeSharedMemory

- ea: `0x140065e70`
- end: `0x140066143`
- name: `NdisFreeSharedMemory`
- size: `723`
- prototype: `void __stdcall(NDIS_HANDLE NdisHandle, NDIS_HANDLE AllocationHandle)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14001cf50`
- `0x140029620`
- `0x140029b00`
- `0x140029d40`
- `0x140065e70`
- `0x140066150`
- `0x1400662c0`
- `0x1400e6160`
- `0x1400e6240`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140066034`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066034`
- `ntoskrnl!KeReleaseSpinLock` at `0x140066023`
- `ntoskrnl!KeReleaseSpinLock` at `0x140066023`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065fb0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140065fb0`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x140065f92`
- `ntoskrnl!MmFreeContiguousMemorySpecifyCache` at `0x140065f92`
- `HAL!KeQueryPerformanceCounter` at `0x140065ed3`
- `HAL!KeQueryPerformanceCounter` at `0x140065ed3`

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
  _InterlockedIncrement64(&qword_14011CEB8);
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
          _InterlockedAdd64(&qword_14011CEC8, v2->SharedMemoryParameters.Length);
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
0x140065e70  push    rbx
0x140065e72  push    rdi
0x140065e73  push    r14
0x140065e75  push    r15
0x140065e77  sub     rsp, 128h
0x140065e7e  mov     rax, cs:__security_cookie
0x140065e85  xor     rax, rsp
0x140065e88  mov     [rsp+148h+var_38], rax
0x140065e90  mov     rbx, rdx
0x140065e93  mov     rdi, rcx
0x140065e96  lea     r14, WPP_RECORDER_INITIALIZED
0x140065e9d  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140065ea4  lea     r15, WPP_2779bc3468263007f5ef77c40b63ca16_Traceguids
0x140065eab  jnz     loc_1400660BC
0x140065eb1  mov     [rsp+148h+arg_10], rbp
0x140065eb9  mov     [rsp+148h+var_28], rsi
0x140065ec1  lock inc cs:qword_14011CEB8
0x140065ec9  xor     ecx, ecx; PerformanceFrequency
0x140065ecb  mov     [rsp+148h+var_118], 6
0x140065ed3  call    cs:__imp_KeQueryPerformanceCounter
0x140065eda  nop     dword ptr [rax+rax+00h]
0x140065edf  mov     rdx, rbx; struct _NDIS_SHARED_MEMORY_BLOCK *
0x140065ee2  lea     rcx, [rsp+148h+var_108]; this
0x140065ee7  mov     [rsp+148h+var_110], rax
0x140065eec  call    ??0NdisFreeSharedMemoryTelemetry@@QEAA@PEBU_NDIS_SHARED_MEMORY_BLOCK@@@Z; NdisFreeSharedMemoryTelemetry::NdisFreeSharedMemoryTelemetry(_NDIS_SHARED_MEMORY_BLOCK const *)
0x140065ef1  test    rdi, rdi
0x140065ef4  jnz     short loc_140065F46
0x140065ef6  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140065efd  jnz     loc_14006611B
0x140065f03  lea     rcx, [rsp+148h+var_108]; this
0x140065f08  call    ??1NdisFreeSharedMemoryTelemetry@@QEAA@XZ; NdisFreeSharedMemoryTelemetry::~NdisFreeSharedMemoryTelemetry(void)
0x140065f0d  lea     rcx, [rsp+148h+var_118]; this
0x140065f12  call    ??1NdisStatisticalStopwatch@@QEAA@XZ; NdisStatisticalStopwatch::~NdisStatisticalStopwatch(void)
0x140065f17  mov     rsi, [rsp+148h+var_28]
0x140065f1f  mov     rbp, [rsp+148h+arg_10]
0x140065f27  mov     rcx, [rsp+148h+var_38]
0x140065f2f  xor     rcx, rsp; StackCookie
0x140065f32  call    __security_check_cookie
0x140065f37  add     rsp, 128h
0x140065f3e  pop     r15
0x140065f40  pop     r14
0x140065f42  pop     rdi
0x140065f43  pop     rbx
0x140065f44  retn
0x140065f46  movzx   eax, byte ptr [rdi]
0x140065f49  cmp     al, 12h
0x140065f4b  jz      loc_1400660E9
0x140065f51  xor     esi, esi
0x140065f53  cmp     al, 11h
0x140065f55  jnz     loc_1400660F5
0x140065f5b  test    rbx, rbx
0x140065f5e  jz      short loc_140065EF6
0x140065f60  test    rdi, rdi
0x140065f63  jz      short loc_140065EF6
0x140065f65  mov     ecx, [rbx+30h]
0x140065f68  mov     eax, ecx
0x140065f6a  and     eax, 3Fh
0x140065f6d  cmp     eax, 1
0x140065f70  jz      loc_14006604C
0x140065f76  cmp     eax, 2
0x140065f79  jnz     loc_140066104
0x140065f7f  mov     edx, [rbx+90h]; NumberOfBytes
0x140065f85  mov     r8d, 1; CacheType
0x140065f8b  mov     rcx, [rbx+98h]; BaseAddress
0x140065f92  call    cs:__imp_MmFreeContiguousMemorySpecifyCache
0x140065f99  nop     dword ptr [rax+rax+00h]
0x140065f9e  mov     eax, [rbx+90h]
0x140065fa4  lock add cs:qword_14011CEC8, rax
0x140065fac  lea     rcx, [rdi+60h]; SpinLock
0x140065fb0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140065fb7  nop     dword ptr [rax+rax+00h]
0x140065fbc  mov     rcx, gs:188h
0x140065fc5  movzx   r9d, al
0x140065fc9  mov     [rdi+208h], rcx
0x140065fd0  mov     rdx, [rbx]
0x140065fd3  cmp     [rdx+8], rbx
0x140065fd7  jnz     short loc_140066045
0x140065fd9  mov     rcx, [rbx+8]
0x140065fdd  cmp     [rcx], rbx
0x140065fe0  jnz     short loc_140066045
0x140065fe2  mov     [rcx], rdx
0x140065fe5  mov     [rdx+8], rcx
0x140065fe9  test    rsi, rsi
0x140065fec  jnz     loc_140066099
0x140065ff2  mov     rdx, [rbx+20h]
0x140065ff6  lea     rax, [rbx+20h]
0x140065ffa  cmp     [rdx+8], rax
0x140065ffe  jnz     short loc_140066045
0x140066000  mov     r8, [rax+8]
0x140066004  cmp     [r8], rax
0x140066007  jnz     short loc_140066045
0x140066009  mov     [r8], rdx
0x14006600c  lea     rcx, [rdi+60h]; SpinLock
0x140066010  mov     [rdx+8], r8
0x140066014  movzx   edx, r9b; NewIrql
0x140066018  mov     qword ptr [rdi+208h], 0
0x140066023  call    cs:__imp_KeReleaseSpinLock
0x14006602a  nop     dword ptr [rax+rax+00h]
0x14006602f  xor     edx, edx; Tag
0x140066031  mov     rcx, rbx; P
0x140066034  call    cs:__imp_ExFreePoolWithTag
0x14006603b  nop     dword ptr [rax+rax+00h]
0x140066040  jmp     loc_140065EF6
0x140066045  mov     ecx, 3
0x14006604a  int     29h; Win8: RtlFailFast(ecx)
0x14006604c  mov     rbp, [rdi+1F8h]
0x140066053  test    rbp, rbp
0x140066056  jz      loc_140065EF6
0x14006605c  mov     rcx, [rbp+28h]
0x140066060  test    rcx, rcx
0x140066063  jz      loc_140065EF6
0x140066069  mov     rax, [rcx+8]
0x14006606d  mov     r9, [rbx+98h]
0x140066074  mov     r8, [rbx+68h]
0x140066078  mov     edx, [rbx+90h]
0x14006607e  mov     rax, [rax+18h]
0x140066082  mov     byte ptr [rsp+148h+var_128], 1
0x140066087  call    _guard_dispatch_icall
0x14006608c  mov     rcx, rbp; struct _NDIS_SG_DMA_BLOCK *
0x14006608f  call    ?ndisDereferenceDmaAdapter@@YAXPEAU_NDIS_SG_DMA_BLOCK@@@Z; ndisDereferenceDmaAdapter(_NDIS_SG_DMA_BLOCK *)
0x140066094  jmp     loc_140065F9E
0x140066099  mov     rcx, [rbx+10h]
0x14006609d  lea     rax, [rbx+10h]
0x1400660a1  cmp     [rcx+8], rax
0x1400660a5  jnz     short loc_140066045
0x1400660a7  mov     rdx, [rax+8]
0x1400660ab  cmp     [rdx], rax
0x1400660ae  jnz     short loc_140066045
0x1400660b0  mov     [rdx], rcx
0x1400660b3  mov     [rcx+8], rdx
0x1400660b7  jmp     loc_140065FF2
0x1400660bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400660c3  mov     r9d, 47h ; 'G'; int
0x1400660c9  mov     qword ptr [rsp+148h+var_120], rbx; char
0x1400660ce  mov     r8d, 15h; int
0x1400660d4  mov     dl, 4; int
0x1400660d6  mov     [rsp+148h+var_128], r15; struct _GUID *
0x1400660db  mov     rcx, [rcx+40h]; int
0x1400660df  call    WPP_RECORDER_SF_q
0x1400660e4  jmp     loc_140065EB1
0x1400660e9  mov     rsi, rdi
0x1400660ec  mov     rdi, [rdi+10h]
0x1400660f0  jmp     loc_140065F5B
0x1400660f5  cmp     al, 1
0x1400660f7  jnz     loc_140065EF6
0x1400660fd  xor     edi, edi
0x1400660ff  jmp     loc_140065F5B
0x140066104  test    cl, 4
0x140066107  jz      loc_1400EDE02
0x14006610d  test    rsi, rsi
0x140066110  jnz     loc_140065F9E
0x140066116  jmp     loc_1400EDE0B
0x14006611b  mov     rcx, cs:WPP_GLOBAL_Control
0x140066122  mov     r9d, 48h ; 'H'; int
0x140066128  mov     r8d, 15h; int
0x14006612e  mov     [rsp+148h+var_128], r15; struct _GUID *
0x140066133  mov     dl, 4; int
0x140066135  mov     rcx, [rcx+40h]; int
0x140066139  call    WPP_RECORDER_SF_
0x14006613e  jmp     loc_140065F03
0x1400ede02  test    cl, 8
0x1400ede05  jz      loc_140065EF6
0x1400ede0b  mov     rdx, [rbx+60h]
0x1400ede0f  mov     rcx, [rbx+58h]
0x1400ede13  mov     rax, [rbx+50h]
0x1400ede17  call    _guard_dispatch_icall
0x1400ede1c  nop
0x1400ede1d  jmp     loc_140065F9E
```
