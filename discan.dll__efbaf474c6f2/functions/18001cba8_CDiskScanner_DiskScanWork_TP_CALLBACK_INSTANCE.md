# CDiskScanner::DiskScanWork(_TP_CALLBACK_INSTANCE *)

- ea: `0x18001cba8`
- end: `0x18001ce86`
- name: `?DiskScanWork@CDiskScanner@@IEAAXPEAU_TP_CALLBACK_INSTANCE@@@Z`
- size: `734`
- prototype: `void __fastcall(CDiskScanner *__hidden this, PTP_CALLBACK_INSTANCE pci)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001ec20`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x18000aaec`
- `0x18000ac34`
- `0x18001c8c4`
- `0x18001cba8`
- `0x18001ce8c`
- `0x1800201a0`
- `0x1800202b8`
- `0x180039010`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18001cd3b`
- `KERNEL32!GetTickCount64` at `0x18001cdf6`
- `KERNEL32!GetTickCount64` at `0x18001cd3b`
- `KERNEL32!GetTickCount64` at `0x18001cdf6`
- `KERNEL32!ReleaseSemaphoreWhenCallbackReturns` at `0x18001cd25`
- `KERNEL32!ReleaseSemaphoreWhenCallbackReturns` at `0x18001cd25`
- `KERNEL32!GetThreadPriority` at `0x18001cd96`
- `KERNEL32!GetThreadPriority` at `0x18001cd96`
- `KERNEL32!GetCurrentThread` at `0x18001cd8d`
- `KERNEL32!GetCurrentThread` at `0x18001cd8d`
- `KERNEL32!GetPriorityClass` at `0x18001cda7`
- `KERNEL32!GetPriorityClass` at `0x18001cda7`
- `KERNEL32!GetCurrentProcess` at `0x18001cd9e`
- `KERNEL32!GetCurrentProcess` at `0x18001cd9e`
- `KERNEL32!WaitForSingleObject` at `0x18001cce4`
- `KERNEL32!WaitForSingleObject` at `0x18001cce4`

## pseudocode

```c
void __fastcall CDiskScanner::DiskScanWork(CDiskScanner *this, PTP_CALLBACK_INSTANCE pci)
{
  __int64 v4; // rdx
  USHORT v5; // dx
  USHORT Length; // cx
  USHORT v7; // ax
  PVOID *v8; // rcx
  ULONGLONG TickCount64; // r15
  PVOID *v10; // rcx
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE CurrentProcess; // rax
  DWORD PriorityClass; // eax
  __int64 v15; // rdx
  __int64 v16; // r8
  unsigned __int8 v17; // si
  int v18; // eax
  int v19; // ebx
  ULONGLONG v20; // rax
  __int64 v21; // r8
  __int64 v22; // r8
  __int64 v23; // [rsp+30h] [rbp-20h]
  char *v24; // [rsp+38h] [rbp-18h]
  const char *v25; // [rsp+40h] [rbp-10h] BYREF
  int v26; // [rsp+48h] [rbp-8h]
  unsigned __int8 v27; // [rsp+80h] [rbp+30h] BYREF

  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v4 + 16) = "CDiskScanner::DiskScanWork";
  v25 = "CDiskScanner::DiskScanWork";
  v26 = 0;
  v5 = ++*(_WORD *)(v4 + 8);
  Length = GlobalIndentString.Length;
  v7 = GlobalIndentString.Length;
  if ( v5 < GlobalIndentString.Length )
    v7 = v5;
  LOWORD(v23) = v7;
  if ( v5 < GlobalIndentString.Length )
    Length = v5;
  WORD1(v23) = Length;
  HIDWORD(v23) = 0;
  v24 = off_180047060;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskScanner::DiskScanWork");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
  {
    WPP_SF_d(v8[2], 16, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, *((unsigned int *)this + 4));
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( *(_QWORD *)(*((_QWORD *)this + 10) + 16LL) )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 && *((_BYTE *)v8 + 25) >= 4u )
      WPP_SF_d(v8[2], 17, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, *((unsigned int *)this + 4));
    WaitForSingleObject(*(HANDLE *)(*((_QWORD *)this + 10) + 16LL), 0xFFFFFFFF);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *((unsigned int *)this + 4));
    }
    ReleaseSemaphoreWhenCallbackReturns(pci, *(HANDLE *)(*((_QWORD *)this + 10) + 16LL), 1u);
  }
  EventWriteDiskScanStart(
    *((struct _SCRUB_ENVIRONMENT **)this + 10),
    (const struct _STORAGE_DEVICE_NUMBER_EX *)this,
    (CDiskScanner *)((char *)this + 40));
  TickCount64 = GetTickCount64();
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *((unsigned int *)this + 4));
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 1) != 0 && *((_BYTE *)v10 + 25) >= 4u )
    {
      CurrentThread = GetCurrentThread();
      ThreadPriority = GetThreadPriority(CurrentThread);
      CurrentProcess = GetCurrentProcess();
      PriorityClass = GetPriorityClass(CurrentProcess);
      WPP_SF_DLL(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v16,
        *((unsigned int *)this + 4),
        PriorityClass,
        ThreadPriority,
        v23,
        v24,
        v25,
        v26);
    }
  }
  v17 = 0;
  v27 = 0;
  if ( *(_DWORD *)(*((_QWORD *)this + 10) + 8LL) == 1 )
  {
    v18 = CDiskScanner::DrtDiskScanWork(this);
  }
  else
  {
    v18 = CDiskScanner::DiskScanWork(this, &v27);
    v17 = v27;
  }
  v26 = v18;
  v19 = v18;
  v20 = GetTickCount64();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Did(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      &WPP_GLOBAL_Control,
      v21,
      *((unsigned int *)this + 4),
      10000 * (v20 - TickCount64),
      v19);
  }
  EventWriteDiskScanComplete(
    *((struct _SCRUB_ENVIRONMENT **)this + 10),
    (const struct _STORAGE_DEVICE_NUMBER_EX *)this,
    (CDiskScanner *)((char *)this + 40),
    0);
  LOBYTE(v22) = v17;
  (***((void (__fastcall ****)(_QWORD, CDiskScanner *, __int64))this + 11))(*((_QWORD *)this + 11), this, v22);
  CHResultImp::~CHResultImp((CHResultImp *)&v25);
}

```

