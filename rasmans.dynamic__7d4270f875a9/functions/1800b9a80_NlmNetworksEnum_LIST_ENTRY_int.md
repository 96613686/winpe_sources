# NlmNetworksEnum(_LIST_ENTRY *,int *)

- ea: `0x1800b9a80`
- end: `0x1800ba3e2`
- name: `?NlmNetworksEnum@@YAJPEAU_LIST_ENTRY@@PEAH@Z`
- size: `2402`
- prototype: `__int64 __fastcall(struct _LIST_ENTRY *, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b57b0`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000ebe8`
- `0x1800b90a0`
- `0x1800b99d4`
- `0x1800b9a80`
- `0x1800e3ca0`
- `0x1800e4534`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `msvcrt!tolower` at `0x1800ba0d0`
- `msvcrt!tolower` at `0x1800ba0d0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b9cbf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b9cbf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b9b2b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b9b2b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ba051`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800ba051`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b9c2a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b9c2a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba154`
- `OLEAUT32!__imp_SysFreeString` at `0x1800ba154`
- `OLEAUT32!__imp_VariantInit` at `0x1800b9e51`
- `OLEAUT32!__imp_VariantInit` at `0x1800b9e51`

## pseudocode

```c
__int64 __fastcall NlmNetworksEnum(struct _LIST_ENTRY *a1, int *a2)
{
  int *v2; // r15
  __int64 v3; // r12
  __int64 v4; // r14
  HRESULT v5; // eax
  int v6; // edi
  struct _LIST_ENTRY *v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // r9
  unsigned int i; // r13d
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  OLECHAR *v15; // rax
  OLECHAR *v16; // rbx
  __int64 v17; // rax
  _QWORD *v18; // r15
  _WORD *v19; // r9
  __int64 v20; // rbx
  __int16 v21; // ax
  struct _LIST_ENTRY *Blink; // rax
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // [rsp+30h] [rbp-89h] BYREF
  unsigned int v26; // [rsp+38h] [rbp-81h] BYREF
  int v27; // [rsp+3Ch] [rbp-7Dh] BYREF
  int v28; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v29; // [rsp+44h] [rbp-75h]
  int v30; // [rsp+48h] [rbp-71h]
  int v31; // [rsp+4Ch] [rbp-6Dh]
  __int64 v32; // [rsp+50h] [rbp-69h] BYREF
  __int64 v33; // [rsp+58h] [rbp-61h] BYREF
  __int64 v34; // [rsp+60h] [rbp-59h] BYREF
  __int64 v35; // [rsp+68h] [rbp-51h] BYREF
  BSTR bstrString; // [rsp+70h] [rbp-49h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp-41h] BYREF
  int *v38; // [rsp+80h] [rbp-39h]
  VARIANTARG pvarg; // [rsp+88h] [rbp-31h] BYREF
  GUID rguid; // [rsp+A0h] [rbp-19h] BYREF
  __int128 v41; // [rsp+B0h] [rbp-9h] BYREF

  v2 = a2;
  v38 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 122, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
  LODWORD(v3) = 0;
  ppv = 0;
  v33 = 0;
  v32 = 0;
  v34 = 0;
  v25 = 0;
  v4 = 0;
  v28 = 0;
  v27 = 0;
  v41 = 0;
  bstrString = 0;
  v26 = 0;
  rguid = 0;
  v35 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v5 = CoInitializeEx(0, 0);
  v6 = v5;
  if ( v5 < 0 )
  {
    v31 = 0;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 123;
LABEL_8:
    v9 = (unsigned int)v5;
LABEL_9:
    WPP_SF_d(v7[1].Flink, v8, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v9);
    goto LABEL_10;
  }
  v31 = 1;
  v5 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 124;
    goto LABEL_8;
  }
  v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 56LL))(ppv, 1, &v33);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 125;
    goto LABEL_8;
  }
  for ( i = 0; ; ++i )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v33 + 64LL))(v33, 1, &v25, 0);
    if ( v6 )
      break;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  v29 = i;
  if ( !i )
    goto LABEL_10;
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v33 + 80LL))(v33);
  v6 = v12;
  if ( v12 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_11;
    }
    v8 = 126;
