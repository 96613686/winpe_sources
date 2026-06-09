# DhcpDeleteIpRoute

- ea: `0x18000b82c`
- end: `0x18000bb63`
- name: `DhcpDeleteIpRoute`
- size: `823`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, unsigned int)`
- caller_count: `5`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x18000b470`
- `0x18000b564`
- `0x18003d538`
- `0x18003d8d0`
- `0x18003de84`

## callees

- `0x180007190`
- `0x1800089f8`
- `0x18000a580`
- `0x18000b82c`
- `0x18000f940`
- `0x18000f98c`
- `0x1800125e4`
- `0x180015668`
- `0x18001cef0`
- `0x18001d826`
- `0x180049008`
- `0x180049534`
- `0x18004d4c0`
- `0x18004dbc4`

## pseudocode

```c
__int64 __fastcall DhcpDeleteIpRoute(__int64 a1, unsigned int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // edi
  unsigned int v6; // esi
  int v7; // edx
  int v8; // ecx
  int v9; // r8d
  char v10; // al
  __int64 v11; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // edi
  unsigned int v18; // [rsp+40h] [rbp-258h] BYREF
  unsigned int v19; // [rsp+48h] [rbp-250h] BYREF
  unsigned int v20; // [rsp+50h] [rbp-248h] BYREF
  int v21; // [rsp+58h] [rbp-240h] BYREF
  int v22; // [rsp+5Ch] [rbp-23Ch] BYREF
  int v23; // [rsp+60h] [rbp-238h] BYREF
  __int64 v24; // [rsp+68h] [rbp-230h] BYREF
  _BYTE v25[136]; // [rsp+70h] [rbp-228h] BYREF
  unsigned int v26; // [rsp+F8h] [rbp-1A0h]
  unsigned int v27; // [rsp+FCh] [rbp-19Ch]
  unsigned int v28; // [rsp+100h] [rbp-198h]
  _BYTE v29[32]; // [rsp+1B0h] [rbp-E8h] BYREF
  __int64 v30; // [rsp+1D0h] [rbp-C8h]
  __int64 v31; // [rsp+1D8h] [rbp-C0h]
  int *v32; // [rsp+1E0h] [rbp-B8h]
  __int64 v33; // [rsp+1E8h] [rbp-B0h]
  int *v34; // [rsp+1F0h] [rbp-A8h]
  __int64 v35; // [rsp+1F8h] [rbp-A0h]
  int *v36; // [rsp+200h] [rbp-98h]
  __int64 v37; // [rsp+208h] [rbp-90h]
  __int64 v38; // [rsp+210h] [rbp-88h]
  __int64 v39; // [rsp+218h] [rbp-80h]
  UUID *v40; // [rsp+220h] [rbp-78h]
  __int64 v41; // [rsp+228h] [rbp-70h]
  unsigned int *v42; // [rsp+230h] [rbp-68h]
  __int64 v43; // [rsp+238h] [rbp-60h]
  unsigned int *v44; // [rsp+240h] [rbp-58h]
  __int64 v45; // [rsp+248h] [rbp-50h]
  unsigned int *v46; // [rsp+250h] [rbp-48h]
  __int64 v47; // [rsp+258h] [rbp-40h]
  __int64 *v48; // [rsp+260h] [rbp-38h]
  __int64 v49; // [rsp+268h] [rbp-30h]

  v4 = a2;
  v19 = a2;
  v20 = a3;
  v18 = a4;
  v6 = a4;
  memset_0(v25, 0, 0x140u);
  if ( v4 )
  {
    v10 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v11 = 25;
      goto LABEL_6;
    }
  }
  else
  {
    v10 = xmmword_1800616A0;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
    {
      v11 = 24;
LABEL_6:
      WPP_SF_DDJ(1028, v11, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v4, v6, *(_QWORD *)(a1 + 24));
      v10 = xmmword_1800616A0;
      v6 = v18;
      v4 = v19;
    }
  }
  if ( !v4 && !v20 && !v6 )
  {
    if ( (v10 & 2) != 0 )
      WPP_SF_q(1025, 26, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, *(_QWORD *)(a1 + 24));
    return 0;
  }
  if ( (v10 & 2) != 0 )
    WPP_SF__IPV4__IPV4__IPV4__IPV4_(v8, v7, v9, (unsigned int)&v19, (__int64)&v20, (__int64)&v18, a1 + 120);
  InitializeTraceElementFromContext(v25, a1, 0, 8);
  v26 = v19;
  v27 = v20;
  v28 = v18;
  TraceLogEx(v25);
  if ( (unsigned int)dword_1800610D8 > 5 && tlgKeywordOn((__int64)&dword_1800610D8, 0x400000000000LL) )
  {
    v31 = 16;
    v30 = a1 + 32;
    v21 = *(_DWORD *)(a1 + 48);
    v32 = &v21;
    v22 = *(_DWORD *)(a1 + 112);
    v34 = &v22;
    v23 = *(_DWORD *)(a1 + 116);
    v36 = &v23;
    v38 = a1 + 2112;
    v40 = &DhcpGlobalBootGuid;
    v42 = &v19;
    v44 = &v20;
    v46 = &v18;
    v48 = &v24;
    v33 = 4;
    v35 = 4;
    v37 = 4;
    v39 = 16;
    v41 = 16;
    v43 = 4;
    v45 = 4;
    v47 = 4;
    v24 = 0x1000000;
    v49 = 8;
    tlgWriteTransfer_EtwEventWriteTransfer(v13, (unsigned __int8 *)&unk_180059D80, v14, v15, 12, (__int64)v29);
  }
  LOBYTE(v16) = DhcpGetPrefixLength(v20);
  v17 = DhcpDelIPv4Route(v19, v16, a1 + 24, v18);
  if ( (Microsoft_Windows_Dhcp_ClientEnableBits & 1) != 0 )
    McTemplateU0qqqq_EtwEventWriteTransfer(v18, (unsigned int)RouteDeletev2, v19, v20, v18, *(_DWORD *)(a1 + 120));
  if ( !v17 )
    return 0;
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_dJ(1025, 28, WPP_c340248efe383a4e03597a9397b959ee_Traceguids, v17, *(_QWORD *)(a1 + 24));
  return v17;
}

```

