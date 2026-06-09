# ShimLogList(char const *,DEBUGLEVEL,char const *,char *)

- ea: `0x1800a3e38`
- end: `0x1800a4241`
- name: `?ShimLogList@@YAXPEBDW4DEBUGLEVEL@@0PEAD@Z`
- size: `1033`
- prototype: `void __high(const char *, enum DEBUGLEVEL, const char *, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180024b2c`

## callees

- `0x18004d120`
- `0x1800a3e38`
- `0x1800a4248`
- `0x180106a60`

## import_xrefs

- `msvcrt!strnlen` at `0x1800a4061`
- `msvcrt!strnlen` at `0x1800a414a`
- `msvcrt!strnlen` at `0x1800a41ae`
- `msvcrt!strnlen` at `0x1800a4061`
- `msvcrt!strnlen` at `0x1800a414a`
- `msvcrt!strnlen` at `0x1800a41ae`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3fc1`
- `ntdll!RtlFreeUnicodeString` at `0x1800a3fc1`
- `ntdll!NtCreateFile` at `0x1800a3fb1`
- `ntdll!NtCreateFile` at `0x1800a3fb1`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a3f25`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800a3f25`
- `ntdll!NtWriteFile` at `0x1800a4101`
- `ntdll!NtWriteFile` at `0x1800a4182`
- `ntdll!NtWriteFile` at `0x1800a41eb`
- `ntdll!NtWriteFile` at `0x1800a4101`
- `ntdll!NtWriteFile` at `0x1800a4182`
- `ntdll!NtWriteFile` at `0x1800a41eb`
- `ntdll!RtlInitUnicodeString` at `0x1800a3f09`
- `ntdll!RtlInitUnicodeString` at `0x1800a3f09`
- `ntdll!NtClose` at `0x1800a41fc`
- `ntdll!NtClose` at `0x1800a41fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a421c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800a421c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a40ad`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a40ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a3fd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x1800a3fd7`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a40c9`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a40c9`

## string_xrefs

- `0x1800a4014`: `MSCTF.DLL`

## pseudocode

