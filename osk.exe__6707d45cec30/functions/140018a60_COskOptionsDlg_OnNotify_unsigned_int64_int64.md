# COskOptionsDlg::OnNotify(unsigned __int64,__int64)

- ea: `0x140018a60`
- end: `0x140018b30`
- name: `?OnNotify@COskOptionsDlg@@AEAAX_K_J@Z`
- size: `208`
- prototype: `void __fastcall(COskOptionsDlg *__hidden this, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140018db0`

## callees

- `0x14000f93c`
- `0x140012db0`
- `0x140018a60`
- `0x140019030`
- `0x14001b7bc`
- `0x140027010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x140018ae2`
- `ole32!CoCreateInstance` at `0x140018ae2`

## string_xrefs

- `0x140018afe`: `Microsoft.EaseOfAccessCenter`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall COskOptionsDlg::OnNotify(COskOptionsDlg *this, unsigned __int16 a2, __int64 a3)
{
  int v3; // r9d
  int v4; // edx
  __int64 v5; // rdx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  v3 = a2;
  v4 = a2 - 5017;
  if ( v4 && (v5 = (unsigned int)(v4 - 3), (_DWORD)v5) )
  {
    if ( (_DWORD)v5 == 11 )
    {
      if ( a3 )
      {
        if ( ((*(_DWORD *)(a3 + 16) + 4) & 0xFFFFFFFD) == 0 )
        {
          LOBYTE(v5) = 1;
          wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(
            `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl'::`2'::impl,
            v5);
          if ( !COSKUtils::ShouldRunSecureOnLockScreen() )
          {
            ppv = 0;
            if ( CoCreateInstance(&CLSID_OpenControlPanel, 0, 0x17u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &ppv) >= 0 )
              (*(void (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                L"Microsoft.EaseOfAccessCenter",
                L"pageNoMouseOrKeyboard",
                0);
            ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(&ppv);
          }
        }
      }
    }
  }
  else if ( a3 )
  {
    COskOptionsDlg::SetIntervalUI(this, v3);
  }
}

```

## disassembly

```asm
0x140018a60  sub     rsp, 38h
0x140018a64  movzx   r9d, dx
0x140018a68  mov     edx, r9d
0x140018a6b  sub     edx, 1399h
0x140018a71  jz      loc_140018B1E
0x140018a77  sub     edx, 3
0x140018a7a  jz      loc_140018B1E
0x140018a80  cmp     edx, 0Bh
0x140018a83  jnz     loc_140018B2B
0x140018a89  test    r8, r8
0x140018a8c  jz      loc_140018B2B
0x140018a92  mov     eax, [r8+10h]
0x140018a96  add     eax, 4
0x140018a99  test    eax, 0FFFFFFFDh
0x140018a9e  jnz     loc_140018B2B
0x140018aa4  mov     dl, 1
0x140018aa6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen> `wil::Feature<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::GetImpl(void)'::`2'::impl
0x140018aad  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_OSK_SecureOnLockScreen@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OSK_SecureOnLockScreen>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140018ab2  call    ?ShouldRunSecureOnLockScreen@COSKUtils@@SA_NXZ; COSKUtils::ShouldRunSecureOnLockScreen(void)
0x140018ab7  test    al, al
0x140018ab9  jnz     short loc_140018B2B
0x140018abb  mov     [rsp+38h+arg_8], 0
0x140018ac4  lea     rax, [rsp+38h+arg_8]
0x140018ac9  mov     [rsp+38h+ppv], rax; ppv
0x140018ace  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x140018ad5  xor     edx, edx; pUnkOuter
0x140018ad7  lea     r8d, [rdx+17h]; dwClsContext
0x140018adb  lea     rcx, CLSID_OpenControlPanel; rclsid
0x140018ae2  call    cs:__imp_CoCreateInstance
0x140018ae8  test    eax, eax
0x140018aea  js      short loc_140018B0F
0x140018aec  mov     rcx, [rsp+38h+arg_8]
0x140018af1  mov     rax, [rcx]
0x140018af4  xor     r9d, r9d
0x140018af7  lea     r8, aPagenomouseork; "pageNoMouseOrKeyboard"
0x140018afe  lea     rdx, aMicrosoftEaseo; "Microsoft.EaseOfAccessCenter"
0x140018b05  mov     rax, [rax+18h]
0x140018b09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018b0e  nop
0x140018b0f  lea     rcx, [rsp+38h+arg_8]
0x140018b14  call    ??1?$CComPtrBase@UITPLangMod@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ITPLangMod>::~CComPtrBase<ITPLangMod>(void)
0x140018b19  add     rsp, 38h
0x140018b1d  retn
0x140018b1e  test    r8, r8
0x140018b21  jz      short loc_140018B2B
0x140018b23  mov     edx, r9d; int
0x140018b26  call    ?SetIntervalUI@COskOptionsDlg@@AEAAXH@Z; COskOptionsDlg::SetIntervalUI(int)
0x140018b2b  add     rsp, 38h
0x140018b2f  retn
```
