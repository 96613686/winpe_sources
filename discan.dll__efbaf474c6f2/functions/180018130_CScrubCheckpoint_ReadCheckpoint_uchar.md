# CScrubCheckpoint::_ReadCheckpoint(uchar *)

- ea: `0x180018130`
- end: `0x180018606`
- name: `?_ReadCheckpoint@CScrubCheckpoint@@AEAAJPEAE@Z`
- size: `1238`
- prototype: `__int64 __fastcall(CScrubCheckpoint *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800177c4`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x1800064d8`
- `0x180006688`
- `0x180006874`
- `0x1800088a4`
- `0x18000891c`
- `0x180010160`
- `0x180012940`
- `0x1800129b0`
- `0x180017ca0`
- `0x180018130`
- `0x180037620`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x180018576`
- `ntdll!NtQueryInformationFile` at `0x180018576`
- `ntdll!NtReadFile` at `0x18001832f`
- `ntdll!NtReadFile` at `0x1800184af`
- `ntdll!NtReadFile` at `0x18001832f`
- `ntdll!NtReadFile` at `0x1800184af`
- `ntdll!RtlGetThreadErrorMode` at `0x180018205`
- `ntdll!RtlGetThreadErrorMode` at `0x180018205`
- `ntdll!NtOpenFile` at `0x180018282`
- `ntdll!NtOpenFile` at `0x180018282`

## string_xrefs

- `0x180018185`: `CScrubCheckpoint::_ReadCheckpoint`

## pseudocode

```c
__int64 __fastcall CScrubCheckpoint::_ReadCheckpoint(CScrubCheckpoint *this, unsigned __int8 *a2)
{
  USHORT Length; // cx
  unsigned int v5; // ebx
  __int64 v6; // r9
  USHORT v7; // dx
  USHORT v8; // ax
  ULONG ThreadErrorMode; // eax
  NTSTATUS v10; // eax
  NTSTATUS v11; // r14d
  NTSTATUS v12; // ebx
  NTSTATUS v13; // edi
  _QWORD *v14; // rcx
  int v15; // edx
  unsigned int *v16; // rax
  __int64 v17; // r9
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rcx
  const char *v22; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-A8h]
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  int v25; // [rsp+68h] [rbp-98h]
  char v26; // [rsp+6Ch] [rbp-94h]
  ULONG OldMode; // [rsp+70h] [rbp-90h] BYREF
  char v28; // [rsp+74h] [rbp-8Ch]
  __int128 v29; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-78h] BYREF
  USHORT v31; // [rsp+98h] [rbp-68h]
  USHORT v32; // [rsp+9Ah] [rbp-66h]
  int v33; // [rsp+9Ch] [rbp-64h]
  char *v34; // [rsp+A0h] [rbp-60h]
  union _LARGE_INTEGER ByteOffset; // [rsp+A8h] [rbp-58h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+100h] [rbp+0h]

  Length = GlobalIndentString.Length;
  v5 = 1;
  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v22 = "CScrubCheckpoint::_ReadCheckpoint";
  v7 = ++*(_WORD *)(v6 + 8);
  *(_QWORD *)(v6 + 16) = "CScrubCheckpoint::_ReadCheckpoint";
  v8 = Length;
  if ( v7 < Length )
  {
    v8 = v7;
    Length = v7;
  }
  v31 = v8;
  v33 = 0;
  v34 = off_180047060;
  v32 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubCheckpoint::_ReadCheckpoint");
  }
  v28 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
  ObjectAttributes.RootDirectory = (HANDLE)*((_QWORD *)this + 1);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)L"TV";
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  FileHandle = 0;
  v25 = 0;
  v26 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  if ( a2 )
    *a2 = 0;
  v10 = NtOpenFile(&FileHandle, 0x100081u, &ObjectAttributes, &IoStatusBlock, 5u, 0x64u);
  v11 = v10;
  if ( v10 == -1073741766 )
  {
    if ( a2 )
      *a2 = 1;
    goto LABEL_22;
  }
  if ( v10 < 0 )
  {
    if ( a2 && v10 == -1073741772 )
      *a2 = 1;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
        (unsigned int)L"TV",
        v10);
    }
    v12 = v11;
    goto LABEL_21;
  }
  v13 = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, *((PVOID *)this + 5), 0x120u, &LiZero, 0);
  if ( v13 >= 0 )
  {
    if ( IoStatusBlock.Information >= 0x120 )
    {
      v16 = (unsigned int *)*((_QWORD *)this + 5);
      v17 = *v16;
      if ( (_DWORD)v17 == 296 )
      {
        if ( *((_WORD *)v16 + 140) <= 0x200u )
        {
          *((_QWORD *)v16 + 14) = 0;
          v18 = CScrubCheckpoint::_EnsureCheckpointDataLength(this, *(_WORD *)(*((_QWORD *)this + 5) + 280LL));
          v23 = v18;
          if ( v18 < 0 )
          {
            v5 = v18;
            goto LABEL_66;
          }
          v19 = *((_QWORD *)this + 5);
          ByteOffset.QuadPart = 288;
          v13 = NtReadFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  (PVOID)(v19 + 288),
                  *(unsigned __int16 *)(v19 + 280),
                  &ByteOffset,
                  0);
          if ( v13 >= 0 )
          {
            v20 = *((_QWORD *)this + 5);
            v29 = 0;
            WORD1(v29) = *(_WORD *)(v20 + 280);
            LOWORD(v29) = WORD1(v29);
            if ( WORD1(v29) )
              *((_QWORD *)&v29 + 1) = v20 + 288;
            else
              *((_QWORD *)&v29 + 1) = 0;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            {
              WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids, &v29);
            }
            v39 = 0;
            FileInformation = 0;
            v38 = 0;
            v13 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
            if ( v13 >= 0 )
            {
              v5 = 0;
              *((_QWORD *)this + 7) = v38;
              v23 = 0;
              goto LABEL_66;
            }
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_29;
            }
            v15 = 21;
          }
          else
          {
            v14 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_29;
            }
            v15 = 19;
          }
          goto LABEL_28;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
            *((unsigned __int16 *)v16 + 140));
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids, v17, 296);
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
        IoStatusBlock.Information);
    }
    v5 = -2147467259;
    goto LABEL_22;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_29;
  }
  v15 = 15;
LABEL_28:
  WPP_SF_Zd(v14[2], v15, (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids, (unsigned int)L"TV", v13);
LABEL_29:
  v12 = v13;
LABEL_21:
  v5 = v12 | 0x10000000;
LABEL_22:
  v23 = v5;
LABEL_66:
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
  CHResultImp::~CHResultImp((CHResultImp *)&v22);
  return v5;
}

```

