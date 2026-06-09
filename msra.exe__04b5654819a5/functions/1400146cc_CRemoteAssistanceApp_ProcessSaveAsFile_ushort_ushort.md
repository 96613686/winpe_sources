# CRemoteAssistanceApp::ProcessSaveAsFile(ushort *,ushort *)

- ea: `0x1400146cc`
- end: `0x140014a3d`
- name: `?ProcessSaveAsFile@CRemoteAssistanceApp@@QEAAJPEAG0@Z`
- size: `881`
- prototype: `int(CRemoteAssistanceApp *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting`

## callers

- `0x140012794`

## callees

- `0x140002463`
- `0x14000e8b8`
- `0x1400146cc`
- `0x140025c54`
- `0x1400269f0`
- `0x140027ce0`
- `0x1400289a8`
- `0x14002a6bc`
- `0x14002b178`
- `0x14002c0a4`
- `0x140034ce4`
- `0x140040220`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x140014859`
- `KERNEL32!GetFullPathNameW` at `0x140014859`
- `OLEAUT32!__imp_SysAllocString` at `0x14001479f`
- `OLEAUT32!__imp_SysAllocString` at `0x1400147d3`
- `OLEAUT32!__imp_SysAllocString` at `0x140014911`
- `OLEAUT32!__imp_SysAllocString` at `0x14001479f`
- `OLEAUT32!__imp_SysAllocString` at `0x1400147d3`
- `OLEAUT32!__imp_SysAllocString` at `0x140014911`
- `OLEAUT32!__imp_SysFreeString` at `0x140014900`
- `OLEAUT32!__imp_SysFreeString` at `0x1400149f4`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a08`
- `OLEAUT32!__imp_SysFreeString` at `0x140014900`
- `OLEAUT32!__imp_SysFreeString` at `0x1400149f4`
- `OLEAUT32!__imp_SysFreeString` at `0x140014a08`
- `OLEAUT32!__imp_SysStringLen` at `0x140014741`
- `OLEAUT32!__imp_SysStringLen` at `0x140014741`

## pseudocode

```c
__int64 __fastcall CRemoteAssistanceApp::ProcessSaveAsFile(
        CRATicket **this,
        unsigned __int16 *a2,
        unsigned __int16 *a3)
{
  OLECHAR *v6; // rdi
  CRemoteAssistanceApp *v7; // rcx
  unsigned int v8; // ebx
  signed int Password; // eax
  CEventLogger *v10; // rcx
  unsigned __int16 *v11; // rsi
  CEventLogger *v12; // rcx
  CEventLogger *v13; // rcx
  signed int v14; // eax
  CEventLogger *v15; // rcx
  DWORD FullPathNameW; // eax
  CEventLogger *v17; // rcx
  unsigned __int16 v18; // dx
  unsigned int v19; // ecx
  CEventLogger *v20; // rcx
  int v21; // r8d
  HWND v22; // r9
  int v23; // r8d
  signed int v24; // eax
  CEventLogger *v25; // rcx
  struct CReadWriteLock *v26; // r8
  int pnButton; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpFileName; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[264]; // [rsp+40h] [rbp-C0h] BYREF

  lpFileName = 0;
  v6 = 0;
  memset_0(Buffer, 0, 0x208u);
  v29 = 0;
  if ( !CRemoteAssistanceApp::CanUserBeNovice(v7, 1, 1, 0) )
    return (unsigned int)-2147467259;
  if ( SysStringLen(a3) )
  {
    v11 = SysAllocString(a3);
    if ( !v11 )
    {
      v8 = -2147024882;
      CEventLogger::LogError(
        v13,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x673u,
        L"CRemoteAssistanceApp::ProcessSaveAsFile",
        0x8007000E);
      goto LABEL_28;
    }
  }
  else
  {
    Password = CreatePassword((CEventLogger *)0xC, (unsigned __int16 **)&lpFileName);
    v8 = Password;
    if ( Password < 0 )
    {
      CEventLogger::LogError(
        v10,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x670u,
        L"CRemoteAssistanceApp::ProcessSaveAsFile",
        Password);
      v11 = (unsigned __int16 *)lpFileName;
LABEL_28:
      v18 = 650;
      v19 = 531;
      goto LABEL_17;
    }
    v11 = (unsigned __int16 *)lpFileName;
  }
  lpFileName = SysAllocString(a2);
  v6 = (OLECHAR *)lpFileName;
  if ( !lpFileName )
  {
    v8 = -2147024882;
    CEventLogger::LogError(
      v12,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x67Au,
      L"CRemoteAssistanceApp::ProcessSaveAsFile",
      0x8007000E);
    goto LABEL_28;
  }
  v14 = AddFileExtension((unsigned __int16 **)&lpFileName);
  v8 = v14;
  if ( v14 < 0 )
  {
    CEventLogger::LogError(
      v15,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x67Bu,
      L"CRemoteAssistanceApp::ProcessSaveAsFile",
      v14);
    v6 = (OLECHAR *)lpFileName;
    goto LABEL_28;
  }
  v6 = (OLECHAR *)lpFileName;
  FullPathNameW = GetFullPathNameW(lpFileName, 0x104u, Buffer, 0);
  if ( !FullPathNameW )
  {
    CEventLogger::LogError(
      v17,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\app.cpp",
      0x683u,
      L"CRemoteAssistanceApp::ProcessSaveAsFile",
      0);
    v8 = -2147467259;
    goto LABEL_28;
  }
  if ( FullPathNameW <= 0x104 )
  {
    if ( v6 )
      SysFreeString(v6);
    v6 = SysAllocString(Buffer);
    if ( v6 )
    {
      IsValidPassword(v11, &v29, v21, v22);
      if ( v29 || (unsigned int)FileExists(v6) && (v29 = 0, QueryUser(536, 643, v23, 0, &v29), v29 != 6) )
      {
        v8 = -2147467259;
        goto LABEL_30;
      }
      v24 = CRATicket::put_UserPassword(this[104], v11);
      v8 = v24;
      if ( v24 >= 0 )
      {
        v8 = EscalateAsFile(v6, this[104], v26, 0, pnButton);
        goto LABEL_30;
      }
      CEventLogger::LogError(
        v25,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x6BAu,
        L"CRemoteAssistanceApp::ProcessSaveAsFile",
        v24);
    }
    else
    {
      v8 = -2147024882;
      CEventLogger::LogError(
        v20,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\app.cpp",
        0x692u,
        L"CRemoteAssistanceApp::ProcessSaveAsFile",
        0x8007000E);
    }
    goto LABEL_28;
  }
  v8 = -2147467259;
  CEventLogger::LogError(
    v17,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\app.cpp",
    0x687u,
    L"CRemoteAssistanceApp::ProcessSaveAsFile",
    0);
  v18 = 665;
  v19 = 570;
LABEL_17:
  ShowErrorMessage(v19, v18, 0, 0, (unsigned __int16 *)0xFFFE, 0);
LABEL_30:
  if ( v6 )
    SysFreeString(v6);
  if ( v11 )
    SysFreeString(v11);
  return v8;
}

```

