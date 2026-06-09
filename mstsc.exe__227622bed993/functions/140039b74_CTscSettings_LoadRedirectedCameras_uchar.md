# CTscSettings::LoadRedirectedCameras(uchar)

- ea: `0x140039b74`
- end: `0x14003a122`
- name: `?LoadRedirectedCameras@CTscSettings@@AEAAJE@Z`
- size: `1454`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14003a128`

## callees

- `0x140003b14`
- `0x140003b20`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cffc`
- `0x14000d078`
- `0x140039b74`
- `0x140040474`
- `0x140112010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x140039df2`
- `msvcrt!wcstok_s` at `0x140039e50`
- `msvcrt!wcstok_s` at `0x140039f22`
- `msvcrt!wcstok_s` at `0x140039df2`
- `msvcrt!wcstok_s` at `0x140039e50`
- `msvcrt!wcstok_s` at `0x140039f22`
- `KERNEL32!CompareStringOrdinal` at `0x140039e22`
- `KERNEL32!CompareStringOrdinal` at `0x140039eba`
- `KERNEL32!CompareStringOrdinal` at `0x140039e22`
- `KERNEL32!CompareStringOrdinal` at `0x140039eba`
- `OLEAUT32!__imp_SysAllocString` at `0x140039ee0`
- `OLEAUT32!__imp_SysAllocString` at `0x140039ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x140039f12`
- `OLEAUT32!__imp_SysFreeString` at `0x140039f86`
- `OLEAUT32!__imp_SysFreeString` at `0x140039f12`
- `OLEAUT32!__imp_SysFreeString` at `0x140039f86`

## string_xrefs

- `0x140039ddb`: `StringCchCopy failed`
- `0x140039c99`: `spRdpNonScript->get_CameraRedirConfigCollection failed`
- `0x140039e90`: `spConfigCollection->put_RedirectByDefault failed`
- `0x14003a040`: `spConfigCollection->put_EncodeVideo failed`
- `0x140039f54`: `spConfigCollection->AddConfig failed`
- `0x14003a0a5`: `spConfigCollection->put_EncodingQuality failed`

## pseudocode