LABEL_47:
    v9 = (unsigned int)v12;
    goto LABEL_9;
  }
  v13 = 0;
  v30 = 0;
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v33 + 64LL))(v33, 1, &v25, 0);
    if ( v6 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
      {
        goto LABEL_133;
      }
      v24 = 127;
      goto LABEL_132;
    }
    v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v25)(v25, &IID_IPropertyBag, &v35);
    if ( v6 >= 0 )
      break;
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v14 = 128;
LABEL_54:
    WPP_SF_d(v7[1].Flink, v14, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
LABEL_55:
    v4 = 0;
LABEL_92:
    v30 = ++v13;
    if ( v13 >= i )
      goto LABEL_11;
  }
  VariantInit(&pvarg);
  v6 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v35 + 24LL))(
         v35,
         L"NA_NetworkClass",
         &pvarg,
         0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_55;
    }
    v14 = 129;
    goto LABEL_54;
  }
  if ( pvarg.lVal == 1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 130, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
    }
    *v2 = 1;
    v4 = 0;
LABEL_91:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_92;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 144LL))(v25, &v28);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_133;
    }
    v24 = 131;
    goto LABEL_132;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v25 + 56LL))(v25, &bstrString);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_133;
    }
    v24 = 132;
    goto LABEL_132;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 104LL))(v25, &v32);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_133;
    }
    v24 = 133;
    goto LABEL_132;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 136LL))(v25, &v27);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_133;
    }
    v24 = 134;
    goto LABEL_132;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v25 + 88LL))(v25, &v41);
  if ( v6 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) == 0 )
    {
      goto LABEL_133;
    }
    v24 = 135;
LABEL_132:
    WPP_SF_d(v7[1].Flink, v24, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v6);
    v7 = WPP_GLOBAL_Control;
LABEL_133:
    v4 = 0;
    goto LABEL_11;
  }
  v4 = VpnAlloc(64);
  if ( !v4 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_11;
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 136, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
      v7 = WPP_GLOBAL_Control;
    }
    if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v7[1].Blink) & 1) == 0 )
      goto LABEL_11;
    v23 = 137;
LABEL_100:
    WPP_SF_d(v7[1].Flink, v23, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
LABEL_10:
    v7 = WPP_GLOBAL_Control;
    goto LABEL_11;
  }
  while ( 1 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, unsigned int *))(*(_QWORD *)v32 + 64LL))(
           v32,
           1,
           &v34,
           &v26);
    if ( v6 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v8 = 138;
        v9 = (unsigned int)v6;
        goto LABEL_9;
      }
      goto LABEL_11;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 139, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v26);
    }
    if ( v6 || !v26 )
      break;
    v12 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v34 + 96LL))(v34, &rguid);
    v6 = v12;
    if ( v12 < 0 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v8 = 140;
        goto LABEL_47;
      }
      goto LABEL_11;
    }
    v15 = (OLECHAR *)VpnAlloc(544);
    v16 = v15;
    if ( !v15 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      {
        if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 141, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
          v7 = WPP_GLOBAL_Control;
        }
        if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v7[1].Blink) & 1) != 0 )
        {
          v23 = 142;
          goto LABEL_100;
        }
      }
      goto LABEL_11;
    }
    StringFromGUID2(&rguid, v15, 260);
    v17 = *(_QWORD *)(v4 + 56);
    if ( v17 )
      *((_QWORD *)v16 + 67) = v17;
    ++*(_DWORD *)(v4 + 48);
    *(_QWORD *)(v4 + 56) = v16;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v18 = (_QWORD *)(v4 + 16);
  *(_DWORD *)(v4 + 24) = v27;
  *(_DWORD *)(v4 + 28) = v28;
  *(_OWORD *)(v4 + 32) = v41;
  v12 = VpnStringCopy(bstrString);
  v6 = v12;
  if ( v12 >= 0 )
  {
    v19 = (_WORD *)*v18;
    if ( *(_WORD *)*v18 )
    {
      do
      {
        v20 = (unsigned int)v3;
        v21 = tolower((unsigned __int16)v19[(unsigned int)v3]);
        v3 = (unsigned int)(v3 + 1);
        *(_WORD *)(*v18 + 2 * v20) = v21;
        v19 = (_WORD *)*v18;
      }
      while ( *(_WORD *)(*v18 + 2 * v3) );
      i = v29;
      LODWORD(v3) = 0;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_S(WPP_GLOBAL_Control[1].Flink, 144, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v19);
    }
    Blink = g_NlmNetwork.Blink;
    if ( g_NlmNetwork.Blink->Flink != &g_NlmNetwork )
      __fastfail(3u);
    *(_QWORD *)v4 = &g_NlmNetwork;
    *(_QWORD *)(v4 + 8) = Blink;
    Blink->Flink = (struct _LIST_ENTRY *)v4;
    g_NlmNetwork.Blink = (struct _LIST_ENTRY *)v4;
    v4 = 0;
    SysFreeString(bstrString);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v32 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v13 = v30;
    v2 = v38;
    v25 = 0;
    goto LABEL_91;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v8 = 143;
    goto LABEL_47;
  }
