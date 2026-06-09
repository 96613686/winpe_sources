# BfsPostCleanupOperation

- ea: `0x1400017d0`
- end: `0x140001b98`
- name: `BfsPostCleanupOperation`
- size: `968`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001320`
- `0x1400017d0`
- `0x140013860`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001926`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140001926`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001a1b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140001a1b`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400018cb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001947`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400018cb`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140001947`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400018f9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400019fa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001a29`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400018f9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400019fa`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140001a29`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001a54`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001b4f`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001a54`
- `ntoskrnl!ExReleaseRundownProtection` at `0x140001b4f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001911`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001932`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001a41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b3c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018b6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001911`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001932`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001a41`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001b3c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001905`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b5b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001905`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a06`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a35`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001a60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001b5b`
- `ntoskrnl!EtwWriteTransfer` at `0x140001b2b`
- `ntoskrnl!EtwWriteTransfer` at `0x140001b2b`
- `FLTMGR!FltReleaseContext` at `0x140001b6f`
- `FLTMGR!FltReleaseContext` at `0x140001b6f`
- `FLTMGR!FltQueryInformationFile` at `0x140001852`
- `FLTMGR!FltQueryInformationFile` at `0x140001852`
- `FLTMGR!FltFsControlFile` at `0x140001899`
- `FLTMGR!FltFsControlFile` at `0x140001899`

## pseudocode

```c
__int64 __fastcall BfsPostCleanupOperation(__int64 a1, __int64 a2, _QWORD *a3)
{
  NTSTATUS v6; // eax
  __int64 v7; // rdi
  __int64 GlobalFileEntry; // rax
  __int64 v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // r8
  _QWORD *v13; // rdx
  _DWORD v15[2]; // [rsp+40h] [rbp-79h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-71h] BYREF
  __int128 FileInformation; // [rsp+58h] [rbp-61h] BYREF
  __int64 v18; // [rsp+68h] [rbp-51h]
  struct _EVENT_DATA_DESCRIPTOR OutputBuffer[4]; // [rsp+70h] [rbp-49h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+B0h] [rbp-9h] BYREF
  int *v21; // [rsp+C0h] [rbp+7h]
  int v22; // [rsp+C8h] [rbp+Fh]
  int v23; // [rsp+CCh] [rbp+13h]
  _DWORD *v24; // [rsp+D0h] [rbp+17h]
  __int64 v25; // [rsp+D8h] [rbp+1Fh]

  v18 = 0;
  FileInformation = 0;
  memset(OutputBuffer, 0, sizeof(OutputBuffer));
  if ( a3
    && *(_BYTE *)a3
    && FltQueryInformationFile(
         *(PFLT_INSTANCE *)(a2 + 24),
         *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL),
         &FileInformation,
         0x18u,
         FileStandardInformation,
         0) == -1073741533 )
  {
    v6 = FltFsControlFile(
           *(PFLT_INSTANCE *)(a2 + 24),
           *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL),
           0x9009Cu,
           0,
           0,
           OutputBuffer,
           0x40u,
           0);
    if ( v6 == -1073741533 )
    {
      v7 = a3[1];
      KeEnterCriticalRegion();
      ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
      if ( BfsGetGlobalFileEntry(&gBfsGlobalFileTable, v7 + 8) )
      {
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
        KeLeaveCriticalRegion();
        KeEnterCriticalRegion();
        ExAcquirePushLockExclusiveEx(&qword_140019168, 0);
        KeEnterCriticalRegion();
        ExAcquirePushLockSharedEx(&gBfsGlobalFileTable, 0);
        GlobalFileEntry = BfsGetGlobalFileEntry(&gBfsGlobalFileTable, v7 + 8);
        v9 = GlobalFileEntry;
        if ( GlobalFileEntry )
        {
          if ( *(_BYTE *)(GlobalFileEntry + 40) == 1 )
          {
            *(_BYTE *)(GlobalFileEntry + 40) = 0;
            v10 = (_QWORD *)(GlobalFileEntry + 24);
            v11 = *v10;
            if ( *(_QWORD **)(*v10 + 8LL) != v10 || (v12 = (_QWORD *)v10[1], (_QWORD *)*v12 != v10) )
LABEL_12:
              __fastfail(3u);
            *v12 = v11;
            *(_QWORD *)(v11 + 8) = v12;
            *v10 = 0;
            *(_QWORD *)(v9 + 32) = 0;
            *(_QWORD *)(v9 + 48) = 0;
            *(_QWORD *)(v9 + 56) = 0;
          }
          *(_BYTE *)(v9 + 40) = 1;
          *(_QWORD *)(v9 + 48) = qword_1400191A0;
          *(_QWORD *)(v9 + 56) = MEMORY[0xFFFFF78000000014];
          v13 = (_QWORD *)qword_140019198;
          if ( *(__int64 **)qword_140019198 != &qword_140019190 )
            goto LABEL_12;
          *(_QWORD *)(v9 + 24) = &qword_140019190;
          *(_QWORD *)(v9 + 32) = v13;
          *v13 = v9 + 24;
          qword_140019198 = v9 + 24;
        }
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
        KeLeaveCriticalRegion();
        ExReleasePushLockExclusiveEx(&qword_140019168, 0);
      }
      else
      {
        ExReleasePushLockSharedEx(&gBfsGlobalFileTable, 0);
      }
      KeLeaveCriticalRegion();
      goto LABEL_17;
    }
    if ( (int)(v6 + 0x80000000) >= 0 && v6 != -1073741072 )
    {
      if ( (unsigned int)dword_140019000 > 3 )
      {
        v15[0] = v6;
        v24 = v15;
        UserData.Ptr = (ULONGLONG)EventInformation;
        *(_DWORD *)&EventDescriptor.Level = 3;
        v25 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)EventInformation;
        v21 = &dword_140016D9C;
        UserData.Reserved = 2;
        v22 = 30;
        v23 = 1;
        v15[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
LABEL_17:
      KeEnterCriticalRegion();
      ExReleaseRundownProtection(&gBfsRundownProtection);
      KeLeaveCriticalRegion();
LABEL_23:
      FltReleaseContext(a3);
      return 0;
    }
  }
  KeEnterCriticalRegion();
  ExReleaseRundownProtection(&gBfsRundownProtection);
  KeLeaveCriticalRegion();
  if ( a3 )
    goto LABEL_23;
  return 0;
}

```

