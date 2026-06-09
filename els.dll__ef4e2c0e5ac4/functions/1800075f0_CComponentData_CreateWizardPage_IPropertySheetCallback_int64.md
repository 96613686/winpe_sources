# CComponentData::_CreateWizardPage(IPropertySheetCallback *,__int64)

- ea: `0x1800075f0`
- end: `0x18000771e`
- name: `?_CreateWizardPage@CComponentData@@AEAAJPEAUIPropertySheetCallback@@_J@Z`
- size: `302`
- prototype: `int(CComponentData *__hidden this, struct IPropertySheetCallback *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180005ab0`

## callees

- `0x180002928`
- `0x1800075f0`
- `0x180008e8c`
- `0x180008f84`
- `0x180022108`
- `0x180022292`
- `0x180024010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800076ca`
- `KERNEL32!GetLastError` at `0x1800076ca`

## pseudocode

```c
__int64 __fastcall CComponentData::_CreateWizardPage(
        CComponentData *this,
        struct IPropertySheetCallback *a2,
        LONG_PTR a3)
{
  _WORD *v6; // rax
  _WORD *v7; // rbx
  __int64 PropertySheetPageW; // rax
  __int64 v9; // rdi
  signed int LastError; // eax
  int v11; // ebx
  _DWORD v13[2]; // [rsp+20h] [rbp-98h] BYREF
  HINSTANCE v14; // [rsp+28h] [rbp-90h]
  __int64 v15; // [rsp+30h] [rbp-88h]
  __int64 (__fastcall *v16)(HWND, unsigned int, __int64, __int64); // [rsp+48h] [rbp-70h]
  _WORD *v17; // [rsp+50h] [rbp-68h]
  unsigned int (__fastcall *v18)(HWND, unsigned int, struct _PROPSHEETPAGEW *); // [rsp+58h] [rbp-60h]

  memset_0(v13, 0, 0x68u);
  v6 = operator new(0x30u);
  v7 = v6;
  if ( v6 )
  {
    v6[4] = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_DWORD *)v6 + 8) = 0;
    *(_QWORD *)v6 = &CWizardPage::`vftable';
    *((_QWORD *)v6 + 5) = this;
    *((_QWORD *)v6 + 3) = a3;
    *((_DWORD *)v6 + 8) = 1;
    memset_0(v13, 0, 0x68u);
    v14 = g_hinst;
    v16 = CPropSheetPage::DlgProc;
    v18 = PropSheetCallback;
    v13[0] = 104;
    v13[1] = 128;
    v15 = 970;
    v17 = v7;
    PropertySheetPageW = IsolationAwareCreatePropertySheetPageW((__int64)v13);
    v9 = PropertySheetPageW;
    if ( PropertySheetPageW )
    {
      v11 = ((__int64 (__fastcall *)(struct IPropertySheetCallback *, __int64))a2->lpVtbl->AddPage)(
              a2,
              PropertySheetPageW);
      if ( v11 < 0 )
        IsolationAwareDestroyPropertySheetPage(v9);
    }
    else
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    v11 = -2147024882;
    MMCFreeNotifyHandle(a3);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800075f0  push    rbx
0x1800075f2  push    rbp
0x1800075f3  push    rsi
0x1800075f4  push    rdi
0x1800075f5  sub     rsp, 98h
0x1800075fc  mov     rsi, rdx
0x1800075ff  mov     rdi, r8
0x180007602  xor     edx, edx; Val
0x180007604  mov     rbp, rcx
0x180007607  lea     rcx, [rsp+0B8h+var_98]; void *
0x18000760c  lea     r8d, [rdx+68h]; Size
0x180007610  call    memset_0
0x180007615  mov     ecx, 30h ; '0'; Size
0x18000761a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000761f  mov     [rsp+0B8h+arg_18], rax
0x180007627  mov     rbx, rax
0x18000762a  test    rax, rax
0x18000762d  jz      loc_180007703
0x180007633  xor     ecx, ecx
0x180007635  mov     [rax+8], cx
0x180007639  mov     [rax+10h], rcx
0x18000763d  mov     [rax+18h], rcx
0x180007641  mov     [rax+20h], ecx
0x180007644  lea     rax, ??_7CWizardPage@@6B@; const CWizardPage::`vftable'
0x18000764b  mov     [rbx], rax
0x18000764e  mov     [rbx+28h], rbp
0x180007652  test    rbx, rbx
0x180007655  jz      loc_180007703
0x18000765b  lea     r8d, [rcx+68h]; Size
0x18000765f  mov     [rbx+18h], rdi
0x180007663  lea     rcx, [rsp+0B8h+var_98]; void *
0x180007668  mov     dword ptr [rbx+20h], 1
0x18000766f  xor     edx, edx; Val
0x180007671  call    memset_0
0x180007676  mov     rax, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hinst
0x18000767d  lea     rcx, [rsp+0B8h+var_98]
0x180007682  mov     [rsp+0B8h+var_90], rax
0x180007687  lea     rax, ?DlgProc@CPropSheetPage@@SA_JPEAUHWND__@@I_K_J@Z; CPropSheetPage::DlgProc(HWND__ *,uint,unsigned __int64,__int64)
0x18000768e  mov     [rsp+0B8h+var_70], rax
0x180007693  lea     rax, ?PropSheetCallback@@YAIPEAUHWND__@@IPEAU_PROPSHEETPAGEW@@@Z; PropSheetCallback(HWND__ *,uint,_PROPSHEETPAGEW *)
0x18000769a  mov     [rsp+0B8h+var_60], rax
0x18000769f  mov     [rsp+0B8h+var_98], 68h ; 'h'
0x1800076a7  mov     [rsp+0B8h+var_94], 80h
0x1800076af  mov     [rsp+0B8h+var_88], 3CAh
0x1800076b8  mov     [rsp+0B8h+var_68], rbx
0x1800076bd  call    IsolationAwareCreatePropertySheetPageW
0x1800076c2  mov     rdi, rax
0x1800076c5  test    rax, rax
0x1800076c8  jnz     short loc_1800076E1
0x1800076ca  call    cs:__imp_GetLastError
0x1800076d0  mov     ebx, eax
0x1800076d2  test    eax, eax
0x1800076d4  jle     short loc_180007710
0x1800076d6  movzx   ebx, ax
0x1800076d9  or      ebx, 80070000h
0x1800076df  jmp     short loc_180007710
0x1800076e1  mov     rax, [rsi]
0x1800076e4  mov     rdx, rdi
0x1800076e7  mov     rcx, rsi
0x1800076ea  mov     rax, [rax+18h]
0x1800076ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076f3  mov     ebx, eax
0x1800076f5  test    eax, eax
0x1800076f7  jns     short loc_180007710
0x1800076f9  mov     rcx, rdi
0x1800076fc  call    IsolationAwareDestroyPropertySheetPage
0x180007701  jmp     short loc_180007710
0x180007703  mov     rcx, rdi; lNotifyHandle
0x180007706  mov     ebx, 8007000Eh
0x18000770b  call    MMCFreeNotifyHandle
0x180007710  mov     eax, ebx
0x180007712  add     rsp, 98h
0x180007719  pop     rdi
0x18000771a  pop     rsi
0x18000771b  pop     rbp
0x18000771c  pop     rbx
0x18000771d  retn
```