## disassembly

```asm
0x18000b82c  push    rbx
0x18000b82e  push    rsi
0x18000b82f  push    rdi
0x18000b830  sub     rsp, 280h
0x18000b837  mov     rax, cs:__security_cookie
0x18000b83e  xor     rax, rsp
0x18000b841  mov     [rsp+298h+var_28], rax
0x18000b849  mov     edi, edx
0x18000b84b  mov     [rsp+298h+var_250], edx
0x18000b84f  mov     rbx, rcx
0x18000b852  mov     [rsp+298h+var_248], r8d
0x18000b857  xor     edx, edx; Val
0x18000b859  mov     [rsp+298h+var_258], r9d
0x18000b85e  mov     r8d, 140h; Size
0x18000b864  lea     rcx, [rsp+298h+var_228]; void *
0x18000b869  mov     esi, r9d
0x18000b86c  call    memset_0
0x18000b871  test    edi, edi
0x18000b873  jnz     short loc_18000B884
0x18000b875  mov     al, byte ptr cs:xmmword_1800616A0
0x18000b87b  test    al, 10h
0x18000b87d  jz      short loc_18000B8C2
0x18000b87f  lea     edx, [rdi+18h]
0x18000b882  jmp     short loc_18000B893
0x18000b884  mov     al, byte ptr cs:xmmword_1800616A0
0x18000b88a  test    al, 10h
0x18000b88c  jz      short loc_18000B8C2
0x18000b88e  mov     edx, 19h
0x18000b893  mov     rax, [rbx+18h]
0x18000b897  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b89e  mov     [rsp+298h+var_270], rax
0x18000b8a3  mov     r9d, edi
0x18000b8a6  mov     ecx, 404h
0x18000b8ab  mov     dword ptr [rsp+298h+var_278], esi
0x18000b8af  call    WPP_SF_DDJ
0x18000b8b4  mov     al, byte ptr cs:xmmword_1800616A0
0x18000b8ba  mov     esi, [rsp+298h+var_258]
0x18000b8be  mov     edi, [rsp+298h+var_250]
0x18000b8c2  test    edi, edi
0x18000b8c4  jnz     short loc_18000B909
0x18000b8c6  cmp     [rsp+298h+var_248], edi
0x18000b8ca  jnz     short loc_18000B909
0x18000b8cc  test    esi, esi
0x18000b8ce  jnz     short loc_18000B909
0x18000b8d0  test    al, 2
0x18000b8d2  jz      short loc_18000B8EC
0x18000b8d4  mov     r9, [rbx+18h]
0x18000b8d8  lea     edx, [rdi+1Ah]
0x18000b8db  mov     ecx, 401h
0x18000b8e0  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000b8e7  call    WPP_SF_q
0x18000b8ec  xor     eax, eax
0x18000b8ee  mov     rcx, [rsp+298h+var_28]
0x18000b8f6  xor     rcx, rsp; StackCookie
0x18000b8f9  call    __security_check_cookie
0x18000b8fe  add     rsp, 280h
0x18000b905  pop     rdi
0x18000b906  pop     rsi
0x18000b907  pop     rbx
0x18000b908  retn
0x18000b909  test    al, 2
0x18000b90b  jz      short loc_18000B934
0x18000b90d  lea     rax, [rbx+78h]
0x18000b911  mov     [rsp+298h+var_268], rax
0x18000b916  lea     r9, [rsp+298h+var_250]
0x18000b91b  lea     rax, [rsp+298h+var_258]
0x18000b920  mov     [rsp+298h+var_270], rax
0x18000b925  lea     rax, [rsp+298h+var_248]
0x18000b92a  mov     [rsp+298h+var_278], rax
0x18000b92f  call    WPP_SF__IPV4__IPV4__IPV4__IPV4_
0x18000b934  mov     edi, 8
0x18000b939  lea     rcx, [rsp+298h+var_228]
0x18000b93e  mov     r9d, edi
0x18000b941  xor     r8d, r8d
0x18000b944  mov     rdx, rbx
0x18000b947  call    InitializeTraceElementFromContext
0x18000b94c  mov     eax, [rsp+298h+var_250]
0x18000b950  lea     rcx, [rsp+298h+var_228]
0x18000b955  mov     [rsp+298h+var_1A0], eax
0x18000b95c  mov     eax, [rsp+298h+var_248]
0x18000b960  mov     [rsp+298h+var_19C], eax
0x18000b967  mov     eax, [rsp+298h+var_258]
0x18000b96b  mov     [rsp+298h+var_198], eax
0x18000b972  call    TraceLogEx
0x18000b977  mov     eax, cs:dword_1800610D8
0x18000b97d  cmp     eax, 5
0x18000b980  jbe     loc_18000BADC
0x18000b986  mov     rdx, 400000000000h
0x18000b990  lea     rcx, dword_1800610D8
0x18000b997  call    _tlgKeywordOn
0x18000b99c  test    al, al
0x18000b99e  jz      loc_18000BADC
0x18000b9a4  lea     rax, [rbx+20h]
0x18000b9a8  mov     [rsp+298h+var_C0], 10h
0x18000b9b4  mov     [rsp+298h+var_C8], rax
0x18000b9bc  lea     rdx, unk_180059D80
0x18000b9c3  mov     eax, [rbx+30h]
0x18000b9c6  mov     [rsp+298h+var_240], eax
0x18000b9ca  lea     rax, [rsp+298h+var_240]
0x18000b9cf  mov     [rsp+298h+var_B8], rax
0x18000b9d7  mov     eax, [rbx+70h]
0x18000b9da  mov     [rsp+298h+var_23C], eax
0x18000b9de  lea     rax, [rsp+298h+var_23C]
0x18000b9e3  mov     [rsp+298h+var_A8], rax
0x18000b9eb  mov     eax, [rbx+74h]
0x18000b9ee  mov     [rsp+298h+var_238], eax
0x18000b9f2  lea     rax, [rsp+298h+var_238]
0x18000b9f7  mov     [rsp+298h+var_98], rax
0x18000b9ff  lea     rax, [rbx+840h]
0x18000ba06  mov     [rsp+298h+var_88], rax
0x18000ba0e  lea     rax, DhcpGlobalBootGuid
0x18000ba15  mov     [rsp+298h+var_78], rax
0x18000ba1d  lea     rax, [rsp+298h+var_250]
0x18000ba22  mov     [rsp+298h+var_68], rax
0x18000ba2a  lea     rax, [rsp+298h+var_248]
0x18000ba2f  mov     [rsp+298h+var_58], rax
0x18000ba37  lea     rax, [rsp+298h+var_258]
0x18000ba3c  mov     [rsp+298h+var_48], rax
0x18000ba44  lea     rax, [rsp+298h+var_230]
0x18000ba49  mov     [rsp+298h+var_38], rax
0x18000ba51  lea     rax, [rsp+298h+var_E8]
0x18000ba59  mov     [rsp+298h+var_270], rax
0x18000ba5e  mov     dword ptr [rsp+298h+var_278], 0Ch
0x18000ba66  mov     [rsp+298h+var_B0], 4
0x18000ba72  mov     [rsp+298h+var_A0], 4
0x18000ba7e  mov     [rsp+298h+var_90], 4
0x18000ba8a  mov     [rsp+298h+var_80], 10h
0x18000ba96  mov     [rsp+298h+var_70], 10h
0x18000baa2  mov     [rsp+298h+var_60], 4
0x18000baae  mov     [rsp+298h+var_50], 4
0x18000baba  mov     [rsp+298h+var_40], 4
0x18000bac6  mov     [rsp+298h+var_230], 1000000h
0x18000bacf  mov     [rsp+298h+var_30], rdi
0x18000bad7  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18000badc  mov     ecx, [rsp+298h+var_248]
0x18000bae0  call    DhcpGetPrefixLength
0x18000bae5  mov     r9d, [rsp+298h+var_258]
0x18000baea  lea     r8, [rbx+18h]
0x18000baee  mov     ecx, [rsp+298h+var_250]
0x18000baf2  mov     dl, al
0x18000baf4  call    DhcpDelIPv4Route
0x18000baf9  test    cs:Microsoft_Windows_Dhcp_ClientEnableBits, 1
0x18000bb00  mov     edi, eax
0x18000bb02  jz      short loc_18000BB29
0x18000bb04  mov     ecx, [rbx+78h]
0x18000bb07  lea     rdx, RouteDeletev2
0x18000bb0e  mov     r9d, [rsp+298h+var_248]
0x18000bb13  mov     r8d, [rsp+298h+var_250]
0x18000bb18  mov     dword ptr [rsp+298h+var_270], ecx
0x18000bb1c  mov     ecx, [rsp+298h+var_258]
0x18000bb20  mov     dword ptr [rsp+298h+var_278], ecx
0x18000bb24  call    McTemplateU0qqqq_EtwEventWriteTransfer
0x18000bb29  test    edi, edi
0x18000bb2b  jz      loc_18000B8EC
0x18000bb31  test    byte ptr cs:xmmword_1800616A0, 2
0x18000bb38  jz      short loc_18000BB5C
0x18000bb3a  mov     rax, [rbx+18h]
0x18000bb3e  lea     r8, WPP_c340248efe383a4e03597a9397b959ee_Traceguids
0x18000bb45  mov     edx, 1Ch
0x18000bb4a  mov     [rsp+298h+var_278], rax
0x18000bb4f  mov     ecx, 401h
0x18000bb54  mov     r9d, edi
0x18000bb57  call    WPP_SF_dJ
0x18000bb5c  mov     eax, edi
0x18000bb5e  jmp     loc_18000B8EE
```