## disassembly

```asm
0x180018130  mov     [rsp-8+arg_10], rbx
0x180018135  push    rbp
0x180018136  push    rsi
0x180018137  push    rdi
0x180018138  push    r12
0x18001813a  push    r13
0x18001813c  push    r14
0x18001813e  push    r15
0x180018140  lea     rbp, [rsp-10h]
0x180018145  sub     rsp, 110h
0x18001814c  mov     rax, cs:__security_cookie
0x180018153  xor     rax, rsp
0x180018156  mov     [rbp+40h+var_38], rax
0x18001815a  mov     r8d, cs:_tls_index
0x180018161  mov     rdi, rdx
0x180018164  mov     rax, gs:58h
0x18001816d  mov     rsi, rcx
0x180018170  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180018177  mov     ebx, 1
0x18001817c  mov     edx, 8
0x180018181  mov     r9, [rax+r8*8]
0x180018185  lea     r8, aCscrubcheckpoi_3; "CScrubCheckpoint::_ReadCheckpoint"
0x18001818c  mov     eax, 10h
0x180018191  mov     [rsp+140h+var_F0], r8
0x180018196  add     [rdx+r9], bx
0x18001819b  movzx   edx, word ptr [rdx+r9]
0x1800181a0  mov     [rax+r9], r8
0x1800181a4  cmp     dx, cx
0x1800181a7  movzx   eax, cx
0x1800181aa  cmovb   ax, dx
0x1800181ae  cmovb   cx, dx
0x1800181b2  mov     [rbp+40h+var_A8], ax
0x1800181b6  xor     eax, eax
0x1800181b8  mov     [rbp+40h+var_A4], eax
0x1800181bb  mov     rax, cs:off_180047060; "                                       "...
0x1800181c2  mov     [rbp+40h+var_A0], rax
0x1800181c6  mov     [rbp+40h+var_A6], cx
0x1800181ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800181d1  lea     r12, WPP_GLOBAL_Control
0x1800181d8  cmp     rcx, r12
0x1800181db  jz      short loc_1800181FD
0x1800181dd  test    [rcx+1Ch], bl
0x1800181e0  jz      short loc_1800181FD
0x1800181e2  cmp     byte ptr [rcx+19h], 5
0x1800181e6  jb      short loc_1800181FD
0x1800181e8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800181ec  lea     edx, [rbx+0Ch]
0x1800181ef  lea     r9, [rbp+40h+var_A8]
0x1800181f3  mov     qword ptr [rsp+140h+ShareAccess], r8; __int64
0x1800181f8  call    WPP_SF_aZs
0x1800181fd  xor     r15d, r15d
0x180018200  mov     [rsp+140h+var_CC], r15b
0x180018205  call    cs:__imp_RtlGetThreadErrorMode
0x18001820b  or      eax, 10h
0x18001820e  lea     rcx, [rsp+140h+OldMode]; OldMode
0x180018213  mov     edx, eax; NewMode
0x180018215  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x18001821a  mov     rax, [rsi+8]
0x18001821e  xorps   xmm0, xmm0
0x180018221  mov     [rbp+40h+ObjectAttributes.RootDirectory], rax
0x180018225  lea     r13, ?g_CheckpointFile1Path@@3U_UNICODE_STRING@@B; "TV"
0x18001822c  mov     qword ptr [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x180018234  mov     [rbp+40h+ObjectAttributes.ObjectName], r13
0x180018238  mov     qword ptr [rbp+40h+ObjectAttributes.Attributes], 40h ; '@'
0x180018240  mov     [rsp+140h+FileHandle], r15
0x180018245  mov     [rsp+140h+var_D8], r15d
0x18001824a  mov     [rsp+140h+var_D4], r15b
0x18001824f  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018254  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x180018258  test    rdi, rdi
0x18001825b  jz      short loc_180018260
0x18001825d  mov     [rdi], r15b
0x180018260  mov     [rsp+140h+OpenOptions], 64h ; 'd'; OpenOptions
0x180018268  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x18001826c  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x180018270  mov     [rsp+140h+ShareAccess], 5; ShareAccess
0x180018278  mov     edx, 100081h; DesiredAccess
0x18001827d  lea     rcx, [rsp+140h+FileHandle]; FileHandle
0x180018282  call    cs:__imp_NtOpenFile
0x180018288  mov     r14d, eax
0x18001828b  cmp     eax, 0C000003Ah
0x180018290  jnz     short loc_18001829B
0x180018292  test    rdi, rdi
0x180018295  jz      short loc_1800182EB
0x180018297  mov     [rdi], bl
0x180018299  jmp     short loc_1800182EB
0x18001829b  test    r14d, r14d
0x18001829e  jns     short loc_1800182F4
0x1800182a0  test    rdi, rdi
0x1800182a3  jz      short loc_1800182B0
0x1800182a5  cmp     r14d, 0C0000034h
0x1800182ac  jnz     short loc_1800182B0
0x1800182ae  mov     [rdi], bl
0x1800182b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800182b7  cmp     rcx, r12
0x1800182ba  jz      short loc_1800182E4
0x1800182bc  test    [rcx+1Ch], bl
0x1800182bf  jz      short loc_1800182E4
0x1800182c1  cmp     byte ptr [rcx+19h], 2
0x1800182c5  jb      short loc_1800182E4
0x1800182c7  mov     rcx, [rcx+10h]
0x1800182cb  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x1800182d2  mov     edx, 0Eh
0x1800182d7  mov     [rsp+140h+ShareAccess], r14d
0x1800182dc  mov     r9, r13
0x1800182df  call    WPP_SF_Zd
0x1800182e4  mov     ebx, r14d
0x1800182e7  bts     ebx, 1Ch
0x1800182eb  mov     [rsp+140h+var_E8], ebx
0x1800182ef  jmp     loc_1800185BF
0x1800182f4  mov     rcx, [rsp+140h+FileHandle]; FileHandle
0x1800182f9  lea     rax, ?LiZero@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LiZero
0x180018300  mov     [rsp+140h+Key], r15; Key
0x180018305  mov     r14d, 120h
0x18001830b  mov     [rsp+140h+ByteOffset], rax; ByteOffset
0x180018310  xor     r9d, r9d; ApcContext
0x180018313  mov     rax, [rsi+28h]
0x180018317  xor     r8d, r8d; ApcRoutine
0x18001831a  mov     [rsp+140h+Length], r14d; Length
0x18001831f  xor     edx, edx; Event
0x180018321  mov     qword ptr [rsp+140h+OpenOptions], rax; Buffer
0x180018326  lea     rax, [rbp+40h+IoStatusBlock]
0x18001832a  mov     qword ptr [rsp+140h+ShareAccess], rax; IoStatusBlock
0x18001832f  call    cs:__imp_NtReadFile
0x180018335  mov     edi, eax
0x180018337  test    eax, eax
0x180018339  jns     short loc_180018375
0x18001833b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018342  cmp     rcx, r12
0x180018345  jz      short loc_18001836E
0x180018347  test    [rcx+1Ch], bl
0x18001834a  jz      short loc_18001836E
0x18001834c  cmp     byte ptr [rcx+19h], 2
0x180018350  jb      short loc_18001836E
0x180018352  mov     edx, 0Fh
0x180018357  mov     rcx, [rcx+10h]
0x18001835b  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180018362  mov     r9, r13
0x180018365  mov     [rsp+140h+ShareAccess], edi
0x180018369  call    WPP_SF_Zd
0x18001836e  mov     ebx, edi
0x180018370  jmp     loc_1800182E7
0x180018375  mov     r9, [rbp+40h+IoStatusBlock.Information]
0x180018379  cmp     r9, r14
0x18001837c  jnb     short loc_1800183BB
0x18001837e  mov     rcx, cs:WPP_GLOBAL_Control
0x180018385  cmp     rcx, r12
0x180018388  jz      loc_180018440
0x18001838e  test    [rcx+1Ch], bl
0x180018391  jz      loc_180018440
0x180018397  cmp     byte ptr [rcx+19h], 2
0x18001839b  jb      loc_180018440
0x1800183a1  mov     rcx, [rcx+10h]
0x1800183a5  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x1800183ac  mov     edx, 10h
0x1800183b1  call    WPP_SF_q
0x1800183b6  jmp     loc_180018440
0x1800183bb  mov     rax, [rsi+28h]
0x1800183bf  mov     r8d, 128h
0x1800183c5  mov     r9d, [rax]
0x1800183c8  cmp     r9d, r8d
0x1800183cb  jz      short loc_180018400
0x1800183cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800183d4  cmp     rcx, r12
0x1800183d7  jz      short loc_180018440
0x1800183d9  test    [rcx+1Ch], bl
0x1800183dc  jz      short loc_180018440
0x1800183de  cmp     byte ptr [rcx+19h], 2
0x1800183e2  jb      short loc_180018440
0x1800183e4  mov     rcx, [rcx+10h]
0x1800183e8  mov     edx, 11h
0x1800183ed  mov     [rsp+140h+ShareAccess], r8d
0x1800183f2  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x1800183f9  call    WPP_SF_Dd
0x1800183fe  jmp     short loc_180018440
0x180018400  movzx   edx, word ptr [rax+118h]
0x180018407  mov     ecx, 200h
0x18001840c  cmp     dx, cx
0x18001840f  jbe     short loc_18001844A
0x180018411  mov     rcx, cs:WPP_GLOBAL_Control
0x180018418  cmp     rcx, r12
0x18001841b  jz      short loc_180018440
0x18001841d  test    [rcx+1Ch], bl
0x180018420  jz      short loc_180018440
0x180018422  cmp     byte ptr [rcx+19h], 2
0x180018426  jb      short loc_180018440
0x180018428  mov     rcx, [rcx+10h]
0x18001842c  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180018433  mov     r9d, edx
0x180018436  mov     edx, 12h
0x18001843b  call    WPP_SF_d
0x180018440  mov     ebx, 80004005h
0x180018445  jmp     loc_1800182EB
0x18001844a  mov     [rax+70h], r15
0x18001844e  mov     rcx, rsi; this
0x180018451  mov     rdx, [rsi+28h]
0x180018455  movzx   edx, word ptr [rdx+118h]; unsigned __int16
0x18001845c  call    ?_EnsureCheckpointDataLength@CScrubCheckpoint@@AEAAJG@Z; CScrubCheckpoint::_EnsureCheckpointDataLength(ushort)
0x180018461  mov     [rsp+140h+var_E8], eax
0x180018465  test    eax, eax
0x180018467  jns     short loc_180018470
0x180018469  mov     ebx, eax
0x18001846b  jmp     loc_1800185BF
0x180018470  mov     rax, [rsi+28h]
0x180018474  lea     rcx, [rbp+40h+var_98]
0x180018478  mov     [rsp+140h+Key], r15; Key
0x18001847d  xor     r9d, r9d; ApcContext
0x180018480  mov     [rsp+140h+ByteOffset], rcx; ByteOffset
0x180018485  xor     r8d, r8d; ApcRoutine
0x180018488  mov     rcx, [rsp+140h+FileHandle]; FileHandle
0x18001848d  mov     qword ptr [rbp+40h+var_98], r14
0x180018491  movzx   edx, word ptr [rax+118h]
0x180018498  add     rax, r14
0x18001849b  mov     [rsp+140h+Length], edx; Length
0x18001849f  xor     edx, edx; Event
0x1800184a1  mov     qword ptr [rsp+140h+OpenOptions], rax; Buffer
0x1800184a6  lea     rax, [rbp+40h+IoStatusBlock]
0x1800184aa  mov     qword ptr [rsp+140h+ShareAccess], rax; IoStatusBlock
0x1800184af  call    cs:__imp_NtReadFile
0x1800184b5  mov     edi, eax
0x1800184b7  test    eax, eax
0x1800184b9  jns     short loc_1800184E8
0x1800184bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800184c2  cmp     rcx, r12
0x1800184c5  jz      loc_18001836E
0x1800184cb  test    [rcx+1Ch], bl
0x1800184ce  jz      loc_18001836E
0x1800184d4  cmp     byte ptr [rcx+19h], 2
0x1800184d8  jb      loc_18001836E
0x1800184de  mov     edx, 13h
0x1800184e3  jmp     loc_180018357
0x1800184e8  mov     rcx, [rsi+28h]
0x1800184ec  xorps   xmm0, xmm0
0x1800184ef  movups  [rsp+140h+var_C8], xmm0
0x1800184f4  movzx   eax, word ptr [rcx+118h]
0x1800184fb  mov     word ptr [rsp+140h+var_C8+2], ax
0x180018500  mov     word ptr [rsp+140h+var_C8], ax
0x180018505  test    ax, ax
0x180018508  jz      short loc_180018517
0x18001850a  lea     rax, [rcx+120h]
0x180018511  mov     qword ptr [rbp+40h+var_C8+8], rax
0x180018515  jmp     short loc_18001851B
0x180018517  mov     qword ptr [rbp+40h+var_C8+8], r15
0x18001851b  mov     rcx, cs:WPP_GLOBAL_Control
0x180018522  cmp     rcx, r12
0x180018525  jz      short loc_18001854C
0x180018527  test    [rcx+1Ch], bl
0x18001852a  jz      short loc_18001854C
0x18001852c  cmp     byte ptr [rcx+19h], 4
0x180018530  jb      short loc_18001854C
0x180018532  mov     rcx, [rcx+10h]
0x180018536  lea     r9, [rsp+140h+var_C8]
0x18001853b  mov     edx, 14h
0x180018540  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180018547  call    WPP_SF_Z
0x18001854c  mov     rcx, [rsp+140h+FileHandle]; FileHandle
0x180018551  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x180018555  xor     eax, eax
0x180018557  mov     [rsp+140h+ShareAccess], 4; FileInformationClass
0x18001855f  xorps   xmm0, xmm0
0x180018562  mov     [rbp+40h+var_40], rax
0x180018566  lea     rdx, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x18001856a  movups  [rbp+40h+FileInformation], xmm0
0x18001856e  lea     r9d, [rax+28h]; Length
0x180018572  movups  [rbp+40h+var_50], xmm0
0x180018576  call    cs:__imp_NtQueryInformationFile
0x18001857c  mov     edi, eax
0x18001857e  test    eax, eax
0x180018580  jns     short loc_1800185AF
0x180018582  mov     rcx, cs:WPP_GLOBAL_Control
0x180018589  cmp     rcx, r12
0x18001858c  jz      loc_18001836E
0x180018592  test    [rcx+1Ch], bl
0x180018595  jz      loc_18001836E
0x18001859b  cmp     byte ptr [rcx+19h], 2
0x18001859f  jb      loc_18001836E
0x1800185a5  mov     edx, 15h
0x1800185aa  jmp     loc_180018357
0x1800185af  mov     rax, qword ptr [rbp+40h+var_50]
0x1800185b3  mov     ebx, r15d
0x1800185b6  mov     [rsi+38h], rax
0x1800185ba  mov     [rsp+140h+var_E8], r15d
0x1800185bf  lea     rcx, [rsp+140h+FileHandle]
0x1800185c4  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800185c9  lea     rcx, [rsp+140h+OldMode]; this
0x1800185ce  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x1800185d3  lea     rcx, [rsp+140h+var_F0]; this
0x1800185d8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800185dd  mov     eax, ebx
0x1800185df  mov     rcx, [rbp+40h+var_38]
0x1800185e3  xor     rcx, rsp; StackCookie
0x1800185e6  call    __security_check_cookie
0x1800185eb  mov     rbx, [rsp+140h+arg_10]
0x1800185f3  add     rsp, 110h
0x1800185fa  pop     r15
0x1800185fc  pop     r14
0x1800185fe  pop     r13
0x180018600  pop     r12
0x180018602  pop     rdi
0x180018603  pop     rsi
  ... truncated ...
```
