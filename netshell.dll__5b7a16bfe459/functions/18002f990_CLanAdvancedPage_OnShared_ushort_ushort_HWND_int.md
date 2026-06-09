# CLanAdvancedPage::OnShared(ushort,ushort,HWND__ *,int &)

- ea: `0x18002f990`
- end: `0x18002fb73`
- name: `?OnShared@CLanAdvancedPage@@QEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `483`
- prototype: `__int64 __fastcall(CLanAdvancedPage *__hidden this, unsigned __int16, unsigned __int16, HWND, struct IUnknown *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x18002fc20`

## callees

- `0x180009930`
- `0x180017714`
- `0x180018d74`
- `0x18001bc10`
- `0x18002f990`
- `0x1800351e8`
- `0x18003ff7c`
- `0x180065010`

## import_xrefs

- `USER32!EnableWindow` at `0x18002fb35`
- `USER32!EnableWindow` at `0x18002fb5c`
- `USER32!EnableWindow` at `0x18002fb35`
- `USER32!EnableWindow` at `0x18002fb5c`
- `USER32!IsDlgButtonChecked` at `0x18002f9b7`
- `USER32!IsDlgButtonChecked` at `0x18002f9b7`
- `ole32!CoTaskMemFree` at `0x18002fb17`
- `ole32!CoTaskMemFree` at `0x18002fb17`

## pseudocode

```c
__int64 __fastcall CLanAdvancedPage::OnShared(
        HWND *this,
        __int64 a2,
        __int16 a3,
        struct IUnknown *a4,
        struct IUnknown *a5)
{
  HWND *v5; // rsi
  UINT v7; // eax
  BOOL v8; // r14d
  HWND v9; // rcx
  int v10; // edi
  HWND *DlgItem; // rax
  HWND *v12; // rax
  NETCON_PROPERTIES *pProps; // [rsp+40h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-8h] BYREF
  struct IUnknown *v16; // [rsp+80h] [rbp+30h] BYREF
  int v17; // [rsp+90h] [rbp+40h] BYREF
  struct IUnknown *v18; // [rsp+98h] [rbp+48h] BYREF

  v18 = a4;
  LOWORD(v17) = a3;
  v5 = this + 1;
  v7 = IsDlgButtonChecked(this[1], 105);
  v8 = v7;
  if ( !*((_DWORD *)this + 8) )
  {
    if ( v7 )
    {
      v9 = this[11];
      v18 = 0;
      v16 = 0;
      pv = 0;
      pProps = 0;
      a5 = 0;
      if ( (*(int (__fastcall **)(HWND, struct IUnknown **))(*(_QWORD *)v9 + 24LL))(v9, &a5) >= 0 )
      {
        v17 = 0;
        v10 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, struct IUnknown **, int *))a5->lpVtbl[1].QueryInterface)(
                a5,
                1,
                &v18,
                &v17);
        if ( v10 >= 0 && v17 == 1 )
        {
          v10 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IUnknown **))v18->lpVtbl->QueryInterface)(
                  v18,
                  &GUID_85d18b71_3032_11d4_9348_00c04f8eeb71,
                  &v16);
          if ( v10 < 0 )
          {
            ReleaseObj(v18);
          }
          else
          {
            v10 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID *))v16->lpVtbl[1].Release)(v16, &pv);
            ReleaseObj(v16);
            this[6] = (HWND)v18;
            *((_DWORD *)this + 10) = 1;
          }
        }
        else
        {
          *((_DWORD *)this + 10) = 0;
        }
        ReleaseObj(a5);
        if ( v10 >= 0 )
        {
          if ( *((_DWORD *)this + 10) )
          {
            if ( (*(int (__fastcall **)(HWND, NETCON_PROPERTIES **))(*(_QWORD *)this[2] + 56LL))(this[2], &pProps) >= 0 )
            {
              NcMsgBox(hInst, *v5, 0x3E88u, 0x3EA0u, 0x40u, pv, pProps->pszwName);
              NcFreeNetconProperties(pProps);
            }
            CoTaskMemFree(pv);
          }
        }
      }
    }
  }
  DlgItem = (HWND *)ATL::CWindow::GetDlgItem(v5, &v18, 112);
  EnableWindow(*DlgItem, v8);
  if ( IsHomenetBeaconOSType() )
  {
    v12 = (HWND *)ATL::CWindow::GetDlgItem(v5, &v18, 109);
    EnableWindow(*v12, v8);
  }
  return LresFromHr(0);
}

