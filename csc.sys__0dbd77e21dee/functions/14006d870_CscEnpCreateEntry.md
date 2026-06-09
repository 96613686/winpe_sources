# CscEnpCreateEntry

- ea: `0x14006d870`
- end: `0x14006dd7e`
- name: `CscEnpCreateEntry`
- size: `1294`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING **, _BYTE *, PWSTR *)`
- caller_count: `4`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x14000aaf0`
- `0x14000b0e0`
- `0x140059edc`
- `0x14006bc40`

## callees

- `0x1400081b0`
- `0x14000c6a0`
- `0x140010b00`
- `0x140012ed0`
- `0x14002d44c`
- `0x14005c44c`
- `0x14005db10`
- `0x14006d870`
- `0x14006dd90`
- `0x140071c00`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14006d8d5`
- `ntoskrnl!ExAllocatePool2` at `0x14006d94b`
- `ntoskrnl!ExAllocatePool2` at `0x14006d990`
- `ntoskrnl!ExAllocatePool2` at `0x14006d8d5`
- `ntoskrnl!ExAllocatePool2` at `0x14006d94b`
- `ntoskrnl!ExAllocatePool2` at `0x14006d990`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc79`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006dc79`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006d966`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006d9ab`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006d966`
- `ntoskrnl!ExInitializeResourceLite` at `0x14006d9ab`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14006dab3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14006dad4`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14006dab3`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14006dad4`
- `ntoskrnl!RtlAssert` at `0x14006dc44`
- `ntoskrnl!RtlAssert` at `0x14006dc44`

## pseudocode

```c
__int64 __fastcall CscEnpCreateEntry(struct _UNICODE_STRING **a1, _BYTE *a2, PWSTR *a3)
{
  PWSTR v3; // rdi
  unsigned __int64 v7; // rbp
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v9; // rbx
  __int64 v10; // r12
  __int64 v11; // rbp
  __int64 v12; // rax
  struct _ERESOURCE *v13; // rax
  struct _ERESOURCE *v14; // r13
  NTSTATUS InformationFile; // edi
  struct _ERESOURCE *v16; // rax
  struct _ERESOURCE *v17; // r13
  WCHAR *v18; // rax
  PWSTR v19; // rax
  int v20; // edi
  PWSTR v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  struct _UNICODE_STRING *v24; // rax
  PWSTR v25; // rcx
  __int64 result; // rax
  PWSTR Buffer; // rax
  WCHAR *v28; // rcx
  struct _UNICODE_STRING v29; // xmm0
  PWSTR v30; // rax
  USHORT InitialDiffTransferType; // ax
  UNICODE_STRING StringIn; // [rsp+40h] [rbp-58h] BYREF
  UNICODE_STRING v33; // [rsp+50h] [rbp-48h] BYREF
  char v34; // [rsp+A0h] [rbp+8h] BYREF
  __int64 v35; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v36; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a3[1];
  v36 = 0;
  v34 = 0;
  LODWORD(v35) = 0;
  *a1 = 0;
  StringIn = 0;
  v33 = 0;
  if ( !v3 )
    v3 = (PWSTR)*((_QWORD *)*a3 + 1);
  v7 = *((unsigned int *)v3 + 86);
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, v7, 641758019);
  v9 = Pool2;
  if ( !Pool2 )
  {
    v10 = 4;
    v11 = 144;
LABEL_42:
    InformationFile = -1073741670;
    goto LABEL_29;
  }
  Pool2->Length = -9723;
  v10 = (__int64)(&Pool2->MaximumLength + 1);
  if ( v7 > 0x7FFF )
    LOWORD(v7) = 0x7FFF;
  Pool2->MaximumLength = v7;
  v11 = (__int64)&Pool2[9];
  v12 = *((unsigned int *)v3 + 87);
  *(_DWORD *)v10 = 1;
  v9[24].Buffer = (USHORT *)((char *)&v9->Length + v12);
  *(_DWORD *)(&v9[1].MaximumLength + 1) = 0;
  v9[5].Buffer = &v9[5].Length;
  *(_QWORD *)&v9[5].Length = v9 + 5;
  *(_QWORD *)&v9[9].Length = a3[2];
  v13 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155);
  v14 = v13;
  if ( !v13 )
  {
    InformationFile = -1073741670;
    goto LABEL_58;
  }
  InformationFile = ExInitializeResourceLite(v13);
  if ( InformationFile < 0 )
  {
    ExFreePoolWithTag(v14, 0x22407343u);
LABEL_58:
    *(_QWORD *)&v9[7].Length = 0;
    goto LABEL_29;
  }
  *(_QWORD *)&v9[7].Length = v14;
  v16 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155);
  v17 = v16;
  if ( !v16 )
  {
    v9[7].Buffer = 0;
    goto LABEL_42;
  }
  InformationFile = ExInitializeResourceLite(v16);
  if ( InformationFile < 0 )
  {
    ExFreePoolWithTag(v17, 0x22407343u);
    v9[7].Buffer = 0;
    goto LABEL_29;
  }
  v18 = a3[4];
  v9[7].Buffer = (PWSTR)v17;
  if ( v18 )
  {
    v9[8].Buffer = v18;
  }
  else
  {
    InformationFile = CscStorepLowIoQueryInformationFile(
                        *(HANDLE *)v11,
                        &v9[8].Buffer,
                        8u,
                        FileInternalInformation,
                        (__int64)&v35);
    if ( InformationFile < 0 )
      goto LABEL_29;
  }
  v19 = *a3;
  v9[1].Buffer = *a3;
  if ( !v19 )
  {
    v28 = a3[1];
    *(_DWORD *)&v9[1].Length = 0;
    v9->Buffer = v28;
    *(_DWORD *)&v9[12].Length = 2048;
    *(_DWORD *)&v9[21].Length = 16;
LABEL_23:
    *(_DWORD *)(&v9[1].MaximumLength + 1) |= 1u;
    if ( (*(_DWORD *)&v9[21].Length & 0x10) != 0 && (*(_DWORD *)(&v9[1].MaximumLength + 1) & 0x400) != 0 )
    {
      Buffer = v9[1].Buffer;
      if ( Buffer )
      {
        if ( (*((_DWORD *)Buffer + 5) & 0x400) == 0 )
          CscEnpCreateTombstoneCount(v9);
      }
    }
    if ( (*(_DWORD *)&v9[21].Length & 0x10) != 0 && (*(_DWORD *)(&v9[12].MaximumLength + 1) & 1) != 0 )
    {
      v25 = v9[1].Buffer;
      if ( v25 )
      {
        if ( (*((_DWORD *)v25 + 49) & 0x10) == 0 )
          CscEnpUpdateAncestorDfsLinkStatus();
      }
    }
    goto LABEL_29;
  }
  v20 = *((_DWORD *)v19 + 4);
  if ( v20 )
  {
    if ( v20 == 1 )
    {
      v20 = 2;
    }
    else if ( v20 == 2 )
    {
      v20 = 3;
    }
    else if ( v20 != 3 )
    {
      RtlAssert("0", "base\\fs\\remotefs\\rdr\\csc\\newdb\\entry_i.h", 0x47Du, 0);
    }
  }
  else
  {
    v20 = 1;
  }
  v21 = v9[1].Buffer;
  *(_DWORD *)&v9[1].Length = v20;
  v9->Buffer = (PWSTR)*((_QWORD *)v21 + 1);
  CscEnReferenceEntry(v21);
  v22 = (__int64)(v9[1].Buffer + 40);
  v23 = *(_QWORD *)v22;
  if ( *(_QWORD *)(*(_QWORD *)v22 + 8LL) != v22 )
    __fastfail(3u);
  *(_QWORD *)&v9[6].Length = v23;
  v9[6].Buffer = (PWSTR)v22;
  *(_QWORD *)(v23 + 8) = v9 + 6;
  *(_QWORD *)v22 = v9 + 6;
  InformationFile = CscEnpQueryChildNames(v9[1].Buffer, a3[3], &v9[8].Buffer, &v34, &v36, &StringIn, &v33);
  if ( InformationFile >= 0 )
  {
    InformationFile = RtlDuplicateUnicodeString(0, &StringIn, v9 + 3);
    if ( InformationFile >= 0 )
    {
      InformationFile = RtlDuplicateUnicodeString(0, &v33, v9 + 4);
      if ( InformationFile >= 0 )
      {
        v24 = (struct _UNICODE_STRING *)a3[6];
        if ( v24 )
        {
          v9[12] = *v24;
          v9[13] = v24[1];
          v9[14] = v24[2];
          v9[15] = v24[3];
          v29 = v24[4];
          v30 = a3[5];
          v9[16] = v29;
          v9[18] = *(struct _UNICODE_STRING *)v30;
          v9[19] = *((struct _UNICODE_STRING *)v30 + 1);
          v9[20] = *((struct _UNICODE_STRING *)v30 + 2);
          *(_QWORD *)&v9[21].Length = *((_QWORD *)v30 + 6);
          if ( (*(_DWORD *)&v9[21].Length & 0x10) != 0 )
            InitialDiffTransferType = 0;
          else
            InitialDiffTransferType = CscDiffTransferGetInitialDiffTransferType();
          *(&v9[24].MaximumLength + 1) = InitialDiffTransferType;
        }
        else
        {
          InformationFile = CscEnpReadAttributes(v9);
          if ( InformationFile < 0 )
            goto LABEL_29;
        }
        if ( v34 )
          *(_DWORD *)(&v9[1].MaximumLength + 1) |= 2u;
        goto LABEL_23;
      }
    }
  }
