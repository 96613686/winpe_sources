# GetPreviousValue

- ea: `0x14000c990`
- end: `0x14000cf04`
- name: `GetPreviousValue`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002110`

## callees

- `0x140003510`
- `0x140003550`
- `0x14000c990`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000c9e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cc29`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c9e9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cc29`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000caaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbfe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000caaf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbfe`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ca4e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb0f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb5b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb9a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cc92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cd0c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cd92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ce18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cea6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ca4e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb0f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb5b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cb9a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cc92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cd0c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cd92`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000ce18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000cea6`
- `FLTMGR!FltQueryInformationFile` at `0x14000cc6a`
- `FLTMGR!FltQueryInformationFile` at `0x14000cce8`
- `FLTMGR!FltQueryInformationFile` at `0x14000cd6a`
- `FLTMGR!FltQueryInformationFile` at `0x14000cdf0`
- `FLTMGR!FltQueryInformationFile` at `0x14000ce82`
- `FLTMGR!FltQueryInformationFile` at `0x14000cc6a`
- `FLTMGR!FltQueryInformationFile` at `0x14000cce8`
- `FLTMGR!FltQueryInformationFile` at `0x14000cd6a`
- `FLTMGR!FltQueryInformationFile` at `0x14000cdf0`
- `FLTMGR!FltQueryInformationFile` at `0x14000ce82`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000cbe2`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000cbe2`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca21`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca97`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca21`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca97`

## pseudocode

