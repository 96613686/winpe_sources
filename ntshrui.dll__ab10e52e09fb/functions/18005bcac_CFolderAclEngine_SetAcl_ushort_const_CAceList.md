# CFolderAclEngine::_SetAcl(ushort const *,CAceList *)

- ea: `0x18005bcac`
- end: `0x18005be51`
- name: `?_SetAcl@CFolderAclEngine@@IEAAJPEBGPEAVCAceList@@@Z`
- size: `421`
- prototype: `int(CFolderAclEngine *__hidden this, const unsigned __int16 *, struct CAceList *)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005a044`
- `0x18005c1d0`
- `0x18005c398`

## callees

- `0x18000ac90`
- `0x18000d1f0`
- `0x180013220`
- `0x18001c4a8`
- `0x180023adc`
- `0x1800254e0`
- `0x180056420`
- `0x180056ce4`
- `0x18005bcac`
- `0x18005e1c8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bdf9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005bdf9`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005bd04`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005bd04`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18005bdb2`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18005bdb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFolderAclEngine::_SetAcl(CFolderAclEngine *this, unsigned __int16 *a2, struct CAceList *a3)
{
  CFolderAclEngine *v6; // rcx
  int AclForExplicitEntries; // ebx
  int v8; // r8d
  unsigned int v9; // edx
  SECURITY_INFORMATION v10; // r8d
  PACL v11; // rdi
  signed int v12; // eax
  IUnknown *v13; // r8
  PACL pDacl; // [rsp+40h] [rbp-C0h] BYREF
  struct CAceList *v16; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF

  pDacl = 0;
  if ( *((_DWORD *)a3 + 6) )
  {
    AclForExplicitEntries = CAceList::GetAclForExplicitEntries(a3, a2, &pDacl);
  }
  else
  {
    StringCchCopyW(pszPath, 0x104u, a2);
    PathRemoveFileSpecW(pszPath);
    v16 = 0;
    AclForExplicitEntries = CFolderAclEngine::_GetAcl(v6, pszPath, &v16, 0, 0);
    if ( AclForExplicitEntries < 0 )
    {
LABEL_13:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, v8, (_DWORD)a2, AclForExplicitEntries);
      return (unsigned int)AclForExplicitEntries;
    }
    AclForExplicitEntries = CAceList::GetAclForExplicitEntriesWithInheritanceCheck(a3, v16, &pDacl);
    if ( v16 )
      CAceList::`scalar deleting destructor'(v16, v9);
  }
  if ( AclForExplicitEntries < 0 )
    goto LABEL_13;
  v10 = *((_DWORD *)a3 + 6) != 0 ? 536870916 : -2147483644;
  v11 = pDacl;
  v12 = SetNamedSecurityInfoW(a2, SE_FILE_OBJECT, v10, 0, 0, pDacl, 0);
  AclForExplicitEntries = v12;
  if ( v12 > 0 )
    AclForExplicitEntries = (unsigned __int16)v12 | 0x80070000;
  if ( AclForExplicitEntries >= 0 )
  {
    v13 = (IUnknown *)*((_QWORD *)this + 1);
    if ( v13 )
    {
      pDacl = 0;
      AclForExplicitEntries = CAclInheritanceChecker::InitAndCheckInheritance((CAclInheritanceChecker *)&pDacl, a2, v13);
      ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&pDacl);
    }
  }
  LocalFree(v11);
  if ( AclForExplicitEntries < 0 )
    goto LABEL_13;
  return (unsigned int)AclForExplicitEntries;
}

