# ChangeDestinationToTempDirectory(void *,PLATFORM,void *,void *,ushort *)

- ea: `0x18000908c`
- end: `0x18000939e`
- name: `?ChangeDestinationToTempDirectory@@YAJPEAXW4PLATFORM@@00PEAG@Z`
- size: `786`
- prototype: `int __high(void *, enum PLATFORM, void *, void *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x180009d64`

## callees

- `0x180001ea4`
- `0x180001eb0`
- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180008f7c`
- `0x18000908c`
- `0x18000cfb4`
- `0x180018d18`
- `0x18002fd3c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000926b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000927e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009291`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009310`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009323`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009347`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000926b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000927e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009291`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092a4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800092fd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009310`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009323`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009336`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009347`
- `SETUPAPI!SetupScanFileQueueW` at `0x180009215`
- `SETUPAPI!SetupScanFileQueueW` at `0x180009215`
- `SETUPAPI!SetupQueueCopyIndirectW` at `0x180009251`
- `SETUPAPI!SetupQueueCopyIndirectW` at `0x180009251`

## pseudocode

```c
__int64 __fastcall ChangeDestinationToTempDirectory(__int64 a1, int a2, char *a3, __int64 a4, WCHAR *lpPathName)
{
  __int64 v6; // r14
  HRESULT UniqueTempDirInUserTempDir; // ebx
  char *v10; // rax
  void *v11; // rdx
  int v12; // eax
  __int16 v13; // cx
  struct _SP_FILE_COPY_PARAMS_W *v14; // rdi
  WCHAR *SourceRootPath; // rcx
  WCHAR *SourceFilename; // rcx
  WCHAR *SourceDescription; // rcx
  WCHAR *SourceTagfile; // rcx
  _QWORD *v19; // rdi
  void *v20; // rsi
  void *v21; // rcx
  void *v22; // rcx
  void *v23; // rcx
  void *v24; // rcx
  DWORD Result[12]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 CallbackContext; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+6Ch] [rbp-94h]
  int v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+74h] [rbp-8Ch]
  __int16 v32; // [rsp+7Ch] [rbp-84h]
  __int64 v33; // [rsp+7Eh] [rbp-82h]
  __int16 v34; // [rsp+86h] [rbp-7Ah]
  __int64 v35; // [rsp+88h] [rbp-78h]
  void *v36; // [rsp+90h] [rbp-70h]
  unsigned __int16 v37[260]; // [rsp+98h] [rbp-68h] BYREF

  v6 = a2;
  memset_0(&CallbackContext, 0, 0x240u);
  Result[0] = 0;
  if ( (unsigned __int64)(a3 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL
    || !lpPathName )
  {
    UniqueTempDirInUserTempDir = -2147024809;
    goto LABEL_28;
  }
  UniqueTempDirInUserTempDir = GetUniqueTempDirInUserTempDir(lpPathName);
  if ( UniqueTempDirInUserTempDir < 0 )
    goto LABEL_28;
  CallbackContext = a1;
  v35 = a4;
  v28 = v6;
  v10 = (char *)operator new(0x38u);
  v11 = v10;
  if ( v10 )
  {
    *(_DWORD *)v10 = 1768844404;
    *((_DWORD *)v10 + 4) = 1802398836;
    *((_QWORD *)v10 + 3) = v10 + 8;
    *((_QWORD *)v10 + 4) = v10 + 8;
    *((_QWORD *)v10 + 1) = &NCoreLibrary::TLinkNi<_SP_FILE_COPY_PARAMS_W>::`vftable';
    *((_DWORD *)v10 + 10) = 1802398836;
    *((_QWORD *)v10 + 6) = 0;
  }
  else
  {
    v11 = 0;
  }
  v36 = v11;
  if ( !v11 )
    UniqueTempDirInUserTempDir = -2147024882;
  if ( UniqueTempDirInUserTempDir < 0 )
    goto LABEL_29;
  v29 = 28;
  v12 = *(&PlatformArch + 2 * v6);
  v13 = *((_WORD *)&PlatformArch + 4 * v6 + 2);
  memset(&Result[2], 0, 28);
  v30 = v12;
  v31 = *(_QWORD *)&Result[4];
  v32 = v13;
  v34 = 0;
  v33 = 0;
  UniqueTempDirInUserTempDir = StringCchCopyW(v37, 0x104u, lpPathName);
  if ( UniqueTempDirInUserTempDir < 0
    || (SetupScanFileQueueW(a3, 8u, 0, RewriterCallback, &CallbackContext, Result), !Result[0])
    && (UniqueTempDirInUserTempDir = GetLastErrorAsHResult(), UniqueTempDirInUserTempDir < 0) )
  {
LABEL_28:
    v11 = v36;
    goto LABEL_29;
  }
  while ( 1 )
  {
    v11 = v36;
    if ( (char *)v36 + 8 == *((void **)v36 + 3) )
      break;
    v14 = (struct _SP_FILE_COPY_PARAMS_W *)NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(v36);
    if ( !SetupQueueCopyIndirectW(v14) )
      UniqueTempDirInUserTempDir = GetLastErrorAsHResult();
    SourceRootPath = (WCHAR *)v14->SourceRootPath;
    if ( SourceRootPath )
    {
      LocalFree(SourceRootPath);
      v14->SourceRootPath = 0;
    }
    SourceFilename = (WCHAR *)v14->SourceFilename;
    if ( SourceFilename )
    {
      LocalFree(SourceFilename);
      v14->SourceFilename = 0;
    }
    SourceDescription = (WCHAR *)v14->SourceDescription;
    if ( SourceDescription )
    {
      LocalFree(SourceDescription);
      v14->SourceDescription = 0;
    }
    SourceTagfile = (WCHAR *)v14->SourceTagfile;
    if ( SourceTagfile )
    {
      LocalFree(SourceTagfile);
      v14->SourceTagfile = 0;
    }
    v14->TargetFilename = 0;
    LocalFree(v14);
    if ( UniqueTempDirInUserTempDir < 0 )
      goto LABEL_28;
  }
LABEL_29:
  if ( v11 )
  {
    v19 = (_QWORD *)NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(v11);
    if ( UniqueTempDirInUserTempDir < 0 )
    {
      v20 = v36;
    }
    else
    {
      while ( 1 )
      {
        v20 = v36;
        if ( (char *)v36 + 8 == *((void **)v36 + 3) )
          break;
        v21 = (void *)v19[2];
        if ( v21 )
        {
          LocalFree(v21);
          v19[2] = 0;
        }
        v22 = (void *)v19[4];
        if ( v22 )
        {
          LocalFree(v22);
          v19[4] = 0;
        }
        v23 = (void *)v19[5];
        if ( v23 )
        {
          LocalFree(v23);
          v19[5] = 0;
        }
        v24 = (void *)v19[6];
        if ( v24 )
        {
          LocalFree(v24);
          v19[6] = 0;
        }
        v19[8] = 0;
        LocalFree(v19);
        v19 = (_QWORD *)NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(v36);
      }
    }
    if ( v20 )
    {
      NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::~TListNi<_SP_FILE_COPY_PARAMS_W>(v20);
      operator delete(v20, 0x38u);
    }
  }
  return (unsigned int)UniqueTempDirInUserTempDir;
}

```

## disassembly

```asm
0x18000908c  push    rbp
0x18000908e  push    rbx
0x18000908f  push    rsi
0x180009090  push    rdi
0x180009091  push    r12
0x180009093  push    r13
0x180009095  push    r14
0x180009097  push    r15
0x180009099  lea     rbp, [rsp-1B8h]
0x1800090a1  sub     rsp, 2B8h
0x1800090a8  mov     rax, cs:__security_cookie
0x1800090af  xor     rax, rsp
0x1800090b2  mov     [rbp+1F0h+var_50], rax
0x1800090b9  mov     rdi, [rbp+1F0h+lpPathName]
0x1800090c0  mov     r13, r8
0x1800090c3  movsxd  r14, edx
0x1800090c6  mov     r15, rcx
0x1800090c9  xor     edx, edx; Val
0x1800090cb  lea     rcx, [rsp+2F0h+var_290]; void *
0x1800090d0  mov     r8d, 240h; Size
0x1800090d6  mov     rsi, r9
0x1800090d9  call    memset_0
0x1800090de  xor     r12d, r12d
0x1800090e1  lea     rax, [r13-1]
0x1800090e5  mov     [rsp+2F0h+var_2C0], r12d
0x1800090ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800090ee  ja      loc_1800092C5
0x1800090f4  lea     rax, [rsi-1]
0x1800090f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800090fc  ja      loc_1800092C5
0x180009102  test    rdi, rdi
0x180009105  jz      loc_1800092C5
0x18000910b  mov     rcx, rdi; lpPathName
0x18000910e  call    GetUniqueTempDirInUserTempDir
0x180009113  mov     ebx, eax
0x180009115  test    eax, eax
0x180009117  js      loc_1800092CA
0x18000911d  lea     ecx, [r12+38h]; Size
0x180009122  mov     [rsp+2F0h+var_290], r15
0x180009127  mov     [rbp+1F0h+var_268], rsi
0x18000912b  mov     [rsp+2F0h+var_288], r14d
0x180009130  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009135  mov     rdx, rax
0x180009138  test    rax, rax
0x18000913b  jz      short loc_18000916D
0x18000913d  mov     dword ptr [rax], 696E6C74h
0x180009143  lea     rcx, [rax+8]
0x180009147  mov     r8d, 6B6E6C74h
0x18000914d  lea     rax, ??_7?$TLinkNi@U_SP_FILE_COPY_PARAMS_W@@@NCoreLibrary@@6B@; const NCoreLibrary::TLinkNi<_SP_FILE_COPY_PARAMS_W>::`vftable'
0x180009154  mov     [rcx+8], r8d
0x180009158  mov     [rcx+10h], rcx
0x18000915c  mov     [rcx+18h], rcx
0x180009160  mov     [rcx], rax
0x180009163  mov     [rcx+20h], r8d
0x180009167  mov     [rcx+28h], r12
0x18000916b  jmp     short loc_180009170
0x18000916d  mov     rdx, r12
0x180009170  test    rdx, rdx
0x180009173  mov     [rbp+1F0h+var_260], rdx
0x180009177  mov     eax, 8007000Eh
0x18000917c  cmovz   ebx, eax
0x18000917f  test    ebx, ebx
0x180009181  js      loc_1800092CE
0x180009187  xorps   xmm0, xmm0
0x18000918a  mov     [rsp+2F0h+var_284], 1Ch
0x180009192  lea     rdx, PlatformArch
0x180009199  mov     r8, rdi; unsigned __int16 *
0x18000919c  mov     eax, [rdx+r14*8]
0x1800091a0  movzx   ecx, word ptr [rdx+r14*8+4]
0x1800091a6  mov     edx, 104h; unsigned __int64
0x1800091ab  movups  [rsp+2F0h+var_2B8], xmm0
0x1800091b0  mov     [rsp+2F0h+var_280], eax
0x1800091b4  movups  [rsp+2F0h+var_2B8+0Ch], xmm0
0x1800091b9  mov     rax, qword ptr [rsp+2F0h+var_2B8+8]
0x1800091be  movsd   xmm0, [rsp+2F0h+var_2A6]
0x1800091c4  mov     [rsp+2F0h+var_27C], rax
0x1800091c9  movzx   eax, [rsp+2F0h+var_29E]
0x1800091ce  mov     [rsp+2F0h+var_274], cx
0x1800091d3  lea     rcx, [rbp+1F0h+var_258]; unsigned __int16 *
0x1800091d7  mov     [rbp+1F0h+var_26A], ax
0x1800091db  movsd   [rsp+2F0h+var_272], xmm0
0x1800091e1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800091e6  mov     ebx, eax
0x1800091e8  test    eax, eax
0x1800091ea  js      loc_1800092CA
0x1800091f0  xor     r8d, r8d; Window
0x1800091f3  lea     rax, [rsp+2F0h+var_2C0]
0x1800091f8  mov     [rsp+2F0h+Result], rax; Result
0x1800091fd  lea     r9, ?RewriterCallback@@YAIPEAXI_K1@Z; CallbackRoutine
0x180009204  lea     rax, [rsp+2F0h+var_290]
0x180009209  mov     rcx, r13; FileQueue
0x18000920c  mov     [rsp+2F0h+CallbackContext], rax; CallbackContext
0x180009211  lea     edx, [r8+8]; Flags
0x180009215  call    cs:__imp_SetupScanFileQueueW
0x18000921b  cmp     [rsp+2F0h+var_2C0], r12d
0x180009220  jnz     short loc_180009231
0x180009222  call    GetLastErrorAsHResult
0x180009227  mov     ebx, eax
0x180009229  test    eax, eax
0x18000922b  js      loc_1800092CA
0x180009231  mov     rdx, [rbp+1F0h+var_260]
0x180009235  lea     rax, [rdx+8]
0x180009239  cmp     rax, [rax+10h]
0x18000923d  jz      loc_1800092CE
0x180009243  mov     rcx, rdx
0x180009246  call    ?RemoveAtTail@?$TListNi@U_SP_FILE_COPY_PARAMS_W@@@NCoreLibrary@@QEAAPEAU_SP_FILE_COPY_PARAMS_W@@XZ; NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(void)
0x18000924b  mov     rcx, rax; CopyParams
0x18000924e  mov     rdi, rax
0x180009251  call    cs:__imp_SetupQueueCopyIndirectW
0x180009257  test    eax, eax
0x180009259  jnz     short loc_180009262
0x18000925b  call    GetLastErrorAsHResult
0x180009260  mov     ebx, eax
0x180009262  mov     rcx, [rdi+10h]; hMem
0x180009266  test    rcx, rcx
0x180009269  jz      short loc_180009275
0x18000926b  call    cs:__imp_LocalFree
0x180009271  mov     [rdi+10h], r12
0x180009275  mov     rcx, [rdi+20h]; hMem
0x180009279  test    rcx, rcx
0x18000927c  jz      short loc_180009288
0x18000927e  call    cs:__imp_LocalFree
0x180009284  mov     [rdi+20h], r12
0x180009288  mov     rcx, [rdi+28h]; hMem
0x18000928c  test    rcx, rcx
0x18000928f  jz      short loc_18000929B
0x180009291  call    cs:__imp_LocalFree
0x180009297  mov     [rdi+28h], r12
0x18000929b  mov     rcx, [rdi+30h]; hMem
0x18000929f  test    rcx, rcx
0x1800092a2  jz      short loc_1800092AE
0x1800092a4  call    cs:__imp_LocalFree
0x1800092aa  mov     [rdi+30h], r12
0x1800092ae  mov     rcx, rdi; hMem
0x1800092b1  mov     [rdi+40h], r12
0x1800092b5  call    cs:__imp_LocalFree
0x1800092bb  test    ebx, ebx
0x1800092bd  jns     loc_180009231
0x1800092c3  jmp     short loc_1800092CA
0x1800092c5  mov     ebx, 80070057h
0x1800092ca  mov     rdx, [rbp+1F0h+var_260]
0x1800092ce  test    rdx, rdx
0x1800092d1  jz      loc_180009379
0x1800092d7  mov     rcx, rdx
0x1800092da  call    ?RemoveAtTail@?$TListNi@U_SP_FILE_COPY_PARAMS_W@@@NCoreLibrary@@QEAAPEAU_SP_FILE_COPY_PARAMS_W@@XZ; NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(void)
0x1800092df  mov     rdi, rax
0x1800092e2  test    ebx, ebx
0x1800092e4  js      short loc_18000935B
0x1800092e6  mov     rsi, [rbp+1F0h+var_260]
0x1800092ea  lea     rcx, [rsi+8]
0x1800092ee  cmp     rcx, [rcx+10h]
0x1800092f2  jz      short loc_18000935F
0x1800092f4  mov     rcx, [rdi+10h]; hMem
0x1800092f8  test    rcx, rcx
0x1800092fb  jz      short loc_180009307
0x1800092fd  call    cs:__imp_LocalFree
0x180009303  mov     [rdi+10h], r12
0x180009307  mov     rcx, [rdi+20h]; hMem
0x18000930b  test    rcx, rcx
0x18000930e  jz      short loc_18000931A
0x180009310  call    cs:__imp_LocalFree
0x180009316  mov     [rdi+20h], r12
0x18000931a  mov     rcx, [rdi+28h]; hMem
0x18000931e  test    rcx, rcx
0x180009321  jz      short loc_18000932D
0x180009323  call    cs:__imp_LocalFree
0x180009329  mov     [rdi+28h], r12
0x18000932d  mov     rcx, [rdi+30h]; hMem
0x180009331  test    rcx, rcx
0x180009334  jz      short loc_180009340
0x180009336  call    cs:__imp_LocalFree
0x18000933c  mov     [rdi+30h], r12
0x180009340  mov     rcx, rdi; hMem
0x180009343  mov     [rdi+40h], r12
0x180009347  call    cs:__imp_LocalFree
0x18000934d  mov     rcx, [rbp+1F0h+var_260]
0x180009351  call    ?RemoveAtTail@?$TListNi@U_SP_FILE_COPY_PARAMS_W@@@NCoreLibrary@@QEAAPEAU_SP_FILE_COPY_PARAMS_W@@XZ; NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::RemoveAtTail(void)
0x180009356  mov     rdi, rax
0x180009359  jmp     short loc_1800092E6
0x18000935b  mov     rsi, [rbp+1F0h+var_260]
0x18000935f  test    rsi, rsi
0x180009362  jz      short loc_180009379
0x180009364  mov     rcx, rsi
0x180009367  call    ??1?$TListNi@U_SP_FILE_COPY_PARAMS_W@@@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TListNi<_SP_FILE_COPY_PARAMS_W>::~TListNi<_SP_FILE_COPY_PARAMS_W>(void)
0x18000936c  mov     edx, 38h ; '8'; unsigned __int64
0x180009371  mov     rcx, rsi; void *
0x180009374  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180009379  mov     eax, ebx
0x18000937b  mov     rcx, [rbp+1F0h+var_50]
0x180009382  xor     rcx, rsp; StackCookie
0x180009385  call    __security_check_cookie
0x18000938a  add     rsp, 2B8h
0x180009391  pop     r15
0x180009393  pop     r14
0x180009395  pop     r13
0x180009397  pop     r12
0x180009399  pop     rdi
0x18000939a  pop     rsi
0x18000939b  pop     rbx
0x18000939c  pop     rbp
0x18000939d  retn
```
