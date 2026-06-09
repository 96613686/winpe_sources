# CComponentData::CreatePropertyPages(IPropertySheetCallback *,__int64,IDataObject *)

- ea: `0x180005ab0`
- end: `0x180005dd8`
- name: `?CreatePropertyPages@CComponentData@@UEAAJPEAUIPropertySheetCallback@@_JPEAUIDataObject@@@Z`
- size: `808`
- prototype: `int(CComponentData *__hidden this, struct IPropertySheetCallback *, __int64, struct IDataObject *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002928`
- `0x180005ab0`
- `0x1800075f0`
- `0x180008e8c`
- `0x180008f84`
- `0x18001f638`
- `0x180022108`
- `0x180022292`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005d09`
- `KERNEL32!GetLastError` at `0x180005d09`
- `USER32!SetForegroundWindow` at `0x180005b10`
- `USER32!SetForegroundWindow` at `0x180005b10`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180005b74`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180005bf8`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180005b74`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x180005bf8`

## pseudocode

```c
int __fastcall CComponentData::CreatePropertyPages(
        CComponentData *this,
        struct IPropertySheetCallback *a2,
        __int64 a3,
        struct IDataObject *a4)
{
  struct CDataObject *OwnDataObject; // rax
  __int64 v9; // r13
  HWND v10; // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rsi
  int v12; // r12d
  int v13; // edi
  _WORD *v14; // rax
  _WORD *v15; // rbx
  LPSTREAM v16; // r8
  void (__fastcall ***v17)(_QWORD, __int64); // rax
  LPSTREAM v18; // rcx
  __int64 PropertySheetPageW; // rax
  __int64 v20; // r14
  __int64 v21; // rax
  signed int LastError; // eax
  LPSTREAM ppStm; // [rsp+20h] [rbp-79h] BYREF
  LPSTREAM v24; // [rsp+28h] [rbp-71h] BYREF
  LPUNKNOWN pUnk; // [rsp+30h] [rbp-69h]
  _DWORD v26[2]; // [rsp+40h] [rbp-59h] BYREF
  HINSTANCE v27; // [rsp+48h] [rbp-51h]
  __int64 v28; // [rsp+50h] [rbp-49h]
  __int64 (__fastcall *v29)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+68h] [rbp-31h]
  void (__fastcall ***v30)(_QWORD, __int64); // [rsp+70h] [rbp-29h]
  unsigned int (__fastcall *v31)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+78h] [rbp-21h]

  OwnDataObject = ExtractOwnDataObject(a4);
  if ( !OwnDataObject )
    goto LABEL_7;
  if ( *((_DWORD *)OwnDataObject + 6) == 32770 )
    return CComponentData::_CreateWizardPage((CComponentData *)((char *)this - 16), a2, a3);
  if ( !*((_DWORD *)OwnDataObject + 7) )
    goto LABEL_7;
  v9 = *((_QWORD *)OwnDataObject + 2);
  v10 = *(HWND *)(v9 + 4848);
  if ( v10 )
  {
    SetForegroundWindow(v10);
LABEL_7:
    MMCFreeNotifyHandle(a3);
    return 0;
  }
  memset_0(v26, 0, 0x68u);
  ppStm = 0;
  v24 = 0;
  v11 = 0;
  v12 = 0;
  pUnk = (LPUNKNOWN)(((unsigned __int64)this + 16) & -(__int64)(this != (CComponentData *)16));
  v13 = CoMarshalInterThreadInterfaceInStream(&IID_INamespacePrshtActions, pUnk, &ppStm);
  if ( v13 < 0 )
    goto LABEL_26;
  v14 = operator new(0x50u);
  v15 = v14;
  if ( !v14 )
  {
    v13 = -2147024882;
    MMCFreeNotifyHandle(a3);
LABEL_26:
    v15 = 0;
    goto LABEL_27;
  }
  v16 = ppStm;
  v14[4] = 0;
  *((_QWORD *)v14 + 2) = 0;
  *((_QWORD *)v14 + 3) = 0;
  *((_DWORD *)v14 + 8) = 0;
  *(_QWORD *)v14 = &CGeneralPage::`vftable';
  *((_QWORD *)v14 + 5) = v16;
  *((_QWORD *)v14 + 6) = 0;
  *((_QWORD *)v14 + 7) = v9;
  *((_DWORD *)v14 + 16) = 0;
  *((_DWORD *)v14 + 17) = 0x4000;
  *((_DWORD *)v14 + 18) = 122;
  *((_DWORD *)v14 + 19) = 7;
  _InterlockedIncrement((volatile signed __int32 *)(v9 + 4760));
  ppStm = 0;
  v13 = CoMarshalInterThreadInterfaceInStream(&IID_INamespacePrshtActions, pUnk, &v24);
  if ( v13 < 0 )
  {
    MMCFreeNotifyHandle(a3);
LABEL_27:
    if ( ppStm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
    if ( v24 )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v24 + 16LL))(v24);
    if ( !v12 && v15 )
      (**(void (__fastcall ***)(_WORD *, __int64))v15)(v15, 1);
    if ( v11 )
      (**v11)(v11, 1);
    return v13;
  }
  v17 = (void (__fastcall ***)(_QWORD, __int64))operator new(0x40u);
  v11 = v17;
  if ( !v17 )
  {
    v13 = -2147024882;
    MMCFreeNotifyHandle(a3);
    v11 = 0;
    goto LABEL_27;
  }
  v18 = v24;
  *((_WORD *)v17 + 4) = 0;
  v17[2] = 0;
  v17[6] = (void (__fastcall **)(_QWORD, __int64))v18;
  *v17 = (void (__fastcall **)(_QWORD, __int64))&CFilterPage::`vftable';
  v17[5] = (void (__fastcall **)(_QWORD, __int64))v9;
  v17[7] = 0;
  v24 = 0;
  *((_QWORD *)v15 + 3) = a3;
  *((_DWORD *)v15 + 8) = 1;
  v17[3] = (void (__fastcall **)(_QWORD, __int64))a3;
  *((_DWORD *)v17 + 8) = 0;
  memset_0(v26, 0, 0x68u);
  v27 = g_hinst;
  v29 = CPropSheetPage::DlgProc;
  v31 = PropSheetCallback;
  v26[0] = 104;
  v26[1] = 128;
  v28 = 103;
  v30 = (void (__fastcall ***)(_QWORD, __int64))v15;
  PropertySheetPageW = IsolationAwareCreatePropertySheetPageW(v26);
  v20 = PropertySheetPageW;
  if ( !PropertySheetPageW )
  {
    v13 = -2147467259;
    goto LABEL_27;
  }
  v13 = ((__int64 (__fastcall *)(struct IPropertySheetCallback *, __int64))a2->lpVtbl->AddPage)(a2, PropertySheetPageW);
  if ( v13 < 0 )
  {
LABEL_16:
    IsolationAwareDestroyPropertySheetPage(v20);
    goto LABEL_27;
  }
  v28 = 102;
  v30 = v11;
  v21 = IsolationAwareCreatePropertySheetPageW(v26);
  v20 = v21;
  if ( !v21 )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
      return v13;
    v12 = 1;
    goto LABEL_27;
  }
  v13 = ((__int64 (__fastcall *)(struct IPropertySheetCallback *, __int64))a2->lpVtbl->AddPage)(a2, v21);
  if ( v13 < 0 )
  {
    v12 = 1;
    goto LABEL_16;
  }
  return v13;
}

