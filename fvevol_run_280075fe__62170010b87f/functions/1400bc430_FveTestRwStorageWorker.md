# FveTestRwStorageWorker

- ea: `0x1400bc430`
- end: `0x1400bc84a`
- name: `FveTestRwStorageWorker`
- size: `1050`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140006670`
- `0x140009bf4`
- `0x140021a00`
- `0x1400bbe7c`
- `0x1400bbf98`
- `0x1400bc430`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400bc51f`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400bc51f`
- `ntoskrnl!IofCompleteRequest` at `0x1400bc7e9`
- `ntoskrnl!IofCompleteRequest` at `0x1400bc7e9`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc59f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc7d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc825`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc59f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc7d8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bc825`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc53e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc7a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc7fd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc53e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc7a4`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc7fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bc6ed`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400bc6ed`

## pseudocode

```c
void __fastcall FveTestRwStorageWorker(PDEVICE_OBJECT DeviceObject, _QWORD *Context)
{
  __int64 v2; // rbx
  __int64 v3; // rbp
  __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // rsi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  _QWORD *v10; // rdi
  KSPIN_LOCK *v11; // r13
  KIRQL v12; // al
  char *v13; // r14
  bool v14; // si
  _QWORD *v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r11
  size_t v19; // r12
  unsigned __int64 v20; // r11
  size_t v21; // rcx
  ULONG_PTR v22; // r15
  __int64 v23; // rax
  unsigned __int64 v24; // rdx
  NTSTATUS v25; // edi
  __int64 v26; // r11
  int v27; // eax
  __int64 v28; // rcx
  PVOID v29; // rax
  __int64 v30; // r8
  const void *v31; // rdx
  void *v32; // rcx
  __int64 v33; // rcx
  IRP *v34; // r12
  KIRQL v35; // al
  __int64 v36; // r8
  _QWORD *v37; // rdx
  char *v38; // rdi
  ULONG v39; // [rsp+30h] [rbp-58h]
  ULONG TimeIncrement; // [rsp+34h] [rbp-54h]
  unsigned __int64 v41; // [rsp+38h] [rbp-50h]
  unsigned __int64 v42; // [rsp+40h] [rbp-48h]
  __int64 v43; // [rsp+48h] [rbp-40h]
  ULONG pulResult; // [rsp+A0h] [rbp+18h] BYREF
  ULONG v46; // [rsp+A8h] [rbp+20h] BYREF

  v2 = 0;
  v43 = 0;
  TimeIncrement = 0;
  v41 = 0;
  v3 = *(_QWORD *)(Context[8] + 16LL);
  v42 = 0;
  v4 = *(_QWORD *)(v3 + 72);
  v39 = 0;
  pulResult = 0;
  v46 = 0;
  v5 = *(_QWORD *)(v4 + 976);
  if ( !v5 )
  {
LABEL_12:
    if ( *(_BYTE *)(v3 + 318) && (unsigned __int64)(*(_QWORD *)(v3 + 248) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      TimeIncrement = KeQueryTimeIncrement();
    goto LABEL_15;
  }
  if ( *(_BYTE *)(v3 + 318) )
  {
    v6 = *(_QWORD *)(v5 + 56);
    v41 = v6;
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(DeviceObject)
      && (*(_BYTE *)(v4 + 4403) & 8) != 0
      || (v7 = *(_QWORD *)(v4 + 976), *(_WORD *)(v7 + 10) == 1) )
    {
      v8 = 0;
    }
    else
    {
      v8 = *(unsigned int *)(v7 + 28);
      if ( !(_DWORD)v8 )
        v8 = 1;
    }
    RtlULongLongToULong(v8 * *(unsigned int *)(v4 + 1308), &pulResult);
    v9 = -1;
    v39 = pulResult;
    if ( v6 + pulResult >= v6 )
      v9 = v6 + pulResult;
    v42 = v9;
    goto LABEL_12;
  }
LABEL_15:
  v10 = Context;
  v11 = Context + 14;
  v12 = KeAcquireSpinLockRaiseToDpc(Context + 14);
  v13 = (char *)(Context + 12);
  v14 = *(_QWORD *)v13 != (_QWORD)v13;
  while ( v14 )
  {
    v15 = *(_QWORD **)v13;
    if ( *(char **)(*(_QWORD *)v13 + 8LL) != v13
      || (v16 = *v15, *(_QWORD **)(*v15 + 8LL) != v15)
      || (*(_QWORD *)v13 = v16, *(_QWORD *)(v16 + 8) = v13,
                                v17 = *(_QWORD *)v13,
                                *(char **)(*(_QWORD *)v13 + 8LL) != v13) )
    {
LABEL_58:
      __fastfail(3u);
    }
    *v15 = v17;
    v15[1] = v13;
    *(_QWORD *)(v17 + 8) = v15;
    *(_QWORD *)v13 = v15;
    KeReleaseSpinLock(v11, v12);
    v18 = v15[2];
    v19 = *(unsigned int *)(v18 + 8);
    if ( *(_BYTE *)(v3 + 318) )
    {
      LOBYTE(pulResult) = *(_BYTE *)v18;
      v20 = *(_QWORD *)(v18 + 24);
      if ( (unsigned __int64)(*(_QWORD *)(v3 + 248) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        v2 = MEMORY[0xFFFFF78000000320];
      v21 = v19 + v20;
      v22 = v19;
      if ( v39 && (unsigned int)(*(_DWORD *)(v3 + 312) - 5) > 1 )
      {
        if ( v20 < v39 || v20 < v41 && v21 > v41 || v20 < v42 && v21 > v42 )
        {
LABEL_49:
          v25 = -1073741823;
          goto LABEL_50;
        }
        if ( v20 >= v41 && v20 < v42 && v10[2] < (unsigned __int64)v39 )
        {
          v20 -= v41;
          v21 -= v41;
        }
      }
      v23 = *((unsigned int *)v10 + 20);
      if ( (unsigned int)v19 > (unsigned int)v23 )
        goto LABEL_49;
      v24 = v10[2];
      if ( v20 < v24 || v21 > v24 + v23 )
        goto LABEL_49;
      v25 = RtlULongLongToULong(v20 - v24, &v46);
      if ( v25 < 0 )
        goto LABEL_50;
      v27 = FveTestRwCheckBadSectorInRange(v3, v26, (unsigned int)v19);
      v25 = v27;
      if ( v27 == -1073741668 )
      {
        *((_BYTE *)Context + 120) = 1;
LABEL_50:
        v22 = 0;
        goto LABEL_54;
      }
      if ( v27 < 0 )
        goto LABEL_50;
      v28 = *(v15 - 20);
      if ( (*(_BYTE *)(v28 + 10) & 5) != 0 )
        v29 = *(PVOID *)(v28 + 24);
      else
        v29 = MmMapLockedPagesSpecifyCache((PMDL)v28, 0, MmCached, 0, 0, 0x40000010u);
      v30 = Context[6];
      if ( (_BYTE)pulResult == 4 )
      {
        v31 = v29;
        v32 = (void *)(v30 + v46);
      }
      else
      {
        v32 = v29;
        v31 = (const void *)(v30 + v46);
      }
      memmove(v32, v31, v19);
      if ( (unsigned __int64)(*(_QWORD *)(v3 + 248) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
        v43 = TimeIncrement * (MEMORY[0xFFFFF78000000320] - v2);
    }
    else
    {
      v25 = 0;
      v22 = *(unsigned int *)(v18 + 8);
    }
    v33 = *(_QWORD *)(v3 + 248);
    if ( (unsigned __int64)(v33 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      FveTestRwDelayData(v33, (unsigned int)v19, v43);
LABEL_54:
    v34 = (IRP *)(v15 - 21);
    v34->IoStatus.Information = v22;
    v34->IoStatus.Status = v25;
    v35 = KeAcquireSpinLockRaiseToDpc(v11);
    v36 = *v15;
    if ( *(_QWORD **)(*v15 + 8LL) != v15 )
      goto LABEL_58;
    v37 = (_QWORD *)v15[1];
    if ( (_QWORD *)*v37 != v15 )
      goto LABEL_58;
    *v37 = v36;
    *(_QWORD *)(v36 + 8) = v37;
    v38 = *(char **)v13;
    v14 = *(_QWORD *)v13 != (_QWORD)v13;
    KeReleaseSpinLock(v11, v35);
    IofCompleteRequest(v34, 1);
    if ( v38 == v13 )
      return;
    v12 = KeAcquireSpinLockRaiseToDpc(v11);
    v10 = Context;
  }
  KeReleaseSpinLock(v11, v12);
}

```

