# CScrubJetNameTable::SetupSystemVolumeInformation(_UNICODE_STRING const *)

- ea: `0x180030fc0`
- end: `0x18003132c`
- name: `?SetupSystemVolumeInformation@CScrubJetNameTable@@SAJPEBU_UNICODE_STRING@@@Z`
- size: `876`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e49c`
- `0x180024b24`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800088a4`
- `0x18000893c`
- `0x1800129b0`
- `0x180030fc0`

## import_xrefs

- `msvcrt!free` at `0x18003129b`
- `msvcrt!free` at `0x1800312f7`
- `msvcrt!free` at `0x18003129b`
- `msvcrt!free` at `0x1800312f7`
- `ntdll!NtCreateFile` at `0x1800311c1`
- `ntdll!NtCreateFile` at `0x1800311c1`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180031080`
- `ntdll!RtlCreateSystemVolumeInformationFolder` at `0x180031080`
- `ntdll!NtClose` at `0x180031248`
- `ntdll!NtClose` at `0x180031248`
- `ntdll!NtFsControlFile` at `0x18003121b`
- `ntdll!NtFsControlFile` at `0x18003121b`

## pseudocode

```c
__int64 __fastcall CScrubJetNameTable::SetupSystemVolumeInformation(struct _UNICODE_STRING *a1)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v4; // r8
  USHORT v5; // ax
  NTSTATUS SystemVolumeInformationFolder; // eax
  NTSTATUS v7; // ebx
  unsigned int v8; // ebx
  int v9; // eax
  char v10; // si
  ACCESS_MASK v11; // edi
  NTSTATUS v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // eax
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  int v17; // [rsp+68h] [rbp-51h]
  char v18; // [rsp+6Ch] [rbp-4Dh]
  const char *v19; // [rsp+70h] [rbp-49h] BYREF
  unsigned int v20; // [rsp+78h] [rbp-41h]
  USHORT v21; // [rsp+80h] [rbp-39h]
  USHORT v22; // [rsp+82h] [rbp-37h]
  int v23; // [rsp+84h] [rbp-35h]
  char *v24; // [rsp+88h] [rbp-31h]
  struct _UNICODE_STRING v25; // [rsp+90h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  void *Block; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 InputBuffer; // [rsp+130h] [rbp+77h] BYREF

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v19 = "CScrubJetNameTable::SetupSystemVolumeInformation";
  v4 = ThreadLocalStoragePointer[tls_index];
  *(_QWORD *)(v4 + 16) = "CScrubJetNameTable::SetupSystemVolumeInformation";
  v5 = Length;
  if ( ++*(_WORD *)(v4 + 8) < Length )
  {
    v5 = *(_WORD *)(v4 + 8);
    Length = v5;
  }
  v21 = v5;
  v23 = 0;
  v24 = off_180047060;
  v22 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrubJetNameTable::SetupSystemVolumeInformation");
  }
  SystemVolumeInformationFolder = RtlCreateSystemVolumeInformationFolder(a1);
  v7 = SystemVolumeInformationFolder;
  if ( SystemVolumeInformationFolder >= 0 )
  {
    FileHandle = 0;
    v17 = 0;
    v18 = 0;
    Block = 0;
    v25 = 0;
    v9 = CopyUnicodeStringToBuffer(a1, (struct _UNICODE_STRING *)&DiscanJetDatabaseDirectory, 0, &v25, (__int64)&Block);
    v20 = v9;
    v8 = v9;
    if ( v9 >= 0 )
    {
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &v25;
      v10 = 1;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      v11 = 1966083;
      IoStatusBlock = 0;
      while ( 1 )
      {
        v12 = NtCreateFile(&FileHandle, v11, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0x21u, 0, 0);
        v13 = v12;
        if ( v12 < 0 )
          break;
        if ( !v10 )
        {
          v20 = 0;
          free(Block);
          CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
          CHResultImp::~CHResultImp((CHResultImp *)&v19);
          return 0;
        }
        InputBuffer = 1;
        v14 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x9C280u, &InputBuffer, 8u, 0, 0);
        v13 = v14;
        if ( ((v14 + 0x80000000) & 0x80000000) == 0 && v14 != -1073741808 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids, v14);
          }
          goto LABEL_37;
        }
        if ( FileHandle && (!v18 || !v17) )
        {
          NtClose(FileHandle);
          FileHandle = 0;
          v18 = 0;
        }
        v11 &= 0xFFFFFFFC;
        v10 = 0;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids,
          (unsigned int)&v25,
          v12);
      }
