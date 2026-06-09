# DxgkpCopyFile(ushort const *,ushort const *)

- ea: `0x140235460`
- end: `0x140235811`
- name: `?DxgkpCopyFile@@YAJPEBG0@Z`
- size: `945`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PCWSTR)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140235b5c`

## callees

- `0x140009030`
- `0x14000d7d0`
- `0x14001b890`
- `0x14023531c`
- `0x140235460`
- `0x140235974`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1402357c1`
- `ntoskrnl!ZwClose` at `0x1402357eb`
- `ntoskrnl!ZwClose` at `0x1402357c1`
- `ntoskrnl!ZwClose` at `0x1402357eb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140235490`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402354a3`
- `ntoskrnl!RtlInitUnicodeString` at `0x140235490`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402354a3`
- `ntoskrnl!ZwReadFile` at `0x1402356e4`
- `ntoskrnl!ZwReadFile` at `0x1402356e4`
- `ntoskrnl!ZwCreateFile` at `0x140235549`
- `ntoskrnl!ZwCreateFile` at `0x140235668`
- `ntoskrnl!ZwCreateFile` at `0x140235549`
- `ntoskrnl!ZwCreateFile` at `0x140235668`
- `ntoskrnl!ZwWriteFile` at `0x140235722`
- `ntoskrnl!ZwWriteFile` at `0x140235722`
- `watchdog!WdLogSingleEntry0` at `0x1402355db`
- `watchdog!WdLogSingleEntry0` at `0x1402355db`
- `watchdog!WdLogSingleEntry1` at `0x14023556e`
- `watchdog!WdLogSingleEntry1` at `0x140235683`
- `watchdog!WdLogSingleEntry1` at `0x14023573d`
- `watchdog!WdLogSingleEntry1` at `0x140235771`
- `watchdog!WdLogSingleEntry1` at `0x14023556e`
- `watchdog!WdLogSingleEntry1` at `0x140235683`
- `watchdog!WdLogSingleEntry1` at `0x14023573d`
- `watchdog!WdLogSingleEntry1` at `0x140235771`

## string_xrefs

- `0x1402355ec`: `Failed allocate memory for CopyBuffer`
- `0x14023557f`: `Failed ZwCreateFile for source in DxgkpCopyFile: 0x%I64x`
- `0x14023577d`: `Failed ZwReadFile in DxgkpCopyFile: 0x%I64x`
- `0x14023568f`: `Failed ZwCreateFile for dest in DxgkpCopyFile: 0x%I64x`
- `0x140235749`: `Failed ZwWriteFile in DxgkpCopyFile: 0x%I64x`

## pseudocode

