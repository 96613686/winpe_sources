# GetFileHandle

- ea: `0x1800bc6d8`
- end: `0x1800bca52`
- name: `GetFileHandle`
- size: `890`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bcad0`
- `0x1800bcf34`

## callees

- `0x180063d74`
- `0x18007e3a8`
- `0x1800bb898`
- `0x1800bc6d8`
- `0x1800ded50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1800bc9b5`
- `ntdll!RtlFreeHeap` at `0x1800bc9d7`
- `ntdll!RtlFreeHeap` at `0x1800bc9b5`
- `ntdll!RtlFreeHeap` at `0x1800bc9d7`
- `ntdll!wcschr` at `0x1800bc8e2`
- `ntdll!wcschr` at `0x1800bc8e2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800bc848`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800bc957`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800bc848`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800bc957`
- `ntdll!NtCreateFile` at `0x1800bc8cd`
- `ntdll!NtCreateFile` at `0x1800bc8cd`
- `ntdll!RtlInitUnicodeString` at `0x1800bc85d`
- `ntdll!RtlInitUnicodeString` at `0x1800bc85d`
- `ntdll!NtClose` at `0x1800bc98e`
- `ntdll!NtClose` at `0x1800bc98e`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bc8ff`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bc940`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bc8ff`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800bc940`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc7a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc7ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc913`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc9e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc9fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bca14`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc7a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc7ce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc913`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc9e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bc9fb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800bca14`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc9f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bca09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bca22`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bc9f0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bca09`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800bca22`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc7b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc7df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc924`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc7b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc7df`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800bc924`
- `RPCRT4!UuidCreate` at `0x1800bc756`
- `RPCRT4!UuidCreate` at `0x1800bc756`

## pseudocode

```c
__int64 __fastcall GetFileHandle(__int64 a1, void *a2)
{
  __int64 v3; // rdi
  wchar_t *v4; // r13
  WCHAR *v5; // r12
  __int64 v6; // r14
  __int64 v7; // r15
  HANDLE ProcessHeap; // rax
  WCHAR *v9; // rsi
  size_t v10; // r14
  HANDLE v11; // rax
  DWORD v12; // r15d
  DWORD FinalPathNameByHandleW; // eax
  DWORD v14; // r14d
  SIZE_T v15; // rbx
  HANDLE v16; // rax
  WCHAR *v17; // rax
  HANDLE v18; // rax
  HANDLE v19; // rax
  HANDLE v20; // rax
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P; // [rsp+68h] [rbp-98h]
  PVOID Buffer; // [rsp+70h] [rbp-90h]
  __int64 v25; // [rsp+78h] [rbp-88h]
  size_t cchDest; // [rsp+80h] [rbp-80h]
  void *v27; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING NtPathName; // [rsp+90h] [rbp-70h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D0h] [rbp-30h] BYREF
  struct _UNICODE_STRING v31; // [rsp+E0h] [rbp-20h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  UUID Uuid; // [rsp+100h] [rbp+0h] BYREF
  _WORD v34[40]; // [rsp+110h] [rbp+10h] BYREF

  v25 = a1;
  v27 = a2;
  P = 0;
  Buffer = 0;
  v3 = -1;
  FileHandle = (void *)-1LL;
  v4 = 0;
  v5 = 0;
  NtPathName = 0;
  v31 = 0;
  DestinationString = 0;
  Uuid = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( UuidCreate(&Uuid) < 0 )
  {
    v9 = 0;
  }
  else
  {
    ConvertGuid2String(&Uuid, 39, v34);
    v6 = -1;
    do
      ++v6;
    while ( v34[v6] );
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)(a1 + 2 * v7) );
    cchDest = v6 + 1;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * (v6 + 1));
    if ( v9 )
    {
      v10 = v7 + v6 + 2;
      v11 = GetProcessHeap();
      v4 = (wchar_t *)HeapAlloc(v11, 8u, 2 * v10);
      if ( v4 )
      {
        if ( StringCchPrintfW(v4, v10, L"%s\\%s", v25, v34) >= 0
          && StringCchPrintfW(v9, cchDest, L"%s", v34) >= 0
          && RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0) )
        {
          RtlInitUnicodeString(&DestinationString, v9);
          P = NtPathName.Buffer;
          ObjectAttributes.RootDirectory = v27;
          ObjectAttributes.Attributes = 4160;
          ObjectAttributes.ObjectName = &DestinationString;
          ObjectAttributes.Length = 48;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          if ( NtCreateFile(&FileHandle, 0x10001u, &ObjectAttributes, &IoStatusBlock, 0, 0x82u, 0, 2u, 0x1040u, 0, 0) < 0 )
            goto LABEL_21;
          v12 = wcschr(v4, 0x3Au) == 0;
          FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileHandle, 0, 0, v12);
          if ( FinalPathNameByHandleW )
          {
            v14 = FinalPathNameByHandleW + 1;
            v15 = 2LL * (FinalPathNameByHandleW + 1);
            v16 = GetProcessHeap();
            v17 = (WCHAR *)HeapAlloc(v16, 8u, v15);
            v5 = v17;
            if ( v17 )
            {
              if ( GetFinalPathNameByHandleW(FileHandle, v17, v14, v12) )
              {
                if ( RtlDosPathNameToNtPathName_U(v5, &v31, 0, 0) )
                {
                  Buffer = v31.Buffer;
                  if ( !wcsicmp_0(NtPathName.Buffer, v31.Buffer) )
                  {
                    v3 = (__int64)FileHandle;
                    goto LABEL_22;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( FileHandle == (void *)-1LL )
    goto LABEL_22;
  NtClose(FileHandle);
LABEL_21:
  FileHandle = (void *)-1LL;
LABEL_22:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v4 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v4);
  }
  if ( v5 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v5);
  }
  if ( v9 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v9);
  }
  return v3;
}

```