```c
__int64 __fastcall CTscSettings::LoadRedirectedCameras(CTscSettings *this, char a2)
{
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  int v5; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v7; // edx
  const char *v8; // rcx
  unsigned int v9; // edi
  unsigned __int64 v10; // rbx
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r12
  unsigned int v13; // eax
  unsigned int v14; // eax
  int v15; // edx
  const char *v16; // rcx
  __int64 v17; // rdx
  wchar_t *v18; // rbx
  WCHAR v19; // ax
  unsigned __int16 v20; // r15
  OLECHAR *v21; // r14
  unsigned int v22; // eax
  unsigned int v23; // eax
  int v24; // ecx
  int v25; // ecx
  __int64 v26; // rcx
  __int64 v27; // rcx
  wchar_t *Context; // [rsp+30h] [rbp-10h] BYREF
  unsigned __int64 v30; // [rsp+38h] [rbp-8h] BYREF
  int Delimiter; // [rsp+80h] [rbp+40h] BYREF
  __int64 v32; // [rsp+90h] [rbp+50h] BYREF
  __int64 v33; // [rsp+98h] [rbp+58h] BYREF

  v33 = 0;
  v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 27150);
  v32 = 0;
  wcscpy((wchar_t *)&Delimiter, L";");
  Context = 0;
  v30 = 0;
  if ( !v3 )
  {
    v5 = 1;
    goto LABEL_75;
  }
  v5 = (**v3)(v3, &IID_IMsRdpClientNonScriptable7, &v33);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v7 = 423;
      v8 = "QI for IMsRdpClientNonScriptable7 failed!";
LABEL_8:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v8,
        v5);
      goto LABEL_75;
    }
    goto LABEL_75;
  }
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 536LL))(v33, &v32);
  if ( v5 >= 0 )
  {
    if ( !v32 )
      goto LABEL_75;
    v5 = StringCchLengthW((const unsigned __int16 *)this + 26222, 0x400u, &v30);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v7 = 425;
        v8 = "StringCchLength failed";
        goto LABEL_8;
      }
      goto LABEL_75;
    }
    v9 = 1;
    v10 = v30 + 1;
    v11 = (unsigned __int16 *)operator new[](saturated_mul(v30 + 1, 2u));
    v12 = v11;
    if ( !v11 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v13 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Ds(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          426,
          (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
          v13,
          (__int64)"TCHAR[]");
      }
      v5 = -2147024882;
      goto LABEL_75;
    }
    v5 = StringCchCopyW(v11, v10, (const unsigned __int16 *)this + 26222);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_74;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 427;
      v16 = "StringCchCopy failed";
LABEL_73:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
        v14,
        (__int64)v16,
        v5);
LABEL_74:
      operator delete(v12);
      goto LABEL_75;
    }
    v18 = wcstok_s(v12, (const wchar_t *)&Delimiter, &Context);
    if ( a2 )
    {
      while ( v18 )
      {
        if ( CompareStringOrdinal(v18, -1, L"*", -1, 1) == 2 )
        {
          v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 72LL))(v32, 0xFFFFFFFFLL);
          if ( v5 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v14 = RdpWppGetCurrentThreadActivityIdPrefix();
              v15 = 428;
              v16 = "spConfigCollection->put_RedirectByDefault failed";
              goto LABEL_73;
            }
            goto LABEL_74;
          }
        }
        v18 = wcstok_s(0, (const wchar_t *)&Delimiter, &Context);
      }
    }
    else
    {
      while ( v18 )
      {
        if ( CompareStringOrdinal(v18, -1, L"*", -1, 1) != 2 )
        {
          v19 = *v18;
          if ( *v18 == 45 )
            ++v18;
          v20 = -(v19 != 45);
          v21 = SysAllocString(v18);
          if ( !v21 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v23 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_Ds(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                429,
                (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
                v23,
                (__int64)"BSTR");
            }
            v5 = -2147024882;
            goto LABEL_74;
          }
          v5 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD))(*(_QWORD *)v32 + 64LL))(v32, v21, v20);
          if ( v5 < 0 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v22 = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                430,
                (unsigned int)WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids,
                v22,
                (__int64)"spConfigCollection->AddConfig failed",
                v5);
            }
            SysFreeString(v21);
            goto LABEL_74;
          }
          SysFreeString(v21);
        }
        v18 = wcstok_s(0, (const wchar_t *)&Delimiter, &Context);
      }
    }
    LOWORD(v17) = -(*((_DWORD *)this + 13623) != 0);
    v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v32 + 88LL))(v32, v17);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_74;
      }
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      v15 = 431;
      v16 = "spConfigCollection->put_EncodeVideo failed";
      goto LABEL_73;
    }
    v24 = *((_DWORD *)this + 13624);
    if ( !v24 )
      goto LABEL_67;
    v25 = v24 - 1;
    if ( !v25 )
      goto LABEL_68;
    if ( v25 == 1 )
      v9 = 2;
    else
LABEL_67:
      v9 = 0;
LABEL_68:
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v32 + 104LL))(v32, v9);
    if ( v5 >= 0
      || WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_74;
    }
    v14 = RdpWppGetCurrentThreadActivityIdPrefix();
    v15 = 432;
    v16 = "spConfigCollection->put_EncodingQuality failed";
    goto LABEL_73;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v7 = 424;
    v8 = "spRdpNonScript->get_CameraRedirConfigCollection failed";
    goto LABEL_8;
  }
LABEL_75:
  v26 = v32;
  if ( v32 )
  {
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140039b74  push    rbp
0x140039b76  push    rbx
0x140039b77  push    rsi
0x140039b78  push    rdi
0x140039b79  push    r12
0x140039b7b  push    r14
0x140039b7d  push    r15
0x140039b7f  mov     rbp, rsp
0x140039b82  sub     rsp, 40h
0x140039b86  mov     rsi, rcx
0x140039b89  mov     [rbp+arg_18], 0
0x140039b91  mov     rcx, [rcx+35070h]
0x140039b98  mov     r15b, dl
0x140039b9b  mov     [rbp+arg_10], 0
0x140039ba3  mov     [rbp+Delimiter], 3Bh ; ';'
0x140039baa  mov     [rbp+Context], 0
0x140039bb2  mov     [rbp+var_8], 0
0x140039bba  test    rcx, rcx
0x140039bbd  jnz     short loc_140039BC7
0x140039bbf  lea     ebx, [rcx+1]
0x140039bc2  jmp     loc_14003A0D7
0x140039bc7  mov     rax, [rcx]
0x140039bca  lea     r8, [rbp+arg_18]
0x140039bce  lea     rdx, IID_IMsRdpClientNonScriptable7
0x140039bd5  mov     rax, [rax]
0x140039bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039bdd  mov     ebx, eax
0x140039bdf  test    eax, eax
0x140039be1  jns     short loc_140039C47
0x140039be3  mov     rcx, cs:WPP_GLOBAL_Control
0x140039bea  lea     rax, WPP_GLOBAL_Control
0x140039bf1  cmp     rcx, rax
0x140039bf4  jz      loc_14003A0D7
0x140039bfa  test    byte ptr [rcx+1Ch], 8
0x140039bfe  jz      loc_14003A0D7
0x140039c04  cmp     byte ptr [rcx+19h], 2
0x140039c08  jb      loc_14003A0D7
0x140039c0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039c13  mov     edx, 1A7h
0x140039c18  lea     rcx, aQiForImsrdpcli; "QI for IMsRdpClientNonScriptable7 faile"...
0x140039c1f  mov     [rsp+40h+var_18], ebx
0x140039c23  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140039c2a  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x140039c2f  mov     r9d, eax
0x140039c32  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c39  mov     rcx, [rcx+10h]
0x140039c3d  call    WPP_SF_DsD
0x140039c42  jmp     loc_14003A0D7
0x140039c47  mov     rcx, [rbp+arg_18]
0x140039c4b  lea     rdx, [rbp+arg_10]
0x140039c4f  mov     rax, [rcx]
0x140039c52  mov     rax, [rax+218h]
0x140039c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039c5e  mov     ebx, eax
0x140039c60  test    eax, eax
0x140039c62  jns     short loc_140039CA5
0x140039c64  mov     rcx, cs:WPP_GLOBAL_Control
0x140039c6b  lea     rax, WPP_GLOBAL_Control
0x140039c72  cmp     rcx, rax
0x140039c75  jz      loc_14003A0D7
0x140039c7b  test    byte ptr [rcx+1Ch], 8
0x140039c7f  jz      loc_14003A0D7
0x140039c85  cmp     byte ptr [rcx+19h], 2
0x140039c89  jb      loc_14003A0D7
0x140039c8f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039c94  mov     edx, 1A8h
0x140039c99  lea     rcx, aSprdpnonscript; "spRdpNonScript->get_CameraRedirConfigCo"...
0x140039ca0  jmp     loc_140039C1F
0x140039ca5  cmp     [rbp+arg_10], 0
0x140039caa  jz      loc_14003A0D7
0x140039cb0  lea     r14, [rsi+0CCDCh]
0x140039cb7  mov     edx, 400h; unsigned __int64
0x140039cbc  mov     rcx, r14; unsigned __int16 *
0x140039cbf  lea     r8, [rbp+var_8]; unsigned __int64 *
0x140039cc3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x140039cc8  mov     ebx, eax
0x140039cca  test    eax, eax
0x140039ccc  jns     short loc_140039D0F
0x140039cce  mov     rcx, cs:WPP_GLOBAL_Control
0x140039cd5  lea     rax, WPP_GLOBAL_Control
0x140039cdc  cmp     rcx, rax
0x140039cdf  jz      loc_14003A0D7
0x140039ce5  test    byte ptr [rcx+1Ch], 8
0x140039ce9  jz      loc_14003A0D7
0x140039cef  cmp     byte ptr [rcx+19h], 2
0x140039cf3  jb      loc_14003A0D7
0x140039cf9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039cfe  mov     edx, 1A9h
0x140039d03  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x140039d0a  jmp     loc_140039C1F
0x140039d0f  mov     rbx, [rbp+var_8]
0x140039d13  mov     edi, 1
0x140039d18  add     rbx, rdi
0x140039d1b  lea     rcx, [rdi-2]
0x140039d1f  lea     eax, [rdi+1]
0x140039d22  mul     rbx
0x140039d25  cmovb   rax, rcx
0x140039d29  mov     rcx, rax; unsigned __int64
0x140039d2c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x140039d31  mov     r12, rax
0x140039d34  test    rax, rax
0x140039d37  jnz     short loc_140039D92
0x140039d39  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d40  lea     rax, WPP_GLOBAL_Control
0x140039d47  cmp     rcx, rax
0x140039d4a  jz      short loc_140039D88
0x140039d4c  test    byte ptr [rcx+1Ch], 8
0x140039d50  jz      short loc_140039D88
0x140039d52  cmp     byte ptr [rcx+19h], 2
0x140039d56  jb      short loc_140039D88
0x140039d58  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039d5d  lea     rcx, aTchar_0; "TCHAR[]"
0x140039d64  mov     edx, 1AAh
0x140039d69  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x140039d6e  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140039d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140039d7c  mov     r9d, eax
0x140039d7f  mov     rcx, [rcx+10h]
0x140039d83  call    WPP_SF_Ds
0x140039d88  mov     ebx, 8007000Eh
0x140039d8d  jmp     loc_14003A0D7
0x140039d92  mov     r8, r14; unsigned __int16 *
0x140039d95  mov     rdx, rbx; unsigned __int64
0x140039d98  mov     rcx, r12; unsigned __int16 *
0x140039d9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140039da0  mov     ebx, eax
0x140039da2  test    eax, eax
0x140039da4  jns     short loc_140039DE7
0x140039da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140039dad  lea     rax, WPP_GLOBAL_Control
0x140039db4  cmp     rcx, rax
0x140039db7  jz      loc_14003A0CF
0x140039dbd  test    byte ptr [rcx+1Ch], 8
0x140039dc1  jz      loc_14003A0CF
0x140039dc7  cmp     byte ptr [rcx+19h], 2
0x140039dcb  jb      loc_14003A0CF
0x140039dd1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039dd6  mov     edx, 1ABh
0x140039ddb  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x140039de2  jmp     loc_14003A0AC
0x140039de7  lea     r8, [rbp+Context]; Context
0x140039deb  mov     rcx, r12; String
0x140039dee  lea     rdx, [rbp+Delimiter]; Delimiter
0x140039df2  call    cs:__imp_wcstok_s
0x140039df8  mov     rbx, rax
0x140039dfb  test    r15b, r15b
0x140039dfe  jz      loc_140039E9C
0x140039e04  test    rbx, rbx
0x140039e07  jz      loc_140039FEA
0x140039e0d  or      r9d, 0FFFFFFFFh; cchCount2
0x140039e11  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x140039e15  or      edx, r9d; cchCount1
0x140039e18  lea     r8, pszMore; "*"
0x140039e1f  mov     rcx, rbx; lpString1
0x140039e22  call    cs:__imp_CompareStringOrdinal
0x140039e28  cmp     eax, 2
0x140039e2b  jnz     short loc_140039E46
0x140039e2d  mov     rcx, [rbp+arg_10]
0x140039e31  or      edx, 0FFFFFFFFh
0x140039e34  mov     rax, [rcx]
0x140039e37  mov     rax, [rax+48h]
0x140039e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039e40  mov     ebx, eax
0x140039e42  test    eax, eax
0x140039e44  js      short loc_140039E5B
0x140039e46  lea     r8, [rbp+Context]; Context
0x140039e4a  xor     ecx, ecx; String
0x140039e4c  lea     rdx, [rbp+Delimiter]; Delimiter
0x140039e50  call    cs:__imp_wcstok_s
0x140039e56  mov     rbx, rax
0x140039e59  jmp     short loc_140039E04
0x140039e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039e62  lea     rax, WPP_GLOBAL_Control
0x140039e69  cmp     rcx, rax
0x140039e6c  jz      loc_14003A0CF
0x140039e72  test    byte ptr [rcx+1Ch], 8
0x140039e76  jz      loc_14003A0CF
0x140039e7c  cmp     byte ptr [rcx+19h], 2
0x140039e80  jb      loc_14003A0CF
0x140039e86  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039e8b  mov     edx, 1ACh
0x140039e90  lea     rcx, aSpconfigcollec; "spConfigCollection->put_RedirectByDefau"...
0x140039e97  jmp     loc_14003A0AC
0x140039e9c  test    rbx, rbx
0x140039e9f  jz      loc_140039FEA
0x140039ea5  or      r9d, 0FFFFFFFFh; cchCount2
0x140039ea9  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x140039ead  or      edx, r9d; cchCount1
0x140039eb0  lea     r8, pszMore; "*"
0x140039eb7  mov     rcx, rbx; lpString1
0x140039eba  call    cs:__imp_CompareStringOrdinal
0x140039ec0  cmp     eax, 2
0x140039ec3  jz      short loc_140039F18
0x140039ec5  movzx   eax, word ptr [rbx]
0x140039ec8  cmp     ax, 2Dh ; '-'
0x140039ecc  jnz     short loc_140039ED2
0x140039ece  add     rbx, 2
0x140039ed2  sub     ax, 2Dh ; '-'
0x140039ed6  mov     rcx, rbx; psz
0x140039ed9  neg     ax
0x140039edc  sbb     r15w, r15w
0x140039ee0  call    cs:__imp_SysAllocString
0x140039ee6  mov     r14, rax
0x140039ee9  test    rax, rax
0x140039eec  jz      loc_140039F91
0x140039ef2  mov     rcx, [rbp+arg_10]
0x140039ef6  movzx   r8d, r15w
0x140039efa  mov     rdx, [rcx]
0x140039efd  mov     rax, [rdx+40h]
0x140039f01  mov     rdx, r14
0x140039f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140039f09  mov     ebx, eax
0x140039f0b  test    eax, eax
0x140039f0d  js      short loc_140039F30
0x140039f0f  mov     rcx, r14; bstrString
0x140039f12  call    cs:__imp_SysFreeString
0x140039f18  lea     r8, [rbp+Context]; Context
0x140039f1c  xor     ecx, ecx; String
0x140039f1e  lea     rdx, [rbp+Delimiter]; Delimiter
0x140039f22  call    cs:__imp_wcstok_s
0x140039f28  mov     rbx, rax
0x140039f2b  jmp     loc_140039E9C
0x140039f30  mov     rcx, cs:WPP_GLOBAL_Control
0x140039f37  lea     rax, WPP_GLOBAL_Control
0x140039f3e  cmp     rcx, rax
0x140039f41  jz      short loc_140039F83
0x140039f43  test    byte ptr [rcx+1Ch], 8
0x140039f47  jz      short loc_140039F83
0x140039f49  cmp     byte ptr [rcx+19h], 2
0x140039f4d  jb      short loc_140039F83
0x140039f4f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039f54  lea     rcx, aSpconfigcollec_4; "spConfigCollection->AddConfig failed"
0x140039f5b  mov     [rsp+40h+var_18], ebx
0x140039f5f  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x140039f64  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140039f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140039f72  mov     edx, 1AEh
0x140039f77  mov     r9d, eax
0x140039f7a  mov     rcx, [rcx+10h]
0x140039f7e  call    WPP_SF_DsD
0x140039f83  mov     rcx, r14; bstrString
0x140039f86  call    cs:__imp_SysFreeString
0x140039f8c  jmp     loc_14003A0CF
0x140039f91  mov     rcx, cs:WPP_GLOBAL_Control
0x140039f98  lea     rax, WPP_GLOBAL_Control
0x140039f9f  cmp     rcx, rax
0x140039fa2  jz      short loc_140039FE0
0x140039fa4  test    byte ptr [rcx+1Ch], 8
0x140039fa8  jz      short loc_140039FE0
0x140039faa  cmp     byte ptr [rcx+19h], 2
0x140039fae  jb      short loc_140039FE0
0x140039fb0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140039fb5  lea     rcx, aBstr; "BSTR"
0x140039fbc  mov     edx, 1ADh
0x140039fc1  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x140039fc6  lea     r8, WPP_1ffab99480f73a0d18cdaa1f0fd20242_Traceguids
0x140039fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140039fd4  mov     r9d, eax
0x140039fd7  mov     rcx, [rcx+10h]
0x140039fdb  call    WPP_SF_Ds
0x140039fe0  mov     ebx, 8007000Eh
0x140039fe5  jmp     loc_14003A0CF
0x140039fea  mov     eax, [rsi+0D4DCh]
0x140039ff0  mov     rcx, [rbp+arg_10]
0x140039ff4  neg     eax
0x140039ff6  sbb     dx, dx
0x140039ff9  mov     r8, [rcx]
0x140039ffc  mov     rax, [r8+58h]
0x14003a000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a005  mov     ebx, eax
0x14003a007  test    eax, eax
0x14003a009  jns     short loc_14003A049
0x14003a00b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003a012  lea     rax, WPP_GLOBAL_Control
0x14003a019  cmp     rcx, rax
0x14003a01c  jz      loc_14003A0CF
0x14003a022  test    byte ptr [rcx+1Ch], 8
0x14003a026  jz      loc_14003A0CF
0x14003a02c  cmp     byte ptr [rcx+19h], 2
0x14003a030  jb      loc_14003A0CF
0x14003a036  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003a03b  mov     edx, 1AFh
0x14003a040  lea     rcx, aSpconfigcollec_3; "spConfigCollection->put_EncodeVideo fai"...
0x14003a047  jmp     short loc_14003A0AC
0x14003a049  mov     ecx, [rsi+0D4E0h]
0x14003a04f  test    ecx, ecx
0x14003a051  jz      short loc_14003A062
0x14003a053  sub     ecx, edi
0x14003a055  jz      short loc_14003A064
0x14003a057  cmp     ecx, edi
0x14003a059  jnz     short loc_14003A062
0x14003a05b  mov     edi, 2
0x14003a060  jmp     short loc_14003A064
0x14003a062  xor     edi, edi
0x14003a064  mov     rcx, [rbp+arg_10]
0x14003a068  mov     edx, edi
0x14003a06a  mov     rax, [rcx]
0x14003a06d  mov     rax, [rax+68h]
0x14003a071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003a076  mov     ebx, eax
  ... truncated ...
```
