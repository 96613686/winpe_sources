# BasepSetFileEncryptionCompression

- ea: `0x18000db20`
- end: `0x18000e157`
- name: `BasepSetFileEncryptionCompression`
- size: `1591`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000db20`
- `0x18000f920`
- `0x180046188`
- `0x180046eb0`
- `0x18007a840`
- `0x18007c010`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000dd2e`
- `ntdll!NtOpenFile` at `0x18000dde1`
- `ntdll!NtOpenFile` at `0x18000de24`
- `ntdll!NtOpenFile` at `0x18000dd2e`
- `ntdll!NtOpenFile` at `0x18000dde1`
- `ntdll!NtOpenFile` at `0x18000de24`
- `ntdll!NtFsControlFile` at `0x18000dd96`
- `ntdll!NtFsControlFile` at `0x18000de7f`
- `ntdll!NtFsControlFile` at `0x18000deea`
- `ntdll!NtFsControlFile` at `0x18000dd96`
- `ntdll!NtFsControlFile` at `0x18000de7f`
- `ntdll!NtFsControlFile` at `0x18000deea`
- `ntdll!NtClose` at `0x18000dcb6`
- `ntdll!NtClose` at `0x18000dcb6`
- `ntdll!NtQueryInformationFile` at `0x18000dc7c`
- `ntdll!NtQueryInformationFile` at `0x18000dc7c`
- `ntdll!RtlSetLastWin32Error` at `0x18000e0cb`
- `ntdll!RtlSetLastWin32Error` at `0x18000e0cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0e2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000df40`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e0e2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e14f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007acbd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e14f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007acbd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dcda`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000dcda`

## string_xrefs

- `0x18000dcd3`: `advapi32.dll`

## pseudocode

