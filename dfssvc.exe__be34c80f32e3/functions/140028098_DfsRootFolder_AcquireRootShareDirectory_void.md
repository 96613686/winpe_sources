# DfsRootFolder::AcquireRootShareDirectory(void)

- ea: `0x140028098`
- end: `0x14002879a`
- name: `?AcquireRootShareDirectory@DfsRootFolder@@QEAAKXZ`
- size: `1794`
- prototype: `unsigned int __fastcall(DfsRootFolder *__hidden this)`
- caller_count: `7`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000b040`
- `0x14000c2bc`
- `0x140021460`
- `0x140021e40`
- `0x14002b810`
- `0x140044df0`
- `0x140045478`

## callees

- `0x1400011c4`
- `0x1400011d0`
- `0x1400096d8`
- `0x14000971c`
- `0x1400097f8`
- `0x14000b934`
- `0x14001648c`
- `0x14001668c`
- `0x1400181b0`
- `0x140018dbc`
- `0x140028098`
- `0x14002a7b4`
- `0x14002bdc8`
- `0x14002f21c`
- `0x140032c20`
- `0x14005858c`
- `0x140058ce0`
- `0x14005ce70`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140028253`
- `ntdll!NtOpenFile` at `0x140028253`
- `ntdll!RtlCompareUnicodeString` at `0x14002858c`
- `ntdll!RtlCompareUnicodeString` at `0x14002858c`
- `ntdll!RtlNtStatusToDosError` at `0x1400282f4`
- `ntdll!RtlNtStatusToDosError` at `0x140028358`
- `ntdll!RtlNtStatusToDosError` at `0x1400282f4`
- `ntdll!RtlNtStatusToDosError` at `0x140028358`
- `ntdll!NtQueryVolumeInformationFile` at `0x140028282`
- `ntdll!NtQueryVolumeInformationFile` at `0x140028282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400282cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400282cf`

## pseudocode

