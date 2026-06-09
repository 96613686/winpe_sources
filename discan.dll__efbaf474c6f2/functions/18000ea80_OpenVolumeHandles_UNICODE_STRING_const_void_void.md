# OpenVolumeHandles(_UNICODE_STRING const *,void * *,void * *)

- ea: `0x18000ea80`
- end: `0x18000ecd8`
- name: `?OpenVolumeHandles@@YAJPEBU_UNICODE_STRING@@PEAPEAX1@Z`
- size: `600`
- prototype: `__int64 __fastcall(const struct _UNICODE_STRING *, void **, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013b48`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x18000891c`
- `0x180009088`
- `0x18000ea80`
- `0x180010160`
- `0x1800129b0`

## import_xrefs

- `ntdll!RtlGetThreadErrorMode` at `0x18000eb64`
- `ntdll!RtlGetThreadErrorMode` at `0x18000eb64`
- `ntdll!NtOpenFile` at `0x18000ebac`
- `ntdll!NtOpenFile` at `0x18000ec38`
- `ntdll!NtOpenFile` at `0x18000ebac`
- `ntdll!NtOpenFile` at `0x18000ec38`

## string_xrefs

- `0x18000eaba`: `OpenVolumeHandles`

## pseudocode

```c
__int64 __fastcall OpenVolumeHandles(struct _UNICODE_STRING *a1, void **a2, void **a3)
{
  _QWORD *ThreadLocalStoragePointer; // rax
  USHORT Length; // cx
  __int64 v8; // r10
  USHORT v9; // dx
  USHORT v10; // ax
  ULONG ThreadErrorMode; // eax
  NTSTATUS v12; // ebx
  unsigned int v13; // ebx
  NTSTATUS v14; // ebx
  void *FileHandle; // [rsp+30h] [rbp-59h] BYREF
  int v17; // [rsp+38h] [rbp-51h]
  char v18; // [rsp+3Ch] [rbp-4Dh]
  void *v19; // [rsp+40h] [rbp-49h] BYREF
  int v20; // [rsp+48h] [rbp-41h]
  char v21; // [rsp+4Ch] [rbp-3Dh]
  const char *v22; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-31h]
  USHORT v24; // [rsp+60h] [rbp-29h]
  USHORT v25; // [rsp+62h] [rbp-27h]
  int v26; // [rsp+64h] [rbp-25h]
  char *v27; // [rsp+68h] [rbp-21h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-9h] BYREF
  ULONG OldMode; // [rsp+F0h] [rbp+67h] BYREF
  char v31; // [rsp+F4h] [rbp+6Bh]

  ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
  Length = GlobalIndentString.Length;
  v22 = "OpenVolumeHandles";
  v8 = ThreadLocalStoragePointer[tls_index];
  v9 = ++*(_WORD *)(v8 + 8);
  *(_QWORD *)(v8 + 16) = "OpenVolumeHandles";
  v10 = Length;
  if ( v9 < Length )
  {
    v10 = v9;
    Length = v9;
  }
  v24 = v10;
  v26 = 0;
  v27 = off_180047060;
  v25 = Length;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"OpenVolumeHandles");
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  IoStatusBlock = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.ObjectName = a1;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  v31 = 0;
  ThreadErrorMode = RtlGetThreadErrorMode();
  CThreadErrorMode::SetThreadErrorMode(&OldMode, ThreadErrorMode | 0x10);
  FileHandle = 0;
  v17 = 0;
  v18 = 0;
  v12 = NtOpenFile(&FileHandle, 0x1000A0u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
  if ( v12 >= 0 )
  {
    v19 = 0;
    v20 = 0;
    v21 = 0;
    v14 = NtOpenFile(&v19, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    if ( v14 >= 0 )
    {
      *a2 = (void *)CHandleT<void *,NtHandleTrait>::Detach(&v19);
      *a3 = (void *)CHandleT<void *,NtHandleTrait>::Detach(&FileHandle);
      v13 = 0;
      v23 = 0;
    }
    else
    {
      v13 = v14 | 0x10000000;
      v23 = v13;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Zd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
          (_DWORD)a1,
          v13);
      }
    }
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&v19);
  }
  else
  {
    v13 = v12 | 0x10000000;
    v23 = v13;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Zd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        (unsigned int)&WPP_ac7e02637b6a307e043befe010ba928c_Traceguids,
        (_DWORD)a1,
        v13);
    }
  }
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CThreadErrorMode::~CThreadErrorMode((CThreadErrorMode *)&OldMode);
  CHResultImp::~CHResultImp((CHResultImp *)&v22);
  return v13;
}

