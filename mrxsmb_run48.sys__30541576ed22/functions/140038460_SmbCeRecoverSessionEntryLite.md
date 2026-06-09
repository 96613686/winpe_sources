# SmbCeRecoverSessionEntryLite

- ea: `0x140038460`
- end: `0x1400385ad`
- name: `SmbCeRecoverSessionEntryLite`
- size: `333`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140006ec0`
- `0x14000a260`
- `0x1400181f0`

## callees

- `0x140037aa4`
- `0x140038460`
- `0x1400423fc`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140038485`
- `ntoskrnl!ExAllocatePool2` at `0x140038485`
- `rdbss!RxPostToWorkerThread` at `0x140038591`
- `rdbss!RxPostToWorkerThread` at `0x140038591`

## pseudocode

```c
__int64 __fastcall SmbCeRecoverSessionEntryLite(__int64 a1, unsigned int a2)
{
  _QWORD *Pool2; // rax
  void *pContext; // rdi
  char v5; // r8
  __int64 i; // rcx
  __int64 v7; // rdx

  if ( !*(_DWORD *)(a1 + 12) )
  {
    Pool2 = (_QWORD *)ExAllocatePool2(64, 48, 1834181187);
    pContext = Pool2;
    if ( Pool2 )
    {
      Pool2[2] = a1;
      *Pool2 = SmbCepCompleteSessionEntryRecovery;
      v5 = _InterlockedExchange((volatile __int32 *)(a1 + 12), 4);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qZd(
          WPP_GLOBAL_Control->AttachedDevice,
          46,
          (unsigned int)&WPP_84a53c2c5f823219b45553a65390e18c_Traceguids,
          a1,
          *(_QWORD *)(a1 + 384) + 80LL,
          v5);
      }
      if ( Microsoft_Windows_SMBClientEnableBits < 0 )
        McTemplateK0phzr1_EtwWriteTransfer(
          *(_WORD *)(*(_QWORD *)(a1 + 384) + 80LL) >> 1,
          (unsigned int)&SmbSessionExpired,
          0,
          a1,
          *(_WORD *)(*(_QWORD *)(a1 + 384) + 80LL) >> 1,
          *(_QWORD *)(*(_QWORD *)(a1 + 384) + 88LL));
      for ( i = *(_QWORD *)(a1 + 408); ; i = *(_QWORD *)(v7 + 384) )
      {
        v7 = 0;
        if ( i != a1 + 408 )
          v7 = i - 384;
        if ( !v7 )
          break;
        if ( !*(_DWORD *)(v7 + 12) )
          _InterlockedExchange((volatile __int32 *)(v7 + 12), 4);
      }
      return (unsigned int)RxPostToWorkerThread(
                             *(PRDBSS_DEVICE_OBJECT *)(a1 + 24),
                             NormalWorkQueue,
                             (PRX_WORK_QUEUE_ITEM)(a1 + 200),
                             SmbCepSessionRecoveryWorker,
                             pContext);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140038460  mov     [rsp+arg_0], rbx
0x140038465  push    rdi
0x140038466  sub     rsp, 30h
0x14003846a  cmp     dword ptr [rcx+0Ch], 0
0x14003846e  mov     rbx, rcx
0x140038471  jnz     loc_14003859F
0x140038477  mov     edx, 30h ; '0'
0x14003847c  mov     r8d, 6D536243h
0x140038482  lea     ecx, [rdx+10h]
0x140038485  call    cs:__imp_ExAllocatePool2
0x14003848c  nop     dword ptr [rax+rax+00h]
0x140038491  mov     rdi, rax
0x140038494  test    rax, rax
0x140038497  jnz     short loc_1400384A3
0x140038499  mov     edx, 0C000009Ah
0x14003849e  jmp     loc_14003859F
0x1400384a3  lea     rax, SmbCepCompleteSessionEntryRecovery
0x1400384aa  mov     [rdi+10h], rbx
0x1400384ae  mov     r8d, 4
0x1400384b4  mov     [rdi], rax
0x1400384b7  xchg    r8d, [rbx+0Ch]
0x1400384bb  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400384c2  lea     rax, WPP_GLOBAL_Control
0x1400384c9  cmp     rcx, rax
0x1400384cc  jz      short loc_140038508
0x1400384ce  mov     eax, [rcx+2Ch]
0x1400384d1  test    al, 1
0x1400384d3  jz      short loc_140038508
0x1400384d5  cmp     byte ptr [rcx+29h], 1
0x1400384d9  jb      short loc_140038508
0x1400384db  mov     rax, [rbx+180h]
0x1400384e2  mov     edx, 2Eh ; '.'
0x1400384e7  mov     rcx, [rcx+18h]
0x1400384eb  add     rax, 50h ; 'P'
0x1400384ef  mov     dword ptr [rsp+38h+var_10], r8d
0x1400384f4  mov     r9, rbx
0x1400384f7  lea     r8, WPP_84a53c2c5f823219b45553a65390e18c_Traceguids
0x1400384fe  mov     [rsp+38h+pContext], rax
0x140038503  call    WPP_SF_qZd
0x140038508  cmp     cs:Microsoft_Windows_SMBClientEnableBits, 0
0x14003850f  jge     short loc_14003853F
0x140038511  mov     rax, [rbx+180h]
0x140038518  lea     rdx, SmbSessionExpired
0x14003851f  mov     r9, rbx
0x140038522  xor     r8d, r8d
0x140038525  movzx   ecx, word ptr [rax+50h]
0x140038529  mov     rax, [rax+58h]
0x14003852d  shr     cx, 1
0x140038530  mov     [rsp+38h+var_10], rax
0x140038535  mov     word ptr [rsp+38h+pContext], cx
0x14003853a  call    McTemplateK0phzr1_EtwWriteTransfer
0x14003853f  lea     r8, [rbx+198h]
0x140038546  mov     rcx, [r8]
0x140038549  jmp     short loc_140038560
0x14003854b  cmp     dword ptr [rdx+0Ch], 0
0x14003854f  jnz     short loc_140038559
0x140038551  mov     eax, 4
0x140038556  xchg    eax, [rdx+0Ch]
0x140038559  mov     rcx, [rdx+180h]
0x140038560  xor     edx, edx
0x140038562  lea     rax, [rcx-180h]
0x140038569  cmp     rcx, r8
0x14003856c  cmovnz  rdx, rax
0x140038570  test    rdx, rdx
0x140038573  jnz     short loc_14003854B
0x140038575  mov     rcx, [rbx+18h]; pMRxDeviceObject
0x140038579  lea     r8, [rbx+0C8h]; pWorkQueueItem
0x140038580  lea     r9, SmbCepSessionRecoveryWorker; Routine
0x140038587  mov     [rsp+38h+pContext], rdi; pContext
0x14003858c  mov     edx, 3; WorkQueueType
0x140038591  call    cs:__imp_RxPostToWorkerThread
0x140038598  nop     dword ptr [rax+rax+00h]
0x14003859d  mov     edx, eax
0x14003859f  mov     rbx, [rsp+38h+arg_0]
0x1400385a4  mov     eax, edx
0x1400385a6  add     rsp, 30h
0x1400385aa  pop     rdi
0x1400385ab  retn
```
