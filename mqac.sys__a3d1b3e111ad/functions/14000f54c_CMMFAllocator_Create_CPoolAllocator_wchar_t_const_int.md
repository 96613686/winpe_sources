# CMMFAllocator::Create(CPoolAllocator *,wchar_t const *,int)

- ea: `0x14000f54c`
- end: `0x14000f948`
- name: `?Create@CMMFAllocator@@SAPEAV1@PEAVCPoolAllocator@@PEB_WH@Z`
- size: `1020`
- prototype: `struct CMMFAllocator *__fastcall(struct CPoolAllocator *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14000f950`
- `0x140010984`

## callees

- `0x1400010a4`
- `0x140001128`
- `0x14000ec14`
- `0x14000f390`
- `0x14000f54c`
- `0x140010108`
- `0x14001105c`
- `0x1400110d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000f8f6`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f8f6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f796`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000f796`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f5aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000f5aa`
- `ntoskrnl!ZwClose` at `0x14000f7d5`
- `ntoskrnl!ZwClose` at `0x14000f8be`
- `ntoskrnl!ZwClose` at `0x14000f906`
- `ntoskrnl!ZwClose` at `0x14000f7d5`
- `ntoskrnl!ZwClose` at `0x14000f8be`
- `ntoskrnl!ZwClose` at `0x14000f906`
- `ntoskrnl!ZwDeleteFile` at `0x14000f916`
- `ntoskrnl!ZwDeleteFile` at `0x14000f916`
- `ntoskrnl!ZwCreateFile` at `0x14000f62a`
- `ntoskrnl!ZwCreateFile` at `0x14000f62a`
- `ntoskrnl!ZwCreateSection` at `0x14000f72f`
- `ntoskrnl!ZwCreateSection` at `0x14000f72f`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14000f880`
- `ntoskrnl!ZwFlushBuffersFile` at `0x14000f880`

## pseudocode