```

## disassembly

```asm
0x18005bcac  push    rbp
0x18005bcae  push    rbx
0x18005bcaf  push    rdi
0x18005bcb0  push    r14
0x18005bcb2  push    r15
0x18005bcb4  lea     rbp, [rsp-170h]
0x18005bcbc  sub     rsp, 270h
0x18005bcc3  mov     rax, cs:__security_cookie
0x18005bcca  xor     rax, rsp
0x18005bccd  mov     [rbp+190h+var_30], rax
0x18005bcd4  mov     rdi, r8
0x18005bcd7  mov     r14, rdx
0x18005bcda  mov     r15, rcx
0x18005bcdd  mov     [rsp+290h+var_250], 0
0x18005bce6  cmp     dword ptr [r8+18h], 0
0x18005bceb  jnz     short loc_18005BD5F
0x18005bced  mov     r8, rdx; unsigned __int16 *
0x18005bcf0  mov     edx, 104h; unsigned __int64
0x18005bcf5  lea     rcx, [rsp+290h+pszPath]; unsigned __int16 *
0x18005bcfa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005bcff  lea     rcx, [rsp+290h+pszPath]; pszPath
0x18005bd04  call    cs:__imp_PathRemoveFileSpecW
0x18005bd0a  mov     [rsp+290h+var_248], 0
0x18005bd13  mov     dword ptr [rsp+290h+psidGroup], 0; int
0x18005bd1b  xor     r9d, r9d; void **
0x18005bd1e  lea     r8, [rsp+290h+var_248]; struct CAceList **
0x18005bd23  lea     rdx, [rsp+290h+pszPath]; unsigned __int16 *
0x18005bd28  call    ?_GetAcl@CFolderAclEngine@@IEAAJPEBGPEAPEAVCAceList@@PEAPEAXH@Z; CFolderAclEngine::_GetAcl(ushort const *,CAceList * *,void * *,int)
0x18005bd2d  mov     ebx, eax
0x18005bd2f  test    eax, eax
0x18005bd31  js      loc_18005BE03
0x18005bd37  lea     r8, [rsp+290h+var_250]; struct _ACL **
0x18005bd3c  mov     rdx, [rsp+290h+var_248]; struct CAceList *
0x18005bd41  mov     rcx, rdi; this
0x18005bd44  call    ?GetAclForExplicitEntriesWithInheritanceCheck@CAceList@@QEAAJPEAV1@PEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntriesWithInheritanceCheck(CAceList *,_ACL * *)
0x18005bd49  mov     ebx, eax
0x18005bd4b  cmp     [rsp+290h+var_248], 0
0x18005bd51  jz      short loc_18005BD6E
0x18005bd53  mov     rcx, [rsp+290h+var_248]; this
0x18005bd58  call    ??_GCAceList@@QEAAPEAXI@Z; CAceList::`scalar deleting destructor'(uint)
0x18005bd5d  jmp     short loc_18005BD6E
0x18005bd5f  lea     r8, [rsp+290h+var_250]; struct _ACL **
0x18005bd64  mov     rcx, rdi; this
0x18005bd67  call    ?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z; CAceList::GetAclForExplicitEntries(void *,_ACL * *)
0x18005bd6c  mov     ebx, eax
0x18005bd6e  test    ebx, ebx
0x18005bd70  js      loc_18005BE03
0x18005bd76  mov     eax, [rdi+18h]
0x18005bd79  neg     eax
0x18005bd7b  sbb     r8d, r8d
0x18005bd7e  and     r8d, 0A0000000h
0x18005bd85  add     r8d, 80000004h; SecurityInfo
0x18005bd8c  mov     [rsp+290h+pSacl], 0; pSacl
0x18005bd95  mov     rdi, [rsp+290h+var_250]
0x18005bd9a  mov     [rsp+290h+pDacl], rdi; pDacl
0x18005bd9f  mov     [rsp+290h+psidGroup], 0; psidGroup
0x18005bda8  xor     r9d, r9d; psidOwner
0x18005bdab  lea     edx, [r9+1]; ObjectType
0x18005bdaf  mov     rcx, r14; pObjectName
0x18005bdb2  call    cs:__imp_SetNamedSecurityInfoW
0x18005bdb8  mov     ebx, eax
0x18005bdba  test    eax, eax
0x18005bdbc  jle     short loc_18005BDC7
0x18005bdbe  movzx   ebx, ax
0x18005bdc1  or      ebx, 80070000h
0x18005bdc7  test    ebx, ebx
0x18005bdc9  js      short loc_18005BDF6
0x18005bdcb  mov     r8, [r15+8]; punk
0x18005bdcf  test    r8, r8
0x18005bdd2  jz      short loc_18005BDF6
0x18005bdd4  mov     [rsp+290h+var_250], 0
0x18005bddd  mov     rdx, r14; unsigned __int16 *
0x18005bde0  lea     rcx, [rsp+290h+var_250]; this
0x18005bde5  call    ?InitAndCheckInheritance@CAclInheritanceChecker@@QEAAJPEBGPEAUIShareProgressSink@@@Z; CAclInheritanceChecker::InitAndCheckInheritance(ushort const *,IShareProgressSink *)
0x18005bdea  mov     ebx, eax
0x18005bdec  lea     rcx, [rsp+290h+var_250]
0x18005bdf1  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18005bdf6  mov     rcx, rdi; hMem
0x18005bdf9  call    cs:__imp_LocalFree
0x18005bdff  test    ebx, ebx
0x18005be01  jns     short loc_18005BE31
0x18005be03  lea     rax, WPP_GLOBAL_Control
0x18005be0a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005be11  cmp     rcx, rax
0x18005be14  jz      short loc_18005BE31
0x18005be16  test    byte ptr [rcx+1Ch], 2
0x18005be1a  jz      short loc_18005BE31
0x18005be1c  mov     edx, 0Bh
0x18005be21  mov     dword ptr [rsp+290h+psidGroup], ebx
0x18005be25  mov     r9, r14
0x18005be28  mov     rcx, [rcx+10h]
0x18005be2c  call    WPP_SF_Sd
0x18005be31  mov     eax, ebx
0x18005be33  mov     rcx, [rbp+190h+var_30]
0x18005be3a  xor     rcx, rsp; StackCookie
0x18005be3d  call    __security_check_cookie
0x18005be42  add     rsp, 270h
0x18005be49  pop     r15
0x18005be4b  pop     r14
0x18005be4d  pop     rdi
0x18005be4e  pop     rbx
0x18005be4f  pop     rbp
0x18005be50  retn
```
