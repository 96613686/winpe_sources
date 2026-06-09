# BasepSetFileEncryptionCompression

- ea: `0x18000acc0`
- end: `0x18000b34a`
- name: `BasepSetFileEncryptionCompression`
- size: `1674`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, __int64, int, int, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000a4b8`
- `0x18000a880`
- `0x18000acc0`
- `0x18000ccf0`
- `0x1800827c0`
- `0x180084010`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18000aee4`
- `ntdll!NtOpenFile` at `0x18000afa3`
- `ntdll!NtOpenFile` at `0x18000afec`
- `ntdll!NtOpenFile` at `0x18000aee4`
- `ntdll!NtOpenFile` at `0x18000afa3`
- `ntdll!NtOpenFile` at `0x18000afec`
- `ntdll!NtFsControlFile` at `0x18000af52`
- `ntdll!NtFsControlFile` at `0x18000b04d`
- `ntdll!NtFsControlFile` at `0x18000b0be`
- `ntdll!NtFsControlFile` at `0x18000af52`
- `ntdll!NtFsControlFile` at `0x18000b04d`
- `ntdll!NtFsControlFile` at `0x18000b0be`
- `ntdll!NtClose` at `0x18000ae60`
- `ntdll!NtClose` at `0x18000ae60`
- `ntdll!NtQueryInformationFile` at `0x18000ae1c`
- `ntdll!NtQueryInformationFile` at `0x18000ae1c`
- `ntdll!RtlSetLastWin32Error` at `0x18000b2ab`
- `ntdll!RtlSetLastWin32Error` at `0x18000b2ab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b11a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b2c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b11a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b2c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b33c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082903`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b33c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180082903`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ae8a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000ae8a`

## string_xrefs