LABEL_11:
  if ( v6 )
  {
    NlmFreeNetwork((struct _NETWORKPROFILE *)v4);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    v7 = WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v31 )
  {
    CoUninitialize();
    v7 = WPP_GLOBAL_Control;
  }
  if ( v6 < 0 )
  {
    NlmNetworkListFree(v7);
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v7[1].Blink) & 8) != 0 )
    WPP_SF_d(v7[1].Flink, 145, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b9a80  push    rbp
0x1800b9a82  push    rbx
0x1800b9a83  push    rsi
0x1800b9a84  push    rdi
0x1800b9a85  push    r12
0x1800b9a87  push    r13
0x1800b9a89  push    r14
0x1800b9a8b  push    r15
0x1800b9a8d  lea     rbp, [rsp-1Fh]
0x1800b9a92  sub     rsp, 0D8h
0x1800b9a99  mov     rax, cs:__security_cookie
0x1800b9aa0  xor     rax, rsp
0x1800b9aa3  mov     [rbp+57h+var_50], rax
0x1800b9aa7  mov     r15, rdx
0x1800b9aaa  mov     [rbp+57h+var_90], rdx
0x1800b9aae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ab5  lea     rbx, WPP_GLOBAL_Control
0x1800b9abc  lea     r13, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9ac3  cmp     rcx, rbx
0x1800b9ac6  jz      short loc_1800B9ADF
0x1800b9ac8  test    byte ptr [rcx+1Ch], 8
0x1800b9acc  jz      short loc_1800B9ADF
0x1800b9ace  mov     rcx, [rcx+10h]
0x1800b9ad2  mov     edx, 7Ah ; 'z'
0x1800b9ad7  mov     r8, r13
0x1800b9ada  call    WPP_SF_
0x1800b9adf  xor     r12d, r12d
0x1800b9ae2  xorps   xmm0, xmm0
0x1800b9ae5  xorps   xmm1, xmm1
0x1800b9ae8  mov     [rbp+57h+var_98], r12
0x1800b9aec  xor     eax, eax
0x1800b9aee  mov     [rbp+57h+var_B8], r12
0x1800b9af2  xor     edx, edx; dwCoInit
0x1800b9af4  mov     [rbp+57h+var_C0], r12
0x1800b9af8  xor     ecx, ecx; pvReserved
0x1800b9afa  mov     [rbp+57h+var_B0], r12
0x1800b9afe  mov     [rsp+110h+var_E0], r12
0x1800b9b03  mov     r14d, r12d
0x1800b9b06  mov     [rbp+57h+var_D0], r12d
0x1800b9b0a  mov     [rbp+57h+var_D4], r12d
0x1800b9b0e  movups  [rbp+57h+var_60], xmm0
0x1800b9b12  mov     [rbp+57h+bstrString], r12
0x1800b9b16  mov     [rsp+110h+var_D8], r12d
0x1800b9b1b  movups  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800b9b1f  mov     [rbp+57h+var_A8], r12
0x1800b9b23  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x1800b9b27  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800b9b2b  call    cs:__imp_CoInitializeEx
0x1800b9b32  nop     dword ptr [rax+rax+00h]
0x1800b9b37  mov     edi, eax
0x1800b9b39  test    eax, eax
0x1800b9b3b  jns     loc_1800B9C9A
0x1800b9b41  mov     [rbp+57h+var_C4], r12d
0x1800b9b45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b4c  cmp     rcx, rbx
0x1800b9b4f  jz      short loc_1800B9B75
0x1800b9b51  lea     esi, [r12+1]
0x1800b9b56  test    [rcx+1Ch], sil
0x1800b9b5a  jz      short loc_1800B9B75
0x1800b9b5c  lea     edx, [rsi+7Ah]
0x1800b9b5f  mov     r9d, eax
0x1800b9b62  mov     r8, r13
0x1800b9b65  mov     rcx, [rcx+10h]
0x1800b9b69  call    WPP_SF_d
0x1800b9b6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b75  test    edi, edi
0x1800b9b77  jz      short loc_1800B9B88
0x1800b9b79  mov     rcx, r14; lpMem
0x1800b9b7c  call    ?NlmFreeNetwork@@YAXPEAU_NETWORKPROFILE@@@Z; NlmFreeNetwork(_NETWORKPROFILE *)
0x1800b9b81  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9b88  mov     rdx, [rbp+57h+var_B0]
0x1800b9b8c  test    rdx, rdx
0x1800b9b8f  jz      short loc_1800B9BA7
0x1800b9b91  mov     rax, [rdx]
0x1800b9b94  mov     rcx, rdx
0x1800b9b97  mov     rax, [rax+10h]
0x1800b9b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9ba0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ba7  mov     rdx, [rbp+57h+var_C0]
0x1800b9bab  test    rdx, rdx
0x1800b9bae  jz      short loc_1800B9BC6
0x1800b9bb0  mov     rax, [rdx]
0x1800b9bb3  mov     rcx, rdx
0x1800b9bb6  mov     rax, [rax+10h]
0x1800b9bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9bbf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9bc6  mov     rdx, [rsp+110h+var_E0]
0x1800b9bcb  test    rdx, rdx
0x1800b9bce  jz      short loc_1800B9BE6
0x1800b9bd0  mov     rax, [rdx]
0x1800b9bd3  mov     rcx, rdx
0x1800b9bd6  mov     rax, [rax+10h]
0x1800b9bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9be6  mov     rdx, [rbp+57h+var_B8]
0x1800b9bea  test    rdx, rdx
0x1800b9bed  jz      short loc_1800B9C05
0x1800b9bef  mov     rax, [rdx]
0x1800b9bf2  mov     rcx, rdx
0x1800b9bf5  mov     rax, [rax+10h]
0x1800b9bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c05  mov     rdx, [rbp+57h+var_98]
0x1800b9c09  test    rdx, rdx
0x1800b9c0c  jz      short loc_1800B9C24
0x1800b9c0e  mov     rax, [rdx]
0x1800b9c11  mov     rcx, rdx
0x1800b9c14  mov     rax, [rax+10h]
0x1800b9c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9c1d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c24  cmp     [rbp+57h+var_C4], r12d
0x1800b9c28  jz      short loc_1800B9C3D
0x1800b9c2a  call    cs:__imp_CoUninitialize
0x1800b9c31  nop     dword ptr [rax+rax+00h]
0x1800b9c36  mov     rcx, cs:WPP_GLOBAL_Control; struct _LIST_ENTRY *
0x1800b9c3d  test    edi, edi
0x1800b9c3f  jns     short loc_1800B9C4D
0x1800b9c41  call    ?NlmNetworkListFree@@YAXPEAU_LIST_ENTRY@@@Z; NlmNetworkListFree(_LIST_ENTRY *)
0x1800b9c46  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9c4d  lea     rax, WPP_GLOBAL_Control
0x1800b9c54  cmp     rcx, rax
0x1800b9c57  jz      short loc_1800B9C77
0x1800b9c59  test    byte ptr [rcx+1Ch], 8
0x1800b9c5d  jz      short loc_1800B9C77
0x1800b9c5f  mov     rcx, [rcx+10h]
0x1800b9c63  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9c6a  mov     edx, 91h
0x1800b9c6f  mov     r9d, edi
0x1800b9c72  call    WPP_SF_d
0x1800b9c77  mov     eax, edi
0x1800b9c79  mov     rcx, [rbp+57h+var_50]
0x1800b9c7d  xor     rcx, rsp; StackCookie
0x1800b9c80  call    __security_check_cookie
0x1800b9c85  add     rsp, 0D8h
0x1800b9c8c  pop     r15
0x1800b9c8e  pop     r14
0x1800b9c90  pop     r13
0x1800b9c92  pop     r12
0x1800b9c94  pop     rdi
0x1800b9c95  pop     rsi
0x1800b9c96  pop     rbx
0x1800b9c97  pop     rbp
0x1800b9c98  retn
0x1800b9c9a  mov     esi, 1
0x1800b9c9f  lea     rax, [rbp+57h+var_98]
0x1800b9ca3  lea     r9, IID_INetworkListManager; riid
0x1800b9caa  mov     [rbp+57h+var_C4], esi
0x1800b9cad  xor     edx, edx; pUnkOuter
0x1800b9caf  mov     [rsp+110h+ppv], rax; ppv
0x1800b9cb4  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800b9cbb  lea     r8d, [rsi+16h]; dwClsContext
0x1800b9cbf  call    cs:__imp_CoCreateInstance
0x1800b9cc6  nop     dword ptr [rax+rax+00h]
0x1800b9ccb  mov     edi, eax
0x1800b9ccd  test    eax, eax
0x1800b9ccf  jns     short loc_1800B9CF3
0x1800b9cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9cd8  cmp     rcx, rbx
0x1800b9cdb  jz      loc_1800B9B75
0x1800b9ce1  test    [rcx+1Ch], sil
0x1800b9ce5  jz      loc_1800B9B75
0x1800b9ceb  lea     edx, [rsi+7Bh]
0x1800b9cee  jmp     loc_1800B9B5F
0x1800b9cf3  mov     rcx, [rbp+57h+var_98]
0x1800b9cf7  lea     r8, [rbp+57h+var_B8]
0x1800b9cfb  mov     edx, esi
0x1800b9cfd  mov     rax, [rcx]
0x1800b9d00  mov     rax, [rax+38h]
0x1800b9d04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d09  mov     edi, eax
0x1800b9d0b  test    eax, eax
0x1800b9d0d  jns     short loc_1800B9D33
0x1800b9d0f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d16  cmp     rcx, rbx
0x1800b9d19  jz      loc_1800B9B75
0x1800b9d1f  test    [rcx+1Ch], sil
0x1800b9d23  jz      loc_1800B9B75
0x1800b9d29  mov     edx, 7Dh ; '}'
0x1800b9d2e  jmp     loc_1800B9B5F
0x1800b9d33  mov     r13d, r12d
0x1800b9d36  mov     rcx, [rbp+57h+var_B8]
0x1800b9d3a  lea     r8, [rsp+110h+var_E0]
0x1800b9d3f  xor     r9d, r9d
0x1800b9d42  mov     edx, esi
0x1800b9d44  mov     rax, [rcx]
0x1800b9d47  mov     rax, [rax+40h]
0x1800b9d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d50  mov     edi, eax
0x1800b9d52  test    eax, eax
0x1800b9d54  jnz     short loc_1800B9D71
0x1800b9d56  mov     rcx, [rsp+110h+var_E0]
0x1800b9d5b  mov     rax, [rcx]
0x1800b9d5e  mov     rax, [rax+10h]
0x1800b9d62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d67  add     r13d, esi
0x1800b9d6a  mov     [rsp+110h+var_E0], r12
0x1800b9d6f  jmp     short loc_1800B9D36
0x1800b9d71  mov     [rbp+57h+var_CC], r13d
0x1800b9d75  test    r13d, r13d
0x1800b9d78  jz      loc_1800B9B6E
0x1800b9d7e  mov     rcx, [rbp+57h+var_B8]
0x1800b9d82  mov     rax, [rcx]
0x1800b9d85  mov     rax, [rax+50h]
0x1800b9d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9d8e  mov     edi, eax
0x1800b9d90  test    eax, eax
0x1800b9d92  jns     short loc_1800B9DC2
0x1800b9d94  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9d9b  cmp     rcx, rbx
0x1800b9d9e  jz      loc_1800B9B75
0x1800b9da4  test    [rcx+1Ch], sil
0x1800b9da8  jz      loc_1800B9B75
0x1800b9dae  mov     edx, 7Eh ; '~'
0x1800b9db3  mov     r9d, eax
0x1800b9db6  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9dbd  jmp     loc_1800B9B65
0x1800b9dc2  mov     ebx, r12d
0x1800b9dc5  mov     [rbp+57h+var_C8], ebx
0x1800b9dc8  mov     rcx, [rbp+57h+var_B8]
0x1800b9dcc  lea     r8, [rsp+110h+var_E0]
0x1800b9dd1  xor     r9d, r9d
0x1800b9dd4  mov     edx, esi
0x1800b9dd6  mov     rax, [rcx]
0x1800b9dd9  mov     rax, [rax+40h]
0x1800b9ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9de2  mov     edi, eax
0x1800b9de4  test    eax, eax
0x1800b9de6  jnz     loc_1800BA3C2
0x1800b9dec  mov     rcx, [rsp+110h+var_E0]
0x1800b9df1  lea     r8, [rbp+57h+var_A8]
0x1800b9df5  lea     rdx, IID_IPropertyBag
0x1800b9dfc  mov     rax, [rcx]
0x1800b9dff  mov     rax, [rax]
0x1800b9e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e07  mov     edi, eax
0x1800b9e09  test    eax, eax
0x1800b9e0b  jns     short loc_1800B9E4D
0x1800b9e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9e14  lea     rax, WPP_GLOBAL_Control
0x1800b9e1b  cmp     rcx, rax
0x1800b9e1e  jz      short loc_1800B9E45
0x1800b9e20  test    [rcx+1Ch], sil
0x1800b9e24  jz      short loc_1800B9E45
0x1800b9e26  mov     edx, 80h
0x1800b9e2b  mov     rcx, [rcx+10h]
0x1800b9e2f  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9e36  mov     r9d, edi
0x1800b9e39  call    WPP_SF_d
0x1800b9e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9e45  mov     r14, r12
0x1800b9e48  jmp     loc_1800BA198
0x1800b9e4d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b9e51  call    cs:__imp_VariantInit
0x1800b9e58  nop     dword ptr [rax+rax+00h]
0x1800b9e5d  mov     rcx, [rbp+57h+var_A8]
0x1800b9e61  lea     r8, [rbp+57h+pvarg]
0x1800b9e65  xor     r9d, r9d
0x1800b9e68  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800b9e6f  mov     rax, [rcx]
0x1800b9e72  mov     rax, [rax+18h]
0x1800b9e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e7b  mov     rcx, [rbp+57h+var_A8]
0x1800b9e7f  mov     edi, eax
0x1800b9e81  mov     rax, [rcx]
0x1800b9e84  mov     rax, [rax+10h]
0x1800b9e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9e8d  test    edi, edi
0x1800b9e8f  jns     short loc_1800B9EB4
0x1800b9e91  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9e98  lea     rax, WPP_GLOBAL_Control
0x1800b9e9f  cmp     rcx, rax
0x1800b9ea2  jz      short loc_1800B9E45
0x1800b9ea4  test    [rcx+1Ch], sil
0x1800b9ea8  jz      short loc_1800B9E45
0x1800b9eaa  mov     edx, 81h
0x1800b9eaf  jmp     loc_1800B9E2B
0x1800b9eb4  cmp     dword ptr [rbp+57h+pvarg+8], esi
0x1800b9eb7  jnz     short loc_1800B9EF2
0x1800b9eb9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9ec0  lea     rax, WPP_GLOBAL_Control
0x1800b9ec7  cmp     rcx, rax
0x1800b9eca  jz      short loc_1800B9EE7
0x1800b9ecc  test    byte ptr [rcx+1Ch], 4
0x1800b9ed0  jz      short loc_1800B9EE7
0x1800b9ed2  mov     rcx, [rcx+10h]
0x1800b9ed6  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9edd  mov     edx, 82h
0x1800b9ee2  call    WPP_SF_
0x1800b9ee7  mov     [r15], esi
0x1800b9eea  mov     r14, r12
0x1800b9eed  jmp     loc_1800BA191
0x1800b9ef2  mov     rcx, [rsp+110h+var_E0]
0x1800b9ef7  lea     rdx, [rbp+57h+var_D0]
0x1800b9efb  mov     rax, [rcx]
0x1800b9efe  mov     rax, [rax+90h]
0x1800b9f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9f0a  mov     edi, eax
0x1800b9f0c  test    eax, eax
0x1800b9f0e  js      loc_1800BA382
0x1800b9f14  mov     rcx, [rsp+110h+var_E0]
  ... truncated ...
```
