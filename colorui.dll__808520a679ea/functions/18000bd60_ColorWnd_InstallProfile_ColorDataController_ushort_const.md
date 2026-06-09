# ColorWnd::InstallProfile(ColorDataController *,ushort const *)

- ea: `0x18000bd60`
- end: `0x18000bed4`
- name: `?InstallProfile@ColorWnd@@QEAAJPEAVColorDataController@@PEBG@Z`
- size: `372`
- prototype: `__int64 __fastcall(HINSTANCE *this, struct ColorDataController *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006880`

## callees

- `0x18000bd60`
- `0x180012438`
- `0x18001772c`
- `0x1800178d4`
- `0x1800179f0`
- `0x18001837c`
- `0x1800184ce`
- `0x180019010`

## import_xrefs

- `SHLWAPI!PathFindFileNameW` at `0x18000bda8`
- `SHLWAPI!PathFindFileNameW` at `0x18000bda8`

## pseudocode

```c
__int64 __fastcall ColorWnd::InstallProfile(
        HINSTANCE *this,
        struct ColorDataController *a2,
        const unsigned __int16 *a3)
{
  const unsigned __int16 *FileNameW; // rax
  const unsigned __int16 *v7; // rsi
  ColorDataController *v8; // rcx
  HRESULT IsProfileInstalled; // ebx
  int v10; // ecx
  int v12; // [rsp+20h] [rbp-A9h] BYREF
  const WCHAR *v13; // [rsp+28h] [rbp-A1h]
  int v14; // [rsp+30h] [rbp-99h] BYREF
  unsigned __int16 *v15; // [rsp+38h] [rbp-91h]
  int v16; // [rsp+40h] [rbp-89h] BYREF
  const WCHAR *v17; // [rsp+48h] [rbp-81h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+50h] [rbp-79h] BYREF
  int v19; // [rsp+148h] [rbp+7Fh] BYREF

  v17 = &NCoreLibrary::TString::gszNullState;
  v16 = 1735554163;
  v14 = 1735554163;
  v12 = 1735554163;
  v15 = &NCoreLibrary::TString::gszNullState;
  v13 = &NCoreLibrary::TString::gszNullState;
  FileNameW = PathFindFileNameW(a3);
  v19 = 0;
  v7 = FileNameW;
  IsProfileInstalled = ColorDataController::IsProfileInstalled(v8, FileNameW, &v19);
  if ( IsProfileInstalled >= 0 )
  {
    v10 = v19;
  }
  else
  {
    v10 = 0;
    IsProfileInstalled = 0;
  }
  if ( !v10
    && (*(int (__fastcall **)(_QWORD, const unsigned __int16 *))(**((_QWORD **)a2 + 2) + 32LL))(*((_QWORD *)a2 + 2), a3) < 0 )
  {
    IsProfileInstalled = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v16, *this, 6u);
    if ( IsProfileInstalled >= 0 )
    {
      IsProfileInstalled = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v14, *this, 0x1518u);
      if ( IsProfileInstalled >= 0 )
      {
        IsProfileInstalled = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v12, v15, v7);
        if ( IsProfileInstalled >= 0 )
        {
          memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
          pTaskConfig.hInstance = *this;
          pTaskConfig.pszWindowTitle = v17;
          pTaskConfig.pszContent = v13;
          pTaskConfig.cbSize = 160;
          pTaskConfig.hwndParent = 0;
          pTaskConfig.dwFlags = 8;
          pTaskConfig.dwCommonButtons = 1;
          pTaskConfig.hMainIcon = (HICON)65534;
          IsProfileInstalled = TaskDialogIndirect(&pTaskConfig, 0, 0, 0);
        }
      }
    }
  }
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v12);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v14);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v16);
  return (unsigned int)IsProfileInstalled;
}

```

## disassembly

