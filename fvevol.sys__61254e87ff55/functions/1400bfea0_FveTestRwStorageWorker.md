# FveTestRwStorageWorker

- ea: `0x1400bfea0`
- end: `0x1400c02ba`
- name: `FveTestRwStorageWorker`
- size: `1050`
- prototype: `IO_WORKITEM_ROUTINE`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140006730`
- `0x140009cb4`
- `0x140022d40`
- `0x1400bf8ec`
- `0x1400bfa08`
- `0x1400bfea0`

## import_xrefs

- `ntoskrnl!KeQueryTimeIncrement` at `0x1400bff8f`
- `ntoskrnl!KeQueryTimeIncrement` at `0x1400bff8f`
- `ntoskrnl!IofCompleteRequest` at `0x1400c0259`
- `ntoskrnl!IofCompleteRequest` at `0x1400c0259`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c000f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c0248`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c0295`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c000f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c0248`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c0295`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bffae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c0214`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c026d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bffae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c0214`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c026d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c015d`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c015d`

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
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(
                         DeviceObject,
                         Context)
      && (*(_BYTE *)(v4 + 4419) & 8) != 0
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
0x1400bfea0  mov     r11, rsp
0x1400bfea3  mov     [r11+8], rbx
0x1400bfea7  mov     [r11+10h], rdx
0x1400bfeab  push    rbp
0x1400bfeac  push    rsi
0x1400bfead  push    rdi
0x1400bfeae  push    r12
0x1400bfeb0  push    r13
0x1400bfeb2  push    r14
0x1400bfeb4  push    r15
0x1400bfeb6  sub     rsp, 50h
0x1400bfeba  mov     rax, [rdx+40h]
0x1400bfebe  xor     r15d, r15d
0x1400bfec1  mov     ebx, r15d
0x1400bfec4  mov     [rsp+88h+var_40], r15
0x1400bfec9  mov     [rsp+88h+var_54], r15d
0x1400bfece  mov     [rsp+88h+var_50], r15
0x1400bfed3  mov     rbp, [rax+10h]
0x1400bfed7  lea     r14d, [r15+1]
0x1400bfedb  mov     [rsp+88h+var_48], r15
0x1400bfee0  mov     rdi, [rbp+48h]
0x1400bfee4  mov     [r11-58h], r15d
0x1400bfee8  mov     [r11+18h], r15d
0x1400bfeec  mov     [r11+20h], r15d
0x1400bfef0  mov     rax, [rdi+3D0h]
0x1400bfef7  test    rax, rax
0x1400bfefa  jz      short loc_1400BFF76
0x1400bfefc  cmp     [rbp+13Eh], r15b
0x1400bff03  jz      loc_1400BFF9F
0x1400bff09  mov     rsi, [rax+38h]
0x1400bff0d  mov     [rsp+88h+var_50], rsi
0x1400bff12  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400bff17  test    eax, eax
0x1400bff19  jz      short loc_1400BFF24
0x1400bff1b  test    byte ptr [rdi+1143h], 8
0x1400bff22  jnz     short loc_1400BFF32
0x1400bff24  mov     rax, [rdi+3D0h]
0x1400bff2b  cmp     [rax+0Ah], r14w
0x1400bff30  jnz     short loc_1400BFF37
0x1400bff32  mov     eax, r15d
0x1400bff35  jmp     short loc_1400BFF40
0x1400bff37  mov     eax, [rax+1Ch]
0x1400bff3a  test    eax, eax
0x1400bff3c  cmovz   eax, r14d
0x1400bff40  mov     ecx, [rdi+51Ch]
0x1400bff46  lea     rdx, [rsp+88h+pulResult]; pulResult
0x1400bff4e  imul    rcx, rax; ullOperand
0x1400bff52  call    RtlULongLongToULong
0x1400bff57  mov     eax, [rsp+88h+pulResult]
0x1400bff5e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400bff62  mov     [rsp+88h+var_58], eax
0x1400bff66  lea     rcx, [rsi+rax]
0x1400bff6a  cmp     rcx, rsi
0x1400bff6d  cmovnb  rdx, rcx
0x1400bff71  mov     [rsp+88h+var_48], rdx
0x1400bff76  cmp     [rbp+13Eh], r15b
0x1400bff7d  jz      short loc_1400BFF9F
0x1400bff7f  mov     rax, [rbp+0F8h]
0x1400bff86  sub     rax, r14
0x1400bff89  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400bff8d  ja      short loc_1400BFF9F
0x1400bff8f  call    cs:__imp_KeQueryTimeIncrement
0x1400bff96  nop     dword ptr [rax+rax+00h]
0x1400bff9b  mov     [rsp+88h+var_54], eax
0x1400bff9f  mov     rdi, [rsp+88h+arg_8]
0x1400bffa7  lea     r13, [rdi+70h]
0x1400bffab  mov     rcx, r13; SpinLock
0x1400bffae  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bffb5  nop     dword ptr [rax+rax+00h]
0x1400bffba  lea     r14, [rdi+60h]
0x1400bffbe  cmp     [r14], r14
0x1400bffc1  setnz   sil
0x1400bffc5  test    sil, sil
0x1400bffc8  jz      loc_1400C0290
0x1400bffce  mov     rsi, [r14]
0x1400bffd1  cmp     [rsi+8], r14
0x1400bffd5  jnz     loc_1400C0289
0x1400bffdb  mov     rcx, [rsi]
0x1400bffde  cmp     [rcx+8], rsi
0x1400bffe2  jnz     loc_1400C0289
0x1400bffe8  mov     [r14], rcx
0x1400bffeb  mov     [rcx+8], r14
0x1400bffef  mov     rcx, [r14]
0x1400bfff2  cmp     [rcx+8], r14
0x1400bfff6  jnz     loc_1400C0289
0x1400bfffc  mov     [rsi], rcx
0x1400bffff  mov     dl, al; NewIrql
0x1400c0001  mov     [rsi+8], r14
0x1400c0005  mov     [rcx+8], rsi
0x1400c0009  mov     rcx, r13; SpinLock
0x1400c000c  mov     [r14], rsi
0x1400c000f  call    cs:__imp_KeReleaseSpinLock
0x1400c0016  nop     dword ptr [rax+rax+00h]
0x1400c001b  mov     r11, [rsi+10h]
0x1400c001f  mov     r12d, [r11+8]
0x1400c0023  cmp     [rbp+13Eh], r15b
0x1400c002a  jz      loc_1400C01DC
0x1400c0030  mov     al, [r11]
0x1400c0033  mov     byte ptr [rsp+88h+pulResult], al
0x1400c003a  mov     rax, [rbp+0F8h]
0x1400c0041  mov     r11, [r11+18h]
0x1400c0045  dec     rax
0x1400c0048  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400c004c  ja      short loc_1400C005B
0x1400c004e  mov     rax, 0FFFFF78000000320h
0x1400c0058  mov     rbx, [rax]
0x1400c005b  mov     edx, [rsp+88h+var_58]
0x1400c005f  lea     rcx, [r12+r11]
0x1400c0063  mov     r15, r12
0x1400c0066  test    edx, edx
0x1400c0068  jz      short loc_1400C00BF
0x1400c006a  mov     eax, [rbp+138h]
0x1400c0070  sub     eax, 5
0x1400c0073  cmp     eax, 1
0x1400c0076  jbe     short loc_1400C00BF
0x1400c0078  mov     eax, edx
0x1400c007a  cmp     r11, rdx
0x1400c007d  jb      loc_1400C01D2
0x1400c0083  mov     rdx, [rsp+88h+var_50]
0x1400c0088  cmp     r11, rdx
0x1400c008b  jnb     short loc_1400C0096
0x1400c008d  cmp     rcx, rdx
0x1400c0090  ja      loc_1400C01D2
0x1400c0096  mov     r8, [rsp+88h+var_48]
0x1400c009b  cmp     r11, r8
0x1400c009e  jnb     short loc_1400C00A9
0x1400c00a0  cmp     rcx, r8
0x1400c00a3  ja      loc_1400C01D2
0x1400c00a9  cmp     r11, rdx
0x1400c00ac  jb      short loc_1400C00BF
0x1400c00ae  cmp     r11, r8
0x1400c00b1  jnb     short loc_1400C00BF
0x1400c00b3  cmp     [rdi+10h], rax
0x1400c00b7  jnb     short loc_1400C00BF
0x1400c00b9  sub     r11, rdx
0x1400c00bc  sub     rcx, rdx
0x1400c00bf  mov     eax, [rdi+50h]
0x1400c00c2  cmp     r12d, eax
0x1400c00c5  ja      loc_1400C01D2
0x1400c00cb  mov     rdx, [rdi+10h]
0x1400c00cf  cmp     r11, rdx
0x1400c00d2  jb      loc_1400C01D2
0x1400c00d8  add     rax, rdx
0x1400c00db  cmp     rcx, rax
0x1400c00de  ja      loc_1400C01D2
0x1400c00e4  mov     rcx, r11
0x1400c00e7  sub     rcx, rdx; ullOperand
0x1400c00ea  lea     rdx, [rsp+88h+arg_18]; pulResult
0x1400c00f2  call    RtlULongLongToULong
0x1400c00f7  mov     edi, eax
0x1400c00f9  test    eax, eax
0x1400c00fb  js      loc_1400C01D7
0x1400c0101  mov     r8d, r12d
0x1400c0104  mov     rdx, r11
0x1400c0107  mov     rcx, rbp
0x1400c010a  call    FveTestRwCheckBadSectorInRange
0x1400c010f  mov     edi, eax
0x1400c0111  cmp     eax, 0C000009Ch
0x1400c0116  jnz     short loc_1400C0129
0x1400c0118  mov     rdx, [rsp+88h+arg_8]
0x1400c0120  mov     byte ptr [rdx+78h], 1
0x1400c0124  jmp     loc_1400C01D7
0x1400c0129  test    eax, eax
0x1400c012b  js      loc_1400C01D7
0x1400c0131  mov     rcx, [rsi-0A0h]; MemoryDescriptorList
0x1400c0138  test    byte ptr [rcx+0Ah], 5
0x1400c013c  jz      short loc_1400C0144
0x1400c013e  mov     rax, [rcx+18h]
0x1400c0142  jmp     short loc_1400C0169
0x1400c0144  xor     r9d, r9d; RequestedAddress
0x1400c0147  mov     [rsp+88h+Priority], 40000010h; Priority
0x1400c014f  xor     edx, edx; AccessMode
0x1400c0151  mov     [rsp+88h+BugCheckOnFailure], 0; BugCheckOnFailure
0x1400c0159  lea     r8d, [r9+1]; CacheType
0x1400c015d  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x1400c0164  nop     dword ptr [rax+rax+00h]
0x1400c0169  cmp     byte ptr [rsp+88h+pulResult], 4
0x1400c0171  mov     rdx, [rsp+88h+arg_8]
0x1400c0179  mov     r8, [rdx+30h]
0x1400c017d  jnz     short loc_1400C018E
0x1400c017f  mov     ecx, [rsp+88h+arg_18]
0x1400c0186  mov     rdx, rax
0x1400c0189  add     rcx, r8
0x1400c018c  jmp     short loc_1400C019B
0x1400c018e  mov     edx, [rsp+88h+arg_18]
0x1400c0195  mov     rcx, rax; void *
0x1400c0198  add     rdx, r8; Src
0x1400c019b  mov     r8, r12; Size
0x1400c019e  call    memmove
0x1400c01a3  mov     rax, [rbp+0F8h]
0x1400c01aa  dec     rax
0x1400c01ad  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400c01b1  ja      short loc_1400C01E2
0x1400c01b3  mov     rax, 0FFFFF78000000320h
0x1400c01bd  mov     rcx, [rax]
0x1400c01c0  mov     eax, [rsp+88h+var_54]
0x1400c01c4  sub     rcx, rbx
0x1400c01c7  imul    rcx, rax
0x1400c01cb  mov     [rsp+88h+var_40], rcx
0x1400c01d0  jmp     short loc_1400C01E2
0x1400c01d2  mov     edi, 0C0000001h
0x1400c01d7  xor     r15d, r15d
0x1400c01da  jmp     short loc_1400C0200
0x1400c01dc  mov     edi, r15d
0x1400c01df  mov     r15, r12
0x1400c01e2  mov     rcx, [rbp+0F8h]
0x1400c01e9  lea     rax, [rcx-1]
0x1400c01ed  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1400c01f1  ja      short loc_1400C0200
0x1400c01f3  mov     r8, [rsp+88h+var_40]
0x1400c01f8  mov     edx, r12d
0x1400c01fb  call    FveTestRwDelayData
0x1400c0200  lea     r12, [rsi-0A8h]
0x1400c0207  mov     rcx, r13; SpinLock
0x1400c020a  mov     [r12+38h], r15
0x1400c020f  mov     [r12+30h], edi
0x1400c0214  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c021b  nop     dword ptr [rax+rax+00h]
0x1400c0220  mov     r8, [rsi]
0x1400c0223  cmp     [r8+8], rsi
0x1400c0227  jnz     short loc_1400C0289
0x1400c0229  mov     rdx, [rsi+8]
0x1400c022d  cmp     [rdx], rsi
0x1400c0230  jnz     short loc_1400C0289
0x1400c0232  mov     [rdx], r8
0x1400c0235  mov     rcx, r13; SpinLock
0x1400c0238  mov     [r8+8], rdx
0x1400c023c  mov     dl, al; NewIrql
0x1400c023e  mov     rdi, [r14]
0x1400c0241  cmp     rdi, r14
0x1400c0244  setnz   sil
0x1400c0248  call    cs:__imp_KeReleaseSpinLock
0x1400c024f  nop     dword ptr [rax+rax+00h]
0x1400c0254  mov     dl, 1; PriorityBoost
0x1400c0256  mov     rcx, r12; Irp
0x1400c0259  call    cs:__imp_IofCompleteRequest
0x1400c0260  nop     dword ptr [rax+rax+00h]
0x1400c0265  cmp     rdi, r14
0x1400c0268  jz      short loc_1400C02A1
0x1400c026a  mov     rcx, r13; SpinLock
0x1400c026d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c0274  nop     dword ptr [rax+rax+00h]
0x1400c0279  mov     rdi, [rsp+88h+arg_8]
0x1400c0281  xor     r15d, r15d
0x1400c0284  jmp     loc_1400BFFC5
0x1400c0289  mov     ecx, 3
0x1400c028e  int     29h; Win8: RtlFailFast(ecx)
0x1400c0290  mov     dl, al; NewIrql
0x1400c0292  mov     rcx, r13; SpinLock
0x1400c0295  call    cs:__imp_KeReleaseSpinLock
0x1400c029c  nop     dword ptr [rax+rax+00h]
0x1400c02a1  mov     rbx, [rsp+88h+arg_0]
0x1400c02a9  add     rsp, 50h
0x1400c02ad  pop     r15
0x1400c02af  pop     r14
0x1400c02b1  pop     r13
0x1400c02b3  pop     r12
0x1400c02b5  pop     rdi
0x1400c02b6  pop     rsi
0x1400c02b7  pop     rbp
0x1400c02b8  retn
```
