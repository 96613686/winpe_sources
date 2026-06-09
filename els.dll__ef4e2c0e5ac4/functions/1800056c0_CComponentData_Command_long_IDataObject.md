# CComponentData::Command(long,IDataObject *)

- ea: `0x1800056c0`
- end: `0x18000599c`
- name: `?Command@CComponentData@@UEAAJJPEAUIDataObject@@@Z`
- size: `732`
- prototype: `int(CComponentData *__hidden this, int, struct IDataObject *)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001910`
- `0x1800056c0`
- `0x18000688c`
- `0x180007a08`
- `0x180007bd8`
- `0x1800087bc`
- `0x180008be0`
- `0x1800126d8`
- `0x180016978`
- `0x180016a98`
- `0x18001cf48`
- `0x18001d42c`
- `0x18001e214`
- `0x18001eef4`
- `0x18001ef94`
- `0x18001f638`
- `0x180020338`
- `0x1800214b8`
- `0x1800222d0`
- `0x180024010`

## import_xrefs

- `USER32!SetForegroundWindow` at `0x180005966`
- `USER32!SetForegroundWindow` at `0x180005966`

## pseudocode

```c
struct CDataObject *__fastcall CComponentData::Command(CComponentData *this, int a2, struct IDataObject *a3)
{
  struct CDataObject *result; // rax
  unsigned int v7; // esi
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rdx
  CLogInfo *v13; // rcx
  int v14; // ebx
  const unsigned __int16 *DisplayName; // rax
  CSynchWindow *v16; // rcx
  struct CLogInfo *v17; // rbx
  __int64 v18; // rcx
  struct CLogInfo *v19; // rbx
  __int64 v20; // rcx
  int v21; // eax
  _QWORD *v22; // r9
  int v23; // ebx
  int v24; // ebx
  int v25; // ebx
  __int64 v26; // rdx
  CComponentData *v27; // rcx
  struct CLogSet *i; // rdx
  CSnapin *v29; // rcx
  struct CLogInfo *v30; // rdx
  HWND v31; // rcx
  unsigned int v32; // [rsp+20h] [rbp-E0h]
  HWND v33; // [rsp+30h] [rbp-D0h] BYREF
  HWND v34; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v35[4]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v36[264]; // [rsp+60h] [rbp-A0h] BYREF

  result = ExtractOwnDataObject(a3);
  if ( result )
  {
    v7 = 0;
    if ( a2 > 107 )
    {
      v23 = a2 - 108;
      if ( !v23 )
      {
        v29 = (CSnapin *)*((_QWORD *)this + 6);
        if ( v29 )
        {
          v30 = (struct CLogInfo *)*((_QWORD *)result + 2);
          v34 = 0;
          if ( (int)CSnapin::_GetFindInfo(v29, v30, (struct CFindInfo **)&v34) >= 0 )
          {
            v31 = (HWND)*((_QWORD *)v34 + 269);
            if ( v31 )
              SetForegroundWindow(v31);
            else
              CFindDlg::DoModelessDlg((LPSTREAM *)v34 + 268, *((IUnknown **)v34 + 266));
          }
        }
        return (struct CDataObject *)v7;
      }
      v24 = v23 - 9;
      if ( !v24 )
      {
        CChooserDlg::OnChooseTargetMachine((CComponentData *)((char *)this - 24), *((_QWORD *)this + 139), a3);
        CComponentData::_UpdateRootDisplayName((CComponentData *)((char *)this - 24));
        return (struct CDataObject *)v7;
      }
      v25 = v24 - 1;
      if ( !v25 )
      {
        v26 = *((_QWORD *)result + 2);
        v27 = (CComponentData *)((char *)this - 24);
        if ( v26 )
        {
          i = *(struct CLogSet **)(v26 + 4864);
LABEL_28:
          CComponentData::_OnOpenSavedLog(v27, i);
        }
        else
        {
          for ( i = (struct CLogSet *)*((_QWORD *)v27 + 10); i; i = (struct CLogSet *)*((_QWORD *)i + 1) )
          {
            if ( *((_QWORD *)this + 139) == *((_QWORD *)i + 5) )
              goto LABEL_28;
          }
        }
        return (struct CDataObject *)v7;
      }
      if ( v25 == 1 )
      {
        CComponentData::_OnNewView((CComponentData *)((char *)this - 24), *((struct CLogInfo **)result + 2));
        return (struct CDataObject *)v7;
      }
    }
    else
    {
      if ( a2 == 107 )
      {
        v12 = 9;
        goto LABEL_10;
      }
      v8 = a2 - 102;
      if ( !v8 )
      {
        v19 = (struct CLogInfo *)*((_QWORD *)result + 2);
        v20 = *((_QWORD *)this + 141);
        v34 = 0;
        LODWORD(v33) = 0;
        (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v20 + 96LL))(v20, &v34);
        if ( (unsigned int)PromptForLogClear(v34, v19, (enum SAVE_TYPE *)&v33, v36, v32) != 2 )
        {
          v21 = (*(__int64 (__fastcall **)(char *, struct CLogInfo *, _QWORD, unsigned __int16 *))(*((_QWORD *)this + 1)
                                                                                                 + 24LL))(
                  (char *)this + 8,
                  v19,
                  (unsigned int)v33,
                  v36);
          if ( v21 < 0 )
          {
            ComposeErrorMessgeFromHRESULT(v35, (unsigned int)v21);
            v22 = v35;
            if ( v35[3] >= 8u )
              v22 = (_QWORD *)v35[0];
            ConsoleMsgBox(*((struct IConsole **)this + 141), 0x130u, 0x10u, v22);
            std::wstring::_Tidy(v35, 1, 0);
          }
        }
        return (struct CDataObject *)v7;
      }
      v9 = v8 - 1;
      if ( !v9 )
      {
        v17 = (struct CLogInfo *)*((_QWORD *)result + 2);
        v18 = *((_QWORD *)this + 141);
        v33 = 0;
        (*(void (__fastcall **)(__int64, HWND *))(*(_QWORD *)v18 + 96LL))(v18, &v33);
        CComponentData::_SaveAs((CComponentData *)((char *)this - 24), v33, v17);
        return (struct CDataObject *)v7;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        CLogInfo::Filter(*((CLogInfo **)result + 2), 0);
        CSynchWindow::Post(v16, 0x7E8u, 3u, (__int64)v16);
        return (struct CDataObject *)v7;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        v13 = (CLogInfo *)*((_QWORD *)result + 2);
        v14 = *((_DWORD *)v13 + 1214);
        DisplayName = CLogInfo::GetDisplayName(v13);
        InvokePropertySheet(
          *((struct IPropertySheetProvider **)this + 143),
          DisplayName,
          v14,
          a3,
          (struct IExtendPropertySheet *)(((unsigned __int64)this - 8) & -(__int64)(this != (CComponentData *)24)),
          1u);
        return (struct CDataObject *)v7;
      }
      if ( v11 == 1 )
      {
        v12 = 8;
LABEL_10:
        CSnapin::SetDisplayOrder(*((_QWORD *)this + 6), v12);
        return (struct CDataObject *)v7;
      }
    }
    return (struct CDataObject *)(unsigned int)-2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x1800056c0  push    rbp
0x1800056c2  push    rbx
0x1800056c3  push    rsi
0x1800056c4  push    rdi
0x1800056c5  push    r14
0x1800056c7  lea     rbp, [rsp-180h]
0x1800056cf  sub     rsp, 280h
0x1800056d6  mov     rax, cs:__security_cookie
0x1800056dd  xor     rax, rsp
0x1800056e0  mov     [rbp+1A0h+var_30], rax
0x1800056e7  mov     rdi, rcx
0x1800056ea  mov     r14, r8
0x1800056ed  mov     rcx, r8; struct IDataObject *
0x1800056f0  mov     ebx, edx
0x1800056f2  call    ?ExtractOwnDataObject@@YAPEAVCDataObject@@PEAUIDataObject@@@Z; ExtractOwnDataObject(IDataObject *)
0x1800056f7  test    rax, rax
0x1800056fa  jz      loc_18000597F
0x180005700  xor     esi, esi
0x180005702  cmp     ebx, 6Bh ; 'k'
0x180005705  jg      loc_1800058A5
0x18000570b  jz      loc_18000589B
0x180005711  sub     ebx, 66h ; 'f'
0x180005714  jz      loc_1800057E7
0x18000571a  sub     ebx, 1
0x18000571d  jz      loc_1800057B0
0x180005723  sub     ebx, 1
0x180005726  jz      short loc_18000578D
0x180005728  sub     ebx, 1
0x18000572b  jz      short loc_180005747
0x18000572d  cmp     ebx, 1
0x180005730  jnz     loc_1800058BD
0x180005736  lea     edx, [rsi+8]
0x180005739  mov     rcx, [rdi+30h]
0x18000573d  call    ?SetDisplayOrder@CSnapin@@QEAAJW4SORT_ORDER@@@Z; CSnapin::SetDisplayOrder(SORT_ORDER)
0x180005742  jmp     loc_18000597D
0x180005747  mov     rcx, [rax+10h]; this
0x18000574b  mov     ebx, [rcx+12F8h]
0x180005751  call    ?GetDisplayName@CLogInfo@@QEAAPEAGXZ; CLogInfo::GetDisplayName(void)
0x180005756  mov     rcx, [rdi+478h]; struct IPropertySheetProvider *
0x18000575d  lea     r10, [rdi-8]
0x180005761  lea     rdx, [rdi-18h]
0x180005765  mov     [rsp+2A0h+var_278], 1; unsigned __int16
0x18000576c  neg     rdx
0x18000576f  mov     r9, r14; struct IDataObject *
0x180005772  mov     r8d, ebx; int
0x180005775  mov     rdx, rax; unsigned __int16 *
0x180005778  sbb     r11, r11
0x18000577b  and     r11, r10
0x18000577e  mov     [rsp+2A0h+var_280], r11; struct IExtendPropertySheet *
0x180005783  call    ?InvokePropertySheet@@YAJPEAUIPropertySheetProvider@@PEBGJPEAUIDataObject@@PEAUIExtendPropertySheet@@G@Z; InvokePropertySheet(IPropertySheetProvider *,ushort const *,long,IDataObject *,IExtendPropertySheet *,ushort)
0x180005788  jmp     loc_18000597D
0x18000578d  mov     rcx, [rax+10h]; this
0x180005791  xor     edx, edx; int
0x180005793  call    ?Filter@CLogInfo@@QEAAXH@Z; CLogInfo::Filter(int)
0x180005798  mov     r9, rcx; __int64
0x18000579b  mov     edx, 7E8h; unsigned int
0x1800057a0  mov     r8d, 3; unsigned __int64
0x1800057a6  call    ?Post@CSynchWindow@@QEAAJI_K_J@Z; CSynchWindow::Post(uint,unsigned __int64,__int64)
0x1800057ab  jmp     loc_18000597D
0x1800057b0  mov     rbx, [rax+10h]
0x1800057b4  lea     rdx, [rsp+2A0h+var_270]
0x1800057b9  mov     rcx, [rdi+468h]
0x1800057c0  mov     [rsp+2A0h+var_270], rsi
0x1800057c5  mov     rax, [rcx]
0x1800057c8  mov     rax, [rax+60h]
0x1800057cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057d1  mov     rdx, [rsp+2A0h+var_270]; HWND
0x1800057d6  lea     rcx, [rdi-18h]; this
0x1800057da  mov     r8, rbx; struct CLogInfo *
0x1800057dd  call    ?_SaveAs@CComponentData@@AEAAJPEAUHWND__@@PEAVCLogInfo@@@Z; CComponentData::_SaveAs(HWND__ *,CLogInfo *)
0x1800057e2  jmp     loc_18000597D
0x1800057e7  mov     rbx, [rax+10h]
0x1800057eb  lea     rdx, [rsp+2A0h+var_268]
0x1800057f0  mov     rcx, [rdi+468h]
0x1800057f7  mov     [rsp+2A0h+var_268], rsi
0x1800057fc  mov     dword ptr [rsp+2A0h+var_270], esi
0x180005800  mov     rax, [rcx]
0x180005803  mov     rax, [rax+60h]
0x180005807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000580c  mov     rcx, [rsp+2A0h+var_268]; HWND
0x180005811  lea     r9, [rsp+2A0h+var_240]; unsigned __int16 *
0x180005816  lea     r8, [rsp+2A0h+var_270]; enum SAVE_TYPE *
0x18000581b  mov     rdx, rbx; struct CLogInfo *
0x18000581e  call    ?PromptForLogClear@@YAJPEAUHWND__@@PEAVCLogInfo@@PEAW4SAVE_TYPE@@PEAGK@Z; PromptForLogClear(HWND__ *,CLogInfo *,SAVE_TYPE *,ushort *,ulong)
0x180005823  cmp     eax, 2
0x180005826  jz      loc_18000597D
0x18000582c  mov     r8d, dword ptr [rsp+2A0h+var_270]
0x180005831  lea     rcx, [rdi+8]
0x180005835  mov     rax, [rcx]
0x180005838  lea     r9, [rsp+2A0h+var_240]
0x18000583d  mov     rdx, rbx
0x180005840  mov     rax, [rax+18h]
0x180005844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005849  test    eax, eax
0x18000584b  jns     loc_18000597D
0x180005851  mov     edx, eax
0x180005853  lea     rcx, [rsp+2A0h+var_260]
0x180005858  call    ?ComposeErrorMessgeFromHRESULT@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@J@Z; ComposeErrorMessgeFromHRESULT(long)
0x18000585d  cmp     [rsp+2A0h+var_248], 8
0x180005863  lea     r9, [rsp+2A0h+var_260]
0x180005868  mov     rcx, [rdi+468h]; struct IConsole *
0x18000586f  mov     edx, 130h; unsigned int
0x180005874  cmovnb  r9, [rsp+2A0h+var_260]
0x18000587a  mov     r8d, 10h; unsigned int
0x180005880  call    ?ConsoleMsgBox@@YAHPEAUIConsole@@KKZZ; ConsoleMsgBox(IConsole *,ulong,ulong,...)
0x180005885  xor     r8d, r8d
0x180005888  lea     rcx, [rsp+2A0h+var_260]
0x18000588d  lea     edx, [r8+1]
0x180005891  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180005896  jmp     loc_18000597D
0x18000589b  mov     edx, 9
0x1800058a0  jmp     loc_180005739
0x1800058a5  sub     ebx, 6Ch ; 'l'
0x1800058a8  jz      loc_180005931
0x1800058ae  sub     ebx, 9
0x1800058b1  jz      short loc_180005913
0x1800058b3  sub     ebx, 1
0x1800058b6  jz      short loc_1800058D9
0x1800058b8  cmp     ebx, 1
0x1800058bb  jz      short loc_1800058C7
0x1800058bd  mov     esi, 80070057h
0x1800058c2  jmp     loc_18000597D
0x1800058c7  mov     rdx, [rax+10h]; struct CLogInfo *
0x1800058cb  lea     rcx, [rdi-18h]; this
0x1800058cf  call    ?_OnNewView@CComponentData@@AEAAJPEAVCLogInfo@@@Z; CComponentData::_OnNewView(CLogInfo *)
0x1800058d4  jmp     loc_18000597D
0x1800058d9  mov     rdx, [rax+10h]
0x1800058dd  lea     rcx, [rdi-18h]; this
0x1800058e1  test    rdx, rdx
0x1800058e4  jz      short loc_1800058F7
0x1800058e6  mov     rdx, [rdx+1300h]; struct CLogSet *
0x1800058ed  call    ?_OnOpenSavedLog@CComponentData@@AEAAJPEAVCLogSet@@@Z; CComponentData::_OnOpenSavedLog(CLogSet *)
0x1800058f2  jmp     loc_18000597D
0x1800058f7  mov     rdx, [rcx+50h]
0x1800058fb  test    rdx, rdx
0x1800058fe  jz      short loc_18000597D
0x180005900  mov     rax, [rdx+28h]
0x180005904  cmp     [rdi+458h], rax
0x18000590b  jz      short loc_1800058ED
0x18000590d  mov     rdx, [rdx+8]
0x180005911  jmp     short loc_1800058FB
0x180005913  mov     rdx, [rdi+458h]; __int64
0x18000591a  lea     rcx, [rdi-18h]; struct CComponentData *
0x18000591e  mov     r8, r14; struct IDataObject *
0x180005921  call    ?OnChooseTargetMachine@CChooserDlg@@SAXPEAVCComponentData@@_JPEAUIDataObject@@@Z; CChooserDlg::OnChooseTargetMachine(CComponentData *,__int64,IDataObject *)
0x180005926  lea     rcx, [rdi-18h]; this
0x18000592a  call    ?_UpdateRootDisplayName@CComponentData@@AEAAXXZ; CComponentData::_UpdateRootDisplayName(void)
0x18000592f  jmp     short loc_18000597D
0x180005931  mov     rcx, [rdi+30h]; this
0x180005935  test    rcx, rcx
0x180005938  jz      short loc_18000597D
0x18000593a  mov     rdx, [rax+10h]; struct CLogInfo *
0x18000593e  lea     r8, [rsp+2A0h+var_268]; struct CFindInfo **
0x180005943  mov     [rsp+2A0h+var_268], rsi
0x180005948  call    ?_GetFindInfo@CSnapin@@AEAAJPEAVCLogInfo@@PEAPEAVCFindInfo@@@Z; CSnapin::_GetFindInfo(CLogInfo *,CFindInfo * *)
0x18000594d  test    eax, eax
0x18000594f  js      short loc_18000597D
0x180005951  mov     rdx, [rsp+2A0h+var_268]
0x180005956  lea     rax, [rdx+860h]
0x18000595d  mov     rcx, [rax+8]; hWnd
0x180005961  test    rcx, rcx
0x180005964  jz      short loc_18000596E
0x180005966  call    cs:__imp_SetForegroundWindow
0x18000596c  jmp     short loc_18000597D
0x18000596e  mov     rdx, [rdx+850h]; struct CSnapin *
0x180005975  mov     rcx, rax; this
0x180005978  call    ?DoModelessDlg@CFindDlg@@QEAAJPEAVCSnapin@@@Z; CFindDlg::DoModelessDlg(CSnapin *)
0x18000597d  mov     eax, esi
0x18000597f  mov     rcx, [rbp+1A0h+var_30]
0x180005986  xor     rcx, rsp; StackCookie
0x180005989  call    __security_check_cookie
0x18000598e  add     rsp, 280h
0x180005995  pop     r14
0x180005997  pop     rdi
0x180005998  pop     rsi
0x180005999  pop     rbx
0x18000599a  pop     rbp
0x18000599b  retn
```
