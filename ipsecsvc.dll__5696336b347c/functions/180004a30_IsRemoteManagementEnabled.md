# IsRemoteManagementEnabled

- ea: `0x180004a30`
- end: `0x180004c6f`
- name: `IsRemoteManagementEnabled`
- size: `575`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180001e20`
- `0x180003de0`

## callees

- `0x180004a30`
- `0x18000e510`
- `0x18000f638`
- `0x18004e010`

## import_xrefs

- `FirewallAPI!FwIsRemoteManagementEnabled` at `0x180004b76`
- `FirewallAPI!FwIsRemoteManagementEnabled` at `0x180004b76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004ae8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004ae8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a56`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180004a56`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004c58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180004c58`
- `OLEAUT32!__imp_SysAllocString` at `0x180004aff`
- `OLEAUT32!__imp_SysAllocString` at `0x180004aff`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a8e`
- `OLEAUT32!__imp_SysFreeString` at `0x180004a8e`

## string_xrefs

- `0x180004af8`: `@FirewallAPI.dll,-30002`

## pseudocode

```c
__int64 __fastcall IsRemoteManagementEnabled(_DWORD *a1)
{
  OLECHAR *v2; // rsi
  HRESULT v3; // edi
  HRESULT v4; // ebx
  __int64 result; // rax
  BSTR v6; // rax
  _QWORD *v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-38h] BYREF
  __int16 v11; // [rsp+78h] [rbp+10h] BYREF
  int v12; // [rsp+80h] [rbp+18h] BYREF
  int v13; // [rsp+88h] [rbp+20h] BYREF

  ppv = 0;
  v11 = 0;
  v2 = 0;
  v12 = 0;
  v13 = 0;
  v3 = CoInitializeEx(0, 0);
  if ( (int)(v3 + 0x80000000) >= 0 && v3 != -2147417850 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        WPP_196d68d6ad89386858c02b7e955f8655_Traceguids,
        (unsigned int)v3);
    v4 = (unsigned __int16)v3;
    goto LABEL_5;
  }
  v4 = CoCreateInstance(&CLSID_NetFwPolicy2, 0, 0x17u, &IID_INetFwPolicy2, &ppv);
  if ( v4 < 0 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
      goto LABEL_16;
    v9 = 24;
    goto LABEL_25;
  }
  v6 = SysAllocString(L"@FirewallAPI.dll,-30002");
  v2 = v6;
  if ( v6 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, BSTR, __int16 *))(*(_QWORD *)ppv + 216LL))(ppv, v6, &v11);
    if ( v4 >= 0 )
    {
      v4 = 0;
      if ( v11 )
      {
        *a1 = 1;
      }
      else
      {
        *a1 = 0;
        v8 = FwIsRemoteManagementEnabled(0, 0, &v12, &v13);
        if ( v8 )
          v4 = (unsigned __int16)v8;
        else
          *a1 = v12 != 0;
      }
      goto LABEL_5;
    }
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) == 0 )
    {
LABEL_16:
      v4 = (unsigned __int16)v4;
      goto LABEL_5;
    }
    v9 = 26;
LABEL_25:
    WPP_SF_d(v7[2], v9, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids, (unsigned int)v4);
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids);
  v4 = 8;
LABEL_5:
  SysFreeString(v2);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v3 >= 0 )
    CoUninitialize();
  result = (unsigned int)v4;
  if ( v4 == 8 )
    *a1 = 1;
  return result;
}

```

## disassembly

