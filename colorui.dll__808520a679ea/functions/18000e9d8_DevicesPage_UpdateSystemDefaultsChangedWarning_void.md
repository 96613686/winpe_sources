# DevicesPage::UpdateSystemDefaultsChangedWarning(void)

- ea: `0x18000e9d8`
- end: `0x18000eaf4`
- name: `?UpdateSystemDefaultsChangedWarning@DevicesPage@@AEAAJXZ`
- size: `284`
- prototype: `__int64 __fastcall(DevicesPage *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e144`

## callees

- `0x18000e094`
- `0x18000e9d8`
- `0x18001772c`
- `0x1800179f0`
- `0x18001837c`
- `0x1800184ce`

## pseudocode

```c
__int64 __fastcall DevicesPage::UpdateSystemDefaultsChangedWarning(DevicesPage *this)
{
  int StringFromRC; // edi
  HINSTANCE v3; // rdx
  int v5; // [rsp+20h] [rbp-69h] BYREF
  const WCHAR *v6; // [rsp+28h] [rbp-61h]
  int v7; // [rsp+30h] [rbp-59h] BYREF
  const WCHAR *v8; // [rsp+38h] [rbp-51h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+40h] [rbp-49h] BYREF

  v8 = &NCoreLibrary::TString::gszNullState;
  StringFromRC = 0;
  v7 = 1735554163;
  v5 = 1735554163;
  v6 = &NCoreLibrary::TString::gszNullState;
  if ( !*((_DWORD *)this + 29) )
  {
    v3 = (HINSTANCE)*((_QWORD *)this + 2);
    *((_DWORD *)this + 29) = 1;
    StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v7, v3, 6u);
    if ( StringFromRC >= 0 )
    {
      StringFromRC = NCoreLibrary::TString::LoadStringFromRC(
                       (NCoreLibrary::TString *)&v5,
                       *((HINSTANCE *)this + 2),
                       0x7EDu);
      if ( StringFromRC >= 0 )
      {
        memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
        pTaskConfig.hwndParent = (HWND)*((_QWORD *)this + 1);
        pTaskConfig.hInstance = (HINSTANCE)*((_QWORD *)this + 2);
        pTaskConfig.pszWindowTitle = v8;
        pTaskConfig.pszContent = v6;
        pTaskConfig.cbSize = 160;
        pTaskConfig.dwFlags = 8;
        pTaskConfig.dwCommonButtons = 1;
        pTaskConfig.hMainIcon = (HICON)0xFFFF;
        StringFromRC = TaskDialogIndirect(&pTaskConfig, 0, 0, 0);
        if ( StringFromRC >= 0 )
          StringFromRC = DevicesPage::OnSyncWithSystemAssociations((HWND **)this, 2);
      }
    }
    *((_DWORD *)this + 29) = 0;
  }
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v5);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v7);
  return (unsigned int)StringFromRC;
}

```

## disassembly

```asm
0x18000e9d8  mov     [rsp-8+arg_0], rbx
0x18000e9dd  mov     [rsp-8+arg_8], rdi
0x18000e9e2  push    rbp
0x18000e9e3  lea     rbp, [rsp-57h]
0x18000e9e8  sub     rsp, 0E0h
0x18000e9ef  mov     rbx, rcx
0x18000e9f2  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18000e9f9  mov     ecx, 67727473h
0x18000e9fe  mov     [rbp+57h+var_A8], rax
0x18000ea02  xor     edi, edi
0x18000ea04  mov     [rbp+57h+var_B0], ecx
0x18000ea07  mov     [rbp+57h+var_C0], ecx
0x18000ea0a  mov     [rbp+57h+var_B8], rax
0x18000ea0e  cmp     [rbx+74h], edi
0x18000ea11  jnz     loc_18000EACB
0x18000ea17  mov     rdx, [rbx+10h]; HINSTANCE
0x18000ea1b  lea     r8d, [rdi+6]; unsigned int
0x18000ea1f  lea     rcx, [rbp+57h+var_B0]; this
0x18000ea23  mov     dword ptr [rbx+74h], 1
0x18000ea2a  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18000ea2f  mov     edi, eax
0x18000ea31  test    eax, eax
0x18000ea33  js      loc_18000EAC4
0x18000ea39  mov     rdx, [rbx+10h]; HINSTANCE
0x18000ea3d  lea     rcx, [rbp+57h+var_C0]; this
0x18000ea41  mov     r8d, 7EDh; unsigned int
0x18000ea47  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18000ea4c  mov     edi, eax
0x18000ea4e  test    eax, eax
0x18000ea50  js      short loc_18000EAC4
0x18000ea52  mov     edi, 0A0h
0x18000ea57  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x18000ea5b  mov     r8d, edi; Size
0x18000ea5e  xor     edx, edx; Val
0x18000ea60  call    memset_0
0x18000ea65  mov     rax, [rbx+8]
0x18000ea69  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x18000ea6d  mov     [rbp+57h+pTaskConfig.hwndParent], rax
0x18000ea71  xor     r9d, r9d; pfVerificationFlagChecked
0x18000ea74  mov     rax, [rbx+10h]
0x18000ea78  xor     r8d, r8d; pnRadioButton
0x18000ea7b  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x18000ea7f  xor     edx, edx; pnButton
0x18000ea81  mov     rax, [rbp+57h+var_A8]
0x18000ea85  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rax
0x18000ea89  mov     rax, [rbp+57h+var_B8]
0x18000ea8d  mov     [rbp+57h+pTaskConfig.pszContent], rax
0x18000ea91  mov     [rbp+57h+pTaskConfig.cbSize], edi
0x18000ea94  mov     [rbp+57h+pTaskConfig.dwFlags], 8
0x18000ea9b  mov     [rbp+57h+pTaskConfig.dwCommonButtons], 1
0x18000eaa2  mov     qword ptr [rbp+57h+pTaskConfig.24h], 0FFFFh
0x18000eaaa  call    TaskDialogIndirect
0x18000eaaf  mov     edi, eax
0x18000eab1  test    eax, eax
0x18000eab3  js      short loc_18000EAC4
0x18000eab5  mov     edx, 2
0x18000eaba  mov     rcx, rbx
0x18000eabd  call    ?OnSyncWithSystemAssociations@DevicesPage@@AEAAJW4AssocListSyncType@1@@Z; DevicesPage::OnSyncWithSystemAssociations(DevicesPage::AssocListSyncType)
0x18000eac2  mov     edi, eax
0x18000eac4  mov     dword ptr [rbx+74h], 0
0x18000eacb  lea     rcx, [rbp+57h+var_C0]; this
0x18000eacf  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000ead4  lea     rcx, [rbp+57h+var_B0]; this
0x18000ead8  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000eadd  lea     r11, [rsp+0E0h+var_s0]
0x18000eae5  mov     eax, edi
0x18000eae7  mov     rbx, [r11+10h]
0x18000eaeb  mov     rdi, [r11+18h]
0x18000eaef  mov     rsp, r11
0x18000eaf2  pop     rbp
0x18000eaf3  retn
```
