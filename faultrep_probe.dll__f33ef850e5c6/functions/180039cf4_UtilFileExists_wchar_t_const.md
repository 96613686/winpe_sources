# UtilFileExists(wchar_t const *)

- ea: `0x180039cf4`
- end: `0x180039e46`
- name: `?UtilFileExists@@YA_NPEB_W@Z`
- size: `338`
- prototype: `bool __fastcall(const wchar_t *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180029f1c`
- `0x180035780`

## callees

- `0x1800028b4`
- `0x180009ed8`
- `0x18000aac8`
- `0x180039cf4`
- `0x18003cbb8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039dfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039dfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dbe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039dbe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039da8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180039da8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039d6d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180039d6d`

## pseudocode

```c
char __fastcall UtilFileExists(const wchar_t *a1)
{
  int v1; // edi
  DWORD FileAttributesW; // eax
  char v3; // bl
  char v4; // bl
  HANDLE FileW; // rax
  char LastError; // al
  int v8; // edx
  int v9; // r8d
  WCHAR v10[8]; // [rsp+50h] [rbp-10h] BYREF

  v1 = (int)a1;
  v10[0] = 0;
  if ( (int)UtilExpandEnvironmentStrings(a1) < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    return 0;
  }
  FileAttributesW = GetFileAttributesW(v10);
  v3 = FileAttributesW;
  if ( (FileAttributesW & 0x10) != 0 || FileAttributesW == -1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_SDd(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, v9, v1, v3, LastError);
    }
    return 0;
  }
  v4 = 1;
  FileW = CreateFileW(v10, 1u, 7u, 0, 3u, 0, 0);
  if ( (unsigned __int64)FileW + 1 <= 1 )
    return 0;
  CloseHandle(FileW);
  return v4;
}

```

## disassembly

```asm
0x180039cf4  mov     [rsp-8+arg_0], rbx
0x180039cf9  mov     [rsp-8+arg_8], rdi
0x180039cfe  push    rbp
0x180039cff  mov     rbp, rsp
0x180039d02  sub     rsp, 60h
0x180039d06  lea     rax, [rbp+var_10]
0x180039d0a  mov     rdi, rcx
0x180039d0d  mov     [rbp+lpFileName], rax
0x180039d11  lea     rdx, [rbp+lpFileName]
0x180039d15  lea     rax, [rbp+var_10]
0x180039d19  mov     [rbp+var_18], rax
0x180039d1d  xor     eax, eax
0x180039d1f  mov     [rbp+var_10], ax
0x180039d23  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180039d28  test    eax, eax
0x180039d2a  jns     short loc_180039D69
0x180039d2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039d33  lea     rax, WPP_GLOBAL_Control
0x180039d3a  cmp     rcx, rax
0x180039d3d  jz      loc_180039E1B
0x180039d43  mov     ebx, 1
0x180039d48  test    [rcx+1Ch], bl
0x180039d4b  jz      loc_180039E1B
0x180039d51  mov     rcx, [rcx+10h]
0x180039d55  lea     edx, [rbx+2Eh]
0x180039d58  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x180039d5f  call    WPP_SF_
0x180039d64  jmp     loc_180039E1B
0x180039d69  mov     rcx, [rbp+lpFileName]; lpFileName
0x180039d6d  call    cs:__imp_GetFileAttributesW
0x180039d73  mov     ebx, eax
0x180039d75  test    al, 10h
0x180039d77  jnz     short loc_180039DE1
0x180039d79  cmp     eax, 0FFFFFFFFh
0x180039d7c  jz      short loc_180039DE1
0x180039d7e  mov     rcx, [rbp+lpFileName]; lpFileName
0x180039d82  xor     r9d, r9d; lpSecurityAttributes
0x180039d85  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x180039d8e  mov     [rsp+60h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180039d96  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x180039d9e  lea     ebx, [r9+1]
0x180039da2  mov     edx, ebx; dwDesiredAccess
0x180039da4  lea     r8d, [r9+7]; dwShareMode
0x180039da8  call    cs:__imp_CreateFileW
0x180039dae  lea     rcx, [rax+1]
0x180039db2  cmp     rcx, rbx
0x180039db5  ja      short loc_180039DBB
0x180039db7  xor     bl, bl
0x180039db9  jmp     short loc_180039DC4
0x180039dbb  mov     rcx, rax; hObject
0x180039dbe  call    cs:__imp_CloseHandle
0x180039dc4  mov     rcx, [rbp+lpFileName]; void *
0x180039dc8  lea     rax, [rbp+var_10]
0x180039dcc  cmp     rcx, rax
0x180039dcf  jz      short loc_180039DDD
0x180039dd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039dd8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039ddd  mov     al, bl
0x180039ddf  jmp     short loc_180039E36
0x180039de1  mov     rcx, cs:WPP_GLOBAL_Control
0x180039de8  lea     rax, WPP_GLOBAL_Control
0x180039def  cmp     rcx, rax
0x180039df2  jz      short loc_180039E1B
0x180039df4  test    byte ptr [rcx+1Ch], 8
0x180039df8  jz      short loc_180039E1B
0x180039dfa  call    cs:__imp_GetLastError
0x180039e00  mov     rcx, cs:WPP_GLOBAL_Control
0x180039e07  mov     r9, rdi
0x180039e0a  mov     [rsp+60h+dwFlagsAndAttributes], eax
0x180039e0e  mov     [rsp+60h+dwCreationDisposition], ebx
0x180039e12  mov     rcx, [rcx+10h]
0x180039e16  call    WPP_SF_SDd
0x180039e1b  mov     rcx, [rbp+lpFileName]; void *
0x180039e1f  lea     rax, [rbp+var_10]
0x180039e23  cmp     rcx, rax
0x180039e26  jz      short loc_180039E34
0x180039e28  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039e2f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180039e34  xor     al, al
0x180039e36  mov     rbx, [rsp+60h+arg_0]
0x180039e3b  mov     rdi, [rsp+60h+arg_8]
0x180039e40  add     rsp, 60h
0x180039e44  pop     rbp
0x180039e45  retn
```
