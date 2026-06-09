# CFileAccessor::BindToStream(IStream * *)

- ea: `0x180006cd0`
- end: `0x180007071`
- name: `?BindToStream@CFileAccessor@@UEAAJPEAPEAUIStream@@@Z`
- size: `929`
- prototype: `__int64 __fastcall(CFileAccessor *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002d00`
- `0x180005720`
- `0x180005a50`
- `0x180005d40`
- `0x180006ad0`
- `0x180006cd0`
- `0x18000bbfc`
- `0x18000e9cc`
- `0x18000fcd0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ee5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ea7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006ea7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007035`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006e73`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007035`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180006fdd`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180006fdd`
- `ntdll!RtlNtStatusToDosError` at `0x180006e82`
- `ntdll!RtlNtStatusToDosError` at `0x180006e82`
- `ntdll!RtlInitUnicodeString` at `0x180006dec`
- `ntdll!RtlInitUnicodeString` at `0x180006dec`
- `ntdll!NtCreateFile` at `0x180006e5f`
- `ntdll!NtCreateFile` at `0x180006e5f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFileAccessor::BindToStream(CFileAccessor *this, struct IStream **a2)
{
  const wchar_t *v4; // rdx
  signed int v5; // r15d
  ACCESS_MASK v6; // r14d
  wil *v7; // rdi
  _BOOL8 is_extended_length_path; // rbx
  NTSTATUS v9; // eax
  NTSTATUS v10; // ebx
  DWORD v11; // ecx
  ULONG v12; // eax
  char *v13; // rbx
  signed int LastError; // eax
  FILETIME v15; // rdx
  struct IStream *v16; // rdi
  FILETIME LastAccessTime; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-50h] BYREF
  void **v23; // [rsp+C0h] [rbp-40h] BYREF
  PCWSTR SourceString; // [rsp+C8h] [rbp-38h]
  __int64 v25; // [rsp+D0h] [rbp-30h]
  wchar_t v26[68]; // [rsp+D8h] [rbp-28h] BYREF

  if ( *((_DWORD *)this + 235) || !*((_DWORD *)this + 214) && (*((_BYTE *)this + 904) & 0x10) == 0 )
    return 2147549183LL;
  if ( (unsigned int)CFileAccessor::IsOplockBroken(this) )
    return 2147942432LL;
  v5 = 0;
  if ( (*((_BYTE *)this + 904) & 0x10) != 0 || !*((_DWORD *)this + 36) )
    return 0;
  v6 = (*(_BYTE *)(*((_QWORD *)this + 112) + 152LL) != 0 ? 0x100 : 0) | 0x80100000;
  v7 = (wil *)*((_QWORD *)this + 88);
  is_extended_length_path = wil::is_extended_length_path(v7, v4);
  SourceString = v26;
  v25 = 65;
  v26[0] = 0;
  v23 = &TLMString<64,64,32767>::`vftable';
  CLMString::Assign((CLMString *)&v23, L"\\??\\", 0, 0xFFFFFFFF);
  ((void (__fastcall *)(void ***, __int64, _QWORD, __int64))v23[4])(
    &v23,
    (__int64)v7 + 8 * is_extended_length_path,
    HIDWORD(v25),
    0xFFFFFFFFLL);
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, SourceString);
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v9 = NtCreateFile(&FileHandle, v6, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x204120u, 0, 0);
  v10 = v9;
  if ( v9 == 264 )
  {
    CloseHandle(FileHandle);
    v11 = 32;
  }
  else
  {
    v12 = RtlNtStatusToDosError(v9);
    v11 = v12;
    if ( !v12 )
      goto LABEL_14;
    if ( v10 == -1073739511 )
      v12 = 32;
    v11 = v12;
  }
  FileHandle = (void *)-1LL;
