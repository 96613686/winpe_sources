# CTSF30Base::OnTextUpdatingWorker(Windows::UI::Text::Core::ICoreTextEditContext *,Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *)

- ea: `0x1800eb604`
- end: `0x1800eba8e`
- name: `?OnTextUpdatingWorker@CTSF30Base@@QEAAJPEAUICoreTextEditContext@Core@Text@UI@Windows@@PEAUICoreTextTextUpdatingEventArgs@3456@@Z`
- size: `1162`
- prototype: `__int64 __fastcall(CTSF30Base *__hidden this, struct Windows::UI::Text::Core::ICoreTextEditContext *, struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800eb530`

## callees

- `0x180043e7c`
- `0x1800440f0`
- `0x18009cae8`
- `0x1800eb604`
- `0x1800eba94`
- `0x18013dcce`
- `0x18014948c`
- `0x18016de9c`
- `0x18017a100`
- `0x18027f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb74b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800eb74b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb66b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb89e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb66b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800eb89e`

## pseudocode

```c
__int64 __fastcall CTSF30Base::OnTextUpdatingWorker(
        CTSF30Base *this,
        struct Windows::UI::Text::Core::ICoreTextEditContext *a2,
        struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *a3)
{
  int v4; // r15d
  __int64 v5; // r8
  __int64 (__fastcall *v7)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *); // rax
  int v8; // esi
  __int64 (__fastcall *v9)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, HSTRING *); // rbx
  char v10; // r13
  _QWORD *v11; // rbx
  __int64 v12; // rdx
  CTxtEdit *v13; // rcx
  struct CTxtStory *ActiveStory; // rax
  unsigned __int16 *v15; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int v17; // r14d
  int v18; // r13d
  int v19; // ecx
  int v20; // edx
  int v21; // esi
  _QWORD *v22; // rcx
  _QWORD *v23; // rcx
  __int64 result; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  CTxtEdit *v28; // rcx
  int v29; // eax
  const unsigned __int16 **v30; // r14
  Resp::BStrHolder *v31; // rcx
  int v32; // r15d
  __int64 v33; // [rsp+30h] [rbp-30h] BYREF
  _QWORD *v34; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+40h] [rbp-20h] BYREF
  __int64 v36; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v37; // [rsp+50h] [rbp-10h] BYREF
  int v38; // [rsp+A0h] [rbp+40h] BYREF
  struct Windows::UI::Text::Core::ICoreTextEditContext *length; // [rsp+A8h] [rbp+48h] BYREF
  int v40; // [rsp+B8h] [rbp+58h] BYREF

  length = a2;
  *((_BYTE *)this + 112) = 1;
  v4 = 0;
  v5 = *(_QWORD *)a3;
  if ( (*(_BYTE *)(*((_QWORD *)this + 13) + 176LL) & 4) != 0 )
  {
    result = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64))(v5 + 88))(
               a3,
               1);
    goto LABEL_37;
  }
  v7 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *))(v5 + 48);
  v33 = 0;
  string = 0;
  v8 = v7(a3, &v33);
  if ( v8 >= 0 )
  {
    v9 = *(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, HSTRING *))(*(_QWORD *)a3 + 56LL);
    WindowsDeleteString(string);
    string = 0;
    v8 = v9(a3, &string);
  }
  v37 = 0;
  v10 = 0;
  v34 = 0;
  if ( v8 >= 0 )
  {
    if ( *((_BYTE *)this + 116)
      || ((*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 304LL))(
            *((_QWORD *)this + 13) + 16LL,
            &v34),
          (v11 = v34) == 0) )
    {
      v12 = (unsigned int)v33;
    }
    else
    {
      v38 = -1;
      v40 = -1;
      (*(void (__fastcall **)(_QWORD *, int *))(*v34 + 112LL))(v34, &v38);
      (*(void (__fastcall **)(_QWORD *, int *))(*v11 + 128LL))(v11, &v40);
      v12 = (unsigned int)v33;
      if ( __PAIR64__(v40, v38) == v33 )
      {
        v10 = 1;
        goto LABEL_9;
      }
    }
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 424LL))(
      *((_QWORD *)this + 13) + 16LL,
      v12,
      HIDWORD(v33),
      &v37);
  }
LABEL_9:
  v13 = (CTxtEdit *)*((_QWORD *)this + 13);
  if ( (*((_BYTE *)v13 + 176) & 1) != 0 )
  {
    ActiveStory = CTxtEdit::GetActiveStory(v13);
    if ( *((_DWORD *)ActiveStory + 10) <= SHIDWORD(v33) )
      --HIDWORD(v33);
  }
  LODWORD(length) = 0;
  v15 = 0;
  if ( v8 < 0 )
    goto LABEL_15;
  StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
  v15 = CW32System::SysAllocStringLen(StringRawBuffer, (unsigned int)length);
  if ( !v15 )
  {
    v8 = -2147024882;
    goto LABEL_15;
  }
  if ( !*((_BYTE *)this + 116) )
  {
LABEL_40:
    if ( v10 )
    {
      v25 = v34;
      v26 = *v34;
      if ( *v15 )
      {
        v27 = (*(__int64 (__fastcall **)(_QWORD *, unsigned __int16 *))(v26 + 536))(v34, v15);
LABEL_43:
        v8 = v27;
        goto LABEL_15;
      }
    }
    else
    {
      v25 = v37;
      v26 = *v37;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD *, __int64, unsigned __int16 *))(v26 + 824))(v25, 96, v15);
    goto LABEL_43;
  }
  v29 = *((_DWORD *)this + 32);
  v30 = (const unsigned __int16 **)((char *)this + 144);
  v31 = (CTSF30Base *)((char *)this + 144);
  if ( v29 == 0x3FFFFFFF )
  {
    *((_DWORD *)this + 32) = v33;
    v8 = Resp::BStrHolder::HrCopyWz(v31, v15);
    if ( v8 >= 0 )
      goto LABEL_40;
  }
  else
  {
    v32 = v33 - v29;
    v8 = CW32System::SysReAllocStringLen((unsigned __int16 **)v31, *v30, (int)v33 - v29 + (int)length);
    if ( v8 >= 0 )
    {
      if ( *v30 )
      {
        memcpy_0((void *)&(*v30)[v32], v15, 2LL * (unsigned int)length);
        v4 = 0;
        goto LABEL_40;
      }
      v8 = -2147024882;
    }
    v4 = 0;
  }
LABEL_15:
  v17 = 0x3FFFFFFF;
  v18 = 0;
  if ( *((_BYTE *)this + 169) && !*((_BYTE *)this + 168) )
  {
    v17 = *((_DWORD *)this + 44);
    if ( v17 == 0x3FFFFFFF )
    {
      v19 = 0;
      v20 = 0;
    }
    else
    {
      v19 = *((_DWORD *)this + 45) - v17;
      v20 = v19 + *((_DWORD *)this + 46);
      *((_DWORD *)this + 44) = 0x3FFFFFFF;
    }
    v4 = v17 + v19;
    v18 = v17 + v20;
  }
  *((_BYTE *)this + 169) = 0;
  if ( v8 >= 0 )
  {
    v8 = 0;
    if ( v17 == 0x3FFFFFFF )
      v8 = -2147418113;
  }
  v36 = 0;
  if ( v8 < 0 )
    goto LABEL_44;
  if ( !v34 )
    (*(void (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)(*((_QWORD *)this + 13) + 16LL) + 304LL))(
      *((_QWORD *)this + 13) + 16LL,
      &v34);
  v21 = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64 *))(*(_QWORD *)a3 + 64LL))(
          a3,
          &v36);
  if ( v21 < 0 )
  {
LABEL_44:
    v21 = (*(__int64 (__fastcall **)(struct Windows::UI::Text::Core::ICoreTextTextUpdatingEventArgs *, __int64))(*(_QWORD *)a3 + 88LL))(
            a3,
            1);
  }
  else if ( v18 - v4 == (_DWORD)v33 + (_DWORD)length - HIDWORD(v33) && __PAIR64__(v4, v17) == v33 )
  {
    (*(void (__fastcall **)(_QWORD *, _QWORD, _QWORD))(*v34 + 224LL))(v34, (unsigned int)v36, HIDWORD(v36));
    if ( *((_BYTE *)this + 116) )
    {
      v28 = (CTxtEdit *)*((_QWORD *)this + 13);
      if ( *((_QWORD *)v28 + 64) )
        CTxtEdit::RaiseUiaTextEditTextChangedEvent(
          v28,
          TextEditChangeType_Composition,
          *((const unsigned __int16 **)this + 18));
    }
  }
  else
  {
    CTSF30Base::SendTextChangedNotification(this, v17, v4 - v17, v18 - v17);
  }
  if ( v15 )
    CW32System::SysFreeString(v15);
  v22 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v22 + 16LL))(v22);
  }
  v23 = v37;
  if ( v37 )
  {
    v37 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
  }
  WindowsDeleteString(string);
  result = (unsigned int)v21;
LABEL_37:
  *((_BYTE *)this + 112) = 0;
  return result;
}

```

