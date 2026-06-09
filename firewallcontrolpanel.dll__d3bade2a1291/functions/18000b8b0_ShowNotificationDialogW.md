# ShowNotificationDialogW

- ea: `0x18000b8b0`
- end: `0x18000bdbb`
- name: `ShowNotificationDialogW`
- size: `1291`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000a53c`
- `0x18000b8b0`
- `0x1800111cc`
- `0x18001182c`
- `0x18001557c`
- `0x18002dcd0`
- `0x180030ea0`

## import_xrefs

- `msvcrt!_wtol` at `0x18000ba42`
- `msvcrt!_wtol` at `0x18000bad1`
- `msvcrt!_wtol` at `0x18000bb26`
- `msvcrt!_wtol` at `0x18000bb7b`
- `msvcrt!_wtol` at `0x18000bbcc`
- `msvcrt!_wtol` at `0x18000bc1a`
- `msvcrt!_wtol` at `0x18000ba42`
- `msvcrt!_wtol` at `0x18000bad1`
- `msvcrt!_wtol` at `0x18000bb26`
- `msvcrt!_wtol` at `0x18000bb7b`
- `msvcrt!_wtol` at `0x18000bbcc`
- `msvcrt!_wtol` at `0x18000bc1a`
- `ntdll!RtlQueryElevationFlags` at `0x18000bc44`
- `ntdll!RtlQueryElevationFlags` at `0x18000bc44`
- `ntdll!EtwEventWrite` at `0x18000b8f9`
- `ntdll!EtwEventWrite` at `0x18000b8f9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b9b0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b9e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ba20`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ba74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000baaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bb04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bb59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bbae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bbfc`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b9b0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000b9e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ba20`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000ba74`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000baaf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bb04`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bb59`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bbae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000bbfc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bd89`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b906`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000b906`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bd8f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000bd8f`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000b927`
- `api-ms-win-shcore-obsolete-l1-1-0!CommandLineToArgvW` at `0x18000b927`
- `USER32!GetActiveWindow` at `0x18000bd6b`
- `USER32!GetActiveWindow` at `0x18000bd6b`
- `USER32!LockSetForegroundWindow` at `0x18000bc9b`
- `USER32!LockSetForegroundWindow` at `0x18000bc9b`

## string_xrefs

- `0x18000b9a2`: `configure`

## pseudocode

```c
__int64 __fastcall ShowNotificationDialogW(__int64 a1, __int64 a2, const WCHAR *a3)
{
  HRESULT v4; // r15d
  LPWSTR *v5; // rdi
  const unsigned __int16 *v6; // r12
  int v7; // r14d
  int v8; // r13d
  DWORD dwSize; // esi
  int v10; // ebx
  LPWSTR v11; // rcx
  int v12; // ebx
  HWND ActiveWindow; // rax
  INITCOMMONCONTROLSEX picce; // [rsp+60h] [rbp-A0h] BYREF
  int pNumArgs; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v17; // [rsp+6Ch] [rbp-94h]
  unsigned int v18; // [rsp+70h] [rbp-90h]
  unsigned int v19; // [rsp+74h] [rbp-8Ch]
  unsigned int v20; // [rsp+78h] [rbp-88h]
  unsigned int v21; // [rsp+7Ch] [rbp-84h]
  unsigned int v22; // [rsp+80h] [rbp-80h]
  _QWORD v23[7]; // [rsp+90h] [rbp-70h] BYREF
  int v24; // [rsp+C8h] [rbp-38h]
  __int128 v25; // [rsp+D0h] [rbp-30h]
  __int64 v26; // [rsp+E0h] [rbp-20h]
  int v27; // [rsp+E8h] [rbp-18h]
  __int64 v28; // [rsp+F0h] [rbp-10h]
  __int16 v29; // [rsp+F8h] [rbp-8h]
  __int16 v30; // [rsp+300h] [rbp+200h]
  __int64 v31; // [rsp+710h] [rbp+610h]
  int v32; // [rsp+718h] [rbp+618h]
  __int128 v33; // [rsp+71Ch] [rbp+61Ch]
  __int64 v34; // [rsp+734h] [rbp+634h]
  __int64 v35; // [rsp+73Ch] [rbp+63Ch]
  int v36; // [rsp+744h] [rbp+644h]
  __int64 v37; // [rsp+748h] [rbp+648h]
  __int64 v38; // [rsp+750h] [rbp+650h]
  __int64 v39; // [rsp+758h] [rbp+658h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, QUInitialize_Start, 0, 0);
  v4 = CoInitializeEx(0, 2u);
  if ( v4 < 0 )
    return (unsigned int)v4;
  pNumArgs = 0;
  v5 = CommandLineToArgvW(a3, &pNumArgs);
  if ( !v5 )
    goto LABEL_45;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  dwSize = 0;
  v10 = 0;
  picce.dwSize = 0;
  v22 = 0;
  v21 = 0;
  v20 = 0;
  v19 = 0;
  v18 = 0;
  v17 = 0;
  if ( pNumArgs <= 0 )
  {
LABEL_35:
    picce.dwSize = 0;
    RtlQueryElevationFlags(&picce);
    if ( (picce.dwSize & 1) != 0 )
      v7 = 1;
    goto LABEL_37;
  }
  do
  {
    v11 = v5[v10];
    if ( ((*v11 - 45) & 0xFFFD) != 0 )
    {
      v6 = v5[v10];
    }
    else if ( CompareStringW(0x7Fu, 1u, L"configure", -1, v11 + 1, -1) == 2 )
    {
      v7 = 1;
    }
    else if ( CompareStringW(0x7Fu, 1u, L"hint", -1, v5[v10] + 1, -1) == 2 )
    {
      v8 = 1;
    }
    else if ( CompareStringW(0x7Fu, 1u, L"OnProfiles", -1, v5[v10] + 1, -1) == 2 )
    {
      if ( v10 < pNumArgs - 1 )
        v22 = _wtol(v5[++v10]);
    }
    else
    {
      if ( CompareStringW(0x7Fu, 1u, L"dynedge", -1, v5[v10] + 1, -1) == 2 )
      {
        dwSize = 1;
        picce.dwSize = 1;
        goto LABEL_33;
      }
      if ( CompareStringW(0x7Fu, 1u, L"ETOnly", -1, v5[v10] + 1, -1) == 2 )
      {
        if ( v10 < pNumArgs - 1 )
          v21 = _wtol(v5[++v10]);
      }
      else if ( CompareStringW(0x7Fu, 1u, L"OtherBlocked", -1, v5[v10] + 1, -1) == 2 )
      {
        if ( v10 < pNumArgs - 1 )
          v20 = _wtol(v5[++v10]);
      }
      else if ( CompareStringW(0x7Fu, 1u, L"OtherAllowed", -1, v5[v10] + 1, -1) == 2 )
      {
        if ( v10 < pNumArgs - 1 )
          v19 = _wtol(v5[++v10]);
      }
      else if ( CompareStringW(0x7Fu, 1u, L"OtherEdgeAllowed", -1, v5[v10] + 1, -1) == 2 )
      {
        if ( v10 < pNumArgs - 1 )
          v18 = _wtol(v5[++v10]);
      }
      else if ( CompareStringW(0x7Fu, 1u, L"NewBlocked", -1, v5[v10] + 1, -1) == 2 && v10 < pNumArgs - 1 )
      {
        v17 = _wtol(v5[++v10]);
      }
    }
    dwSize = picce.dwSize;
LABEL_33:
    ++v10;
  }
  while ( v10 < pNumArgs );
  if ( !v7 )
    goto LABEL_35;
LABEL_37:
  if ( v6 )
  {
    picce.dwSize = 8;
    picce.dwICC = 49152;
    if ( InitCommonControlsEx(&picce) )
    {
      v12 = IsDxgExclusiveModeActive();
      if ( v12 )
        LockSetForegroundWindow(1u);
      v23[0] = &CNotificationDialog::`vftable';
      v23[1] = 0;
      v23[5] = 0;
      v23[6] = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      v27 = 0;
      v28 = 0;
      v31 = 0;
      v32 = 0;
      v33 = 0;
      v34 = 0;
      v35 = 0;
      v36 = 0;
      v37 = 0;
      v38 = 0;
      v39 = 0;
      v29 = 0;
      v30 = 0;
      v4 = CNotificationDialog::Initialize(
             (CNotificationDialog *)v23,
             v6,
             v22,
             v7,
             v8,
             v12,
             dwSize,
             v21,
             v20,
             v19,
             v18,
             v17);
      if ( v4 >= 0 )
      {
        ActiveWindow = GetActiveWindow();
        ATL::CDialogImpl<CBaseDlg,ATL::CWindow>::DoModal((__int64)v23, ActiveWindow);
      }
      CNotificationDialog::~CNotificationDialog((CNotificationDialog *)v23);
    }
  }
  LocalFree(v5);
LABEL_45:
  CoUninitialize();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000b8b0  push    rbp
0x18000b8b2  push    rbx
0x18000b8b3  push    rsi
0x18000b8b4  push    rdi
0x18000b8b5  push    r12
0x18000b8b7  push    r13
0x18000b8b9  push    r14
0x18000b8bb  push    r15
0x18000b8bd  lea     rbp, [rsp-678h]
0x18000b8c5  sub     rsp, 778h
0x18000b8cc  mov     rax, cs:__security_cookie
0x18000b8d3  xor     rax, rsp
0x18000b8d6  mov     [rbp+6B0h+var_50], rax
0x18000b8dd  mov     rcx, cs:g_Provider
0x18000b8e4  mov     rbx, r8
0x18000b8e7  test    rcx, rcx
0x18000b8ea  jz      short loc_18000B8FF
0x18000b8ec  xor     r9d, r9d
0x18000b8ef  lea     rdx, QUInitialize_Start
0x18000b8f6  xor     r8d, r8d
0x18000b8f9  call    cs:__imp_EtwEventWrite
0x18000b8ff  mov     edx, 2; dwCoInit
0x18000b904  xor     ecx, ecx; pvReserved
0x18000b906  call    cs:__imp_CoInitializeEx
0x18000b90c  mov     r15d, eax
0x18000b90f  test    eax, eax
0x18000b911  js      loc_18000BD95
0x18000b917  lea     rdx, [rsp+7B0h+pNumArgs]; pNumArgs
0x18000b91c  mov     [rsp+7B0h+pNumArgs], 0
0x18000b924  mov     rcx, rbx; lpCmdLine
0x18000b927  call    cs:__imp_CommandLineToArgvW
0x18000b92d  mov     rdi, rax
0x18000b930  xor     eax, eax
0x18000b932  test    rdi, rdi
0x18000b935  jz      loc_18000BD8F
0x18000b93b  mov     r12d, eax
0x18000b93e  mov     r14d, eax
0x18000b941  mov     r13d, eax
0x18000b944  mov     esi, eax
0x18000b946  mov     ebx, eax
0x18000b948  mov     [rsp+7B0h+picce.dwSize], eax
0x18000b94c  mov     [rbp+6B0h+var_730], eax
0x18000b94f  mov     [rsp+7B0h+var_734], eax
0x18000b953  mov     [rsp+7B0h+var_738], eax
0x18000b957  mov     [rsp+7B0h+var_73C], eax
0x18000b95b  mov     [rsp+7B0h+var_740], eax
0x18000b95f  mov     [rsp+7B0h+var_744], eax
0x18000b963  cmp     [rsp+7B0h+pNumArgs], eax
0x18000b967  jle     loc_18000BC3B
0x18000b96d  movsxd  rsi, ebx
0x18000b970  mov     edx, 0FFFDh
0x18000b975  mov     rcx, [rdi+rsi*8]
0x18000b979  movzx   eax, word ptr [rcx]
0x18000b97c  sub     ax, 2Dh ; '-'
0x18000b980  test    dx, ax
0x18000b983  jz      short loc_18000B98D
0x18000b985  mov     r12, rcx
0x18000b988  jmp     loc_18000BC24
0x18000b98d  lea     rax, [rcx+2]
0x18000b991  mov     [rsp+7B0h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000b999  or      r9d, 0FFFFFFFFh; cchCount1
0x18000b99d  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000b9a2  lea     r8, String1; "configure"
0x18000b9a9  lea     edx, [r9+2]; dwCmpFlags
0x18000b9ad  lea     ecx, [rdx+7Eh]; Locale
0x18000b9b0  call    cs:__imp_CompareStringW
0x18000b9b6  cmp     eax, 2
0x18000b9b9  jnz     short loc_18000B9C4
0x18000b9bb  lea     r14d, [rax-1]
0x18000b9bf  jmp     loc_18000BC24
0x18000b9c4  mov     rax, [rdi+rsi*8]
0x18000b9c8  lea     r8, aHint; "hint"
0x18000b9cf  or      r9d, 0FFFFFFFFh; cchCount1
0x18000b9d3  add     rax, 2
0x18000b9d7  mov     [rsp+7B0h+cchCount2], r9d; cchCount2
0x18000b9dc  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000b9e1  lea     edx, [r9+2]; dwCmpFlags
0x18000b9e5  lea     ecx, [rdx+7Eh]; Locale
0x18000b9e8  call    cs:__imp_CompareStringW
0x18000b9ee  cmp     eax, 2
0x18000b9f1  jnz     short loc_18000B9FC
0x18000b9f3  lea     r13d, [rax-1]
0x18000b9f7  jmp     loc_18000BC24
0x18000b9fc  mov     rax, [rdi+rsi*8]
0x18000ba00  lea     r8, aOnprofiles; "OnProfiles"
0x18000ba07  or      ecx, 0FFFFFFFFh
0x18000ba0a  add     rax, 2
0x18000ba0e  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000ba12  mov     r9d, ecx; cchCount1
0x18000ba15  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000ba1a  lea     edx, [rcx+2]; dwCmpFlags
0x18000ba1d  lea     ecx, [rdx+7Eh]; Locale
0x18000ba20  call    cs:__imp_CompareStringW
0x18000ba26  cmp     eax, 2
0x18000ba29  jnz     short loc_18000BA50
0x18000ba2b  mov     eax, [rsp+7B0h+pNumArgs]
0x18000ba2f  dec     eax
0x18000ba31  cmp     ebx, eax
0x18000ba33  jge     loc_18000BC24
0x18000ba39  inc     ebx
0x18000ba3b  movsxd  rcx, ebx
0x18000ba3e  mov     rcx, [rdi+rcx*8]; String
0x18000ba42  call    cs:__imp__wtol
0x18000ba48  mov     [rbp+6B0h+var_730], eax
0x18000ba4b  jmp     loc_18000BC24
0x18000ba50  mov     rax, [rdi+rsi*8]
0x18000ba54  lea     r8, aDynedge; "dynedge"
0x18000ba5b  or      ecx, 0FFFFFFFFh
0x18000ba5e  add     rax, 2
0x18000ba62  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000ba66  mov     r9d, ecx; cchCount1
0x18000ba69  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000ba6e  lea     edx, [rcx+2]; dwCmpFlags
0x18000ba71  lea     ecx, [rdx+7Eh]; Locale
0x18000ba74  call    cs:__imp_CompareStringW
0x18000ba7a  cmp     eax, 2
0x18000ba7d  jnz     short loc_18000BA8B
0x18000ba7f  lea     esi, [rax-1]
0x18000ba82  mov     [rsp+7B0h+picce.dwSize], esi
0x18000ba86  jmp     loc_18000BC28
0x18000ba8b  mov     rax, [rdi+rsi*8]
0x18000ba8f  lea     r8, aEtonly; "ETOnly"
0x18000ba96  or      ecx, 0FFFFFFFFh
0x18000ba99  add     rax, 2
0x18000ba9d  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000baa1  mov     r9d, ecx; cchCount1
0x18000baa4  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000baa9  lea     edx, [rcx+2]; dwCmpFlags
0x18000baac  lea     ecx, [rdx+7Eh]; Locale
0x18000baaf  call    cs:__imp_CompareStringW
0x18000bab5  cmp     eax, 2
0x18000bab8  jnz     short loc_18000BAE0
0x18000baba  mov     eax, [rsp+7B0h+pNumArgs]
0x18000babe  dec     eax
0x18000bac0  cmp     ebx, eax
0x18000bac2  jge     loc_18000BC24
0x18000bac8  inc     ebx
0x18000baca  movsxd  rcx, ebx
0x18000bacd  mov     rcx, [rdi+rcx*8]; String
0x18000bad1  call    cs:__imp__wtol
0x18000bad7  mov     [rsp+7B0h+var_734], eax
0x18000badb  jmp     loc_18000BC24
0x18000bae0  mov     rax, [rdi+rsi*8]
0x18000bae4  lea     r8, aOtherblocked; "OtherBlocked"
0x18000baeb  or      ecx, 0FFFFFFFFh
0x18000baee  add     rax, 2
0x18000baf2  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000baf6  mov     r9d, ecx; cchCount1
0x18000baf9  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000bafe  lea     edx, [rcx+2]; dwCmpFlags
0x18000bb01  lea     ecx, [rdx+7Eh]; Locale
0x18000bb04  call    cs:__imp_CompareStringW
0x18000bb0a  cmp     eax, 2
0x18000bb0d  jnz     short loc_18000BB35
0x18000bb0f  mov     eax, [rsp+7B0h+pNumArgs]
0x18000bb13  dec     eax
0x18000bb15  cmp     ebx, eax
0x18000bb17  jge     loc_18000BC24
0x18000bb1d  inc     ebx
0x18000bb1f  movsxd  rcx, ebx
0x18000bb22  mov     rcx, [rdi+rcx*8]; String
0x18000bb26  call    cs:__imp__wtol
0x18000bb2c  mov     [rsp+7B0h+var_738], eax
0x18000bb30  jmp     loc_18000BC24
0x18000bb35  mov     rax, [rdi+rsi*8]
0x18000bb39  lea     r8, aOtherallowed; "OtherAllowed"
0x18000bb40  or      ecx, 0FFFFFFFFh
0x18000bb43  add     rax, 2
0x18000bb47  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000bb4b  mov     r9d, ecx; cchCount1
0x18000bb4e  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000bb53  lea     edx, [rcx+2]; dwCmpFlags
0x18000bb56  lea     ecx, [rdx+7Eh]; Locale
0x18000bb59  call    cs:__imp_CompareStringW
0x18000bb5f  cmp     eax, 2
0x18000bb62  jnz     short loc_18000BB8A
0x18000bb64  mov     eax, [rsp+7B0h+pNumArgs]
0x18000bb68  dec     eax
0x18000bb6a  cmp     ebx, eax
0x18000bb6c  jge     loc_18000BC24
0x18000bb72  inc     ebx
0x18000bb74  movsxd  rcx, ebx
0x18000bb77  mov     rcx, [rdi+rcx*8]; String
0x18000bb7b  call    cs:__imp__wtol
0x18000bb81  mov     [rsp+7B0h+var_73C], eax
0x18000bb85  jmp     loc_18000BC24
0x18000bb8a  mov     rax, [rdi+rsi*8]
0x18000bb8e  lea     r8, aOtheredgeallow; "OtherEdgeAllowed"
0x18000bb95  or      ecx, 0FFFFFFFFh
0x18000bb98  add     rax, 2
0x18000bb9c  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000bba0  mov     r9d, ecx; cchCount1
0x18000bba3  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000bba8  lea     edx, [rcx+2]; dwCmpFlags
0x18000bbab  lea     ecx, [rdx+7Eh]; Locale
0x18000bbae  call    cs:__imp_CompareStringW
0x18000bbb4  cmp     eax, 2
0x18000bbb7  jnz     short loc_18000BBD8
0x18000bbb9  mov     eax, [rsp+7B0h+pNumArgs]
0x18000bbbd  dec     eax
0x18000bbbf  cmp     ebx, eax
0x18000bbc1  jge     short loc_18000BC24
0x18000bbc3  inc     ebx
0x18000bbc5  movsxd  rcx, ebx
0x18000bbc8  mov     rcx, [rdi+rcx*8]; String
0x18000bbcc  call    cs:__imp__wtol
0x18000bbd2  mov     [rsp+7B0h+var_740], eax
0x18000bbd6  jmp     short loc_18000BC24
0x18000bbd8  mov     rax, [rdi+rsi*8]
0x18000bbdc  lea     r8, aNewblocked; "NewBlocked"
0x18000bbe3  or      ecx, 0FFFFFFFFh
0x18000bbe6  add     rax, 2
0x18000bbea  mov     [rsp+7B0h+cchCount2], ecx; cchCount2
0x18000bbee  mov     r9d, ecx; cchCount1
0x18000bbf1  mov     [rsp+7B0h+lpString2], rax; lpString2
0x18000bbf6  lea     edx, [rcx+2]; dwCmpFlags
0x18000bbf9  lea     ecx, [rdx+7Eh]; Locale
0x18000bbfc  call    cs:__imp_CompareStringW
0x18000bc02  cmp     eax, 2
0x18000bc05  jnz     short loc_18000BC24
0x18000bc07  mov     eax, [rsp+7B0h+pNumArgs]
0x18000bc0b  dec     eax
0x18000bc0d  cmp     ebx, eax
0x18000bc0f  jge     short loc_18000BC24
0x18000bc11  inc     ebx
0x18000bc13  movsxd  rcx, ebx
0x18000bc16  mov     rcx, [rdi+rcx*8]; String
0x18000bc1a  call    cs:__imp__wtol
0x18000bc20  mov     [rsp+7B0h+var_744], eax
0x18000bc24  mov     esi, [rsp+7B0h+picce.dwSize]
0x18000bc28  inc     ebx
0x18000bc2a  cmp     ebx, [rsp+7B0h+pNumArgs]
0x18000bc2e  jl      loc_18000B96D
0x18000bc34  xor     eax, eax
0x18000bc36  test    r14d, r14d
0x18000bc39  jnz     short loc_18000BC59
0x18000bc3b  lea     rcx, [rsp+7B0h+picce]
0x18000bc40  mov     [rsp+7B0h+picce.dwSize], eax
0x18000bc44  call    cs:__imp_RtlQueryElevationFlags
0x18000bc4a  mov     ebx, 1
0x18000bc4f  test    byte ptr [rsp+7B0h+picce.dwSize], bl
0x18000bc53  cmovnz  r14d, ebx
0x18000bc57  jmp     short loc_18000BC5E
0x18000bc59  mov     ebx, 1
0x18000bc5e  test    r12, r12
0x18000bc61  jz      loc_18000BD86
0x18000bc67  lea     rcx, [rsp+7B0h+picce]; picce
0x18000bc6c  mov     [rsp+7B0h+picce.dwSize], 8
0x18000bc74  mov     [rsp+7B0h+picce.dwICC], 0C000h
0x18000bc7c  call    InitCommonControlsEx
0x18000bc81  cmp     eax, ebx
0x18000bc83  jnz     loc_18000BD86
0x18000bc89  call    ?IsDxgExclusiveModeActive@@YAHXZ; IsDxgExclusiveModeActive(void)
0x18000bc8e  xor     r15d, r15d
0x18000bc91  mov     ebx, eax
0x18000bc93  test    eax, eax
0x18000bc95  jz      short loc_18000BCA1
0x18000bc97  lea     ecx, [r15+1]; uLockCode
0x18000bc9b  call    cs:__imp_LockSetForegroundWindow
0x18000bca1  mov     r8d, [rbp+6B0h+var_730]; unsigned int
0x18000bca5  lea     rax, ??_7CNotificationDialog@@6B@; const CNotificationDialog::`vftable'
0x18000bcac  mov     [rbp+6B0h+var_720], rax
0x18000bcb0  lea     rcx, [rbp+6B0h+var_720]; this
0x18000bcb4  mov     eax, [rsp+7B0h+var_744]
0x18000bcb8  xorps   xmm0, xmm0
0x18000bcbb  mov     [rsp+7B0h+var_758], eax; unsigned int
0x18000bcbf  mov     r9d, r14d; int
0x18000bcc2  mov     eax, [rsp+7B0h+var_740]
0x18000bcc6  mov     rdx, r12; unsigned __int16 *
0x18000bcc9  mov     [rsp+7B0h+var_760], eax; unsigned int
0x18000bccd  mov     eax, [rsp+7B0h+var_73C]
0x18000bcd1  mov     [rsp+7B0h+var_768], eax; unsigned int
0x18000bcd5  mov     eax, [rsp+7B0h+var_738]
0x18000bcd9  mov     [rsp+7B0h+var_770], eax; unsigned int
0x18000bcdd  mov     eax, [rsp+7B0h+var_734]
0x18000bce1  mov     [rsp+7B0h+var_778], eax; unsigned int
0x18000bce5  mov     [rsp+7B0h+var_780], esi; int
0x18000bce9  mov     [rsp+7B0h+cchCount2], ebx; int
0x18000bced  mov     dword ptr [rsp+7B0h+lpString2], r13d; int
0x18000bcf2  mov     [rbp+6B0h+var_718], r15
0x18000bcf6  mov     [rbp+6B0h+var_6F8], r15
0x18000bcfa  mov     [rbp+6B0h+var_6F0], r15
0x18000bcfe  mov     [rbp+6B0h+var_6E8], r15d
0x18000bd02  movdqa  [rbp+6B0h+var_6E0], xmm0
0x18000bd07  mov     [rbp+6B0h+var_6D0], r15
0x18000bd0b  mov     [rbp+6B0h+var_6C8], r15d
0x18000bd0f  mov     [rbp+6B0h+var_6C0], r15
0x18000bd13  mov     [rbp+6B0h+var_A0], r15
0x18000bd1a  mov     [rbp+6B0h+var_98], r15d
0x18000bd21  movups  [rbp+6B0h+var_94], xmm0
0x18000bd28  mov     [rbp+6B0h+var_7C], r15
0x18000bd2f  mov     [rbp+6B0h+var_74], r15
0x18000bd36  mov     [rbp+6B0h+var_6C], r15d
0x18000bd3d  mov     [rbp+6B0h+var_68], r15
0x18000bd44  mov     [rbp+6B0h+var_60], r15
0x18000bd4b  mov     [rbp+6B0h+var_58], r15
0x18000bd52  mov     [rbp+6B0h+var_6B8], r15w
0x18000bd57  mov     [rbp+6B0h+var_4B0], r15w
0x18000bd5f  call    ?Initialize@CNotificationDialog@@QEAAJPEBGKHHHHKKKKK@Z; CNotificationDialog::Initialize(ushort const *,ulong,int,int,int,int,ulong,ulong,ulong,ulong,ulong)
0x18000bd64  mov     r15d, eax
  ... truncated ...
```
