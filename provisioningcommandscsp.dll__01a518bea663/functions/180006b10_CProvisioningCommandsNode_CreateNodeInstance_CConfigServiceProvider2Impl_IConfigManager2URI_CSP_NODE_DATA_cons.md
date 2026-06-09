# CProvisioningCommandsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180006b10`
- end: `0x1800071d1`
- name: `?CreateNodeInstance@CProvisioningCommandsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `1729`
- prototype: `__int64 __fastcall(struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *, int, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180009080`

## callees

- `0x18000108c`
- `0x1800021f8`
- `0x180004da4`
- `0x180006b10`
- `0x1800071d8`
- `0x180007360`
- `0x18000747c`
- `0x1800074c4`
- `0x1800079c0`
- `0x180007b08`
- `0x180007c18`
- `0x180009f34`
- `0x18000a010`
- `0x18000a050`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000a640`
- `0x18000a7f8`
- `0x18000c600`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006fac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007020`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006fac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007020`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c70`
- `OLEAUT32!__imp_SysFreeString` at `0x180006c70`

## string_xrefs

- `0x180006d43`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x180006f32`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x180006f67`: `\Commands`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::CreateNodeInstance(
        struct CConfigServiceProvider2Impl *a1,
        struct IConfigManager2URI *a2,
        const struct CSP_NODE_DATA *a3,
        int a4,
        struct ICSPNode **a5,
        unsigned int *a6)
{
  BSTR v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ebx
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  RegistryConfig *v22; // rcx
  RegistryConfig *v23; // rcx
  struct ICSPNode *v24; // rax
  struct ICSPNode *v25; // rdi
  int v26; // eax
  __int64 v27; // rdx
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // eax
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  int Command; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  int v40; // [rsp+20h] [rbp-E0h]
  BSTR bstrString; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v42; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-C0h] BYREF
  int v44; // [rsp+48h] [rbp-B8h] BYREF
  int v45; // [rsp+4Ch] [rbp-B4h] BYREF
  void *v46[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v47; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v48; // [rsp+68h] [rbp-98h]
  void *Src[6]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v50[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v51; // [rsp+B0h] [rbp-50h]
  __int64 v52; // [rsp+B8h] [rbp-48h]
  __int16 v53; // [rsp+C0h] [rbp-40h]
  __int64 v54; // [rsp+D0h] [rbp-30h]
  __int64 v55; // [rsp+D8h] [rbp-28h]
  __int16 v56[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v57; // [rsp+F0h] [rbp-10h]
  __int64 v58; // [rsp+F8h] [rbp-8h]
  int v59; // [rsp+100h] [rbp+0h]
  int v60; // [rsp+104h] [rbp+4h]
  _DWORD v61[6]; // [rsp+110h] [rbp+10h] BYREF
  char v62[8]; // [rsp+128h] [rbp+28h] BYREF
  BSTR v63; // [rsp+130h] [rbp+30h]
  int v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+13Ch] [rbp+3Ch]
  unsigned __int16 **v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+148h] [rbp+48h]
  wchar_t **p_String1; // [rsp+150h] [rbp+50h]
  __int64 v69; // [rsp+158h] [rbp+58h]
  int *v70; // [rsp+160h] [rbp+60h]
  __int64 v71; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v44 = 0;
  if ( !a1 || !a2 || !a3 || !a5 || !a6 )
    return (unsigned int)-2147024809;
  *a5 = 0;
  *a6 = 0;
  if ( (unsigned int)dword_180014230 > 4 )
  {
    bstrString = 0;
    (*(void (__fastcall **)(struct IConfigManager2URI *, _QWORD, __int64, BSTR *))(*(_QWORD *)a2 + 120LL))(
      a2,
      0,
      47,
      &bstrString);
    if ( (unsigned int)dword_180014230 > 4 )
    {
      v45 = a4;
      LODWORD(String1) = *((_DWORD *)a3 + 6);
      LODWORD(v42) = *((_DWORD *)a3 + 3);
      v10 = bstrString;
      v70 = &v45;
      v71 = 4;
      p_String1 = &String1;
      v69 = 4;
      v66 = &v42;
      v67 = 4;
      if ( bstrString )
      {
        v11 = -1;
        do
          ++v11;
        while ( bstrString[v11] );
        v12 = 2 * v11 + 2;
      }
      else
      {
        v10 = (BSTR)&qword_180010000;
        v12 = 2;
      }
      v63 = v10;
      v64 = v12;
      v65 = 0;
      v40 = 6;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_180010889, 0, 0);
    }
    SysFreeString(bstrString);
  }
  if ( a4 )
  {
    if ( (*((_BYTE *)a3 + 20) & 4) == 0 )
      return (unsigned int)-2046820335;
    v14 = *((_DWORD *)a3 + 3);
    if ( v14 > 7 )
    {
      v28 = v14 - 8;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            if ( v30 - 1 >= 2 )
              return (unsigned int)-2147418113;
          }
        }
      }
      goto LABEL_34;
    }
    if ( v14 == 7 )
      goto LABEL_39;
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_34;
    v16 = v15 - 1;
    if ( !v16 )
      goto LABEL_26;
    v17 = v16 - 1;
    if ( !v17 )
    {
LABEL_39:
      RegistryConfig::RegistryConfig((RegistryConfig *)v61);
      v52 = 7;
      v51 = 0;
      v50[0] = 0;
      v55 = 7;
      v54 = 0;
      v53 = 0;
      v58 = 7;
      v57 = 0;
      v56[0] = 0;
      v59 = 0;
      v60 = 1;
      v42 = 0;
      String1 = 0;
      bstrString = 0;
      v26 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, wchar_t **))(*(_QWORD *)a2 + 88LL))(
              a2,
              1,
              &String1);
      v13 = v26;
      if ( v26 >= 0 )
      {
        v26 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                a2,
                2,
                &v42);
        v13 = v26;
        if ( v26 >= 0 )
        {
          v26 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, BSTR *))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  3,
                  &bstrString);
          v13 = v26;
          if ( v26 >= 0 )
          {
            CProvisioningCommandsNode::GetSessionStringFromCsp(Src);
            std::wstring::append(Src, L"\\Commands");
            v48 = 7;
            v47 = 0;
            LOWORD(v46[0]) = 0;
            std::wstring::assign(v46);
            if ( Src[3] >= (void *)8 )
              operator delete(Src[0]);
            if ( *((_DWORD *)a3 + 3) == 7 )
            {
              std::wstring::append(v46, L"\\");
              std::wstring::append(v46, bstrString);
            }
            std::wstring::assign(v50, bstrString);
            std::wstring::assign(v56);
            RegistryConfig::AddCommand((RegistryConfig *)v61, String1, v42, (const struct Command *)v50);
            if ( v48 >= 8 )
              operator delete(v46[0]);
            v48 = 7;
            v47 = 0;
            LOWORD(v46[0]) = 0;
            Command::~Command((Command *)v50);
            v23 = (RegistryConfig *)v61;
LABEL_33:
            RegistryConfig::~RegistryConfig(v23);
            goto LABEL_34;
          }
          v27 = 160;
        }
        else
        {
          v27 = 159;
        }
      }
      else
      {
        v27 = 158;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
        (const char *)(unsigned int)v26,
        v40);
      Command::~Command((Command *)v50);
      v22 = (RegistryConfig *)v61;
      goto LABEL_31;
    }
    v18 = v17 - 1;
    if ( v18 )
    {
      v19 = v18 - 1;
      if ( v19 )
      {
        if ( v19 != 1 )
          return (unsigned int)-2147418113;
LABEL_26:
        RegistryConfig::RegistryConfig((RegistryConfig *)Src);
        CommandSet::CommandSet((CommandSet *)v61);
        bstrString = 0;
        v42 = 0;
        v20 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
                a2,
                1,
                &v42);
        v13 = v20;
        if ( v20 < 0 )
        {
          v21 = 138;
LABEL_30:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
            (const char *)(unsigned int)v20,
            v40);
          CommandSet::~CommandSet((CommandSet *)v61);
          v22 = (RegistryConfig *)Src;
LABEL_31:
          RegistryConfig::~RegistryConfig(v22);
          return (unsigned int)v13;
        }
        v20 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, BSTR *))(*(_QWORD *)a2 + 88LL))(
                a2,
                2,
                &bstrString);
        v13 = v20;
        if ( v20 < 0 )
        {
          v21 = 139;
          goto LABEL_30;
        }
        std::wstring::assign(v62, bstrString);
        v61[0] = CProvisioningCommandsNode::GetAltitude(a1);
        RegistryConfig::Add((RegistryConfig *)Src, v42, (const struct CommandSet *)v61);
        CommandSet::~CommandSet((CommandSet *)v61);
        v23 = (RegistryConfig *)Src;
        goto LABEL_33;
      }
    }
LABEL_34:
    v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, int *))(*(_QWORD *)a2 + 136LL))(a2, &v44);
    if ( v13 < 0 )
      return (unsigned int)v13;
    if ( *((_DWORD *)a3 + 2) + 1 == v44 )
    {
      v24 = (struct ICSPNode *)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
      v25 = v24;
      bstrString = (BSTR)v24;
      if ( v24 )
      {
        *((_QWORD *)v24 + 2) = 0;
        *((_QWORD *)v24 + 3) = 0;
        *((_DWORD *)v24 + 16) = 1;
        *((_OWORD *)v24 + 2) = 0;
        *((_OWORD *)v24 + 3) = 0;
        *(_QWORD *)v24 = &CProvisioningCommandsNode::`vftable'{for `ICSPNode'};
        *((_QWORD *)v24 + 1) = &CProvisioningCommandsNode::`vftable'{for `ICSPNodeTransactioning'};
        *((_DWORD *)v24 + 18) = 0;
        _InterlockedIncrement(&dword_180014AB8);
        v13 = (*(__int64 (__fastcall **)(struct ICSPNode *, struct CConfigServiceProvider2Impl *, struct IConfigManager2URI *, const struct CSP_NODE_DATA *))(*(_QWORD *)v24 + 136LL))(
                v24,
                a1,
                a2,
                a3);
        if ( v13 < 0 )
          (*(void (__fastcall **)(struct ICSPNode *))(*(_QWORD *)v25 + 16LL))(v25);
        else
          *a5 = v25;
      }
      else
      {
        return (unsigned int)-2147024882;
      }
      return (unsigned int)v13;
    }
    return (unsigned int)-2147418113;
  }
  if ( *((_DWORD *)a3 + 6) )
    goto LABEL_34;
  bstrString = 0;
  v42 = 0;
  v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(
          a2,
          1,
          &v42);
  if ( v13 >= 0 )
  {
    v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, BSTR *))(*(_QWORD *)a2 + 88LL))(
            a2,
            2,
            &bstrString);
    if ( v13 >= 0 )
    {
      v31 = *((_DWORD *)a3 + 3);
      if ( v31 > 8 )
      {
        v37 = v31 - 9;
        if ( !v37 )
          goto LABEL_34;
        v38 = v37 - 1;
        if ( !v38 || v38 - 1 < 2 )
          goto LABEL_34;
      }
      else
      {
        if ( v31 == 8 )
          goto LABEL_34;
        v32 = v31 - 2;
        if ( !v32 )
          goto LABEL_72;
        v33 = v32 - 1;
        if ( !v33 )
        {
LABEL_68:
          String1 = 0;
          v13 = (*(__int64 (__fastcall **)(struct IConfigManager2URI *, __int64, wchar_t **))(*(_QWORD *)a2 + 88LL))(
                  a2,
                  3,
                  &String1);
          if ( v13 < 0 )
            return (unsigned int)v13;
          Command = CProvisioningCommandsNode::FindCommand(v42, bstrString, String1, 0);
          goto LABEL_70;
        }
        v34 = v33 - 1;
        if ( !v34 )
          goto LABEL_34;
        v35 = v34 - 2;
        if ( !v35 )
        {
LABEL_72:
          Command = CProvisioningCommandsNode::FindCommandSet(v42, bstrString, 0);
LABEL_70:
          v13 = Command;
          if ( Command < 0 )
            return (unsigned int)v13;
          goto LABEL_34;
        }
        if ( v35 == 1 )
          goto LABEL_68;
      }
      return (unsigned int)-2046820350;
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006b10  mov     [rsp-8+arg_18], rbx
0x180006b15  push    rbp
0x180006b16  push    rsi
0x180006b17  push    rdi
0x180006b18  push    r12
0x180006b1a  push    r13
0x180006b1c  push    r14
0x180006b1e  push    r15
0x180006b20  lea     rbp, [rsp-80h]
0x180006b25  sub     rsp, 180h
0x180006b2c  mov     rax, cs:__security_cookie
0x180006b33  xor     rax, rsp
0x180006b36  mov     [rbp+0B0h+var_40], rax
0x180006b3a  mov     ebx, r9d
0x180006b3d  mov     r14, r8
0x180006b40  mov     rsi, rdx
0x180006b43  mov     r12, rcx
0x180006b46  mov     r15, [rbp+0B0h+arg_20]
0x180006b4d  mov     rax, [rbp+0B0h+arg_28]
0x180006b54  xor     r13d, r13d
0x180006b57  mov     [rsp+1B0h+var_168], r13d
0x180006b5c  test    rcx, rcx
0x180006b5f  jz      loc_1800071A3
0x180006b65  test    rdx, rdx
0x180006b68  jz      loc_1800071A3
0x180006b6e  test    r8, r8
0x180006b71  jz      loc_1800071A3
0x180006b77  test    r15, r15
0x180006b7a  jz      loc_1800071A3
0x180006b80  test    rax, rax
0x180006b83  jz      loc_1800071A3
0x180006b89  mov     [r15], r13
0x180006b8c  mov     [rax], r13d
0x180006b8f  mov     eax, cs:dword_180014230
0x180006b95  lea     edi, [r13+4]
0x180006b99  cmp     eax, edi
0x180006b9b  jbe     loc_180006C76
0x180006ba1  mov     [rsp+1B0h+bstrString], r13
0x180006ba6  mov     rax, [rdx]
0x180006ba9  lea     r8d, [r13+2Fh]
0x180006bad  lea     r9, [rsp+1B0h+bstrString]
0x180006bb2  xor     edx, edx
0x180006bb4  mov     rcx, rsi
0x180006bb7  mov     rax, [rax+78h]
0x180006bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc0  mov     eax, cs:dword_180014230
0x180006bc6  cmp     eax, edi
0x180006bc8  jbe     loc_180006C6B
0x180006bce  mov     [rsp+1B0h+var_164], ebx
0x180006bd2  mov     eax, [r14+18h]
0x180006bd6  mov     dword ptr [rsp+1B0h+String1], eax
0x180006bda  mov     eax, [r14+0Ch]
0x180006bde  mov     dword ptr [rsp+1B0h+var_178], eax
0x180006be2  mov     rcx, [rsp+1B0h+bstrString]
0x180006be7  lea     rax, [rsp+1B0h+var_164]
0x180006bec  mov     [rbp+0B0h+var_50], rax
0x180006bf0  mov     [rbp+0B0h+var_48], rdi
0x180006bf4  lea     rax, [rsp+1B0h+String1]
0x180006bf9  mov     [rbp+0B0h+var_60], rax
0x180006bfd  mov     [rbp+0B0h+var_58], rdi
0x180006c01  lea     rax, [rsp+1B0h+var_178]
0x180006c06  mov     [rbp+0B0h+var_70], rax
0x180006c0a  mov     [rbp+0B0h+var_68], rdi
0x180006c0e  test    rcx, rcx
0x180006c11  jz      short loc_180006C2A
0x180006c13  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006c17  inc     rax
0x180006c1a  cmp     [rcx+rax*2], r13w
0x180006c1f  jnz     short loc_180006C17
0x180006c21  lea     eax, ds:2[rax*2]
0x180006c28  jmp     short loc_180006C36
0x180006c2a  lea     rcx, qword_180010000
0x180006c31  mov     eax, 2
0x180006c36  mov     [rbp+0B0h+var_80], rcx
0x180006c3a  mov     [rbp+0B0h+var_78], eax
0x180006c3d  mov     [rbp+0B0h+var_74], r13d
0x180006c41  lea     rax, [rbp+0B0h+var_A0]
0x180006c45  mov     [rsp+1B0h+var_188], rax
0x180006c4a  mov     [rsp+1B0h+var_190], 6; int
0x180006c52  xor     r9d, r9d
0x180006c55  xor     r8d, r8d
0x180006c58  lea     rdx, byte_180010889
0x180006c5f  lea     rcx, dword_180014230
0x180006c66  call    _tlgWriteTransfer_EventWriteTransfer
0x180006c6b  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x180006c70  call    cs:__imp_SysFreeString
0x180006c76  test    ebx, ebx
0x180006c78  jz      loc_180007080
0x180006c7e  test    [r14+14h], dil
0x180006c82  jnz     short loc_180006C8E
0x180006c84  mov     ebx, 86000011h
0x180006c89  jmp     loc_1800071A8
0x180006c8e  mov     eax, [r14+0Ch]
0x180006c92  mov     edi, 7
0x180006c97  cmp     eax, edi
0x180006c99  ja      loc_180007049
0x180006c9f  jz      loc_180006E74
0x180006ca5  sub     eax, 1
0x180006ca8  jz      loc_180006DB1
0x180006cae  sub     eax, 1
0x180006cb1  jz      short loc_180006CD7
0x180006cb3  sub     eax, 1
0x180006cb6  jz      loc_180006E74
0x180006cbc  sub     eax, 1
0x180006cbf  jz      loc_180006DB1
0x180006cc5  sub     eax, 1
0x180006cc8  jz      loc_180006DB1
0x180006cce  cmp     eax, 1
0x180006cd1  jnz     loc_180007076
0x180006cd7  lea     rcx, [rsp+1B0h+Src]; this
0x180006cdc  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180006ce1  nop
0x180006ce2  lea     rcx, [rbp+0B0h+var_A0]; this
0x180006ce6  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x180006ceb  nop
0x180006cec  mov     [rsp+1B0h+bstrString], r13
0x180006cf1  mov     [rsp+1B0h+var_178], r13
0x180006cf6  mov     rax, [rsi]
0x180006cf9  lea     r8, [rsp+1B0h+var_178]
0x180006cfe  mov     edx, 1
0x180006d03  mov     rcx, rsi
0x180006d06  mov     rax, [rax+58h]
0x180006d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0f  mov     ebx, eax
0x180006d11  test    eax, eax
0x180006d13  jns     short loc_180006D1C
0x180006d15  mov     edx, 8Ah
0x180006d1a  jmp     short loc_180006D40
0x180006d1c  mov     rax, [rsi]
0x180006d1f  lea     r8, [rsp+1B0h+bstrString]
0x180006d24  mov     edx, 2
0x180006d29  mov     rcx, rsi
0x180006d2c  mov     rax, [rax+58h]
0x180006d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d35  mov     ebx, eax
0x180006d37  test    eax, eax
0x180006d39  jns     short loc_180006D70
0x180006d3b  mov     edx, 8Bh; void *
0x180006d40  mov     r9d, eax; char *
0x180006d43  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180006d4a  mov     rcx, [rbp+0B8h]; this
0x180006d51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006d56  nop
0x180006d57  lea     rcx, [rbp+0B0h+var_A0]; this
0x180006d5b  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180006d60  nop
0x180006d61  lea     rcx, [rsp+1B0h+Src]; this
0x180006d66  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180006d6b  jmp     loc_1800071A8
0x180006d70  mov     rdx, [rsp+1B0h+bstrString]; Src
0x180006d75  lea     rcx, [rbp+0B0h+var_88]; void *
0x180006d79  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180006d7e  mov     rcx, r12; struct CConfigServiceProvider2Impl *
0x180006d81  call    ?GetAltitude@CProvisioningCommandsNode@@CAKPEAVCConfigServiceProvider2Impl@@@Z; CProvisioningCommandsNode::GetAltitude(CConfigServiceProvider2Impl *)
0x180006d86  mov     [rbp+0B0h+var_A0], eax
0x180006d89  lea     r8, [rbp+0B0h+var_A0]; struct CommandSet *
0x180006d8d  mov     rdx, [rsp+1B0h+var_178]; unsigned __int16 *
0x180006d92  lea     rcx, [rsp+1B0h+Src]; this
0x180006d97  call    ?Add@RegistryConfig@@QEAAXPEBGPEBUCommandSet@@@Z; RegistryConfig::Add(ushort const *,CommandSet const *)
0x180006d9c  nop
0x180006d9d  lea     rcx, [rbp+0B0h+var_A0]; this
0x180006da1  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180006da6  nop
0x180006da7  lea     rcx, [rsp+1B0h+Src]; this
0x180006dac  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180006db1  mov     rax, [rsi]
0x180006db4  lea     rdx, [rsp+1B0h+var_168]
0x180006db9  mov     rcx, rsi
0x180006dbc  mov     rax, [rax+88h]
0x180006dc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc8  mov     ebx, eax
0x180006dca  test    eax, eax
0x180006dcc  js      loc_1800071A8
0x180006dd2  mov     eax, [r14+8]
0x180006dd6  inc     eax
0x180006dd8  cmp     eax, [rsp+1B0h+var_168]
0x180006ddc  jnz     loc_180007076
0x180006de2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006de9  mov     ecx, 50h ; 'P'; unsigned __int64
0x180006dee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006df3  mov     rdi, rax
0x180006df6  mov     [rsp+1B0h+bstrString], rax
0x180006dfb  test    rax, rax
0x180006dfe  jz      loc_18000719C
0x180006e04  mov     [rax+10h], r13
0x180006e08  mov     [rax+18h], r13
0x180006e0c  mov     dword ptr [rax+40h], 1
0x180006e13  xorps   xmm0, xmm0
0x180006e16  movups  xmmword ptr [rax+20h], xmm0
0x180006e1a  movups  xmmword ptr [rax+30h], xmm0
0x180006e1e  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNode@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNode'}
0x180006e25  mov     [rdi], rax
0x180006e28  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNodeTransactioning@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180006e2f  mov     [rdi+8], rax
0x180006e33  mov     [rdi+48h], r13d
0x180006e37  lock inc cs:dword_180014AB8
0x180006e3e  test    rdi, rdi
0x180006e41  jz      loc_18000719C
0x180006e47  mov     rax, [rdi]
0x180006e4a  mov     r9, r14
0x180006e4d  mov     r8, rsi
0x180006e50  mov     rdx, r12
0x180006e53  mov     rcx, rdi
0x180006e56  mov     rax, [rax+88h]
0x180006e5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e62  mov     ebx, eax
0x180006e64  test    eax, eax
0x180006e66  js      loc_18000718B
0x180006e6c  mov     [r15], rdi
0x180006e6f  jmp     loc_1800071A8
0x180006e74  lea     rcx, [rbp+0B0h+var_A0]; this
0x180006e78  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180006e7d  nop
0x180006e7e  mov     [rbp+0B0h+var_F8], rdi
0x180006e82  mov     [rbp+0B0h+var_100], r13
0x180006e86  mov     [rbp+0B0h+var_110], r13w
0x180006e8b  mov     [rbp+0B0h+var_D8], rdi
0x180006e8f  mov     [rbp+0B0h+var_E0], r13
0x180006e93  mov     [rbp+0B0h+var_F0], r13w
0x180006e98  mov     [rbp+0B0h+var_B8], rdi
0x180006e9c  mov     [rbp+0B0h+var_C0], r13
0x180006ea0  mov     [rbp+0B0h+var_D0], r13w
0x180006ea5  mov     [rbp+0B0h+var_B0], r13d
0x180006ea9  mov     [rbp+0B0h+var_AC], 1
0x180006eb0  mov     [rsp+1B0h+var_178], r13
0x180006eb5  mov     [rsp+1B0h+String1], r13
0x180006eba  mov     [rsp+1B0h+bstrString], r13
0x180006ebf  mov     rax, [rsi]
0x180006ec2  lea     r8, [rsp+1B0h+String1]
0x180006ec7  mov     edx, 1
0x180006ecc  mov     rcx, rsi
0x180006ecf  mov     rax, [rax+58h]
0x180006ed3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed8  mov     ebx, eax
0x180006eda  test    eax, eax
0x180006edc  jns     short loc_180006EE5
0x180006ede  mov     edx, 9Eh
0x180006ee3  jmp     short loc_180006F2F
0x180006ee5  mov     rax, [rsi]
0x180006ee8  lea     r8, [rsp+1B0h+var_178]
0x180006eed  mov     edx, 2
0x180006ef2  mov     rcx, rsi
0x180006ef5  mov     rax, [rax+58h]
0x180006ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006efe  mov     ebx, eax
0x180006f00  test    eax, eax
0x180006f02  jns     short loc_180006F0B
0x180006f04  mov     edx, 9Fh
0x180006f09  jmp     short loc_180006F2F
0x180006f0b  mov     rax, [rsi]
0x180006f0e  lea     r8, [rsp+1B0h+bstrString]
0x180006f13  mov     edx, 3
0x180006f18  mov     rcx, rsi
0x180006f1b  mov     rax, [rax+58h]
0x180006f1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f24  mov     ebx, eax
0x180006f26  test    eax, eax
0x180006f28  jns     short loc_180006F59
0x180006f2a  mov     edx, 0A0h; void *
0x180006f2f  mov     r9d, eax; char *
0x180006f32  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180006f39  mov     rcx, [rbp+0B8h]; this
0x180006f40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006f45  nop
0x180006f46  lea     rcx, [rbp+0B0h+var_110]; this
0x180006f4a  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180006f4f  nop
0x180006f50  lea     rcx, [rbp+0B0h+var_A0]
0x180006f54  jmp     loc_180006D66
0x180006f59  mov     r8, r12
0x180006f5c  lea     rcx, [rsp+1B0h+Src]; void *
0x180006f61  call    ?GetSessionStringFromCsp@CProvisioningCommandsNode@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAVCConfigServiceProvider2Impl@@@Z; CProvisioningCommandsNode::GetSessionStringFromCsp(ushort const *,CConfigServiceProvider2Impl *)
0x180006f66  nop
0x180006f67  lea     rdx, aCommands; "\\Commands"
0x180006f6e  lea     rcx, [rsp+1B0h+Src]; Src
0x180006f73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180006f78  mov     [rsp+1B0h+var_148], rdi
0x180006f7d  mov     [rsp+1B0h+var_150], r13
0x180006f82  mov     word ptr [rsp+1B0h+var_160], r13w
0x180006f88  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180006f8c  mov     r9, rbx
0x180006f8f  xor     r8d, r8d
0x180006f92  mov     rdx, rax
0x180006f95  lea     rcx, [rsp+1B0h+var_160]; void *
0x180006f9a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006f9f  nop
0x180006fa0  cmp     [rbp+0B0h+var_128], 8
0x180006fa5  jb      short loc_180006FB3
0x180006fa7  mov     rcx, [rsp+1B0h+Src]
0x180006fac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180006fb2  nop
0x180006fb3  cmp     [r14+0Ch], edi
0x180006fb7  jnz     short loc_180006FD9
0x180006fb9  lea     rdx, asc_180010164; "\\"
0x180006fc0  lea     rcx, [rsp+1B0h+var_160]; Src
0x180006fc5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180006fca  mov     rdx, [rsp+1B0h+bstrString]; void *
0x180006fcf  lea     rcx, [rsp+1B0h+var_160]; Src
0x180006fd4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180006fd9  mov     rdx, [rsp+1B0h+bstrString]; Src
  ... truncated ...
```
