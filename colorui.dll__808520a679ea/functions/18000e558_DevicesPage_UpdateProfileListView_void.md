# DevicesPage::UpdateProfileListView(void)

- ea: `0x18000e558`
- end: `0x18000e6aa`
- name: `?UpdateProfileListView@DevicesPage@@AEAAJXZ`
- size: `338`
- prototype: `__int64 __fastcall(ListView **this)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000d67c`
- `0x18000d7dc`
- `0x18000e094`
- `0x18000e144`

## callees

- `0x18000ccc0`
- `0x18000cd08`
- `0x18000e558`
- `0x18000e7ac`
- `0x180011050`
- `0x180013050`
- `0x180013160`
- `0x180017f54`
- `0x180017fa8`
- `0x180017ff4`

## pseudocode

```c
__int64 __fastcall DevicesPage::UpdateProfileListView(ListView **this)
{
  struct _DSA *v2; // rbx
  HWND *v4; // rcx
  int SelectedLParam; // esi
  LRESULT v6; // rbx
  WCS_PROFILE_MANAGEMENT_SCOPE SettingsScope; // eax
  DWORD v8; // r9d
  WCS_PROFILE_MANAGEMENT_SCOPE v9; // eax
  DWORD v10; // r9d
  struct Profile *v11; // r9
  unsigned int updated; // eax
  unsigned int v13; // edi
  LRESULT v14; // [rsp+50h] [rbp+20h] BYREF
  HDSA hdsa; // [rsp+58h] [rbp+28h] BYREF

  ListView::Clear(this[10]);
  hdsa = DSA_Create(1060, 10);
  v2 = hdsa;
  if ( !hdsa )
    return 2147500037LL;
  v4 = (HWND *)this[11];
  v14 = 0;
  SelectedLParam = Combo<Device>::GetSelectedLParam(v4, &v14);
  if ( SelectedLParam < 0 )
  {
LABEL_4:
    DSA_DeleteAllItems(v2);
    DSA_Destroy(v2);
    return (unsigned int)SelectedLParam;
  }
  if ( SelectedLParam == 1 )
  {
    v13 = 0;
  }
  else
  {
    v6 = v14;
    SettingsScope = (unsigned int)DevicesPage::GetReadSettingsScope((DevicesPage *)this);
    v8 = *(_DWORD *)v6;
    LODWORD(v14) = 0;
    SelectedLParam = ColorDataController::EnumerateProfiles(
                       (__int64)&v14,
                       SettingsScope,
                       (const WCHAR *)(v6 + 4),
                       v8,
                       &v14,
                       &hdsa);
    if ( SelectedLParam < 0
      || (v9 = (unsigned int)DevicesPage::GetReadSettingsScope((DevicesPage *)this),
          v10 = *(_DWORD *)v6,
          LODWORD(v14) = 1,
          SelectedLParam = ColorDataController::EnumerateProfiles(
                             (__int64)&v14,
                             v9,
                             (const WCHAR *)(v6 + 4),
                             v10,
                             &v14,
                             &hdsa),
          SelectedLParam < 0)
      || (SelectedLParam = ListView::AddProfileItems((WPARAM)this[10]), SelectedLParam < 0) )
    {
      v2 = hdsa;
      if ( !hdsa )
        return (unsigned int)SelectedLParam;
      goto LABEL_4;
    }
    updated = DevicesPage::UpdateProfileListViewOnDefaultsChanged((DevicesPage *)this, 1, 0, v11);
    v2 = hdsa;
    v13 = updated;
  }
  if ( v2 )
  {
    DSA_DeleteAllItems(v2);
    DSA_Destroy(v2);
  }
  return v13;
}

```

## disassembly

