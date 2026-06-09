# GetPreviousValue

- ea: `0x14000c95c`
- end: `0x14000cec6`
- name: `GetPreviousValue`
- size: `1386`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002110`

## callees

- `0x140003510`
- `0x140003550`
- `0x14000c95c`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000c9b5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cbf1`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000c9b5`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000cbf1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ca7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbc6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ca7b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000cbc6`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca1a`
- `ntoskrnl!ExAllocatePool2` at `0x14000cad9`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb25`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb62`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc59`
- `ntoskrnl!ExAllocatePool2` at `0x14000ccd1`
- `ntoskrnl!ExAllocatePool2` at `0x14000cd56`
- `ntoskrnl!ExAllocatePool2` at `0x14000cddb`
- `ntoskrnl!ExAllocatePool2` at `0x14000ce68`
- `ntoskrnl!ExAllocatePool2` at `0x14000ca1a`
- `ntoskrnl!ExAllocatePool2` at `0x14000cad9`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb25`
- `ntoskrnl!ExAllocatePool2` at `0x14000cb62`
- `ntoskrnl!ExAllocatePool2` at `0x14000cc59`
- `ntoskrnl!ExAllocatePool2` at `0x14000ccd1`
- `ntoskrnl!ExAllocatePool2` at `0x14000cd56`
- `ntoskrnl!ExAllocatePool2` at `0x14000cddb`
- `ntoskrnl!ExAllocatePool2` at `0x14000ce68`
- `FLTMGR!FltQueryInformationFile` at `0x14000cc32`
- `FLTMGR!FltQueryInformationFile` at `0x14000ccaf`
- `FLTMGR!FltQueryInformationFile` at `0x14000cd2f`
- `FLTMGR!FltQueryInformationFile` at `0x14000cdb4`
- `FLTMGR!FltQueryInformationFile` at `0x14000ce45`
- `FLTMGR!FltQueryInformationFile` at `0x14000cc32`
- `FLTMGR!FltQueryInformationFile` at `0x14000ccaf`
- `FLTMGR!FltQueryInformationFile` at `0x14000cd2f`
- `FLTMGR!FltQueryInformationFile` at `0x14000cdb4`
- `FLTMGR!FltQueryInformationFile` at `0x14000ce45`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000cbaa`
- `FLTMGR!FltQueryVolumeInformation` at `0x14000cbaa`
- `FLTMGR!FltQuerySecurityObject` at `0x14000c9ed`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca63`
- `FLTMGR!FltQuerySecurityObject` at `0x14000c9ed`
- `FLTMGR!FltQuerySecurityObject` at `0x14000ca63`

## pseudocode

```c
void __fastcall GetPreviousValue(__int64 a1, __int64 a2, ULONG *a3, PVOID *a4)
{
  char v8; // cl
  ULONG v9; // r13d
  _DWORD *v10; // rax
  int v11; // ecx
  __int64 v12; // rax
  NTSTATUS VolumeInformation; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  int v16; // ecx
  __int64 Pool2; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  struct _FILE_OBJECT *v21; // rdx
  struct _FLT_INSTANCE *v22; // rcx
  __int64 v23; // rax
  struct _FILE_OBJECT *v24; // rdx
  struct _FLT_INSTANCE *v25; // rcx
  __int64 v26; // rax
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
      Pool2 = ExAllocatePool2(66, 12, 1920224326);
      *a4 = (PVOID)Pool2;
      if ( !Pool2 )
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
          v19 = ExAllocatePool2(66, 5, 1920224326);
          *a4 = (PVOID)v19;
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
        v20 = ExAllocatePool2(66, 12, 1920224326);
        *a4 = (PVOID)v20;
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
              v26 = ExAllocatePool2(66, 44, 1920224326);
              *a4 = (PVOID)v26;
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
        v23 = ExAllocatePool2(66, 12, 1920224326);
        *a4 = (PVOID)v23;
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
    v10 = (_DWORD *)ExAllocatePool2(64, LengthNeeded[0] + 4, 1920224326);
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
      v12 = ExAllocatePool2(64, 52, 1920224326);
      *a4 = (PVOID)v12;
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
        v14 = ExAllocatePool2(64, 2076, 1920224326);
        *a4 = (PVOID)v14;
        if ( !v14 )
          return;
        *a3 = 2076;
        Length = 1;
      }
      else
      {
        if ( v11 != 8 )
          return;
        v15 = ExAllocatePool2(64, 68, 1920224326);
        *a4 = (PVOID)v15;
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
0x14000c95c  push    rbp
0x14000c95e  push    rsi
0x14000c95f  push    rdi
0x14000c960  push    r13
0x14000c962  push    r14
0x14000c964  push    r15
0x14000c966  lea     rbp, [rsp-2Fh]
0x14000c96b  sub     rsp, 98h
0x14000c972  mov     rax, cs:WmiRegistrationContext.DeviceExtension
0x14000c979  xor     rax, rsp
0x14000c97c  mov     [rbp+57h+var_40], rax
0x14000c980  mov     rax, [rcx+10h]
0x14000c984  mov     r15, rcx
0x14000c987  mov     rdi, r9
0x14000c98a  mov     rsi, r8
0x14000c98d  mov     r14, rdx
0x14000c990  mov     cl, [rax+4]
0x14000c993  cmp     cl, 6
0x14000c996  jz      loc_14000CBE4
0x14000c99c  cmp     cl, 0Bh
0x14000c99f  jz      loc_14000CA96
0x14000c9a5  cmp     cl, 15h
0x14000c9a8  jnz     loc_14000CEA8
0x14000c9ae  mov     [rbp+57h+var_90], 0
0x14000c9b5  call    cs:__imp_KeGetCurrentIrql
0x14000c9bc  nop     dword ptr [rax+rax+00h]
0x14000c9c1  cmp     al, 1
0x14000c9c3  ja      loc_14000CEA8
0x14000c9c9  mov     r8, [r15+10h]
0x14000c9cd  lea     rax, [rbp+57h+var_90]
0x14000c9d1  mov     rdx, [r14+20h]; FileObject
0x14000c9d5  xor     r9d, r9d; SecurityDescriptor
0x14000c9d8  mov     rcx, [r14+18h]; Instance
0x14000c9dc  mov     [rsp+0C0h+LengthNeeded], rax; LengthNeeded
0x14000c9e1  mov     r8d, [r8+18h]; SecurityInformation
0x14000c9e5  mov     [rsp+0C0h+Length], 0; Length
0x14000c9ed  call    cs:__imp_FltQuerySecurityObject
0x14000c9f4  nop     dword ptr [rax+rax+00h]
0x14000c9f9  cmp     eax, 0C0000023h
0x14000c9fe  jnz     loc_14000CEA8
0x14000ca04  mov     r13d, [rbp+57h+var_90]
0x14000ca08  mov     ecx, 40h ; '@'
0x14000ca0d  add     r13d, 4
0x14000ca11  mov     r8d, 72744C46h
0x14000ca17  mov     edx, r13d
0x14000ca1a  call    cs:__imp_ExAllocatePool2
0x14000ca21  nop     dword ptr [rax+rax+00h]
0x14000ca26  mov     [rdi], rax
0x14000ca29  test    rax, rax
0x14000ca2c  jz      loc_14000CBD9
0x14000ca32  mov     rcx, [r15+10h]
0x14000ca36  mov     edx, [rcx+18h]
0x14000ca39  lea     rcx, [rbp+57h+var_90]
0x14000ca3d  mov     [rax], edx
0x14000ca3f  lea     eax, [r13-4]
0x14000ca43  mov     r8, [r15+10h]
0x14000ca47  mov     r9, [rdi]
0x14000ca4a  mov     rdx, [r14+20h]; FileObject
0x14000ca4e  add     r9, 4; SecurityDescriptor
0x14000ca52  mov     [rsp+0C0h+LengthNeeded], rcx; LengthNeeded
0x14000ca57  mov     r8d, [r8+18h]; SecurityInformation
0x14000ca5b  mov     rcx, [r14+18h]; Instance
0x14000ca5f  mov     [rsp+0C0h+Length], eax; Length
0x14000ca63  call    cs:__imp_FltQuerySecurityObject
0x14000ca6a  nop     dword ptr [rax+rax+00h]
0x14000ca6f  test    eax, eax
0x14000ca71  jns     short loc_14000CA8E
0x14000ca73  mov     rcx, [rdi]; P
0x14000ca76  mov     edx, 72744C46h; Tag
0x14000ca7b  call    cs:__imp_ExFreePoolWithTag
0x14000ca82  nop     dword ptr [rax+rax+00h]
0x14000ca87  mov     qword ptr [rdi], 0
0x14000ca8e  mov     [rsi], r13d
0x14000ca91  jmp     loc_14000CEA8
0x14000ca96  mov     rax, cs:GlobalLateBoundFunctions
0x14000ca9d  xorps   xmm0, xmm0
0x14000caa0  movups  xmmword ptr [rbp+57h+var_90], xmm0
0x14000caa4  test    rax, rax
0x14000caa7  jz      short loc_14000CAB2
0x14000caa9  call    _guard_dispatch_icall
0x14000caae  test    al, al
0x14000cab0  jz      short loc_14000CAC1
0x14000cab2  mov     rax, [r15+10h]
0x14000cab6  mov     ecx, [rax]
0x14000cab8  test    cl, 2
0x14000cabb  jnz     loc_14000CEA8
0x14000cac1  mov     rax, [r15+10h]
0x14000cac5  mov     ecx, [rax+20h]
0x14000cac8  cmp     ecx, 6
0x14000cacb  jnz     short loc_14000CB10
0x14000cacd  lea     edx, [rcx+2Eh]
0x14000cad0  mov     r8d, 72744C46h
0x14000cad6  lea     ecx, [rdx+0Ch]
0x14000cad9  call    cs:__imp_ExAllocatePool2
0x14000cae0  nop     dword ptr [rax+rax+00h]
0x14000cae5  mov     [rdi], rax
0x14000cae8  test    rax, rax
0x14000caeb  jz      loc_14000CEA8
0x14000caf1  mov     dword ptr [rsi], 34h ; '4'
0x14000caf7  mov     rax, [r15+10h]
0x14000cafb  mov     rdx, [rdi]
0x14000cafe  mov     [rsp+0C0h+Length], 6
0x14000cb06  mov     eax, [rax+20h]
0x14000cb09  mov     [rdx], eax
0x14000cb0b  jmp     loc_14000CB94
0x14000cb10  cmp     ecx, 2
0x14000cb13  jnz     short loc_14000CB4D
0x14000cb15  mov     edx, 81Ch
0x14000cb1a  mov     ecx, 40h ; '@'
0x14000cb1f  mov     r8d, 72744C46h
0x14000cb25  call    cs:__imp_ExAllocatePool2
0x14000cb2c  nop     dword ptr [rax+rax+00h]
0x14000cb31  mov     [rdi], rax
0x14000cb34  test    rax, rax
0x14000cb37  jz      loc_14000CEA8
0x14000cb3d  mov     dword ptr [rsi], 81Ch
0x14000cb43  mov     [rsp+0C0h+Length], 1
0x14000cb4b  jmp     short loc_14000CB88
0x14000cb4d  cmp     ecx, 8
0x14000cb50  jnz     loc_14000CEA8
0x14000cb56  lea     edx, [rcx+3Ch]
0x14000cb59  mov     r8d, 72744C46h
0x14000cb5f  lea     ecx, [rdx-4]
0x14000cb62  call    cs:__imp_ExAllocatePool2
0x14000cb69  nop     dword ptr [rax+rax+00h]
0x14000cb6e  mov     [rdi], rax
0x14000cb71  test    rax, rax
0x14000cb74  jz      loc_14000CEA8
0x14000cb7a  mov     dword ptr [rsi], 44h ; 'D'
0x14000cb80  mov     [rsp+0C0h+Length], 8; FsInformationClass
0x14000cb88  mov     rax, [r15+10h]
0x14000cb8c  mov     rcx, [rdi]
0x14000cb8f  mov     eax, [rax+20h]
0x14000cb92  mov     [rcx], eax
0x14000cb94  mov     r9d, [rsi]
0x14000cb97  lea     rdx, [rbp+57h+var_90]; Iosb
0x14000cb9b  mov     r8, [rdi]
0x14000cb9e  sub     r9d, 4; Length
0x14000cba2  mov     rcx, [r14+18h]; Instance
0x14000cba6  add     r8, 4; FsInformation
0x14000cbaa  call    cs:__imp_FltQueryVolumeInformation
0x14000cbb1  nop     dword ptr [rax+rax+00h]
0x14000cbb6  test    eax, eax
0x14000cbb8  jns     loc_14000CEA8
0x14000cbbe  mov     rcx, [rdi]; P
0x14000cbc1  mov     edx, 72744C46h; Tag
0x14000cbc6  call    cs:__imp_ExFreePoolWithTag
0x14000cbcd  nop     dword ptr [rax+rax+00h]
0x14000cbd2  mov     qword ptr [rdi], 0
0x14000cbd9  mov     dword ptr [rsi], 0
0x14000cbdf  jmp     loc_14000CEA8
0x14000cbe4  xorps   xmm0, xmm0
0x14000cbe7  xor     eax, eax
0x14000cbe9  movups  [rbp+57h+FileInformation], xmm0
0x14000cbed  mov     [rbp+57h+var_70], rax
0x14000cbf1  call    cs:__imp_KeGetCurrentIrql
0x14000cbf8  nop     dword ptr [rax+rax+00h]
0x14000cbfd  cmp     al, 1
0x14000cbff  ja      loc_14000CEA8
0x14000cc05  mov     rax, [r15+10h]
0x14000cc09  mov     ecx, [rax+20h]
0x14000cc0c  cmp     ecx, 13h
0x14000cc0f  jnz     short loc_14000CC89
0x14000cc11  mov     rdx, [r14+20h]; FileObject
0x14000cc15  lea     r9d, [rcx+5]; Length
0x14000cc19  mov     rcx, [r14+18h]; Instance
0x14000cc1d  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000cc21  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cc2a  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000cc32  call    cs:__imp_FltQueryInformationFile
0x14000cc39  nop     dword ptr [rax+rax+00h]
0x14000cc3e  test    eax, eax
0x14000cc40  js      loc_14000CEA8
0x14000cc46  mov     r14d, 0Ch
0x14000cc4c  mov     r8d, 72744C46h
0x14000cc52  mov     edx, r14d
0x14000cc55  lea     ecx, [r14+36h]
0x14000cc59  call    cs:__imp_ExAllocatePool2
0x14000cc60  nop     dword ptr [rax+rax+00h]
0x14000cc65  mov     [rdi], rax
0x14000cc68  test    rax, rax
0x14000cc6b  jz      loc_14000CEA8
0x14000cc71  mov     [rsi], r14d
0x14000cc74  mov     rax, [r15+10h]
0x14000cc78  mov     rcx, [rdi]
0x14000cc7b  mov     eax, [rax+20h]
0x14000cc7e  mov     [rcx], eax
0x14000cc80  mov     rax, qword ptr [rbp+57h+FileInformation]
0x14000cc84  jmp     loc_14000CE06
0x14000cc89  cmp     ecx, 0Dh
0x14000cc8c  jnz     short loc_14000CD09
0x14000cc8e  mov     rdx, [r14+20h]; FileObject
0x14000cc92  lea     r9d, [rcx+0Bh]; Length
0x14000cc96  mov     rcx, [r14+18h]; Instance
0x14000cc9a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000cc9e  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cca7  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000ccaf  call    cs:__imp_FltQueryInformationFile
0x14000ccb6  nop     dword ptr [rax+rax+00h]
0x14000ccbb  test    eax, eax
0x14000ccbd  js      loc_14000CEA8
0x14000ccc3  mov     edx, 5
0x14000ccc8  mov     r8d, 72744C46h
0x14000ccce  lea     ecx, [rdx+3Dh]
0x14000ccd1  call    cs:__imp_ExAllocatePool2
0x14000ccd8  nop     dword ptr [rax+rax+00h]
0x14000ccdd  mov     [rdi], rax
0x14000cce0  test    rax, rax
0x14000cce3  jz      loc_14000CEA8
0x14000cce9  mov     dword ptr [rsi], 5
0x14000ccef  mov     rax, [r15+10h]
0x14000ccf3  mov     rcx, [rdi]
0x14000ccf6  mov     eax, [rax+20h]
0x14000ccf9  mov     [rcx], eax
0x14000ccfb  mov     rcx, [rdi]
0x14000ccfe  mov     al, byte ptr [rbp+57h+var_70+4]
0x14000cd01  mov     [rcx+4], al
0x14000cd04  jmp     loc_14000CEA8
0x14000cd09  cmp     ecx, 14h
0x14000cd0c  jnz     short loc_14000CD86
0x14000cd0e  mov     rdx, [r14+20h]; FileObject
0x14000cd12  lea     r9d, [rcx+4]; Length
0x14000cd16  mov     rcx, [r14+18h]; Instance
0x14000cd1a  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x14000cd1e  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cd27  mov     [rsp+0C0h+Length], 5; FileInformationClass
0x14000cd2f  call    cs:__imp_FltQueryInformationFile
0x14000cd36  nop     dword ptr [rax+rax+00h]
0x14000cd3b  test    eax, eax
0x14000cd3d  js      loc_14000CEA8
0x14000cd43  mov     r14d, 0Ch
0x14000cd49  mov     r8d, 72744C46h
0x14000cd4f  mov     edx, r14d
0x14000cd52  lea     ecx, [r14+36h]
0x14000cd56  call    cs:__imp_ExAllocatePool2
0x14000cd5d  nop     dword ptr [rax+rax+00h]
0x14000cd62  mov     [rdi], rax
0x14000cd65  test    rax, rax
0x14000cd68  jz      loc_14000CEA8
0x14000cd6e  mov     [rsi], r14d
0x14000cd71  mov     rax, [r15+10h]
0x14000cd75  mov     rcx, [rdi]
0x14000cd78  mov     eax, [rax+20h]
0x14000cd7b  mov     [rcx], eax
0x14000cd7d  mov     rax, qword ptr [rbp+57h+FileInformation+8]
0x14000cd81  jmp     loc_14000CE06
0x14000cd86  cmp     ecx, 0Eh
0x14000cd89  jnz     loc_14000CE12
0x14000cd8f  mov     rdx, [r14+20h]; FileObject
0x14000cd93  lea     r9d, [rcx-6]; Length
0x14000cd97  mov     [rsp+0C0h+LengthNeeded], 0; LengthReturned
0x14000cda0  lea     r8, [rbp+57h+var_90]; FileInformation
0x14000cda4  mov     [rsp+0C0h+Length], ecx; FileInformationClass
0x14000cda8  mov     rcx, [r14+18h]; Instance
0x14000cdac  mov     qword ptr [rbp+57h+var_90], 0
0x14000cdb4  call    cs:__imp_FltQueryInformationFile
0x14000cdbb  nop     dword ptr [rax+rax+00h]
0x14000cdc0  test    eax, eax
0x14000cdc2  js      loc_14000CEA8
0x14000cdc8  mov     r14d, 0Ch
0x14000cdce  mov     r8d, 72744C46h
0x14000cdd4  mov     edx, r14d
0x14000cdd7  lea     ecx, [r14+36h]
0x14000cddb  call    cs:__imp_ExAllocatePool2
0x14000cde2  nop     dword ptr [rax+rax+00h]
0x14000cde7  mov     [rdi], rax
0x14000cdea  test    rax, rax
0x14000cded  jz      loc_14000CEA8
0x14000cdf3  mov     [rsi], r14d
0x14000cdf6  mov     rax, [r15+10h]
0x14000cdfa  mov     rcx, [rdi]
0x14000cdfd  mov     eax, [rax+20h]
0x14000ce00  mov     [rcx], eax
0x14000ce02  mov     rax, qword ptr [rbp+57h+var_90]
0x14000ce06  mov     rcx, [rdi]
0x14000ce09  mov     [rcx+4], rax
0x14000ce0d  jmp     loc_14000CEA8
0x14000ce12  cmp     ecx, 4
0x14000ce15  jnz     loc_14000CEA8
0x14000ce1b  mov     rdx, [r14+20h]; FileObject
0x14000ce1f  lea     r9d, [rcx+24h]; Length
0x14000ce23  xor     eax, eax
0x14000ce25  lea     r8, [rbp+57h+var_68]; FileInformation
0x14000ce29  xorps   xmm0, xmm0
0x14000ce2c  mov     [rsp+0C0h+LengthNeeded], rax; LengthReturned
0x14000ce31  mov     [rsp+0C0h+Length], ecx; FileInformationClass
0x14000ce35  mov     rcx, [r14+18h]; Instance
0x14000ce39  movups  [rbp+57h+var_68], xmm0
0x14000ce3d  mov     [rbp+57h+var_48], rax
0x14000ce41  movups  [rbp+57h+var_58], xmm0
0x14000ce45  call    cs:__imp_FltQueryInformationFile
0x14000ce4c  nop     dword ptr [rax+rax+00h]
0x14000ce51  test    eax, eax
0x14000ce53  js      short loc_14000CEA8
0x14000ce55  mov     r14d, 2Ch ; ','
0x14000ce5b  mov     r8d, 72744C46h
0x14000ce61  mov     edx, r14d
0x14000ce64  lea     ecx, [r14+16h]
0x14000ce68  call    cs:__imp_ExAllocatePool2
0x14000ce6f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
