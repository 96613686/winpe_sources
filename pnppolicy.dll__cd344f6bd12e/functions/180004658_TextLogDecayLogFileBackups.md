# TextLogDecayLogFileBackups

- ea: `0x180004658`
- end: `0x180004cad`
- name: `TextLogDecayLogFileBackups`
- size: `1621`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update`

## callers

- `0x1800063bc`

## callees

- `0x1800034e8`
- `0x180004560`
- `0x180004658`
- `0x180006e28`
- `0x180006fb0`
- `0x18000a162`
- `0x18000a16e`
- `0x18000a1a0`

## import_xrefs

- `msvcrt!wcsrchr` at `0x180004896`
- `msvcrt!wcsrchr` at `0x180004896`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004c7d`
- `KERNEL32!HeapFree` at `0x180004bb4`
- `KERNEL32!HeapFree` at `0x180004c22`
- `KERNEL32!HeapFree` at `0x180004c3d`
- `KERNEL32!HeapFree` at `0x180004c61`
- `KERNEL32!HeapFree` at `0x180004bb4`
- `KERNEL32!HeapFree` at `0x180004c22`
- `KERNEL32!HeapFree` at `0x180004c3d`
- `KERNEL32!HeapFree` at `0x180004c61`
- `KERNEL32!HeapAlloc` at `0x18000490e`
- `KERNEL32!HeapAlloc` at `0x180004b04`
- `KERNEL32!HeapAlloc` at `0x18000490e`
- `KERNEL32!HeapAlloc` at `0x180004b04`
- `KERNEL32!FindClose` at `0x180004c75`
- `KERNEL32!FindClose` at `0x180004c75`
- `KERNEL32!FindNextFileW` at `0x180004bcf`
- `KERNEL32!FindNextFileW` at `0x180004bcf`
- `KERNEL32!SetFileAttributesW` at `0x180004b8c`
- `KERNEL32!SetFileAttributesW` at `0x180004b8c`
- `KERNEL32!LCMapStringW` at `0x180004a51`
- `KERNEL32!LCMapStringW` at `0x180004a51`
- `KERNEL32!FindFirstFileW` at `0x1800048e0`
- `KERNEL32!FindFirstFileW` at `0x1800048e0`
- `KERNEL32!DeleteFileW` at `0x180004b95`
- `KERNEL32!DeleteFileW` at `0x180004b95`

## pseudocode

