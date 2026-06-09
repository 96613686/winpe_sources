# CDiskPnpMonitor::NewDiskDeviceHandler(CDeviceNotifyData *,CDiskPnpMonitor::NewDiskDeviceHandlerType)

- ea: `0x18001a014`
- end: `0x18001a4f4`
- name: `?NewDiskDeviceHandler@CDiskPnpMonitor@@AEAAJPEAVCDeviceNotifyData@@W4NewDiskDeviceHandlerType@1@@Z`
- size: `1248`
- prototype: `__int64 __fastcall(_QWORD **, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180018f18`
- `0x180019d5c`

## callees

- `0x1800032f8`
- `0x180006498`
- `0x1800064d8`
- `0x180006584`
- `0x180006688`
- `0x180009088`
- `0x1800092ec`
- `0x180010460`
- `0x1800128c8`
- `0x180013720`
- `0x18001a014`
- `0x18001b288`
- `0x18001b2ec`
- `0x1800375ee`
- `0x180037620`
- `0x180039010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x18001a16c`
- `KERNEL32!CreateFileW` at `0x18001a1b8`
- `KERNEL32!CreateFileW` at `0x18001a16c`
- `KERNEL32!CreateFileW` at `0x18001a1b8`
- `KERNEL32!GetLastError` at `0x18001a17f`
- `KERNEL32!GetLastError` at `0x18001a1c7`
- `KERNEL32!GetLastError` at `0x18001a17f`
- `KERNEL32!GetLastError` at `0x18001a1c7`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001a3fe`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x18001a3fe`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a40f`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x18001a40f`

## pseudocode

