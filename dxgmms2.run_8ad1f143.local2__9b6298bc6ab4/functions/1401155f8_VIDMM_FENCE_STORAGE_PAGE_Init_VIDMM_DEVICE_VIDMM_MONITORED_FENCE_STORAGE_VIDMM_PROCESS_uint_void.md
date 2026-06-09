# VIDMM_FENCE_STORAGE_PAGE::Init(VIDMM_DEVICE *,VIDMM_MONITORED_FENCE_STORAGE *,VIDMM_PROCESS *,uint,void *)

- ea: `0x1401155f8`
- end: `0x1401159a8`
- name: `?Init@VIDMM_FENCE_STORAGE_PAGE@@QEAAJPEAVVIDMM_DEVICE@@PEAUVIDMM_MONITORED_FENCE_STORAGE@@PEAVVIDMM_PROCESS@@IPEAX@Z`
- size: `944`
- prototype: `__int64 __fastcall(VIDMM_FENCE_STORAGE_PAGE *this, struct VIDMM_DEVICE *, struct VIDMM_MONITORED_FENCE_STORAGE *, struct VIDMM_PROCESS *, unsigned int, __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14000288c`
- `0x140002ba8`

## callees

- `0x1400045ec`
- `0x14002ec00`
- `0x14002ed1c`
- `0x1400c1738`
- `0x1400edb04`
- `0x1400f7684`
- `0x1401155f8`
- `0x1401159b0`
- `0x140115a58`

## import_xrefs

