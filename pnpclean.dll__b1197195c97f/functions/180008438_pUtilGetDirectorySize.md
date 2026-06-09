# pUtilGetDirectorySize

- ea: `0x180008438`
- end: `0x180008620`
- name: `pUtilGetDirectorySize`
- size: `488`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007680`
- `0x180007c00`
- `0x180008438`

## callees

- `0x1800083ac`
- `0x180008438`
- `0x180008dfe`
- `0x180008e30`

## import_xrefs

- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800084af`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800085dc`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800084af`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x1800085dc`
- `KERNEL32!FindClose` at `0x1800085ee`
- `KERNEL32!FindClose` at `0x1800085ee`
- `KERNEL32!FindNextFileW` at `0x1800085bf`
- `KERNEL32!FindNextFileW` at `0x1800085bf`
- `KERNEL32!FindFirstFileW` at `0x1800084c8`
- `KERNEL32!FindFirstFileW` at `0x1800084c8`
- `KERNEL32!GetLastError` at `0x1800084d7`
- `KERNEL32!GetLastError` at `0x1800084d7`

## pseudocode

```c
__int64 __fastcall pUtilGetDirectorySize(__int64 a1, unsigned int a2, unsigned __int64 *a3)
{
  __int64 v4; // r14
  NTSTATUS v6; // eax
  ULONG DirectorySize; // ebx
  HANDLE FirstFileW; // rsi
  unsigned __int64 v10; // rdi
  int v11; // eax
  unsigned __int64 v12; // rcx
  __int64 v13; // rax
  unsigned __int64 v14; // rdx
  NTSTATUS v15; // ecx
  unsigned __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+290h] [rbp+190h] BYREF

  v4 = a2;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v17 = 0;
  *a3 = 0;
  v6 = RtlStringCchPrintfW(FileName, 260, L"%s\\*", a1);
  if ( v6 < 0 )
    return RtlNtStatusToDosErrorNoTeb(v6);
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
    return GetLastError();
  DirectorySize = 0;
  v10 = 0;
  while ( (FindFileData.dwFileAttributes & 0x400) != 0 )
  {
LABEL_21:
    if ( !FindNextFileW(FirstFileW, &FindFileData) )
      goto LABEL_27;
  }
  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
  {
    if ( FindFileData.cFileName[0] == 46
      && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
    {
      goto LABEL_21;
    }
    v11 = RtlStringCchPrintfW(FileName, 260, L"%s\\%s\\", a1, FindFileData.cFileName);
    if ( v11 < 0 )
    {
      v15 = v11;
      goto LABEL_26;
    }
    DirectorySize = pUtilGetDirectorySize(FileName, (unsigned int)v4, &v17);
    if ( DirectorySize )
      goto LABEL_28;
    v12 = v17;
  }
  else
  {
    v12 = FindFileData.nFileSizeLow | ((unsigned __int64)FindFileData.nFileSizeHigh << 32);
    v17 = v12;
    if ( (_DWORD)v4 )
    {
      v13 = -(int)v4;
      v14 = v13 & (v12 + v4 - 1);
      if ( v14 < v12 )
        goto LABEL_25;
      v12 = v13 & (v12 + v4 - 1);
      v17 = v14;
    }
  }
  if ( v12 + v10 >= v10 )
  {
    v10 += v12;
    goto LABEL_21;
  }
  v10 = -1;
LABEL_25:
  v15 = -1073741675;
LABEL_26:
  DirectorySize = RtlNtStatusToDosErrorNoTeb(v15);
  if ( DirectorySize )
    goto LABEL_28;
LABEL_27:
  *a3 = v10;
LABEL_28:
  FindClose(FirstFileW);
  return DirectorySize;
}