## disassembly

```asm
0x1400017d0  push    rbp
0x1400017d2  push    rbx
0x1400017d3  push    rsi
0x1400017d4  push    rdi
0x1400017d5  push    r14
0x1400017d7  lea     rbp, [rsp-37h]
0x1400017dc  sub     rsp, 0F0h
0x1400017e3  mov     rax, cs:__security_cookie
0x1400017ea  xor     rax, rsp
0x1400017ed  mov     [rbp+57h+var_30], rax
0x1400017f1  xorps   xmm1, xmm1
0x1400017f4  xor     eax, eax
0x1400017f6  mov     [rbp+57h+var_A8], rax
0x1400017fa  xorps   xmm0, xmm0
0x1400017fd  mov     rbx, r8
0x140001800  mov     rsi, rdx
0x140001803  mov     rdi, rcx
0x140001806  movups  [rbp+57h+FileInformation], xmm0
0x14000180a  movups  [rbp+57h+OutputBuffer], xmm1
0x14000180e  movups  [rbp+57h+var_90], xmm1
0x140001812  movups  [rbp+57h+var_80], xmm1
0x140001816  movups  [rbp+57h+var_70], xmm1
0x14000181a  test    r8, r8
0x14000181d  jz      loc_140001B3C
0x140001823  cmp     [r8], al
0x140001826  jz      loc_140001B3C
0x14000182c  mov     rdx, [rcx+10h]
0x140001830  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140001834  mov     rcx, [rsi+18h]; Instance
0x140001838  xor     r14d, r14d
0x14000183b  mov     [rsp+110h+LengthReturned], r14; LengthReturned
0x140001840  mov     r9d, 18h; Length
0x140001846  mov     [rsp+110h+FileInformationClass], 5; FileInformationClass
0x14000184e  mov     rdx, [rdx+8]; FileObject
0x140001852  call    cs:__imp_FltQueryInformationFile
0x140001859  nop     dword ptr [rax+rax+00h]
0x14000185e  cmp     eax, 0C0000123h
0x140001863  jnz     loc_140001B3C
0x140001869  mov     rdx, [rdi+10h]
0x14000186d  lea     rax, [rbp+57h+OutputBuffer]
0x140001871  mov     rcx, [rsi+18h]; Instance
0x140001875  xor     r9d, r9d; InputBuffer
0x140001878  mov     [rsp+110h+var_D8], r14; LengthReturned
0x14000187d  mov     r8d, 9009Ch; FsControlCode
0x140001883  mov     [rsp+110h+OutputBufferLength], 40h ; '@'; OutputBufferLength
0x14000188b  mov     rdx, [rdx+8]; FileObject
0x14000188f  mov     [rsp+110h+LengthReturned], rax; OutputBuffer
0x140001894  mov     [rsp+110h+FileInformationClass], r14d; InputBufferLength
0x140001899  call    cs:__imp_FltFsControlFile
0x1400018a0  nop     dword ptr [rax+rax+00h]
0x1400018a5  mov     ecx, eax
0x1400018a7  cmp     eax, 0C0000123h
0x1400018ac  jnz     loc_140001A71
0x1400018b2  mov     rdi, [rbx+8]
0x1400018b6  call    cs:__imp_KeEnterCriticalRegion
0x1400018bd  nop     dword ptr [rax+rax+00h]
0x1400018c2  xor     edx, edx
0x1400018c4  lea     rcx, gBfsGlobalFileTable
0x1400018cb  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400018d2  nop     dword ptr [rax+rax+00h]
0x1400018d7  lea     rdx, [rdi+8]
0x1400018db  lea     rcx, gBfsGlobalFileTable
0x1400018e2  call    BfsGetGlobalFileEntry
0x1400018e7  xor     edx, edx
0x1400018e9  lea     rcx, gBfsGlobalFileTable
0x1400018f0  test    rax, rax
0x1400018f3  jz      loc_140001A29
0x1400018f9  call    cs:__imp_ExReleasePushLockSharedEx
0x140001900  nop     dword ptr [rax+rax+00h]
0x140001905  call    cs:__imp_KeLeaveCriticalRegion
0x14000190c  nop     dword ptr [rax+rax+00h]
0x140001911  call    cs:__imp_KeEnterCriticalRegion
0x140001918  nop     dword ptr [rax+rax+00h]
0x14000191d  xor     edx, edx
0x14000191f  lea     rcx, qword_140019168
0x140001926  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000192d  nop     dword ptr [rax+rax+00h]
0x140001932  call    cs:__imp_KeEnterCriticalRegion
0x140001939  nop     dword ptr [rax+rax+00h]
0x14000193e  xor     edx, edx
0x140001940  lea     rcx, gBfsGlobalFileTable
0x140001947  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000194e  nop     dword ptr [rax+rax+00h]
0x140001953  lea     rdx, [rdi+8]
0x140001957  lea     rcx, gBfsGlobalFileTable
0x14000195e  call    BfsGetGlobalFileEntry
0x140001963  mov     rcx, rax
0x140001966  test    rax, rax
0x140001969  jz      loc_1400019F1
0x14000196f  cmp     byte ptr [rax+28h], 1
0x140001973  jnz     short loc_1400019A5
0x140001975  mov     [rax+28h], r14b
0x140001979  add     rax, 18h
0x14000197d  mov     rdx, [rax]
0x140001980  cmp     [rdx+8], rax
0x140001984  jnz     short loc_1400019D5
0x140001986  mov     r8, [rax+8]
0x14000198a  cmp     [r8], rax
0x14000198d  jnz     short loc_1400019D5
0x14000198f  mov     [r8], rdx
0x140001992  mov     [rdx+8], r8
0x140001996  mov     [rax], r14
0x140001999  mov     [rcx+20h], r14
0x14000199d  mov     [rcx+30h], r14
0x1400019a1  mov     [rcx+38h], r14
0x1400019a5  mov     byte ptr [rcx+28h], 1
0x1400019a9  lea     r8, qword_140019190
0x1400019b0  mov     rax, cs:qword_1400191A0
0x1400019b7  mov     [rcx+30h], rax
0x1400019bb  mov     rax, ds:0FFFFF78000000014h
0x1400019c5  mov     [rcx+38h], rax
0x1400019c9  mov     rdx, cs:qword_140019198
0x1400019d0  cmp     [rdx], r8
0x1400019d3  jz      short loc_1400019DC
0x1400019d5  mov     ecx, 3
0x1400019da  int     29h; Win8: RtlFailFast(ecx)
0x1400019dc  lea     rax, [rcx+18h]
0x1400019e0  mov     [rax], r8
0x1400019e3  mov     [rax+8], rdx
0x1400019e7  mov     [rdx], rax
0x1400019ea  mov     cs:qword_140019198, rax
0x1400019f1  xor     edx, edx
0x1400019f3  lea     rcx, gBfsGlobalFileTable
0x1400019fa  call    cs:__imp_ExReleasePushLockSharedEx
0x140001a01  nop     dword ptr [rax+rax+00h]
0x140001a06  call    cs:__imp_KeLeaveCriticalRegion
0x140001a0d  nop     dword ptr [rax+rax+00h]
0x140001a12  xor     edx, edx
0x140001a14  lea     rcx, qword_140019168
0x140001a1b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140001a22  nop     dword ptr [rax+rax+00h]
0x140001a27  jmp     short loc_140001A35
0x140001a29  call    cs:__imp_ExReleasePushLockSharedEx
0x140001a30  nop     dword ptr [rax+rax+00h]
0x140001a35  call    cs:__imp_KeLeaveCriticalRegion
0x140001a3c  nop     dword ptr [rax+rax+00h]
0x140001a41  call    cs:__imp_KeEnterCriticalRegion
0x140001a48  nop     dword ptr [rax+rax+00h]
0x140001a4d  lea     rcx, gBfsRundownProtection; RunRef
0x140001a54  call    cs:__imp_ExReleaseRundownProtection
0x140001a5b  nop     dword ptr [rax+rax+00h]
0x140001a60  call    cs:__imp_KeLeaveCriticalRegion
0x140001a67  nop     dword ptr [rax+rax+00h]
0x140001a6c  jmp     loc_140001B6C
0x140001a71  mov     edx, 80000000h
0x140001a76  add     eax, edx
0x140001a78  test    edx, eax
0x140001a7a  jnz     loc_140001B3C
0x140001a80  cmp     ecx, 0C00002F0h
0x140001a86  jz      loc_140001B3C
0x140001a8c  mov     eax, cs:dword_140019000
0x140001a92  cmp     eax, 3
0x140001a95  jbe     short loc_140001A41
0x140001a97  mov     [rbp+57h+var_D0], ecx
0x140001a9a  lea     rax, [rbp+57h+var_D0]
0x140001a9e  mov     [rbp+57h+var_40], rax
0x140001aa2  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x140001aa6  mov     rax, cs:qword_140016D92
0x140001aad  xor     r9d, r9d; RelatedActivityId
0x140001ab0  movzx   ecx, ax
0x140001ab3  xor     r8d, r8d; ActivityId
0x140001ab6  mov     rax, cs:EventInformation
0x140001abd  mov     [rbp+57h+UserData.Ptr], rax
0x140001ac1  mov     dword ptr [rbp+57h+EventDescriptor.Level], ecx
0x140001ac4  lea     rcx, _TraceLoggingMetadata
0x140001acb  mov     [rbp+57h+var_38], 4
0x140001ad3  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x140001ada  mov     [rbp+57h+EventDescriptor.Keyword], r14
0x140001ade  movzx   eax, word ptr [rax]
0x140001ae1  mov     [rbp+57h+UserData.Size], eax
0x140001ae4  lea     rax, dword_140016D9C
0x140001aeb  mov     [rbp+57h+var_50], rax
0x140001aef  lea     rax, _TraceLoggingMetadataEnd
0x140001af6  sub     eax, ecx
0x140001af8  mov     dword ptr [rbp+57h+UserData.0Ch], 2
0x140001aff  mov     [rbp+57h+var_48], 1Eh
0x140001b06  mov     [rbp+57h+var_44], 1
0x140001b0d  mov     [rbp+57h+var_CC], eax
0x140001b10  mov     eax, [rbp+57h+var_CC]
0x140001b13  mov     rcx, cs:RegHandle; RegHandle
0x140001b1a  lea     rax, [rbp+57h+UserData]
0x140001b1e  mov     [rsp+110h+LengthReturned], rax; UserData
0x140001b23  mov     [rsp+110h+FileInformationClass], 3; UserDataCount
0x140001b2b  call    cs:__imp_EtwWriteTransfer
0x140001b32  nop     dword ptr [rax+rax+00h]
0x140001b37  jmp     loc_140001A41
0x140001b3c  call    cs:__imp_KeEnterCriticalRegion
0x140001b43  nop     dword ptr [rax+rax+00h]
0x140001b48  lea     rcx, gBfsRundownProtection; RunRef
0x140001b4f  call    cs:__imp_ExReleaseRundownProtection
0x140001b56  nop     dword ptr [rax+rax+00h]
0x140001b5b  call    cs:__imp_KeLeaveCriticalRegion
0x140001b62  nop     dword ptr [rax+rax+00h]
0x140001b67  test    rbx, rbx
0x140001b6a  jz      short loc_140001B7B
0x140001b6c  mov     rcx, rbx; Context
0x140001b6f  call    cs:__imp_FltReleaseContext
0x140001b76  nop     dword ptr [rax+rax+00h]
0x140001b7b  xor     eax, eax
0x140001b7d  mov     rcx, [rbp+57h+var_30]
0x140001b81  xor     rcx, rsp; StackCookie
0x140001b84  call    __security_check_cookie
0x140001b89  add     rsp, 0F0h
0x140001b90  pop     r14
0x140001b92  pop     rdi
0x140001b93  pop     rsi
0x140001b94  pop     rbx
0x140001b95  pop     rbp
0x140001b96  retn
```
