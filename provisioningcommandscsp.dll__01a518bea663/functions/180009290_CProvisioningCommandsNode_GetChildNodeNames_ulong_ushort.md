# CProvisioningCommandsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180009290`
- end: `0x180009816`
- name: `?GetChildNodeNames@CProvisioningCommandsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1414`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000108c`
- `0x180006a00`
- `0x180007360`
- `0x180007820`
- `0x180009290`
- `0x180009f34`
- `0x18000a010`
- `0x18000a4d4`
- `0x18000a550`
- `0x18000b1c8`
- `0x18000c5ce`
- `0x18000c600`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800093a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000948c`
- `OLEAUT32!__imp_SysAllocString` at `0x180009509`
- `OLEAUT32!__imp_SysAllocString` at `0x18000955c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800096ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18000975b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800093a9`
- `OLEAUT32!__imp_SysAllocString` at `0x18000948c`
- `OLEAUT32!__imp_SysAllocString` at `0x180009509`
- `OLEAUT32!__imp_SysAllocString` at `0x18000955c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800096ed`
- `OLEAUT32!__imp_SysAllocString` at `0x18000975b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000978f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000978f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000979f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000979f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000937a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009430`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000953c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009738`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000937a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009430`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000953c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009682`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009738`

## string_xrefs

- `0x18000932a`: `CommandLine`
- `0x1800094d8`: `CommandLine`
- `0x180009339`: `ContinueInstall`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetChildNodeNames(
        CProvisioningCommandsNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  unsigned int v6; // esi
  unsigned int v7; // r15d
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  unsigned int v14; // ebx
  _QWORD *v15; // r14
  BSTR v16; // rax
  _QWORD *v17; // rax
  const char *v18; // r9
  _QWORD *v19; // rdi
  _QWORD *j; // rbx
  wil *v21; // rcx
  const OLECHAR *v22; // rcx
  BSTR v23; // rax
  const char *v24; // r9
  int v25; // edi
  BSTR v26; // rax
  int v27; // edi
  BSTR v28; // rax
  _QWORD *v29; // rax
  const char *v30; // r9
  OLECHAR *v31; // rdi
  OLECHAR *i; // rbx
  const OLECHAR *v33; // rcx
  BSTR v34; // rax
  const char *v35; // r9
  _OWORD *v36; // rax
  BSTR v37; // rax
  __int64 result; // rax
  unsigned __int16 *v39; // [rsp+30h] [rbp-D8h] BYREF
  OLECHAR *v40; // [rsp+38h] [rbp-D0h] BYREF
  unsigned int v41; // [rsp+40h] [rbp-C8h]
  LPVOID pv; // [rsp+48h] [rbp-C0h]
  OLECHAR *v43; // [rsp+50h] [rbp-B8h] BYREF
  const wchar_t *v44; // [rsp+58h] [rbp-B0h]
  char v45[8]; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD *v46; // [rsp+68h] [rbp-A0h]
  __int64 v47; // [rsp+70h] [rbp-98h]
  unsigned __int16 **v48; // [rsp+80h] [rbp-88h]
  __int64 v49; // [rsp+88h] [rbp-80h]
  OLECHAR *psz[4]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int16 **v51; // [rsp+B8h] [rbp-50h]
  __int64 v52; // [rsp+C0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v6 = 0;
  if ( !a2 || !a3 )
  {
    v14 = -2147024809;
    goto LABEL_61;
  }
  v7 = 0;
  v41 = 0;
  pv = 0;
  *a2 = 0;
  *a3 = 0;
  v8 = *((_DWORD *)this + 11);
  if ( !v8 )
  {
    v43 = L"DeviceContext";
    v44 = L"PrimaryContext";
    v36 = CoTaskMemAlloc(0x10u);
    v15 = v36;
    if ( v36 )
    {
      *v36 = 0;
      while ( 1 )
      {
        v37 = SysAllocString((&v43)[v7]);
        v15[v7] = v37;
        if ( !v37 )
          goto LABEL_56;
        if ( ++v7 >= 2 )
          goto LABEL_55;
      }
    }
    goto LABEL_51;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    if ( (unsigned int)dword_180014230 > 4 )
    {
      LODWORD(v39) = *((_DWORD *)this + 11);
      v51 = &v39;
      v52 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, &dword_180010A5C, 0, 0);
    }
LABEL_38:
    RegistryConfig::RegistryConfig((RegistryConfig *)psz);
    v40 = 0;
    if ( *((_DWORD *)this + 11) == 5 && (unsigned int)dword_180014230 > 4 )
    {
      LODWORD(v39) = *((_DWORD *)this + 11);
      v48 = &v39;
      v49 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_180010AAD, 0, 0);
    }
    (*(void (__fastcall **)(_QWORD, __int64, OLECHAR **))(**((_QWORD **)this + 3) + 88LL))(
      *((_QWORD *)this + 3),
      1,
      &v40);
    RegistryConfig::Parse(psz, &v43, v40);
    v29 = CoTaskMemAlloc(8LL * (_QWORD)v44);
    v15 = v29;
    pv = v29;
    if ( !v29 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x4F,
        (unsigned int)"admin\\prov\\launch\\csp\\getchildnodenames.cpp",
        v30);
    memset_0(v29, 0, 8LL * (_QWORD)v44);
    v31 = v43;
    for ( i = *(OLECHAR **)v43; i != v31; i = *(OLECHAR **)i )
    {
      v33 = i + 20;
      if ( *((_QWORD *)i + 8) >= 8u )
        v33 = *(const OLECHAR **)v33;
      v34 = SysAllocString(v33);
      v15[v7] = v34;
      if ( !v34 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x55,
          (unsigned int)"admin\\prov\\launch\\csp\\getchildnodenames.cpp",
          v35);
      v41 = ++v7;
    }
    std::list<CommandSet>::~list<CommandSet>(&v43);
    RegistryConfig::~RegistryConfig((RegistryConfig *)psz);
    goto LABEL_55;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v40 = L"Default";
    v15 = CoTaskMemAlloc(8u);
    if ( v15 )
    {
      *v15 = 0;
      v27 = 0;
      while ( 1 )
      {
        v28 = SysAllocString((&v40)[v27]);
        v15[v27] = v28;
        if ( !v28 )
          goto LABEL_56;
        ++v7;
        if ( ++v27 )
          goto LABEL_55;
      }
    }
    goto LABEL_51;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v40 = L"CommandLine";
    v15 = CoTaskMemAlloc(8u);
    if ( v15 )
    {
      *v15 = 0;
      v25 = 0;
      while ( 1 )
      {
        v26 = SysAllocString((&v40)[v25]);
        v15[v25] = v26;
        if ( !v26 )
          goto LABEL_56;
        ++v7;
        if ( ++v25 )
          goto LABEL_55;
      }
    }
