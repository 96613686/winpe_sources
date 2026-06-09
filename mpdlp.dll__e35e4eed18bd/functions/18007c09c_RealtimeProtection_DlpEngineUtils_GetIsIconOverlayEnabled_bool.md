# RealtimeProtection::DlpEngineUtils::GetIsIconOverlayEnabled(bool &)

- ea: `0x18007c09c`
- end: `0x18007c261`
- name: `?GetIsIconOverlayEnabled@DlpEngineUtils@RealtimeProtection@@YAJAEA_N@Z`
- size: `453`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007a790`
- `0x18019d7f8`

## callees

- `0x18003fa60`
- `0x180040290`
- `0x18007c09c`
- `0x18007cdd4`
- `0x1800809d0`
- `0x180089510`
- `0x1800a7df0`
- `0x18010cb40`

## import_xrefs

- `MpClient!MpConfigClose` at `0x18007c202`
- `MpClient!MpConfigClose` at `0x18007c23d`
- `MpClient!MpConfigClose` at `0x18007c202`
- `MpClient!MpConfigClose` at `0x18007c23d`
- `MpClient!MpConfigOpen` at `0x18007c181`
- `MpClient!MpConfigOpen` at `0x18007c1cb`
- `MpClient!MpConfigOpen` at `0x18007c181`
- `MpClient!MpConfigOpen` at `0x18007c1cb`

## string_xrefs

- `0x18007c1c4`: `Miscellaneous Configuration`

## pseudocode

```c
__int64 __fastcall RealtimeProtection::DlpEngineUtils::GetIsIconOverlayEnabled(
        RealtimeProtection::DlpEngineUtils *this,
        struct RealtimeProtection::DlpCEngine **a2)
{
  int v3; // eax
  int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  unsigned int v9; // [rsp+20h] [rbp-20h] BYREF
  CommonUtil::CRefObject *v10; // [rsp+28h] [rbp-18h] BYREF
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF

  *(_BYTE *)this = 0;
  v10 = 0;
  RealtimeProtection::DlpPlugin::GetEngine((RealtimeProtection::DlpPlugin *)&v10, a2);
  if ( v10 )
  {
    v9 = 0;
    v3 = RealtimeProtection::DlpCEngine::QueryEngineSettings(v10, L"MpDlpShowIconOverlay", &v9);
    if ( v3 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          105,
          &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
          (unsigned int)v3);
    }
    else
    {
      *(_BYTE *)this = v9 == 1;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_12;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 106, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  }
  if ( v10 )
    CommonUtil::CRefObject::Release(v10);
LABEL_12:
  v11 = 0;
  v4 = MpConfigOpen(L"Features", &v11);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        107,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v4);
  }
  else
  {
    v9 = 0;
    if ( (int)MpConfigGetValueDword(v11, L"DlpShowIconOverlay", &v9, 0) < 0 )
    {
      v10 = 0;
      if ( (int)MpConfigOpen(L"Miscellaneous Configuration", &v10) >= 0
        && (int)MpConfigGetValueDword(v10, L"DlpShowIconOverlay", &v9, 0) >= 0 )
      {
        *(_BYTE *)this = v9 == 1;
      }
      if ( v10 )
        MpConfigClose(v10, v5, v6, v7);
    }
    else
    {
      *(_BYTE *)this = v9 == 1;
    }
  }
  if ( v11 )
    MpConfigClose(v11, v5, v6, v7);
  return 0;
}

