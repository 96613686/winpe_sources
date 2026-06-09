# LuafvCopyFile

- ea: `0x1400230a8`
- end: `0x140023d0e`
- name: `LuafvCopyFile`
- size: `3174`
- prototype: `__int64 __fastcall(PFLT_INSTANCE Instance, struct _FLT_CALLBACK_DATA *, __m128i *, __m128i *, void *, char)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140017648`
- `0x140022de8`

## callees

- `0x140002388`
- `0x140002408`
- `0x140005f30`
- `0x140014474`
- `0x140014cd0`
- `0x14001b6a0`
- `0x14001dd90`
- `0x1400230a8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140023aa0`
- `ntoskrnl!ObfDereferenceObject` at `0x140023ad8`
- `ntoskrnl!ObfDereferenceObject` at `0x140023bf8`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c11`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c2a`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c43`
- `ntoskrnl!ObfDereferenceObject` at `0x14002634d`
- `ntoskrnl!ObfDereferenceObject` at `0x140026366`
- `ntoskrnl!ObfDereferenceObject` at `0x14002637f`
- `ntoskrnl!ObfDereferenceObject` at `0x140026398`
- `ntoskrnl!ObfDereferenceObject` at `0x140023aa0`
- `ntoskrnl!ObfDereferenceObject` at `0x140023ad8`
- `ntoskrnl!ObfDereferenceObject` at `0x140023bf8`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c11`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c2a`
- `ntoskrnl!ObfDereferenceObject` at `0x140023c43`
- `ntoskrnl!ObfDereferenceObject` at `0x14002634d`
- `ntoskrnl!ObfDereferenceObject` at `0x140026366`
- `ntoskrnl!ObfDereferenceObject` at `0x14002637f`
- `ntoskrnl!ObfDereferenceObject` at `0x140026398`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023cdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002643b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023cdc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002643b`
- `FLTMGR!FltSetInformationFile` at `0x140023b87`
- `FLTMGR!FltSetInformationFile` at `0x140023bdf`
- `FLTMGR!FltSetInformationFile` at `0x140026334`
- `FLTMGR!FltSetInformationFile` at `0x140023b87`
- `FLTMGR!FltSetInformationFile` at `0x140023bdf`
- `FLTMGR!FltSetInformationFile` at `0x140026334`
- `FLTMGR!FltClose` at `0x140023abc`
- `FLTMGR!FltClose` at `0x140023af4`
- `FLTMGR!FltClose` at `0x140023c5c`
- `FLTMGR!FltClose` at `0x140023c75`
- `FLTMGR!FltClose` at `0x140023c9b`
- `FLTMGR!FltClose` at `0x140023cb4`
- `FLTMGR!FltClose` at `0x1400263b1`
- `FLTMGR!FltClose` at `0x1400263ca`
- `FLTMGR!FltClose` at `0x1400263f5`
- `FLTMGR!FltClose` at `0x14002640e`
- `FLTMGR!FltClose` at `0x140023abc`
- `FLTMGR!FltClose` at `0x140023af4`
- `FLTMGR!FltClose` at `0x140023c5c`
- `FLTMGR!FltClose` at `0x140023c75`
- `FLTMGR!FltClose` at `0x140023c9b`
- `FLTMGR!FltClose` at `0x140023cb4`
- `FLTMGR!FltClose` at `0x1400263b1`
- `FLTMGR!FltClose` at `0x1400263ca`
- `FLTMGR!FltClose` at `0x1400263f5`
- `FLTMGR!FltClose` at `0x14002640e`
- `FLTMGR!FltQueryEaFile` at `0x1400234f6`
- `FLTMGR!FltQueryEaFile` at `0x1400234f6`
- `FLTMGR!FltQueryInformationFile` at `0x140023413`
- `FLTMGR!FltQueryInformationFile` at `0x14002346b`
- `FLTMGR!FltQueryInformationFile` at `0x1400237c7`
- `FLTMGR!FltQueryInformationFile` at `0x140023413`
- `FLTMGR!FltQueryInformationFile` at `0x14002346b`
- `FLTMGR!FltQueryInformationFile` at `0x1400237c7`
- `FLTMGR!FltCreateFileEx2` at `0x1400233cc`
- `FLTMGR!FltCreateFileEx2` at `0x140023666`
- `FLTMGR!FltCreateFileEx2` at `0x140023928`
- `FLTMGR!FltCreateFileEx2` at `0x140023a06`
- `FLTMGR!FltCreateFileEx2` at `0x1400233cc`
- `FLTMGR!FltCreateFileEx2` at `0x140023666`
- `FLTMGR!FltCreateFileEx2` at `0x140023928`
- `FLTMGR!FltCreateFileEx2` at `0x140023a06`

