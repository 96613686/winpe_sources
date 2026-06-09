# CVolume::GetFileSize(_DF_FILE_ID_128 *,__int64 *)

- ea: `0x180063850`
- end: `0x180063a8e`
- name: `?GetFileSize@CVolume@@UEAAJPEAU_DF_FILE_ID_128@@PEA_J@Z`
- size: `574`
- prototype: `__int64 __fastcall(CVolume *__hidden this, struct _DF_FILE_ID_128 *, __int64 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x18001a630`
- `0x180063850`
- `0x180067b30`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180063998`
- `ntdll!NtCreateFile` at `0x180063998`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063a54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180063a54`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180063a0d`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x180063a0d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CVolume::GetFileSize(CVolume *this, struct _DF_FILE_ID_128 *a2, __int64 *a3)
{
  __int16 v6; // ax
  unsigned int LastFailureAsHRESULT; // ebx
  void *v8; // rcx
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v16; // [rsp+68h] [rbp-98h] BYREF
  __int16 v17; // [rsp+6Ch] [rbp-94h]
  __int16 v18; // [rsp+6Eh] [rbp-92h]
  __int128 v19; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE FileInformation[20]; // [rsp+F0h] [rbp-10h] BYREF
  int v23; // [rsp+104h] [rbp+4h]

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v16, "CVolume::GetFileSize", 2663, 1);
  FileHandle = (void *)-1LL;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  v19 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v23 = 0;
  v6 = 2671;
  if ( !a2 || (v17 = 2671, v6 = 2672, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_3:
    v18 = v6;
    goto LABEL_17;
  }
  v17 = 2672;
  v8 = (void *)*((_QWORD *)this + 5);
  v6 = 2674;
  if ( (((unsigned __int64)v8 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = -2147467259;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 2674;
  LODWORD(v19) = 1048592;
  *((_QWORD *)&v19 + 1) = a2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = v8;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v19;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtCreateFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x6000u, 0, 0);
  if ( v9 < 0 )
  {
    if ( v9 == -1073741533 || v9 == -1073741738 )
    {
      LastFailureAsHRESULT = -805306077;
      v6 = 2697;
    }
    else
    {
      LastFailureAsHRESULT = -1996488674;
      v6 = 2701;
    }
    goto LABEL_3;
  }
  v6 = 2705;
  if ( (((unsigned __int64)FileHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastFailureAsHRESULT = -1996488674;
    goto LABEL_3;
  }
  v16 = 0;
  v17 = 2705;
  if ( !GetFileInformationByHandleEx(FileHandle, FileStandardInfo, FileInformation, 0x18u) )
  {
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v11, v10, v12, v13);
    v16 = LastFailureAsHRESULT;
    v18 = 2707;
    goto LABEL_18;
  }
  LastFailureAsHRESULT = 0;
  v17 = 2707;
  *a3 = *(_QWORD *)FileInformation;
LABEL_17:
  v16 = LastFailureAsHRESULT;
LABEL_18:
  if ( (char *)FileHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(FileHandle);
    FileHandle = (void *)-1LL;
  }
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v16);
  return LastFailureAsHRESULT;
}

```

## disassembly