LABEL_29:
  if ( v36 )
    CscStorepLowIoFreeRenameInformation();
  if ( InformationFile < 0 && v9 )
  {
    *(_DWORD *)v10 = 0;
    *(_QWORD *)v11 = 0;
    CscEnpDestroyEntry(v9);
    v9 = 0;
  }
  if ( a2 )
    *a2 = v34;
  result = (unsigned int)InformationFile;
  *a1 = v9;
  return result;
}

```

## disassembly

```asm
0x14006d870  mov     rax, rsp
0x14006d873  push    rbx
0x14006d874  push    rbp
0x14006d875  push    rsi
0x14006d876  push    rdi
0x14006d877  push    r13
0x14006d879  push    r14
0x14006d87b  push    r15
0x14006d87d  sub     rsp, 60h
0x14006d881  mov     rdi, [r8+8]
0x14006d885  xor     r13d, r13d
0x14006d888  mov     [rax+20h], r13
0x14006d88c  xorps   xmm0, xmm0
0x14006d88f  mov     [rax+8], r13b
0x14006d893  xorps   xmm1, xmm1
0x14006d896  mov     [rax+18h], r13d
0x14006d89a  mov     r14, r8
0x14006d89d  mov     [rcx], r13
0x14006d8a0  mov     rsi, rdx
0x14006d8a3  mov     r15, rcx
0x14006d8a6  movups  xmmword ptr [rax-58h], xmm0
0x14006d8aa  movups  xmmword ptr [rax-48h], xmm1
0x14006d8ae  test    rdi, rdi
0x14006d8b1  jnz     short loc_14006D8BA
0x14006d8b3  mov     rax, [r8]
0x14006d8b6  mov     rdi, [rax+8]
0x14006d8ba  mov     ebp, [rdi+158h]
0x14006d8c0  mov     r8d, 26407343h
0x14006d8c6  mov     edx, ebp
0x14006d8c8  mov     [rsp+98h+arg_8], r12
0x14006d8d0  mov     ecx, 100h
0x14006d8d5  call    cs:__imp_ExAllocatePool2
0x14006d8dc  nop     dword ptr [rax+rax+00h]
0x14006d8e1  mov     rbx, rax
0x14006d8e4  test    rax, rax
0x14006d8e7  jz      loc_14006DC03
0x14006d8ed  mov     word ptr [rax], 0DA05h
0x14006d8f2  lea     r12, [rbx+4]
0x14006d8f6  mov     eax, 7FFFh
0x14006d8fb  mov     edx, 68h ; 'h'
0x14006d900  cmp     rbp, rax
0x14006d903  mov     ecx, 42h ; 'B'
0x14006d908  mov     r8d, 22407343h
0x14006d90e  cmova   ebp, eax
0x14006d911  mov     [rbx+2], bp
0x14006d915  lea     rbp, [rbx+90h]
0x14006d91c  mov     eax, [rdi+15Ch]
0x14006d922  add     rax, rbx
0x14006d925  mov     dword ptr [r12], 1
0x14006d92d  mov     [rbx+188h], rax
0x14006d934  lea     rax, [rbx+50h]
0x14006d938  mov     [rbx+14h], r13d
0x14006d93c  mov     [rax+8], rax
0x14006d940  mov     [rax], rax
0x14006d943  mov     rax, [r14+10h]
0x14006d947  mov     [rbp+0], rax
0x14006d94b  call    cs:__imp_ExAllocatePool2
0x14006d952  nop     dword ptr [rax+rax+00h]
0x14006d957  mov     r13, rax
0x14006d95a  test    rax, rax
0x14006d95d  jz      loc_14006DD4F
0x14006d963  mov     rcx, rax; Resource
0x14006d966  call    cs:__imp_ExInitializeResourceLite
0x14006d96d  nop     dword ptr [rax+rax+00h]
0x14006d972  mov     edi, eax
0x14006d974  test    eax, eax
0x14006d976  js      loc_14006DC55
0x14006d97c  mov     edx, 68h ; 'h'
0x14006d981  mov     [rbx+70h], r13
0x14006d985  mov     ecx, 42h ; 'B'
0x14006d98a  mov     r8d, 22407343h
0x14006d990  call    cs:__imp_ExAllocatePool2
0x14006d997  nop     dword ptr [rax+rax+00h]
0x14006d99c  mov     r13, rax
0x14006d99f  test    rax, rax
0x14006d9a2  jz      loc_14006DD43
0x14006d9a8  mov     rcx, rax; Resource
0x14006d9ab  call    cs:__imp_ExInitializeResourceLite
0x14006d9b2  nop     dword ptr [rax+rax+00h]
0x14006d9b7  mov     edi, eax
0x14006d9b9  test    eax, eax
0x14006d9bb  js      loc_14006DC71
0x14006d9c1  mov     rax, [r14+20h]
0x14006d9c5  mov     [rbx+78h], r13
0x14006d9c9  test    rax, rax
0x14006d9cc  jnz     loc_14006DB9E
0x14006d9d2  mov     rcx, [rbp+0]; FileHandle
0x14006d9d6  lea     rax, [rsp+98h+arg_10]
0x14006d9de  mov     r9d, 6; FileInformationClass
0x14006d9e4  mov     [rsp+98h+var_78], rax; __int64
0x14006d9e9  mov     r8d, 8; Length
0x14006d9ef  lea     rdx, [rbx+88h]; FileInformation
0x14006d9f6  call    CscStorepLowIoQueryInformationFile
0x14006d9fb  mov     edi, eax
0x14006d9fd  test    eax, eax
0x14006d9ff  js      loc_14006DB55
0x14006da05  mov     rax, [r14]
0x14006da08  mov     [rbx+18h], rax
0x14006da0c  test    rax, rax
0x14006da0f  jz      loc_14006DBDB
0x14006da15  mov     edi, [rax+10h]
0x14006da18  test    edi, edi
0x14006da1a  jnz     loc_14006DC18
0x14006da20  mov     edi, 1
0x14006da25  mov     rcx, [rbx+18h]
0x14006da29  mov     [rbx+10h], edi
0x14006da2c  mov     rax, [rcx+8]
0x14006da30  mov     [rbx+8], rax
0x14006da34  call    CscEnReferenceEntry
0x14006da39  mov     rdx, [rbx+18h]
0x14006da3d  add     rdx, 50h ; 'P'
0x14006da41  mov     r8, [rdx]
0x14006da44  cmp     [r8+8], rdx
0x14006da48  jnz     loc_14006DCA5
0x14006da4e  mov     [rbx+60h], r8
0x14006da52  lea     rax, [rbx+60h]
0x14006da56  mov     [rax+8], rdx
0x14006da5a  lea     r9, [rsp+98h+arg_0]
0x14006da62  mov     [r8+8], rax
0x14006da66  lea     r8, [rbx+88h]
0x14006da6d  mov     [rdx], rax
0x14006da70  lea     rax, [rsp+98h+var_48]
0x14006da75  mov     rdx, [r14+18h]
0x14006da79  mov     rcx, [rbx+18h]
0x14006da7d  mov     [rsp+98h+var_68], rax
0x14006da82  lea     rax, [rsp+98h+StringIn]
0x14006da87  mov     [rsp+98h+var_70], rax
0x14006da8c  lea     rax, [rsp+98h+arg_18]
0x14006da94  mov     [rsp+98h+var_78], rax
0x14006da99  call    CscEnpQueryChildNames
0x14006da9e  mov     edi, eax
0x14006daa0  test    eax, eax
0x14006daa2  js      loc_14006DB55
0x14006daa8  lea     r8, [rbx+30h]; StringOut
0x14006daac  xor     ecx, ecx; Flags
0x14006daae  lea     rdx, [rsp+98h+StringIn]; StringIn
0x14006dab3  call    cs:__imp_RtlDuplicateUnicodeString
0x14006daba  nop     dword ptr [rax+rax+00h]
0x14006dabf  mov     edi, eax
0x14006dac1  test    eax, eax
0x14006dac3  js      loc_14006DB55
0x14006dac9  lea     r8, [rbx+40h]; StringOut
0x14006dacd  xor     ecx, ecx; Flags
0x14006dacf  lea     rdx, [rsp+98h+var_48]; StringIn
0x14006dad4  call    cs:__imp_RtlDuplicateUnicodeString
0x14006dadb  nop     dword ptr [rax+rax+00h]
0x14006dae0  mov     edi, eax
0x14006dae2  test    eax, eax
0x14006dae4  js      short loc_14006DB55
0x14006dae6  mov     rax, [r14+30h]
0x14006daea  test    rax, rax
0x14006daed  jnz     loc_14006DCAC
0x14006daf3  mov     rcx, rbx
0x14006daf6  call    CscEnpReadAttributes
0x14006dafb  xor     r13d, r13d
0x14006dafe  mov     edi, eax
0x14006db00  test    eax, eax
0x14006db02  js      short loc_14006DB58
0x14006db04  cmp     [rsp+98h+arg_0], 0
0x14006db0c  jnz     loc_14006DD3A
0x14006db12  or      dword ptr [rbx+14h], 1
0x14006db16  mov     eax, [rbx+150h]
0x14006db1c  mov     ecx, [rbx+14h]
0x14006db1f  test    al, 10h
0x14006db21  jnz     loc_14006DBAA
0x14006db27  mov     eax, [rbx+150h]
0x14006db2d  test    al, 10h
0x14006db2f  jz      short loc_14006DB58
0x14006db31  mov     eax, [rbx+0C4h]
0x14006db37  test    al, 1
0x14006db39  jz      short loc_14006DB58
0x14006db3b  mov     rcx, [rbx+18h]
0x14006db3f  test    rcx, rcx
0x14006db42  jz      short loc_14006DB58
0x14006db44  mov     eax, [rcx+0C4h]
0x14006db4a  test    al, 10h
0x14006db4c  jnz     short loc_14006DB58
0x14006db4e  call    CscEnpUpdateAncestorDfsLinkStatus
0x14006db53  jmp     short loc_14006DB58
0x14006db55  xor     r13d, r13d
0x14006db58  mov     rcx, [rsp+98h+arg_18]
0x14006db60  test    rcx, rcx
0x14006db63  jz      short loc_14006DB6A
0x14006db65  call    CscStorepLowIoFreeRenameInformation
0x14006db6a  test    edi, edi
0x14006db6c  js      loc_14006DD5D
0x14006db72  test    rsi, rsi
0x14006db75  jz      short loc_14006DB81
0x14006db77  movzx   eax, [rsp+98h+arg_0]
0x14006db7f  mov     [rsi], al
0x14006db81  mov     r12, [rsp+98h+arg_8]
0x14006db89  mov     eax, edi
0x14006db8b  mov     [r15], rbx
0x14006db8e  add     rsp, 60h
0x14006db92  pop     r15
0x14006db94  pop     r14
0x14006db96  pop     r13
0x14006db98  pop     rdi
0x14006db99  pop     rsi
0x14006db9a  pop     rbp
0x14006db9b  pop     rbx
0x14006db9c  retn
0x14006db9e  mov     [rbx+88h], rax
0x14006dba5  jmp     loc_14006DA05
0x14006dbaa  bt      ecx, 0Ah
0x14006dbae  jnb     loc_14006DB27
0x14006dbb4  mov     rax, [rbx+18h]
0x14006dbb8  test    rax, rax
0x14006dbbb  jz      loc_14006DB27
0x14006dbc1  test    dword ptr [rax+14h], 400h
0x14006dbc8  jnz     loc_14006DB27
0x14006dbce  mov     rcx, rbx
0x14006dbd1  call    CscEnpCreateTombstoneCount
0x14006dbd6  jmp     loc_14006DB27
0x14006dbdb  mov     rcx, [r14+8]
0x14006dbdf  xor     r13d, r13d
0x14006dbe2  mov     [rbx+10h], r13d
0x14006dbe6  mov     [rbx+8], rcx
0x14006dbea  mov     dword ptr [rbx+0C0h], 800h
0x14006dbf4  mov     dword ptr [rbx+150h], 10h
0x14006dbfe  jmp     loc_14006DB12
0x14006dc03  lea     r12, [rax+4]
0x14006dc07  lea     rbp, [rax+90h]
0x14006dc0e  mov     edi, 0C000009Ah
0x14006dc13  jmp     loc_14006DB58
0x14006dc18  mov     ecx, edi
0x14006dc1a  sub     ecx, 1
0x14006dc1d  jz      short loc_14006DC9B
0x14006dc1f  sub     ecx, 1
0x14006dc22  jz      short loc_14006DC91
0x14006dc24  cmp     ecx, 1
0x14006dc27  jz      loc_14006DA25
0x14006dc2d  xor     r9d, r9d; MutableMessage
0x14006dc30  lea     rdx, aBaseFsRemotefs_1; "base\\fs\\remotefs\\rdr\\csc\\newdb\\en"...
0x14006dc37  mov     r8d, 47Dh; LineNumber
0x14006dc3d  lea     rcx, a0; "0"
0x14006dc44  call    cs:__imp_RtlAssert
0x14006dc4b  nop     dword ptr [rax+rax+00h]
0x14006dc50  jmp     loc_14006DA25
0x14006dc55  mov     edx, 22407343h; Tag
0x14006dc5a  mov     rcx, r13; P
0x14006dc5d  call    cs:__imp_ExFreePoolWithTag
0x14006dc64  nop     dword ptr [rax+rax+00h]
0x14006dc69  xor     r13d, r13d
0x14006dc6c  jmp     loc_14006DD54
0x14006dc71  mov     edx, 22407343h; Tag
0x14006dc76  mov     rcx, r13; P
0x14006dc79  call    cs:__imp_ExFreePoolWithTag
0x14006dc80  nop     dword ptr [rax+rax+00h]
0x14006dc85  xor     r13d, r13d
0x14006dc88  mov     [rbx+78h], r13
0x14006dc8c  jmp     loc_14006DB58
0x14006dc91  mov     edi, 3
0x14006dc96  jmp     loc_14006DA25
0x14006dc9b  mov     edi, 2
0x14006dca0  jmp     loc_14006DA25
0x14006dca5  mov     ecx, 3
0x14006dcaa  int     29h; Win8: RtlFailFast(ecx)
0x14006dcac  movups  xmm0, xmmword ptr [rax]
0x14006dcaf  movups  xmmword ptr [rbx+0C0h], xmm0
0x14006dcb6  movups  xmm1, xmmword ptr [rax+10h]
0x14006dcba  movups  xmmword ptr [rbx+0D0h], xmm1
0x14006dcc1  movups  xmm0, xmmword ptr [rax+20h]
0x14006dcc5  movups  xmmword ptr [rbx+0E0h], xmm0
0x14006dccc  movups  xmm1, xmmword ptr [rax+30h]
0x14006dcd0  movups  xmmword ptr [rbx+0F0h], xmm1
0x14006dcd7  movups  xmm0, xmmword ptr [rax+40h]
0x14006dcdb  mov     rax, [r14+28h]
0x14006dcdf  movups  xmmword ptr [rbx+100h], xmm0
0x14006dce6  movups  xmm0, xmmword ptr [rax]
0x14006dce9  movups  xmmword ptr [rbx+120h], xmm0
0x14006dcf0  movups  xmm1, xmmword ptr [rax+10h]
0x14006dcf4  movups  xmmword ptr [rbx+130h], xmm1
0x14006dcfb  movups  xmm0, xmmword ptr [rax+20h]
0x14006dcff  movups  xmmword ptr [rbx+140h], xmm0
0x14006dd06  movsd   xmm1, qword ptr [rax+30h]
0x14006dd0b  movsd   qword ptr [rbx+150h], xmm1
0x14006dd13  mov     edx, [rbx+150h]
0x14006dd19  test    dl, 10h
0x14006dd1c  jz      short loc_14006DD26
0x14006dd1e  xor     r13d, r13d
0x14006dd21  mov     eax, r13d
0x14006dd24  jmp     short loc_14006DD2E
0x14006dd26  call    CscDiffTransferGetInitialDiffTransferType
0x14006dd2b  xor     r13d, r13d
0x14006dd2e  mov     [rbx+184h], ax
0x14006dd35  jmp     loc_14006DB04
0x14006dd3a  or      dword ptr [rbx+14h], 2
0x14006dd3e  jmp     loc_14006DB12
0x14006dd43  mov     [rbx+78h], r13
0x14006dd47  xor     r13d, r13d
0x14006dd4a  jmp     loc_14006DC0E
0x14006dd4f  mov     edi, 0C000009Ah
0x14006dd54  mov     [rbx+70h], r13
0x14006dd58  jmp     loc_14006DB55
0x14006dd5d  test    rbx, rbx
0x14006dd60  jz      loc_14006DB72
0x14006dd66  mov     rcx, rbx; P
0x14006dd69  mov     [r12], r13d
0x14006dd6d  mov     [rbp+0], r13
  ... truncated ...
```
