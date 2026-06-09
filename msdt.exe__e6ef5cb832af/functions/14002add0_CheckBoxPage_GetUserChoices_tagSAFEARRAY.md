# CheckBoxPage::GetUserChoices(tagSAFEARRAY * *)

- ea: `0x14002add0`
- end: `0x14002b005`
- name: `?GetUserChoices@CheckBoxPage@@MEAAJPEAPEAUtagSAFEARRAY@@@Z`
- size: `565`
- prototype: `__int64 __fastcall(CheckBoxPage *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400070b0`
- `0x14000e72c`
- `0x140020420`
- `0x14002ad30`
- `0x14002add0`
- `0x140061c90`

## import_xrefs

- `USER32!SendMessageW` at `0x14002ae6a`
- `USER32!SendMessageW` at `0x14002af42`
- `USER32!SendMessageW` at `0x14002ae6a`
- `USER32!SendMessageW` at `0x14002af42`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002aec5`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x14002aec5`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002afcc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x14002afcc`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002af76`
- `OLEAUT32!__imp_SafeArrayPutElement` at `0x14002af76`

## pseudocode

```c
__int64 __fastcall CheckBoxPage::GetUserChoices(CheckBoxPage *this, struct tagSAFEARRAY **a2)
{
  unsigned int v4; // ebx
  ULONG v5; // r14d
  unsigned int v6; // esi
  int NamedHandle; // eax
  LRESULT v8; // rax
  ULONG v9; // ecx
  int v10; // r9d
  SAFEARRAY *v11; // r14
  unsigned int i; // esi
  HRESULT Item; // eax
  int v14; // r9d
  LONG rgIndices; // [rsp+30h] [rbp-40h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-38h] BYREF
  SAFEARRAYBOUND rgsabound; // [rsp+40h] [rbp-30h] BYREF
  struct InteractivityChoice *v19; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int16 v20[12]; // [rsp+50h] [rbp-20h] BYREF

  rgIndices = 0;
  v4 = 0;
  hWnd = 0;
  v5 = 0;
  v19 = 0;
  v6 = 0;
  while ( v6 < *((_DWORD *)this + 42) )
  {
    NamedHandle = StringCchPrintfW(v20, 0xAu, L"cb%d", ++v6);
    v4 = NamedHandle;
    if ( NamedHandle < 0 )
    {
      v10 = 2797;
      goto LABEL_10;
    }
    NamedHandle = WizardPage::GetNamedHandle(this, v20, &hWnd);
    v4 = NamedHandle;
    if ( NamedHandle < 0 )
    {
      v10 = 2800;
LABEL_10:
      SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::GetUserChoices", v10, NamedHandle);
      return v4;
    }
    v8 = SendMessageW(hWnd, 0xF0u, 0, 0);
    v9 = v5 + 1;
    if ( v8 != 1 )
      v9 = v5;
    v5 = v9;
  }
  rgsabound.lLbound = 0;
  rgsabound.cElements = v5;
  v11 = SafeArrayCreate(8u, 1u, &rgsabound);
  if ( v11 )
  {
    for ( i = 0; i < *((_DWORD *)this + 42); ++i )
    {
      Item = StringCchPrintfW(v20, 0xAu, L"cb%d", i + 1);
      v4 = Item;
      if ( Item < 0 )
      {
        v14 = 2822;
        goto LABEL_27;
      }
      Item = WizardPage::GetNamedHandle(this, v20, &hWnd);
      v4 = Item;
      if ( Item < 0 )
      {
        v14 = 2825;
        goto LABEL_27;
      }
      if ( SendMessageW(hWnd, 0xF0u, 0, 0) == 1 )
      {
        Item = InteractivityPage::GetItem(this, i, &v19);
        v4 = Item;
        if ( Item < 0 )
        {
          v14 = 2829;
          goto LABEL_27;
        }
        Item = SafeArrayPutElement(v11, &rgIndices, *((void **)v19 + 2));
        v4 = Item;
        if ( Item < 0 )
        {
          v14 = 2837;
LABEL_27:
          SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::GetUserChoices", v14, Item);
          SafeArrayDestroy(v11);
          return v4;
        }
        ++rgIndices;
      }
    }
    *a2 = v11;
  }
  else
  {
    v4 = -2147024882;
    SdpDebugPrint(1u, "Dwz ERROR: %s:%d - hr = 0x%08X\n", "CheckBoxPage::GetUserChoices", 2811, -2147024882);
  }
  return v4;
}

```

