# GetCredentials(HINSTANCE__ *,HWND__ *,ulong,ulong,_CREDUI_CONTEXT const *,ulong,ulong,void *,void * *)

- ea: `0x140015d68`
- end: `0x140015fbf`
- name: `?GetCredentials@@YAKPEAUHINSTANCE__@@PEAUHWND__@@KKPEBU_CREDUI_CONTEXT@@KKPEAXPEAPEAX@Z`
- size: `599`
- prototype: `__int64 __fastcall(HINSTANCE, HWND, __int16, unsigned int, const struct _CREDUI_CONTEXT *, unsigned int, unsigned int, void *, void **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000cfdc`

## callees

- `0x14000fbec`
- `0x14000fc2c`
- `0x140013928`
- `0x140014764`
- `0x140015d68`
- `0x140019b34`
- `0x14001e012`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015eff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f8d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140015f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140015f08`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140015f08`
- `credui!CredUIPromptForWindowsCredentialsWorker` at `0x140015e8c`
- `credui!CredUIPromptForWindowsCredentialsWorker` at `0x140015e8c`

## pseudocode

```c
__int64 __fastcall GetCredentials(
        HINSTANCE a1,
        HWND a2,
        __int16 a3,
        unsigned int a4,
        const struct _CREDUI_CONTEXT *a5,
        unsigned int a6,
        unsigned int a7,
        void *a8,
        void **a9)
{
  void *v9; // rsi
  int v10; // r12d
  int v11; // ebx
  unsigned int v13; // r14d
  int v14; // ebx
  void **v15; // r15
  void *v16; // rax
  _BYTE *v17; // rcx
  __int64 v18; // rax
  SIZE_T cb[2]; // [rsp+60h] [rbp-31h] BYREF
  void *Src; // [rsp+70h] [rbp-21h] BYREF
  _QWORD v22[2]; // [rsp+78h] [rbp-19h] BYREF
  __int128 v23; // [rsp+88h] [rbp-9h]
  __int64 v24; // [rsp+98h] [rbp+7h]
  int v25; // [rsp+E0h] [rbp+4Fh] BYREF

  v22[0] = 40;
  Src = 0;
  v25 = 0;
  v9 = 0;
  v24 = 0;
  v22[1] = a2;
  v10 = 0;
  v11 = a3 & 8;
  v23 = 0;
  *(_OWORD *)cb = 0;
  if ( (a3 & 0x4004) == 0x4004 )
  {
    v13 = 33;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      v14 = v11 != 0 ? 832 : 320;
    else
      v14 = 512;
  }
  else
  {
    v13 = 1;
    v14 = v11 != 0 ? 768 : 256;
  }
  v15 = a9;
  do
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 21, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids);
    a4 = CredUIPromptForWindowsCredentialsWorker(
           v13,
           a5,
           v22,
           a4,
           (char *)cb + 4,
           v9,
           v10 & (unsigned int)-(v9 != 0),
           &Src,
           &cb[1],
           &v25,
           v14);
    if ( a4 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        WPP_SF_D(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 22, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids, a4);
LABEL_18:
      if ( a4 != 1223 )
      {
        if ( v9 )
          CoTaskMemFree(v9);
        v16 = CoTaskMemAlloc(LODWORD(cb[1]));
        v9 = v16;
        if ( v16 )
        {
          memcpy_0(v16, Src, LODWORD(cb[1]));
          v10 = cb[1];
        }
      }
      goto LABEL_23;
    }
    a4 = AttemptLogon((struct _CRED_PROV_CREDENTIAL *)cb, a6, a7, v15);
    if ( a4 == 87 )
      a4 = 1326;
    if ( a4 )
      goto LABEL_18;
LABEL_23:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl'::`2'::impl) )
      EtwEventWrite_CredUI_Elevation(a5, a8, *v15, a4);
  }
  while ( a4 && a4 != 1223 && a4 != 1400 );
  v17 = Src;
  if ( Src )
  {
    v18 = LODWORD(cb[1]);
    if ( LODWORD(cb[1]) )
    {
      do
      {
        *v17++ = 0;
        --v18;
      }
      while ( v18 );
      v17 = Src;
    }
    CoTaskMemFree(v17);
  }
  if ( v9 )
    CoTaskMemFree(v9);
  return a4;
}