```c
void __fastcall ShimLogList(__int64 a1, int a2, const char *a3, char *a4)
{
  NTSTATUS v7; // ebx
  ULONG v8; // esi
  ULONG v9; // eax
  ULONG v10; // eax
  char String[8]; // [rsp+60h] [rbp-C8h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+68h] [rbp-C0h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-B8h] BYREF
  ULONG v14; // [rsp+78h] [rbp-B0h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-A8h] BYREF
  PCWSTR DosPathName[2]; // [rsp+90h] [rbp-98h] BYREF
  const char *v17; // [rsp+A0h] [rbp-88h]
  char *v18; // [rsp+A8h] [rbp-80h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-78h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+E0h] [rbp-48h] BYREF

  v17 = a3;
  v18 = a4;
  SystemTime = 0;
  *(_OWORD *)DosPathName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  ByteOffset.QuadPart = 0;
  strcpy(String, "\r\n");
  FileHandle = (void *)-1LL;
  if ( g_szFileLog )
  {
    if ( g_szMutex )
    {
      if ( g_LogMutex != (HANDLE)-1LL )
      {
        v14 = 0;
        if ( g_LogMutex )
        {
          RtlInitUnicodeString((PUNICODE_STRING)DosPathName, &g_szFileLog);
          if ( RtlDosPathNameToNtPathName_U(DosPathName[1], (PUNICODE_STRING)DosPathName, 0, 0) )
          {
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            ObjectAttributes.ObjectName = (PUNICODE_STRING)DosPathName;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v7 = NtCreateFile(&FileHandle, 0x100004u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 0, 3u, 0x60u, 0, 0);
            RtlFreeUnicodeString((PUNICODE_STRING)DosPathName);
            if ( v7 >= 0 )
            {
              GetLocalTime(&SystemTime);
              if ( StringCbPrintfA(
                     Buffer,
                     0x400u,
                     "%02d/%02d/%04d %02d:%02d:%02d %s %d - ",
                     SystemTime.wMonth,
                     SystemTime.wDay,
                     SystemTime.wYear,
                     SystemTime.wHour,
                     SystemTime.wMinute,
                     SystemTime.wSecond,
                     "MSCTF.DLL",
                     a2) >= 0 )
              {
                v8 = strnlen(Buffer, 0x400u);
                v14 = v8;
                IoStatusBlock.Status = 0;
                IoStatusBlock.Information = 0;
                ByteOffset.QuadPart = 0;
                if ( !WaitForSingleObject(g_LogMutex, 0x1F4u) )
                {
                  SetFilePointer(FileHandle, 0, 0, 2u);
                  if ( NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, v8, &ByteOffset, 0) >= 0
                    && (int)StringCchVPrintfA(Buffer, 0x3FFu, a3, a4) >= 0 )
                  {
                    IoStatusBlock.Status = 0;
                    IoStatusBlock.Information = 0;
                    ByteOffset.QuadPart = 0;
                    v9 = strnlen(Buffer, 0x400u);
                    if ( NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, Buffer, v9, &ByteOffset, 0) >= 0 )
                    {
                      IoStatusBlock.Status = 0;
                      IoStatusBlock.Information = 0;
                      ByteOffset.QuadPart = 0;
                      v10 = strnlen(String, 3u);
                      NtWriteFile(FileHandle, 0, 0, 0, &IoStatusBlock, String, v10, &ByteOffset, 0);
                    }
                  }
                }
                if ( FileHandle != (void *)-1LL )
                {
                  NtClose(FileHandle);
                  FileHandle = (void *)-1LL;
                }
                if ( (char *)g_LogMutex - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
                  ReleaseMutex(g_LogMutex);
              }
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800a3e38  mov     r11, rsp
0x1800a3e3b  push    rbx
0x1800a3e3c  push    rsi
0x1800a3e3d  push    rdi
0x1800a3e3e  push    r12
0x1800a3e40  push    r15
0x1800a3e42  sub     rsp, 100h
0x1800a3e49  mov     rax, cs:__security_cookie
0x1800a3e50  xor     rax, rsp
0x1800a3e53  mov     [rsp+128h+var_38], rax
0x1800a3e5b  mov     r12, r9
0x1800a3e5e  mov     r15, r8
0x1800a3e61  mov     esi, edx
0x1800a3e63  mov     [rsp+128h+var_88], r8
0x1800a3e6b  mov     [rsp+128h+var_80], r9
0x1800a3e73  xorps   xmm0, xmm0
0x1800a3e76  movups  xmmword ptr [r11-48h], xmm0
0x1800a3e7b  xorps   xmm1, xmm1
0x1800a3e7e  movups  xmmword ptr [rsp+128h+DosPathName], xmm1
0x1800a3e86  movups  xmmword ptr [r11-78h], xmm0
0x1800a3e8b  movups  xmmword ptr [r11-68h], xmm0
0x1800a3e90  movups  xmmword ptr [r11-58h], xmm0
0x1800a3e95  movups  xmmword ptr [rsp+128h+IoStatusBlock], xmm0
0x1800a3e9d  xor     edi, edi
0x1800a3e9f  mov     qword ptr [rsp+128h+ByteOffset], rdi
0x1800a3ea4  movzx   eax, word ptr cs:asc_18011F2A0; "\r\n"
0x1800a3eab  mov     word ptr [rsp+128h+String], ax
0x1800a3eb0  mov     al, byte ptr cs:asc_18011F2A0+2; ""
0x1800a3eb6  mov     [rsp+128h+var_C6], al
0x1800a3eba  mov     [rsp+128h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800a3ec3  cmp     cs:?g_szFileLog@@3PAGA, di; ushort near * g_szFileLog
0x1800a3eca  jz      loc_1800A4222
0x1800a3ed0  cmp     cs:?g_szMutex@@3PAGA, di; ushort near * g_szMutex
0x1800a3ed7  jz      loc_1800A4222
0x1800a3edd  mov     rax, cs:?g_LogMutex@@3PEAXEA; void * g_LogMutex
0x1800a3ee4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a3ee8  jz      loc_1800A4222
0x1800a3eee  mov     [rsp+128h+var_B0], edi
0x1800a3ef2  test    rax, rax
0x1800a3ef5  jz      loc_1800A4222
0x1800a3efb  lea     rdx, ?g_szFileLog@@3PAGA; SourceString
0x1800a3f02  lea     rcx, [r11-98h]; DestinationString
0x1800a3f09  call    cs:__imp_RtlInitUnicodeString
0x1800a3f0f  xor     r9d, r9d; DirectoryInfo
0x1800a3f12  xor     r8d, r8d; NtFileNamePart
0x1800a3f15  lea     rdx, [rsp+128h+DosPathName]; NtPathName
0x1800a3f1d  mov     rcx, [rsp+128h+DosPathName+8]; DosPathName
0x1800a3f25  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800a3f2b  test    al, al
0x1800a3f2d  jz      loc_1800A4222
0x1800a3f33  mov     [rsp+128h+ObjectAttributes.Length], 30h ; '0'
0x1800a3f3e  mov     [rsp+128h+ObjectAttributes.RootDirectory], rdi
0x1800a3f46  mov     [rsp+128h+ObjectAttributes.Attributes], 40h ; '@'
0x1800a3f51  lea     rax, [rsp+128h+DosPathName]
0x1800a3f59  mov     [rsp+128h+ObjectAttributes.ObjectName], rax
0x1800a3f61  xorps   xmm0, xmm0
0x1800a3f64  movdqu  xmmword ptr [rsp+128h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a3f6d  mov     [rsp+128h+EaLength], edi; EaLength
0x1800a3f71  mov     [rsp+128h+EaBuffer], rdi; EaBuffer
0x1800a3f76  mov     [rsp+128h+CreateOptions], 60h ; '`'; CreateOptions
0x1800a3f7e  mov     [rsp+128h+CreateDisposition], 3; CreateDisposition
0x1800a3f86  mov     [rsp+128h+ShareAccess], edi; ShareAccess
0x1800a3f8a  mov     [rsp+128h+FileAttributes], 80h; FileAttributes
0x1800a3f92  mov     [rsp+128h+AllocationSize], rdi; AllocationSize
0x1800a3f97  lea     r9, [rsp+128h+IoStatusBlock]; IoStatusBlock
0x1800a3f9f  lea     r8, [rsp+128h+ObjectAttributes]; ObjectAttributes
0x1800a3fa7  mov     edx, 100004h; DesiredAccess
0x1800a3fac  lea     rcx, [rsp+128h+FileHandle]; FileHandle
0x1800a3fb1  call    cs:__imp_NtCreateFile
0x1800a3fb7  mov     ebx, eax
0x1800a3fb9  lea     rcx, [rsp+128h+DosPathName]; UnicodeString
0x1800a3fc1  call    cs:__imp_RtlFreeUnicodeString
0x1800a3fc7  test    ebx, ebx
0x1800a3fc9  js      loc_1800A4222
0x1800a3fcf  lea     rcx, [rsp+128h+SystemTime]; lpSystemTime
0x1800a3fd7  call    cs:__imp_GetLocalTime
0x1800a3fdd  movzx   eax, [rsp+128h+SystemTime.wSecond]
0x1800a3fe5  movzx   ecx, [rsp+128h+SystemTime.wMinute]
0x1800a3fed  movzx   edx, [rsp+128h+SystemTime.wHour]
0x1800a3ff5  movzx   r8d, [rsp+128h+SystemTime.wYear]
0x1800a3ffe  movzx   r10d, [rsp+128h+SystemTime.wDay]
0x1800a4007  movzx   r9d, [rsp+128h+SystemTime.wMonth]
0x1800a4010  mov     [rsp+128h+EaLength], esi
0x1800a4014  lea     r11, aMsctfDll_1; "MSCTF.DLL"
0x1800a401b  mov     [rsp+128h+EaBuffer], r11
0x1800a4020  mov     [rsp+128h+CreateOptions], eax
0x1800a4024  mov     [rsp+128h+CreateDisposition], ecx
0x1800a4028  mov     [rsp+128h+ShareAccess], edx
0x1800a402c  mov     [rsp+128h+FileAttributes], r8d
0x1800a4031  mov     dword ptr [rsp+128h+AllocationSize], r10d
0x1800a4036  lea     r8, a02d02d04d02d02; "%02d/%02d/%04d %02d:%02d:%02d %s %d - "
0x1800a403d  mov     edx, 400h; unsigned __int64
0x1800a4042  lea     rbx, Buffer
0x1800a4049  mov     rcx, rbx; char *
0x1800a404c  call    ?StringCbPrintfA@@YAJPEAD_KPEBDZZ; StringCbPrintfA(char *,unsigned __int64,char const *,...)
0x1800a4051  test    eax, eax
0x1800a4053  js      loc_1800A4222
0x1800a4059  mov     edx, 400h; MaxCount
0x1800a405e  mov     rcx, rbx; String
0x1800a4061  call    cs:__imp_strnlen
0x1800a4067  mov     rsi, rax
0x1800a406a  mov     [rsp+128h+var_B0], eax
0x1800a406e  mov     dword ptr [rsp+128h+IoStatusBlock], edi
0x1800a4075  mov     [rsp+128h+IoStatusBlock.Information], rdi
0x1800a407d  mov     qword ptr [rsp+128h+ByteOffset], rdi
0x1800a4082  jmp     short loc_1800A40A1
0x1800a4084  xor     edi, edi
0x1800a4086  lea     rbx, Buffer
0x1800a408d  mov     esi, [rsp+128h+var_B0]
0x1800a4091  mov     r15, [rsp+128h+var_88]
0x1800a4099  mov     r12, [rsp+128h+var_80]
0x1800a40a1  mov     edx, 1F4h; dwMilliseconds
0x1800a40a6  mov     rcx, cs:?g_LogMutex@@3PEAXEA; hHandle
0x1800a40ad  call    cs:__imp_WaitForSingleObject
0x1800a40b3  test    eax, eax
0x1800a40b5  jnz     loc_1800A41F1
0x1800a40bb  lea     r9d, [rax+2]; dwMoveMethod
0x1800a40bf  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a40c2  xor     edx, edx; lDistanceToMove
0x1800a40c4  mov     rcx, [rsp+128h+FileHandle]; hFile
0x1800a40c9  call    cs:__imp_SetFilePointer
0x1800a40cf  mov     qword ptr [rsp+128h+CreateOptions], rdi; Key
0x1800a40d4  lea     rax, [rsp+128h+ByteOffset]
0x1800a40d9  mov     qword ptr [rsp+128h+CreateDisposition], rax; ByteOffset
0x1800a40de  mov     [rsp+128h+ShareAccess], esi; Length
0x1800a40e2  mov     qword ptr [rsp+128h+FileAttributes], rbx; Buffer
0x1800a40e7  lea     rax, [rsp+128h+IoStatusBlock]
0x1800a40ef  mov     [rsp+128h+AllocationSize], rax; IoStatusBlock
0x1800a40f4  xor     r9d, r9d; ApcContext
0x1800a40f7  xor     r8d, r8d; ApcRoutine
0x1800a40fa  xor     edx, edx; Event
0x1800a40fc  mov     rcx, [rsp+128h+FileHandle]; FileHandle
0x1800a4101  call    cs:__imp_NtWriteFile
0x1800a4107  test    eax, eax
0x1800a4109  js      loc_1800A41F1
0x1800a410f  mov     r9, r12; char *
0x1800a4112  mov     r8, r15; char *
0x1800a4115  mov     edx, 3FFh; unsigned __int64
0x1800a411a  mov     rcx, rbx; char *
0x1800a411d  call    ?StringCchVPrintfA@@YAJPEAD_KPEBD0@Z; StringCchVPrintfA(char *,unsigned __int64,char const *,char *)
0x1800a4122  test    eax, eax
0x1800a4124  js      loc_1800A41F1
0x1800a412a  mov     dword ptr [rsp+128h+IoStatusBlock], edi
0x1800a4131  mov     [rsp+128h+IoStatusBlock.Information], rdi
0x1800a4139  mov     qword ptr [rsp+128h+ByteOffset], 0
0x1800a4142  mov     edx, 400h; MaxCount
0x1800a4147  mov     rcx, rbx; String
0x1800a414a  call    cs:__imp_strnlen
0x1800a4150  mov     qword ptr [rsp+128h+CreateOptions], rdi; Key
0x1800a4155  lea     rcx, [rsp+128h+ByteOffset]
0x1800a415a  mov     qword ptr [rsp+128h+CreateDisposition], rcx; ByteOffset
0x1800a415f  mov     [rsp+128h+ShareAccess], eax; Length
0x1800a4163  mov     qword ptr [rsp+128h+FileAttributes], rbx; Buffer
0x1800a4168  lea     rax, [rsp+128h+IoStatusBlock]
0x1800a4170  mov     [rsp+128h+AllocationSize], rax; IoStatusBlock
0x1800a4175  xor     r9d, r9d; ApcContext
0x1800a4178  xor     r8d, r8d; ApcRoutine
0x1800a417b  xor     edx, edx; Event
0x1800a417d  mov     rcx, [rsp+128h+FileHandle]; FileHandle
0x1800a4182  call    cs:__imp_NtWriteFile
0x1800a4188  test    eax, eax
0x1800a418a  js      short loc_1800A41F1
0x1800a418c  mov     dword ptr [rsp+128h+IoStatusBlock], edi
0x1800a4193  mov     [rsp+128h+IoStatusBlock.Information], rdi
0x1800a419b  mov     qword ptr [rsp+128h+ByteOffset], 0
0x1800a41a4  mov     edx, 3; MaxCount
0x1800a41a9  lea     rcx, [rsp+128h+String]; String
0x1800a41ae  call    cs:__imp_strnlen
0x1800a41b4  mov     qword ptr [rsp+128h+CreateOptions], rdi; Key
0x1800a41b9  lea     rcx, [rsp+128h+ByteOffset]
0x1800a41be  mov     qword ptr [rsp+128h+CreateDisposition], rcx; ByteOffset
0x1800a41c3  mov     [rsp+128h+ShareAccess], eax; Length
0x1800a41c7  lea     rax, [rsp+128h+String]
0x1800a41cc  mov     qword ptr [rsp+128h+FileAttributes], rax; Buffer
0x1800a41d1  lea     rax, [rsp+128h+IoStatusBlock]
0x1800a41d9  mov     [rsp+128h+AllocationSize], rax; IoStatusBlock
0x1800a41de  xor     r9d, r9d; ApcContext
0x1800a41e1  xor     r8d, r8d; ApcRoutine
0x1800a41e4  xor     edx, edx; Event
0x1800a41e6  mov     rcx, [rsp+128h+FileHandle]; FileHandle
0x1800a41eb  call    cs:__imp_NtWriteFile
0x1800a41f1  mov     rcx, [rsp+128h+FileHandle]; Handle
0x1800a41f6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a41fa  jz      short loc_1800A420B
0x1800a41fc  call    cs:__imp_NtClose
0x1800a4202  mov     [rsp+128h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800a420b  mov     rcx, cs:?g_LogMutex@@3PEAXEA; hMutex
0x1800a4212  lea     rax, [rcx-1]
0x1800a4216  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a421a  ja      short loc_1800A4222
0x1800a421c  call    cs:__imp_ReleaseMutex
0x1800a4222  mov     rcx, [rsp+128h+var_38]
0x1800a422a  xor     rcx, rsp; StackCookie
0x1800a422d  call    __security_check_cookie
0x1800a4232  add     rsp, 100h
0x1800a4239  pop     r15
0x1800a423b  pop     r12
0x1800a423d  pop     rdi
0x1800a423e  pop     rsi
0x1800a423f  pop     rbx
0x1800a4240  retn
```