```

## disassembly

```asm
0x180005ab0  push    rbp
0x180005ab2  push    rbx
0x180005ab3  push    rsi
0x180005ab4  push    rdi
0x180005ab5  push    r12
0x180005ab7  push    r13
0x180005ab9  push    r14
0x180005abb  push    r15
0x180005abd  lea     rbp, [rsp-1Fh]
0x180005ac2  sub     rsp, 0B8h
0x180005ac9  mov     rbx, rcx
0x180005acc  mov     r14, r8
0x180005acf  mov     rcx, r9; struct IDataObject *
0x180005ad2  mov     r15, rdx
0x180005ad5  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x180005ada  xor     edi, edi
0x180005adc  test    rax, rax
0x180005adf  jz      short loc_180005B16
0x180005ae1  cmp     dword ptr [rax+18h], 8002h
0x180005ae8  jnz     short loc_180005AFB
0x180005aea  lea     rcx, [rbx-10h]; this
0x180005aee  mov     r8, r14; __int64
0x180005af1  mov     rdx, r15; struct IPropertySheetCallback *
0x180005af4  call    ?_CreateWizardPage@CComponentData@@AEAAJPEAUIPropertySheetCallback@@_J@Z; CComponentData::_CreateWizardPage(IPropertySheetCallback *,__int64)
0x180005af9  jmp     short loc_180005B20
0x180005afb  cmp     [rax+1Ch], edi
0x180005afe  jz      short loc_180005B16
0x180005b00  mov     r13, [rax+10h]
0x180005b04  mov     rcx, [r13+12F0h]; hWnd
0x180005b0b  test    rcx, rcx
0x180005b0e  jz      short loc_180005B34
0x180005b10  call    cs:__imp_SetForegroundWindow
0x180005b16  mov     rcx, r14; lNotifyHandle
0x180005b19  call    MMCFreeNotifyHandle
0x180005b1e  xor     eax, eax
0x180005b20  add     rsp, 0B8h
0x180005b27  pop     r15
0x180005b29  pop     r14
0x180005b2b  pop     r13
0x180005b2d  pop     r12
0x180005b2f  pop     rdi
0x180005b30  pop     rsi
0x180005b31  pop     rbx
0x180005b32  pop     rbp
0x180005b33  retn
0x180005b34  xor     edx, edx; Val
0x180005b36  lea     rcx, [rbp+57h+var_B0]; void *
0x180005b3a  lea     r8d, [rdx+68h]; Size
0x180005b3e  call    memset_0
0x180005b43  lea     rcx, [rbx+10h]
0x180005b47  mov     [rbp+57h+ppStm], rdi
0x180005b4b  lea     rax, [rbx-10h]
0x180005b4f  mov     [rbp+57h+var_C8], rdi
0x180005b53  neg     rax
0x180005b56  lea     r8, [rbp+57h+ppStm]; ppStm
0x180005b5a  mov     rsi, rdi
0x180005b5d  mov     r12d, edi
0x180005b60  sbb     rax, rax
0x180005b63  and     rax, rcx
0x180005b66  lea     rcx, IID_INamespacePrshtActions; riid
0x180005b6d  mov     rdx, rax; pUnk
0x180005b70  mov     [rbp+57h+pUnk], rax
0x180005b74  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180005b7a  mov     edi, eax
0x180005b7c  test    eax, eax
0x180005b7e  js      loc_180005D70
0x180005b84  mov     ecx, 50h ; 'P'; Size
0x180005b89  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005b8e  xor     ecx, ecx
0x180005b90  mov     rbx, rax
0x180005b93  test    rax, rax
0x180005b96  jz      loc_180005D63
0x180005b9c  mov     r8, [rbp+57h+ppStm]
0x180005ba0  mov     [rax+8], cx
0x180005ba4  mov     [rax+10h], rcx
0x180005ba8  mov     [rax+18h], rcx
0x180005bac  mov     [rax+20h], ecx
0x180005baf  lea     rax, ??_7CGeneralPage@@6B@; const CGeneralPage::`vftable'
0x180005bb6  mov     [rbx], rax
0x180005bb9  mov     [rbx+28h], r8
0x180005bbd  mov     [rbx+30h], rcx
0x180005bc1  mov     [rbx+38h], r13
0x180005bc5  mov     [rbx+40h], ecx
0x180005bc8  mov     dword ptr [rbx+44h], 4000h
0x180005bcf  mov     dword ptr [rbx+48h], 7Ah ; 'z'
0x180005bd6  mov     dword ptr [rbx+4Ch], 7
0x180005bdd  lock inc dword ptr [r13+1298h]
0x180005be5  mov     rdx, [rbp+57h+pUnk]; pUnk
0x180005be9  lea     r8, [rbp+57h+var_C8]; ppStm
0x180005bed  mov     [rbp+57h+ppStm], rcx
0x180005bf1  lea     rcx, IID_INamespacePrshtActions; riid
0x180005bf8  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x180005bfe  mov     edi, eax
0x180005c00  test    eax, eax
0x180005c02  jns     short loc_180005C11
0x180005c04  mov     rcx, r14; lNotifyHandle
0x180005c07  call    MMCFreeNotifyHandle
0x180005c0c  jmp     loc_180005D72
0x180005c11  mov     ecx, 40h ; '@'; Size
0x180005c16  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c1b  mov     rsi, rax
0x180005c1e  test    rax, rax
0x180005c21  jz      loc_180005D52
0x180005c27  mov     rcx, [rbp+57h+var_C8]
0x180005c2b  xor     eax, eax
0x180005c2d  mov     [rsi+8], ax
0x180005c31  mov     edi, 68h ; 'h'
0x180005c36  mov     [rsi+10h], rax
0x180005c3a  mov     r8d, edi; Size
0x180005c3d  mov     [rsi+30h], rcx
0x180005c41  lea     rax, ??_7CFilterPage@@6B@; const CFilterPage::`vftable'
0x180005c48  mov     [rsi], rax
0x180005c4b  lea     rcx, [rbp+57h+var_B0]; void *
0x180005c4f  mov     [rsi+28h], r13
0x180005c53  xor     edx, edx; Val
0x180005c55  mov     [rsi+38h], r12
0x180005c59  mov     [rbp+57h+var_C8], r12
0x180005c5d  mov     [rbx+18h], r14
0x180005c61  mov     dword ptr [rbx+20h], 1
0x180005c68  mov     [rsi+18h], r14
0x180005c6c  mov     [rsi+20h], r12d
0x180005c70  call    memset_0
0x180005c75  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x180005c7c  lea     rcx, [rbp+57h+var_B0]
0x180005c80  mov     [rbp+57h+var_A8], rax
0x180005c84  lea     rax, ?DlgProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropSheetPage::DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x180005c8b  mov     [rbp+57h+var_88], rax
0x180005c8f  lea     rax, ?PropSheetCallback@@YAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; PropSheetCallback(HWND__ *,uint,_PROPSHEETPAGEW *)
0x180005c96  mov     [rbp+57h+var_78], rax
0x180005c9a  mov     [rbp+57h+var_B0], edi
0x180005c9d  mov     [rbp+57h+var_AC], 80h
0x180005ca4  mov     [rbp+57h+var_A0], 67h ; 'g'
0x180005cac  mov     [rbp+57h+var_80], rbx
0x180005cb0  call    IsolationAwareCreatePropertySheetPageW
0x180005cb5  mov     r14, rax
0x180005cb8  test    rax, rax
0x180005cbb  jnz     short loc_180005CC7
0x180005cbd  mov     edi, 80004005h
0x180005cc2  jmp     loc_180005D72
0x180005cc7  mov     rax, [r15]
0x180005cca  mov     rdx, r14
0x180005ccd  mov     rcx, r15
0x180005cd0  mov     rax, [rax+18h]
0x180005cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cd9  mov     edi, eax
0x180005cdb  test    eax, eax
0x180005cdd  jns     short loc_180005CEC
0x180005cdf  mov     rcx, r14
0x180005ce2  call    IsolationAwareDestroyPropertySheetPage
0x180005ce7  jmp     loc_180005D72
0x180005cec  lea     rcx, [rbp+57h+var_B0]
0x180005cf0  mov     [rbp+57h+var_A0], 66h ; 'f'
0x180005cf8  mov     [rbp+57h+var_80], rsi
0x180005cfc  call    IsolationAwareCreatePropertySheetPageW
0x180005d01  mov     r14, rax
0x180005d04  test    rax, rax
0x180005d07  jnz     short loc_180005D2E
0x180005d09  call    cs:__imp_GetLastError
0x180005d0f  mov     edi, eax
0x180005d11  test    eax, eax
0x180005d13  jle     short loc_180005D1E
0x180005d15  movzx   edi, ax
0x180005d18  or      edi, 80070000h
0x180005d1e  test    edi, edi
0x180005d20  jns     loc_180005DD1
0x180005d26  mov     r12d, 1
0x180005d2c  jmp     short loc_180005D72
0x180005d2e  mov     rax, [r15]
0x180005d31  mov     rdx, r14
0x180005d34  mov     rcx, r15
0x180005d37  mov     rax, [rax+18h]
0x180005d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d40  mov     edi, eax
0x180005d42  test    eax, eax
0x180005d44  jns     loc_180005DD1
0x180005d4a  mov     r12d, 1
0x180005d50  jmp     short loc_180005CDF
0x180005d52  mov     rcx, r14; lNotifyHandle
0x180005d55  mov     edi, 8007000Eh
0x180005d5a  call    MMCFreeNotifyHandle
0x180005d5f  xor     esi, esi
0x180005d61  jmp     short loc_180005D72
0x180005d63  mov     rcx, r14; lNotifyHandle
0x180005d66  mov     edi, 8007000Eh
0x180005d6b  call    MMCFreeNotifyHandle
0x180005d70  xor     ebx, ebx
0x180005d72  mov     rcx, [rbp+57h+ppStm]
0x180005d76  test    rcx, rcx
0x180005d79  jz      short loc_180005D87
0x180005d7b  mov     rax, [rcx]
0x180005d7e  mov     rax, [rax+10h]
0x180005d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d87  mov     rcx, [rbp+57h+var_C8]
0x180005d8b  test    rcx, rcx
0x180005d8e  jz      short loc_180005D9C
0x180005d90  mov     rax, [rcx]
0x180005d93  mov     rax, [rax+10h]
0x180005d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9c  test    r12d, r12d
0x180005d9f  jnz     short loc_180005DB9
0x180005da1  test    rbx, rbx
0x180005da4  jz      short loc_180005DB9
0x180005da6  mov     rax, [rbx]
0x180005da9  lea     edx, [r12+1]
0x180005dae  mov     rcx, rbx
0x180005db1  mov     rax, [rax]
0x180005db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db9  test    rsi, rsi
0x180005dbc  jz      short loc_180005DD1
0x180005dbe  mov     rax, [rsi]
0x180005dc1  mov     edx, 1
0x180005dc6  mov     rcx, rsi
0x180005dc9  mov     rax, [rax]
0x180005dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd1  mov     eax, edi
0x180005dd3  jmp     loc_180005B20
```