```

## disassembly

```asm
0x140015d68  mov     [rsp-8+arg_0], rbx
0x140015d6d  mov     [rsp-8+arg_8], rsi
0x140015d72  push    rbp
0x140015d73  push    rdi
0x140015d74  push    r12
0x140015d76  push    r14
0x140015d78  push    r15
0x140015d7a  lea     rbp, [rsp-0Fh]
0x140015d7f  sub     rsp, 0A0h
0x140015d86  xor     eax, eax
0x140015d88  mov     [rbp+2Fh+var_48], 28h ; '('
0x140015d90  mov     ebx, r8d
0x140015d93  mov     [rbp+2Fh+Src], rax
0x140015d97  mov     [rbp+2Fh+arg_10], eax
0x140015d9a  xor     esi, esi
0x140015d9c  mov     eax, 4004h
0x140015da1  mov     [rbp+2Fh+var_28], 0
0x140015da9  and     r8d, eax
0x140015dac  mov     [rbp+2Fh+var_40], rdx
0x140015db0  xor     r12d, r12d
0x140015db3  and     ebx, 8
0x140015db6  xorps   xmm0, xmm0
0x140015db9  xorps   xmm1, xmm1
0x140015dbc  mov     edi, r9d
0x140015dbf  movdqu  [rbp+2Fh+var_38], xmm0
0x140015dc4  movups  xmmword ptr [rbp+2Fh+cb], xmm1
0x140015dc8  cmp     r8d, eax
0x140015dcb  jnz     short loc_140015DFA
0x140015dcd  lea     r14d, [rsi+21h]
0x140015dd1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140015dd8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x140015ddd  test    al, al
0x140015ddf  jz      short loc_140015DF3
0x140015de1  neg     ebx
0x140015de3  sbb     ebx, ebx
0x140015de5  and     ebx, 200h
0x140015deb  add     ebx, 140h
0x140015df1  jmp     short loc_140015E10
0x140015df3  mov     ebx, 200h
0x140015df8  jmp     short loc_140015E10
0x140015dfa  neg     ebx
0x140015dfc  mov     r14d, 1
0x140015e02  sbb     ebx, ebx
0x140015e04  and     ebx, 200h
0x140015e0a  add     ebx, 100h
0x140015e10  mov     r15, [rbp+2Fh+arg_40]
0x140015e14  lea     rax, WPP_GLOBAL_Control
0x140015e1b  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e22  cmp     rcx, rax
0x140015e25  jz      short loc_140015E42
0x140015e27  test    byte ptr [rcx+1Ch], 2
0x140015e2b  jz      short loc_140015E42
0x140015e2d  mov     rcx, [rcx+10h]
0x140015e31  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x140015e38  mov     edx, 15h
0x140015e3d  call    WPP_SF_
0x140015e42  mov     rdx, [rbp+2Fh+arg_20]
0x140015e46  lea     r8, [rbp+2Fh+var_48]
0x140015e4a  mov     [rsp+0C0h+var_70], ebx
0x140015e4e  mov     rax, rsi
0x140015e51  neg     rax
0x140015e54  mov     r9d, edi
0x140015e57  lea     rax, [rbp+2Fh+arg_10]
0x140015e5b  mov     [rsp+0C0h+var_78], rax
0x140015e60  sbb     ecx, ecx
0x140015e62  and     ecx, r12d
0x140015e65  lea     rax, [rbp+2Fh+cb+8]
0x140015e69  mov     [rsp+0C0h+var_80], rax
0x140015e6e  lea     rax, [rbp+2Fh+Src]
0x140015e72  mov     [rsp+0C0h+var_88], rax
0x140015e77  lea     rax, [rbp+2Fh+cb+4]
0x140015e7b  mov     [rsp+0C0h+var_90], ecx
0x140015e7f  mov     ecx, r14d
0x140015e82  mov     [rsp+0C0h+var_98], rsi
0x140015e87  mov     [rsp+0C0h+var_A0], rax
0x140015e8c  call    cs:__imp_CredUIPromptForWindowsCredentialsWorker
0x140015e92  mov     edi, eax
0x140015e94  test    eax, eax
0x140015e96  jnz     short loc_140015EBE
0x140015e98  mov     r8d, [rbp+2Fh+arg_30]; unsigned int
0x140015e9c  lea     rcx, [rbp+2Fh+cb]; struct _CRED_PROV_CREDENTIAL *
0x140015ea0  mov     edx, [rbp+2Fh+arg_28]; unsigned int
0x140015ea3  mov     r9, r15; void **
0x140015ea6  call    ?AttemptLogon@@YAKPEAU_CRED_PROV_CREDENTIAL@@KKPEAPEAX@Z; AttemptLogon(_CRED_PROV_CREDENTIAL *,ulong,ulong,void * *)
0x140015eab  mov     edi, eax
0x140015ead  mov     eax, 52Eh
0x140015eb2  cmp     edi, 57h ; 'W'
0x140015eb5  cmovz   edi, eax
0x140015eb8  test    edi, edi
0x140015eba  jz      short loc_140015F2A
0x140015ebc  jmp     short loc_140015EEF
0x140015ebe  mov     rcx, cs:WPP_GLOBAL_Control
0x140015ec5  lea     rax, WPP_GLOBAL_Control
0x140015ecc  cmp     rcx, rax
0x140015ecf  jz      short loc_140015EEF
0x140015ed1  test    byte ptr [rcx+1Ch], 2
0x140015ed5  jz      short loc_140015EEF
0x140015ed7  mov     rcx, [rcx+10h]
0x140015edb  lea     r8, WPP_dfa7687bdc833f88b236fff3fe8ed34e_Traceguids
0x140015ee2  mov     edx, 16h
0x140015ee7  mov     r9d, edi
0x140015eea  call    WPP_SF_D
0x140015eef  cmp     edi, 4C7h
0x140015ef5  jz      short loc_140015F2A
0x140015ef7  test    rsi, rsi
0x140015efa  jz      short loc_140015F05
0x140015efc  mov     rcx, rsi; pv
0x140015eff  call    cs:__imp_CoTaskMemFree
0x140015f05  mov     ecx, dword ptr [rbp+2Fh+cb+8]; cb
0x140015f08  call    cs:__imp_CoTaskMemAlloc
0x140015f0e  mov     rsi, rax
0x140015f11  test    rax, rax
0x140015f14  jz      short loc_140015F2A
0x140015f16  mov     r8d, dword ptr [rbp+2Fh+cb+8]; Size
0x140015f1a  mov     rcx, rax; void *
0x140015f1d  mov     rdx, [rbp+2Fh+Src]; Src
0x140015f21  call    memcpy_0
0x140015f26  mov     r12d, dword ptr [rbp+2Fh+cb+8]
0x140015f2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ShadowAdmin@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin> `wil::Feature<__WilFeatureTraits_Feature_ShadowAdmin>::GetImpl(void)'::`2'::impl
0x140015f31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ShadowAdmin@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ShadowAdmin>::__private_IsEnabled(void)
0x140015f36  test    al, al
0x140015f38  jz      short loc_140015F4D
0x140015f3a  mov     r8, [r15]; void *
0x140015f3d  mov     r9d, edi; unsigned int
0x140015f40  mov     rdx, [rbp+2Fh+arg_38]; void *
0x140015f44  mov     rcx, [rbp+2Fh+arg_20]; struct _CREDUI_CONTEXT *
0x140015f48  call    ?EtwEventWrite_CredUI_Elevation@@YAXPEBU_CREDUI_CONTEXT@@PEAX1K@Z; EtwEventWrite_CredUI_Elevation(_CREDUI_CONTEXT const *,void *,void *,ulong)
0x140015f4d  test    edi, edi
0x140015f4f  jz      short loc_140015F6C
0x140015f51  cmp     edi, 4C7h
0x140015f57  jz      short loc_140015F6C
0x140015f59  lea     rax, WPP_GLOBAL_Control
0x140015f60  cmp     edi, 578h
0x140015f66  jnz     loc_140015E1B
0x140015f6c  mov     rcx, [rbp+2Fh+Src]
0x140015f70  test    rcx, rcx
0x140015f73  jz      short loc_140015F93
0x140015f75  mov     eax, dword ptr [rbp+2Fh+cb+8]
0x140015f78  test    rax, rax
0x140015f7b  jz      short loc_140015F8D
0x140015f7d  mov     byte ptr [rcx], 0
0x140015f80  inc     rcx
0x140015f83  sub     rax, 1
0x140015f87  jnz     short loc_140015F7D
0x140015f89  mov     rcx, [rbp+2Fh+Src]; pv
0x140015f8d  call    cs:__imp_CoTaskMemFree
0x140015f93  test    rsi, rsi
0x140015f96  jz      short loc_140015FA1
0x140015f98  mov     rcx, rsi; pv
0x140015f9b  call    cs:__imp_CoTaskMemFree
0x140015fa1  lea     r11, [rsp+0C0h+var_20]
0x140015fa9  mov     eax, edi
0x140015fab  mov     rbx, [r11+30h]
0x140015faf  mov     rsi, [r11+38h]
0x140015fb3  mov     rsp, r11
0x140015fb6  pop     r15
0x140015fb8  pop     r14
0x140015fba  pop     r12
0x140015fbc  pop     rdi
0x140015fbd  pop     rbp
0x140015fbe  retn
```