```c
__int64 __fastcall BasepSetFileEncryptionCompression(
        HANDLE FileHandle,
        void **a2,
        struct _OBJECT_ATTRIBUTES *a3,
        __int64 a4,
        __int64 a5,
        __int16 a6,
        int a7,
        char a8)
{
  HANDLE v9; // r10
  int v10; // edi
  int v11; // r13d
  int v12; // eax
  int v13; // ebx
  int v14; // esi
  int v15; // ecx
  void **v16; // rdi
  unsigned int v17; // ebx
  HMODULE Library; // rax
  NTSTATUS v19; // eax
  struct _OBJECT_ATTRIBUTES *v20; // r14
  char *InputBuffer; // rax
  FARPROC v22; // r14
  int v23; // edi
  ULONG EncryptedFileVersionExt; // eax
  int v25; // eax
  FARPROC ProcAddress; // rax
  HMODULE hModule; // [rsp+58h] [rbp-B0h]
  int v29; // [rsp+60h] [rbp-A8h] BYREF
  NTSTATUS v30; // [rsp+64h] [rbp-A4h]
  int v31; // [rsp+68h] [rbp-A0h]
  int v32; // [rsp+6Ch] [rbp-9Ch]
  int v33; // [rsp+70h] [rbp-98h]
  __int64 v34; // [rsp+78h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-88h] BYREF
  PHANDLE FileHandlea; // [rsp+90h] [rbp-78h]
  HANDLE v37; // [rsp+98h] [rbp-70h]
  POBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-68h]
  __int128 OutputBuffer; // [rsp+A8h] [rbp-60h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-50h] BYREF
  int v41; // [rsp+138h] [rbp+30h]

  ObjectAttributes = a3;
  FileHandlea = a2;
  v9 = FileHandle;
  v37 = FileHandle;
  hModule = (HMODULE)-1LL;
  IoStatusBlock = 0;
  FileInformation = 0;
  OutputBuffer = 0;
  v34 = 0;
  v29 = 0;
  v10 = a6 & 0x4000;
  v11 = a6 & 0x800;
  v12 = a6 & 0x8000;
  v41 = v12;
  if ( a7 == -1 )
  {
    v13 = v10 == 0;
    v14 = v11 == 0;
    v15 = v12 == 0;
  }
  else
  {
    v13 = a7 & 0x4000;
    v14 = a7 & 0x800;
    v15 = a7 & 0x8000;
  }
  v31 = v13;
  v32 = v14;
  v33 = v15;
  if ( !v10 && !v13 )
  {
    v16 = FileHandlea;
    goto LABEL_6;
  }
  NtClose(*a2);
  *FileHandlea = (void *)-1LL;
  Library = LoadLibraryExW(L"advapi32.dll", 0, 0x800u);
  hModule = Library;
  if ( !Library )
  {
    if ( (a8 & 1) == 0 )
      goto LABEL_18;
    goto LABEL_21;
  }
  if ( v10 )
  {
    if ( v13 )
    {
      EncryptedFileVersionExt = GetEncryptedFileVersionExt(a4, &v29);
      v23 = a8 & 1;
      if ( !EncryptedFileVersionExt || (a8 & 1) != 0 )
      {
        if ( (unsigned int)(v29 - 5) > 1 || (unsigned int)CopyNCryptEfsProtector(a4, a5, 1) )
          goto LABEL_21;
        goto LABEL_44;
      }
    }
    else
    {
      EncryptedFileVersionExt = GetEncryptedFileVersionExt(a4, &v29);
      v23 = a8 & 1;
      if ( !EncryptedFileVersionExt || (a8 & 1) != 0 )
      {
        if ( (unsigned int)(v29 - 5) > 1 )
        {
          ProcAddress = GetProcAddress(hModule, "EncryptFileW");
          if ( !ProcAddress )
            goto LABEL_44;
          v25 = ((__int64 (__fastcall *)(__int64))ProcAddress)(a5);
        }
        else
        {
          v25 = CopyNCryptEfsProtector(a4, a5, 0);
        }
        if ( v25 )
        {
          v13 = 1;
          v31 = 1;
          v14 = 0;
          v32 = 0;
          goto LABEL_21;
        }
LABEL_44:
        if ( !v23 )
          goto LABEL_17;
        goto LABEL_21;
      }
    }
LABEL_68:
    RtlSetLastWin32Error(EncryptedFileVersionExt);
    goto LABEL_17;
  }
  if ( !v13 )
    goto LABEL_21;
  v22 = GetProcAddress(Library, "DecryptFileW");
  v23 = a8 & 1;
  if ( !v22 )
    goto LABEL_44;
  EncryptedFileVersionExt = GetEncryptedFileVersionExt(a5, &v29);
  if ( EncryptedFileVersionExt && (a8 & 1) == 0 )
    goto LABEL_68;
  if ( (unsigned int)(v29 - 5) > 1 )
  {
    if ( ((unsigned int (__fastcall *)(__int64, _QWORD))v22)(a5, 0) )
    {
      v13 = 0;
      v31 = 0;
      goto LABEL_21;
    }
    goto LABEL_44;
  }
LABEL_21:
  v20 = ObjectAttributes;
  v16 = FileHandlea;
  v19 = NtOpenFile(FileHandlea, 0xC0150000, ObjectAttributes, &IoStatusBlock, 0, 0x60u);
  v30 = v19;
  if ( v19 == -1073741790 )
  {
    if ( (a8 & 1) != 0 )
    {
      v19 = NtOpenFile(v16, 0x80150000, v20, &IoStatusBlock, 0, 0x60u);
      v30 = v19;
    }
    if ( v19 == -1073741790 && (a8 & 1) != 0 )
    {
      v19 = NtOpenFile(v16, 0x80110000, v20, &IoStatusBlock, 0, 0x60u);
      v30 = v19;
    }
  }
  if ( v19 < 0 )
    goto LABEL_16;
  v9 = v37;
LABEL_6:
  if ( !v11 )
  {
    if ( v14 && !v13 )
    {
      LOWORD(v29) = 0;
      InputBuffer = (char *)&v29;
      goto LABEL_25;
    }
LABEL_8:
    if ( v41 )
    {
      if ( v33 )
        goto LABEL_10;
      v19 = NtFsControlFile(v37, 0, 0, 0, &IoStatusBlock, 0x9027Cu, 0, 0, &OutputBuffer, 0x10u);
      v30 = v19;
      if ( v19 < 0 )
      {
        if ( a7 == -1 )
          goto LABEL_10;
LABEL_38:
        if ( (a8 & 1) != 0 )
          goto LABEL_10;
        goto LABEL_16;
      }
      LODWORD(v34) = (unsigned __int16)OutputBuffer;
      HIDWORD(v34) = DWORD1(OutputBuffer);
    }
    else
    {
      if ( !v33 )
      {
LABEL_10:
        v17 = 1;
        Library = hModule;
        goto LABEL_76;
      }
      LOWORD(v34) = 0;
      HIDWORD(v34) = 0;
    }
    v19 = NtFsControlFile(*v16, 0, 0, 0, &IoStatusBlock, 0x9C280u, &v34, 8u, 0, 0);
    v30 = v19;
    if ( a7 == -1 || v19 >= 0 )
      goto LABEL_10;
    goto LABEL_38;
  }
  if ( v14 || v13 )
    goto LABEL_8;
  v19 = NtQueryInformationFile(v9, &IoStatusBlock, &FileInformation, 0x10u, FileCompressionInformation);
  v30 = v19;
  if ( v19 >= 0 )
  {
    InputBuffer = (char *)&FileInformation + 8;
LABEL_25:
    v19 = NtFsControlFile(*v16, 0, 0, 0, &IoStatusBlock, 0x9C040u, InputBuffer, 2u, 0, 0);
    v30 = v19;
    if ( a7 == -1 || v19 >= 0 )
      goto LABEL_8;
    goto LABEL_15;
  }
  if ( a7 == -1 )
    goto LABEL_8;
LABEL_15:
  if ( (a8 & 1) != 0 )
    goto LABEL_8;
LABEL_16:
  BaseSetLastNTError((unsigned int)v19);
LABEL_17:
  Library = hModule;
LABEL_18:
  v17 = 0;
LABEL_76:
  if ( (unsigned __int64)Library - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    FreeLibrary(Library);
  return v17;
}

```

