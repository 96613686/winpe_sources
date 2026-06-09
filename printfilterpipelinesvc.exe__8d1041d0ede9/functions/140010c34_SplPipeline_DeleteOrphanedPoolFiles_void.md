# SplPipeline::DeleteOrphanedPoolFiles(void)

- ea: `0x140010c34`
- end: `0x140010d59`
- name: `?DeleteOrphanedPoolFiles@SplPipeline@@YAXXZ`
- size: `293`
- prototype: `void __fastcall(SplPipeline *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x140007fb0`

## callees

- `0x140002070`
- `0x140002c68`
- `0x140007654`
- `0x140009848`
- `0x14000d494`
- `0x140010c34`
- `0x140011310`
- `0x14004650c`

## import_xrefs

- `KERNEL32!FindClose` at `0x140010d28`
- `KERNEL32!FindClose` at `0x140010d28`
- `KERNEL32!FindNextFileW` at `0x140010d1b`
- `KERNEL32!FindNextFileW` at `0x140010d1b`
- `KERNEL32!DeleteFileW` at `0x140010d0d`
- `KERNEL32!DeleteFileW` at `0x140010d0d`
- `KERNEL32!FindFirstFileW` at `0x140010cca`
- `KERNEL32!FindFirstFileW` at `0x140010cca`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall SplPipeline::DeleteOrphanedPoolFiles(SplPipeline *this)
{
  wchar_t *FilePoolDirectory; // rax
  int v2; // eax
  int v3; // edx
  const char *v4; // r8
  unsigned int v5; // r9d
  HANDLE FirstFileW; // rbx
  SplException *v7; // rbx
  struct SplException::TSystemException *v8; // rdx
  __int64 v9; // [rsp+0h] [rbp-4C8h] BYREF
  __int64 v10; // [rsp+30h] [rbp-498h] BYREF
  SplException::TSystemException *v11; // [rsp+38h] [rbp-490h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-488h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp-238h] BYREF
  std::bad_alloc *v14; // [rsp+4A0h] [rbp-28h] BYREF
  std::exception *v15; // [rsp+4A8h] [rbp-20h] BYREF

  v10 = 0;
  try
  {
    FilePoolDirectory = SplPipeline::GetFilePoolDirectory(this);
    NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(&v10, FilePoolDirectory);
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    v2 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s*%s", v10, aPp, aTmp);
    if ( v2 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v2, v3, v4, v5);
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( (int)StringCchPrintfW(FileName, 0x104u, L"%s\\%s", v10, FindFileData.cFileName) >= 0 )
          DeleteFileW(FileName);
      }
      while ( FindNextFileW(FirstFileW, &FindFileData) );
      FindClose(FirstFileW);
    }
    NCoreLibrary::TGenericSP<unsigned char,NCoreLibrary::TAutoPtrArray<unsigned char>,unsigned char *,0,unsigned char const *>::Reset(&v10);
  }
  catch ( SplException::TSystemException *v11 )
  {
    v8 = (struct SplException::TSystemException *)&v9;
    v7 = v11;
    if ( SplException::gpfnExceptionLogger )
      SplException::gpfnExceptionLogger(v11);
    SplException::SetErrorInfoFromException(v7, v8);
    return;
  }
  catch ( std::bad_alloc *v14 )
  {
    SetErrorInfo(0, 0);
    return;
  }
  catch ( std::exception *v15 )
  {
    SetErrorInfo(0, 0);
  }
}

```

## disassembly

```asm
0x140010c34  push    rbx
0x140010c36  sub     rsp, 4C0h
0x140010c3d  mov     rax, cs:__security_cookie
0x140010c44  xor     rax, rsp
0x140010c47  mov     [rsp+4C8h+var_18], rax
0x140010c4f  mov     [rsp+4C8h+var_498], 0
0x140010c58  call    ?GetFilePoolDirectory@SplPipeline@@YAPEA_WXZ; SplPipeline::GetFilePoolDirectory(void)
0x140010c5d  mov     rdx, rax
0x140010c60  lea     rcx, [rsp+4C8h+var_498]
0x140010c65  call    ??4?$TAutoPtrArray@_W@NCoreLibrary@@QEAAPEA_WPEA_W@Z; NCoreLibrary::TAutoPtrArray<wchar_t>::operator=(wchar_t *)
0x140010c6a  xor     edx, edx; Val
0x140010c6c  mov     r8d, 250h; Size
0x140010c72  lea     rcx, [rsp+4C8h+FindFileData]; void *
0x140010c77  call    memset_0
0x140010c7c  lea     rax, aTmp; ".TMP"
0x140010c83  mov     [rsp+4C8h+var_4A0], rax
0x140010c88  lea     rax, aPp; "PP"
0x140010c8f  mov     [rsp+4C8h+var_4A8], rax
0x140010c94  mov     r9, [rsp+4C8h+var_498]
0x140010c99  lea     r8, aSSS; "%s\\%s*%s"
0x140010ca0  mov     edx, 104h; unsigned __int64
0x140010ca5  lea     rcx, [rsp+4C8h+FileName]; wchar_t *
0x140010cad  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140010cb2  test    eax, eax
0x140010cb4  jns     short loc_140010CBD
0x140010cb6  mov     ecx, eax; this
0x140010cb8  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x140010cbd  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140010cc2  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140010cca  call    cs:__imp_FindFirstFileW
0x140010cd0  mov     rbx, rax
0x140010cd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140010cd7  jz      short loc_140010D2F
0x140010cd9  lea     rax, [rsp+4C8h+FindFileData.cFileName]
0x140010cde  mov     [rsp+4C8h+var_4A8], rax
0x140010ce3  mov     r9, [rsp+4C8h+var_498]
0x140010ce8  lea     r8, aSS; "%s\\%s"
0x140010cef  mov     edx, 104h; unsigned __int64
0x140010cf4  lea     rcx, [rsp+4C8h+FileName]; wchar_t *
0x140010cfc  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140010d01  test    eax, eax
0x140010d03  js      short loc_140010D13
0x140010d05  lea     rcx, [rsp+4C8h+FileName]; lpFileName
0x140010d0d  call    cs:__imp_DeleteFileW
0x140010d13  lea     rdx, [rsp+4C8h+FindFileData]; lpFindFileData
0x140010d18  mov     rcx, rbx; hFindFile
0x140010d1b  call    cs:__imp_FindNextFileW
0x140010d21  test    eax, eax
0x140010d23  jnz     short loc_140010CD9
0x140010d25  mov     rcx, rbx; hFindFile
0x140010d28  call    cs:__imp_FindClose
0x140010d2e  nop
0x140010d2f  lea     rcx, [rsp+4C8h+var_498]
0x140010d34  call    ?Reset@?$TGenericSP@EV?$TAutoPtrArray@E@NCoreLibrary@@PEAE$0A@PEBE@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<uchar,NCoreLibrary::TAutoPtrArray<uchar>,uchar *,0,uchar const *>::Reset(void)
0x140010d39  nop
0x140010d3a  jmp     short loc_140010D40
0x140010d3c  jmp     short loc_140010D40
0x140010d3e  jmp     short $+2
0x140010d40  mov     rcx, [rsp+4C8h+var_18]
0x140010d48  xor     rcx, rsp; StackCookie
0x140010d4b  call    __security_check_cookie
0x140010d50  add     rsp, 4C0h
0x140010d57  pop     rbx
0x140010d58  retn
```