```c
__int64 __fastcall TextLogDecayLogFileBackups(wchar_t *a1)
{
  unsigned int v2; // ebx
  DWORD v3; // edi
  _QWORD *v4; // r12
  WCHAR *v5; // rsi
  __int64 v6; // r8
  wchar_t *v7; // r9
  __int64 v8; // rdx
  _WORD *v9; // rax
  int v10; // r11d
  __int64 v11; // rcx
  _WORD *FileTitle; // r8
  char *v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  wchar_t *v16; // rax
  int v17; // r10d
  __int64 v18; // rcx
  wchar_t *v19; // rax
  _QWORD *v20; // rax
  __int64 v21; // r8
  WCHAR *v22; // r9
  __int64 v23; // rdx
  WCHAR *v24; // rax
  int v25; // r11d
  __int64 v26; // rcx
  __int64 v27; // rax
  unsigned int v28; // r13d
  unsigned int i; // r14d
  __int64 v30; // r15
  bool v31; // cc
  char *v32; // rax
  char *v33; // r8
  int v34; // ecx
  int v35; // edx
  int v36; // r8d
  wchar_t *v37; // rax
  __int64 j; // r14
  void *v39; // r8
  unsigned int v41; // [rsp+34h] [rbp-B84h]
  __int64 hFindFile; // [rsp+48h] [rbp-B70h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-AD8h] BYREF
  wchar_t SrcStr[264]; // [rsp+330h] [rbp-888h] BYREF
  _WORD v45[264]; // [rsp+540h] [rbp-678h] BYREF
  wchar_t Str[264]; // [rsp+750h] [rbp-468h] BYREF
  wchar_t pszDest[264]; // [rsp+960h] [rbp-258h] BYREF

  v2 = 0;
  v3 = 0;
  hFindFile = -1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  v41 = 0;
  v5 = 0;
  v6 = 2147483646;
  v7 = a1;
  v8 = 260;
  v9 = v45;
  v10 = 0;
  v11 = 0;
  while ( v8 )
  {
    if ( !v6 || !*v7 )
      goto LABEL_8;
    *v9++ = *v7++;
    --v8;
    --v6;
    ++v11;
  }
  --v9;
  v10 = -2147024774;
LABEL_8:
  *v9 = 0;
  if ( v10 >= 0 )
  {
    FileTitle = (_WORD *)pSetupGetFileTitle(v45);
    if ( FileTitle != v45 )
    {
      v13 = (char *)(FileTitle - 1);
      if ( *(FileTitle - 1) == 92 || *(_WORD *)v13 == 47 )
      {
        if ( v13 - (char *)v45 == 4 && v45[0] && v45[1] == 58 )
          *FileTitle = 0;
        else
          *(_WORD *)v13 = 0;
        v14 = 2147483646;
        v15 = 260;
        v16 = Str;
        v17 = 0;
        v18 = 0;
        while ( v15 )
        {
          if ( !v14 || !*a1 )
            goto LABEL_24;
          *v16++ = *a1++;
          --v15;
          --v14;
          ++v18;
        }
        --v16;
        v17 = -2147024774;
LABEL_24:
        *v16 = 0;
        if ( v17 >= 0 )
        {
          v19 = wcsrchr(Str, 0x2Eu);
          if ( v19 )
          {
            *v19 = 0;
            if ( StringCchPrintfW(pszDest, 0x104u, L"%s.????????_??????.%s", Str, v19 + 1) >= 0 )
            {
              hFindFile = (__int64)FindFirstFileW(pszDest, &FindFileData);
              if ( hFindFile == -1 )
              {
                v3 = 0;
                goto LABEL_71;
              }
              v20 = HeapAlloc(hHeap, 0, 0x40u);
              v4 = v20;
              if ( !v20 )
              {
LABEL_31:
                v3 = 8;
                goto LABEL_71;
              }
              memset_0(v20, 0, 0x40u);
              while ( 1 )
              {
                v21 = 2147483646;
                v22 = v45;
                v23 = 260;
                v24 = SrcStr;
                v25 = 0;
                v26 = 0;
                while ( v23 )
                {
                  if ( !v21 || !*v22 )
                    goto LABEL_40;
                  *v24++ = *v22++;
                  --v23;
                  --v21;
                  ++v26;
                }
                --v24;
                v25 = -2147024774;
LABEL_40:
                *v24 = 0;
                if ( v25 < 0 || !(unsigned int)pSetupConcatenatePaths(SrcStr, FindFileData.cFileName, 260) )
                  break;
                v27 = -1;
                do
                  ++v27;
                while ( SrcStr[v27] );
                v28 = v27 + 1;
                LCMapStringW(0x7Fu, 0x100u, SrcStr, v27 + 1, SrcStr, v27 + 1);
                v5 = 0;
                for ( i = 0; ; ++i )
                {
                  v30 = i;
                  v31 = i <= v41;
                  if ( i >= v41 )
                    break;
                  v32 = (char *)v4[v30];
                  v33 = (char *)((char *)SrcStr - v32);
                  do
                  {
                    v34 = *(unsigned __int16 *)&v33[(_QWORD)v32];
                    v35 = *(unsigned __int16 *)v32 - v34;
                    if ( v35 )
                      break;
                    v32 += 2;
                  }
                  while ( v34 );
                  if ( v35 < 0 )
                  {
                    if ( v41 >= 8 )
                    {
                      v5 = (WCHAR *)v4[7];
                      v36 = 7;
                    }
                    else
                    {
                      v36 = v41;
                    }
                    memmove_0(&v4[i + 1], &v4[i], 8LL * (v36 - i));
                    v4[v30] = 0;
                    v31 = i <= v41;
                    break;
                  }
                }
                if ( v31 && i < 8 )
                {
                  v37 = (wchar_t *)HeapAlloc(hHeap, 0, 2 * v28);
                  v4[v30] = v37;
                  if ( !v37 )
                    goto LABEL_31;
                  if ( StringCchCopyW(v37, v28, SrcStr) < 0 )
                    break;
                  if ( v41 < 8 )
                    ++v41;
                }
                else
                {
                  v5 = SrcStr;
                }
                if ( v5 )
                {
                  if ( v5 != SrcStr || (FindFileData.dwFileAttributes & 1) != 0 )
                    SetFileAttributesW(v5, 0x80u);
                  DeleteFileW(v5);
                  if ( v5 != SrcStr )
                  {
                    HeapFree(hHeap, 0, v5);
                    v5 = 0;
                  }
                }
                if ( !FindNextFileW((HANDLE)hFindFile, &FindFileData) )
                  goto LABEL_71;
              }
            }
          }
        }
        v3 = 13;
        goto LABEL_71;
      }
    }
  }
  v3 = 87;
LABEL_71:
  if ( v4 )
  {
    for ( j = 0; j != 8; ++j )
    {
      v39 = (void *)v4[j];
      if ( v39 )
        HeapFree(hHeap, 0, v39);
    }
    HeapFree(hHeap, 0, v4);
  }
  if ( v5 && v5 != SrcStr )
    HeapFree(hHeap, 0, v5);
  if ( hFindFile != -1 )
    FindClose((HANDLE)hFindFile);
  SetLastError(v3);
  LOBYTE(v2) = v3 == 0;
  return v2;
}

```