LABEL_51:
    v14 = -2147024882;
    goto LABEL_61;
  }
  v12 = v11 - 2;
  if ( !v12 )
    goto LABEL_38;
  v13 = v12 - 1;
  if ( v13 )
  {
    if ( v13 != 1 )
    {
      v14 = -2046820335;
      goto LABEL_61;
    }
    psz[0] = L"CommandLine";
    psz[1] = (OLECHAR *)L"ContinueInstall";
    psz[2] = (OLECHAR *)L"RestartRequired";
    psz[3] = (OLECHAR *)L"ReturnCodeRestart";
    v51 = (unsigned __int16 **)L"ReturnCodeSuccess";
    v15 = CoTaskMemAlloc(0x28u);
    if ( v15 )
    {
      *(_OWORD *)v15 = 0;
      *((_OWORD *)v15 + 1) = 0;
      v15[4] = 0;
      while ( 1 )
      {
        v16 = SysAllocString(psz[v7]);
        v15[v7] = v16;
        if ( !v16 )
          break;
        if ( ++v7 >= 5 )
          goto LABEL_55;
      }
LABEL_56:
      v14 = -2147024882;
      goto LABEL_57;
    }
    goto LABEL_51;
  }
  try
  {
    CommandSet::CommandSet((CommandSet *)v45);
    v40 = 0;
    v39 = 0;
    (*(void (__fastcall **)(_QWORD, __int64, OLECHAR **))(**((_QWORD **)this + 3) + 88LL))(
      *((_QWORD *)this + 3),
      1,
      &v40);
    (*(void (__fastcall **)(_QWORD, __int64, unsigned __int16 **))(**((_QWORD **)this + 3) + 88LL))(
      *((_QWORD *)this + 3),
      2,
      &v39);
    CProvisioningCommandsNode::FindCommandSet(v40, v39, (struct CommandSet *)v45);
    v17 = CoTaskMemAlloc(8 * v47);
    v15 = v17;
    pv = v17;
    if ( !v17 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xB9,
        (unsigned int)"admin\\prov\\launch\\csp\\getchildnodenames.cpp",
        v18);
    memset_0(v17, 0, 8 * v47);
    v19 = v46;
    for ( j = (_QWORD *)*v46; j != v19; j = (_QWORD *)*j )
    {
      v22 = (const OLECHAR *)(j + 2);
      if ( j[5] >= 8u )
        v22 = *(const OLECHAR **)v22;
      v23 = SysAllocString(v22);
      v15[v7] = v23;
      if ( !v23 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xBF,
          (unsigned int)"admin\\prov\\launch\\csp\\getchildnodenames.cpp",
          v24);
      v41 = ++v7;
    }
    CommandSet::~CommandSet((CommandSet *)v45);
  }
  catch ( ... )
  {
    LODWORD(v39) = wil::ResultFromCaughtException(v21);
    v15 = pv;
    v6 = 0;
    v14 = (unsigned int)v39;
    if ( !pv )
      goto LABEL_61;
    v7 = v41;
LABEL_57:
    if ( v7 )
    {
      do
        SysFreeString((BSTR)v15[v6++]);
      while ( v6 < v7 );
    }
    CoTaskMemFree(v15);
LABEL_61:
    result = v14;
  }
