# DevicesPage::UpdateProfileListViewOnDefaultsChanged(int,COLORPROFILETYPE *,Profile *)

- ea: `0x18000e7ac`
- end: `0x18000e9d1`
- name: `?UpdateProfileListViewOnDefaultsChanged@DevicesPage@@AEAAJHPEAW4COLORPROFILETYPE@@PEAUProfile@@@Z`
- size: `549`
- prototype: `__int64 __fastcall(DevicesPage *__hidden this, int, enum COLORPROFILETYPE *, struct Profile *)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d9a0`
- `0x18000dcdc`
- `0x18000dfe4`
- `0x18000e558`

## callees

- `0x180001334`
- `0x18000134c`
- `0x18000ccc0`
- `0x18000cd08`
- `0x18000e7ac`
- `0x180011f4c`
- `0x1800131ec`
- `0x18001351c`
- `0x180013950`
- `0x180013a50`
- `0x180013b34`
- `0x1800145f4`
- `0x18001772c`
- `0x1800178d4`
- `0x1800179f0`

## import_xrefs

- `USER32!SendMessageW` at `0x18000e8e0`
- `USER32!SendMessageW` at `0x18000e8e0`

## pseudocode

```c
__int64 __fastcall DevicesPage::UpdateProfileListViewOnDefaultsChanged(
        DevicesPage *this,
        int a2,
        enum COLORPROFILETYPE *a3,
        struct Profile *a4)
{
  enum WCS_PROFILE_MANAGEMENT_SCOPE SettingsScope; // eax
  HWND *v7; // rcx
  enum WCS_PROFILE_MANAGEMENT_SCOPE v8; // esi
  int SelectedLParam; // eax
  ColorDataController *v10; // rcx
  int ItemLParam; // ebx
  struct Device *v12; // rdi
  int v13; // eax
  Helper::DefaultChecker *v14; // rax
  const struct ColorDataController *v15; // rdx
  __int64 v16; // rax
  Helper::DefaultChecker *v17; // rdi
  __int64 v18; // rsi
  unsigned int v19; // eax
  unsigned __int64 v20; // r13
  HWND *v21; // rcx
  struct Device *v22; // r14
  int v23; // eax
  int IsDefault; // eax
  int v25; // r8d
  const unsigned __int16 *v26; // r9
  int v28; // [rsp+30h] [rbp-20h] BYREF
  unsigned __int16 *v29; // [rsp+38h] [rbp-18h]
  int v30; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v31; // [rsp+48h] [rbp-8h]
  struct Device *v32; // [rsp+90h] [rbp+40h] BYREF
  int v33; // [rsp+98h] [rbp+48h]
  struct Profile *v34; // [rsp+A8h] [rbp+58h] BYREF

  v34 = a4;
  v33 = a2;
  v31 = &NCoreLibrary::TString::gszNullState;
  v30 = 1735554163;
  v28 = 1735554163;
  v29 = &NCoreLibrary::TString::gszNullState;
  SettingsScope = (unsigned int)DevicesPage::GetReadSettingsScope(this);
  v7 = (HWND *)*((_QWORD *)this + 11);
  v8 = SettingsScope;
  v32 = 0;
  SelectedLParam = Combo<Device>::GetSelectedLParam(v7, (LRESULT *)&v32);
  ItemLParam = SelectedLParam;
  if ( SelectedLParam >= 0 )
  {
    if ( SelectedLParam == 1 )
    {
      ItemLParam = 0;
      goto LABEL_38;
    }
    if ( (v12 = v32, LODWORD(v34) = 1, *(_DWORD *)v32 == 1886549106)
      && (ColorDataController::GetPrinterConfigMode(v10, v8, v32, (int *)&v34) >= 0
        ? (v13 = (int)v34)
        : (v13 = 0, LODWORD(v34) = 0),
          !v13)
      || (ItemLParam = NCoreLibrary::TString::LoadStringFromRC(
                         (NCoreLibrary::TString *)&v30,
                         *((HINSTANCE *)this + 2),
                         0x7DEu),
          ItemLParam >= 0) )
    {
      v14 = (Helper::DefaultChecker *)operator new(0x18u);
      if ( a3 )
      {
        if ( !v14 )
        {
          v17 = 0;
          goto LABEL_16;
        }
        v16 = Helper::DefaultChecker::DefaultChecker(v14, v15, v8, v12, *a3);
      }
      else
      {
        if ( !v14 )
          goto LABEL_36;
        v16 = Helper::DefaultChecker::DefaultChecker(v14, v15, v8, v12);
      }
      v17 = (Helper::DefaultChecker *)v16;
LABEL_16:
      if ( v17 )
      {
        ItemLParam = *((_DWORD *)v17 + 4);
        if ( ItemLParam >= 0 )
        {
          v18 = 0;
          v19 = SendMessageW(**((HWND **)this + 10), 0x1004u, 0, 0);
          v20 = v19;
          if ( v19 )
          {
            while ( 1 )
            {
              v21 = (HWND *)*((_QWORD *)this + 10);
              v32 = 0;
              ItemLParam = ListView::GetItemLParam(v21, v18, &v32);
              if ( ItemLParam < 0 )
                goto LABEL_35;
              v22 = v32;
              if ( !a3 )
                break;
              v23 = *(_DWORD *)v32;
              if ( *a3 == *(_DWORD *)v32 )
                break;
              if ( *a3 )
              {
                if ( *a3 == CPT_DMP && !v23 )
                  break;
              }
              else if ( v23 == 1 )
              {
                break;
              }
LABEL_34:
              if ( ++v18 >= v20 )
                goto LABEL_35;
            }
            IsDefault = Helper::DefaultChecker::IsDefault(v17, v32);
            if ( !v33 || IsDefault )
            {
              if ( (_DWORD)v34 && IsDefault )
              {
                NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v28, v31, (char *)v22 + 12);
                v26 = v29;
              }
              else
              {
                v26 = (const unsigned __int16 *)((char *)v22 + 12);
              }
              ListView::SetItemText(*((ListView **)this + 10), v18, v25, v26);
            }
            goto LABEL_34;
          }
        }
LABEL_35:
        Helper::DefaultChecker::~DefaultChecker(v17);
        operator delete(v17);
        goto LABEL_38;
      }
LABEL_36:
      ItemLParam = -2147024882;
    }
  }
LABEL_38:
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v28);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v30);
  return (unsigned int)ItemLParam;
}

```

