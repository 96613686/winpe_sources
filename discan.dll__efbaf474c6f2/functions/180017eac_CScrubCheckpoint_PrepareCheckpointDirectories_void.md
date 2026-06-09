# CScrubCheckpoint::_PrepareCheckpointDirectories(void)

- ea: `0x180017eac`
- end: `0x180018127`
- name: `?_PrepareCheckpointDirectories@CScrubCheckpoint@@AEAAJXZ`
- size: `635`
- prototype: `__int64 __fastcall(PCUNICODE_STRING *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001860c`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x18000891c`
- `0x180010160`
- `0x1800129b0`
- `0x180017eac`
- `0x1800188f4`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18001809a`
- `ntdll!NtCreateFile` at `0x18001809a`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180017f85`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180017f85`
- `ntdll!RtlGetThreadErrorMode` at `0x180017f6e`
- `ntdll!RtlGetThreadErrorMode` at `0x180017f6e`
- `ntdll!NtOpenFile` at `0x180018031`
- `ntdll!NtOpenFile` at `0x180018031`

## pseudocode

```c
__int64 __fastcall CScrubCheckpoint::_PrepareCheckpointDirectories(PCUNICODE_STRING *this)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // r8
  USHORT v5; // ax
  ULONG ThreadErrorMode; // eax
  NTSTATUS SystemVolumeInformationFolder; // eax
  NTSTATUS v8; // ebx
  unsigned int v9; // ebx
  UNICODE_STRING *v10; // rax
  NTSTATUS v11; // eax
  NTSTATUS v12; // ebx
  const char *v14; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v15; // [rsp+68h] [rbp-21h]
  void *FileHandle; // [rsp+70h] [rbp-19h] BYREF
  char *v17; // [rsp+78h] [rbp-11h]
  void *v18; // [rsp+80h] [rbp-9h] BYREF
  int v19; // [rsp+88h] [rbp-1h]
  char v20; // [rsp+8Ch] [rbp+3h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+17h] BYREF
  ULONG OldMode; // [rsp+F0h] [rbp+67h] BYREF
  char v24; // [rsp+F4h] [rbp+6Bh]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v14 = "CScrubCheckpoint::_PrepareCheckpointDirectories";
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "CScrubCheckpoint::_PrepareCheckpointDirectories";
  v5 = Length;
  if ( ++*(_WORD *)(v4 + 8) < Length )
  {
    v5 = *(_WORD *)(v4 + 8);
    Length = v5;
  }
  LOWORD(FileHandle) = v5;
  HIDWORD(FileHandle) = 0;
  v17 = off_180047060;
  WORD1(FileHandle) = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubCheckpoint::_PrepareCheckpointDirectories");
  }
  v24 = 0;
  IoStatusBlock = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
  SystemVolumeInformationFolder = RtlCreateSystemVolumeInformationFolder(*this);
  v8 = SystemVolumeInformationFolder;
  if ( SystemVolumeInformationFolder >= 0 )
  {
    v10 = (UNICODE_STRING *)this[1];
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"@B";
    ObjectAttributes.RootDirectory = v10;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileHandle = 0;
    LODWORD(v17) = 0;
    BYTE4(v17) = 0;
    NtOpenFile(&FileHandle, 0x10000u, &ObjectAttributes, &IoStatusBlock, 7u, 0x1060u);
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v11 = NtCreateFile(&v18, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0x21u, 0, 0);
    v12 = v11;
    if ( v11 >= 0 )
    {
      v15 = 0;
      v9 = 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_ZZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
          *this,
          L"@B",
          v11);
      }
      v9 = v12 | 0x10000000;
      v15 = v9;
    }
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&v18);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
        (unsigned int)*this,
        SystemVolumeInformationFolder);
    }
    v9 = v8 | 0x10000000;
    v15 = v9;
  }
  CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
  CHResultImp::~CHResultImp((CHResultImp *)&v14);
  return v9;
}

```