## disassembly

```asm
0x180004658  push    rbx
0x18000465a  push    rsi
0x18000465b  push    rdi
0x18000465c  push    r12
0x18000465e  push    r13
0x180004660  push    r14
0x180004662  push    r15
0x180004664  sub     rsp, 0B80h
0x18000466b  mov     rax, cs:__security_cookie
0x180004672  xor     rax, rsp
0x180004675  mov     [rsp+0BB8h+var_48], rax
0x18000467d  mov     r14, rcx
0x180004680  xor     ebx, ebx
0x180004682  mov     edi, ebx
0x180004684  mov     [rsp+0BB8h+hFindFile], 0FFFFFFFFFFFFFFFFh
0x18000468d  xor     edx, edx; Val
0x18000468f  mov     r8d, 250h; Size
0x180004695  lea     rcx, [rsp+0BB8h+FindFileData]; void *
0x18000469d  call    memset_0
0x1800046a2  mov     r12d, ebx
0x1800046a5  mov     [rsp+0BB8h+var_B38], rbx
0x1800046ad  mov     [rsp+0BB8h+var_B84], ebx
0x1800046b1  mov     esi, ebx
0x1800046b3  mov     [rsp+0BB8h+var_B80], rbx
0x1800046b8  mov     r8d, 7FFFFFFEh
0x1800046be  mov     [rsp+0BB8h+var_B18], r8
0x1800046c6  mov     r9, r14
0x1800046c9  mov     [rsp+0BB8h+var_B28], r14
0x1800046d1  mov     r13d, 104h
0x1800046d7  mov     edx, r13d
0x1800046da  mov     [rsp+0BB8h+var_B20], rdx
0x1800046e2  lea     rax, [rsp+0BB8h+var_678]
0x1800046ea  mov     [rsp+0BB8h+var_B68], rax
0x1800046ef  mov     r11d, ebx
0x1800046f2  mov     ecx, ebx
0x1800046f4  mov     [rsp+0BB8h+var_B60], rbx
0x1800046f9  test    rdx, rdx
0x1800046fc  jz      short loc_18000474B
0x1800046fe  test    r8, r8
0x180004701  jz      short loc_180004746
0x180004703  movzx   r10d, word ptr [r9]
0x180004707  test    r10w, r10w
0x18000470b  jz      short loc_180004746
0x18000470d  mov     [rax], r10w
0x180004711  add     rax, 2
0x180004715  mov     [rsp+0BB8h+var_B68], rax
0x18000471a  add     r9, 2
0x18000471e  mov     [rsp+0BB8h+var_B28], r9
0x180004726  dec     rdx
0x180004729  mov     [rsp+0BB8h+var_B20], rdx
0x180004731  dec     r8
0x180004734  mov     [rsp+0BB8h+var_B18], r8
0x18000473c  inc     rcx
0x18000473f  mov     [rsp+0BB8h+var_B60], rcx
0x180004744  jmp     short loc_1800046F9
0x180004746  test    rdx, rdx
0x180004749  jnz     short loc_180004762
0x18000474b  sub     rax, 2
0x18000474f  mov     [rsp+0BB8h+var_B68], rax
0x180004754  dec     rcx
0x180004757  mov     [rsp+0BB8h+var_B60], rcx
0x18000475c  mov     r11d, 8007007Ah
0x180004762  mov     [rax], bx
0x180004765  test    r11d, r11d
0x180004768  js      loc_180004BE5
0x18000476e  lea     rcx, [rsp+0BB8h+var_678]
0x180004776  call    pSetupGetFileTitle
0x18000477b  mov     r8, rax
0x18000477e  lea     rax, [rsp+0BB8h+var_678]
0x180004786  cmp     r8, rax
0x180004789  jz      loc_180004BE5
0x18000478f  lea     rcx, [r8-2]
0x180004793  cmp     word ptr [rcx], 5Ch ; '\'
0x180004797  jz      short loc_1800047A3
0x180004799  cmp     word ptr [rcx], 2Fh ; '/'
0x18000479d  jnz     loc_180004BE5
0x1800047a3  lea     rdx, [rsp+0BB8h+var_678]
0x1800047ab  mov     rax, rcx
0x1800047ae  sub     rax, rdx
0x1800047b1  cmp     rax, 4
0x1800047b5  jnz     short loc_1800047D2
0x1800047b7  cmp     [rsp+0BB8h+var_678], bx
0x1800047bf  jz      short loc_1800047D2
0x1800047c1  cmp     [rsp+0BB8h+var_676], 3Ah ; ':'
0x1800047ca  jnz     short loc_1800047D2
0x1800047cc  mov     [r8], bx
0x1800047d0  jmp     short loc_1800047D5
0x1800047d2  mov     [rcx], bx
0x1800047d5  mov     r8d, 7FFFFFFEh
0x1800047db  mov     [rsp+0BB8h+var_B00], r8
0x1800047e3  mov     [rsp+0BB8h+var_B10], r14
0x1800047eb  mov     rdx, r13
0x1800047ee  mov     [rsp+0BB8h+var_B08], rdx
0x1800047f6  lea     rax, [rsp+0BB8h+Str]
0x1800047fe  mov     [rsp+0BB8h+var_B58], rax
0x180004803  mov     r10d, ebx
0x180004806  mov     rcx, rbx
0x180004809  mov     [rsp+0BB8h+var_B50], rbx
0x18000480e  test    rdx, rdx
0x180004811  jz      short loc_180004860
0x180004813  test    r8, r8
0x180004816  jz      short loc_18000485B
0x180004818  movzx   r9d, word ptr [r14]
0x18000481c  test    r9w, r9w
0x180004820  jz      short loc_18000485B
0x180004822  mov     [rax], r9w
0x180004826  add     rax, 2
0x18000482a  mov     [rsp+0BB8h+var_B58], rax
0x18000482f  add     r14, 2
0x180004833  mov     [rsp+0BB8h+var_B10], r14
0x18000483b  dec     rdx
0x18000483e  mov     [rsp+0BB8h+var_B08], rdx
0x180004846  dec     r8
0x180004849  mov     [rsp+0BB8h+var_B00], r8
0x180004851  inc     rcx
0x180004854  mov     [rsp+0BB8h+var_B50], rcx
0x180004859  jmp     short loc_18000480E
0x18000485b  test    rdx, rdx
0x18000485e  jnz     short loc_180004877
0x180004860  sub     rax, 2
0x180004864  mov     [rsp+0BB8h+var_B58], rax
0x180004869  dec     rcx
0x18000486c  mov     [rsp+0BB8h+var_B50], rcx
0x180004871  mov     r10d, 8007007Ah
0x180004877  mov     [rax], bx
0x18000487a  test    r10d, r10d
0x18000487d  jns     short loc_180004889
0x18000487f  mov     edi, 0Dh
0x180004884  jmp     loc_180004BEA
0x180004889  mov     edx, 2Eh ; '.'; Ch
0x18000488e  lea     rcx, [rsp+0BB8h+Str]; Str
0x180004896  call    cs:__imp_wcsrchr
0x18000489c  test    rax, rax
0x18000489f  jz      short loc_18000487F
0x1800048a1  mov     [rax], bx
0x1800048a4  add     rax, 2
0x1800048a8  mov     [rsp+0BB8h+lpDestStr], rax
0x1800048ad  lea     r9, [rsp+0BB8h+Str]
0x1800048b5  lea     r8, aSS; "%s.????????_??????.%s"
0x1800048bc  mov     rdx, r13; cchDest
0x1800048bf  lea     rcx, [rsp+0BB8h+pszDest]; pszDest
0x1800048c7  call    StringCchPrintfW
0x1800048cc  test    eax, eax
0x1800048ce  js      short loc_18000487F
0x1800048d0  lea     rdx, [rsp+0BB8h+FindFileData]; lpFindFileData
0x1800048d8  lea     rcx, [rsp+0BB8h+pszDest]; lpFileName
0x1800048e0  call    cs:__imp_FindFirstFileW
0x1800048e6  mov     [rsp+0BB8h+hFindFile], rax
0x1800048eb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800048ef  jnz     short loc_1800048FC
0x1800048f1  mov     edi, ebx
0x1800048f3  mov     [rsp+0BB8h+var_B88], ebx
0x1800048f7  jmp     loc_180004BEE
0x1800048fc  mov     r14d, 40h ; '@'
0x180004902  mov     r8d, r14d; dwBytes
0x180004905  xor     edx, edx; dwFlags
0x180004907  mov     rcx, cs:hHeap; hHeap
0x18000490e  call    cs:__imp_HeapAlloc
0x180004914  mov     r12, rax
0x180004917  mov     [rsp+0BB8h+var_B38], rax
0x18000491f  test    rax, rax
0x180004922  jnz     short loc_18000492E
0x180004924  mov     edi, 8
0x180004929  jmp     loc_180004BEA
0x18000492e  mov     r8, r14; Size
0x180004931  xor     edx, edx; Val
0x180004933  mov     rcx, r12; void *
0x180004936  call    memset_0
0x18000493b  mov     r8d, 7FFFFFFEh
0x180004941  mov     [rsp+0BB8h+var_AE8], r8
0x180004949  lea     r9, [rsp+0BB8h+var_678]
0x180004951  mov     [rsp+0BB8h+var_AF8], r9
0x180004959  mov     rdx, r13
0x18000495c  mov     [rsp+0BB8h+var_AF0], rdx
0x180004964  lea     rax, [rsp+0BB8h+SrcStr]
0x18000496c  mov     [rsp+0BB8h+var_B48], rax
0x180004971  mov     r11d, ebx
0x180004974  mov     rcx, rbx
0x180004977  mov     [rsp+0BB8h+var_B40], rbx
0x18000497c  test    rdx, rdx
0x18000497f  jz      short loc_1800049CE
0x180004981  test    r8, r8
0x180004984  jz      short loc_1800049C9
0x180004986  movzx   r10d, word ptr [r9]
0x18000498a  test    r10w, r10w
0x18000498e  jz      short loc_1800049C9
0x180004990  mov     [rax], r10w
0x180004994  add     rax, 2
0x180004998  mov     [rsp+0BB8h+var_B48], rax
0x18000499d  add     r9, 2
0x1800049a1  mov     [rsp+0BB8h+var_AF8], r9
0x1800049a9  dec     rdx
0x1800049ac  mov     [rsp+0BB8h+var_AF0], rdx
0x1800049b4  dec     r8
0x1800049b7  mov     [rsp+0BB8h+var_AE8], r8
0x1800049bf  inc     rcx
0x1800049c2  mov     [rsp+0BB8h+var_B40], rcx
0x1800049c7  jmp     short loc_18000497C
0x1800049c9  test    rdx, rdx
0x1800049cc  jnz     short loc_1800049E5
0x1800049ce  sub     rax, 2
0x1800049d2  mov     [rsp+0BB8h+var_B48], rax
0x1800049d7  dec     rcx
0x1800049da  mov     [rsp+0BB8h+var_B40], rcx
0x1800049df  mov     r11d, 8007007Ah
0x1800049e5  mov     [rax], bx
0x1800049e8  test    r11d, r11d
0x1800049eb  js      loc_18000487F
0x1800049f1  mov     r8d, r13d
0x1800049f4  lea     rdx, [rsp+0BB8h+FindFileData.cFileName]
0x1800049fc  lea     rcx, [rsp+0BB8h+SrcStr]
0x180004a04  call    pSetupConcatenatePaths
0x180004a09  test    eax, eax
0x180004a0b  jz      loc_18000487F
0x180004a11  lea     rcx, [rsp+0BB8h+SrcStr]
0x180004a19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180004a1d  inc     rax
0x180004a20  cmp     [rcx+rax*2], bx
0x180004a24  jnz     short loc_180004A1D
0x180004a26  lea     r13d, [rax+1]
0x180004a2a  mov     [rsp+0BB8h+cchDest], r13d; cchDest
0x180004a2f  lea     rax, [rsp+0BB8h+SrcStr]
0x180004a37  mov     [rsp+0BB8h+lpDestStr], rax; lpDestStr
0x180004a3c  mov     r9d, r13d; cchSrc
0x180004a3f  lea     r8, [rsp+0BB8h+SrcStr]; lpSrcStr
0x180004a47  mov     edx, 100h; dwMapFlags
0x180004a4c  mov     ecx, 7Fh; Locale
0x180004a51  call    cs:__imp_LCMapStringW
0x180004a57  mov     rsi, rbx
0x180004a5a  mov     [rsp+0BB8h+var_B80], rbx
0x180004a5f  mov     r14d, ebx
0x180004a62  mov     [rsp+0BB8h+var_B78], ebx
0x180004a66  mov     r9d, [rsp+0BB8h+var_B84]
0x180004a6b  mov     eax, r14d
0x180004a6e  lea     r15, ds:0[rax*8]
0x180004a76  cmp     r14d, r9d
0x180004a79  jnb     short loc_180004AE8
0x180004a7b  mov     rax, [r15+r12]
0x180004a7f  lea     r8, [rsp+0BB8h+SrcStr]
0x180004a87  sub     r8, rax
0x180004a8a  movzx   edx, word ptr [rax]
0x180004a8d  movzx   ecx, word ptr [rax+r8]
0x180004a92  sub     edx, ecx
0x180004a94  jnz     short loc_180004A9E
0x180004a96  add     rax, 2
0x180004a9a  test    ecx, ecx
0x180004a9c  jnz     short loc_180004A8A
0x180004a9e  lea     ecx, [r14+1]
0x180004aa2  test    edx, edx
0x180004aa4  jns     loc_180004B4F
0x180004aaa  mov     eax, r14d
0x180004aad  lea     rdx, [r12+rax*8]; Src
0x180004ab1  lea     rcx, [r12+rcx*8]; void *
0x180004ab5  cmp     r9d, 8
0x180004ab9  jnb     short loc_180004AC0
0x180004abb  mov     r8d, r9d
0x180004abe  jmp     short loc_180004AD0
0x180004ac0  mov     rsi, [r12+38h]
0x180004ac5  mov     [rsp+0BB8h+var_B80], rsi
0x180004aca  mov     r8d, 7
0x180004ad0  sub     r8d, r14d
0x180004ad3  shl     r8, 3; Size
0x180004ad7  call    memmove_0
0x180004adc  mov     [r15+r12], rbx
0x180004ae0  mov     r9d, [rsp+0BB8h+var_B84]
0x180004ae5  cmp     r14d, r9d
0x180004ae8  ja      short loc_180004B5B
0x180004aea  cmp     r14d, 8
0x180004aee  jnb     short loc_180004B5B
0x180004af0  mov     r14d, r13d
0x180004af3  lea     r8d, ds:0[r13*2]; dwBytes
0x180004afb  xor     edx, edx; dwFlags
0x180004afd  mov     rcx, cs:hHeap; hHeap
0x180004b04  call    cs:__imp_HeapAlloc
0x180004b0a  mov     [r15+r12], rax
0x180004b0e  test    rax, rax
0x180004b11  jz      loc_180004924
0x180004b17  lea     r8, [rsp+0BB8h+SrcStr]; pszSrc
0x180004b1f  mov     edx, r14d; cchDest
0x180004b22  mov     rcx, rax; pszDest
0x180004b25  call    StringCchCopyW
0x180004b2a  test    eax, eax
0x180004b2c  js      loc_18000487F
0x180004b32  mov     r9d, [rsp+0BB8h+var_B84]
0x180004b37  cmp     r9d, 8
0x180004b3b  jnb     short loc_180004B68
0x180004b3d  inc     r9d
0x180004b40  mov     [rsp+0BB8h+var_B84], r9d
0x180004b45  mov     [rsp+0BB8h+var_B30], r9d
0x180004b4d  jmp     short loc_180004B68
0x180004b4f  mov     r14d, ecx
0x180004b52  mov     [rsp+0BB8h+var_B78], ecx
0x180004b56  jmp     loc_180004A6B
0x180004b5b  lea     rsi, [rsp+0BB8h+SrcStr]
0x180004b63  mov     [rsp+0BB8h+var_B80], rsi
0x180004b68  test    rsi, rsi
0x180004b6b  jz      short loc_180004BC2
0x180004b6d  lea     rax, [rsp+0BB8h+SrcStr]
0x180004b75  cmp     rsi, rax
0x180004b78  jnz     short loc_180004B84
  ... truncated ...
```
