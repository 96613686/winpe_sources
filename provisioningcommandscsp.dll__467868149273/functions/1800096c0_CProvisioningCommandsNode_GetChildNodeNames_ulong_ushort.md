# CProvisioningCommandsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x1800096c0`
- end: `0x180009c9b`
- name: `?GetChildNodeNames@CProvisioningCommandsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1499`
- prototype: `__int64 __fastcall(CProvisioningCommandsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001090`
- `0x180006d20`
- `0x1800076ac`
- `0x180007ba4`
- `0x1800096c0`
- `0x18000a418`
- `0x18000a50c`
- `0x18000aa28`
- `0x18000aab0`
- `0x18000b81c`
- `0x18000cc8e`
- `0x18000ccc0`
- `0x18000e010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800097df`
- `OLEAUT32!__imp_SysAllocString` at `0x1800098ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180009957`
- `OLEAUT32!__imp_SysAllocString` at `0x1800099b6`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b53`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bcd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800097df`
- `OLEAUT32!__imp_SysAllocString` at `0x1800098ce`
- `OLEAUT32!__imp_SysAllocString` at `0x180009957`
- `OLEAUT32!__imp_SysAllocString` at `0x1800099b6`
- `OLEAUT32!__imp_SysAllocString` at `0x180009b53`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bcd`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c07`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800097aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000986c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800097aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000986c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009931`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009990`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ae2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009ba4`

## string_xrefs

- `0x18000975a`: `CommandLine`
- `0x180009920`: `CommandLine`
- `0x180009769`: `ContinueInstall`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, &dword_180010A5C, 0, 0, 3, psz, (_DWORD)v39);
    }
LABEL_38:
    RegistryConfig::RegistryConfig((RegistryConfig *)psz);
    v40 = 0;
    if ( *((_DWORD *)this + 11) == 5 && (unsigned int)dword_180014230 > 4 )
    {
      LODWORD(v39) = *((_DWORD *)this + 11);
      v48 = &v39;
      v49 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_180014230, byte_180010AAD, 0, 0, 3, v45, (_DWORD)v39);
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
0x1800096c0  push    rbx
0x1800096c2  push    rsi
0x1800096c3  push    rdi
0x1800096c4  push    r12
0x1800096c6  push    r13
0x1800096c8  push    r14
0x1800096ca  push    r15
0x1800096cc  sub     rsp, 0D0h
0x1800096d3  mov     rax, cs:__security_cookie
0x1800096da  xor     rax, rsp
0x1800096dd  mov     [rsp+108h+var_40], rax
0x1800096e5  mov     r12, r8
0x1800096e8  mov     r13, rdx
0x1800096eb  mov     rbx, rcx
0x1800096ee  xor     esi, esi
0x1800096f0  test    rdx, rdx
0x1800096f3  jz      loc_180009C2B
0x1800096f9  test    r8, r8
0x1800096fc  jz      loc_180009C2B
0x180009702  mov     r15d, esi
0x180009705  mov     [rsp+108h+var_C8], esi
0x180009709  mov     [rsp+108h+pv], rsi
0x18000970e  mov     [rdx], esi
0x180009710  mov     [r8], rsi
0x180009713  mov     ecx, [rcx+2Ch]
0x180009716  test    ecx, ecx
0x180009718  jz      loc_180009B87
0x18000971e  sub     ecx, 1
0x180009721  jz      loc_1800099DE
0x180009727  sub     ecx, 1
0x18000972a  jz      loc_18000997F
0x180009730  sub     ecx, 1
0x180009733  jz      loc_180009920
0x180009739  sub     ecx, 2
0x18000973c  jz      loc_180009A38
0x180009742  sub     ecx, 1
0x180009745  jz      loc_180009806
0x18000974b  cmp     ecx, 1
0x18000974e  jz      short loc_18000975A
0x180009750  mov     ebx, 86000011h
0x180009755  jmp     loc_180009C30
0x18000975a  lea     rax, aCommandline; "CommandLine"
0x180009761  mov     [rsp+108h+psz], rax
0x180009769  lea     rax, aContinueinstal; "ContinueInstall"
0x180009770  mov     [rsp+108h+var_68], rax
0x180009778  lea     rax, aRestartrequire; "RestartRequired"
0x18000977f  mov     [rsp+108h+var_60], rax
0x180009787  lea     rax, aReturncoderest; "ReturnCodeRestart"
0x18000978e  mov     [rsp+108h+var_58], rax
0x180009796  lea     rax, aReturncodesucc; "ReturnCodeSuccess"
0x18000979d  mov     [rsp+108h+var_50], rax
0x1800097a5  mov     ecx, 28h ; '('; cb
0x1800097aa  call    cs:__imp_CoTaskMemAlloc
0x1800097b1  nop     dword ptr [rax+rax+00h]
0x1800097b6  mov     r14, rax
0x1800097b9  test    rax, rax
0x1800097bc  jz      loc_180009BB8
0x1800097c2  xorps   xmm0, xmm0
0x1800097c5  xor     eax, eax
0x1800097c7  movups  xmmword ptr [r14], xmm0
0x1800097cb  movups  xmmword ptr [r14+10h], xmm0
0x1800097d0  mov     [r14+20h], rax
0x1800097d4  mov     ebx, r15d
0x1800097d7  mov     rcx, [rsp+rbx*8+108h+psz]; psz
0x1800097df  call    cs:__imp_SysAllocString
0x1800097e6  nop     dword ptr [rax+rax+00h]
0x1800097eb  mov     [r14+rbx*8], rax
0x1800097ef  test    rax, rax
0x1800097f2  jz      loc_180009BF7
0x1800097f8  inc     r15d
0x1800097fb  cmp     r15d, 5
0x1800097ff  jb      short loc_1800097D4
0x180009801  jmp     loc_180009BEB
0x180009806  lea     rcx, [rsp+108h+var_A8]; this
0x18000980b  call    ??0CommandSet@@QEAA@XZ; CommandSet::CommandSet(void)
0x180009810  nop
0x180009811  mov     [rsp+108h+var_D0], rsi
0x180009816  mov     [rsp+108h+var_D8], rsi
0x18000981b  mov     rcx, [rbx+18h]
0x18000981f  mov     rax, [rcx]
0x180009822  lea     r8, [rsp+108h+var_D0]
0x180009827  mov     edx, 1
0x18000982c  mov     rax, [rax+58h]
0x180009830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009835  mov     rcx, [rbx+18h]
0x180009839  mov     rax, [rcx]
0x18000983c  lea     r8, [rsp+108h+var_D8]
0x180009841  mov     edx, 2
0x180009846  mov     rax, [rax+58h]
0x18000984a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000984f  lea     r8, [rsp+108h+var_A8]; struct CommandSet *
0x180009854  mov     rdx, [rsp+108h+var_D8]; unsigned __int16 *
0x180009859  mov     rcx, [rsp+108h+var_D0]; unsigned __int16 *
0x18000985e  call    ?FindCommandSet@CProvisioningCommandsNode@@CAJPEBG0PEAUCommandSet@@@Z; CProvisioningCommandsNode::FindCommandSet(ushort const *,ushort const *,CommandSet *)
0x180009863  mov     rcx, [rsp+108h+var_98]
0x180009868  shl     rcx, 3; cb
0x18000986c  call    cs:__imp_CoTaskMemAlloc
0x180009873  nop     dword ptr [rax+rax+00h]
0x180009878  mov     r14, rax
0x18000987b  mov     [rsp+108h+pv], rax
0x180009880  mov     rcx, [rsp+108h]; this
0x180009888  test    rax, rax
0x18000988b  jz      loc_180009C56
0x180009891  mov     r8, [rsp+108h+var_98]
0x180009896  shl     r8, 3; Size
0x18000989a  xor     edx, edx; Val
0x18000989c  mov     rcx, r14; void *
0x18000989f  call    memset_0
0x1800098a4  mov     rdi, [rsp+108h+var_A0]
0x1800098a9  mov     rbx, [rdi]
0x1800098ac  cmp     rbx, rdi
0x1800098af  jnz     short loc_1800098C0
0x1800098b1  lea     rcx, [rsp+108h+var_A8]; this
0x1800098b6  call    ??1CommandSet@@QEAA@XZ; CommandSet::~CommandSet(void)
0x1800098bb  jmp     loc_180009B40
0x1800098c0  lea     rcx, [rbx+10h]
0x1800098c4  cmp     qword ptr [rbx+28h], 8
0x1800098c9  jb      short loc_1800098CE
0x1800098cb  mov     rcx, [rcx]; psz
0x1800098ce  call    cs:__imp_SysAllocString
0x1800098d5  nop     dword ptr [rax+rax+00h]
0x1800098da  mov     rdx, rax
0x1800098dd  mov     eax, r15d
0x1800098e0  mov     [r14+rax*8], rdx
0x1800098e4  mov     rcx, [rsp+108h]; this
0x1800098ec  test    rdx, rdx
0x1800098ef  jz      loc_180009C67
0x1800098f5  inc     r15d
0x1800098f8  mov     [rsp+108h+var_C8], r15d
0x1800098fd  mov     rbx, [rbx]
0x180009900  jmp     short loc_1800098AC
0x180009902  mov     r14, [rsp+108h+pv]
0x180009907  xor     esi, esi
0x180009909  mov     ebx, dword ptr [rsp+108h+var_D8]
0x18000990d  test    r14, r14
0x180009910  jz      loc_180009C30
0x180009916  mov     r15d, [rsp+108h+var_C8]
0x18000991b  jmp     loc_180009BFC
0x180009920  lea     rax, aCommandline; "CommandLine"
0x180009927  mov     [rsp+108h+var_D0], rax
0x18000992c  mov     ecx, 8; cb
0x180009931  call    cs:__imp_CoTaskMemAlloc
0x180009938  nop     dword ptr [rax+rax+00h]
0x18000993d  mov     r14, rax
0x180009940  test    rax, rax
0x180009943  jz      loc_180009BB8
0x180009949  xor     eax, eax
0x18000994b  mov     [r14], rax
0x18000994e  mov     edi, esi
0x180009950  mov     ebx, edi
0x180009952  mov     rcx, [rsp+rbx*8+108h+var_D0]; psz
0x180009957  call    cs:__imp_SysAllocString
0x18000995e  nop     dword ptr [rax+rax+00h]
0x180009963  mov     [r14+rbx*8], rax
0x180009967  test    rax, rax
0x18000996a  jz      loc_180009BF7
0x180009970  inc     r15d
0x180009973  inc     edi
0x180009975  cmp     edi, 1
0x180009978  jb      short loc_180009950
0x18000997a  jmp     loc_180009BEB
0x18000997f  lea     rax, aDefault; "Default"
0x180009986  mov     [rsp+108h+var_D0], rax
0x18000998b  mov     ecx, 8; cb
0x180009990  call    cs:__imp_CoTaskMemAlloc
0x180009997  nop     dword ptr [rax+rax+00h]
0x18000999c  mov     r14, rax
0x18000999f  test    rax, rax
0x1800099a2  jz      loc_180009BB8
0x1800099a8  xor     eax, eax
0x1800099aa  mov     [r14], rax
0x1800099ad  mov     edi, esi
0x1800099af  mov     ebx, edi
0x1800099b1  mov     rcx, [rsp+rbx*8+108h+var_D0]; psz
0x1800099b6  call    cs:__imp_SysAllocString
0x1800099bd  nop     dword ptr [rax+rax+00h]
0x1800099c2  mov     [r14+rbx*8], rax
0x1800099c6  test    rax, rax
0x1800099c9  jz      loc_180009BF7
0x1800099cf  inc     r15d
0x1800099d2  inc     edi
0x1800099d4  cmp     edi, 1
0x1800099d7  jb      short loc_1800099AF
0x1800099d9  jmp     loc_180009BEB
0x1800099de  mov     eax, cs:dword_180014230
0x1800099e4  cmp     eax, 4
0x1800099e7  jbe     short loc_180009A38
0x1800099e9  mov     eax, [rbx+2Ch]
0x1800099ec  mov     dword ptr [rsp+108h+var_D8], eax
0x1800099f0  lea     rax, [rsp+108h+var_D8]
0x1800099f5  mov     [rsp+108h+var_50], rax
0x1800099fd  mov     [rsp+108h+var_48], 4
0x180009a09  lea     rax, [rsp+108h+psz]
0x180009a11  mov     [rsp+108h+var_E0], rax
0x180009a16  mov     [rsp+108h+var_E8], 3
0x180009a1e  xor     r9d, r9d
0x180009a21  xor     r8d, r8d
0x180009a24  lea     rdx, dword_180010A5C
0x180009a2b  lea     rcx, dword_180014230
0x180009a32  call    _tlgWriteTransfer_EventWriteTransfer
0x180009a37  nop
0x180009a38  lea     rcx, [rsp+108h+psz]; this
0x180009a40  call    ??0RegistryConfig@@QEAA@XZ; RegistryConfig::RegistryConfig(void)
0x180009a45  nop
0x180009a46  mov     [rsp+108h+var_D0], rsi
0x180009a4b  cmp     dword ptr [rbx+2Ch], 5
0x180009a4f  jnz     short loc_180009AA7
0x180009a51  mov     eax, cs:dword_180014230
0x180009a57  cmp     eax, 4
0x180009a5a  jbe     short loc_180009AA7
0x180009a5c  mov     eax, [rbx+2Ch]
0x180009a5f  mov     dword ptr [rsp+108h+var_D8], eax
0x180009a63  lea     rax, [rsp+108h+var_D8]
0x180009a68  mov     [rsp+108h+var_88], rax
0x180009a70  mov     [rsp+108h+var_80], 4
0x180009a7c  lea     rax, [rsp+108h+var_A8]
0x180009a81  mov     [rsp+108h+var_E0], rax
0x180009a86  mov     [rsp+108h+var_E8], 3
0x180009a8e  xor     r9d, r9d
0x180009a91  xor     r8d, r8d
0x180009a94  lea     rdx, byte_180010AAD
0x180009a9b  lea     rcx, dword_180014230
0x180009aa2  call    _tlgWriteTransfer_EventWriteTransfer
0x180009aa7  mov     rcx, [rbx+18h]
0x180009aab  mov     rax, [rcx]
0x180009aae  lea     r8, [rsp+108h+var_D0]
0x180009ab3  mov     edx, 1
0x180009ab8  mov     rax, [rax+58h]
0x180009abc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ac1  mov     r8, [rsp+108h+var_D0]
0x180009ac6  lea     rdx, [rsp+108h+var_B8]
0x180009acb  lea     rcx, [rsp+108h+psz]
0x180009ad3  call    ?Parse@RegistryConfig@@QEAA?AV?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@PEBG@Z; RegistryConfig::Parse(ushort const *)
0x180009ad8  nop
0x180009ad9  mov     rcx, [rsp+108h+var_B0]
0x180009ade  shl     rcx, 3; cb
0x180009ae2  call    cs:__imp_CoTaskMemAlloc
0x180009ae9  nop     dword ptr [rax+rax+00h]
0x180009aee  mov     r14, rax
0x180009af1  mov     [rsp+108h+pv], rax
0x180009af6  mov     rcx, [rsp+108h]; this
0x180009afe  test    rax, rax
0x180009b01  jz      loc_180009C79
0x180009b07  mov     r8, [rsp+108h+var_B0]
0x180009b0c  shl     r8, 3; Size
0x180009b10  xor     edx, edx; Val
0x180009b12  mov     rcx, r14; void *
0x180009b15  call    memset_0
0x180009b1a  mov     rdi, [rsp+108h+var_B8]
0x180009b1f  mov     rbx, [rdi]
0x180009b22  cmp     rbx, rdi
0x180009b25  jnz     short loc_180009B45
0x180009b27  lea     rcx, [rsp+108h+var_B8]; void *
0x180009b2c  call    ??1?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ; std::list<CommandSet>::~list<CommandSet>(void)
0x180009b31  nop
0x180009b32  lea     rcx, [rsp+108h+psz]; this
0x180009b3a  call    ??1RegistryConfig@@QEAA@XZ; RegistryConfig::~RegistryConfig(void)
0x180009b3f  nop
0x180009b40  jmp     loc_180009BEB
0x180009b45  lea     rcx, [rbx+28h]
0x180009b49  cmp     qword ptr [rbx+40h], 8
0x180009b4e  jb      short loc_180009B53
0x180009b50  mov     rcx, [rcx]; psz
0x180009b53  call    cs:__imp_SysAllocString
0x180009b5a  nop     dword ptr [rax+rax+00h]
0x180009b5f  mov     rdx, rax
0x180009b62  mov     eax, r15d
0x180009b65  mov     [r14+rax*8], rdx
0x180009b69  mov     rcx, [rsp+108h]; this
0x180009b71  test    rdx, rdx
0x180009b74  jz      loc_180009C88
0x180009b7a  inc     r15d
0x180009b7d  mov     [rsp+108h+var_C8], r15d
0x180009b82  mov     rbx, [rbx]
0x180009b85  jmp     short loc_180009B22
0x180009b87  lea     rax, aDevicecontext; "DeviceContext"
0x180009b8e  mov     [rsp+108h+var_B8], rax
0x180009b93  lea     rax, aPrimarycontext; "PrimaryContext"
0x180009b9a  mov     [rsp+108h+var_B0], rax
0x180009b9f  mov     ecx, 10h; cb
0x180009ba4  call    cs:__imp_CoTaskMemAlloc
0x180009bab  nop     dword ptr [rax+rax+00h]
0x180009bb0  mov     r14, rax
0x180009bb3  test    rax, rax
0x180009bb6  jnz     short loc_180009BBF
0x180009bb8  mov     ebx, 8007000Eh
0x180009bbd  jmp     short loc_180009C30
0x180009bbf  xorps   xmm0, xmm0
0x180009bc2  movups  xmmword ptr [rax], xmm0
0x180009bc5  mov     ebx, r15d
0x180009bc8  mov     rcx, [rsp+rbx*8+108h+var_B8]; psz
0x180009bcd  call    cs:__imp_SysAllocString
0x180009bd4  nop     dword ptr [rax+rax+00h]
0x180009bd9  mov     [r14+rbx*8], rax
0x180009bdd  test    rax, rax
0x180009be0  jz      short loc_180009BF7
0x180009be2  inc     r15d
0x180009be5  cmp     r15d, 2
0x180009be9  jb      short loc_180009BC5
0x180009beb  mov     ebx, esi
  ... truncated ...
```