```

## disassembly

```asm
0x18002f990  mov     [rsp-28h+arg_18], r9
0x18002f995  mov     word ptr [rsp-28h+arg_10], r8w
0x18002f99b  push    rbp
0x18002f99c  push    rbx
0x18002f99d  push    rsi
0x18002f99e  push    rdi
0x18002f99f  push    r14
0x18002f9a1  mov     rbp, rsp
0x18002f9a4  sub     rsp, 50h
0x18002f9a8  lea     rsi, [rcx+8]
0x18002f9ac  mov     rbx, rcx
0x18002f9af  mov     rcx, [rsi]; hDlg
0x18002f9b2  mov     edx, 69h ; 'i'; nIDButton
0x18002f9b7  call    cs:__imp_IsDlgButtonChecked
0x18002f9bd  cmp     dword ptr [rbx+20h], 0
0x18002f9c1  mov     r14d, eax
0x18002f9c4  jnz     loc_18002FB1D
0x18002f9ca  test    eax, eax
0x18002f9cc  jz      loc_18002FB1D
0x18002f9d2  mov     rcx, [rbx+58h]
0x18002f9d6  mov     [rbp+arg_18], 0
0x18002f9de  mov     [rbp+arg_0], 0
0x18002f9e6  mov     [rbp+pv], 0
0x18002f9ee  mov     [rbp+pProps], 0
0x18002f9f6  mov     [rbp+arg_20], 0
0x18002f9fe  mov     rdx, [rcx]
0x18002fa01  mov     rax, [rdx+18h]
0x18002fa05  lea     rdx, [rbp+arg_20]
0x18002fa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa0e  test    eax, eax
0x18002fa10  js      loc_18002FB1D
0x18002fa16  mov     rcx, [rbp+arg_20]
0x18002fa1a  lea     r9, [rbp+arg_10]
0x18002fa1e  mov     [rbp+arg_10], 0
0x18002fa25  lea     r8, [rbp+arg_18]
0x18002fa29  mov     edx, 1
0x18002fa2e  mov     rax, [rcx]
0x18002fa31  mov     rax, [rax+18h]
0x18002fa35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa3a  mov     edi, eax
0x18002fa3c  test    eax, eax
0x18002fa3e  js      short loc_18002FAA1
0x18002fa40  cmp     [rbp+arg_10], 1
0x18002fa44  jnz     short loc_18002FAA1
0x18002fa46  mov     rcx, [rbp+arg_18]
0x18002fa4a  lea     r8, [rbp+arg_0]
0x18002fa4e  lea     rdx, _GUID_85d18b71_3032_11d4_9348_00c04f8eeb71
0x18002fa55  mov     rax, [rcx]
0x18002fa58  mov     rax, [rax]
0x18002fa5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa60  mov     edi, eax
0x18002fa62  test    eax, eax
0x18002fa64  js      short loc_18002FA96
0x18002fa66  mov     rcx, [rbp+arg_0]
0x18002fa6a  lea     rdx, [rbp+pv]
0x18002fa6e  mov     rax, [rcx]
0x18002fa71  mov     rax, [rax+28h]
0x18002fa75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fa7a  mov     rcx, [rbp+arg_0]; struct IUnknown *
0x18002fa7e  mov     edi, eax
0x18002fa80  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002fa85  mov     rax, [rbp+arg_18]
0x18002fa89  mov     [rbx+30h], rax
0x18002fa8d  mov     dword ptr [rbx+28h], 1
0x18002fa94  jmp     short loc_18002FAA8
0x18002fa96  mov     rcx, [rbp+arg_18]; struct IUnknown *
0x18002fa9a  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002fa9f  jmp     short loc_18002FAA8
0x18002faa1  mov     dword ptr [rbx+28h], 0
0x18002faa8  mov     rcx, [rbp+arg_20]; struct IUnknown *
0x18002faac  call    ?ReleaseObj@@YAKPEAUIUnknown@@@Z; ReleaseObj(IUnknown *)
0x18002fab1  test    edi, edi
0x18002fab3  js      short loc_18002FB1D
0x18002fab5  cmp     dword ptr [rbx+28h], 0
0x18002fab9  jz      short loc_18002FB1D
0x18002fabb  mov     rcx, [rbx+10h]
0x18002fabf  lea     rdx, [rbp+pProps]
0x18002fac3  mov     rax, [rcx]
0x18002fac6  mov     rax, [rax+38h]
0x18002faca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002facf  test    eax, eax
0x18002fad1  js      short loc_18002FB13
0x18002fad3  mov     rax, [rbp+pProps]
0x18002fad7  mov     r9d, 3EA0h; unsigned int
0x18002fadd  mov     rdx, [rsi]; hWnd
0x18002fae0  mov     rcx, [rax+10h]
0x18002fae4  lea     r8d, [r9-18h]; unsigned int
0x18002fae8  mov     rax, [rbp+pv]
0x18002faec  mov     [rsp+50h+var_20], rcx
0x18002faf1  mov     rcx, cs:hInst; hModule
0x18002faf8  mov     [rsp+50h+var_28], rax
0x18002fafd  mov     [rsp+50h+uType], 40h ; '@'; uType
0x18002fb05  call    ?NcMsgBox@@YAHPEAUHINSTANCE__@@PEAUHWND__@@IIIZZ; NcMsgBox(HINSTANCE__ *,HWND__ *,uint,uint,uint,...)
0x18002fb0a  mov     rcx, [rbp+pProps]; pProps
0x18002fb0e  call    NcFreeNetconProperties
0x18002fb13  mov     rcx, [rbp+pv]; pv
0x18002fb17  call    cs:__imp_CoTaskMemFree
0x18002fb1d  mov     r8d, 70h ; 'p'
0x18002fb23  lea     rdx, [rbp+arg_18]
0x18002fb27  mov     rcx, rsi
0x18002fb2a  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002fb2f  mov     edx, r14d; bEnable
0x18002fb32  mov     rcx, [rax]; hWnd
0x18002fb35  call    cs:__imp_EnableWindow
0x18002fb3b  call    ?IsHomenetBeaconOSType@@YAHXZ; IsHomenetBeaconOSType(void)
0x18002fb40  test    eax, eax
0x18002fb42  jz      short loc_18002FB62
0x18002fb44  mov     r8d, 6Dh ; 'm'
0x18002fb4a  lea     rdx, [rbp+arg_18]
0x18002fb4e  mov     rcx, rsi
0x18002fb51  call    ?GetDlgItem@CWindow@ATL@@QEBA?AV12@H@Z; ATL::CWindow::GetDlgItem(int)
0x18002fb56  mov     edx, r14d; bEnable
0x18002fb59  mov     rcx, [rax]; hWnd
0x18002fb5c  call    cs:__imp_EnableWindow
0x18002fb62  xor     ecx, ecx; int
0x18002fb64  add     rsp, 50h
0x18002fb68  pop     r14
0x18002fb6a  pop     rdi
0x18002fb6b  pop     rsi
0x18002fb6c  pop     rbx
0x18002fb6d  pop     rbp
0x18002fb6e  jmp     ?LresFromHr@@YA_JJ@Z; LresFromHr(long)
```
