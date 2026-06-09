# CManagerThread::AddRemoveRegisteredConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,int)

- ea: `0x180009af0`
- end: `0x180009fc2`
- name: `?AddRemoveRegisteredConfig@CManagerThread@@AEAAJV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@H@Z`
- size: `1234`
- prototype: `__int64 __fastcall(__int64, LPCWSTR *, int)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003f00`
- `0x1800062b0`
- `0x1800065c0`
- `0x180007330`

## callees

- `0x180009af0`
- `0x18000b48c`
- `0x18000ca14`
- `0x18000d910`
- `0x18000d970`
- `0x180013010`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x180009bb4`
- `ADVAPI32!RegDeleteValueW` at `0x180009bb4`
- `ADVAPI32!RegSetValueExW` at `0x180009dec`
- `ADVAPI32!RegSetValueExW` at `0x180009dec`
- `ADVAPI32!SetThreadToken` at `0x180009b68`
- `ADVAPI32!SetThreadToken` at `0x180009b68`
- `KERNEL32!GetLastError` at `0x180009b72`
- `KERNEL32!GetLastError` at `0x180009b72`
- `OLEAUT32!__imp_SysAllocString` at `0x180009e91`
- `OLEAUT32!__imp_SysAllocString` at `0x180009e91`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c77`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f01`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c77`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180009d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e1a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f01`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009c26`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009c26`

## pseudocode

```c
__int64 __fastcall CManagerThread::AddRemoveRegisteredConfig(__int64 a1, LPCWSTR *a2, int a3)
{
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  signed int LastError; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  LSTATUS v13; // eax
  OLECHAR *v14; // rbx
  HRESULT v15; // eax
  int v16; // eax
  int v17; // eax
  LSTATUS v18; // eax
  volatile signed __int32 *v19; // rdx
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  OLECHAR *v22; // [rsp+40h] [rbp-38h]
  int Data; // [rsp+90h] [rbp+18h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp+20h] BYREF

  if ( a3 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v7 = 106;
LABEL_8:
      WPP_SF_S(v6[2], v7, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, *a2);
    }
  }
  else
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v7 = 107;
      goto LABEL_8;
    }
  }
  if ( SetThreadToken(0, 0) )
  {
    v13 = RegDeleteValueW(*(HKEY *)a1, *a2);
    v9 = v13;
    if ( v13 )
    {
      if ( v13 != 2 )
      {
        if ( v13 > 0 )
          v9 = (unsigned __int16)v13 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            109,
            (int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (int)*a2,
            v9);
        goto LABEL_73;
      }
    }
    else
    {
      --*(_DWORD *)(a1 + 8);
    }
    if ( a3 )
    {
      ppv = 0;
      if ( *a2 )
      {
        v14 = SysAllocString(*a2);
        v22 = v14;
        if ( !v14 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v14 = 0;
        v22 = 0;
      }
      v21 = 0;
      Data = 0;
      v15 = CoCreateInstance(&CLSID_FhConfigMgr, 0, 0x17u, &GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4, &ppv);
      v9 = v15;
      if ( v15 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            110,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (unsigned int)v15);
        SysFreeString(v14);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_73;
      }
      v16 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *))(*(_QWORD *)ppv + 144LL))(ppv, v14);
      v9 = v16;
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            111,
            (int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (int)v14,
            v16);
        SysFreeString(v14);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_73;
      }
      v17 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 96LL))(ppv, &v21);
      v9 = v17;
      if ( v17 >= 0 )
      {
        Data = 1;
      }
      else if ( v17 != -2147023728 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (unsigned int)v17);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        SysFreeString(v14);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_73;
      }
      v18 = RegSetValueExW(*(HKEY *)a1, *a2, 0, 4u, (const BYTE *)&Data, 4u);
      v9 = v18;
      if ( v18 )
      {
        if ( v18 > 0 )
          v9 = (unsigned __int16)v18 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            113,
            (int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (int)*a2,
            v9);
        if ( v21 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        SysFreeString(v14);
        if ( ppv )
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
        goto LABEL_73;
      }
      ++*(_DWORD *)(a1 + 8);
      if ( v21 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
      SysFreeString(v14);
      if ( ppv )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    v9 = 0;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v11 = 115;
      v12 = *(unsigned int *)(a1 + 8);
      goto LABEL_72;
    }
  }
  else
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 108;
      v12 = v9;
LABEL_72:
      WPP_SF_d(v10[2], v11, &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids, v12);
    }
  }
