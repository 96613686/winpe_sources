# _lambda_488da5a65988c65ea4b6f74dbc66c10d_::operator()

- ea: `0x18001c1d8`
- end: `0x18001c598`
- name: `_lambda_488da5a65988c65ea4b6f74dbc66c10d_::operator()`
- size: `960`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001b87c`

## callees

- `0x1800032f8`
- `0x180006688`
- `0x1800088a4`
- `0x18000ef90`
- `0x180010460`
- `0x180012470`
- `0x18001712c`
- `0x18001c1d8`
- `0x18001e004`
- `0x180037620`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18001c305`
- `ntdll!NtOpenFile` at `0x18001c305`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_488da5a65988c65ea4b6f74dbc66c10d_::operator()(
        CDiskScanner **a1,
        const struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3)
{
  __int64 v6; // r8
  USHORT v7; // dx
  USHORT Length; // cx
  USHORT v9; // ax
  int i; // esi
  NTSTATUS v11; // eax
  int DeviceNumber; // r8d
  _QWORD *v13; // rcx
  int v14; // edx
  int v15; // r9d
  unsigned int v16; // esi
  int v18; // eax
  void *FileHandle; // [rsp+30h] [rbp-79h] BYREF
  int v20; // [rsp+38h] [rbp-71h]
  char v21; // [rsp+3Ch] [rbp-6Dh]
  _DISK_EXTENT v22; // [rsp+40h] [rbp-69h] BYREF
  const char *v23; // [rsp+58h] [rbp-51h] BYREF
  int v24; // [rsp+60h] [rbp-49h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-11h] BYREF
  struct _STORAGE_DEVICE_NUMBER_EX OutputBuffer; // [rsp+A8h] [rbp-1h] BYREF

  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v6 + 16) = "CDiskScanner::DrtDiskScanWork::<lambda_488da5a65988c65ea4b6f74dbc66c10d>::operator ()";
  v23 = "CDiskScanner::DrtDiskScanWork::<lambda_488da5a65988c65ea4b6f74dbc66c10d>::operator ()";
  v7 = ++*(_WORD *)(v6 + 8);
  Length = GlobalIndentString.Length;
  v9 = GlobalIndentString.Length;
  if ( v7 < GlobalIndentString.Length )
    v9 = *(_WORD *)(v6 + 8);
  LOWORD(v22.DiskNumber) = v9;
  if ( v7 < GlobalIndentString.Length )
    Length = v7;
  HIWORD(v22.DiskNumber) = Length;
  *(&v22.DiskNumber + 1) = 0;
  v22.StartingOffset.QuadPart = (LONGLONG)off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (__int64)"CDiskScanner::DrtDiskScanWork::<lambda_488da5a65988c65ea4b6f74dbc66c10d>::operator ()");
  }
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a3;
  *(_QWORD *)&ObjectAttributes.Attributes = 192;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  FileHandle = 0;
  v20 = 0;
  v21 = 0;
  for ( i = 32; ; i = 0 )
  {
    v11 = NtOpenFile(&FileHandle, i | 0x100080, &ObjectAttributes, &IoStatusBlock, 7u, 0x60u);
    if ( v11 >= 0 )
      break;
    if ( !i )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *((_DWORD *)*a1 + 4),
          (__int64)a3,
          v11);
      }
      goto LABEL_42;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *((_DWORD *)*a1 + 4),
        (__int64)a3,
        v11);
    }
  }
  memset(&OutputBuffer, 0, sizeof(OutputBuffer));
  DeviceNumber = StorageGetDeviceNumber(FileHandle, &OutputBuffer);
  if ( DeviceNumber < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v14 = 35;
    goto LABEL_25;
  }
  v15 = *((_DWORD *)*a1 + 4);
  if ( OutputBuffer.DeviceNumber != v15 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v14 = 36;
    goto LABEL_41;
  }
  memset(&v22, 0, sizeof(v22));
  DeviceNumber = QueryVolumeDiskExtent(FileHandle, &v22);
  v24 = DeviceNumber;
  if ( DeviceNumber < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v14 = 37;
LABEL_25:
    v15 = *((_DWORD *)*a1 + 4);
LABEL_41:
    WPP_SF_DZd(
      v13[2],
      v14,
      (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      v15,
      (__int64)a3,
      DeviceNumber);
LABEL_42:
    v24 = 0;
    v16 = 0;
    goto LABEL_43;
  }
  v15 = *((_DWORD *)*a1 + 4);
  if ( v22.DiskNumber != v15 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_42;
    }
    v14 = 38;
    goto LABEL_41;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      v15,
      (__int64)a3);
  }
  *(_BYTE *)a1[1] = 1;
  v18 = CDiskScanner::QueueVolume(*a1, a2, &OutputBuffer, &v22);
  v16 = v18;
  v24 = v18;
  if ( v18 >= 0 )
    goto LABEL_42;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DZd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      *((_DWORD *)*a1 + 4),
      (__int64)a3,
      v18);
  }
