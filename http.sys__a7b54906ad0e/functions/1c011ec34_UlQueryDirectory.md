# UlQueryDirectory

- ea: `0x1c011ec34`
- end: `0x1c011f0f4`
- name: `UlQueryDirectory`
- size: `1216`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1c0017690`
- `0x1c0033f60`

## callees

- `0x1c0002c80`
- `0x1c0018150`
- `0x1c001a4b0`
- `0x1c00919c0`
- `0x1c0098374`
- `0x1c00986a0`
- `0x1c0098710`
- `0x1c011ec34`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x1c011ed4c`
- `ntoskrnl!ZwCreateFile` at `0x1c011ed4c`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1c011ee4e`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1c011efc7`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1c011ee4e`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1c011efc7`
- `ntoskrnl!wcsstr` at `0x1c011eec5`
- `ntoskrnl!wcsstr` at `0x1c011eec5`
- `ntoskrnl!isdigit` at `0x1c011eee6`
- `ntoskrnl!isdigit` at `0x1c011eee6`
- `ntoskrnl!ZwClose` at `0x1c011f0c5`
- `ntoskrnl!ZwClose` at `0x1c011f0c5`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c011edf0`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c011edf0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c011f087`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c011f087`

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
  wchar_t v10; // bx
  __int64 v11; // r14
  __int64 v12; // rax
  NTSTATUS v13; // eax
  NTSTATUS v14; // edi
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int *PoolWithTagPriority; // r13
  unsigned __int64 v19; // r15
  int v20; // ecx
  unsigned int *i; // rdi
  _WORD *v22; // r12
  unsigned __int64 v23; // rax
  wchar_t *v24; // rax
  unsigned __int64 *v25; // rcx
  int v26; // r12d
  __int64 v27; // rax
  NTSTATUS v28; // eax
  __int64 v29; // r15
  int v30; // ebx
  __int64 v31; // rdx
  _DWORD *v32; // rcx
  __int64 CreateDisposition; // [rsp+38h] [rbp-C8h]
  __int64 CreateDispositiona; // [rsp+38h] [rbp-C8h]
  __int16 v36; // [rsp+60h] [rbp-A0h]
  unsigned int v37; // [rsp+64h] [rbp-9Ch]
  bool v38; // [rsp+68h] [rbp-98h]
  void *FileHandle; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v40; // [rsp+78h] [rbp-88h] BYREF
  size_t pcchRemaining; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *SubStr; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h]
  NTSTRSAFE_PWSTR v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  _QWORD *v47; // [rsp+B8h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t pszDest; // [rsp+100h] [rbp+0h] BYREF
  char v51; // [rsp+102h] [rbp+2h] BYREF

  v46 = a5;
  v47 = a6;
  SubStr = a4;
  v38 = 0;
  v44 = a3;
  v45 = a2;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  FileName = 0;
  if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
    WPP_SF_S(26, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids, a1->Buffer);
  v10 = a2[1];
  v11 = -1;
  a2[1] = 0;
  v12 = -1;
  do
    ++v12;
  while ( a1->Buffer[v12] );
  a1->Length = 2 * v12;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x21u, 0, 0);
  a2[1] = v10;
  v14 = v13;
  v15 = 0;
  v16 = -1;
  do
    ++v16;
  while ( a1->Buffer[v16] );
  a1->Length = 2 * v16;
  if ( v14 < 0 )
    goto LABEL_44;
  FileName.Buffer = (PWSTR)&v51;
  LODWORD(CreateDisposition) = 60;
  RtlStringCchPrintfExW(&pszDest, 0x21u, 0, &pcchRemaining, 0, L"%s%c.%s", a3, CreateDisposition, a4 + 1);
  v17 = -1;
  do
    ++v17;
  while ( FileName.Buffer[v17] );
  FileName.Length = 2 * v17;
  FileName.MaximumLength = 2 * v17;
  PoolWithTagPriority = (unsigned int *)ExAllocatePoolWithTagPriority(
                                          (POOL_TYPE)512,
                                          0x1002u,
                                          0x474C6C55u,
                                          LowPoolPriority);
  if ( !PoolWithTagPriority )
  {
    v14 = -1073741670;
LABEL_44:
    if ( (*(_WORD *)&WPP_MAIN_CB.StackSize & 0x400) != 0 )
      WPP_SF_dS(29, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids, (unsigned int)v14, a1->Buffer);
    goto LABEL_46;
  }
  v19 = 1;
  v14 = ZwQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          PoolWithTagPriority,
          0xFFEu,
          FileDirectoryInformation,
          0,
          &FileName,
          1u);
  if ( v14 >= 0 )
  {
    v37 = 1;
    v40 = 1;
    while ( 1 )
    {
      for ( i = PoolWithTagPriority; ; i = (unsigned int *)((char *)i + v27) )
      {
        v22 = i + 16;
        v23 = (unsigned __int64)i[15] >> 1;
        v36 = *((_WORD *)i + v23 + 32);
        *((_WORD *)i + v23 + 32) = 0;
        v24 = wcsstr((const wchar_t *)i + 32, SubStr);
        pcchRemaining = (size_t)v24;
        if ( v24 )
        {
          *v24 = 0;
          while ( *v22 )
          {
            if ( isdigit(*(unsigned __int8 *)v22) )
            {
              v25 = &v40;
              LOBYTE(v25) = 1;
              if ( (int)HttpStringToULongLong(
                          (_DWORD)v25,
                          (_DWORD)v22,
                          (__int64)(pcchRemaining - (_QWORD)v22) >> 1,
                          0,
                          10,
                          0,
                          (__int64)&v40) < 0
                || (v19 = v40, v40 > 0xFFFFFF) )
              {
                v19 = 0;
                v40 = 0;
              }
              break;
            }
            ++v22;
          }
        }
        v26 = v37;
        *((_WORD *)i + ((unsigned __int64)i[15] >> 1) + 32) = v36;
        if ( v19 >= v37 )
        {
          v26 = v19;
          v15 = *((_QWORD *)i + 5);
          v37 = v19;
          v38 = (i[14] & 0x10) != 0;
        }
        v27 = *i;
        if ( !(_DWORD)v27 )
          break;
      }
      v28 = ZwQueryDirectoryFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              PoolWithTagPriority,
              0x1000u,
              FileDirectoryInformation,
              0,
              0,
              0);
      v14 = v28;
      if ( v28 == -2147483642 )
        break;
      if ( v28 < 0 )
        goto LABEL_43;
    }
    v29 = 0;
    if ( !v38 )
      v29 = v15;
    v14 = 0;
    v30 = v26 + 1;
    if ( !v38 )
      v30 = v26;
    LODWORD(CreateDispositiona) = v30;
    RtlStringCchPrintfExW(v45, 0x21u, 0, &pcchRemaining, 0, L"%s%d.%s", v44, CreateDispositiona, SubStr + 1);
    do
      ++v11;
    while ( a1->Buffer[v11] );
    v32 = (_DWORD *)v46;
    a1->Length = 2 * v11;
    *v32 = v30 + 1;
    *v47 = v29;
    if ( (WORD2(WPP_MAIN_CB.Queue.Wcb.DmaWaitEntry.Flink) & 0x400) != 0 )
      WPP_SF_SI(v32, v31, a1->Buffer, v29);
  }
  else
  {
    if ( (*(_WORD *)&WPP_MAIN_CB.StackSize & 0x400) != 0 )
      WPP_SF_dSS(v20, 0, v14, a1->Buffer, (__int64)FileName.Buffer);
    if ( v14 == -1073741809 )
      v14 = 0;
  }
LABEL_43:
  ExFreePoolWithTag(PoolWithTagPriority, 0);
  if ( v14 < 0 )
    goto LABEL_44;
LABEL_46:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1c011ec34  push    rbp
0x1c011ec36  push    rbx
0x1c011ec37  push    rsi
0x1c011ec38  push    rdi
0x1c011ec39  push    r12
0x1c011ec3b  push    r13
0x1c011ec3d  push    r14
0x1c011ec3f  push    r15
0x1c011ec41  lea     rbp, [rsp-68h]
0x1c011ec46  sub     rsp, 168h
0x1c011ec4d  mov     rax, cs:__security_cookie
0x1c011ec54  xor     rax, rsp
0x1c011ec57  mov     [rbp+0A0h+var_50], rax
0x1c011ec5b  mov     rax, [rbp+0A0h+arg_20]
0x1c011ec62  xor     edi, edi
0x1c011ec64  mov     [rbp+0A0h+var_F0], rax
0x1c011ec68  xorps   xmm0, xmm0
0x1c011ec6b  mov     rax, [rbp+0A0h+arg_28]
0x1c011ec72  xorps   xmm1, xmm1
0x1c011ec75  mov     [rbp+0A0h+var_E8], rax
0x1c011ec79  mov     r13, r9
0x1c011ec7c  mov     al, dil
0x1c011ec7f  mov     [rbp+0A0h+SubStr], r9
0x1c011ec83  mov     dword ptr [rsp+1A0h+var_138], eax
0x1c011ec87  mov     r12, r8
0x1c011ec8a  mov     [rbp+0A0h+var_100], r8
0x1c011ec8e  mov     r15, rdx
0x1c011ec91  mov     [rbp+0A0h+var_F8], rdx
0x1c011ec95  mov     rsi, rcx
0x1c011ec98  mov     dword ptr [rbp+0A0h+ObjectAttributes+4], edi
0x1c011ec9b  mov     dword ptr [rbp+0A0h+ObjectAttributes+1Ch], edi
0x1c011ec9e  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1c011eca2  mov     [rsp+1A0h+FileHandle], rdi
0x1c011eca7  movups  xmmword ptr [rbp+0A0h+FileName.Length], xmm1
0x1c011ecab  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 400h
0x1c011ecb5  jz      short loc_1C011ECCA
0x1c011ecb7  mov     r8, [rsi+8]
0x1c011ecbb  lea     ecx, [rdi+1Ah]
0x1c011ecbe  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c011ecc5  call    WPP_SF_S
0x1c011ecca  movzx   ebx, word ptr [r15+2]
0x1c011eccf  or      r14, 0FFFFFFFFFFFFFFFFh
0x1c011ecd3  mov     [r15+2], di
0x1c011ecd8  mov     rax, r14
0x1c011ecdb  mov     rcx, [rsi+8]
0x1c011ecdf  inc     rax
0x1c011ece2  cmp     [rcx+rax*2], di
0x1c011ece6  jnz     short loc_1C011ECDF
0x1c011ece8  mov     [rsp+1A0h+EaLength], edi; EaLength
0x1c011ecec  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1c011ecf0  mov     [rsp+1A0h+EaBuffer], rdi; EaBuffer
0x1c011ecf5  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1c011ecf9  mov     [rsp+1A0h+CreateOptions], 21h ; '!'; CreateOptions
0x1c011ed01  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1c011ed06  mov     dword ptr [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x1c011ed0e  add     ax, ax
0x1c011ed11  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x1c011ed19  xorps   xmm0, xmm0
0x1c011ed1c  mov     [rsp+1A0h+FileAttributes], 80h; FileAttributes
0x1c011ed24  mov     edx, 100001h; DesiredAccess
0x1c011ed29  mov     [rsp+1A0h+AllocationSize], rdi; AllocationSize
0x1c011ed2e  mov     [rsi], ax
0x1c011ed31  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1c011ed38  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rdi
0x1c011ed3c  mov     [rbp+0A0h+ObjectAttributes.Attributes], 240h
0x1c011ed43  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rsi
0x1c011ed47  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1c011ed4c  call    cs:__imp_ZwCreateFile
0x1c011ed53  nop     dword ptr [rax+rax+00h]
0x1c011ed58  mov     [r15+2], bx
0x1c011ed5d  mov     edi, eax
0x1c011ed5f  mov     rcx, [rsi+8]
0x1c011ed63  xor     ebx, ebx
0x1c011ed65  mov     rax, r14
0x1c011ed68  inc     rax
0x1c011ed6b  cmp     [rcx+rax*2], bx
0x1c011ed6f  jnz     short loc_1C011ED68
0x1c011ed71  add     ax, ax
0x1c011ed74  mov     [rsi], ax
0x1c011ed77  test    edi, edi
0x1c011ed79  js      loc_1C011F097
0x1c011ed7f  lea     rax, [rbp+0A0h+var_9E]
0x1c011ed83  xor     r8d, r8d; ppszDestEnd
0x1c011ed86  mov     [rbp+0A0h+FileName.Buffer], rax
0x1c011ed8a  lea     r9, [rbp+0A0h+pcchRemaining]; pcchRemaining
0x1c011ed8e  lea     rax, [r13+2]
0x1c011ed92  mov     qword ptr [rsp+1A0h+CreateOptions], rax
0x1c011ed97  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1c011ed9b  mov     dword ptr [rsp+1A0h+CreateDisposition], 3Ch ; '<'
0x1c011eda3  lea     rax, aSCS; "%s%c.%s"
0x1c011edaa  mov     qword ptr [rsp+1A0h+ShareAccess], r12
0x1c011edaf  lea     edx, [r8+21h]; cchDest
0x1c011edb3  mov     qword ptr [rsp+1A0h+FileAttributes], rax; pszFormat
0x1c011edb8  mov     [rsp+1A0h+AllocationSize], rbx; dwFlags
0x1c011edbd  call    RtlStringCchPrintfExW
0x1c011edc2  mov     rcx, [rbp+0A0h+FileName.Buffer]
0x1c011edc6  mov     rax, r14
0x1c011edc9  inc     rax
0x1c011edcc  cmp     [rcx+rax*2], bx
0x1c011edd0  jnz     short loc_1C011EDC9
0x1c011edd2  add     ax, ax
0x1c011edd5  xor     r9d, r9d; Priority
0x1c011edd8  mov     edx, 1002h; NumberOfBytes
0x1c011eddd  mov     [rbp+0A0h+FileName.Length], ax
0x1c011ede1  mov     ecx, 200h; PoolType
0x1c011ede6  mov     [rbp+0A0h+FileName.MaximumLength], ax
0x1c011edea  mov     r8d, 474C6C55h; Tag
0x1c011edf0  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c011edf7  nop     dword ptr [rax+rax+00h]
0x1c011edfc  mov     r13, rax
0x1c011edff  test    rax, rax
0x1c011ee02  jnz     short loc_1C011EE0E
0x1c011ee04  mov     edi, 0C000009Ah
0x1c011ee09  jmp     loc_1C011F097
0x1c011ee0e  mov     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1c011ee13  lea     rax, [rbp+0A0h+FileName]
0x1c011ee17  mov     r15d, 1
0x1c011ee1d  xor     r9d, r9d; ApcContext
0x1c011ee20  mov     byte ptr [rsp+1A0h+EaLength], r15b; RestartScan
0x1c011ee25  xor     r8d, r8d; ApcRoutine
0x1c011ee28  mov     [rsp+1A0h+EaBuffer], rax; FileName
0x1c011ee2d  xor     edx, edx; Event
0x1c011ee2f  mov     byte ptr [rsp+1A0h+CreateOptions], bl; ReturnSingleEntry
0x1c011ee33  lea     rax, [rbp+0A0h+IoStatusBlock]
0x1c011ee37  mov     dword ptr [rsp+1A0h+CreateDisposition], r15d; FileInformationClass
0x1c011ee3c  mov     [rsp+1A0h+ShareAccess], 0FFEh; Length
0x1c011ee44  mov     qword ptr [rsp+1A0h+FileAttributes], r13; FileInformation
0x1c011ee49  mov     [rsp+1A0h+AllocationSize], rax; IoStatusBlock
0x1c011ee4e  call    cs:__imp_ZwQueryDirectoryFile
0x1c011ee55  nop     dword ptr [rax+rax+00h]
0x1c011ee5a  xor     edx, edx
0x1c011ee5c  mov     edi, eax
0x1c011ee5e  test    eax, eax
0x1c011ee60  jns     short loc_1C011EE98
0x1c011ee62  test    dword ptr cs:WPP_MAIN_CB.StackSize, 400h
0x1c011ee6c  jz      short loc_1C011EE85
0x1c011ee6e  mov     rax, [rbp+0A0h+FileName.Buffer]
0x1c011ee72  mov     r8d, edi
0x1c011ee75  mov     r9, [rsi+8]
0x1c011ee79  mov     [rsp+1A0h+AllocationSize], rax
0x1c011ee7e  call    WPP_SF_dSS
0x1c011ee83  xor     edx, edx
0x1c011ee85  cmp     edi, 0C000000Fh
0x1c011ee8b  jnz     loc_1C011F082
0x1c011ee91  mov     edi, edx
0x1c011ee93  jmp     loc_1C011F082
0x1c011ee98  mov     [rsp+1A0h+var_13C], r15d
0x1c011ee9d  mov     [rsp+1A0h+var_128], r15
0x1c011eea2  mov     rdi, r13
0x1c011eea5  mov     eax, [rdi+3Ch]
0x1c011eea8  lea     r12, [rdi+40h]
0x1c011eeac  shr     rax, 1
0x1c011eeaf  movzx   ecx, word ptr [rdi+rax*2+40h]
0x1c011eeb4  mov     [rsp+1A0h+var_140], cx
0x1c011eeb9  mov     rcx, r12; Str
0x1c011eebc  mov     [rdi+rax*2+40h], dx
0x1c011eec1  mov     rdx, [rbp+0A0h+SubStr]; SubStr
0x1c011eec5  call    cs:__imp_wcsstr
0x1c011eecc  nop     dword ptr [rax+rax+00h]
0x1c011eed1  xor     edx, edx
0x1c011eed3  mov     [rbp+0A0h+pcchRemaining], rax
0x1c011eed7  test    rax, rax
0x1c011eeda  jz      short loc_1C011EF4F
0x1c011eedc  mov     [rax], dx
0x1c011eedf  jmp     short loc_1C011EEFC
0x1c011eee1  movzx   ecx, byte ptr [r12]; C
0x1c011eee6  call    cs:__imp_isdigit
0x1c011eeed  nop     dword ptr [rax+rax+00h]
0x1c011eef2  xor     edx, edx
0x1c011eef4  test    eax, eax
0x1c011eef6  jnz     short loc_1C011EF05
0x1c011eef8  add     r12, 2
0x1c011eefc  cmp     [r12], dx
0x1c011ef01  jnz     short loc_1C011EEE1
0x1c011ef03  jmp     short loc_1C011EF4F
0x1c011ef05  mov     r8, [rbp+0A0h+pcchRemaining]
0x1c011ef09  lea     rcx, [rsp+1A0h+var_128]
0x1c011ef0e  mov     qword ptr [rsp+1A0h+ShareAccess], rcx
0x1c011ef13  sub     r8, r12
0x1c011ef16  mov     qword ptr [rsp+1A0h+FileAttributes], rdx
0x1c011ef1b  xor     r9d, r9d
0x1c011ef1e  sar     r8, 1
0x1c011ef21  mov     rdx, r12
0x1c011ef24  mov     cl, 1
0x1c011ef26  mov     dword ptr [rsp+1A0h+AllocationSize], 0Ah
0x1c011ef2e  call    HttpStringToULongLong
0x1c011ef33  xor     edx, edx
0x1c011ef35  test    eax, eax
0x1c011ef37  js      short loc_1C011EF47
0x1c011ef39  mov     r15, [rsp+1A0h+var_128]
0x1c011ef3e  cmp     r15, 0FFFFFFh
0x1c011ef45  jbe     short loc_1C011EF4F
0x1c011ef47  mov     r15, rdx
0x1c011ef4a  mov     [rsp+1A0h+var_128], rdx
0x1c011ef4f  mov     eax, [rdi+3Ch]
0x1c011ef52  mov     r12d, [rsp+1A0h+var_13C]
0x1c011ef57  movzx   ecx, [rsp+1A0h+var_140]
0x1c011ef5c  shr     rax, 1
0x1c011ef5f  mov     [rdi+rax*2+40h], cx
0x1c011ef64  cmp     r15, r12
0x1c011ef67  jb      short loc_1C011EF81
0x1c011ef69  mov     eax, [rdi+38h]
0x1c011ef6c  mov     r12d, r15d
0x1c011ef6f  mov     rbx, [rdi+28h]
0x1c011ef73  shr     eax, 4
0x1c011ef76  and     al, 1
0x1c011ef78  mov     [rsp+1A0h+var_13C], r15d
0x1c011ef7d  mov     dword ptr [rsp+1A0h+var_138], eax
0x1c011ef81  mov     eax, [rdi]
0x1c011ef83  test    eax, eax
0x1c011ef85  jz      short loc_1C011EF8F
0x1c011ef87  add     rdi, rax
0x1c011ef8a  jmp     loc_1C011EEA5
0x1c011ef8f  mov     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1c011ef94  lea     rax, [rbp+0A0h+IoStatusBlock]
0x1c011ef98  mov     byte ptr [rsp+1A0h+EaLength], dl; RestartScan
0x1c011ef9c  xor     r9d, r9d; ApcContext
0x1c011ef9f  mov     [rsp+1A0h+EaBuffer], rdx; FileName
0x1c011efa4  xor     r8d, r8d; ApcRoutine
0x1c011efa7  mov     byte ptr [rsp+1A0h+CreateOptions], dl; ReturnSingleEntry
0x1c011efab  xor     edx, edx; Event
0x1c011efad  mov     dword ptr [rsp+1A0h+CreateDisposition], 1; FileInformationClass
0x1c011efb5  mov     [rsp+1A0h+ShareAccess], 1000h; Length
0x1c011efbd  mov     qword ptr [rsp+1A0h+FileAttributes], r13; FileInformation
0x1c011efc2  mov     [rsp+1A0h+AllocationSize], rax; IoStatusBlock
0x1c011efc7  call    cs:__imp_ZwQueryDirectoryFile
0x1c011efce  nop     dword ptr [rax+rax+00h]
0x1c011efd3  xor     edx, edx
0x1c011efd5  mov     edi, eax
0x1c011efd7  cmp     eax, 80000006h
0x1c011efdc  jz      short loc_1C011EFEB
0x1c011efde  test    eax, eax
0x1c011efe0  js      loc_1C011F082
0x1c011efe6  jmp     loc_1C011EEA2
0x1c011efeb  mov     eax, dword ptr [rsp+1A0h+var_138]
0x1c011efef  lea     r9, [rbp+0A0h+pcchRemaining]; pcchRemaining
0x1c011eff3  mov     rcx, [rbp+0A0h+var_F8]; pszDest
0x1c011eff7  test    al, al
0x1c011eff9  mov     rax, [rbp+0A0h+SubStr]
0x1c011effd  mov     r15, rdx
0x1c011f000  cmovz   r15, rbx
0x1c011f004  mov     edi, edx
0x1c011f006  lea     ebx, [r12+1]
0x1c011f00b  cmovz   ebx, r12d
0x1c011f00f  add     rax, 2
0x1c011f013  mov     qword ptr [rsp+1A0h+CreateOptions], rax
0x1c011f018  xor     r8d, r8d; ppszDestEnd
0x1c011f01b  mov     rax, [rbp+0A0h+var_100]
0x1c011f01f  mov     dword ptr [rsp+1A0h+CreateDisposition], ebx
0x1c011f023  mov     qword ptr [rsp+1A0h+ShareAccess], rax
0x1c011f028  lea     rax, aSDS; "%s%d.%s"
0x1c011f02f  mov     qword ptr [rsp+1A0h+FileAttributes], rax; pszFormat
0x1c011f034  mov     [rsp+1A0h+AllocationSize], rdx; dwFlags
0x1c011f039  lea     edx, [r8+21h]; cchDest
0x1c011f03d  call    RtlStringCchPrintfExW
0x1c011f042  mov     rax, [rsi+8]
0x1c011f046  xor     ecx, ecx
0x1c011f048  inc     r14
0x1c011f04b  cmp     [rax+r14*2], cx
0x1c011f050  jnz     short loc_1C011F048
0x1c011f052  mov     rcx, [rbp+0A0h+var_F0]
0x1c011f056  lea     eax, [rbx+1]
0x1c011f059  add     r14w, r14w
0x1c011f05d  mov     [rsi], r14w
0x1c011f061  mov     [rcx], eax
0x1c011f063  mov     rax, [rbp+0A0h+var_E8]
0x1c011f067  mov     [rax], r15
0x1c011f06a  test    dword ptr cs:WPP_MAIN_CB.Queue+4, 400h
0x1c011f074  jz      short loc_1C011F082
0x1c011f076  mov     r8, [rsi+8]
0x1c011f07a  mov     r9, r15
0x1c011f07d  call    WPP_SF_SI
0x1c011f082  xor     edx, edx; Tag
0x1c011f084  mov     rcx, r13; P
0x1c011f087  call    cs:__imp_ExFreePoolWithTag
0x1c011f08e  nop     dword ptr [rax+rax+00h]
0x1c011f093  test    edi, edi
0x1c011f095  jns     short loc_1C011F0BB
0x1c011f097  test    dword ptr cs:WPP_MAIN_CB.StackSize, 400h
0x1c011f0a1  jz      short loc_1C011F0BB
0x1c011f0a3  mov     r9, [rsi+8]
0x1c011f0a7  lea     rdx, WPP_07d3f8078d093d4b6da456c67947dc87_Traceguids
0x1c011f0ae  mov     ecx, 1Dh
0x1c011f0b3  mov     r8d, edi
0x1c011f0b6  call    WPP_SF_dS
0x1c011f0bb  mov     rcx, [rsp+1A0h+FileHandle]; Handle
0x1c011f0c0  test    rcx, rcx
0x1c011f0c3  jz      short loc_1C011F0D1
0x1c011f0c5  call    cs:__imp_ZwClose
0x1c011f0cc  nop     dword ptr [rax+rax+00h]
0x1c011f0d1  mov     eax, edi
0x1c011f0d3  mov     rcx, [rbp+0A0h+var_50]
0x1c011f0d7  xor     rcx, rsp; StackCookie
0x1c011f0da  call    __security_check_cookie
0x1c011f0df  add     rsp, 168h
0x1c011f0e6  pop     r15
0x1c011f0e8  pop     r14
0x1c011f0ea  pop     r13
0x1c011f0ec  pop     r12
0x1c011f0ee  pop     rdi
  ... truncated ...
```
