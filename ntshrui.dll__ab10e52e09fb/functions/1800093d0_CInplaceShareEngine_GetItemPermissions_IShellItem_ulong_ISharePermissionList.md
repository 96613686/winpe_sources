# CInplaceShareEngine::GetItemPermissions(IShellItem *,ulong,ISharePermissionList * *)

- ea: `0x1800093d0`
- end: `0x18000959a`
- name: `?GetItemPermissions@CInplaceShareEngine@@UEAAJPEAUIShellItem@@KPEAPEAUISharePermissionList@@@Z`
- size: `458`
- prototype: `__int64 __fastcall(CInplaceShareEngine *__hidden this, struct IShellItem *, unsigned int, struct ISharePermissionList **)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180008f68`
- `0x1800093d0`
- `0x1800095a0`
- `0x18000ac90`
- `0x18000d1f0`
- `0x18000e8b0`
- `0x1800254e0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000954d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000954d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000956c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000956c`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x1800094bc`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x1800094bc`
- `SHLWAPI!PathIsRootW` at `0x1800094a9`
- `SHLWAPI!PathIsRootW` at `0x1800094a9`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::GetItemPermissions(
        CInplaceShareEngine *this,
        struct IShellItem *a2,
        int a3,
        struct ISharePermissionList **a4)
{
  char v6; // si
  int Related; // ebx
  int v8; // r14d
  CFolderAclEngine *v9; // rcx
  int UncPath; // eax
  CAceList *v11; // rdi
  unsigned int v12; // edx
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR pszPath; // [rsp+38h] [rbp-C8h] BYREF
  struct CAceList *v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v17[264]; // [rsp+50h] [rbp-B0h] BYREF