```

## disassembly

```asm
0x18007c09c  mov     [rsp-8+arg_8], rdi
0x18007c0a1  mov     [rsp-8+arg_10], r14
0x18007c0a6  push    rbp
0x18007c0a7  mov     rbp, rsp
0x18007c0aa  sub     rsp, 40h
0x18007c0ae  mov     rax, cs:__security_cookie
0x18007c0b5  xor     rax, rsp
0x18007c0b8  mov     [rbp+var_8], rax
0x18007c0bc  mov     rdi, rcx
0x18007c0bf  mov     byte ptr [rcx], 0
0x18007c0c2  lea     rcx, [rbp+var_18]; this
0x18007c0c6  mov     [rbp+var_18], 0
0x18007c0ce  call    ?GetEngine@DlpPlugin@RealtimeProtection@@YAXPEAPEAVDlpCEngine@2@@Z; RealtimeProtection::DlpPlugin::GetEngine(RealtimeProtection::DlpCEngine * *)
0x18007c0d3  cmp     [rbp+var_18], 0
0x18007c0d8  lea     r14, WPP_GLOBAL_Control
0x18007c0df  jz      short loc_18007C137
0x18007c0e1  mov     rcx, [rbp+var_18]; this
0x18007c0e5  lea     r8, [rbp+var_20]; unsigned int *
0x18007c0e9  lea     rdx, aMpdlpshowicono; "MpDlpShowIconOverlay"
0x18007c0f0  mov     [rbp+var_20], 0
0x18007c0f7  call    ?QueryEngineSettings@DlpCEngine@RealtimeProtection@@AEAAJPEB_WPEAK@Z; RealtimeProtection::DlpCEngine::QueryEngineSettings(wchar_t const *,ulong *)
0x18007c0fc  test    eax, eax
0x18007c0fe  js      short loc_18007C10B
0x18007c100  cmp     [rbp+var_20], 1
0x18007c104  setz    al
0x18007c107  mov     [rdi], al
0x18007c109  jmp     short loc_18007C15E
0x18007c10b  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c112  cmp     rcx, r14
0x18007c115  jz      short loc_18007C15E
0x18007c117  test    byte ptr [rcx+1Ch], 1
0x18007c11b  jz      short loc_18007C15E
0x18007c11d  mov     rcx, [rcx+10h]
0x18007c121  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c128  mov     edx, 69h ; 'i'
0x18007c12d  mov     r9d, eax
0x18007c130  call    WPP_SF_d
0x18007c135  jmp     short loc_18007C15E
0x18007c137  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c13e  cmp     rcx, r14
0x18007c141  jz      short loc_18007C16E
0x18007c143  test    byte ptr [rcx+1Ch], 2
0x18007c147  jz      short loc_18007C16E
0x18007c149  mov     rcx, [rcx+10h]
0x18007c14d  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c154  mov     edx, 6Ah ; 'j'
0x18007c159  call    WPP_SF_
0x18007c15e  cmp     [rbp+var_18], 0
0x18007c163  jz      short loc_18007C16E
0x18007c165  mov     rcx, [rbp+var_18]; this
0x18007c169  call    ?Release@CRefObject@CommonUtil@@QEBAJXZ; CommonUtil::CRefObject::Release(void)
0x18007c16e  lea     rdx, [rbp+var_10]
0x18007c172  mov     [rbp+var_10], 0
0x18007c17a  lea     rcx, aFeatures_0; "Features"
0x18007c181  call    cs:__imp_MpConfigOpen
0x18007c187  test    eax, eax
0x18007c189  js      short loc_18007C20A
0x18007c18b  mov     rcx, [rbp+var_10]
0x18007c18f  lea     r8, [rbp+var_20]
0x18007c193  xor     r9d, r9d
0x18007c196  mov     [rbp+var_20], 0
0x18007c19d  lea     rdx, aDlpshowiconove; "DlpShowIconOverlay"
0x18007c1a4  call    MpConfigGetValueDword
0x18007c1a9  test    eax, eax
0x18007c1ab  js      short loc_18007C1B8
0x18007c1ad  cmp     [rbp+var_20], 1
0x18007c1b1  setz    al
0x18007c1b4  mov     [rdi], al
0x18007c1b6  jmp     short loc_18007C234
0x18007c1b8  lea     rdx, [rbp+var_18]
0x18007c1bc  mov     [rbp+var_18], 0
0x18007c1c4  lea     rcx, aMiscellaneousC_0; "Miscellaneous Configuration"
0x18007c1cb  call    cs:__imp_MpConfigOpen
0x18007c1d1  test    eax, eax
0x18007c1d3  js      short loc_18007C1F9
0x18007c1d5  mov     rcx, [rbp+var_18]
0x18007c1d9  lea     r8, [rbp+var_20]
0x18007c1dd  xor     r9d, r9d
0x18007c1e0  lea     rdx, aDlpshowiconove; "DlpShowIconOverlay"
0x18007c1e7  call    MpConfigGetValueDword
0x18007c1ec  test    eax, eax
0x18007c1ee  js      short loc_18007C1F9
0x18007c1f0  cmp     [rbp+var_20], 1
0x18007c1f4  setz    al
0x18007c1f7  mov     [rdi], al
0x18007c1f9  mov     rcx, [rbp+var_18]
0x18007c1fd  test    rcx, rcx
0x18007c200  jz      short loc_18007C234
0x18007c202  call    cs:__imp_MpConfigClose
0x18007c208  jmp     short loc_18007C234
0x18007c20a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007c211  cmp     rcx, r14
0x18007c214  jz      short loc_18007C234
0x18007c216  test    byte ptr [rcx+1Ch], 1
0x18007c21a  jz      short loc_18007C234
0x18007c21c  mov     rcx, [rcx+10h]
0x18007c220  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007c227  mov     edx, 6Bh ; 'k'
0x18007c22c  mov     r9d, eax
0x18007c22f  call    WPP_SF_d
0x18007c234  mov     rcx, [rbp+var_10]
0x18007c238  test    rcx, rcx
0x18007c23b  jz      short loc_18007C243
0x18007c23d  call    cs:__imp_MpConfigClose
0x18007c243  xor     eax, eax
0x18007c245  mov     rcx, [rbp+var_8]
0x18007c249  xor     rcx, rsp; StackCookie
0x18007c24c  call    __security_check_cookie
0x18007c251  mov     rdi, [rsp+40h+arg_8]
0x18007c256  mov     r14, [rsp+40h+arg_10]
0x18007c25b  add     rsp, 40h
0x18007c25f  pop     rbp
0x18007c260  retn
```
