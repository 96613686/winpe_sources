# CSnapin::_CreatePropertyInspector(IPropertySheetCallback *)

- ea: `0x18001d134`
- end: `0x18001d30f`
- name: `?_CreatePropertyInspector@CSnapin@@AEAAJPEAUIPropertySheetCallback@@@Z`
- size: `475`
- prototype: `__int64 __fastcall(CSnapin *__hidden this, struct IPropertySheetCallback *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001bd90`

## callees

- `0x180002928`
- `0x18000513c`
- `0x180008e8c`
- `0x180008f84`
- `0x180014b88`
- `0x18001a2d0`
- `0x18001d134`
- `0x180022292`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001d283`
- `KERNEL32!GetLastError` at `0x18001d283`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18001d196`
- `ole32!CoMarshalInterThreadInterfaceInStream` at `0x18001d196`

## pseudocode

```c
__int64 __fastcall CSnapin::_CreatePropertyInspector(CSnapin *this, struct IPropertySheetCallback *a2)
{
  int v4; // ebx
  _WORD *v5; // rax
  _WORD *v6; // rbx
  LPSTREAM v7; // rdx
  __int64 PropertySheetPageW; // rax
  __int64 v9; // rdi
  signed int LastError; // eax
  struct _EVENTLOGRECORD *v11; // rax
  int v12; // r8d
  _DWORD v14[2]; // [rsp+20h] [rbp-39h] BYREF
  HINSTANCE v15; // [rsp+28h] [rbp-31h]
  __int64 v16; // [rsp+30h] [rbp-29h]
  __int64 (__fastcall *v17)(HWND, unsigned int, unsigned __int64, __int64); // [rsp+48h] [rbp-11h]
  _WORD *v18; // [rsp+50h] [rbp-9h]
  unsigned int (__fastcall *v19)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+58h] [rbp-1h]
  LPSTREAM ppStm; // [rsp+C0h] [rbp+67h] BYREF
  _WORD *v21; // [rsp+D0h] [rbp+77h]

  memset_0(v14, 0, 0x68u);
  ppStm = 0;
  *((_DWORD *)this + 380) = 1;
  v4 = CoMarshalInterThreadInterfaceInStream(
         &IID_IResultPrshtActions,
         (LPUNKNOWN)(((unsigned __int64)this + 40) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64)),
         &ppStm);
  if ( v4 < 0 )
    goto LABEL_12;
  v5 = operator new(0x90u);
  v21 = v5;
  v6 = v5;
  if ( !v5 )
  {
    v4 = -2147024882;
    goto LABEL_12;
  }
  v7 = ppStm;
  v5[4] = 0;
  *((_QWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 3) = 0;
  *((_DWORD *)v5 + 8) = 0;
  *(_QWORD *)v5 = &CDetailsPage::`vftable';
  *((_QWORD *)v5 + 6) = 0;
  *((_QWORD *)v5 + 7) = 0;
  *((_DWORD *)v5 + 16) = 0;
  *((_QWORD *)v5 + 9) = 0;
  *((_DWORD *)v5 + 20) = 0;
  *((_DWORD *)v5 + 23) = -1;
  *((_DWORD *)v5 + 24) = -1;
  *((_QWORD *)v5 + 5) = v7;
  *((_DWORD *)v5 + 21) = 80;
  *((_DWORD *)v5 + 22) = 84;
  *((_DWORD *)v5 + 25) = 130;
  std::wstring::wstring(v5 + 56);
  *((_QWORD *)v6 + 13) = 0;
  ppStm = 0;
  memset_0(v14, 0, 0x68u);
  v15 = g_hinst;
  v17 = CPropSheetPage::DlgProc;
  v19 = PropSheetCallback;
  v14[0] = 104;
  v14[1] = 128;
  v16 = 100;
  v18 = v6;
  PropertySheetPageW = IsolationAwareCreatePropertySheetPageW(v14);
  v9 = PropertySheetPageW;
  if ( PropertySheetPageW )
  {
    v4 = ((__int64 (__fastcall *)(struct IPropertySheetCallback *, __int64))a2->lpVtbl->AddPage)(a2, PropertySheetPageW);
    if ( v4 >= 0 )
    {
      v11 = CResultRecs::CopyRecord((CSnapin *)((char *)this + 88), *((_DWORD *)this + 396));
      CInspectorInfo::UpdateCurResultRec((CSnapin *)((char *)this + 1520), v11, v12);
      return (unsigned int)v4;
    }
    IsolationAwareDestroyPropertySheetPage(v9);
    goto LABEL_12;
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 < 0 )
  {
LABEL_12:
    if ( ppStm )
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppStm + 16LL))(ppStm);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18001d134  mov     [rsp-8+arg_8], rbx
0x18001d139  push    rbp
0x18001d13a  push    rsi
0x18001d13b  push    rdi
0x18001d13c  push    r14
0x18001d13e  push    r15
0x18001d140  lea     rbp, [rsp-37h]
0x18001d145  sub     rsp, 90h
0x18001d14c  mov     r14, rdx
0x18001d14f  mov     rsi, rcx
0x18001d152  mov     edi, 68h ; 'h'
0x18001d157  lea     rcx, [rbp+57h+var_90]; void *
0x18001d15b  mov     r8d, edi; Size
0x18001d15e  xor     edx, edx; Val
0x18001d160  call    memset_0
0x18001d165  lea     r8, [rsi+28h]
0x18001d169  mov     [rbp+57h+ppStm], 0
0x18001d171  mov     rax, rsi
0x18001d174  lea     r15, [rsi+5F0h]
0x18001d17b  neg     rax
0x18001d17e  mov     dword ptr [r15], 1
0x18001d185  lea     rcx, IID_IResultPrshtActions; riid
0x18001d18c  sbb     rdx, rdx
0x18001d18f  and     rdx, r8; pUnk
0x18001d192  lea     r8, [rbp+57h+ppStm]; ppStm
0x18001d196  call    cs:__imp_CoMarshalInterThreadInterfaceInStream
0x18001d19c  mov     ebx, eax
0x18001d19e  test    eax, eax
0x18001d1a0  js      loc_18001D2E1
0x18001d1a6  lea     ecx, [rdi+28h]; Size
0x18001d1a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d1ae  mov     [rbp+57h+arg_10], rax
0x18001d1b2  mov     rbx, rax
0x18001d1b5  test    rax, rax
0x18001d1b8  jz      loc_18001D2DC
0x18001d1be  mov     rdx, [rbp+57h+ppStm]
0x18001d1c2  xor     ecx, ecx
0x18001d1c4  mov     [rax+8], cx
0x18001d1c8  mov     [rax+10h], rcx
0x18001d1cc  mov     [rax+18h], rcx
0x18001d1d0  mov     [rax+20h], ecx
0x18001d1d3  lea     rax, ??_7CDetailsPage@@6B@; const CDetailsPage::`vftable'
0x18001d1da  mov     [rbx], rax
0x18001d1dd  or      eax, 0FFFFFFFFh
0x18001d1e0  mov     [rbx+30h], rcx
0x18001d1e4  mov     [rbx+38h], rcx
0x18001d1e8  mov     [rbx+40h], ecx
0x18001d1eb  mov     [rbx+48h], rcx
0x18001d1ef  mov     [rbx+50h], ecx
0x18001d1f2  lea     rcx, [rbx+70h]
0x18001d1f6  mov     [rbx+5Ch], eax
0x18001d1f9  mov     [rbx+60h], eax
0x18001d1fc  mov     [rbx+28h], rdx
0x18001d200  mov     dword ptr [rbx+54h], 50h ; 'P'
0x18001d207  mov     dword ptr [rbx+58h], 54h ; 'T'
0x18001d20e  mov     dword ptr [rbx+64h], 82h
0x18001d215  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001d21a  xor     eax, eax
0x18001d21c  mov     [rbx+68h], rax
0x18001d220  test    rbx, rbx
0x18001d223  jz      loc_18001D2DC
0x18001d229  mov     r8d, edi; Size
0x18001d22c  mov     [rbp+57h+ppStm], rax
0x18001d230  xor     edx, edx; Val
0x18001d232  lea     rcx, [rbp+57h+var_90]; void *
0x18001d236  call    memset_0
0x18001d23b  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18001d242  lea     rcx, [rbp+57h+var_90]
0x18001d246  mov     [rbp+57h+var_88], rax
0x18001d24a  lea     rax, ?DlgProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropSheetPage::DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18001d251  mov     [rbp+57h+var_68], rax
0x18001d255  lea     rax, ?PropSheetCallback@@YAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; PropSheetCallback(HWND__ *,uint,_PROPSHEETPAGEW *)
0x18001d25c  mov     [rbp+57h+var_58], rax
0x18001d260  mov     [rbp+57h+var_90], edi
0x18001d263  mov     [rbp+57h+var_8C], 80h
0x18001d26a  mov     [rbp+57h+var_80], 64h ; 'd'
0x18001d272  mov     [rbp+57h+var_60], rbx
0x18001d276  call    IsolationAwareCreatePropertySheetPageW
0x18001d27b  mov     rdi, rax
0x18001d27e  test    rax, rax
0x18001d281  jnz     short loc_18001D29E
0x18001d283  call    cs:__imp_GetLastError
0x18001d289  mov     ebx, eax
0x18001d28b  test    eax, eax
0x18001d28d  jle     short loc_18001D298
0x18001d28f  movzx   ebx, ax
0x18001d292  or      ebx, 80070000h
0x18001d298  test    ebx, ebx
0x18001d29a  jns     short loc_18001D2F6
0x18001d29c  jmp     short loc_18001D2E1
0x18001d29e  mov     rax, [r14]
0x18001d2a1  mov     rdx, rdi
0x18001d2a4  mov     rcx, r14
0x18001d2a7  mov     rax, [rax+18h]
0x18001d2ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2b0  mov     ebx, eax
0x18001d2b2  test    eax, eax
0x18001d2b4  jns     short loc_18001D2C0
0x18001d2b6  mov     rcx, rdi
0x18001d2b9  call    IsolationAwareDestroyPropertySheetPage
0x18001d2be  jmp     short loc_18001D2E1
0x18001d2c0  mov     edx, [rsi+630h]; unsigned int
0x18001d2c6  lea     rcx, [rsi+58h]; this
0x18001d2ca  call    ?CopyRecord@CResultRecs@@QEAAPEAU_EVENTLOGRECORD@@K@Z; CResultRecs::CopyRecord(ulong)
0x18001d2cf  mov     rdx, rax; struct _EVENTLOGRECORD *
0x18001d2d2  mov     rcx, r15; this
0x18001d2d5  call    ?UpdateCurResultRec@CInspectorInfo@@QEAAXPEAU_EVENTLOGRECORD@@H@Z; CInspectorInfo::UpdateCurResultRec(_EVENTLOGRECORD *,int)
0x18001d2da  jmp     short loc_18001D2F6
0x18001d2dc  mov     ebx, 8007000Eh
0x18001d2e1  mov     rcx, [rbp+57h+ppStm]
0x18001d2e5  test    rcx, rcx
0x18001d2e8  jz      short loc_18001D2F6
0x18001d2ea  mov     rax, [rcx]
0x18001d2ed  mov     rax, [rax+10h]
0x18001d2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2f6  mov     eax, ebx
0x18001d2f8  mov     rbx, [rsp+0B0h+arg_8]
0x18001d300  add     rsp, 90h
0x18001d307  pop     r15
0x18001d309  pop     r14
0x18001d30b  pop     rdi
0x18001d30c  pop     rsi
0x18001d30d  pop     rbp
0x18001d30e  retn
```