LABEL_43:
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CHResultImp::~CHResultImp((CHResultImp *)&v23);
  return v16;
}

```

## disassembly

```asm
0x18001c1d8  mov     [rsp-8+arg_18], rbx
0x18001c1dd  push    rbp
0x18001c1de  push    rsi
0x18001c1df  push    rdi
0x18001c1e0  push    r13
0x18001c1e2  push    r14
0x18001c1e4  lea     rbp, [rsp-37h]
0x18001c1e9  sub     rsp, 0E0h
0x18001c1f0  mov     rax, cs:__security_cookie
0x18001c1f7  xor     rax, rsp
0x18001c1fa  mov     [rbp+57h+var_30], rax
0x18001c1fe  mov     rdi, r8
0x18001c201  mov     r14, rdx
0x18001c204  mov     rbx, rcx
0x18001c207  mov     edx, cs:_tls_index
0x18001c20d  mov     rax, gs:58h
0x18001c216  mov     r8, [rax+rdx*8]
0x18001c21a  mov     eax, 10h
0x18001c21f  lea     r9, aCdiskscannerDr_0; "CDiskScanner::DrtDiskScanWork::<lambda_"...
0x18001c226  mov     [rax+r8], r9
0x18001c22a  mov     [rbp+57h+var_A8], r9
0x18001c22e  mov     edx, 8
0x18001c233  inc     word ptr [rdx+r8]
0x18001c238  movzx   edx, word ptr [rdx+r8]
0x18001c23d  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001c244  movzx   eax, cx
0x18001c247  cmp     dx, cx
0x18001c24a  cmovb   ax, dx
0x18001c24e  mov     word ptr [rbp+57h+var_C0.DiskNumber], ax
0x18001c252  cmovb   cx, dx
0x18001c256  mov     word ptr [rbp+57h+var_C0.DiskNumber+2], cx
0x18001c25a  xor     eax, eax
0x18001c25c  mov     dword ptr [rbp+57h+var_C0+4], eax
0x18001c25f  mov     rax, cs:off_180047060; "                                       "...
0x18001c266  mov     qword ptr [rbp+57h+var_C0.StartingOffset], rax
0x18001c26a  lea     r13, WPP_GLOBAL_Control
0x18001c271  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c278  cmp     rcx, r13
0x18001c27b  jz      short loc_18001C2A1
0x18001c27d  test    byte ptr [rcx+1Ch], 1
0x18001c281  jz      short loc_18001C2A1
0x18001c283  cmp     byte ptr [rcx+19h], 5
0x18001c287  jb      short loc_18001C2A1
0x18001c289  mov     edx, 0Dh
0x18001c28e  mov     qword ptr [rsp+100h+ShareAccess], r9; __int64
0x18001c293  lea     r9, [rbp+57h+var_C0]
0x18001c297  mov     rcx, [rcx+10h]; LoggerHandle
0x18001c29b  call    WPP_SF_aZs
0x18001c2a0  nop
0x18001c2a1  xorps   xmm0, xmm0
0x18001c2a4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001c2a8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001c2b0  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18001c2b8  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x18001c2bc  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0C0h
0x18001c2c4  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001c2c9  mov     [rbp+57h+FileHandle], 0
0x18001c2d1  mov     [rbp+57h+var_C8], 0
0x18001c2d8  mov     [rbp+57h+var_C4], 0
0x18001c2dc  mov     esi, 20h ; ' '
0x18001c2e1  mov     edx, esi
0x18001c2e3  or      edx, 100080h; DesiredAccess
0x18001c2e9  mov     [rsp+100h+OpenOptions], 60h ; '`'; OpenOptions
0x18001c2f1  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x18001c2f9  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001c2fd  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001c301  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001c305  call    cs:__imp_NtOpenFile
0x18001c30b  test    eax, eax
0x18001c30d  jns     loc_18001C393
0x18001c313  bts     eax, 1Ch
0x18001c317  test    esi, esi
0x18001c319  jz      short loc_18001C35A
0x18001c31b  xor     esi, esi
0x18001c31d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c324  cmp     rcx, r13
0x18001c327  jz      short loc_18001C2E1
0x18001c329  test    byte ptr [rcx+1Ch], 1
0x18001c32d  jz      short loc_18001C2E1
0x18001c32f  cmp     byte ptr [rcx+19h], 2
0x18001c333  jb      short loc_18001C2E1
0x18001c335  mov     r9, [rbx]
0x18001c338  lea     edx, [rsi+21h]
0x18001c33b  mov     [rsp+100h+OpenOptions], eax
0x18001c33f  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x18001c344  mov     r9d, [r9+10h]
0x18001c348  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001c34f  mov     rcx, [rcx+10h]
0x18001c353  call    WPP_SF_DZd
0x18001c358  jmp     short loc_18001C2E1
0x18001c35a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c361  cmp     rcx, r13
0x18001c364  jz      loc_18001C4AF
0x18001c36a  test    byte ptr [rcx+1Ch], 1
0x18001c36e  jz      loc_18001C4AF
0x18001c374  cmp     byte ptr [rcx+19h], 2
0x18001c378  jb      loc_18001C4AF
0x18001c37e  mov     r9, [rbx]
0x18001c381  mov     edx, 22h ; '"'
0x18001c386  mov     [rsp+100h+OpenOptions], eax
0x18001c38a  mov     r9d, [r9+10h]
0x18001c38e  jmp     loc_18001C49A
0x18001c393  xorps   xmm0, xmm0
0x18001c396  xor     eax, eax
0x18001c398  movups  [rbp+57h+OutputBuffer], xmm0
0x18001c39c  movups  [rbp+57h+var_48], xmm0
0x18001c3a0  mov     [rbp+57h+var_38], rax
0x18001c3a4  lea     rdx, [rbp+57h+OutputBuffer]; OutputBuffer
0x18001c3a8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001c3ac  call    ?StorageGetDeviceNumber@@YAJPEAXPEAU_STORAGE_DEVICE_NUMBER_EX@@@Z; StorageGetDeviceNumber(void *,_STORAGE_DEVICE_NUMBER_EX *)
0x18001c3b1  mov     r8d, eax
0x18001c3b4  test    eax, eax
0x18001c3b6  jns     short loc_18001C3ED
0x18001c3b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3bf  cmp     rcx, r13
0x18001c3c2  jz      loc_18001C4AF
0x18001c3c8  test    byte ptr [rcx+1Ch], 1
0x18001c3cc  jz      loc_18001C4AF
0x18001c3d2  cmp     byte ptr [rcx+19h], 2
0x18001c3d6  jb      loc_18001C4AF
0x18001c3dc  mov     edx, 23h ; '#'
0x18001c3e1  mov     r9, [rbx]
0x18001c3e4  mov     r9d, [r9+10h]
0x18001c3e8  jmp     loc_18001C495
0x18001c3ed  mov     rax, [rbx]
0x18001c3f0  mov     r9d, [rax+10h]
0x18001c3f4  cmp     dword ptr [rbp+57h+var_48], r9d
0x18001c3f8  jz      short loc_18001C425
0x18001c3fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c401  cmp     rcx, r13
0x18001c404  jz      loc_18001C4AF
0x18001c40a  test    byte ptr [rcx+1Ch], 1
0x18001c40e  jz      loc_18001C4AF
0x18001c414  cmp     byte ptr [rcx+19h], 2
0x18001c418  jb      loc_18001C4AF
0x18001c41e  mov     edx, 24h ; '$'
0x18001c423  jmp     short loc_18001C495
0x18001c425  xorps   xmm0, xmm0
0x18001c428  xor     eax, eax
0x18001c42a  movups  xmmword ptr [rbp+57h+var_C0.DiskNumber], xmm0
0x18001c42e  mov     qword ptr [rbp+57h+var_C0.ExtentLength], rax
0x18001c432  lea     rdx, [rbp+57h+var_C0]; struct _DISK_EXTENT *
0x18001c436  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001c43a  call    ?QueryVolumeDiskExtent@@YAJPEAXPEAU_DISK_EXTENT@@@Z; QueryVolumeDiskExtent(void *,_DISK_EXTENT *)
0x18001c43f  mov     r8d, eax
0x18001c442  mov     [rbp+57h+var_A0], eax
0x18001c445  test    eax, eax
0x18001c447  jns     short loc_18001C46B
0x18001c449  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c450  cmp     rcx, r13
0x18001c453  jz      short loc_18001C4AF
0x18001c455  test    byte ptr [rcx+1Ch], 1
0x18001c459  jz      short loc_18001C4AF
0x18001c45b  cmp     byte ptr [rcx+19h], 2
0x18001c45f  jb      short loc_18001C4AF
0x18001c461  mov     edx, 25h ; '%'
0x18001c466  jmp     loc_18001C3E1
0x18001c46b  mov     rax, [rbx]
0x18001c46e  mov     r9d, [rax+10h]
0x18001c472  cmp     [rbp+57h+var_C0.DiskNumber], r9d
0x18001c476  jz      short loc_18001C4F0
0x18001c478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c47f  cmp     rcx, r13
0x18001c482  jz      short loc_18001C4AF
0x18001c484  test    byte ptr [rcx+1Ch], 1
0x18001c488  jz      short loc_18001C4AF
0x18001c48a  cmp     byte ptr [rcx+19h], 2
0x18001c48e  jb      short loc_18001C4AF
0x18001c490  mov     edx, 26h ; '&'
0x18001c495  mov     [rsp+100h+OpenOptions], r8d
0x18001c49a  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x18001c49f  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001c4a6  mov     rcx, [rcx+10h]
0x18001c4aa  call    WPP_SF_DZd
0x18001c4af  mov     [rbp+57h+var_A0], 0
0x18001c4b6  xor     esi, esi
0x18001c4b8  lea     rcx, [rbp+57h+FileHandle]
0x18001c4bc  call    ??1?$CHandleT@PEAXUNtHandleTrait@@@@QEAA@XZ; CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(void)
0x18001c4c1  nop
0x18001c4c2  lea     rcx, [rbp+57h+var_A8]; this
0x18001c4c6  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001c4cb  mov     eax, esi
0x18001c4cd  mov     rcx, [rbp+57h+var_30]
0x18001c4d1  xor     rcx, rsp; StackCookie
0x18001c4d4  call    __security_check_cookie
0x18001c4d9  mov     rbx, [rsp+100h+arg_18]
0x18001c4e1  add     rsp, 0E0h
0x18001c4e8  pop     r14
0x18001c4ea  pop     r13
0x18001c4ec  pop     rdi
0x18001c4ed  pop     rsi
0x18001c4ee  pop     rbp
0x18001c4ef  retn
0x18001c4f0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c4f7  cmp     rcx, r13
0x18001c4fa  jz      short loc_18001C522
0x18001c4fc  test    byte ptr [rcx+1Ch], 1
0x18001c500  jz      short loc_18001C522
0x18001c502  cmp     byte ptr [rcx+19h], 4
0x18001c506  jb      short loc_18001C522
0x18001c508  mov     edx, 27h ; '''
0x18001c50d  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x18001c512  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001c519  mov     rcx, [rcx+10h]
0x18001c51d  call    WPP_SF_DZ
0x18001c522  mov     rax, [rbx+8]
0x18001c526  mov     byte ptr [rax], 1
0x18001c529  lea     r9, [rbp+57h+var_C0]; struct _DISK_EXTENT *
0x18001c52d  lea     r8, [rbp+57h+OutputBuffer]; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001c531  mov     rdx, r14; struct _UNICODE_STRING *
0x18001c534  mov     rcx, [rbx]; this
0x18001c537  call    ?QueueVolume@CDiskScanner@@QEAAJPEBU_UNICODE_STRING@@AEBU_STORAGE_DEVICE_NUMBER_EX@@AEBU_DISK_EXTENT@@@Z; CDiskScanner::QueueVolume(_UNICODE_STRING const *,_STORAGE_DEVICE_NUMBER_EX const &,_DISK_EXTENT const &)
0x18001c53c  mov     esi, eax
0x18001c53e  mov     [rbp+57h+var_A0], eax
0x18001c541  test    eax, eax
0x18001c543  jns     loc_18001C4AF
0x18001c549  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c550  cmp     rcx, r13
0x18001c553  jz      loc_18001C4B8
0x18001c559  test    byte ptr [rcx+1Ch], 1
0x18001c55d  jz      loc_18001C4B8
0x18001c563  cmp     byte ptr [rcx+19h], 2
0x18001c567  jb      loc_18001C4B8
0x18001c56d  mov     r9, [rbx]
0x18001c570  mov     edx, 28h ; '('
0x18001c575  mov     [rsp+100h+OpenOptions], eax
0x18001c579  mov     qword ptr [rsp+100h+ShareAccess], rdi
0x18001c57e  mov     r9d, [r9+10h]
0x18001c582  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001c589  mov     rcx, [rcx+10h]
0x18001c58d  call    WPP_SF_DZd
0x18001c592  jmp     loc_18001C4B8
```