## pseudocode

```c
__int64 __fastcall LuafvCopyFile(
        PFLT_INSTANCE Instance,
        struct _FLT_CALLBACK_DATA *a2,
        __m128i *a3,
        __m128i *a4,
        void *a5,
        char a6)
{
  void *v7; // r10
  unsigned int *Pool; // rsi
  void *EaBuffer; // r15
  char v10; // dl
  unsigned __int64 v11; // xmm0_8
  unsigned __int16 v12; // r13
  _WORD *v13; // rcx
  unsigned __int64 v14; // xmm0_8
  _WORD *v15; // rcx
  NTSTATUS v16; // ebx
  __int64 v17; // r8
  ULONG EaLength; // ebx
  NTSTATUS EaFile; // edi
  ULONG FileAttributes; // edx
  ACCESS_MASK DesiredAccess; // eax
  __int64 v22; // r8
  ULONG v23; // ebx
  NTSTATUS InformationFile; // edi
  unsigned int *v25; // rdi
  __int64 v26; // rax
  NTSTATUS v28; // [rsp+80h] [rbp-1C8h]
  char v29; // [rsp+84h] [rbp-1C4h] BYREF
  char v30; // [rsp+85h] [rbp-1C3h]
  ULONG v31; // [rsp+88h] [rbp-1C0h] BYREF
  PFILE_OBJECT FileObject; // [rsp+90h] [rbp-1B8h] BYREF
  ULONG CreateOptions; // [rsp+98h] [rbp-1B0h]
  PVOID P; // [rsp+A0h] [rbp-1A8h] BYREF
  PFILE_OBJECT v35; // [rsp+A8h] [rbp-1A0h] BYREF
  PFILE_OBJECT v36; // [rsp+B0h] [rbp-198h] BYREF
  PFILE_OBJECT v37; // [rsp+B8h] [rbp-190h] BYREF
  HANDLE v38; // [rsp+C0h] [rbp-188h] BYREF
  ULONG Length; // [rsp+C8h] [rbp-180h] BYREF
  ULONG v40; // [rsp+CCh] [rbp-17Ch]
  HANDLE v41; // [rsp+D0h] [rbp-178h] BYREF
  HANDLE v42; // [rsp+D8h] [rbp-170h] BYREF
  unsigned int *v43; // [rsp+E0h] [rbp-168h]
  void *FileHandle; // [rsp+E8h] [rbp-160h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-158h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+120h] [rbp-128h] BYREF
  int v47; // [rsp+130h] [rbp-118h]
  int v48; // [rsp+134h] [rbp-114h]
  void *v49; // [rsp+138h] [rbp-110h]
  __m128i Data; // [rsp+140h] [rbp-108h] BYREF
  _WORD *v51; // [rsp+150h] [rbp-F8h]
  _WORD *v52; // [rsp+158h] [rbp-F0h]
  unsigned int *i; // [rsp+160h] [rbp-E8h]
  __int128 v54; // [rsp+168h] [rbp-E0h] BYREF
  __m128i v55; // [rsp+178h] [rbp-D0h] BYREF
  __m128i *v56; // [rsp+188h] [rbp-C0h]
  PFLT_CALLBACK_DATA CallbackData; // [rsp+190h] [rbp-B8h]
  PFLT_INSTANCE v58; // [rsp+198h] [rbp-B0h]
  __int128 FileInformation; // [rsp+1A0h] [rbp-A8h] BYREF
  __int128 v60; // [rsp+1B0h] [rbp-98h]
  __int128 v61; // [rsp+1C0h] [rbp-88h]
  __int64 v62; // [rsp+1D0h] [rbp-78h]
  FILE_INFORMATION_CLASS FileInformationClass[4]; // [rsp+1D8h] [rbp-70h] BYREF
  __int128 v64; // [rsp+1E8h] [rbp-60h]
  __int64 v65; // [rsp+1F8h] [rbp-50h]

  v56 = a3;
  CallbackData = a2;
  v58 = Instance;
  v7 = a5;
  Data = 0;
  v55 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v54 = 0;
  Length = 0;
  FileInformation = 0;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  *(_OWORD *)FileInformationClass = 0;
  v64 = 0;
  v65 = 0;
  FileHandle = 0;
  v41 = 0;
  v38 = 0;
  v42 = 0;
  Pool = 0;
  v43 = 0;
  EaBuffer = 0;
  v49 = 0;
  P = 0;
  v31 = 0;
  FileObject = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  Data = *a3;
  v10 = 0;
  v30 = 0;
  v11 = _mm_srli_si128(Data, 8).m128i_u64[0];
  v12 = _mm_cvtsi128_si32(Data);
  v13 = (_WORD *)(v11 + v12);
  v51 = v13;
  while ( (unsigned __int64)v13 > v11 )
  {
    v51 = --v13;
    if ( *v13 == 58 )
    {
      v12 = 2 * ((__int64)((__int64)v13 - v11) >> 1);
      Data.m128i_i16[0] = v12;
      v10 = 1;
      v30 = 1;
    }
    else if ( *v13 == 92 )
    {
      break;
    }
  }
  v55 = *a4;
  v14 = _mm_srli_si128(v55, 8).m128i_u64[0];
  v15 = (_WORD *)(v14 + (unsigned __int16)_mm_cvtsi128_si32(v55));
  v52 = v15;
  while ( (unsigned __int64)v15 > v14 )
  {
    v52 = --v15;
    if ( *v15 == 58 )
    {
      v55.m128i_i16[0] = 2 * ((__int64)((__int64)v15 - v14) >> 1);
    }
    else if ( *v15 == 92 )
    {
      break;
    }
  }
  if ( a5 )
  {
    if ( v10 )
      v7 = 0;
    else
      Data.m128i_i16[0] = 0;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v7;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&Data;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  CreateOptions = a6 != 0 ? 37 : 100;
  v16 = FltCreateFileEx2(
          LuafvDriverData,
          Instance,
          &FileHandle,
          &FileObject,
          0x100081u,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0x80u,
          7u,
          1u,
          CreateOptions,
          0,
          0,
          0x901u,
          0);
  if ( v16 >= 0 )
  {
    v16 = FltQueryInformationFile(Instance, FileObject, &FileInformation, 0x38u, FileNetworkOpenInformation, 0);
    if ( v16 >= 0 )
    {
      if ( a6 )
        v61 = 0;
      v28 = FltQueryInformationFile(Instance, FileObject, &Length, 4u, FileEaInformation, 0);
      EaLength = Length;
      v40 = Length;
      if ( v28 >= 0 && Length )
      {
        while ( 1 )
        {
          LOBYTE(v17) = 1;
          EaBuffer = (void *)LuafvAllocatePool(1, EaLength, v17);
          v49 = EaBuffer;
          if ( !EaBuffer )
            break;
          EaFile = FltQueryEaFile(
                     Instance,
                     FileObject,
                     EaBuffer,
                     EaLength,
                     0,
                     0,
                     0,
                     0,
                     1u,
                     (PULONG)&IoStatusBlock.Information);
          if ( EaFile < 0 )
          {
            EaLength *= 2;
            v40 = EaLength;
            LuafvFreePool(EaBuffer);
            EaBuffer = 0;
            v49 = 0;
          }
          if ( EaFile != -2147483643 && EaFile != -1073741789 )
          {
            EaLength = IoStatusBlock.Information;
            if ( EaFile < 0 )
              EaLength = 0;
            v40 = EaLength;
            goto LABEL_31;
          }
        }
LABEL_62:
        v16 = -1073741670;
        goto LABEL_63;
      }
LABEL_31:
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)&v55;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      FileAttributes = v62 & 0xFFFFEFFF;
      LODWORD(v62) = v62 & 0xFFFFEFFF;
      CreateOptions = a6 != 0 ? 16421 : 16484;
      DesiredAccess = 1048850;
      v47 = 1048850;
      if ( !a6 )
        DesiredAccess = 1114386;
      v47 = DesiredAccess;
      v16 = FltCreateFileEx2(
              LuafvDriverData,
              Instance,
              &v38,
              &v35,
              DesiredAccess,
              &ObjectAttributes,
              &IoStatusBlock,
              0,
              FileAttributes,
              7u,
              2u,
              a6 != 0 ? 16421 : 16484,
              EaBuffer,
              EaLength,
              0x101u,
              0);
      if ( v16 < 0 )
        goto LABEL_63;
      LuafvCopyShortName(Instance);
      Data.m128i_i16[0] = v12;
      v16 = LuafvCopySaclWithAudit(Instance, CallbackData, FileObject, &Data, &v55);
      if ( v16 < 0 )
        goto LABEL_63;
      if ( !a6 )
      {
        if ( *((_QWORD *)&v61 + 1) )
        {
          v16 = AllocateDataBuffer(&P, &v31);
          if ( v16 < 0 )
            goto LABEL_63;
          v16 = LuafvCopyStreamData(Instance, FileObject, v35, P, v31);
          if ( v16 < 0 )
            goto LABEL_63;
        }
      }
      v23 = 4096;
      v48 = 4096;
      while ( 1 )
      {
        LOBYTE(v22) = 1;
        Pool = (unsigned int *)LuafvAllocatePool(1, v23, v22);
        v43 = Pool;
        if ( !Pool )
          goto LABEL_62;
        InformationFile = FltQueryInformationFile(
                            Instance,
                            FileObject,
                            Pool,
                            v23,
                            FileStreamInformation,
                            (PULONG)&IoStatusBlock.Information);
        if ( InformationFile >= 0 )
        {
          if ( IoStatusBlock.Information )
            goto LABEL_45;
        }
        else
        {
          v23 *= 2;
          v48 = v23;
        }
        LuafvFreePool(Pool);
        v43 = 0;
        Pool = 0;
LABEL_45:
        if ( InformationFile != -2147483643 && InformationFile != -1073741789 )
        {
          if ( Pool )
          {
            v25 = Pool;
            for ( i = Pool; ; i = v25 )
            {
              if ( v25[1] > 2 && *((_WORD *)v25 + 13) != 58 )
              {
                *((_QWORD *)&v54 + 1) = v25 + 6;
                LOWORD(v54) = *((_WORD *)v25 + 2);
                WORD1(v54) = v54;
                ObjectAttributes.Length = 48;
                ObjectAttributes.RootDirectory = v38;
                ObjectAttributes.Attributes = 512;
                ObjectAttributes.ObjectName = (PUNICODE_STRING)&v54;
                *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                v16 = FltCreateFileEx2(
                        LuafvDriverData,
                        Instance,
                        &v42,
                        &v37,
                        0x100102u,
                        &ObjectAttributes,
                        &IoStatusBlock,
                        0,
                        0,
                        7u,
                        2u,
                        0x64u,
                        0,
                        0,
                        0x101u,
                        0);
                if ( v16 < 0 )
                  goto LABEL_63;
                if ( *((_QWORD *)v25 + 1) )
                {
                  ObjectAttributes.Length = 48;
                  ObjectAttributes.RootDirectory = FileHandle;
                  ObjectAttributes.Attributes = 512;
                  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v54;
                  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
                  v16 = FltCreateFileEx2(
                          LuafvDriverData,
                          Instance,
                          &v41,
                          &v36,
                          0x100081u,
                          &ObjectAttributes,
                          &IoStatusBlock,
                          0,
                          0,
                          7u,
                          1u,
                          0x64u,
                          0,
                          0,
                          0x901u,
                          0);
                  if ( v16 < 0 )
                    goto LABEL_63;
                  if ( !P )
                  {
                    v16 = AllocateDataBuffer(&P, &v31);
                    if ( v16 < 0 )
                      goto LABEL_63;
                  }
                  v16 = LuafvCopyStreamData(Instance, v36, v37, P, v31);
                  if ( v16 < 0 )
                    goto LABEL_63;
                  ObfDereferenceObject(v36);
                  v36 = 0;
                  FltClose(v41);
                  v41 = 0;
                }
                ObfDereferenceObject(v37);
                v37 = 0;
                FltClose(v42);
                v42 = 0;
              }
              v26 = *v25;
              if ( !(_DWORD)v26 )
                break;
              v25 = (unsigned int *)((char *)v25 + v26);
            }
          }
          *(_OWORD *)FileInformationClass = FileInformation;
          v64 = v60;
          LODWORD(v65) = 0;
          v16 = FltSetInformationFile(Instance, v35, FileInformationClass, 0x28u, FileBasicInformation);
          break;
        }
      }
    }
  }
LABEL_63:
  if ( v16 < 0 && v35 )
  {
    v29 = 1;
    FltSetInformationFile(Instance, v35, &v29, 1u, FileDispositionInformation);
  }
  if ( v36 )
    ObfDereferenceObject(v36);
  if ( v37 )
    ObfDereferenceObject(v37);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( v35 )
    ObfDereferenceObject(v35);
  if ( v41 )
    FltClose(v41);
  if ( v42 )
    FltClose(v42);
  if ( Pool )
    LuafvFreePool(Pool);
  if ( v38 )
    FltClose(v38);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( EaBuffer )
    LuafvFreePool(EaBuffer);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400230a8  push    rbx
0x1400230aa  push    rsi
0x1400230ab  push    rdi
0x1400230ac  push    r12
0x1400230ae  push    r13
0x1400230b0  push    r14
0x1400230b2  push    r15
0x1400230b4  sub     rsp, 210h
0x1400230bb  mov     rax, cs:__security_cookie
0x1400230c2  xor     rax, rsp
0x1400230c5  mov     [rsp+248h+var_48], rax
0x1400230cd  mov     rdi, r8
0x1400230d0  mov     [rsp+248h+var_C0], r8
0x1400230d8  mov     [rsp+248h+CallbackData], rdx
0x1400230e0  mov     r14, rcx
0x1400230e3  mov     [rsp+248h+var_B0], rcx
0x1400230eb  mov     r10, [rsp+248h+arg_20]
0x1400230f3  xorps   xmm0, xmm0
0x1400230f6  movups  [rsp+248h+Data], xmm0
0x1400230fe  xorps   xmm1, xmm1
0x140023101  movups  [rsp+248h+var_D0], xmm1
0x140023109  xor     eax, eax
0x14002310b  movups  xmmword ptr [rsp+248h+var_158.Length], xmm0
0x140023113  movups  xmmword ptr [rsp+248h+var_158.ObjectName], xmm0
0x14002311b  movups  xmmword ptr [rsp+248h+var_158+1Ch], xmm0
0x140023123  movups  xmmword ptr [rsp+248h+var_128], xmm0
0x14002312b  movups  [rsp+248h+var_E0], xmm1
0x140023133  xor     r11d, r11d
0x140023136  mov     [rsp+248h+Length], r11d
0x14002313e  movups  [rsp+248h+FileInformation], xmm0
0x140023146  movups  [rsp+248h+var_98], xmm0
0x14002314e  movups  [rsp+248h+var_88], xmm0
0x140023156  mov     [rsp+248h+var_78], rax
0x14002315e  movups  xmmword ptr [rsp+248h+FileInformationClass], xmm0
0x140023166  movups  [rsp+248h+var_60], xmm0
0x14002316e  mov     [rsp+248h+var_50], rax
0x140023176  mov     [rsp+248h+var_1C8], r11d
0x14002317e  mov     [rsp+248h+FileHandle], r11
0x140023186  mov     [rsp+248h+var_178], r11
0x14002318e  mov     [rsp+248h+var_188], r11
0x140023196  mov     [rsp+248h+var_170], r11
0x14002319e  mov     esi, r11d
0x1400231a1  mov     [rsp+248h+var_168], r11
0x1400231a9  mov     r15d, r11d
0x1400231ac  mov     [rsp+248h+var_110], r11
0x1400231b4  mov     [rsp+248h+P], r11
0x1400231bc  mov     [rsp+248h+var_1C0], r11d
0x1400231c4  mov     [rsp+248h+FileObject], r11
0x1400231cc  mov     [rsp+248h+var_1A0], r11
0x1400231d4  mov     [rsp+248h+var_198], r11
0x1400231dc  mov     [rsp+248h+var_190], r11
0x1400231e4  movups  xmm1, xmmword ptr [r8]
0x1400231e8  movups  [rsp+248h+Data], xmm1
0x1400231f0  mov     [rsp+248h+var_1C3], r11b
0x1400231f8  mov     [rsp+248h+var_F8], r11
0x140023200  mov     dl, r11b
0x140023203  mov     [rsp+248h+var_1C3], dl
0x14002320a  movdqa  xmm0, xmm1
0x14002320e  psrldq  xmm0, 8
0x140023213  movq    r8, xmm0
0x140023218  movd    r13d, xmm1
0x14002321d  movzx   ecx, r13w
0x140023221  add     rcx, r8
0x140023224  mov     [rsp+248h+var_F8], rcx
0x14002322c  cmp     rcx, r8
0x14002322f  jbe     short loc_140023250
0x140023231  sub     rcx, 2
0x140023235  mov     [rsp+248h+var_F8], rcx
0x14002323d  movzx   eax, word ptr [rcx]
0x140023240  cmp     ax, 3Ah ; ':'
0x140023244  jz      short loc_1400232B8
0x140023246  cmp     ax, 5Ch ; '\'
0x14002324a  jnz     loc_1400232D9
0x140023250  movups  xmm1, xmmword ptr [r9]
0x140023254  movups  [rsp+248h+var_D0], xmm1
0x14002325c  mov     [rsp+248h+var_F0], r11
0x140023264  movdqa  xmm0, xmm1
0x140023268  psrldq  xmm0, 8
0x14002326d  movq    r8, xmm0
0x140023272  movd    eax, xmm1
0x140023276  movzx   ecx, ax
0x140023279  add     rcx, r8
0x14002327c  mov     [rsp+248h+var_F0], rcx
0x140023284  cmp     rcx, r8
0x140023287  jbe     short loc_1400232A4
0x140023289  sub     rcx, 2
0x14002328d  mov     [rsp+248h+var_F0], rcx
0x140023295  movzx   eax, word ptr [rcx]
0x140023298  cmp     ax, 3Ah ; ':'
0x14002329c  jz      short loc_1400232DE
0x14002329e  cmp     ax, 5Ch ; '\'
0x1400232a2  jnz     short loc_1400232F2
0x1400232a4  test    r10, r10
0x1400232a7  jz      short loc_1400232F7
0x1400232a9  test    dl, dl
0x1400232ab  jnz     short loc_1400232F4
0x1400232ad  mov     word ptr [rsp+248h+Data], r11w
0x1400232b6  jmp     short loc_1400232F7
0x1400232b8  mov     rax, rcx
0x1400232bb  sub     rax, r8
0x1400232be  sar     rax, 1
0x1400232c1  add     ax, ax
0x1400232c4  movzx   r13d, ax
0x1400232c8  mov     word ptr [rsp+248h+Data], ax
0x1400232d0  mov     dl, 1
0x1400232d2  mov     [rsp+248h+var_1C3], dl
0x1400232d9  jmp     loc_14002322C
0x1400232de  mov     rax, rcx
0x1400232e1  sub     rax, r8
0x1400232e4  sar     rax, 1
0x1400232e7  add     ax, ax
0x1400232ea  mov     word ptr [rsp+248h+var_D0], ax
0x1400232f2  jmp     short loc_140023284
0x1400232f4  mov     r10, r11
0x1400232f7  mov     [rsp+248h+var_158.Length], 30h ; '0'
0x140023302  mov     [rsp+248h+var_158.RootDirectory], r10
0x14002330a  mov     [rsp+248h+var_158.Attributes], 240h
0x140023315  lea     rax, [rsp+248h+Data]
0x14002331d  mov     [rsp+248h+var_158.ObjectName], rax
0x140023325  xorps   xmm0, xmm0
0x140023328  movdqu  xmmword ptr [rsp+248h+var_158.SecurityDescriptor], xmm0
0x140023331  mov     [rsp+248h+var_1B0], 24h ; '$'
0x14002333c  mov     r12b, [rsp+248h+arg_28]
0x140023344  mov     al, r12b
0x140023347  neg     al
0x140023349  sbb     ecx, ecx
0x14002334b  and     ecx, 0FFFFFFC1h
0x14002334e  add     ecx, 64h ; 'd'
0x140023351  mov     [rsp+248h+var_1B0], ecx
0x140023358  mov     [rsp+248h+DriverContext], r11; DriverContext
0x14002335d  mov     [rsp+248h+Flags], 901h; Flags
0x140023365  mov     [rsp+248h+EaLength], r11d; EaLength
0x14002336a  mov     [rsp+248h+EaBuffer], r11; EaBuffer
0x14002336f  mov     [rsp+248h+CreateOptions], ecx; CreateOptions
0x140023373  mov     [rsp+248h+CreateDisposition], 1; CreateDisposition
0x14002337b  mov     [rsp+248h+ShareAccess], 7; ShareAccess
0x140023383  mov     [rsp+248h+FileAttributes], 80h; FileAttributes
0x14002338b  mov     [rsp+248h+AllocationSize], r11; AllocationSize
0x140023390  lea     rax, [rsp+248h+var_128]
0x140023398  mov     [rsp+248h+IoStatusBlock], rax; IoStatusBlock
0x14002339d  lea     rax, [rsp+248h+var_158]
0x1400233a5  mov     [rsp+248h+ObjectAttributes], rax; ObjectAttributes
0x1400233aa  mov     [rsp+248h+DesiredAccess], 100081h; DesiredAccess
0x1400233b2  lea     r9, [rsp+248h+FileObject]; FileObject
0x1400233ba  lea     r8, [rsp+248h+FileHandle]; FileHandle
0x1400233c2  mov     rdx, r14; Instance
0x1400233c5  mov     rcx, cs:LuafvDriverData; Filter
0x1400233cc  call    cs:__imp_FltCreateFileEx2
0x1400233d3  nop     dword ptr [rax+rax+00h]
0x1400233d8  mov     ebx, eax
0x1400233da  mov     [rsp+248h+var_1C8], eax
0x1400233e1  test    eax, eax
0x1400233e3  js      loc_140023BAA
0x1400233e9  mov     [rsp+248h+ObjectAttributes], 0; LengthReturned
0x1400233f2  mov     [rsp+248h+DesiredAccess], 22h ; '"'; FileInformationClass
0x1400233fa  mov     r9d, 38h ; '8'; Length
0x140023400  lea     r8, [rsp+248h+FileInformation]; FileInformation
0x140023408  mov     rdx, [rsp+248h+FileObject]; FileObject
0x140023410  mov     rcx, r14; Instance
0x140023413  call    cs:__imp_FltQueryInformationFile
0x14002341a  nop     dword ptr [rax+rax+00h]
0x14002341f  mov     ebx, eax
0x140023421  mov     [rsp+248h+var_1C8], eax
0x140023428  test    eax, eax
0x14002342a  js      loc_140023BAA
0x140023430  test    r12b, r12b
0x140023433  jz      short loc_140023441
0x140023435  xorps   xmm0, xmm0
0x140023438  movdqu  [rsp+248h+var_88], xmm0
0x140023441  mov     [rsp+248h+ObjectAttributes], 0; LengthReturned
0x14002344a  mov     [rsp+248h+DesiredAccess], 7; FileInformationClass
0x140023452  mov     r9d, 4; Length
0x140023458  lea     r8, [rsp+248h+Length]; FileInformation
0x140023460  mov     rdx, [rsp+248h+FileObject]; FileObject
0x140023468  mov     rcx, r14; Instance
0x14002346b  call    cs:__imp_FltQueryInformationFile
0x140023472  nop     dword ptr [rax+rax+00h]
0x140023477  mov     [rsp+248h+var_1C8], eax
0x14002347e  mov     ebx, [rsp+248h+Length]
0x140023485  mov     [rsp+248h+var_17C], ebx
0x14002348c  test    eax, eax
0x14002348e  js      loc_140023561
0x140023494  test    ebx, ebx
0x140023496  jz      loc_140023561
0x14002349c  mov     r8b, 1
0x14002349f  mov     edx, ebx
0x1400234a1  mov     ecx, 1
0x1400234a6  call    LuafvAllocatePool
0x1400234ab  mov     r15, rax
0x1400234ae  mov     [rsp+248h+var_110], rax
0x1400234b6  xor     ecx, ecx
0x1400234b8  test    rax, rax
0x1400234bb  jz      loc_140023B9E
0x1400234c1  lea     rax, [rsp+248h+var_128.Information]
0x1400234c9  mov     qword ptr [rsp+248h+ShareAccess], rax; LengthReturned
0x1400234ce  mov     byte ptr [rsp+248h+FileAttributes], 1; RestartScan
0x1400234d3  mov     [rsp+248h+AllocationSize], rcx; EaIndex
0x1400234d8  mov     dword ptr [rsp+248h+IoStatusBlock], ecx; EaListLength
0x1400234dc  mov     [rsp+248h+ObjectAttributes], rcx; EaList
0x1400234e1  mov     byte ptr [rsp+248h+DesiredAccess], cl; ReturnSingleEntry
0x1400234e5  mov     r9d, ebx; Length
0x1400234e8  mov     r8, r15; ReturnedEaData
0x1400234eb  mov     rdx, [rsp+248h+FileObject]; FileObject
0x1400234f3  mov     rcx, r14; Instance
0x1400234f6  call    cs:__imp_FltQueryEaFile
0x1400234fd  nop     dword ptr [rax+rax+00h]
0x140023502  mov     edi, eax
0x140023504  mov     [rsp+248h+var_1C8], eax
0x14002350b  test    eax, eax
0x14002350d  jns     short loc_14002352B
0x14002350f  add     ebx, ebx
0x140023511  mov     [rsp+248h+var_17C], ebx
0x140023518  mov     rcx, r15
0x14002351b  call    LuafvFreePool
0x140023520  xor     r15d, r15d
0x140023523  mov     [rsp+248h+var_110], r15
0x14002352b  cmp     edi, 80000005h
0x140023531  jz      loc_14002349C
0x140023537  cmp     edi, 0C0000023h
0x14002353d  jz      loc_14002349C
0x140023543  mov     rbx, [rsp+248h+var_128.Information]
0x14002354b  xor     eax, eax
0x14002354d  test    edi, edi
0x14002354f  cmovs   ebx, eax
0x140023552  mov     [rsp+248h+var_17C], ebx
0x140023559  mov     rdi, [rsp+248h+var_C0]
0x140023561  mov     [rsp+248h+var_158.Length], 30h ; '0'
0x14002356c  mov     [rsp+248h+var_158.RootDirectory], 0
0x140023578  mov     [rsp+248h+var_158.Attributes], 240h
0x140023583  lea     rax, [rsp+248h+var_D0]
0x14002358b  mov     [rsp+248h+var_158.ObjectName], rax
0x140023593  xorps   xmm0, xmm0
0x140023596  movdqu  xmmword ptr [rsp+248h+var_158.SecurityDescriptor], xmm0
0x14002359f  mov     edx, dword ptr [rsp+248h+var_78]
0x1400235a6  btr     edx, 0Ch
0x1400235aa  mov     dword ptr [rsp+248h+var_78], edx
0x1400235b1  mov     [rsp+248h+var_1B0], 4024h
0x1400235bc  mov     al, r12b
0x1400235bf  neg     al
0x1400235c1  sbb     ecx, ecx
0x1400235c3  and     ecx, 0FFFFFFC1h
0x1400235c6  add     ecx, 4064h
0x1400235cc  mov     [rsp+248h+var_1B0], ecx
0x1400235d3  mov     eax, 100112h
0x1400235d8  mov     [rsp+248h+var_118], eax
0x1400235df  mov     r8d, 110112h
0x1400235e5  test    r12b, r12b
0x1400235e8  cmovz   eax, r8d
0x1400235ec  mov     [rsp+248h+var_118], eax
0x1400235f3  mov     [rsp+248h+DriverContext], 0; DriverContext
0x1400235fc  mov     [rsp+248h+Flags], 101h; Flags
0x140023604  mov     [rsp+248h+EaLength], ebx; EaLength
0x140023608  mov     [rsp+248h+EaBuffer], r15; EaBuffer
0x14002360d  mov     [rsp+248h+CreateOptions], ecx; CreateOptions
0x140023611  mov     [rsp+248h+CreateDisposition], 2; CreateDisposition
0x140023619  mov     [rsp+248h+ShareAccess], 7; ShareAccess
0x140023621  mov     [rsp+248h+FileAttributes], edx; FileAttributes
0x140023625  mov     [rsp+248h+AllocationSize], 0; AllocationSize
0x14002362e  lea     rcx, [rsp+248h+var_128]
0x140023636  mov     [rsp+248h+IoStatusBlock], rcx; IoStatusBlock
0x14002363b  lea     rcx, [rsp+248h+var_158]
0x140023643  mov     [rsp+248h+ObjectAttributes], rcx; ObjectAttributes
0x140023648  mov     [rsp+248h+DesiredAccess], eax; DesiredAccess
0x14002364c  lea     r9, [rsp+248h+var_1A0]; FileObject
0x140023654  lea     r8, [rsp+248h+var_188]; FileHandle
0x14002365c  mov     rdx, r14; Instance
0x14002365f  mov     rcx, cs:LuafvDriverData; Filter
0x140023666  call    cs:__imp_FltCreateFileEx2
0x14002366d  nop     dword ptr [rax+rax+00h]
0x140023672  mov     ebx, eax
0x140023674  mov     [rsp+248h+var_1C8], eax
0x14002367b  test    eax, eax
0x14002367d  js      loc_140023BAA
0x140023683  mov     r8, [rsp+248h+var_188]
0x14002368b  mov     rdx, rdi
0x14002368e  mov     rcx, r14; Instance
0x140023691  call    LuafvCopyShortName
0x140023696  mov     [rsp+248h+var_1C8], eax
0x14002369d  mov     word ptr [rsp+248h+Data], r13w
0x1400236a6  lea     rax, [rsp+248h+var_D0]
0x1400236ae  mov     [rsp+248h+ObjectAttributes], rax; PVOID
0x1400236b3  lea     rax, [rsp+248h+Data]
0x1400236bb  mov     qword ptr [rsp+248h+DesiredAccess], rax; Data
0x1400236c0  mov     r9, [rsp+248h+var_188]
0x1400236c8  mov     r8, [rsp+248h+FileObject]; FileObject
0x1400236d0  mov     rdx, [rsp+248h+CallbackData]; CallbackData
0x1400236d8  mov     rcx, r14; Instance
0x1400236db  call    LuafvCopySaclWithAudit
0x1400236e0  mov     ebx, eax
0x1400236e2  mov     [rsp+248h+var_1C8], eax
0x1400236e9  xor     r13d, r13d
0x1400236ec  test    eax, eax
0x1400236ee  js      loc_140023BAA
0x1400236f4  test    r12b, r12b
0x1400236f7  jnz     short loc_140023772
0x1400236f9  cmp     qword ptr [rsp+248h+var_88+8], r13
0x140023701  jz      short loc_140023772
0x140023703  lea     rdx, [rsp+248h+var_1C0]
0x14002370b  lea     rcx, [rsp+248h+P]
0x140023713  call    AllocateDataBuffer
  ... truncated ...
```
