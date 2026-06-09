# CProvisioningCommandsNode::CreateNodeInstance(CConfigServiceProvider2Impl *,IConfigManager2URI *,CSP_NODE_DATA const *,int,ICSPNode * *,ulong *)

- ea: `0x180006e40`
- end: `0x180007514`
- name: `?CreateNodeInstance@CProvisioningCommandsNode@@SAJPEAVCConfigServiceProvider2Impl@@PEAUIConfigManager2URI@@PEBUCSP_NODE_DATA@@HPEAPEAUICSPNode@@PEAK@Z`
- size: `1748`
- prototype: `__int64 __usercall@<rax>(struct CConfigServiceProvider2Impl *@<rcx>, struct IConfigManager2URI *@<rdx>, const struct CSP_NODE_DATA *@<r8>, int@<r9d>, struct ICSPNode **, unsigned int *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800094a0`

## callees

- `0x180001090`
- `0x180002208`
- `0x180004ee4`
- `0x180006e40`
- `0x18000751c`
- `0x1800076ac`
- `0x1800077cc`
- `0x18000781c`
- `0x180007d54`
- `0x180007e9c`
- `0x180007fac`
- `0x18000a418`
- `0x18000a50c`
- `0x18000a554`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000abb0`
- `0x18000ad90`
- `0x18000ccc0`
- `0x18000e010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800072e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000735c`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800072e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000735c`
- `OLEAUT32!__imp_SysFreeString` at `0x180006fa0`
- `OLEAUT32!__imp_SysFreeString` at `0x180006fa0`

## string_xrefs

