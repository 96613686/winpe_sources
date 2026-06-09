# ConfirmCopy(ushort const *,ushort const *,OPS *,HWND__ *,CFtpFolder *,CFtpDir *,ulong *,int,int *)

- ea: `0x1800121f0`
- end: `0x180012373`
- name: `?ConfirmCopy@@YAJPEBG0PEAW4OPS@@PEAUHWND__@@PEAVCFtpFolder@@PEAVCFtpDir@@PEAKHPEAH@Z`
- size: `387`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, const unsigned __int16 *@<rdx>, enum OPS *@<r8>, HWND@<r9>, struct CFtpFolder *, struct CFtpDir *, unsigned int *, int, int *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001237c`
- `0x18001357c`
- `0x1800142a0`

## callees

- `0x180002240`
- `0x180002b60`
- `0x180011218`
- `0x180011d14`
- `0x1800121f0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012273`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180012273`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800122ed`
- `api-ms-win-core-file-l1-1-0!FileTimeToLocalFileTime` at `0x1800122ed`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012288`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180012288`

## pseudocode

```c
__int64 __fastcall ConfirmCopy(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2,
        enum OPS *a3,
        HWND a4,
        struct CFtpFolder *a5,
        struct CFtpDir *a6,
        unsigned int *a7,
        int a8,
        int *a9)
{
  unsigned int v13; // ebx
  HANDLE FirstFileW; // rax
  int DataForDisplayPath; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAA v23; // [rsp+290h] [rbp+190h] BYREF

  *a9 = 1;
  if ( *(_DWORD *)a3 == 3 )
    return 1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  v13 = 0;
  if ( FirstFileW != (HANDLE)-1LL )
  {
    FindClose(FirstFileW);
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      memset_0(&v23, 0, sizeof(v23));
      DataForDisplayPath = CFtpDir::GetFindDataForDisplayPath(a6, a4, a2, &v23, a5);
      if ( *(_DWORD *)a3 != 1 && !DataForDisplayPath )
      {
        if ( *(_DWORD *)a3 != 2 )
        {
          FileTime = FindFileData.ftLastWriteTime;
          FileTimeToLocalFileTime(&FileTime, &FindFileData.ftLastWriteTime);
          v16 = FtpConfirmReplaceDialog(a4, &FindFileData, &v23, a8, a5) - 2;
          if ( !v16 )
          {
LABEL_16:
            if ( a7 )
              *a7 = 0;
            *(_DWORD *)a3 = 3;
            return (unsigned int)-2147023673;
          }
          v17 = v16 - 4;
          if ( !v17 )
            return v13;
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 25;
            if ( !v19 )
            {
              *(_DWORD *)a3 = 1;
              return v13;
            }
            if ( v19 == 1 )
            {
              *(_DWORD *)a3 = 2;
              return 1;
            }
            goto LABEL_16;
          }
        }
        return 1;
      }
    }
  }
  return v13;
}

