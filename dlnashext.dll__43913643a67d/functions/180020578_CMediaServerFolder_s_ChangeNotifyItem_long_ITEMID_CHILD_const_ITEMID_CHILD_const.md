# CMediaServerFolder::s_ChangeNotifyItem(long,_ITEMID_CHILD const *,_ITEMID_CHILD const *)

- ea: `0x180020578`
- end: `0x1800206c3`
- name: `?s_ChangeNotifyItem@CMediaServerFolder@@SAJJPEFBU_ITEMID_CHILD@@0@Z`
- size: `331`
- prototype: `static int(int, const struct _ITEMID_CHILD *, const struct _ITEMID_CHILD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001fdc0`

## callees

- `0x180001710`
- `0x18000ab48`
- `0x180020578`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800205c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800205c0`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18002066e`
- `api-ms-win-shell-changenotify-l1-1-0!SHChangeNotify` at `0x18002066e`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180020620`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180020645`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180020620`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180020645`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CMediaServerFolder::s_ChangeNotifyItem(__int64 a1, const ITEMIDLIST *a2, const ITEMIDLIST *a3)
{
  HRESULT v5; // edi
  LPITEMIDLIST v6; // rbx
  LPITEMIDLIST v7; // rax
  __int64 v8; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-28h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+38h] [rbp-20h] BYREF
  LPITEMIDLIST v12; // [rsp+40h] [rbp-18h] BYREF
  LPITEMIDLIST v13[2]; // [rsp+48h] [rbp-10h] BYREF
  __int64 v14; // [rsp+98h] [rbp+40h] BYREF

  pidl1 = 0;
  ppv = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  v5 = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &ppv);
  if ( v5 < 0 )
    goto LABEL_15;
  v14 = 0;
  v5 = (*(__int64 (__fastcall **)(LPVOID, const GUID *, __int64 *))(*(_QWORD *)ppv + 48LL))(
         ppv,
         &FOLDERID_ComputerFolder,
         &v14);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCITEMIDLIST *))(*(_QWORD *)v14 + 64LL))(v14, 0, &pidl1);
    if ( v5 >= 0 )
    {
      v6 = ILCombine(pidl1, a2);
      v13[0] = v6;
      if ( !v6 )
      {
        v5 = -2147024882;
LABEL_12:
        CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(v13);
        goto LABEL_13;
      }
      if ( a3 )
      {
        v7 = ILCombine(pidl1, a3);
        v12 = v7;
        if ( !v7 )
        {
          v5 = -2147024882;
LABEL_11:
          CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&v12);
          goto LABEL_12;
        }
      }
      else
      {
        v7 = 0;
        v12 = 0;
      }
      v5 = 0;
      SHChangeNotify(1, 0, v6, v7);
      goto LABEL_11;
    }
  }
LABEL_13:
  v8 = v14;
  if ( v14 )
  {
    v14 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
LABEL_15:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(&ppv);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&pidl1);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020578  push    rbp
0x18002057a  push    rbx
0x18002057b  push    rsi
0x18002057c  push    rdi
0x18002057d  mov     rbp, rsp
0x180020580  sub     rsp, 58h
0x180020584  mov     rsi, r8
0x180020587  mov     rbx, rdx
0x18002058a  mov     [rbp+pidl1], 0
0x180020592  mov     [rbp+var_28], 0
0x18002059a  lea     rcx, [rbp+var_28]
0x18002059e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800205a3  lea     rax, [rbp+var_28]
0x1800205a7  mov     [rsp+58h+ppv], rax; ppv
0x1800205ac  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800205b3  xor     edx, edx; pUnkOuter
0x1800205b5  lea     r8d, [rdx+1]; dwClsContext
0x1800205b9  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1800205c0  call    cs:__imp_CoCreateInstance
0x1800205c6  mov     edi, eax
0x1800205c8  test    eax, eax
0x1800205ca  js      loc_1800206A5
0x1800205d0  mov     [rbp+arg_18], 0
0x1800205d8  mov     rcx, [rbp+var_28]
0x1800205dc  mov     rax, [rcx]
0x1800205df  lea     r8, [rbp+arg_18]
0x1800205e3  lea     rdx, FOLDERID_ComputerFolder
0x1800205ea  mov     rax, [rax+30h]
0x1800205ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800205f3  mov     edi, eax
0x1800205f5  test    eax, eax
0x1800205f7  js      loc_180020687
0x1800205fd  mov     rcx, [rbp+arg_18]
0x180020601  mov     rax, [rcx]
0x180020604  lea     r8, [rbp+pidl1]
0x180020608  xor     edx, edx
0x18002060a  mov     rax, [rax+40h]
0x18002060e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020613  mov     edi, eax
0x180020615  test    eax, eax
0x180020617  js      short loc_180020687
0x180020619  mov     rdx, rbx; pidl2
0x18002061c  mov     rcx, [rbp+pidl1]; pidl1
0x180020620  call    cs:__imp_ILCombine
0x180020626  mov     rbx, rax
0x180020629  mov     [rbp+var_10], rax
0x18002062d  test    rax, rax
0x180020630  jnz     short loc_180020639
0x180020632  mov     edi, 8007000Eh
0x180020637  jmp     short loc_18002067D
0x180020639  test    rsi, rsi
0x18002063c  jz      short loc_18002065B
0x18002063e  mov     rdx, rsi; pidl2
0x180020641  mov     rcx, [rbp+pidl1]; pidl1
0x180020645  call    cs:__imp_ILCombine
0x18002064b  mov     [rbp+var_18], rax
0x18002064f  test    rax, rax
0x180020652  jnz     short loc_180020661
0x180020654  mov     edi, 8007000Eh
0x180020659  jmp     short loc_180020674
0x18002065b  xor     eax, eax
0x18002065d  mov     [rbp+var_18], rax
0x180020661  xor     edi, edi
0x180020663  mov     r9, rax; dwItem2
0x180020666  mov     r8, rbx; dwItem1
0x180020669  xor     edx, edx; uFlags
0x18002066b  lea     ecx, [rdi+1]; wEventId
0x18002066e  call    cs:__imp_SHChangeNotify
0x180020674  lea     rcx, [rbp+var_18]
0x180020678  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18002067d  lea     rcx, [rbp+var_10]
0x180020681  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180020686  nop
0x180020687  mov     rcx, [rbp+arg_18]
0x18002068b  test    rcx, rcx
0x18002068e  jz      short loc_1800206A5
0x180020690  mov     [rbp+arg_18], 0
0x180020698  mov     rax, [rcx]
0x18002069b  mov     rax, [rax+10h]
0x18002069f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800206a4  nop
0x1800206a5  lea     rcx, [rbp+var_28]
0x1800206a9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIContentDirectoryItem@Internal@Streaming@Media@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Media::Streaming::Internal::IContentDirectoryItem *>>::InternalRelease(void)
0x1800206ae  nop
0x1800206af  lea     rcx, [rbp+pidl1]
0x1800206b3  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x1800206b8  mov     eax, edi
0x1800206ba  add     rsp, 58h
0x1800206be  pop     rdi
0x1800206bf  pop     rsi
0x1800206c0  pop     rbx
0x1800206c1  pop     rbp
0x1800206c2  retn
```
