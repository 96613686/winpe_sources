# CdCommonWrite

- ea: `0x14001aa78`
- end: `0x14001af06`
- name: `CdCommonWrite`
- size: `1166`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140001240`

## callees

- `0x140001114`
- `0x140001160`
- `0x140003300`
- `0x14000e978`
- `0x140010d70`
- `0x140010e90`
- `0x1400181a4`
- `0x14001a2a0`
- `0x14001a8c4`
- `0x14001aa78`

## import_xrefs

- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14001adb3`
- `ntoskrnl!FsRtlNormalizeNtstatus` at `0x14001adb3`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ae60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bf4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001ae60`
- `ntoskrnl!ExReleaseResourceLite` at `0x14001bf4b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac31`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac31`
- `ntoskrnl!KeInitializeEvent` at `0x14001ac94`
- `ntoskrnl!KeInitializeEvent` at `0x14001ac94`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ae03`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001ae03`

## pseudocode

```c
__int64 __fastcall CdCommonWrite(_DWORD *a1, IRP *a2)
{
  IRP *v2; // r14
  __int64 v3; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdx
  __int64 Length; // r15
  PFILE_OBJECT FileObject; // rax
  char *FsContext; // r13
  unsigned __int64 v9; // rdi
  int v10; // edi
  IRP *v11; // rdx
  LARGE_INTEGER ByteOffset; // rsi
  char v13; // r12
  LARGE_INTEGER v14; // rax
  ULONG v15; // esi
  int v16; // edi
  _OWORD *v17; // rdx
  _OWORD *PoolWithTag; // rax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rcx
  char *v22; // rax
  LARGE_INTEGER v23; // [rsp+38h] [rbp-D0h]
  LARGE_INTEGER v24; // [rsp+40h] [rbp-C8h]
  struct _IO_STACK_LOCATION *v25; // [rsp+48h] [rbp-C0h]
  _OWORD v26[3]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v27[15]; // [rsp+90h] [rbp-78h] BYREF
  int v28; // [rsp+118h] [rbp+10h]
  ULONG v29; // [rsp+120h] [rbp+18h]
  int v30; // [rsp+128h] [rbp+20h]

  v2 = a2;
  v3 = (__int64)a1;
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v25 = CurrentStackLocation;
  memset(v26, 0, 44);
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( !(_DWORD)Length )
  {
    CdCompleteRequest(a1, v2, 0);
    return 0;
  }
  FileObject = CurrentStackLocation->FileObject;
  if ( ((__int64)FileObject->FsContext2 & 7) != 0 )
  {
    FsContext = (char *)FileObject->FsContext;
    v9 = (unsigned __int64)FileObject->FsContext2 & 0xFFFFFFFFFFFFFFF8uLL;
  }
  else
  {
    FsContext = 0;
    v9 = 0;
  }
  if ( ((__int64)FileObject->FsContext2 & 7) != 2 )
  {
    v10 = -1073741808;
    v11 = v2;
    goto LABEL_8;
  }
  v28 = a1[8] & 4;
  v30 = FileObject->Flags & 2;
  ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
  v24 = ByteOffset;
  v29 = CurrentStackLocation->Parameters.Read.Length;
  v23.QuadPart = ByteOffset.QuadPart + Length;
  v13 = 1;
  CdAcquireResource(a1, *((_QWORD *)FsContext + 1), 0, 1);
  if ( (*(_DWORD *)(v9 + 4) & 0x10) == 0 )
    CdVerifyFcbOperation(v3, FsContext);
  if ( (*(_DWORD *)(v9 + 4) & 0x20) == 0 )
  {
    v14 = *(LARGE_INTEGER *)(FsContext + 32);
    if ( ByteOffset.QuadPart >= v14.QuadPart )
    {
      v10 = -1073741807;
      goto LABEL_57;
    }
    if ( v23.QuadPart > v14.QuadPart )
    {
      Length = v14.LowPart - ByteOffset.LowPart;
      v23 = *(LARGE_INTEGER *)(FsContext + 32);
    }
  }
  v15 = *(_DWORD *)(*((_QWORD *)FsContext + 15) + 444LL) & (Length + *(_DWORD *)(*((_QWORD *)FsContext + 15) + 440LL));
  if ( (((unsigned __int16)(*(_WORD *)(*((_QWORD *)FsContext + 15) + 444LL)
                          & (Length + *(_WORD *)(*((_QWORD *)FsContext + 15) + 440LL)))
       | LOWORD(v24.LowPart))
      & 0x7FF) != 0
    || v15 > v29 )
  {
    v16 = v28;
    if ( !v28 )
      CdRaiseStatusEx(v3, 3221225688LL, 0, 1507328, 215);
    v15 = Length;
  }
  else
  {
    v16 = v28;
  }
  v17 = *(_OWORD **)(v3 + 48);
  if ( !v17 || (*(_DWORD *)(v3 + 32) & 0x100) == 0 )
  {
    if ( v16 )
    {
      *(_QWORD *)(v3 + 48) = v26;
      *(_DWORD *)(v3 + 32) &= ~0x100u;
      v17 = v26;
    }
    else
    {
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1552, 0x30u, 0x6F696443u);
      v17 = PoolWithTag;
      if ( !ExPoolZeroingNativelySupported && PoolWithTag )
      {
        *PoolWithTag = 0;
        PoolWithTag[1] = 0;
        PoolWithTag[2] = 0;
      }
      *(_QWORD *)(v3 + 48) = PoolWithTag;
      *(_DWORD *)(v3 + 32) |= 0x100u;
    }
  }
  *v17 = 0;
  v17[1] = 0;
  v17[2] = 0;
  *(_BYTE *)(*(_QWORD *)(v3 + 48) + 20LL) = BYTE1(*(_DWORD *)(v3 + 32)) & 1;
  if ( v16 )
  {
    KeInitializeEvent((PRKEVENT)(*(_QWORD *)(v3 + 48) + 24LL), NotificationEvent, 0);
  }
  else
  {
    *(_QWORD *)(*(_QWORD *)(v3 + 48) + 32LL) = KeGetCurrentThread();
    *(_QWORD *)(*(_QWORD *)(v3 + 48) + 24LL) = *((_QWORD *)FsContext + 1);
    *(_DWORD *)(*(_QWORD *)(v3 + 48) + 40LL) = Length;
  }
  v2->IoStatus.Information = v15;
  v25->FileObject->Flags |= 0x1000u;
  if ( !*(_QWORD *)(*(_QWORD *)(v3 + 8) + 8LL) )
    CdCreateUserMdl(v3, v15);
  memset(v27, 0, 0x40u);
  v27[0] = v24.QuadPart;
  LODWORD(v27[1]) = v15;
  CdSingleAsync(v3, v27, FsContext);
  v19 = *(_DWORD *)(v3 + 32);
  if ( (v19 & 4) != 0 )
  {
    CdWaitSync(v3);
    v10 = *(_DWORD *)(*(_QWORD *)(v3 + 8) + 48LL);
  }
  else
  {
    *(_DWORD *)(v3 + 32) = v19 & 0xFFFFFEFF;
    v10 = 259;
  }
  if ( v10 == 259 )
  {
    v2 = 0;
    v13 = 0;
  }
  else
  {
    if ( v10 >= 0 )
    {
      if ( v15 != (_DWORD)Length )
      {
        v20 = *(_QWORD *)(v3 + 8);
        v21 = *(_QWORD *)(v20 + 8);
        if ( v21 )
        {
          if ( (*(_BYTE *)(v21 + 10) & 5) != 0 )
            v22 = *(char **)(v21 + 24);
          else
            v22 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000010u);
        }
        else
        {
          v22 = *(char **)(v20 + 112);
        }
        if ( !v22 )
          CdRaiseStatusEx(v3, 3221225626LL, 0, 1507328, 337);
        memset(&v22[Length], 0, v15 - (unsigned int)Length);
        v2->IoStatus.Information = (unsigned int)Length;
        v13 = 1;
      }
    }
    else
    {
      v2->IoStatus.Information = 0;
      if ( (unsigned int)(v10 + 1073741662) <= 1
        || v10 == -1073741643
        || (unsigned int)(v10 + 1073741806) <= 2
        || v10 == -2147483626 )
      {
        CdRaiseStatusEx(v3, (unsigned int)v10, 0, 1507328, 326);
      }
      v10 = FsRtlNormalizeNtstatus(v10, -1073741591);
    }
    if ( v30 && v10 >= 0 )
      v25->FileObject->CurrentByteOffset = v23;
  }
LABEL_57:
  if ( v13 )
    ExReleaseResourceLite(*((PERESOURCE *)FsContext + 1));
  v11 = v2;
  a1 = (_DWORD *)v3;
  if ( v10 == -1073741608 )
    return (unsigned int)CdFsdPostRequest(v3, v2);
LABEL_8:
  CdCompleteRequest(a1, v11, v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14001aa78  mov     [rsp+arg_0], rcx
0x14001aa7d  push    rbx
0x14001aa7e  push    rsi
0x14001aa7f  push    rdi
0x14001aa80  push    r12
0x14001aa82  push    r13
0x14001aa84  push    r14
0x14001aa86  push    r15
0x14001aa88  sub     rsp, 0D0h
0x14001aa8f  mov     r14, rdx
0x14001aa92  mov     rbx, rcx
0x14001aa95  mov     rdx, [rdx+0B8h]
0x14001aa9c  mov     [rsp+108h+var_C0], rdx
0x14001aaa1  xor     eax, eax
0x14001aaa3  xorps   xmm0, xmm0
0x14001aaa6  movups  [rsp+108h+var_B0], xmm0
0x14001aaab  movups  xmmword ptr [rsp+108h+var_A0], xmm0
0x14001aab0  movups  xmmword ptr [rsp+108h+var_A0+0Ch], xmm0
0x14001aab5  mov     r15d, [rdx+8]
0x14001aab9  test    r15d, r15d
0x14001aabc  jnz     short loc_14001AADF
0x14001aabe  xor     r8d, r8d
0x14001aac1  mov     rdx, r14
0x14001aac4  call    CdCompleteRequest
0x14001aac9  xor     eax, eax
0x14001aacb  add     rsp, 0D0h
0x14001aad2  pop     r15
0x14001aad4  pop     r14
0x14001aad6  pop     r13
0x14001aad8  pop     r12
0x14001aada  pop     rdi
0x14001aadb  pop     rsi
0x14001aadc  pop     rbx
0x14001aadd  retn
0x14001aadf  mov     rax, [rdx+30h]
0x14001aae3  mov     ecx, [rax+20h]
0x14001aae6  and     ecx, 7
0x14001aae9  jnz     short loc_14001AAF2
0x14001aaeb  xor     r13d, r13d
0x14001aaee  xor     edi, edi
0x14001aaf0  jmp     short loc_14001AAFE
0x14001aaf2  mov     r13, [rax+18h]
0x14001aaf6  mov     rdi, [rax+20h]
0x14001aafa  and     rdi, 0FFFFFFFFFFFFFFF8h
0x14001aafe  mov     [rsp+108h+var_B8], r13
0x14001ab03  cmp     ecx, 2
0x14001ab06  jz      short loc_14001AB1F
0x14001ab08  mov     edi, 0C0000010h
0x14001ab0d  mov     rdx, r14
0x14001ab10  mov     rcx, rbx
0x14001ab13  mov     r8d, edi
0x14001ab16  call    CdCompleteRequest
0x14001ab1b  mov     eax, edi
0x14001ab1d  jmp     short loc_14001AACB
0x14001ab1f  mov     ecx, [rbx+20h]
0x14001ab22  and     ecx, 4
0x14001ab25  mov     [rsp+108h+arg_8], ecx
0x14001ab2c  mov     eax, [rax+50h]
0x14001ab2f  and     eax, 2
0x14001ab32  mov     [rsp+108h+arg_18], eax
0x14001ab39  mov     rsi, [rdx+18h]
0x14001ab3d  mov     [rsp+108h+var_C8], rsi
0x14001ab42  mov     [rsp+108h+arg_10], r15d
0x14001ab4a  lea     rax, [rsi+r15]
0x14001ab4e  mov     [rsp+108h+var_D0], rax
0x14001ab53  mov     r12d, 1
0x14001ab59  mov     r9d, r12d
0x14001ab5c  xor     r8d, r8d
0x14001ab5f  mov     rdx, [r13+8]
0x14001ab63  mov     rcx, rbx
0x14001ab66  call    CdAcquireResource
0x14001ab6b  mov     [rsp+108h+var_D8], r12b
0x14001ab70  mov     eax, [rdi+4]
0x14001ab73  test    al, 10h
0x14001ab75  jnz     short loc_14001AB82
0x14001ab77  mov     rdx, r13
0x14001ab7a  mov     rcx, rbx
0x14001ab7d  call    CdVerifyFcbOperation
0x14001ab82  mov     eax, [rdi+4]
0x14001ab85  test    al, 20h
0x14001ab87  jnz     short loc_14001ABB2
0x14001ab89  mov     rax, [r13+20h]
0x14001ab8d  cmp     rsi, rax
0x14001ab90  jl      short loc_14001ABA0
0x14001ab92  mov     edi, 0C0000011h
0x14001ab97  mov     [rsp+108h+var_D4], edi
0x14001ab9b  jmp     loc_14001AE57
0x14001aba0  cmp     [rsp+108h+var_D0], rax
0x14001aba5  jle     short loc_14001ABB2
0x14001aba7  mov     r15d, eax
0x14001abaa  sub     r15d, esi
0x14001abad  mov     [rsp+108h+var_D0], rax
0x14001abb2  mov     rax, [r13+78h]
0x14001abb6  mov     esi, [rax+1B8h]
0x14001abbc  add     esi, r15d
0x14001abbf  and     esi, [rax+1BCh]
0x14001abc5  mov     eax, dword ptr [rsp+108h+var_C8]
0x14001abc9  or      eax, esi
0x14001abcb  test    eax, 7FFh
0x14001abd0  jnz     short loc_14001ABDB
0x14001abd2  cmp     esi, [rsp+108h+arg_10]
0x14001abd9  jbe     short loc_14001ABEF
0x14001abdb  mov     edi, [rsp+108h+arg_8]
0x14001abe2  test    edi, edi
0x14001abe4  jz      loc_14001AE8A
0x14001abea  mov     esi, r15d
0x14001abed  jmp     short loc_14001ABF6
0x14001abef  mov     edi, [rsp+108h+arg_8]
0x14001abf6  mov     rdx, [rbx+30h]
0x14001abfa  test    rdx, rdx
0x14001abfd  jz      short loc_14001AC08
0x14001abff  test    dword ptr [rbx+20h], 100h
0x14001ac06  jnz     short loc_14001AC65
0x14001ac08  test    edi, edi
0x14001ac0a  jz      short loc_14001AC21
0x14001ac0c  lea     rax, [rsp+108h+var_B0]
0x14001ac11  mov     [rbx+30h], rax
0x14001ac15  btr     dword ptr [rbx+20h], 8
0x14001ac1a  lea     rdx, [rsp+108h+var_B0]
0x14001ac1f  jmp     short loc_14001AC65
0x14001ac21  mov     edx, 30h ; '0'; NumberOfBytes
0x14001ac26  mov     ecx, 610h; PoolType
0x14001ac2b  mov     r8d, 6F696443h; Tag
0x14001ac31  call    cs:__imp_ExAllocatePoolWithTag
0x14001ac38  nop     dword ptr [rax+rax+00h]
0x14001ac3d  mov     rdx, rax
0x14001ac40  cmp     cs:ExPoolZeroingNativelySupported, 0
0x14001ac47  jnz     short loc_14001AC5C
0x14001ac49  test    rax, rax
0x14001ac4c  jz      short loc_14001AC5C
0x14001ac4e  xorps   xmm0, xmm0
0x14001ac51  movups  xmmword ptr [rax], xmm0
0x14001ac54  movups  xmmword ptr [rax+10h], xmm0
0x14001ac58  movups  xmmword ptr [rax+20h], xmm0
0x14001ac5c  mov     [rbx+30h], rax
0x14001ac60  bts     dword ptr [rbx+20h], 8
0x14001ac65  xorps   xmm0, xmm0
0x14001ac68  movups  xmmword ptr [rdx], xmm0
0x14001ac6b  movups  xmmword ptr [rdx+10h], xmm0
0x14001ac6f  movups  xmmword ptr [rdx+20h], xmm0
0x14001ac73  mov     ecx, [rbx+20h]
0x14001ac76  shr     ecx, 8
0x14001ac79  and     cl, r12b
0x14001ac7c  mov     rax, [rbx+30h]
0x14001ac80  mov     [rax+14h], cl
0x14001ac83  test    edi, edi
0x14001ac85  jz      short loc_14001ACA2
0x14001ac87  mov     rcx, [rbx+30h]
0x14001ac8b  add     rcx, 18h; Event
0x14001ac8f  xor     r8d, r8d; State
0x14001ac92  xor     edx, edx; Type
0x14001ac94  call    cs:__imp_KeInitializeEvent
0x14001ac9b  nop     dword ptr [rax+rax+00h]
0x14001aca0  jmp     short loc_14001ACC7
0x14001aca2  mov     rcx, gs:188h
0x14001acab  mov     rax, [rbx+30h]
0x14001acaf  mov     [rax+20h], rcx
0x14001acb3  mov     rcx, [rbx+30h]
0x14001acb7  mov     rax, [r13+8]
0x14001acbb  mov     [rcx+18h], rax
0x14001acbf  mov     rax, [rbx+30h]
0x14001acc3  mov     [rax+28h], r15d
0x14001acc7  mov     eax, esi
0x14001acc9  mov     [r14+38h], rax
0x14001accd  mov     rax, [rsp+108h+var_C0]
0x14001acd2  mov     rax, [rax+30h]
0x14001acd6  bts     dword ptr [rax+50h], 0Ch
0x14001acdb  mov     rax, [rbx+8]
0x14001acdf  cmp     qword ptr [rax+8], 0
0x14001ace4  jnz     short loc_14001ACF0
0x14001ace6  mov     edx, esi
0x14001ace8  mov     rcx, rbx
0x14001aceb  call    CdCreateUserMdl
0x14001acf0  xor     edx, edx; Val
0x14001acf2  lea     r8d, [rdx+40h]; Size
0x14001acf6  lea     rcx, [rsp+108h+var_78]; void *
0x14001acfe  call    memset
0x14001ad03  mov     rax, [rsp+108h+var_C8]
0x14001ad08  mov     [rsp+108h+var_78], rax
0x14001ad10  mov     [rsp+108h+var_70], esi
0x14001ad17  mov     r8, r13
0x14001ad1a  lea     rdx, [rsp+108h+var_78]
0x14001ad22  mov     rcx, rbx
0x14001ad25  call    CdSingleAsync
0x14001ad2a  mov     eax, [rbx+20h]
0x14001ad2d  test    al, 4
0x14001ad2f  jz      short loc_14001AD42
0x14001ad31  mov     rcx, rbx
0x14001ad34  call    CdWaitSync
0x14001ad39  mov     rax, [rbx+8]
0x14001ad3d  mov     edi, [rax+30h]
0x14001ad40  jmp     short loc_14001AD4E
0x14001ad42  btr     eax, 8
0x14001ad46  mov     [rbx+20h], eax
0x14001ad49  mov     edi, 103h
0x14001ad4e  mov     [rsp+108h+var_D4], edi
0x14001ad52  cmp     edi, 103h
0x14001ad58  jnz     short loc_14001AD6A
0x14001ad5a  xor     r14d, r14d
0x14001ad5d  xor     r12b, r12b
0x14001ad60  mov     [rsp+108h+var_D8], r12b
0x14001ad65  jmp     loc_14001AE57
0x14001ad6a  test    edi, edi
0x14001ad6c  jns     short loc_14001ADC7
0x14001ad6e  mov     qword ptr [r14+38h], 0
0x14001ad76  lea     eax, [rdi+3FFFFF5Eh]
0x14001ad7c  cmp     eax, r12d
0x14001ad7f  jbe     loc_14001AEA8
0x14001ad85  cmp     edi, 0C00000B5h
0x14001ad8b  jz      loc_14001AEA8
0x14001ad91  lea     eax, [rdi+3FFFFFEEh]
0x14001ad97  cmp     eax, 2
0x14001ad9a  jbe     loc_14001AEA8
0x14001ada0  cmp     edi, 80000016h
0x14001ada6  jz      loc_14001AEA8
0x14001adac  mov     edx, 0C00000E9h; GenericException
0x14001adb1  mov     ecx, edi; Exception
0x14001adb3  call    cs:__imp_FsRtlNormalizeNtstatus
0x14001adba  nop     dword ptr [rax+rax+00h]
0x14001adbf  mov     edi, eax
0x14001adc1  mov     [rsp+108h+var_D4], eax
0x14001adc5  jmp     short loc_14001AE37
0x14001adc7  cmp     esi, r15d
0x14001adca  jz      short loc_14001AE37
0x14001adcc  mov     rax, [rbx+8]
0x14001add0  mov     rcx, [rax+8]; MemoryDescriptorList
0x14001add4  test    rcx, rcx
0x14001add7  jnz     short loc_14001ADDF
0x14001add9  mov     rax, [rax+70h]
0x14001addd  jmp     short loc_14001AE0F
0x14001addf  test    byte ptr [rcx+0Ah], 5
0x14001ade3  jz      short loc_14001ADEB
0x14001ade5  mov     rax, [rcx+18h]
0x14001ade9  jmp     short loc_14001AE0F
0x14001adeb  mov     [rsp+108h+Priority], 40000010h; Priority
0x14001adf3  mov     [rsp+108h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001adfb  xor     r9d, r9d; RequestedAddress
0x14001adfe  mov     r8d, r12d; CacheType
0x14001ae01  xor     edx, edx; AccessMode
0x14001ae03  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001ae0a  nop     dword ptr [rax+rax+00h]
0x14001ae0f  test    rax, rax
0x14001ae12  jz      loc_14001AEC3
0x14001ae18  mov     r12d, r15d
0x14001ae1b  sub     esi, r15d
0x14001ae1e  mov     r8d, esi; Size
0x14001ae21  lea     rcx, [r15+rax]; void *
0x14001ae25  xor     edx, edx; Val
0x14001ae27  call    memset
0x14001ae2c  nop
0x14001ae2d  mov     [r14+38h], r12
0x14001ae31  mov     r12d, 1
0x14001ae37  cmp     [rsp+108h+arg_18], 0
0x14001ae3f  jz      short loc_14001AE57
0x14001ae41  test    edi, edi
0x14001ae43  js      short loc_14001AE57
0x14001ae45  mov     rax, [rsp+108h+var_C0]
0x14001ae4a  mov     rax, [rax+30h]
0x14001ae4e  mov     rcx, [rsp+108h+var_D0]
0x14001ae53  mov     [rax+68h], rcx
0x14001ae57  test    r12b, r12b
0x14001ae5a  jz      short loc_14001AE6C
0x14001ae5c  mov     rcx, [r13+8]; Resource
0x14001ae60  call    cs:__imp_ExReleaseResourceLite
0x14001ae67  nop     dword ptr [rax+rax+00h]
0x14001ae6c  mov     rdx, r14
0x14001ae6f  mov     rcx, rbx
0x14001ae72  cmp     edi, 0C00000D8h
0x14001ae78  jnz     loc_14001AB13
0x14001ae7e  call    CdFsdPostRequest
0x14001ae83  mov     edi, eax
0x14001ae85  jmp     loc_14001AB1B
0x14001ae8a  mov     [rsp+108h+BugCheckOnFailure], 0D7h
0x14001ae92  mov     r9d, 170000h
0x14001ae98  xor     r8d, r8d
0x14001ae9b  mov     edx, 0C00000D8h
0x14001aea0  mov     rcx, rbx
0x14001aea3  call    CdRaiseStatusEx
0x14001aea8  mov     [rsp+108h+BugCheckOnFailure], 146h
0x14001aeb0  mov     r9d, 170000h
0x14001aeb6  xor     r8d, r8d
0x14001aeb9  mov     edx, edi
0x14001aebb  mov     rcx, rbx
0x14001aebe  call    CdRaiseStatusEx
0x14001aec3  mov     [rsp+108h+BugCheckOnFailure], 151h
0x14001aecb  mov     r9d, 170000h
0x14001aed1  xor     r8d, r8d
0x14001aed4  mov     edx, 0C000009Ah
0x14001aed9  mov     rcx, rbx
0x14001aedc  call    CdRaiseStatusEx
0x14001aee2  mov     [rsp+arg_18], 157h
0x14001aeea  mov     r9d, 170000h
0x14001aef0  xor     r8d, r8d
0x14001aef3  mov     edx, 0C00000E8h
0x14001aef8  mov     rcx, [rsp+arg_108]
0x14001af00  call    CdRaiseStatusEx
0x14001bf34  push    rbp
0x14001bf36  sub     rsp, 30h
0x14001bf3a  mov     rbp, rdx
0x14001bf3d  cmp     byte ptr [rbp+30h], 0
  ... truncated ...
```
