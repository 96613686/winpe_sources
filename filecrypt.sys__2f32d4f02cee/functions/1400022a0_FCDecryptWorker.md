# FCDecryptWorker

- ea: `0x1400022a0`
- end: `0x140002528`
- name: `FCDecryptWorker`
- size: `648`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _QWORD *Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002580`

## callees

- `0x1400022a0`
- `0x140002fd0`
- `0x140003028`
- `0x14000320c`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400024a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003e67`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400024a6`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140003e67`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002505`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002505`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000231d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000231d`
- `FLTMGR!FltGetFsZeroingOffset` at `0x14000237c`
- `FLTMGR!FltGetFsZeroingOffset` at `0x14000237c`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400024f1`
- `FLTMGR!FltFreeGenericWorkItem` at `0x1400024f1`
- `FLTMGR!FltLockUserBuffer` at `0x1400023ae`
- `FLTMGR!FltLockUserBuffer` at `0x1400023ae`
- `FLTMGR!FltReleaseContext` at `0x140002480`
- `FLTMGR!FltReleaseContext` at `0x140002490`
- `FLTMGR!FltReleaseContext` at `0x140003e41`
- `FLTMGR!FltReleaseContext` at `0x140003e51`
- `FLTMGR!FltReleaseContext` at `0x140002480`
- `FLTMGR!FltReleaseContext` at `0x140002490`
- `FLTMGR!FltReleaseContext` at `0x140003e41`
- `FLTMGR!FltReleaseContext` at `0x140003e51`
- `FLTMGR!FltCompletePendedPostOperation` at `0x1400024e2`
- `FLTMGR!FltCompletePendedPostOperation` at `0x1400024e2`

## pseudocode

```c
void __fastcall FCDecryptWorker(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _QWORD *Context)
{
  _QWORD *v3; // rsi
  __int64 v5; // r14
  __int64 *v6; // r13
  void ***v7; // r15
  __int64 v8; // rcx
  UCHAR *v9; // rsi
  __int64 v10; // r9
  int v11; // ebx
  void *v12; // rdx
  int FsZeroingOffset; // eax
  NTSTATUS v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned int v19; // [rsp+B8h] [rbp+20h] BYREF

  v3 = Context;
  v5 = *Context;
  v6 = *(__int64 **)(*Context + 16LL);
  v7 = (void ***)Context[1];
  v19 = 0;
  v8 = v6[7];
  if ( v8 )
  {
LABEL_2:
    if ( (*(_BYTE *)(v8 + 10) & 5) != 0 )
      v9 = *(UCHAR **)(v8 + 24);
    else
      v9 = (UCHAR *)MmMapLockedPagesSpecifyCache((PMDL)v8, 0, MmCached, 0, 0, 0x40000010u);
    if ( !v9 )
    {
      v10 = 3221225626LL;
      v11 = -1073741670;
      if ( (Microsoft_Windows_FileCryptEnableBits & 1) == 0 )
      {
LABEL_19:
        v3 = Context;
        goto LABEL_20;
      }
      v12 = &GetSystemAddressFailure;
LABEL_8:
      McTemplateK0d_EtwWriteTransfer(v8, v12, Context, v10);
      goto LABEL_19;
    }
    goto LABEL_11;
  }
  if ( (*(_DWORD *)v5 & 8) == 0 )
  {
    v14 = FltLockUserBuffer((PFLT_CALLBACK_DATA)v5);
    v11 = v14;
    if ( v14 < 0 )
    {
      if ( (Microsoft_Windows_FileCryptEnableBits & 1) != 0 )
        McTemplateK0d_EtwWriteTransfer(v15, &LockUserBufferFailure, Context, (unsigned int)v14);
      goto LABEL_20;
    }
    v8 = v6[7];
    goto LABEL_2;
  }
  v9 = (UCHAR *)v6[6];
LABEL_11:
  FsZeroingOffset = FltGetFsZeroingOffset(v5, &v19);
  v11 = FsZeroingOffset;
  if ( FsZeroingOffset < 0 )
  {
    if ( (Microsoft_Windows_FileCryptEnableBits & 1) == 0 )
      goto LABEL_19;
    v10 = (unsigned int)FsZeroingOffset;
    v12 = &GetFsZeroingOffsetFailure;
    goto LABEL_8;
  }
  v11 = FCpEncDecrypt(
          (__int64)(*v7 + 3),
          v7[1],
          v9,
          v9,
          -*((_DWORD *)*v7 + 4) & (unsigned int)(*((_DWORD *)*v7 + 4) + *(_DWORD *)(v5 + 32) - 1),
          v6[5],
          v19);
  v3 = Context;
LABEL_20:
  FltReleaseContext(*v7);
  FltReleaseContext(v7[1]);
  ExFreeToNPagedLookasideList(&gPre2PostIoContextList, v7);
  if ( v11 < 0 )
  {
    *(_DWORD *)(v5 + 24) = v11;
    *(_QWORD *)(v5 + 32) = 0;
    if ( (Microsoft_Windows_FileCryptEnableBits & 2) != 0 )
      McTemplateK0d_EtwWriteTransfer(v16, &DecryptWorkerFailure, v17, (unsigned int)v11);
  }
  if ( FltWorkItem )
  {
    FltCompletePendedPostOperation((PFLT_CALLBACK_DATA)v5);
    FltFreeGenericWorkItem(FltWorkItem);
    ExFreePoolWithTag(v3, 0x63644346u);
  }
}

```

