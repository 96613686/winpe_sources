# CWMWriterProperties::OnApplyChanges(void)

- ea: `0x1800128f0`
- end: `0x180012a9b`
- name: `?OnApplyChanges@CWMWriterProperties@@EEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CWMWriterProperties *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001460`
- `0x1800128f0`
- `0x18001f010`

## import_xrefs

- `WMVCore!WMCreateProfileManager` at `0x18001293c`
- `WMVCore!WMCreateProfileManager` at `0x18001293c`
- `USER32!SendMessageW` at `0x18001291c`
- `USER32!SendMessageW` at `0x180012a1a`
- `USER32!SendMessageW` at `0x180012a48`
- `USER32!SendMessageW` at `0x18001291c`
- `USER32!SendMessageW` at `0x180012a1a`
- `USER32!SendMessageW` at `0x180012a48`

## pseudocode

```c
__int64 __fastcall CWMWriterProperties::OnApplyChanges(HWND *this)
{
  int v2; // eax
  unsigned int v3; // edi
  int v4; // ebx
  int v5; // eax
  int v6; // eax
  __int64 v8; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v9; // [rsp+38h] [rbp-30h] BYREF
  IWMProfileManager *ppProfileManager; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+48h] [rbp-20h] BYREF

  v2 = SendMessageW(this[9], 0x147u, 0, 0);
  v3 = 0;
  *((_DWORD *)this + 14) = 0;
  ppProfileManager = 0;
  if ( v2 > 0 )
    v3 = v2;
  WMCreateProfileManager(&ppProfileManager);
  v8 = 0;
  if ( ((__int64 (__fastcall *)(IWMProfileManager *, GUID *, __int64 *))ppProfileManager->lpVtbl->QueryInterface)(
         ppProfileManager,
         &IID_IWMProfileManager2,
         &v8) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v8 + 80LL))(v8, 0x80000);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  v9 = 0;
  v4 = ((__int64 (__fastcall *)(IWMProfileManager *, unsigned int *))ppProfileManager->lpVtbl->GetSystemProfileCount)(
         ppProfileManager,
         &v9);
  if ( v4 >= 0 )
  {
    if ( v3 < v9 )
    {
      v11 = 0;
      v4 = ((__int64 (__fastcall *)(IWMProfileManager *, _QWORD, __int64 *))ppProfileManager->lpVtbl->LoadSystemProfile)(
             ppProfileManager,
             v3,
             &v11);
      if ( v4 >= 0 )
        v4 = (*(__int64 (__fastcall **)(HWND, __int64))(*(_QWORD *)this[12] + 56LL))(this[12], v11);
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    else
    {
      v4 = -2147467259;
    }
  }
  v5 = SendMessageW(this[10], 0xF0u, 0, 0);
  (*(void (__fastcall **)(HWND, bool))(*(_QWORD *)this[12] + 72LL))(this[12], v5 == 1);
  v6 = SendMessageW(this[11], 0xF0u, 0, 0);
  (*(void (__fastcall **)(HWND, __int64, bool))(*(_QWORD *)this[12] + 96LL))(this[12], 2, v6 == 1);
  if ( ppProfileManager )
    ((void (__fastcall *)(IWMProfileManager *))ppProfileManager->lpVtbl->Release)(ppProfileManager);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800128f0  push    rbp
0x1800128f2  push    rbx
0x1800128f3  push    rsi
0x1800128f4  push    rdi
0x1800128f5  mov     rbp, rsp
0x1800128f8  sub     rsp, 68h
0x1800128fc  mov     rax, cs:__security_cookie
0x180012903  xor     rax, rsp
0x180012906  mov     [rbp+var_18], rax
0x18001290a  mov     rsi, rcx
0x18001290d  xor     r9d, r9d; lParam
0x180012910  mov     rcx, [rcx+48h]; hWnd
0x180012914  xor     r8d, r8d; wParam
0x180012917  mov     edx, 147h; Msg
0x18001291c  call    cs:__imp_SendMessageW
0x180012922  xor     edi, edi
0x180012924  mov     dword ptr [rsi+38h], 0
0x18001292b  test    eax, eax
0x18001292d  mov     [rbp+ppProfileManager], 0
0x180012935  lea     rcx, [rbp+ppProfileManager]; ppProfileManager
0x180012939  cmovg   edi, eax
0x18001293c  call    cs:__imp_WMCreateProfileManager
0x180012942  mov     rcx, [rbp+ppProfileManager]
0x180012946  lea     r8, [rbp+var_38]
0x18001294a  mov     [rbp+var_38], 0
0x180012952  lea     rdx, IID_IWMProfileManager2
0x180012959  mov     rax, [rcx]
0x18001295c  mov     rax, [rax]
0x18001295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012964  test    eax, eax
0x180012966  js      short loc_18001298D
0x180012968  mov     rcx, [rbp+var_38]
0x18001296c  mov     edx, 80000h
0x180012971  mov     rax, [rcx]
0x180012974  mov     rax, [rax+50h]
0x180012978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001297d  mov     rcx, [rbp+var_38]
0x180012981  mov     rax, [rcx]
0x180012984  mov     rax, [rax+10h]
0x180012988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001298d  mov     rcx, [rbp+ppProfileManager]
0x180012991  lea     rdx, [rbp+var_30]
0x180012995  mov     [rbp+var_30], 0
0x18001299c  mov     rax, [rcx]
0x18001299f  mov     rax, [rax+38h]
0x1800129a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129a8  mov     ebx, eax
0x1800129aa  test    eax, eax
0x1800129ac  js      short loc_180012A09
0x1800129ae  cmp     edi, [rbp+var_30]
0x1800129b1  jb      short loc_1800129BA
0x1800129b3  mov     ebx, 80004005h
0x1800129b8  jmp     short loc_180012A09
0x1800129ba  mov     rcx, [rbp+ppProfileManager]
0x1800129be  lea     r8, [rbp+var_20]
0x1800129c2  mov     [rbp+var_20], 0
0x1800129ca  mov     edx, edi
0x1800129cc  mov     rax, [rcx]
0x1800129cf  mov     rax, [rax+40h]
0x1800129d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129d8  mov     ebx, eax
0x1800129da  test    eax, eax
0x1800129dc  js      short loc_1800129F4
0x1800129de  mov     rcx, [rsi+60h]
0x1800129e2  mov     rdx, [rbp+var_20]
0x1800129e6  mov     rax, [rcx]
0x1800129e9  mov     rax, [rax+38h]
0x1800129ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800129f2  mov     ebx, eax
0x1800129f4  mov     rcx, [rbp+var_20]
0x1800129f8  test    rcx, rcx
0x1800129fb  jz      short loc_180012A09
0x1800129fd  mov     rax, [rcx]
0x180012a00  mov     rax, [rax+10h]
0x180012a04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a09  mov     rcx, [rsi+50h]; hWnd
0x180012a0d  mov     edi, 0F0h
0x180012a12  mov     edx, edi; Msg
0x180012a14  xor     r9d, r9d; lParam
0x180012a17  xor     r8d, r8d; wParam
0x180012a1a  call    cs:__imp_SendMessageW
0x180012a20  mov     rcx, [rsi+60h]
0x180012a24  xor     edx, edx
0x180012a26  mov     r8, rax
0x180012a29  cmp     r8d, 1
0x180012a2d  mov     rax, [rcx]
0x180012a30  setz    dl
0x180012a33  mov     rax, [rax+48h]
0x180012a37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a3c  mov     rcx, [rsi+58h]; hWnd
0x180012a40  xor     r9d, r9d; lParam
0x180012a43  xor     r8d, r8d; wParam
0x180012a46  mov     edx, edi; Msg
0x180012a48  call    cs:__imp_SendMessageW
0x180012a4e  mov     rcx, [rsi+60h]
0x180012a52  xor     r8d, r8d
0x180012a55  cmp     eax, 1
0x180012a58  setz    r8b
0x180012a5c  xor     r9d, r9d
0x180012a5f  mov     rdx, [rcx]
0x180012a62  mov     rax, [rdx+60h]
0x180012a66  lea     edx, [r9+2]
0x180012a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a6f  mov     rcx, [rbp+ppProfileManager]
0x180012a73  test    rcx, rcx
0x180012a76  jz      short loc_180012A84
0x180012a78  mov     rax, [rcx]
0x180012a7b  mov     rax, [rax+10h]
0x180012a7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012a84  mov     eax, ebx
0x180012a86  mov     rcx, [rbp+var_18]
0x180012a8a  xor     rcx, rsp; StackCookie
0x180012a8d  call    __security_check_cookie
0x180012a92  add     rsp, 68h
0x180012a96  pop     rdi
0x180012a97  pop     rsi
0x180012a98  pop     rbx
0x180012a99  pop     rbp
0x180012a9a  retn
```
