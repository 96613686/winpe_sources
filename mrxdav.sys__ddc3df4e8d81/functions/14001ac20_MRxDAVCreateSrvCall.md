# MRxDAVCreateSrvCall

- ea: `0x14001ac20`
- end: `0x14001ae12`
- name: `MRxDAVCreateSrvCall`
- size: `498`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000163c`
- `0x140001b64`
- `0x140002ac4`
- `0x140002be4`
- `0x140006880`
- `0x14001ac20`

## import_xrefs

- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ac55`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ac91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001acdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ad46`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ac55`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ac91`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001acdb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ad46`
- `ntoskrnl!ExAllocatePool2` at `0x14001ad18`
- `ntoskrnl!ExAllocatePool2` at `0x14001ad18`
- `ntoskrnl!IoGetCurrentProcess` at `0x14001ad8d`
- `ntoskrnl!IoGetCurrentProcess` at `0x14001ad8d`
- `rdbss!RxDispatchToWorkerThread` at `0x14001addc`
- `rdbss!RxDispatchToWorkerThread` at `0x14001addc`

## pseudocode

```c
__int64 __fastcall MRxDAVCreateSrvCall(__int64 a1, __int64 a2)
{
  __int64 v4; // rbx
  HANDLE CurrentThreadId; // rax
  __int64 v6; // rbx
  HANDLE v7; // rax
  __int64 v8; // rbx
  __int64 v9; // rdi
  unsigned int v10; // eax
  __int64 Pool2; // rax
  __int64 v12; // rbx
  HANDLE v13; // rax
  _QWORD *v14; // rdi
  __int64 v15; // rbx
  NTSTATUS v16; // eax

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
    {
      v4 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      CurrentThreadId = PsGetCurrentThreadId();
      WPP_SF_q(v4, 10, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, CurrentThreadId);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
      {
        v6 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v7 = PsGetCurrentThreadId();
        WPP_SF_qqq(v6, 11, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v7, a1, a2);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x4000) != 0 )
      {
        v8 = *(_QWORD *)(a1 + 64);
        v9 = *((_QWORD *)WPP_GLOBAL_Control + 3);
        v10 = (unsigned int)PsGetCurrentThreadId();
        WPP_SF_qZ(v9, 12, (unsigned int)WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v10, v8);
      }
    }
  }
  *(_DWORD *)(a1 + 100) = 150;
  Pool2 = ExAllocatePool2(66, 40, 1666405956);
  *(_QWORD *)(a1 + 32) = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x2000) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 3);
      v13 = PsGetCurrentThreadId();
      WPP_SF_q(v12, 13, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids, v13);
    }
    goto LABEL_14;
  }
  *(_OWORD *)Pool2 = 0;
  *(_OWORD *)(Pool2 + 16) = 0;
  *(_QWORD *)(Pool2 + 32) = 0;
  v14 = *(_QWORD **)(a2 + 32);
  v15 = *(_QWORD *)(a1 + 32);
  *(_QWORD *)(v15 + 8) = IoGetCurrentProcess();
  *(_QWORD *)(v15 + 16) = KeGetCurrentThread();
  if ( (int)MRxDAVGetCompletePathName((__int64)v14, 0x63535644u, (struct _UNICODE_STRING *)(v15 + 24)) < 0 )
  {
LABEL_14:
    *(_DWORD *)(a2 + 280) = -1073741670;
LABEL_18:
    (*(void (__fastcall **)(__int64))(a2 + 272))(a2);
    return 259;
  }
  v14[27] = a2;
  v16 = RxDispatchToWorkerThread(g_MRxDAVDeviceObject, DelayedWorkQueue, MRxDAVSrvCallWrapper, v14);
  if ( v16 )
  {
    *(_DWORD *)(a2 + 280) = v16;
    goto LABEL_18;
  }
  return 259;
}

```

## disassembly

