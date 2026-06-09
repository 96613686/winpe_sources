# CInplaceShareEngine::CanShareItem(IShellItem *,int *)

- ea: `0x180012160`
- end: `0x18001232e`
- name: `?CanShareItem@CInplaceShareEngine@@UEAAJPEAUIShellItem@@PEAH@Z`
- size: `462`
- prototype: `__int64 __fastcall(CInplaceShareEngine *__hidden this, struct IShellItem *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18000bdc0`
- `0x180012160`
- `0x180012340`
- `0x180012678`
- `0x18001b05c`
- `0x18001d7b4`
- `0x180022734`
- `0x1800254e0`
- `0x18005e0a0`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1800121d4`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001228c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1800121d4`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18001228c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012238`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180012300`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x1800121e7`
- `SHCORE!__imp_PathIsNetworkPathW` at `0x1800121e7`
- `SHELL32!__imp_PathComparePaths` at `0x1800122a6`
- `SHELL32!__imp_PathComparePaths` at `0x1800122a6`
- `SHLWAPI!PathIsRootW` at `0x1800121f6`
- `SHLWAPI!PathIsRootW` at `0x1800121f6`

## pseudocode

```c
__int64 __fastcall CInplaceShareEngine::CanShareItem(WCHAR *this, struct IShellItem *a2, int *a3)
{
  int LocalPathForItemIfPossible; // edi
  const WCHAR *v7; // r14
  __int64 v8; // r8
  __int64 v10; // r9
  int IsUnderSmbShare; // eax
  void *v12; // rcx
  LPCWSTR pszPath; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR v15[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+240h] [rbp+140h] BYREF

  *a3 = 0;
  pszPath = 0;
  LocalPathForItemIfPossible = GetLocalPathForItemIfPossible(a2, &pszPath);
  if ( LocalPathForItemIfPossible >= 0 )
  {
    v7 = pszPath;
    if ( PathCchCanonicalize(pszPathOut, 0x104u, this + 556) >= 0
      && PathCchCanonicalize(v15, 0x104u, v7) >= 0
      && (PathComparePaths(pszPathOut, v15) & 8) != 0 )
    {
      *a3 = 1;
      CInplaceShareEngine::_DoesUsersShareExist((CInplaceShareEngine *)this);
    }
    else
    {
      if ( PathIsNetworkPathW(pszPath) )
      {
        v10 = 13;
      }
      else
      {
        if ( !PathIsRootW(pszPath) )
        {
          if ( (unsigned int)CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(pszPath) )
          {
            pv = 0;
            LocalPathForItemIfPossible = GetIdentityItemName(a2, SIGDN_FILESYSPATH, (unsigned __int16 **)&pv);
            if ( LocalPathForItemIfPossible >= 0 )
            {
              IsUnderSmbShare = CInplaceShareEngine::_IsUnderSmbShare(
                                  (CInplaceShareEngine *)this,
                                  (const unsigned __int16 *)pv);
              v12 = pv;
              *a3 = IsUnderSmbShare;
              CoTaskMemFree(v12);
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v8, pszPath);
          }
          goto LABEL_9;
        }
        v10 = 7;
      }
      CFolderAclEngine::_ReportShareEvent(this + 8, pszPath, pszPath, v10);
    }
LABEL_9:
    CoTaskMemFree((LPVOID)pszPath);
  }
  return (unsigned int)LocalPathForItemIfPossible;
}

