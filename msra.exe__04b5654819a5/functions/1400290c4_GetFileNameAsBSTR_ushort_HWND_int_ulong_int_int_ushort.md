# GetFileNameAsBSTR(ushort *,HWND__ *,int,ulong,int,int,ushort * *)

- ea: `0x1400290c4`
- end: `0x14002932d`
- name: `?GetFileNameAsBSTR@@YAJPEAGPEAUHWND__@@HKHHPEAPEAG@Z`
- size: `617`
- prototype: `__int64 __fastcall(unsigned __int16 *, HWND, int, unsigned int, int, UINT uID, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14001f624`
- `0x140032274`

## callees

- `0x140002463`
- `0x1400290c4`
- `0x140034ce4`
- `0x14004ad80`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x140029175`
- `KERNEL32!GetModuleHandleW` at `0x1400291e9`
- `KERNEL32!GetModuleHandleW` at `0x140029175`
- `KERNEL32!GetModuleHandleW` at `0x1400291e9`
- `USER32!LoadStringW` at `0x140029196`
- `USER32!LoadStringW` at `0x140029204`
- `USER32!LoadStringW` at `0x140029196`
- `USER32!LoadStringW` at `0x140029204`
- `OLEAUT32!__imp_SysAllocString` at `0x1400292d6`
- `OLEAUT32!__imp_SysAllocString` at `0x1400292d6`
- `COMDLG32!GetSaveFileNameW` at `0x1400292be`
- `COMDLG32!GetSaveFileNameW` at `0x1400292be`
- `COMDLG32!GetOpenFileNameW` at `0x1400292b0`
- `COMDLG32!GetOpenFileNameW` at `0x1400292b0`

## string_xrefs

- `0x140029156`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400291bb`: `base\diagnosis\ra\ui\commonfunc.cpp`

## pseudocode

```c
__int64 __fastcall GetFileNameAsBSTR(
        unsigned __int16 *a1,
        HWND a2,
        __int64 a3,
        DWORD a4,
        int a5,
        UINT uID,
        unsigned __int16 **a7)
{
  CEventLogger *v10; // rcx
  unsigned int v11; // ebx
  HMODULE ModuleHandleW; // rax
  CEventLogger *v13; // rcx
  unsigned int v14; // r9d
  HMODULE v15; // rax
  BOOL OpenFileNameW; // eax
  unsigned __int16 *v17; // rax
  CEventLogger *v18; // rcx
  tagOFNW v20; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR psz[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR Buffer[1024]; // [rsp+2E0h] [rbp+1E0h] BYREF

  memset_0(&v20, 0, sizeof(v20));
  memset_0(Buffer, 0, sizeof(Buffer));
  memset_0(psz, 0, 0x208u);
  if ( !a7 )
  {
    v11 = -2147467261;
    CEventLogger::LogError(
      v10,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x149Fu,
      L"GetFileNameAsBSTR",
      0x80004003);
    return v11;
  }
  ModuleHandleW = GetModuleHandleW(0);
  if ( !LoadStringW(ModuleHandleW, 0x27Eu, Buffer, 1024) )
  {
    v14 = 5288;
LABEL_6:
    CEventLogger::LogError(
      v13,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v14,
      L"GetFileNameAsBSTR",
      0);
    return (unsigned int)-2147467259;
  }
  if ( uID )
  {
    v15 = GetModuleHandleW(0);
    if ( !LoadStringW(v15, uID, psz, 260) )
    {
      v14 = 5299;
      goto LABEL_6;
    }
  }
  memset_0(&v20, 0, sizeof(v20));
  v20.lStructSize = 152;
  v20.lpstrFilter = Buffer;
  v20.hwndOwner = a2;
  v20.lpstrFile = psz;
  v20.hInstance = 0;
  v20.lpstrCustomFilter = 0;
  *(_QWORD *)&v20.nMaxCustFilter = 0;
  v20.nMaxFile = 260;
  v20.lpstrFileTitle = 0;
  v20.nMaxFileTitle = 260;
  *(_OWORD *)&v20.lpstrInitialDir = 0;
  v20.Flags = a4;
  *(_DWORD *)&v20.nFileOffset = 0;
  v20.lpstrDefExt = a1;
  memset(&v20.lCustData, 0, 24);
  if ( a5 )
    OpenFileNameW = GetOpenFileNameW(&v20);
  else
    OpenFileNameW = GetSaveFileNameW(&v20);
  if ( !OpenFileNameW )
    return (unsigned int)-2147467259;
  v17 = SysAllocString(psz);
  *a7 = v17;
  if ( v17 )
  {
    return 0;
  }
  else
  {
    v11 = -2147024882;
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x14E3u,
      L"GetFileNameAsBSTR",
      0x8007000E);
  }
  return v11;
}

```