```asm
0x14001ac20  push    rbx
0x14001ac22  push    rbp
0x14001ac23  push    rsi
0x14001ac24  push    rdi
0x14001ac25  push    r14
0x14001ac27  sub     rsp, 30h
0x14001ac2b  mov     rsi, rdx
0x14001ac2e  mov     rbp, rcx
0x14001ac31  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ac38  lea     r14, WPP_GLOBAL_Control
0x14001ac3f  cmp     rbx, r14
0x14001ac42  jz      loc_14001AD03
0x14001ac48  test    dword ptr [rbx+2Ch], 4000h
0x14001ac4f  jz      short loc_14001AC78
0x14001ac51  mov     rbx, [rbx+18h]
0x14001ac55  call    cs:__imp_PsGetCurrentThreadId
0x14001ac5c  nop     dword ptr [rax+rax+00h]
0x14001ac61  mov     edx, 0Ah
0x14001ac66  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001ac6d  mov     r9, rax
0x14001ac70  mov     rcx, rbx
0x14001ac73  call    WPP_SF_q
0x14001ac78  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ac7f  cmp     rbx, r14
0x14001ac82  jz      short loc_14001AD03
0x14001ac84  test    dword ptr [rbx+2Ch], 2000h
0x14001ac8b  jz      short loc_14001ACBE
0x14001ac8d  mov     rbx, [rbx+18h]
0x14001ac91  call    cs:__imp_PsGetCurrentThreadId
0x14001ac98  nop     dword ptr [rax+rax+00h]
0x14001ac9d  mov     edx, 0Bh
0x14001aca2  mov     [rsp+58h+var_30], rsi
0x14001aca7  mov     r9, rax
0x14001acaa  mov     [rsp+58h+var_38], rbp
0x14001acaf  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001acb6  mov     rcx, rbx
0x14001acb9  call    WPP_SF_qqq
0x14001acbe  mov     rdi, cs:WPP_GLOBAL_Control
0x14001acc5  cmp     rdi, r14
0x14001acc8  jz      short loc_14001AD03
0x14001acca  test    dword ptr [rdi+2Ch], 4000h
0x14001acd1  jz      short loc_14001AD03
0x14001acd3  mov     rbx, [rbp+40h]
0x14001acd7  mov     rdi, [rdi+18h]
0x14001acdb  call    cs:__imp_PsGetCurrentThreadId
0x14001ace2  nop     dword ptr [rax+rax+00h]
0x14001ace7  mov     edx, 0Ch
0x14001acec  mov     [rsp+58h+var_38], rbx
0x14001acf1  mov     r9, rax
0x14001acf4  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001acfb  mov     rcx, rdi
0x14001acfe  call    WPP_SF_qZ
0x14001ad03  mov     edx, 28h ; '('
0x14001ad08  mov     dword ptr [rbp+64h], 96h
0x14001ad0f  mov     r8d, 63535644h
0x14001ad15  lea     ecx, [rdx+1Ah]
0x14001ad18  call    cs:__imp_ExAllocatePool2
0x14001ad1f  nop     dword ptr [rax+rax+00h]
0x14001ad24  mov     [rbp+20h], rax
0x14001ad28  test    rax, rax
0x14001ad2b  jnz     short loc_14001AD75
0x14001ad2d  mov     rbx, cs:WPP_GLOBAL_Control
0x14001ad34  cmp     rbx, r14
0x14001ad37  jz      short loc_14001AD69
0x14001ad39  test    dword ptr [rbx+2Ch], 2000h
0x14001ad40  jz      short loc_14001AD69
0x14001ad42  mov     rbx, [rbx+18h]
0x14001ad46  call    cs:__imp_PsGetCurrentThreadId
0x14001ad4d  nop     dword ptr [rax+rax+00h]
0x14001ad52  mov     edx, 0Dh
0x14001ad57  lea     r8, WPP_9f6b857bdcc233f5ea08fff8764f28e7_Traceguids
0x14001ad5e  mov     r9, rax
0x14001ad61  mov     rcx, rbx
0x14001ad64  call    WPP_SF_q
0x14001ad69  mov     dword ptr [rsi+118h], 0C000009Ah
0x14001ad73  jmp     short loc_14001ADF2
0x14001ad75  xorps   xmm0, xmm0
0x14001ad78  xor     ecx, ecx
0x14001ad7a  movups  xmmword ptr [rax], xmm0
0x14001ad7d  movups  xmmword ptr [rax+10h], xmm0
0x14001ad81  mov     [rax+20h], rcx
0x14001ad85  mov     rdi, [rsi+20h]
0x14001ad89  mov     rbx, [rbp+20h]
0x14001ad8d  call    cs:__imp_IoGetCurrentProcess
0x14001ad94  nop     dword ptr [rax+rax+00h]
0x14001ad99  mov     [rbx+8], rax
0x14001ad9d  lea     r8, [rbx+18h]
0x14001ada1  mov     rax, gs:188h
0x14001adaa  mov     edx, 63535644h
0x14001adaf  mov     rcx, rdi
0x14001adb2  mov     [rbx+10h], rax
0x14001adb6  call    MRxDAVGetCompletePathName
0x14001adbb  test    eax, eax
0x14001adbd  js      short loc_14001AD69
0x14001adbf  mov     [rdi+0D8h], rsi
0x14001adc6  lea     r8, MRxDAVSrvCallWrapper; Routine
0x14001adcd  mov     rcx, cs:g_MRxDAVDeviceObject; pMRxDeviceObject
0x14001add4  mov     r9, rdi; pContext
0x14001add7  mov     edx, 1; WorkQueueType
0x14001addc  call    cs:__imp_RxDispatchToWorkerThread
0x14001ade3  nop     dword ptr [rax+rax+00h]
0x14001ade8  test    eax, eax
0x14001adea  jz      short loc_14001AE01
0x14001adec  mov     [rsi+118h], eax
0x14001adf2  mov     rax, [rsi+110h]
0x14001adf9  mov     rcx, rsi
0x14001adfc  call    _guard_dispatch_icall
0x14001ae01  mov     eax, 103h
0x14001ae06  add     rsp, 30h
0x14001ae0a  pop     r14
0x14001ae0c  pop     rdi
0x14001ae0d  pop     rsi
0x14001ae0e  pop     rbp
0x14001ae0f  pop     rbx
0x14001ae10  retn
```