```

## disassembly

```asm
0x1800121f0  push    rbp
0x1800121f2  push    rbx
0x1800121f3  push    rsi
0x1800121f4  push    rdi
0x1800121f5  push    r12
0x1800121f7  push    r13
0x1800121f9  push    r14
0x1800121fb  push    r15
0x1800121fd  lea     rbp, [rsp-2E8h]
0x180012205  sub     rsp, 3E8h
0x18001220c  mov     rax, cs:__security_cookie
0x180012213  xor     rax, rsp
0x180012216  mov     [rbp+320h+var_50], rax
0x18001221d  mov     rax, [rbp+320h+arg_40]
0x180012224  mov     rbx, rcx
0x180012227  mov     r15, [rbp+320h+arg_20]
0x18001222e  mov     ecx, 1
0x180012233  mov     r13, [rbp+320h+arg_28]
0x18001223a  mov     r14, r9
0x18001223d  mov     rsi, [rbp+320h+arg_30]
0x180012244  mov     rdi, r8
0x180012247  mov     [rax], ecx
0x180012249  mov     r12, rdx
0x18001224c  cmp     dword ptr [r8], 3
0x180012250  jnz     short loc_180012259
0x180012252  mov     ebx, ecx
0x180012254  jmp     loc_18001234E
0x180012259  xor     edx, edx; Val
0x18001225b  lea     rcx, [rsp+420h+FindFileData]; void *
0x180012260  mov     r8d, 250h; Size
0x180012266  call    memset_0
0x18001226b  lea     rdx, [rsp+420h+FindFileData]; lpFindFileData
0x180012270  mov     rcx, rbx; lpFileName
0x180012273  call    cs:__imp_FindFirstFileW
0x180012279  xor     ebx, ebx
0x18001227b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001227f  jz      loc_18001234E
0x180012285  mov     rcx, rax; hFindFile
0x180012288  call    cs:__imp_FindClose
0x18001228e  test    byte ptr [rsp+420h+FindFileData.dwFileAttributes], 10h
0x180012293  jnz     loc_18001234E
0x180012299  xor     edx, edx; Val
0x18001229b  lea     rcx, [rbp+320h+var_190]; void *
0x1800122a2  mov     r8d, 140h; Size
0x1800122a8  call    memset_0
0x1800122ad  lea     r9, [rbp+320h+var_190]; struct _WIN32_FIND_DATAA *
0x1800122b4  mov     [rsp+420h+var_400], r15; struct CFtpFolder *
0x1800122b9  mov     r8, r12; unsigned __int16 *
0x1800122bc  mov     rdx, r14; HWND
0x1800122bf  mov     rcx, r13; this
0x1800122c2  call    ?GetFindDataForDisplayPath@CFtpDir@@QEAAJPEAUHWND__@@PEBGPEAU_WIN32_FIND_DATAA@@PEAVCFtpFolder@@@Z; CFtpDir::GetFindDataForDisplayPath(HWND__ *,ushort const *,_WIN32_FIND_DATAA *,CFtpFolder *)
0x1800122c7  lea     r12d, [rbx+1]
0x1800122cb  cmp     [rdi], r12d
0x1800122ce  jz      short loc_18001234E
0x1800122d0  test    eax, eax
0x1800122d2  jnz     short loc_18001234E
0x1800122d4  cmp     dword ptr [rdi], 2
0x1800122d7  jz      short loc_180012332
0x1800122d9  mov     rax, qword ptr [rsp+420h+FindFileData.ftLastWriteTime.dwLowDateTime]
0x1800122de  lea     rdx, [rsp+420h+FindFileData.ftLastWriteTime]; lpLocalFileTime
0x1800122e3  lea     rcx, [rsp+420h+FileTime]; lpFileTime
0x1800122e8  mov     qword ptr [rsp+420h+FileTime.dwLowDateTime], rax
0x1800122ed  call    cs:__imp_FileTimeToLocalFileTime
0x1800122f3  mov     r9d, [rbp+320h+arg_38]; int
0x1800122fa  lea     r8, [rbp+320h+var_190]; struct _WIN32_FIND_DATAA *
0x180012301  lea     rdx, [rsp+420h+FindFileData]; struct _WIN32_FIND_DATAW *
0x180012306  mov     [rsp+420h+var_400], r15; struct CFtpFolder *
0x18001230b  mov     rcx, r14; HWND
0x18001230e  call    ?FtpConfirmReplaceDialog@@YAIPEAUHWND__@@PEBU_WIN32_FIND_DATAW@@PEAU_WIN32_FIND_DATAA@@HPEAVCFtpFolder@@@Z; FtpConfirmReplaceDialog(HWND__ *,_WIN32_FIND_DATAW const *,_WIN32_FIND_DATAA *,int,CFtpFolder *)
0x180012313  sub     eax, 2
0x180012316  jz      short loc_18001233C
0x180012318  sub     eax, 4
0x18001231b  jz      short loc_18001234E
0x18001231d  sub     eax, r12d
0x180012320  jz      short loc_180012332
0x180012322  sub     eax, 19h
0x180012325  jz      short loc_180012337
0x180012327  cmp     eax, r12d
0x18001232a  jnz     short loc_18001233C
0x18001232c  mov     dword ptr [rdi], 2
0x180012332  mov     ebx, r12d
0x180012335  jmp     short loc_18001234E
0x180012337  mov     [rdi], r12d
0x18001233a  jmp     short loc_18001234E
0x18001233c  test    rsi, rsi
0x18001233f  jz      short loc_180012343
0x180012341  mov     [rsi], ebx
0x180012343  mov     dword ptr [rdi], 3
0x180012349  mov     ebx, 800704C7h
0x18001234e  mov     eax, ebx
0x180012350  mov     rcx, [rbp+320h+var_50]
0x180012357  xor     rcx, rsp; StackCookie
0x18001235a  call    __security_check_cookie
0x18001235f  add     rsp, 3E8h
0x180012366  pop     r15
0x180012368  pop     r14
0x18001236a  pop     r13
0x18001236c  pop     r12
0x18001236e  pop     rdi
0x18001236f  pop     rsi
0x180012370  pop     rbx
0x180012371  pop     rbp
0x180012372  retn
```
