# Helper::ShowErrorDialog(HINSTANCE__ *,HWND__ *,ushort const *,long)

- ea: `0x180015cc8`
- end: `0x180015ec5`
- name: `?ShowErrorDialog@Helper@@YAJPEAUHINSTANCE__@@PEAUHWND__@@PEBGJ@Z`
- size: `509`
- prototype: `__int64 __fastcall(HINSTANCE this, HWND, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180006880`
- `0x18000c450`
- `0x18000d338`
- `0x180015c5c`
- `0x180017260`

## callees

- `0x180015cc8`
- `0x18001772c`
- `0x18001775c`
- `0x1800178d4`
- `0x1800179f0`
- `0x180017ab0`
- `0x18001837c`
- `0x1800184ce`
- `0x180018500`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180015d83`
- `KERNEL32!FormatMessageW` at `0x180015d83`
- `KERNEL32!GetLastError` at `0x180015d8d`
- `KERNEL32!GetLastError` at `0x180015d8d`

## pseudocode

```c
__int64 __fastcall Helper::ShowErrorDialog(
        HINSTANCE this,
        HWND a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  unsigned __int16 *v4; // rdi
  int v8; // r15d
  int StringFromRC; // ebx
  signed int LastError; // eax
  int v11; // eax
  const unsigned __int16 *v12; // rdx
  int v14; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v15; // [rsp+48h] [rbp-B8h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v17; // [rsp+58h] [rbp-A8h]
  int v18; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v19; // [rsp+68h] [rbp-98h]
  int v20; // [rsp+70h] [rbp-90h] BYREF
  const WCHAR *v21; // [rsp+78h] [rbp-88h]
  TASKDIALOGCONFIG pTaskConfig; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[264]; // [rsp+120h] [rbp+20h] BYREF

  v4 = &NCoreLibrary::TString::gszNullState;
  v20 = 1735554163;
  v21 = &NCoreLibrary::TString::gszNullState;
  v18 = 1735554163;
  v19 = &NCoreLibrary::TString::gszNullState;
  v14 = 1735554163;
  v15 = &NCoreLibrary::TString::gszNullState;
  v16 = 1735554163;
  v8 = (int)a4;
  v17 = &NCoreLibrary::TString::gszNullState;
  memset_0(Buffer, 0, 0x208u);
  StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v20, this, 0x1389u);
  if ( v8 < 0 )
  {
    if ( !FormatMessageW(0x1000u, 0, (unsigned __int16)v8, 0, Buffer, 0x104u, 0) )
    {
      LastError = GetLastError();
      StringFromRC = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          StringFromRC = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        StringFromRC = -2147467259;
      }
    }
    if ( StringFromRC >= 0 )
    {
      NCoreLibrary::TString::Cat((NCoreLibrary::TString *)&v16, Buffer);
      v4 = v17;
    }
  }
  if ( a3 )
  {
    if ( *v4 )
    {
      StringFromRC = NCoreLibrary::TString::LoadStringFromRC((NCoreLibrary::TString *)&v18, this, 0x139Cu);
      if ( StringFromRC < 0 )
        goto LABEL_20;
      v11 = NCoreLibrary::TString::Format((NCoreLibrary::TString *)&v14, v19, a3, v4);
      goto LABEL_17;
    }
    v12 = a3;
  }
  else
  {
    if ( !*v4 )
      goto LABEL_18;
    v12 = v4;
  }
  v11 = NCoreLibrary::TString::Update((NCoreLibrary::TString *)&v14, v12);
LABEL_17:
  StringFromRC = v11;
LABEL_18:
  if ( StringFromRC >= 0 )
  {
    memset_0(&pTaskConfig, 0, sizeof(pTaskConfig));
    pTaskConfig.pszWindowTitle = v21;
    pTaskConfig.pszContent = v15;
    pTaskConfig.cbSize = 160;
    pTaskConfig.hwndParent = a2;
    pTaskConfig.hInstance = this;
    pTaskConfig.dwFlags = 8;
    pTaskConfig.dwCommonButtons = 1;
    pTaskConfig.hMainIcon = (HICON)0xFFFF;
    StringFromRC = TaskDialogIndirect(&pTaskConfig, 0, 0, 0);
  }