```

## disassembly

```asm
0x180012160  mov     [rsp-8+arg_18], rbx
0x180012165  push    rbp
0x180012166  push    rsi
0x180012167  push    rdi
0x180012168  push    r14
0x18001216a  push    r15
0x18001216c  lea     rbp, [rsp-360h]
0x180012174  sub     rsp, 460h
0x18001217b  mov     rax, cs:__security_cookie
0x180012182  xor     rax, rsp
0x180012185  mov     [rbp+380h+var_30], rax
0x18001218c  mov     r15, rdx
0x18001218f  mov     dword ptr [r8], 0
0x180012196  mov     rbx, rcx
0x180012199  mov     [rsp+480h+pszPath], 0
0x1800121a2  mov     rcx, r15
0x1800121a5  lea     rdx, [rsp+480h+pszPath]
0x1800121aa  mov     rsi, r8
0x1800121ad  call    GetLocalPathForItemIfPossible
0x1800121b2  mov     edi, eax
0x1800121b4  test    eax, eax
0x1800121b6  js      loc_18001223E
0x1800121bc  mov     r14, [rsp+480h+pszPath]
0x1800121c1  lea     r8, [rbx+458h]; pszPathIn
0x1800121c8  mov     edx, 104h; cchPathOut
0x1800121cd  lea     rcx, [rbp+380h+pszPathOut]; pszPathOut
0x1800121d4  call    cs:__imp_PathCchCanonicalize
0x1800121da  test    eax, eax
0x1800121dc  jns     loc_18001227F
0x1800121e2  mov     rcx, [rsp+480h+pszPath]; pszPath
0x1800121e7  call    cs:__imp_PathIsNetworkPathW
0x1800121ed  test    eax, eax
0x1800121ef  jnz     short loc_180012266
0x1800121f1  mov     rcx, [rsp+480h+pszPath]; pszPath
0x1800121f6  call    cs:__imp_PathIsRootW
0x1800121fc  test    eax, eax
0x1800121fe  jnz     loc_180012323
0x180012204  mov     rcx, [rsp+480h+pszPath]; unsigned __int16 *
0x180012209  call    ?s_DoesVolumeSupportFileSystemAcls@CFolderAclEngine@@SAHPEBG@Z; CFolderAclEngine::s_DoesVolumeSupportFileSystemAcls(ushort const *)
0x18001220e  test    eax, eax
0x180012210  jnz     loc_1800122C7
0x180012216  mov     rcx, cs:WPP_GLOBAL_Control
0x18001221d  lea     rax, WPP_GLOBAL_Control
0x180012224  cmp     rcx, rax
0x180012227  jz      short loc_180012233
0x180012229  test    byte ptr [rcx+1Ch], 4
0x18001222d  jnz     loc_18001230B
0x180012233  mov     rcx, [rsp+480h+pszPath]; pv
0x180012238  call    cs:__imp_CoTaskMemFree
0x18001223e  mov     eax, edi
0x180012240  mov     rcx, [rbp+380h+var_30]
0x180012247  xor     rcx, rsp; StackCookie
0x18001224a  call    __security_check_cookie
0x18001224f  mov     rbx, [rsp+480h+arg_18]
0x180012257  add     rsp, 460h
0x18001225e  pop     r15
0x180012260  pop     r14
0x180012262  pop     rdi
0x180012263  pop     rsi
0x180012264  pop     rbp
0x180012265  retn
0x180012266  mov     r9d, 0Dh
0x18001226c  mov     rdx, [rsp+480h+pszPath]
0x180012271  lea     rcx, [rbx+10h]
0x180012275  mov     r8, rdx
0x180012278  call    ?_ReportShareEvent@CFolderAclEngine@@IEAAXPEBG0W4_tagSHARE_EVENT@@@Z; CFolderAclEngine::_ReportShareEvent(ushort const *,ushort const *,_tagSHARE_EVENT)
0x18001227d  jmp     short loc_180012233
0x18001227f  mov     r8, r14; pszPathIn
0x180012282  lea     rcx, [rsp+480h+var_450]; pszPathOut
0x180012287  mov     edx, 104h; cchPathOut
0x18001228c  call    cs:__imp_PathCchCanonicalize
0x180012292  test    eax, eax
0x180012294  js      loc_1800121E2
0x18001229a  lea     rdx, [rsp+480h+var_450]
0x18001229f  lea     rcx, [rbp+380h+pszPathOut]
0x1800122a6  call    cs:__imp_PathComparePaths
0x1800122ac  test    al, 8
0x1800122ae  jz      loc_1800121E2
0x1800122b4  mov     rcx, rbx; this
0x1800122b7  mov     dword ptr [rsi], 1
0x1800122bd  call    ?_DoesUsersShareExist@CInplaceShareEngine@@AEAAHXZ; CInplaceShareEngine::_DoesUsersShareExist(void)
0x1800122c2  jmp     loc_180012233
0x1800122c7  lea     r8, [rsp+480h+pv]; unsigned __int16 **
0x1800122cc  mov     [rsp+480h+pv], 0
0x1800122d5  mov     edx, 80058000h; enum _SIGDN
0x1800122da  mov     rcx, r15; struct IShellItem *
0x1800122dd  call    ?GetIdentityItemName@@YAJPEAUIShellItem@@W4_SIGDN@@PEAPEAG@Z; GetIdentityItemName(IShellItem *,_SIGDN,ushort * *)
0x1800122e2  mov     edi, eax
0x1800122e4  test    eax, eax
0x1800122e6  js      loc_180012233
0x1800122ec  mov     rdx, [rsp+480h+pv]; unsigned __int16 *
0x1800122f1  mov     rcx, rbx; this
0x1800122f4  call    ?_IsUnderSmbShare@CInplaceShareEngine@@AEAAHPEBG@Z; CInplaceShareEngine::_IsUnderSmbShare(ushort const *)
0x1800122f9  mov     rcx, [rsp+480h+pv]; pv
0x1800122fe  mov     [rsi], eax
0x180012300  call    cs:__imp_CoTaskMemFree
0x180012306  jmp     loc_180012233
0x18001230b  mov     r9, [rsp+480h+pszPath]
0x180012310  mov     edx, 1Fh
0x180012315  mov     rcx, [rcx+10h]
0x180012319  call    WPP_SF_S
0x18001231e  jmp     loc_180012233
0x180012323  mov     r9d, 7
0x180012329  jmp     loc_18001226C
```