```asm
0x18000e558  mov     [rsp-18h+arg_10], rbx
0x18000e55d  mov     [rsp-18h+arg_18], rsi
0x18000e562  push    rbp
0x18000e563  push    rdi
0x18000e564  push    r14
0x18000e566  mov     rbp, rsp
0x18000e569  sub     rsp, 30h
0x18000e56d  mov     rdi, rcx
0x18000e570  mov     rcx, [rcx+50h]; this
0x18000e574  call    ?Clear@ListView@@QEAAXXZ; ListView::Clear(void)
0x18000e579  mov     edx, 0Ah; cItemGrow
0x18000e57e  mov     ecx, 424h; cbItem
0x18000e583  call    DSA_Create
0x18000e588  mov     [rbp+hdsa], rax
0x18000e58c  mov     rbx, rax
0x18000e58f  test    rax, rax
0x18000e592  jnz     short loc_18000E59E
0x18000e594  mov     eax, 80004005h
0x18000e599  jmp     loc_18000E697
0x18000e59e  mov     rcx, [rdi+58h]
0x18000e5a2  lea     rdx, [rbp+arg_0]
0x18000e5a6  mov     [rbp+arg_0], 0
0x18000e5ae  call    ?GetSelectedLParam@?$Combo@UDevice@@@@QEBAJPEAPEAUDevice@@@Z; Combo<Device>::GetSelectedLParam(Device * *)
0x18000e5b3  mov     esi, eax
0x18000e5b5  test    eax, eax
0x18000e5b7  jns     short loc_18000E5D0
0x18000e5b9  mov     rcx, rbx; hdsa
0x18000e5bc  call    DSA_DeleteAllItems
0x18000e5c1  mov     rcx, rbx; hdsa
0x18000e5c4  call    DSA_Destroy
0x18000e5c9  mov     eax, esi
0x18000e5cb  jmp     loc_18000E697
0x18000e5d0  cmp     esi, 1
0x18000e5d3  jz      loc_18000E67E
0x18000e5d9  mov     rbx, [rbp+arg_0]
0x18000e5dd  mov     rcx, rdi; this
0x18000e5e0  call    ?GetReadSettingsScope@DevicesPage@@AEAA?AW4WCS_PROFILE_MANAGEMENT_SCOPE@@XZ; DevicesPage::GetReadSettingsScope(void)
0x18000e5e5  mov     r9d, [rbx]
0x18000e5e8  lea     rcx, [rbp+hdsa]
0x18000e5ec  mov     [rsp+30h+var_8], rcx
0x18000e5f1  lea     r8, [rbx+4]
0x18000e5f5  lea     rcx, [rbp+arg_0]
0x18000e5f9  mov     dword ptr [rbp+arg_0], 0
0x18000e600  mov     edx, eax
0x18000e602  mov     [rsp+30h+var_10], rcx
0x18000e607  call    ?EnumerateProfiles@ColorDataController@@AEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKPEAHPEAV?$Array@UProfile@@@@@Z; ColorDataController::EnumerateProfiles(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int *,Array<Profile> *)
0x18000e60c  mov     esi, eax
0x18000e60e  test    eax, eax
0x18000e610  jns     short loc_18000E61D
0x18000e612  mov     rbx, [rbp+hdsa]
0x18000e616  test    rbx, rbx
0x18000e619  jz      short loc_18000E5C9
0x18000e61b  jmp     short loc_18000E5B9
0x18000e61d  mov     rcx, rdi; this
0x18000e620  call    ?GetReadSettingsScope@DevicesPage@@AEAA?AW4WCS_PROFILE_MANAGEMENT_SCOPE@@XZ; DevicesPage::GetReadSettingsScope(void)
0x18000e625  mov     r9d, [rbx]
0x18000e628  lea     rcx, [rbp+hdsa]
0x18000e62c  mov     [rsp+30h+var_8], rcx
0x18000e631  lea     r8, [rbx+4]
0x18000e635  lea     rcx, [rbp+arg_0]
0x18000e639  mov     dword ptr [rbp+arg_0], 1
0x18000e640  mov     edx, eax
0x18000e642  mov     [rsp+30h+var_10], rcx
0x18000e647  call    ?EnumerateProfiles@ColorDataController@@AEBAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKPEAHPEAV?$Array@UProfile@@@@@Z; ColorDataController::EnumerateProfiles(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,int *,Array<Profile> *)
0x18000e64c  mov     esi, eax
0x18000e64e  test    eax, eax
0x18000e650  js      short loc_18000E612
0x18000e652  mov     rcx, [rdi+50h]; wParam
0x18000e656  lea     r8, [rbp+hdsa]
0x18000e65a  xor     edx, edx
0x18000e65c  call    ?AddProfileItems@ListView@@QEAAJW4Enum@ListViewStyle@@AEBV?$Array@UProfile@@@@@Z; ListView::AddProfileItems(ListViewStyle::Enum,Array<Profile> const &)
0x18000e661  mov     esi, eax
0x18000e663  test    eax, eax
0x18000e665  js      short loc_18000E612
0x18000e667  xor     r8d, r8d; enum COLORPROFILETYPE *
0x18000e66a  mov     rcx, rdi; this
0x18000e66d  lea     edx, [r8+1]; int
0x18000e671  call    ?UpdateProfileListViewOnDefaultsChanged@DevicesPage@@AEAAJHPEAW4COLORPROFILETYPE@@PEAUProfile@@@Z; DevicesPage::UpdateProfileListViewOnDefaultsChanged(int,COLORPROFILETYPE *,Profile *)
0x18000e676  mov     rbx, [rbp+hdsa]
0x18000e67a  mov     edi, eax
0x18000e67c  jmp     short loc_18000E680
0x18000e67e  xor     edi, edi
0x18000e680  test    rbx, rbx
0x18000e683  jz      short loc_18000E695
0x18000e685  mov     rcx, rbx; hdsa
0x18000e688  call    DSA_DeleteAllItems
0x18000e68d  mov     rcx, rbx; hdsa
0x18000e690  call    DSA_Destroy
0x18000e695  mov     eax, edi
0x18000e697  mov     rbx, [rsp+30h+arg_10]
0x18000e69c  mov     rsi, [rsp+30h+arg_18]
0x18000e6a1  add     rsp, 30h
0x18000e6a5  pop     r14
0x18000e6a7  pop     rdi
0x18000e6a8  pop     rbp
0x18000e6a9  retn
```
