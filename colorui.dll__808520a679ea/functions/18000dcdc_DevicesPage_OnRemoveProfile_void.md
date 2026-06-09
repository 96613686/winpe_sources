# DevicesPage::OnRemoveProfile(void)

- ea: `0x18000dcdc`
- end: `0x18000de78`
- name: `?OnRemoveProfile@DevicesPage@@AEAAJXZ`
- size: `412`
- prototype: `__int64 __fastcall(DevicesPage *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cd90`

## callees

- `0x18000cd08`
- `0x18000dcdc`
- `0x18000e7ac`
- `0x18001330c`
- `0x180013458`
- `0x180013a50`
- `0x180013b34`
- `0x1800145f4`
- `0x180015ecc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall DevicesPage::OnRemoveProfile(DevicesPage *this)
{
  HWND *v2; // rcx
  __int64 result; // rax
  enum COLORPROFILETYPE v4; // esi
  const struct ColorDataController *v5; // rdx
  enum COLORPROFILETYPE *v6; // r14
  struct Device *v7; // r13
  int v8; // ebx
  HWND *v9; // rcx
  int SelectedLParam; // eax
  int IsDefault; // eax
  int v12; // r15d
  HINSTANCE v13; // rdx
  HINSTANCE v14; // rcx
  int updated; // eax
  ListView *v16; // rcx
  struct Profile *v17; // r9
  int *v18; // [rsp+28h] [rbp-28h]
  _BYTE v19[16]; // [rsp+30h] [rbp-20h] BYREF
  int v20; // [rsp+40h] [rbp-10h]
  enum COLORPROFILETYPE *v21; // [rsp+80h] [rbp+30h] BYREF
  struct Device *v22; // [rsp+88h] [rbp+38h] BYREF

  v22 = 0;
  v2 = (HWND *)*((_QWORD *)this + 11);
  v21 = 0;
  result = Combo<Device>::GetSelectedLParam(v2, (LRESULT *)&v22);
  if ( (int)result >= 0 )
  {
    v4 = CPT_DMP;
    if ( (_DWORD)result == 1 )
      return 0;
    result = ListView::GetSelectedLParam(*((HWND **)this + 10), (struct Profile **)&v21);
    if ( (int)result < 0 )
      return result;
    if ( (_DWORD)result == 1 )
      return 0;
    v6 = v21;
    v7 = v22;
    Helper::DefaultChecker::DefaultChecker(
      (Helper::DefaultChecker *)v19,
      v5,
      *((enum WCS_PROFILE_MANAGEMENT_SCOPE *)this + 18),
      v22,
      *v21);
    v8 = v20;
    if ( v20 >= 0 )
    {
      if ( *(_DWORD *)v7 == 1886549106 )
      {
        v9 = (HWND *)*((_QWORD *)this + 12);
        v21 = 0;
        SelectedLParam = Combo<Device>::GetSelectedLParam(v9, (LRESULT *)&v21);
        v8 = SelectedLParam;
        if ( SelectedLParam < 0 )
          goto LABEL_20;
        if ( SelectedLParam == 1 )
        {
          v8 = -2147467259;
          goto LABEL_20;
        }
        v4 = *v21;
      }
      IsDefault = Helper::DefaultChecker::IsDefault((Helper::DefaultChecker *)v19, (const struct Profile *)v6);
      v12 = IsDefault;
      if ( v4 == CPT_ICC
        || !IsDefault
        || (v13 = (HINSTANCE)*((_QWORD *)this + 1),
            v14 = (HINSTANCE)*((_QWORD *)this + 2),
            LODWORD(v21) = 0,
            updated = Helper::ShowWarningDialog(v14, v13, (HWND)0x1397, 0, (int)&v21, v18),
            updated >= 0)
        && !(_DWORD)v21 )
      {
        updated = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, enum COLORPROFILETYPE *, _DWORD))(**(_QWORD **)(*((_QWORD *)this + 7) + 16LL) + 56LL))(
                    *(_QWORD *)(*((_QWORD *)this + 7) + 16LL),
                    *((unsigned int *)this + 18),
                    (__int64)v7 + 4,
                    v6 + 133,
                    *((_DWORD *)v6 + 264));
        if ( updated >= 0 )
        {
          v16 = (ListView *)*((_QWORD *)this + 10);
          SLODWORD(v21) = *v6;
          v8 = ListView::RemoveSelectedItem(v16);
          if ( v8 < 0 || !v12 )
            goto LABEL_20;
          updated = DevicesPage::UpdateProfileListViewOnDefaultsChanged(this, 0, (enum COLORPROFILETYPE *)&v21, v17);
        }
      }
      v8 = updated;
    }
LABEL_20:
    Helper::DefaultChecker::~DefaultChecker((Helper::DefaultChecker *)v19);
    return (unsigned int)v8;
  }
  return result;
}

```

