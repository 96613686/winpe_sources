# TLSLogger::DeleteOldFiles(ushort const *)

- ea: `0x1400810a8`
- end: `0x1400811ee`
- name: `?DeleteOldFiles@TLSLogger@@AEAAXPEBG@Z`
- size: `326`
- prototype: `void __fastcall(TLSLogger *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140081560`

## callees

- `0x140004703`
- `0x14005b608`
- `0x140080ef4`
- `0x1400810a8`
- `0x140113390`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400810f4`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400810f4`
- `KERNEL32!FindClose` at `0x1400811c6`
- `KERNEL32!FindClose` at `0x1400811c6`
- `KERNEL32!FindNextFileW` at `0x1400811b9`
- `KERNEL32!FindNextFileW` at `0x1400811b9`
- `KERNEL32!FindFirstFileW` at `0x14008113f`
- `KERNEL32!FindFirstFileW` at `0x14008113f`
- `KERNEL32!DeleteFileW` at `0x1400811ab`
- `KERNEL32!DeleteFileW` at `0x1400811ab`

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
0x1400810a8  mov     [rsp-8+arg_10], rbx
0x1400810ad  push    rbp
0x1400810ae  push    rsi
0x1400810af  push    rdi
0x1400810b0  lea     rbp, [rsp-3B0h]
0x1400810b8  sub     rsp, 4B0h
0x1400810bf  mov     rax, cs:__security_cookie
0x1400810c6  xor     rax, rsp
0x1400810c9  mov     [rbp+3C0h+var_20], rax
0x1400810d0  mov     rbx, rdx
0x1400810d3  mov     rdi, rcx
0x1400810d6  xor     edx, edx; Val
0x1400810d8  lea     rcx, [rsp+4C0h+FindFileData]; void *
0x1400810dd  mov     r8d, 250h; Size
0x1400810e3  call    memset_0
0x1400810e8  xor     esi, esi
0x1400810ea  lea     rcx, [rsp+4C0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400810ef  mov     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x1400810f4  call    cs:__imp_GetSystemTimeAsFileTime
0x1400810fa  mov     eax, [rdi+0Ch]
0x1400810fd  lea     r9, pszMore; "*"
0x140081104  mov     rcx, 0C92A69C000h
0x14008110e  mov     [rsp+4C0h+var_4A0], rbx; unsigned __int16 *
0x140081113  imul    rax, rcx
0x140081117  lea     rdx, [rbp+3C0h+FileName]; unsigned __int16 *
0x14008111e  mov     rcx, rdi; this
0x140081121  sub     qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x140081126  call    ?CreateFullPath@TLSLogger@@AEAAJPEAG_KPEBG2@Z; TLSLogger::CreateFullPath(ushort *,unsigned __int64,ushort const *,ushort const *)
0x14008112b  test    eax, eax
0x14008112d  js      loc_1400811CC
0x140081133  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x140081138  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x14008113f  call    cs:__imp_FindFirstFileW
0x140081145  mov     rbx, rax
0x140081148  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14008114c  jz      short loc_1400811CC
0x14008114e  test    byte ptr [rsp+4C0h+FindFileData.dwFileAttributes], 10h
0x140081153  jnz     short loc_1400811B1
0x140081155  mov     rcx, qword ptr [rsp+4C0h+SystemTimeAsFileTime.dwLowDateTime]
0x14008115a  cmp     qword ptr [rsp+4C0h+FindFileData.ftLastWriteTime.dwLowDateTime], rcx
0x14008115f  jnb     short loc_1400811B1
0x140081161  lea     r9, [rdi+28h]
0x140081165  mov     edx, 208h; unsigned __int64
0x14008116a  lea     rcx, [rbp+3C0h+FileName]; unsigned __int16 *
0x140081171  cmp     [r9], si
0x140081175  jz      short loc_14008118F
0x140081177  lea     rax, [rsp+4C0h+FindFileData.cFileName]
0x14008117c  lea     r8, aSS_0; "%s\\%s"
0x140081183  mov     [rsp+4C0h+var_4A0], rax
0x140081188  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14008118d  jmp     short loc_1400811A0
0x14008118f  lea     r9, [rsp+4C0h+FindFileData.cFileName]
0x140081194  lea     r8, aS_3; "%s"
0x14008119b  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400811a0  test    eax, eax
0x1400811a2  js      short loc_1400811C3
0x1400811a4  lea     rcx, [rbp+3C0h+FileName]; lpFileName
0x1400811ab  call    cs:__imp_DeleteFileW
0x1400811b1  lea     rdx, [rsp+4C0h+FindFileData]; lpFindFileData
0x1400811b6  mov     rcx, rbx; hFindFile
0x1400811b9  call    cs:__imp_FindNextFileW
0x1400811bf  test    eax, eax
0x1400811c1  jnz     short loc_14008114E
0x1400811c3  mov     rcx, rbx; hFindFile
0x1400811c6  call    cs:__imp_FindClose
0x1400811cc  mov     rcx, [rbp+3C0h+var_20]
0x1400811d3  xor     rcx, rsp; StackCookie
0x1400811d6  call    __security_check_cookie
0x1400811db  mov     rbx, [rsp+4C0h+arg_10]
0x1400811e3  add     rsp, 4B0h
0x1400811ea  pop     rdi
0x1400811eb  pop     rsi
0x1400811ec  pop     rbp
0x1400811ed  retn
```