## disassembly

```asm
0x1800bc6d8  mov     [rsp-8+arg_10], rbx
0x1800bc6dd  push    rbp
0x1800bc6de  push    rsi
0x1800bc6df  push    rdi
0x1800bc6e0  push    r12
0x1800bc6e2  push    r13
0x1800bc6e4  push    r14
0x1800bc6e6  push    r15
0x1800bc6e8  lea     rbp, [rsp-70h]
0x1800bc6ed  sub     rsp, 170h
0x1800bc6f4  mov     rax, cs:__security_cookie
0x1800bc6fb  xor     rax, rsp
0x1800bc6fe  mov     [rbp+0A0h+var_40], rax
0x1800bc702  xorps   xmm0, xmm0
0x1800bc705  mov     [rsp+1A0h+var_128], rcx
0x1800bc70a  xor     r14d, r14d
0x1800bc70d  mov     [rbp+0A0h+var_118], rdx
0x1800bc711  xorps   xmm1, xmm1
0x1800bc714  mov     [rsp+1A0h+P], r14
0x1800bc719  mov     rbx, rcx
0x1800bc71c  mov     [rsp+1A0h+var_130], r14
0x1800bc721  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1800bc725  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bc729  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x1800bc72d  xor     eax, eax
0x1800bc72f  mov     [rsp+1A0h+FileHandle], rdi
0x1800bc734  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x1800bc738  mov     r13d, r14d
0x1800bc73b  mov     r12d, r14d
0x1800bc73e  movups  xmmword ptr [rbp+0A0h+NtPathName.Length], xmm0
0x1800bc742  movups  xmmword ptr [rbp+0A0h+var_C0.Length], xmm1
0x1800bc746  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1800bc74a  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm1
0x1800bc74e  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1800bc752  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x1800bc756  call    cs:__imp_UuidCreate
0x1800bc75c  test    eax, eax
0x1800bc75e  js      loc_1800BC981
0x1800bc764  lea     r8, [rbp+0A0h+var_90]
0x1800bc768  lea     edx, [rdi+28h]
0x1800bc76b  lea     rcx, [rbp+0A0h+Uuid]
0x1800bc76f  call    ConvertGuid2String
0x1800bc774  lea     rcx, [rbp+0A0h+var_90]
0x1800bc778  xor     eax, eax
0x1800bc77a  mov     r14, rdi
0x1800bc77d  inc     r14
0x1800bc780  cmp     [rcx+r14*2], ax
0x1800bc785  jnz     short loc_1800BC77D
0x1800bc787  mov     r15, rdi
0x1800bc78a  inc     r15
0x1800bc78d  cmp     [rbx+r15*2], ax
0x1800bc792  jnz     short loc_1800BC78A
0x1800bc794  lea     rax, [r14+1]
0x1800bc798  mov     [rbp+0A0h+cchDest], rax
0x1800bc79c  lea     rbx, [rax+rax]
0x1800bc7a0  call    cs:__imp_GetProcessHeap
0x1800bc7a6  mov     r8, rbx; dwBytes
0x1800bc7a9  mov     edx, 8; dwFlags
0x1800bc7ae  mov     rcx, rax; hHeap
0x1800bc7b1  call    cs:__imp_HeapAlloc
0x1800bc7b7  mov     rsi, rax
0x1800bc7ba  test    rax, rax
0x1800bc7bd  jz      loc_1800BC984
0x1800bc7c3  add     r14, 2
0x1800bc7c7  add     r14, r15
0x1800bc7ca  lea     rbx, [r14+r14]
0x1800bc7ce  call    cs:__imp_GetProcessHeap
0x1800bc7d4  mov     r8, rbx; dwBytes
0x1800bc7d7  mov     edx, 8; dwFlags
0x1800bc7dc  mov     rcx, rax; hHeap
0x1800bc7df  call    cs:__imp_HeapAlloc
0x1800bc7e5  mov     r13, rax
0x1800bc7e8  test    rax, rax
0x1800bc7eb  jz      loc_1800BC984
0x1800bc7f1  mov     r9, [rsp+1A0h+var_128]
0x1800bc7f6  lea     rax, [rbp+0A0h+var_90]
0x1800bc7fa  lea     r8, aSS_2; "%s\\%s"
0x1800bc801  mov     [rsp+1A0h+AllocationSize], rax
0x1800bc806  mov     rdx, r14; cchDest
0x1800bc809  mov     rcx, r13; pszDest
0x1800bc80c  call    StringCchPrintfW
0x1800bc811  xor     r14d, r14d
0x1800bc814  test    eax, eax
0x1800bc816  js      loc_1800BC984
0x1800bc81c  mov     rdx, [rbp+0A0h+cchDest]; cchDest
0x1800bc820  lea     r9, [rbp+0A0h+var_90]
0x1800bc824  lea     r8, aS_0; "%s"
0x1800bc82b  mov     rcx, rsi; pszDest
0x1800bc82e  call    StringCchPrintfW
0x1800bc833  test    eax, eax
0x1800bc835  js      loc_1800BC984
0x1800bc83b  xor     r9d, r9d; DirectoryInfo
0x1800bc83e  lea     rdx, [rbp+0A0h+NtPathName]; NtPathName
0x1800bc842  xor     r8d, r8d; NtFileNamePart
0x1800bc845  mov     rcx, r13; DosPathName
0x1800bc848  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800bc84e  test    al, al
0x1800bc850  jz      loc_1800BC984
0x1800bc856  mov     rdx, rsi; SourceString
0x1800bc859  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1800bc85d  call    cs:__imp_RtlInitUnicodeString
0x1800bc863  mov     rax, [rbp+0A0h+NtPathName.Buffer]
0x1800bc867  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800bc86b  mov     [rsp+1A0h+EaLength], r14d; EaLength
0x1800bc870  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800bc874  mov     [rsp+1A0h+EaBuffer], r14; EaBuffer
0x1800bc879  mov     ecx, 1040h
0x1800bc87e  mov     [rsp+1A0h+CreateOptions], ecx; CreateOptions
0x1800bc882  xorps   xmm0, xmm0
0x1800bc885  mov     [rsp+1A0h+P], rax
0x1800bc88a  mov     edx, 10001h; DesiredAccess
0x1800bc88f  mov     rax, [rbp+0A0h+var_118]
0x1800bc893  mov     [rsp+1A0h+CreateDisposition], 2; CreateDisposition
0x1800bc89b  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rax
0x1800bc89f  lea     rax, [rbp+0A0h+DestinationString]
0x1800bc8a3  mov     [rbp+0A0h+ObjectAttributes.Attributes], ecx
0x1800bc8a6  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1800bc8ab  mov     [rsp+1A0h+ShareAccess], r14d; ShareAccess
0x1800bc8b0  mov     [rsp+1A0h+FileAttributes], 82h; FileAttributes
0x1800bc8b8  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1800bc8bc  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1800bc8c3  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800bc8c8  mov     [rsp+1A0h+AllocationSize], r14; AllocationSize
0x1800bc8cd  call    cs:__imp_NtCreateFile
0x1800bc8d3  test    eax, eax
0x1800bc8d5  js      loc_1800BC994
0x1800bc8db  lea     edx, [r14+3Ah]; Ch
0x1800bc8df  mov     rcx, r13; Str
0x1800bc8e2  call    cs:__imp_wcschr
0x1800bc8e8  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800bc8ed  mov     r15d, r14d
0x1800bc8f0  test    rax, rax
0x1800bc8f3  setz    r15b
0x1800bc8f7  xor     r8d, r8d; cchFilePath
0x1800bc8fa  mov     r9d, r15d; dwFlags
0x1800bc8fd  xor     edx, edx; lpszFilePath
0x1800bc8ff  call    cs:__imp_GetFinalPathNameByHandleW
0x1800bc905  test    eax, eax
0x1800bc907  jz      short loc_1800BC984
0x1800bc909  lea     r14d, [rax+1]
0x1800bc90d  mov     ebx, r14d
0x1800bc910  add     rbx, rbx
0x1800bc913  call    cs:__imp_GetProcessHeap
0x1800bc919  mov     r8, rbx; dwBytes
0x1800bc91c  mov     edx, 8; dwFlags
0x1800bc921  mov     rcx, rax; hHeap
0x1800bc924  call    cs:__imp_HeapAlloc
0x1800bc92a  mov     r12, rax
0x1800bc92d  test    rax, rax
0x1800bc930  jz      short loc_1800BC984
0x1800bc932  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800bc937  mov     r9d, r15d; dwFlags
0x1800bc93a  mov     r8d, r14d; cchFilePath
0x1800bc93d  mov     rdx, rax; lpszFilePath
0x1800bc940  call    cs:__imp_GetFinalPathNameByHandleW
0x1800bc946  test    eax, eax
0x1800bc948  jz      short loc_1800BC984
0x1800bc94a  xor     r9d, r9d; DirectoryInfo
0x1800bc94d  lea     rdx, [rbp+0A0h+var_C0]; NtPathName
0x1800bc951  xor     r8d, r8d; NtFileNamePart
0x1800bc954  mov     rcx, r12; DosPathName
0x1800bc957  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800bc95d  test    al, al
0x1800bc95f  jz      short loc_1800BC984
0x1800bc961  mov     rbx, [rbp+0A0h+var_C0.Buffer]
0x1800bc965  mov     rcx, [rbp+0A0h+NtPathName.Buffer]; String1
0x1800bc969  mov     rdx, rbx; String2
0x1800bc96c  mov     [rsp+1A0h+var_130], rbx
0x1800bc971  call    _wcsicmp_0
0x1800bc976  test    eax, eax
0x1800bc978  jnz     short loc_1800BC984
0x1800bc97a  mov     rdi, [rsp+1A0h+FileHandle]
0x1800bc97f  jmp     short loc_1800BC999
0x1800bc981  mov     rsi, r14
0x1800bc984  mov     rcx, [rsp+1A0h+FileHandle]; Handle
0x1800bc989  cmp     rcx, rdi
0x1800bc98c  jz      short loc_1800BC999
0x1800bc98e  call    cs:__imp_NtClose
0x1800bc994  mov     [rsp+1A0h+FileHandle], rdi
0x1800bc999  mov     rax, [rsp+1A0h+P]
0x1800bc99e  test    rax, rax
0x1800bc9a1  jz      short loc_1800BC9BB
0x1800bc9a3  mov     rcx, gs:60h
0x1800bc9ac  mov     r8, rax; P
0x1800bc9af  xor     edx, edx; Flags
0x1800bc9b1  mov     rcx, [rcx+30h]; HeapHandle
0x1800bc9b5  call    cs:__imp_RtlFreeHeap
0x1800bc9bb  mov     rax, [rsp+1A0h+var_130]
0x1800bc9c0  test    rax, rax
0x1800bc9c3  jz      short loc_1800BC9DD
0x1800bc9c5  mov     rcx, gs:60h
0x1800bc9ce  mov     r8, rax; P
0x1800bc9d1  xor     edx, edx; Flags
0x1800bc9d3  mov     rcx, [rcx+30h]; HeapHandle
0x1800bc9d7  call    cs:__imp_RtlFreeHeap
0x1800bc9dd  test    r13, r13
0x1800bc9e0  jz      short loc_1800BC9F6
0x1800bc9e2  call    cs:__imp_GetProcessHeap
0x1800bc9e8  mov     r8, r13; lpMem
0x1800bc9eb  xor     edx, edx; dwFlags
0x1800bc9ed  mov     rcx, rax; hHeap
0x1800bc9f0  call    cs:__imp_HeapFree
0x1800bc9f6  test    r12, r12
0x1800bc9f9  jz      short loc_1800BCA0F
0x1800bc9fb  call    cs:__imp_GetProcessHeap
0x1800bca01  mov     r8, r12; lpMem
0x1800bca04  xor     edx, edx; dwFlags
0x1800bca06  mov     rcx, rax; hHeap
0x1800bca09  call    cs:__imp_HeapFree
0x1800bca0f  test    rsi, rsi
0x1800bca12  jz      short loc_1800BCA28
0x1800bca14  call    cs:__imp_GetProcessHeap
0x1800bca1a  mov     r8, rsi; lpMem
0x1800bca1d  xor     edx, edx; dwFlags
0x1800bca1f  mov     rcx, rax; hHeap
0x1800bca22  call    cs:__imp_HeapFree
0x1800bca28  mov     rax, rdi
0x1800bca2b  mov     rcx, [rbp+0A0h+var_40]
0x1800bca2f  xor     rcx, rsp; StackCookie
0x1800bca32  call    __security_check_cookie
0x1800bca37  mov     rbx, [rsp+1A0h+arg_10]
0x1800bca3f  add     rsp, 170h
0x1800bca46  pop     r15
0x1800bca48  pop     r14
0x1800bca4a  pop     r13
0x1800bca4c  pop     r12
0x1800bca4e  pop     rdi
0x1800bca4f  pop     rsi
0x1800bca50  pop     rbp
0x1800bca51  retn
```
