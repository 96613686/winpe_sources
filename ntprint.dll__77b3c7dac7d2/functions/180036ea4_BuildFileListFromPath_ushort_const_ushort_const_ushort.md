# BuildFileListFromPath(ushort const *,ushort const *,ushort * *)

- ea: `0x180036ea4`
- end: `0x180037050`
- name: `?BuildFileListFromPath@@YAKPEBG0PEAPEAG@Z`
- size: `428`
- prototype: `unsigned int __fastcall(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800281a0`

## callees

- `0x18000d558`
- `0x180015df0`
- `0x18001c660`
- `0x180036a0c`
- `0x180036d04`
- `0x180036ea4`
- `0x180037058`
- `0x180037320`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036ef2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180036ef2`

## string_xrefs

- `0x180036f31`: `BuildFileListFromPath`
- `0x180036fc1`: `BuildFileListFromPath`
- `0x180036ff4`: `BuildFileListFromPath`
- `0x180037017`: `BuildFileListFromPath`
- `0x180036fba`: `GetFilesInDirectory failed with hr: 0x%x`
- `0x180036fed`: `Failed to allocate memory for the directory path!`
- `0x180036f2a`: `StringCbCopyN failed with hr: 0x%x`
- `0x180037010`: `Failed to isolate the file and path information!`

## pseudocode

```c
__int64 __fastcall BuildFileListFromPath(STRSAFE_PCNZWCH pszSrc, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  unsigned __int16 *v3; // rdi
  const unsigned __int16 *FileName; // rax
  __int64 v8; // rax
  unsigned __int64 v9; // rbx
  unsigned __int64 v10; // rbp
  wchar_t *v11; // rsi
  size_t v12; // rbp
  size_t cchToCopy; // rbx
  HRESULT v14; // ebx
  unsigned int v15; // ebx
  int FilesInDirectory; // eax
  int v17; // edi
  void **v19; // [rsp+30h] [rbp-48h] BYREF
  __int128 v20; // [rsp+38h] [rbp-40h]
  int v21; // [rsp+48h] [rbp-30h]
  int v22; // [rsp+4Ch] [rbp-2Ch]
  unsigned __int16 *v23; // [rsp+90h] [rbp+18h] BYREF

  v3 = 0;
  *a3 = 0;
  v23 = 0;
  FileName = FindFileName(pszSrc);
  if ( !FileName )
  {
    SplLibTelemetry::WriteDbgTraceError("BuildFileListFromPath", L"Failed to isolate the file and path information!");
    v15 = 2;
    goto LABEL_18;
  }
  v8 = FileName - pszSrc;
  v9 = 2 * v8;
  v10 = 2 * v8 + 2;
  v11 = (wchar_t *)LocalAlloc(0x40u, (unsigned int)(2 * v8 + 2));
  if ( v11 )
  {
    v12 = v10 >> 1;
    if ( v12 - 1 > 0x7FFFFFFE )
    {
      v14 = -2147024809;
    }
    else
    {
      cchToCopy = v9 >> 1;
      if ( cchToCopy > 0x7FFFFFFE )
      {
        v14 = -2147024809;
        *v11 = 0;
        goto LABEL_6;
      }
      v14 = StringCopyWorkerW_0(v11, v12, 0, pszSrc, cchToCopy);
    }
    if ( v14 >= 0 )
    {
      v22 = 1;
      v19 = &TDoubleList<FileEntry *,unsigned long>::`vftable';
      v15 = 0;
      v21 = 0;
      v20 = 0;
      FilesInDirectory = FileListBuilder::GetFilesInDirectory((FileListBuilder *)&v19, v11, a2, &v23);
      v17 = FilesInDirectory;
      if ( FilesInDirectory < 0 )
      {
        SplLibTelemetry::WriteDbgTraceError(
          "BuildFileListFromPath",
          L"GetFilesInDirectory failed with hr: 0x%x",
          (unsigned int)FilesInDirectory);
        v15 = WIN32_FROM_HRESULT(v17);
      }
      TDoubleList<FileEntry *,unsigned long>::~TDoubleList<FileEntry *,unsigned long>(&v19);
      v3 = v23;
      goto LABEL_7;
    }
LABEL_6:
    SplLibTelemetry::WriteDbgTraceError(
      "BuildFileListFromPath",
      L"StringCbCopyN failed with hr: 0x%x",
      (unsigned int)v14);
    v15 = WIN32_FROM_HRESULT(v14);
LABEL_7:
    DllFreeSplMem(v11);
    goto LABEL_15;
  }
  SplLibTelemetry::WriteDbgTraceError("BuildFileListFromPath", L"Failed to allocate memory for the directory path!");
  v15 = 14;
LABEL_15:
  if ( !v15 )
  {
    *a3 = v3;
    v3 = 0;
  }
LABEL_18:
  if ( v3 )
    DllFreeSplMem(v3);
  return v15;
}

```

## disassembly

```asm
0x180036ea4  mov     rax, rsp
0x180036ea7  mov     [rax+8], rbx
0x180036eab  mov     [rax+10h], rbp
0x180036eaf  push    rsi
0x180036eb0  push    rdi
0x180036eb1  push    r12
0x180036eb3  push    r14
0x180036eb5  push    r15
0x180036eb7  sub     rsp, 50h
0x180036ebb  xor     edi, edi
0x180036ebd  mov     qword ptr [r8], 0
0x180036ec4  mov     [rax+18h], rdi
0x180036ec8  mov     r15, r8
0x180036ecb  mov     r12, rdx
0x180036ece  mov     r14, rcx
0x180036ed1  call    ?FindFileName@@YAPEBGPEBG@Z; FindFileName(ushort const *)
0x180036ed6  test    rax, rax
0x180036ed9  jz      loc_180037010
0x180036edf  sub     rax, r14
0x180036ee2  lea     ecx, [rdi+40h]; uFlags
0x180036ee5  sar     rax, 1
0x180036ee8  lea     rbx, [rax+rax]
0x180036eec  lea     rbp, [rbx+2]
0x180036ef0  mov     edx, ebp; uBytes
0x180036ef2  call    cs:__imp_LocalAlloc
0x180036ef8  mov     rsi, rax
0x180036efb  test    rax, rax
0x180036efe  jz      loc_180036FED
0x180036f04  shr     rbp, 1
0x180036f07  mov     eax, 7FFFFFFEh
0x180036f0c  lea     rcx, [rbp-1]
0x180036f10  cmp     rcx, rax
0x180036f13  ja      short loc_180036F6D
0x180036f15  shr     rbx, 1
0x180036f18  cmp     rbx, rax
0x180036f1b  jbe     short loc_180036F53
0x180036f1d  xor     eax, eax
0x180036f1f  mov     ebx, 80070057h
0x180036f24  mov     [rsi], ax
0x180036f27  mov     r8d, ebx
0x180036f2a  lea     rdx, aStringcbcopynF; "StringCbCopyN failed with hr: 0x%x"
0x180036f31  lea     rcx, aBuildfilelistf_0; "BuildFileListFromPath"
0x180036f38  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180036f3d  mov     ecx, ebx; int
0x180036f3f  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180036f44  mov     ebx, eax
0x180036f46  mov     rcx, rsi
0x180036f49  call    DllFreeSplMem
0x180036f4e  jmp     loc_180037005
0x180036f53  mov     r9, r14; pszSrc
0x180036f56  mov     [rsp+78h+cchToCopy], rbx; cchToCopy
0x180036f5b  xor     r8d, r8d; pcchNewDestLength
0x180036f5e  mov     rdx, rbp; cchDest
0x180036f61  mov     rcx, rsi; pszDest
0x180036f64  call    StringCopyWorkerW_0
0x180036f69  mov     ebx, eax
0x180036f6b  jmp     short loc_180036F72
0x180036f6d  mov     ebx, 80070057h
0x180036f72  test    ebx, ebx
0x180036f74  js      short loc_180036F27
0x180036f76  lea     rax, ??_7?$TDoubleList@PEAVFileEntry@@K@@6B@; const TDoubleList<FileEntry *,ulong>::`vftable'
0x180036f7d  mov     [rsp+78h+var_2C], 1
0x180036f85  xorps   xmm0, xmm0
0x180036f88  mov     [rsp+78h+var_48], rax
0x180036f8d  xor     ebx, ebx
0x180036f8f  lea     r9, [rsp+78h+arg_10]; unsigned __int16 **
0x180036f97  mov     r8, r12; unsigned __int16 *
0x180036f9a  mov     [rsp+78h+var_30], ebx
0x180036f9e  mov     rdx, rsi; unsigned __int16 *
0x180036fa1  lea     rcx, [rsp+78h+var_48]; this
0x180036fa6  movdqu  [rsp+78h+var_40], xmm0
0x180036fac  call    ?GetFilesInDirectory@FileListBuilder@@QEAAJPEBG0PEAPEAG@Z; FileListBuilder::GetFilesInDirectory(ushort const *,ushort const *,ushort * *)
0x180036fb1  mov     edi, eax
0x180036fb3  test    eax, eax
0x180036fb5  jns     short loc_180036FD6
0x180036fb7  mov     r8d, eax
0x180036fba  lea     rdx, aGetfilesindire_1; "GetFilesInDirectory failed with hr: 0x%"...
0x180036fc1  lea     rcx, aBuildfilelistf_0; "BuildFileListFromPath"
0x180036fc8  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180036fcd  mov     ecx, edi; int
0x180036fcf  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180036fd4  mov     ebx, eax
0x180036fd6  lea     rcx, [rsp+78h+var_48]
0x180036fdb  call    ??1?$TDoubleList@PEAVFileEntry@@K@@UEAA@XZ; TDoubleList<FileEntry *,ulong>::~TDoubleList<FileEntry *,ulong>(void)
0x180036fe0  mov     rdi, [rsp+78h+arg_10]
0x180036fe8  jmp     loc_180036F46
0x180036fed  lea     rdx, aFailedToAlloca_2; "Failed to allocate memory for the direc"...
0x180036ff4  lea     rcx, aBuildfilelistf_0; "BuildFileListFromPath"
0x180036ffb  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037000  mov     ebx, 0Eh
0x180037005  test    ebx, ebx
0x180037007  jnz     short loc_180037028
0x180037009  mov     [r15], rdi
0x18003700c  xor     edi, edi
0x18003700e  jmp     short loc_180037028
0x180037010  lea     rdx, aFailedToIsolat; "Failed to isolate the file and path inf"...
0x180037017  lea     rcx, aBuildfilelistf_0; "BuildFileListFromPath"
0x18003701e  call    ?WriteDbgTraceError@SplLibTelemetry@@SAXPEADPEAGZZ; SplLibTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180037023  mov     ebx, 2
0x180037028  test    rdi, rdi
0x18003702b  jz      short loc_180037035
0x18003702d  mov     rcx, rdi
0x180037030  call    DllFreeSplMem
0x180037035  lea     r11, [rsp+78h+var_28]
0x18003703a  mov     eax, ebx
0x18003703c  mov     rbx, [r11+30h]
0x180037040  mov     rbp, [r11+38h]
0x180037044  mov     rsp, r11
0x180037047  pop     r15
0x180037049  pop     r14
0x18003704b  pop     r12
0x18003704d  pop     rdi
0x18003704e  pop     rsi
0x18003704f  retn
```