```asm
0x18000bd60  push    rbp
0x18000bd62  push    rbx
0x18000bd63  push    rsi
0x18000bd64  push    rdi
0x18000bd65  push    r14
0x18000bd67  push    r15
0x18000bd69  lea     rbp, [rsp-2Fh]
0x18000bd6e  sub     rsp, 0F8h
0x18000bd75  lea     rax, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x18000bd7c  mov     rdi, rcx
0x18000bd7f  mov     ecx, 67727473h
0x18000bd84  mov     [rsp+120h+var_D8], rax
0x18000bd89  mov     [rsp+120h+var_E0], ecx
0x18000bd8d  mov     r14, r8
0x18000bd90  mov     [rsp+120h+var_F0], ecx
0x18000bd94  mov     r15, rdx
0x18000bd97  mov     [rsp+120h+var_100], ecx
0x18000bd9b  mov     rcx, r8; pszPath
0x18000bd9e  mov     [rsp+120h+var_E8], rax
0x18000bda3  mov     [rsp+120h+var_F8], rax
0x18000bda8  call    cs:__imp_PathFindFileNameW
0x18000bdae  lea     r8, [rbp+57h+arg_18]; int *
0x18000bdb2  mov     [rbp+57h+arg_18], 0
0x18000bdb9  mov     rdx, rax; unsigned __int16 *
0x18000bdbc  mov     rsi, rax
0x18000bdbf  call    ?IsProfileInstalled@ColorDataController@@QEBAJPEBGPEAH@Z; ColorDataController::IsProfileInstalled(ushort const *,int *)
0x18000bdc4  mov     ebx, eax
0x18000bdc6  test    eax, eax
0x18000bdc8  jns     short loc_18000BDD0
0x18000bdca  xor     ecx, ecx
0x18000bdcc  xor     ebx, ebx
0x18000bdce  jmp     short loc_18000BDD3
0x18000bdd0  mov     ecx, [rbp+57h+arg_18]
0x18000bdd3  test    ecx, ecx
0x18000bdd5  jnz     loc_18000BEA4
0x18000bddb  mov     rcx, [r15+10h]
0x18000bddf  mov     rdx, r14
0x18000bde2  mov     rax, [rcx]
0x18000bde5  mov     rax, [rax+20h]
0x18000bde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdee  test    eax, eax
0x18000bdf0  jns     loc_18000BEA4
0x18000bdf6  mov     rdx, [rdi]; HINSTANCE
0x18000bdf9  lea     rcx, [rsp+120h+var_E0]; this
0x18000bdfe  mov     r8d, 6; unsigned int
0x18000be04  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18000be09  mov     ebx, eax
0x18000be0b  test    eax, eax
0x18000be0d  js      loc_18000BEA4
0x18000be13  mov     rdx, [rdi]; HINSTANCE
0x18000be16  lea     rcx, [rsp+120h+var_F0]; this
0x18000be1b  mov     r8d, 1518h; unsigned int
0x18000be21  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x18000be26  mov     ebx, eax
0x18000be28  test    eax, eax
0x18000be2a  js      short loc_18000BEA4
0x18000be2c  mov     rdx, [rsp+120h+var_E8]; unsigned __int16 *
0x18000be31  lea     rcx, [rsp+120h+var_100]; this
0x18000be36  mov     r8, rsi
0x18000be39  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x18000be3e  mov     ebx, eax
0x18000be40  test    eax, eax
0x18000be42  js      short loc_18000BEA4
0x18000be44  mov     ebx, 0A0h
0x18000be49  lea     rcx, [rbp+57h+pTaskConfig]; void *
0x18000be4d  mov     r8d, ebx; Size
0x18000be50  xor     edx, edx; Val
0x18000be52  call    memset_0
0x18000be57  mov     rax, [rdi]
0x18000be5a  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x18000be5e  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x18000be62  xor     r9d, r9d; pfVerificationFlagChecked
0x18000be65  mov     rax, [rsp+120h+var_D8]
0x18000be6a  xor     r8d, r8d; pnRadioButton
0x18000be6d  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rax
0x18000be71  xor     edx, edx; pnButton
0x18000be73  mov     rax, [rsp+120h+var_F8]
0x18000be78  mov     [rbp+57h+pTaskConfig.pszContent], rax
0x18000be7c  mov     [rbp+57h+pTaskConfig.cbSize], ebx
0x18000be7f  mov     [rbp+57h+pTaskConfig.hwndParent], 0
0x18000be87  mov     [rbp+57h+pTaskConfig.dwFlags], 8
0x18000be8e  mov     [rbp+57h+pTaskConfig.dwCommonButtons], 1
0x18000be95  mov     qword ptr [rbp+57h+pTaskConfig.24h], 0FFFEh
0x18000be9d  call    TaskDialogIndirect
0x18000bea2  mov     ebx, eax
0x18000bea4  lea     rcx, [rsp+120h+var_100]; this
0x18000bea9  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000beae  lea     rcx, [rsp+120h+var_F0]; this
0x18000beb3  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000beb8  lea     rcx, [rsp+120h+var_E0]; this
0x18000bebd  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x18000bec2  mov     eax, ebx
0x18000bec4  add     rsp, 0F8h
0x18000becb  pop     r15
0x18000becd  pop     r14
0x18000becf  pop     rdi
0x18000bed0  pop     rsi
0x18000bed1  pop     rbx
0x18000bed2  pop     rbp
0x18000bed3  retn
```
