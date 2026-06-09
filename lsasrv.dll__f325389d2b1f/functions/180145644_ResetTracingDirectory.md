# ResetTracingDirectory

- ea: `0x180145644`
- end: `0x180145925`
- name: `ResetTracingDirectory`
- size: `737`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180144fb8`

## callees

- `0x1800b86d0`
- `0x1800b9304`
- `0x180144d78`
- `0x18014526c`
- `0x180145644`
- `0x180145964`
- `0x1801459b4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801458c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801458ec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801458c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801458ec`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014581b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014589c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014581b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18014589c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18014574e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801458d8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18014574e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801458d8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18014570e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileExW` at `0x18014570e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18014588c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x18014588c`

## pseudocode

```c
__int64 __fastcall ResetTracingDirectory(__int64 a1, __int64 a2, unsigned int *a3)
{
  unsigned int *v3; // r12
  __int64 v5; // r15
  unsigned int v6; // eax
  WCHAR *v7; // r14
  unsigned int v8; // ebx
  __int64 v9; // rdi
  int v10; // r13d
  unsigned int v11; // esi
  int v12; // edx
  int v13; // ecx
  unsigned int v14; // ebx
  unsigned int v15; // r14d
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  int v18; // [rsp+34h] [rbp-CCh] BYREF
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  __int64 FirstFile; // [rsp+50h] [rbp-B0h]
  __int64 v22; // [rsp+58h] [rbp-A8h]
  __int64 v23; // [rsp+60h] [rbp-A0h]
  unsigned int *v24; // [rsp+68h] [rbp-98h]
  _BYTE FindFileData[44]; // [rsp+70h] [rbp-90h] BYREF
  char v26[548]; // [rsp+9Ch] [rbp-64h] BYREF
  WCHAR FileName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v28[528]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v3 = a3;
  v24 = a3;
  v22 = a2;
  v5 = a1;
  v23 = a1;
  v17 = 0;
  v18 = 0;
  lpFileName = 0;
  hMem = 0;
  memset_0(FindFileData, 0, 0x250u);
  if ( v3 )
    *v3 = 0;
  v6 = BuildCurrentLogFilePath(v5, a2, &lpFileName);
  v7 = (WCHAR *)lpFileName;
  v8 = v6;
  if ( v6 )
  {
    FirstFile = (__int64)FindFirstFileExW(lpFileName, FindExInfoBasic, FindFileData, FindExSearchNameMatch, 0, 0);
    v9 = FirstFile;
    if ( FirstFile == -1 )
    {
      v10 = 0;
    }
    else
    {
      if ( (int)RtlStringCchCopyW(v28, 260, v26) < 0 )
      {
        v8 = 0;
LABEL_29:
        FindClose((HANDLE)v9);
        goto LABEL_30;
      }
      v10 = 1;
      FindClose((HANDLE)v9);
      v9 = -1;
      FirstFile = -1;
    }
    v8 = QueryAndSortOldLogFiles(
           v5,
           a2,
           (unsigned __int64)v28 & -(__int64)(v10 != 0),
           (unsigned int)&v18,
           (__int64)&v17,
           (__int64)&hMem);
    if ( v8 )
    {
      v11 = v17;
      v12 = *(_DWORD *)(v5 + 36);
      v13 = *(_DWORD *)(v5 + 40);
      if ( v10 && v13 )
        --v13;
      if ( v17 > v13 + v12 )
      {
        v17 = 0;
        v14 = v11 - v13 - v12;
        if ( v11 - v13 != v12 )
        {
          v15 = v17;
          do
          {
            if ( (int)RtlStringCchPrintfW(FileName) >= 0 )
            {
              DeleteFileW(FileName);
              --v11;
            }
            ++v15;
          }
          while ( v15 < v14 );
          v9 = FirstFile;
          v7 = (WCHAR *)lpFileName;
          v5 = v23;
          v3 = v24;
        }
      }
      if ( v10 && (int)RtlStringCchPrintfW(FileName) >= 0 )
      {
        if ( *(_DWORD *)(v5 + 40) )
        {
          MoveFileW(v7, FileName);
          ++v11;
        }
        else
        {
          DeleteFileW(v7);
        }
      }
      v8 = 1;
      if ( v3 )
        *v3 = v11;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      if ( v9 != -1 )
        goto LABEL_29;
    }
  }
LABEL_30:
  if ( v7 )
    LocalFree(v7);
  return v8;
}

```

## disassembly

