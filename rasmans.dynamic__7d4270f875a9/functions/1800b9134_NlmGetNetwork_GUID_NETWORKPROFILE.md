# NlmGetNetwork(_GUID,_NETWORKPROFILE * *)

- ea: `0x1800b9134`
- end: `0x1800b99cb`
- name: `?NlmGetNetwork@@YAJU_GUID@@PEAPEAU_NETWORKPROFILE@@@Z`
- size: `2199`
- prototype: `__int64 __fastcall(struct _GUID *Buf2, struct _NETWORKPROFILE **)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800b8800`
- `0x1800b8920`
- `0x1800b8d20`

## callees

- `0x180005bcc`
- `0x180005bfc`
- `0x18000c340`
- `0x180033a48`
- `0x180068a80`
- `0x1800b90a0`
- `0x1800b9134`
- `0x1800e3ca0`
- `0x1800e4534`
- `0x1800e8e72`
- `0x1800e8ef0`
- `0x1800eb010`

## import_xrefs

- `msvcrt!tolower` at `0x1800b9920`
- `msvcrt!tolower` at `0x1800b9920`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b9263`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800b9263`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b91e8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800b91e8`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b97a1`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b97a1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b96d0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800b96d0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b994b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800b994b`
- `OLEAUT32!__imp_VariantInit` at `0x1800b933d`
- `OLEAUT32!__imp_VariantInit` at `0x1800b933d`

## pseudocode

```c
__int64 __fastcall NlmGetNetwork(struct _GUID *Buf2, struct _NETWORKPROFILE **a2)
{
  struct _NETWORKPROFILE **v2; // r13
  __int64 v4; // r12
  __int64 v5; // r14
  HRESULT v6; // eax
  int v7; // edi
  int v8; // r15d
  struct _LIST_ENTRY *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  OLECHAR *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  _QWORD *v17; // r15
  int v18; // eax
  _WORD *v19; // rcx
  __int64 v20; // rbx
  __int16 v21; // ax
  __int64 v22; // [rsp+38h] [rbp-81h] BYREF
  int v23; // [rsp+40h] [rbp-79h] BYREF
  int v24; // [rsp+44h] [rbp-75h] BYREF
  int v25; // [rsp+48h] [rbp-71h] BYREF
  BSTR bstrString; // [rsp+50h] [rbp-69h] BYREF
  __int64 v27; // [rsp+58h] [rbp-61h] BYREF
  __int64 v28; // [rsp+60h] [rbp-59h] BYREF
  __int64 v29; // [rsp+68h] [rbp-51h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-49h] BYREF
  struct _NETWORKPROFILE **v31; // [rsp+78h] [rbp-41h]
  VARIANTARG pvarg; // [rsp+80h] [rbp-39h] BYREF
  struct _GUID v33; // [rsp+A0h] [rbp-19h] BYREF
  __int128 Buf1; // [rsp+B0h] [rbp-9h] BYREF
  GUID rguid; // [rsp+C0h] [rbp+7h] BYREF

  v2 = a2;
  v31 = a2;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 8) != 0 )
    WPP_SF__guid_(WPP_GLOBAL_Control[1].Flink, 83, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, Buf2);
  LODWORD(v4) = 0;
  Buf1 = 0;
  ppv = 0;
  v22 = 0;
  rguid = GUID_NULL;
  v29 = 0;
  v5 = 0;
  v27 = 0;
  bstrString = 0;
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v28 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v6 = CoInitializeEx(0, 0);
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 0;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 84;
LABEL_8:
      v11 = (unsigned int)v6;
LABEL_9:
      WPP_SF_d(v9[1].Flink, v10, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, v11);
LABEL_31:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  v8 = 1;
  v6 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &ppv);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 85;
      goto LABEL_8;
    }
