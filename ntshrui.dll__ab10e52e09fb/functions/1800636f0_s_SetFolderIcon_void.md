# s_SetFolderIcon(void *)

- ea: `0x1800636f0`
- end: `0x18006389c`
- name: `?s_SetFolderIcon@@YAKPEAX@Z`
- size: `428`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180013220`
- `0x18001c4a8`
- `0x1800254e0`
- `0x180025504`
- `0x180061504`
- `0x1800636f0`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006386c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18006386c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006371f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18006371f`
- `KERNEL32!MulDiv` at `0x1800637d9`
- `KERNEL32!MulDiv` at `0x1800637eb`
- `KERNEL32!MulDiv` at `0x1800637d9`
- `KERNEL32!MulDiv` at `0x1800637eb`
- `SHELL32!SHCreateItemFromParsingName` at `0x180063768`
- `SHELL32!SHCreateItemFromParsingName` at `0x180063768`
- `GDI32!DeleteObject` at `0x180063850`
- `GDI32!DeleteObject` at `0x180063850`
- `USER32!GetDlgItem` at `0x180063833`
- `USER32!GetDlgItem` at `0x180063833`
- `USER32!SendMessageW` at `0x180063847`
- `USER32!SendMessageW` at `0x180063847`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall s_SetFolderIcon(unsigned __int16 *a1)
{
  HRESULT v2; // edi
  int v3; // ebx
  int v4; // eax
  LPARAM v5; // rbx
  HWND DlgItem; // rax
  void *v7; // rax
  int nNumerator; // [rsp+30h] [rbp-D0h] BYREF
  int v10[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  void *ppv; // [rsp+48h] [rbp-B8h] BYREF
  LPARAM lParam[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+60h] [rbp-A0h] BYREF

  v2 = CoInitializeEx(0, 2u);
  if ( v2 >= 0 )
  {
    v2 = StringCchCopyW(pszPath, 0x104u, a1 + 4);
    if ( v2 >= 0 )
    {
      ppv = 0;
      v2 = SHCreateItemFromParsingName(pszPath, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( v2 >= 0 )
      {
        v11 = 0;
        v2 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
               ppv,
               &GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b,
               &v11);
        if ( v2 >= 0 )
        {
          nNumerator = 0;
          v10[0] = 0;
          SHComputeDPI(*(HWND *)a1, &nNumerator, v10);
          v3 = MulDiv(32, nNumerator, 96);
          v4 = MulDiv(32, v10[0], 96);
          lParam[0] = 0;
          *(_QWORD *)v10 = __PAIR64__(v4, v3);
          v2 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, LPARAM *))(*(_QWORD *)v11 + 24LL))(
                 v11,
                 __PAIR64__(v4, v3),
                 0,
                 lParam);
          if ( v2 >= 0 )
          {
            v5 = lParam[0];
            DlgItem = GetDlgItem(*(HWND *)a1, 1021);
            v7 = (void *)SendMessageW(DlgItem, 0x172u, 0, v5);
            DeleteObject(v7);
          }
        }
        ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&v11);
      }
      ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(&ppv);
    }
    CoUninitialize();
  }
  operator delete(a1, (const struct std::nothrow_t *)0x210);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800636f0  push    rbp