  *a4 = 0;
  pszPath = 0;
  hMem = 0;
  v6 = a3;
  Related = GetRelatedItem<IIdentityName>((_DWORD)a2, (_DWORD)a2, a3, (_DWORD)a4, (__int64)&hMem);
  if ( Related >= 0 )
  {
    LODWORD(v16[0]) = 0;
    v8 = 0;
    Related = (*(__int64 (__fastcall **)(HLOCAL, __int64, struct CAceList **))(*(_QWORD *)hMem + 48LL))(
                hMem,
                541065216,
                v16);
    if ( Related >= 0 )
    {
      Related = (*(__int64 (__fastcall **)(HLOCAL, __int64, LPCWSTR *))(*(_QWORD *)hMem + 40LL))(
                  hMem,
                  2147844096LL,
                  &pszPath);
      if ( Related >= 0 )
        v8 = (int)v16[0];
    }
    (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
    if ( Related >= 0 )
    {
      if ( PathIsRootW(pszPath) || PathIsNetworkPathW(pszPath) )
      {
        Related = -2147467259;
      }
      else
      {
        v16[0] = 0;
        hMem = 0;
        Related = CFolderAclEngine::_GetAcl(v9, pszPath, v16, &hMem, 0);
        if ( Related >= 0 )
        {
          UncPath = CInplaceShareEngine::_GetUncPath((CInplaceShareEngine *)((char *)this - 8), pszPath, v17);
          v11 = v16[0];
          Related = 1;
          if ( UncPath >= 0 )
            Related = CSharePermissionList_CreateFromAcl(hMem, v16[0], v8 == 0x20000000, (v6 & 1) == 0, 1, a4);
          LocalFree(hMem);
          if ( v11 )
            CAceList::`scalar deleting destructor'(v11, v12);
        }
      }
      CoTaskMemFree((LPVOID)pszPath);
    }
  }
  return (unsigned int)Related;
}

```

## disassembly

```asm
0x1800093d0  mov     [rsp-8+arg_10], rbx
0x1800093d5  push    rbp
0x1800093d6  push    rsi
0x1800093d7  push    rdi
0x1800093d8  push    r14
0x1800093da  push    r15
0x1800093dc  lea     rbp, [rsp-170h]
0x1800093e4  sub     rsp, 270h
0x1800093eb  mov     rax, cs:__security_cookie
0x1800093f2  xor     rax, rsp
0x1800093f5  mov     [rbp+190h+var_30], rax
0x1800093fc  mov     rdi, rcx
0x1800093ff  mov     qword ptr [r9], 0
0x180009406  lea     rax, [rsp+290h+hMem]
0x18000940b  mov     [rsp+290h+pszPath], 0
0x180009414  mov     rcx, rdx
0x180009417  mov     qword ptr [rsp+290h+var_270], rax
0x18000941c  mov     r15, r9
0x18000941f  mov     [rsp+290h+hMem], 0
0x180009428  mov     esi, r8d
0x18000942b  call    ??$GetRelatedItem@UIIdentityName@@@@YAJPEAUIShellItem@@PEAUIBindCtx@@_NAEBU_GUID@@PEAPEAX@Z; GetRelatedItem<IIdentityName>(IShellItem *,IBindCtx *,bool,_GUID const &,void * *)
0x180009430  mov     ebx, eax
0x180009432  test    eax, eax
0x180009434  js      loc_180009572
0x18000943a  mov     rcx, [rsp+290h+hMem]
0x18000943f  lea     r8, [rsp+290h+var_250]
0x180009444  mov     dword ptr [rsp+290h+var_250], 0
0x18000944c  mov     edx, 20400000h
0x180009451  mov     rax, [rcx]
0x180009454  mov     rax, [rax+30h]
0x180009458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945d  xor     r14d, r14d
0x180009460  mov     ebx, eax
0x180009462  test    eax, eax
0x180009464  js      short loc_18000948B
0x180009466  mov     rcx, [rsp+290h+hMem]
0x18000946b  lea     r8, [rsp+290h+pszPath]
0x180009470  mov     edx, 80058000h
0x180009475  mov     rax, [rcx]
0x180009478  mov     rax, [rax+28h]
0x18000947c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009481  test    eax, eax
0x180009483  mov     ebx, eax
0x180009485  cmovns  r14d, dword ptr [rsp+290h+var_250]
0x18000948b  mov     rcx, [rsp+290h+hMem]
0x180009490  mov     rax, [rcx]
0x180009493  mov     rax, [rax+10h]
0x180009497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000949c  test    ebx, ebx
0x18000949e  js      loc_180009572
0x1800094a4  mov     rcx, [rsp+290h+pszPath]; pszPath
0x1800094a9  call    cs:__imp_PathIsRootW
0x1800094af  test    eax, eax
0x1800094b1  jnz     loc_180009562
0x1800094b7  mov     rcx, [rsp+290h+pszPath]; pszPath
0x1800094bc  call    cs:__imp_PathIsNetworkPathW
0x1800094c2  test    eax, eax
0x1800094c4  jnz     loc_180009562
0x1800094ca  mov     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x1800094cf  lea     r9, [rsp+290h+hMem]; void **
0x1800094d4  lea     r8, [rsp+290h+var_250]; struct CAceList **
0x1800094d9  mov     [rsp+290h+var_250], 0
0x1800094e2  mov     [rsp+290h+hMem], 0
0x1800094eb  mov     [rsp+290h+var_270], eax; int
0x1800094ef  call    ?_GetAcl@CFolderAclEngine@@IEAAJPEBGPEAPEAVCAceList@@PEAPEAXH@Z; CFolderAclEngine::_GetAcl(ushort const *,CAceList * *,void * *,int)
0x1800094f4  mov     ebx, eax
0x1800094f6  test    eax, eax
0x1800094f8  js      short loc_180009567
0x1800094fa  mov     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x1800094ff  lea     rcx, [rdi-8]; this
0x180009503  lea     r8, [rsp+290h+var_240]; unsigned __int16 *
0x180009508  call    ?_GetUncPath@CInplaceShareEngine@@AEAAJPEBGPEAGK@Z; CInplaceShareEngine::_GetUncPath(ushort const *,ushort *,ulong)
0x18000950d  mov     rdi, [rsp+290h+var_250]
0x180009512  mov     ebx, 1
0x180009517  test    eax, eax
0x180009519  js      short loc_180009548
0x18000951b  mov     rcx, [rsp+290h+hMem]; void *
0x180009520  xor     r8d, r8d
0x180009523  not     esi
0x180009525  mov     [rsp+290h+var_268], r15; struct ISharePermissionList **
0x18000952a  and     esi, ebx
0x18000952c  mov     [rsp+290h+var_270], ebx; int
0x180009530  cmp     r14d, 20000000h
0x180009537  mov     r9d, esi; int
0x18000953a  mov     rdx, rdi; struct CAceList *
0x18000953d  setz    r8b; int
0x180009541  call    ?CSharePermissionList_CreateFromAcl@@YAJPEAXPEAVCAceList@@HHHPEAPEAUISharePermissionList@@@Z; CSharePermissionList_CreateFromAcl(void *,CAceList *,int,int,int,ISharePermissionList * *)
0x180009546  mov     ebx, eax
0x180009548  mov     rcx, [rsp+290h+hMem]; hMem
0x18000954d  call    cs:__imp_LocalFree
0x180009553  test    rdi, rdi
0x180009556  jz      short loc_180009567
0x180009558  mov     rcx, rdi; this
0x18000955b  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x180009560  jmp     short loc_180009567
0x180009562  mov     ebx, 80004005h
0x180009567  mov     rcx, [rsp+290h+pszPath]; pv
0x18000956c  call    cs:__imp_CoTaskMemFree
0x180009572  mov     eax, ebx
0x180009574  mov     rcx, [rbp+190h+var_30]
0x18000957b  xor     rcx, rsp; StackCookie
0x18000957e  call    __security_check_cookie
0x180009583  mov     rbx, [rsp+290h+arg_10]
0x18000958b  add     rsp, 270h
0x180009592  pop     r15
0x180009594  pop     r14
0x180009596  pop     rdi
0x180009597  pop     rsi
0x180009598  pop     rbp
0x180009599  retn
```