LABEL_65:
    if ( !v7 )
      goto LABEL_67;
    goto LABEL_66;
  }
  v33 = *Buf2;
  v6 = (*(__int64 (__fastcall **)(LPVOID, struct _GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v33, &v22);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 86;
      goto LABEL_8;
    }
    goto LABEL_65;
  }
  v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v22)(v22, &IID_IPropertyBag, &v28);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 87;
      goto LABEL_8;
    }
    goto LABEL_65;
  }
  VariantInit(&pvarg);
  v7 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v28 + 24LL))(
         v28,
         L"NA_NetworkClass",
         &pvarg,
         0);
  if ( v7 < 0
    && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 88, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v7);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v7 < 0 )
  {
LABEL_64:
    v9 = WPP_GLOBAL_Control;
    goto LABEL_65;
  }
  if ( pvarg.lVal == 1 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control[1].Flink, 89, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids);
      goto LABEL_31;
    }
    goto LABEL_65;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v22 + 88LL))(v22, &Buf1);
  v7 = v6;
  if ( v6 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      v10 = 90;
      goto LABEL_8;
    }
    goto LABEL_65;
  }
  if ( !memcmp_0(&Buf1, Buf2, 0x10u) )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v22 + 104LL))(v22, &v29);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 91;
        goto LABEL_8;
      }
      goto LABEL_65;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 144LL))(v22, &v24);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 92;
        goto LABEL_8;
      }
      goto LABEL_65;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v22 + 136LL))(v22, &v23);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 93;
        goto LABEL_8;
      }
      goto LABEL_65;
    }
    v6 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v22 + 56LL))(v22, &bstrString);
    v7 = v6;
    if ( v6 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 94;
        goto LABEL_8;
      }
      goto LABEL_65;
    }
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
    {
      WPP_SF_Sdd(
        WPP_GLOBAL_Control[1].Flink,
        95,
        (unsigned int)&WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids,
        (_DWORD)bstrString,
        v24,
        v23);
    }
    v5 = VpnAlloc(64);
    if ( v5 )
    {
      while ( 1 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 64LL))(v29, 1, &v27, &v25);
        v7 = v6;
        if ( v6 < 0 )
          break;
        if ( v6 || !v25 )
        {
          v17 = (_QWORD *)(v5 + 16);
          *(_DWORD *)(v5 + 24) = v23;
          *(_DWORD *)(v5 + 28) = v24;
          *(_OWORD *)(v5 + 32) = Buf1;
          v18 = VpnStringCopy(bstrString);
          v7 = v18;
          if ( v18 >= 0 )
          {
            v19 = (_WORD *)*v17;
            if ( *(_WORD *)*v17 )
            {
              do
              {
                v20 = (unsigned int)v4;
                v21 = tolower((unsigned __int16)v19[(unsigned int)v4]);
                v4 = (unsigned int)(v4 + 1);
                *(_WORD *)(*v17 + 2 * v20) = v21;
                v19 = (_WORD *)*v17;
              }
              while ( *(_WORD *)(*v17 + 2 * v4) );
              v2 = v31;
            }
            SysFreeString(bstrString);
            *v2 = (struct _NETWORKPROFILE *)v5;
            v8 = 1;
            v9 = WPP_GLOBAL_Control;
            v5 = 0;
          }
          else
          {
            v9 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control[1].Flink,
                103,
                &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids,
                (unsigned int)v18);
              v9 = WPP_GLOBAL_Control;
            }
            v8 = 1;
          }
          goto LABEL_65;
        }
        v6 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v27 + 96LL))(v27, &rguid);
        v7 = v6;
        if ( v6 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
          {
            v10 = 99;
            goto LABEL_8;
          }
          goto LABEL_65;
        }
        v14 = (OLECHAR *)VpnAlloc(544);
        v15 = (__int64)v14;
        if ( !v14 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
          {
            if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 100, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 1) != 0 )
            {
              v12 = 101;
              goto LABEL_63;
            }
          }
          goto LABEL_65;
        }
        StringFromGUID2(&rguid, v14, 260);
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 4) != 0 )
        {
          WPP_SF_SS(
            WPP_GLOBAL_Control[1].Flink,
            102,
            (unsigned int)&WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids,
            (_DWORD)bstrString,
            v15);
        }
        v16 = *(_QWORD *)(v5 + 56);
        if ( v16 )
          *(_QWORD *)(v15 + 536) = v16;
        ++*(_DWORD *)(v5 + 48);
        *(_QWORD *)(v5 + 56) = v15;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
      {
        v10 = 98;
        goto LABEL_8;
      }
      goto LABEL_65;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
      goto LABEL_65;
    if ( (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 96, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
      v9 = WPP_GLOBAL_Control;
    }
    if ( v9 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control || (BYTE4(v9[1].Blink) & 1) == 0 )
      goto LABEL_65;
    v12 = 97;
LABEL_63:
    WPP_SF_d(v9[1].Flink, v12, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, 14);
    goto LABEL_64;
  }
  v7 = -2147467259;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control[1].Blink) & 1) != 0 )
  {
    v10 = 104;
    v11 = 2147500037LL;
    goto LABEL_9;
  }
