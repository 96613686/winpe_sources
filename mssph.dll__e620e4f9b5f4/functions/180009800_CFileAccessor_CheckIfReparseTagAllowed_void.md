# CFileAccessor::CheckIfReparseTagAllowed(void)

- ea: `0x180009800`
- end: `0x1800098e1`
- name: `?CheckIfReparseTagAllowed@CFileAccessor@@AEAAJXZ`
- size: `225`
- prototype: `__int64 __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x180003970`

## callees

- `0x180009800`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800098cb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1800098cb`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x180009896`
- `ntdll!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x180009896`
- `ntdll!RtlIsPartialPlaceholder` at `0x18000985e`
- `ntdll!RtlIsPartialPlaceholder` at `0x18000985e`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180009841`
- `ntdll!RtlIsCloudFilesPlaceholder` at `0x180009841`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000982a`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000982a`

## pseudocode

```c
__int64 __fastcall CFileAccessor::CheckIfReparseTagAllowed(HANDLE *this)
{
  BOOL FileInformationByHandle; // eax
  __int64 v3; // rcx
  char v4; // di
  char IsCloudFilesPlaceholder; // al
  __int64 v6; // rdx
  __int64 v7; // rcx
  char v8; // al
  char v9; // di
  char IsPartialPlaceholder; // al
  bool v11; // zf
  unsigned int v13; // eax
  char IsNonEmptyDirectoryReparsePointAllowed; // al
  __int64 FileInformation; // [rsp+30h] [rbp+8h] BYREF

  FileInformation = 0;
  FileInformationByHandle = GetFileInformationByHandleEx(this[13], FileAttributeTagInfo, &FileInformation, 8u);
  v3 = FileInformation;
  if ( FileInformationByHandle )
  {
    if ( (FileInformation & 0x400) != 0 )
    {
      v13 = HIDWORD(FileInformation);
      *((_DWORD *)this + 23) = HIDWORD(FileInformation);
      if ( (v3 & 0x10) != 0 )
      {
        IsNonEmptyDirectoryReparsePointAllowed = RtlIsNonEmptyDirectoryReparsePointAllowed(v13);
        v3 = FileInformation;
        *((_BYTE *)this + 90) = IsNonEmptyDirectoryReparsePointAllowed != 0;
      }
    }
  }
  v4 = *((_BYTE *)this + 88);
  IsCloudFilesPlaceholder = RtlIsCloudFilesPlaceholder(v3, HIDWORD(FileInformation));
  v6 = HIDWORD(FileInformation);
  v7 = (unsigned int)FileInformation;
  v8 = v4 | (IsCloudFilesPlaceholder != 0);
  v9 = *((_BYTE *)this + 89);
  *((_BYTE *)this + 88) = v8;
  IsPartialPlaceholder = RtlIsPartialPlaceholder(v7, v6);
  v11 = *((_BYTE *)this + 88) == 0;
  *((_BYTE *)this + 89) = v9 | (IsPartialPlaceholder != 0);
  if ( !v11 )
    return 0;
  if ( *((_BYTE *)this + 90) )
    return 0;
  if ( !*((_DWORD *)this + 23) )
    return 0;
  InitOnceExecuteOnce(
    &g_initOnceOnPerUserCatalogCheck,
    _lambda_f0b3a3176349e3c23c9c4546c2833d77_::_lambda_invoker_cdecl_,
    0,
    0);
  if ( g_isPerUserCatalogEnabled )
    return 0;
  else
    return 2147749127LL;
}

```

## disassembly

```asm
0x180009800  mov     [rsp+arg_8], rbx
0x180009805  push    rdi
0x180009806  sub     rsp, 20h
0x18000980a  mov     rbx, rcx
0x18000980d  mov     [rsp+28h+FileInformation], 0
0x180009816  mov     rcx, [rcx+68h]; hFile
0x18000981a  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x18000981f  mov     r9d, 8; dwBufferSize
0x180009825  mov     edx, 9; FileInformationClass
0x18000982a  call    cs:__imp_GetFileInformationByHandleEx
0x180009830  mov     rcx, [rsp+28h+FileInformation]
0x180009835  test    eax, eax
0x180009837  jnz     short loc_180009882
0x180009839  mov     edx, dword ptr [rsp+28h+FileInformation+4]
0x18000983d  movzx   edi, byte ptr [rbx+58h]
0x180009841  call    cs:__imp_RtlIsCloudFilesPlaceholder
0x180009847  mov     edx, dword ptr [rsp+28h+FileInformation+4]
0x18000984b  test    al, al
0x18000984d  mov     ecx, dword ptr [rsp+28h+FileInformation]
0x180009851  setnz   al
0x180009854  or      al, dil
0x180009857  movzx   edi, byte ptr [rbx+59h]
0x18000985b  mov     [rbx+58h], al
0x18000985e  call    cs:__imp_RtlIsPartialPlaceholder
0x180009864  test    al, al
0x180009866  setnz   al
0x180009869  or      al, dil
0x18000986c  cmp     byte ptr [rbx+58h], 0
0x180009870  mov     [rbx+59h], al
0x180009873  jz      short loc_1800098AB
0x180009875  xor     eax, eax
0x180009877  mov     rbx, [rsp+28h+arg_8]
0x18000987c  add     rsp, 20h
0x180009880  pop     rdi
0x180009881  retn
0x180009882  bt      ecx, 0Ah
0x180009886  jnb     short loc_180009839
0x180009888  mov     eax, dword ptr [rsp+28h+FileInformation+4]
0x18000988c  mov     [rbx+5Ch], eax
0x18000988f  test    cl, 10h
0x180009892  jz      short loc_180009839
0x180009894  mov     ecx, eax
0x180009896  call    cs:__imp_RtlIsNonEmptyDirectoryReparsePointAllowed
0x18000989c  mov     rcx, [rsp+28h+FileInformation]
0x1800098a1  test    al, al
0x1800098a3  setnz   al
0x1800098a6  mov     [rbx+5Ah], al
0x1800098a9  jmp     short loc_180009839
0x1800098ab  cmp     byte ptr [rbx+5Ah], 0
0x1800098af  jnz     short loc_180009875
0x1800098b1  cmp     dword ptr [rbx+5Ch], 0
0x1800098b5  jz      short loc_180009875
0x1800098b7  xor     r9d, r9d; Context
0x1800098ba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_f0b3a3176349e3c23c9c4546c2833d77_@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x1800098c1  xor     r8d, r8d; Parameter
0x1800098c4  lea     rcx, ?g_initOnceOnPerUserCatalogCheck@@3T_RTL_RUN_ONCE@@A; InitOnce
0x1800098cb  call    cs:__imp_InitOnceExecuteOnce
0x1800098d1  cmp     cs:?g_isPerUserCatalogEnabled@@3_NA, 0; bool g_isPerUserCatalogEnabled
0x1800098d8  jnz     short loc_180009875
0x1800098da  mov     eax, 80040D07h
0x1800098df  jmp     short loc_180009877
```