```c
__int64 __fastcall DfsRootFolder::AcquireRootShareDirectory(DfsRootFolder *this)
{
  struct _UNICODE_STRING *v1; // r12
  struct _UNICODE_STRING *v2; // r13
  _UNKNOWN **v4; // rax
  unsigned int *v5; // rcx
  ULONG SharePath; // ebx
  _WORD *v7; // rax
  char *v8; // r15
  NTSTATUS v9; // eax
  NTSTATUS IsRootShareMountPoint; // esi
  ULONG v11; // eax
  int v12; // r8d
  int v13; // r8d
  unsigned int *v14; // r10
  struct _UNICODE_STRING *v15; // rcx
  struct _UNICODE_STRING *v16; // r15
  struct _UNICODE_STRING *v17; // rcx
  int v18; // eax
  struct _UNICODE_STRING *v19; // rcx
  struct _UNICODE_STRING *v20; // rcx
  char v22; // [rsp+48h] [rbp-59h]
  char v23; // [rsp+49h] [rbp-58h]
  void *FileHandle; // [rsp+50h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-49h] BYREF
  struct _UNICODE_STRING v26; // [rsp+68h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-29h] BYREF
  unsigned __int16 *v28[2]; // [rsp+A8h] [rbp+7h] BYREF
  __int128 v29; // [rsp+B8h] [rbp+17h]

  v1 = (struct _UNICODE_STRING *)((char *)this + 152);
  FileHandle = 0;
  v2 = 0;
  v22 = 0;
  v23 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  *(_OWORD *)v28 = 0;
  v29 = 0;
  v26 = 0;
  v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v5 = pWppControl;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && pWppControl
    && (pWppControl[7] & 0x20) != 0
    && *((_BYTE *)pWppControl + 25) >= 3u )
  {
    WPP_SF_qZ(
      *((_QWORD *)pWppControl + 2),
      38,
      (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
      (_DWORD)this,
      (__int64)v1);
    v4 = (_UNKNOWN **)WPP_GLOBAL_Control;
    v5 = pWppControl;
  }
  if ( (*((_BYTE *)this + 272) & 0x20) == 0 && *((_BYTE *)this + 217) )
  {
    SharePath = DfsGetSharePath(*((_QWORD *)this + 36), *((_QWORD *)this + 20), (char *)this + 168);
    if ( !SharePath )
    {
      v7 = (_WORD *)*((_QWORD *)this + 22);
      if ( !v7 || !*v7 )
        goto LABEL_37;
      SharePath = DfsCreateUnicodeString((char *)this + 184, (char *)this + 168);
    }
    if ( SharePath )
      goto LABEL_38;
    v2 = (struct _UNICODE_STRING *)((char *)this + 184);
    if ( this != (DfsRootFolder *)-184LL && *((_QWORD *)this + 24) && v2->Length )
    {
      v8 = (char *)operator new(0x114u);
      if ( !v8 )
      {
        SharePath = 8;
        goto LABEL_38;
      }
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)((char *)this + 184);
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v9 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 3u, 0x4021u);
      IsRootShareMountPoint = v9;
      if ( v9 )
      {
        v11 = RtlNtStatusToDosError(v9);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (((1 << (v11 != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
          && *((_BYTE *)pWppControl + 25) )
        {
          WPP_SF_qZZd(
            *((_QWORD *)pWppControl + 2),
            40,
            v12,
            (_DWORD)this,
            (__int64)v1,
            (__int64)this + 184,
            IsRootShareMountPoint);
        }
      }
      else
      {
        IsRootShareMountPoint = NtQueryVolumeInformationFile(
                                  FileHandle,
                                  &IoStatusBlock,
                                  v8,
                                  0x114u,
                                  FileFsAttributeInformation);
        if ( !IsRootShareMountPoint && *v8 >= 0 )
        {
          v28[0] = v1->Buffer;
          IsRootShareMountPoint = -1073741637;
          v28[1] = *((unsigned __int16 **)this + 24);
          DfsRootFolder::GenerateEventLog(this, 0xC00038A8, 2u, (const unsigned __int16 **const)v28, 0);
        }
        CloseHandle(FileHandle);
        if ( !IsRootShareMountPoint )
        {
          IsRootShareMountPoint = DfsRootFolder::IsRootShareMountPoint(
                                    this,
                                    (struct _UNICODE_STRING *)((char *)this + 184));
          if ( !IsRootShareMountPoint )
            goto LABEL_30;
        }
      }
      SharePath = RtlNtStatusToDosError(IsRootShareMountPoint);
LABEL_30:
      operator delete(v8);
      v14 = pWppControl;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
        goto LABEL_44;
      if ( !pWppControl
        || (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
        || !*((_BYTE *)pWppControl + 25) )
      {
LABEL_39:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && v14
          && (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & v14[7]) != 0
          && *((_BYTE *)v14 + 25) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)v14 + 2), 42, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, this, SharePath);
          v14 = pWppControl;
        }
LABEL_44:
        if ( SharePath )
          goto LABEL_73;
        SharePath = DfsAddKnownDirectoryPath(v2, v1);
        if ( SharePath )
        {
          v28[0] = v1->Buffer;
          v28[1] = v2->Buffer;
          SharePath = 161;
          DfsRootFolder::GenerateEventLog(this, 0xC00038A9, 2u, (const unsigned __int16 **const)v28, 0);
        }
        else
        {
          v22 = 1;
        }
        v14 = pWppControl;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)pWppControl + 2), 43, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, this, SharePath);
          v14 = pWppControl;
        }
        if ( SharePath )
        {
LABEL_73:
          v16 = (struct _UNICODE_STRING *)((char *)this + 296);
          goto LABEL_74;
        }
        v15 = (struct _UNICODE_STRING *)((char *)this + 280);
        if ( *((_BYTE *)this + 216) != 1 )
          v15 = 0;
        SharePath = DfsUserModeAttachToFilesystem(v15, v2, v1);
        v14 = pWppControl;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && pWppControl
          && (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) != 0
          && *((_BYTE *)pWppControl + 25) >= 3u )
        {
          WPP_SF_qd(*((_QWORD *)pWppControl + 2), 44, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, this, SharePath);
          v14 = pWppControl;
        }
        v16 = (struct _UNICODE_STRING *)((char *)this + 296);
        if ( SharePath )
          goto LABEL_74;
        v23 = 1;
        if ( RtlCompareUnicodeString(v1, (PCUNICODE_STRING)((char *)this + 296), 1u) )
        {
          v17 = (struct _UNICODE_STRING *)((char *)this + 280);
          if ( *((_BYTE *)this + 216) != 1 )
            v17 = 0;
          SharePath = DfsUserModeAttachToFilesystem(v17, &v26, (struct _UNICODE_STRING *)((char *)this + 296));
          if ( SharePath )
          {
LABEL_72:
            v14 = pWppControl;
LABEL_74:
            v18 = *((_DWORD *)this + 68);
            if ( SharePath )
            {
              *((_DWORD *)this + 61) = SharePath;
              *((_DWORD *)this + 68) = v18 & 0xFFFFFF9F;
              if ( v22 == 1 )
              {
                DfsRemoveKnownDirectoryPath(v2, v1);
                v14 = pWppControl;
              }
              if ( v23 == 1 )
              {
                v19 = (struct _UNICODE_STRING *)((char *)this + 280);
                if ( *((_BYTE *)this + 216) != 1 )
                  v19 = 0;
                DfsUserModeDetachFromFilesystem(v19, v2, v1);
                v14 = pWppControl;
              }
              if ( *((_BYTE *)this + 125) == 1 )
              {
                v20 = (struct _UNICODE_STRING *)((char *)this + 280);
                if ( *((_BYTE *)this + 216) != 1 )
                  v20 = 0;
                DfsUserModeDetachFromFilesystem(v20, &v26, v16);
                v14 = pWppControl;
              }
            }
            else
            {
              *((_DWORD *)this + 68) = v18 & 0xFFFFFF9F | 0x20;
              *((_DWORD *)this + 61) = 0;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && v14
              && (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & v14[7]) != 0
              && *((_BYTE *)v14 + 25) >= 3u )
            {
              WPP_SF_qZD(
                *((_QWORD *)v14 + 2),
                46,
                (unsigned int)WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids,
                (_DWORD)this,
                (__int64)v1,
                SharePath);
            }
            return SharePath;
          }
          *((_BYTE *)this + 125) = 1;
        }
        SharePath = SendShareToSrv((struct _UNICODE_STRING *)((char *)this + 280), v1, 1u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          v14 = pWppControl;
          if ( !pWppControl
            || (((1 << (SharePath != 0 ? 11 : 31)) | 0x20) & pWppControl[7]) == 0
            || *((_BYTE *)pWppControl + 25) < 3u )
          {
            goto LABEL_74;
          }
          WPP_SF_qd(*((_QWORD *)pWppControl + 2), 45, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, this, SharePath);
        }
        goto LABEL_72;
      }
      WPP_SF_qZZd(
        *((_QWORD *)pWppControl + 2),
        41,
        v13,
        (_DWORD)this,
        (__int64)v1,
        (__int64)this + 184,
        IsRootShareMountPoint);
LABEL_38:
      v14 = pWppControl;
      goto LABEL_39;
    }
LABEL_37:
    SharePath = 87;
    goto LABEL_38;
  }
  if ( v4 != &WPP_GLOBAL_Control && v5 && (v5[7] & 0x20) != 0 && *((_BYTE *)v5 + 25) >= 3u )
    WPP_SF_q(*((_QWORD *)v5 + 2), 39, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids, this);
  return 0;
}

```