```c
struct CMMFAllocator *__fastcall CMMFAllocator::Create(struct CPoolAllocator *a1, wchar_t *a2, int a3)
{
  union _LARGE_INTEGER v3; // r14
  const WCHAR *FileName; // rax
  WCHAR *v7; // rdi
  NTSTATUS v8; // eax
  NTSTATUS v9; // eax
  int v10; // r8d
  NTSTATUS v11; // eax
  int v12; // r8d
  int v13; // esi
  PVOID v14; // rsi
  CMMFAllocator *v15; // rax
  __int64 v16; // r8
  CMMFAllocator *v17; // rax
  CMMFAllocator *v18; // r14
  int v19; // eax
  int v20; // r8d
  int v21; // esi
  NTSTATUS v22; // eax
  void *SectionHandle; // [rsp+60h] [rbp-69h] BYREF
  PVOID Object; // [rsp+68h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES v29; // [rsp+C0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+130h] [rbp+67h] BYREF
  union _LARGE_INTEGER MaximumSize; // [rsp+148h] [rbp+7Fh] BYREF

  v3.QuadPart = g_ulHeapPoolSize;
  FileName = (const WCHAR *)ACpGenerateFileName(a2);
  v7 = (WCHAR *)FileName;
  if ( !FileName )
    return 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, FileName);
  ObjectAttributes.ObjectName = &DestinationString;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  IoStatusBlock = 0;
  MaximumSize = v3;
  v8 = ZwCreateFile(
         &FileHandle,
         0xC0100000,
         &ObjectAttributes,
         &IoStatusBlock,
         &MaximumSize,
         0x80u,
         1u,
         3u,
         0x8022u,
         0,
         0);
  if ( v8 < 0 )
  {
    if ( v8 == -1073741790 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 20, v8, (_DWORD)v7, 34);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 21, v8, (_DWORD)v7, v8);
    }
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
  {
    WPP_SF_S(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 23, (unsigned int)v8, v7);
  }
  MaximumSize = v3;
  *(_QWORD *)&v29.Length = 48;
  *(_QWORD *)&v29.Attributes = 512;
  v29.RootDirectory = 0;
  v29.ObjectName = 0;
  *(_OWORD *)&v29.SecurityDescriptor = 0;
  SectionHandle = 0;
  v9 = ZwCreateSection(&SectionHandle, 0xF0007u, &v29, &MaximumSize, 4u, 0x8000000u, FileHandle);
  if ( v9 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 24, v10, (_DWORD)v7, v9);
    }
LABEL_40:
    ZwClose(FileHandle);
    ZwDeleteFile(&ObjectAttributes);
LABEL_41:
    operator delete(v7);
    return 0;
  }
  Object = 0;
  v11 = ObReferenceObjectByHandle(SectionHandle, 0xF0007u, 0, 0, &Object, 0);
  v13 = v11;
  if ( v11 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
  {
    WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 25, v12, (_DWORD)v7, v11);
  }
  ZwClose(SectionHandle);
  if ( v13 < 0 )
    goto LABEL_40;
  v14 = Object;
  v15 = (CMMFAllocator *)operator new(0xA8u, 0x100u, 0x4841514Du, LowPoolPriority);
  if ( !v15 || (v17 = CMMFAllocator::CMMFAllocator(v15, a1, v14, v7, v3.LowPart), (v18 = v17) == 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 28, v16, v7);
    }
    ObfDereferenceObject(v14);
    goto LABEL_40;
  }
  if ( !a3 && *((_DWORD *)a1 + 12) == 512 )
  {
    v19 = CMMFAllocator::InitializeMemory(v17);
    v21 = v19;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 4) != 0 )
    {
      WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 26, v20, (_DWORD)v7, v19);
    }
    if ( v21 < 0 || (v22 = ZwFlushBuffersFile(FileHandle, &IoStatusBlock), LOBYTE(v21) = v22, v22 < 0) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Queue.Wcb.DeviceRoutine) & 1) != 0 )
      {
        WPP_SF_Sd(WPP_GLOBAL_Control->Queue.ListEntry.Blink, 27, v20, (_DWORD)v7, v21);
      }
    }
  }
  ZwClose(FileHandle);
  return v18;
}

```

## disassembly