## disassembly

```asm
0x14002add0  mov     [rsp-38h+arg_10], rbx
0x14002add5  push    rbp
0x14002add6  push    rsi
0x14002add7  push    rdi
0x14002add8  push    r12
0x14002adda  push    r13
0x14002addc  push    r14
0x14002adde  push    r15
0x14002ade0  mov     rbp, rsp
0x14002ade3  sub     rsp, 70h
0x14002ade7  mov     rax, cs:__security_cookie
0x14002adee  xor     rax, rsp
0x14002adf1  mov     [rbp+var_8], rax
0x14002adf5  xor     r12d, r12d
0x14002adf8  mov     r13, rdx
0x14002adfb  mov     r15, rcx
0x14002adfe  mov     [rbp+rgIndices], r12d
0x14002ae02  mov     ebx, r12d
0x14002ae05  mov     [rbp+hWnd], r12
0x14002ae09  mov     r14d, r12d
0x14002ae0c  mov     [rbp+var_28], r12
0x14002ae10  lea     edi, [r12+1]
0x14002ae15  mov     esi, r12d
0x14002ae18  cmp     esi, [r15+0A8h]
0x14002ae1f  jnb     loc_14002AEB2
0x14002ae25  inc     esi
0x14002ae27  lea     r8, aCbD; "cb%d"
0x14002ae2e  mov     r9d, esi
0x14002ae31  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x14002ae35  mov     edx, 0Ah; unsigned __int64
0x14002ae3a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002ae3f  mov     ebx, eax
0x14002ae41  test    eax, eax
0x14002ae43  js      short loc_14002AE8E
0x14002ae45  lea     r8, [rbp+hWnd]; HWND *
0x14002ae49  mov     rcx, r15; this
0x14002ae4c  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002ae50  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002ae55  mov     ebx, eax
0x14002ae57  test    eax, eax
0x14002ae59  js      short loc_14002AE86
0x14002ae5b  mov     rcx, [rbp+hWnd]; hWnd
0x14002ae5f  xor     r9d, r9d; lParam
0x14002ae62  xor     r8d, r8d; wParam
0x14002ae65  mov     edx, 0F0h; Msg
0x14002ae6a  call    cs:__imp_SendMessageW
0x14002ae71  nop     dword ptr [rax+rax+00h]
0x14002ae76  lea     ecx, [r14+1]
0x14002ae7a  cmp     rax, rdi
0x14002ae7d  cmovnz  ecx, r14d
0x14002ae81  mov     r14d, ecx
0x14002ae84  jmp     short loc_14002AE18
0x14002ae86  mov     r9d, 0AF0h
0x14002ae8c  jmp     short loc_14002AE94
0x14002ae8e  mov     r9d, 0AEDh
0x14002ae94  mov     [rsp+70h+var_50], eax
0x14002ae98  lea     r8, aCheckboxpageGe; "CheckBoxPage::GetUserChoices"
0x14002ae9f  mov     ecx, edi; Level
0x14002aea1  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002aea8  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002aead  jmp     loc_14002AFDE
0x14002aeb2  mov     ecx, 8; vt
0x14002aeb7  mov     [rbp+rgsabound.lLbound], r12d
0x14002aebb  lea     r8, [rbp+rgsabound]; rgsabound
0x14002aebf  mov     [rbp+rgsabound.cElements], r14d
0x14002aec3  mov     edx, edi; cDims
0x14002aec5  call    cs:__imp_SafeArrayCreate
0x14002aecc  nop     dword ptr [rax+rax+00h]
0x14002aed1  mov     r14, rax
0x14002aed4  test    rax, rax
0x14002aed7  jnz     short loc_14002AEEA
0x14002aed9  mov     ebx, 8007000Eh
0x14002aede  mov     r9d, 0AFBh
0x14002aee4  mov     [rsp+70h+var_50], ebx
0x14002aee8  jmp     short loc_14002AE98
0x14002aeea  mov     esi, r12d
0x14002aeed  cmp     esi, [r15+0A8h]
0x14002aef4  jnb     loc_14002AFDA
0x14002aefa  lea     r9d, [rsi+1]
0x14002aefe  mov     edx, 0Ah; unsigned __int64
0x14002af03  lea     r8, aCbD; "cb%d"
0x14002af0a  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x14002af0e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002af13  mov     ebx, eax
0x14002af15  test    eax, eax
0x14002af17  js      loc_14002AFAA
0x14002af1d  lea     r8, [rbp+hWnd]; HWND *
0x14002af21  mov     rcx, r15; this
0x14002af24  lea     rdx, [rbp+var_20]; unsigned __int16 *
0x14002af28  call    ?GetNamedHandle@WizardPage@@IEAAJPEBGPEAPEAUHWND__@@@Z; WizardPage::GetNamedHandle(ushort const *,HWND__ * *)
0x14002af2d  mov     ebx, eax
0x14002af2f  test    eax, eax
0x14002af31  js      short loc_14002AFA2
0x14002af33  mov     rcx, [rbp+hWnd]; hWnd
0x14002af37  xor     r9d, r9d; lParam
0x14002af3a  xor     r8d, r8d; wParam
0x14002af3d  mov     edx, 0F0h; Msg
0x14002af42  call    cs:__imp_SendMessageW
0x14002af49  nop     dword ptr [rax+rax+00h]
0x14002af4e  cmp     rax, rdi
0x14002af51  jnz     short loc_14002AF8B
0x14002af53  lea     r8, [rbp+var_28]; struct InteractivityChoice **
0x14002af57  mov     edx, esi; unsigned int
0x14002af59  mov     rcx, r15; this
0x14002af5c  call    ?GetItem@InteractivityPage@@IEAAJIPEAPEAVInteractivityChoice@@@Z; InteractivityPage::GetItem(uint,InteractivityChoice * *)
0x14002af61  mov     ebx, eax
0x14002af63  test    eax, eax
0x14002af65  js      short loc_14002AF9A
0x14002af67  mov     r8, [rbp+var_28]
0x14002af6b  lea     rdx, [rbp+rgIndices]; rgIndices
0x14002af6f  mov     rcx, r14; psa
0x14002af72  mov     r8, [r8+10h]; pv
0x14002af76  call    cs:__imp_SafeArrayPutElement
0x14002af7d  nop     dword ptr [rax+rax+00h]
0x14002af82  mov     ebx, eax
0x14002af84  test    eax, eax
0x14002af86  js      short loc_14002AF92
0x14002af88  add     [rbp+rgIndices], edi
0x14002af8b  inc     esi
0x14002af8d  jmp     loc_14002AEED
0x14002af92  mov     r9d, 0B15h
0x14002af98  jmp     short loc_14002AFB0
0x14002af9a  mov     r9d, 0B0Dh
0x14002afa0  jmp     short loc_14002AFB0
0x14002afa2  mov     r9d, 0B09h
0x14002afa8  jmp     short loc_14002AFB0
0x14002afaa  mov     r9d, 0B06h
0x14002afb0  lea     r8, aCheckboxpageGe; "CheckBoxPage::GetUserChoices"
0x14002afb7  mov     [rsp+70h+var_50], eax
0x14002afbb  lea     rdx, aDwzErrorSDHr0x; "Dwz ERROR: %s:%d - hr = 0x%08X\n"
0x14002afc2  mov     ecx, edi; Level
0x14002afc4  call    ?SdpDebugPrint@@YAXKPEBDZZ; SdpDebugPrint(ulong,char const *,...)
0x14002afc9  mov     rcx, r14; psa
0x14002afcc  call    cs:__imp_SafeArrayDestroy
0x14002afd3  nop     dword ptr [rax+rax+00h]
0x14002afd8  jmp     short loc_14002AFDE
0x14002afda  mov     [r13+0], r14
0x14002afde  mov     eax, ebx
0x14002afe0  mov     rcx, [rbp+var_8]
0x14002afe4  xor     rcx, rsp; StackCookie
0x14002afe7  call    __security_check_cookie
0x14002afec  mov     rbx, [rsp+70h+arg_10]
0x14002aff4  add     rsp, 70h
0x14002aff8  pop     r15
0x14002affa  pop     r14
0x14002affc  pop     r13
0x14002affe  pop     r12
0x14002b000  pop     rdi
0x14002b001  pop     rsi
0x14002b002  pop     rbp
0x14002b003  retn
```
