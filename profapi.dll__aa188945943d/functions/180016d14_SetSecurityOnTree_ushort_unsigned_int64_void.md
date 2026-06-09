# _SetSecurityOnTree(ushort *,unsigned __int64,void *)

- ea: `0x180016d14`
- end: `0x180016f33`
- name: `?_SetSecurityOnTree@@YAJPEAG_KPEAX@Z`
- size: `543`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180016bec`
- `0x180016d14`

## callees

- `0x180002a8c`
- `0x180005b60`
- `0x1800090f0`
- `0x18000a1c0`
- `0x18000a540`
- `0x18000d984`
- `0x18000dc34`
- `0x180016810`
- `0x180016cf4`
- `0x180016d14`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016da8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180016da8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016d97`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180016d97`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180016e5a`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x180016e5a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016dc5`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180016dc5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016eac`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180016eac`

## pseudocode

```c
__int64 __fastcall _SetSecurityOnTree(unsigned __int16 *a1, unsigned __int64 a2, void *a3)
{
  int LastError; // ebx
  __int64 v6; // rdx
  unsigned __int16 *v7; // r14
  HANDLE ProcessHeap; // rax
  struct _WIN32_FIND_DATAW *v9; // rax
  unsigned __int16 *v10; // rdi
  unsigned __int16 *FirstFileW; // rbx
  const char *v12; // r9
  int v13; // eax
  int v14; // esi
  unsigned int v15; // r8d
  const char *v16; // r9
  int v17; // eax
  void *v18; // rdx
  void *v20; // rdx
  int v21; // [rsp+20h] [rbp-38h]
  int v22; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  unsigned __int64 v24; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v25; // [rsp+78h] [rbp+20h] BYREF

  v25 = 0;
  v24 = 0;
  LastError = PathCchAddBackslashEx(a1, a2, &v25, &v24);
  if ( LastError < 0 )
  {
    v6 = 177;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)(unsigned int)LastError,
      v21);
    return (unsigned int)LastError;
  }
  v7 = v25;
  LastError = StringCchCopyW(v25, v24, L"*.*");
  if ( LastError < 0 )
  {
    v6 = 179;
    goto LABEL_3;
  }
  ProcessHeap = GetProcessHeap();
  v9 = (struct _WIN32_FIND_DATAW *)HeapAlloc(ProcessHeap, 0, 0x250u);
  v10 = (unsigned __int16 *)v9;
  v22 = (int)v9;
  if ( !v9 )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"minio\\profapi\\load.cpp",
      (const char *)0x8007000ELL,
      0);
    return (unsigned int)LastError;
  }
  FirstFileW = (unsigned __int16 *)FindFirstFileW(a1, v9);
  v25 = FirstFileW;
  if ( FirstFileW == (unsigned __int16 *)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xBA,
                  (unsigned int)"minio\\profapi\\load.cpp",
                  v12);
    goto LABEL_22;
  }
  while ( (*(_BYTE *)v10 & 0x10) == 0
       || StringIsEqual(v10 + 22, L".")
       || StringIsEqual(v10 + 22, L"..")
       || (*(_DWORD *)v10 & 0x400) != 0 )
  {
LABEL_19:
    if ( !FindNextFileW(FirstFileW, (LPWIN32_FIND_DATAW)v10) )
    {
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v25);
      wil::details::FreeProcessHeap((wil::details *)v10, v18);
      return 0;
    }
  }
  v13 = StringCchCopyW(v7, v24, v10 + 22);
  v14 = v13;
  if ( v13 >= 0 )
  {
    if ( !SetFileSecurityW(a1, 4u, a3) )
      wil::details::in1diag3::_Log_GetLastError(retaddr, (void *)0xC9, v15, v16);
    v17 = _SetSecurityOnTree(a1, 0x104u, a3);
    if ( v17 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xCB,
        (int)"minio\\profapi\\load.cpp",
        (const char *)(unsigned int)v17);
    *v7 = 0;
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC6,
    (unsigned int)"minio\\profapi\\load.cpp",
    (const char *)(unsigned int)v13,
    v22);
  LastError = v14;
LABEL_22:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&v25);
  wil::details::FreeProcessHeap((wil::details *)v10, v20);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180016d14  mov     rax, rsp
