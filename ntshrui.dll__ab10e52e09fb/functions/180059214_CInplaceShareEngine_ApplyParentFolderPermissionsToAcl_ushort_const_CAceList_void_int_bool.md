# CInplaceShareEngine::_ApplyParentFolderPermissionsToAcl(ushort const *,CAceList *,void * *,int,bool)

- ea: `0x180059214`
- end: `0x180059467`
- name: `?_ApplyParentFolderPermissionsToAcl@CInplaceShareEngine@@AEAAJPEBGPEAVCAceList@@PEAPEAXH_N@Z`
- size: `595`
- prototype: `int(CInplaceShareEngine *__hidden this, const unsigned __int16 *, struct CAceList *, void **, int, bool)`
- caller_count: `1`
- callee_count: `14`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18005dd50`

## callees

- `0x180009340`
- `0x18000ac90`
- `0x18000d1f0`
- `0x18000fdf0`
- `0x18001d1dc`
- `0x18001d9a0`
- `0x180024014`
- `0x1800243c8`
- `0x1800254e0`
- `0x180026394`
- `0x1800572bc`
- `0x180059214`
- `0x18005b5e4`
- `0x18005c4a4`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180059343`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180059343`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059416`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059416`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180059386`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180059386`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180059379`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180059379`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180059314`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180059314`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::_ApplyParentFolderPermissionsToAcl(
        CInplaceShareEngine *this,
        const unsigned __int16 *a2,
        struct CAceList *a3,
        void **a4,
        int a5,
        bool a6)
{
  CInplaceShareEngine *v8; // rdi
  int Acl; // ebx
  int v10; // eax
  unsigned int v11; // edx
  void *v12; // rcx
  struct CAceList *v13; // rsi
  int v14; // eax
  unsigned int *v15; // r14
  __int64 v16; // rcx
  HANDLE FirstFileW; // rdi
  CInplaceShareEngine *v18; // rcx
  int v19; // r15d
  __int64 v20; // rdi
  int v21; // ebx
  __int64 Ace; // rax
  unsigned int v23; // ebx
  int v24; // eax
  struct CAceList *v27; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  void **v30; // [rsp+50h] [rbp-B0h]
  struct CAceList *v31; // [rsp+58h] [rbp-A8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR FileName[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v30 = a4;
  v31 = a3;
  v27 = 0;
  v8 = this;
  Acl = CFolderAclEngine::_GetAcl(this, a2, &v27, 0, 0);
  if ( Acl >= 0 )
  {
    pv = 0;
    v28 = 0;
    v10 = ULongLongMult(a5, 4u, &v28);
    v13 = v27;
    Acl = v10;
    if ( v10 >= 0 )
    {
      v14 = CTCoAllocPolicy::Alloc(v12, 1u, v28, &pv);
      v15 = (unsigned int *)pv;
      Acl = v14;
      if ( pv )
      {
        Acl = StringCchPrintfW(FileName, 0x104u, L"%s\\*", a2);
        if ( Acl >= 0 )
        {
          memset_0(&FindFileData, 0, sizeof(FindFileData));
          FirstFileW = FindFirstFileW(FileName, &FindFileData);
          if ( FirstFileW == (HANDLE)-1LL )
            goto LABEL_31;
          do
          {
            if ( !(unsigned int)PathIsDotOrDotDotW(FindFileData.cFileName) )
            {
              PathCchCombine(pszPathOut, 0x104u, a2, FindFileData.cFileName);
              Acl = CInplaceShareEngine::_OrRequiredAccessMaskForItem(
                      v18,
                      pszPathOut,
                      FindFileData.dwFileAttributes & 0x10,
                      a4,
                      v15,
                      a5);
              if ( Acl < 0 )
                break;
            }
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          FindClose(FirstFileW);
          if ( Acl >= 0 )
          {
LABEL_31:
            v19 = 0;
            if ( a5 > 0 )
            {
              v20 = 0;
              do
              {
                v21 = 0;
                Ace = CAceList::s_FindAce(v16, (char *)v13 + 8, v30[v20], 0, 0);
                if ( Ace && (!a6 || v15[v20] || *(_DWORD *)(Ace + 4) != 1179817 && *(_DWORD *)(Ace + 4) != 1180091) )
                  v21 = *(_DWORD *)(Ace + 4);
                v23 = v15[v20] | v21;
                if ( v23 )
                  v24 = CInplaceShareEngine::_s_SetParentAce(a2, v23, v30[v20]);
                else
                  v24 = CInplaceShareEngine::_s_RemoveParentAce(a2, v30[v20]);
                ++v19;
                ++v20;
                Acl = v24;
              }
              while ( v19 < a5 );
            }
          }
          v8 = this;
        }
        CoTaskMemFree(v15);
      }
    }
    if ( Acl >= 0 )
      Acl = CInplaceShareEngine::_SetParentFolderCreatorOwnerAce(v8, v31, v13, a2);
    if ( v13 )
      CAceList::`scalar deleting destructor'(v13, v11);
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x180059214  push    rbp
0x180059216  push    rbx
0x180059217  push    rsi
0x180059218  push    rdi
0x180059219  push    r12
0x18005921b  push    r13
0x18005921d  push    r14
0x18005921f  push    r15
0x180059221  lea     rbp, [rsp-5E8h]
0x180059229  sub     rsp, 6E8h
0x180059230  mov     rax, cs:__security_cookie
0x180059237  xor     rax, rsp
0x18005923a  mov     [rbp+620h+var_50], rax
0x180059241  mov     r15, r9
0x180059244  mov     [rsp+720h+var_6D0], r9
0x180059249  mov     [rsp+720h+var_6C8], r8
0x18005924e  xor     r14d, r14d
0x180059251  xor     r9d, r9d; void **
0x180059254  mov     [rsp+720h+var_6E8], r14
0x180059259  lea     r8, [rsp+720h+var_6E8]; struct CAceList **
0x18005925e  mov     dword ptr [rsp+720h+var_700], r14d; int
0x180059263  mov     r12, rdx
0x180059266  mov     [rsp+720h+var_6F0], rcx
0x18005926b  mov     rdi, rcx
0x18005926e  call    ?_GetAcl@CFolderAclEngine@@IEAAJPEBGPEAPEAVCAceList@@PEAPEAXH@Z; CFolderAclEngine::_GetAcl(ushort const *,CAceList * *,void * *,int)
0x180059273  mov     ebx, eax
0x180059275  test    eax, eax
0x180059277  js      loc_180059442
0x18005927d  movsxd  r13, [rbp+620h+arg_20]
0x180059284  lea     r8, [rsp+720h+var_6E0]; unsigned __int64 *
0x180059289  mov     rcx, r13; unsigned __int64
0x18005928c  mov     [rsp+720h+pv], r14
0x180059291  lea     edx, [r14+4]; unsigned __int64
0x180059295  mov     [rsp+720h+var_6E0], r14
0x18005929a  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18005929f  mov     rsi, [rsp+720h+var_6E8]
0x1800592a4  mov     ebx, eax
0x1800592a6  test    eax, eax
0x1800592a8  js      loc_18005941C
0x1800592ae  mov     r8, [rsp+720h+var_6E0]; unsigned __int64
0x1800592b3  lea     r9, [rsp+720h+pv]; void **
0x1800592b8  lea     edx, [r14+1]; unsigned int
0x1800592bc  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1800592c1  mov     r14, [rsp+720h+pv]
0x1800592c6  mov     ebx, eax
0x1800592c8  test    r14, r14
0x1800592cb  jz      loc_18005941C
0x1800592d1  mov     r9, r12
0x1800592d4  lea     r8, aS_0; "%s\\*"
0x1800592db  mov     edx, 104h; unsigned __int64
0x1800592e0  lea     rcx, [rbp+620h+FileName]; unsigned __int16 *
0x1800592e7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800592ec  mov     ebx, eax
0x1800592ee  test    eax, eax
0x1800592f0  js      loc_180059413
0x1800592f6  xor     edx, edx; Val
0x1800592f8  lea     rcx, [rsp+720h+FindFileData]; void *
0x1800592fd  mov     r8d, 250h; Size
0x180059303  call    memset_0
0x180059308  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x18005930d  lea     rcx, [rbp+620h+FileName]; lpFileName
0x180059314  call    cs:__imp_FindFirstFileW
0x18005931a  mov     rdi, rax
0x18005931d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180059321  jz      short loc_180059390
0x180059323  lea     rcx, [rbp+620h+FindFileData.cFileName]; unsigned __int16 *
0x180059327  call    ?PathIsDotOrDotDotW@@YAHPEBG@Z; PathIsDotOrDotDotW(ushort const *)
0x18005932c  test    eax, eax
0x18005932e  jnz     short loc_180059371
0x180059330  lea     r9, [rbp+620h+FindFileData.cFileName]; pszMore
0x180059334  mov     r8, r12; pszPathIn
0x180059337  mov     edx, 104h; cchPathOut
0x18005933c  lea     rcx, [rbp+620h+pszPathOut]; pszPathOut
0x180059343  call    cs:__imp_PathCchCombine
0x180059349  mov     r8d, [rsp+720h+FindFileData.dwFileAttributes]
0x18005934e  lea     rdx, [rbp+620h+pszPathOut]; unsigned __int16 *
0x180059355  and     r8d, 10h; int
0x180059359  mov     [rsp+720h+var_6F8], r13d; int
0x18005935e  mov     r9, r15; void **
0x180059361  mov     [rsp+720h+var_700], r14; unsigned int *
0x180059366  call    ?_OrRequiredAccessMaskForItem@CInplaceShareEngine@@AEAAJPEBGHPEAPEAXPEAKH@Z; CInplaceShareEngine::_OrRequiredAccessMaskForItem(ushort const *,int,void * *,ulong *,int)
0x18005936b  mov     ebx, eax
0x18005936d  test    eax, eax
0x18005936f  js      short loc_180059383
0x180059371  lea     rdx, [rsp+720h+FindFileData]; lpFindFileData
0x180059376  mov     rcx, rdi; hFindFile
0x180059379  call    cs:__imp_FindNextFileW
0x18005937f  test    eax, eax
0x180059381  jnz     short loc_180059323
0x180059383  mov     rcx, rdi; hFindFile
0x180059386  call    cs:__imp_FindClose
0x18005938c  test    ebx, ebx
0x18005938e  js      short loc_18005940E
0x180059390  xor     r15d, r15d
0x180059393  test    r13d, r13d
0x180059396  jle     short loc_18005940E
0x180059398  xor     edi, edi
0x18005939a  mov     r8, [rsp+720h+var_6D0]
0x18005939f  lea     rdx, [rsi+8]
0x1800593a3  xor     ebx, ebx
0x1800593a5  xor     r9d, r9d
0x1800593a8  mov     [rsp+720h+var_700], rbx
0x1800593ad  mov     r8, [r8+rdi*8]
0x1800593b1  call    ?s_FindAce@CAceList@@AEAAPEAVCAce@@AEAV?$CDPA@VCAce@@V?$CTContainer_PolicyUnOwned@VCAce@@@@@@PEAXEPEBV2@@Z; CAceList::s_FindAce(CDPA<CAce,CTContainer_PolicyUnOwned<CAce>> &,void *,uchar,CAce const *)
0x1800593b6  test    rax, rax
0x1800593b9  jz      short loc_1800593DE
0x1800593bb  cmp     [rbp+620h+arg_28], bl
0x1800593c1  jz      short loc_1800593DB
0x1800593c3  cmp     [r14+rdi*4], ebx
0x1800593c7  jnz     short loc_1800593DB
0x1800593c9  cmp     dword ptr [rax+4], 1200A9h
0x1800593d0  jz      short loc_1800593DE
0x1800593d2  cmp     dword ptr [rax+4], 1201BBh
0x1800593d9  jz      short loc_1800593DE
0x1800593db  mov     ebx, [rax+4]
0x1800593de  or      ebx, [r14+rdi*4]
0x1800593e2  mov     rcx, r12; lpFileName
0x1800593e5  mov     rax, [rsp+720h+var_6D0]
0x1800593ea  mov     rdx, [rax+rdi*8]; pSid2
0x1800593ee  jz      short loc_1800593FC
0x1800593f0  mov     r8, rdx; void *
0x1800593f3  mov     edx, ebx; unsigned int
0x1800593f5  call    ?_s_SetParentAce@CInplaceShareEngine@@CAJPEBGKPEAX@Z; CInplaceShareEngine::_s_SetParentAce(ushort const *,ulong,void *)
0x1800593fa  jmp     short loc_180059401
0x1800593fc  call    ?_s_RemoveParentAce@CInplaceShareEngine@@CAJPEBGPEAX@Z; CInplaceShareEngine::_s_RemoveParentAce(ushort const *,void *)
0x180059401  inc     r15d
0x180059404  inc     rdi
0x180059407  mov     ebx, eax
0x180059409  cmp     r15d, r13d
0x18005940c  jl      short loc_18005939A
0x18005940e  mov     rdi, [rsp+720h+var_6F0]
0x180059413  mov     rcx, r14; pv
0x180059416  call    cs:__imp_CoTaskMemFree
0x18005941c  test    ebx, ebx
0x18005941e  js      short loc_180059435
0x180059420  mov     rdx, [rsp+720h+var_6C8]; struct CAceList *
0x180059425  mov     r9, r12; unsigned __int16 *
0x180059428  mov     r8, rsi; struct CAceList *
0x18005942b  mov     rcx, rdi; this
0x18005942e  call    ?_SetParentFolderCreatorOwnerAce@CInplaceShareEngine@@AEAAJPEAVCAceList@@0PEBG@Z; CInplaceShareEngine::_SetParentFolderCreatorOwnerAce(CAceList *,CAceList *,ushort const *)
0x180059433  mov     ebx, eax
0x180059435  test    rsi, rsi
0x180059438  jz      short loc_180059442
0x18005943a  mov     rcx, rsi; this
0x18005943d  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x180059442  mov     eax, ebx
0x180059444  mov     rcx, [rbp+620h+var_50]
0x18005944b  xor     rcx, rsp; StackCookie
0x18005944e  call    __security_check_cookie
0x180059453  add     rsp, 6E8h
0x18005945a  pop     r15
0x18005945c  pop     r14
0x18005945e  pop     r13
0x180059460  pop     r12
0x180059462  pop     rdi
0x180059463  pop     rsi
0x180059464  pop     rbx
0x180059465  pop     rbp
0x180059466  retn
```