LABEL_14:
  SetLastError(v11);
  v13 = (char *)FileHandle;
  v23 = &TLMString<64,64,32767>::`vftable';
  CLMString::DeleteBuf((CLMString *)&v23, v26);
  v23 = &CLMString::`vftable';
  if ( ((unsigned __int64)(v13 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    if ( *(_BYTE *)(*((_QWORD *)this + 112) + 152LL) )
    {
      LastAccessTime = (FILETIME)-1LL;
      SetFileTime(v13, 0, &LastAccessTime, 0);
      LastAccessTime = 0;
      goto LABEL_18;
    }
  }
  else
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
  }
  v15 = 0;
  LastAccessTime = 0;
  if ( v5 >= 0 )
  {
LABEL_18:
    v5 = ATL::CComObject<CFileStream>::CreateInstance(&LastAccessTime);
    v15 = LastAccessTime;
  }
  LastAccessTime = 0;
  if ( v5 < 0
    || (((void (__fastcall *)(_QWORD, _QWORD))TComPointer<CFileStream>::operator=)(&LastAccessTime, v15),
        v16 = (struct IStream *)LastAccessTime,
        v5 = (*(__int64 (__fastcall **)(FILETIME, char *, __int64, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)&LastAccessTime + 120LL))(
               LastAccessTime,
               v13,
               0x80000000LL,
               *((_QWORD *)this + 88),
               *((_QWORD *)this + 109),
               *((_QWORD *)this + 110),
               *((_QWORD *)this + 108),
               *((_QWORD *)this + 114)),
        v5 < 0) )
  {
    TComPointer<CFileStream>::~TComPointer<CFileStream>(&LastAccessTime);
    if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      CloseHandle(v13);
    return (unsigned int)v5;
  }
  else
  {
    if ( (unsigned int)CFileAccessor::IsOplockBroken(this) )
    {
      TComPointer<CFileStream>::~TComPointer<CFileStream>(&LastAccessTime);
      return 2147942432LL;
    }
    (*(void (__fastcall **)(struct IStream *))(*(_QWORD *)v16 + 8LL))(v16);
    *a2 = v16;
    TComPointer<CFileStream>::operator=((char *)this + 216, v16);
    TComPointer<CFileStream>::~TComPointer<CFileStream>(&LastAccessTime);
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x180006cd0  mov     [rsp-8+arg_10], rbx
0x180006cd5  push    rbp
0x180006cd6  push    rsi
0x180006cd7  push    rdi
0x180006cd8  push    r12
0x180006cda  push    r13
0x180006cdc  push    r14
0x180006cde  push    r15
0x180006ce0  lea     rbp, [rsp-70h]
0x180006ce5  sub     rsp, 170h
0x180006cec  mov     rax, cs:__security_cookie
0x180006cf3  xor     rax, rsp
0x180006cf6  mov     [rbp+0A0h+var_40], rax
0x180006cfa  mov     r12, rdx
0x180006cfd  mov     rsi, rcx
0x180006d00  cmp     dword ptr [rcx+3ACh], 0
0x180006d07  jnz     loc_180007045
0x180006d0d  cmp     dword ptr [rcx+358h], 0
0x180006d14  jnz     short loc_180006D23
0x180006d16  test    byte ptr [rcx+388h], 10h
0x180006d1d  jz      loc_180007045
0x180006d23  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x180006d28  test    eax, eax
0x180006d2a  jnz     loc_180006FA9
0x180006d30  xor     r13d, r13d
0x180006d33  mov     r15d, r13d
0x180006d36  test    byte ptr [rsi+388h], 10h
0x180006d3d  jnz     loc_180007040
0x180006d43  cmp     [rsi+90h], r13d
0x180006d4a  jz      loc_180007040
0x180006d50  mov     rax, [rsi+380h]
0x180006d57  movzx   ecx, byte ptr [rax+98h]
0x180006d5e  neg     cl
0x180006d60  sbb     r14d, r14d
0x180006d63  and     r14d, 100h
0x180006d6a  or      r14d, 80100000h
0x180006d71  mov     rdi, [rsi+2C0h]
0x180006d78  mov     rcx, rdi; this
0x180006d7b  call    ?is_extended_length_path@wil@@YA_NPEB_W@Z; wil::is_extended_length_path(wchar_t const *)
0x180006d80  movzx   ebx, al
0x180006d83  lea     rax, [rbp+0A0h+var_C8]
0x180006d87  mov     [rbp+0A0h+SourceString], rax
0x180006d8b  mov     [rbp+0A0h+var_D0], 41h ; 'A'
0x180006d93  mov     [rbp+0A0h+var_C8], r13w
0x180006d98  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180006d9f  mov     [rbp+0A0h+var_E0], rax
0x180006da3  mov     r9d, 0FFFFFFFFh; unsigned int
0x180006da9  xor     r8d, r8d; unsigned int
0x180006dac  lea     rdx, asc_18002A8A8; "\\??\\"
0x180006db3  lea     rcx, [rbp+0A0h+var_E0]; this
0x180006db7  call    ?Assign@CLMString@@UEAAHPEB_WII@Z; CLMString::Assign(wchar_t const *,uint,uint)
0x180006dbc  lea     rdx, [rdi+rbx*8]
0x180006dc0  mov     rax, [rbp+0A0h+var_E0]
0x180006dc4  mov     r9d, 0FFFFFFFFh
0x180006dca  mov     r8d, dword ptr [rbp+0A0h+var_D0+4]
0x180006dce  lea     rcx, [rbp+0A0h+var_E0]
0x180006dd2  mov     rax, [rax+20h]
0x180006dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ddb  xorps   xmm0, xmm0
0x180006dde  movups  xmmword ptr [rsp+1A0h+DestinationString.Length], xmm0
0x180006de3  mov     rdx, [rbp+0A0h+SourceString]; SourceString
0x180006de7  lea     rcx, [rsp+1A0h+DestinationString]; DestinationString
0x180006dec  call    cs:__imp_RtlInitUnicodeString
0x180006df2  mov     qword ptr [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x180006dfa  mov     qword ptr [rbp+0A0h+ObjectAttributes.Attributes], 40h ; '@'
0x180006e02  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], r13
0x180006e06  lea     rax, [rsp+1A0h+DestinationString]
0x180006e0b  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x180006e0f  xorps   xmm0, xmm0
0x180006e12  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180006e17  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x180006e1b  mov     [rsp+1A0h+FileHandle], r13
0x180006e20  mov     [rsp+1A0h+EaLength], r13d; EaLength
0x180006e25  mov     [rsp+1A0h+EaBuffer], r13; EaBuffer
0x180006e2a  mov     [rsp+1A0h+CreateOptions], 204120h; CreateOptions
0x180006e32  mov     [rsp+1A0h+CreateDisposition], 1; CreateDisposition
0x180006e3a  mov     [rsp+1A0h+ShareAccess], 7; ShareAccess
0x180006e42  mov     [rsp+1A0h+FileAttributes], 80h; FileAttributes
0x180006e4a  mov     [rsp+1A0h+AllocationSize], r13; AllocationSize
0x180006e4f  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x180006e53  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x180006e57  mov     edx, r14d; DesiredAccess
0x180006e5a  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x180006e5f  call    cs:__imp_NtCreateFile
0x180006e65  mov     ebx, eax
0x180006e67  cmp     eax, 108h
0x180006e6c  jnz     short loc_180006E80
0x180006e6e  mov     rcx, [rsp+1A0h+FileHandle]; hObject
0x180006e73  call    cs:__imp_CloseHandle
0x180006e79  mov     ecx, 20h ; ' '
0x180006e7e  jmp     short loc_180006E9E
0x180006e80  mov     ecx, ebx; Status
0x180006e82  call    cs:__imp_RtlNtStatusToDosError
0x180006e88  mov     ecx, eax
0x180006e8a  test    eax, eax
0x180006e8c  jz      short loc_180006EA7
0x180006e8e  mov     ecx, 20h ; ' '
0x180006e93  cmp     ebx, 0C0000909h
0x180006e99  cmovz   eax, ecx
0x180006e9c  mov     ecx, eax; dwErrCode
0x180006e9e  mov     [rsp+1A0h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180006ea7  call    cs:__imp_SetLastError
0x180006ead  mov     rbx, [rsp+1A0h+FileHandle]
0x180006eb2  lea     rax, ??_7?$TLMString@$0EA@$0EA@$0HPPP@@@6B@; const TLMString<64,64,32767>::`vftable'
0x180006eb9  mov     [rbp+0A0h+var_E0], rax
0x180006ebd  lea     rdx, [rbp+0A0h+var_C8]; wchar_t *
0x180006ec1  lea     rcx, [rbp+0A0h+var_E0]; this
0x180006ec5  call    ?DeleteBuf@CLMString@@IEAAXPEB_W@Z; CLMString::DeleteBuf(wchar_t const *)
0x180006eca  lea     rax, ??_7CLMString@@6B@; const CLMString::`vftable'
0x180006ed1  mov     [rbp+0A0h+var_E0], rax
0x180006ed5  lea     rax, [rbx+1]
0x180006ed9  test    rax, 0FFFFFFFFFFFFFFFEh
0x180006edf  jnz     loc_180006FB3
0x180006ee5  call    cs:__imp_GetLastError
0x180006eeb  mov     r15d, eax
0x180006eee  test    eax, eax
0x180006ef0  jle     short loc_180006EFD
0x180006ef2  movzx   r15d, ax
0x180006ef6  or      r15d, 80070000h
0x180006efd  mov     rdx, r13
0x180006f00  mov     qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime], rdx
0x180006f05  test    r15d, r15d
0x180006f08  js      short loc_180006F1C
0x180006f0a  lea     rcx, [rsp+1A0h+LastAccessTime]
0x180006f0f  call    ?CreateInstance@?$CComObject@VCFileStream@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFileStream>::CreateInstance(ATL::CComObject<CFileStream> * *)
0x180006f14  mov     r15d, eax
0x180006f17  mov     rdx, qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime]
0x180006f1c  mov     qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime], r13
0x180006f21  test    r15d, r15d
0x180006f24  js      loc_18000701E
0x180006f2a  lea     rcx, [rsp+1A0h+LastAccessTime]
0x180006f2f  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x180006f34  mov     rdi, qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime]
0x180006f39  mov     rcx, [rsi+390h]
0x180006f40  mov     rdx, [rsi+360h]
0x180006f47  mov     r8, [rsi+370h]
0x180006f4e  mov     r9, [rsi+368h]
0x180006f55  mov     rax, [rdi]
0x180006f58  mov     qword ptr [rsp+1A0h+CreateDisposition], rcx
0x180006f5d  mov     qword ptr [rsp+1A0h+ShareAccess], rdx
0x180006f62  mov     qword ptr [rsp+1A0h+FileAttributes], r8
0x180006f67  mov     [rsp+1A0h+AllocationSize], r9
0x180006f6c  mov     r9, [rsi+2C0h]
0x180006f73  mov     r8d, 80000000h
0x180006f79  mov     rdx, rbx
0x180006f7c  mov     rcx, rdi
0x180006f7f  mov     rax, [rax+78h]
0x180006f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f88  mov     r15d, eax
0x180006f8b  test    eax, eax
0x180006f8d  js      loc_18000701E
0x180006f93  mov     rcx, rsi; this
0x180006f96  call    ?IsOplockBroken@CFileAccessor@@AEAAHXZ; CFileAccessor::IsOplockBroken(void)
0x180006f9b  test    eax, eax
0x180006f9d  jz      short loc_180006FED
0x180006f9f  lea     rcx, [rsp+1A0h+LastAccessTime]
0x180006fa4  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x180006fa9  mov     eax, 80070020h
0x180006fae  jmp     loc_18000704A
0x180006fb3  mov     rax, [rsi+380h]
0x180006fba  cmp     byte ptr [rax+98h], 0
0x180006fc1  jz      loc_180006EFD
0x180006fc7  mov     qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime], 0FFFFFFFFFFFFFFFFh
0x180006fd0  xor     r9d, r9d; lpLastWriteTime
0x180006fd3  lea     r8, [rsp+1A0h+LastAccessTime]; lpLastAccessTime
0x180006fd8  xor     edx, edx; lpCreationTime
0x180006fda  mov     rcx, rbx; hFile
0x180006fdd  call    cs:__imp_SetFileTime
0x180006fe3  mov     qword ptr [rsp+1A0h+LastAccessTime.dwLowDateTime], r13
0x180006fe8  jmp     loc_180006F0A
0x180006fed  mov     rax, [rdi]
0x180006ff0  mov     rcx, rdi
0x180006ff3  mov     rax, [rax+8]
0x180006ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ffc  mov     [r12], rdi
0x180007000  lea     rcx, [rsi+0D8h]
0x180007007  mov     rdx, rdi
0x18000700a  call    ??4?$TComPointer@VCFileStream@@@@QEAAPEAVCFileStream@@PEAV1@@Z; TComPointer<CFileStream>::operator=(CFileStream *)
0x18000700f  lea     rcx, [rsp+1A0h+LastAccessTime]
0x180007014  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x180007019  mov     eax, r15d
0x18000701c  jmp     short loc_18000704A
0x18000701e  lea     rcx, [rsp+1A0h+LastAccessTime]
0x180007023  call    ??1?$TComPointer@VCFileStream@@@@QEAA@XZ; TComPointer<CFileStream>::~TComPointer<CFileStream>(void)
0x180007028  lea     rax, [rbx-1]
0x18000702c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180007030  ja      short loc_18000703B
0x180007032  mov     rcx, rbx; hObject
0x180007035  call    cs:__imp_CloseHandle
0x18000703b  mov     eax, r15d
0x18000703e  jmp     short loc_18000704A
0x180007040  mov     eax, r13d
0x180007043  jmp     short loc_18000704A
0x180007045  mov     eax, 8000FFFFh
0x18000704a  mov     rcx, [rbp+0A0h+var_40]
0x18000704e  xor     rcx, rsp; StackCookie
0x180007051  call    __security_check_cookie
0x180007056  mov     rbx, [rsp+1A0h+arg_10]
0x18000705e  add     rsp, 170h
0x180007065  pop     r15
0x180007067  pop     r14
0x180007069  pop     r13
0x18000706b  pop     r12
0x18000706d  pop     rdi
0x18000706e  pop     rsi
0x18000706f  pop     rbp
0x180007070  retn
```
