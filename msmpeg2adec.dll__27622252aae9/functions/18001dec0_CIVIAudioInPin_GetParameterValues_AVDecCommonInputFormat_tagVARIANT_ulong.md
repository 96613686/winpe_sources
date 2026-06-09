# CIVIAudioInPin::GetParameterValues_AVDecCommonInputFormat(tagVARIANT * *,ulong *)

- ea: `0x18001dec0`
- end: `0x18001e1d8`
- name: `?GetParameterValues_AVDecCommonInputFormat@CIVIAudioInPin@@AEAAJPEAPEAUtagVARIANT@@PEAK@Z`
- size: `792`
- prototype: `__int64 __fastcall(CIVIAudioInPin *__hidden this, struct tagVARIANT **, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001dce0`

## callees

- `0x18001dec0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001dff9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e01c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e03f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e05f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e07f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e09f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001dff9`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e01c`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e03f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e05f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e07f`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e09f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e155`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e16a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e17f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e194`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e155`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e16a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e17f`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e194`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001df16`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001df16`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001df76`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001df8d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfa4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfbb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfd2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfe9`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001df76`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001df8d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfa4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfbb`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfd2`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18001dfe9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e125`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e0f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e105`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e115`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e125`

## pseudocode

```c
__int64 __fastcall CIVIAudioInPin::GetParameterValues_AVDecCommonInputFormat(
        CIVIAudioInPin *this,
        struct tagVARIANT **a2,
        unsigned int *a3)
{
  int v3; // ebx
  struct tagVARIANT *v6; // rdi
  BSTR v7; // rax
  BSTR v8; // rax
  BSTR v9; // rax
  BSTR v10; // rax
  BSTR v11; // rax
  BSTR v12; // rax
  OLECHAR *bstrVal; // rcx
  OLECHAR *v14; // rcx
  OLECHAR *v15; // rcx
  OLECHAR *v16; // rcx
  OLECHAR *v17; // rcx
  OLECHAR *v18; // rcx
  LPOLESTR v20; // [rsp+20h] [rbp-30h] BYREF
  LPOLESTR v21; // [rsp+28h] [rbp-28h] BYREF
  LPOLESTR v22; // [rsp+30h] [rbp-20h] BYREF
  LPOLESTR lpsz; // [rsp+70h] [rbp+20h] BYREF
  LPOLESTR psz; // [rsp+78h] [rbp+28h] BYREF
  LPOLESTR v25; // [rsp+88h] [rbp+38h] BYREF

  v3 = 0;
  lpsz = 0;
  v21 = 0;
  psz = 0;
  v25 = 0;
  v20 = 0;
  v22 = 0;
  if ( a2 && a3 )
  {
    *a2 = 0;
    *a3 = 0;
    v6 = (struct tagVARIANT *)CoTaskMemAlloc(0x90u);
    if ( v6 )
    {
      v6->llVal = 0;
      v6->vt = 8;
      v6[1].vt = 8;
      v6[2].vt = 8;
      v6[3].vt = 8;
      v6[4].vt = 8;
      v6[5].vt = 8;
      v6[1].llVal = 0;
      v6[2].llVal = 0;
      v6[3].llVal = 0;
      v6[4].llVal = 0;
      v6[5].llVal = 0;
      StringFromCLSID(&GUID_8e4228a0_f000_4e0b_8f54_ab8d24ad61a2, &lpsz);
      StringFromCLSID(&GUID_0803e185_8f5d_47f5_9908_19a5bbc9fe34, &v21);
      StringFromCLSID(&GUID_f2421da5_bbb4_4cd5_a996_933c6b5d1347, &psz);
      StringFromCLSID(&GUID_91106f36_02c5_4f75_9719_3b7abf75e1f6, &v25);
      StringFromCLSID(&GUID_600bc0ca_6a1f_4e91_b241_1bbeb1cb19e0, &v20);
      StringFromCLSID(&GUID_97df7828_b94a_47e2_a4bc_51194db22a4d, &v22);
      v7 = SysAllocString(lpsz);
      v6->llVal = (LONGLONG)v7;
      if ( v7 )
      {
        v8 = SysAllocString(psz);
        v6[1].llVal = (LONGLONG)v8;
        if ( v8 )
        {
          v9 = SysAllocString(v25);
          v6[2].llVal = (LONGLONG)v9;
          if ( v9 )
          {
            v10 = SysAllocString(v20);
            v6[3].llVal = (LONGLONG)v10;
            if ( v10 )
            {
              v11 = SysAllocString(v21);
              v6[4].llVal = (LONGLONG)v11;
              if ( v11 )
              {
                v12 = SysAllocString(v22);
                v6[5].llVal = (LONGLONG)v12;
                if ( v12 )
                {
                  *a3 = 6;
                  *a2 = v6;
                }
                else
                {
                  v3 = -2147024882;
                }
              }
              else
              {
                v3 = -2147024882;
              }
            }
            else
            {
              v3 = -2147024882;
            }
          }
          else
          {
            v3 = -2147024882;
          }
        }
        else
        {
          v3 = -2147024882;
        }
      }
      else
      {
        v3 = -2147024882;
      }
    }
    else
    {
      v3 = -2147024882;
    }
  }
  else
  {
    v6 = 0;
    v3 = -2147024809;
  }
  CoTaskMemFree(lpsz);
  CoTaskMemFree(psz);
  CoTaskMemFree(v25);
  CoTaskMemFree(v20);
  CoTaskMemFree(v21);
  CoTaskMemFree(v22);
  if ( v3 < 0 && v6 )
  {
    bstrVal = v6->bstrVal;
    if ( bstrVal )
      SysFreeString(bstrVal);
    v14 = v6[1].bstrVal;
    if ( v14 )
      SysFreeString(v14);
    v15 = v6[2].bstrVal;
    if ( v15 )
      SysFreeString(v15);
    v16 = v6[3].bstrVal;
    if ( v16 )
      SysFreeString(v16);
    v17 = v6[4].bstrVal;
    if ( v17 )
      SysFreeString(v17);
    v18 = v6[5].bstrVal;
    if ( v18 )
      SysFreeString(v18);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001dec0  mov     [rsp-18h+lpsz], rcx
0x18001dec5  push    rbp
0x18001dec6  push    rbx
0x18001dec7  push    rdi
0x18001dec8  mov     rbp, rsp
0x18001decb  sub     rsp, 50h
0x18001decf  xor     ebx, ebx
0x18001ded1  mov     [rsp+50h+var_8], rsi
0x18001ded6  mov     [rsp+50h+var_10], r14
0x18001dedb  mov     rsi, r8
0x18001dede  mov     [rbp+lpsz], rbx
0x18001dee2  mov     r14, rdx
0x18001dee5  mov     [rbp+var_28], rbx
0x18001dee9  mov     [rbp+psz], rbx
0x18001deed  mov     [rbp+arg_18], rbx
0x18001def1  mov     [rbp+var_30], rbx
0x18001def5  mov     [rbp+var_20], rbx
0x18001def9  test    rdx, rdx
0x18001defc  jz      loc_18001E0C9
0x18001df02  test    r8, r8
0x18001df05  jz      loc_18001E0C9
0x18001df0b  mov     [rdx], rbx
0x18001df0e  mov     ecx, 90h; cb
0x18001df13  mov     [r8], ebx
0x18001df16  call    cs:__imp_CoTaskMemAlloc
0x18001df1d  nop     dword ptr [rax+rax+00h]
0x18001df22  mov     rdi, rax
0x18001df25  test    rax, rax
0x18001df28  jnz     short loc_18001DF34
0x18001df2a  mov     ebx, 8007000Eh
0x18001df2f  jmp     loc_18001E0D1
0x18001df34  mov     eax, 8
0x18001df39  mov     [rdi+8], rbx
0x18001df3d  lea     rdx, [rbp+lpsz]; lplpsz
0x18001df41  mov     [rdi], ax
0x18001df44  lea     rcx, _GUID_8e4228a0_f000_4e0b_8f54_ab8d24ad61a2; rclsid
0x18001df4b  mov     [rdi+18h], ax
0x18001df4f  mov     [rdi+30h], ax
0x18001df53  mov     [rdi+48h], ax
0x18001df57  mov     [rdi+60h], ax
0x18001df5b  mov     [rdi+78h], ax
0x18001df5f  mov     [rdi+20h], rbx
0x18001df63  mov     [rdi+38h], rbx
0x18001df67  mov     [rdi+50h], rbx
0x18001df6b  mov     [rdi+68h], rbx
0x18001df6f  mov     [rdi+80h], rbx
0x18001df76  call    cs:__imp_StringFromCLSID
0x18001df7d  nop     dword ptr [rax+rax+00h]
0x18001df82  lea     rdx, [rbp+var_28]; lplpsz
0x18001df86  lea     rcx, _GUID_0803e185_8f5d_47f5_9908_19a5bbc9fe34; rclsid
0x18001df8d  call    cs:__imp_StringFromCLSID
0x18001df94  nop     dword ptr [rax+rax+00h]
0x18001df99  lea     rdx, [rbp+psz]; lplpsz
0x18001df9d  lea     rcx, _GUID_f2421da5_bbb4_4cd5_a996_933c6b5d1347; rclsid
0x18001dfa4  call    cs:__imp_StringFromCLSID
0x18001dfab  nop     dword ptr [rax+rax+00h]
0x18001dfb0  lea     rdx, [rbp+arg_18]; lplpsz
0x18001dfb4  lea     rcx, _GUID_91106f36_02c5_4f75_9719_3b7abf75e1f6; rclsid
0x18001dfbb  call    cs:__imp_StringFromCLSID
0x18001dfc2  nop     dword ptr [rax+rax+00h]
0x18001dfc7  lea     rdx, [rbp+var_30]; lplpsz
0x18001dfcb  lea     rcx, _GUID_600bc0ca_6a1f_4e91_b241_1bbeb1cb19e0; rclsid
0x18001dfd2  call    cs:__imp_StringFromCLSID
0x18001dfd9  nop     dword ptr [rax+rax+00h]
0x18001dfde  lea     rdx, [rbp+var_20]; lplpsz
0x18001dfe2  lea     rcx, _GUID_97df7828_b94a_47e2_a4bc_51194db22a4d; rclsid
0x18001dfe9  call    cs:__imp_StringFromCLSID
0x18001dff0  nop     dword ptr [rax+rax+00h]
0x18001dff5  mov     rcx, [rbp+lpsz]; psz
0x18001dff9  call    cs:__imp_SysAllocString
0x18001e000  nop     dword ptr [rax+rax+00h]
0x18001e005  mov     [rdi+8], rax
0x18001e009  test    rax, rax
0x18001e00c  jnz     short loc_18001E018
0x18001e00e  mov     ebx, 8007000Eh
0x18001e013  jmp     loc_18001E0D1
0x18001e018  mov     rcx, [rbp+psz]; psz
0x18001e01c  call    cs:__imp_SysAllocString
0x18001e023  nop     dword ptr [rax+rax+00h]
0x18001e028  mov     [rdi+20h], rax
0x18001e02c  test    rax, rax
0x18001e02f  jnz     short loc_18001E03B
0x18001e031  mov     ebx, 8007000Eh
0x18001e036  jmp     loc_18001E0D1
0x18001e03b  mov     rcx, [rbp+arg_18]; psz
0x18001e03f  call    cs:__imp_SysAllocString
0x18001e046  nop     dword ptr [rax+rax+00h]
0x18001e04b  mov     [rdi+38h], rax
0x18001e04f  test    rax, rax
0x18001e052  jnz     short loc_18001E05B
0x18001e054  mov     ebx, 8007000Eh
0x18001e059  jmp     short loc_18001E0D1
0x18001e05b  mov     rcx, [rbp+var_30]; psz
0x18001e05f  call    cs:__imp_SysAllocString
0x18001e066  nop     dword ptr [rax+rax+00h]
0x18001e06b  mov     [rdi+50h], rax
0x18001e06f  test    rax, rax
0x18001e072  jnz     short loc_18001E07B
0x18001e074  mov     ebx, 8007000Eh
0x18001e079  jmp     short loc_18001E0D1
0x18001e07b  mov     rcx, [rbp+var_28]; psz
0x18001e07f  call    cs:__imp_SysAllocString
0x18001e086  nop     dword ptr [rax+rax+00h]
0x18001e08b  mov     [rdi+68h], rax
0x18001e08f  test    rax, rax
0x18001e092  jnz     short loc_18001E09B
0x18001e094  mov     ebx, 8007000Eh
0x18001e099  jmp     short loc_18001E0D1
0x18001e09b  mov     rcx, [rbp+var_20]; psz
0x18001e09f  call    cs:__imp_SysAllocString
0x18001e0a6  nop     dword ptr [rax+rax+00h]
0x18001e0ab  mov     [rdi+80h], rax
0x18001e0b2  test    rax, rax
0x18001e0b5  jnz     short loc_18001E0BE
0x18001e0b7  mov     ebx, 8007000Eh
0x18001e0bc  jmp     short loc_18001E0D1
0x18001e0be  mov     dword ptr [rsi], 6
0x18001e0c4  mov     [r14], rdi
0x18001e0c7  jmp     short loc_18001E0D1
0x18001e0c9  mov     rdi, rbx
0x18001e0cc  mov     ebx, 80070057h
0x18001e0d1  mov     rcx, [rbp+lpsz]; pv
0x18001e0d5  call    cs:__imp_CoTaskMemFree
0x18001e0dc  nop     dword ptr [rax+rax+00h]
0x18001e0e1  mov     rcx, [rbp+psz]; pv
0x18001e0e5  call    cs:__imp_CoTaskMemFree
0x18001e0ec  nop     dword ptr [rax+rax+00h]
0x18001e0f1  mov     rcx, [rbp+arg_18]; pv
0x18001e0f5  call    cs:__imp_CoTaskMemFree
0x18001e0fc  nop     dword ptr [rax+rax+00h]
0x18001e101  mov     rcx, [rbp+var_30]; pv
0x18001e105  call    cs:__imp_CoTaskMemFree
0x18001e10c  nop     dword ptr [rax+rax+00h]
0x18001e111  mov     rcx, [rbp+var_28]; pv
0x18001e115  call    cs:__imp_CoTaskMemFree
0x18001e11c  nop     dword ptr [rax+rax+00h]
0x18001e121  mov     rcx, [rbp+var_20]; pv
0x18001e125  call    cs:__imp_CoTaskMemFree
0x18001e12c  nop     dword ptr [rax+rax+00h]
0x18001e131  mov     r14, [rsp+50h+var_10]
0x18001e136  mov     rsi, [rsp+50h+var_8]
0x18001e13b  test    ebx, ebx
0x18001e13d  jns     loc_18001E1CD
0x18001e143  test    rdi, rdi
0x18001e146  jz      loc_18001E1CD
0x18001e14c  mov     rcx, [rdi+8]; bstrString
0x18001e150  test    rcx, rcx
0x18001e153  jz      short loc_18001E161
0x18001e155  call    cs:__imp_SysFreeString
0x18001e15c  nop     dword ptr [rax+rax+00h]
0x18001e161  mov     rcx, [rdi+20h]; bstrString
0x18001e165  test    rcx, rcx
0x18001e168  jz      short loc_18001E176
0x18001e16a  call    cs:__imp_SysFreeString
0x18001e171  nop     dword ptr [rax+rax+00h]
0x18001e176  mov     rcx, [rdi+38h]; bstrString
0x18001e17a  test    rcx, rcx
0x18001e17d  jz      short loc_18001E18B
0x18001e17f  call    cs:__imp_SysFreeString
0x18001e186  nop     dword ptr [rax+rax+00h]
0x18001e18b  mov     rcx, [rdi+50h]; bstrString
0x18001e18f  test    rcx, rcx
0x18001e192  jz      short loc_18001E1A0
0x18001e194  call    cs:__imp_SysFreeString
0x18001e19b  nop     dword ptr [rax+rax+00h]
0x18001e1a0  mov     rcx, [rdi+68h]; bstrString
0x18001e1a4  test    rcx, rcx
0x18001e1a7  jz      short loc_18001E1B5
0x18001e1a9  call    cs:__imp_SysFreeString
0x18001e1b0  nop     dword ptr [rax+rax+00h]
0x18001e1b5  mov     rcx, [rdi+80h]; bstrString
0x18001e1bc  test    rcx, rcx
0x18001e1bf  jz      short loc_18001E1CD
0x18001e1c1  call    cs:__imp_SysFreeString
0x18001e1c8  nop     dword ptr [rax+rax+00h]
0x18001e1cd  mov     eax, ebx
0x18001e1cf  add     rsp, 50h
0x18001e1d3  pop     rdi
0x18001e1d4  pop     rbx
0x18001e1d5  pop     rbp
0x18001e1d6  retn
```