```c
__int64 __fastcall CDiskPnpMonitor::NewDiskDeviceHandler(_QWORD **a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // r9
  USHORT v7; // dx
  USHORT Length; // cx
  USHORT v9; // ax
  PVOID *v10; // rcx
  __int64 v11; // rdx
  const WCHAR *v12; // r14
  HANDLE FileW; // rdi
  signed int LastError; // eax
  signed int v15; // eax
  unsigned int v16; // ebx
  int DeviceNumber; // eax
  unsigned int v18; // esi
  int DiskAttributes; // eax
  int v20; // r8d
  char v21; // si
  PVOID *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, HANDLE, const WCHAR *, __int64); // rcx
  __int64 v24; // r9
  __int64 (__fastcall **v25)(_QWORD, HANDLE, const WCHAR *, __int64); // rax
  int v26; // eax
  CONFIGRET v27; // eax
  __int64 v28; // rdx
  __int64 v29; // r8
  signed int v30; // eax
  signed int v31; // edi
  int hTemplateFile; // [rsp+30h] [rbp-D0h]
  int v34; // [rsp+38h] [rbp-C8h]
  int v35; // [rsp+40h] [rbp-C0h]
  HANDLE v36; // [rsp+50h] [rbp-B0h] BYREF
  char *v37; // [rsp+58h] [rbp-A8h]
  const char *v38; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v39; // [rsp+68h] [rbp-98h]
  int v40; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v41[4]; // [rsp+74h] [rbp-8Ch] BYREF
  int v42; // [rsp+78h] [rbp-88h]
  HANDLE v43; // [rsp+80h] [rbp-80h]

  v6 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v6 + 16) = "CDiskPnpMonitor::NewDiskDeviceHandler";
  v38 = "CDiskPnpMonitor::NewDiskDeviceHandler";
  v7 = ++*(_WORD *)(v6 + 8);
  Length = GlobalIndentString.Length;
  v9 = GlobalIndentString.Length;
  if ( v7 < GlobalIndentString.Length )
    v9 = *(_WORD *)(v6 + 8);
  LOWORD(v36) = v9;
  if ( v7 < GlobalIndentString.Length )
    Length = v7;
  WORD1(v36) = Length;
  HIDWORD(v36) = 0;
  v37 = off_180047060;
  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskPnpMonitor::NewDiskDeviceHandler");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a3 <= 1 )
  {
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 || *((_BYTE *)v10 + 25) < 4u )
      goto LABEL_19;
    v11 = 41;
  }
  else
  {
    if ( v10 == &WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 || *((_BYTE *)v10 + 25) < 4u )
      goto LABEL_19;
    v11 = 42;
  }
  WPP_SF_S(v10[2], v11, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids, *(_QWORD *)(a2 + 72));
LABEL_19:
  v12 = *(const WCHAR **)(a2 + 72);
  FileW = CreateFileW(v12, 0xC0000000, 7u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError != -2147024891 || (FileW = CreateFileW(v12, 0x80u, 7u, 0, 3u, 0, 0), FileW == (HANDLE)-1LL) )
    {
      v15 = GetLastError();
      v16 = v15;
      if ( v15 > 0 )
        v16 = (unsigned __int16)v15 | 0x80070000;
      v39 = v16;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)&WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
          (_DWORD)v12,
          v16);
      }
      goto LABEL_68;
    }
  }
  v36 = FileW;
  LODWORD(v37) = 0;
  BYTE4(v37) = 0;
  DeviceNumber = StorageGetDeviceNumber(FileW, (PVOID)(a2 + 16));
  v18 = DeviceNumber;
  v39 = DeviceNumber;
  if ( DeviceNumber < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        44,
        &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
        (unsigned int)DeviceNumber);
    }
    goto LABEL_35;
  }
  DiskAttributes = DiskGetDiskAttributes(
                     (const struct _STORAGE_DEVICE_NUMBER_EX *)(a2 + 16),
                     FileW,
                     (struct _GET_DISK_ATTRIBUTES *)(a2 + 56));
  v18 = DiskAttributes;
  v39 = DiskAttributes;
  if ( DiskAttributes < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        45,
        &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
        *(unsigned int *)(a2 + 32),
        DiskAttributes);
    }
    goto LABEL_35;
  }
  v21 = *(_DWORD *)(a2 + 64) & 1;
  v22 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v35 = *(_DWORD *)(a2 + 64);
    v34 = *(_DWORD *)(a2 + 24);
    hTemplateFile = *(_DWORD *)(a2 + 28);
    WPP_SF_LD_guid_LLL(*((_QWORD *)WPP_GLOBAL_Control + 2), a2 + 36, v20, a3, *(_DWORD *)(a2 + 32), a2 + 36);
    v22 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v21 )
  {
    if ( v22 != &WPP_GLOBAL_Control && (*((_BYTE *)v22 + 28) & 1) != 0 && *((_BYTE *)v22 + 25) >= 4u )
      WPP_SF_d(v22[2], 47, &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids, *(unsigned int *)(a2 + 32));
  }
  else
  {
    v23 = (__int64 (__fastcall ***)(_QWORD, HANDLE, const WCHAR *, __int64))*a1;
    v24 = a2 + 16;
    v25 = (__int64 (__fastcall **)(_QWORD, HANDLE, const WCHAR *, __int64))**a1;
    if ( a3 <= 1 )
      v26 = (*v25)(v23, FileW, v12, v24);
    else
      v26 = v25[1](v23, FileW, v12, v24);
    v39 = v26;
    v18 = v26;
    if ( v26 < 0 )
    {
LABEL_35:
      CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&v36);
      v16 = v18;
      goto LABEL_68;
    }
  }
  v40 = 416;
  memset_0(v41, 0, 0x19Cu);
  v42 = 1;
  v43 = FileW;
  v27 = CM_Register_Notification(&v40, a2, &CDiskPnpMonitor::DeviceNotifyCallback, a2 + 88);
  if ( !v27 )
    goto LABEL_65;
  v30 = CM_MapCrToWin32Err(v27, 0xDu);
  v31 = v30;
  if ( v30 > 0 )
    v31 = (unsigned __int16)v30 | 0x80070000;
  v39 = v31;
  if ( v31 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        &WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids,
        *(unsigned int *)(a2 + 32),
        v31);
    }
    CHandleT<void *,NtHandleTrait>::Detach(a2 + 88);
    CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&v36);
    v16 = v31;
  }
  else
  {
LABEL_65:
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dqq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v29,
        *(unsigned int *)(a2 + 32),
        a2,
        *(_QWORD *)(a2 + 88),
        hTemplateFile,
        v34,
        v35);
    }
    v39 = 0;
    CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(&v36);
    v16 = 0;
  }
LABEL_68:
  CHResultImp::~CHResultImp((CHResultImp *)&v38);
  return v16;
}

```

## disassembly

