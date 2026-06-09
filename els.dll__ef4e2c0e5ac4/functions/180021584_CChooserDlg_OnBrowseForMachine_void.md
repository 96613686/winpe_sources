# CChooserDlg::_OnBrowseForMachine(void)

- ea: `0x180021584`
- end: `0x180021819`
- name: `?_OnBrowseForMachine@CChooserDlg@@AEAAXXZ`
- size: `661`
- prototype: `void __fastcall(CChooserDlg *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021820`

## callees

- `0x180001dd0`
- `0x180002928`
- `0x18000513c`
- `0x180021490`
- `0x180021584`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `KERNEL32!GlobalLock` at `0x1800216f6`
- `KERNEL32!GlobalLock` at `0x1800216f6`
- `KERNEL32!GlobalUnlock` at `0x1800217b9`
- `KERNEL32!GlobalUnlock` at `0x1800217b9`
- `USER32!GetDlgItem` at `0x180021711`
- `USER32!GetDlgItem` at `0x180021711`
- `USER32!SetWindowLongPtrW` at `0x1800217af`
- `USER32!SetWindowLongPtrW` at `0x1800217af`
- `USER32!SetWindowTextW` at `0x180021721`
- `USER32!SetWindowTextW` at `0x180021721`
- `USER32!GetWindowLongPtrW` at `0x18002172f`
- `USER32!GetWindowLongPtrW` at `0x18002172f`
- `ole32!ReleaseStgMedium` at `0x1800217c3`
- `ole32!ReleaseStgMedium` at `0x1800217c3`
- `ole32!CoCreateInstance` at `0x180021656`
- `ole32!CoCreateInstance` at `0x180021656`

## pseudocode

```c
void __fastcall CChooserDlg::_OnBrowseForMachine(CChooserDlg *this)
{
  int v2; // eax
  LPCWSTR *v3; // rdi
  HWND DlgItem; // r14
  SObjectPickerResult *WindowLongPtrW; // rax
  unsigned int v6; // edx
  LONG_PTR v7; // rsi
  LPCWSTR v8; // rax
  char *v9; // rax
  char *v10; // rbx
  LPVOID ppv; // [rsp+30h] [rbp-89h] BYREF
  __int64 v12; // [rsp+38h] [rbp-81h] BYREF
  STGMEDIUM v13; // [rsp+40h] [rbp-79h] BYREF
  __int16 v14; // [rsp+58h] [rbp-61h] BYREF
  int v15; // [rsp+5Ah] [rbp-5Fh]
  __int16 v16; // [rsp+5Eh] [rbp-5Bh]
  __int64 v17; // [rsp+60h] [rbp-59h]
  int v18; // [rsp+68h] [rbp-51h]
  int v19; // [rsp+6Ch] [rbp-4Dh]
  __int64 v20; // [rsp+70h] [rbp-49h]
  const wchar_t *v21; // [rsp+78h] [rbp-41h] BYREF
  _QWORD v22[4]; // [rsp+80h] [rbp-39h] BYREF
  int v23; // [rsp+A0h] [rbp-19h]
  int v24; // [rsp+A4h] [rbp-15h]
  const wchar_t **v25; // [rsp+A8h] [rbp-11h]
  void *v26; // [rsp+B0h] [rbp-9h]
  int v27; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v28; // [rsp+BCh] [rbp+3h]
  int v29; // [rsp+C4h] [rbp+Bh]
  __int128 v30; // [rsp+C8h] [rbp+Fh]
  __int128 v31; // [rsp+D8h] [rbp+1Fh]
  __int64 v32; // [rsp+E8h] [rbp+2Fh]

  v22[0] = 48;
  v32 = 0;
  v23 = 0;
  v27 = 56;
  v28 = 1016;
  v21 = L"dNSHostName";
  v29 = 2048;
  v22[3] = &v27;
  v22[2] = 1;
  v25 = &v21;
  v22[1] = 0;
  v30 = 0;
  v31 = 0;
  DWORD2(v30) = -2147483640;
  v24 = 1;
  ppv = 0;
  v12 = 0;
  *(_QWORD *)&v13.tymed = 1;
  *(_OWORD *)&v13.hBitmap = 0;
  if ( CoCreateInstance(&CLSID_DsObjectPicker, 0, 1u, &IID_IDsObjectPicker, &ppv) >= 0
    && (*(int (__fastcall **)(LPVOID, _QWORD *))(*(_QWORD *)ppv + 24LL))(ppv, v22) >= 0 )
  {
    v2 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)ppv + 32LL))(
           ppv,
           *((_QWORD *)this + 1),
           &v12);
    if ( v2 >= 0 && v2 != 1 )
    {
      v14 = g_cfDsObjectPicker;
      v15 = 0;
      v16 = 0;
      v17 = 0;
      v18 = 1;
      v19 = -1;
      v20 = 1;
      if ( (*(int (__fastcall **)(__int64, __int16 *, STGMEDIUM *))(*(_QWORD *)v12 + 24LL))(v12, &v14, &v13) >= 0 )
      {
        v3 = (LPCWSTR *)GlobalLock(v13.hBitmap);
        if ( v3 )
        {
          DlgItem = GetDlgItem(*((HWND *)this + 1), 974);
          SetWindowTextW(DlgItem, v3[1]);
          WindowLongPtrW = (SObjectPickerResult *)GetWindowLongPtrW(DlgItem, -21);
          v7 = (LONG_PTR)WindowLongPtrW;
          if ( WindowLongPtrW )
          {
            SObjectPickerResult::`scalar deleting destructor'(WindowLongPtrW, v6);
            v7 = 0;
          }
          v8 = v3[5];
          if ( *v8 == 8 )
          {
            if ( *((_QWORD *)v8 + 1) )
            {
              v9 = (char *)operator new(0x40u);
              v26 = v9;
              v10 = v9;
              if ( v9 )
              {
                std::wstring::wstring(v9);
                std::wstring::wstring(v10 + 32);
                std::wstring::assign(v10, v3[1]);
                std::wstring::assign(v10 + 32, *((_QWORD *)v3[5] + 1));
                v7 = (LONG_PTR)v10;
              }
            }
          }
          SetWindowLongPtrW(DlgItem, -21, v7);
          GlobalUnlock(v13.hBitmap);
        }
        ReleaseStgMedium(&v13);
      }
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
}