0x1800636f2  push    rbx
0x1800636f3  push    rsi
0x1800636f4  push    rdi
0x1800636f5  lea     rbp, [rsp-188h]
0x1800636fd  sub     rsp, 288h
0x180063704  mov     rax, cs:__security_cookie
0x18006370b  xor     rax, rsp
0x18006370e  mov     [rbp+1A0h+var_30], rax
0x180063715  mov     rsi, rcx
0x180063718  mov     edx, 2; dwCoInit
0x18006371d  xor     ecx, ecx; pvReserved
0x18006371f  call    cs:__imp_CoInitializeEx
0x180063725  mov     edi, eax
0x180063727  test    eax, eax
0x180063729  js      loc_180063872
0x18006372f  lea     r8, [rsi+8]; unsigned __int16 *
0x180063733  mov     edx, 104h; unsigned __int64
0x180063738  lea     rcx, [rsp+2A0h+pszPath]; unsigned __int16 *
0x18006373d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180063742  mov     edi, eax
0x180063744  test    eax, eax
0x180063746  js      loc_18006386C
0x18006374c  mov     [rsp+2A0h+ppv], 0
0x180063755  lea     r9, [rsp+2A0h+ppv]; ppv
0x18006375a  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180063761  xor     edx, edx; pbc
0x180063763  lea     rcx, [rsp+2A0h+pszPath]; pszPath
0x180063768  call    cs:__imp_SHCreateItemFromParsingName
0x18006376e  mov     edi, eax
0x180063770  test    eax, eax
0x180063772  js      loc_180063862
0x180063778  mov     [rsp+2A0h+var_260], 0
0x180063781  mov     rcx, [rsp+2A0h+ppv]
0x180063786  mov     rax, [rcx]
0x180063789  lea     r8, [rsp+2A0h+var_260]
0x18006378e  lea     rdx, _GUID_bcc18b79_ba16_442f_80c4_8a59c30c463b
0x180063795  mov     rax, [rax]
0x180063798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006379d  mov     edi, eax
0x18006379f  test    eax, eax
0x1800637a1  js      loc_180063857
0x1800637a7  mov     [rsp+2A0h+nNumerator], 0
0x1800637af  mov     [rsp+2A0h+var_268], 0
0x1800637b7  lea     r8, [rsp+2A0h+var_268]; int *
0x1800637bc  lea     rdx, [rsp+2A0h+nNumerator]; int *
0x1800637c1  mov     rcx, [rsi]; HWND
0x1800637c4  call    ?SHComputeDPI@@YAXPEAUHWND__@@PEAH1@Z; SHComputeDPI(HWND__ *,int *,int *)
0x1800637c9  mov     r8d, 60h ; '`'; nDenominator
0x1800637cf  mov     edx, [rsp+2A0h+nNumerator]; nNumerator
0x1800637d3  lea     edi, [r8-40h]
0x1800637d7  mov     ecx, edi; nNumber
0x1800637d9  call    cs:__imp_MulDiv
0x1800637df  mov     ebx, eax
0x1800637e1  lea     r8d, [rdi+40h]; nDenominator
0x1800637e5  mov     edx, [rsp+2A0h+var_268]; nNumerator
0x1800637e9  mov     ecx, edi; nNumber
0x1800637eb  call    cs:__imp_MulDiv
0x1800637f1  mov     [rsp+2A0h+lParam], 0
0x1800637fa  mov     rcx, [rsp+2A0h+var_260]
0x1800637ff  mov     [rsp+2A0h+var_268], ebx
0x180063803  mov     [rsp+2A0h+var_268+4], eax
0x180063807  mov     rax, [rcx]
0x18006380a  lea     r9, [rsp+2A0h+lParam]
0x18006380f  xor     r8d, r8d
0x180063812  mov     rdx, qword ptr [rsp+2A0h+var_268]
0x180063817  mov     rax, [rax+18h]
0x18006381b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063820  mov     edi, eax
0x180063822  test    eax, eax
0x180063824  js      short loc_180063857
0x180063826  mov     rbx, [rsp+2A0h+lParam]
0x18006382b  mov     edx, 3FDh; nIDDlgItem
0x180063830  mov     rcx, [rsi]; hDlg
0x180063833  call    cs:__imp_GetDlgItem
0x180063839  mov     r9, rbx; lParam
0x18006383c  xor     r8d, r8d; wParam
0x18006383f  mov     edx, 172h; Msg
0x180063844  mov     rcx, rax; hWnd
0x180063847  call    cs:__imp_SendMessageW
0x18006384d  mov     rcx, rax; ho
0x180063850  call    cs:__imp_DeleteObject
0x180063856  nop
0x180063857  lea     rcx, [rsp+2A0h+var_260]
0x18006385c  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x180063861  nop
0x180063862  lea     rcx, [rsp+2A0h+ppv]
0x180063867  call    ??1?$CComPtr@UIShellItemImageFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IShellItemImageFactory>::~CComPtr<IShellItemImageFactory>(void)
0x18006386c  call    cs:__imp_CoUninitialize
0x180063872  mov     edx, 210h; struct std::nothrow_t *
0x180063877  mov     rcx, rsi; void *
0x18006387a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18006387f  mov     eax, edi
0x180063881  mov     rcx, [rbp+1A0h+var_30]
0x180063888  xor     rcx, rsp; StackCookie
0x18006388b  call    __security_check_cookie
0x180063890  add     rsp, 288h
0x180063897  pop     rdi
0x180063898  pop     rsi
0x180063899  pop     rbx
0x18006389a  pop     rbp
0x18006389b  retn
```