## disassembly

```asm
0x1800eb604  mov     [rsp-38h+arg_10], rbx
0x1800eb609  mov     [rsp-38h+length], rdx
0x1800eb60e  push    rbp
0x1800eb60f  push    rsi
0x1800eb610  push    rdi
0x1800eb611  push    r12
0x1800eb613  push    r13
0x1800eb615  push    r14
0x1800eb617  push    r15
0x1800eb619  mov     rbp, rsp
0x1800eb61c  sub     rsp, 60h
0x1800eb620  mov     byte ptr [rcx+70h], 1
0x1800eb624  mov     r12, r8
0x1800eb627  mov     rax, [rcx+68h]
0x1800eb62b  xor     r15d, r15d
0x1800eb62e  mov     r8, [r8]
0x1800eb631  mov     rdi, rcx
0x1800eb634  mov     rcx, r12
0x1800eb637  test    byte ptr [rax+0B0h], 4
0x1800eb63e  jnz     loc_1800EB9E8
0x1800eb644  mov     rax, [r8+30h]
0x1800eb648  lea     rdx, [rbp+var_30]
0x1800eb64c  mov     [rbp+var_30], r15
0x1800eb650  mov     [rbp+string], r15
0x1800eb654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb659  mov     esi, eax
0x1800eb65b  test    eax, eax
0x1800eb65d  js      short loc_1800EB68C
0x1800eb65f  mov     rax, [r12]
0x1800eb663  mov     rcx, [rbp+string]; string
0x1800eb667  mov     rbx, [rax+38h]
0x1800eb66b  call    cs:__imp_WindowsDeleteString
0x1800eb672  nop     dword ptr [rax+rax+00h]
0x1800eb677  lea     rdx, [rbp+string]
0x1800eb67b  mov     [rbp+string], r15
0x1800eb67f  mov     rcx, r12
0x1800eb682  mov     rax, rbx
0x1800eb685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb68a  mov     esi, eax
0x1800eb68c  mov     [rbp+var_10], r15
0x1800eb690  mov     r13b, r15b
0x1800eb693  mov     [rbp+var_28], r15
0x1800eb697  test    esi, esi
0x1800eb699  js      short loc_1800EB71A
0x1800eb69b  cmp     [rdi+74h], r15b
0x1800eb69f  jnz     loc_1800EB950
0x1800eb6a5  mov     rcx, [rdi+68h]
0x1800eb6a9  lea     rdx, [rbp+var_28]
0x1800eb6ad  add     rcx, 10h
0x1800eb6b1  mov     rax, [rcx]
0x1800eb6b4  mov     rax, [rax+130h]
0x1800eb6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6c0  mov     rbx, [rbp+var_28]
0x1800eb6c4  test    rbx, rbx
0x1800eb6c7  jz      loc_1800EB950
0x1800eb6cd  or      eax, 0FFFFFFFFh
0x1800eb6d0  lea     rdx, [rbp+arg_0]
0x1800eb6d4  mov     [rbp+arg_0], eax
0x1800eb6d7  mov     rcx, rbx
0x1800eb6da  mov     [rbp+arg_18], eax
0x1800eb6dd  mov     rax, [rbx]
0x1800eb6e0  mov     rax, [rax+70h]
0x1800eb6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6e9  mov     rax, [rbx]
0x1800eb6ec  lea     rdx, [rbp+arg_18]
0x1800eb6f0  mov     rcx, rbx
0x1800eb6f3  mov     rax, [rax+80h]
0x1800eb6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb6ff  mov     edx, dword ptr [rbp+var_30]
0x1800eb702  cmp     [rbp+arg_0], edx
0x1800eb705  jnz     loc_1800EB953
0x1800eb70b  mov     eax, dword ptr [rbp+var_30+4]
0x1800eb70e  cmp     [rbp+arg_18], eax
0x1800eb711  jnz     loc_1800EB953
0x1800eb717  mov     r13b, 1
0x1800eb71a  mov     rcx, [rdi+68h]; this
0x1800eb71e  test    byte ptr [rcx+0B0h], 1
0x1800eb725  jz      short loc_1800EB738
0x1800eb727  call    ?GetActiveStory@CTxtEdit@@QEAAPEAVCTxtStory@@XZ; CTxtEdit::GetActiveStory(void)
0x1800eb72c  mov     ecx, dword ptr [rbp+var_30+4]
0x1800eb72f  cmp     [rax+28h], ecx
0x1800eb732  jle     loc_1800EB9FB
0x1800eb738  mov     dword ptr [rbp+length], r15d
0x1800eb73c  mov     rbx, r15
0x1800eb73f  test    esi, esi
0x1800eb741  js      short loc_1800EB773
0x1800eb743  mov     rcx, [rbp+string]; string
0x1800eb747  lea     rdx, [rbp+length]; length
0x1800eb74b  call    cs:__imp_WindowsGetStringRawBuffer
0x1800eb752  nop     dword ptr [rax+rax+00h]
0x1800eb757  mov     edx, dword ptr [rbp+length]; unsigned int
0x1800eb75a  mov     rcx, rax; unsigned __int16 *
0x1800eb75d  call    ?SysAllocStringLen@CW32System@@SAPEAGPEBGI@Z; CW32System::SysAllocStringLen(ushort const *,uint)
0x1800eb762  mov     rbx, rax
0x1800eb765  test    rax, rax
0x1800eb768  jnz     loc_1800EB8F2
0x1800eb76e  mov     esi, 8007000Eh
0x1800eb773  xor     r8d, r8d
0x1800eb776  mov     r9d, 3FFFFFFFh
0x1800eb77c  mov     r14d, r9d
0x1800eb77f  mov     r13d, r8d
0x1800eb782  cmp     [rdi+0A9h], r8b
0x1800eb789  jz      short loc_1800EB7C4
0x1800eb78b  cmp     [rdi+0A8h], r8b
0x1800eb792  jnz     short loc_1800EB7C4
0x1800eb794  mov     r14d, [rdi+0B0h]
0x1800eb79b  cmp     r14d, r9d
0x1800eb79e  jz      loc_1800EB945
0x1800eb7a4  mov     ecx, [rdi+0B4h]
0x1800eb7aa  mov     edx, [rdi+0B8h]
0x1800eb7b0  sub     ecx, r14d
0x1800eb7b3  add     edx, ecx
0x1800eb7b5  mov     [rdi+0B0h], r9d
0x1800eb7bc  lea     r15d, [r14+rcx]
0x1800eb7c0  lea     r13d, [r14+rdx]
0x1800eb7c4  mov     [rdi+0A9h], r8b
0x1800eb7cb  test    esi, esi
0x1800eb7cd  js      short loc_1800EB7DD
0x1800eb7cf  cmp     r14d, r9d
0x1800eb7d2  mov     esi, r8d
0x1800eb7d5  mov     eax, 8000FFFFh
0x1800eb7da  cmovz   esi, eax
0x1800eb7dd  mov     [rbp+var_18], r8
0x1800eb7e1  test    esi, esi
0x1800eb7e3  js      loc_1800EB92C
0x1800eb7e9  cmp     [rbp+var_28], r8
0x1800eb7ed  jz      loc_1800EBA6E
0x1800eb7f3  mov     rax, [r12]
0x1800eb7f7  lea     rdx, [rbp+var_18]
0x1800eb7fb  mov     rcx, r12
0x1800eb7fe  mov     rax, [rax+40h]
0x1800eb802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb807  mov     esi, eax
0x1800eb809  test    eax, eax
0x1800eb80b  js      loc_1800EB92C
0x1800eb811  mov     edx, dword ptr [rbp+length]
0x1800eb814  mov     ecx, r13d
0x1800eb817  sub     edx, dword ptr [rbp+var_30+4]
0x1800eb81a  sub     ecx, r15d
0x1800eb81d  add     edx, dword ptr [rbp+var_30]
0x1800eb820  cmp     ecx, edx
0x1800eb822  jnz     loc_1800EB8D3
0x1800eb828  cmp     r14d, dword ptr [rbp+var_30]
0x1800eb82c  jnz     loc_1800EB8D3
0x1800eb832  cmp     r15d, dword ptr [rbp+var_30+4]
0x1800eb836  jnz     loc_1800EB8D3
0x1800eb83c  mov     rcx, [rbp+var_28]
0x1800eb840  mov     r8d, dword ptr [rbp+var_18+4]
0x1800eb844  mov     edx, dword ptr [rbp+var_18]
0x1800eb847  mov     rax, [rcx]
0x1800eb84a  mov     rax, [rax+0E0h]
0x1800eb851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb856  xor     r15d, r15d
0x1800eb859  cmp     [rdi+74h], r15b
0x1800eb85d  jnz     loc_1800EB9C1
0x1800eb863  test    rbx, rbx
0x1800eb866  jnz     short loc_1800EB8C9
0x1800eb868  mov     rcx, [rbp+var_28]
0x1800eb86c  test    rcx, rcx
0x1800eb86f  jz      short loc_1800EB881
0x1800eb871  mov     [rbp+var_28], r15
0x1800eb875  mov     rax, [rcx]
0x1800eb878  mov     rax, [rax+10h]
0x1800eb87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb881  mov     rcx, [rbp+var_10]
0x1800eb885  test    rcx, rcx
0x1800eb888  jz      short loc_1800EB89A
0x1800eb88a  mov     [rbp+var_10], r15
0x1800eb88e  mov     rax, [rcx]
0x1800eb891  mov     rax, [rax+10h]
0x1800eb895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb89a  mov     rcx, [rbp+string]; string
0x1800eb89e  call    cs:__imp_WindowsDeleteString
0x1800eb8a5  nop     dword ptr [rax+rax+00h]
0x1800eb8aa  mov     eax, esi
0x1800eb8ac  mov     rbx, [rsp+60h+arg_10]
0x1800eb8b4  mov     [rdi+70h], r15b
0x1800eb8b8  add     rsp, 60h
0x1800eb8bc  pop     r15
0x1800eb8be  pop     r14
0x1800eb8c0  pop     r13
0x1800eb8c2  pop     r12
0x1800eb8c4  pop     rdi
0x1800eb8c5  pop     rsi
0x1800eb8c6  pop     rbp
0x1800eb8c7  retn
0x1800eb8c9  mov     rcx, rbx; unsigned __int16 *
0x1800eb8cc  call    ?SysFreeString@CW32System@@SAXPEAG@Z; CW32System::SysFreeString(ushort *)
0x1800eb8d1  jmp     short loc_1800EB868
0x1800eb8d3  sub     r13d, r14d
0x1800eb8d6  sub     r15d, r14d
0x1800eb8d9  mov     r9d, r13d; int
0x1800eb8dc  mov     r8d, r15d; int
0x1800eb8df  mov     edx, r14d; int
0x1800eb8e2  mov     rcx, rdi; this
0x1800eb8e5  call    ?SendTextChangedNotification@CTSF30Base@@AEAAXJJJ@Z; CTSF30Base::SendTextChangedNotification(long,long,long)
0x1800eb8ea  xor     r15d, r15d
0x1800eb8ed  jmp     loc_1800EB863
0x1800eb8f2  cmp     [rdi+74h], r15b
0x1800eb8f6  jnz     loc_1800EBA03
0x1800eb8fc  test    r13b, r13b
0x1800eb8ff  jz      loc_1800EBA4E
0x1800eb905  mov     rcx, [rbp+var_28]
0x1800eb909  mov     rax, [rcx]
0x1800eb90c  cmp     [rbx], r15w
0x1800eb910  jz      loc_1800EBA55
0x1800eb916  mov     rax, [rax+218h]
0x1800eb91d  mov     rdx, rbx
0x1800eb920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb925  mov     esi, eax
0x1800eb927  jmp     loc_1800EB773
0x1800eb92c  mov     rax, [r12]
0x1800eb930  mov     edx, 1
0x1800eb935  mov     rcx, r12
0x1800eb938  mov     rax, [rax+58h]
0x1800eb93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb941  mov     esi, eax
0x1800eb943  jmp     short loc_1800EB8EA
0x1800eb945  mov     ecx, r8d
0x1800eb948  mov     edx, r8d
0x1800eb94b  jmp     loc_1800EB7BC
0x1800eb950  mov     edx, dword ptr [rbp+var_30]
0x1800eb953  mov     rcx, [rdi+68h]
0x1800eb957  lea     r9, [rbp+var_10]
0x1800eb95b  mov     r8d, dword ptr [rbp+var_30+4]
0x1800eb95f  add     rcx, 10h
0x1800eb963  mov     rax, [rcx]
0x1800eb966  mov     rax, [rax+1A8h]
0x1800eb96d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb972  jmp     loc_1800EB71A
0x1800eb977  mov     eax, dword ptr [rbp+var_30]
0x1800eb97a  mov     rdx, rbx; unsigned __int16 *
0x1800eb97d  mov     [rdi+80h], eax
0x1800eb983  call    ?HrCopyWz@BStrHolder@Resp@@QEAAJPEBG@Z; Resp::BStrHolder::HrCopyWz(ushort const *)
0x1800eb988  mov     esi, eax
0x1800eb98a  test    eax, eax
0x1800eb98c  jns     loc_1800EB8FC
0x1800eb992  jmp     loc_1800EB773
0x1800eb997  cmp     [r14], rax
0x1800eb99a  jz      loc_1800EBA41
0x1800eb9a0  mov     rax, [r14]
0x1800eb9a3  mov     rdx, rbx; Src
0x1800eb9a6  mov     r8d, dword ptr [rbp+length]
0x1800eb9aa  movsxd  rcx, r15d
0x1800eb9ad  add     r8, r8; Size
0x1800eb9b0  lea     rcx, [rax+rcx*2]; void *
0x1800eb9b4  call    memcpy_0
0x1800eb9b9  xor     r15d, r15d
0x1800eb9bc  jmp     loc_1800EB8FC
0x1800eb9c1  mov     rcx, [rdi+68h]; this
0x1800eb9c5  cmp     [rcx+200h], r15
0x1800eb9cc  jz      loc_1800EB863
0x1800eb9d2  mov     r8, [rdi+90h]; unsigned __int16 *
0x1800eb9d9  mov     edx, 2; enum TextEditChangeType
0x1800eb9de  call    ?RaiseUiaTextEditTextChangedEvent@CTxtEdit@@QEAAXW4TextEditChangeType@@PEBG@Z; CTxtEdit::RaiseUiaTextEditTextChangedEvent(TextEditChangeType,ushort const *)
0x1800eb9e3  jmp     loc_1800EB863
0x1800eb9e8  mov     rax, [r8+58h]
0x1800eb9ec  mov     edx, 1
0x1800eb9f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eb9f6  jmp     loc_1800EB8AC
0x1800eb9fb  dec     dword ptr [rbp+var_30+4]
0x1800eb9fe  jmp     loc_1800EB738
0x1800eba03  mov     eax, [rdi+80h]
0x1800eba09  lea     r14, [rdi+90h]
0x1800eba10  mov     rcx, r14; unsigned __int16 **
0x1800eba13  cmp     eax, 3FFFFFFFh
0x1800eba18  jz      loc_1800EB977
0x1800eba1e  mov     r15d, dword ptr [rbp+var_30]
0x1800eba22  mov     r8d, dword ptr [rbp+length]
0x1800eba26  sub     r15d, eax
0x1800eba29  mov     rdx, [r14]; unsigned __int16 *
0x1800eba2c  add     r8d, r15d; unsigned int
0x1800eba2f  call    ?SysReAllocStringLen@CW32System@@SAHPEAPEAGPEBGI@Z; CW32System::SysReAllocStringLen(ushort * *,ushort const *,uint)
0x1800eba34  mov     esi, eax
0x1800eba36  xor     eax, eax
0x1800eba38  test    esi, esi
0x1800eba3a  js      short loc_1800EBA46
0x1800eba3c  jmp     loc_1800EB997
0x1800eba41  mov     esi, 8007000Eh
0x1800eba46  xor     r15d, r15d
0x1800eba49  jmp     loc_1800EB773
0x1800eba4e  mov     rcx, [rbp+var_10]
0x1800eba52  mov     rax, [rcx]
0x1800eba55  mov     rax, [rax+338h]
0x1800eba5c  mov     r8, rbx
0x1800eba5f  mov     edx, 60h ; '`'
0x1800eba64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eba69  jmp     loc_1800EB925
0x1800eba6e  mov     rcx, [rdi+68h]
0x1800eba72  lea     rdx, [rbp+var_28]
0x1800eba76  add     rcx, 10h
0x1800eba7a  mov     rax, [rcx]
0x1800eba7d  mov     rax, [rax+130h]
0x1800eba84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800eba89  jmp     loc_1800EB7F3
```