```asm
0x180145644  mov     [rsp-8+arg_18], rbx
0x180145649  push    rbp
0x18014564a  push    rsi
0x18014564b  push    rdi
0x18014564c  push    r12
0x18014564e  push    r13
0x180145650  push    r14
0x180145652  push    r15
0x180145654  lea     rbp, [rsp-5F0h]
0x18014565c  sub     rsp, 6F0h
0x180145663  mov     rax, cs:__security_cookie
0x18014566a  xor     rax, rsp
0x18014566d  mov     [rbp+620h+var_40], rax
0x180145674  mov     r12, r8
0x180145677  mov     [rsp+720h+var_6B8], r8
0x18014567c  mov     rsi, rdx
0x18014567f  mov     [rsp+720h+var_6C8], rdx
0x180145684  mov     r15, rcx
0x180145687  mov     [rsp+720h+var_6C0], rcx
0x18014568c  xor     edx, edx; Val
0x18014568e  mov     [rsp+720h+var_6F0], 0
0x180145696  mov     r8d, 250h; Size
0x18014569c  mov     [rsp+720h+var_6EC], 0
0x1801456a4  lea     rcx, [rsp+720h+FindFileData]; void *
0x1801456a9  mov     [rsp+720h+lpFileName], 0
0x1801456b2  mov     [rsp+720h+hMem], 0
0x1801456bb  call    memset_0
0x1801456c0  test    r12, r12
0x1801456c3  jz      short loc_1801456CD
0x1801456c5  mov     dword ptr [r12], 0
0x1801456cd  lea     r8, [rsp+720h+lpFileName]
0x1801456d2  mov     rdx, rsi
0x1801456d5  mov     rcx, r15
0x1801456d8  call    BuildCurrentLogFilePath
0x1801456dd  mov     r14, [rsp+720h+lpFileName]
0x1801456e2  mov     ebx, eax
0x1801456e4  test    eax, eax
0x1801456e6  jz      loc_1801458E4
0x1801456ec  xor     r9d, r9d; fSearchOp
0x1801456ef  mov     [rsp+720h+dwAdditionalFlags], 0; dwAdditionalFlags
0x1801456f7  lea     r8, [rsp+720h+FindFileData]; lpFindFileData
0x1801456fc  mov     [rsp+720h+lpSearchFilter], 0; lpSearchFilter
0x180145705  mov     rcx, r14; lpFileName
0x180145708  lea     ebx, [r9+1]
0x18014570c  mov     edx, ebx; fInfoLevelId
0x18014570e  call    cs:__imp_FindFirstFileExW
0x180145715  nop     dword ptr [rax+rax+00h]
0x18014571a  mov     [rsp+720h+var_6D0], rax
0x18014571f  mov     rdi, rax
0x180145722  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180145726  jz      short loc_180145765
0x180145728  lea     r8, [rbp+620h+var_684]
0x18014572c  mov     edx, 104h
0x180145731  lea     rcx, [rbp+620h+var_250]
0x180145738  call    RtlStringCchCopyW
0x18014573d  test    eax, eax
0x18014573f  jns     short loc_180145748
0x180145741  xor     ebx, ebx
0x180145743  jmp     loc_1801458D5
0x180145748  mov     rcx, rdi; hFindFile
0x18014574b  mov     r13d, ebx
0x18014574e  call    cs:__imp_FindClose
0x180145755  nop     dword ptr [rax+rax+00h]
0x18014575a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18014575e  mov     [rsp+720h+var_6D0], rdi
0x180145763  jmp     short loc_180145768
0x180145765  xor     r13d, r13d
0x180145768  mov     eax, r13d
0x18014576b  lea     r9, [rsp+720h+var_6EC]
0x180145770  neg     eax
0x180145772  mov     rdx, rsi
0x180145775  lea     rax, [rbp+620h+var_250]
0x18014577c  mov     rcx, r15
0x18014577f  sbb     r8, r8
0x180145782  and     r8, rax
0x180145785  lea     rax, [rsp+720h+hMem]
0x18014578a  mov     qword ptr [rsp+720h+dwAdditionalFlags], rax
0x18014578f  lea     rax, [rsp+720h+var_6F0]
0x180145794  mov     [rsp+720h+lpSearchFilter], rax
0x180145799  call    QueryAndSortOldLogFiles
0x18014579e  mov     ebx, eax
0x1801457a0  test    eax, eax
0x1801457a2  jz      loc_1801458B6
0x1801457a8  mov     esi, [rsp+720h+var_6F0]
0x1801457ac  mov     edx, [r15+24h]
0x1801457b0  mov     ecx, [r15+28h]
0x1801457b4  test    r13d, r13d
0x1801457b7  jz      short loc_1801457BF
0x1801457b9  test    ecx, ecx
0x1801457bb  jz      short loc_1801457BF
0x1801457bd  dec     ecx
0x1801457bf  lea     eax, [rcx+rdx]
0x1801457c2  cmp     esi, eax
0x1801457c4  jbe     short loc_180145845
0x1801457c6  mov     ebx, esi
0x1801457c8  mov     [rsp+720h+var_6F0], 0
0x1801457d0  sub     ebx, ecx
0x1801457d2  sub     ebx, edx
0x1801457d4  jz      short loc_180145845
0x1801457d6  mov     r14d, [rsp+720h+var_6F0]
0x1801457db  mov     r12d, edx
0x1801457de  mov     r15, [rsp+720h+hMem]
0x1801457e3  mov     rdi, [rsp+720h+var_6C8]
0x1801457e8  lea     eax, [r12+r14]
0x1801457ec  mov     r9, rdi
0x1801457ef  mov     rax, [r15+rax*8]
0x1801457f3  lea     r8, aSS_1; "%s\\%s"
0x1801457fa  mov     edx, 104h
0x1801457ff  mov     [rsp+720h+lpSearchFilter], rax
0x180145804  lea     rcx, [rbp+620h+FileName]; Buffer
0x18014580b  call    RtlStringCchPrintfW
0x180145810  test    eax, eax
0x180145812  js      short loc_180145829
0x180145814  lea     rcx, [rbp+620h+FileName]; lpFileName
0x18014581b  call    cs:__imp_DeleteFileW
0x180145822  nop     dword ptr [rax+rax+00h]
0x180145827  dec     esi
0x180145829  inc     r14d
0x18014582c  cmp     r14d, ebx
0x18014582f  jb      short loc_1801457E8
0x180145831  mov     rdi, [rsp+720h+var_6D0]
0x180145836  mov     r14, [rsp+720h+lpFileName]
0x18014583b  mov     r15, [rsp+720h+var_6C0]
0x180145840  mov     r12, [rsp+720h+var_6B8]
0x180145845  test    r13d, r13d
0x180145848  jz      short loc_1801458A8
0x18014584a  mov     eax, [rsp+720h+var_6EC]
0x18014584e  lea     r8, aSS08xEtl; "%s\\%s%08x.etl"
0x180145855  mov     r9, [rsp+720h+var_6C8]
0x18014585a  lea     rcx, [rbp+620h+FileName]; Buffer
0x180145861  mov     [rsp+720h+dwAdditionalFlags], eax
0x180145865  mov     edx, 104h
0x18014586a  mov     rax, [r15]
0x18014586d  mov     [rsp+720h+lpSearchFilter], rax
0x180145872  call    RtlStringCchPrintfW
0x180145877  test    eax, eax
0x180145879  js      short loc_1801458A8
0x18014587b  cmp     dword ptr [r15+28h], 0
0x180145880  mov     rcx, r14; lpFileName
0x180145883  jbe     short loc_18014589C
0x180145885  lea     rdx, [rbp+620h+FileName]; lpNewFileName
0x18014588c  call    cs:__imp_MoveFileW
0x180145893  nop     dword ptr [rax+rax+00h]
0x180145898  inc     esi
0x18014589a  jmp     short loc_1801458A8
0x18014589c  call    cs:__imp_DeleteFileW
0x1801458a3  nop     dword ptr [rax+rax+00h]
0x1801458a8  mov     ebx, 1
0x1801458ad  test    r12, r12
0x1801458b0  jz      short loc_1801458B6
0x1801458b2  mov     [r12], esi
0x1801458b6  mov     rax, [rsp+720h+hMem]
0x1801458bb  test    rax, rax
0x1801458be  jz      short loc_1801458E4
0x1801458c0  mov     rcx, rax; hMem
0x1801458c3  call    cs:__imp_LocalFree
0x1801458ca  nop     dword ptr [rax+rax+00h]
0x1801458cf  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1801458d3  jz      short loc_1801458E4
0x1801458d5  mov     rcx, rdi; hFindFile
0x1801458d8  call    cs:__imp_FindClose
0x1801458df  nop     dword ptr [rax+rax+00h]
0x1801458e4  test    r14, r14
0x1801458e7  jz      short loc_1801458F8
0x1801458e9  mov     rcx, r14; hMem
0x1801458ec  call    cs:__imp_LocalFree
0x1801458f3  nop     dword ptr [rax+rax+00h]
0x1801458f8  mov     eax, ebx
0x1801458fa  mov     rcx, [rbp+620h+var_40]
0x180145901  xor     rcx, rsp; StackCookie
0x180145904  call    __security_check_cookie
0x180145909  mov     rbx, [rsp+720h+arg_18]
0x180145911  add     rsp, 6F0h
0x180145918  pop     r15
0x18014591a  pop     r14
0x18014591c  pop     r13
0x18014591e  pop     r12
0x180145920  pop     rdi
0x180145921  pop     rsi
0x180145922  pop     rbp
0x180145923  retn
```
