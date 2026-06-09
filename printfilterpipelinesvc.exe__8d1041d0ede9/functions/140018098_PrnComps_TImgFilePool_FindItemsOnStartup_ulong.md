# PrnComps::TImgFilePool::FindItemsOnStartup(ulong)

- ea: `0x140018098`
- end: `0x1400181d6`
- name: `?FindItemsOnStartup@TImgFilePool@PrnComps@@AEAAXK@Z`
- size: `318`
- prototype: `void __fastcall(PrnComps::TImgFilePool *this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14001782c`

## callees

- `0x140002070`
- `0x140002c68`
- `0x14000537c`
- `0x140010e58`
- `0x140013250`
- `0x140018098`
- `0x140018984`
- `0x14004650c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140018172`
- `KERNEL32!GetLastError` at `0x140018172`
- `KERNEL32!FindNextFileW` at `0x14001815d`
- `KERNEL32!FindNextFileW` at `0x14001815d`
- `KERNEL32!DeleteFileW` at `0x140018145`
- `KERNEL32!DeleteFileW` at `0x140018145`
- `KERNEL32!FindFirstFileW` at `0x140018114`
- `KERNEL32!FindFirstFileW` at `0x140018114`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall PrnComps::TImgFilePool::FindItemsOnStartup(PrnComps::TImgFilePool *this)
{
  int v1; // eax
  int v2; // edx
  const char *v3; // r8
  unsigned int v4; // r9d
  __int64 FirstFileW; // rbx
  __int64 v6; // rcx
  void *v7; // rcx
  DWORD LastError; // eax
  int v9; // edx
  unsigned int v10; // eax
  int v11; // edx
  const char *v12; // r8
  unsigned int v13; // r9d
  NCoreLibrary::TString *v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-D0h] BYREF

  lpFileName = (LPCWSTR)&NCoreLibrary::TString::gszNullState;
  v1 = NCoreLibrary::TString::Format(
         (NCoreLibrary::TString *)&lpFileName,
         L"%s*%s",
         *((_QWORD *)this + 3),
         *((_QWORD *)this + 4));
  if ( v1 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v1, v2, v3, v4);
  v15 = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(&v15);
  if ( FirstFileW )
  {
    v15 = FirstFileW;
    v6 = 0;
    if ( FirstFileW != -1 )
      v6 = FirstFileW;
    if ( v6 )
    {
      do
      {
        DeleteFileW(FindFileData.cFileName);
        v7 = (void *)FirstFileW;
        if ( FirstFileW == -1 )
          v7 = 0;
      }
      while ( FindNextFileW(v7, &FindFileData) );
    }
  }
  else
  {
    FirstFileW = -1;
    v15 = -1;
  }
  LastError = GetLastError();
  if ( FirstFileW != -1 && LastError != 18 )
  {
    v10 = NCoreLibrary::HResultFromWin32((NCoreLibrary *)LastError, v9);
    SplException::RealThrowFromHR((SplException *)v10, v11, v12, v13);
  }
  NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(&v15);
  NCoreLibrary::TString::vFree(v14, (void *)lpFileName);
}

```

## disassembly

```asm
0x140018098  mov     [rsp-8+arg_8], rbx
0x14001809d  push    rbp
0x14001809e  lea     rbp, [rsp-190h]
0x1400180a6  sub     rsp, 290h
0x1400180ad  mov     rax, cs:__security_cookie
0x1400180b4  xor     rax, rsp
0x1400180b7  mov     [rbp+190h+var_10], rax
0x1400180be  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PA_WA; wchar_t near * NCoreLibrary::TString::gszNullState
0x1400180c5  mov     [rsp+290h+lpFileName], rax
0x1400180ca  mov     r9, [rcx+20h]
0x1400180ce  mov     r8, [rcx+18h]
0x1400180d2  lea     rdx, aSS_0; "%s*%s"
0x1400180d9  lea     rcx, [rsp+290h+lpFileName]; this
0x1400180de  call    ?Format@TString@NCoreLibrary@@QEAAJPEB_WZZ; NCoreLibrary::TString::Format(wchar_t const *,...)
0x1400180e3  test    eax, eax
0x1400180e5  jns     short loc_1400180EF
0x1400180e7  mov     ecx, eax; this
0x1400180e9  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400180ef  mov     [rsp+290h+var_270], 0FFFFFFFFFFFFFFFFh
0x1400180f8  xor     edx, edx; Val
0x1400180fa  mov     r8d, 250h; Size
0x140018100  lea     rcx, [rsp+290h+FindFileData]; void *
0x140018105  call    memset_0
0x14001810a  lea     rdx, [rsp+290h+FindFileData]; lpFindFileData
0x14001810f  mov     rcx, [rsp+290h+lpFileName]; lpFileName
0x140018114  call    cs:__imp_FindFirstFileW
0x14001811a  mov     rbx, rax
0x14001811d  lea     rcx, [rsp+290h+var_270]
0x140018122  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleFindFirst@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(void)
0x140018127  test    rbx, rbx
0x14001812a  jz      short loc_140018169
0x14001812c  mov     [rsp+290h+var_270], rbx
0x140018131  xor     ecx, ecx
0x140018133  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140018137  cmovnz  rcx, rbx
0x14001813b  test    rcx, rcx
0x14001813e  jz      short loc_140018172
0x140018140  lea     rcx, [rsp+290h+FindFileData.cFileName]; lpFileName
0x140018145  call    cs:__imp_DeleteFileW
0x14001814b  mov     rcx, rbx
0x14001814e  xor     eax, eax
0x140018150  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140018154  cmovz   rcx, rax; hFindFile
0x140018158  lea     rdx, [rsp+290h+FindFileData]; lpFindFileData
0x14001815d  call    cs:__imp_FindNextFileW
0x140018163  test    eax, eax
0x140018165  jnz     short loc_140018140
0x140018167  jmp     short loc_140018172
0x140018169  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001816d  mov     [rsp+290h+var_270], rbx
0x140018172  call    cs:__imp_GetLastError
0x140018178  test    rbx, rbx
0x14001817b  jnz     short loc_140018182
0x14001817d  cmp     eax, 2
0x140018180  jnz     short loc_140018192
0x140018182  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140018186  jz      short loc_1400181A1
0x140018188  test    rbx, rbx
0x14001818b  jz      short loc_1400181A1
0x14001818d  cmp     eax, 12h
0x140018190  jz      short loc_1400181A1
0x140018192  mov     ecx, eax; this
0x140018194  call    ?HResultFromWin32@NCoreLibrary@@YAJJ@Z; NCoreLibrary::HResultFromWin32(long)
0x140018199  mov     ecx, eax; this
0x14001819b  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1400181a1  lea     rcx, [rsp+290h+var_270]
0x1400181a6  call    ?Reset@?$TGenericSP@PEAXVTAutoHandleFindFirst@NCoreLibrary@@PEAX$0?0PEBQEAX@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<void *,NCoreLibrary::TAutoHandleFindFirst,void *,-1,void * const *>::Reset(void)
0x1400181ab  nop
0x1400181ac  mov     rdx, [rsp+290h+lpFileName]; void *
0x1400181b1  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x1400181b6  mov     rcx, [rbp+190h+var_10]
0x1400181bd  xor     rcx, rsp; StackCookie
0x1400181c0  call    __security_check_cookie
0x1400181c5  mov     rbx, [rsp+290h+arg_8]
0x1400181cd  add     rsp, 290h
0x1400181d4  pop     rbp
0x1400181d5  retn
```
