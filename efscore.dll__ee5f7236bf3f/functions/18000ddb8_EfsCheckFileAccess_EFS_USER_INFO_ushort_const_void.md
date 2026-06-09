# EfsCheckFileAccess(_EFS_USER_INFO *,ushort const *,void *)

- ea: `0x18000ddb8`
- end: `0x18000df72`
- name: `?EfsCheckFileAccess@@YAJPEAU_EFS_USER_INFO@@PEBGPEAX@Z`
- size: `442`
- prototype: `int(struct _EFS_USER_INFO *, const unsigned __int16 *, void *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010390`
- `0x180016588`
- `0x18004e4c4`

## callees

- `0x18000b10c`
- `0x18000b12c`
- `0x18000dc68`
- `0x18000ddb8`
- `0x18000e0fc`
- `0x18000ef44`
- `0x1800264e0`
- `0x18006861c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000deeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df3d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000de82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000deeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000df3d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000def9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df4b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000de90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000def9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000df4b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de00`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000de00`

## string_xrefs

- `0x18000de1c`: `onecoreuap\ds\security\efs\dll\efscore.cpp`
- `0x18000de67`: `onecoreuap\ds\security\efs\dll\efscore.cpp`
- `0x18000ded0`: `onecoreuap\ds\security\efs\dll\efscore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EfsCheckFileAccess(struct _EFS_USER_INFO *a1, const unsigned __int16 *a2, char *a3)
{
  char *FileW; // r9
  unsigned int LastError; // ebx
  unsigned int FileEfsStream; // eax
  __int64 v7; // rdx
  void *v8; // rdi
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  void *v12; // rbx
  HANDLE v13; // rax
  unsigned int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  LPVOID lpMem; // [rsp+40h] [rbp-20h] BYREF
  _QWORD v17[2]; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+58h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v20; // [rsp+90h] [rbp+30h] BYREF
  unsigned int v21; // [rsp+98h] [rbp+38h]

  FileW = a3;
  v17[0] = -1;
  if ( !a3 )
  {
    FileW = (char *)CreateFileW(a2, 0x80u, 7u, 0, 3u, 0x2200000u, 0);
    v17[0] = FileW;
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x8F4,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efscore.cpp",
                    FileW);
      goto LABEL_19;
    }
  }
  lpMem = 0;
  v17[1] = &lpMem;
  v18 = 1;
  v21 = 0;
  FileEfsStream = EfspGetFileEfsStream(FileW);
  if ( FileEfsStream )
  {
    v7 = 2305;
    goto LABEL_6;
  }
  v20 = 0;
  FileEfsStream = EfsValidateEfsStream((const struct _EFS_DATA_STREAM_HEADER *)lpMem, v21, &v20);
  if ( FileEfsStream )
  {
    v7 = 2308;
    goto LABEL_6;
  }
  if ( v20 )
  {
    dwCreationDisposition = 0;
    FileEfsStream = EfspDecryptFek(a1, lpMem, 0, 1);
    if ( FileEfsStream )
    {
      v7 = 2312;
LABEL_6:
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)v7,
                    (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efscore.cpp",
                    (const char *)FileEfsStream,
                    dwCreationDisposition);
      v8 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        lpMem = 0;
      }
      goto LABEL_19;
    }
    v12 = lpMem;
    if ( lpMem )
    {
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v12);
      lpMem = 0;
    }
    LastError = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x905,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efscore.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    v10 = lpMem;
    if ( lpMem )
    {
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      lpMem = 0;
    }
    LastError = -2147024809;
  }
LABEL_19:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v17);
  return LastError;
}