```asm
0x18001a014  mov     [rsp-8+arg_18], rbx
0x18001a019  push    rbp
0x18001a01a  push    rsi
0x18001a01b  push    rdi
0x18001a01c  push    r12
0x18001a01e  push    r13
0x18001a020  push    r14
0x18001a022  push    r15
0x18001a024  lea     rbp, [rsp-120h]
0x18001a02c  sub     rsp, 220h
0x18001a033  mov     rax, cs:__security_cookie
0x18001a03a  xor     rax, rsp
0x18001a03d  mov     [rbp+150h+var_40], rax
0x18001a044  mov     r12d, r8d
0x18001a047  mov     rbx, rdx
0x18001a04a  mov     r13, rcx
0x18001a04d  mov     edx, cs:_tls_index
0x18001a053  mov     rax, gs:58h
0x18001a05c  mov     r9, [rax+rdx*8]
0x18001a060  mov     eax, 10h
0x18001a065  lea     r8, aCdiskpnpmonito_4; "CDiskPnpMonitor::NewDiskDeviceHandler"
0x18001a06c  mov     [rax+r9], r8
0x18001a070  mov     [rsp+250h+var_1F0], r8
0x18001a075  mov     edx, 8
0x18001a07a  mov     r15d, 1
0x18001a080  add     [rdx+r9], r15w
0x18001a085  movzx   edx, word ptr [rdx+r9]
0x18001a08a  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001a091  movzx   eax, cx
0x18001a094  cmp     dx, cx
0x18001a097  cmovb   ax, dx
0x18001a09b  mov     word ptr [rsp+250h+var_200], ax
0x18001a0a0  cmovb   cx, dx
0x18001a0a4  mov     word ptr [rsp+250h+var_200+2], cx
0x18001a0a9  xor     eax, eax
0x18001a0ab  mov     dword ptr [rsp+250h+var_200+4], eax
0x18001a0af  mov     rax, cs:off_180047060; "                                       "...
0x18001a0b6  mov     [rsp+250h+var_1F8], rax
0x18001a0bb  lea     rax, WPP_GLOBAL_Control
0x18001a0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0c9  cmp     rcx, rax
0x18001a0cc  jz      short loc_18001A0FF
0x18001a0ce  test    [rcx+1Ch], r15b
0x18001a0d2  jz      short loc_18001A0FF
0x18001a0d4  cmp     byte ptr [rcx+19h], 5
0x18001a0d8  jb      short loc_18001A0FF
0x18001a0da  lea     edx, [r15+0Ch]
0x18001a0de  mov     qword ptr [rsp+250h+dwCreationDisposition], r8; __int64
0x18001a0e3  lea     r9, [rsp+250h+var_200]
0x18001a0e8  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a0ec  call    WPP_SF_aZs
0x18001a0f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a0f8  lea     rax, WPP_GLOBAL_Control
0x18001a0ff  cmp     r12d, r15d
0x18001a102  jbe     short loc_18001A11C
0x18001a104  cmp     rcx, rax
0x18001a107  jz      short loc_18001A146
0x18001a109  test    [rcx+1Ch], r15b
0x18001a10d  jz      short loc_18001A146
0x18001a10f  cmp     byte ptr [rcx+19h], 4
0x18001a113  jb      short loc_18001A146
0x18001a115  mov     edx, 2Ah ; '*'
0x18001a11a  jmp     short loc_18001A132
0x18001a11c  cmp     rcx, rax
0x18001a11f  jz      short loc_18001A146
0x18001a121  test    [rcx+1Ch], r15b
0x18001a125  jz      short loc_18001A146
0x18001a127  cmp     byte ptr [rcx+19h], 4
0x18001a12b  jb      short loc_18001A146
0x18001a12d  mov     edx, 29h ; ')'
0x18001a132  mov     r9, [rbx+48h]
0x18001a136  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a13d  mov     rcx, [rcx+10h]
0x18001a141  call    WPP_SF_S
0x18001a146  mov     r14, [rbx+48h]
0x18001a14a  xor     esi, esi
0x18001a14c  mov     [rsp+250h+hTemplateFile], rsi; hTemplateFile
0x18001a151  mov     [rsp+250h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001a155  mov     [rsp+250h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a15d  xor     r9d, r9d; lpSecurityAttributes
0x18001a160  mov     edx, 0C0000000h; dwDesiredAccess
0x18001a165  lea     r8d, [rsi+7]; dwShareMode
0x18001a169  mov     rcx, r14; lpFileName
0x18001a16c  call    cs:__imp_CreateFileW
0x18001a172  mov     rdi, rax
0x18001a175  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a179  jnz     loc_18001A22C
0x18001a17f  call    cs:__imp_GetLastError
0x18001a185  test    eax, eax
0x18001a187  jle     short loc_18001A191
0x18001a189  movzx   eax, ax
0x18001a18c  or      eax, 80070000h
0x18001a191  cmp     eax, 80070005h
0x18001a196  jnz     short loc_18001A1C7
0x18001a198  mov     [rsp+250h+hTemplateFile], rsi; hTemplateFile
0x18001a19d  mov     [rsp+250h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18001a1a1  mov     [rsp+250h+dwCreationDisposition], 3; dwCreationDisposition
0x18001a1a9  xor     r9d, r9d; lpSecurityAttributes
0x18001a1ac  mov     edx, 80h; dwDesiredAccess
0x18001a1b1  lea     r8d, [r9+7]; dwShareMode
0x18001a1b5  mov     rcx, r14; lpFileName
0x18001a1b8  call    cs:__imp_CreateFileW
0x18001a1be  mov     rdi, rax
0x18001a1c1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a1c5  jnz     short loc_18001A22C
0x18001a1c7  call    cs:__imp_GetLastError
0x18001a1cd  mov     ebx, eax
0x18001a1cf  test    eax, eax
0x18001a1d1  jle     short loc_18001A1DC
0x18001a1d3  movzx   ebx, ax
0x18001a1d6  or      ebx, 80070000h
0x18001a1dc  mov     [rsp+250h+var_1E8], ebx
0x18001a1e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a1e7  lea     rdx, WPP_GLOBAL_Control
0x18001a1ee  cmp     rcx, rdx
0x18001a1f1  jz      loc_18001A4BE
0x18001a1f7  test    [rcx+1Ch], r15b
0x18001a1fb  jz      loc_18001A4BE
0x18001a201  cmp     byte ptr [rcx+19h], 2
0x18001a205  jb      loc_18001A4BE
0x18001a20b  mov     edx, 2Bh ; '+'
0x18001a210  mov     [rsp+250h+dwCreationDisposition], ebx
0x18001a214  mov     r9, r14
0x18001a217  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a21e  mov     rcx, [rcx+10h]
0x18001a222  call    WPP_SF_Sd
0x18001a227  jmp     loc_18001A4BE
0x18001a22c  mov     [rsp+250h+var_200], rdi
0x18001a231  mov     dword ptr [rsp+250h+var_1F8], esi
0x18001a235  mov     byte ptr [rsp+250h+var_1F8+4], sil
0x18001a23a  lea     r15, [rbx+10h]
0x18001a23e  mov     rdx, r15; OutputBuffer
0x18001a241  mov     rcx, rdi; Handle
0x18001a244  call    ?StorageGetDeviceNumber@@YAJPEAXPEAU_STORAGE_DEVICE_NUMBER_EX@@@Z; StorageGetDeviceNumber(void *,_STORAGE_DEVICE_NUMBER_EX *)
0x18001a249  mov     esi, eax
0x18001a24b  mov     [rsp+250h+var_1E8], eax
0x18001a24f  test    eax, eax
0x18001a251  jns     short loc_18001A29C
0x18001a253  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a25a  lea     rdx, WPP_GLOBAL_Control
0x18001a261  cmp     rcx, rdx
0x18001a264  jz      short loc_18001A28B
0x18001a266  test    byte ptr [rcx+1Ch], 1
0x18001a26a  jz      short loc_18001A28B
0x18001a26c  cmp     byte ptr [rcx+19h], 2
0x18001a270  jb      short loc_18001A28B
0x18001a272  mov     edx, 2Ch ; ','
0x18001a277  mov     r9d, eax
0x18001a27a  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a281  mov     rcx, [rcx+10h]
0x18001a285  call    WPP_SF_d
0x18001a28a  nop
0x18001a28b  lea     rcx, [rsp+250h+var_200]
0x18001a290  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x18001a295  mov     ebx, esi
0x18001a297  jmp     loc_18001A4BE
0x18001a29c  lea     r8, [rbx+38h]; struct _GET_DISK_ATTRIBUTES *
0x18001a2a0  mov     rdx, rdi; void *
0x18001a2a3  mov     rcx, r15; struct _STORAGE_DEVICE_NUMBER_EX *
0x18001a2a6  call    ?DiskGetDiskAttributes@@YAJPEBU_STORAGE_DEVICE_NUMBER_EX@@PEAXPEAU_GET_DISK_ATTRIBUTES@@@Z; DiskGetDiskAttributes(_STORAGE_DEVICE_NUMBER_EX const *,void *,_GET_DISK_ATTRIBUTES *)
0x18001a2ab  mov     esi, eax
0x18001a2ad  mov     [rsp+250h+var_1E8], eax
0x18001a2b1  test    eax, eax
0x18001a2b3  jns     short loc_18001A2F3
0x18001a2b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a2bc  lea     rdx, WPP_GLOBAL_Control
0x18001a2c3  cmp     rcx, rdx
0x18001a2c6  jz      short loc_18001A28B
0x18001a2c8  test    byte ptr [rcx+1Ch], 1
0x18001a2cc  jz      short loc_18001A28B
0x18001a2ce  cmp     byte ptr [rcx+19h], 2
0x18001a2d2  jb      short loc_18001A28B
0x18001a2d4  mov     edx, 2Dh ; '-'
0x18001a2d9  mov     [rsp+250h+dwCreationDisposition], eax
0x18001a2dd  mov     r9d, [rbx+20h]
0x18001a2e1  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a2e8  mov     rcx, [rcx+10h]
0x18001a2ec  call    WPP_SF_Dd
0x18001a2f1  jmp     short loc_18001A28B
0x18001a2f3  mov     eax, [rbx+40h]
0x18001a2f6  mov     sil, al
0x18001a2f9  and     sil, 1
0x18001a2fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a304  lea     rdx, WPP_GLOBAL_Control
0x18001a30b  cmp     rcx, rdx
0x18001a30e  jz      short loc_18001A351
0x18001a310  test    byte ptr [rcx+1Ch], 1
0x18001a314  jz      short loc_18001A351
0x18001a316  cmp     byte ptr [rcx+19h], 4
0x18001a31a  jb      short loc_18001A351
0x18001a31c  lea     rdx, [rbx+24h]
0x18001a320  mov     [rsp+250h+var_210], eax
0x18001a324  mov     eax, [rbx+18h]
0x18001a327  mov     [rsp+250h+var_218], eax
0x18001a32b  mov     eax, [rbx+1Ch]
0x18001a32e  mov     dword ptr [rsp+250h+hTemplateFile], eax
0x18001a332  mov     qword ptr [rsp+250h+dwFlagsAndAttributes], rdx
0x18001a337  mov     eax, [rbx+20h]
0x18001a33a  mov     [rsp+250h+dwCreationDisposition], eax
0x18001a33e  mov     r9d, r12d
0x18001a341  mov     rcx, [rcx+10h]
0x18001a345  call    WPP_SF_LD_guid_LLL
0x18001a34a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a351  test    sil, sil
0x18001a354  jz      short loc_18001A389
0x18001a356  lea     r14, WPP_GLOBAL_Control
0x18001a35d  cmp     rcx, r14
0x18001a360  jz      short loc_18001A3C2
0x18001a362  test    byte ptr [rcx+1Ch], 1
0x18001a366  jz      short loc_18001A3C2
0x18001a368  cmp     byte ptr [rcx+19h], 4
0x18001a36c  jb      short loc_18001A3C2
0x18001a36e  mov     edx, 2Fh ; '/'
0x18001a373  mov     r9d, [rbx+20h]
0x18001a377  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a37e  mov     rcx, [rcx+10h]
0x18001a382  call    WPP_SF_d
0x18001a387  jmp     short loc_18001A3C2
0x18001a389  mov     rcx, [r13+0]
0x18001a38d  mov     r9, r15
0x18001a390  mov     r8, r14
0x18001a393  mov     rdx, rdi
0x18001a396  mov     rax, [rcx]
0x18001a399  cmp     r12d, 1
0x18001a39d  jbe     short loc_18001A3A5
0x18001a39f  mov     rax, [rax+8]
0x18001a3a3  jmp     short loc_18001A3A8
0x18001a3a5  mov     rax, [rax]
0x18001a3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3ad  mov     [rsp+250h+var_1E8], eax
0x18001a3b1  mov     esi, eax
0x18001a3b3  test    eax, eax
0x18001a3b5  js      loc_18001A28B
0x18001a3bb  lea     r14, WPP_GLOBAL_Control
0x18001a3c2  mov     [rsp+250h+var_1E0], 1A0h
0x18001a3ca  xor     edx, edx; Val
0x18001a3cc  mov     r8d, 19Ch; Size
0x18001a3d2  lea     rcx, [rsp+250h+var_1DC]; void *
0x18001a3d7  call    memset_0
0x18001a3dc  mov     [rsp+250h+var_1D8], 1
0x18001a3e4  mov     [rbp+150h+var_1D0], rdi
0x18001a3e8  lea     rsi, [rbx+58h]
0x18001a3ec  mov     r9, rsi
0x18001a3ef  lea     r8, ?DeviceNotifyCallback@CDiskPnpMonitor@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CDiskPnpMonitor::DeviceNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x18001a3f6  mov     rdx, rbx
0x18001a3f9  lea     rcx, [rsp+250h+var_1E0]
0x18001a3fe  call    cs:__imp_CM_Register_Notification
0x18001a404  test    eax, eax
0x18001a406  jz      short loc_18001A478
0x18001a408  mov     edx, 0Dh; DefaultErr
0x18001a40d  mov     ecx, eax; CmReturnCode
0x18001a40f  call    cs:__imp_CM_MapCrToWin32Err
0x18001a415  mov     edi, eax
0x18001a417  test    eax, eax
0x18001a419  jle     short loc_18001A424
0x18001a41b  movzx   edi, ax
0x18001a41e  or      edi, 80070000h
0x18001a424  mov     [rsp+250h+var_1E8], edi
0x18001a428  test    edi, edi
0x18001a42a  jns     short loc_18001A478
0x18001a42c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a433  cmp     rcx, r14
0x18001a436  jz      short loc_18001A461
0x18001a438  test    byte ptr [rcx+1Ch], 1
0x18001a43c  jz      short loc_18001A461
0x18001a43e  cmp     byte ptr [rcx+19h], 2
0x18001a442  jb      short loc_18001A461
0x18001a444  mov     edx, 30h ; '0'
0x18001a449  mov     [rsp+250h+dwCreationDisposition], edi
0x18001a44d  mov     r9d, [rbx+20h]
0x18001a451  lea     r8, WPP_4073ae80b6403f4fb8156f4a79a44180_Traceguids
0x18001a458  mov     rcx, [rcx+10h]
0x18001a45c  call    WPP_SF_Dd
0x18001a461  mov     rcx, rsi
0x18001a464  call    ?Detach@?$CHandleT@PEAXUNtHandleTrait@@@@QEAAPEAXXZ; CHandleT<void *,NtHandleTrait>::Detach(void)
0x18001a469  nop
0x18001a46a  lea     rcx, [rsp+250h+var_200]
0x18001a46f  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x18001a474  mov     ebx, edi
0x18001a476  jmp     short loc_18001A4BE
0x18001a478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a47f  cmp     rcx, r14
0x18001a482  jz      short loc_18001A4AA
0x18001a484  test    byte ptr [rcx+1Ch], 1
0x18001a488  jz      short loc_18001A4AA
0x18001a48a  cmp     byte ptr [rcx+19h], 4
0x18001a48e  jb      short loc_18001A4AA
0x18001a490  mov     rax, [rsi]
0x18001a493  mov     qword ptr [rsp+250h+dwFlagsAndAttributes], rax
0x18001a498  mov     qword ptr [rsp+250h+dwCreationDisposition], rbx
0x18001a49d  mov     r9d, [rbx+20h]
0x18001a4a1  mov     rcx, [rcx+10h]
0x18001a4a5  call    WPP_SF_Dqq
0x18001a4aa  mov     [rsp+250h+var_1E8], 0
0x18001a4b2  lea     rcx, [rsp+250h+var_200]
0x18001a4b7  call    ??1?$CHandleT@PEAXUFileHandleTrait@@@@QEAA@XZ; CHandleT<void *,FileHandleTrait>::~CHandleT<void *,FileHandleTrait>(void)
0x18001a4bc  xor     ebx, ebx
0x18001a4be  lea     rcx, [rsp+250h+var_1F0]; this
0x18001a4c3  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x18001a4c8  mov     eax, ebx
  ... truncated ...
```
