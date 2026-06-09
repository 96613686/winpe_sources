# CTscSettings::LoadRedirectedCameras(uchar)

- ea: `0x14003b464`
- end: `0x14003ba12`
- name: `?LoadRedirectedCameras@CTscSettings@@AEAAJE@Z`
- size: `1454`
- prototype: `__int64 __fastcall(CTscSettings *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14003ba18`

## callees

- `0x140003b14`
- `0x140003b20`
- `0x140008a34`
- `0x14000b7d8`
- `0x14000cffc`
- `0x14000d078`
- `0x14003b464`
- `0x140042438`
- `0x140114010`

## import_xrefs

- `msvcrt!wcstok_s` at `0x14003b6e2`
- `msvcrt!wcstok_s` at `0x14003b740`
- `msvcrt!wcstok_s` at `0x14003b812`
- `msvcrt!wcstok_s` at `0x14003b6e2`
- `msvcrt!wcstok_s` at `0x14003b740`
- `msvcrt!wcstok_s` at `0x14003b812`
- `KERNEL32!CompareStringOrdinal` at `0x14003b712`
- `KERNEL32!CompareStringOrdinal` at `0x14003b7aa`
- `KERNEL32!CompareStringOrdinal` at `0x14003b712`
- `KERNEL32!CompareStringOrdinal` at `0x14003b7aa`
- `OLEAUT32!__imp_SysAllocString` at `0x14003b7d0`
- `OLEAUT32!__imp_SysAllocString` at `0x14003b7d0`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b802`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b876`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b802`
- `OLEAUT32!__imp_SysFreeString` at `0x14003b876`

## string_xrefs

- `0x14003b6cb`: `StringCchCopy failed`
- `0x14003b589`: `spRdpNonScript->get_CameraRedirConfigCollection failed`
- `0x14003b780`: `spConfigCollection->put_RedirectByDefault failed`
- `0x14003b930`: `spConfigCollection->put_EncodeVideo failed`
- `0x14003b844`: `spConfigCollection->AddConfig failed`
- `0x14003b995`: `spConfigCollection->put_EncodingQuality failed`

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
        (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
          (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
        (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
                (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
                (unsigned int)WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids,
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
0x14003b464  push    rbp
0x14003b466  push    rbx
0x14003b467  push    rsi
0x14003b468  push    rdi
0x14003b469  push    r12
0x14003b46b  push    r14
0x14003b46d  push    r15
0x14003b46f  mov     rbp, rsp
0x14003b472  sub     rsp, 40h
0x14003b476  mov     rsi, rcx
0x14003b479  mov     [rbp+arg_18], 0
0x14003b481  mov     rcx, [rcx+35070h]
0x14003b488  mov     r15b, dl
0x14003b48b  mov     [rbp+arg_10], 0
0x14003b493  mov     [rbp+Delimiter], 3Bh ; ';'
0x14003b49a  mov     [rbp+Context], 0
0x14003b4a2  mov     [rbp+var_8], 0
0x14003b4aa  test    rcx, rcx
0x14003b4ad  jnz     short loc_14003B4B7
0x14003b4af  lea     ebx, [rcx+1]
0x14003b4b2  jmp     loc_14003B9C7
0x14003b4b7  mov     rax, [rcx]
0x14003b4ba  lea     r8, [rbp+arg_18]
0x14003b4be  lea     rdx, IID_IMsRdpClientNonScriptable7
0x14003b4c5  mov     rax, [rax]
0x14003b4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b4cd  mov     ebx, eax
0x14003b4cf  test    eax, eax
0x14003b4d1  jns     short loc_14003B537
0x14003b4d3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b4da  lea     rax, WPP_GLOBAL_Control
0x14003b4e1  cmp     rcx, rax
0x14003b4e4  jz      loc_14003B9C7
0x14003b4ea  test    byte ptr [rcx+1Ch], 8
0x14003b4ee  jz      loc_14003B9C7
0x14003b4f4  cmp     byte ptr [rcx+19h], 2
0x14003b4f8  jb      loc_14003B9C7
0x14003b4fe  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b503  mov     edx, 1A7h
0x14003b508  lea     rcx, aQiForImsrdpcli; "QI for IMsRdpClientNonScriptable7 faile"...
0x14003b50f  mov     [rsp+40h+var_18], ebx
0x14003b513  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003b51a  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x14003b51f  mov     r9d, eax
0x14003b522  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b529  mov     rcx, [rcx+10h]
0x14003b52d  call    WPP_SF_DsD
0x14003b532  jmp     loc_14003B9C7
0x14003b537  mov     rcx, [rbp+arg_18]
0x14003b53b  lea     rdx, [rbp+arg_10]
0x14003b53f  mov     rax, [rcx]
0x14003b542  mov     rax, [rax+218h]
0x14003b549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b54e  mov     ebx, eax
0x14003b550  test    eax, eax
0x14003b552  jns     short loc_14003B595
0x14003b554  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b55b  lea     rax, WPP_GLOBAL_Control
0x14003b562  cmp     rcx, rax
0x14003b565  jz      loc_14003B9C7
0x14003b56b  test    byte ptr [rcx+1Ch], 8
0x14003b56f  jz      loc_14003B9C7
0x14003b575  cmp     byte ptr [rcx+19h], 2
0x14003b579  jb      loc_14003B9C7
0x14003b57f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b584  mov     edx, 1A8h
0x14003b589  lea     rcx, aSprdpnonscript; "spRdpNonScript->get_CameraRedirConfigCo"...
0x14003b590  jmp     loc_14003B50F
0x14003b595  cmp     [rbp+arg_10], 0
0x14003b59a  jz      loc_14003B9C7
0x14003b5a0  lea     r14, [rsi+0CCDCh]
0x14003b5a7  mov     edx, 400h; unsigned __int64
0x14003b5ac  mov     rcx, r14; unsigned __int16 *
0x14003b5af  lea     r8, [rbp+var_8]; unsigned __int64 *
0x14003b5b3  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x14003b5b8  mov     ebx, eax
0x14003b5ba  test    eax, eax
0x14003b5bc  jns     short loc_14003B5FF
0x14003b5be  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b5c5  lea     rax, WPP_GLOBAL_Control
0x14003b5cc  cmp     rcx, rax
0x14003b5cf  jz      loc_14003B9C7
0x14003b5d5  test    byte ptr [rcx+1Ch], 8
0x14003b5d9  jz      loc_14003B9C7
0x14003b5df  cmp     byte ptr [rcx+19h], 2
0x14003b5e3  jb      loc_14003B9C7
0x14003b5e9  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b5ee  mov     edx, 1A9h
0x14003b5f3  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x14003b5fa  jmp     loc_14003B50F
0x14003b5ff  mov     rbx, [rbp+var_8]
0x14003b603  mov     edi, 1
0x14003b608  add     rbx, rdi
0x14003b60b  lea     rcx, [rdi-2]
0x14003b60f  lea     eax, [rdi+1]
0x14003b612  mul     rbx
0x14003b615  cmovb   rax, rcx
0x14003b619  mov     rcx, rax; unsigned __int64
0x14003b61c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x14003b621  mov     r12, rax
0x14003b624  test    rax, rax
0x14003b627  jnz     short loc_14003B682
0x14003b629  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b630  lea     rax, WPP_GLOBAL_Control
0x14003b637  cmp     rcx, rax
0x14003b63a  jz      short loc_14003B678
0x14003b63c  test    byte ptr [rcx+1Ch], 8
0x14003b640  jz      short loc_14003B678
0x14003b642  cmp     byte ptr [rcx+19h], 2
0x14003b646  jb      short loc_14003B678
0x14003b648  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b64d  lea     rcx, aTchar_0; "TCHAR[]"
0x14003b654  mov     edx, 1AAh
0x14003b659  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x14003b65e  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003b665  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b66c  mov     r9d, eax
0x14003b66f  mov     rcx, [rcx+10h]
0x14003b673  call    WPP_SF_Ds
0x14003b678  mov     ebx, 8007000Eh
0x14003b67d  jmp     loc_14003B9C7
0x14003b682  mov     r8, r14; unsigned __int16 *
0x14003b685  mov     rdx, rbx; unsigned __int64
0x14003b688  mov     rcx, r12; unsigned __int16 *
0x14003b68b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14003b690  mov     ebx, eax
0x14003b692  test    eax, eax
0x14003b694  jns     short loc_14003B6D7
0x14003b696  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b69d  lea     rax, WPP_GLOBAL_Control
0x14003b6a4  cmp     rcx, rax
0x14003b6a7  jz      loc_14003B9BF
0x14003b6ad  test    byte ptr [rcx+1Ch], 8
0x14003b6b1  jz      loc_14003B9BF
0x14003b6b7  cmp     byte ptr [rcx+19h], 2
0x14003b6bb  jb      loc_14003B9BF
0x14003b6c1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b6c6  mov     edx, 1ABh
0x14003b6cb  lea     rcx, aStringcchcopyF_1; "StringCchCopy failed"
0x14003b6d2  jmp     loc_14003B99C
0x14003b6d7  lea     r8, [rbp+Context]; Context
0x14003b6db  mov     rcx, r12; String
0x14003b6de  lea     rdx, [rbp+Delimiter]; Delimiter
0x14003b6e2  call    cs:__imp_wcstok_s
0x14003b6e8  mov     rbx, rax
0x14003b6eb  test    r15b, r15b
0x14003b6ee  jz      loc_14003B78C
0x14003b6f4  test    rbx, rbx
0x14003b6f7  jz      loc_14003B8DA
0x14003b6fd  or      r9d, 0FFFFFFFFh; cchCount2
0x14003b701  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x14003b705  or      edx, r9d; cchCount1
0x14003b708  lea     r8, pszMore; "*"
0x14003b70f  mov     rcx, rbx; lpString1
0x14003b712  call    cs:__imp_CompareStringOrdinal
0x14003b718  cmp     eax, 2
0x14003b71b  jnz     short loc_14003B736
0x14003b71d  mov     rcx, [rbp+arg_10]
0x14003b721  or      edx, 0FFFFFFFFh
0x14003b724  mov     rax, [rcx]
0x14003b727  mov     rax, [rax+48h]
0x14003b72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b730  mov     ebx, eax
0x14003b732  test    eax, eax
0x14003b734  js      short loc_14003B74B
0x14003b736  lea     r8, [rbp+Context]; Context
0x14003b73a  xor     ecx, ecx; String
0x14003b73c  lea     rdx, [rbp+Delimiter]; Delimiter
0x14003b740  call    cs:__imp_wcstok_s
0x14003b746  mov     rbx, rax
0x14003b749  jmp     short loc_14003B6F4
0x14003b74b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b752  lea     rax, WPP_GLOBAL_Control
0x14003b759  cmp     rcx, rax
0x14003b75c  jz      loc_14003B9BF
0x14003b762  test    byte ptr [rcx+1Ch], 8
0x14003b766  jz      loc_14003B9BF
0x14003b76c  cmp     byte ptr [rcx+19h], 2
0x14003b770  jb      loc_14003B9BF
0x14003b776  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b77b  mov     edx, 1ACh
0x14003b780  lea     rcx, aSpconfigcollec; "spConfigCollection->put_RedirectByDefau"...
0x14003b787  jmp     loc_14003B99C
0x14003b78c  test    rbx, rbx
0x14003b78f  jz      loc_14003B8DA
0x14003b795  or      r9d, 0FFFFFFFFh; cchCount2
0x14003b799  mov     [rsp+40h+bIgnoreCase], edi; bIgnoreCase
0x14003b79d  or      edx, r9d; cchCount1
0x14003b7a0  lea     r8, pszMore; "*"
0x14003b7a7  mov     rcx, rbx; lpString1
0x14003b7aa  call    cs:__imp_CompareStringOrdinal
0x14003b7b0  cmp     eax, 2
0x14003b7b3  jz      short loc_14003B808
0x14003b7b5  movzx   eax, word ptr [rbx]
0x14003b7b8  cmp     ax, 2Dh ; '-'
0x14003b7bc  jnz     short loc_14003B7C2
0x14003b7be  add     rbx, 2
0x14003b7c2  sub     ax, 2Dh ; '-'
0x14003b7c6  mov     rcx, rbx; psz
0x14003b7c9  neg     ax
0x14003b7cc  sbb     r15w, r15w
0x14003b7d0  call    cs:__imp_SysAllocString
0x14003b7d6  mov     r14, rax
0x14003b7d9  test    rax, rax
0x14003b7dc  jz      loc_14003B881
0x14003b7e2  mov     rcx, [rbp+arg_10]
0x14003b7e6  movzx   r8d, r15w
0x14003b7ea  mov     rdx, [rcx]
0x14003b7ed  mov     rax, [rdx+40h]
0x14003b7f1  mov     rdx, r14
0x14003b7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b7f9  mov     ebx, eax
0x14003b7fb  test    eax, eax
0x14003b7fd  js      short loc_14003B820
0x14003b7ff  mov     rcx, r14; bstrString
0x14003b802  call    cs:__imp_SysFreeString
0x14003b808  lea     r8, [rbp+Context]; Context
0x14003b80c  xor     ecx, ecx; String
0x14003b80e  lea     rdx, [rbp+Delimiter]; Delimiter
0x14003b812  call    cs:__imp_wcstok_s
0x14003b818  mov     rbx, rax
0x14003b81b  jmp     loc_14003B78C
0x14003b820  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b827  lea     rax, WPP_GLOBAL_Control
0x14003b82e  cmp     rcx, rax
0x14003b831  jz      short loc_14003B873
0x14003b833  test    byte ptr [rcx+1Ch], 8
0x14003b837  jz      short loc_14003B873
0x14003b839  cmp     byte ptr [rcx+19h], 2
0x14003b83d  jb      short loc_14003B873
0x14003b83f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b844  lea     rcx, aSpconfigcollec_4; "spConfigCollection->AddConfig failed"
0x14003b84b  mov     [rsp+40h+var_18], ebx
0x14003b84f  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x14003b854  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003b85b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b862  mov     edx, 1AEh
0x14003b867  mov     r9d, eax
0x14003b86a  mov     rcx, [rcx+10h]
0x14003b86e  call    WPP_SF_DsD
0x14003b873  mov     rcx, r14; bstrString
0x14003b876  call    cs:__imp_SysFreeString
0x14003b87c  jmp     loc_14003B9BF
0x14003b881  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b888  lea     rax, WPP_GLOBAL_Control
0x14003b88f  cmp     rcx, rax
0x14003b892  jz      short loc_14003B8D0
0x14003b894  test    byte ptr [rcx+1Ch], 8
0x14003b898  jz      short loc_14003B8D0
0x14003b89a  cmp     byte ptr [rcx+19h], 2
0x14003b89e  jb      short loc_14003B8D0
0x14003b8a0  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b8a5  lea     rcx, aBstr; "BSTR"
0x14003b8ac  mov     edx, 1ADh
0x14003b8b1  mov     qword ptr [rsp+40h+bIgnoreCase], rcx
0x14003b8b6  lea     r8, WPP_1cc9dfb3459e3cfebeeebd7e80eb8ca5_Traceguids
0x14003b8bd  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b8c4  mov     r9d, eax
0x14003b8c7  mov     rcx, [rcx+10h]
0x14003b8cb  call    WPP_SF_Ds
0x14003b8d0  mov     ebx, 8007000Eh
0x14003b8d5  jmp     loc_14003B9BF
0x14003b8da  mov     eax, [rsi+0D4DCh]
0x14003b8e0  mov     rcx, [rbp+arg_10]
0x14003b8e4  neg     eax
0x14003b8e6  sbb     dx, dx
0x14003b8e9  mov     r8, [rcx]
0x14003b8ec  mov     rax, [r8+58h]
0x14003b8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b8f5  mov     ebx, eax
0x14003b8f7  test    eax, eax
0x14003b8f9  jns     short loc_14003B939
0x14003b8fb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003b902  lea     rax, WPP_GLOBAL_Control
0x14003b909  cmp     rcx, rax
0x14003b90c  jz      loc_14003B9BF
0x14003b912  test    byte ptr [rcx+1Ch], 8
0x14003b916  jz      loc_14003B9BF
0x14003b91c  cmp     byte ptr [rcx+19h], 2
0x14003b920  jb      loc_14003B9BF
0x14003b926  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14003b92b  mov     edx, 1AFh
0x14003b930  lea     rcx, aSpconfigcollec_3; "spConfigCollection->put_EncodeVideo fai"...
0x14003b937  jmp     short loc_14003B99C
0x14003b939  mov     ecx, [rsi+0D4E0h]
0x14003b93f  test    ecx, ecx
0x14003b941  jz      short loc_14003B952
0x14003b943  sub     ecx, edi
0x14003b945  jz      short loc_14003B954
0x14003b947  cmp     ecx, edi
0x14003b949  jnz     short loc_14003B952
0x14003b94b  mov     edi, 2
0x14003b950  jmp     short loc_14003B954
0x14003b952  xor     edi, edi
0x14003b954  mov     rcx, [rbp+arg_10]
0x14003b958  mov     edx, edi
0x14003b95a  mov     rax, [rcx]
0x14003b95d  mov     rax, [rax+68h]
0x14003b961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003b966  mov     ebx, eax
  ... truncated ...
```