## disassembly

```asm
0x18001cba8  mov     [rsp-28h+arg_8], rbx
0x18001cbad  mov     [rsp-28h+arg_10], rsi
0x18001cbb2  push    rbp
0x18001cbb3  push    rdi
0x18001cbb4  push    r12
0x18001cbb6  push    r14
0x18001cbb8  push    r15
0x18001cbba  mov     rbp, rsp
0x18001cbbd  sub     rsp, 50h
0x18001cbc1  mov     rbx, rdx
0x18001cbc4  mov     rdi, rcx
0x18001cbc7  mov     r8d, cs:_tls_index
0x18001cbce  mov     rax, gs:58h
0x18001cbd7  mov     rdx, [rax+r8*8]
0x18001cbdb  mov     eax, 10h
0x18001cbe0  lea     r8, aCdiskscannerDi; "CDiskScanner::DiskScanWork"
0x18001cbe7  mov     [rax+rdx], r8
0x18001cbeb  mov     [rbp+var_10], r8
0x18001cbef  mov     [rbp+var_8], 0
0x18001cbf6  mov     eax, 8
0x18001cbfb  mov     r12d, 1
0x18001cc01  add     [rax+rdx], r12w
0x18001cc06  movzx   edx, word ptr [rax+rdx]
0x18001cc0a  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001cc11  movzx   eax, cx
0x18001cc14  cmp     dx, cx
0x18001cc17  cmovb   ax, dx
0x18001cc1b  mov     [rbp+var_20], ax
0x18001cc1f  cmovb   cx, dx
0x18001cc23  mov     [rbp+var_1E], cx
0x18001cc27  xor     eax, eax
0x18001cc29  mov     [rbp+var_1C], eax
0x18001cc2c  mov     rax, cs:off_180047060; "                                       "...
0x18001cc33  mov     [rbp+var_18], rax
0x18001cc37  lea     rsi, WPP_GLOBAL_Control
0x18001cc3e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc45  cmp     rcx, rsi
0x18001cc48  jz      short loc_18001CC74
0x18001cc4a  test    [rcx+1Ch], r12b
0x18001cc4e  jz      short loc_18001CC74
0x18001cc50  cmp     byte ptr [rcx+19h], 5
0x18001cc54  jb      short loc_18001CC74
0x18001cc56  lea     edx, [r12+0Ch]
0x18001cc5b  mov     [rsp+50h+var_30], r8; __int64
0x18001cc60  lea     r9, [rbp+var_20]
0x18001cc64  mov     rcx, [rcx+10h]; LoggerHandle
0x18001cc68  call    WPP_SF_aZs
0x18001cc6d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cc74  lea     r14, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001cc7b  cmp     rcx, rsi
0x18001cc7e  jz      short loc_18001CCA8
0x18001cc80  test    [rcx+1Ch], r12b
0x18001cc84  jz      short loc_18001CCA8
0x18001cc86  cmp     byte ptr [rcx+19h], 4
0x18001cc8a  jb      short loc_18001CCA8
0x18001cc8c  mov     edx, 10h
0x18001cc91  mov     r9d, [rdi+10h]
0x18001cc95  mov     r8, r14
0x18001cc98  mov     rcx, [rcx+10h]
0x18001cc9c  call    WPP_SF_d
0x18001cca1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cca8  mov     rax, [rdi+50h]
0x18001ccac  cmp     qword ptr [rax+10h], 0
0x18001ccb1  jz      short loc_18001CD2B
0x18001ccb3  cmp     rcx, rsi
0x18001ccb6  jz      short loc_18001CCD9
0x18001ccb8  test    [rcx+1Ch], r12b
0x18001ccbc  jz      short loc_18001CCD9
0x18001ccbe  cmp     byte ptr [rcx+19h], 4
0x18001ccc2  jb      short loc_18001CCD9
0x18001ccc4  mov     edx, 11h
0x18001ccc9  mov     r9d, [rdi+10h]
0x18001cccd  mov     r8, r14
0x18001ccd0  mov     rcx, [rcx+10h]
0x18001ccd4  call    WPP_SF_d
0x18001ccd9  mov     rcx, [rdi+50h]
0x18001ccdd  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001cce0  mov     rcx, [rcx+10h]; hHandle
0x18001cce4  call    cs:__imp_WaitForSingleObject
0x18001ccea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ccf1  cmp     rcx, rsi
0x18001ccf4  jz      short loc_18001CD17
0x18001ccf6  test    [rcx+1Ch], r12b
0x18001ccfa  jz      short loc_18001CD17
0x18001ccfc  cmp     byte ptr [rcx+19h], 4
0x18001cd00  jb      short loc_18001CD17
0x18001cd02  mov     edx, 12h
0x18001cd07  mov     r9d, [rdi+10h]
0x18001cd0b  mov     r8, r14
0x18001cd0e  mov     rcx, [rcx+10h]
0x18001cd12  call    WPP_SF_d
0x18001cd17  mov     rdx, [rdi+50h]
0x18001cd1b  mov     r8d, r12d; crel
0x18001cd1e  mov     rdx, [rdx+10h]; sem
0x18001cd22  mov     rcx, rbx; pci
0x18001cd25  call    cs:__imp_ReleaseSemaphoreWhenCallbackReturns
0x18001cd2b  lea     r8, [rdi+28h]; struct SPACEPORT_DISK_INFO *
0x18001cd2f  mov     rdx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001cd32  mov     rcx, [rdi+50h]; struct _SCRUB_ENVIRONMENT *
0x18001cd36  call    ?EventWriteDiskScanStart@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@@Z; EventWriteDiskScanStart(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *)
0x18001cd3b  call    cs:__imp_GetTickCount64
0x18001cd41  mov     r15, rax
0x18001cd44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd4b  cmp     rcx, rsi
0x18001cd4e  jz      short loc_18001CDC9
0x18001cd50  test    [rcx+1Ch], r12b
0x18001cd54  jz      short loc_18001CD7C
0x18001cd56  cmp     byte ptr [rcx+19h], 4
0x18001cd5a  jb      short loc_18001CD7C
0x18001cd5c  mov     edx, 13h
0x18001cd61  mov     r9d, [rdi+10h]
0x18001cd65  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001cd6c  mov     rcx, [rcx+10h]
0x18001cd70  call    WPP_SF_d
0x18001cd75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cd7c  cmp     rcx, rsi
0x18001cd7f  jz      short loc_18001CDC9
0x18001cd81  test    [rcx+1Ch], r12b
0x18001cd85  jz      short loc_18001CDC9
0x18001cd87  cmp     byte ptr [rcx+19h], 4
0x18001cd8b  jb      short loc_18001CDC9
0x18001cd8d  call    cs:__imp_GetCurrentThread
0x18001cd93  mov     rcx, rax; hThread
0x18001cd96  call    cs:__imp_GetThreadPriority
0x18001cd9c  mov     ebx, eax
0x18001cd9e  call    cs:__imp_GetCurrentProcess
0x18001cda4  mov     rcx, rax; hProcess
0x18001cda7  call    cs:__imp_GetPriorityClass
0x18001cdad  mov     [rsp+50h+var_28], ebx
0x18001cdb1  mov     dword ptr [rsp+50h+var_30], eax
0x18001cdb5  mov     r9d, [rdi+10h]
0x18001cdb9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cdc0  mov     rcx, [rcx+10h]
0x18001cdc4  call    WPP_SF_DLL
0x18001cdc9  xor     sil, sil
0x18001cdcc  mov     [rbp+arg_0], sil
0x18001cdd0  mov     rax, [rdi+50h]
0x18001cdd4  mov     rcx, rdi; this
0x18001cdd7  cmp     [rax+8], r12d
0x18001cddb  jz      short loc_18001CDEC
0x18001cddd  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x18001cde1  call    ?DiskScanWork@CDiskScanner@@IEAAJPEAE@Z; CDiskScanner::DiskScanWork(uchar *)
0x18001cde6  mov     sil, [rbp+arg_0]
0x18001cdea  jmp     short loc_18001CDF1
0x18001cdec  call    ?DrtDiskScanWork@CDiskScanner@@IEAAJXZ; CDiskScanner::DrtDiskScanWork(void)
0x18001cdf1  mov     [rbp+var_8], eax
0x18001cdf4  mov     ebx, eax
0x18001cdf6  call    cs:__imp_GetTickCount64
0x18001cdfc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ce03  lea     rdx, WPP_GLOBAL_Control
0x18001ce0a  cmp     rcx, rdx
0x18001ce0d  jz      short loc_18001CE3B
0x18001ce0f  test    [rcx+1Ch], r12b
0x18001ce13  jz      short loc_18001CE3B
0x18001ce15  cmp     byte ptr [rcx+19h], 4
0x18001ce19  jb      short loc_18001CE3B
0x18001ce1b  sub     rax, r15
0x18001ce1e  imul    rax, 2710h
0x18001ce25  mov     [rsp+50h+var_28], ebx
0x18001ce29  mov     [rsp+50h+var_30], rax
0x18001ce2e  mov     r9d, [rdi+10h]
0x18001ce32  mov     rcx, [rcx+10h]
0x18001ce36  call    WPP_SF_Did
0x18001ce3b  xor     r9d, r9d; int
0x18001ce3e  lea     r8, [rdi+28h]; struct SPACEPORT_DISK_INFO *
0x18001ce42  mov     rdx, rdi; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001ce45  mov     rcx, [rdi+50h]; struct _SCRUB_ENVIRONMENT *
0x18001ce49  call    ?EventWriteDiskScanComplete@@YAXPEAU_SCRUB_ENVIRONMENT@@PEBU_STORAGE_DEVICE_NUMBER_EX@@PEBUSPACEPORT_DISK_INFO@@H@Z; EventWriteDiskScanComplete(_SCRUB_ENVIRONMENT *,_STORAGE_DEVICE_NUMBER_EX const *,SPACEPORT_DISK_INFO const *,int)
0x18001ce4e  mov     rcx, [rdi+58h]
0x18001ce52  mov     rax, [rcx]
0x18001ce55  mov     r8b, sil
0x18001ce58  mov     rdx, rdi
0x18001ce5b  mov     rax, [rax]
0x18001ce5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce63  nop
0x18001ce64  lea     rcx, [rbp+var_10]; this
0x18001ce68  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001ce6d  lea     r11, [rsp+50h+var_s0]
0x18001ce72  mov     rbx, [r11+38h]
0x18001ce76  mov     rsi, [r11+40h]
0x18001ce7a  mov     rsp, r11
0x18001ce7d  pop     r15
0x18001ce7f  pop     r14
0x18001ce81  pop     r12
0x18001ce83  pop     rdi
0x18001ce84  pop     rbp
0x18001ce85  retn
```