## disassembly

```asm
0x1400bc430  mov     r11, rsp
0x1400bc433  mov     [r11+8], rbx
0x1400bc437  mov     [r11+10h], rdx
0x1400bc43b  push    rbp
0x1400bc43c  push    rsi
0x1400bc43d  push    rdi
0x1400bc43e  push    r12
0x1400bc440  push    r13
0x1400bc442  push    r14
0x1400bc444  push    r15
0x1400bc446  sub     rsp, 50h
0x1400bc44a  mov     rax, [rdx+40h]
0x1400bc44e  xor     r15d, r15d
0x1400bc451  mov     ebx, r15d
0x1400bc454  mov     [rsp+88h+var_40], r15
0x1400bc459  mov     [rsp+88h+var_54], r15d
0x1400bc45e  mov     [rsp+88h+var_50], r15
0x1400bc463  mov     rbp, [rax+10h]
0x1400bc467  lea     r14d, [r15+1]
0x1400bc46b  mov     [rsp+88h+var_48], r15
0x1400bc470  mov     rdi, [rbp+48h]
0x1400bc474  mov     [r11-58h], r15d
0x1400bc478  mov     [r11+18h], r15d
0x1400bc47c  mov     [r11+20h], r15d
0x1400bc480  mov     rax, [rdi+3D0h]
0x1400bc487  test    rax, rax
0x1400bc48a  jz      short loc_1400BC506
0x1400bc48c  cmp     [rbp+13Eh], r15b
0x1400bc493  jz      loc_1400BC52F
0x1400bc499  mov     rsi, [rax+38h]
0x1400bc49d  mov     [rsp+88h+var_50], rsi
0x1400bc4a2  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400bc4a7  test    eax, eax
0x1400bc4a9  jz      short loc_1400BC4B4
0x1400bc4ab  test    byte ptr [rdi+1133h], 8
0x1400bc4b2  jnz     short loc_1400BC4C2
0x1400bc4b4  mov     rax, [rdi+3D0h]
0x1400bc4bb  cmp     [rax+0Ah], r14w
0x1400bc4c0  jnz     short loc_1400BC4C7
0x1400bc4c2  mov     eax, r15d
0x1400bc4c5  jmp     short loc_1400BC4D0
0x1400bc4c7  mov     eax, [rax+1Ch]
0x1400bc4ca  test    eax, eax
0x1400bc4cc  cmovz   eax, r14d
0x1400bc4d0  mov     ecx, [rdi+51Ch]
0x1400bc4d6  lea     rdx, [rsp+88h+pulResult]; pulResult
0x1400bc4de  imul    rcx, rax; ullOperand
0x1400bc4e2  call    RtlULongLongToULong
0x1400bc4e7  mov     eax, [rsp+88h+pulResult]
0x1400bc4ee  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400bc4f2  mov     [rsp+88h+var_58], eax
0x1400bc4f6  lea     rcx, [rsi+rax]
0x1400bc4fa  cmp     rcx, rsi
0x1400bc4fd  cmovnb  rdx, rcx
0x1400bc501  mov     [rsp+88h+var_48], rdx
0x1400bc506  cmp     [rbp+13Eh], r15b
0x1400bc50d  jz      short loc_1400BC52F
0x1400bc50f  mov     rax, [rbp+0F8h]
0x1400bc516  sub     rax, r14
0x1400bc519  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bc51d  ja      short loc_1400BC52F
0x1400bc51f  call    cs:__imp_KeQueryTimeIncrement
0x1400bc526  nop     dword ptr [rax+rax+00h]
0x1400bc52b  mov     [rsp+88h+var_54], eax
0x1400bc52f  mov     rdi, [rsp+88h+arg_8]
0x1400bc537  lea     r13, [rdi+70h]
0x1400bc53b  mov     rcx, r13; SpinLock
0x1400bc53e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc545  nop     dword ptr [rax+rax+00h]
0x1400bc54a  lea     r14, [rdi+60h]
0x1400bc54e  cmp     [r14], r14
0x1400bc551  setnz   sil
0x1400bc555  test    sil, sil
0x1400bc558  jz      loc_1400BC820
0x1400bc55e  mov     rsi, [r14]
0x1400bc561  cmp     [rsi+8], r14
0x1400bc565  jnz     loc_1400BC819
0x1400bc56b  mov     rcx, [rsi]
0x1400bc56e  cmp     [rcx+8], rsi
0x1400bc572  jnz     loc_1400BC819
0x1400bc578  mov     [r14], rcx
0x1400bc57b  mov     [rcx+8], r14
0x1400bc57f  mov     rcx, [r14]
0x1400bc582  cmp     [rcx+8], r14
0x1400bc586  jnz     loc_1400BC819
0x1400bc58c  mov     [rsi], rcx
0x1400bc58f  mov     dl, al; NewIrql
0x1400bc591  mov     [rsi+8], r14
0x1400bc595  mov     [rcx+8], rsi
0x1400bc599  mov     rcx, r13; SpinLock
0x1400bc59c  mov     [r14], rsi
0x1400bc59f  call    cs:__imp_KeReleaseSpinLock
0x1400bc5a6  nop     dword ptr [rax+rax+00h]
0x1400bc5ab  mov     r11, [rsi+10h]
0x1400bc5af  mov     r12d, [r11+8]
0x1400bc5b3  cmp     [rbp+13Eh], r15b
0x1400bc5ba  jz      loc_1400BC76C
0x1400bc5c0  mov     al, [r11]
0x1400bc5c3  mov     byte ptr [rsp+88h+pulResult], al
0x1400bc5ca  mov     rax, [rbp+0F8h]
0x1400bc5d1  mov     r11, [r11+18h]
0x1400bc5d5  dec     rax
0x1400bc5d8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bc5dc  ja      short loc_1400BC5EB
0x1400bc5de  mov     rax, 0FFFFF78000000320h
0x1400bc5e8  mov     rbx, [rax]
0x1400bc5eb  mov     edx, [rsp+88h+var_58]
0x1400bc5ef  lea     rcx, [r12+r11]
0x1400bc5f3  mov     r15, r12
0x1400bc5f6  test    edx, edx
0x1400bc5f8  jz      short loc_1400BC64F
0x1400bc5fa  mov     eax, [rbp+138h]
0x1400bc600  sub     eax, 5
0x1400bc603  cmp     eax, 1
0x1400bc606  jbe     short loc_1400BC64F
0x1400bc608  mov     eax, edx
0x1400bc60a  cmp     r11, rdx
0x1400bc60d  jb      loc_1400BC762
0x1400bc613  mov     rdx, [rsp+88h+var_50]
0x1400bc618  cmp     r11, rdx
0x1400bc61b  jnb     short loc_1400BC626
0x1400bc61d  cmp     rcx, rdx
0x1400bc620  ja      loc_1400BC762
0x1400bc626  mov     r8, [rsp+88h+var_48]
0x1400bc62b  cmp     r11, r8
0x1400bc62e  jnb     short loc_1400BC639
0x1400bc630  cmp     rcx, r8
0x1400bc633  ja      loc_1400BC762
0x1400bc639  cmp     r11, rdx
0x1400bc63c  jb      short loc_1400BC64F
0x1400bc63e  cmp     r11, r8
0x1400bc641  jnb     short loc_1400BC64F
0x1400bc643  cmp     [rdi+10h], rax
0x1400bc647  jnb     short loc_1400BC64F
0x1400bc649  sub     r11, rdx
0x1400bc64c  sub     rcx, rdx
0x1400bc64f  mov     eax, [rdi+50h]
0x1400bc652  cmp     r12d, eax
0x1400bc655  ja      loc_1400BC762
0x1400bc65b  mov     rdx, [rdi+10h]
0x1400bc65f  cmp     r11, rdx
0x1400bc662  jb      loc_1400BC762
0x1400bc668  add     rax, rdx
0x1400bc66b  cmp     rcx, rax
0x1400bc66e  ja      loc_1400BC762
0x1400bc674  mov     rcx, r11
0x1400bc677  sub     rcx, rdx; ullOperand
0x1400bc67a  lea     rdx, [rsp+88h+arg_18]; pulResult
0x1400bc682  call    RtlULongLongToULong
0x1400bc687  mov     edi, eax
0x1400bc689  test    eax, eax
0x1400bc68b  js      loc_1400BC767
0x1400bc691  mov     r8d, r12d
0x1400bc694  mov     rdx, r11
0x1400bc697  mov     rcx, rbp
0x1400bc69a  call    FveTestRwCheckBadSectorInRange
0x1400bc69f  mov     edi, eax
0x1400bc6a1  cmp     eax, 0C000009Ch
0x1400bc6a6  jnz     short loc_1400BC6B9
0x1400bc6a8  mov     rdx, [rsp+88h+arg_8]
0x1400bc6b0  mov     byte ptr [rdx+78h], 1
0x1400bc6b4  jmp     loc_1400BC767
0x1400bc6b9  test    eax, eax
0x1400bc6bb  js      loc_1400BC767
0x1400bc6c1  mov     rcx, [rsi-0A0h]; MemoryDescriptorList
0x1400bc6c8  test    byte ptr [rcx+0Ah], 5
0x1400bc6cc  jz      short loc_1400BC6D4
0x1400bc6ce  mov     rax, [rcx+18h]
0x1400bc6d2  jmp     short loc_1400BC6F9
0x1400bc6d4  xor     r9d, r9d; RequestedAddress
0x1400bc6d7  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400bc6df  xor     edx, edx; AccessMode
0x1400bc6e1  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400bc6e9  lea     r8d, [r9+1]; CacheType
0x1400bc6ed  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400bc6f4  nop     dword ptr [rax+rax+00h]
0x1400bc6f9  cmp     byte ptr [rsp+88h+pulResult], 4
0x1400bc701  mov     rdx, [rsp+88h+arg_8]
0x1400bc709  mov     r8, [rdx+30h]
0x1400bc70d  jnz     short loc_1400BC71E
0x1400bc70f  mov     ecx, [rsp+88h+arg_18]
0x1400bc716  mov     rdx, rax
0x1400bc719  add     rcx, r8
0x1400bc71c  jmp     short loc_1400BC72B
0x1400bc71e  mov     edx, [rsp+88h+arg_18]
0x1400bc725  mov     rcx, rax; void *
0x1400bc728  add     rdx, r8; Src
0x1400bc72b  mov     r8, r12; Size
0x1400bc72e  call    memmove
0x1400bc733  mov     rax, [rbp+0F8h]
0x1400bc73a  dec     rax
0x1400bc73d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bc741  ja      short loc_1400BC772
0x1400bc743  mov     rax, 0FFFFF78000000320h
0x1400bc74d  mov     rcx, [rax]
0x1400bc750  mov     eax, [rsp+88h+var_54]
0x1400bc754  sub     rcx, rbx
0x1400bc757  imul    rcx, rax
0x1400bc75b  mov     [rsp+88h+var_40], rcx
0x1400bc760  jmp     short loc_1400BC772
0x1400bc762  mov     edi, 0C0000001h
0x1400bc767  xor     r15d, r15d
0x1400bc76a  jmp     short loc_1400BC790
0x1400bc76c  mov     edi, r15d
0x1400bc76f  mov     r15, r12
0x1400bc772  mov     rcx, [rbp+0F8h]
0x1400bc779  lea     rax, [rcx-1]
0x1400bc77d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bc781  ja      short loc_1400BC790
0x1400bc783  mov     r8, [rsp+88h+var_40]
0x1400bc788  mov     edx, r12d
0x1400bc78b  call    FveTestRwDelayData
0x1400bc790  lea     r12, [rsi-0A8h]
0x1400bc797  mov     rcx, r13; SpinLock
0x1400bc79a  mov     [r12+38h], r15
0x1400bc79f  mov     [r12+30h], edi
0x1400bc7a4  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc7ab  nop     dword ptr [rax+rax+00h]
0x1400bc7b0  mov     r8, [rsi]
0x1400bc7b3  cmp     [r8+8], rsi
0x1400bc7b7  jnz     short loc_1400BC819
0x1400bc7b9  mov     rdx, [rsi+8]
0x1400bc7bd  cmp     [rdx], rsi
0x1400bc7c0  jnz     short loc_1400BC819
0x1400bc7c2  mov     [rdx], r8
0x1400bc7c5  mov     rcx, r13; SpinLock
0x1400bc7c8  mov     [r8+8], rdx
0x1400bc7cc  mov     dl, al; NewIrql
0x1400bc7ce  mov     rdi, [r14]
0x1400bc7d1  cmp     rdi, r14
0x1400bc7d4  setnz   sil
0x1400bc7d8  call    cs:__imp_KeReleaseSpinLock
0x1400bc7df  nop     dword ptr [rax+rax+00h]
0x1400bc7e4  mov     dl, 1; PriorityBoost
0x1400bc7e6  mov     rcx, r12; Irp
0x1400bc7e9  call    cs:__imp_IofCompleteRequest
0x1400bc7f0  nop     dword ptr [rax+rax+00h]
0x1400bc7f5  cmp     rdi, r14
0x1400bc7f8  jz      short loc_1400BC831
0x1400bc7fa  mov     rcx, r13; SpinLock
0x1400bc7fd  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc804  nop     dword ptr [rax+rax+00h]
0x1400bc809  mov     rdi, [rsp+88h+arg_8]
0x1400bc811  xor     r15d, r15d
0x1400bc814  jmp     loc_1400BC555
0x1400bc819  mov     ecx, 3
0x1400bc81e  int     29h; Win8: RtlFailFast(ecx)
0x1400bc820  mov     dl, al; NewIrql
0x1400bc822  mov     rcx, r13; SpinLock
0x1400bc825  call    cs:__imp_KeReleaseSpinLock
0x1400bc82c  nop     dword ptr [rax+rax+00h]
0x1400bc831  mov     rbx, [rsp+88h+arg_0]
0x1400bc839  add     rsp, 50h
0x1400bc83d  pop     r15
0x1400bc83f  pop     r14
0x1400bc841  pop     r13
0x1400bc843  pop     r12
0x1400bc845  pop     rdi
0x1400bc846  pop     rsi
0x1400bc847  pop     rbp
0x1400bc848  retn
```
