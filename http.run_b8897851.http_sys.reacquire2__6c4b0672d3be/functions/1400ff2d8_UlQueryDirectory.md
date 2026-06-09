# UlQueryDirectory

- ea: `0x1400ff2d8`
- end: `0x1400ff7c9`
- name: `UlQueryDirectory`
- size: `1265`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005aed0`
- `0x140100fa0`

## callees

- `0x14002a240`
- `0x1400afcc0`
- `0x1400ff2d8`
- `0x140167700`
- `0x1401c6e34`
- `0x1401ceeb4`
- `0x1401cf2b0`
- `0x1401cf328`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1400ff3f8`
- `ntoskrnl!ZwCreateFile` at `0x1400ff3f8`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff511`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff695`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff511`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1400ff695`
- `ntoskrnl!wcsstr` at `0x1400ff58b`
- `ntoskrnl!wcsstr` at `0x1400ff58b`
- `ntoskrnl!isdigit` at `0x1400ff5b1`
- `ntoskrnl!isdigit` at `0x1400ff5b1`
- `ntoskrnl!ZwClose` at `0x1400ff79a`
- `ntoskrnl!ZwClose` at `0x1400ff79a`
- `ntoskrnl!ExAllocatePool3` at `0x1400ff4b3`
- `ntoskrnl!ExAllocatePool3` at `0x1400ff4b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff756`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ff756`

## pseudocode

```c
__int64 __fastcall UlQueryDirectory(
        struct _UNICODE_STRING *a1,
        wchar_t *a2,
        __int64 a3,
        wchar_t *a4,
        __int64 a5,
        _QWORD *a6)
{
  __int64 *p_Buffer; // rsi
  wchar_t v10; // bx
  __int64 v11; // r15
  __int64 v12; // rax
  NTSTATUS v13; // eax
  int v14; // edi
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int *Pool3; // rdi
  NTSTATUS v18; // eax
  int v19; // r8d
  NTSTATUS v20; // ebx
  unsigned int v21; // r13d
  unsigned __int64 v22; // r14
  __int64 v23; // rbx
  _WORD *v24; // r12
  unsigned __int64 v25; // rcx
  __int16 v26; // ax
  wchar_t *v27; // rax
  unsigned __int64 *v28; // rcx
  bool v29; // r12
  __int64 v30; // rax
  NTSTATUS v31; // eax
  int v32; // edx
  int v33; // r8d
  _DWORD *v34; // rcx
  __int64 CreateDisposition; // [rsp+38h] [rbp-C8h]
  __int64 CreateDispositiona; // [rsp+38h] [rbp-C8h]
  __int16 v38; // [rsp+60h] [rbp-A0h]
  bool v39; // [rsp+64h] [rbp-9Ch]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  PVOID FileInformation; // [rsp+78h] [rbp-88h]
  size_t pcchRemaining; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *SubStr; // [rsp+98h] [rbp-68h]
  __int64 v46; // [rsp+A0h] [rbp-60h]
  NTSTRSAFE_PWSTR v47; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING *v48; // [rsp+B0h] [rbp-50h]
  __int64 v49; // [rsp+B8h] [rbp-48h]
  _QWORD *v50; // [rsp+C0h] [rbp-40h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t pszDest; // [rsp+110h] [rbp+10h] BYREF
  char v54; // [rsp+112h] [rbp+12h] BYREF

  v49 = a5;
  v50 = a6;
  SubStr = a4;
  v46 = a3;
  FileHandle = 0;
  v47 = a2;
  v48 = a1;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileName = 0;
  p_Buffer = (__int64 *)&a1->Buffer;
  if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
    WPP_SF_S(1291, 26, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, *p_Buffer);
  v10 = a2[1];
  v11 = -1;
  a2[1] = 0;
  v12 = -1;
  do
    ++v12;
  while ( *(_WORD *)(*p_Buffer + 2 * v12) );
  a1->Length = 2 * v12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x21u, 0, 0);
  a2[1] = v10;
  v14 = v13;
  v15 = -1;
  do
    ++v15;
  while ( *(_WORD *)(*p_Buffer + 2 * v15) );
  a1->Length = 2 * v15;
  if ( v14 < 0 )
    goto LABEL_42;
  FileName.Buffer = (PWSTR)&v54;
  LODWORD(CreateDisposition) = 60;
  RtlStringCchPrintfExW(&pszDest, 0x21u, 0, &pcchRemaining, 0, L"%s%c.%s", v46, CreateDisposition, a4 + 1);
  v16 = -1;
  do
    ++v16;
  while ( FileName.Buffer[v16] );
  FileName.Length = 2 * v16;
  FileName.MaximumLength = 2 * v16;
  Pool3 = (unsigned int *)ExAllocatePool3(66, 4098, 1196190805, UxLowPriorityPool, 1);
  FileInformation = Pool3;
  if ( !Pool3 )
  {
    v14 = -1073741670;
LABEL_42:
    if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
      WPP_SF_dS(779, 29, (unsigned int)WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids, v14, *p_Buffer);
    goto LABEL_44;
  }
  v18 = ZwQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          Pool3,
          0xFFEu,
          FileDirectoryInformation,
          0,
          &FileName,
          1u);
  v20 = v18;
  if ( v18 >= 0 )
  {
    v39 = 0;
    v21 = 1;
    v22 = 1;
    v41 = 1;
    v23 = 0;
    while ( 1 )
    {
      while ( 1 )
      {
        v24 = Pool3 + 16;
        v25 = (unsigned __int64)Pool3[15] >> 1;
        v26 = *((_WORD *)Pool3 + v25 + 32);
        *((_WORD *)Pool3 + v25 + 32) = 0;
        v38 = v26;
        v27 = wcsstr((const wchar_t *)Pool3 + 32, SubStr);
        pcchRemaining = (size_t)v27;
        if ( v27 )
        {
          *v27 = 0;
          while ( *v24 )
          {
            if ( isdigit(*(unsigned __int8 *)v24) )
            {
              v28 = &v41;
              LOBYTE(v28) = 1;
              if ( (int)HttpStringToULongLong(
                          (_DWORD)v28,
                          (_DWORD)v24,
                          (__int64)(pcchRemaining - (_QWORD)v24) >> 1,
                          0,
                          10,
                          0,
                          (__int64)&v41) < 0
                || (v22 = v41, v41 > 0xFFFFFF) )
              {
                v22 = 0;
                v41 = 0;
              }
              break;
            }
            ++v24;
          }
        }
        *((_WORD *)Pool3 + ((unsigned __int64)Pool3[15] >> 1) + 32) = v38;
        if ( v22 < v21 )
        {
          v29 = v39;
        }
        else
        {
          v21 = v22;
          v23 = *((_QWORD *)Pool3 + 5);
          v29 = (Pool3[14] & 0x10) != 0;
          v39 = v29;
        }
        v30 = *Pool3;
        if ( !(_DWORD)v30 )
          break;
        Pool3 = (unsigned int *)((char *)Pool3 + v30);
      }
      v31 = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              FileInformation,
              0x1000u,
              FileDirectoryInformation,
              0,
              0,
              0);
      v14 = v31;
      if ( v31 == -2147483642 )
        break;
      if ( v31 < 0 )
        goto LABEL_41;
      Pool3 = (unsigned int *)FileInformation;
    }
    v14 = 0;
    if ( v29 )
    {
      ++v21;
      v23 = 0;
    }
    LODWORD(CreateDispositiona) = v21;
    RtlStringCchPrintfExW(v47, 0x21u, 0, &pcchRemaining, 0, L"%s%d.%s", v46, CreateDispositiona, SubStr + 1);
    do
      ++v11;
    while ( *(_WORD *)(*p_Buffer + 2 * v11) );
    v34 = (_DWORD *)v49;
    v48->Length = 2 * v11;
    *v34 = v21 + 1;
    *v50 = v23;
    if ( (BYTE9(xmmword_1401A2CA0) & 8) != 0 )
      WPP_SF_SI((_DWORD)v34, v32, v33, *p_Buffer, v23);
  }
  else
  {
    if ( (BYTE9(xmmword_1401A2C90) & 8) != 0 )
      WPP_SF_dSS(*p_Buffer, 0, v19, v18, *p_Buffer, (__int64)FileName.Buffer);
    v14 = 0;
    if ( v20 != -1073741809 )
      v14 = v20;
  }