```

## disassembly

```asm
0x180008438  mov     [rsp-8+arg_18], rbx
0x18000843d  push    rbp
0x18000843e  push    rsi
0x18000843f  push    rdi
0x180008440  push    r12
0x180008442  push    r13
0x180008444  push    r14
0x180008446  push    r15
0x180008448  lea     rbp, [rsp-3B0h]
0x180008450  sub     rsp, 4B0h
0x180008457  mov     rax, cs:__security_cookie
0x18000845e  xor     rax, rsp
0x180008461  mov     [rbp+3E0h+var_40], rax
0x180008468  mov     r15, r8
0x18000846b  mov     r14d, edx
0x18000846e  mov     r12, rcx
0x180008471  xor     edx, edx; Val
0x180008473  mov     r8d, 250h; Size
0x180008479  lea     rcx, [rsp+4E0h+FindFileData]; void *
0x18000847e  call    memset_0
0x180008483  xor     r13d, r13d
0x180008486  lea     r8, aS; "%s\\*"
0x18000848d  mov     r9, r12
0x180008490  mov     [rsp+4E0h+var_4B0], r13
0x180008495  mov     edx, 104h
0x18000849a  mov     [r15], r13
0x18000849d  lea     rcx, [rbp+3E0h+FileName]
0x1800084a4  call    RtlStringCchPrintfW
0x1800084a9  test    eax, eax
0x1800084ab  jns     short loc_1800084BC
0x1800084ad  mov     ecx, eax; Status
0x1800084af  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800084b5  mov     ebx, eax
0x1800084b7  jmp     loc_1800085F4
0x1800084bc  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x1800084c1  lea     rcx, [rbp+3E0h+FileName]; lpFileName
0x1800084c8  call    cs:__imp_FindFirstFileW
0x1800084ce  mov     rsi, rax
0x1800084d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800084d5  jnz     short loc_1800084DF
0x1800084d7  call    cs:__imp_GetLastError
0x1800084dd  jmp     short loc_1800084B5
0x1800084df  mov     ebx, r13d
0x1800084e2  mov     rdi, r13
0x1800084e5  test    [rsp+4E0h+FindFileData.dwFileAttributes], 400h
0x1800084ed  jnz     loc_1800085B7
0x1800084f3  test    byte ptr [rsp+4E0h+FindFileData.dwFileAttributes], 10h
0x1800084f8  jz      short loc_180008574
0x1800084fa  cmp     [rsp+4E0h+FindFileData.cFileName], 2Eh ; '.'
0x180008500  movzx   eax, [rsp+4E0h+FindFileData.cFileName+2]
0x180008505  jnz     short loc_18000852A
0x180008507  test    ax, ax
0x18000850a  jz      loc_1800085B7
0x180008510  cmp     [rsp+4E0h+FindFileData.cFileName], 2Eh ; '.'
0x180008516  jnz     short loc_18000852A
0x180008518  cmp     ax, 2Eh ; '.'
0x18000851c  jnz     short loc_18000852A
0x18000851e  cmp     [rsp+4E0h+FindFileData.cFileName+4], r13w
0x180008524  jz      loc_1800085B7
0x18000852a  lea     rax, [rsp+4E0h+FindFileData.cFileName]
0x18000852f  mov     r9, r12
0x180008532  lea     r8, aSS; "%s\\%s\\"
0x180008539  mov     [rsp+4E0h+var_4C0], rax
0x18000853e  mov     edx, 104h
0x180008543  lea     rcx, [rbp+3E0h+FileName]
0x18000854a  call    RtlStringCchPrintfW
0x18000854f  test    eax, eax
0x180008551  js      short loc_1800085CF
0x180008553  lea     r8, [rsp+4E0h+var_4B0]
0x180008558  mov     edx, r14d
0x18000855b  lea     rcx, [rbp+3E0h+FileName]
0x180008562  call    pUtilGetDirectorySize
0x180008567  mov     ebx, eax
0x180008569  test    eax, eax
0x18000856b  jnz     short loc_1800085EB
0x18000856d  mov     rcx, [rsp+4E0h+var_4B0]
0x180008572  jmp     short loc_1800085AB
0x180008574  mov     ecx, [rsp+4E0h+FindFileData.nFileSizeHigh]
0x180008578  mov     eax, [rsp+4E0h+FindFileData.nFileSizeLow]
0x18000857c  shl     rcx, 20h
0x180008580  or      rcx, rax
0x180008583  mov     [rsp+4E0h+var_4B0], rcx
0x180008588  test    r14d, r14d
0x18000858b  jz      short loc_1800085AB
0x18000858d  mov     eax, r14d
0x180008590  lea     rdx, [r14-1]
0x180008594  neg     eax
0x180008596  add     rdx, rcx
0x180008599  cdqe
0x18000859b  and     rdx, rax
0x18000859e  cmp     rdx, rcx
0x1800085a1  jb      short loc_1800085D7
0x1800085a3  mov     rcx, rdx
0x1800085a6  mov     [rsp+4E0h+var_4B0], rdx
0x1800085ab  lea     rax, [rcx+rdi]
0x1800085af  cmp     rax, rdi
0x1800085b2  jb      short loc_1800085D3
0x1800085b4  mov     rdi, rax
0x1800085b7  lea     rdx, [rsp+4E0h+FindFileData]; lpFindFileData
0x1800085bc  mov     rcx, rsi; hFindFile
0x1800085bf  call    cs:__imp_FindNextFileW
0x1800085c5  test    eax, eax
0x1800085c7  jnz     loc_1800084E5
0x1800085cd  jmp     short loc_1800085E8
0x1800085cf  mov     ecx, eax
0x1800085d1  jmp     short loc_1800085DC
0x1800085d3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800085d7  mov     ecx, 0C0000095h; Status
0x1800085dc  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x1800085e2  mov     ebx, eax
0x1800085e4  test    eax, eax
0x1800085e6  jnz     short loc_1800085EB
0x1800085e8  mov     [r15], rdi
0x1800085eb  mov     rcx, rsi; hFindFile
0x1800085ee  call    cs:__imp_FindClose
0x1800085f4  mov     eax, ebx
0x1800085f6  mov     rcx, [rbp+3E0h+var_40]
0x1800085fd  xor     rcx, rsp; StackCookie
0x180008600  call    __security_check_cookie
0x180008605  mov     rbx, [rsp+4E0h+arg_18]
0x18000860d  add     rsp, 4B0h
0x180008614  pop     r15
0x180008616  pop     r14
0x180008618  pop     r13
0x18000861a  pop     r12
0x18000861c  pop     rdi
0x18000861d  pop     rsi
0x18000861e  pop     rbp
0x18000861f  retn
```