```asm
0x180063850  mov     [rsp-8+arg_18], rbx
0x180063855  push    rbp
0x180063856  push    rsi
0x180063857  push    rdi
0x180063858  lea     rbp, [rsp-10h]
0x18006385d  sub     rsp, 110h
0x180063864  mov     rax, cs:__security_cookie
0x18006386b  xor     rax, rsp
0x18006386e  mov     [rbp+20h+var_18], rax
0x180063872  mov     rdi, r8
0x180063875  mov     rsi, rdx
0x180063878  mov     rbx, rcx
0x18006387b  mov     r9d, 1; unsigned __int16
0x180063881  mov     r8d, 0A67h; unsigned __int16
0x180063887  lea     rdx, aCvolumeGetfile; "CVolume::GetFileSize"
0x18006388e  lea     rcx, [rsp+120h+var_B8]; this
0x180063893  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180063898  nop
0x180063899  mov     [rsp+120h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800638a2  xorps   xmm0, xmm0
0x1800638a5  movups  xmmword ptr [rbp+20h+ObjectAttributes.Length], xmm0
0x1800638a9  movups  xmmword ptr [rbp+20h+ObjectAttributes.ObjectName], xmm0
0x1800638ad  movups  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800638b1  movups  xmmword ptr [rbp+20h+IoStatusBlock], xmm0
0x1800638b5  xorps   xmm1, xmm1
0x1800638b8  movups  [rbp+20h+var_80], xmm1
0x1800638bc  mov     dword ptr [rbp+20h+FileInformation], 0
0x1800638c3  xor     eax, eax
0x1800638c5  movups  xmmword ptr [rbp+20h+FileInformation+4], xmm0
0x1800638c9  mov     [rbp+20h+var_1C], eax
0x1800638cc  mov     eax, 0A6Fh
0x1800638d1  test    rsi, rsi
0x1800638d4  jnz     short loc_1800638E5
0x1800638d6  mov     ebx, 80070057h
0x1800638db  mov     [rsp+120h+var_B2], ax
0x1800638e0  jmp     loc_180063A41
0x1800638e5  mov     [rsp+120h+var_B4], ax
0x1800638ea  mov     eax, 0A70h
0x1800638ef  test    rdi, rdi
0x1800638f2  jz      short loc_1800638D6
0x1800638f4  mov     [rsp+120h+var_B4], ax
0x1800638f9  mov     rcx, [rbx+28h]
0x1800638fd  lea     rax, [rcx+1]
0x180063901  test    rax, 0FFFFFFFFFFFFFFFEh
0x180063907  mov     eax, 0A72h
0x18006390c  jnz     short loc_180063915
0x18006390e  mov     ebx, 80004005h
0x180063913  jmp     short loc_1800638DB
0x180063915  mov     [rsp+120h+var_B8], 0
0x18006391d  mov     [rsp+120h+var_B4], ax
0x180063922  mov     dword ptr [rbp+20h+var_80], 100010h
0x180063929  mov     qword ptr [rbp+20h+var_80+8], rsi
0x18006392d  mov     [rbp+20h+ObjectAttributes.Length], 30h ; '0'
0x180063934  mov     [rbp+20h+ObjectAttributes.RootDirectory], rcx
0x180063938  mov     [rbp+20h+ObjectAttributes.Attributes], 40h ; '@'
0x18006393f  lea     rax, [rbp+20h+var_80]
0x180063943  mov     [rbp+20h+ObjectAttributes.ObjectName], rax
0x180063947  movdqu  xmmword ptr [rbp+20h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006394c  mov     [rsp+120h+EaLength], 0; EaLength
0x180063954  mov     [rsp+120h+EaBuffer], 0; EaBuffer
0x18006395d  mov     [rsp+120h+CreateOptions], 6000h; CreateOptions
0x180063965  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x18006396d  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x180063975  mov     [rsp+120h+FileAttributes], 0; FileAttributes
0x18006397d  mov     [rsp+120h+AllocationSize], 0; AllocationSize
0x180063986  lea     r9, [rbp+20h+IoStatusBlock]; IoStatusBlock
0x18006398a  lea     r8, [rbp+20h+ObjectAttributes]; ObjectAttributes
0x18006398e  mov     edx, 80h; DesiredAccess
0x180063993  lea     rcx, [rsp+120h+FileHandle]; FileHandle
0x180063998  call    cs:__imp_NtCreateFile
0x18006399e  test    eax, eax
0x1800639a0  jns     short loc_1800639CE
0x1800639a2  cmp     eax, 0C0000123h
0x1800639a7  jz      short loc_1800639BF
0x1800639a9  cmp     eax, 0C0000056h
0x1800639ae  jz      short loc_1800639BF
0x1800639b0  mov     ebx, 8900001Eh
0x1800639b5  mov     eax, 0A8Dh
0x1800639ba  jmp     loc_1800638DB
0x1800639bf  mov     ebx, 0D0000123h
0x1800639c4  mov     eax, 0A89h
0x1800639c9  jmp     loc_1800638DB
0x1800639ce  mov     rax, [rsp+120h+FileHandle]
0x1800639d3  inc     rax
0x1800639d6  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800639dc  mov     eax, 0A91h
0x1800639e1  jnz     short loc_1800639ED
0x1800639e3  mov     ebx, 8900001Eh
0x1800639e8  jmp     loc_1800638DB
0x1800639ed  mov     [rsp+120h+var_B8], 0
0x1800639f5  mov     [rsp+120h+var_B4], ax
0x1800639fa  mov     r9d, 18h; dwBufferSize
0x180063a00  lea     r8, [rbp+20h+FileInformation]; lpFileInformation
0x180063a04  lea     edx, [r9-17h]; FileInformationClass
0x180063a08  mov     rcx, [rsp+120h+FileHandle]; hFile
0x180063a0d  call    cs:__imp_GetFileInformationByHandleEx
0x180063a13  test    eax, eax
0x180063a15  jnz     short loc_180063A2E
0x180063a17  call    GetLastFailureAsHRESULT
0x180063a1c  mov     ebx, eax
0x180063a1e  mov     [rsp+120h+var_B8], eax
0x180063a22  mov     eax, 0A93h
0x180063a27  mov     [rsp+120h+var_B2], ax
0x180063a2c  jmp     short loc_180063A45
0x180063a2e  xor     ebx, ebx
0x180063a30  mov     eax, 0A93h
0x180063a35  mov     [rsp+120h+var_B4], ax
0x180063a3a  mov     rax, qword ptr [rbp+20h+FileInformation]
0x180063a3e  mov     [rdi], rax
0x180063a41  mov     [rsp+120h+var_B8], ebx
0x180063a45  mov     rcx, [rsp+120h+FileHandle]; hObject
0x180063a4a  lea     rdx, [rcx-1]
0x180063a4e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180063a52  ja      short loc_180063A63
0x180063a54  call    cs:__imp_CloseHandle
0x180063a5a  mov     [rsp+120h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180063a63  lea     rcx, [rsp+120h+var_B8]; this
0x180063a68  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x180063a6d  mov     eax, ebx
0x180063a6f  mov     rcx, [rbp+20h+var_18]
0x180063a73  xor     rcx, rsp; StackCookie
0x180063a76  call    __security_check_cookie
0x180063a7b  mov     rbx, [rsp+120h+arg_18]
0x180063a83  add     rsp, 110h
0x180063a8a  pop     rdi
0x180063a8b  pop     rsi
0x180063a8c  pop     rbp
0x180063a8d  retn
```
