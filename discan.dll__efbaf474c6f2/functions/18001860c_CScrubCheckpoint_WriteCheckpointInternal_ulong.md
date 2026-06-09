# CScrubCheckpoint::_WriteCheckpointInternal(ulong)

- ea: `0x18001860c`
- end: `0x1800188eb`
- name: `?_WriteCheckpointInternal@CScrubCheckpoint@@AEAAJK@Z`
- size: `735`
- prototype: `__int64 __fastcall(CScrubCheckpoint *this, char)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180017698`
- `0x180017a80`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800088a4`
- `0x18000891c`
- `0x180010160`
- `0x1800129b0`
- `0x180017eac`
- `0x18001860c`

## import_xrefs

- `ntdll!NtWriteFile` at `0x180018877`
- `ntdll!NtWriteFile` at `0x180018877`
- `ntdll!NtCreateFile` at `0x1800187d6`
- `ntdll!NtCreateFile` at `0x1800187d6`
- `ntdll!RtlGetThreadErrorMode` at `0x180018727`
- `ntdll!RtlGetThreadErrorMode` at `0x180018727`

## string_xrefs

- `0x180018655`: `CScrubCheckpoint::_WriteCheckpointInternal`

## pseudocode

```c
__int64 __fastcall CScrubCheckpoint::_WriteCheckpointInternal(CScrubCheckpoint *this, char a2)
{
  USHORT Length; // cx
  __int64 v5; // r9
  USHORT v6; // dx
  USHORT v7; // ax
  int v8; // edi
  int v9; // eax
  unsigned int v10; // ebx
  ULONG ThreadErrorMode; // eax
  NTSTATUS v12; // ebx
  _QWORD *v13; // rcx
  int v14; // edx
  void *FileHandle; // [rsp+60h] [rbp-39h] BYREF
  int v17; // [rsp+68h] [rbp-31h]
  char v18; // [rsp+6Ch] [rbp-2Dh]
  const char *v19; // [rsp+70h] [rbp-29h] BYREF
  unsigned int v20; // [rsp+78h] [rbp-21h]
  USHORT v21; // [rsp+80h] [rbp-19h]
  USHORT v22; // [rsp+82h] [rbp-17h]
  int v23; // [rsp+84h] [rbp-15h]
  char *v24; // [rsp+88h] [rbp-11h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+7h] BYREF
  ULONG OldMode; // [rsp+110h] [rbp+77h] BYREF
  char v28; // [rsp+114h] [rbp+7Bh]
  union _LARGE_INTEGER AllocationSize; // [rsp+118h] [rbp+7Fh] BYREF

  Length = GlobalIndentString.Length;
  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  v19 = "CScrubCheckpoint::_WriteCheckpointInternal";
  v6 = ++*(_WORD *)(v5 + 8);
  *(_QWORD *)(v5 + 16) = "CScrubCheckpoint::_WriteCheckpointInternal";
  v7 = Length;
  if ( v6 < Length )
  {
    v7 = v6;
    Length = v6;
  }
  v21 = v7;
  v23 = 0;
  v24 = off_180047060;
  v22 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubCheckpoint::_WriteCheckpointInternal");
  }
  v8 = a2 & 1;
  if ( v8
    || (v9 = CScrubCheckpoint::_PrepareCheckpointDirectories((PCUNICODE_STRING *)this), v20 = v9, v10 = v9, v9 >= 0) )
  {
    v28 = 0;
    ThreadErrorMode = RtlGetThreadErrorMode();
    CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
    ObjectAttributes.RootDirectory = (HANDLE)*((_QWORD *)this + 1);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)L"TV";
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    FileHandle = 0;
    v17 = 0;
    v18 = 0;
    IoStatusBlock = 0;
    AllocationSize.QuadPart = 0x20000;
    v12 = NtCreateFile(
            &FileHandle,
            0x100002u,
            &ObjectAttributes,
            &IoStatusBlock,
            &AllocationSize,
            0x80u,
            5u,
            2 * (v8 ^ 1) + 1,
            0x64u,
            0,
            0);
    if ( v12 >= 0 )
    {
      v12 = NtWriteFile(
              FileHandle,
              0,
              0,
              0,
              &IoStatusBlock,
              *((PVOID *)this + 5),
              *(unsigned __int16 *)(*((_QWORD *)this + 5) + 280LL) + 288,
              &LiZero,
              0);
      if ( v12 >= 0 )
      {
        v20 = 0;
        CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
        CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
        v10 = 0;
        goto LABEL_26;
      }
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v14 = 29;
    }
    else
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_19;
      }
      v14 = 28;
    }
    WPP_SF_Zd(v13[2], v14, (unsigned int)&WPP_50cd40487cfb379966d33e670ff2d168_Traceguids, (unsigned int)L"TV", v12);