LABEL_66:
  NlmFreeNetwork((struct _NETWORKPROFILE *)v5);
  v9 = WPP_GLOBAL_Control;
LABEL_67:
  if ( v27 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v29 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v9 = WPP_GLOBAL_Control;
  }
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    v9 = WPP_GLOBAL_Control;
  }
  if ( v8 )
  {
    CoUninitialize();
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && (BYTE4(v9[1].Blink) & 8) != 0 )
    WPP_SF_d(v9[1].Flink, 105, &WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids, (unsigned int)v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800b9134  mov     [rsp-8+arg_10], rbx
0x1800b9139  push    rbp
0x1800b913a  push    rsi
0x1800b913b  push    rdi
0x1800b913c  push    r12
0x1800b913e  push    r13
0x1800b9140  push    r14
0x1800b9142  push    r15
0x1800b9144  lea     rbp, [rsp-27h]
0x1800b9149  sub     rsp, 0E0h
0x1800b9150  mov     rax, cs:__security_cookie
0x1800b9157  xor     rax, rsp
0x1800b915a  mov     [rbp+57h+var_40], rax
0x1800b915e  mov     r13, rdx
0x1800b9161  mov     [rbp+57h+var_98], rdx
0x1800b9165  mov     rbx, rcx
0x1800b9168  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b916f  lea     rax, WPP_GLOBAL_Control
0x1800b9176  cmp     rcx, rax
0x1800b9179  jz      short loc_1800B9199
0x1800b917b  test    byte ptr [rcx+1Ch], 8
0x1800b917f  jz      short loc_1800B9199
0x1800b9181  mov     rcx, [rcx+10h]
0x1800b9185  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b918c  mov     edx, 53h ; 'S'
0x1800b9191  mov     r9, rbx
0x1800b9194  call    WPP_SF__guid_
0x1800b9199  xor     r12d, r12d
0x1800b919c  xorps   xmm0, xmm0
0x1800b919f  movups  [rbp+57h+Buf1], xmm0
0x1800b91a3  xor     eax, eax
0x1800b91a5  xor     edx, edx; dwCoInit
0x1800b91a7  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800b91ae  mov     [rbp+57h+var_A0], r12
0x1800b91b2  xor     ecx, ecx; pvReserved
0x1800b91b4  xorps   xmm1, xmm1
0x1800b91b7  mov     [rsp+110h+var_D8], r12
0x1800b91bc  movdqu  xmmword ptr [rbp+57h+rguid.Data1], xmm0
0x1800b91c1  mov     [rbp+57h+var_A8], r12
0x1800b91c5  mov     r14d, r12d
0x1800b91c8  mov     [rbp+57h+var_B8], r12
0x1800b91cc  mov     [rbp+57h+bstrString], r12
0x1800b91d0  mov     [rbp+57h+var_CC], r12d
0x1800b91d4  mov     [rbp+57h+var_D0], r12d
0x1800b91d8  mov     [rbp+57h+var_C8], r12d
0x1800b91dc  mov     [rbp+57h+var_B0], r12
0x1800b91e0  movups  xmmword ptr [rbp+57h+pvarg], xmm1
0x1800b91e4  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800b91e8  call    cs:__imp_CoInitializeEx
0x1800b91ef  nop     dword ptr [rax+rax+00h]
0x1800b91f4  mov     edi, eax
0x1800b91f6  test    eax, eax
0x1800b91f8  jns     short loc_1800B923E
0x1800b91fa  mov     r15d, r12d
0x1800b91fd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9204  lea     rbx, WPP_GLOBAL_Control
0x1800b920b  cmp     rcx, rbx
0x1800b920e  jz      loc_1800B963B
0x1800b9214  lea     esi, [r12+1]
0x1800b9219  test    [rcx+1Ch], sil
0x1800b921d  jz      loc_1800B963B
0x1800b9223  lea     edx, [rsi+53h]
0x1800b9226  mov     r9d, eax
0x1800b9229  mov     rcx, [rcx+10h]
0x1800b922d  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9234  call    WPP_SF_d
0x1800b9239  jmp     loc_1800B93F1
0x1800b923e  mov     esi, 1
0x1800b9243  lea     rax, [rbp+57h+var_A0]
0x1800b9247  lea     r9, IID_INetworkListManager; riid
0x1800b924e  mov     [rsp+110h+ppv], rax; ppv
0x1800b9253  xor     edx, edx; pUnkOuter
0x1800b9255  lea     rcx, CLSID_NetworkListManager; rclsid
0x1800b925c  mov     r15d, esi
0x1800b925f  lea     r8d, [rsi+16h]; dwClsContext
0x1800b9263  call    cs:__imp_CoCreateInstance
0x1800b926a  nop     dword ptr [rax+rax+00h]
0x1800b926f  mov     edi, eax
0x1800b9271  test    eax, eax
0x1800b9273  jns     short loc_1800B929B
0x1800b9275  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b927c  lea     rbx, WPP_GLOBAL_Control
0x1800b9283  cmp     rcx, rbx
0x1800b9286  jz      loc_1800B963B
0x1800b928c  test    [rcx+1Ch], sil
0x1800b9290  jz      loc_1800B963B
0x1800b9296  lea     edx, [rsi+54h]
0x1800b9299  jmp     short loc_1800B9226
0x1800b929b  mov     rcx, [rbp+57h+var_A0]
0x1800b929f  lea     r8, [rsp+110h+var_D8]
0x1800b92a4  movaps  xmm0, xmmword ptr [rbx]
0x1800b92a7  lea     rdx, [rbp+57h+var_70]
0x1800b92ab  movdqa  [rbp+57h+var_70], xmm0
0x1800b92b0  mov     rax, [rcx]
0x1800b92b3  mov     rax, [rax+40h]
0x1800b92b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b92bc  mov     edi, eax
0x1800b92be  test    eax, eax
0x1800b92c0  jns     short loc_1800B92ED
0x1800b92c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b92c9  lea     rbx, WPP_GLOBAL_Control
0x1800b92d0  cmp     rcx, rbx
0x1800b92d3  jz      loc_1800B963B
0x1800b92d9  test    [rcx+1Ch], sil
0x1800b92dd  jz      loc_1800B963B
0x1800b92e3  mov     edx, 56h ; 'V'
0x1800b92e8  jmp     loc_1800B9226
0x1800b92ed  mov     rcx, [rsp+110h+var_D8]
0x1800b92f2  lea     r8, [rbp+57h+var_B0]
0x1800b92f6  lea     rdx, IID_IPropertyBag
0x1800b92fd  mov     rax, [rcx]
0x1800b9300  mov     rax, [rax]
0x1800b9303  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9308  mov     edi, eax
0x1800b930a  test    eax, eax
0x1800b930c  jns     short loc_1800B9339
0x1800b930e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9315  lea     rbx, WPP_GLOBAL_Control
0x1800b931c  cmp     rcx, rbx
0x1800b931f  jz      loc_1800B963B
0x1800b9325  test    [rcx+1Ch], sil
0x1800b9329  jz      loc_1800B963B
0x1800b932f  mov     edx, 57h ; 'W'
0x1800b9334  jmp     loc_1800B9226
0x1800b9339  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b933d  call    cs:__imp_VariantInit
0x1800b9344  nop     dword ptr [rax+rax+00h]
0x1800b9349  mov     rcx, [rbp+57h+var_B0]
0x1800b934d  lea     r8, [rbp+57h+pvarg]
0x1800b9351  xor     r9d, r9d
0x1800b9354  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x1800b935b  mov     rax, [rcx]
0x1800b935e  mov     rax, [rax+18h]
0x1800b9362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9367  mov     edi, eax
0x1800b9369  test    eax, eax
0x1800b936b  jns     short loc_1800B939E
0x1800b936d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9374  lea     rax, WPP_GLOBAL_Control
0x1800b937b  cmp     rcx, rax
0x1800b937e  jz      short loc_1800B939E
0x1800b9380  test    [rcx+1Ch], sil
0x1800b9384  jz      short loc_1800B939E
0x1800b9386  mov     rcx, [rcx+10h]
0x1800b938a  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9391  mov     edx, 58h ; 'X'
0x1800b9396  mov     r9d, edi
0x1800b9399  call    WPP_SF_d
0x1800b939e  mov     rcx, [rbp+57h+var_B0]
0x1800b93a2  mov     rax, [rcx]
0x1800b93a5  mov     rax, [rax+10h]
0x1800b93a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b93ae  test    edi, edi
0x1800b93b0  js      loc_1800B962D
0x1800b93b6  cmp     dword ptr [rbp+57h+pvarg+8], esi
0x1800b93b9  jnz     short loc_1800B93FD
0x1800b93bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b93c2  lea     rbx, WPP_GLOBAL_Control
0x1800b93c9  cmp     rcx, rbx
0x1800b93cc  jz      loc_1800B963B
0x1800b93d2  test    byte ptr [rcx+1Ch], 4
0x1800b93d6  jz      loc_1800B963B
0x1800b93dc  mov     rcx, [rcx+10h]
0x1800b93e0  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b93e7  mov     edx, 59h ; 'Y'
0x1800b93ec  call    WPP_SF_
0x1800b93f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b93f8  jmp     loc_1800B963B
0x1800b93fd  mov     rcx, [rsp+110h+var_D8]
0x1800b9402  lea     rdx, [rbp+57h+Buf1]
0x1800b9406  mov     rax, [rcx]
0x1800b9409  mov     rax, [rax+58h]
0x1800b940d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9412  mov     edi, eax
0x1800b9414  test    eax, eax
0x1800b9416  jns     short loc_1800B9443
0x1800b9418  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b941f  lea     rbx, WPP_GLOBAL_Control
0x1800b9426  cmp     rcx, rbx
0x1800b9429  jz      loc_1800B963B
0x1800b942f  test    [rcx+1Ch], sil
0x1800b9433  jz      loc_1800B963B
0x1800b9439  mov     edx, 5Ah ; 'Z'
0x1800b943e  jmp     loc_1800B9226
0x1800b9443  mov     r8d, 10h; Size
0x1800b9449  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1800b944d  mov     rdx, rbx; Buf2
0x1800b9450  call    memcmp_0
0x1800b9455  test    eax, eax
0x1800b9457  jnz     loc_1800B9998
0x1800b945d  mov     rcx, [rsp+110h+var_D8]
0x1800b9462  lea     rdx, [rbp+57h+var_A8]
0x1800b9466  mov     rax, [rcx]
0x1800b9469  mov     rax, [rax+68h]
0x1800b946d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9472  mov     edi, eax
0x1800b9474  test    eax, eax
0x1800b9476  jns     short loc_1800B94A3
0x1800b9478  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b947f  lea     rbx, WPP_GLOBAL_Control
0x1800b9486  cmp     rcx, rbx
0x1800b9489  jz      loc_1800B963B
0x1800b948f  test    [rcx+1Ch], sil
0x1800b9493  jz      loc_1800B963B
0x1800b9499  mov     edx, 5Bh ; '['
0x1800b949e  jmp     loc_1800B9226
0x1800b94a3  mov     rcx, [rsp+110h+var_D8]
0x1800b94a8  lea     rdx, [rbp+57h+var_CC]
0x1800b94ac  mov     rax, [rcx]
0x1800b94af  mov     rax, [rax+90h]
0x1800b94b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b94bb  mov     edi, eax
0x1800b94bd  test    eax, eax
0x1800b94bf  jns     short loc_1800B94EC
0x1800b94c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b94c8  lea     rbx, WPP_GLOBAL_Control
0x1800b94cf  cmp     rcx, rbx
0x1800b94d2  jz      loc_1800B963B
0x1800b94d8  test    [rcx+1Ch], sil
0x1800b94dc  jz      loc_1800B963B
0x1800b94e2  mov     edx, 5Ch ; '\'
0x1800b94e7  jmp     loc_1800B9226
0x1800b94ec  mov     rcx, [rsp+110h+var_D8]
0x1800b94f1  lea     rdx, [rbp+57h+var_D0]
0x1800b94f5  mov     rax, [rcx]
0x1800b94f8  mov     rax, [rax+88h]
0x1800b94ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b9504  mov     edi, eax
0x1800b9506  test    eax, eax
0x1800b9508  jns     short loc_1800B9535
0x1800b950a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9511  lea     rbx, WPP_GLOBAL_Control
0x1800b9518  cmp     rcx, rbx
0x1800b951b  jz      loc_1800B963B
0x1800b9521  test    [rcx+1Ch], sil
0x1800b9525  jz      loc_1800B963B
0x1800b952b  mov     edx, 5Dh ; ']'
0x1800b9530  jmp     loc_1800B9226
0x1800b9535  mov     rcx, [rsp+110h+var_D8]
0x1800b953a  lea     rdx, [rbp+57h+bstrString]
0x1800b953e  mov     rax, [rcx]
0x1800b9541  mov     rax, [rax+38h]
0x1800b9545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b954a  mov     edi, eax
0x1800b954c  test    eax, eax
0x1800b954e  jns     short loc_1800B957B
0x1800b9550  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9557  lea     rbx, WPP_GLOBAL_Control
0x1800b955e  cmp     rcx, rbx
0x1800b9561  jz      loc_1800B963B
0x1800b9567  test    [rcx+1Ch], sil
0x1800b956b  jz      loc_1800B963B
0x1800b9571  mov     edx, 5Eh ; '^'
0x1800b9576  jmp     loc_1800B9226
0x1800b957b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9582  lea     rbx, WPP_GLOBAL_Control
0x1800b9589  cmp     rcx, rbx
0x1800b958c  jz      short loc_1800B95BB
0x1800b958e  test    byte ptr [rcx+1Ch], 4
0x1800b9592  jz      short loc_1800B95BB
0x1800b9594  mov     eax, [rbp+57h+var_D0]
0x1800b9597  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b959e  mov     r9, [rbp+57h+bstrString]
0x1800b95a2  mov     edx, 5Fh ; '_'
0x1800b95a7  mov     rcx, [rcx+10h]
0x1800b95ab  mov     [rsp+110h+var_E8], eax
0x1800b95af  mov     eax, [rbp+57h+var_CC]
0x1800b95b2  mov     dword ptr [rsp+110h+ppv], eax
0x1800b95b6  call    WPP_SF_Sdd
0x1800b95bb  mov     ecx, 40h ; '@'
0x1800b95c0  call    VpnAlloc
0x1800b95c5  mov     r14, rax
0x1800b95c8  test    rax, rax
0x1800b95cb  jnz     loc_1800B9730
0x1800b95d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b95d8  cmp     rcx, rbx
0x1800b95db  jz      short loc_1800B963B
0x1800b95dd  lea     ebx, [rax+0Eh]
0x1800b95e0  test    [rcx+1Ch], sil
0x1800b95e4  jz      short loc_1800B9603
0x1800b95e6  mov     rcx, [rcx+10h]
0x1800b95ea  lea     edx, [rax+60h]
0x1800b95ed  mov     r9d, ebx
0x1800b95f0  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b95f7  call    WPP_SF_d
0x1800b95fc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9603  lea     rax, WPP_GLOBAL_Control
0x1800b960a  cmp     rcx, rax
0x1800b960d  jz      short loc_1800B9634
0x1800b960f  test    [rcx+1Ch], sil
0x1800b9613  jz      short loc_1800B9634
0x1800b9615  mov     edx, 61h ; 'a'
0x1800b961a  mov     rcx, [rcx+10h]
0x1800b961e  lea     r8, WPP_4ac933651d0f3fa44bba0fafd27ed502_Traceguids
0x1800b9625  mov     r9d, ebx
0x1800b9628  call    WPP_SF_d
0x1800b962d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b9634  lea     rbx, WPP_GLOBAL_Control
0x1800b963b  test    edi, edi
0x1800b963d  jz      short loc_1800B964E
  ... truncated ...
```