LABEL_41:
  ExFreePoolWithTag(FileInformation, 0);
  if ( v14 < 0 )
    goto LABEL_42;
LABEL_44:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400ff2d8  push    rbp
0x1400ff2da  push    rbx
0x1400ff2db  push    rsi
0x1400ff2dc  push    rdi
0x1400ff2dd  push    r12
0x1400ff2df  push    r13
0x1400ff2e1  push    r14
0x1400ff2e3  push    r15
0x1400ff2e5  lea     rbp, [rsp-78h]
0x1400ff2ea  sub     rsp, 178h
0x1400ff2f1  mov     rax, cs:__security_cookie
0x1400ff2f8  xor     rax, rsp
0x1400ff2fb  mov     [rbp+0B0h+var_50], rax
0x1400ff2ff  mov     rax, [rbp+0B0h+arg_20]
0x1400ff306  xorps   xmm0, xmm0
0x1400ff309  mov     [rbp+0B0h+var_F8], rax
0x1400ff30d  xorps   xmm1, xmm1
0x1400ff310  mov     rax, [rbp+0B0h+arg_28]
0x1400ff317  mov     r13, r9
0x1400ff31a  mov     [rbp+0B0h+var_F0], rax
0x1400ff31e  mov     r14, rdx
0x1400ff321  xor     eax, eax
0x1400ff323  mov     [rbp+0B0h+SubStr], r9
0x1400ff327  xor     edi, edi
0x1400ff329  mov     [rbp+0B0h+var_110], r8
0x1400ff32d  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.ObjectName], xmm0
0x1400ff331  mov     [rsp+1B0h+FileHandle], rdi
0x1400ff336  mov     r12, rcx
0x1400ff339  mov     [rbp+0B0h+var_108], rdx
0x1400ff33d  mov     [rbp+0B0h+var_100], rcx
0x1400ff341  movups  xmmword ptr [rbp+0B0h+ObjectAttributes.Length], xmm0
0x1400ff345  movups  xmmword ptr [rbp+0B0h+ObjectAttributes+1Ch], xmm0
0x1400ff349  movups  xmmword ptr [rbp+0B0h+IoStatusBlock], xmm0
0x1400ff34d  movups  xmmword ptr [rbp+0B0h+FileName.Length], xmm1
0x1400ff351  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1400ff358  lea     rsi, [rcx+8]
0x1400ff35c  jz      short loc_1400FF375
0x1400ff35e  mov     r9, [rsi]
0x1400ff361  lea     edx, [rax+1Ah]
0x1400ff364  mov     ecx, 50Bh
0x1400ff369  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x1400ff370  call    WPP_SF_S
0x1400ff375  movzx   ebx, word ptr [r14+2]
0x1400ff37a  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400ff37e  mov     [r14+2], di
0x1400ff383  mov     rax, r15
0x1400ff386  mov     rcx, [rsi]
0x1400ff389  inc     rax
0x1400ff38c  cmp     [rcx+rax*2], di
0x1400ff390  jnz     short loc_1400FF389
0x1400ff392  mov     [rsp+1B0h+EaLength], edi; EaLength
0x1400ff396  lea     r9, [rbp+0B0h+IoStatusBlock]; IoStatusBlock
0x1400ff39a  mov     [rsp+1B0h+EaBuffer], rdi; EaBuffer
0x1400ff39f  lea     r8, [rbp+0B0h+ObjectAttributes]; ObjectAttributes
0x1400ff3a3  mov     [rsp+1B0h+CreateOptions], 21h ; '!'; CreateOptions
0x1400ff3ab  lea     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff3b0  mov     dword ptr [rsp+1B0h+CreateDisposition], 1; CreateDisposition
0x1400ff3b8  add     ax, ax
0x1400ff3bb  mov     [rsp+1B0h+ShareAccess], 7; ShareAccess
0x1400ff3c3  xorps   xmm0, xmm0
0x1400ff3c6  mov     [rsp+1B0h+FileAttributes], 80h; FileAttributes
0x1400ff3ce  mov     edx, 100001h; DesiredAccess
0x1400ff3d3  mov     [rsp+1B0h+AllocationSize], rdi; AllocationSize
0x1400ff3d8  mov     [r12], ax
0x1400ff3dd  mov     [rbp+0B0h+ObjectAttributes.Length], 30h ; '0'
0x1400ff3e4  mov     [rbp+0B0h+ObjectAttributes.RootDirectory], rdi
0x1400ff3e8  mov     [rbp+0B0h+ObjectAttributes.Attributes], 240h
0x1400ff3ef  mov     [rbp+0B0h+ObjectAttributes.ObjectName], r12
0x1400ff3f3  movdqu  xmmword ptr [rbp+0B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ff3f8  call    cs:__imp_ZwCreateFile
0x1400ff3ff  nop     dword ptr [rax+rax+00h]
0x1400ff404  mov     [r14+2], bx
0x1400ff409  mov     edi, eax
0x1400ff40b  mov     rcx, [rsi]
0x1400ff40e  xor     r14d, r14d
0x1400ff411  mov     rax, r15
0x1400ff414  inc     rax
0x1400ff417  cmp     [rcx+rax*2], r14w
0x1400ff41c  jnz     short loc_1400FF414
0x1400ff41e  add     ax, ax
0x1400ff421  mov     [r12], ax
0x1400ff426  test    edi, edi
0x1400ff428  js      loc_1400FF766
0x1400ff42e  lea     rax, [rbp+0B0h+var_9E]
0x1400ff432  xor     r8d, r8d; ppszDestEnd
0x1400ff435  mov     [rbp+0B0h+FileName.Buffer], rax
0x1400ff439  lea     r9, [rbp+0B0h+pcchRemaining]; pcchRemaining
0x1400ff43d  lea     rax, [r13+2]
0x1400ff441  mov     qword ptr [rsp+1B0h+CreateOptions], rax
0x1400ff446  lea     rcx, [rbp+0B0h+pszDest]; pszDest
0x1400ff44a  mov     rax, [rbp+0B0h+var_110]
0x1400ff44e  lea     edx, [r8+21h]; cchDest
0x1400ff452  mov     dword ptr [rsp+1B0h+CreateDisposition], 3Ch ; '<'
0x1400ff45a  mov     qword ptr [rsp+1B0h+ShareAccess], rax
0x1400ff45f  lea     rax, aSCS; "%s%c.%s"
0x1400ff466  mov     qword ptr [rsp+1B0h+FileAttributes], rax; pszFormat
0x1400ff46b  mov     [rsp+1B0h+AllocationSize], r14; dwFlags
0x1400ff470  call    RtlStringCchPrintfExW
0x1400ff475  mov     rcx, [rbp+0B0h+FileName.Buffer]
0x1400ff479  mov     rax, r15
0x1400ff47c  inc     rax
0x1400ff47f  cmp     [rcx+rax*2], r14w
0x1400ff484  jnz     short loc_1400FF47C
0x1400ff486  add     ax, ax
0x1400ff489  lea     r9, UxLowPriorityPool
0x1400ff490  mov     r12d, 1
0x1400ff496  mov     [rbp+0B0h+FileName.Length], ax
0x1400ff49a  mov     edx, 1002h
0x1400ff49f  mov     [rbp+0B0h+FileName.MaximumLength], ax
0x1400ff4a3  mov     r8d, 474C6C55h
0x1400ff4a9  mov     dword ptr [rsp+1B0h+AllocationSize], r12d
0x1400ff4ae  lea     ecx, [r12+41h]
0x1400ff4b3  call    cs:__imp_ExAllocatePool3
0x1400ff4ba  nop     dword ptr [rax+rax+00h]
0x1400ff4bf  mov     rdi, rax
0x1400ff4c2  mov     [rsp+1B0h+FileInformation], rax
0x1400ff4c7  test    rax, rax
0x1400ff4ca  jnz     short loc_1400FF4D6
0x1400ff4cc  mov     edi, 0C000009Ah
0x1400ff4d1  jmp     loc_1400FF766
0x1400ff4d6  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff4db  lea     rax, [rbp+0B0h+FileName]
0x1400ff4df  mov     byte ptr [rsp+1B0h+EaLength], r12b; RestartScan
0x1400ff4e4  xor     r9d, r9d; ApcContext
0x1400ff4e7  mov     [rsp+1B0h+EaBuffer], rax; FileName
0x1400ff4ec  xor     r8d, r8d; ApcRoutine
0x1400ff4ef  mov     byte ptr [rsp+1B0h+CreateOptions], r14b; ReturnSingleEntry
0x1400ff4f4  lea     rax, [rbp+0B0h+IoStatusBlock]
0x1400ff4f8  mov     dword ptr [rsp+1B0h+CreateDisposition], r12d; FileInformationClass
0x1400ff4fd  xor     edx, edx; Event
0x1400ff4ff  mov     [rsp+1B0h+ShareAccess], 0FFEh; Length
0x1400ff507  mov     qword ptr [rsp+1B0h+FileAttributes], rdi; FileInformation
0x1400ff50c  mov     [rsp+1B0h+AllocationSize], rax; IoStatusBlock
0x1400ff511  call    cs:__imp_ZwQueryDirectoryFile
0x1400ff518  nop     dword ptr [rax+rax+00h]
0x1400ff51d  xor     edx, edx
0x1400ff51f  mov     ebx, eax
0x1400ff521  test    eax, eax
0x1400ff523  jns     short loc_1400FF559
0x1400ff525  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x1400ff52c  jz      short loc_1400FF549
0x1400ff52e  mov     rcx, [rbp+0B0h+FileName.Buffer]
0x1400ff532  mov     r9d, eax
0x1400ff535  mov     qword ptr [rsp+1B0h+FileAttributes], rcx
0x1400ff53a  mov     rcx, [rsi]
0x1400ff53d  mov     [rsp+1B0h+AllocationSize], rcx
0x1400ff542  call    WPP_SF_dSS
0x1400ff547  xor     edx, edx
0x1400ff549  cmp     ebx, 0C000000Fh
0x1400ff54f  mov     edi, edx
0x1400ff551  cmovnz  edi, ebx
0x1400ff554  jmp     loc_1400FF74F
0x1400ff559  mov     byte ptr [rsp+1B0h+var_14C], dl
0x1400ff55d  mov     r13d, r12d
0x1400ff560  mov     r14, r12
0x1400ff563  mov     [rsp+1B0h+var_140], r12
0x1400ff568  mov     rbx, rdx
0x1400ff56b  mov     ecx, [rdi+3Ch]
0x1400ff56e  lea     r12, [rdi+40h]
0x1400ff572  shr     rcx, 1
0x1400ff575  movzx   eax, word ptr [rdi+rcx*2+40h]
0x1400ff57a  mov     [rdi+rcx*2+40h], dx
0x1400ff57f  mov     rcx, r12; Str
0x1400ff582  mov     rdx, [rbp+0B0h+SubStr]; SubStr
0x1400ff586  mov     [rsp+1B0h+var_150], ax
0x1400ff58b  call    cs:__imp_wcsstr
0x1400ff592  nop     dword ptr [rax+rax+00h]
0x1400ff597  xor     edx, edx
0x1400ff599  mov     [rbp+0B0h+pcchRemaining], rax
0x1400ff59d  test    rax, rax
0x1400ff5a0  jz      short loc_1400FF613
0x1400ff5a2  mov     [rax], dx
0x1400ff5a5  cmp     [r12], dx
0x1400ff5aa  jz      short loc_1400FF613
0x1400ff5ac  movzx   ecx, byte ptr [r12]; C
0x1400ff5b1  call    cs:__imp_isdigit
0x1400ff5b8  nop     dword ptr [rax+rax+00h]
0x1400ff5bd  xor     edx, edx
0x1400ff5bf  test    eax, eax
0x1400ff5c1  jnz     short loc_1400FF5C9
0x1400ff5c3  add     r12, 2
0x1400ff5c7  jmp     short loc_1400FF5A5
0x1400ff5c9  mov     r8, [rbp+0B0h+pcchRemaining]
0x1400ff5cd  lea     rcx, [rsp+1B0h+var_140]
0x1400ff5d2  mov     qword ptr [rsp+1B0h+ShareAccess], rcx
0x1400ff5d7  sub     r8, r12
0x1400ff5da  mov     qword ptr [rsp+1B0h+FileAttributes], rdx
0x1400ff5df  xor     r9d, r9d
0x1400ff5e2  sar     r8, 1
0x1400ff5e5  mov     rdx, r12
0x1400ff5e8  mov     cl, 1
0x1400ff5ea  mov     dword ptr [rsp+1B0h+AllocationSize], 0Ah
0x1400ff5f2  call    HttpStringToULongLong
0x1400ff5f7  xor     edx, edx
0x1400ff5f9  test    eax, eax
0x1400ff5fb  js      short loc_1400FF60B
0x1400ff5fd  mov     r14, [rsp+1B0h+var_140]
0x1400ff602  cmp     r14, 0FFFFFFh
0x1400ff609  jbe     short loc_1400FF613
0x1400ff60b  mov     r14, rdx
0x1400ff60e  mov     [rsp+1B0h+var_140], rdx
0x1400ff613  mov     eax, [rdi+3Ch]
0x1400ff616  movzx   ecx, [rsp+1B0h+var_150]
0x1400ff61b  shr     rax, 1
0x1400ff61e  mov     [rdi+rax*2+40h], cx
0x1400ff623  mov     eax, r13d
0x1400ff626  cmp     r14, rax
0x1400ff629  jb      short loc_1400FF645
0x1400ff62b  mov     r12d, [rdi+38h]
0x1400ff62f  mov     r13d, r14d
0x1400ff632  mov     rbx, [rdi+28h]
0x1400ff636  shr     r12d, 4
0x1400ff63a  and     r12b, 1
0x1400ff63e  mov     [rsp+1B0h+var_14C], r12d
0x1400ff643  jmp     short loc_1400FF64A
0x1400ff645  mov     r12d, [rsp+1B0h+var_14C]
0x1400ff64a  mov     eax, [rdi]
0x1400ff64c  test    eax, eax
0x1400ff64e  jz      short loc_1400FF658
0x1400ff650  add     rdi, rax
0x1400ff653  jmp     loc_1400FF56B
0x1400ff658  mov     rax, [rsp+1B0h+FileInformation]
0x1400ff65d  xor     r9d, r9d; ApcContext
0x1400ff660  mov     rcx, [rsp+1B0h+FileHandle]; FileHandle
0x1400ff665  xor     r8d, r8d; ApcRoutine
0x1400ff668  mov     byte ptr [rsp+1B0h+EaLength], dl; RestartScan
0x1400ff66c  mov     [rsp+1B0h+EaBuffer], rdx; FileName
0x1400ff671  mov     byte ptr [rsp+1B0h+CreateOptions], dl; ReturnSingleEntry
0x1400ff675  xor     edx, edx; Event
0x1400ff677  mov     dword ptr [rsp+1B0h+CreateDisposition], 1; FileInformationClass
0x1400ff67f  mov     [rsp+1B0h+ShareAccess], 1000h; Length
0x1400ff687  mov     qword ptr [rsp+1B0h+FileAttributes], rax; FileInformation
0x1400ff68c  lea     rax, [rbp+0B0h+IoStatusBlock]
0x1400ff690  mov     [rsp+1B0h+AllocationSize], rax; IoStatusBlock
0x1400ff695  call    cs:__imp_ZwQueryDirectoryFile
0x1400ff69c  nop     dword ptr [rax+rax+00h]
0x1400ff6a1  mov     edi, eax
0x1400ff6a3  cmp     eax, 80000006h
0x1400ff6a8  jz      short loc_1400FF6BE
0x1400ff6aa  xor     edx, edx
0x1400ff6ac  test    eax, eax
0x1400ff6ae  js      loc_1400FF74F
0x1400ff6b4  mov     rdi, [rsp+1B0h+FileInformation]
0x1400ff6b9  jmp     loc_1400FF56B
0x1400ff6be  xor     r14d, r14d
0x1400ff6c1  mov     edi, r14d
0x1400ff6c4  test    r12b, r12b
0x1400ff6c7  jz      short loc_1400FF6CF
0x1400ff6c9  inc     r13d
0x1400ff6cc  mov     ebx, r14d
0x1400ff6cf  mov     rax, [rbp+0B0h+SubStr]
0x1400ff6d3  lea     r9, [rbp+0B0h+pcchRemaining]; pcchRemaining
0x1400ff6d7  mov     rcx, [rbp+0B0h+var_108]; pszDest
0x1400ff6db  add     rax, 2
0x1400ff6df  mov     qword ptr [rsp+1B0h+CreateOptions], rax
0x1400ff6e4  xor     r8d, r8d; ppszDestEnd
0x1400ff6e7  mov     rax, [rbp+0B0h+var_110]
0x1400ff6eb  mov     dword ptr [rsp+1B0h+CreateDisposition], r13d
0x1400ff6f0  mov     qword ptr [rsp+1B0h+ShareAccess], rax
0x1400ff6f5  lea     rax, aSDS; "%s%d.%s"
0x1400ff6fc  mov     qword ptr [rsp+1B0h+FileAttributes], rax; pszFormat
0x1400ff701  lea     edx, [r8+21h]; cchDest
0x1400ff705  mov     [rsp+1B0h+AllocationSize], r14; dwFlags
0x1400ff70a  call    RtlStringCchPrintfExW
0x1400ff70f  mov     rax, [rsi]
0x1400ff712  inc     r15
0x1400ff715  cmp     [rax+r15*2], r14w
0x1400ff71a  jnz     short loc_1400FF712
0x1400ff71c  mov     rax, [rbp+0B0h+var_100]
0x1400ff720  add     r15w, r15w
0x1400ff724  mov     rcx, [rbp+0B0h+var_F8]
0x1400ff728  mov     [rax], r15w
0x1400ff72c  lea     eax, [r13+1]
0x1400ff730  mov     [rcx], eax
0x1400ff732  mov     rax, [rbp+0B0h+var_F0]
0x1400ff736  mov     [rax], rbx
0x1400ff739  test    byte ptr cs:xmmword_1401A2CA0+9, 8
0x1400ff740  jz      short loc_1400FF74F
0x1400ff742  mov     r9, [rsi]
0x1400ff745  mov     [rsp+1B0h+AllocationSize], rbx
0x1400ff74a  call    WPP_SF_SI
0x1400ff74f  mov     rcx, [rsp+1B0h+FileInformation]; P
0x1400ff754  xor     edx, edx; Tag
0x1400ff756  call    cs:__imp_ExFreePoolWithTag
0x1400ff75d  nop     dword ptr [rax+rax+00h]
0x1400ff762  test    edi, edi
0x1400ff764  jns     short loc_1400FF790
0x1400ff766  test    byte ptr cs:xmmword_1401A2C90+9, 8
0x1400ff76d  jz      short loc_1400FF790
0x1400ff76f  mov     rax, [rsi]
0x1400ff772  lea     r8, WPP_2f23f8be26c5304edaaa6b14059384ee_Traceguids
0x1400ff779  mov     edx, 1Dh
0x1400ff77e  mov     [rsp+1B0h+AllocationSize], rax
0x1400ff783  mov     ecx, 30Bh
0x1400ff788  mov     r9d, edi
0x1400ff78b  call    WPP_SF_dS
0x1400ff790  mov     rcx, [rsp+1B0h+FileHandle]; Handle
0x1400ff795  test    rcx, rcx
0x1400ff798  jz      short loc_1400FF7A6
0x1400ff79a  call    cs:__imp_ZwClose
  ... truncated ...
```