- `0x180007079`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x180007268`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`
- `0x18000729d`: `\Commands`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  HKEY v61[3]; // [rsp+110h] [rbp+10h] BYREF
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
      tlgWriteTransfer_EventWriteTransfer(
        (__int64)&dword_180014230,
        (unsigned __int8 *)byte_180010889,
        0,
        0,
        6u,
        (PEVENT_DATA_DESCRIPTOR)v61);
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
            RegistryConfig::AddCommand(v61, String1, v42, (const struct Command *)v50);
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
        LODWORD(v61[0]) = CProvisioningCommandsNode::GetAltitude(a1);
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
0x180006e40  mov     [rsp-8+arg_18], rbx
0x180006e45  push    rbp
0x180006e46  push    rsi
0x180006e47  push    rdi
0x180006e48  push    r12
0x180006e4a  push    r13
0x180006e4c  push    r14
0x180006e4e  push    r15
0x180006e50  lea     rbp, [rsp-80h]
0x180006e55  sub     rsp, 180h
0x180006e5c  mov     rax, cs:__security_cookie
0x180006e63  xor     rax, rsp
0x180006e66  mov     [rbp+0B0h+var_40], rax
0x180006e6a  mov     ebx, r9d
0x180006e6d  mov     r14, r8
0x180006e70  mov     rsi, rdx
0x180006e73  mov     r12, rcx
0x180006e76  mov     r15, [rbp+0B0h+arg_20]
0x180006e7d  mov     rax, [rbp+0B0h+arg_28]
0x180006e84  xor     r13d, r13d
0x180006e87  mov     [rsp+1B0h+var_168], r13d
0x180006e8c  test    rcx, rcx
0x180006e8f  jz      loc_1800074E5
0x180006e95  test    rdx, rdx
0x180006e98  jz      loc_1800074E5
0x180006e9e  test    r8, r8
0x180006ea1  jz      loc_1800074E5
0x180006ea7  test    r15, r15
0x180006eaa  jz      loc_1800074E5
0x180006eb0  test    rax, rax
0x180006eb3  jz      loc_1800074E5
0x180006eb9  mov     [r15], r13
0x180006ebc  mov     [rax], r13d
0x180006ebf  mov     eax, cs:dword_180014230
0x180006ec5  lea     edi, [r13+4]
0x180006ec9  cmp     eax, edi
0x180006ecb  jbe     loc_180006FAC
0x180006ed1  mov     [rsp+1B0h+bstrString], r13
0x180006ed6  mov     rax, [rdx]
0x180006ed9  lea     r8d, [r13+2Fh]
0x180006edd  lea     r9, [rsp+1B0h+bstrString]
0x180006ee2  xor     edx, edx
0x180006ee4  mov     rcx, rsi
0x180006ee7  mov     rax, [rax+78h]
0x180006eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef0  mov     eax, cs:dword_180014230
0x180006ef6  cmp     eax, edi
0x180006ef8  jbe     loc_180006F9B
0x180006efe  mov     [rsp+1B0h+var_164], ebx
0x180006f02  mov     eax, [r14+18h]
0x180006f06  mov     dword ptr [rsp+1B0h+String1], eax
0x180006f0a  mov     eax, [r14+0Ch]
0x180006f0e  mov     dword ptr [rsp+1B0h+var_178], eax
0x180006f12  mov     rcx, [rsp+1B0h+bstrString]
0x180006f17  lea     rax, [rsp+1B0h+var_164]
0x180006f1c  mov     [rbp+0B0h+var_50], rax
0x180006f20  mov     [rbp+0B0h+var_48], rdi
0x180006f24  lea     rax, [rsp+1B0h+String1]
0x180006f29  mov     [rbp+0B0h+var_60], rax
0x180006f2d  mov     [rbp+0B0h+var_58], rdi
0x180006f31  lea     rax, [rsp+1B0h+var_178]
0x180006f36  mov     [rbp+0B0h+var_70], rax
0x180006f3a  mov     [rbp+0B0h+var_68], rdi
0x180006f3e  test    rcx, rcx
0x180006f41  jz      short loc_180006F5A
0x180006f43  or      rax, 0FFFFFFFFFFFFFFFFh
0x180006f47  inc     rax
0x180006f4a  cmp     [rcx+rax*2], r13w
0x180006f4f  jnz     short loc_180006F47
0x180006f51  lea     eax, ds:2[rax*2]
0x180006f58  jmp     short loc_180006F66
0x180006f5a  lea     rcx, qword_180010000
0x180006f61  mov     eax, 2
0x180006f66  mov     [rbp+0B0h+var_80], rcx
0x180006f6a  mov     [rbp+0B0h+var_78], eax
0x180006f6d  mov     [rbp+0B0h+var_74], r13d
0x180006f71  lea     rax, [rbp+0B0h+var_A0]
0x180006f75  mov     [rsp+1B0h+var_188], rax
0x180006f7a  mov     [rsp+1B0h+var_190], 6; int
0x180006f82  xor     r9d, r9d
0x180006f85  xor     r8d, r8d
0x180006f88  lea     rdx, byte_180010889
0x180006f8f  lea     rcx, dword_180014230
0x180006f96  call    _tlgWriteTransfer_EventWriteTransfer
0x180006f9b  mov     rcx, [rsp+1B0h+bstrString]; bstrString
0x180006fa0  call    cs:__imp_SysFreeString
0x180006fa7  nop     dword ptr [rax+rax+00h]
0x180006fac  test    ebx, ebx
0x180006fae  jz      loc_1800073C2
0x180006fb4  test    [r14+14h], dil
0x180006fb8  jnz     short loc_180006FC4
0x180006fba  mov     ebx, 86000011h
0x180006fbf  jmp     loc_1800074EA
0x180006fc4  mov     eax, [r14+0Ch]
0x180006fc8  mov     edi, 7
0x180006fcd  cmp     eax, edi
0x180006fcf  ja      loc_18000738B
0x180006fd5  jz      loc_1800071AA
0x180006fdb  sub     eax, 1
0x180006fde  jz      loc_1800070E7
0x180006fe4  sub     eax, 1
0x180006fe7  jz      short loc_18000700D
0x180006fe9  sub     eax, 1
0x180006fec  jz      loc_1800071AA
0x180006ff2  sub     eax, 1
0x180006ff5  jz      loc_1800070E7
0x180006ffb  sub     eax, 1
0x180006ffe  jz      loc_1800070E7
0x180007004  cmp     eax, 1
0x180007007  jnz     loc_1800073B8
0x18000700d  lea     rcx, [rsp+1B0h+Src]; this
0x180007012  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180007017  nop
0x180007018  lea     rcx, [rbp+0B0h+var_A0]; this
0x18000701c  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x180007021  nop
0x180007022  mov     [rsp+1B0h+bstrString], r13
0x180007027  mov     [rsp+1B0h+var_178], r13
0x18000702c  mov     rax, [rsi]
0x18000702f  lea     r8, [rsp+1B0h+var_178]
0x180007034  mov     edx, 1
0x180007039  mov     rcx, rsi
0x18000703c  mov     rax, [rax+58h]
0x180007040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007045  mov     ebx, eax
0x180007047  test    eax, eax
0x180007049  jns     short loc_180007052
0x18000704b  mov     edx, 8Ah
0x180007050  jmp     short loc_180007076
0x180007052  mov     rax, [rsi]
0x180007055  lea     r8, [rsp+1B0h+bstrString]
0x18000705a  mov     edx, 2
0x18000705f  mov     rcx, rsi
0x180007062  mov     rax, [rax+58h]
0x180007066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000706b  mov     ebx, eax
0x18000706d  test    eax, eax
0x18000706f  jns     short loc_1800070A6
0x180007071  mov     edx, 8Bh; void *
0x180007076  mov     r9d, eax; char *
0x180007079  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x180007080  mov     rcx, [rbp+0B8h]; this
0x180007087  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000708c  nop
0x18000708d  lea     rcx, [rbp+0B0h+var_A0]; this
0x180007091  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180007096  nop
0x180007097  lea     rcx, [rsp+1B0h+Src]; this
0x18000709c  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800070a1  jmp     loc_1800074EA
0x1800070a6  mov     rdx, [rsp+1B0h+bstrString]; Src
0x1800070ab  lea     rcx, [rbp+0B0h+var_88]; void *
0x1800070af  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800070b4  mov     rcx, r12; struct CConfigServiceProvider2Impl *
0x1800070b7  call    ?GetAltitude@CProvisioningCommandsNode@@CAKPEAVCConfigServiceProvider2Impl@@@Z; CProvisioningCommandsNode::GetAltitude(CConfigServiceProvider2Impl *)
0x1800070bc  mov     dword ptr [rbp+0B0h+var_A0], eax
0x1800070bf  lea     r8, [rbp+0B0h+var_A0]; struct CommandSet *
0x1800070c3  mov     rdx, [rsp+1B0h+var_178]; unsigned __int16 *
0x1800070c8  lea     rcx, [rsp+1B0h+Src]; this
0x1800070cd  call    ?Add@RegistryConfig@@QEAAXPEBGPEBUCommandSet@@@Z; RegistryConfig::Add(ushort const *,CommandSet const *)
0x1800070d2  nop
0x1800070d3  lea     rcx, [rbp+0B0h+var_A0]; this
0x1800070d7  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x1800070dc  nop
0x1800070dd  lea     rcx, [rsp+1B0h+Src]; this
0x1800070e2  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800070e7  mov     rax, [rsi]
0x1800070ea  lea     rdx, [rsp+1B0h+var_168]
0x1800070ef  mov     rcx, rsi
0x1800070f2  mov     rax, [rax+88h]
0x1800070f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fe  mov     ebx, eax
0x180007100  test    eax, eax
0x180007102  js      loc_1800074EA
0x180007108  mov     eax, [r14+8]
0x18000710c  inc     eax
0x18000710e  cmp     eax, [rsp+1B0h+var_168]
0x180007112  jnz     loc_1800073B8
0x180007118  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000711f  mov     ecx, 50h ; 'P'; unsigned __int64
0x180007124  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007129  mov     rdi, rax
0x18000712c  mov     [rsp+1B0h+bstrString], rax
0x180007131  test    rax, rax
0x180007134  jz      loc_1800074DE
0x18000713a  mov     [rax+10h], r13
0x18000713e  mov     [rax+18h], r13
0x180007142  mov     dword ptr [rax+40h], 1
0x180007149  xorps   xmm0, xmm0
0x18000714c  movups  xmmword ptr [rax+20h], xmm0
0x180007150  movups  xmmword ptr [rax+30h], xmm0
0x180007154  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNode@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNode'}
0x18000715b  mov     [rdi], rax
0x18000715e  lea     rax, ??_7CProvisioningCommandsNode@@6BICSPNodeTransactioning@@@; const CProvisioningCommandsNode::`vftable'{for `ICSPNodeTransactioning'}
0x180007165  mov     [rdi+8], rax
0x180007169  mov     [rdi+48h], r13d
0x18000716d  lock inc cs:dword_180014AB8
0x180007174  test    rdi, rdi
0x180007177  jz      loc_1800074DE
0x18000717d  mov     rax, [rdi]
0x180007180  mov     r9, r14
0x180007183  mov     r8, rsi
0x180007186  mov     rdx, r12
0x180007189  mov     rcx, rdi
0x18000718c  mov     rax, [rax+88h]
0x180007193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007198  mov     ebx, eax
0x18000719a  test    eax, eax
0x18000719c  js      loc_1800074CD
0x1800071a2  mov     [r15], rdi
0x1800071a5  jmp     loc_1800074EA
0x1800071aa  lea     rcx, [rbp+0B0h+var_A0]; this
0x1800071ae  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800071b3  nop
0x1800071b4  mov     [rbp+0B0h+var_F8], rdi
0x1800071b8  mov     [rbp+0B0h+var_100], r13
0x1800071bc  mov     [rbp+0B0h+var_110], r13w
0x1800071c1  mov     [rbp+0B0h+var_D8], rdi
0x1800071c5  mov     [rbp+0B0h+var_E0], r13
0x1800071c9  mov     [rbp+0B0h+var_F0], r13w
0x1800071ce  mov     [rbp+0B0h+var_B8], rdi
0x1800071d2  mov     [rbp+0B0h+var_C0], r13
0x1800071d6  mov     [rbp+0B0h+var_D0], r13w
0x1800071db  mov     [rbp+0B0h+var_B0], r13d
0x1800071df  mov     [rbp+0B0h+var_AC], 1
0x1800071e6  mov     [rsp+1B0h+var_178], r13
0x1800071eb  mov     [rsp+1B0h+String1], r13
0x1800071f0  mov     [rsp+1B0h+bstrString], r13
0x1800071f5  mov     rax, [rsi]
0x1800071f8  lea     r8, [rsp+1B0h+String1]
0x1800071fd  mov     edx, 1
0x180007202  mov     rcx, rsi
0x180007205  mov     rax, [rax+58h]
0x180007209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000720e  mov     ebx, eax
0x180007210  test    eax, eax
0x180007212  jns     short loc_18000721B
0x180007214  mov     edx, 9Eh
0x180007219  jmp     short loc_180007265
0x18000721b  mov     rax, [rsi]
0x18000721e  lea     r8, [rsp+1B0h+var_178]
0x180007223  mov     edx, 2
0x180007228  mov     rcx, rsi
0x18000722b  mov     rax, [rax+58h]
0x18000722f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007234  mov     ebx, eax
0x180007236  test    eax, eax
0x180007238  jns     short loc_180007241
0x18000723a  mov     edx, 9Fh
0x18000723f  jmp     short loc_180007265
0x180007241  mov     rax, [rsi]
0x180007244  lea     r8, [rsp+1B0h+bstrString]
0x180007249  mov     edx, 3
0x18000724e  mov     rcx, rsi
0x180007251  mov     rax, [rax+58h]
0x180007255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000725a  mov     ebx, eax
0x18000725c  test    eax, eax
0x18000725e  jns     short loc_18000728F
0x180007260  mov     edx, 0A0h; void *
0x180007265  mov     r9d, eax; char *
0x180007268  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000726f  mov     rcx, [rbp+0B8h]; this
0x180007276  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000727b  nop
0x18000727c  lea     rcx, [rbp+0B0h+var_110]; this
0x180007280  call    ??1Command@@QEAA@XZ; Command::~Command(void)
0x180007285  nop
0x180007286  lea     rcx, [rbp+0B0h+var_A0]
0x18000728a  jmp     loc_18000709C
0x18000728f  mov     r8, r12
0x180007292  lea     rcx, [rsp+1B0h+Src]; void *
0x180007297  call    ?GetSessionStringFromCsp@CProvisioningCommandsNode@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGPEAVCConfigServiceProvider2Impl@@@Z; CProvisioningCommandsNode::GetSessionStringFromCsp(ushort const *,CConfigServiceProvider2Impl *)
0x18000729c  nop
0x18000729d  lea     rdx, aCommands; "\\Commands"
0x1800072a4  lea     rcx, [rsp+1B0h+Src]; Src
0x1800072a9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800072ae  mov     [rsp+1B0h+var_148], rdi
0x1800072b3  mov     [rsp+1B0h+var_150], r13
0x1800072b8  mov     word ptr [rsp+1B0h+var_160], r13w
0x1800072be  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800072c2  mov     r9, rbx
0x1800072c5  xor     r8d, r8d
0x1800072c8  mov     rdx, rax
0x1800072cb  lea     rcx, [rsp+1B0h+var_160]; void *
0x1800072d0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800072d5  nop
0x1800072d6  cmp     [rbp+0B0h+var_128], 8
0x1800072db  jb      short loc_1800072EF
0x1800072dd  mov     rcx, [rsp+1B0h+Src]
0x1800072e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800072e9  nop     dword ptr [rax+rax+00h]
0x1800072ee  nop
0x1800072ef  cmp     [r14+0Ch], edi
0x1800072f3  jnz     short loc_180007315
0x1800072f5  lea     rdx, asc_180010164; "\\"
0x1800072fc  lea     rcx, [rsp+1B0h+var_160]; Src
0x180007301  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180007306  mov     rdx, [rsp+1B0h+bstrString]; void *
0x18000730b  lea     rcx, [rsp+1B0h+var_160]; Src
  ... truncated ...
```
