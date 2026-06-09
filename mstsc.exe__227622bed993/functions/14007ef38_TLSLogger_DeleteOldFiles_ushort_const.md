# TLSLogger::DeleteOldFiles(ushort const *)

- ea: `0x14007ef38`
- end: `0x14007f07e`
- name: `?DeleteOldFiles@TLSLogger@@AEAAXPEBG@Z`
- size: `326`
- prototype: `void __fastcall(TLSLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x14007f3f0`

## callees

- `0x140004703`
- `0x140059498`
- `0x14007ed84`
- `0x14007ef38`
- `0x140111220`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x14007ef84`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14007ef84`
- `KERNEL32!FindClose` at `0x14007f056`
- `KERNEL32!FindClose` at `0x14007f056`
- `KERNEL32!FindNextFileW` at `0x14007f049`
- `KERNEL32!FindNextFileW` at `0x14007f049`
- `KERNEL32!FindFirstFileW` at `0x14007efcf`
- `KERNEL32!FindFirstFileW` at `0x14007efcf`
- `KERNEL32!DeleteFileW` at `0x14007f03b`
- `KERNEL32!DeleteFileW` at `0x14007f03b`

## pseudocode

```c
void __fastcall TLSLogger::DeleteOldFiles(TLSLogger *this, const unsigned __int16 *a2)
{
  unsigned __int64 v4; // r8
  HANDLE FirstFileW; // rbx
  int v6; // eax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)&SystemTimeAsFileTime -= 864000000000LL * *((unsigned int *)this + 3);
  if ( TLSLogger::CreateFullPath(this, FileName, v4, L"*", a2) >= 0 )
  {
    FirstFileW = FindFirstFileW(FileName, &FindFileData);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0
          && *(_QWORD *)&FindFileData.ftLastWriteTime < *(unsigned __int64 *)&SystemTimeAsFileTime )
        {
          if ( *((_WORD *)this + 20) )
            v6 = StringCbPrintfW(FileName, 0x208u, L"%s\\%s");
          else
            v6 = StringCbPrintfW(FileName, 0x208u, L"%s", FindFileData.cFileName);
          if ( v6 < 0 )
          {
LABEL_11:
            FindClose(FirstFileW);
            return;
          }
          DeleteFileW(FileName);
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          goto LABEL_11;
      }
    }
  }
}

```

## disassembly

```asm
0x14007ef38  mov     [rsp-8+arg_10], rbx
0x14007ef3d  push    rbp
0x14007ef3e  push    rsi
0x14007ef3f  push    rdi
0x14007ef40  lea     rbp, [rsp-3B0h]
0x14007ef48  sub     rsp, 4B0h
0x14007ef4f  mov     rax, cs:__security_cookie
0x14007ef56  xor     rax, rsp
0x14007ef59  mov     [rbp+3C0h+var_20], rax
0x14007ef60  mov     rbx, rdx
0x14007ef63  mov     rdi, rcx
0x14007ef66  xor     edx, edx; Val
0x14007ef68  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x14007ef6d  mov     r8d, 250h; Size
0x14007ef73  call    memset_0
0x14007ef78  xor     esi, esi
0x14007ef7a  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14007ef7f  mov     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x14007ef84  call    cs:__imp_GetSystemTimeAsFileTime
0x14007ef8a  mov     eax, [rdi+0Ch]
0x14007ef8d  lea     r9, pszMore; "*"
0x14007ef94  mov     rcx, 0C92A69C000h
0x14007ef9e  mov     [rsp+4C0h+var_4A0], rbx; unsigned __int16 *
0x14007efa3  imul    rax, rcx
0x14007efa7  lea     rdx, [rbp+3C0h+FileName]; unsigned __int16 *
0x14007efae  mov     rcx, rdi; this
0x14007efb1  sub     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x14007efb6  call    ?CreateFullPath@TLSLogger@@AEAAJPEAG_KPEBG2@Z; TLSLogger::CreateFullPath(ushort *,unsigned __int64,ushort const *,ushort const *)
0x14007efbb  test    eax, eax
0x14007efbd  js      loc_14007F05C
0x14007efc3  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x14007efc8  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x14007efcf  call    cs:__imp_FindFirstFileW
0x14007efd5  mov     rbx, rax
0x14007efd8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007efdc  jz      short loc_14007F05C
0x14007efde  test    byte ptr [rsp+4C0h+FindFileData.dwFileAttributes], 10h
0x14007efe3  jnz     short loc_14007F041
0x14007efe5  mov     rcx, qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime]
0x14007efea  cmp     qword ptr [rsp+4C0h+FindFileData.ftLastWriteTime.dwLowDateTime], rcx
0x14007efef  jnb     short loc_14007F041
0x14007eff1  lea     r9, [rdi+28h]
0x14007eff5  mov     edx, 208h; unsigned __int64
0x14007effa  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x14007f001  cmp     [r9], si
0x14007f005  jz      short loc_14007F01F
0x14007f007  lea     rax, [rsp+4C0h+FindFileData.cFileName]
0x14007f00c  lea     r8, aSS_0; "%s\\%s"
0x14007f013  mov     [rsp+4C0h+var_4A0], rax
0x14007f018  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007f01d  jmp     short loc_14007F030
0x14007f01f  lea     r9, [rsp+4C0h+FindFileData.cFileName]
0x14007f024  lea     r8, aS_3; "%s"
0x14007f02b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14007f030  test    eax, eax
0x14007f032  js      short loc_14007F053
0x14007f034  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x14007f03b  call    cs:__imp_DeleteFileW
0x14007f041  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x14007f046  mov     rcx, rbx; hFindFile
0x14007f049  call    cs:__imp_FindNextFileW
0x14007f04f  test    eax, eax
0x14007f051  jnz     short loc_14007EFDE
0x14007f053  mov     rcx, rbx; hFindFile
0x14007f056  call    cs:__imp_FindClose
0x14007f05c  mov     rcx, [rbp+3C0h+var_20]
0x14007f063  xor     rcx, rsp; StackCookie
0x14007f066  call    __security_check_cookie
0x14007f06b  mov     rbx, [rsp+4C0h+arg_10]
0x14007f073  add     rsp, 4B0h
0x14007f07a  pop     rdi
0x14007f07b  pop     rsi
0x14007f07c  pop     rbp
0x14007f07d  retn
```
