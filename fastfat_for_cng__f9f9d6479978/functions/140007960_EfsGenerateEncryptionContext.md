# EfsGenerateEncryptionContext

- ea: `0x140007960`
- end: `0x140007d3d`
- name: `EfsGenerateEncryptionContext`
- size: `989`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, installer_update`

## callees

- `0x1400077e4`
- `0x1400078fc`
- `0x140007960`
- `0x140008090`
- `0x14004d720`
- `0x14004e560`
- `0x14004e610`
- `0x14004ea30`
- `0x1400566c4`
- `0x14005693c`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140007bec`
- `ntoskrnl!KeInitializeEvent` at `0x140007bec`
- `ntoskrnl!IofCallDriver` at `0x140007c77`
- `ntoskrnl!IofCallDriver` at `0x140007c77`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007ca2`
- `ntoskrnl!KeWaitForSingleObject` at `0x140007ca2`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140007c35`
- `ntoskrnl!IoBuildDeviceIoControlRequest` at `0x140007c35`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007ac7`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007ac7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d438`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007cec`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007d11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d438`
- `ntoskrnl!ExAllocatePool2` at `0x1400079b5`
- `ntoskrnl!ExAllocatePool2` at `0x140007b8e`
- `ntoskrnl!ExAllocatePool2` at `0x1400079b5`
- `ntoskrnl!ExAllocatePool2` at `0x140007b8e`

## pseudocode

