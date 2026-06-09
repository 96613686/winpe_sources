# Dlp::FileMetadata::DataStore::ReadKernelEA(RealtimeProtection::DlpFilePath const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::optional<std::vector<uchar,std::allocator<uchar>>> &)

- ea: `0x1801c32c8`
- end: `0x1801c3599`
- name: `?ReadKernelEA@DataStore@FileMetadata@Dlp@@YAJAEBVDlpFilePath@RealtimeProtection@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$optional@V?$vector@EV?$allocator@E@std@@@std@@@7@@Z`
- size: `721`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801bce50`

## callees

- `0x180065394`
- `0x180065438`
- `0x1800a1824`
- `0x18010cb40`
- `0x18010d700`
- `0x1801c2498`
- `0x1801c3190`
- `0x1801c32c8`
- `0x1801c359c`
- `0x1801c35ec`
- `0x18023a290`
- `0x18023a310`

## import_xrefs

- `ntdll!ZwQueryEaFile` at `0x1801c3407`
- `ntdll!ZwQueryEaFile` at `0x1801c34c7`
- `ntdll!ZwQueryEaFile` at `0x1801c3407`
- `ntdll!ZwQueryEaFile` at `0x1801c34c7`
- `KERNEL32!CreateFileW` at `0x1801c3389`
- `KERNEL32!CreateFileW` at `0x1801c3389`

## string_xrefs

- `0x1801c33a9`: `failed to open a file for getting EA`
- `0x1801c3320`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\read_kernel_ea.cpp`
- `0x1801c33b0`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\read_kernel_ea.cpp`
- `0x1801c3465`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\read_kernel_ea.cpp`
- `0x1801c34f8`: `src\epp\Dlp\FileMetadataBroker\data_store\fs_utils\src\read_kernel_ea.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Dlp::FileMetadata::DataStore::ReadKernelEA(_QWORD *a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  __int64 v8; // rax
  HANDLE FileW; // rbx
  unsigned int LastErrorMsg; // eax
  NTSTATUS v11; // eax
  __int64 v12; // r8
  NTSTATUS v13; // eax
  __int64 v14; // r8
  unsigned int EAData; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  HANDLE v20; // [rsp+50h] [rbp-B0h] BYREF
  PVOID v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-90h] BYREF
  _BYTE Buffer[4096]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+10A8h] [rbp+FA8h]

  if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1) + 16) )
  {
    v5 = 165;
LABEL_3:
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\read_kernel_ea.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    return v6;
  }
  if ( !qword_180311AD8 )
  {
    v5 = 166;
    goto LABEL_3;
  }
  v8 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  if ( *(_QWORD *)(v8 + 24) > 7u )
    v8 = *(_QWORD *)v8;
  FileW = CreateFileW((LPCWSTR)v8, 8u, 0, 0, 3u, 0x80u, 0);
  v20 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                     retaddr,
                     (void *)0xB1,
                     (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\read_kernel_ea.cpp",
                     "failed to open a file for getting EA",
                     dwCreationDispositiona);
    goto LABEL_13;
  }
  IoStatusBlock = 0;
  memset(Buffer, 0, sizeof(Buffer));
  v11 = ZwQueryEaFile(FileW, &IoStatusBlock, Buffer, 0x1000u, 0, 0, 0, 0, 1u);
  if ( v11 >= 0 )
  {
    LastErrorMsg = Dlp::FileMetadata::DataStore::_anonymous_namespace_::GetEAData(
                     Buffer,
                     LODWORD(IoStatusBlock.Information),
                     v12,
                     a3);
    goto LABEL_13;
  }
  if ( v11 != -1073741772 && v11 != -1073741742 )
  {
    if ( v11 == -1073741789 || v11 == -2147483643 )
    {
      *(_OWORD *)v21 = 0;
      v22 = 0;
      std::vector<unsigned char>::vector<unsigned char>(v21, 0x4000);
      v13 = ZwQueryEaFile(FileW, &IoStatusBlock, v21[0], LODWORD(v21[1]) - LODWORD(v21[0]), 0, 0, 0, 0, 1u);
      if ( v13 == -1073741772 || v13 == -1073741742 )
      {
        if ( *(_BYTE *)(a3 + 24) )
        {
          std::vector<unsigned char>::_Tidy(a3);
          *(_BYTE *)(a3 + 24) = 0;
        }
        std::vector<unsigned char>::_Tidy(v21);
        v6 = 0;
      }
      else
      {
        if ( v13 >= 0 )
        {
          EAData = Dlp::FileMetadata::DataStore::_anonymous_namespace_::GetEAData(
                     v21[0],
                     LODWORD(IoStatusBlock.Information),
                     v14,
                     a3);
        }
        else
        {
          _mm_lfence();
          EAData = wil::details::in1diag3::Return_NtStatusMsg(
                     retaddr,
                     (void *)0xE8,
                     (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\read_kernel_ea.cpp",
                     (const char *)(unsigned int)v13,
                     (int)"ZwQueryEaFile failed",
                     dwFlagsAndAttributesa);
        }
        v6 = EAData;
        std::vector<unsigned char>::_Tidy(v21);
      }
      goto LABEL_28;
    }
    _mm_lfence();
    LastErrorMsg = wil::details::in1diag3::Return_NtStatusMsg(
                     retaddr,
                     (void *)0xD3,
                     (unsigned int)"src\\epp\\Dlp\\FileMetadataBroker\\data_store\\fs_utils\\src\\read_kernel_ea.cpp",
                     (const char *)(unsigned int)v11,
                     (int)"ZwQueryEaFile failed",
                     dwFlagsAndAttributes);
LABEL_13:
    v6 = LastErrorMsg;
LABEL_28:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
    return v6;
  }
  if ( *(_BYTE *)(a3 + 24) )
  {
    std::vector<unsigned char>::_Tidy(a3);
    *(_BYTE *)(a3 + 24) = 0;
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  return 0;
}

```