```

## disassembly

```asm
0x180021584  mov     [rsp-8+arg_8], rbx
0x180021589  mov     [rsp-8+arg_10], rsi
0x18002158e  push    rbp
0x18002158f  push    rdi
0x180021590  push    r14
0x180021592  lea     rbp, [rsp-47h]
0x180021597  sub     rsp, 100h
0x18002159e  mov     rax, cs:__security_cookie
0x1800215a5  xor     rax, rsp
0x1800215a8  mov     [rbp+57h+var_20], rax
0x1800215ac  xor     eax, eax
0x1800215ae  mov     [rbp+57h+var_90], 30h ; '0'
0x1800215b6  mov     [rbp+57h+var_28], rax
0x1800215ba  lea     r9, IID_IDsObjectPicker; riid
0x1800215c1  mov     [rbp+57h+var_70], eax
0x1800215c4  xorps   xmm0, xmm0
0x1800215c7  movups  [rbp+57h+var_58], xmm0
0x1800215cb  mov     edi, 1
0x1800215d0  mov     dword ptr [rbp+57h+var_58], 38h ; '8'
0x1800215d7  lea     rax, aDnshostname; "dNSHostName"
0x1800215de  mov     dword ptr [rbp+57h+var_58+4], 3F8h
0x1800215e5  mov     [rbp+57h+var_98], rax
0x1800215e9  mov     rbx, rcx
0x1800215ec  lea     rax, [rbp+57h+var_58]
0x1800215f0  mov     dword ptr [rbp+57h+var_58+0Ch], 800h
0x1800215f7  mov     [rbp+57h+var_78], rax
0x1800215fb  lea     rcx, CLSID_DsObjectPicker; rclsid
0x180021602  lea     rax, [rbp+57h+var_98]
0x180021606  mov     [rbp+57h+var_80], 1
0x18002160e  mov     [rbp+57h+var_68], rax
0x180021612  mov     r8d, edi; dwClsContext
0x180021615  lea     rax, [rsp+110h+var_E0]
0x18002161a  mov     [rbp+57h+var_88], 0
0x180021622  movups  [rbp+57h+var_48], xmm0
0x180021626  xor     edx, edx; pUnkOuter
0x180021628  mov     [rsp+110h+ppv], rax; ppv
0x18002162d  movups  [rbp+57h+var_38], xmm0
0x180021631  mov     dword ptr [rbp+57h+var_48+8], 80000008h
0x180021638  mov     [rbp+57h+var_6C], edi
0x18002163b  mov     [rsp+110h+var_E0], 0
0x180021644  mov     [rsp+110h+var_D8], 0
0x18002164d  mov     qword ptr [rbp+57h+var_D0.tymed], rdi
0x180021651  movdqu  xmmword ptr [rbp+57h+var_D0.8], xmm0
0x180021656  call    cs:__imp_CoCreateInstance
0x18002165c  test    eax, eax
0x18002165e  js      loc_1800217C9
0x180021664  mov     rcx, [rsp+110h+var_E0]
0x180021669  lea     rdx, [rbp+57h+var_90]
0x18002166d  mov     rax, [rcx]
0x180021670  mov     rax, [rax+18h]
0x180021674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021679  test    eax, eax
0x18002167b  js      loc_1800217C9
0x180021681  mov     rcx, [rsp+110h+var_E0]
0x180021686  lea     r8, [rsp+110h+var_D8]
0x18002168b  mov     rdx, [rbx+8]
0x18002168f  mov     rax, [rcx]
0x180021692  mov     rax, [rax+20h]
0x180021696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002169b  test    eax, eax
0x18002169d  js      loc_1800217C9
0x1800216a3  cmp     eax, edi
0x1800216a5  jz      loc_1800217C9
0x1800216ab  movzx   eax, word ptr cs:?g_cfDsObjectPicker@@3IA; uint g_cfDsObjectPicker
0x1800216b2  lea     r8, [rbp+57h+var_D0]
0x1800216b6  mov     rcx, [rsp+110h+var_D8]
0x1800216bb  lea     rdx, [rbp+57h+var_B8]
0x1800216bf  mov     [rbp+57h+var_B8], ax
0x1800216c3  xor     eax, eax
0x1800216c5  mov     [rbp+57h+var_B6], eax
0x1800216c8  mov     [rbp+57h+var_B2], ax
0x1800216cc  mov     [rbp+57h+var_B0], rax
0x1800216d0  mov     [rbp+57h+var_A8], edi
0x1800216d3  mov     [rbp+57h+var_A4], 0FFFFFFFFh
0x1800216da  mov     [rbp+57h+var_A0], rdi
0x1800216de  mov     rax, [rcx]
0x1800216e1  mov     rax, [rax+18h]
0x1800216e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ea  test    eax, eax
0x1800216ec  js      loc_1800217C9
0x1800216f2  mov     rcx, qword ptr [rbp+57h+var_D0.8]; hMem
0x1800216f6  call    cs:__imp_GlobalLock
0x1800216fc  mov     rdi, rax
0x1800216ff  test    rax, rax
0x180021702  jz      loc_1800217BF
0x180021708  mov     rcx, [rbx+8]; hDlg
0x18002170c  mov     edx, 3CEh; nIDDlgItem
0x180021711  call    cs:__imp_GetDlgItem
0x180021717  mov     rdx, [rdi+8]; lpString
0x18002171b  mov     rcx, rax; hWnd
0x18002171e  mov     r14, rax
0x180021721  call    cs:__imp_SetWindowTextW
0x180021727  mov     edx, 0FFFFFFEBh; nIndex
0x18002172c  mov     rcx, r14; hWnd
0x18002172f  call    cs:__imp_GetWindowLongPtrW
0x180021735  mov     rsi, rax
0x180021738  test    rax, rax
0x18002173b  jz      short loc_180021747
0x18002173d  mov     rcx, rax; this
0x180021740  call    ??_GSObjectPickerResult@@QEAAPEAXI@Z; SObjectPickerResult::`scalar deleting destructor'(uint)
0x180021745  xor     esi, esi
0x180021747  mov     rax, [rdi+28h]
0x18002174b  cmp     word ptr [rax], 8
0x18002174f  jnz     short loc_1800217A4
0x180021751  cmp     qword ptr [rax+8], 0
0x180021756  jz      short loc_1800217A4
0x180021758  mov     ecx, 40h ; '@'; Size
0x18002175d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021762  mov     [rbp+57h+var_60], rax
0x180021766  mov     rbx, rax
0x180021769  test    rax, rax
0x18002176c  jz      short loc_1800217A4
0x18002176e  mov     rcx, rax
0x180021771  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180021776  lea     rcx, [rbx+20h]
0x18002177a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002177f  test    rbx, rbx
0x180021782  jz      short loc_1800217A4
0x180021784  mov     rdx, [rdi+8]
0x180021788  mov     rcx, rbx
0x18002178b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180021790  mov     rdx, [rdi+28h]
0x180021794  lea     rcx, [rbx+20h]
0x180021798  mov     rdx, [rdx+8]
0x18002179c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800217a1  mov     rsi, rbx
0x1800217a4  mov     r8, rsi; dwNewLong
0x1800217a7  mov     edx, 0FFFFFFEBh; nIndex
0x1800217ac  mov     rcx, r14; hWnd
0x1800217af  call    cs:__imp_SetWindowLongPtrW
0x1800217b5  mov     rcx, qword ptr [rbp+57h+var_D0.8]; hMem
0x1800217b9  call    cs:__imp_GlobalUnlock
0x1800217bf  lea     rcx, [rbp+57h+var_D0]; LPSTGMEDIUM
0x1800217c3  call    cs:__imp_ReleaseStgMedium
0x1800217c9  mov     rcx, [rsp+110h+var_D8]
0x1800217ce  test    rcx, rcx
0x1800217d1  jz      short loc_1800217DF
0x1800217d3  mov     rax, [rcx]
0x1800217d6  mov     rax, [rax+10h]
0x1800217da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217df  mov     rcx, [rsp+110h+var_E0]
0x1800217e4  test    rcx, rcx
0x1800217e7  jz      short loc_1800217F5
0x1800217e9  mov     rax, [rcx]
0x1800217ec  mov     rax, [rax+10h]
0x1800217f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800217f5  mov     rcx, [rbp+57h+var_20]
0x1800217f9  xor     rcx, rsp; StackCookie
0x1800217fc  call    __security_check_cookie
0x180021801  lea     r11, [rsp+110h+var_10]
0x180021809  mov     rbx, [r11+28h]
0x18002180d  mov     rsi, [r11+30h]
0x180021811  mov     rsp, r11
0x180021814  pop     r14
0x180021816  pop     rdi
0x180021817  pop     rbp
0x180021818  retn
```