LABEL_73:
  v19 = (volatile signed __int32 *)(*a2 - 12);
  if ( _InterlockedExchangeAdd(v19 + 4, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  return v9;
}

```

## disassembly

```asm
0x180009af0  mov     [rsp+arg_8], rdx
0x180009af5  mov     [rsp+arg_0], rcx
0x180009afa  push    rbx
0x180009afb  push    rsi
0x180009afc  push    rdi
0x180009afd  push    r14
0x180009aff  push    r15
0x180009b01  sub     rsp, 50h
0x180009b05  mov     ebx, r8d
0x180009b08  mov     r15, rdx
0x180009b0b  mov     r14, rcx
0x180009b0e  test    r8d, r8d
0x180009b11  jz      short loc_180009B33
0x180009b13  lea     rsi, WPP_GLOBAL_Control
0x180009b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b21  cmp     rcx, rsi
0x180009b24  jz      short loc_180009B64
0x180009b26  test    byte ptr [rcx+1Ch], 8
0x180009b2a  jz      short loc_180009B64
0x180009b2c  mov     edx, 6Ah ; 'j'
0x180009b31  jmp     short loc_180009B51
0x180009b33  lea     rsi, WPP_GLOBAL_Control
0x180009b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b41  cmp     rcx, rsi
0x180009b44  jz      short loc_180009B64
0x180009b46  test    byte ptr [rcx+1Ch], 8
0x180009b4a  jz      short loc_180009B64
0x180009b4c  mov     edx, 6Bh ; 'k'
0x180009b51  mov     r9, [r15]
0x180009b54  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009b5b  mov     rcx, [rcx+10h]
0x180009b5f  call    WPP_SF_S
0x180009b64  xor     edx, edx; Token
0x180009b66  xor     ecx, ecx; Thread
0x180009b68  call    cs:__imp_SetThreadToken
0x180009b6e  test    eax, eax
0x180009b70  jnz     short loc_180009BAE
0x180009b72  call    cs:__imp_GetLastError
0x180009b78  mov     edi, eax
0x180009b7a  test    eax, eax
0x180009b7c  jle     short loc_180009B87
0x180009b7e  movzx   edi, ax
0x180009b81  or      edi, 80070000h
0x180009b87  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b8e  cmp     rcx, rsi
0x180009b91  jz      loc_180009F83
0x180009b97  test    byte ptr [rcx+1Ch], 1
0x180009b9b  jz      loc_180009F83
0x180009ba1  mov     edx, 6Ch ; 'l'
0x180009ba6  mov     r9d, edi
0x180009ba9  jmp     loc_180009F72
0x180009bae  mov     rdx, [r15]; lpValueName
0x180009bb1  mov     rcx, [r14]; hKey
0x180009bb4  call    cs:__imp_RegDeleteValueW
0x180009bba  mov     edi, eax
0x180009bbc  test    eax, eax
0x180009bbe  jnz     loc_180009E40
0x180009bc4  dec     dword ptr [r14+8]
0x180009bc8  test    ebx, ebx
0x180009bca  jz      loc_180009F24
0x180009bd0  mov     [rsp+78h+arg_18], 0
0x180009bdc  mov     rcx, [r15]; psz
0x180009bdf  test    rcx, rcx
0x180009be2  jnz     loc_180009E91
0x180009be8  xor     ebx, ebx
0x180009bea  mov     [rsp+78h+var_38], rbx
0x180009bef  mov     [rsp+78h+var_40], 0
0x180009bf8  mov     [rsp+78h+Data], 0
0x180009c03  lea     rax, [rsp+78h+arg_18]
0x180009c0b  mov     [rsp+78h+ppv], rax; ppv
0x180009c10  lea     r9, _GUID_e388cb3e_d90b_4e2a_a025_42c7f1e655a4; riid
0x180009c17  xor     edx, edx; pUnkOuter
0x180009c19  mov     r8d, 17h; dwClsContext
0x180009c1f  lea     rcx, CLSID_FhConfigMgr; rclsid
0x180009c26  call    cs:__imp_CoCreateInstance
0x180009c2c  mov     edi, eax
0x180009c2e  test    eax, eax
0x180009c30  jns     short loc_180009C9D
0x180009c32  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c39  cmp     rcx, rsi
0x180009c3c  jz      short loc_180009C5D
0x180009c3e  test    byte ptr [rcx+1Ch], 1
0x180009c42  jz      short loc_180009C5D
0x180009c44  mov     edx, 6Eh ; 'n'
0x180009c49  mov     r9d, eax
0x180009c4c  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009c53  mov     rcx, [rcx+10h]
0x180009c57  call    WPP_SF_d
0x180009c5c  nop
0x180009c5d  mov     rcx, [rsp+78h+var_40]
0x180009c62  test    rcx, rcx
0x180009c65  jz      short loc_180009C74
0x180009c67  mov     rax, [rcx]
0x180009c6a  mov     rax, [rax+10h]
0x180009c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c73  nop
0x180009c74  mov     rcx, rbx; bstrString
0x180009c77  call    cs:__imp_SysFreeString
0x180009c7d  nop
0x180009c7e  mov     rcx, [rsp+78h+arg_18]
0x180009c86  test    rcx, rcx
0x180009c89  jz      short loc_180009C98
0x180009c8b  mov     rax, [rcx]
0x180009c8e  mov     rax, [rax+10h]
0x180009c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c97  nop
0x180009c98  jmp     loc_180009F83
0x180009c9d  mov     rcx, [rsp+78h+arg_18]
0x180009ca5  mov     rax, [rcx]
0x180009ca8  mov     rdx, rbx
0x180009cab  mov     rax, [rax+90h]
0x180009cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cb7  mov     edi, eax
0x180009cb9  test    eax, eax
0x180009cbb  jns     short loc_180009D2C
0x180009cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180009cc4  cmp     rcx, rsi
0x180009cc7  jz      short loc_180009CEC
0x180009cc9  test    byte ptr [rcx+1Ch], 1
0x180009ccd  jz      short loc_180009CEC
0x180009ccf  mov     edx, 6Fh ; 'o'
0x180009cd4  mov     dword ptr [rsp+78h+ppv], eax
0x180009cd8  mov     r9, rbx
0x180009cdb  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009ce2  mov     rcx, [rcx+10h]
0x180009ce6  call    WPP_SF_Sd
0x180009ceb  nop
0x180009cec  mov     rcx, [rsp+78h+var_40]
0x180009cf1  test    rcx, rcx
0x180009cf4  jz      short loc_180009D03
0x180009cf6  mov     rax, [rcx]
0x180009cf9  mov     rax, [rax+10h]
0x180009cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d02  nop
0x180009d03  mov     rcx, rbx; bstrString
0x180009d06  call    cs:__imp_SysFreeString
0x180009d0c  nop
0x180009d0d  mov     rcx, [rsp+78h+arg_18]
0x180009d15  test    rcx, rcx
0x180009d18  jz      short loc_180009D27
0x180009d1a  mov     rax, [rcx]
0x180009d1d  mov     rax, [rax+10h]
0x180009d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d26  nop
0x180009d27  jmp     loc_180009F83
0x180009d2c  mov     rcx, [rsp+78h+arg_18]
0x180009d34  mov     rax, [rcx]
0x180009d37  lea     rdx, [rsp+78h+var_40]
0x180009d3c  mov     rax, [rax+60h]
0x180009d40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d45  mov     edi, eax
0x180009d47  test    eax, eax
0x180009d49  jns     short loc_180009DBD
0x180009d4b  cmp     eax, 80070490h
0x180009d50  jz      short loc_180009DC8
0x180009d52  mov     rcx, cs:WPP_GLOBAL_Control
0x180009d59  cmp     rcx, rsi
0x180009d5c  jz      short loc_180009D7D
0x180009d5e  test    byte ptr [rcx+1Ch], 1
0x180009d62  jz      short loc_180009D7D
0x180009d64  mov     edx, 70h ; 'p'
0x180009d69  mov     r9d, eax
0x180009d6c  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009d73  mov     rcx, [rcx+10h]
0x180009d77  call    WPP_SF_d
0x180009d7c  nop
0x180009d7d  mov     rcx, [rsp+78h+var_40]
0x180009d82  test    rcx, rcx
0x180009d85  jz      short loc_180009D94
0x180009d87  mov     rax, [rcx]
0x180009d8a  mov     rax, [rax+10h]
0x180009d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d93  nop
0x180009d94  mov     rcx, rbx; bstrString
0x180009d97  call    cs:__imp_SysFreeString
0x180009d9d  nop
0x180009d9e  mov     rcx, [rsp+78h+arg_18]
0x180009da6  test    rcx, rcx
0x180009da9  jz      short loc_180009DB8
0x180009dab  mov     rax, [rcx]
0x180009dae  mov     rax, [rax+10h]
0x180009db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009db7  nop
0x180009db8  jmp     loc_180009F83
0x180009dbd  mov     [rsp+78h+Data], 1
0x180009dc8  mov     [rsp+78h+cbData], 4; cbData
0x180009dd0  lea     rax, [rsp+78h+Data]
0x180009dd8  mov     [rsp+78h+ppv], rax; lpData
0x180009ddd  mov     r9d, 4; dwType
0x180009de3  xor     r8d, r8d; Reserved
0x180009de6  mov     rdx, [r15]; lpValueName
0x180009de9  mov     rcx, [r14]; hKey
0x180009dec  call    cs:__imp_RegSetValueExW
0x180009df2  mov     edi, eax
0x180009df4  test    eax, eax
0x180009df6  jnz     loc_180009EAD
0x180009dfc  inc     dword ptr [r14+8]
0x180009e00  mov     rcx, [rsp+78h+var_40]
0x180009e05  test    rcx, rcx
0x180009e08  jz      short loc_180009E17
0x180009e0a  mov     rax, [rcx]
0x180009e0d  mov     rax, [rax+10h]
0x180009e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e16  nop
0x180009e17  mov     rcx, rbx; bstrString
0x180009e1a  call    cs:__imp_SysFreeString
0x180009e20  nop
0x180009e21  mov     rcx, [rsp+78h+arg_18]
0x180009e29  test    rcx, rcx
0x180009e2c  jz      short loc_180009E3B
0x180009e2e  mov     rax, [rcx]
0x180009e31  mov     rax, [rax+10h]
0x180009e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e3a  nop
0x180009e3b  jmp     loc_180009F24
0x180009e40  cmp     eax, 2
0x180009e43  jz      loc_180009BC8
0x180009e49  test    eax, eax
0x180009e4b  jle     short loc_180009E56
0x180009e4d  movzx   edi, ax
0x180009e50  or      edi, 80070000h
0x180009e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180009e5d  cmp     rcx, rsi
0x180009e60  jz      loc_180009F83
0x180009e66  test    byte ptr [rcx+1Ch], 1
0x180009e6a  jz      loc_180009F83
0x180009e70  mov     edx, 6Dh ; 'm'
0x180009e75  mov     dword ptr [rsp+78h+ppv], edi
0x180009e79  mov     r9, [r15]
0x180009e7c  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009e83  mov     rcx, [rcx+10h]
0x180009e87  call    WPP_SF_Sd
0x180009e8c  jmp     loc_180009F83
0x180009e91  call    cs:__imp_SysAllocString
0x180009e97  mov     rbx, rax
0x180009e9a  mov     [rsp+78h+var_38], rax
0x180009e9f  test    rax, rax
0x180009ea2  jz      loc_180009FB6
0x180009ea8  jmp     loc_180009BEF
0x180009ead  jle     short loc_180009EB8
0x180009eaf  movzx   edi, ax
0x180009eb2  or      edi, 80070000h
0x180009eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180009ebf  cmp     rcx, rsi
0x180009ec2  jz      short loc_180009EE7
0x180009ec4  test    byte ptr [rcx+1Ch], 1
0x180009ec8  jz      short loc_180009EE7
0x180009eca  mov     edx, 71h ; 'q'
0x180009ecf  mov     dword ptr [rsp+78h+ppv], edi
0x180009ed3  mov     r9, [r15]
0x180009ed6  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009edd  mov     rcx, [rcx+10h]
0x180009ee1  call    WPP_SF_Sd
0x180009ee6  nop
0x180009ee7  mov     rcx, [rsp+78h+var_40]
0x180009eec  test    rcx, rcx
0x180009eef  jz      short loc_180009EFE
0x180009ef1  mov     rax, [rcx]
0x180009ef4  mov     rax, [rax+10h]
0x180009ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009efd  nop
0x180009efe  mov     rcx, rbx; bstrString
0x180009f01  call    cs:__imp_SysFreeString
0x180009f07  nop
0x180009f08  mov     rcx, [rsp+78h+arg_18]
0x180009f10  test    rcx, rcx
0x180009f13  jz      short loc_180009F22
0x180009f15  mov     rax, [rcx]
0x180009f18  mov     rax, [rax+10h]
0x180009f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f21  nop
0x180009f22  jmp     short loc_180009F83
0x180009f24  xor     edi, edi
0x180009f26  jmp     short loc_180009F57
0x180009f28  mov     r15, [rsp+78h+arg_8]
0x180009f30  mov     edi, [rsp+78h+Data]
0x180009f37  jmp     short loc_180009F83
0x180009f39  lea     rsi, WPP_GLOBAL_Control
0x180009f40  mov     r14, [rsp+78h+arg_0]
0x180009f48  mov     r15, [rsp+78h+arg_8]
0x180009f50  mov     edi, [rsp+78h+Data]
0x180009f57  mov     rcx, cs:WPP_GLOBAL_Control
0x180009f5e  cmp     rcx, rsi
0x180009f61  jz      short loc_180009F83
0x180009f63  test    byte ptr [rcx+1Ch], 8
0x180009f67  jz      short loc_180009F83
0x180009f69  mov     edx, 73h ; 's'
0x180009f6e  mov     r9d, [r14+8]
0x180009f72  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009f79  mov     rcx, [rcx+10h]
0x180009f7d  call    WPP_SF_d
0x180009f82  nop
0x180009f83  mov     rdx, [r15]
0x180009f86  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180009f8a  mov     eax, 0FFFFFFFFh
0x180009f8f  lock xadd [rdx+10h], eax
0x180009f94  sub     eax, 1
0x180009f97  jg      short loc_180009FA8
0x180009f99  mov     rcx, [rdx]
0x180009f9c  mov     rax, [rcx]
  ... truncated ...
```