## disassembly

```asm
0x140028098  mov     rax, rsp
0x14002809b  mov     [rax+10h], rbx
0x14002809f  mov     [rax+18h], rsi
0x1400280a3  mov     [rax+20h], rdi
0x1400280a7  push    rbp
0x1400280a8  push    r12
0x1400280aa  push    r13
0x1400280ac  push    r14
0x1400280ae  push    r15
0x1400280b0  lea     rbp, [rax-5Fh]
0x1400280b4  sub     rsp, 0D0h
0x1400280bb  mov     rax, cs:__security_cookie
0x1400280c2  xor     rax, rsp
0x1400280c5  mov     [rbp+57h+var_30], rax
0x1400280c9  xorps   xmm0, xmm0
0x1400280cc  lea     r12, [rcx+98h]
0x1400280d3  xor     r15d, r15d
0x1400280d6  xorps   xmm1, xmm1
0x1400280d9  mov     [rbp+57h+FileHandle], r15
0x1400280dd  mov     r13d, r15d
0x1400280e0  mov     [rbp+57h+var_B0], r15b
0x1400280e4  mov     rdi, rcx
0x1400280e7  mov     [rbp+57h+var_AF], r15b
0x1400280eb  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400280ef  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400280f3  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400280f7  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400280fb  movups  xmmword ptr [rbp+57h+var_50], xmm1
0x1400280ff  movups  [rbp+57h+var_40], xmm1
0x140028103  movups  xmmword ptr [rbp+57h+var_90.Length], xmm0
0x140028107  mov     rax, cs:WPP_GLOBAL_Control
0x14002810e  lea     rdx, WPP_GLOBAL_Control
0x140028115  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002811c  lea     r14d, [r15+20h]
0x140028120  cmp     rax, rdx
0x140028123  jz      short loc_140028167
0x140028125  test    rcx, rcx
0x140028128  jz      short loc_140028167
0x14002812a  test    [rcx+1Ch], r14b
0x14002812e  jz      short loc_140028167
0x140028130  cmp     byte ptr [rcx+19h], 3
0x140028134  jb      short loc_140028167
0x140028136  mov     rcx, [rcx+10h]
0x14002813a  lea     edx, [r15+26h]
0x14002813e  mov     r9, rdi
0x140028141  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x140028146  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x14002814d  call    WPP_SF_qZ
0x140028152  mov     rax, cs:WPP_GLOBAL_Control
0x140028159  lea     rdx, WPP_GLOBAL_Control
0x140028160  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028167  test    [rdi+110h], r14b
0x14002816e  jnz     loc_14002873C
0x140028174  cmp     [rdi+0D9h], r15b
0x14002817b  jz      loc_14002873C
0x140028181  mov     rdx, [rdi+0A0h]
0x140028188  lea     rsi, [rdi+0A8h]
0x14002818f  mov     rcx, [rdi+120h]
0x140028196  mov     r8, rsi
0x140028199  call    DfsGetSharePath
0x14002819e  mov     ebx, eax
0x1400281a0  test    eax, eax
0x1400281a2  jnz     short loc_1400281CF
0x1400281a4  mov     rax, [rdi+0B0h]
0x1400281ab  test    rax, rax
0x1400281ae  jz      loc_1400283DA
0x1400281b4  cmp     [rax], r15w
0x1400281b8  jz      loc_1400283DA
0x1400281be  lea     rcx, [rdi+0B8h]
0x1400281c5  mov     rdx, rsi
0x1400281c8  call    DfsCreateUnicodeString
0x1400281cd  mov     ebx, eax
0x1400281cf  test    ebx, ebx
0x1400281d1  jnz     loc_1400283DF
0x1400281d7  lea     r13, [rdi+0B8h]
0x1400281de  test    r13, r13
0x1400281e1  jz      loc_1400283DA
0x1400281e7  cmp     [r13+8], r15
0x1400281eb  jz      loc_1400283DA
0x1400281f1  cmp     [r13+0], r15w
0x1400281f6  jz      loc_1400283DA
0x1400281fc  mov     ecx, 114h; Size
0x140028201  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140028206  mov     r15, rax
0x140028209  xor     eax, eax
0x14002820b  test    r15, r15
0x14002820e  jz      loc_1400283D3
0x140028214  xorps   xmm0, xmm0
0x140028217  mov     [rsp+0F0h+OpenOptions], 4021h; OpenOptions
0x14002821f  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140028223  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002822a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002822e  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140028232  mov     edx, 100001h; DesiredAccess
0x140028237  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14002823e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140028242  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x140028246  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002824b  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x140028253  call    cs:__imp_NtOpenFile
0x14002825a  nop     dword ptr [rax+rax+00h]
0x14002825f  mov     esi, eax
0x140028261  test    eax, eax
0x140028263  jnz     loc_1400282F2
0x140028269  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002826d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140028271  mov     r9d, 114h; Length
0x140028277  mov     [rsp+0F0h+ShareAccess], 5; FsInformationClass
0x14002827f  mov     r8, r15; FsInformation
0x140028282  call    cs:__imp_NtQueryVolumeInformationFile
0x140028289  nop     dword ptr [rax+rax+00h]
0x14002828e  xor     ecx, ecx
0x140028290  mov     esi, eax
0x140028292  test    eax, eax
0x140028294  jnz     short loc_1400282CB
0x140028296  test    byte ptr [r15], 80h
0x14002829a  jnz     short loc_1400282CB
0x14002829c  mov     rax, [r12+8]
0x1400282a1  lea     r8d, [rbx+2]; unsigned __int16
0x1400282a5  mov     [rbp+57h+var_50], rax
0x1400282a9  lea     r9, [rbp+57h+var_50]; unsigned __int16 **
0x1400282ad  mov     rax, [r13+8]
0x1400282b1  mov     edx, 0C00038A8h; unsigned int
0x1400282b6  mov     [rsp+0F0h+ShareAccess], ecx; unsigned int
0x1400282ba  mov     esi, 0C00000BBh
0x1400282bf  mov     rcx, rdi; this
0x1400282c2  mov     [rbp+57h+var_50+8], rax
0x1400282c6  call    ?GenerateEventLog@DfsRootFolder@@QEAAXKGQEAPEBGK@Z; DfsRootFolder::GenerateEventLog(ulong,ushort,ushort const * * const,ulong)
0x1400282cb  mov     rcx, [rbp+57h+FileHandle]; hObject
0x1400282cf  call    cs:__imp_CloseHandle
0x1400282d6  nop     dword ptr [rax+rax+00h]
0x1400282db  test    esi, esi
0x1400282dd  jnz     short loc_140028356
0x1400282df  mov     rdx, r13; struct _UNICODE_STRING *
0x1400282e2  mov     rcx, rdi; this
0x1400282e5  call    ?IsRootShareMountPoint@DfsRootFolder@@QEAAJPEAU_UNICODE_STRING@@@Z; DfsRootFolder::IsRootShareMountPoint(_UNICODE_STRING *)
0x1400282ea  mov     esi, eax
0x1400282ec  test    eax, eax
0x1400282ee  jz      short loc_140028366
0x1400282f0  jmp     short loc_140028356
0x1400282f2  mov     ecx, esi; Status
0x1400282f4  call    cs:__imp_RtlNtStatusToDosError
0x1400282fb  nop     dword ptr [rax+rax+00h]
0x140028300  lea     rcx, WPP_GLOBAL_Control
0x140028307  cmp     cs:WPP_GLOBAL_Control, rcx
0x14002830e  jz      short loc_140028356
0x140028310  mov     rcx, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028317  test    rcx, rcx
0x14002831a  jz      short loc_140028356
0x14002831c  neg     eax
0x14002831e  mov     eax, r14d
0x140028321  sbb     edx, edx
0x140028323  and     edx, 0FFFFFFECh
0x140028326  add     edx, 1Fh
0x140028329  bts     eax, edx
0x14002832c  test    [rcx+1Ch], eax
0x14002832f  jz      short loc_140028356
0x140028331  cmp     byte ptr [rcx+19h], 1
0x140028335  jb      short loc_140028356
0x140028337  mov     rcx, [rcx+10h]
0x14002833b  mov     edx, 28h ; '('
0x140028340  mov     [rsp+0F0h+var_C0], esi
0x140028344  mov     r9, rdi
0x140028347  mov     qword ptr [rsp+0F0h+OpenOptions], r13
0x14002834c  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x140028351  call    WPP_SF_qZZd
0x140028356  mov     ecx, esi; Status
0x140028358  call    cs:__imp_RtlNtStatusToDosError
0x14002835f  nop     dword ptr [rax+rax+00h]
0x140028364  mov     ebx, eax
0x140028366  mov     rcx, r15; Block
0x140028369  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002836e  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028375  lea     rax, WPP_GLOBAL_Control
0x14002837c  cmp     cs:WPP_GLOBAL_Control, rax
0x140028383  jz      short loc_1400283CA
0x140028385  test    r10, r10
0x140028388  jz      short loc_1400283E6
0x14002838a  mov     ecx, ebx
0x14002838c  mov     eax, r14d
0x14002838f  neg     ecx
0x140028391  sbb     edx, edx
0x140028393  and     edx, 0FFFFFFECh
0x140028396  add     edx, 1Fh
0x140028399  bts     eax, edx
0x14002839c  test    [r10+1Ch], eax
0x1400283a0  jz      short loc_1400283E6
0x1400283a2  cmp     byte ptr [r10+19h], 1
0x1400283a7  jb      short loc_1400283E6
0x1400283a9  mov     rcx, [r10+10h]
0x1400283ad  mov     edx, 29h ; ')'
0x1400283b2  mov     [rsp+0F0h+var_C0], esi
0x1400283b6  mov     r9, rdi
0x1400283b9  mov     qword ptr [rsp+0F0h+OpenOptions], r13
0x1400283be  mov     qword ptr [rsp+0F0h+ShareAccess], r12
0x1400283c3  call    WPP_SF_qZZd
0x1400283c8  jmp     short loc_1400283DF
0x1400283ca  lea     rsi, WPP_GLOBAL_Control
0x1400283d1  jmp     short loc_14002843D
0x1400283d3  mov     ebx, 8
0x1400283d8  jmp     short loc_1400283DF
0x1400283da  mov     ebx, 57h ; 'W'
0x1400283df  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400283e6  lea     rsi, WPP_GLOBAL_Control
0x1400283ed  cmp     cs:WPP_GLOBAL_Control, rsi
0x1400283f4  jz      short loc_14002843D
0x1400283f6  test    r10, r10
0x1400283f9  jz      short loc_14002843D
0x1400283fb  mov     eax, ebx
0x1400283fd  neg     eax
0x1400283ff  mov     eax, r14d
0x140028402  sbb     ecx, ecx
0x140028404  and     ecx, 0FFFFFFECh
0x140028407  add     ecx, 1Fh
0x14002840a  bts     eax, ecx
0x14002840d  test    [r10+1Ch], eax
0x140028411  jz      short loc_14002843D
0x140028413  cmp     byte ptr [r10+19h], 3
0x140028418  jb      short loc_14002843D
0x14002841a  mov     rcx, [r10+10h]
0x14002841e  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x140028425  mov     edx, 2Ah ; '*'
0x14002842a  mov     [rsp+0F0h+ShareAccess], ebx
0x14002842e  mov     r9, rdi
0x140028431  call    WPP_SF_qd
0x140028436  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002843d  xor     r15d, r15d
0x140028440  test    ebx, ebx
0x140028442  jnz     loc_140028632
0x140028448  mov     rdx, r12; struct _UNICODE_STRING *
0x14002844b  mov     rcx, r13; struct _UNICODE_STRING *
0x14002844e  call    ?DfsAddKnownDirectoryPath@@YAKPEAU_UNICODE_STRING@@0@Z; DfsAddKnownDirectoryPath(_UNICODE_STRING *,_UNICODE_STRING *)
0x140028453  mov     ebx, eax
0x140028455  test    eax, eax
0x140028457  jnz     short loc_14002845F
0x140028459  mov     [rbp+57h+var_B0], 1
0x14002845d  jmp     short loc_140028491
0x14002845f  mov     rax, [r12+8]
0x140028464  lea     r9, [rbp+57h+var_50]; unsigned __int16 **
0x140028468  mov     [rbp+57h+var_50], rax
0x14002846c  mov     r8d, 2; unsigned __int16
0x140028472  mov     rax, [r13+8]
0x140028476  mov     edx, 0C00038A9h; unsigned int
0x14002847b  mov     rcx, rdi; this
0x14002847e  mov     [rbp+57h+var_50+8], rax
0x140028482  mov     ebx, 0A1h
0x140028487  mov     [rsp+0F0h+ShareAccess], r15d; unsigned int
0x14002848c  call    ?GenerateEventLog@DfsRootFolder@@QEAAXKGQEAPEBGK@Z; DfsRootFolder::GenerateEventLog(ulong,ushort,ushort const * * const,ulong)
0x140028491  cmp     cs:WPP_GLOBAL_Control, rsi
0x140028498  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x14002849f  jz      short loc_1400284E8
0x1400284a1  test    r10, r10
0x1400284a4  jz      short loc_1400284E8
0x1400284a6  mov     eax, ebx
0x1400284a8  neg     eax
0x1400284aa  mov     eax, r14d
0x1400284ad  sbb     ecx, ecx
0x1400284af  and     ecx, 0FFFFFFECh
0x1400284b2  add     ecx, 1Fh
0x1400284b5  bts     eax, ecx
0x1400284b8  test    [r10+1Ch], eax
0x1400284bc  jz      short loc_1400284E8
0x1400284be  cmp     byte ptr [r10+19h], 3
0x1400284c3  jb      short loc_1400284E8
0x1400284c5  mov     rcx, [r10+10h]
0x1400284c9  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
0x1400284d0  mov     edx, 2Bh ; '+'
0x1400284d5  mov     [rsp+0F0h+ShareAccess], ebx
0x1400284d9  mov     r9, rdi
0x1400284dc  call    WPP_SF_qd
0x1400284e1  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x1400284e8  test    ebx, ebx
0x1400284ea  jnz     loc_140028632
0x1400284f0  cmp     byte ptr [rdi+0D8h], 1
0x1400284f7  lea     rsi, [rdi+118h]
0x1400284fe  mov     rcx, rsi
0x140028501  mov     r8, r12; struct _UNICODE_STRING *
0x140028504  cmovnz  rcx, r15; struct _UNICODE_STRING *
0x140028508  mov     rdx, r13; struct _UNICODE_STRING *
0x14002850b  call    ?DfsUserModeAttachToFilesystem@@YAKPEAU_UNICODE_STRING@@00@Z; DfsUserModeAttachToFilesystem(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x140028510  mov     ebx, eax
0x140028512  mov     r10, cs:?pWppControl@@3PEAXEA; void * pWppControl
0x140028519  lea     rax, WPP_GLOBAL_Control
0x140028520  cmp     cs:WPP_GLOBAL_Control, rax
0x140028527  jz      short loc_140028570
0x140028529  test    r10, r10
0x14002852c  jz      short loc_140028570
0x14002852e  mov     eax, ebx
0x140028530  neg     eax
0x140028532  mov     eax, r14d
0x140028535  sbb     ecx, ecx
0x140028537  and     ecx, 0FFFFFFECh
0x14002853a  add     ecx, 1Fh
0x14002853d  bts     eax, ecx
0x140028540  test    [r10+1Ch], eax
0x140028544  jz      short loc_140028570
0x140028546  cmp     byte ptr [r10+19h], 3
0x14002854b  jb      short loc_140028570
0x14002854d  mov     rcx, [r10+10h]
0x140028551  lea     r8, WPP_88cd1a0d2bcf348834b1df4c6fbc4108_Traceguids
  ... truncated ...
```