LABEL_37:
      v8 = v13 | 0x10000000;
      v20 = v8;
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids,
        (unsigned int)v9);
    }
    free(Block);
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        (unsigned int)WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids,
        (_DWORD)a1,
        SystemVolumeInformationFolder);
    }
    v8 = v7 | 0x10000000;
    v20 = v8;
  }
  CHResultImp::~CHResultImp((CHResultImp *)&v19);
  return v8;
}

```

## disassembly

```asm
0x180030fc0  mov     [rsp-8+arg_0], rbx
0x180030fc5  push    rbp
0x180030fc6  push    rsi
0x180030fc7  push    rdi
0x180030fc8  push    r12
0x180030fca  push    r13
0x180030fcc  push    r14
0x180030fce  push    r15
0x180030fd0  lea     rbp, [rsp-27h]
0x180030fd5  sub     rsp, 0E0h
0x180030fdc  mov     edx, cs:_tls_index
0x180030fe2  lea     r9, aCscrubjetnamet; "CScrubJetNameTable::SetupSystemVolumeIn"...
0x180030fe9  mov     rax, gs:58h
0x180030ff2  mov     rdi, rcx
0x180030ff5  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180030ffc  mov     r15d, 1
0x180031002  mov     [rbp+57h+var_A0], r9
0x180031006  mov     r8, [rax+rdx*8]
0x18003100a  mov     eax, 10h
0x18003100f  mov     edx, 8
0x180031014  mov     [rax+r8], r9
0x180031018  movzx   eax, cx
0x18003101b  add     [rdx+r8], r15w
0x180031020  movzx   edx, word ptr [rdx+r8]
0x180031025  cmp     dx, cx
0x180031028  cmovb   ax, dx
0x18003102c  cmovb   cx, dx
0x180031030  mov     [rbp+57h+var_90], ax
0x180031034  xor     eax, eax
0x180031036  mov     [rbp+57h+var_8C], eax
0x180031039  mov     rax, cs:off_180047060; "                                       "...
0x180031040  mov     [rbp+57h+var_88], rax
0x180031044  mov     [rbp+57h+var_8E], cx
0x180031048  mov     rcx, cs:WPP_GLOBAL_Control
0x18003104f  lea     r12, WPP_GLOBAL_Control
0x180031056  cmp     rcx, r12
0x180031059  jz      short loc_18003107D
0x18003105b  test    [rcx+1Ch], r15b
0x18003105f  jz      short loc_18003107D
0x180031061  cmp     byte ptr [rcx+19h], 5
0x180031065  jb      short loc_18003107D
0x180031067  mov     rcx, [rcx+10h]; LoggerHandle
0x18003106b  lea     edx, [r15+0Ch]
0x18003106f  mov     [rsp+110h+AllocationSize], r9; __int64
0x180031074  lea     r9, [rbp+57h+var_90]
0x180031078  call    WPP_SF_aZs
0x18003107d  mov     rcx, rdi; VolumeRootPath
0x180031080  call    cs:__imp_RtlCreateSystemVolumeInformationFolder
0x180031086  xor     r14d, r14d
0x180031089  mov     ebx, eax
0x18003108b  test    eax, eax
0x18003108d  jns     short loc_1800310CE
0x18003108f  mov     rcx, cs:WPP_GLOBAL_Control
0x180031096  cmp     rcx, r12
0x180031099  jz      short loc_1800310C2
0x18003109b  test    [rcx+1Ch], r15b
0x18003109f  jz      short loc_1800310C2
0x1800310a1  cmp     byte ptr [rcx+19h], 2
0x1800310a5  jb      short loc_1800310C2
0x1800310a7  mov     rcx, [rcx+10h]
0x1800310ab  lea     edx, [r14+12h]
0x1800310af  mov     r9, rdi
0x1800310b2  mov     dword ptr [rsp+110h+AllocationSize], eax
0x1800310b6  lea     r8, WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids
0x1800310bd  call    WPP_SF_Zd
0x1800310c2  bts     ebx, 1Ch
0x1800310c6  mov     [rbp+57h+var_98], ebx
0x1800310c9  jmp     loc_180031306
0x1800310ce  xorps   xmm0, xmm0
0x1800310d1  mov     [rbp+57h+FileHandle], r14
0x1800310d5  lea     rax, [rbp+57h+Block]
0x1800310d9  mov     [rbp+57h+var_A8], r14d
0x1800310dd  lea     r9, [rbp+57h+var_80]; struct _UNICODE_STRING *
0x1800310e1  mov     [rsp+110h+AllocationSize], rax; __int64
0x1800310e6  xor     r8d, r8d; struct _UNICODE_STRING *
0x1800310e9  mov     [rbp+57h+var_A4], r14b
0x1800310ed  lea     rdx, ?DiscanJetDatabaseDirectory@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x1800310f4  mov     [rbp+57h+Block], r14
0x1800310f8  mov     rcx, rdi; struct _UNICODE_STRING *
0x1800310fb  movups  xmmword ptr [rbp+57h+var_80.Length], xmm0
0x1800310ff  call    ?CopyUnicodeStringToBuffer@@YAJPEBU_UNICODE_STRING@@00PEAU1@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z; CopyUnicodeStringToBuffer(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)
0x180031104  mov     [rbp+57h+var_98], eax
0x180031107  mov     ebx, eax
0x180031109  test    eax, eax
0x18003110b  jns     short loc_18003114E
0x18003110d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031114  cmp     rcx, r12
0x180031117  jz      loc_1800312F3
0x18003111d  test    [rcx+1Ch], r15b
0x180031121  jz      loc_1800312F3
0x180031127  cmp     byte ptr [rcx+19h], 2
0x18003112b  jb      loc_1800312F3
0x180031131  mov     rcx, [rcx+10h]
0x180031135  lea     r8, WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids
0x18003113c  mov     edx, 13h
0x180031141  mov     r9d, eax
0x180031144  call    WPP_SF_d
0x180031149  jmp     loc_1800312F3
0x18003114e  xorps   xmm0, xmm0
0x180031151  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180031159  lea     rax, [rbp+57h+var_80]
0x18003115d  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x180031161  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180031165  mov     sil, r15b
0x180031168  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18003116d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180031175  mov     edi, 1E0003h
0x18003117a  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18003117e  mov     r13d, 80000000h
0x180031184  mov     [rsp+110h+EaLength], r14d; EaLength
0x180031189  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18003118d  mov     [rsp+110h+EaBuffer], r14; EaBuffer
0x180031192  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180031196  mov     [rsp+110h+CreateOptions], 21h ; '!'; CreateOptions
0x18003119e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800311a2  mov     [rsp+110h+CreateDisposition], 3; CreateDisposition
0x1800311aa  mov     edx, edi; DesiredAccess
0x1800311ac  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x1800311b4  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x1800311bc  mov     [rsp+110h+AllocationSize], r14; AllocationSize
0x1800311c1  call    cs:__imp_NtCreateFile
0x1800311c7  mov     ebx, eax
0x1800311c9  test    eax, eax
0x1800311cb  js      loc_1800312B7
0x1800311d1  test    sil, sil
0x1800311d4  jz      loc_180031293
0x1800311da  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800311de  lea     rax, [rbp+57h+InputBuffer]
0x1800311e2  mov     dword ptr [rsp+110h+EaBuffer], r14d; OutputBufferLength
0x1800311e7  xor     r9d, r9d; ApcContext
0x1800311ea  mov     qword ptr [rsp+110h+CreateOptions], r14; OutputBuffer
0x1800311ef  xor     r8d, r8d; ApcRoutine
0x1800311f2  mov     [rsp+110h+CreateDisposition], 8; InputBufferLength
0x1800311fa  xor     edx, edx; Event
0x1800311fc  mov     qword ptr [rsp+110h+ShareAccess], rax; InputBuffer
0x180031201  lea     rax, [rbp+57h+IoStatusBlock]
0x180031205  mov     [rbp+57h+InputBuffer], r14
0x180031209  mov     [rsp+110h+FileAttributes], 9C280h; FsControlCode
0x180031211  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x180031216  mov     word ptr [rbp+57h+InputBuffer], r15w
0x18003121b  call    cs:__imp_NtFsControlFile
0x180031221  mov     ebx, eax
0x180031223  lea     ecx, [rax+r13]
0x180031227  test    r13d, ecx
0x18003122a  jnz     short loc_180031233
0x18003122c  cmp     eax, 0C0000010h
0x180031231  jnz     short loc_180031261
0x180031233  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180031237  test    rcx, rcx
0x18003123a  jz      short loc_180031256
0x18003123c  cmp     [rbp+57h+var_A4], r14b
0x180031240  jz      short loc_180031248
0x180031242  cmp     [rbp+57h+var_A8], r14d
0x180031246  jnz     short loc_180031256
0x180031248  call    cs:__imp_NtClose
0x18003124e  mov     [rbp+57h+FileHandle], r14
0x180031252  mov     [rbp+57h+var_A4], r14b
0x180031256  and     edi, 0FFFFFFFCh
0x180031259  mov     sil, r14b
0x18003125c  jmp     loc_180031184
0x180031261  mov     rcx, cs:WPP_GLOBAL_Control
0x180031268  cmp     rcx, r12
0x18003126b  jz      short loc_1800312EC
0x18003126d  test    [rcx+1Ch], r15b
0x180031271  jz      short loc_1800312EC
0x180031273  cmp     byte ptr [rcx+19h], 2
0x180031277  jb      short loc_1800312EC
0x180031279  mov     rcx, [rcx+10h]
0x18003127d  lea     r8, WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids
0x180031284  mov     edx, 15h
0x180031289  mov     r9d, ebx
0x18003128c  call    WPP_SF_d
0x180031291  jmp     short loc_1800312EC
0x180031293  mov     rcx, [rbp+57h+Block]; Block
0x180031297  mov     [rbp+57h+var_98], r14d
0x18003129b  call    cs:__imp_free
0x1800312a1  lea     rcx, [rbp+57h+FileHandle]
0x1800312a5  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x1800312aa  lea     rcx, [rbp+57h+var_A0]; this
0x1800312ae  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x1800312b3  xor     eax, eax
0x1800312b5  jmp     short loc_180031311
0x1800312b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800312be  cmp     rcx, r12
0x1800312c1  jz      short loc_1800312EC
0x1800312c3  test    [rcx+1Ch], r15b
0x1800312c7  jz      short loc_1800312EC
0x1800312c9  cmp     byte ptr [rcx+19h], 2
0x1800312cd  jb      short loc_1800312EC
0x1800312cf  mov     rcx, [rcx+10h]
0x1800312d3  lea     r9, [rbp+57h+var_80]
0x1800312d7  mov     edx, 14h
0x1800312dc  mov     dword ptr [rsp+110h+AllocationSize], ebx
0x1800312e0  lea     r8, WPP_6242dd7fc9e938476b07df1604c9eaa5_Traceguids
0x1800312e7  call    WPP_SF_Zd
0x1800312ec  bts     ebx, 1Ch
0x1800312f0  mov     [rbp+57h+var_98], ebx
0x1800312f3  mov     rcx, [rbp+57h+Block]; Block
0x1800312f7  call    cs:__imp_free
0x1800312fd  lea     rcx, [rbp+57h+FileHandle]
0x180031301  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x180031306  lea     rcx, [rbp+57h+var_A0]; this
0x18003130a  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18003130f  mov     eax, ebx
0x180031311  mov     rbx, [rsp+110h+arg_0]
0x180031319  add     rsp, 0E0h
0x180031320  pop     r15
0x180031322  pop     r14
0x180031324  pop     r13
0x180031326  pop     r12
0x180031328  pop     rdi
0x180031329  pop     rsi
0x18003132a  pop     rbp
0x18003132b  retn
```