```

## disassembly

```asm
0x18000ea80  push    rbp
0x18000ea82  push    rbx
0x18000ea83  push    rsi
0x18000ea84  push    rdi
0x18000ea85  push    r13
0x18000ea87  push    r14
0x18000ea89  lea     rbp, [rsp-2Fh]
0x18000ea8e  sub     rsp, 0B8h
0x18000ea95  mov     rax, gs:58h
0x18000ea9e  mov     r14, rdx
0x18000eaa1  mov     r9d, cs:_tls_index
0x18000eaa8  mov     rdi, rcx
0x18000eaab  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18000eab2  mov     rsi, r8
0x18000eab5  mov     edx, 8
0x18000eaba  lea     r8, aOpenvolumehand; "OpenVolumeHandles"
0x18000eac1  mov     [rbp+57h+var_90], r8
0x18000eac5  mov     r10, [rax+r9*8]
0x18000eac9  mov     eax, 10h
0x18000eace  inc     word ptr [rdx+r10]
0x18000ead3  movzx   edx, word ptr [rdx+r10]
0x18000ead8  mov     [rax+r10], r8
0x18000eadc  cmp     dx, cx
0x18000eadf  movzx   eax, cx
0x18000eae2  cmovb   ax, dx
0x18000eae6  cmovb   cx, dx
0x18000eaea  mov     [rbp+57h+var_80], ax
0x18000eaee  xor     eax, eax
0x18000eaf0  mov     [rbp+57h+var_7C], eax
0x18000eaf3  mov     rax, cs:off_180047060; "                                       "...
0x18000eafa  mov     [rbp+57h+var_78], rax
0x18000eafe  mov     [rbp+57h+var_7E], cx
0x18000eb02  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb09  lea     r13, WPP_GLOBAL_Control
0x18000eb10  cmp     rcx, r13
0x18000eb13  jz      short loc_18000EB38
0x18000eb15  test    byte ptr [rcx+1Ch], 1
0x18000eb19  jz      short loc_18000EB38
0x18000eb1b  cmp     byte ptr [rcx+19h], 5
0x18000eb1f  jb      short loc_18000EB38
0x18000eb21  mov     rcx, [rcx+10h]; LoggerHandle
0x18000eb25  lea     r9, [rbp+57h+var_80]
0x18000eb29  mov     edx, 0Dh
0x18000eb2e  mov     qword ptr [rsp+0E0h+ShareAccess], r8; __int64
0x18000eb33  call    WPP_SF_aZs
0x18000eb38  xorps   xmm0, xmm0
0x18000eb3b  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000eb43  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000eb47  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000eb4f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000eb54  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x18000eb58  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x18000eb60  mov     [rbp+57h+arg_4], 0
0x18000eb64  call    cs:__imp_RtlGetThreadErrorMode
0x18000eb6a  or      eax, 10h
0x18000eb6d  lea     rcx, [rbp+57h+OldMode]; OldMode
0x18000eb71  mov     edx, eax; NewMode
0x18000eb73  call    ?SetThreadErrorMode@CThreadErrorMode@@QEAAJK@Z; CThreadErrorMode::SetThreadErrorMode(ulong)
0x18000eb78  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000eb7c  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x18000eb84  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000eb88  mov     [rbp+57h+FileHandle], 0
0x18000eb90  mov     edx, 1000A0h; DesiredAccess
0x18000eb95  mov     [rbp+57h+var_A8], 0
0x18000eb9c  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000eba0  mov     [rbp+57h+var_A4], 0
0x18000eba4  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18000ebac  call    cs:__imp_NtOpenFile
0x18000ebb2  mov     ebx, eax
0x18000ebb4  test    eax, eax
0x18000ebb6  jns     short loc_18000EC04
0x18000ebb8  bts     ebx, 1Ch
0x18000ebbc  mov     [rbp+57h+var_88], ebx
0x18000ebbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ebc6  cmp     rcx, r13
0x18000ebc9  jz      loc_18000ECAB
0x18000ebcf  test    byte ptr [rcx+1Ch], 1
0x18000ebd3  jz      loc_18000ECAB
0x18000ebd9  cmp     byte ptr [rcx+19h], 2
0x18000ebdd  jb      loc_18000ECAB
0x18000ebe3  mov     rcx, [rcx+10h]
0x18000ebe7  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000ebee  mov     edx, 1Bh
0x18000ebf3  mov     [rsp+0E0h+ShareAccess], ebx
0x18000ebf7  mov     r9, rdi
0x18000ebfa  call    WPP_SF_Zd
0x18000ebff  jmp     loc_18000ECAB
0x18000ec04  mov     [rsp+0E0h+OpenOptions], 60h ; '`'; OpenOptions
0x18000ec0c  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000ec10  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000ec14  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18000ec1c  mov     edx, 100080h; DesiredAccess
0x18000ec21  mov     [rbp+57h+var_A0], 0
0x18000ec29  lea     rcx, [rbp+57h+var_A0]; FileHandle
0x18000ec2d  mov     [rbp+57h+var_98], 0
0x18000ec34  mov     [rbp+57h+var_94], 0
0x18000ec38  call    cs:__imp_NtOpenFile
0x18000ec3e  mov     ebx, eax
0x18000ec40  test    eax, eax
0x18000ec42  jns     short loc_18000EC81
0x18000ec44  bts     ebx, 1Ch
0x18000ec48  mov     [rbp+57h+var_88], ebx
0x18000ec4b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ec52  cmp     rcx, r13
0x18000ec55  jz      short loc_18000ECA2
0x18000ec57  test    byte ptr [rcx+1Ch], 1
0x18000ec5b  jz      short loc_18000ECA2
0x18000ec5d  cmp     byte ptr [rcx+19h], 2
0x18000ec61  jb      short loc_18000ECA2
0x18000ec63  mov     rcx, [rcx+10h]
0x18000ec67  lea     r8, WPP_ac7e02637b6a307e043befe010ba928c_Traceguids
0x18000ec6e  mov     edx, 1Ch
0x18000ec73  mov     [rsp+0E0h+ShareAccess], ebx
0x18000ec77  mov     r9, rdi
0x18000ec7a  call    WPP_SF_Zd
0x18000ec7f  jmp     short loc_18000ECA2
0x18000ec81  lea     rcx, [rbp+57h+var_A0]
0x18000ec85  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18000ec8a  lea     rcx, [rbp+57h+FileHandle]
0x18000ec8e  mov     [r14], rax
0x18000ec91  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18000ec96  mov     [rsi], rax
0x18000ec99  xor     ebx, ebx
0x18000ec9b  mov     [rbp+57h+var_88], 0
0x18000eca2  lea     rcx, [rbp+57h+var_A0]
0x18000eca6  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18000ecab  lea     rcx, [rbp+57h+FileHandle]
0x18000ecaf  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18000ecb4  lea     rcx, [rbp+57h+OldMode]; this
0x18000ecb8  call    ??1CThreadErrorMode@@QEAA@XZ; CThreadErrorMode::~CThreadErrorMode(void)
0x18000ecbd  lea     rcx, [rbp+57h+var_90]; this
0x18000ecc1  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18000ecc6  mov     eax, ebx
0x18000ecc8  add     rsp, 0B8h
0x18000eccf  pop     r14
0x18000ecd1  pop     r13
0x18000ecd3  pop     rdi
0x18000ecd4  pop     rsi
0x18000ecd5  pop     rbx
0x18000ecd6  pop     rbp
0x18000ecd7  retn
```