## disassembly

```asm
0x180017eac  mov     [rsp-8+arg_8], rbx
0x180017eb1  mov     [rsp-8+arg_10], rdi
0x180017eb6  push    rbp
0x180017eb7  push    r12
0x180017eb9  push    r15
0x180017ebb  lea     rbp, [rsp-47h]
0x180017ec0  sub     rsp, 0D0h
0x180017ec7  mov     edx, cs:_tls_index
0x180017ecd  lea     r9, aCscrubcheckpoi_0; "CScrubCheckpoint::_PrepareCheckpointDir"...
0x180017ed4  mov     rax, gs:58h
0x180017edd  mov     rdi, rcx
0x180017ee0  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180017ee7  mov     [rbp+57h+var_80], r9
0x180017eeb  mov     r8, [rax+rdx*8]
0x180017eef  mov     eax, 10h
0x180017ef4  mov     edx, 8
0x180017ef9  mov     [rax+r8], r9
0x180017efd  movzx   eax, cx
0x180017f00  inc     word ptr [rdx+r8]
0x180017f05  movzx   edx, word ptr [rdx+r8]
0x180017f0a  cmp     dx, cx
0x180017f0d  cmovb   ax, dx
0x180017f11  cmovb   cx, dx
0x180017f15  mov     word ptr [rbp+57h+FileHandle], ax
0x180017f19  xor     eax, eax
0x180017f1b  mov     dword ptr [rbp+57h+FileHandle+4], eax
0x180017f1e  mov     rax, cs:off_180047060; "                                       "...
0x180017f25  mov     [rbp+57h+var_68], rax
0x180017f29  mov     word ptr [rbp+57h+FileHandle+2], cx
0x180017f2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f34  lea     r15, WPP_GLOBAL_Control
0x180017f3b  cmp     rcx, r15
0x180017f3e  jz      short loc_180017F63
0x180017f40  test    byte ptr [rcx+1Ch], 1
0x180017f44  jz      short loc_180017F63
0x180017f46  cmp     byte ptr [rcx+19h], 5
0x180017f4a  jb      short loc_180017F63
0x180017f4c  mov     rcx, [rcx+10h]; LoggerHandle
0x180017f50  mov     edx, 0Dh
0x180017f55  mov     qword ptr [rsp+0E0h+ShareAccess], r9; __int64
0x180017f5a  lea     r9, [rbp+57h+FileHandle]
0x180017f5e  call    WPP_SF_aZs
0x180017f63  xorps   xmm0, xmm0
0x180017f66  mov     [rbp+57h+arg_4], 0
0x180017f6a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180017f6e  call    cs:__imp_RtlGetThreadErrorMode
0x180017f74  or      eax, 10h
0x180017f77  lea     rcx, [rbp+57h+OldMode]; OldMode
0x180017f7b  mov     edx, eax; NewMode
0x180017f7d  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x180017f82  mov     rcx, [rdi]; VolumeRootPath
0x180017f85  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x180017f8b  mov     ebx, eax
0x180017f8d  test    eax, eax
0x180017f8f  jns     short loc_180017FD1
0x180017f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180017f98  cmp     rcx, r15
0x180017f9b  jz      short loc_180017FC5
0x180017f9d  test    byte ptr [rcx+1Ch], 1
0x180017fa1  jz      short loc_180017FC5
0x180017fa3  cmp     byte ptr [rcx+19h], 2
0x180017fa7  jb      short loc_180017FC5
0x180017fa9  mov     r9, [rdi]
0x180017fac  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180017fb3  mov     rcx, [rcx+10h]
0x180017fb7  mov     edx, 16h
0x180017fbc  mov     [rsp+0E0h+ShareAccess], eax
0x180017fc0  call    WPP_SF_Zd
0x180017fc5  bts     ebx, 1Ch
0x180017fc9  mov     [rbp+57h+var_78], ebx
0x180017fcc  jmp     loc_1800180FA
0x180017fd1  mov     rax, [rdi+8]
0x180017fd5  lea     r12, ?g_CheckpointDirectory@@3U_UNICODE_STRING@@B; "@B"
0x180017fdc  xorps   xmm0, xmm0
0x180017fdf  mov     [rsp+0E0h+OpenOptions], 1060h; OpenOptions
0x180017fe7  mov     ebx, 7
0x180017fec  mov     [rbp+57h+ObjectAttributes.ObjectName], r12
0x180017ff0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180017ff4  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x180017ff8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180017ffc  mov     [rsp+0E0h+ShareAccess], ebx; ShareAccess
0x180018000  mov     edx, 10000h; DesiredAccess
0x180018005  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001800d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180018011  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180018019  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001801e  mov     [rbp+57h+FileHandle], 0
0x180018026  mov     dword ptr [rbp+57h+var_68], 0
0x18001802d  mov     byte ptr [rbp+57h+var_68+4], 0
0x180018031  call    cs:__imp_NtOpenFile
0x180018037  lea     rcx, [rbp+57h+FileHandle]
0x18001803b  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180018040  mov     [rsp+0E0h+EaLength], 0; EaLength
0x180018048  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001804c  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x180018055  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180018059  mov     [rsp+0E0h+CreateOptions], 21h ; '!'; CreateOptions
0x180018061  lea     rcx, [rbp+57h+var_60]; FileHandle
0x180018065  mov     [rsp+0E0h+CreateDisposition], 3; CreateDisposition
0x18001806d  mov     edx, 100000h; DesiredAccess
0x180018072  mov     [rsp+0E0h+var_B0], ebx; ShareAccess
0x180018076  mov     [rsp+0E0h+OpenOptions], 80h; FileAttributes
0x18001807e  mov     qword ptr [rsp+0E0h+ShareAccess], 0; AllocationSize
0x180018087  mov     [rbp+57h+var_60], 0
0x18001808f  mov     [rbp+57h+var_58], 0
0x180018096  mov     [rbp+57h+var_54], 0
0x18001809a  call    cs:__imp_NtCreateFile
0x1800180a0  mov     ebx, eax
0x1800180a2  test    eax, eax
0x1800180a4  jns     short loc_1800180E8
0x1800180a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800180ad  cmp     rcx, r15
0x1800180b0  jz      short loc_1800180DF
0x1800180b2  test    byte ptr [rcx+1Ch], 1
0x1800180b6  jz      short loc_1800180DF
0x1800180b8  cmp     byte ptr [rcx+19h], 2
0x1800180bc  jb      short loc_1800180DF
0x1800180be  mov     r9, [rdi]
0x1800180c1  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x1800180c8  mov     rcx, [rcx+10h]
0x1800180cc  mov     edx, 17h
0x1800180d1  mov     [rsp+0E0h+OpenOptions], eax
0x1800180d5  mov     qword ptr [rsp+0E0h+ShareAccess], r12
0x1800180da  call    WPP_SF_ZZd
0x1800180df  bts     ebx, 1Ch
0x1800180e3  mov     [rbp+57h+var_78], ebx
0x1800180e6  jmp     short loc_1800180F1
0x1800180e8  mov     [rbp+57h+var_78], 0
0x1800180ef  xor     ebx, ebx
0x1800180f1  lea     rcx, [rbp+57h+var_60]
0x1800180f5  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800180fa  lea     rcx, [rbp+57h+OldMode]; this
0x1800180fe  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x180018103  lea     rcx, [rbp+57h+var_80]; this
0x180018107  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001810c  lea     r11, [rsp+0E0h+var_10]
0x180018114  mov     eax, ebx
0x180018116  mov     rbx, [r11+28h]
0x18001811a  mov     rdi, [r11+30h]
0x18001811e  mov     rsp, r11
0x180018121  pop     r15
0x180018123  pop     r12
0x180018125  pop     rbp
0x180018126  retn
```
