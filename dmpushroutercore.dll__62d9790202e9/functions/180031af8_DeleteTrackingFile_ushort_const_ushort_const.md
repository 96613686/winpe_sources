# DeleteTrackingFile(ushort const *,ushort const *)

- ea: `0x180031af8`
- end: `0x180031bf6`
- name: `?DeleteTrackingFile@@YAJPEBG0@Z`
- size: `254`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180032ea8`

## callees

- `0x18000ba94`
- `0x18000bab4`
- `0x180031af8`
- `0x180032d0c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bde`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031b96`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031bde`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180031ba2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180031ba2`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180031b69`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x180031b69`

## pseudocode

```c
__int64 __fastcall DeleteTrackingFile(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  int StoragePath; // eax
  unsigned int LastError; // ebx
  HRESULT v6; // eax
  const char *v7; // r9
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+8h]
  HLOCAL hMem; // [rsp+40h] [rbp+20h] BYREF
  PWSTR ppszPathOut; // [rsp+48h] [rbp+28h] BYREF

  hMem = 0;
  StoragePath = GetStoragePath(a1, (PWSTR *)&hMem);
  LastError = StoragePath;
  if ( StoragePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)StoragePath,
      savedregs);
LABEL_3:
    if ( hMem )
      LocalFree(hMem);
    return LastError;
  }
  ppszPathOut = 0;
  v6 = PathAllocCombine((PCWSTR)hMem, a2, 0, &ppszPathOut);
  LastError = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x186,
      (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
    goto LABEL_8;
  }
  if ( !DeleteFileW(ppszPathOut) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x187,
                  (unsigned int)"onecoreuap\\admin\\dm\\dmstoreutils\\dmstoreutils.cpp",
                  v7);
LABEL_8:
    if ( ppszPathOut )
      LocalFree(ppszPathOut);
    goto LABEL_3;
  }
  if ( ppszPathOut )
    LocalFree(ppszPathOut);
  if ( hMem )
    LocalFree(hMem);
  return 0;
}

```

## disassembly

```asm
0x180031af8  mov     [rsp-8+arg_0], rbx
0x180031afd  mov     [rsp-8+arg_8], rdi
0x180031b02  push    rbp; int
0x180031b03  mov     rbp, rsp
0x180031b06  sub     rsp, 20h
0x180031b0a  mov     rdi, rdx
0x180031b0d  mov     [rbp+hMem], 0
0x180031b15  lea     rdx, [rbp+hMem]; ppszPathOut
0x180031b19  call    ?GetStoragePath@@YAJPEBGPEAPEAG@Z; GetStoragePath(ushort const *,ushort * *)
0x180031b1e  mov     ebx, eax
0x180031b20  test    eax, eax
0x180031b22  jns     short loc_180031B53
0x180031b24  mov     rcx, [rbp+8]; this
0x180031b28  mov     r9d, eax; char *
0x180031b2b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180031b32  mov     edx, 184h; void *
0x180031b37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031b3c  nop
0x180031b3d  mov     rcx, [rbp+hMem]; hMem
0x180031b41  test    rcx, rcx
0x180031b44  jz      short loc_180031B4C
0x180031b46  call    cs:__imp_LocalFree
0x180031b4c  mov     eax, ebx
0x180031b4e  jmp     loc_180031BE6
0x180031b53  mov     [rbp+ppszPathOut], 0
0x180031b5b  lea     r9, [rbp+ppszPathOut]; ppszPathOut
0x180031b5f  xor     r8d, r8d; dwFlags
0x180031b62  mov     rdx, rdi; pszMore
0x180031b65  mov     rcx, [rbp+hMem]; pszPathIn
0x180031b69  call    cs:__imp_PathAllocCombine
0x180031b6f  mov     ebx, eax
0x180031b71  test    eax, eax
0x180031b73  jns     short loc_180031B9E
0x180031b75  mov     rcx, [rbp+8]; this
0x180031b79  mov     r9d, eax; char *
0x180031b7c  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180031b83  mov     edx, 186h; void *
0x180031b88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031b8d  mov     rcx, [rbp+ppszPathOut]; hMem
0x180031b91  test    rcx, rcx
0x180031b94  jz      short loc_180031B3D
0x180031b96  call    cs:__imp_LocalFree
0x180031b9c  jmp     short loc_180031B3D
0x180031b9e  mov     rcx, [rbp+ppszPathOut]; lpFileName
0x180031ba2  call    cs:__imp_DeleteFileW
0x180031ba8  test    eax, eax
0x180031baa  jnz     short loc_180031BC5
0x180031bac  mov     rcx, [rbp+8]; this
0x180031bb0  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\dm\\dmstoreutils\\dm"...
0x180031bb7  mov     edx, 187h; void *
0x180031bbc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031bc1  mov     ebx, eax
0x180031bc3  jmp     short loc_180031B8D
0x180031bc5  mov     rcx, [rbp+ppszPathOut]; hMem
0x180031bc9  test    rcx, rcx
0x180031bcc  jz      short loc_180031BD5
0x180031bce  call    cs:__imp_LocalFree
0x180031bd4  nop
0x180031bd5  mov     rcx, [rbp+hMem]; hMem
0x180031bd9  test    rcx, rcx
0x180031bdc  jz      short loc_180031BE4
0x180031bde  call    cs:__imp_LocalFree
0x180031be4  xor     eax, eax
0x180031be6  mov     rbx, [rsp+20h+arg_0]
0x180031beb  mov     rdi, [rsp+20h+arg_8]
0x180031bf0  add     rsp, 20h
0x180031bf4  pop     rbp
0x180031bf5  retn
```