## disassembly

```asm
0x18000db20  mov     r11, rsp
0x18000db23  push    rbx
0x18000db24  push    rsi
0x18000db25  push    rdi
0x18000db26  push    r12
0x18000db28  push    r13
0x18000db2a  push    r14
0x18000db2c  push    r15
0x18000db2e  sub     rsp, 0D0h
0x18000db35  mov     rax, cs:__security_cookie
0x18000db3c  xor     rax, rsp
0x18000db3f  mov     [rsp+108h+var_40], rax
0x18000db47  mov     r14, r9
0x18000db4a  mov     [rsp+108h+ObjectAttributes], r8
0x18000db52  mov     [rsp+108h+FileHandle], rdx
0x18000db5a  mov     r10, rcx
0x18000db5d  mov     [rsp+108h+var_70], rcx
0x18000db65  mov     r15, [rsp+108h+arg_20]
0x18000db6d  mov     [rsp+108h+hModule], 0FFFFFFFFFFFFFFFFh
0x18000db76  xorps   xmm0, xmm0
0x18000db79  movups  xmmword ptr [rsp+108h+IoStatusBlock], xmm0
0x18000db81  xor     r8d, r8d
0x18000db84  mov     [rsp+108h+var_B8], r8d
0x18000db89  movups  xmmword ptr [r11-50h], xmm0
0x18000db8e  xorps   xmm1, xmm1
0x18000db91  movups  xmmword ptr [r11-60h], xmm1
0x18000db96  mov     [rsp+108h+var_90], r8
0x18000db9b  mov     [rsp+108h+var_A8], r8d
0x18000dba0  mov     eax, [rsp+108h+arg_28]
0x18000dba7  mov     edi, eax
0x18000dba9  mov     ecx, 4000h
0x18000dbae  and     edi, ecx
0x18000dbb0  mov     r13d, eax
0x18000dbb3  mov     r11d, 800h
0x18000dbb9  and     r13d, r11d
0x18000dbbc  mov     r9d, 8000h
0x18000dbc2  and     eax, r9d
0x18000dbc5  mov     [rsp+108h+arg_28], eax
0x18000dbcc  mov     r12d, [rsp+108h+arg_30]
0x18000dbd4  cmp     r12d, 0FFFFFFFFh
0x18000dbd8  jz      loc_18000E0A2
0x18000dbde  mov     ebx, r12d
0x18000dbe1  and     ebx, ecx
0x18000dbe3  mov     esi, r12d
0x18000dbe6  and     esi, r11d
0x18000dbe9  mov     ecx, r12d
0x18000dbec  and     ecx, r9d
0x18000dbef  mov     [rsp+108h+var_A0], ebx
0x18000dbf3  mov     [rsp+108h+var_9C], esi
0x18000dbf7  mov     [rsp+108h+var_98], ecx
0x18000dbfb  test    edi, edi
0x18000dbfd  jnz     loc_18000DCB3
0x18000dc03  test    ebx, ebx
0x18000dc05  jnz     loc_18000DCB3
0x18000dc0b  mov     rdi, [rsp+108h+FileHandle]
0x18000dc13  xor     r14d, r14d
0x18000dc16  test    r13d, r13d
0x18000dc19  jnz     short loc_18000DC4D
0x18000dc1b  test    esi, esi
0x18000dc1d  jnz     loc_18000DF65
0x18000dc23  mov     eax, [rsp+108h+arg_28]
0x18000dc2a  mov     edx, [rsp+108h+var_98]
0x18000dc2e  test    eax, eax
0x18000dc30  jnz     loc_18000DE33
0x18000dc36  test    edx, edx
0x18000dc38  jnz     loc_18000DF19
0x18000dc3e  mov     ebx, 1
0x18000dc43  mov     rax, [rsp+108h+hModule]
0x18000dc48  jmp     loc_18000E11D
0x18000dc4d  test    esi, esi
0x18000dc4f  jnz     loc_18000E02A
0x18000dc55  test    ebx, ebx
0x18000dc57  jnz     loc_18000E02A
0x18000dc5d  mov     [rsp+108h+FileInformationClass], 1Ch; FileInformationClass
0x18000dc65  lea     r9d, [rsi+10h]; Length
0x18000dc69  lea     r8, [rsp+108h+FileInformation]; FileInformation
0x18000dc71  lea     rdx, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000dc79  mov     rcx, r10; FileHandle
0x18000dc7c  call    cs:__imp_NtQueryInformationFile
0x18000dc82  mov     [rsp+108h+var_A4], eax
0x18000dc86  test    eax, eax
0x18000dc88  jns     loc_18000DD57
0x18000dc8e  cmp     r12d, 0FFFFFFFFh
0x18000dc92  jz      short loc_18000DC23
0x18000dc94  test    byte ptr [rsp+108h+arg_38], 1
0x18000dc9c  jnz     short loc_18000DC23
0x18000dc9e  mov     ecx, eax
0x18000dca0  call    BaseSetLastNTError
0x18000dca5  mov     rax, [rsp+108h+hModule]
0x18000dcaa  mov     ebx, [rsp+108h+var_B8]
0x18000dcae  jmp     loc_18000E11D
0x18000dcb3  mov     rcx, [rdx]; Handle
0x18000dcb6  call    cs:__imp_NtClose
0x18000dcbc  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000dcc0  mov     rax, [rsp+108h+FileHandle]
0x18000dcc8  mov     [rax], rcx
0x18000dccb  xor     edx, edx; hFile
0x18000dccd  mov     r8d, 800h; dwFlags
0x18000dcd3  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18000dcda  call    cs:__imp_LoadLibraryExW
0x18000dce0  mov     [rsp+108h+hModule], rax
0x18000dce5  test    rax, rax
0x18000dce8  jnz     loc_18000DF26
0x18000dcee  test    byte ptr [rsp+108h+arg_38], 1
0x18000dcf6  jz      short loc_18000DCAA
0x18000dcf8  mov     r15d, 60h ; '`'
0x18000dcfe  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000dd03  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000dd0b  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000dd13  mov     r14, [rsp+108h+ObjectAttributes]
0x18000dd1b  mov     r8, r14; ObjectAttributes
0x18000dd1e  mov     edx, 0C0150000h; DesiredAccess
0x18000dd23  mov     rdi, [rsp+108h+FileHandle]
0x18000dd2b  mov     rcx, rdi; FileHandle
0x18000dd2e  call    cs:__imp_NtOpenFile
0x18000dd34  mov     [rsp+108h+var_A4], eax
0x18000dd38  cmp     eax, 0C0000022h
0x18000dd3d  jz      short loc_18000DDB7
0x18000dd3f  xor     r14d, r14d
0x18000dd42  test    eax, eax
0x18000dd44  js      loc_18000DC9E
0x18000dd4a  mov     r10, [rsp+108h+var_70]
0x18000dd52  jmp     loc_18000DC16
0x18000dd57  lea     rax, [rsp+108h+var_48]
0x18000dd5f  mov     [rsp+108h+OutputBufferLength], r14d; OutputBufferLength
0x18000dd64  mov     [rsp+108h+OutputBuffer], r14; OutputBuffer
0x18000dd69  mov     [rsp+108h+InputBufferLength], 2; InputBufferLength
0x18000dd71  mov     [rsp+108h+InputBuffer], rax; InputBuffer
0x18000dd76  mov     [rsp+108h+OpenOptions], 9C040h; FsControlCode
0x18000dd7e  lea     rax, [rsp+108h+IoStatusBlock]
0x18000dd86  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000dd8b  xor     r9d, r9d; ApcContext
0x18000dd8e  xor     r8d, r8d; ApcRoutine
0x18000dd91  xor     edx, edx; Event
0x18000dd93  mov     rcx, [rdi]; FileHandle
0x18000dd96  call    cs:__imp_NtFsControlFile
0x18000dd9c  mov     [rsp+108h+var_A4], eax
0x18000dda0  cmp     r12d, 0FFFFFFFFh
0x18000dda4  jz      loc_18000DC23
0x18000ddaa  test    eax, eax
0x18000ddac  js      loc_18000DC94
0x18000ddb2  jmp     loc_18000DC23
0x18000ddb7  test    byte ptr [rsp+108h+arg_38], 1
0x18000ddbf  jz      short loc_18000DDEB
0x18000ddc1  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000ddc6  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000ddce  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000ddd6  mov     r8, r14; ObjectAttributes
0x18000ddd9  mov     edx, 80150000h; DesiredAccess
0x18000ddde  mov     rcx, rdi; FileHandle
0x18000dde1  call    cs:__imp_NtOpenFile
0x18000dde7  mov     [rsp+108h+var_A4], eax
0x18000ddeb  cmp     eax, 0C0000022h
0x18000ddf0  jnz     loc_18000DD3F
0x18000ddf6  test    byte ptr [rsp+108h+arg_38], 1
0x18000ddfe  jz      loc_18000DD3F
0x18000de04  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000de09  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000de11  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000de19  mov     r8, r14; ObjectAttributes
0x18000de1c  mov     edx, 80110000h; DesiredAccess
0x18000de21  mov     rcx, rdi; FileHandle
0x18000de24  call    cs:__imp_NtOpenFile
0x18000de2a  mov     [rsp+108h+var_A4], eax
0x18000de2e  jmp     loc_18000DD3F
0x18000de33  test    edx, edx
0x18000de35  jnz     loc_18000E095
0x18000de3b  mov     [rsp+108h+OutputBufferLength], 10h; OutputBufferLength
0x18000de43  lea     rax, [rsp+108h+var_60]
0x18000de4b  mov     [rsp+108h+OutputBuffer], rax; OutputBuffer
0x18000de50  mov     [rsp+108h+InputBufferLength], r14d; InputBufferLength
0x18000de55  mov     [rsp+108h+InputBuffer], r14; InputBuffer
0x18000de5a  mov     [rsp+108h+OpenOptions], 9027Ch; FsControlCode
0x18000de62  lea     rax, [rsp+108h+IoStatusBlock]
0x18000de6a  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000de6f  xor     r9d, r9d; ApcContext
0x18000de72  xor     r8d, r8d; ApcRoutine
0x18000de75  xor     edx, edx; Event
0x18000de77  mov     rcx, [rsp+108h+var_70]; FileHandle
0x18000de7f  call    cs:__imp_NtFsControlFile
0x18000de85  mov     [rsp+108h+var_A4], eax
0x18000de89  test    eax, eax
0x18000de8b  js      loc_18000DFBE
0x18000de91  mov     [rsp+108h+var_90], r14
0x18000de96  movzx   eax, [rsp+108h+var_60]
0x18000de9e  mov     word ptr [rsp+108h+var_90], ax
0x18000dea3  mov     eax, [rsp+108h+var_5C]
0x18000deaa  mov     dword ptr [rsp+108h+var_90+4], eax
0x18000deae  mov     [rsp+108h+OutputBufferLength], r14d; OutputBufferLength
0x18000deb3  mov     [rsp+108h+OutputBuffer], r14; OutputBuffer
0x18000deb8  mov     [rsp+108h+InputBufferLength], 8; InputBufferLength
0x18000dec0  lea     rax, [rsp+108h+var_90]
0x18000dec5  mov     [rsp+108h+InputBuffer], rax; InputBuffer
0x18000deca  mov     [rsp+108h+OpenOptions], 9C280h; FsControlCode
0x18000ded2  lea     rax, [rsp+108h+IoStatusBlock]
0x18000deda  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000dedf  xor     r9d, r9d; ApcContext
0x18000dee2  xor     r8d, r8d; ApcRoutine
0x18000dee5  xor     edx, edx; Event
0x18000dee7  mov     rcx, [rdi]; FileHandle
0x18000deea  call    cs:__imp_NtFsControlFile
0x18000def0  mov     [rsp+108h+var_A4], eax
0x18000def4  cmp     r12d, 0FFFFFFFFh
0x18000def8  jz      loc_18000DC3E
0x18000defe  test    eax, eax
0x18000df00  jns     loc_18000DC3E
0x18000df06  test    byte ptr [rsp+108h+arg_38], 1
0x18000df0e  jz      loc_18000DC9E
0x18000df14  jmp     loc_18000DC3E
0x18000df19  mov     word ptr [rsp+108h+var_90], r14w
0x18000df1f  mov     dword ptr [rsp+108h+var_90+4], r14d
0x18000df24  jmp     short loc_18000DEAE
0x18000df26  test    edi, edi
0x18000df28  jnz     loc_18000DFCD
0x18000df2e  test    ebx, ebx
0x18000df30  jz      loc_18000E107
0x18000df36  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x18000df3d  mov     rcx, rax; hModule
0x18000df40  call    cs:__imp_GetProcAddress
0x18000df46  mov     r14, rax
0x18000df49  mov     edi, [rsp+108h+arg_38]
0x18000df50  and     edi, 1
0x18000df53  test    rax, rax
0x18000df56  jnz     short loc_18000DF7D
0x18000df58  test    edi, edi
0x18000df5a  jnz     loc_18000DCF8
0x18000df60  jmp     loc_18000DCA5
0x18000df65  test    ebx, ebx
0x18000df67  jnz     loc_18000DC23
0x18000df6d  mov     word ptr [rsp+108h+var_A8], r14w
0x18000df73  lea     rax, [rsp+108h+var_A8]
0x18000df78  jmp     loc_18000DD5F
0x18000df7d  lea     rdx, [rsp+108h+var_A8]
0x18000df82  mov     rcx, r15
0x18000df85  call    GetEncryptedFileVersionExt
0x18000df8a  test    eax, eax
0x18000df8c  jnz     loc_18000E0FE
0x18000df92  mov     eax, [rsp+108h+var_A8]
0x18000df96  add     eax, 0FFFFFFFBh
0x18000df99  cmp     eax, 1
0x18000df9c  jbe     loc_18000DCF8
0x18000dfa2  xor     edx, edx
0x18000dfa4  mov     rcx, r15
0x18000dfa7  mov     rax, r14
0x18000dfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfaf  test    eax, eax
0x18000dfb1  jz      short loc_18000DF58
0x18000dfb3  xor     ebx, ebx
0x18000dfb5  mov     [rsp+108h+var_A0], ebx
0x18000dfb9  jmp     loc_18000DCF8
0x18000dfbe  cmp     r12d, 0FFFFFFFFh
0x18000dfc2  jnz     loc_18000DF06
0x18000dfc8  jmp     loc_18000DC3E
0x18000dfcd  test    ebx, ebx
0x18000dfcf  jnz     short loc_18000E038
0x18000dfd1  lea     rdx, [rsp+108h+var_A8]
0x18000dfd6  mov     rcx, r14
0x18000dfd9  call    GetEncryptedFileVersionExt
0x18000dfde  mov     edi, [rsp+108h+arg_38]
0x18000dfe5  and     edi, 1
0x18000dfe8  test    eax, eax
0x18000dfea  jnz     loc_18000E0C1
0x18000dff0  mov     eax, [rsp+108h+var_A8]
0x18000dff4  add     eax, 0FFFFFFFBh
0x18000dff7  cmp     eax, 1
0x18000dffa  ja      loc_18000E0D6
0x18000e000  xor     r8d, r8d
0x18000e003  mov     rdx, r15
0x18000e006  mov     rcx, r14
0x18000e009  call    CopyNCryptEfsProtector
0x18000e00e  test    eax, eax
0x18000e010  jz      loc_18000DF58
0x18000e016  mov     ebx, 1
0x18000e01b  mov     [rsp+108h+var_A0], ebx
0x18000e01f  xor     esi, esi
0x18000e021  mov     [rsp+108h+var_9C], esi
0x18000e025  jmp     loc_18000DCF8
0x18000e02a  test    r13d, r13d
0x18000e02d  jnz     loc_18000DC23
0x18000e033  jmp     loc_18000DC1B
0x18000e038  test    edi, edi
0x18000e03a  jz      loc_18000DF2E
0x18000e040  test    ebx, ebx
0x18000e042  jz      loc_18000DCF8
0x18000e048  lea     rdx, [rsp+108h+var_A8]
0x18000e04d  mov     rcx, r14
0x18000e050  call    GetEncryptedFileVersionExt
0x18000e055  mov     edi, [rsp+108h+arg_38]
0x18000e05c  and     edi, 1
0x18000e05f  test    eax, eax
0x18000e061  jnz     loc_18000E114
0x18000e067  mov     eax, [rsp+108h+var_A8]
0x18000e06b  add     eax, 0FFFFFFFBh
0x18000e06e  cmp     eax, 1
0x18000e071  ja      loc_18000DCF8
0x18000e077  mov     r8d, 1
0x18000e07d  mov     rdx, r15
0x18000e080  mov     rcx, r14
0x18000e083  call    CopyNCryptEfsProtector
0x18000e088  test    eax, eax
  ... truncated ...
```