```c
__int64 __fastcall DxgkpCopyFile(PCWSTR SourceString, PCWSTR a2)
{
  NTSTATUS v3; // eax
  __int64 v4; // rdi
  void *v5; // rsi
  NTSTATUS v6; // eax
  const wchar_t *v7; // r9
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING v13; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES v15; // [rsp+C0h] [rbp+7h] BYREF
  HANDLE Handle; // [rsp+130h] [rbp+77h] BYREF
  void *FileHandle; // [rsp+138h] [rbp+7Fh] BYREF

  DestinationString = 0;
  v13 = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  RtlInitUnicodeString(&v13, a2);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  *(_QWORD *)&v15.Length = 48;
  *(_QWORD *)&v15.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v15.RootDirectory = 0;
  v15.ObjectName = &v13;
  *(_OWORD *)&v15.SecurityDescriptor = 0;
  FileHandle = (void *)-1LL;
  Handle = (HANDLE)-1LL;
  IoStatusBlock = 0;
  v3 = ZwCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 0x4010u, 0, 0);
  if ( v3 < 0 )
  {
    LODWORD(v4) = 0;
    if ( v3 != -1073741772 )
      LODWORD(v4) = v3;
    WdLogSingleEntry1(2);
    WdLogGlobalForLineNumber = 465;
    DxgkLogInternalTriageEvent(
      0,
      0x40000,
      -1,
      (unsigned int)L"Failed ZwCreateFile for source in DxgkpCopyFile: 0x%I64x",
      (int)v4,
      0,
      0,
      0,
      0);
    return (unsigned int)v4;
  }
  v5 = (void *)operator new[](0x10000, 1265072196, 258);
  if ( !v5 )
  {
    WdLogSingleEntry0(6);
    WdLogGlobalForLineNumber = 473;
    DxgkLogInternalTriageEvent(0, 262145, -1, (unsigned int)L"Failed allocate memory for CopyBuffer", 473, 0, 0, 0, 0);
    LODWORD(v4) = -1073741801;
    goto LABEL_17;
  }
  v6 = ZwCreateFile(&Handle, 0x1F019Fu, &v15, &IoStatusBlock, 0, 0x80u, 7u, 5u, 0x4010u, 0, 0);
  v4 = v6;
  if ( v6 >= 0 )
  {
    LODWORD(v4) = DxgkpCopyAttributes(FileHandle, Handle);
    if ( (int)v4 < 0 )
      goto LABEL_17;
    while ( 1 )
    {
      v8 = ZwReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, v5, 0x10000u, 0, 0);
      v4 = v8;
      if ( v8 < 0 )
        break;
      v9 = ZwWriteFile(Handle, 0, 0, 0, &IoStatusBlock, v5, IoStatusBlock.Information, 0, 0);
      v4 = v9;
      if ( v9 < 0 )
      {
        WdLogSingleEntry1(2);
        v7 = L"Failed ZwWriteFile in DxgkpCopyFile: 0x%I64x";
        WdLogGlobalForLineNumber = 546;
        goto LABEL_16;
      }
    }
    if ( v8 == -1073741807 )
    {
      LODWORD(v4) = 0;
      goto LABEL_17;
    }
    WdLogSingleEntry1(2);
    v7 = L"Failed ZwReadFile in DxgkpCopyFile: 0x%I64x";
    WdLogGlobalForLineNumber = 526;
  }
  else
  {
    WdLogSingleEntry1(2);
    v7 = L"Failed ZwCreateFile for dest in DxgkpCopyFile: 0x%I64x";
    WdLogGlobalForLineNumber = 492;
  }
LABEL_16:
  DxgkLogInternalTriageEvent(0, 0x40000, -1, (_DWORD)v7, v4, 0, 0, 0, 0);
LABEL_17:
  if ( Handle != (HANDLE)-1LL )
  {
    ZwClose(Handle);
    if ( (int)v4 < 0 )
      DxgkpDeleteFile(a2);
  }
  DXGQUOTAALLOCATOR<256,1835156294>::operator delete(v5);
  if ( FileHandle != (void *)-1LL )
    ZwClose(FileHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140235460  mov     [rsp-8+arg_0], rbx
0x140235465  push    rbp
0x140235466  push    rsi
0x140235467  push    rdi
0x140235468  push    r14
0x14023546a  push    r15
0x14023546c  lea     rbp, [rsp-37h]
0x140235471  sub     rsp, 0F0h
0x140235478  mov     r14, rdx
0x14023547b  xorps   xmm0, xmm0
0x14023547e  mov     rdx, rcx; SourceString
0x140235481  xorps   xmm1, xmm1
0x140235484  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140235488  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14023548c  movups  xmmword ptr [rbp+57h+var_90.Length], xmm1
0x140235490  call    cs:__imp_RtlInitUnicodeString
0x140235497  nop     dword ptr [rax+rax+00h]
0x14023549c  mov     rdx, r14; SourceString
0x14023549f  lea     rcx, [rbp+57h+var_90]; DestinationString
0x1402354a3  call    cs:__imp_RtlInitUnicodeString
0x1402354aa  nop     dword ptr [rax+rax+00h]
0x1402354af  xor     r15d, r15d
0x1402354b2  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1402354ba  mov     [rsp+110h+EaLength], r15d; EaLength
0x1402354bf  lea     rax, [rbp+57h+DestinationString]
0x1402354c3  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x1402354c8  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1402354cc  xorps   xmm0, xmm0
0x1402354cf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1402354d3  lea     rax, [rbp+57h+var_90]
0x1402354d7  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x1402354df  mov     edi, 4010h
0x1402354e4  mov     qword ptr [rbp+57h+var_50.Length], 30h ; '0'
0x1402354ec  mov     [rsp+110h+CreateOptions], edi; CreateOptions
0x1402354f0  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1402354f4  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x1402354fc  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140235500  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x140235508  mov     edx, 120089h; DesiredAccess
0x14023550d  mov     [rsp+110h+FileAttributes], r15d; FileAttributes
0x140235512  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x140235517  mov     qword ptr [rbp+57h+var_50.Attributes], 240h
0x14023551f  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140235523  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140235528  mov     [rbp+57h+var_50.RootDirectory], r15
0x14023552c  mov     [rbp+57h+var_50.ObjectName], rax
0x140235530  movdqu  xmmword ptr [rbp+57h+var_50.SecurityDescriptor], xmm0
0x140235535  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x14023553d  mov     [rbp+57h+Handle], 0FFFFFFFFFFFFFFFFh
0x140235545  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140235549  call    cs:__imp_ZwCreateFile
0x140235550  nop     dword ptr [rax+rax+00h]
0x140235555  test    eax, eax
0x140235557  jns     short loc_1402355B9
0x140235559  cmp     eax, 0C0000034h
0x14023555e  lea     ecx, [r15+2]
0x140235562  mov     edi, r15d
0x140235565  cmovnz  edi, eax
0x140235568  movsxd  rbx, edi
0x14023556b  mov     rdx, rbx
0x14023556e  call    cs:__imp_WdLogSingleEntry1
0x140235575  nop     dword ptr [rax+rax+00h]
0x14023557a  mov     qword ptr [rsp+110h+CreateOptions], r15
0x14023557f  lea     r9, aFailedZwcreate; "Failed ZwCreateFile for source in Dxgkp"...
0x140235586  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x14023558b  or      r8d, 0FFFFFFFFh
0x14023558f  mov     qword ptr [rsp+110h+ShareAccess], r15
0x140235594  mov     edx, 40000h
0x140235599  mov     qword ptr [rsp+110h+FileAttributes], r15
0x14023559e  xor     ecx, ecx
0x1402355a0  mov     [rsp+110h+AllocationSize], rbx
0x1402355a5  mov     cs:WdLogGlobalForLineNumber, 1D1h
0x1402355af  call    DxgkLogInternalTriageEvent
0x1402355b4  jmp     loc_1402357F7
0x1402355b9  mov     ebx, 10000h
0x1402355be  mov     edx, 4B677844h
0x1402355c3  mov     ecx, ebx
0x1402355c5  mov     r8d, 102h
0x1402355cb  call    ??_U@YAPEAX_KIW4DXGK_POOL_FLAGS@@@Z; operator new[](unsigned __int64,uint,DXGK_POOL_FLAGS)
0x1402355d0  mov     rsi, rax
0x1402355d3  test    rax, rax
0x1402355d6  jnz     short loc_14023562C
0x1402355d8  lea     ecx, [rax+6]
0x1402355db  call    cs:__imp_WdLogSingleEntry0
0x1402355e2  nop     dword ptr [rax+rax+00h]
0x1402355e7  mov     qword ptr [rsp+110h+CreateOptions], r15
0x1402355ec  lea     r9, aFailedAllocate; "Failed allocate memory for CopyBuffer"
0x1402355f3  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x1402355f8  mov     eax, 1D9h
0x1402355fd  mov     qword ptr [rsp+110h+ShareAccess], r15
0x140235602  or      r8d, 0FFFFFFFFh
0x140235606  mov     qword ptr [rsp+110h+FileAttributes], r15
0x14023560b  mov     edx, 40001h
0x140235610  xor     ecx, ecx
0x140235612  mov     [rsp+110h+AllocationSize], rax
0x140235617  mov     cs:WdLogGlobalForLineNumber, eax
0x14023561d  call    DxgkLogInternalTriageEvent
0x140235622  mov     edi, 0C0000017h
0x140235627  jmp     loc_1402357B7
0x14023562c  mov     [rsp+110h+EaLength], r15d; EaLength
0x140235631  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140235635  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x14023563a  lea     r8, [rbp+57h+var_50]; ObjectAttributes
0x14023563e  mov     [rsp+110h+CreateOptions], edi; CreateOptions
0x140235642  lea     rcx, [rbp+57h+Handle]; FileHandle
0x140235646  mov     [rsp+110h+CreateDisposition], 5; CreateDisposition
0x14023564e  mov     edx, 1F019Fh; DesiredAccess
0x140235653  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x14023565b  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x140235663  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x140235668  call    cs:__imp_ZwCreateFile
0x14023566f  nop     dword ptr [rax+rax+00h]
0x140235674  movsxd  rdi, eax
0x140235677  test    eax, eax
0x140235679  jns     short loc_1402356A5
0x14023567b  mov     rdx, rdi
0x14023567e  mov     ecx, 2
0x140235683  call    cs:__imp_WdLogSingleEntry1
0x14023568a  nop     dword ptr [rax+rax+00h]
0x14023568f  lea     r9, aFailedZwcreate_0; "Failed ZwCreateFile for dest in DxgkpCo"...
0x140235696  mov     cs:WdLogGlobalForLineNumber, 1ECh
0x1402356a0  jmp     loc_14023578E
0x1402356a5  mov     rdx, [rbp+57h+Handle]; void *
0x1402356a9  mov     rcx, [rbp+57h+FileHandle]; void *
0x1402356ad  call    ?DxgkpCopyAttributes@@YAJPEAX0@Z; DxgkpCopyAttributes(void *,void *)
0x1402356b2  mov     edi, eax
0x1402356b4  test    eax, eax
0x1402356b6  js      loc_1402357B7
0x1402356bc  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1402356c0  lea     rax, [rbp+57h+IoStatusBlock]
0x1402356c4  mov     qword ptr [rsp+110h+CreateOptions], r15; Key
0x1402356c9  xor     r9d, r9d; ApcContext
0x1402356cc  mov     qword ptr [rsp+110h+CreateDisposition], r15; ByteOffset
0x1402356d1  xor     r8d, r8d; ApcRoutine
0x1402356d4  mov     [rsp+110h+ShareAccess], ebx; Length
0x1402356d8  xor     edx, edx; Event
0x1402356da  mov     qword ptr [rsp+110h+FileAttributes], rsi; Buffer
0x1402356df  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x1402356e4  call    cs:__imp_ZwReadFile
0x1402356eb  nop     dword ptr [rax+rax+00h]
0x1402356f0  movsxd  rdi, eax
0x1402356f3  test    eax, eax
0x1402356f5  js      short loc_14023575C
0x1402356f7  mov     eax, dword ptr [rbp+57h+IoStatusBlock.Information]
0x1402356fa  xor     r9d, r9d; ApcContext
0x1402356fd  mov     rcx, [rbp+57h+Handle]; FileHandle
0x140235701  xor     r8d, r8d; ApcRoutine
0x140235704  mov     qword ptr [rsp+110h+CreateOptions], r15; Key
0x140235709  xor     edx, edx; Event
0x14023570b  mov     qword ptr [rsp+110h+CreateDisposition], r15; ByteOffset
0x140235710  mov     [rsp+110h+ShareAccess], eax; Length
0x140235714  lea     rax, [rbp+57h+IoStatusBlock]
0x140235718  mov     qword ptr [rsp+110h+FileAttributes], rsi; Buffer
0x14023571d  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x140235722  call    cs:__imp_ZwWriteFile
0x140235729  nop     dword ptr [rax+rax+00h]
0x14023572e  movsxd  rdi, eax
0x140235731  test    eax, eax
0x140235733  jns     short loc_1402356BC
0x140235735  mov     rdx, rdi
0x140235738  mov     ecx, 2
0x14023573d  call    cs:__imp_WdLogSingleEntry1
0x140235744  nop     dword ptr [rax+rax+00h]
0x140235749  lea     r9, aFailedZwwritef; "Failed ZwWriteFile in DxgkpCopyFile: 0x"...
0x140235750  mov     cs:WdLogGlobalForLineNumber, 222h
0x14023575a  jmp     short loc_14023578E
0x14023575c  cmp     edi, 0C0000011h
0x140235762  jnz     short loc_140235769
0x140235764  mov     edi, r15d
0x140235767  jmp     short loc_1402357B7
0x140235769  mov     rdx, rdi
0x14023576c  mov     ecx, 2
0x140235771  call    cs:__imp_WdLogSingleEntry1
0x140235778  nop     dword ptr [rax+rax+00h]
0x14023577d  lea     r9, aFailedZwreadfi; "Failed ZwReadFile in DxgkpCopyFile: 0x%"...
0x140235784  mov     cs:WdLogGlobalForLineNumber, 20Eh
0x14023578e  mov     qword ptr [rsp+110h+CreateOptions], r15
0x140235793  or      r8d, 0FFFFFFFFh
0x140235797  mov     qword ptr [rsp+110h+CreateDisposition], r15
0x14023579c  mov     edx, 40000h
0x1402357a1  mov     qword ptr [rsp+110h+ShareAccess], r15
0x1402357a6  xor     ecx, ecx
0x1402357a8  mov     qword ptr [rsp+110h+FileAttributes], r15
0x1402357ad  mov     [rsp+110h+AllocationSize], rdi
0x1402357b2  call    DxgkLogInternalTriageEvent
0x1402357b7  mov     rcx, [rbp+57h+Handle]; Handle
0x1402357bb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1402357bf  jz      short loc_1402357D9
0x1402357c1  call    cs:__imp_ZwClose
0x1402357c8  nop     dword ptr [rax+rax+00h]
0x1402357cd  test    edi, edi
0x1402357cf  jns     short loc_1402357D9
0x1402357d1  mov     rcx, r14; SourceString
0x1402357d4  call    ?DxgkpDeleteFile@@YAJPEBG@Z; DxgkpDeleteFile(ushort const *)
0x1402357d9  mov     rcx, rsi; void *
0x1402357dc  call    ??3?$DXGQUOTAALLOCATOR@$0BAA@$0GNGCEDEG@@@SAXPEAX@Z; DXGQUOTAALLOCATOR<256,1835156294>::operator delete(void *)
0x1402357e1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1402357e5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1402357e9  jz      short loc_1402357F7
0x1402357eb  call    cs:__imp_ZwClose
0x1402357f2  nop     dword ptr [rax+rax+00h]
0x1402357f7  mov     rbx, [rsp+110h+arg_0]
0x1402357ff  mov     eax, edi
0x140235801  add     rsp, 0F0h
0x140235808  pop     r15
0x14023580a  pop     r14
0x14023580c  pop     rdi
0x14023580d  pop     rsi
0x14023580e  pop     rbp
0x14023580f  retn
```