```c
void __fastcall GetPreviousValue(__int64 a1, __int64 a2, ULONG *a3, PVOID *a4)
{
  char v8; // cl
  ULONG v9; // r13d
  _DWORD *v10; // rax
  int v11; // ecx
  PVOID v12; // rax
  NTSTATUS VolumeInformation; // eax
  PVOID v14; // rax
  PVOID v15; // rax
  int v16; // ecx
  PVOID PoolWithTag; // rax
  __int64 v18; // rax
  PVOID v19; // rax
  PVOID v20; // rax
  struct _FILE_OBJECT *v21; // rdx
  struct _FLT_INSTANCE *v22; // rcx
  PVOID v23; // rax
  struct _FILE_OBJECT *v24; // rdx
  struct _FLT_INSTANCE *v25; // rcx
  PVOID v26; // rax
  char *v27; // rax
  signed int Length; // [rsp+20h] [rbp-49h]
  ULONG LengthNeeded[4]; // [rsp+30h] [rbp-39h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-29h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h]
  __int128 v32; // [rsp+58h] [rbp-11h] BYREF
  __int128 v33; // [rsp+68h] [rbp-1h]
  __int64 v34; // [rsp+78h] [rbp+Fh]

  v8 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 4LL);
  if ( v8 == 6 )
  {
    FileInformation = 0;
    v31 = 0;
    if ( KeGetCurrentIrql() > 1u )
      return;
    v16 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
    if ( v16 == 19 )
    {
      if ( FltQueryInformationFile(
             *(PFLT_INSTANCE *)(a2 + 24),
             *(PFILE_OBJECT *)(a2 + 32),
             &FileInformation,
             0x18u,
             FileStandardInformation,
             0) < 0 )
        return;
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0xCu, 0x72744C46u);
      *a4 = PoolWithTag;
      if ( !PoolWithTag )
        return;
      *a3 = 12;
      *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
      v18 = FileInformation;
    }
    else
    {
      if ( v16 == 13 )
      {
        if ( FltQueryInformationFile(
               *(PFLT_INSTANCE *)(a2 + 24),
               *(PFILE_OBJECT *)(a2 + 32),
               &FileInformation,
               0x18u,
               FileStandardInformation,
               0) >= 0 )
        {
          v19 = ExAllocatePoolWithTag((POOL_TYPE)512, 5u, 0x72744C46u);
          *a4 = v19;
          if ( v19 )
          {
            *a3 = 5;
            *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
            *((_BYTE *)*a4 + 4) = BYTE4(v31);
          }
        }
        return;
      }
      if ( v16 == 20 )
      {
        if ( FltQueryInformationFile(
               *(PFLT_INSTANCE *)(a2 + 24),
               *(PFILE_OBJECT *)(a2 + 32),
               &FileInformation,
               0x18u,
               FileStandardInformation,
               0) < 0 )
          return;
        v20 = ExAllocatePoolWithTag((POOL_TYPE)512, 0xCu, 0x72744C46u);
        *a4 = v20;
        if ( !v20 )
          return;
        *a3 = 12;
        *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
        v18 = *((_QWORD *)&FileInformation + 1);
      }
      else
      {
        if ( v16 != 14 )
        {
          if ( v16 == 4 )
          {
            v24 = *(struct _FILE_OBJECT **)(a2 + 32);
            v25 = *(struct _FLT_INSTANCE **)(a2 + 24);
            v32 = 0;
            v34 = 0;
            v33 = 0;
            if ( FltQueryInformationFile(v25, v24, &v32, 0x28u, FileBasicInformation, 0) >= 0 )
            {
              v26 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x2Cu, 0x72744C46u);
              *a4 = v26;
              if ( v26 )
              {
                *a3 = 44;
                *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
                v27 = (char *)*a4;
                *(_OWORD *)(v27 + 4) = v32;
                *(_OWORD *)(v27 + 20) = v33;
                *(_QWORD *)(v27 + 36) = v34;
              }
            }
          }
          return;
        }
        v21 = *(struct _FILE_OBJECT **)(a2 + 32);
        v22 = *(struct _FLT_INSTANCE **)(a2 + 24);
        *(_QWORD *)LengthNeeded = 0;
        if ( FltQueryInformationFile(v22, v21, LengthNeeded, 8u, FilePositionInformation, 0) < 0 )
          return;
        v23 = ExAllocatePoolWithTag((POOL_TYPE)512, 0xCu, 0x72744C46u);
        *a4 = v23;
        if ( !v23 )
          return;
        *a3 = 12;
        *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
        v18 = *(_QWORD *)LengthNeeded;
      }
    }
    *(_QWORD *)((char *)*a4 + 4) = v18;
    return;
  }
  if ( v8 != 11 )
  {
    if ( v8 != 21 )
      return;
    LengthNeeded[0] = 0;
    if ( KeGetCurrentIrql() > 1u
      || FltQuerySecurityObject(
           *(PFLT_INSTANCE *)(a2 + 24),
           *(PFILE_OBJECT *)(a2 + 32),
           *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL),
           0,
           0,
           LengthNeeded) != -1073741789 )
    {
      return;
    }
    v9 = LengthNeeded[0] + 4;
    v10 = ExAllocatePoolWithTag((POOL_TYPE)512, LengthNeeded[0] + 4, 0x72744C46u);
    *a4 = v10;
    if ( v10 )
    {
      *v10 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL);
      if ( FltQuerySecurityObject(
             *(PFLT_INSTANCE *)(a2 + 24),
             *(PFILE_OBJECT *)(a2 + 32),
             *(_DWORD *)(*(_QWORD *)(a1 + 16) + 24LL),
             (char *)*a4 + 4,
             v9 - 4,
             LengthNeeded) < 0 )
      {
        ExFreePoolWithTag(*a4, 0x72744C46u);
        *a4 = 0;
      }
      *a3 = v9;
      return;
    }
LABEL_25:
    *a3 = 0;
    return;
  }
  *(_OWORD *)LengthNeeded = 0;
  if ( GlobalLateBoundFunctions && !(unsigned __int8)GlobalLateBoundFunctions() || (**(_DWORD **)(a1 + 16) & 2) == 0 )
  {
    v11 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
    if ( v11 == 6 )
    {
      v12 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x34u, 0x72744C46u);
      *a4 = v12;
      if ( !v12 )
        return;
      *a3 = 52;
      *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
      VolumeInformation = FltQueryVolumeInformation(
                            *(PFLT_INSTANCE *)(a2 + 24),
                            (PIO_STATUS_BLOCK)LengthNeeded,
                            (char *)*a4 + 4,
                            *a3 - 4,
                            FileFsControlInformation);
    }
    else
    {
      if ( v11 == 2 )
      {
        v14 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x81Cu, 0x72744C46u);
        *a4 = v14;
        if ( !v14 )
          return;
        *a3 = 2076;
        Length = 1;
      }
      else
      {
        if ( v11 != 8 )
          return;
        v15 = ExAllocatePoolWithTag((POOL_TYPE)512, 0x44u, 0x72744C46u);
        *a4 = v15;
        if ( !v15 )
          return;
        *a3 = 68;
        Length = 8;
      }
      *(_DWORD *)*a4 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 32LL);
      VolumeInformation = FltQueryVolumeInformation(
                            *(PFLT_INSTANCE *)(a2 + 24),
                            (PIO_STATUS_BLOCK)LengthNeeded,
                            (char *)*a4 + 4,
                            *a3 - 4,
                            (FS_INFORMATION_CLASS)Length);
    }
    if ( VolumeInformation >= 0 )
      return;
    ExFreePoolWithTag(*a4, 0x72744C46u);
    *a4 = 0;
    goto LABEL_25;
  }
}

```