```asm
0x14000f54c  mov     [rsp-8+arg_8], rbx
0x14000f551  push    rbp
0x14000f552  push    rsi
0x14000f553  push    rdi
0x14000f554  push    r12
0x14000f556  push    r13
0x14000f558  push    r14
0x14000f55a  push    r15
0x14000f55c  lea     rbp, [rsp-27h]
0x14000f561  sub     rsp, 0F0h
0x14000f568  mov     rax, [rcx]
0x14000f56b  mov     r9, rdx
0x14000f56e  mov     r14d, cs:?g_ulHeapPoolSize@@3KA; ulong g_ulHeapPoolSize
0x14000f575  mov     r15, rcx
0x14000f578  mov     rcx, r9; wchar_t *
0x14000f57b  mov     r12d, r8d
0x14000f57e  mov     rdx, [rax+40h]
0x14000f582  mov     edx, [rdx+148h]
0x14000f588  call    ACpGenerateFileName
0x14000f58d  xor     r13d, r13d
0x14000f590  mov     rdi, rax
0x14000f593  test    rax, rax
0x14000f596  jz      loc_14000F92A
0x14000f59c  xorps   xmm0, xmm0
0x14000f59f  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000f5a3  mov     rdx, rax; SourceString
0x14000f5a6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000f5aa  call    cs:__imp_RtlInitUnicodeString
0x14000f5b1  nop     dword ptr [rax+rax+00h]
0x14000f5b6  mov     [rsp+120h+EaLength], r13d; EaLength
0x14000f5bb  lea     rax, [rbp+57h+DestinationString]
0x14000f5bf  mov     [rsp+120h+EaBuffer], r13; EaBuffer
0x14000f5c4  lea     esi, [r13+1]
0x14000f5c8  mov     [rsp+120h+CreateOptions], 8022h; CreateOptions
0x14000f5d0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000f5d4  mov     [rsp+120h+CreateDisposition], 3; CreateDisposition
0x14000f5dc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f5e0  xorps   xmm0, xmm0
0x14000f5e3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000f5e7  mov     [rsp+120h+ShareAccess], esi; ShareAccess
0x14000f5eb  lea     rax, [rbp+57h+MaximumSize]
0x14000f5ef  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x14000f5f7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000f5fb  mov     edx, 0C0100000h; DesiredAccess
0x14000f600  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x14000f605  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000f60d  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 240h
0x14000f615  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x14000f619  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f61e  mov     [rbp+57h+FileHandle], r13
0x14000f622  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14000f626  mov     qword ptr [rbp+57h+MaximumSize], r14
0x14000f62a  call    cs:__imp_ZwCreateFile
0x14000f631  nop     dword ptr [rax+rax+00h]
0x14000f636  mov     r8d, eax
0x14000f639  test    eax, eax
0x14000f63b  jns     short loc_14000F6B2
0x14000f63d  cmp     eax, 0C0000022h
0x14000f642  jnz     short loc_14000F674
0x14000f644  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f64b  lea     rbx, WPP_GLOBAL_Control
0x14000f652  cmp     rcx, rbx
0x14000f655  jz      loc_14000F922
0x14000f65b  mov     eax, [rcx+6Ch]
0x14000f65e  test    sil, al
0x14000f661  jz      loc_14000F922
0x14000f667  lea     edx, [rsi+13h]
0x14000f66a  mov     dword ptr [rsp+120h+AllocationSize], 0C0000022h
0x14000f672  jmp     short loc_14000F6A1
0x14000f674  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f67b  lea     rbx, WPP_GLOBAL_Control
0x14000f682  cmp     rcx, rbx
0x14000f685  jz      loc_14000F922
0x14000f68b  mov     eax, [rcx+6Ch]
0x14000f68e  test    sil, al
0x14000f691  jz      loc_14000F922
0x14000f697  mov     edx, 15h
0x14000f69c  mov     dword ptr [rsp+120h+AllocationSize], r8d
0x14000f6a1  mov     rcx, [rcx+58h]
0x14000f6a5  mov     r9, rdi
0x14000f6a8  call    WPP_SF_Sd
0x14000f6ad  jmp     loc_14000F922
0x14000f6b2  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f6b9  lea     rbx, WPP_GLOBAL_Control
0x14000f6c0  cmp     rcx, rbx
0x14000f6c3  jz      short loc_14000F6DD
0x14000f6c5  mov     eax, [rcx+6Ch]
0x14000f6c8  test    al, 4
0x14000f6ca  jz      short loc_14000F6DD
0x14000f6cc  mov     rcx, [rcx+58h]
0x14000f6d0  mov     edx, 17h
0x14000f6d5  mov     r9, rdi
0x14000f6d8  call    WPP_SF_S
0x14000f6dd  mov     rax, [rbp+57h+FileHandle]
0x14000f6e1  lea     r9, [rbp+57h+MaximumSize]; MaximumSize
0x14000f6e5  mov     qword ptr [rsp+120h+ShareAccess], rax; FileHandle
0x14000f6ea  lea     r8, [rbp+57h+var_60]; ObjectAttributes
0x14000f6ee  xorps   xmm0, xmm0
0x14000f6f1  mov     [rsp+120h+FileAttributes], 8000000h; AllocationAttributes
0x14000f6f9  mov     edx, 0F0007h; DesiredAccess
0x14000f6fe  mov     dword ptr [rsp+120h+AllocationSize], 4; SectionPageProtection
0x14000f706  lea     rcx, [rbp+57h+SectionHandle]; SectionHandle
0x14000f70a  mov     qword ptr [rbp+57h+MaximumSize], r14
0x14000f70e  mov     qword ptr [rbp+57h+var_60.Length], 30h ; '0'
0x14000f716  mov     qword ptr [rbp+57h+var_60.Attributes], 200h
0x14000f71e  mov     [rbp+57h+var_60.RootDirectory], r13
0x14000f722  mov     [rbp+57h+var_60.ObjectName], r13
0x14000f726  movdqu  xmmword ptr [rbp+57h+var_60.SecurityDescriptor], xmm0
0x14000f72b  mov     [rbp+57h+SectionHandle], r13
0x14000f72f  call    cs:__imp_ZwCreateSection
0x14000f736  nop     dword ptr [rax+rax+00h]
0x14000f73b  test    eax, eax
0x14000f73d  jns     short loc_14000F775
0x14000f73f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f746  cmp     rcx, rbx
0x14000f749  jz      loc_14000F902
0x14000f74f  mov     edx, [rcx+6Ch]
0x14000f752  test    sil, dl
0x14000f755  jz      loc_14000F902
0x14000f75b  mov     rcx, [rcx+58h]
0x14000f75f  mov     edx, 18h
0x14000f764  mov     r9, rdi
0x14000f767  mov     dword ptr [rsp+120h+AllocationSize], eax
0x14000f76b  call    WPP_SF_Sd
0x14000f770  jmp     loc_14000F902
0x14000f775  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x14000f779  lea     rax, [rbp+57h+Object]
0x14000f77d  mov     qword ptr [rsp+120h+FileAttributes], r13; HandleInformation
0x14000f782  xor     r9d, r9d; AccessMode
0x14000f785  xor     r8d, r8d; ObjectType
0x14000f788  mov     [rsp+120h+AllocationSize], rax; Object
0x14000f78d  mov     edx, 0F0007h; DesiredAccess
0x14000f792  mov     [rbp+57h+Object], r13
0x14000f796  call    cs:__imp_ObReferenceObjectByHandle
0x14000f79d  nop     dword ptr [rax+rax+00h]
0x14000f7a2  mov     esi, eax
0x14000f7a4  test    eax, eax
0x14000f7a6  jns     short loc_14000F7D1
0x14000f7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f7af  cmp     rcx, rbx
0x14000f7b2  jz      short loc_14000F7D1
0x14000f7b4  mov     edx, [rcx+6Ch]
0x14000f7b7  test    dl, 1
0x14000f7ba  jz      short loc_14000F7D1
0x14000f7bc  mov     rcx, [rcx+58h]
0x14000f7c0  mov     edx, 19h
0x14000f7c5  mov     r9, rdi
0x14000f7c8  mov     dword ptr [rsp+120h+AllocationSize], eax
0x14000f7cc  call    WPP_SF_Sd
0x14000f7d1  mov     rcx, [rbp+57h+SectionHandle]; Handle
0x14000f7d5  call    cs:__imp_ZwClose
0x14000f7dc  nop     dword ptr [rax+rax+00h]
0x14000f7e1  test    esi, esi
0x14000f7e3  js      loc_14000F902
0x14000f7e9  mov     rsi, [rbp+57h+Object]
0x14000f7ed  mov     edx, 100h; unsigned __int64
0x14000f7f2  xor     r9d, r9d; enum _EX_POOL_PRIORITY
0x14000f7f5  mov     r8d, 4841514Dh; unsigned int
0x14000f7fb  lea     ecx, [rdx-58h]; unsigned __int64
0x14000f7fe  call    ??2@YAPEAX_K0KW4_EX_POOL_PRIORITY@@@Z; operator new(unsigned __int64,unsigned __int64,ulong,_EX_POOL_PRIORITY)
0x14000f803  test    rax, rax
0x14000f806  jz      loc_14000F8CF
0x14000f80c  mov     r9, rdi; wchar_t *
0x14000f80f  mov     dword ptr [rsp+120h+AllocationSize], r14d; unsigned int
0x14000f814  mov     r8, rsi; void *
0x14000f817  mov     rdx, r15; struct CPoolAllocator *
0x14000f81a  mov     rcx, rax; this
0x14000f81d  call    ??0CMMFAllocator@@AEAA@PEAVCPoolAllocator@@PEAXPEA_WK@Z; CMMFAllocator::CMMFAllocator(CPoolAllocator *,void *,wchar_t *,ulong)
0x14000f822  mov     r14, rax
0x14000f825  test    rax, rax
0x14000f828  jz      loc_14000F8CF
0x14000f82e  test    r12d, r12d
0x14000f831  jnz     loc_14000F8BA
0x14000f837  cmp     dword ptr [r15+30h], 200h
0x14000f83f  jnz     short loc_14000F8BA
0x14000f841  mov     rcx, rax; this
0x14000f844  call    ?InitializeMemory@CMMFAllocator@@AEAAJXZ; CMMFAllocator::InitializeMemory(void)
0x14000f849  mov     esi, eax
0x14000f84b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f852  cmp     rcx, rbx
0x14000f855  jz      short loc_14000F874
0x14000f857  mov     edx, [rcx+6Ch]
0x14000f85a  test    dl, 4
0x14000f85d  jz      short loc_14000F874
0x14000f85f  mov     rcx, [rcx+58h]
0x14000f863  lea     edx, [r12+1Ah]
0x14000f868  mov     r9, rdi
0x14000f86b  mov     dword ptr [rsp+120h+AllocationSize], eax
0x14000f86f  call    WPP_SF_Sd
0x14000f874  test    esi, esi
0x14000f876  js      short loc_14000F892
0x14000f878  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000f87c  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14000f880  call    cs:__imp_ZwFlushBuffersFile
0x14000f887  nop     dword ptr [rax+rax+00h]
0x14000f88c  mov     esi, eax
0x14000f88e  test    eax, eax
0x14000f890  jns     short loc_14000F8BA
0x14000f892  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f899  cmp     rcx, rbx
0x14000f89c  jz      short loc_14000F8BA
0x14000f89e  mov     eax, [rcx+6Ch]
0x14000f8a1  test    al, 1
0x14000f8a3  jz      short loc_14000F8BA
0x14000f8a5  mov     rcx, [rcx+58h]
0x14000f8a9  mov     edx, 1Bh
0x14000f8ae  mov     r9, rdi
0x14000f8b1  mov     dword ptr [rsp+120h+AllocationSize], esi
0x14000f8b5  call    WPP_SF_Sd
0x14000f8ba  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000f8be  call    cs:__imp_ZwClose
0x14000f8c5  nop     dword ptr [rax+rax+00h]
0x14000f8ca  mov     rax, r14
0x14000f8cd  jmp     short loc_14000F92C
0x14000f8cf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8d6  cmp     rcx, rbx
0x14000f8d9  jz      short loc_14000F8F3
0x14000f8db  mov     eax, [rcx+6Ch]
0x14000f8de  test    al, 1
0x14000f8e0  jz      short loc_14000F8F3
0x14000f8e2  mov     rcx, [rcx+58h]
0x14000f8e6  mov     edx, 1Ch
0x14000f8eb  mov     r9, rdi
0x14000f8ee  call    WPP_SF_S
0x14000f8f3  mov     rcx, rsi; Object
0x14000f8f6  call    cs:__imp_ObfDereferenceObject
0x14000f8fd  nop     dword ptr [rax+rax+00h]
0x14000f902  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000f906  call    cs:__imp_ZwClose
0x14000f90d  nop     dword ptr [rax+rax+00h]
0x14000f912  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000f916  call    cs:__imp_ZwDeleteFile
0x14000f91d  nop     dword ptr [rax+rax+00h]
0x14000f922  mov     rcx, rdi; void *
0x14000f925  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000f92a  xor     eax, eax
0x14000f92c  mov     rbx, [rsp+120h+arg_8]
0x14000f934  add     rsp, 0F0h
0x14000f93b  pop     r15
0x14000f93d  pop     r14
0x14000f93f  pop     r13
0x14000f941  pop     r12
0x14000f943  pop     rdi
0x14000f944  pop     rsi
0x14000f945  pop     rbp
0x14000f946  retn
```