## disassembly

```asm
0x1400022a0  mov     rax, rsp
0x1400022a3  mov     [rax+10h], rbx
0x1400022a7  mov     [rax+18h], r8
0x1400022ab  mov     [rax+8], rcx
0x1400022af  push    rsi
0x1400022b0  push    r12
0x1400022b2  push    r13
0x1400022b4  push    r14
0x1400022b6  push    r15
0x1400022b8  sub     rsp, 70h
0x1400022bc  mov     rsi, r8
0x1400022bf  mov     r12, rcx
0x1400022c2  mov     r14, [r8]
0x1400022c5  mov     [rsp+98h+var_48], r14
0x1400022ca  mov     [rsp+98h+var_30], r14
0x1400022cf  mov     r13, [r14+10h]
0x1400022d3  mov     r15, [r8+8]
0x1400022d7  mov     [rsp+98h+var_40], r15
0x1400022dc  mov     [rsp+98h+var_38], r15
0x1400022e1  mov     dword ptr [rax+20h], 0
0x1400022e8  mov     dword ptr [rax-58h], 0
0x1400022ef  mov     rcx, [r13+38h]; MemoryDescriptorList
0x1400022f3  test    rcx, rcx
0x1400022f6  jz      short loc_140002361
0x1400022f8  test    byte ptr [rcx+0Ah], 5
0x1400022fc  jz      short loc_140002304
0x1400022fe  mov     rsi, [rcx+18h]
0x140002302  jmp     short loc_14000232C
0x140002304  mov     [rsp+98h+Priority], 40000010h; Priority
0x14000230c  mov     [rsp+98h+BugCheckOnFailure], 0; BugCheckOnFailure
0x140002314  xor     r9d, r9d; RequestedAddress
0x140002317  xor     edx, edx; AccessMode
0x140002319  lea     r8d, [r9+1]; CacheType
0x14000231d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140002324  nop     dword ptr [rax+rax+00h]
0x140002329  mov     rsi, rax
0x14000232c  mov     [rsp+98h+var_50], rsi
0x140002331  test    rsi, rsi
0x140002334  jnz     short loc_140002371
0x140002336  mov     r9d, 0C000009Ah
0x14000233c  mov     ebx, r9d
0x14000233f  mov     [rsp+98h+var_58], ebx
0x140002343  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x14000234a  jz      loc_140002475
0x140002350  lea     rdx, GetSystemAddressFailure
0x140002357  call    McTemplateK0d_EtwWriteTransfer
0x14000235c  jmp     loc_140002475
0x140002361  mov     eax, [r14]
0x140002364  test    al, 8
0x140002366  jz      short loc_1400023AB
0x140002368  mov     rsi, [r13+30h]
0x14000236c  mov     [rsp+98h+var_50], rsi
0x140002371  lea     rdx, [rsp+98h+arg_18]
0x140002379  mov     rcx, r14
0x14000237c  call    cs:__imp_FltGetFsZeroingOffset
0x140002383  nop     dword ptr [rax+rax+00h]
0x140002388  mov     ebx, eax
0x14000238a  mov     [rsp+98h+var_58], eax
0x14000238e  test    eax, eax
0x140002390  jns     short loc_1400023EE
0x140002392  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x140002399  jz      loc_140002475
0x14000239f  mov     r9d, eax
0x1400023a2  lea     rdx, GetFsZeroingOffsetFailure
0x1400023a9  jmp     short loc_140002357
0x1400023ab  mov     rcx, r14; CallbackData
0x1400023ae  call    cs:__imp_FltLockUserBuffer
0x1400023b5  nop     dword ptr [rax+rax+00h]
0x1400023ba  mov     ebx, eax
0x1400023bc  mov     [rsp+98h+var_58], eax
0x1400023c0  test    eax, eax
0x1400023c2  jns     short loc_1400023E5
0x1400023c4  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x1400023cb  jz      loc_14000247D
0x1400023d1  mov     r9d, eax
0x1400023d4  lea     rdx, LockUserBufferFailure
0x1400023db  call    McTemplateK0d_EtwWriteTransfer
0x1400023e0  jmp     loc_14000247D
0x1400023e5  mov     rcx, [r13+38h]
0x1400023e9  jmp     loc_1400022F8
0x1400023ee  mov     r8, [r15]
0x1400023f1  mov     ecx, [r8+10h]
0x1400023f5  mov     edx, [r14+20h]
0x1400023f9  dec     edx
0x1400023fb  add     edx, ecx
0x1400023fd  neg     ecx
0x1400023ff  and     edx, ecx
0x140002401  lea     rcx, [r8+18h]
0x140002405  mov     eax, [rsp+98h+arg_18]
0x14000240c  mov     [rsp+98h+var_68], eax
0x140002410  mov     rax, [r13+28h]
0x140002414  mov     qword ptr [rsp+98h+Priority], rax
0x140002419  mov     [rsp+98h+BugCheckOnFailure], edx
0x14000241d  mov     r9, rsi
0x140002420  mov     r8, rsi
0x140002423  mov     rdx, [r15+8]
0x140002427  call    FCpEncDecrypt
0x14000242c  mov     ebx, eax
0x14000242e  mov     [rsp+98h+var_58], eax
0x140002432  mov     rsi, [rsp+98h+arg_10]
0x14000243a  jmp     short loc_14000247D
0x14000243c  mov     ebx, eax
0x14000243e  mov     [rsp+98h+var_58], eax
0x140002442  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 1
0x140002449  jz      short loc_140002459
0x14000244b  mov     [rsp+98h+BugCheckOnFailure], eax
0x14000244f  mov     r9, [rsp+98h+var_50]
0x140002454  call    McTemplateK0pd_EtwWriteTransfer
0x140002459  mov     r12, [rsp+98h+arg_0]
0x140002461  mov     r14, [rsp+98h+var_48]
0x140002466  mov     r15, [rsp+98h+var_40]
0x14000246b  mov     rsi, [rsp+98h+arg_10]
0x140002473  jmp     short loc_14000247D
0x140002475  mov     rsi, [rsp+98h+arg_10]
0x14000247d  mov     rcx, [r15]; Context
0x140002480  call    cs:__imp_FltReleaseContext
0x140002487  nop     dword ptr [rax+rax+00h]
0x14000248c  mov     rcx, [r15+8]; Context
0x140002490  call    cs:__imp_FltReleaseContext
0x140002497  nop     dword ptr [rax+rax+00h]
0x14000249c  mov     rdx, r15; Entry
0x14000249f  lea     rcx, gPre2PostIoContextList; Lookaside
0x1400024a6  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400024ad  nop     dword ptr [rax+rax+00h]
0x1400024b2  test    ebx, ebx
0x1400024b4  jns     short loc_1400024DA
0x1400024b6  mov     [r14+18h], ebx
0x1400024ba  mov     qword ptr [r14+20h], 0
0x1400024c2  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 2
0x1400024c9  jz      short loc_1400024DA
0x1400024cb  mov     r9d, ebx
0x1400024ce  lea     rdx, DecryptWorkerFailure
0x1400024d5  call    McTemplateK0d_EtwWriteTransfer
0x1400024da  test    r12, r12
0x1400024dd  jz      short loc_140002511
0x1400024df  mov     rcx, r14; CallbackData
0x1400024e2  call    cs:__imp_FltCompletePendedPostOperation
0x1400024e9  nop     dword ptr [rax+rax+00h]
0x1400024ee  mov     rcx, r12; FltWorkItem
0x1400024f1  call    cs:__imp_FltFreeGenericWorkItem
0x1400024f8  nop     dword ptr [rax+rax+00h]
0x1400024fd  mov     edx, 63644346h; Tag
0x140002502  mov     rcx, rsi; P
0x140002505  call    cs:__imp_ExFreePoolWithTag
0x14000250c  nop     dword ptr [rax+rax+00h]
0x140002511  mov     rbx, [rsp+98h+arg_8]
0x140002519  add     rsp, 70h
0x14000251d  pop     r15
0x14000251f  pop     r14
0x140002521  pop     r13
0x140002523  pop     r12
0x140002525  pop     rsi
0x140002526  retn
0x140003e30  push    rbx
0x140003e32  push    rbp
0x140003e33  sub     rsp, 48h
0x140003e37  mov     rbp, rdx
0x140003e3a  mov     rbx, [rbp+60h]
0x140003e3e  mov     rcx, [rbx]; Context
0x140003e41  call    cs:__imp_FltReleaseContext
0x140003e48  nop     dword ptr [rax+rax+00h]
0x140003e4d  mov     rcx, [rbx+8]; Context
0x140003e51  call    cs:__imp_FltReleaseContext
0x140003e58  nop     dword ptr [rax+rax+00h]
0x140003e5d  mov     rdx, rbx; Entry
0x140003e60  lea     rcx, gPre2PostIoContextList; Lookaside
0x140003e67  call    cs:__imp_ExFreeToNPagedLookasideList
0x140003e6e  nop     dword ptr [rax+rax+00h]
0x140003e73  mov     r9d, [rbp+40h]
0x140003e77  test    r9d, r9d
0x140003e7a  jns     short loc_140003EA2
0x140003e7c  mov     rax, [rbp+68h]
0x140003e80  mov     [rax+18h], r9d
0x140003e84  mov     qword ptr [rax+20h], 0
0x140003e8c  test    byte ptr cs:Microsoft_Windows_FileCryptEnableBits, 2
0x140003e93  jz      short loc_140003EA2
0x140003e95  lea     rdx, DecryptWorkerFailure
0x140003e9c  call    McTemplateK0d_EtwWriteTransfer
0x140003ea1  nop
0x140003ea2  add     rsp, 48h
0x140003ea6  pop     rbp
0x140003ea7  pop     rbx
0x140003ea8  retn
```