LABEL_55:
  v14 = 0;
  *a3 = (unsigned __int16 **)v15;
  *a2 = v7;
  goto LABEL_61;
}

```

## disassembly

```asm
0x180009290  push    rbx
0x180009292  push    rsi
0x180009293  push    rdi
0x180009294  push    r12
0x180009296  push    r13
0x180009298  push    r14
0x18000929a  push    r15
0x18000929c  sub     rsp, 0D0h
0x1800092a3  mov     rax, cs:__security_cookie
0x1800092aa  xor     rax, rsp
0x1800092ad  mov     [rsp+108h+var_40], rax
0x1800092b5  mov     r12, r8
0x1800092b8  mov     r13, rdx
0x1800092bb  mov     rbx, rcx
0x1800092be  xor     esi, esi
0x1800092c0  test    rdx, rdx
0x1800092c3  jz      loc_1800097A7
0x1800092c9  test    r8, r8
0x1800092cc  jz      loc_1800097A7
0x1800092d2  mov     r15d, esi
0x1800092d5  mov     [rsp+108h+var_C8], esi
0x1800092d9  mov     [rsp+108h+pv], rsi
0x1800092de  mov     [rdx], esi
0x1800092e0  mov     [r8], rsi
0x1800092e3  mov     ecx, [rcx+2Ch]
0x1800092e6  test    ecx, ecx
0x1800092e8  jz      loc_18000971B
0x1800092ee  sub     ecx, 1
0x1800092f1  jz      loc_18000957E
0x1800092f7  sub     ecx, 1
0x1800092fa  jz      loc_18000952B
0x180009300  sub     ecx, 1
0x180009303  jz      loc_1800094D8
0x180009309  sub     ecx, 2
0x18000930c  jz      loc_1800095D8
0x180009312  sub     ecx, 1
0x180009315  jz      loc_1800093CA
0x18000931b  cmp     ecx, 1
0x18000931e  jz      short loc_18000932A
0x180009320  mov     ebx, 86000011h
0x180009325  jmp     loc_1800097AC
0x18000932a  lea     rax, aCommandline; "CommandLine"
0x180009331  mov     [rsp+108h+psz], rax
0x180009339  lea     rax, aContinueinstal; "ContinueInstall"
0x180009340  mov     [rsp+108h+var_68], rax
0x180009348  lea     rax, aRestartrequire; "RestartRequired"
0x18000934f  mov     [rsp+108h+var_60], rax
0x180009357  lea     rax, aReturncoderest; "ReturnCodeRestart"
0x18000935e  mov     [rsp+108h+var_58], rax
0x180009366  lea     rax, aReturncodesucc; "ReturnCodeSuccess"
0x18000936d  mov     [rsp+108h+var_50], rax
0x180009375  mov     ecx, 28h ; '('; cb
0x18000937a  call    cs:__imp_CoTaskMemAlloc
0x180009380  mov     r14, rax
0x180009383  test    rax, rax
0x180009386  jz      loc_180009746
0x18000938c  xorps   xmm0, xmm0
0x18000938f  xor     eax, eax
0x180009391  movups  xmmword ptr [r14], xmm0
0x180009395  movups  xmmword ptr [r14+10h], xmm0
0x18000939a  mov     [r14+20h], rax
0x18000939e  mov     ebx, r15d
0x1800093a1  mov     rcx, [rsp+rbx*8+108h+psz]; psz
0x1800093a9  call    cs:__imp_SysAllocString
0x1800093af  mov     [r14+rbx*8], rax
0x1800093b3  test    rax, rax
0x1800093b6  jz      loc_18000977F
0x1800093bc  inc     r15d
0x1800093bf  cmp     r15d, 5
0x1800093c3  jb      short loc_18000939E
0x1800093c5  jmp     loc_180009773
0x1800093ca  lea     rcx, [rsp+108h+var_A8]; this
0x1800093cf  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x1800093d4  nop
0x1800093d5  mov     [rsp+108h+var_D0], rsi
0x1800093da  mov     [rsp+108h+var_D8], rsi
0x1800093df  mov     rcx, [rbx+18h]
0x1800093e3  mov     rax, [rcx]
0x1800093e6  lea     r8, [rsp+108h+var_D0]
0x1800093eb  mov     edx, 1
0x1800093f0  mov     rax, [rax+58h]
0x1800093f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f9  mov     rcx, [rbx+18h]
0x1800093fd  mov     rax, [rcx]
0x180009400  lea     r8, [rsp+108h+var_D8]
0x180009405  mov     edx, 2
0x18000940a  mov     rax, [rax+58h]
0x18000940e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009413  lea     r8, [rsp+108h+var_A8]; struct CommandSet *
0x180009418  mov     rdx, [rsp+108h+var_D8]; unsigned __int16 *
0x18000941d  mov     rcx, [rsp+108h+var_D0]; unsigned __int16 *
0x180009422  call    ?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z; CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)
0x180009427  mov     rcx, [rsp+108h+var_98]
0x18000942c  shl     rcx, 3; cb
0x180009430  call    cs:__imp_CoTaskMemAlloc
0x180009436  mov     r14, rax
0x180009439  mov     [rsp+108h+pv], rax
0x18000943e  mov     rcx, [rsp+108h]; this
0x180009446  test    rax, rax
0x180009449  jz      loc_1800097D1
0x18000944f  mov     r8, [rsp+108h+var_98]
0x180009454  shl     r8, 3; Size
0x180009458  xor     edx, edx; Val
0x18000945a  mov     rcx, r14; void *
0x18000945d  call    memset_0
0x180009462  mov     rdi, [rsp+108h+var_A0]
0x180009467  mov     rbx, [rdi]
0x18000946a  cmp     rbx, rdi
0x18000946d  jnz     short loc_18000947E
0x18000946f  lea     rcx, [rsp+108h+var_A8]; this
0x180009474  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x180009479  jmp     loc_1800096DA
0x18000947e  lea     rcx, [rbx+10h]
0x180009482  cmp     qword ptr [rbx+28h], 8
0x180009487  jb      short loc_18000948C
0x180009489  mov     rcx, [rcx]; psz
0x18000948c  call    cs:__imp_SysAllocString
0x180009492  mov     rdx, rax
0x180009495  mov     eax, r15d
0x180009498  mov     [r14+rax*8], rdx
0x18000949c  mov     rcx, [rsp+108h]; this
0x1800094a4  test    rdx, rdx
0x1800094a7  jz      loc_1800097E2
0x1800094ad  inc     r15d
0x1800094b0  mov     [rsp+108h+var_C8], r15d
0x1800094b5  mov     rbx, [rbx]
0x1800094b8  jmp     short loc_18000946A
0x1800094ba  mov     r14, [rsp+108h+pv]
0x1800094bf  xor     esi, esi
0x1800094c1  mov     ebx, dword ptr [rsp+108h+var_D8]
0x1800094c5  test    r14, r14
0x1800094c8  jz      loc_1800097AC
0x1800094ce  mov     r15d, [rsp+108h+var_C8]
0x1800094d3  jmp     loc_180009784
0x1800094d8  lea     rax, aCommandline; "CommandLine"
0x1800094df  mov     [rsp+108h+var_D0], rax
0x1800094e4  mov     ecx, 8; cb
0x1800094e9  call    cs:__imp_CoTaskMemAlloc
0x1800094ef  mov     r14, rax
0x1800094f2  test    rax, rax
0x1800094f5  jz      loc_180009746
0x1800094fb  xor     eax, eax
0x1800094fd  mov     [r14], rax
0x180009500  mov     edi, esi
0x180009502  mov     ebx, edi
0x180009504  mov     rcx, [rsp+rbx*8+108h+var_D0]; psz
0x180009509  call    cs:__imp_SysAllocString
0x18000950f  mov     [r14+rbx*8], rax
0x180009513  test    rax, rax
0x180009516  jz      loc_18000977F
0x18000951c  inc     r15d
0x18000951f  inc     edi
0x180009521  cmp     edi, 1
0x180009524  jb      short loc_180009502
0x180009526  jmp     loc_180009773
0x18000952b  lea     rax, aDefault; "Default"
0x180009532  mov     [rsp+108h+var_D0], rax
0x180009537  mov     ecx, 8; cb
0x18000953c  call    cs:__imp_CoTaskMemAlloc
0x180009542  mov     r14, rax
0x180009545  test    rax, rax
0x180009548  jz      loc_180009746
0x18000954e  xor     eax, eax
0x180009550  mov     [r14], rax
0x180009553  mov     edi, esi
0x180009555  mov     ebx, edi
0x180009557  mov     rcx, [rsp+rbx*8+108h+var_D0]; psz
0x18000955c  call    cs:__imp_SysAllocString
0x180009562  mov     [r14+rbx*8], rax
0x180009566  test    rax, rax
0x180009569  jz      loc_18000977F
0x18000956f  inc     r15d
0x180009572  inc     edi
0x180009574  cmp     edi, 1
0x180009577  jb      short loc_180009555
0x180009579  jmp     loc_180009773
0x18000957e  mov     eax, cs:dword_180014230
0x180009584  cmp     eax, 4
0x180009587  jbe     short loc_1800095D8
0x180009589  mov     eax, [rbx+2Ch]
0x18000958c  mov     dword ptr [rsp+108h+var_D8], eax
0x180009590  lea     rax, [rsp+108h+var_D8]
0x180009595  mov     [rsp+108h+var_50], rax
0x18000959d  mov     [rsp+108h+var_48], 4
0x1800095a9  lea     rax, [rsp+108h+psz]
0x1800095b1  mov     [rsp+108h+var_E0], rax
0x1800095b6  mov     [rsp+108h+var_E8], 3
0x1800095be  xor     r9d, r9d
0x1800095c1  xor     r8d, r8d
0x1800095c4  lea     rdx, dword_180010A5C
0x1800095cb  lea     rcx, dword_180014230
0x1800095d2  call    _tlgWriteTransfer_EventWriteTransfer
0x1800095d7  nop
0x1800095d8  lea     rcx, [rsp+108h+psz]; this
0x1800095e0  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x1800095e5  nop
0x1800095e6  mov     [rsp+108h+var_D0], rsi
0x1800095eb  cmp     dword ptr [rbx+2Ch], 5
0x1800095ef  jnz     short loc_180009647
0x1800095f1  mov     eax, cs:dword_180014230
0x1800095f7  cmp     eax, 4
0x1800095fa  jbe     short loc_180009647
0x1800095fc  mov     eax, [rbx+2Ch]
0x1800095ff  mov     dword ptr [rsp+108h+var_D8], eax
0x180009603  lea     rax, [rsp+108h+var_D8]
0x180009608  mov     [rsp+108h+var_88], rax
0x180009610  mov     [rsp+108h+var_80], 4
0x18000961c  lea     rax, [rsp+108h+var_A8]
0x180009621  mov     [rsp+108h+var_E0], rax
0x180009626  mov     [rsp+108h+var_E8], 3
0x18000962e  xor     r9d, r9d
0x180009631  xor     r8d, r8d
0x180009634  lea     rdx, byte_180010AAD
0x18000963b  lea     rcx, dword_180014230
0x180009642  call    _tlgWriteTransfer_EventWriteTransfer
0x180009647  mov     rcx, [rbx+18h]
0x18000964b  mov     rax, [rcx]
0x18000964e  lea     r8, [rsp+108h+var_D0]
0x180009653  mov     edx, 1
0x180009658  mov     rax, [rax+58h]
0x18000965c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009661  mov     r8, [rsp+108h+var_D0]
0x180009666  lea     rdx, [rsp+108h+var_B8]
0x18000966b  lea     rcx, [rsp+108h+psz]
0x180009673  call    ?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z; RegistryConfig::Parse(ushort const *)
0x180009678  nop
0x180009679  mov     rcx, [rsp+108h+var_B0]
0x18000967e  shl     rcx, 3; cb
0x180009682  call    cs:__imp_CoTaskMemAlloc
0x180009688  mov     r14, rax
0x18000968b  mov     [rsp+108h+pv], rax
0x180009690  mov     rcx, [rsp+108h]; this
0x180009698  test    rax, rax
0x18000969b  jz      loc_1800097F4
0x1800096a1  mov     r8, [rsp+108h+var_B0]
0x1800096a6  shl     r8, 3; Size
0x1800096aa  xor     edx, edx; Val
0x1800096ac  mov     rcx, r14; void *
0x1800096af  call    memset_0
0x1800096b4  mov     rdi, [rsp+108h+var_B8]
0x1800096b9  mov     rbx, [rdi]
0x1800096bc  cmp     rbx, rdi
0x1800096bf  jnz     short loc_1800096DF
0x1800096c1  lea     rcx, [rsp+108h+var_B8]; void *
0x1800096c6  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x1800096cb  nop
0x1800096cc  lea     rcx, [rsp+108h+psz]; this
0x1800096d4  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x1800096d9  nop
0x1800096da  jmp     loc_180009773
0x1800096df  lea     rcx, [rbx+28h]
0x1800096e3  cmp     qword ptr [rbx+40h], 8
0x1800096e8  jb      short loc_1800096ED
0x1800096ea  mov     rcx, [rcx]; psz
0x1800096ed  call    cs:__imp_SysAllocString
0x1800096f3  mov     rdx, rax
0x1800096f6  mov     eax, r15d
0x1800096f9  mov     [r14+rax*8], rdx
0x1800096fd  mov     rcx, [rsp+108h]; this
0x180009705  test    rdx, rdx
0x180009708  jz      loc_180009803
0x18000970e  inc     r15d
0x180009711  mov     [rsp+108h+var_C8], r15d
0x180009716  mov     rbx, [rbx]
0x180009719  jmp     short loc_1800096BC
0x18000971b  lea     rax, aDevicecontext; "DeviceContext"
0x180009722  mov     [rsp+108h+var_B8], rax
0x180009727  lea     rax, aPrimarycontext; "PrimaryContext"
0x18000972e  mov     [rsp+108h+var_B0], rax
0x180009733  mov     ecx, 10h; cb
0x180009738  call    cs:__imp_CoTaskMemAlloc
0x18000973e  mov     r14, rax
0x180009741  test    rax, rax
0x180009744  jnz     short loc_18000974D
0x180009746  mov     ebx, 8007000Eh
0x18000974b  jmp     short loc_1800097AC
0x18000974d  xorps   xmm0, xmm0
0x180009750  movups  xmmword ptr [rax], xmm0
0x180009753  mov     ebx, r15d
0x180009756  mov     rcx, [rsp+rbx*8+108h+var_B8]; psz
0x18000975b  call    cs:__imp_SysAllocString
0x180009761  mov     [r14+rbx*8], rax
0x180009765  test    rax, rax
0x180009768  jz      short loc_18000977F
0x18000976a  inc     r15d
0x18000976d  cmp     r15d, 2
0x180009771  jb      short loc_180009753
0x180009773  mov     ebx, esi
0x180009775  mov     [r12], r14
0x180009779  mov     [r13+0], r15d
0x18000977d  jmp     short loc_1800097AC
0x18000977f  mov     ebx, 8007000Eh
0x180009784  test    r15d, r15d
0x180009787  jz      short loc_18000979C
0x180009789  mov     ecx, esi
0x18000978b  mov     rcx, [r14+rcx*8]; bstrString
0x18000978f  call    cs:__imp_SysFreeString
0x180009795  inc     esi
0x180009797  cmp     esi, r15d
0x18000979a  jb      short loc_180009789
  ... truncated ...
```