LABEL_19:
    v10 = v12 | 0x10000000;
    v20 = v10;
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
    goto LABEL_26;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      27,
      &WPP_50cd40487cfb379966d33e670ff2d168_Traceguids,
      (unsigned int)v9);
  }
LABEL_26:
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v10;
}

```

## disassembly

```asm
0x18001860c  mov     [rsp-8+arg_0], rbx
0x180018611  mov     [rsp-8+arg_8], rsi
0x180018616  push    rbp
0x180018617  push    rdi
0x180018618  push    r12
0x18001861a  push    r13
0x18001861c  push    r15
0x18001861e  lea     rbp, [rsp-37h]
0x180018623  sub     rsp, 0D0h
0x18001862a  mov     r8d, cs:_tls_index
0x180018631  mov     edi, edx
0x180018633  mov     rax, gs:58h
0x18001863c  mov     rsi, rcx
0x18001863f  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180018646  mov     r15d, 1
0x18001864c  mov     edx, 8
0x180018651  mov     r9, [rax+r8*8]
0x180018655  lea     r8, aCscrubcheckpoi_2; "CScrubCheckpoint::_WriteCheckpointInter"...
0x18001865c  mov     eax, 10h
0x180018661  mov     [rbp+57h+var_80], r8
0x180018665  add     [rdx+r9], r15w
0x18001866a  movzx   edx, word ptr [rdx+r9]
0x18001866f  mov     [rax+r9], r8
0x180018673  cmp     dx, cx
0x180018676  movzx   eax, cx
0x180018679  cmovb   ax, dx
0x18001867d  cmovb   cx, dx
0x180018681  mov     [rbp+57h+var_70], ax
0x180018685  xor     eax, eax
0x180018687  mov     [rbp+57h+var_6C], eax
0x18001868a  mov     rax, cs:off_180047060; "                                       "...
0x180018691  mov     [rbp+57h+var_68], rax
0x180018695  mov     [rbp+57h+var_6E], cx
0x180018699  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186a0  lea     r12, WPP_GLOBAL_Control
0x1800186a7  cmp     rcx, r12
0x1800186aa  jz      short loc_1800186CE
0x1800186ac  test    [rcx+1Ch], r15b
0x1800186b0  jz      short loc_1800186CE
0x1800186b2  cmp     byte ptr [rcx+19h], 5
0x1800186b6  jb      short loc_1800186CE
0x1800186b8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800186bc  lea     edx, [r15+0Ch]
0x1800186c0  lea     r9, [rbp+57h+var_70]
0x1800186c4  mov     [rsp+0F0h+AllocationSize], r8; __int64
0x1800186c9  call    WPP_SF_aZs
0x1800186ce  and     edi, r15d
0x1800186d1  jnz     short loc_180018723
0x1800186d3  mov     rcx, rsi; this
0x1800186d6  call    ?_PrepareCheckpointDirectories@CScrubCheckpoint@@AEAAJXZ; CScrubCheckpoint::_PrepareCheckpointDirectories(void)
0x1800186db  mov     [rbp+57h+var_78], eax
0x1800186de  mov     ebx, eax
0x1800186e0  test    eax, eax
0x1800186e2  jns     short loc_180018723
0x1800186e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800186eb  cmp     rcx, r12
0x1800186ee  jz      loc_1800188C4
0x1800186f4  test    [rcx+1Ch], r15b
0x1800186f8  jz      loc_1800188C4
0x1800186fe  cmp     byte ptr [rcx+19h], 2
0x180018702  jb      loc_1800188C4
0x180018708  mov     rcx, [rcx+10h]
0x18001870c  lea     edx, [rdi+1Bh]
0x18001870f  mov     r9d, eax
0x180018712  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x180018719  call    WPP_SF_d
0x18001871e  jmp     loc_1800188C4
0x180018723  mov     [rbp+57h+arg_14], 0
0x180018727  call    cs:__imp_RtlGetThreadErrorMode
0x18001872d  or      eax, 10h
0x180018730  lea     rcx, [rbp+57h+OldMode]; OldMode
0x180018734  mov     edx, eax; NewMode
0x180018736  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x18001873b  mov     rax, [rsi+8]
0x18001873f  lea     r13, ?g_CheckpointFile1Path@@3U_UNICODE_STRING@@B; "TV"
0x180018746  mov     [rsp+0F0h+EaLength], 0; EaLength
0x18001874e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180018752  mov     [rsp+0F0h+EaBuffer], 0; EaBuffer
0x18001875b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001875f  mov     [rsp+0F0h+CreateOptions], 64h ; 'd'; CreateOptions
0x180018767  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001876b  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001876f  xorps   xmm0, xmm0
0x180018772  xor     edi, r15d
0x180018775  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001877d  mov     edx, 100002h; DesiredAccess
0x180018782  mov     [rbp+57h+ObjectAttributes.ObjectName], r13
0x180018786  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001878e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180018793  lea     eax, ds:1[rdi*2]
0x18001879a  mov     [rbp+57h+FileHandle], 0
0x1800187a2  mov     [rsp+0F0h+CreateDisposition], eax; CreateDisposition
0x1800187a6  lea     rax, [rbp+57h+arg_18]
0x1800187aa  mov     [rsp+0F0h+ShareAccess], 5; ShareAccess
0x1800187b2  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x1800187ba  mov     [rsp+0F0h+AllocationSize], rax; AllocationSize
0x1800187bf  mov     [rbp+57h+var_88], 0
0x1800187c6  mov     [rbp+57h+var_84], 0
0x1800187ca  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800187ce  mov     qword ptr [rbp+57h+arg_18], 20000h
0x1800187d6  call    cs:__imp_NtCreateFile
0x1800187dc  mov     ebx, eax
0x1800187de  test    eax, eax
0x1800187e0  jns     short loc_180018834
0x1800187e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800187e9  cmp     rcx, r12
0x1800187ec  jz      short loc_180018816
0x1800187ee  test    [rcx+1Ch], r15b
0x1800187f2  jz      short loc_180018816
0x1800187f4  cmp     byte ptr [rcx+19h], 2
0x1800187f8  jb      short loc_180018816
0x1800187fa  mov     edx, 1Ch
0x1800187ff  mov     rcx, [rcx+10h]
0x180018803  lea     r8, WPP_50cd40487cfb379966d33e670ff2d168_Traceguids
0x18001880a  mov     r9, r13
0x18001880d  mov     dword ptr [rsp+0F0h+AllocationSize], ebx
0x180018811  call    WPP_SF_Zd
0x180018816  bts     ebx, 1Ch
0x18001881a  lea     rcx, [rbp+57h+FileHandle]
0x18001881e  mov     [rbp+57h+var_78], ebx
0x180018821  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180018826  lea     rcx, [rbp+57h+OldMode]; this
0x18001882a  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x18001882f  jmp     loc_1800188C4
0x180018834  mov     rdx, [rsi+28h]
0x180018838  lea     rcx, ?LiZero@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LiZero
0x18001883f  mov     qword ptr [rsp+0F0h+CreateOptions], 0; Key
0x180018848  xor     r9d, r9d; ApcContext
0x18001884b  mov     qword ptr [rsp+0F0h+CreateDisposition], rcx; ByteOffset
0x180018850  xor     r8d, r8d; ApcRoutine
0x180018853  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180018857  movzx   eax, word ptr [rdx+118h]
0x18001885e  add     eax, 120h
0x180018863  mov     [rsp+0F0h+ShareAccess], eax; Length
0x180018867  lea     rax, [rbp+57h+IoStatusBlock]
0x18001886b  mov     qword ptr [rsp+0F0h+FileAttributes], rdx; Buffer
0x180018870  xor     edx, edx; Event
0x180018872  mov     [rsp+0F0h+AllocationSize], rax; IoStatusBlock
0x180018877  call    cs:__imp_NtWriteFile
0x18001887d  mov     ebx, eax
0x18001887f  test    eax, eax
0x180018881  jns     short loc_1800188A9
0x180018883  mov     rcx, cs:WPP_GLOBAL_Control
0x18001888a  cmp     rcx, r12
0x18001888d  jz      short loc_180018816
0x18001888f  test    [rcx+1Ch], r15b
0x180018893  jz      short loc_180018816
0x180018895  cmp     byte ptr [rcx+19h], 2
0x180018899  jb      loc_180018816
0x18001889f  mov     edx, 1Dh
0x1800188a4  jmp     loc_1800187FF
0x1800188a9  lea     rcx, [rbp+57h+FileHandle]
0x1800188ad  mov     [rbp+57h+var_78], 0
0x1800188b4  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800188b9  lea     rcx, [rbp+57h+OldMode]; this
0x1800188bd  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x1800188c2  xor     ebx, ebx
0x1800188c4  lea     rcx, [rbp+57h+var_80]; this
0x1800188c8  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800188cd  lea     r11, [rsp+0F0h+var_20]
0x1800188d5  mov     eax, ebx
0x1800188d7  mov     rbx, [r11+30h]
0x1800188db  mov     rsi, [r11+38h]
0x1800188df  mov     rsp, r11
0x1800188e2  pop     r15
0x1800188e4  pop     r13
0x1800188e6  pop     r12
0x1800188e8  pop     rdi
0x1800188e9  pop     rbp
0x1800188ea  retn
```