```asm
0x180004a30  mov     rax, rsp
0x180004a33  push    rbx
0x180004a34  push    rbp
0x180004a35  push    rsi
0x180004a36  push    rdi
0x180004a37  push    r14
0x180004a39  sub     rsp, 40h
0x180004a3d  xor     ebp, ebp
0x180004a3f  mov     r14, rcx
0x180004a42  xor     ecx, ecx; pvReserved
0x180004a44  mov     [rax-38h], rbp
0x180004a48  xor     edx, edx; dwCoInit
0x180004a4a  mov     [rax+10h], bp
0x180004a4e  mov     esi, ebp
0x180004a50  mov     [rax+18h], ebp
0x180004a53  mov     [rax+20h], ebp
0x180004a56  call    cs:__imp_CoInitializeEx
0x180004a5c  mov     ecx, 80000000h
0x180004a61  mov     edi, eax
0x180004a63  add     eax, ecx
0x180004a65  test    ecx, eax
0x180004a67  jnz     short loc_180004AC8
0x180004a69  cmp     edi, 80010106h
0x180004a6f  jz      short loc_180004AC8
0x180004a71  mov     rcx, cs:WPP_GLOBAL_Control
0x180004a78  lea     rax, WPP_GLOBAL_Control
0x180004a7f  cmp     rcx, rax
0x180004a82  jnz     loc_180004B8C
0x180004a88  movzx   ebx, di
0x180004a8b  mov     rcx, rsi; bstrString
0x180004a8e  call    cs:__imp_SysFreeString
0x180004a94  mov     rcx, [rsp+68h+var_38]
0x180004a99  test    rcx, rcx
0x180004a9c  jz      short loc_180004AAA
0x180004a9e  mov     rax, [rcx]
0x180004aa1  mov     rax, [rax+10h]
0x180004aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aaa  test    edi, edi
0x180004aac  jns     loc_180004C58
0x180004ab2  mov     eax, ebx
0x180004ab4  cmp     ebx, 8
0x180004ab7  jz      loc_180004C63
0x180004abd  add     rsp, 40h
0x180004ac1  pop     r14
0x180004ac3  pop     rdi
0x180004ac4  pop     rsi
0x180004ac5  pop     rbp
0x180004ac6  pop     rbx
0x180004ac7  retn
0x180004ac8  lea     rax, [rsp+68h+var_38]
0x180004acd  xor     edx, edx; pUnkOuter
0x180004acf  lea     r9, IID_INetFwPolicy2; riid
0x180004ad6  mov     [rsp+68h+ppv], rax; ppv
0x180004adb  mov     r8d, 17h; dwClsContext
0x180004ae1  lea     rcx, CLSID_NetFwPolicy2; rclsid
0x180004ae8  call    cs:__imp_CoCreateInstance
0x180004aee  mov     ebx, eax
0x180004af0  test    eax, eax
0x180004af2  js      loc_180004BB3
0x180004af8  lea     rcx, psz; "@FirewallAPI.dll,-30002"
0x180004aff  call    cs:__imp_SysAllocString
0x180004b05  mov     rsi, rax
0x180004b08  test    rax, rax
0x180004b0b  jz      loc_180004BF4
0x180004b11  mov     rcx, [rsp+68h+var_38]
0x180004b16  lea     r8, [rsp+68h+arg_8]
0x180004b1b  mov     rdx, rsi
0x180004b1e  mov     rax, [rcx]
0x180004b21  mov     rax, [rax+0D8h]
0x180004b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2d  mov     ebx, eax
0x180004b2f  test    eax, eax
0x180004b31  jns     short loc_180004B52
0x180004b33  mov     rcx, cs:WPP_GLOBAL_Control
0x180004b3a  lea     rax, WPP_GLOBAL_Control
0x180004b41  cmp     rcx, rax
0x180004b44  jnz     loc_180004C2C
0x180004b4a  movzx   ebx, bx
0x180004b4d  jmp     loc_180004A8B
0x180004b52  mov     ebx, ebp
0x180004b54  cmp     [rsp+68h+arg_8], bx
0x180004b59  jnz     loc_180004C38
0x180004b5f  lea     r9, [rsp+68h+arg_18]
0x180004b67  mov     [r14], ebp
0x180004b6a  lea     r8, [rsp+68h+arg_10]
0x180004b72  xor     edx, edx
0x180004b74  xor     ecx, ecx
0x180004b76  call    cs:__imp_FwIsRemoteManagementEnabled
0x180004b7c  test    eax, eax
0x180004b7e  jz      loc_180004C44
0x180004b84  movzx   ebx, ax
0x180004b87  jmp     loc_180004A8B
0x180004b8c  test    byte ptr [rcx+1Ch], 10h
0x180004b90  jz      loc_180004A88
0x180004b96  mov     rcx, [rcx+10h]
0x180004b9a  lea     r8, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids
0x180004ba1  mov     edx, 17h
0x180004ba6  mov     r9d, edi
0x180004ba9  call    WPP_SF_d
0x180004bae  jmp     loc_180004A88
0x180004bb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bba  lea     rax, WPP_GLOBAL_Control
0x180004bc1  cmp     rcx, rax
0x180004bc4  jz      short loc_180004B4A
0x180004bc6  test    byte ptr [rcx+1Ch], 10h
0x180004bca  jz      loc_180004B4A
0x180004bd0  mov     edx, 18h
0x180004bd5  jmp     short loc_180004BDC
0x180004bd7  mov     edx, 1Ah
0x180004bdc  mov     rcx, [rcx+10h]
0x180004be0  lea     r8, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids
0x180004be7  mov     r9d, ebx
0x180004bea  call    WPP_SF_d
0x180004bef  jmp     loc_180004B4A
0x180004bf4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004bfb  lea     rax, WPP_GLOBAL_Control
0x180004c02  cmp     rcx, rax
0x180004c05  jz      short loc_180004C22
0x180004c07  test    byte ptr [rcx+1Ch], 10h
0x180004c0b  jz      short loc_180004C22
0x180004c0d  mov     rcx, [rcx+10h]
0x180004c11  lea     r8, WPP_196d68d6ad89386858c02b7e955f8655_Traceguids
0x180004c18  mov     edx, 19h
0x180004c1d  call    WPP_SF_
0x180004c22  mov     ebx, 8
0x180004c27  jmp     loc_180004A8B
0x180004c2c  test    byte ptr [rcx+1Ch], 10h
0x180004c30  jz      loc_180004B4A
0x180004c36  jmp     short loc_180004BD7
0x180004c38  mov     dword ptr [r14], 1
0x180004c3f  jmp     loc_180004A8B
0x180004c44  mov     eax, ebp
0x180004c46  cmp     [rsp+68h+arg_10], eax
0x180004c4d  setnz   al
0x180004c50  mov     [r14], eax
0x180004c53  jmp     loc_180004A8B
0x180004c58  call    cs:__imp_CoUninitialize
0x180004c5e  jmp     loc_180004AB2
0x180004c63  mov     dword ptr [r14], 1
0x180004c6a  jmp     loc_180004ABD
```
