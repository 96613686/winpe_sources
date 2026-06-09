# BrowseForDirectory

- ea: `0x18000d450`
- end: `0x18000d6b3`
- name: `BrowseForDirectory`
- size: `611`
- prototype: `__int64 __usercall@<rax>(HWND hDlg@<rcx>, int nIDDlgItem@<edx>, int)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800117e0`
- `0x180014df8`

## callees

- `0x180005eac`
- `0x180005ed4`
- `0x18000d450`
- `0x180015cf0`
- `0x180017010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000d569`
- `KERNEL32!SetLastError` at `0x18000d68a`
- `KERNEL32!SetLastError` at `0x18000d569`
- `KERNEL32!SetLastError` at `0x18000d68a`
- `SHELL32!SHGetPathFromIDListW` at `0x18000d61a`
- `SHELL32!SHGetPathFromIDListW` at `0x18000d61a`
- `SHELL32!SHGetMalloc` at `0x18000d59f`
- `SHELL32!SHGetMalloc` at `0x18000d59f`
- `SHELL32!SHBrowseForFolderW` at `0x18000d604`
- `SHELL32!SHBrowseForFolderW` at `0x18000d604`
- `ole32!CoInitializeEx` at `0x18000d51a`
- `ole32!CoInitializeEx` at `0x18000d51a`
- `ole32!CoUninitialize` at `0x18000d682`
- `ole32!CoUninitialize` at `0x18000d682`
- `USER32!SetDlgItemTextW` at `0x18000d652`
- `USER32!SetDlgItemTextW` at `0x18000d652`
- `USER32!GetDlgItemTextW` at `0x18000d587`
- `USER32!GetDlgItemTextW` at `0x18000d587`

## pseudocode

```c
__int64 __fastcall BrowseForDirectory(HWND hDlg, int nIDDlgItem, __int64 a3, const WCHAR *a4, UINT a5)
{
  UINT ulFlags; // eax
  HRESULT v8; // eax
  DWORD v9; // ebx
  unsigned int v11; // esi
  HRESULT v12; // ebx
  const ITEMIDLIST *v13; // rax
  const ITEMIDLIST *v14; // rdi
  unsigned __int64 v15; // rcx
  IMalloc *ppMalloc; // [rsp+20h] [rbp-E0h] BYREF
  _browseinfoW bi; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR String[264]; // [rsp+70h] [rbp-90h] BYREF

  bi.hwndOwner = hDlg;
  ppMalloc = 0;
  bi.pidlRoot = 0;
  *(&bi.ulFlags + 1) = 0;
  bi.pszDisplayName = String;
  ulFlags = a5;
  bi.lpfn = (BFFCALLBACK)BrowseFolderCallbackProc;
  bi.lParam = (LPARAM)String;
  bi.lpszTitle = a4;
  bi.ulFlags = a5;
  *(_QWORD *)&bi.iImage = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids);
    ulFlags = bi.ulFlags;
  }
  if ( !ulFlags )
    ulFlags = 65;
  bi.ulFlags = ulFlags;
  v8 = CoInitializeEx(0, 2u);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( !GetDlgItemTextW(hDlg, nIDDlgItem, String, 260) )
      String[0] = 0;
    v11 = 0;
    v12 = SHGetMalloc(&ppMalloc);
    if ( v12 >= 0 )
    {
      v12 = 0;
      v13 = SHBrowseForFolderW(&bi);
      v14 = v13;
      if ( v13 )
      {
        if ( SHGetPathFromIDListW(v13, String) )
        {
          v15 = -1;
          do
            ++v15;
          while ( String[v15] );
          if ( v15 <= 0xB4 )
          {
            SetDlgItemTextW(hDlg, nIDDlgItem, String);
            v11 = 1;
          }
          else
          {
            v12 = 122;
          }
        }
        ((void (__fastcall *)(IMalloc *, const ITEMIDLIST *))ppMalloc->lpVtbl->Free)(ppMalloc, v14);
      }
      ((void (__fastcall *)(IMalloc *))ppMalloc->lpVtbl->Release)(ppMalloc);
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          114,
          WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
          (unsigned int)v12);
      }
      if ( (v12 & 0x1FFF0000) == 0x70000 )
        v12 = (unsigned __int16)v12;
    }
    CoUninitialize();
    SetLastError(v12);
    return v11;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        113,
        WPP_c16f0c0a47d9333974be9389587270d1_Traceguids,
        (unsigned int)v8);
    }
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      v9 = (unsigned __int16)v9;
    SetLastError(v9);
    return 0;
  }
}

```