## disassembly

```asm
0x18000e7ac  mov     [rsp-38h+arg_10], rbx
0x18000e7b1  mov     [rsp-38h+arg_18], r9
0x18000e7b6  mov     [rsp-38h+arg_8], edx
0x18000e7ba  push    rbp
0x18000e7bb  push    rsi
0x18000e7bc  push    rdi
0x18000e7bd  push    r12
0x18000e7bf  push    r13
0x18000e7c1  push    r14
0x18000e7c3  push    r15
0x18000e7c5  mov     rbp, rsp
0x18000e7c8  sub     rsp, 50h
0x18000e7cc  mov     r15, rcx
0x18000e7cf  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18000e7d6  mov     ecx, 67727473h
0x18000e7db  mov     [rbp+var_8], rax
0x18000e7df  mov     [rbp+var_10], ecx
0x18000e7e2  mov     r12, r8
0x18000e7e5  mov     [rbp+var_20], ecx
0x18000e7e8  mov     rcx, r15; this
0x18000e7eb  mov     [rbp+var_18], rax
0x18000e7ef  call    ?GetReadSettingsScope@DevicesPage@@AEAA?AW4WCS_PROFILE_MANAGEMENT_SCOPE@@XZ; DevicesPage::GetReadSettingsScope(void)
0x18000e7f4  mov     rcx, [r15+58h]
0x18000e7f8  lea     rdx, [rbp+arg_0]
0x18000e7fc  mov     esi, eax
0x18000e7fe  mov     [rbp+arg_0], 0
0x18000e806  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000e80b  mov     ebx, eax
0x18000e80d  test    eax, eax
0x18000e80f  js      loc_18000E9A5
0x18000e815  cmp     eax, 1
0x18000e818  jz      loc_18000E9A3
0x18000e81e  mov     rdi, [rbp+arg_0]
0x18000e822  mov     dword ptr [rbp+arg_18], 1
0x18000e829  cmp     dword ptr [rdi], 70727472h
0x18000e82f  jnz     short loc_18000E851
0x18000e831  lea     r9, [rbp+arg_18]; int *
0x18000e835  mov     r8, rdi; struct Device *
0x18000e838  mov     edx, esi; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000e83a  call    ?GetPrinterConfigMode@ColorDataController@@QEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@PEAH@Z; ColorDataController::GetPrinterConfigMode(WCS_PROFILE_MANAGEMENT_SCOPE,Device const &,int *)
0x18000e83f  test    eax, eax
0x18000e841  jns     short loc_18000E84A
0x18000e843  xor     eax, eax
0x18000e845  mov     dword ptr [rbp+arg_18], eax
0x18000e848  jmp     short loc_18000E84D
0x18000e84a  mov     eax, dword ptr [rbp+arg_18]
0x18000e84d  test    eax, eax
0x18000e84f  jz      short loc_18000E86E
0x18000e851  mov     rdx, [r15+10h]; HINSTANCE
0x18000e855  lea     rcx, [rbp+var_10]; this
0x18000e859  mov     r8d, 7DEh; unsigned int
0x18000e85f  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18000e864  mov     ebx, eax
0x18000e866  test    eax, eax
0x18000e868  js      loc_18000E9A5
0x18000e86e  mov     ecx, 18h; Size
0x18000e873  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e878  test    r12, r12
0x18000e87b  jz      short loc_18000E89E
0x18000e87d  test    rax, rax
0x18000e880  jz      short loc_18000E89A
0x18000e882  mov     ecx, [r12]
0x18000e886  mov     r9, rdi; struct Device *
0x18000e889  mov     [rsp+50h+var_30], ecx; enum COLORPROFILETYPE
0x18000e88d  mov     r8d, esi; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000e890  mov     rcx, rax; this
0x18000e893  call    ??0DefaultChecker@Helper@@QEAA@AEBVColorDataController@@W4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@W4COLORPROFILETYPE@@@Z; Helper::DefaultChecker::DefaultChecker(ColorDataController const &,WCS_PROFILE_MANAGEMENT_SCOPE,Device const &,COLORPROFILETYPE)
0x18000e898  jmp     short loc_18000E8B5
0x18000e89a  xor     edi, edi
0x18000e89c  jmp     short loc_18000E8B8
0x18000e89e  test    rax, rax
0x18000e8a1  jz      loc_18000E99C
0x18000e8a7  mov     r9, rdi; struct Device *
0x18000e8aa  mov     r8d, esi; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000e8ad  mov     rcx, rax; this
0x18000e8b0  call    ??0DefaultChecker@Helper@@QEAA@AEBVColorDataController@@W4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@@Z; Helper::DefaultChecker::DefaultChecker(ColorDataController const &,WCS_PROFILE_MANAGEMENT_SCOPE,Device const &)
0x18000e8b5  mov     rdi, rax
0x18000e8b8  test    rdi, rdi
0x18000e8bb  jz      loc_18000E99C
0x18000e8c1  mov     ebx, [rdi+10h]
0x18000e8c4  test    ebx, ebx
0x18000e8c6  js      loc_18000E98A
0x18000e8cc  mov     rcx, [r15+50h]
0x18000e8d0  xor     r9d, r9d; lParam
0x18000e8d3  xor     r8d, r8d; wParam
0x18000e8d6  mov     edx, 1004h; Msg
0x18000e8db  xor     esi, esi
0x18000e8dd  mov     rcx, [rcx]; hWnd
0x18000e8e0  call    cs:__imp_SendMessageW
0x18000e8e6  mov     r13d, eax
0x18000e8e9  test    eax, eax
0x18000e8eb  jz      loc_18000E98A
0x18000e8f1  mov     rcx, [r15+50h]; this
0x18000e8f5  lea     r8, [rbp+arg_0]; struct Profile **
0x18000e8f9  mov     edx, esi; int
0x18000e8fb  mov     [rbp+arg_0], 0
0x18000e903  call    ?GetItemLParam@ListView@@QEBAJHPEAPEAUProfile@@@Z; ListView::GetItemLParam(int,Profile * *)
0x18000e908  mov     ebx, eax
0x18000e90a  test    eax, eax
0x18000e90c  js      short loc_18000E98A
0x18000e90e  mov     r14, [rbp+arg_0]
0x18000e912  test    r12, r12
0x18000e915  jz      short loc_18000E939
0x18000e917  mov     eax, [r14]
0x18000e91a  cmp     [r12], eax
0x18000e91e  jz      short loc_18000E939
0x18000e920  cmp     dword ptr [r12], 0
0x18000e925  jnz     short loc_18000E92E
0x18000e927  cmp     eax, 1
0x18000e92a  jz      short loc_18000E939
0x18000e92c  jmp     short loc_18000E97E
0x18000e92e  cmp     dword ptr [r12], 1
0x18000e933  jnz     short loc_18000E97E
0x18000e935  test    eax, eax
0x18000e937  jnz     short loc_18000E97E
0x18000e939  mov     rdx, r14; struct Profile *
0x18000e93c  mov     rcx, rdi; this
0x18000e93f  call    ?IsDefault@DefaultChecker@Helper@@QEBAHAEBUProfile@@@Z; Helper::DefaultChecker::IsDefault(Profile const &)
0x18000e944  cmp     [rbp+arg_8], 0
0x18000e948  jz      short loc_18000E94E
0x18000e94a  test    eax, eax
0x18000e94c  jz      short loc_18000E97E
0x18000e94e  cmp     dword ptr [rbp+arg_18], 0
0x18000e952  jz      short loc_18000E96F
0x18000e954  test    eax, eax
0x18000e956  jz      short loc_18000E96F
0x18000e958  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x18000e95c  lea     r8, [r14+0Ch]
0x18000e960  lea     rcx, [rbp+var_20]; this
0x18000e964  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x18000e969  mov     r9, [rbp+var_18]
0x18000e96d  jmp     short loc_18000E973
0x18000e96f  lea     r9, [r14+0Ch]; unsigned __int16 *
0x18000e973  mov     rcx, [r15+50h]; this
0x18000e977  mov     edx, esi; int
0x18000e979  call    ?SetItemText@ListView@@QEAAXHHPEBG@Z; ListView::SetItemText(int,int,ushort const *)
0x18000e97e  inc     rsi
0x18000e981  cmp     rsi, r13
0x18000e984  jb      loc_18000E8F1
0x18000e98a  mov     rcx, rdi; this
0x18000e98d  call    ??1DefaultChecker@Helper@@QEAA@XZ; Helper::DefaultChecker::~DefaultChecker(void)
0x18000e992  mov     rcx, rdi; Block
0x18000e995  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e99a  jmp     short loc_18000E9A5
0x18000e99c  mov     ebx, 8007000Eh
0x18000e9a1  jmp     short loc_18000E9A5
0x18000e9a3  xor     ebx, ebx
0x18000e9a5  lea     rcx, [rbp+var_20]; this
0x18000e9a9  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000e9ae  lea     rcx, [rbp+var_10]; this
0x18000e9b2  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000e9b7  mov     eax, ebx
0x18000e9b9  mov     rbx, [rsp+50h+arg_10]
0x18000e9c1  add     rsp, 50h
0x18000e9c5  pop     r15
0x18000e9c7  pop     r14
0x18000e9c9  pop     r13
0x18000e9cb  pop     r12
0x18000e9cd  pop     rdi
0x18000e9ce  pop     rsi
0x18000e9cf  pop     rbp
0x18000e9d0  retn
```