## disassembly

```asm
0x1400146cc  mov     [rsp-8+arg_18], rbx
0x1400146d1  push    rbp
0x1400146d2  push    rsi
0x1400146d3  push    rdi
0x1400146d4  push    r14
0x1400146d6  push    r15
0x1400146d8  lea     rbp, [rsp-160h]
0x1400146e0  sub     rsp, 260h
0x1400146e7  mov     rax, cs:__security_cookie
0x1400146ee  xor     rax, rsp
0x1400146f1  mov     [rbp+180h+var_30], rax
0x1400146f8  mov     rbx, r8
0x1400146fb  mov     [rsp+280h+lpFileName], 0
0x140014704  mov     r15, rdx
0x140014707  mov     r14, rcx
0x14001470a  xor     edx, edx; Val
0x14001470c  lea     rcx, [rsp+280h+Buffer]; void *
0x140014711  mov     r8d, 208h; Size
0x140014717  xor     edi, edi
0x140014719  call    memset_0
0x14001471e  lea     edx, [rdi+1]; int
0x140014721  mov     [rsp+280h+var_250], edi
0x140014725  mov     r8d, edx; int
0x140014728  xor     r9d, r9d; HWND
0x14001472b  call    ?CanUserBeNovice@CRemoteAssistanceApp@@QEAAHHHPEAUHWND__@@@Z; CRemoteAssistanceApp::CanUserBeNovice(int,int,HWND__ *)
0x140014730  test    eax, eax
0x140014732  jnz     short loc_14001473E
0x140014734  mov     ebx, 80004005h
0x140014739  jmp     loc_140014A14
0x14001473e  mov     rcx, rbx; pbstr
0x140014741  call    cs:__imp_SysStringLen
0x140014748  nop     dword ptr [rax+rax+00h]
0x14001474d  test    eax, eax
0x14001474f  jnz     short loc_1400147D0
0x140014751  lea     rdx, [rsp+280h+lpFileName]; unsigned __int16 **
0x140014756  lea     ecx, [rax+0Ch]; unsigned int
0x140014759  call    ?CreatePassword@@YAJIPEAPEAG@Z; CreatePassword(uint,ushort * *)
0x14001475e  mov     ebx, eax
0x140014760  test    eax, eax
0x140014762  jns     short loc_140014797
0x140014764  mov     [rsp+280h+var_258], eax; unsigned int
0x140014768  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14001476f  lea     rax, aCremoteassista_9; "CRemoteAssistanceApp::ProcessSaveAsFile"
0x140014776  mov     r9d, 670h; unsigned int
0x14001477c  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140014783  mov     [rsp+280h+pnButton], rax; unsigned __int16 *
0x140014788  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14001478d  mov     rsi, [rsp+280h+lpFileName]
0x140014792  jmp     loc_1400149CB
0x140014797  mov     rsi, [rsp+280h+lpFileName]
0x14001479c  mov     rcx, r15; psz
0x14001479f  call    cs:__imp_SysAllocString
0x1400147a6  nop     dword ptr [rax+rax+00h]
0x1400147ab  mov     [rsp+280h+lpFileName], rax
0x1400147b0  mov     rdi, rax
0x1400147b3  test    rax, rax
0x1400147b6  jnz     short loc_1400147FF
0x1400147b8  mov     ebx, 8007000Eh
0x1400147bd  mov     [rsp+280h+var_258], 8007000Eh
0x1400147c5  mov     r9d, 67Ah
0x1400147cb  jmp     loc_1400149AC
0x1400147d0  mov     rcx, rbx; psz
0x1400147d3  call    cs:__imp_SysAllocString
0x1400147da  nop     dword ptr [rax+rax+00h]
0x1400147df  mov     rsi, rax
0x1400147e2  test    rax, rax
0x1400147e5  jnz     short loc_14001479C
0x1400147e7  mov     ebx, 8007000Eh
0x1400147ec  mov     [rsp+280h+var_258], 8007000Eh
0x1400147f4  mov     r9d, 673h
0x1400147fa  jmp     loc_1400149AC
0x1400147ff  lea     rcx, [rsp+280h+lpFileName]; unsigned __int16 **
0x140014804  call    ?AddFileExtension@@YAJPEAPEAG@Z; AddFileExtension(ushort * *)
0x140014809  mov     ebx, eax
0x14001480b  test    eax, eax
0x14001480d  jns     short loc_140014842
0x14001480f  mov     [rsp+280h+var_258], eax; unsigned int
0x140014813  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x14001481a  lea     rax, aCremoteassista_9; "CRemoteAssistanceApp::ProcessSaveAsFile"
0x140014821  mov     r9d, 67Bh; unsigned int
0x140014827  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x14001482e  mov     [rsp+280h+pnButton], rax; unsigned __int16 *
0x140014833  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014838  mov     rdi, [rsp+280h+lpFileName]
0x14001483d  jmp     loc_1400149CB
0x140014842  mov     rdi, [rsp+280h+lpFileName]
0x140014847  lea     r8, [rsp+280h+Buffer]; lpBuffer
0x14001484c  mov     ebx, 104h
0x140014851  mov     rcx, rdi; lpFileName
0x140014854  mov     edx, ebx; nBufferLength
0x140014856  xor     r9d, r9d; lpFilePart
0x140014859  call    cs:__imp_GetFullPathNameW
0x140014860  nop     dword ptr [rax+rax+00h]
0x140014865  test    eax, eax
0x140014867  jnz     short loc_14001489C
0x140014869  mov     [rsp+280h+var_258], eax; unsigned int
0x14001486d  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x140014874  lea     rax, aCremoteassista_9; "CRemoteAssistanceApp::ProcessSaveAsFile"
0x14001487b  mov     r9d, 683h; unsigned int
0x140014881  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140014888  mov     [rsp+280h+pnButton], rax; unsigned __int16 *
0x14001488d  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140014892  mov     ebx, 80004005h
0x140014897  jmp     loc_1400149CB
0x14001489c  cmp     eax, ebx
0x14001489e  jbe     short loc_1400148F8
0x1400148a0  lea     rax, aCremoteassista_9; "CRemoteAssistanceApp::ProcessSaveAsFile"
0x1400148a7  mov     [rsp+280h+var_258], 0; unsigned int
0x1400148af  mov     r9d, 687h; unsigned int
0x1400148b5  mov     [rsp+280h+pnButton], rax; unsigned __int16 *
0x1400148ba  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x1400148c1  mov     ebx, 80004005h
0x1400148c6  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400148cd  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400148d2  mov     edx, 299h; int
0x1400148d7  lea     ecx, [rdx-5Fh]; int
0x1400148da  xor     r9d, r9d; int
0x1400148dd  xor     r8d, r8d; HWND
0x1400148e0  mov     [rsp+280h+var_258], r9d; int
0x1400148e5  mov     [rsp+280h+pnButton], 0FFFEh; unsigned __int16 *
0x1400148ee  call    ?ShowErrorMessage@@YAJHHPEAUHWND__@@JPEBGH@Z; ShowErrorMessage(int,int,HWND__ *,long,ushort const *,int)
0x1400148f3  jmp     loc_1400149EC
0x1400148f8  test    rdi, rdi
0x1400148fb  jz      short loc_14001490C
0x1400148fd  mov     rcx, rdi; bstrString
0x140014900  call    cs:__imp_SysFreeString
0x140014907  nop     dword ptr [rax+rax+00h]
0x14001490c  lea     rcx, [rsp+280h+Buffer]; psz
0x140014911  call    cs:__imp_SysAllocString
0x140014918  nop     dword ptr [rax+rax+00h]
0x14001491d  mov     rdi, rax
0x140014920  test    rax, rax
0x140014923  jnz     short loc_14001493A
0x140014925  mov     ebx, 8007000Eh
0x14001492a  mov     [rsp+280h+var_258], 8007000Eh
0x140014932  mov     r9d, 692h
0x140014938  jmp     short loc_1400149AC
0x14001493a  lea     rdx, [rsp+280h+var_250]; int *
0x14001493f  mov     rcx, rsi; unsigned __int16 *
0x140014942  call    ?IsValidPassword@@YAJPEAGPEAHHPEAUHWND__@@@Z; IsValidPassword(ushort *,int *,int,HWND__ *)
0x140014947  cmp     [rsp+280h+var_250], 0
0x14001494c  jz      short loc_140014958
0x14001494e  mov     ebx, 80004005h
0x140014953  jmp     loc_1400149EC
0x140014958  mov     rcx, rdi; lpFileName
0x14001495b  call    ?FileExists@@YAHPEAG@Z; FileExists(ushort *)
0x140014960  test    eax, eax
0x140014962  jz      short loc_14001498D
0x140014964  mov     edx, 283h; int
0x140014969  mov     [rsp+280h+var_250], 0
0x140014971  lea     rax, [rsp+280h+var_250]
0x140014976  xor     r9d, r9d; HWND
0x140014979  mov     [rsp+280h+pnButton], rax; int
0x14001497e  lea     ecx, [rdx-6Bh]; int
0x140014981  call    ?QueryUser@@YAJHHHPEAUHWND__@@PEAH@Z; QueryUser(int,int,int,HWND__ *,int *)
0x140014986  cmp     [rsp+280h+var_250], 6
0x14001498b  jnz     short loc_14001494E
0x14001498d  mov     rcx, [r14+340h]; this
0x140014994  mov     rdx, rsi; unsigned __int16 *
0x140014997  call    ?put_UserPassword@CRATicket@@QEAAJPEAG@Z; CRATicket::put_UserPassword(ushort *)
0x14001499c  mov     ebx, eax
0x14001499e  test    eax, eax
0x1400149a0  jns     short loc_1400149D8
0x1400149a2  mov     [rsp+280h+var_258], eax; unsigned int
0x1400149a6  mov     r9d, 6BAh; unsigned int
0x1400149ac  lea     rax, aCremoteassista_9; "CRemoteAssistanceApp::ProcessSaveAsFile"
0x1400149b3  lea     r8, aBaseDiagnosisR_14; "base\\diagnosis\\ra\\ui\\app.cpp"
0x1400149ba  mov     [rsp+280h+pnButton], rax; unsigned __int16 *
0x1400149bf  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400149c6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400149cb  mov     edx, 28Ah
0x1400149d0  lea     ecx, [rdx-77h]
0x1400149d3  jmp     loc_1400148DA
0x1400149d8  mov     rdx, [r14+340h]; this
0x1400149df  xor     r9d, r9d; HWND
0x1400149e2  mov     rcx, rdi; unsigned __int16 *
0x1400149e5  call    ?EscalateAsFile@@YAJPEAGPEAVCRATicket@@PEAVCReadWriteLock@@PEAUHWND__@@H@Z; EscalateAsFile(ushort *,CRATicket *,CReadWriteLock *,HWND__ *,int)
0x1400149ea  mov     ebx, eax
0x1400149ec  test    rdi, rdi
0x1400149ef  jz      short loc_140014A00
0x1400149f1  mov     rcx, rdi; bstrString
0x1400149f4  call    cs:__imp_SysFreeString
0x1400149fb  nop     dword ptr [rax+rax+00h]
0x140014a00  test    rsi, rsi
0x140014a03  jz      short loc_140014A14
0x140014a05  mov     rcx, rsi; bstrString
0x140014a08  call    cs:__imp_SysFreeString
0x140014a0f  nop     dword ptr [rax+rax+00h]
0x140014a14  mov     eax, ebx
0x140014a16  mov     rcx, [rbp+180h+var_30]
0x140014a1d  xor     rcx, rsp; StackCookie
0x140014a20  call    __security_check_cookie
0x140014a25  mov     rbx, [rsp+280h+arg_18]
0x140014a2d  add     rsp, 260h
0x140014a34  pop     r15
0x140014a36  pop     r14
0x140014a38  pop     rdi
0x140014a39  pop     rsi
0x140014a3a  pop     rbp
0x140014a3b  retn
```