## disassembly

```asm
0x18000d450  push    rbp
0x18000d452  push    rbx
0x18000d453  push    rsi
0x18000d454  push    rdi
0x18000d455  push    r12
0x18000d457  push    r14
0x18000d459  push    r15
0x18000d45b  lea     rbp, [rsp-190h]
0x18000d463  sub     rsp, 290h
0x18000d46a  mov     rax, cs:__security_cookie
0x18000d471  xor     rax, rsp
0x18000d474  mov     [rbp+1C0h+var_40], rax
0x18000d47b  xor     r12d, r12d
0x18000d47e  mov     [rsp+2C0h+bi.hwndOwner], rcx
0x18000d483  mov     r14, rcx
0x18000d486  mov     [rsp+2C0h+ppMalloc], r12
0x18000d48b  xor     ecx, ecx
0x18000d48d  mov     [rsp+2C0h+bi.pidlRoot], r12
0x18000d492  mov     dword ptr [rsp+2C0h+bi+24h], ecx
0x18000d496  lea     rax, [rsp+2C0h+String]
0x18000d49b  lea     rcx, ?BrowseFolderCallbackProc@@YAHPEAUHWND__@@I_J1@Z; BrowseFolderCallbackProc(HWND__ *,uint,__int64,__int64)
0x18000d4a2  mov     [rsp+2C0h+bi.pszDisplayName], rax
0x18000d4a7  mov     eax, [rbp+1C0h+arg_20]
0x18000d4ad  mov     r15d, edx
0x18000d4b0  mov     [rsp+2C0h+bi.lpfn], rcx
0x18000d4b5  lea     rcx, [rsp+2C0h+String]
0x18000d4ba  mov     [rsp+2C0h+bi.lParam], rcx
0x18000d4bf  mov     [rsp+2C0h+bi.lpszTitle], r9
0x18000d4c4  mov     [rsp+2C0h+bi.ulFlags], eax
0x18000d4c8  mov     qword ptr [rsp+2C0h+bi.iImage], r12
0x18000d4cd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d4d4  lea     rsi, WPP_GLOBAL_Control
0x18000d4db  lea     edi, [r12+2]
0x18000d4e0  cmp     rcx, rsi
0x18000d4e3  jz      short loc_18000D508
0x18000d4e5  test    [rcx+1Ch], dil
0x18000d4e9  jz      short loc_18000D508
0x18000d4eb  cmp     byte ptr [rcx+19h], 5
0x18000d4ef  jb      short loc_18000D508
0x18000d4f1  mov     rcx, [rcx+10h]
0x18000d4f5  lea     edx, [rdi+6Eh]
0x18000d4f8  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18000d4ff  call    WPP_SF_
0x18000d504  mov     eax, [rsp+2C0h+bi.ulFlags]
0x18000d508  test    eax, eax
0x18000d50a  mov     ecx, 41h ; 'A'
0x18000d50f  mov     edx, edi; dwCoInit
0x18000d511  cmovz   eax, ecx
0x18000d514  xor     ecx, ecx; pvReserved
0x18000d516  mov     [rsp+2C0h+bi.ulFlags], eax
0x18000d51a  call    cs:__imp_CoInitializeEx
0x18000d520  mov     ebx, eax
0x18000d522  test    eax, eax
0x18000d524  jns     short loc_18000D576
0x18000d526  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d52d  cmp     rcx, rsi
0x18000d530  jz      short loc_18000D556
0x18000d532  test    [rcx+1Ch], dil
0x18000d536  jz      short loc_18000D556
0x18000d538  cmp     [rcx+19h], dil
0x18000d53c  jb      short loc_18000D556
0x18000d53e  mov     rcx, [rcx+10h]
0x18000d542  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18000d549  mov     edx, 71h ; 'q'
0x18000d54e  mov     r9d, eax
0x18000d551  call    WPP_SF_d
0x18000d556  mov     eax, ebx
0x18000d558  and     eax, 1FFF0000h
0x18000d55d  cmp     eax, 70000h
0x18000d562  jnz     short loc_18000D567
0x18000d564  movzx   ebx, bx
0x18000d567  mov     ecx, ebx; dwErrCode
0x18000d569  call    cs:__imp_SetLastError
0x18000d56f  xor     eax, eax
0x18000d571  jmp     loc_18000D692
0x18000d576  mov     r9d, 104h; cchMax
0x18000d57c  lea     r8, [rsp+2C0h+String]; lpString
0x18000d581  mov     edx, r15d; nIDDlgItem
0x18000d584  mov     rcx, r14; hDlg
0x18000d587  call    cs:__imp_GetDlgItemTextW
0x18000d58d  test    eax, eax
0x18000d58f  jnz     short loc_18000D597
0x18000d591  mov     [rsp+2C0h+String], r12w
0x18000d597  lea     rcx, [rsp+2C0h+ppMalloc]; ppMalloc
0x18000d59c  mov     esi, r12d
0x18000d59f  call    cs:__imp_SHGetMalloc
0x18000d5a5  mov     ebx, eax
0x18000d5a7  test    eax, eax
0x18000d5a9  jns     short loc_18000D5FC
0x18000d5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d5b2  lea     rax, WPP_GLOBAL_Control
0x18000d5b9  cmp     rcx, rax
0x18000d5bc  jz      short loc_18000D5E2
0x18000d5be  test    [rcx+1Ch], dil
0x18000d5c2  jz      short loc_18000D5E2
0x18000d5c4  cmp     [rcx+19h], dil
0x18000d5c8  jb      short loc_18000D5E2
0x18000d5ca  mov     rcx, [rcx+10h]
0x18000d5ce  lea     r8, WPP_c16f0c0a47d9333974be9389587270d1_Traceguids
0x18000d5d5  mov     edx, 72h ; 'r'
0x18000d5da  mov     r9d, ebx
0x18000d5dd  call    WPP_SF_d
0x18000d5e2  mov     eax, ebx
0x18000d5e4  and     eax, 1FFF0000h
0x18000d5e9  cmp     eax, 70000h
0x18000d5ee  jnz     loc_18000D682
0x18000d5f4  movzx   ebx, bx
0x18000d5f7  jmp     loc_18000D682
0x18000d5fc  lea     rcx, [rsp+2C0h+bi]; lpbi
0x18000d601  mov     ebx, r12d
0x18000d604  call    cs:__imp_SHBrowseForFolderW
0x18000d60a  mov     rdi, rax
0x18000d60d  test    rax, rax
0x18000d610  jz      short loc_18000D671
0x18000d612  lea     rdx, [rsp+2C0h+String]; pszPath
0x18000d617  mov     rcx, rax; pidl
0x18000d61a  call    cs:__imp_SHGetPathFromIDListW
0x18000d620  test    eax, eax
0x18000d622  jz      short loc_18000D65D
0x18000d624  lea     rax, [rsp+2C0h+String]
0x18000d629  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d62d  inc     rcx
0x18000d630  cmp     [rax+rcx*2], r12w
0x18000d635  jnz     short loc_18000D62D
0x18000d637  cmp     rcx, 0B4h
0x18000d63e  jbe     short loc_18000D647
0x18000d640  mov     ebx, 7Ah ; 'z'
0x18000d645  jmp     short loc_18000D65D
0x18000d647  lea     r8, [rsp+2C0h+String]; lpString
0x18000d64c  mov     edx, r15d; nIDDlgItem
0x18000d64f  mov     rcx, r14; hDlg
0x18000d652  call    cs:__imp_SetDlgItemTextW
0x18000d658  mov     esi, 1
0x18000d65d  mov     rcx, [rsp+2C0h+ppMalloc]
0x18000d662  mov     rdx, rdi
0x18000d665  mov     rax, [rcx]
0x18000d668  mov     rax, [rax+28h]
0x18000d66c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d671  mov     rcx, [rsp+2C0h+ppMalloc]
0x18000d676  mov     rdx, [rcx]
0x18000d679  mov     rax, [rdx+10h]
0x18000d67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d682  call    cs:__imp_CoUninitialize
0x18000d688  mov     ecx, ebx; dwErrCode
0x18000d68a  call    cs:__imp_SetLastError
0x18000d690  mov     eax, esi
0x18000d692  mov     rcx, [rbp+1C0h+var_40]
0x18000d699  xor     rcx, rsp; StackCookie
0x18000d69c  call    __security_check_cookie
0x18000d6a1  add     rsp, 290h
0x18000d6a8  pop     r15
0x18000d6aa  pop     r14
0x18000d6ac  pop     r12
0x18000d6ae  pop     rdi
0x18000d6af  pop     rsi
0x18000d6b0  pop     rbx
0x18000d6b1  pop     rbp
0x18000d6b2  retn
```
