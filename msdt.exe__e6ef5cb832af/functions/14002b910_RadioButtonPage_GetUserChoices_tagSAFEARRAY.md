# RadioButtonPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002b910`
- end: `0x14002bb56`
- name: `?GetUserChoices@RadioButtonPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `582`
- prototype: `__int64 __fastcall(RadioButtonPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x1400070b0`
- `0x14000e6bc`
- `0x14000e72c`
- `0x140020420`
- `0x14002ad30`
- `0x14002b910`
- `0x140061c90`
- `0x140063010`

## import_xrefs

- `USER32!SendMessageW` at `0x14002b9f9`
- `USER32!SendMessageW` at `0x14002ba44`
- `USER32!SendMessageW` at `0x14002b9f9`
- `USER32!SendMessageW` at `0x14002ba44`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b977`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002b977`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002ba6a`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002ba6a`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002baf8`
- `DUI70!?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z` at `0x14002baf8`

## pseudocode

```c
__int64 __fastcall RadioButtonPage::GetUserChoices(RadioButtonPage *this, struct tagSAFEARRAY **a2)
{
  SAFEARRAY *v4; // r14
  unsigned int v5; // ebx
  unsigned int i; // edi
  HRESULT NamedElement; // eax
  int v8; // r9d
  void *v9; // rbx
  LONG rgIndices; // [rsp+30h] [rbp-50h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-48h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-40h] BYREF
  struct InteractivityChoice *v14; // [rsp+48h] [rbp-38h] BYREF
  struct DirectUI::Element *v15; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int16 v16[12]; // [rsp+58h] [rbp-28h] BYREF

  rgIndices = 0;
  hWnd = 0;
  v14 = 0;
  v15 = 0;
  rgsabound = (SAFEARRAYBOUND)1LL;
  v4 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( v4 )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= *((_DWORD *)this + 42) )
      {
        NamedElement = StringCchPrintfW(v16, 0xAu, L"rb%d", 1);
        v5 = NamedElement;
        if ( NamedElement < 0 )
        {
          v8 = 2075;
          goto LABEL_24;
        }
        NamedElement = WizardPage::GetNamedElement(this, v16, &v15);
        v5 = NamedElement;
        if ( NamedElement < 0 )
        {
          v8 = 2078;
          goto LABEL_24;
        }
        (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v15 + 168LL))(v15);
        DirectUI::TaskPage::PropSheet_SendMessage(this, 0x48Bu, 0, 2);
        v8 = 2085;
        goto LABEL_23;
      }
      NamedElement = StringCchPrintfW(v16, 0xAu, L"rb%d", i + 1);
      v5 = NamedElement;
      if ( NamedElement < 0 )
      {
        v8 = 2045;
        goto LABEL_24;
      }
      NamedElement = WizardPage::GetNamedHandle(this, v16, &hWnd);
      v5 = NamedElement;
      if ( NamedElement < 0 )
      {
        v8 = 2048;
        goto LABEL_24;
      }
      if ( SendMessageW(hWnd, 0xF0u, 0, 0) == 1 )
        break;
    }
    NamedElement = InteractivityPage::GetItem(this, i, &v14);
    v5 = NamedElement;
    if ( NamedElement < 0 )
    {
      v8 = 2052;
      goto LABEL_24;
    }
    v9 = (void *)*((_QWORD *)v14 + 2);
    SendMessageW(hWnd, 0xF1u, 0, 0);
    if ( !v9 )
    {
      v8 = 2090;
LABEL_23:
      NamedElement = -2147467259;
      v5 = -2147467259;
      goto LABEL_24;
    }
    NamedElement = SafeArrayPutElement(v4, &rgIndices, v9);
    v5 = NamedElement;
    if ( NamedElement >= 0 )
    {
      *a2 = v4;
      return v5;
    }
    v8 = 2094;
LABEL_24:
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::GetUserChoices", v8, NamedElement);
  }
  else
  {
    v5 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "RadioButtonPage::GetUserChoices", 2034, -2147024882);
  }
  return v5;
}

```

## disassembly

```asm
0x14002b910  mov     [rsp-28h+arg_10], rbx
0x14002b915  mov     [rsp-28h+arg_18], rsi
0x14002b91a  push    rbp
0x14002b91b  push    rdi
0x14002b91c  push    r12
0x14002b91e  push    r14
0x14002b920  push    r15
0x14002b922  mov     rbp, rsp
0x14002b925  sub     rsp, 80h
0x14002b92c  mov     rax, cs:__security_cookie
0x14002b933  xor     rax, rsp
0x14002b936  mov     [rbp+var_10], rax
0x14002b93a  mov     rsi, rcx
0x14002b93d  mov     [rbp+rgIndices], 0
0x14002b944  mov     ecx, 8; vt
0x14002b949  mov     [rbp+hWnd], 0
0x14002b951  mov     r12, rdx
0x14002b954  mov     [rbp+var_38], 0
0x14002b95c  lea     r8, [rbp+rgsabound]; rgsabound
0x14002b960  mov     [rbp+var_30], 0
0x14002b968  mov     qword ptr [rbp+rgsabound.cElements], 1
0x14002b970  lea     r15d, [rcx-7]
0x14002b974  mov     edx, r15d; cDims
0x14002b977  call    cs:__imp_SafeArrayCreate
0x14002b97e  nop     dword ptr [rax+rax+00h]
0x14002b983  mov     r14, rax
0x14002b986  test    rax, rax
0x14002b989  jnz     short loc_14002B99F
0x14002b98b  mov     ebx, 8007000Eh
0x14002b990  mov     r9d, 7F2h
0x14002b996  mov     [rsp+80h+var_60], ebx
0x14002b99a  jmp     loc_14002BB15
0x14002b99f  xor     edi, edi
0x14002b9a1  lea     r8, aRbD; "rb%d"
0x14002b9a8  mov     edx, 0Ah; unsigned __int64
0x14002b9ad  lea     rcx, [rbp+var_28]; unsigned __int16 *
0x14002b9b1  cmp     edi, [rsi+0A8h]
0x14002b9b7  jnb     loc_14002BAA0
0x14002b9bd  lea     r9d, [rdi+1]
0x14002b9c1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002b9c6  mov     ebx, eax
0x14002b9c8  test    eax, eax
0x14002b9ca  js      loc_14002BA98
0x14002b9d0  lea     r8, [rbp+hWnd]; HWND *
0x14002b9d4  mov     rcx, rsi; this
0x14002b9d7  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x14002b9db  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002b9e0  mov     ebx, eax
0x14002b9e2  test    eax, eax
0x14002b9e4  js      loc_14002BA90
0x14002b9ea  mov     rcx, [rbp+hWnd]; hWnd
0x14002b9ee  xor     r9d, r9d; lParam
0x14002b9f1  xor     r8d, r8d; wParam
0x14002b9f4  mov     edx, 0F0h; Msg
0x14002b9f9  call    cs:__imp_SendMessageW
0x14002ba00  nop     dword ptr [rax+rax+00h]
0x14002ba05  cmp     rax, r15
0x14002ba08  jz      short loc_14002BA0E
0x14002ba0a  inc     edi
0x14002ba0c  jmp     short loc_14002B9A1
0x14002ba0e  lea     r8, [rbp+var_38]; struct InteractivityChoice **
0x14002ba12  mov     edx, edi; unsigned int
0x14002ba14  mov     rcx, rsi; this
0x14002ba17  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002ba1c  mov     ebx, eax
0x14002ba1e  test    eax, eax
0x14002ba20  jns     short loc_14002BA2D
0x14002ba22  mov     r9d, 804h
0x14002ba28  jmp     loc_14002BB11
0x14002ba2d  mov     rax, [rbp+var_38]
0x14002ba31  xor     r9d, r9d; lParam
0x14002ba34  mov     rcx, [rbp+hWnd]; hWnd
0x14002ba38  xor     r8d, r8d; wParam
0x14002ba3b  mov     edx, 0F1h; Msg
0x14002ba40  mov     rbx, [rax+10h]
0x14002ba44  call    cs:__imp_SendMessageW
0x14002ba4b  nop     dword ptr [rax+rax+00h]
0x14002ba50  test    rbx, rbx
0x14002ba53  jnz     short loc_14002BA60
0x14002ba55  mov     r9d, 82Ah
0x14002ba5b  jmp     loc_14002BB0A
0x14002ba60  mov     r8, rbx; pv
0x14002ba63  lea     rdx, [rbp+rgIndices]; rgIndices
0x14002ba67  mov     rcx, r14; psa
0x14002ba6a  call    cs:__imp_SafeArrayPutElement
0x14002ba71  nop     dword ptr [rax+rax+00h]
0x14002ba76  mov     ebx, eax
0x14002ba78  test    eax, eax
0x14002ba7a  jns     short loc_14002BA87
0x14002ba7c  mov     r9d, 82Eh
0x14002ba82  jmp     loc_14002BB11
0x14002ba87  mov     [r12], r14
0x14002ba8b  jmp     loc_14002BB2B
0x14002ba90  mov     r9d, 800h
0x14002ba96  jmp     short loc_14002BB11
0x14002ba98  mov     r9d, 7FDh
0x14002ba9e  jmp     short loc_14002BB11
0x14002baa0  mov     r9d, r15d
0x14002baa3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002baa8  mov     ebx, eax
0x14002baaa  test    eax, eax
0x14002baac  jns     short loc_14002BAB6
0x14002baae  mov     r9d, 81Bh
0x14002bab4  jmp     short loc_14002BB11
0x14002bab6  lea     r8, [rbp+var_30]; struct DirectUI::Element **
0x14002baba  mov     rcx, rsi; this
0x14002babd  lea     rdx, [rbp+var_28]; unsigned __int16 *
0x14002bac1  call    ?GetNamedElement@WizardPage@@QEAAJPEBGPEAPEAVElement@DirectUI@@@Z; WizardPage::GetNamedElement(ushort const *,DirectUI::Element * *)
0x14002bac6  mov     ebx, eax
0x14002bac8  test    eax, eax
0x14002baca  jns     short loc_14002BAD4
0x14002bacc  mov     r9d, 81Eh
0x14002bad2  jmp     short loc_14002BB11
0x14002bad4  mov     rcx, [rbp+var_30]
0x14002bad8  mov     rax, [rcx]
0x14002badb  mov     rax, [rax+0A8h]
0x14002bae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002bae7  mov     r9d, 2
0x14002baed  xor     r8d, r8d
0x14002baf0  mov     edx, 48Bh
0x14002baf5  mov     rcx, rsi
0x14002baf8  call    cs:__imp_?PropSheet_SendMessage@TaskPage@DirectUI@@IEAA_JI_K_J@Z; DirectUI::TaskPage::PropSheet_SendMessage(uint,unsigned __int64,__int64)
0x14002baff  nop     dword ptr [rax+rax+00h]
0x14002bb04  mov     r9d, 825h
0x14002bb0a  mov     eax, 80004005h
0x14002bb0f  mov     ebx, eax
0x14002bb11  mov     [rsp+80h+var_60], eax
0x14002bb15  lea     r8, aRadiobuttonpag_3; "RadioButtonPage::GetUserChoices"
0x14002bb1c  mov     ecx, r15d; Level
0x14002bb1f  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002bb26  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002bb2b  mov     eax, ebx
0x14002bb2d  mov     rcx, [rbp+var_10]
0x14002bb31  xor     rcx, rsp; StackCookie
0x14002bb34  call    __security_check_cookie
0x14002bb39  lea     r11, [rsp+80h+var_s0]
0x14002bb41  mov     rbx, [r11+40h]
0x14002bb45  mov     rsi, [r11+48h]
0x14002bb49  mov     rsp, r11
0x14002bb4c  pop     r15
0x14002bb4e  pop     r14
0x14002bb50  pop     r12
0x14002bb52  pop     rdi
0x14002bb53  pop     rbp
0x14002bb54  retn
```
