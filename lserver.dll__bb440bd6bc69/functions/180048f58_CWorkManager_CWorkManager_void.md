# CWorkManager::CWorkManager(void)

- ea: `0x180048f58`
- end: `0x1800490b1`
- name: `??0CWorkManager@@QEAA@XZ`
- size: `345`
- prototype: `CWorkManager *__fastcall(CWorkManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180001bc0`

## callees

- `0x180031db8`
- `0x18004692c`
- `0x180048f58`
- `0x18004aa90`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x180048f9e`
- `KERNEL32!CreateEventW` at `0x180048fbc`
- `KERNEL32!CreateEventW` at `0x180048f9e`
- `KERNEL32!CreateEventW` at `0x180048fbc`
- `KERNEL32!CreateMutexW` at `0x180048fd6`
- `KERNEL32!CreateMutexW` at `0x180048fd6`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
CWorkManager *__fastcall CWorkManager::CWorkManager(CWorkManager *this)
{
  HANDLE MutexW; // rax
  unsigned int v2; // edx

  g_WorkManager = 0;
  qword_1800E92B8 = 0;
  g_WorkManager = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<unsigned long const,CWorkObject *>>>::_Buyheadnode();
  qword_1800E92D0 = (__int64)CreateEventW(0, 1, 0, 0);
  qword_1800E92C0 = (__int64)CreateEventW(0, 0, 1, 0);
  MutexW = CreateMutexW(0, 0, 0);
  qword_1800E92C8 = (__int64)MutexW;
  if ( qword_1800E92D0 && qword_1800E92C0 && MutexW )
  {
    dword_1800E92D8 = -1;
    dword_1800E92DC = -1;
    qword_1800E92E0 = 0;
  }
  CCriticalSection::CCriticalSection((CCriticalSection *)qword_1800E92E8, v2);
  qword_1800E9318 = 0;
  qword_1800E9320 = 0;
  qword_1800E9318 = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<void * const,CWorkManager::WorkMangerInProcessJob>>>::_Buyheadnode();
  qword_1800E9328 = 0;
  xmmword_1800E9330 = 0;
  xmmword_1800E9340 = 0;
  dword_1800E9350 = -1;
  dword_1800E9354 = -1;
  dword_1800E935C = 900000;
  dword_1800E9360 = 50;
  qword_1800E9368 = 0;
  qword_1800E9370 = 0;
  dword_1800E9378 = 0;
  qword_1800E9380 = 0;
  return (CWorkManager *)&g_WorkManager;
}

```

## disassembly

```asm
0x180048f58  mov     rax, rsp
0x180048f5b  mov     [rax+20h], rsi
0x180048f5f  mov     [rax+8], rcx
0x180048f63  push    rdi
0x180048f64  sub     rsp, 20h
0x180048f68  lea     rsi, ?g_WorkManager@@3VCWorkManager@@A; CWorkManager g_WorkManager
0x180048f6f  mov     [rax+10h], rsi
0x180048f73  mov     [rax+18h], rsi
0x180048f77  xor     edi, edi
0x180048f79  mov     cs:?g_WorkManager@@3VCWorkManager@@A, rdi; CWorkManager g_WorkManager
0x180048f80  mov     cs:qword_1800E92B8, rdi
0x180048f87  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBKPEAVCWorkObject@@@std@@V?$allocator@U?$pair@$$CBKPEAVCWorkObject@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKPEAVCWorkObject@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ulong const,CWorkObject *>>>::_Buyheadnode(void)
0x180048f8c  mov     cs:?g_WorkManager@@3VCWorkManager@@A, rax; CWorkManager g_WorkManager
0x180048f93  xor     r9d, r9d; lpName
0x180048f96  xor     r8d, r8d; bInitialState
0x180048f99  lea     edx, [rdi+1]; bManualReset
0x180048f9c  xor     ecx, ecx; lpEventAttributes
0x180048f9e  call    cs:__imp_CreateEventW
0x180048fa5  nop     dword ptr [rax+rax+00h]
0x180048faa  mov     cs:qword_1800E92D0, rax
0x180048fb1  xor     r9d, r9d; lpName
0x180048fb4  xor     edx, edx; bManualReset
0x180048fb6  xor     ecx, ecx; lpEventAttributes
0x180048fb8  lea     r8d, [rdi+1]; bInitialState
0x180048fbc  call    cs:__imp_CreateEventW
0x180048fc3  nop     dword ptr [rax+rax+00h]
0x180048fc8  mov     cs:qword_1800E92C0, rax
0x180048fcf  xor     r8d, r8d; lpName
0x180048fd2  xor     edx, edx; bInitialOwner
0x180048fd4  xor     ecx, ecx; lpMutexAttributes
0x180048fd6  call    cs:__imp_CreateMutexW
0x180048fdd  nop     dword ptr [rax+rax+00h]
0x180048fe2  mov     cs:qword_1800E92C8, rax
0x180048fe9  cmp     cs:qword_1800E92D0, rdi
0x180048ff0  jz      short loc_180049015
0x180048ff2  cmp     cs:qword_1800E92C0, rdi
0x180048ff9  jz      short loc_180049015
0x180048ffb  test    rax, rax
0x180048ffe  jz      short loc_180049015
0x180049000  or      cs:dword_1800E92D8, 0FFFFFFFFh
0x180049007  or      cs:dword_1800E92DC, 0FFFFFFFFh
0x18004900e  mov     cs:qword_1800E92E0, rdi
0x180049015  lea     rcx, qword_1800E92E8; this
0x18004901c  call    ??0CCriticalSection@@QEAA@K@Z; CCriticalSection::CCriticalSection(ulong)
0x180049021  nop
0x180049022  lea     rax, qword_1800E9318
0x180049029  mov     [rsp+28h+arg_0], rax
0x18004902e  mov     cs:qword_1800E9318, rdi
0x180049035  mov     cs:qword_1800E9320, rdi
0x18004903c  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@QEAXUWorkMangerInProcessJob@CWorkManager@@@std@@V?$allocator@U?$pair@QEAXUWorkMangerInProcessJob@CWorkManager@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@QEAXUWorkMangerInProcessJob@CWorkManager@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<void * const,CWorkManager::WorkMangerInProcessJob>>>::_Buyheadnode(void)
0x180049041  mov     cs:qword_1800E9318, rax
0x180049048  mov     cs:qword_1800E9328, rdi
0x18004904f  xorps   xmm0, xmm0
0x180049052  movdqa  cs:xmmword_1800E9330, xmm0
0x18004905a  xorps   xmm1, xmm1
0x18004905d  movdqa  cs:xmmword_1800E9340, xmm1
0x180049065  or      cs:dword_1800E9350, 0FFFFFFFFh
0x18004906c  or      cs:dword_1800E9354, 0FFFFFFFFh
0x180049073  mov     cs:dword_1800E935C, 0DBBA0h
0x18004907d  mov     cs:dword_1800E9360, 32h ; '2'
0x180049087  mov     cs:qword_1800E9368, rdi
0x18004908e  mov     cs:qword_1800E9370, rdi
0x180049095  mov     cs:dword_1800E9378, edi
0x18004909b  mov     cs:qword_1800E9380, rdi
0x1800490a2  mov     rax, rsi
0x1800490a5  mov     rsi, [rsp+28h+arg_18]
0x1800490aa  add     rsp, 20h
0x1800490ae  pop     rdi
0x1800490af  retn
```
