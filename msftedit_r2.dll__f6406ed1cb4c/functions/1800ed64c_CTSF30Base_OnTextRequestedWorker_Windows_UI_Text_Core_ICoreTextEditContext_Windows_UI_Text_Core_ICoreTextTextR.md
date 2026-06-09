# CTSF30Base::OnTextRequestedWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *)

- ea: `0x1800ed64c`
- end: `0x1800ed92a`
- name: `?OnTextRequestedWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextTextRequestedEventArgs@3456@@Z`
- size: `734`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800ed640`

## callees

- `0x18001caf4`
- `0x180043e7c`
- `0x18006ad18`
- `0x18006af48`
- `0x1800ed64c`
- `0x1800ed930`
- `0x18020a9a4`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed7b3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800ed830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800ed849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800ed849`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnTextRequestedWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *, __int64 *); // rbx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  int v12; // ebx
  int v13; // eax
  CTSF30Base *v14; // rcx
  int v15; // eax
  const WCHAR *v16; // rdi
  unsigned __int64 v17; // rbx
  __int64 v18; // rcx
  unsigned __int16 *v19; // rcx
  struct ITextRange2 *v20; // rcx
  __int64 v21; // rcx
  HRESULT v23; // eax
  __int64 v24; // rcx
  unsigned __int16 *v25; // rcx
  struct ITextRange2 *v26; // rcx
  __int64 v27; // rcx
  struct ITextRange2 *v28; // [rsp+30h] [rbp-20h] BYREF
  __int64 v29; // [rsp+38h] [rbp-18h] BYREF
  HSTRING string; // [rsp+40h] [rbp-10h] BYREF
  __int64 v31; // [rsp+48h] [rbp-8h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *v32; // [rsp+88h] [rbp+38h] BYREF
  __int64 v33; // [rsp+90h] [rbp+40h] BYREF
  PCNZWCH sourceString; // [rsp+98h] [rbp+48h] BYREF

  v32 = a2;
  v3 = *(_QWORD *)a3;
  v29 = 0;
  v33 = 0;
  v6 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextRequestedEventArgs *, __int64 *))(v3 + 48);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
  v7 = v6(a3, &v33);
  v8 = v33;
  if ( v7 < 0 )
  {
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return 2147500037LL;
  }
  else
  {
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 48LL))(v33, &v29);
    v9 = *((_QWORD *)this + 13) + 16LL;
    v28 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, struct ITextRange2 **))(*(_QWORD *)v9 + 424LL))(
            v9,
            (unsigned int)v29,
            HIDWORD(v29),
            &v28);
    sourceString = 0;
    v11 = 0;
    v31 = 0;
    v12 = v10;
    if ( v10 >= 0 )
    {
      v13 = ((__int64 (__fastcall *)(struct ITextRange2 *, __int64 *))v28->lpVtbl->GetFont2)(v28, &v31);
      v11 = v31;
      v12 = v13;
    }
    LODWORD(v32) = 0;
    if ( v12 < 0
      || (v12 = (*(__int64 (__fastcall **)(__int64, struct Windows::UI::Text::Core::ICoreTextEditContext **))(*(_QWORD *)v11 + 208LL))(
                  v11,
                  &v32),
          v12 < 0)
      || (CTxtEdit::fHiddenPassword(*((CTxtEdit **)this + 13))
        ? (v12 = CTSF30Base::FillWithPasswordCharacter(
                   this,
                   (unsigned __int16 **)&sourceString,
                   HIDWORD(v29) - (int)v29),
           v15 = 0,
           LODWORD(v32) = 0)
        : (v12 = ((__int64 (__fastcall *)(struct ITextRange2 *, PCNZWCH *))v28->lpVtbl->GetText)(v28, &sourceString),
           v15 = (int)v32),
          v12 < 0) )
    {
LABEL_12:
      string = 0;
      if ( v12 < 0 )
      {
LABEL_20:
        WindowsDeleteString(string);
        v18 = v31;
        string = 0;
        if ( v31 )
        {
          v31 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        v19 = (unsigned __int16 *)sourceString;
        if ( sourceString )
        {
          sourceString = 0;
          CW32System::SysFreeString(v19);
        }
        v20 = v28;
        if ( v28 )
        {
          v28 = 0;
          ((void (__fastcall *)(struct ITextRange2 *))v20->lpVtbl->Release)(v20);
        }
        v21 = v33;
        if ( v33 )
        {
          v33 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
        return (unsigned int)v12;
      }
      v16 = sourceString;
      if ( sourceString )
      {
        v17 = -1;
        do
          ++v17;
        while ( sourceString[v17] );
        if ( v17 > 0xFFFFFFFF )
        {
          v12 = -2147024362;
          goto LABEL_18;
        }
        WindowsDeleteString(0);
        string = 0;
        v23 = WindowsCreateString(v16, v17, &string);
      }
      else
      {
        v23 = Microsoft::WRL::Wrappers::HString::Set((Microsoft::WRL::Wrappers::HString *)&string, &WindowName, 0);
      }
      v12 = v23;
LABEL_18:
      if ( v12 >= 0 )
        v12 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*(_QWORD *)v33 + 64LL))(v33, string);
      goto LABEL_20;
    }
    if ( sourceString )
    {
      if ( v15 )
        v12 = CTSF30Base::ConvertHiddenCharacters(v14, v28, (struct Resp::BStrHolder *)&sourceString);
      goto LABEL_12;
    }
    v24 = v31;
    if ( v31 )
    {
      v31 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      v25 = (unsigned __int16 *)sourceString;
      if ( sourceString )
      {
        sourceString = 0;
        CW32System::SysFreeString(v25);
      }
    }
    v26 = v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(struct ITextRange2 *))v26->lpVtbl->Release)(v26);
    }
    v27 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1800ed64c  mov     [rsp-28h+arg_8], rdx