## disassembly

```asm
0x1801c32c8  mov     [rsp-8+arg_8], rbx
0x1801c32cd  push    rbp
0x1801c32ce  push    rdi
0x1801c32cf  push    r14
0x1801c32d1  lea     rbp, [rsp-0F90h]
0x1801c32d9  mov     eax, 1090h
0x1801c32de  call    _alloca_probe
0x1801c32e3  sub     rsp, rax
0x1801c32e6  mov     rax, cs:__security_cookie
0x1801c32ed  xor     rax, rsp
0x1801c32f0  mov     [rbp+0FA0h+var_20], rax
0x1801c32f7  mov     rdi, r8
0x1801c32fa  mov     rbx, rcx
0x1801c32fd  mov     rcx, [rcx]
0x1801c3300  mov     rax, [rcx]
0x1801c3303  mov     rax, [rax+10h]
0x1801c3307  call    cs:__guard_dispatch_icall_fptr
0x1801c330d  xor     r14d, r14d
0x1801c3310  cmp     [rax+10h], r14
0x1801c3314  jnz     short loc_1801C333D
0x1801c3316  mov     edx, 0A5h; void *
0x1801c331b  mov     ebx, 80070057h
0x1801c3320  lea     r8, aSrcEppDlpFilem_2; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c3327  mov     r9d, ebx; char *
0x1801c332a  mov     rcx, [rbp+0FA8h]; this
0x1801c3331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801c3336  mov     eax, ebx
0x1801c3338  jmp     loc_1801C3576
0x1801c333d  cmp     cs:qword_180311AD8, r14
0x1801c3344  jnz     short loc_1801C334D
0x1801c3346  mov     edx, 0A6h
0x1801c334b  jmp     short loc_1801C331B
0x1801c334d  mov     rcx, [rbx]
0x1801c3350  mov     rax, [rcx]
0x1801c3353  mov     rax, [rax+10h]
0x1801c3357  call    cs:__guard_dispatch_icall_fptr
0x1801c335d  cmp     qword ptr [rax+18h], 7
0x1801c3362  jbe     short loc_1801C3367
0x1801c3364  mov     rax, [rax]
0x1801c3367  mov     [rsp+10A0h+hTemplateFile], r14; hTemplateFile
0x1801c336c  mov     [rsp+10A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801c3374  mov     [rsp+10A0h+dwCreationDisposition], 3; char *
0x1801c337c  xor     r9d, r9d; lpSecurityAttributes
0x1801c337f  xor     r8d, r8d; dwShareMode
0x1801c3382  lea     edx, [r9+8]; dwDesiredAccess
0x1801c3386  mov     rcx, rax; lpFileName
0x1801c3389  call    cs:__imp_CreateFileW
0x1801c338f  mov     rbx, rax
0x1801c3392  mov     [rsp+10A0h+var_1050], rax
0x1801c3397  inc     rax
0x1801c339a  test    rax, 0FFFFFFFFFFFFFFFEh
0x1801c33a0  jnz     short loc_1801C33C3
0x1801c33a2  mov     rcx, [rbp+0FA8h]; this
0x1801c33a9  lea     r9, aFailedToOpenAF; "failed to open a file for getting EA"
0x1801c33b0  lea     r8, aSrcEppDlpFilem_2; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c33b7  mov     edx, 0B1h; void *
0x1801c33bc  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1801c33c1  jmp     short loc_1801C3421
0x1801c33c3  xorps   xmm0, xmm0
0x1801c33c6  movups  xmmword ptr [rsp+10A0h+IoStatusBlock], xmm0
0x1801c33cb  xor     edx, edx; Val
0x1801c33cd  mov     r8d, 1000h; Size
0x1801c33d3  lea     rcx, [rbp+0FA0h+Buffer]; void *
0x1801c33d7  call    memset
0x1801c33dc  mov     [rsp+10A0h+RestartScan], 1; RestartScan
0x1801c33e1  mov     [rsp+10A0h+EaIndex], r14; EaIndex
0x1801c33e6  mov     dword ptr [rsp+10A0h+hTemplateFile], r14d; EaListLength
0x1801c33eb  mov     qword ptr [rsp+10A0h+dwFlagsAndAttributes], r14; char *
0x1801c33f0  mov     byte ptr [rsp+10A0h+dwCreationDisposition], r14b; ReturnSingleEntry
0x1801c33f5  mov     r9d, 1000h; Length
0x1801c33fb  lea     r8, [rbp+0FA0h+Buffer]; Buffer
0x1801c33ff  lea     rdx, [rsp+10A0h+IoStatusBlock]; IoStatusBlock
0x1801c3404  mov     rcx, rbx; FileHandle
0x1801c3407  call    cs:__imp_ZwQueryEaFile
0x1801c340d  test    eax, eax
0x1801c340f  js      short loc_1801C3428
0x1801c3411  mov     r9, rdi
0x1801c3414  mov     edx, dword ptr [rsp+10A0h+IoStatusBlock.Information]
0x1801c3418  lea     rcx, [rbp+0FA0h+Buffer]
0x1801c341c  call    Dlp__FileMetadata__DataStore___anonymous_namespace___GetEAData
0x1801c3421  mov     ebx, eax
0x1801c3423  jmp     loc_1801C3549
0x1801c3428  cmp     eax, 0C0000034h
0x1801c342d  jz      loc_1801C3558
0x1801c3433  cmp     eax, 0C0000052h
0x1801c3438  jz      loc_1801C3558
0x1801c343e  cmp     eax, 0C0000023h
0x1801c3443  jz      short loc_1801C3478
0x1801c3445  cmp     eax, 80000005h
0x1801c344a  jz      short loc_1801C3478
0x1801c344c  lfence
0x1801c344f  mov     rcx, [rbp+0FA8h]; this
0x1801c3456  lea     rdx, aZwqueryeafileF; "ZwQueryEaFile failed"
0x1801c345d  mov     qword ptr [rsp+10A0h+dwCreationDisposition], rdx; int
0x1801c3462  mov     r9d, eax; char *
0x1801c3465  lea     r8, aSrcEppDlpFilem_2; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c346c  mov     edx, 0D3h; void *
0x1801c3471  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1801c3476  jmp     short loc_1801C3421
0x1801c3478  xorps   xmm0, xmm0
0x1801c347b  xor     eax, eax
0x1801c347d  movups  xmmword ptr [rsp+10A0h+var_1048], xmm0
0x1801c3482  mov     [rsp+10A0h+var_1038], rax
0x1801c3487  mov     edx, 4000h
0x1801c348c  lea     rcx, [rsp+10A0h+var_1048]
0x1801c3491  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x1801c3496  nop
0x1801c3497  mov     r9d, dword ptr [rsp+10A0h+var_1048+8]
0x1801c349c  sub     r9d, dword ptr [rsp+10A0h+var_1048]; Length
0x1801c34a1  mov     [rsp+10A0h+RestartScan], 1; RestartScan
0x1801c34a6  mov     [rsp+10A0h+EaIndex], r14; EaIndex
0x1801c34ab  mov     dword ptr [rsp+10A0h+hTemplateFile], r14d; EaListLength
0x1801c34b0  mov     qword ptr [rsp+10A0h+dwFlagsAndAttributes], r14; char *
0x1801c34b5  mov     byte ptr [rsp+10A0h+dwCreationDisposition], r14b; ReturnSingleEntry
0x1801c34ba  mov     r8, [rsp+10A0h+var_1048]; Buffer
0x1801c34bf  lea     rdx, [rsp+10A0h+IoStatusBlock]; IoStatusBlock
0x1801c34c4  mov     rcx, rbx; FileHandle
0x1801c34c7  call    cs:__imp_ZwQueryEaFile
0x1801c34cd  cmp     eax, 0C0000034h
0x1801c34d2  jz      short loc_1801C352A
0x1801c34d4  cmp     eax, 0C0000052h
0x1801c34d9  jz      short loc_1801C352A
0x1801c34db  test    eax, eax
0x1801c34dd  jns     short loc_1801C3517
0x1801c34df  lfence
0x1801c34e2  mov     rcx, [rbp+0FA8h]; this
0x1801c34e9  lea     rdx, aZwqueryeafileF; "ZwQueryEaFile failed"
0x1801c34f0  mov     qword ptr [rsp+10A0h+dwCreationDisposition], rdx; int
0x1801c34f5  mov     r9d, eax; char *
0x1801c34f8  lea     r8, aSrcEppDlpFilem_2; "src\\epp\\Dlp\\FileMetadataBroker\\data"...
0x1801c34ff  mov     edx, 0E8h; void *
0x1801c3504  call    ?Return_NtStatusMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_NtStatusMsg(void *,uint,char const *,long,char const *,...)
0x1801c3509  mov     ebx, eax
0x1801c350b  lea     rcx, [rsp+10A0h+var_1048]
0x1801c3510  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c3515  jmp     short loc_1801C3549
0x1801c3517  mov     r9, rdi
0x1801c351a  mov     edx, dword ptr [rsp+10A0h+IoStatusBlock.Information]
0x1801c351e  mov     rcx, [rsp+10A0h+var_1048]
0x1801c3523  call    Dlp__FileMetadata__DataStore___anonymous_namespace___GetEAData
0x1801c3528  jmp     short loc_1801C3509
0x1801c352a  cmp     [rdi+18h], r14b
0x1801c352e  jz      short loc_1801C353C
0x1801c3530  mov     rcx, rdi
0x1801c3533  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c3538  mov     [rdi+18h], r14b
0x1801c353c  lea     rcx, [rsp+10A0h+var_1048]
0x1801c3541  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c3546  mov     ebx, r14d
0x1801c3549  lea     rcx, [rsp+10A0h+var_1050]
0x1801c354e  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c3553  jmp     loc_1801C3336
0x1801c3558  cmp     [rdi+18h], r14b
0x1801c355c  jz      short loc_1801C356A
0x1801c355e  mov     rcx, rdi
0x1801c3561  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801c3566  mov     [rdi+18h], r14b
0x1801c356a  lea     rcx, [rsp+10A0h+var_1050]
0x1801c356f  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801c3574  xor     eax, eax
0x1801c3576  mov     rcx, [rbp+0FA0h+var_20]
0x1801c357d  xor     rcx, rsp; StackCookie
0x1801c3580  call    __security_check_cookie
0x1801c3585  mov     rbx, [rsp+10A0h+arg_8]
0x1801c358d  add     rsp, 1090h
0x1801c3594  pop     r14
0x1801c3596  pop     rdi
0x1801c3597  pop     rbp
0x1801c3598  retn
```