## disassembly

```asm
0x14000c990  push    rbp
0x14000c992  push    rsi
0x14000c993  push    rdi
0x14000c994  push    r13
0x14000c996  push    r14
0x14000c998  push    r15
0x14000c99a  lea     rbp, [rsp-2Fh]
0x14000c99f  sub     rsp, 98h
0x14000c9a6  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000c9ad  xor     rax, rsp
0x14000c9b0  mov     [rbp+57h+var_40], rax
0x14000c9b4  mov     rax, [rcx+10h]
0x14000c9b8  mov     r15, rcx
0x14000c9bb  mov     rdi, r9
0x14000c9be  mov     rsi, r8
0x14000c9c1  mov     r14, rdx
0x14000c9c4  mov     cl, [rax+4]
0x14000c9c7  cmp     cl, 6
0x14000c9ca  jz      loc_14000CC1C
0x14000c9d0  cmp     cl, 0Bh
0x14000c9d3  jz      loc_14000CACA
0x14000c9d9  cmp     cl, 15h
0x14000c9dc  jnz     loc_14000CEE6
0x14000c9e2  mov     [rbp+57h+var_90], 0
0x14000c9e9  call    cs:__imp_KeGetCurrentIrql
0x14000c9f0  nop     dword ptr [rax+rax+00h]
0x14000c9f5  cmp     al, 1
0x14000c9f7  ja      loc_14000CEE6
0x14000c9fd  mov     r8, [r15+10h]
0x14000ca01  lea     rax, [rbp+57h+var_90]
0x14000ca05  mov     rdx, [r14+20h]; FileObject
0x14000ca09  xor     r9d, r9d; SecurityDescriptor
0x14000ca0c  mov     rcx, [r14+18h]; Instance
0x14000ca10  mov     [rsp+0C0h+LengthNeeded], rax; LengthNeeded
0x14000ca15  mov     r8d, [r8+18h]; SecurityInformation
0x14000ca19  mov     [rsp+0C0h+Length], 0; Length
0x14000ca21  call    cs:__imp_FltQuerySecurityObject
0x14000ca28  nop     dword ptr [rax+rax+00h]
0x14000ca2d  cmp     eax, 0C0000023h
0x14000ca32  jnz     loc_14000CEE6
0x14000ca38  mov     r13d, [rbp+57h+var_90]
0x14000ca3c  mov     ecx, 200h; PoolType
0x14000ca41  add     r13d, 4
0x14000ca45  mov     r8d, 72744C46h; Tag
0x14000ca4b  mov     edx, r13d; NumberOfBytes
0x14000ca4e  call    cs:__imp_ExAllocatePoolWithTag
0x14000ca55  nop     dword ptr [rax+rax+00h]
0x14000ca5a  mov     [rdi], rax
0x14000ca5d  test    rax, rax
0x14000ca60  jz      loc_14000CC11
0x14000ca66  mov     rcx, [r15+10h]
0x14000ca6a  mov     edx, [rcx+18h]
0x14000ca6d  lea     rcx, [rbp+57h+var_90]
0x14000ca71  mov     [rax], edx
0x14000ca73  lea     eax, [r13-4]
0x14000ca77  mov     r8, [r15+10h]
0x14000ca7b  mov     r9, [rdi]
0x14000ca7e  mov     rdx, [r14+20h]; FileObject
0x14000ca82  add     r9, 4; SecurityDescriptor
0x14000ca86  mov     [rsp+0C0h+LengthNeeded], rcx; LengthNeeded
0x14000ca8b  mov     r8d, [r8+18h]; SecurityInformation
0x14000ca8f  mov     rcx, [r14+18h]; Instance
0x14000ca93  mov     [rsp+0C0h+Length], eax; Length
0x14000ca97  call    cs:__imp_FltQuerySecurityObject
0x14000ca9e  nop     dword ptr [rax+rax+00h]
0x14000caa3  test    eax, eax
0x14000caa5  jns     short loc_14000CAC2
0x14000caa7  mov     rcx, [rdi]; P
0x14000caaa  mov     edx, 72744C46h; Tag
0x14000caaf  call    cs:__imp_ExFreePoolWithTag
0x14000cab6  nop     dword ptr [rax+rax+00h]
0x14000cabb  mov     qword ptr [rdi], 0
0x14000cac2  mov     [rsi], r13d
0x14000cac5  jmp     loc_14000CEE6
0x14000caca  mov     rax, cs:GlobalLateBoundFunctions
0x14000cad1  xorps   xmm0, xmm0
0x14000cad4  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14000cad8  test    rax, rax
0x14000cadb  jz      short loc_14000CAE6
0x14000cadd  call    _guard_dispatch_icall
0x14000cae2  test    al, al
0x14000cae4  jz      short loc_14000CAF5
0x14000cae6  mov     rax, [r15+10h]
0x14000caea  mov     ecx, [rax]
0x14000caec  test    cl, 2
0x14000caef  jnz     loc_14000CEE6
0x14000caf5  mov     rax, [r15+10h]
0x14000caf9  mov     ecx, [rax+20h]
0x14000cafc  cmp     ecx, 6
0x14000caff  jnz     short loc_14000CB46
0x14000cb01  lea     edx, [rcx+2Eh]; NumberOfBytes
0x14000cb04  mov     r8d, 72744C46h; Tag
0x14000cb0a  mov     ecx, 200h; PoolType
0x14000cb0f  call    cs:__imp_ExAllocatePoolWithTag
0x14000cb16  nop     dword ptr [rax+rax+00h]
0x14000cb1b  mov     [rdi], rax
0x14000cb1e  test    rax, rax
0x14000cb21  jz      loc_14000CEE6
0x14000cb27  mov     dword ptr [rsi], 34h ; '4'
0x14000cb2d  mov     rax, [r15+10h]
0x14000cb31  mov     rdx, [rdi]
0x14000cb34  mov     [rsp+0C0h+Length], 6
0x14000cb3c  mov     eax, [rax+20h]
0x14000cb3f  mov     [rdx], eax
0x14000cb41  jmp     loc_14000CBCC
0x14000cb46  cmp     ecx, 2
0x14000cb49  jnz     short loc_14000CB83
0x14000cb4b  mov     edx, 81Ch; NumberOfBytes
0x14000cb50  mov     ecx, 200h; PoolType
0x14000cb55  mov     r8d, 72744C46h; Tag
0x14000cb5b  call    cs:__imp_ExAllocatePoolWithTag
0x14000cb62  nop     dword ptr [rax+rax+00h]
0x14000cb67  mov     [rdi], rax
0x14000cb6a  test    rax, rax
0x14000cb6d  jz      loc_14000CEE6
0x14000cb73  mov     dword ptr [rsi], 81Ch
0x14000cb79  mov     [rsp+0C0h+Length], 1
0x14000cb81  jmp     short loc_14000CBC0
0x14000cb83  cmp     ecx, 8
0x14000cb86  jnz     loc_14000CEE6
0x14000cb8c  lea     edx, [rcx+3Ch]; NumberOfBytes
0x14000cb8f  mov     r8d, 72744C46h; Tag
0x14000cb95  mov     ecx, 200h; PoolType
0x14000cb9a  call    cs:__imp_ExAllocatePoolWithTag
0x14000cba1  nop     dword ptr [rax+rax+00h]
0x14000cba6  mov     [rdi], rax
0x14000cba9  test    rax, rax
0x14000cbac  jz      loc_14000CEE6
0x14000cbb2  mov     dword ptr [rsi], 44h ; 'D'
0x14000cbb8  mov     [rsp+0C0h+Length], 8; FsInformationClass
0x14000cbc0  mov     rax, [r15+10h]
0x14000cbc4  mov     rcx, [rdi]
0x14000cbc7  mov     eax, [rax+20h]
0x14000cbca  mov     [rcx], eax
0x14000cbcc  mov     r9d, [rsi]
0x14000cbcf  lea     rdx, [rbp+57h+var_90]; Iosb
0x14000cbd3  mov     r8, [rdi]
0x14000cbd6  sub     r9d, 4; Length
0x14000cbda  mov     rcx, [r14+18h]; Instance
0x14000cbde  add     r8, 4; FsInformation
0x14000cbe2  call    cs:__imp_FltQueryVolumeInformation
0x14000cbe9  nop     dword ptr [rax+rax+00h]
0x14000cbee  test    eax, eax
0x14000cbf0  jns     loc_14000CEE6
0x14000cbf6  mov     rcx, [rdi]; P
0x14000cbf9  mov     edx, 72744C46h; Tag
0x14000cbfe  call    cs:__imp_ExFreePoolWithTag
0x14000cc05  nop     dword ptr [rax+rax+00h]
0x14000cc0a  mov     qword ptr [rdi], 0
0x14000cc11  mov     dword ptr [rsi], 0
0x14000cc17  jmp     loc_14000CEE6
0x14000cc1c  xorps   xmm0, xmm0
0x14000cc1f  xor     eax, eax
0x14000cc21  movups  [rbp+57h+FileInformation], xmm0
0x14000cc25  mov     [rbp+57h+var_70], rax
0x14000cc29  call    cs:__imp_KeGetCurrentIrql
0x14000cc30  nop     dword ptr [rax+rax+00h]
0x14000cc35  cmp     al, 1
0x14000cc37  ja      loc_14000CEE6
0x14000cc3d  mov     rax, [r15+10h]
0x14000cc41  mov     ecx, [rax+20h]
0x14000cc44  cmp     ecx, 13h
0x14000cc47  jnz     short loc_14000CCC2
0x14000cc49  mov     rdx, [r14+20h]; FileObject
0x14000cc4d  lea     r9d, [rcx+5]; Length
0x14000cc51  mov     rcx, [r14+18h]; Instance
0x14000cc55  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000cc59  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cc62  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000cc6a  call    cs:__imp_FltQueryInformationFile
0x14000cc71  nop     dword ptr [rax+rax+00h]
0x14000cc76  test    eax, eax
0x14000cc78  js      loc_14000CEE6
0x14000cc7e  mov     r14d, 0Ch
0x14000cc84  mov     r8d, 72744C46h; Tag
0x14000cc8a  mov     edx, r14d; NumberOfBytes
0x14000cc8d  mov     ecx, 200h; PoolType
0x14000cc92  call    cs:__imp_ExAllocatePoolWithTag
0x14000cc99  nop     dword ptr [rax+rax+00h]
0x14000cc9e  mov     [rdi], rax
0x14000cca1  test    rax, rax
0x14000cca4  jz      loc_14000CEE6
0x14000ccaa  mov     [rsi], r14d
0x14000ccad  mov     rax, [r15+10h]
0x14000ccb1  mov     rcx, [rdi]
0x14000ccb4  mov     eax, [rax+20h]
0x14000ccb7  mov     [rcx], eax
0x14000ccb9  mov     rax, qword ptr [rbp+57h+FileInformation]
0x14000ccbd  jmp     loc_14000CE43
0x14000ccc2  cmp     ecx, 0Dh
0x14000ccc5  jnz     short loc_14000CD44
0x14000ccc7  mov     rdx, [r14+20h]; FileObject
0x14000cccb  lea     r9d, [rcx+0Bh]; Length
0x14000cccf  mov     rcx, [r14+18h]; Instance
0x14000ccd3  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000ccd7  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cce0  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000cce8  call    cs:__imp_FltQueryInformationFile
0x14000ccef  nop     dword ptr [rax+rax+00h]
0x14000ccf4  test    eax, eax
0x14000ccf6  js      loc_14000CEE6
0x14000ccfc  mov     edx, 5; NumberOfBytes
0x14000cd01  mov     ecx, 200h; PoolType
0x14000cd06  mov     r8d, 72744C46h; Tag
0x14000cd0c  call    cs:__imp_ExAllocatePoolWithTag
0x14000cd13  nop     dword ptr [rax+rax+00h]
0x14000cd18  mov     [rdi], rax
0x14000cd1b  test    rax, rax
0x14000cd1e  jz      loc_14000CEE6
0x14000cd24  mov     dword ptr [rsi], 5
0x14000cd2a  mov     rax, [r15+10h]
0x14000cd2e  mov     rcx, [rdi]
0x14000cd31  mov     eax, [rax+20h]
0x14000cd34  mov     [rcx], eax
0x14000cd36  mov     rcx, [rdi]
0x14000cd39  mov     al, byte ptr [rbp+57h+var_70+4]
0x14000cd3c  mov     [rcx+4], al
0x14000cd3f  jmp     loc_14000CEE6
0x14000cd44  cmp     ecx, 14h
0x14000cd47  jnz     short loc_14000CDC2
0x14000cd49  mov     rdx, [r14+20h]; FileObject
0x14000cd4d  lea     r9d, [rcx+4]; Length
0x14000cd51  mov     rcx, [r14+18h]; Instance
0x14000cd55  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000cd59  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cd62  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000cd6a  call    cs:__imp_FltQueryInformationFile
0x14000cd71  nop     dword ptr [rax+rax+00h]
0x14000cd76  test    eax, eax
0x14000cd78  js      loc_14000CEE6
0x14000cd7e  mov     r14d, 0Ch
0x14000cd84  mov     r8d, 72744C46h; Tag
0x14000cd8a  mov     edx, r14d; NumberOfBytes
0x14000cd8d  mov     ecx, 200h; PoolType
0x14000cd92  call    cs:__imp_ExAllocatePoolWithTag
0x14000cd99  nop     dword ptr [rax+rax+00h]
0x14000cd9e  mov     [rdi], rax
0x14000cda1  test    rax, rax
0x14000cda4  jz      loc_14000CEE6
0x14000cdaa  mov     [rsi], r14d
0x14000cdad  mov     rax, [r15+10h]
0x14000cdb1  mov     rcx, [rdi]
0x14000cdb4  mov     eax, [rax+20h]
0x14000cdb7  mov     [rcx], eax
0x14000cdb9  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14000cdbd  jmp     loc_14000CE43
0x14000cdc2  cmp     ecx, 0Eh
0x14000cdc5  jnz     loc_14000CE4F
0x14000cdcb  mov     rdx, [r14+20h]; FileObject
0x14000cdcf  lea     r9d, [rcx-6]; Length
0x14000cdd3  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cddc  lea     r8, [rbp+57h+var_90]; FileInformation
0x14000cde0  mov     [rsp+0C0h+Length], ecx; FileInformationClass
0x14000cde4  mov     rcx, [r14+18h]; Instance
0x14000cde8  mov     qword ptr [rbp+57h+var_90], 0
0x14000cdf0  call    cs:__imp_FltQueryInformationFile
0x14000cdf7  nop     dword ptr [rax+rax+00h]
0x14000cdfc  test    eax, eax
0x14000cdfe  js      loc_14000CEE6
0x14000ce04  mov     r14d, 0Ch
0x14000ce0a  mov     r8d, 72744C46h; Tag
0x14000ce10  mov     edx, r14d; NumberOfBytes
0x14000ce13  mov     ecx, 200h; PoolType
0x14000ce18  call    cs:__imp_ExAllocatePoolWithTag
0x14000ce1f  nop     dword ptr [rax+rax+00h]
0x14000ce24  mov     [rdi], rax
0x14000ce27  test    rax, rax
0x14000ce2a  jz      loc_14000CEE6
0x14000ce30  mov     [rsi], r14d
0x14000ce33  mov     rax, [r15+10h]
0x14000ce37  mov     rcx, [rdi]
0x14000ce3a  mov     eax, [rax+20h]
0x14000ce3d  mov     [rcx], eax
0x14000ce3f  mov     rax, qword ptr [rbp+57h+var_90]
0x14000ce43  mov     rcx, [rdi]
0x14000ce46  mov     [rcx+4], rax
0x14000ce4a  jmp     loc_14000CEE6
0x14000ce4f  cmp     ecx, 4
0x14000ce52  jnz     loc_14000CEE6
0x14000ce58  mov     rdx, [r14+20h]; FileObject
0x14000ce5c  lea     r9d, [rcx+24h]; Length
0x14000ce60  xor     eax, eax
0x14000ce62  lea     r8, [rbp+57h+var_68]; FileInformation
0x14000ce66  xorps   xmm0, xmm0
0x14000ce69  mov     [rsp+0C0h+LengthNeeded], rax; LengthReturned
0x14000ce6e  mov     [rsp+0C0h+Length], ecx; FileInformationClass
0x14000ce72  mov     rcx, [r14+18h]; Instance
0x14000ce76  movups  [rbp+57h+var_68], xmm0
0x14000ce7a  mov     [rbp+57h+var_48], rax
0x14000ce7e  movups  [rbp+57h+var_58], xmm0
0x14000ce82  call    cs:__imp_FltQueryInformationFile
0x14000ce89  nop     dword ptr [rax+rax+00h]
0x14000ce8e  test    eax, eax
0x14000ce90  js      short loc_14000CEE6
0x14000ce92  mov     r14d, 2Ch ; ','
0x14000ce98  mov     r8d, 72744C46h; Tag
0x14000ce9e  mov     edx, r14d; NumberOfBytes
0x14000cea1  mov     ecx, 200h; PoolType
0x14000cea6  call    cs:__imp_ExAllocatePoolWithTag
0x14000cead  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