```c
__int64 __fastcall EfsGenerateEncryptionContext(
        __int64 a1,
        struct _DEVICE_OBJECT *a2,
        struct _DEVICE_OBJECT *a3,
        __int64 a4,
        _DWORD *a5,
        __int64 *a6)
{
  bool v8; // r15
  __int64 Pool2; // rax
  __int64 v10; // rdi
  __int64 v12; // rcx
  NTSTATUS Status; // ebx
  void *v14; // r14
  int v15; // edx
  unsigned int *KeyBlobBuffer; // rax
  PNPAGED_LOOKASIDE_LIST *v17; // r13
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r12
  struct _DEVICE_OBJECT *v21; // r13
  char v22; // r15
  __int64 v23; // rax
  PIRP v24; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 v26; // rcx
  bool v27[3]; // [rsp+51h] [rbp-87h] BYREF
  NTSTATUS v28; // [rsp+54h] [rbp-84h]
  __int64 v29; // [rsp+58h] [rbp-80h]
  __int64 v30; // [rsp+60h] [rbp-78h]
  __int64 v31; // [rsp+68h] [rbp-70h]
  struct _KEVENT Event; // [rsp+70h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-50h] BYREF

  v29 = 0;
  v8 = 0;
  v27[0] = 0;
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  Pool2 = ExAllocatePool2(64, 88, 1265854021);
  v10 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Status = EfsEncryptMemory(Pool2 + 56);
  v28 = Status;
  if ( Status >= 0 )
  {
    v14 = 0;
    v30 = 0;
    v31 = v10;
    *(_OWORD *)v10 = 0;
    *(_OWORD *)(v10 + 16) = 0;
    *(_OWORD *)(v10 + 32) = 0;
    *(_QWORD *)(v10 + 48) = 0;
    *(_DWORD *)(v10 + 4) = 26128;
    *(_DWORD *)v10 = 32;
    if ( a3 )
    {
      EfspCanOffloadCrypto(v12, 26128, a4, v27);
      v8 = v27[0];
      if ( v27[0] )
        v8 = (unsigned __int8)EfspIsCryptoOffloadTurnedOffByOverride() != 1;
    }
    if ( v8 )
    {
      *(_DWORD *)(v10 + 8) = 1;
      v15 = 1;
    }
    else
    {
      *(_DWORD *)(v10 + 8) = 0;
      v15 = 0;
    }
    KeyBlobBuffer = GetKeyBlobBufferEx(*(_DWORD *)(v10 + 4), v15);
    v17 = (PNPAGED_LOOKASIDE_LIST *)KeyBlobBuffer;
    if ( !KeyBlobBuffer )
      goto LABEL_13;
    if ( !SetKeyTable(KeyBlobBuffer, a5, (unsigned int *)v10) )
    {
      ExFreeToNPagedLookasideList(v17[9], v17);
      Status = -1073741790;
      v28 = -1073741790;
      EfspTraceLogAssert(v19, 5, 2839);
      goto LABEL_29;
    }
    if ( *a5 )
      EfspTraceLogAssert(v18, 5, 2847);
    *a5 = 0;
    v20 = AllocateAndSetContextDataBlock(v17);
    v29 = v20;
    if ( v20 )
    {
      *a6 = v20;
      v29 = 0;
      if ( v8 )
      {
        v21 = a3;
        Status = EfspDevCryptoSetup(a3);
        v28 = Status;
        if ( Status >= 0 )
        {
          v22 = 1;
          v23 = ExAllocatePool2(256, 32, 1836279365);
          v14 = (void *)v23;
          v30 = v23;
          if ( !v23 )
            goto LABEL_22;
          *(_OWORD *)v23 = 0;
          *(_OWORD *)(v23 + 16) = 0;
          *(_WORD *)(v23 + 4) = 21327;
          *(_BYTE *)(v23 + 6) = 1;
          *(_DWORD *)v23 = 0;
          *(_DWORD *)(v23 + 16) = 0;
          *(_QWORD *)(v23 + 20) = 7;
          *(_DWORD *)(v23 + 28) = 0;
          KeInitializeEvent(&Event, SynchronizationEvent, 0);
          v24 = IoBuildDeviceIoControlRequest(0x900DBu, a2, v14, 0x20u, 0, 0, 0, &Event, &IoStatusBlock);
          if ( v24 )
          {
            CurrentStackLocation = v24->Tail.Overlay.CurrentStackLocation;
            *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 13;
            CurrentStackLocation[-1].FileObject = *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 184) + 48LL);
            Status = IofCallDriver(a2, v24);
            v28 = Status;
            if ( Status == 259 )
            {
              KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
              Status = IoStatusBlock.Status;
              v28 = IoStatusBlock.Status;
            }
            if ( Status >= 0 )
              goto LABEL_31;
            EfspTraceLogAssert(v26, 5, 2945);
            Status = -1073741790;
          }
          else
          {
LABEL_22:
            Status = -1073741670;
          }
          v28 = Status;
LABEL_31:
          ExFreePoolWithTag((PVOID)v10, 0);
          if ( v14 )
            ExFreePoolWithTag(v14, 0);
          if ( Status < 0 && v22 == 1 )
            EfspDevCryptoSetup(v21);
          return (unsigned int)Status;
        }
LABEL_30:
        v22 = 0;
        goto LABEL_31;
      }
    }
    else
    {
LABEL_13:
      Status = -1073741670;
      v28 = -1073741670;
    }
LABEL_29:
    v21 = a3;
    goto LABEL_30;
  }
  ExFreePoolWithTag((PVOID)v10, 0);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140007960  mov     r11, rsp
0x140007963  mov     [r11+18h], r8
0x140007967  mov     [r11+10h], rdx
0x14000796b  mov     [r11+8], rcx
0x14000796f  push    rbx
0x140007970  push    rsi
0x140007971  push    rdi
0x140007972  push    r12
0x140007974  push    r13
0x140007976  push    r14
0x140007978  push    r15
0x14000797a  sub     rsp, 0A0h
0x140007981  mov     rsi, r9
0x140007984  mov     r13, r8
0x140007987  xor     r12d, r12d
0x14000798a  mov     [r11-80h], r12
0x14000798e  xor     r15b, r15b
0x140007991  mov     [rsp+0D8h+var_87], r15b
0x140007996  xorps   xmm0, xmm0
0x140007999  xor     eax, eax
0x14000799b  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x1400079a0  mov     [r11-58h], rax
0x1400079a4  movups  xmmword ptr [r11-50h], xmm0
0x1400079a9  lea     edx, [rax+58h]
0x1400079ac  lea     ecx, [rax+40h]
0x1400079af  mov     r8d, 4B736645h
0x1400079b5  call    cs:__imp_ExAllocatePool2
0x1400079bc  nop     dword ptr [rax+rax+00h]
0x1400079c1  mov     rdi, rax
0x1400079c4  test    rax, rax
0x1400079c7  jnz     short loc_1400079E2
0x1400079c9  mov     eax, 0C000009Ah
0x1400079ce  add     rsp, 0A0h
0x1400079d5  pop     r15
0x1400079d7  pop     r14
0x1400079d9  pop     r13
0x1400079db  pop     r12
0x1400079dd  pop     rdi
0x1400079de  pop     rsi
0x1400079df  pop     rbx
0x1400079e0  retn
0x1400079e2  lea     rcx, [rax+38h]
0x1400079e6  call    EfsEncryptMemory
0x1400079eb  mov     ebx, eax
0x1400079ed  mov     [rsp+0D8h+var_84], eax
0x1400079f1  test    eax, eax
0x1400079f3  jns     short loc_140007A0A
0x1400079f5  xor     edx, edx; Tag
0x1400079f7  mov     rcx, rdi; P
0x1400079fa  call    cs:__imp_ExFreePoolWithTag
0x140007a01  nop     dword ptr [rax+rax+00h]
0x140007a06  mov     eax, ebx
0x140007a08  jmp     short loc_1400079CE
0x140007a0a  xor     r14d, r14d
0x140007a0d  mov     [rsp+0D8h+var_78], r14
0x140007a12  mov     [rsp+0D8h+var_88], r12b
0x140007a17  mov     [rsp+0D8h+var_70], rdi
0x140007a1c  xorps   xmm0, xmm0
0x140007a1f  xor     eax, eax
0x140007a21  movups  xmmword ptr [rdi], xmm0
0x140007a24  movups  xmmword ptr [rdi+10h], xmm0
0x140007a28  movups  xmmword ptr [rdi+20h], xmm0
0x140007a2c  mov     [rdi+30h], rax
0x140007a30  mov     edx, 6610h
0x140007a35  mov     [rdi+4], edx
0x140007a38  mov     dword ptr [rdi], 20h ; ' '
0x140007a3e  test    r13, r13
0x140007a41  jz      short loc_140007A71
0x140007a43  lea     r9, [rsp+0D8h+var_87]
0x140007a48  mov     r8, rsi
0x140007a4b  call    EfspCanOffloadCrypto
0x140007a50  movzx   r15d, [rsp+0D8h+var_87]
0x140007a56  lea     esi, [r14+1]
0x140007a5a  cmp     r15b, sil
0x140007a5d  jnz     short loc_140007A76
0x140007a5f  call    EfspIsCryptoOffloadTurnedOffByOverride
0x140007a64  mov     cl, al
0x140007a66  xor     eax, eax
0x140007a68  cmp     cl, sil
0x140007a6b  cmovz   r15d, eax
0x140007a6f  jmp     short loc_140007A76
0x140007a71  mov     esi, 1
0x140007a76  test    r15b, r15b
0x140007a79  jz      short loc_140007A82
0x140007a7b  mov     [rdi+8], esi
0x140007a7e  mov     edx, esi
0x140007a80  jmp     short loc_140007A8B
0x140007a82  mov     dword ptr [rdi+8], 0
0x140007a89  xor     edx, edx
0x140007a8b  mov     ecx, [rdi+4]
0x140007a8e  call    GetKeyBlobBufferEx
0x140007a93  mov     r13, rax
0x140007a96  test    rax, rax
0x140007a99  jnz     short loc_140007AA9
0x140007a9b  mov     ebx, 0C000009Ah
0x140007aa0  mov     [rsp+0D8h+var_84], ebx
0x140007aa4  jmp     loc_140007CDA
0x140007aa9  mov     r8, rdi
0x140007aac  mov     rdx, [rsp+0D8h+arg_20]
0x140007ab4  mov     rcx, r13
0x140007ab7  call    SetKeyTable
0x140007abc  test    al, al
0x140007abe  jnz     short loc_140007AF4
0x140007ac0  mov     rdx, r13; Entry
0x140007ac3  mov     rcx, [r13+48h]; Lookaside
0x140007ac7  call    cs:__imp_ExFreeToNPagedLookasideList
0x140007ace  nop     dword ptr [rax+rax+00h]
0x140007ad3  mov     ebx, 0C0000022h
0x140007ad8  mov     [rsp+0D8h+var_84], ebx
0x140007adc  mov     r9d, ebx
0x140007adf  mov     edx, 5
0x140007ae4  mov     r8d, 0B17h
0x140007aea  call    EfspTraceLogAssert
0x140007aef  jmp     loc_140007CDA
0x140007af4  mov     r12, [rsp+0D8h+arg_20]
0x140007afc  cmp     dword ptr [r12], 0
0x140007b01  jz      short loc_140007B19
0x140007b03  mov     edx, 5
0x140007b08  mov     r9d, 0C0000001h
0x140007b0e  mov     r8d, 0B1Fh
0x140007b14  call    EfspTraceLogAssert
0x140007b19  mov     dword ptr [r12], 0
0x140007b21  mov     rcx, r13
0x140007b24  call    AllocateAndSetContextDataBlock
0x140007b29  mov     r12, rax
0x140007b2c  mov     [rsp+0D8h+var_80], rax
0x140007b31  test    rax, rax
0x140007b34  jz      loc_140007A9B
0x140007b3a  mov     rax, [rsp+0D8h+arg_28]
0x140007b42  mov     [rax], r12
0x140007b45  xor     r12d, r12d
0x140007b48  mov     [rsp+0D8h+var_80], r12
0x140007b4d  cmp     r15b, sil
0x140007b50  jnz     loc_140007CDA
0x140007b56  xor     edx, edx
0x140007b58  mov     r13, [rsp+0D8h+arg_10]
0x140007b60  mov     rcx, r13; DeviceObject
0x140007b63  call    EfspDevCryptoSetup
0x140007b68  mov     ebx, eax
0x140007b6a  mov     [rsp+0D8h+var_84], eax
0x140007b6e  test    eax, eax
0x140007b70  js      loc_140007CE2
0x140007b76  mov     r15b, sil
0x140007b79  mov     [rsp+0D8h+var_88], sil
0x140007b7e  lea     edx, [r12+20h]
0x140007b83  mov     ecx, 100h
0x140007b88  mov     r8d, 6D736645h
0x140007b8e  call    cs:__imp_ExAllocatePool2
0x140007b95  nop     dword ptr [rax+rax+00h]
0x140007b9a  mov     r14, rax
0x140007b9d  mov     [rsp+0D8h+var_78], rax
0x140007ba2  xor     ebx, ebx
0x140007ba4  test    rax, rax
0x140007ba7  jnz     short loc_140007BB7
0x140007ba9  mov     ebx, 0C000009Ah
0x140007bae  mov     [rsp+0D8h+var_84], ebx
0x140007bb2  jmp     loc_140007CE7
0x140007bb7  xorps   xmm0, xmm0
0x140007bba  movups  xmmword ptr [rax], xmm0
0x140007bbd  movups  xmmword ptr [rax+10h], xmm0
0x140007bc1  mov     eax, 534Fh
0x140007bc6  mov     [r14+4], ax
0x140007bcb  mov     [r14+6], sil
0x140007bcf  mov     [r14], ebx
0x140007bd2  mov     [r14+10h], ebx
0x140007bd6  mov     qword ptr [r14+14h], 7
0x140007bde  mov     [r14+1Ch], ebx
0x140007be2  xor     r8d, r8d; State
0x140007be5  mov     edx, esi; Type
0x140007be7  lea     rcx, [rsp+0D8h+Event]; Event
0x140007bec  call    cs:__imp_KeInitializeEvent
0x140007bf3  nop     dword ptr [rax+rax+00h]
0x140007bf8  lea     rax, [rsp+0D8h+var_50]
0x140007c00  mov     [rsp+0D8h+IoStatusBlock], rax; IoStatusBlock
0x140007c05  lea     rax, [rsp+0D8h+Event]
0x140007c0a  mov     [rsp+0D8h+var_A0], rax; Event
0x140007c0f  mov     [rsp+0D8h+InternalDeviceIoControl], bl; InternalDeviceIoControl
0x140007c13  mov     [rsp+0D8h+OutputBufferLength], ebx; OutputBufferLength
0x140007c17  mov     [rsp+0D8h+OutputBuffer], rbx; OutputBuffer
0x140007c1c  mov     r9d, 20h ; ' '; InputBufferLength
0x140007c22  mov     r8, r14; InputBuffer
0x140007c25  mov     rbx, [rsp+0D8h+DeviceObject]
0x140007c2d  mov     rdx, rbx; DeviceObject
0x140007c30  mov     ecx, 900DBh; IoControlCode
0x140007c35  call    cs:__imp_IoBuildDeviceIoControlRequest
0x140007c3c  nop     dword ptr [rax+rax+00h]
0x140007c41  mov     r8, rax
0x140007c44  test    rax, rax
0x140007c47  jz      loc_140007BA9
0x140007c4d  mov     rdx, [rax+0B8h]
0x140007c54  mov     word ptr [rdx-48h], 0Dh
0x140007c5a  mov     rax, [rsp+0D8h+arg_0]
0x140007c62  mov     rax, [rax+0B8h]
0x140007c69  mov     rcx, [rax+30h]
0x140007c6d  mov     [rdx-18h], rcx
0x140007c71  mov     rdx, r8; Irp
0x140007c74  mov     rcx, rbx; DeviceObject
0x140007c77  call    cs:__imp_IofCallDriver
0x140007c7e  nop     dword ptr [rax+rax+00h]
0x140007c83  mov     ebx, eax
0x140007c85  mov     [rsp+0D8h+var_84], eax
0x140007c89  cmp     eax, 103h
0x140007c8e  jnz     short loc_140007CB9
0x140007c90  mov     [rsp+0D8h+OutputBuffer], r12; Timeout
0x140007c95  xor     r9d, r9d; Alertable
0x140007c98  xor     r8d, r8d; WaitMode
0x140007c9b  xor     edx, edx; WaitReason
0x140007c9d  lea     rcx, [rsp+0D8h+Event]; Object
0x140007ca2  call    cs:__imp_KeWaitForSingleObject
0x140007ca9  nop     dword ptr [rax+rax+00h]
0x140007cae  mov     ebx, dword ptr [rsp+0D8h+var_50]
0x140007cb5  mov     [rsp+0D8h+var_84], ebx
0x140007cb9  test    ebx, ebx
0x140007cbb  jns     short loc_140007CE7
0x140007cbd  mov     r9d, ebx
0x140007cc0  mov     edx, 5
0x140007cc5  mov     r8d, 0B81h
0x140007ccb  call    EfspTraceLogAssert
0x140007cd0  mov     ebx, 0C0000022h
0x140007cd5  jmp     loc_140007BAE
0x140007cda  mov     r13, [rsp+0D8h+arg_10]
0x140007ce2  mov     r15b, [rsp+0D8h+var_88]
0x140007ce7  xor     edx, edx; Tag
0x140007ce9  mov     rcx, rdi; P
0x140007cec  call    cs:__imp_ExFreePoolWithTag
0x140007cf3  nop     dword ptr [rax+rax+00h]
0x140007cf8  test    r12, r12
0x140007cfb  jz      short loc_140007D07
0x140007cfd  lea     rcx, [rsp+0D8h+var_80]
0x140007d02  call    FreeContextDataBlock
0x140007d07  test    r14, r14
0x140007d0a  jz      short loc_140007D1D
0x140007d0c  xor     edx, edx; Tag
0x140007d0e  mov     rcx, r14; P
0x140007d11  call    cs:__imp_ExFreePoolWithTag
0x140007d18  nop     dword ptr [rax+rax+00h]
0x140007d1d  test    ebx, ebx
0x140007d1f  jns     loc_140007A06
0x140007d25  cmp     r15b, sil
0x140007d28  jnz     loc_140007A06
0x140007d2e  mov     edx, esi
0x140007d30  mov     rcx, r13; DeviceObject
0x140007d33  call    EfspDevCryptoSetup
0x140007d38  jmp     loc_140007A06
0x14000d3fb  push    rbp
0x14000d3fd  sub     rsp, 50h
0x14000d401  mov     rbp, rdx
0x14000d404  mov     rcx, [rbp+68h]; P
0x14000d408  test    rcx, rcx
0x14000d40b  jz      short loc_14000D41C
0x14000d40d  xor     edx, edx; Tag
0x14000d40f  call    cs:__imp_ExFreePoolWithTag
0x14000d416  nop     dword ptr [rax+rax+00h]
0x14000d41b  nop
0x14000d41c  cmp     qword ptr [rbp+58h], 0
0x14000d421  jz      short loc_14000D42D
0x14000d423  lea     rcx, [rbp+58h]
0x14000d427  call    FreeContextDataBlock
0x14000d42c  nop
0x14000d42d  mov     rcx, [rbp+60h]; P
0x14000d431  test    rcx, rcx
0x14000d434  jz      short loc_14000D445
0x14000d436  xor     edx, edx; Tag
0x14000d438  call    cs:__imp_ExFreePoolWithTag
0x14000d43f  nop     dword ptr [rax+rax+00h]
0x14000d444  nop
0x14000d445  cmp     dword ptr [rbp+54h], 0
0x14000d449  jge     short loc_14000D463
0x14000d44b  cmp     byte ptr [rbp+50h], 1
0x14000d44f  jnz     short loc_14000D463
0x14000d451  mov     edx, 1
0x14000d456  mov     rcx, [rbp+0F0h]; DeviceObject
0x14000d45d  call    EfspDevCryptoSetup
0x14000d462  nop
0x14000d463  add     rsp, 50h
0x14000d467  pop     rbp
0x14000d468  retn
```