## disassembly

```asm
0x18000dcdc  mov     [rsp-28h+arg_10], rbx
0x18000dce1  mov     [rsp-28h+arg_18], rsi
0x18000dce6  push    rbp
0x18000dce7  push    rdi
0x18000dce8  push    r13
0x18000dcea  push    r14
0x18000dcec  push    r15
0x18000dcee  mov     rbp, rsp
0x18000dcf1  sub     rsp, 50h
0x18000dcf5  mov     rdi, rcx
0x18000dcf8  mov     [rbp+arg_8], 0
0x18000dd00  mov     rcx, [rcx+58h]
0x18000dd04  lea     rdx, [rbp+arg_8]
0x18000dd08  mov     [rbp+arg_0], 0
0x18000dd10  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000dd15  test    eax, eax
0x18000dd17  js      loc_18000DE5F
0x18000dd1d  mov     esi, 1
0x18000dd22  cmp     eax, esi
0x18000dd24  jz      loc_18000DE5B
0x18000dd2a  mov     rcx, [rdi+50h]; this
0x18000dd2e  lea     rdx, [rbp+arg_0]; struct Profile **
0x18000dd32  call    ?GetSelectedLParam@ListView@@QEBAJPEAPEAUProfile@@@Z; ListView::GetSelectedLParam(Profile * *)
0x18000dd37  test    eax, eax
0x18000dd39  js      loc_18000DE5F
0x18000dd3f  cmp     eax, esi
0x18000dd41  jz      loc_18000DE5B
0x18000dd47  mov     r14, [rbp+arg_0]
0x18000dd4b  lea     rcx, [rbp+var_20]; this
0x18000dd4f  mov     r13, [rbp+arg_8]
0x18000dd53  mov     r8d, [rdi+48h]; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000dd57  mov     r9, r13; struct Device *
0x18000dd5a  mov     eax, [r14]
0x18000dd5d  mov     [rsp+50h+var_30], eax; enum COLORPROFILETYPE
0x18000dd61  call    ??0DefaultChecker@Helper@@QEAA@AEBVColorDataController@@W4WCS_PROFILE_MANAGEMENT_SCOPE@@AEBUDevice@@W4COLORPROFILETYPE@@@Z; Helper::DefaultChecker::DefaultChecker(ColorDataController const &,WCS_PROFILE_MANAGEMENT_SCOPE,Device const &,COLORPROFILETYPE)
0x18000dd66  mov     ebx, [rbp+var_10]
0x18000dd69  test    ebx, ebx
0x18000dd6b  js      loc_18000DE50
0x18000dd71  cmp     dword ptr [r13+0], 70727472h
0x18000dd79  jnz     short loc_18000DDAE
0x18000dd7b  mov     rcx, [rdi+60h]
0x18000dd7f  lea     rdx, [rbp+arg_0]
0x18000dd83  mov     [rbp+arg_0], 0
0x18000dd8b  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000dd90  mov     ebx, eax
0x18000dd92  test    eax, eax
0x18000dd94  js      loc_18000DE50
0x18000dd9a  cmp     eax, esi
0x18000dd9c  jnz     short loc_18000DDA8
0x18000dd9e  mov     ebx, 80004005h
0x18000dda3  jmp     loc_18000DE50
0x18000dda8  mov     rax, [rbp+arg_0]
0x18000ddac  mov     esi, [rax]
0x18000ddae  mov     rdx, r14; struct Profile *
0x18000ddb1  lea     rcx, [rbp+var_20]; this
0x18000ddb5  call    ?IsDefault@DefaultChecker@Helper@@QEBAHAEBUProfile@@@Z; Helper::DefaultChecker::IsDefault(Profile const &)
0x18000ddba  mov     r15d, eax
0x18000ddbd  test    esi, esi
0x18000ddbf  jz      short loc_18000DDF5
0x18000ddc1  test    eax, eax
0x18000ddc3  jz      short loc_18000DDF5
0x18000ddc5  mov     rdx, [rdi+8]; HINSTANCE
0x18000ddc9  lea     rax, [rbp+arg_0]
0x18000ddcd  mov     rcx, [rdi+10h]; this
0x18000ddd1  xor     r9d, r9d; unsigned int
0x18000ddd4  mov     r8d, 1397h; HWND
0x18000ddda  mov     qword ptr [rsp+50h+var_30], rax; int
0x18000dddf  mov     dword ptr [rbp+arg_0], 0
0x18000dde6  call    ?ShowWarningDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@IHPEAH@Z; Helper::ShowWarningDialog(HINSTANCE__ *,HWND__ *,uint,int,int *)
0x18000ddeb  test    eax, eax
0x18000dded  js      short loc_18000DE4E
0x18000ddef  cmp     dword ptr [rbp+arg_0], 0
0x18000ddf3  jnz     short loc_18000DE4E
0x18000ddf5  mov     rax, [rdi+38h]
0x18000ddf9  lea     r9, [r14+214h]
0x18000de00  mov     edx, [r14+420h]
0x18000de07  lea     r8, [r13+4]
0x18000de0b  mov     [rsp+50h+var_30], edx
0x18000de0f  mov     edx, [rdi+48h]
0x18000de12  mov     rcx, [rax+10h]
0x18000de16  mov     rax, [rcx]
0x18000de19  mov     rax, [rax+38h]
0x18000de1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de22  test    eax, eax
0x18000de24  js      short loc_18000DE4E
0x18000de26  mov     eax, [r14]
0x18000de29  mov     rcx, [rdi+50h]; this
0x18000de2d  mov     dword ptr [rbp+arg_0], eax
0x18000de30  call    ?RemoveSelectedItem@ListView@@QEAAJXZ; ListView::RemoveSelectedItem(void)
0x18000de35  mov     ebx, eax
0x18000de37  test    eax, eax
0x18000de39  js      short loc_18000DE50
0x18000de3b  test    r15d, r15d
0x18000de3e  jz      short loc_18000DE50
0x18000de40  lea     r8, [rbp+arg_0]; enum COLORPROFILETYPE *
0x18000de44  xor     edx, edx; int
0x18000de46  mov     rcx, rdi; this
0x18000de49  call    ?UpdateProfileListViewOnDefaultsChanged@DevicesPage@@AEAAJHPEAW4COLORPROFILETYPE@@PEAUProfile@@@Z; DevicesPage::UpdateProfileListViewOnDefaultsChanged(int,COLORPROFILETYPE *,Profile *)
0x18000de4e  mov     ebx, eax
0x18000de50  lea     rcx, [rbp+var_20]; this
0x18000de54  call    ??1DefaultChecker@Helper@@QEAA@XZ; Helper::DefaultChecker::~DefaultChecker(void)
0x18000de59  jmp     short loc_18000DE5D
0x18000de5b  xor     ebx, ebx
0x18000de5d  mov     eax, ebx
0x18000de5f  lea     r11, [rsp+50h+var_s0]
0x18000de64  mov     rbx, [r11+40h]
0x18000de68  mov     rsi, [r11+48h]
0x18000de6c  mov     rsp, r11
0x18000de6f  pop     r15
0x18000de71  pop     r14
0x18000de73  pop     r13
0x18000de75  pop     rdi
0x18000de76  pop     rbp
0x18000de77  retn
```