0x180016d17  mov     [rax+8], rbx
0x180016d1b  mov     [rax+10h], rdx
0x180016d1f  push    rbp
0x180016d20  push    rsi
0x180016d21  push    rdi
0x180016d22  push    r14
0x180016d24  push    r15
0x180016d26  sub     rsp, 30h
0x180016d2a  mov     r15, r8
0x180016d2d  mov     rbp, rcx
0x180016d30  mov     qword ptr [rax+20h], 0
0x180016d38  mov     qword ptr [rax+10h], 0
0x180016d40  lea     r9, [rax+10h]; unsigned __int64 *
0x180016d44  lea     r8, [rax+20h]; unsigned __int16 **
0x180016d48  call    ?PathCchAddBackslashEx@@YAJPEAG_KPEAPEAGPEA_K@Z; PathCchAddBackslashEx(ushort *,unsigned __int64,ushort * *,unsigned __int64 *)
0x180016d4d  mov     ebx, eax
0x180016d4f  test    eax, eax
0x180016d51  jns     short loc_180016D71
0x180016d53  mov     edx, 0B1h; void *
0x180016d58  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016d5f  mov     r9d, ebx; char *
0x180016d62  mov     rcx, [rsp+58h]; this
0x180016d67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d6c  jmp     loc_180016F20
0x180016d71  lea     r8, asc_18001A4E0; "*.*"
0x180016d78  mov     rdx, [rsp+58h+arg_8]; unsigned __int64
0x180016d7d  mov     r14, [rsp+58h+arg_18]
0x180016d82  mov     rcx, r14; unsigned __int16 *
0x180016d85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016d8a  mov     ebx, eax
0x180016d8c  test    eax, eax
0x180016d8e  jns     short loc_180016D97
0x180016d90  mov     edx, 0B3h
0x180016d95  jmp     short loc_180016D58
0x180016d97  call    cs:__imp_GetProcessHeap
0x180016d9d  mov     rcx, rax; hHeap
0x180016da0  xor     edx, edx; dwFlags
0x180016da2  mov     r8d, 250h; dwBytes
0x180016da8  call    cs:__imp_HeapAlloc
0x180016dae  mov     rdi, rax
0x180016db1  mov     qword ptr [rsp+58h+var_38], rax; int
0x180016db6  test    rax, rax
0x180016db9  jz      loc_180016F01
0x180016dbf  mov     rdx, rax; lpFindFileData
0x180016dc2  mov     rcx, rbp; lpFileName
0x180016dc5  call    cs:__imp_FindFirstFileW
0x180016dcb  mov     rbx, rax
0x180016dce  mov     [rsp+58h+arg_18], rax
0x180016dd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180016dd7  jnz     short loc_180016DF6
0x180016dd9  mov     rcx, [rsp+58h]; this
0x180016dde  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016de5  mov     edx, 0BAh; void *
0x180016dea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180016def  mov     ebx, eax
0x180016df1  jmp     loc_180016EEC
0x180016df6  test    byte ptr [rdi], 10h
0x180016df9  jz      loc_180016EA6
0x180016dff  lea     rsi, [rdi+2Ch]
0x180016e03  lea     rdx, asc_18001CB10; "."
0x180016e0a  mov     rcx, rsi; unsigned __int16 *
0x180016e0d  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180016e12  test    eax, eax
0x180016e14  jnz     loc_180016EA6
0x180016e1a  lea     rdx, asc_18001CBD8; ".."
0x180016e21  mov     rcx, rsi; unsigned __int16 *
0x180016e24  call    ?StringIsEqual@@YAHPEBG0@Z; StringIsEqual(ushort const *,ushort const *)
0x180016e29  test    eax, eax
0x180016e2b  jnz     short loc_180016EA6
0x180016e2d  test    dword ptr [rdi], 400h
0x180016e33  jnz     short loc_180016EA6
0x180016e35  mov     r8, rsi; unsigned __int16 *
0x180016e38  mov     rdx, [rsp+58h+arg_8]; unsigned __int64
0x180016e3d  mov     rcx, r14; unsigned __int16 *
0x180016e40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180016e45  mov     esi, eax
0x180016e47  test    eax, eax
0x180016e49  js      loc_180016ED1
0x180016e4f  mov     r8, r15; pSecurityDescriptor
0x180016e52  mov     edx, 4; SecurityInformation
0x180016e57  mov     rcx, rbp; lpFileName
0x180016e5a  call    cs:__imp_SetFileSecurityW
0x180016e60  mov     rcx, [rsp+58h]; this
0x180016e65  test    eax, eax
0x180016e67  jnz     short loc_180016E73
0x180016e69  mov     edx, 0C9h; void *
0x180016e6e  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x180016e73  mov     r8, r15; void *
0x180016e76  mov     edx, 104h; unsigned __int64
0x180016e7b  mov     rcx, rbp; unsigned __int16 *
0x180016e7e  call    ?_SetSecurityOnTree@@YAJPEAG_KPEAX@Z; _SetSecurityOnTree(ushort *,unsigned __int64,void *)
0x180016e83  mov     rcx, [rsp+58h]; this
0x180016e88  test    eax, eax
0x180016e8a  jns     short loc_180016EA0
0x180016e8c  mov     r9d, eax; char *
0x180016e8f  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016e96  mov     edx, 0CBh; void *
0x180016e9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180016ea0  xor     eax, eax
0x180016ea2  mov     [r14], ax
0x180016ea6  mov     rdx, rdi; lpFindFileData
0x180016ea9  mov     rcx, rbx; hFindFile
0x180016eac  call    cs:__imp_FindNextFileW
0x180016eb2  test    eax, eax
0x180016eb4  jnz     loc_180016DF6
0x180016eba  lea     rcx, [rsp+58h+arg_18]
0x180016ebf  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180016ec4  nop
0x180016ec5  mov     rcx, rdi; this
0x180016ec8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180016ecd  xor     eax, eax
0x180016ecf  jmp     short loc_180016F22
0x180016ed1  mov     rcx, [rsp+58h]; this
0x180016ed6  mov     r9d, esi; char *
0x180016ed9  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016ee0  mov     edx, 0C6h; void *
0x180016ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016eea  mov     ebx, esi
0x180016eec  lea     rcx, [rsp+58h+arg_18]
0x180016ef1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x180016ef6  nop
0x180016ef7  mov     rcx, rdi; this
0x180016efa  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180016eff  jmp     short loc_180016F20
0x180016f01  mov     rcx, [rsp+58h]; this
0x180016f06  mov     ebx, 8007000Eh
0x180016f0b  mov     r9d, ebx; char *
0x180016f0e  lea     r8, aMinioProfapiLo; "minio\\profapi\\load.cpp"
0x180016f15  mov     edx, 0B7h; void *
0x180016f1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016f1f  nop
0x180016f20  mov     eax, ebx
0x180016f22  mov     rbx, [rsp+58h+arg_0]
0x180016f27  add     rsp, 30h
0x180016f2b  pop     r15
0x180016f2d  pop     r14
0x180016f2f  pop     rdi
0x180016f30  pop     rsi
0x180016f31  pop     rbp
0x180016f32  retn
```