- `0x18000ae83`: `advapi32.dll`

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
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-88h] BYREF
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
0x18000acc0  mov     r11, rsp
0x18000acc3  push    rbx
0x18000acc4  push    rsi
0x18000acc5  push    rdi
0x18000acc6  push    r12
0x18000acc8  push    r13
0x18000acca  push    r14
0x18000accc  push    r15
0x18000acce  sub     rsp, 0D0h
0x18000acd5  mov     rax, cs:__security_cookie
0x18000acdc  xor     rax, rsp
0x18000acdf  mov     [rsp+108h+var_40], rax
0x18000ace7  mov     r14, r9
0x18000acea  mov     [rsp+108h+ObjectAttributes], r8
0x18000acf2  mov     [rsp+108h+FileHandle], rdx
0x18000acfa  mov     r10, rcx
0x18000acfd  mov     [rsp+108h+var_70], rcx
0x18000ad05  mov     r15, [rsp+108h+arg_20]
0x18000ad0d  mov     [rsp+108h+hModule], 0FFFFFFFFFFFFFFFFh
0x18000ad16  xorps   xmm0, xmm0
0x18000ad19  movups  xmmword ptr [rsp+108h+IoStatusBlock], xmm0
0x18000ad21  xor     r8d, r8d
0x18000ad24  mov     [rsp+108h+var_B8], r8d
0x18000ad29  movups  xmmword ptr [r11-50h], xmm0
0x18000ad2e  xorps   xmm1, xmm1
0x18000ad31  movups  xmmword ptr [r11-60h], xmm1
0x18000ad36  mov     [rsp+108h+var_90], r8
0x18000ad3b  mov     [rsp+108h+var_A8], r8d
0x18000ad40  mov     eax, [rsp+108h+arg_28]
0x18000ad47  mov     edi, eax
0x18000ad49  mov     ecx, 4000h
0x18000ad4e  and     edi, ecx
0x18000ad50  mov     r13d, eax
0x18000ad53  mov     r11d, 800h
0x18000ad59  and     r13d, r11d
0x18000ad5c  mov     r9d, 8000h
0x18000ad62  and     eax, r9d
0x18000ad65  mov     [rsp+108h+arg_28], eax
0x18000ad6c  mov     r12d, [rsp+108h+arg_30]
0x18000ad74  cmp     r12d, 0FFFFFFFFh
0x18000ad78  jz      loc_18000B282
0x18000ad7e  mov     ebx, r12d
0x18000ad81  and     ebx, ecx
0x18000ad83  mov     esi, r12d
0x18000ad86  and     esi, r11d
0x18000ad89  mov     ecx, r12d
0x18000ad8c  and     ecx, r9d
0x18000ad8f  mov     [rsp+108h+var_A0], ebx
0x18000ad93  mov     [rsp+108h+var_9C], esi
0x18000ad97  mov     [rsp+108h+var_98], ecx
0x18000ad9b  test    edi, edi
0x18000ad9d  jnz     loc_18000AE5D
0x18000ada3  test    ebx, ebx
0x18000ada5  jnz     loc_18000AE5D
0x18000adab  mov     rdi, [rsp+108h+FileHandle]
0x18000adb3  xor     r14d, r14d
0x18000adb6  test    r13d, r13d
0x18000adb9  jnz     short loc_18000ADED
0x18000adbb  test    esi, esi
0x18000adbd  jnz     loc_18000B145
0x18000adc3  mov     eax, [rsp+108h+arg_28]
0x18000adca  mov     edx, [rsp+108h+var_98]
0x18000adce  test    eax, eax
0x18000add0  jnz     loc_18000B001
0x18000add6  test    edx, edx
0x18000add8  jnz     loc_18000B0F3
0x18000adde  mov     ebx, 1
0x18000ade3  mov     rax, [rsp+108h+hModule]
0x18000ade8  jmp     loc_18000B309
0x18000aded  test    esi, esi
0x18000adef  jnz     loc_18000B20A
0x18000adf5  test    ebx, ebx
0x18000adf7  jnz     loc_18000B20A
0x18000adfd  mov     [rsp+108h+FileInformationClass], 1Ch; FileInformationClass
0x18000ae05  lea     r9d, [rsi+10h]; Length
0x18000ae09  lea     r8, [rsp+108h+FileInformation]; FileInformation
0x18000ae11  lea     rdx, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000ae19  mov     rcx, r10; FileHandle
0x18000ae1c  call    cs:__imp_NtQueryInformationFile
0x18000ae23  nop     dword ptr [rax+rax+00h]
0x18000ae28  mov     [rsp+108h+var_A4], eax
0x18000ae2c  test    eax, eax
0x18000ae2e  jns     loc_18000AF13
0x18000ae34  cmp     r12d, 0FFFFFFFFh
0x18000ae38  jz      short loc_18000ADC3
0x18000ae3a  test    byte ptr [rsp+108h+arg_38], 1
0x18000ae42  jnz     loc_18000ADC3
0x18000ae48  mov     ecx, eax
0x18000ae4a  call    BaseSetLastNTError
0x18000ae4f  mov     rax, [rsp+108h+hModule]
0x18000ae54  mov     ebx, [rsp+108h+var_B8]
0x18000ae58  jmp     loc_18000B309
0x18000ae5d  mov     rcx, [rdx]; Handle
0x18000ae60  call    cs:__imp_NtClose
0x18000ae67  nop     dword ptr [rax+rax+00h]
0x18000ae6c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000ae70  mov     rax, [rsp+108h+FileHandle]
0x18000ae78  mov     [rax], rcx
0x18000ae7b  xor     edx, edx; hFile
0x18000ae7d  mov     r8d, 800h; dwFlags
0x18000ae83  lea     rcx, AdvapiDllString; "advapi32.dll"
0x18000ae8a  call    cs:__imp_LoadLibraryExW
0x18000ae91  nop     dword ptr [rax+rax+00h]
0x18000ae96  mov     [rsp+108h+hModule], rax
0x18000ae9b  test    rax, rax
0x18000ae9e  jnz     loc_18000B100
0x18000aea4  test    byte ptr [rsp+108h+arg_38], 1
0x18000aeac  jz      short loc_18000AE54
0x18000aeae  mov     r15d, 60h ; '`'
0x18000aeb4  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000aeb9  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000aec1  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000aec9  mov     r14, [rsp+108h+ObjectAttributes]
0x18000aed1  mov     r8, r14; ObjectAttributes
0x18000aed4  mov     edx, 0C0150000h; DesiredAccess
0x18000aed9  mov     rdi, [rsp+108h+FileHandle]
0x18000aee1  mov     rcx, rdi; FileHandle
0x18000aee4  call    cs:__imp_NtOpenFile
0x18000aeeb  nop     dword ptr [rax+rax+00h]
0x18000aef0  mov     [rsp+108h+var_A4], eax
0x18000aef4  cmp     eax, 0C0000022h
0x18000aef9  jz      short loc_18000AF79
0x18000aefb  xor     r14d, r14d
0x18000aefe  test    eax, eax
0x18000af00  js      loc_18000AE48
0x18000af06  mov     r10, [rsp+108h+var_70]
0x18000af0e  jmp     loc_18000ADB6
0x18000af13  lea     rax, [rsp+108h+var_48]
0x18000af1b  mov     [rsp+108h+OutputBufferLength], r14d; OutputBufferLength
0x18000af20  mov     [rsp+108h+OutputBuffer], r14; OutputBuffer
0x18000af25  mov     [rsp+108h+InputBufferLength], 2; InputBufferLength
0x18000af2d  mov     [rsp+108h+InputBuffer], rax; InputBuffer
0x18000af32  mov     [rsp+108h+OpenOptions], 9C040h; FsControlCode
0x18000af3a  lea     rax, [rsp+108h+IoStatusBlock]
0x18000af42  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000af47  xor     r9d, r9d; ApcContext
0x18000af4a  xor     r8d, r8d; ApcRoutine
0x18000af4d  xor     edx, edx; Event
0x18000af4f  mov     rcx, [rdi]; FileHandle
0x18000af52  call    cs:__imp_NtFsControlFile
0x18000af59  nop     dword ptr [rax+rax+00h]
0x18000af5e  mov     [rsp+108h+var_A4], eax
0x18000af62  cmp     r12d, 0FFFFFFFFh
0x18000af66  jz      loc_18000ADC3
0x18000af6c  test    eax, eax
0x18000af6e  js      loc_18000AE3A
0x18000af74  jmp     loc_18000ADC3
0x18000af79  test    byte ptr [rsp+108h+arg_38], 1
0x18000af81  jz      short loc_18000AFB3
0x18000af83  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000af88  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000af90  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000af98  mov     r8, r14; ObjectAttributes
0x18000af9b  mov     edx, 80150000h; DesiredAccess
0x18000afa0  mov     rcx, rdi; FileHandle
0x18000afa3  call    cs:__imp_NtOpenFile
0x18000afaa  nop     dword ptr [rax+rax+00h]
0x18000afaf  mov     [rsp+108h+var_A4], eax
0x18000afb3  cmp     eax, 0C0000022h
0x18000afb8  jnz     loc_18000AEFB
0x18000afbe  test    byte ptr [rsp+108h+arg_38], 1
0x18000afc6  jz      loc_18000AEFB
0x18000afcc  mov     [rsp+108h+OpenOptions], r15d; OpenOptions
0x18000afd1  mov     [rsp+108h+FileInformationClass], 0; ShareAccess
0x18000afd9  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x18000afe1  mov     r8, r14; ObjectAttributes
0x18000afe4  mov     edx, 80110000h; DesiredAccess
0x18000afe9  mov     rcx, rdi; FileHandle
0x18000afec  call    cs:__imp_NtOpenFile
0x18000aff3  nop     dword ptr [rax+rax+00h]
0x18000aff8  mov     [rsp+108h+var_A4], eax
0x18000affc  jmp     loc_18000AEFB
0x18000b001  test    edx, edx
0x18000b003  jnz     loc_18000B275
0x18000b009  mov     [rsp+108h+OutputBufferLength], 10h; OutputBufferLength
0x18000b011  lea     rax, [rsp+108h+var_60]
0x18000b019  mov     [rsp+108h+OutputBuffer], rax; OutputBuffer
0x18000b01e  mov     [rsp+108h+InputBufferLength], r14d; InputBufferLength
0x18000b023  mov     [rsp+108h+InputBuffer], r14; InputBuffer
0x18000b028  mov     [rsp+108h+OpenOptions], 9027Ch; FsControlCode
0x18000b030  lea     rax, [rsp+108h+IoStatusBlock]
0x18000b038  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000b03d  xor     r9d, r9d; ApcContext
0x18000b040  xor     r8d, r8d; ApcRoutine
0x18000b043  xor     edx, edx; Event
0x18000b045  mov     rcx, [rsp+108h+var_70]; FileHandle
0x18000b04d  call    cs:__imp_NtFsControlFile
0x18000b054  nop     dword ptr [rax+rax+00h]
0x18000b059  mov     [rsp+108h+var_A4], eax
0x18000b05d  test    eax, eax
0x18000b05f  js      loc_18000B19E
0x18000b065  mov     [rsp+108h+var_90], r14
0x18000b06a  movzx   eax, [rsp+108h+var_60]
0x18000b072  mov     word ptr [rsp+108h+var_90], ax
0x18000b077  mov     eax, [rsp+108h+var_5C]
0x18000b07e  mov     dword ptr [rsp+108h+var_90+4], eax
0x18000b082  mov     [rsp+108h+OutputBufferLength], r14d; OutputBufferLength
0x18000b087  mov     [rsp+108h+OutputBuffer], r14; OutputBuffer
0x18000b08c  mov     [rsp+108h+InputBufferLength], 8; InputBufferLength
0x18000b094  lea     rax, [rsp+108h+var_90]
0x18000b099  mov     [rsp+108h+InputBuffer], rax; InputBuffer
0x18000b09e  mov     [rsp+108h+OpenOptions], 9C280h; FsControlCode
0x18000b0a6  lea     rax, [rsp+108h+IoStatusBlock]
0x18000b0ae  mov     qword ptr [rsp+108h+FileInformationClass], rax; IoStatusBlock
0x18000b0b3  xor     r9d, r9d; ApcContext
0x18000b0b6  xor     r8d, r8d; ApcRoutine
0x18000b0b9  xor     edx, edx; Event
0x18000b0bb  mov     rcx, [rdi]; FileHandle
0x18000b0be  call    cs:__imp_NtFsControlFile
0x18000b0c5  nop     dword ptr [rax+rax+00h]
0x18000b0ca  mov     [rsp+108h+var_A4], eax
0x18000b0ce  cmp     r12d, 0FFFFFFFFh
0x18000b0d2  jz      loc_18000ADDE
0x18000b0d8  test    eax, eax
0x18000b0da  jns     loc_18000ADDE
0x18000b0e0  test    byte ptr [rsp+108h+arg_38], 1
0x18000b0e8  jz      loc_18000AE48
0x18000b0ee  jmp     loc_18000ADDE
0x18000b0f3  mov     word ptr [rsp+108h+var_90], r14w
0x18000b0f9  mov     dword ptr [rsp+108h+var_90+4], r14d
0x18000b0fe  jmp     short loc_18000B082
0x18000b100  test    edi, edi
0x18000b102  jnz     loc_18000B1AD
0x18000b108  test    ebx, ebx
0x18000b10a  jz      loc_18000B2F3
0x18000b110  lea     rdx, DECRYPTFILEW_NAME; "DecryptFileW"
0x18000b117  mov     rcx, rax; hModule
0x18000b11a  call    cs:__imp_GetProcAddress
0x18000b121  nop     dword ptr [rax+rax+00h]
0x18000b126  mov     r14, rax
0x18000b129  mov     edi, [rsp+108h+arg_38]
0x18000b130  and     edi, 1
0x18000b133  test    rax, rax
0x18000b136  jnz     short loc_18000B15D
0x18000b138  test    edi, edi
0x18000b13a  jnz     loc_18000AEAE
0x18000b140  jmp     loc_18000AE4F
0x18000b145  test    ebx, ebx
0x18000b147  jnz     loc_18000ADC3
0x18000b14d  mov     word ptr [rsp+108h+var_A8], r14w
0x18000b153  lea     rax, [rsp+108h+var_A8]
0x18000b158  jmp     loc_18000AF1B
0x18000b15d  lea     rdx, [rsp+108h+var_A8]
0x18000b162  mov     rcx, r15
0x18000b165  call    GetEncryptedFileVersionExt
0x18000b16a  test    eax, eax
0x18000b16c  jnz     loc_18000B2EA
0x18000b172  mov     eax, [rsp+108h+var_A8]
0x18000b176  add     eax, 0FFFFFFFBh
0x18000b179  cmp     eax, 1
0x18000b17c  jbe     loc_18000AEAE
0x18000b182  xor     edx, edx
0x18000b184  mov     rcx, r15
0x18000b187  mov     rax, r14
0x18000b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18f  test    eax, eax
0x18000b191  jz      short loc_18000B138
0x18000b193  xor     ebx, ebx
0x18000b195  mov     [rsp+108h+var_A0], ebx
0x18000b199  jmp     loc_18000AEAE
0x18000b19e  cmp     r12d, 0FFFFFFFFh
0x18000b1a2  jnz     loc_18000B0E0
0x18000b1a8  jmp     loc_18000ADDE
0x18000b1ad  test    ebx, ebx
0x18000b1af  jnz     short loc_18000B218
0x18000b1b1  lea     rdx, [rsp+108h+var_A8]
0x18000b1b6  mov     rcx, r14
0x18000b1b9  call    GetEncryptedFileVersionExt
0x18000b1be  mov     edi, [rsp+108h+arg_38]
0x18000b1c5  and     edi, 1
0x18000b1c8  test    eax, eax
0x18000b1ca  jnz     loc_18000B2A1
0x18000b1d0  mov     eax, [rsp+108h+var_A8]
0x18000b1d4  add     eax, 0FFFFFFFBh
0x18000b1d7  cmp     eax, 1
0x18000b1da  ja      loc_18000B2BC
0x18000b1e0  xor     r8d, r8d
0x18000b1e3  mov     rdx, r15
0x18000b1e6  mov     rcx, r14
0x18000b1e9  call    CopyNCryptEfsProtector
0x18000b1ee  test    eax, eax
0x18000b1f0  jz      loc_18000B138
0x18000b1f6  mov     ebx, 1
0x18000b1fb  mov     [rsp+108h+var_A0], ebx
0x18000b1ff  xor     esi, esi
0x18000b201  mov     [rsp+108h+var_9C], esi
0x18000b205  jmp     loc_18000AEAE
0x18000b20a  test    r13d, r13d
0x18000b20d  jnz     loc_18000ADC3
0x18000b213  jmp     loc_18000ADBB
0x18000b218  test    edi, edi
0x18000b21a  jz      loc_18000B108
0x18000b220  test    ebx, ebx
0x18000b222  jz      loc_18000AEAE
0x18000b228  lea     rdx, [rsp+108h+var_A8]
0x18000b22d  mov     rcx, r14
0x18000b230  call    GetEncryptedFileVersionExt
0x18000b235  mov     edi, [rsp+108h+arg_38]
0x18000b23c  and     edi, 1
0x18000b23f  test    eax, eax
  ... truncated ...
```
