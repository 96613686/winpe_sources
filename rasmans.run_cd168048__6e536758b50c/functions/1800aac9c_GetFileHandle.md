# GetFileHandle

- ea: `0x1800aac9c`
- end: `0x1800ab0a5`
- name: `GetFileHandle`
- size: `1033`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800ab130`
- `0x1800ab670`

## callees

- `0x180001fc4`
- `0x18000eb54`
- `0x1800aa0f4`
- `0x1800aac9c`
- `0x1800e8ef0`

## import_xrefs

- `msvcrt!wcschr` at `0x1800aaed6`
- `msvcrt!wcschr` at `0x1800aaed6`
- `ntdll!NtCreateFile` at `0x1800aaebb`
- `ntdll!NtCreateFile` at `0x1800aaebb`
- `ntdll!RtlFreeHeap` at `0x1800aafd7`
- `ntdll!RtlFreeHeap` at `0x1800aafff`
- `ntdll!RtlFreeHeap` at `0x1800aafd7`
- `ntdll!RtlFreeHeap` at `0x1800aafff`
- `ntdll!NtClose` at `0x1800aafaa`
- `ntdll!NtClose` at `0x1800aafaa`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800aae2a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800aaf6d`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800aae2a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800aaf6d`
- `ntdll!RtlInitUnicodeString` at `0x1800aae45`
- `ntdll!RtlInitUnicodeString` at `0x1800aae45`
- `RPCRT4!UuidCreate` at `0x1800aad1a`
- `RPCRT4!UuidCreate` at `0x1800aad1a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aad81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aadbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aaf2e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aad81`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aadbb`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aaf2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab049`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab06e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab024`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab049`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800ab06e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aada4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aaf17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab05a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aad6a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aada4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aaf17`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab010`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab035`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800ab05a`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800aaef9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800aaf50`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800aaef9`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800aaf50`

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
  unsigned __int64 v10; // r14
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
  unsigned __int64 v26; // [rsp+80h] [rbp-80h]
  void *v27; // [rsp+88h] [rbp-78h]
  struct _UNICODE_STRING NtPathName; // [rsp+90h] [rbp-70h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
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
    v26 = v6 + 1;
    ProcessHeap = GetProcessHeap();
    v9 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, 2 * (v6 + 1));
    if ( v9 )
    {
      v10 = v7 + v6 + 2;
      v11 = GetProcessHeap();
      v4 = (wchar_t *)HeapAlloc(v11, 8u, 2 * v10);
      if ( v4 )
      {
        if ( (int)StringCchPrintfW(v4, v10, L"%s\\%s", v25, v34) >= 0
          && (int)StringCchPrintfW(v9, v26, L"%s", v34) >= 0
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
0x1800aac9c  mov     [rsp-8+arg_10], rbx
0x1800aaca1  push    rbp
0x1800aaca2  push    rsi
0x1800aaca3  push    rdi
0x1800aaca4  push    r12
0x1800aaca6  push    r13
0x1800aaca8  push    r14
0x1800aacaa  push    r15
0x1800aacac  lea     rbp, [rsp-70h]
0x1800aacb1  sub     rsp, 170h
0x1800aacb8  mov     rax, cs:__security_cookie
0x1800aacbf  xor     rax, rsp
0x1800aacc2  mov     [rbp+0A0h+var_40], rax
0x1800aacc6  xorps   xmm0, xmm0
0x1800aacc9  mov     [rsp+1A0h+var_128], rcx
0x1800aacce  xor     r14d, r14d
0x1800aacd1  mov     [rbp+0A0h+var_118], rdx
0x1800aacd5  xorps   xmm1, xmm1
0x1800aacd8  mov     [rsp+1A0h+P], r14
0x1800aacdd  mov     rbx, rcx
0x1800aace0  mov     [rsp+1A0h+var_130], r14
0x1800aace5  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x1800aace9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800aaced  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x1800aacf1  xor     eax, eax
0x1800aacf3  mov     [rsp+1A0h+FileHandle], rdi
0x1800aacf8  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x1800aacfc  mov     r13d, r14d
0x1800aacff  mov     r12d, r14d
0x1800aad02  movups  xmmword ptr [rbp+0A0h+NtPathName.Length], xmm0
0x1800aad06  movups  xmmword ptr [rbp+0A0h+var_C0.Length], xmm1
0x1800aad0a  movups  xmmword ptr [rbp+0A0h+DestinationString.Length], xmm0
0x1800aad0e  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm1
0x1800aad12  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x1800aad16  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x1800aad1a  call    cs:__imp_UuidCreate
0x1800aad21  nop     dword ptr [rax+rax+00h]
0x1800aad26  test    eax, eax
0x1800aad28  js      loc_1800AAF9D
0x1800aad2e  lea     r8, [rbp+0A0h+var_90]
0x1800aad32  lea     edx, [rdi+28h]
0x1800aad35  lea     rcx, [rbp+0A0h+Uuid]
0x1800aad39  call    ConvertGuid2String
0x1800aad3e  lea     rcx, [rbp+0A0h+var_90]
0x1800aad42  xor     eax, eax
0x1800aad44  mov     r14, rdi
0x1800aad47  inc     r14
0x1800aad4a  cmp     [rcx+r14*2], ax
0x1800aad4f  jnz     short loc_1800AAD47
0x1800aad51  mov     r15, rdi
0x1800aad54  inc     r15
0x1800aad57  cmp     [rbx+r15*2], ax
0x1800aad5c  jnz     short loc_1800AAD54
0x1800aad5e  lea     rax, [r14+1]
0x1800aad62  mov     [rbp+0A0h+var_120], rax
0x1800aad66  lea     rbx, [rax+rax]
0x1800aad6a  call    cs:__imp_GetProcessHeap
0x1800aad71  nop     dword ptr [rax+rax+00h]
0x1800aad76  mov     r8, rbx; dwBytes
0x1800aad79  mov     edx, 8; dwFlags
0x1800aad7e  mov     rcx, rax; hHeap
0x1800aad81  call    cs:__imp_HeapAlloc
0x1800aad88  nop     dword ptr [rax+rax+00h]
0x1800aad8d  mov     rsi, rax
0x1800aad90  test    rax, rax
0x1800aad93  jz      loc_1800AAFA0
0x1800aad99  add     r14, 2
0x1800aad9d  add     r14, r15
0x1800aada0  lea     rbx, [r14+r14]
0x1800aada4  call    cs:__imp_GetProcessHeap
0x1800aadab  nop     dword ptr [rax+rax+00h]
0x1800aadb0  mov     r8, rbx; dwBytes
0x1800aadb3  mov     edx, 8; dwFlags
0x1800aadb8  mov     rcx, rax; hHeap
0x1800aadbb  call    cs:__imp_HeapAlloc
0x1800aadc2  nop     dword ptr [rax+rax+00h]
0x1800aadc7  mov     r13, rax
0x1800aadca  test    rax, rax
0x1800aadcd  jz      loc_1800AAFA0
0x1800aadd3  mov     r9, [rsp+1A0h+var_128]
0x1800aadd8  lea     rax, [rbp+0A0h+var_90]
0x1800aaddc  lea     r8, aSS_2; "%s\\%s"
0x1800aade3  mov     [rsp+1A0h+AllocationSize], rax
0x1800aade8  mov     rdx, r14; unsigned __int64
0x1800aadeb  mov     rcx, r13; unsigned __int16 *
0x1800aadee  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aadf3  xor     r14d, r14d
0x1800aadf6  test    eax, eax
0x1800aadf8  js      loc_1800AAFA0
0x1800aadfe  mov     rdx, [rbp+0A0h+var_120]; unsigned __int64
0x1800aae02  lea     r9, [rbp+0A0h+var_90]
0x1800aae06  lea     r8, aS; "%s"
0x1800aae0d  mov     rcx, rsi; unsigned __int16 *
0x1800aae10  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800aae15  test    eax, eax
0x1800aae17  js      loc_1800AAFA0
0x1800aae1d  xor     r9d, r9d; DirectoryInfo
0x1800aae20  lea     rdx, [rbp+0A0h+NtPathName]; NtPathName
0x1800aae24  xor     r8d, r8d; NtFileNamePart
0x1800aae27  mov     rcx, r13; DosPathName
0x1800aae2a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800aae31  nop     dword ptr [rax+rax+00h]
0x1800aae36  test    al, al
0x1800aae38  jz      loc_1800AAFA0
0x1800aae3e  mov     rdx, rsi; SourceString
0x1800aae41  lea     rcx, [rbp+0A0h+DestinationString]; DestinationString
0x1800aae45  call    cs:__imp_RtlInitUnicodeString
0x1800aae4c  nop     dword ptr [rax+rax+00h]
0x1800aae51  mov     rax, [rbp+0A0h+NtPathName.Buffer]
0x1800aae55  lea     r9, [rbp+0A0h+IoStatusBlock]; IoStatusBlock
0x1800aae59  mov     [rsp+1A0h+EaLength], r14d; EaLength
0x1800aae5e  lea     r8, [rbp+0A0h+ObjectAttributes]; ObjectAttributes
0x1800aae62  mov     [rsp+1A0h+EaBuffer], r14; EaBuffer
0x1800aae67  mov     ecx, 1040h
0x1800aae6c  mov     [rsp+1A0h+CreateOptions], ecx; CreateOptions
0x1800aae70  xorps   xmm0, xmm0
0x1800aae73  mov     [rsp+1A0h+P], rax
0x1800aae78  mov     edx, 10001h; DesiredAccess
0x1800aae7d  mov     rax, [rbp+0A0h+var_118]
0x1800aae81  mov     [rsp+1A0h+CreateDisposition], 2; CreateDisposition
0x1800aae89  mov     [rbp+0A0h+ObjectAttributes.RootDirectory], rax
0x1800aae8d  lea     rax, [rbp+0A0h+DestinationString]
0x1800aae91  mov     [rbp+0A0h+ObjectAttributes.Attributes], ecx
0x1800aae94  lea     rcx, [rsp+1A0h+FileHandle]; FileHandle
0x1800aae99  mov     [rsp+1A0h+ShareAccess], r14d; ShareAccess
0x1800aae9e  mov     [rsp+1A0h+FileAttributes], 82h; FileAttributes
0x1800aaea6  mov     [rbp+0A0h+ObjectAttributes.ObjectName], rax
0x1800aaeaa  mov     [rbp+0A0h+ObjectAttributes.Length], 30h ; '0'
0x1800aaeb1  movdqu  xmmword ptr [rbp+0A0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800aaeb6  mov     [rsp+1A0h+AllocationSize], r14; AllocationSize
0x1800aaebb  call    cs:__imp_NtCreateFile
0x1800aaec2  nop     dword ptr [rax+rax+00h]
0x1800aaec7  test    eax, eax
0x1800aaec9  js      loc_1800AAFB6
0x1800aaecf  lea     edx, [r14+3Ah]; Ch
0x1800aaed3  mov     rcx, r13; Str
0x1800aaed6  call    cs:__imp_wcschr
0x1800aaedd  nop     dword ptr [rax+rax+00h]
0x1800aaee2  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800aaee7  mov     r15d, r14d
0x1800aaeea  test    rax, rax
0x1800aaeed  setz    r15b
0x1800aaef1  xor     r8d, r8d; cchFilePath
0x1800aaef4  mov     r9d, r15d; dwFlags
0x1800aaef7  xor     edx, edx; lpszFilePath
0x1800aaef9  call    cs:__imp_GetFinalPathNameByHandleW
0x1800aaf00  nop     dword ptr [rax+rax+00h]
0x1800aaf05  test    eax, eax
0x1800aaf07  jz      loc_1800AAFA0
0x1800aaf0d  lea     r14d, [rax+1]
0x1800aaf11  mov     ebx, r14d
0x1800aaf14  add     rbx, rbx
0x1800aaf17  call    cs:__imp_GetProcessHeap
0x1800aaf1e  nop     dword ptr [rax+rax+00h]
0x1800aaf23  mov     r8, rbx; dwBytes
0x1800aaf26  mov     edx, 8; dwFlags
0x1800aaf2b  mov     rcx, rax; hHeap
0x1800aaf2e  call    cs:__imp_HeapAlloc
0x1800aaf35  nop     dword ptr [rax+rax+00h]
0x1800aaf3a  mov     r12, rax
0x1800aaf3d  test    rax, rax
0x1800aaf40  jz      short loc_1800AAFA0
0x1800aaf42  mov     rcx, [rsp+1A0h+FileHandle]; hFile
0x1800aaf47  mov     r9d, r15d; dwFlags
0x1800aaf4a  mov     r8d, r14d; cchFilePath
0x1800aaf4d  mov     rdx, rax; lpszFilePath
0x1800aaf50  call    cs:__imp_GetFinalPathNameByHandleW
0x1800aaf57  nop     dword ptr [rax+rax+00h]
0x1800aaf5c  test    eax, eax
0x1800aaf5e  jz      short loc_1800AAFA0
0x1800aaf60  xor     r9d, r9d; DirectoryInfo
0x1800aaf63  lea     rdx, [rbp+0A0h+var_C0]; NtPathName
0x1800aaf67  xor     r8d, r8d; NtFileNamePart
0x1800aaf6a  mov     rcx, r12; DosPathName
0x1800aaf6d  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800aaf74  nop     dword ptr [rax+rax+00h]
0x1800aaf79  test    al, al
0x1800aaf7b  jz      short loc_1800AAFA0
0x1800aaf7d  mov     rbx, [rbp+0A0h+var_C0.Buffer]
0x1800aaf81  mov     rcx, [rbp+0A0h+NtPathName.Buffer]; String1
0x1800aaf85  mov     rdx, rbx; String2
0x1800aaf88  mov     [rsp+1A0h+var_130], rbx
0x1800aaf8d  call    _wcsicmp_0
0x1800aaf92  test    eax, eax
0x1800aaf94  jnz     short loc_1800AAFA0
0x1800aaf96  mov     rdi, [rsp+1A0h+FileHandle]
0x1800aaf9b  jmp     short loc_1800AAFBB
0x1800aaf9d  mov     rsi, r14
0x1800aafa0  mov     rcx, [rsp+1A0h+FileHandle]; Handle
0x1800aafa5  cmp     rcx, rdi
0x1800aafa8  jz      short loc_1800AAFBB
0x1800aafaa  call    cs:__imp_NtClose
0x1800aafb1  nop     dword ptr [rax+rax+00h]
0x1800aafb6  mov     [rsp+1A0h+FileHandle], rdi
0x1800aafbb  mov     rax, [rsp+1A0h+P]
0x1800aafc0  test    rax, rax
0x1800aafc3  jz      short loc_1800AAFE3
0x1800aafc5  mov     rcx, gs:60h
0x1800aafce  mov     r8, rax; P
0x1800aafd1  xor     edx, edx; Flags
0x1800aafd3  mov     rcx, [rcx+30h]; HeapHandle
0x1800aafd7  call    cs:__imp_RtlFreeHeap
0x1800aafde  nop     dword ptr [rax+rax+00h]
0x1800aafe3  mov     rax, [rsp+1A0h+var_130]
0x1800aafe8  test    rax, rax
0x1800aafeb  jz      short loc_1800AB00B
0x1800aafed  mov     rcx, gs:60h
0x1800aaff6  mov     r8, rax; P
0x1800aaff9  xor     edx, edx; Flags
0x1800aaffb  mov     rcx, [rcx+30h]; HeapHandle
0x1800aafff  call    cs:__imp_RtlFreeHeap
0x1800ab006  nop     dword ptr [rax+rax+00h]
0x1800ab00b  test    r13, r13
0x1800ab00e  jz      short loc_1800AB030
0x1800ab010  call    cs:__imp_GetProcessHeap
0x1800ab017  nop     dword ptr [rax+rax+00h]
0x1800ab01c  mov     r8, r13; lpMem
0x1800ab01f  xor     edx, edx; dwFlags
0x1800ab021  mov     rcx, rax; hHeap
0x1800ab024  call    cs:__imp_HeapFree
0x1800ab02b  nop     dword ptr [rax+rax+00h]
0x1800ab030  test    r12, r12
0x1800ab033  jz      short loc_1800AB055
0x1800ab035  call    cs:__imp_GetProcessHeap
0x1800ab03c  nop     dword ptr [rax+rax+00h]
0x1800ab041  mov     r8, r12; lpMem
0x1800ab044  xor     edx, edx; dwFlags
0x1800ab046  mov     rcx, rax; hHeap
0x1800ab049  call    cs:__imp_HeapFree
0x1800ab050  nop     dword ptr [rax+rax+00h]
0x1800ab055  test    rsi, rsi
0x1800ab058  jz      short loc_1800AB07A
0x1800ab05a  call    cs:__imp_GetProcessHeap
0x1800ab061  nop     dword ptr [rax+rax+00h]
0x1800ab066  mov     r8, rsi; lpMem
0x1800ab069  xor     edx, edx; dwFlags
0x1800ab06b  mov     rcx, rax; hHeap
0x1800ab06e  call    cs:__imp_HeapFree
0x1800ab075  nop     dword ptr [rax+rax+00h]
0x1800ab07a  mov     rax, rdi
0x1800ab07d  mov     rcx, [rbp+0A0h+var_40]
0x1800ab081  xor     rcx, rsp; StackCookie
0x1800ab084  call    __security_check_cookie
0x1800ab089  mov     rbx, [rsp+1A0h+arg_10]
0x1800ab091  add     rsp, 170h
0x1800ab098  pop     r15
0x1800ab09a  pop     r14
0x1800ab09c  pop     r13
0x1800ab09e  pop     r12
0x1800ab0a0  pop     rdi
0x1800ab0a1  pop     rsi
0x1800ab0a2  pop     rbp
0x1800ab0a3  retn
```
