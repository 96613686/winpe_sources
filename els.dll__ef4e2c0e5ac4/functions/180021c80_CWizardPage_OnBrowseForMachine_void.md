# CWizardPage::_OnBrowseForMachine(void)

- ea: `0x180021c80`
- end: `0x180021e53`
- name: `?_OnBrowseForMachine@CWizardPage@@AEAAXXZ`
- size: `467`
- prototype: `void __fastcall(CWizardPage *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021e60`

## callees

- `0x180021c80`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x180021dca`
- `KERNEL32!GlobalLock` at `0x180021dca`
- `KERNEL32!GlobalUnlock` at `0x180021df8`
- `KERNEL32!GlobalUnlock` at `0x180021df8`
- `USER32!GetDlgItem` at `0x180021de2`
- `USER32!GetDlgItem` at `0x180021de2`
- `USER32!SetWindowTextW` at `0x180021dee`
- `USER32!SetWindowTextW` at `0x180021dee`
- `ole32!ReleaseStgMedium` at `0x180021e02`
- `ole32!ReleaseStgMedium` at `0x180021e02`
- `ole32!CoCreateInstance` at `0x180021d32`
- `ole32!CoCreateInstance` at `0x180021d32`

## pseudocode

```c
void __fastcall CWizardPage::_OnBrowseForMachine(CWizardPage *this)
{
  int v2; // eax
  LPVOID v3; // rax
  const WCHAR *v4; // rbx
  HWND DlgItem; // rax
  LPVOID ppv; // [rsp+30h] [rbp-69h] BYREF
  __int64 v7; // [rsp+38h] [rbp-61h] BYREF
  STGMEDIUM v8; // [rsp+40h] [rbp-59h] BYREF
  __int16 v9; // [rsp+58h] [rbp-41h] BYREF
  int v10; // [rsp+5Ah] [rbp-3Fh]
  __int16 v11; // [rsp+5Eh] [rbp-3Bh]
  __int64 v12; // [rsp+60h] [rbp-39h]
  int v13; // [rsp+68h] [rbp-31h]
  int v14; // [rsp+6Ch] [rbp-2Dh]
  __int64 v15; // [rsp+70h] [rbp-29h]
  _QWORD v16[4]; // [rsp+78h] [rbp-21h] BYREF
  __int128 v17; // [rsp+98h] [rbp-1h]
  int v18; // [rsp+A8h] [rbp+Fh] BYREF
  __int64 v19; // [rsp+ACh] [rbp+13h]
  int v20; // [rsp+B4h] [rbp+1Bh]
  __int128 v21; // [rsp+B8h] [rbp+1Fh]
  __int128 v22; // [rsp+C8h] [rbp+2Fh]
  __int64 v23; // [rsp+D8h] [rbp+3Fh]

  v16[0] = 48;
  v23 = 0;
  v16[1] = 0;
  v18 = 56;
  v19 = 1016;
  v16[3] = &v18;
  v20 = 2048;
  v21 = 0;
  DWORD2(v21) = -2147483640;
  v16[2] = 1;
  v22 = 0;
  ppv = 0;
  v17 = 0;
  v7 = 0;
  *(_QWORD *)&v8.tymed = 1;
  *(_OWORD *)&v8.hBitmap = 0;
  if ( CoCreateInstance(&CLSID_DsObjectPicker, 0, 1u, &IID_IDsObjectPicker, &ppv) >= 0
    && (*(int (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v16) >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(ppv, *((_QWORD *)this + 2), &v7);
    if ( v2 >= 0 && v2 != 1 )
    {
      v9 = g_cfDsObjectPicker;
      v10 = 0;
      v11 = 0;
      v12 = 0;
      v13 = 1;
      v14 = -1;
      v15 = 1;
      if ( (*(int (__fastcall **)(__int64, __int16 *, STGMEDIUM *))(*(_QWORD *)v7 + 24LL))(v7, &v9, &v8) >= 0 )
      {
        v3 = GlobalLock(v8.hBitmap);
        if ( v3 )
        {
          v4 = (const WCHAR *)*((_QWORD *)v3 + 1);
          DlgItem = GetDlgItem(*((HWND *)this + 2), 974);
          SetWindowTextW(DlgItem, v4);
          GlobalUnlock(v8.hBitmap);
        }
        ReleaseStgMedium(&v8);
      }
    }
  }
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180021c80  mov     [rsp-8+arg_8], rbx
0x180021c85  mov     [rsp-8+arg_10], rdi
0x180021c8a  push    rbp
0x180021c8b  lea     rbp, [rsp-57h]
0x180021c90  sub     rsp, 0F0h
0x180021c97  mov     rax, cs:__security_cookie
0x180021c9e  xor     rax, rsp
0x180021ca1  mov     [rbp+57h+var_10], rax
0x180021ca5  xor     eax, eax
0x180021ca7  mov     [rbp+57h+var_78], 30h ; '0'
0x180021caf  xorps   xmm0, xmm0
0x180021cb2  mov     [rbp+57h+var_18], rax
0x180021cb6  movups  [rbp+57h+var_48], xmm0
0x180021cba  mov     [rbp+57h+var_70], rax
0x180021cbe  lea     r9, IID_IDsObjectPicker; riid
0x180021cc5  lea     ebx, [rax+1]
0x180021cc8  mov     dword ptr [rbp+57h+var_48], 38h ; '8'
0x180021ccf  lea     rax, [rbp+57h+var_48]
0x180021cd3  mov     dword ptr [rbp+57h+var_48+4], 3F8h
0x180021cda  mov     [rbp+57h+var_60], rax
0x180021cde  mov     rdi, rcx
0x180021ce1  lea     rax, [rbp+57h+var_C0]
0x180021ce5  mov     dword ptr [rbp+57h+var_48+0Ch], 800h
0x180021cec  movups  [rbp+57h+var_38], xmm0
0x180021cf0  mov     r8d, ebx; dwClsContext
0x180021cf3  mov     [rsp+0F0h+ppv], rax; ppv
0x180021cf8  xor     edx, edx; pUnkOuter
0x180021cfa  mov     dword ptr [rbp+57h+var_38+8], 80000008h
0x180021d01  lea     rcx, CLSID_DsObjectPicker; rclsid
0x180021d08  mov     [rbp+57h+var_68], 1
0x180021d10  movups  [rbp+57h+var_28], xmm0
0x180021d14  mov     [rbp+57h+var_C0], 0
0x180021d1c  movdqu  [rbp+57h+var_58], xmm0
0x180021d21  mov     [rbp+57h+var_B8], 0
0x180021d29  mov     qword ptr [rbp+57h+var_B0.tymed], rbx
0x180021d2d  movdqu  xmmword ptr [rbp+57h+var_B0.8], xmm0
0x180021d32  call    cs:__imp_CoCreateInstance
0x180021d38  test    eax, eax
0x180021d3a  js      loc_180021E08
0x180021d40  mov     rcx, [rbp+57h+var_C0]
0x180021d44  lea     rdx, [rbp+57h+var_78]
0x180021d48  mov     rax, [rcx]
0x180021d4b  mov     rax, [rax+18h]
0x180021d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d54  test    eax, eax
0x180021d56  js      loc_180021E08
0x180021d5c  mov     rcx, [rbp+57h+var_C0]
0x180021d60  lea     r8, [rbp+57h+var_B8]
0x180021d64  mov     rdx, [rdi+10h]
0x180021d68  mov     rax, [rcx]
0x180021d6b  mov     rax, [rax+20h]
0x180021d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021d74  test    eax, eax
0x180021d76  js      loc_180021E08
0x180021d7c  cmp     eax, ebx
0x180021d7e  jz      loc_180021E08
0x180021d84  movzx   eax, word ptr cs:?g_cfDsObjectPicker@@3IA; uint g_cfDsObjectPicker
0x180021d8b  lea     r8, [rbp+57h+var_B0]
0x180021d8f  mov     rcx, [rbp+57h+var_B8]
0x180021d93  lea     rdx, [rbp+57h+var_98]
0x180021d97  mov     [rbp+57h+var_98], ax
0x180021d9b  xor     eax, eax
0x180021d9d  mov     [rbp+57h+var_96], eax
0x180021da0  mov     [rbp+57h+var_92], ax
0x180021da4  mov     [rbp+57h+var_90], rax
0x180021da8  mov     [rbp+57h+var_88], ebx
0x180021dab  mov     [rbp+57h+var_84], 0FFFFFFFFh
0x180021db2  mov     [rbp+57h+var_80], rbx
0x180021db6  mov     rax, [rcx]
0x180021db9  mov     rax, [rax+18h]
0x180021dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021dc2  test    eax, eax
0x180021dc4  js      short loc_180021E08
0x180021dc6  mov     rcx, qword ptr [rbp+57h+var_B0.8]; hMem
0x180021dca  call    cs:__imp_GlobalLock
0x180021dd0  test    rax, rax
0x180021dd3  jz      short loc_180021DFE
0x180021dd5  mov     rcx, [rdi+10h]; hDlg
0x180021dd9  mov     edx, 3CEh; nIDDlgItem
0x180021dde  mov     rbx, [rax+8]
0x180021de2  call    cs:__imp_GetDlgItem
0x180021de8  mov     rcx, rax; hWnd
0x180021deb  mov     rdx, rbx; lpString
0x180021dee  call    cs:__imp_SetWindowTextW
0x180021df4  mov     rcx, qword ptr [rbp+57h+var_B0.8]; hMem
0x180021df8  call    cs:__imp_GlobalUnlock
0x180021dfe  lea     rcx, [rbp+57h+var_B0]; LPSTGMEDIUM
0x180021e02  call    cs:__imp_ReleaseStgMedium
0x180021e08  mov     rcx, [rbp+57h+var_B8]
0x180021e0c  test    rcx, rcx
0x180021e0f  jz      short loc_180021E1D
0x180021e11  mov     rax, [rcx]
0x180021e14  mov     rax, [rax+10h]
0x180021e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e1d  mov     rcx, [rbp+57h+var_C0]
0x180021e21  test    rcx, rcx
0x180021e24  jz      short loc_180021E32
0x180021e26  mov     rax, [rcx]
0x180021e29  mov     rax, [rax+10h]
0x180021e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021e32  mov     rcx, [rbp+57h+var_10]
0x180021e36  xor     rcx, rsp; StackCookie
0x180021e39  call    __security_check_cookie
0x180021e3e  lea     r11, [rsp+0F0h+var_s0]
0x180021e46  mov     rbx, [r11+18h]
0x180021e4a  mov     rdi, [r11+20h]
0x180021e4e  mov     rsp, r11
0x180021e51  pop     rbp
0x180021e52  retn
```