LABEL_20:
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v16);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v14);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v18);
  NCoreLibrary::TString::~TString((NCoreLibrary::TString *)&v20);
  return (unsigned int)StringFromRC;
}

```

## disassembly

```asm
0x180015cc8  push    rbp
0x180015cca  push    rbx
0x180015ccb  push    rsi
0x180015ccc  push    rdi
0x180015ccd  push    r12
0x180015ccf  push    r13
0x180015cd1  push    r14
0x180015cd3  push    r15
0x180015cd5  lea     rbp, [rsp-248h]
0x180015cdd  sub     rsp, 348h
0x180015ce4  mov     rax, cs:__security_cookie
0x180015ceb  xor     rax, rsp
0x180015cee  mov     [rbp+280h+var_50], rax
0x180015cf5  mov     eax, 67727473h
0x180015cfa  lea     rdi, ?gszNullState@TString@NCoreLibrary@@0PAGA; ushort near * NCoreLibrary::TString::gszNullState
0x180015d01  mov     rsi, r8
0x180015d04  mov     [rsp+380h+var_310], eax
0x180015d08  mov     r12, rdx
0x180015d0b  mov     [rsp+380h+var_308], rdi
0x180015d10  mov     r14, rcx
0x180015d13  mov     [rsp+380h+var_320], eax
0x180015d17  xor     edx, edx; Val
0x180015d19  mov     [rsp+380h+var_318], rdi
0x180015d1e  mov     r8d, 208h; Size
0x180015d24  mov     [rsp+380h+var_340], eax
0x180015d28  lea     rcx, [rbp+280h+Buffer]; void *
0x180015d2c  mov     [rsp+380h+var_338], rdi
0x180015d31  mov     [rsp+380h+var_330], eax
0x180015d35  mov     r15d, r9d
0x180015d38  mov     [rsp+380h+var_328], rdi
0x180015d3d  call    memset_0
0x180015d42  mov     r8d, 1389h; unsigned int
0x180015d48  lea     rcx, [rsp+380h+var_310]; this
0x180015d4d  mov     rdx, r14; HINSTANCE
0x180015d50  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180015d55  xor     r13d, r13d
0x180015d58  mov     ebx, eax
0x180015d5a  test    r15d, r15d
0x180015d5d  jns     short loc_180015DC2
0x180015d5f  mov     [rsp+380h+Arguments], r13; Arguments
0x180015d64  lea     rax, [rbp+280h+Buffer]
0x180015d68  mov     [rsp+380h+nSize], 104h; nSize
0x180015d70  xor     r9d, r9d; dwLanguageId
0x180015d73  movzx   r8d, r15w; dwMessageId
0x180015d77  xor     edx, edx; lpSource
0x180015d79  mov     ecx, 1000h; dwFlags
0x180015d7e  mov     [rsp+380h+lpBuffer], rax; lpBuffer
0x180015d83  call    cs:__imp_FormatMessageW
0x180015d89  test    eax, eax
0x180015d8b  jnz     short loc_180015DAB
0x180015d8d  call    cs:__imp_GetLastError
0x180015d93  mov     ebx, eax
0x180015d95  test    eax, eax
0x180015d97  jz      short loc_180015DA6
0x180015d99  jle     short loc_180015DAB
0x180015d9b  movzx   ebx, ax
0x180015d9e  or      ebx, 80070000h
0x180015da4  jmp     short loc_180015DAB
0x180015da6  mov     ebx, 80004005h
0x180015dab  test    ebx, ebx
0x180015dad  js      short loc_180015DC2
0x180015daf  lea     rdx, [rbp+280h+Buffer]; unsigned __int16 *
0x180015db3  lea     rcx, [rsp+380h+var_330]; this
0x180015db8  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x180015dbd  mov     rdi, [rsp+380h+var_328]
0x180015dc2  test    rsi, rsi
0x180015dc5  jz      short loc_180015E06
0x180015dc7  cmp     [rdi], r13w
0x180015dcb  jz      short loc_180015E01
0x180015dcd  mov     r8d, 139Ch; unsigned int
0x180015dd3  lea     rcx, [rsp+380h+var_320]; this
0x180015dd8  mov     rdx, r14; HINSTANCE
0x180015ddb  call    ?LoadStringFromRC@TString@NCoreLibrary@@QEAAJPEAUHINSTANCE__@@I@Z; NCoreLibrary::TString::LoadStringFromRC(HINSTANCE__ *,uint)
0x180015de0  mov     ebx, eax
0x180015de2  test    eax, eax
0x180015de4  js      loc_180015E78
0x180015dea  mov     rdx, [rsp+380h+var_318]; unsigned __int16 *
0x180015def  lea     rcx, [rsp+380h+var_340]; this
0x180015df4  mov     r9, rdi
0x180015df7  mov     r8, rsi
0x180015dfa  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180015dff  jmp     short loc_180015E19
0x180015e01  mov     rdx, rsi
0x180015e04  jmp     short loc_180015E0F
0x180015e06  cmp     [rdi], r13w
0x180015e0a  jz      short loc_180015E1B
0x180015e0c  mov     rdx, rdi; unsigned __int16 *
0x180015e0f  lea     rcx, [rsp+380h+var_340]; this
0x180015e14  call    ?Update@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Update(ushort const *)
0x180015e19  mov     ebx, eax
0x180015e1b  test    ebx, ebx
0x180015e1d  js      short loc_180015E78
0x180015e1f  mov     ebx, 0A0h
0x180015e24  lea     rcx, [rbp+280h+pTaskConfig]; void *
0x180015e28  mov     r8d, ebx; Size
0x180015e2b  xor     edx, edx; Val
0x180015e2d  call    memset_0
0x180015e32  mov     rax, [rsp+380h+var_308]
0x180015e37  lea     rcx, [rbp+280h+pTaskConfig]; pTaskConfig
0x180015e3b  mov     [rbp+280h+pTaskConfig.pszWindowTitle], rax
0x180015e3f  xor     r9d, r9d; pfVerificationFlagChecked
0x180015e42  mov     rax, [rsp+380h+var_338]
0x180015e47  xor     r8d, r8d; pnRadioButton
0x180015e4a  xor     edx, edx; pnButton
0x180015e4c  mov     [rbp+280h+pTaskConfig.pszContent], rax
0x180015e50  mov     [rbp+280h+pTaskConfig.cbSize], ebx
0x180015e53  mov     [rbp+280h+pTaskConfig.hwndParent], r12
0x180015e57  mov     [rbp+280h+pTaskConfig.hInstance], r14
0x180015e5b  mov     [rbp+280h+pTaskConfig.dwFlags], 8
0x180015e62  mov     [rbp+280h+pTaskConfig.dwCommonButtons], 1
0x180015e69  mov     qword ptr [rbp+280h+pTaskConfig.24h], 0FFFFh
0x180015e71  call    TaskDialogIndirect
0x180015e76  mov     ebx, eax
0x180015e78  lea     rcx, [rsp+380h+var_330]; this
0x180015e7d  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180015e82  lea     rcx, [rsp+380h+var_340]; this
0x180015e87  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180015e8c  lea     rcx, [rsp+380h+var_320]; this
0x180015e91  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180015e96  lea     rcx, [rsp+380h+var_310]; this
0x180015e9b  call    ??1TString@NCoreLibrary@@QEAA@XZ; NCoreLibrary::TString::~TString(void)
0x180015ea0  mov     eax, ebx
0x180015ea2  mov     rcx, [rbp+280h+var_50]
0x180015ea9  xor     rcx, rsp; StackCookie
0x180015eac  call    __security_check_cookie
0x180015eb1  add     rsp, 348h
0x180015eb8  pop     r15
0x180015eba  pop     r14
0x180015ebc  pop     r13
0x180015ebe  pop     r12
0x180015ec0  pop     rdi
0x180015ec1  pop     rsi
0x180015ec2  pop     rbx
0x180015ec3  pop     rbp
0x180015ec4  retn
```