0x1800ed651  push    rbp
0x1800ed652  push    rbx
0x1800ed653  push    rsi
0x1800ed654  push    rdi
0x1800ed655  push    r14
0x1800ed657  mov     rbp, rsp
0x1800ed65a  sub     rsp, 50h
0x1800ed65e  mov     rax, [r8]
0x1800ed661  mov     rsi, rcx
0x1800ed664  xor     r14d, r14d
0x1800ed667  lea     rcx, [rbp+arg_10]
0x1800ed66b  mov     rdi, r8
0x1800ed66e  mov     [rbp+var_18], r14
0x1800ed672  mov     [rbp+arg_10], r14
0x1800ed676  mov     rbx, [rax+30h]
0x1800ed67a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800ed67f  lea     rdx, [rbp+arg_10]
0x1800ed683  mov     rcx, rdi
0x1800ed686  mov     rax, rbx
0x1800ed689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed68e  mov     rcx, [rbp+arg_10]
0x1800ed692  test    eax, eax
0x1800ed694  js      loc_1800ED8DF
0x1800ed69a  mov     rax, [rcx]
0x1800ed69d  lea     rdx, [rbp+var_18]
0x1800ed6a1  mov     rax, [rax+30h]
0x1800ed6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed6aa  mov     rcx, [rsi+68h]
0x1800ed6ae  lea     r9, [rbp+var_20]
0x1800ed6b2  mov     r8d, dword ptr [rbp+var_18+4]
0x1800ed6b6  add     rcx, 10h
0x1800ed6ba  mov     edx, dword ptr [rbp+var_18]
0x1800ed6bd  mov     [rbp+var_20], r14
0x1800ed6c1  mov     rax, [rcx]
0x1800ed6c4  mov     rax, [rax+1A8h]
0x1800ed6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed6d0  mov     [rbp+sourceString], r14
0x1800ed6d4  mov     ecx, r14d
0x1800ed6d7  mov     [rbp+var_8], rcx
0x1800ed6db  mov     ebx, eax
0x1800ed6dd  test    eax, eax
0x1800ed6df  js      short loc_1800ED6FE
0x1800ed6e1  mov     rcx, [rbp+var_20]
0x1800ed6e5  lea     rdx, [rbp+var_8]
0x1800ed6e9  mov     rax, [rcx]
0x1800ed6ec  mov     rax, [rax+248h]
0x1800ed6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed6f8  mov     rcx, [rbp+var_8]
0x1800ed6fc  mov     ebx, eax
0x1800ed6fe  mov     dword ptr [rbp+arg_8], r14d
0x1800ed702  test    ebx, ebx
0x1800ed704  js      short loc_1800ED75F
0x1800ed706  mov     rax, [rcx]
0x1800ed709  lea     rdx, [rbp+arg_8]
0x1800ed70d  mov     rax, [rax+0D0h]
0x1800ed714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed719  mov     ebx, eax
0x1800ed71b  test    eax, eax
0x1800ed71d  js      short loc_1800ED75F
0x1800ed71f  mov     rcx, [rsi+68h]; this
0x1800ed723  call    ?fHiddenPassword@CTxtEdit@@QEBA_NXZ; CTxtEdit::fHiddenPassword(void)
0x1800ed728  lea     rdx, [rbp+sourceString]; unsigned __int16 **
0x1800ed72c  test    al, al
0x1800ed72e  jnz     loc_1800ED8C2
0x1800ed734  mov     rcx, [rbp+var_20]
0x1800ed738  mov     rax, [rcx]
0x1800ed73b  mov     rax, [rax+38h]
0x1800ed73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed744  mov     ebx, eax
0x1800ed746  mov     eax, dword ptr [rbp+arg_8]
0x1800ed749  test    ebx, ebx
0x1800ed74b  js      short loc_1800ED75F
0x1800ed74d  cmp     [rbp+sourceString], r14
0x1800ed751  jz      loc_1800ED85C
0x1800ed757  test    eax, eax
0x1800ed759  jnz     loc_1800ED8FE
0x1800ed75f  mov     [rbp+string], r14
0x1800ed763  test    ebx, ebx
0x1800ed765  js      short loc_1800ED7AF
0x1800ed767  mov     rdi, [rbp+sourceString]
0x1800ed76b  test    rdi, rdi
0x1800ed76e  jz      loc_1800ED912
0x1800ed774  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800ed778  inc     rbx
0x1800ed77b  cmp     [rdi+rbx*2], r14w
0x1800ed780  jnz     short loc_1800ED778
0x1800ed782  mov     eax, 0FFFFFFFFh
0x1800ed787  cmp     rbx, rax
0x1800ed78a  jbe     loc_1800ED82E
0x1800ed790  mov     ebx, 80070216h
0x1800ed795  test    ebx, ebx
0x1800ed797  js      short loc_1800ED7AF
0x1800ed799  mov     rcx, [rbp+arg_10]
0x1800ed79d  mov     rdx, [rbp+string]
0x1800ed7a1  mov     rax, [rcx]
0x1800ed7a4  mov     rax, [rax+40h]
0x1800ed7a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed7ad  mov     ebx, eax
0x1800ed7af  mov     rcx, [rbp+string]; string
0x1800ed7b3  call    cs:__imp_WindowsDeleteString
0x1800ed7ba  nop     dword ptr [rax+rax+00h]
0x1800ed7bf  mov     rcx, [rbp+var_8]
0x1800ed7c3  mov     [rbp+string], r14
0x1800ed7c7  test    rcx, rcx
0x1800ed7ca  jz      short loc_1800ED7DC
0x1800ed7cc  mov     [rbp+var_8], r14
0x1800ed7d0  mov     rax, [rcx]
0x1800ed7d3  mov     rax, [rax+10h]
0x1800ed7d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed7dc  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800ed7e0  test    rcx, rcx
0x1800ed7e3  jz      short loc_1800ED7EE
0x1800ed7e5  mov     [rbp+sourceString], r14
0x1800ed7e9  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800ed7ee  mov     rcx, [rbp+var_20]
0x1800ed7f2  test    rcx, rcx
0x1800ed7f5  jz      short loc_1800ED807
0x1800ed7f7  mov     [rbp+var_20], r14
0x1800ed7fb  mov     rax, [rcx]
0x1800ed7fe  mov     rax, [rax+10h]
0x1800ed802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed807  mov     rcx, [rbp+arg_10]
0x1800ed80b  test    rcx, rcx
0x1800ed80e  jz      short loc_1800ED820
0x1800ed810  mov     [rbp+arg_10], r14
0x1800ed814  mov     rax, [rcx]
0x1800ed817  mov     rax, [rax+10h]
0x1800ed81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed820  mov     eax, ebx
0x1800ed822  add     rsp, 50h
0x1800ed826  pop     r14
0x1800ed828  pop     rdi
0x1800ed829  pop     rsi
0x1800ed82a  pop     rbx
0x1800ed82b  pop     rbp
0x1800ed82c  retn
0x1800ed82e  xor     ecx, ecx; string
0x1800ed830  call    cs:__imp_WindowsDeleteString
0x1800ed837  nop     dword ptr [rax+rax+00h]
0x1800ed83c  mov     edx, ebx; length
0x1800ed83e  mov     [rbp+string], r14
0x1800ed842  lea     r8, [rbp+string]; string
0x1800ed846  mov     rcx, rdi; sourceString
0x1800ed849  call    cs:__imp_WindowsCreateString
0x1800ed850  nop     dword ptr [rax+rax+00h]
0x1800ed855  mov     ebx, eax
0x1800ed857  jmp     loc_1800ED795
0x1800ed85c  mov     rcx, [rbp+var_8]
0x1800ed860  test    rcx, rcx
0x1800ed863  jz      short loc_1800ED87E
0x1800ed865  mov     [rbp+var_8], r14
0x1800ed869  mov     rax, [rcx]
0x1800ed86c  mov     rax, [rax+10h]
0x1800ed870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed875  mov     rcx, [rbp+sourceString]; unsigned __int16 *
0x1800ed879  test    rcx, rcx
0x1800ed87c  jnz     short loc_1800ED8B7
0x1800ed87e  mov     rcx, [rbp+var_20]
0x1800ed882  test    rcx, rcx
0x1800ed885  jz      short loc_1800ED897
0x1800ed887  mov     [rbp+var_20], r14
0x1800ed88b  mov     rax, [rcx]
0x1800ed88e  mov     rax, [rax+10h]
0x1800ed892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed897  mov     rcx, [rbp+arg_10]
0x1800ed89b  test    rcx, rcx
0x1800ed89e  jz      short loc_1800ED8B0
0x1800ed8a0  mov     [rbp+arg_10], r14
0x1800ed8a4  mov     rax, [rcx]
0x1800ed8a7  mov     rax, [rax+10h]
0x1800ed8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed8b0  xor     eax, eax
0x1800ed8b2  jmp     loc_1800ED822
0x1800ed8b7  mov     [rbp+sourceString], r14
0x1800ed8bb  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800ed8c0  jmp     short loc_1800ED87E
0x1800ed8c2  mov     r8d, dword ptr [rbp+var_18+4]
0x1800ed8c6  mov     rcx, rsi; this
0x1800ed8c9  sub     r8d, dword ptr [rbp+var_18]; int
0x1800ed8cd  call    ?FillWithPasswordCharacter@CTSF30Base@@AEAAJPEAPEAGJ@Z; CTSF30Base::FillWithPasswordCharacter(ushort * *,long)
0x1800ed8d2  mov     ebx, eax
0x1800ed8d4  mov     eax, r14d
0x1800ed8d7  mov     dword ptr [rbp+arg_8], eax
0x1800ed8da  jmp     loc_1800ED749
0x1800ed8df  test    rcx, rcx
0x1800ed8e2  jz      short loc_1800ED8F4
0x1800ed8e4  mov     [rbp+arg_10], r14
0x1800ed8e8  mov     rax, [rcx]
0x1800ed8eb  mov     rax, [rax+10h]
0x1800ed8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ed8f4  mov     eax, 80004005h
0x1800ed8f9  jmp     loc_1800ED822
0x1800ed8fe  mov     rdx, [rbp+var_20]; struct ITextRange2 *
0x1800ed902  lea     r8, [rbp+sourceString]; struct Resp::BStrHolder *
0x1800ed906  call    ?ConvertHiddenCharacters@CTSF30Base@@AEAAJPEAUITextRange2@@AEAVBStrHolder@Resp@@@Z; CTSF30Base::ConvertHiddenCharacters(ITextRange2 *,Resp::BStrHolder &)
0x1800ed90b  mov     ebx, eax
0x1800ed90d  jmp     loc_1800ED75F
0x1800ed912  xor     r8d, r8d; unsigned int
0x1800ed915  lea     rdx, WindowName; unsigned __int16 *
0x1800ed91c  lea     rcx, [rbp+string]; this
0x1800ed920  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x1800ed925  jmp     loc_1800ED855
```