- `ntoskrnl!MmProbeAndLockPages` at `0x14011579a`
- `ntoskrnl!MmProbeAndLockPages` at `0x14011579a`
- `ntoskrnl!MmCreateSection` at `0x140115681`
- `ntoskrnl!MmCreateSection` at `0x140115681`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x1401156c7`
- `ntoskrnl!MmMapViewInSystemSpaceEx` at `0x1401156c7`
- `watchdog!WdLogSingleEntry0` at `0x14011574b`
- `watchdog!WdLogSingleEntry0` at `0x140115802`
- `watchdog!WdLogSingleEntry0` at `0x14011585b`
- `watchdog!WdLogSingleEntry0` at `0x14011574b`
- `watchdog!WdLogSingleEntry0` at `0x140115802`
- `watchdog!WdLogSingleEntry0` at `0x14011585b`
- `watchdog!WdLogSingleEntry1` at `0x1401156e9`
- `watchdog!WdLogSingleEntry1` at `0x140115931`
- `watchdog!WdLogSingleEntry1` at `0x1401156e9`
- `watchdog!WdLogSingleEntry1` at `0x140115931`

## pseudocode

```c
__int64 __fastcall VIDMM_FENCE_STORAGE_PAGE::Init(
        VIDMM_FENCE_STORAGE_PAGE *this,
        struct VIDMM_DEVICE *a2,
        struct VIDMM_MONITORED_FENCE_STORAGE *a3,
        struct VIDMM_PROCESS *a4,
        unsigned int a5,
        __int64 a6)
{
  int v10; // esi
  void *CurrentPartitionHandle; // rax
  _QWORD *v12; // rbx
  __int64 v13; // rsi
  PVOID *v14; // r15
  int v15; // eax
  int v16; // ecx
  int v17; // r8d
  struct _MDL *Mdl; // rax
  int v19; // ecx
  int v20; // r8d
  __int64 v21; // rax
  VIDMM_PROCESS *VmwpProcess; // rcx
  int v23; // ecx
  int v24; // r8d
  __int64 v25; // rax
  int v26; // ecx
  int v27; // r8d
  struct VIDMM_PROCESS *v28; // rbx
  char *v29; // rbx
  __int64 v30; // rcx
  __int64 v32; // [rsp+50h] [rbp-58h] BYREF
  __int64 v33; // [rsp+58h] [rbp-50h] BYREF
  _BYTE v34[32]; // [rsp+60h] [rbp-48h] BYREF

  v33 = 0;
  v32 = 4096;
  a6 = 0;
  if ( *((VIDMM_PROCESS_FENCE_STORAGE **)this + 28) == VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage )
  {
    v10 = 0x8000000;
    CurrentPartitionHandle = 0;
  }
  else
  {
    v10 = 134479872;
    CurrentPartitionHandle = VIDMM_PROCESS::GetCurrentPartitionHandle();
  }
  v12 = (_QWORD *)((char *)this + 104);
  LODWORD(v13) = MmCreateSection((char *)this + 104, 0, 0, &v32, 4, v10, CurrentPartitionHandle, 0);
  if ( (int)v13 >= 0 )
  {
    a6 = 4096;
    v14 = (PVOID *)((char *)this + 112);
    v15 = MmMapViewInSystemSpaceEx(*v12, (char *)this + 112, &a6, &v33, 0);
    v13 = v15;
    if ( v15 < 0 )
    {
      _InterlockedIncrement(&dword_1400867CC);
      WdLogSingleEntry1(6, v15);
      WdLogGlobalForLineNumber = 755;
      DxgkLogInternalTriageEvent(
        v16,
        262145,
        v17,
        (unsigned int)L"Failed to map system space view of fence storage page. Status=0x%.8x",
        v13,
        0,
        0,
        0);
      goto LABEL_25;
    }
    Mdl = VidMmiAllocateMdl(*v14, 0x1000u);
    *((_QWORD *)this + 15) = Mdl;
    if ( Mdl )
    {
      MmProbeAndLockPages(Mdl, 0, IoModifyAccess);
      v21 = *((_QWORD *)this + 28);
      if ( *(_BYTE *)(v21 + 128) || a4 )
      {
        if ( a4 )
          VmwpProcess = VIDMM_PROCESS::GetVmwpProcess(a4);
        else
          VmwpProcess = *(VIDMM_PROCESS **)v21;
        *((_QWORD *)this + 4) = VmwpProcess;
        LODWORD(v13) = VIDMM_PROCESS::MapHostAddressesToGuest(
                         VmwpProcess,
                         *((struct _MDL **)this + 15),
                         0x1000u,
                         (void **)this + 26,
                         (unsigned __int64 *)this + 25);
        if ( (int)v13 < 0 )
        {
          WdLogSingleEntry0(1);
          WdLogGlobalForLineNumber = 841;
          DxgkLogInternalTriageEvent(
            v23,
            0x40000,
            v24,
            (unsigned int)L"Failed to allocate fence storage page for paravirtualization",
            841,
            0,
            0,
            0);
          goto LABEL_25;
        }
        v25 = *((_QWORD *)this + 28);
        if ( !*(_BYTE *)(v25 + 128) )
        {
          if ( *(_QWORD *)v25 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 858;
            DxgkLogInternalTriageEvent(
              v26,
              262146,
              v27,
              (unsigned int)L"_ProcessFenceStorage.GetVidMmProcess() == nullptr",
              858,
              0,
              0,
              0);
          }
          *(_BYTE *)(*((_QWORD *)this + 28) + 129LL) = 1;
          *((_BYTE *)this + 216) = 1;
          v28 = VIDMM_PROCESS::GetVmwpProcess(*((VIDMM_PROCESS **)this + 4));
          DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(
            (DXGAUTOPUSHLOCKEXCLUSIVE *)v34,
            (struct VIDMM_PROCESS *)((char *)v28 + 104));
          v29 = (char *)v28 + 88;
          v30 = *(_QWORD *)v29;
          if ( *(char **)(*(_QWORD *)v29 + 8LL) != v29 )
            __fastfail(3u);
          *((_QWORD *)this + 2) = v30;
          *((_QWORD *)this + 3) = v29;
          *(_QWORD *)(v30 + 8) = (char *)this + 16;
          *(_QWORD *)v29 = (char *)this + 16;
          DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK((DXGAUTOPUSHLOCK *)v34);
        }
      }
      *((_QWORD *)this + 23) = *v14;
      *((_QWORD *)this + 17) = a2;
      *((_DWORD *)this + 38) = *((_DWORD *)a3 + 13);
      *((_DWORD *)this + 39) = *((_DWORD *)a3 + 14);
      return 0;
    }
    _InterlockedIncrement((volatile signed __int32 *)&gVidMmLowResourceAccumulated);
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 767;
    DxgkLogInternalTriageEvent(
      v19,
      262145,
      v20,
      (unsigned int)L"Failed to allocate memory for fence storage page MDL",
      767,
      0,
      0,
      0);
    LODWORD(v13) = -1073741801;
  }
  else
  {
    *v12 = 0;
  }
LABEL_25:
  VIDMM_FENCE_STORAGE_PAGE::FreeStorage(this);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1401155f8  mov     rax, rsp
0x1401155fb  mov     [rax+10h], rbx
0x1401155ff  mov     [rax+18h], rsi
0x140115603  mov     [rax+8], rcx
0x140115607  push    rdi
0x140115608  push    r12
0x14011560a  push    r13
0x14011560c  push    r14
0x14011560e  push    r15
0x140115610  sub     rsp, 80h
0x140115617  mov     r14, r9
0x14011561a  mov     r13, r8
0x14011561d  mov     r12, rdx
0x140115620  mov     rdi, rcx
0x140115623  xor     r15d, r15d
0x140115626  mov     [rax-50h], r15
0x14011562a  mov     qword ptr [rax-58h], 1000h
0x140115632  mov     [rax+30h], r15
0x140115636  mov     rax, cs:?_GlobalFenceStorage@VIDMM_PROCESS_FENCE_STORAGE@@0PEAV1@EA; VIDMM_PROCESS_FENCE_STORAGE * VIDMM_PROCESS_FENCE_STORAGE::_GlobalFenceStorage
0x14011563d  cmp     [rcx+0E0h], rax
0x140115644  jz      short loc_140115652
0x140115646  mov     esi, 8040000h
0x14011564b  call    ?GetCurrentPartitionHandle@VIDMM_PROCESS@@SAPEAXXZ; VIDMM_PROCESS::GetCurrentPartitionHandle(void)
0x140115650  jmp     short loc_14011565A
0x140115652  mov     esi, 8000000h
0x140115657  mov     rax, r15
0x14011565a  lea     rbx, [rdi+68h]
0x14011565e  mov     [rsp+0A8h+var_70], r15
0x140115663  mov     [rsp+0A8h+var_78], rax
0x140115668  mov     dword ptr [rsp+0A8h+var_80], esi
0x14011566c  mov     dword ptr [rsp+0A8h+var_88], 4
0x140115674  lea     r9, [rsp+0A8h+var_58]
0x140115679  xor     r8d, r8d
0x14011567c  xor     edx, edx
0x14011567e  mov     rcx, rbx
0x140115681  call    cs:__imp_MmCreateSection
0x140115688  nop     dword ptr [rax+rax+00h]
0x14011568d  mov     esi, eax
0x14011568f  test    eax, eax
0x140115691  jns     short loc_14011569B
0x140115693  mov     [rbx], r15
0x140115696  jmp     loc_140115980
0x14011569b  mov     [rsp+0A8h+arg_28], 1000h
0x1401156a7  lea     r15, [rdi+70h]
0x1401156ab  mov     [rsp+0A8h+var_88], 0
0x1401156b4  lea     r9, [rsp+0A8h+var_50]
0x1401156b9  lea     r8, [rsp+0A8h+arg_28]
0x1401156c1  mov     rdx, r15
0x1401156c4  mov     rcx, [rbx]
0x1401156c7  call    cs:__imp_MmMapViewInSystemSpaceEx
0x1401156ce  nop     dword ptr [rax+rax+00h]
0x1401156d3  movsxd  rsi, eax
0x1401156d6  xor     ebx, ebx
0x1401156d8  test    eax, eax
0x1401156da  jns     short loc_140115729
0x1401156dc  lock inc cs:dword_1400867CC
0x1401156e3  mov     rdx, rsi
0x1401156e6  lea     ecx, [rbx+6]
0x1401156e9  call    cs:__imp_WdLogSingleEntry1
0x1401156f0  nop     dword ptr [rax+rax+00h]
0x1401156f5  mov     cs:WdLogGlobalForLineNumber, 2F3h
0x1401156ff  mov     [rsp+0A8h+var_70], rbx
0x140115704  mov     [rsp+0A8h+var_78], rbx
0x140115709  mov     [rsp+0A8h+var_80], rbx
0x14011570e  mov     [rsp+0A8h+var_88], rsi
0x140115713  lea     r9, aFailedToMapSys; "Failed to map system space view of fenc"...
0x14011571a  mov     edx, 40001h
0x14011571f  call    DxgkLogInternalTriageEvent
0x140115724  jmp     loc_140115980
0x140115729  mov     esi, 1000h
0x14011572e  mov     edx, esi; Length
0x140115730  mov     rcx, [r15]; Base
0x140115733  call    ?VidMmiAllocateMdl@@YAPEAU_MDL@@PEAX_K@Z; VidMmiAllocateMdl(void *,unsigned __int64)
0x140115738  mov     [rdi+78h], rax
0x14011573c  test    rax, rax
0x14011573f  jnz     short loc_140115791
0x140115741  lock inc cs:?gVidMmLowResourceAccumulated@@3U_VIDMM_LOW_RESOURCE@@A; _VIDMM_LOW_RESOURCE gVidMmLowResourceAccumulated
0x140115748  lea     ecx, [rax+6]
0x14011574b  call    cs:__imp_WdLogSingleEntry0
0x140115752  nop     dword ptr [rax+rax+00h]
0x140115757  mov     eax, 2FFh
0x14011575c  mov     cs:WdLogGlobalForLineNumber, eax
0x140115762  mov     [rsp+0A8h+var_70], rbx
0x140115767  mov     [rsp+0A8h+var_78], rbx
0x14011576c  mov     [rsp+0A8h+var_80], rbx
0x140115771  mov     [rsp+0A8h+var_88], rax
0x140115776  lea     r9, aFailedToAlloca_59; "Failed to allocate memory for fence sto"...
0x14011577d  mov     edx, 40001h
0x140115782  call    DxgkLogInternalTriageEvent
0x140115787  mov     esi, 0C0000017h
0x14011578c  jmp     loc_140115980
0x140115791  xor     edx, edx; AccessMode
0x140115793  lea     r8d, [rdx+2]; Operation
0x140115797  mov     rcx, rax; MemoryDescriptorList
0x14011579a  call    cs:__imp_MmProbeAndLockPages
0x1401157a1  nop     dword ptr [rax+rax+00h]
0x1401157a6  nop
0x1401157a7  mov     rax, [rdi+0E0h]
0x1401157ae  cmp     [rax+80h], bl
0x1401157b4  jnz     short loc_1401157BF
0x1401157b6  test    r14, r14
0x1401157b9  jz      loc_1401158F6
0x1401157bf  test    r14, r14
0x1401157c2  jz      short loc_1401157D1
0x1401157c4  mov     rcx, r14; this
0x1401157c7  call    ?GetVmwpProcess@VIDMM_PROCESS@@QEAAPEAV1@XZ; VIDMM_PROCESS::GetVmwpProcess(void)
0x1401157cc  mov     rcx, rax
0x1401157cf  jmp     short loc_1401157D4
0x1401157d1  mov     rcx, [rax]; this
0x1401157d4  mov     [rdi+20h], rcx
0x1401157d8  lea     rax, [rdi+0C8h]
0x1401157df  lea     r9, [rdi+0D0h]; void **
0x1401157e6  mov     [rsp+0A8h+var_88], rax; unsigned __int64 *
0x1401157eb  mov     r8, rsi; unsigned __int64
0x1401157ee  mov     rdx, [rdi+78h]; struct _MDL *
0x1401157f2  call    ?MapHostAddressesToGuest@VIDMM_PROCESS@@QEAAJPEAU_MDL@@_KPEAPEAXPEA_K@Z; VIDMM_PROCESS::MapHostAddressesToGuest(_MDL *,unsigned __int64,void * *,unsigned __int64 *)
0x1401157f7  mov     esi, eax
0x1401157f9  test    eax, eax
0x1401157fb  jns     short loc_14011583E
0x1401157fd  mov     ecx, 1
0x140115802  call    cs:__imp_WdLogSingleEntry0
0x140115809  nop     dword ptr [rax+rax+00h]
0x14011580e  mov     eax, 349h
0x140115813  mov     cs:WdLogGlobalForLineNumber, eax
0x140115819  mov     [rsp+0A8h+var_70], rbx
0x14011581e  mov     [rsp+0A8h+var_78], rbx
0x140115823  mov     [rsp+0A8h+var_80], rbx
0x140115828  mov     [rsp+0A8h+var_88], rax
0x14011582d  lea     r9, aFailedToAlloca_5; "Failed to allocate fence storage page f"...
0x140115834  mov     edx, 40000h
0x140115839  jmp     loc_14011571F
0x14011583e  mov     rax, [rdi+0E0h]
0x140115845  cmp     [rax+80h], bl
0x14011584b  jnz     loc_1401158F6
0x140115851  cmp     [rax], rbx
0x140115854  jz      short loc_140115897
0x140115856  mov     ecx, 1
0x14011585b  call    cs:__imp_WdLogSingleEntry0
0x140115862  nop     dword ptr [rax+rax+00h]
0x140115867  mov     eax, 35Ah
0x14011586c  mov     cs:WdLogGlobalForLineNumber, eax
0x140115872  mov     [rsp+0A8h+var_70], rbx
0x140115877  mov     [rsp+0A8h+var_78], rbx
0x14011587c  mov     [rsp+0A8h+var_80], rbx
0x140115881  mov     [rsp+0A8h+var_88], rax
0x140115886  lea     r9, aProcessfencest; "_ProcessFenceStorage.GetVidMmProcess() "...
0x14011588d  mov     edx, 40002h
0x140115892  call    DxgkLogInternalTriageEvent
0x140115897  mov     rax, [rdi+0E0h]
0x14011589e  mov     byte ptr [rax+81h], 1
0x1401158a5  mov     byte ptr [rdi+0D8h], 1
0x1401158ac  mov     rcx, [rdi+20h]; this
0x1401158b0  call    ?GetVmwpProcess@VIDMM_PROCESS@@QEAAPEAV1@XZ; VIDMM_PROCESS::GetVmwpProcess(void)
0x1401158b5  mov     rbx, rax
0x1401158b8  lea     rdx, [rax+68h]; struct DXGPUSHLOCK *
0x1401158bc  lea     rcx, [rsp+0A8h+var_48]; this
0x1401158c1  call    ??0DXGAUTOPUSHLOCKEXCLUSIVE@@QEAA@QEAVDXGPUSHLOCK@@@Z; DXGAUTOPUSHLOCKEXCLUSIVE::DXGAUTOPUSHLOCKEXCLUSIVE(DXGPUSHLOCK * const)
0x1401158c6  add     rbx, 58h ; 'X'
0x1401158ca  mov     rcx, [rbx]
0x1401158cd  cmp     [rcx+8], rbx
0x1401158d1  jz      short loc_1401158DA
0x1401158d3  mov     ecx, 3
0x1401158d8  int     29h; Win8: RtlFailFast(ecx)
0x1401158da  lea     rax, [rdi+10h]
0x1401158de  mov     [rax], rcx
0x1401158e1  mov     [rax+8], rbx
0x1401158e5  mov     [rcx+8], rax
0x1401158e9  mov     [rbx], rax
0x1401158ec  lea     rcx, [rsp+0A8h+var_48]; this
0x1401158f1  call    ??1DXGAUTOPUSHLOCK@@QEAA@XZ; DXGAUTOPUSHLOCK::~DXGAUTOPUSHLOCK(void)
0x1401158f6  mov     rax, [r15]
0x1401158f9  mov     [rdi+0B8h], rax
0x140115900  mov     [rdi+88h], r12
0x140115907  mov     eax, [r13+34h]
0x14011590b  mov     [rdi+98h], eax
0x140115911  mov     eax, [r13+38h]
0x140115915  mov     [rdi+9Ch], eax
0x14011591b  xor     eax, eax
0x14011591d  jmp     short loc_14011598A
0x14011591f  movsxd  rsi, eax
0x140115922  lock inc cs:dword_1400866A4
0x140115929  mov     rdx, rsi
0x14011592c  mov     ecx, 6
0x140115931  call    cs:__imp_WdLogSingleEntry1
0x140115938  nop     dword ptr [rax+rax+00h]
0x14011593d  mov     cs:WdLogGlobalForLineNumber, 310h
0x140115947  mov     [rsp+0A8h+var_70], 0
0x140115950  mov     [rsp+0A8h+var_78], 0
0x140115959  mov     [rsp+0A8h+var_80], 0
0x140115962  mov     [rsp+0A8h+var_88], rsi
0x140115967  lea     r9, aFailedToProbeA_0; "Failed to probe and lock fence storage "...
0x14011596e  mov     edx, 40001h
0x140115973  call    DxgkLogInternalTriageEvent
0x140115978  mov     rdi, [rsp+0A8h+arg_0]
0x140115980  mov     rcx, rdi; this
0x140115983  call    ?FreeStorage@VIDMM_FENCE_STORAGE_PAGE@@QEAAXXZ; VIDMM_FENCE_STORAGE_PAGE::FreeStorage(void)
0x140115988  mov     eax, esi
0x14011598a  lea     r11, [rsp+0A8h+var_28]
0x140115992  mov     rbx, [r11+38h]
0x140115996  mov     rsi, [r11+40h]
0x14011599a  mov     rsp, r11
0x14011599d  pop     r15
0x14011599f  pop     r14
0x1401159a1  pop     r13
0x1401159a3  pop     r12
0x1401159a5  pop     rdi
0x1401159a6  retn
```
