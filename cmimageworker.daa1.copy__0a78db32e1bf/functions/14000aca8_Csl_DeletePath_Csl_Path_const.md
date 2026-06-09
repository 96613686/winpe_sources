# Csl::DeletePath(Csl::Path const &)

- ea: `0x14000aca8`
- end: `0x14000ad5d`
- name: `?DeletePath@Csl@@YAJAEBVPath@1@@Z`
- size: `181`
- prototype: `__int64 __fastcall(Csl *__hidden this, const struct Path *)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140018d5c`
- `0x140019e40`
- `0x14001b938`
- `0x14001d310`

## callees

- `0x14000aca8`
- `0x14000c6a4`
- `0x14000e4c0`
- `0x14000ecc4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000acb8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000acb8`

## string_xrefs

- `0x14000acf0`: `Failed to delete directory %ws`
- `0x14000ad41`: `Failed to delete file %ws`

## pseudocode

```c
__int64 __fastcall Csl::DeletePath(LPCWSTR *this, const struct Path *a2)
{
  DWORD FileAttributesW; // eax
  __int64 v4; // r9
  LPCWSTR v5; // rcx
  __int64 result; // rax
  unsigned int v7; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  FileAttributesW = GetFileAttributesW(*this);
  v5 = *this;
  if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
  {
    result = WcpRemoveFile((__int64)v5, 0, 0, v4, 1);
    v7 = result;
    if ( (unsigned int)(result + 2147024894) <= 1 )
      return result;
    if ( (int)result < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2C3,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)result,
        (int)"Failed to delete file %ws",
        (const char *)*this);
      return v7;
    }
  }
  else
  {
    result = WcRemoveFilesInDirectory((int)v5);
    v7 = result;
    if ( (unsigned int)(result + 2147024894) <= 1 )
      return result;
    if ( (int)result < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)(unsigned int)result,
        (int)"Failed to delete directory %ws",
        (const char *)*this);
      return v7;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x14000aca8  mov     [rsp+arg_8], rbx
0x14000acad  push    rdi
0x14000acae  sub     rsp, 30h
0x14000acb2  mov     rdi, rcx
0x14000acb5  mov     rcx, [rcx]; lpFileName
0x14000acb8  call    cs:__imp_GetFileAttributesW
0x14000acbf  nop     dword ptr [rax+rax+00h]
0x14000acc4  mov     rcx, [rdi]; int
0x14000acc7  cmp     eax, 0FFFFFFFFh
0x14000acca  jz      short loc_14000AD19
0x14000accc  bt      eax, 4
0x14000acd0  jnb     short loc_14000AD19
0x14000acd2  call    WcRemoveFilesInDirectory
0x14000acd7  mov     ebx, eax
0x14000acd9  lea     ecx, [rax+7FF8FFFEh]
0x14000acdf  cmp     ecx, 1
0x14000ace2  jbe     short loc_14000AD51
0x14000ace4  test    eax, eax
0x14000ace6  jns     short loc_14000AD4F
0x14000ace8  mov     rdx, [rdi]
0x14000aceb  mov     [rsp+38h+var_10], rdx; char *
0x14000acf0  lea     rax, aFailedToDelete; "Failed to delete directory %ws"
0x14000acf7  mov     edx, 2B4h; void *
0x14000acfc  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000ad03  mov     r9d, ebx; char *
0x14000ad06  mov     qword ptr [rsp+38h+var_18], rax; int
0x14000ad0b  mov     rcx, [rsp+38h]; this
0x14000ad10  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x14000ad15  mov     eax, ebx
0x14000ad17  jmp     short loc_14000AD51
0x14000ad19  mov     byte ptr [rsp+38h+var_18], 1
0x14000ad1e  xor     r8d, r8d
0x14000ad21  xor     edx, edx
0x14000ad23  call    WcpRemoveFile
0x14000ad28  mov     ebx, eax
0x14000ad2a  lea     ecx, [rax+7FF8FFFEh]
0x14000ad30  cmp     ecx, 1
0x14000ad33  jbe     short loc_14000AD51
0x14000ad35  test    eax, eax
0x14000ad37  jns     short loc_14000AD4F
0x14000ad39  mov     rdx, [rdi]
0x14000ad3c  mov     [rsp+38h+var_10], rdx
0x14000ad41  lea     rax, aFailedToDelete_0; "Failed to delete file %ws"
0x14000ad48  mov     edx, 2C3h
0x14000ad4d  jmp     short loc_14000ACFC
0x14000ad4f  xor     eax, eax
0x14000ad51  mov     rbx, [rsp+38h+arg_8]
0x14000ad56  add     rsp, 30h
0x14000ad5a  pop     rdi
0x14000ad5b  retn
```