## disassembly

```asm
0x1400290c4  mov     [rsp-8+arg_10], rbx
0x1400290c9  push    rbp
0x1400290ca  push    rsi
0x1400290cb  push    rdi
0x1400290cc  push    r14
0x1400290ce  push    r15
0x1400290d0  lea     rbp, [rsp-9F0h]
0x1400290d8  sub     rsp, 0AF0h
0x1400290df  mov     rax, cs:__security_cookie
0x1400290e6  xor     rax, rsp
0x1400290e9  mov     [rbp+0A10h+var_30], rax
0x1400290f0  mov     rdi, [rbp+0A10h+arg_30]
0x1400290f7  mov     r14, rdx
0x1400290fa  mov     rsi, rcx
0x1400290fd  xor     edx, edx; Val
0x1400290ff  lea     rcx, [rsp+0B10h+var_AE0]; void *
0x140029104  mov     r8d, 98h; Size
0x14002910a  mov     r15d, r9d
0x14002910d  call    memset_0
0x140029112  xor     edx, edx; Val
0x140029114  lea     rcx, [rbp+0A10h+Buffer]; void *
0x14002911b  mov     r8d, 800h; Size
0x140029121  call    memset_0
0x140029126  xor     edx, edx; Val
0x140029128  lea     rcx, [rbp+0A10h+psz]; void *
0x14002912c  mov     r8d, 208h; Size
0x140029132  call    memset_0
0x140029137  test    rdi, rdi
0x14002913a  jnz     short loc_140029173
0x14002913c  mov     ebx, 80004003h
0x140029141  mov     [rsp+0B10h+var_AE8], 80004003h; unsigned int
0x140029149  mov     r9d, 149Fh; unsigned int
0x14002914f  lea     rax, aGetfilenameasb; "GetFileNameAsBSTR"
0x140029156  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x14002915d  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x140029162  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140029169  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002916e  jmp     loc_140029304
0x140029173  xor     ecx, ecx; lpModuleName
0x140029175  call    cs:__imp_GetModuleHandleW
0x14002917c  nop     dword ptr [rax+rax+00h]
0x140029181  mov     r9d, 400h; cchBufferMax
0x140029187  lea     r8, [rbp+0A10h+Buffer]; lpBuffer
0x14002918e  mov     rcx, rax; hInstance
0x140029191  mov     edx, 27Eh; uID
0x140029196  call    cs:__imp_LoadStringW
0x14002919d  nop     dword ptr [rax+rax+00h]
0x1400291a2  test    eax, eax
0x1400291a4  jnz     short loc_1400291DD
0x1400291a6  mov     r9d, 14A8h; unsigned int
0x1400291ac  lea     rax, aGetfilenameasb; "GetFileNameAsBSTR"
0x1400291b3  mov     [rsp+0B10h+var_AE8], 0; unsigned int
0x1400291bb  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x1400291c2  mov     [rsp+0B10h+var_AF0], rax; unsigned __int16 *
0x1400291c7  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x1400291ce  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400291d3  mov     ebx, 80004005h
0x1400291d8  jmp     loc_140029304
0x1400291dd  mov     ebx, [rbp+0A10h+uID]
0x1400291e3  test    ebx, ebx
0x1400291e5  jz      short loc_14002921C
0x1400291e7  xor     ecx, ecx; lpModuleName
0x1400291e9  call    cs:__imp_GetModuleHandleW
0x1400291f0  nop     dword ptr [rax+rax+00h]
0x1400291f5  mov     r9d, 104h; cchBufferMax
0x1400291fb  lea     r8, [rbp+0A10h+psz]; lpBuffer
0x1400291ff  mov     rcx, rax; hInstance
0x140029202  mov     edx, ebx; uID
0x140029204  call    cs:__imp_LoadStringW
0x14002920b  nop     dword ptr [rax+rax+00h]
0x140029210  test    eax, eax
0x140029212  jnz     short loc_14002921C
0x140029214  mov     r9d, 14B3h
0x14002921a  jmp     short loc_1400291AC
0x14002921c  mov     ebx, 98h
0x140029221  lea     rcx, [rsp+0B10h+var_AE0]; void *
0x140029226  mov     r8d, ebx; Size
0x140029229  xor     edx, edx; Val
0x14002922b  call    memset_0
0x140029230  lea     rax, [rbp+0A10h+Buffer]
0x140029237  mov     [rsp+0B10h+var_AE0.lStructSize], ebx
0x14002923b  mov     [rsp+0B10h+var_AE0.lpstrFilter], rax
0x140029240  lea     rcx, [rsp+0B10h+var_AE0]; LPOPENFILENAMEW
0x140029245  lea     rax, [rbp+0A10h+psz]
0x140029249  mov     [rsp+0B10h+var_AE0.hwndOwner], r14
0x14002924e  mov     [rsp+0B10h+var_AE0.lpstrFile], rax
0x140029253  xorps   xmm0, xmm0
0x140029256  xor     eax, eax
0x140029258  mov     [rsp+0B10h+var_AE0.hInstance], 0
0x140029261  mov     [rsp+0B10h+var_AE0.lpstrCustomFilter], 0
0x14002926a  mov     qword ptr [rsp+0B10h+var_AE0.nMaxCustFilter], 0
0x140029273  mov     [rsp+0B10h+var_AE0.nMaxFile], 104h
0x14002927b  mov     [rsp+0B10h+var_AE0.lpstrFileTitle], 0
0x140029284  mov     [rsp+0B10h+var_AE0.nMaxFileTitle], 104h
0x14002928c  movdqa  xmmword ptr [rbp+0A10h+var_AE0.lpstrInitialDir], xmm0
0x140029291  mov     [rbp+0A10h+var_AE0.Flags], r15d
0x140029295  mov     dword ptr [rbp+0A10h+var_AE0.nFileOffset], eax
0x140029298  mov     [rbp+0A10h+var_AE0.lpstrDefExt], rsi
0x14002929c  mov     [rbp+0A10h+var_AE0.lCustData], rax
0x1400292a0  mov     [rbp+0A10h+var_AE0.lpfnHook], rax
0x1400292a4  mov     [rbp+0A10h+var_AE0.lpTemplateName], rax
0x1400292a8  cmp     [rbp+0A10h+arg_20], eax
0x1400292ae  jz      short loc_1400292BE
0x1400292b0  call    cs:__imp_GetOpenFileNameW
0x1400292b7  nop     dword ptr [rax+rax+00h]
0x1400292bc  jmp     short loc_1400292CA
0x1400292be  call    cs:__imp_GetSaveFileNameW
0x1400292c5  nop     dword ptr [rax+rax+00h]
0x1400292ca  test    eax, eax
0x1400292cc  jz      loc_1400291D3
0x1400292d2  lea     rcx, [rbp+0A10h+psz]; psz
0x1400292d6  call    cs:__imp_SysAllocString
0x1400292dd  nop     dword ptr [rax+rax+00h]
0x1400292e2  mov     [rdi], rax
0x1400292e5  test    rax, rax
0x1400292e8  jnz     short loc_140029302
0x1400292ea  mov     ebx, 8007000Eh
0x1400292ef  mov     [rsp+0B10h+var_AE8], 8007000Eh
0x1400292f7  mov     r9d, 14E3h
0x1400292fd  jmp     loc_14002914F
0x140029302  xor     ebx, ebx
0x140029304  mov     eax, ebx
0x140029306  mov     rcx, [rbp+0A10h+var_30]
0x14002930d  xor     rcx, rsp; StackCookie
0x140029310  call    __security_check_cookie
0x140029315  mov     rbx, [rsp+0B10h+arg_10]
0x14002931d  add     rsp, 0AF0h
0x140029324  pop     r15
0x140029326  pop     r14
0x140029328  pop     rdi
0x140029329  pop     rsi
0x14002932a  pop     rbp
0x14002932b  retn
```