```

## disassembly

```asm
0x18000ddb8  mov     [rsp-18h+arg_0], rbx
0x18000ddbd  push    rbp
0x18000ddbe  push    rsi
0x18000ddbf  push    rdi
0x18000ddc0  mov     rbp, rsp
0x18000ddc3  sub     rsp, 60h
0x18000ddc7  mov     r9, r8; lpSecurityAttributes
0x18000ddca  mov     rax, rdx
0x18000ddcd  mov     rbx, rcx
0x18000ddd0  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFFh
0x18000ddd8  xor     esi, esi
0x18000ddda  test    r8, r8
0x18000dddd  jnz     short loc_18000DE34
0x18000dddf  mov     [rsp+60h+hTemplateFile], rsi; hTemplateFile
0x18000dde4  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18000ddec  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ddf4  mov     edx, 80h; dwDesiredAccess
0x18000ddf9  lea     r8d, [r9+7]; dwShareMode
0x18000ddfd  mov     rcx, rax; lpFileName
0x18000de00  call    cs:__imp_CreateFileW
0x18000de06  mov     r9, rax; char *
0x18000de09  mov     [rbp+var_18], rax
0x18000de0d  inc     rax
0x18000de10  test    rax, 0FFFFFFFFFFFFFFFEh
0x18000de16  jnz     short loc_18000DE34
0x18000de18  mov     rcx, [rbp+18h]; this
0x18000de1c  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18000de23  mov     edx, 8F4h; void *
0x18000de28  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000de2d  mov     ebx, eax
0x18000de2f  jmp     loc_18000DF57
0x18000de34  mov     [rbp+lpMem], rsi
0x18000de38  lea     rax, [rbp+lpMem]
0x18000de3c  mov     [rbp+var_10], rax
0x18000de40  mov     [rbp+var_8], 1
0x18000de44  mov     [rbp+arg_18], esi
0x18000de47  lea     r8, [rbp+arg_18]
0x18000de4b  lea     rdx, [rbp+lpMem]
0x18000de4f  mov     rcx, r9; FileHandle
0x18000de52  call    EfspGetFileEfsStream
0x18000de57  test    eax, eax
0x18000de59  jz      short loc_18000DE9F
0x18000de5b  mov     edx, 901h; void *
0x18000de60  mov     rcx, [rbp+18h]; this
0x18000de64  mov     r9d, eax; char *
0x18000de67  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18000de6e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000de73  mov     ebx, eax
0x18000de75  mov     rdi, [rbp+lpMem]
0x18000de79  test    rdi, rdi
0x18000de7c  jz      loc_18000DF57
0x18000de82  call    cs:__imp_GetProcessHeap
0x18000de88  mov     r8, rdi; lpMem
0x18000de8b  xor     edx, edx; dwFlags
0x18000de8d  mov     rcx, rax; hHeap
0x18000de90  call    cs:__imp_HeapFree
0x18000de96  mov     [rbp+lpMem], rsi
0x18000de9a  jmp     loc_18000DF57
0x18000de9f  mov     [rbp+arg_10], sil
0x18000dea3  lea     r8, [rbp+arg_10]
0x18000dea7  mov     edx, [rbp+arg_18]
0x18000deaa  mov     rcx, [rbp+lpMem]
0x18000deae  call    EfsValidateEfsStream
0x18000deb3  test    eax, eax
0x18000deb5  jz      short loc_18000DEBE
0x18000deb7  mov     edx, 904h
0x18000debc  jmp     short loc_18000DE60
0x18000debe  cmp     [rbp+arg_10], sil
0x18000dec2  jnz     short loc_18000DF07
0x18000dec4  mov     rcx, [rbp+18h]; this
0x18000dec8  mov     edi, 80070057h
0x18000decd  mov     r9d, edi; char *
0x18000ded0  lea     r8, aOnecoreuapDsSe_2; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x18000ded7  mov     edx, 905h; void *
0x18000dedc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dee1  nop
0x18000dee2  mov     rbx, [rbp+lpMem]
0x18000dee6  test    rbx, rbx
0x18000dee9  jz      short loc_18000DF03
0x18000deeb  call    cs:__imp_GetProcessHeap
0x18000def1  mov     r8, rbx; lpMem
0x18000def4  xor     edx, edx; dwFlags
0x18000def6  mov     rcx, rax; hHeap
0x18000def9  call    cs:__imp_HeapFree
0x18000deff  mov     [rbp+lpMem], rsi
0x18000df03  mov     ebx, edi
0x18000df05  jmp     short loc_18000DF57
0x18000df07  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rsi
0x18000df0c  mov     qword ptr [rsp+60h+dwCreationDisposition], rsi
0x18000df11  mov     r9d, 1
0x18000df17  xor     r8d, r8d
0x18000df1a  mov     rdx, [rbp+lpMem]
0x18000df1e  mov     rcx, rbx
0x18000df21  call    ?EfspDecryptFek@@YAJPEAU_EFS_USER_INFO@@PEAU_EFS_DATA_STREAM_HEADER@@PEAU_UNICODE_STRING@@W4EfspDecryptFekFlags@@PEAPEAU_EFS_FILE_KEY@@PEAPEAU2@@Z; EfspDecryptFek(_EFS_USER_INFO *,_EFS_DATA_STREAM_HEADER *,_UNICODE_STRING *,EfspDecryptFekFlags,_EFS_FILE_KEY * *,_EFS_DATA_STREAM_HEADER * *)
0x18000df26  test    eax, eax
0x18000df28  jz      short loc_18000DF34
0x18000df2a  mov     edx, 908h
0x18000df2f  jmp     loc_18000DE60
0x18000df34  mov     rbx, [rbp+lpMem]
0x18000df38  test    rbx, rbx
0x18000df3b  jz      short loc_18000DF55
0x18000df3d  call    cs:__imp_GetProcessHeap
0x18000df43  mov     r8, rbx; lpMem
0x18000df46  xor     edx, edx; dwFlags
0x18000df48  mov     rcx, rax; hHeap
0x18000df4b  call    cs:__imp_HeapFree
0x18000df51  mov     [rbp+lpMem], rsi
0x18000df55  mov     ebx, esi
0x18000df57  lea     rcx, [rbp+var_18]
0x18000df5b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000df60  mov     eax, ebx
0x18000df62  mov     rbx, [rsp+60h+arg_0]
0x18000df6a  add     rsp, 60h
0x18000df6e  pop     rdi
0x18000df6f  pop     rsi
0x18000df70  pop     rbp
0x18000df71  retn
```
