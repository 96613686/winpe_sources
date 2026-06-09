# CIISApplicationPools::CreateApplicationPools(IUnknown *,_GUID const &,void * *)

- ea: `0x18000828c`
- end: `0x1800084c3`
- name: `?CreateApplicationPools@CIISApplicationPools@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x1800085c0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x180007fd0`
- `0x1800080d0`
- `0x18000828c`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180008409`
- `OLEAUT32!__imp_SysFreeString` at `0x180008446`
- `OLEAUT32!__imp_SysFreeString` at `0x180008409`
- `OLEAUT32!__imp_SysFreeString` at `0x180008446`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180008374`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800083bd`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800083cf`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180008374`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800083bd`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800083cf`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008413`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008424`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008455`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000846b`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008413`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008424`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180008455`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000846b`

## pseudocode

```c
__int64 __fastcall CIISApplicationPools::CreateApplicationPools(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int ApplicationPoolsObject; // eax
  void *v8; // rsi
  int inited; // ebx
  LPWSTR *v10; // rax
  LPWSTR v11; // rax
  __int64 v12; // r8
  unsigned __int16 *v13; // rbx
  LPWSTR v14; // rax
  LPWSTR v15; // rax
  OLECHAR *v16; // rcx
  unsigned __int16 *v18; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v19; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v20; // [rsp+34h] [rbp-2Ch] BYREF
  LPCWSTR v21[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v22; // [rsp+48h] [rbp-18h]
  __int64 v23; // [rsp+58h] [rbp-8h]
  LPCWSTR pStr; // [rsp+98h] [rbp+38h] BYREF
  void *Block; // [rsp+A8h] [rbp+48h] BYREF

  pStr = a2;
  CCredentials::Initialize((CCredentials *)&v18, 0, 0, 0);
  Block = 0;
  pStr = 0;
  v23 = 0;
  v5 = 0;
  *(_OWORD *)v21 = 0;
  v6 = 0;
  v22 = 0;
  ApplicationPoolsObject = CIISApplicationPools::AllocateApplicationPoolsObject(
                             a1,
                             (struct CCredentials *)&v18,
                             (struct CIISApplicationPools **)&Block);
  v8 = Block;
  inited = ApplicationPoolsObject;
  if ( ApplicationPoolsObject < 0 )
    goto LABEL_19;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)Block + 7) + 80LL))(
             *((_QWORD *)Block + 7),
             &pStr);
  if ( inited < 0 )
    goto LABEL_19;
  v10 = (LPWSTR *)operator new(0x20u);
  v5 = v10;
  if ( !v10 )
  {
    v5 = 0;
LABEL_18:
    inited = -2147024882;
    goto LABEL_19;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  inited = CLexer::Initialize((CLexer *)v10, (unsigned __int16 *)pStr);
  if ( inited < 0 )
    goto LABEL_19;
  inited = ADsObject((struct CLexer *)v5, (struct _objectinfo *)v21);
  if ( inited < 0 )
    goto LABEL_19;
  v11 = AllocADsStr(pStr);
  v6 = v11;
  if ( !v11 )
    goto LABEL_18;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  *v11 = 0;
  inited = BuildIISPathFromADsPath((struct _objectinfo *)v21, v11, v12 + 1);
  if ( inited < 0 )
    goto LABEL_19;
  v13 = (unsigned __int16 *)v21[1];
  if ( v21[1] )
  {
    v14 = AllocADsStr(v21[1]);
    *((_QWORD *)v8 + 8) = v14;
    if ( !v14 )
      goto LABEL_18;
  }
  v15 = AllocADsStr(v6);
  *((_QWORD *)v8 + 9) = v15;
  if ( !v15 )
    goto LABEL_18;
  inited = InitServerInfo(v13, (struct IMSAdminBaseW **)v8 + 15);
  if ( inited >= 0 )
  {
    v16 = (OLECHAR *)pStr;
    *a3 = (void *)(((unsigned __int64)v8 + 32) & -(__int64)(v8 != 0));
    if ( v16 )
      SysFreeString(v16);
    FreeADsStr(v5[1]);
    operator delete(v5);
    FreeADsStr(v6);
    FreeObjectInfo((struct _objectinfo *)v21);
    goto LABEL_27;
  }
LABEL_19:
  if ( pStr )
    SysFreeString((BSTR)pStr);
  if ( v5 )
  {
    FreeADsStr(v5[1]);
    operator delete(v5);
  }
  if ( v6 )
    FreeADsStr(v6);
  FreeObjectInfo((struct _objectinfo *)v21);
  *a3 = 0;
  if ( v8 )
  {
    CIISApplicationPools::~CIISApplicationPools((CIISApplicationPools *)v8);
    operator delete(v8);
  }
LABEL_27:
  CCredentials::FreeUserName(&v18);
  CCredentials::FreePassword(&v19, &v20);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000828c  mov     [rsp-28h+arg_0], rbx
0x180008291  mov     [rsp-28h+arg_10], rsi
0x180008296  mov     [rsp-28h+pStr], rdx
0x18000829b  push    rbp
0x18000829c  push    rdi
0x18000829d  push    r12
0x18000829f  push    r14
0x1800082a1  push    r15
0x1800082a3  mov     rbp, rsp
0x1800082a6  sub     rsp, 60h
0x1800082aa  mov     r15, r8
0x1800082ad  mov     rbx, rcx
0x1800082b0  xor     r8d, r8d; unsigned __int16 *
0x1800082b3  lea     rcx, [rbp+var_40]; this
0x1800082b7  xor     r9d, r9d; unsigned int
0x1800082ba  xor     edx, edx; pStr
0x1800082bc  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x1800082c1  xor     r12d, r12d
0x1800082c4  lea     r8, [rbp+Block]; struct CIISApplicationPools **
0x1800082c8  xorps   xmm0, xmm0
0x1800082cb  mov     [rbp+Block], r12
0x1800082cf  xor     eax, eax
0x1800082d1  mov     [rbp+pStr], r12
0x1800082d5  lea     rdx, [rbp+var_40]; struct CCredentials *
0x1800082d9  mov     [rbp+var_8], rax
0x1800082dd  mov     rcx, rbx; struct IUnknown *
0x1800082e0  mov     edi, r12d
0x1800082e3  movups  xmmword ptr [rbp+var_28], xmm0
0x1800082e7  mov     r14d, r12d
0x1800082ea  movups  [rbp+var_18], xmm0
0x1800082ee  call    ?AllocateApplicationPoolsObject@CIISApplicationPools@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISApplicationPools::AllocateApplicationPoolsObject(IUnknown *,CCredentials &,CIISApplicationPools * *)
0x1800082f3  mov     rsi, [rbp+Block]
0x1800082f7  mov     ebx, eax
0x1800082f9  test    eax, eax
0x1800082fb  js      loc_18000843D
0x180008301  mov     rcx, [rsi+38h]
0x180008305  lea     rdx, [rbp+pStr]
0x180008309  mov     rax, [rcx]
0x18000830c  mov     rax, [rax+50h]
0x180008310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008315  mov     ebx, eax
0x180008317  test    eax, eax
0x180008319  js      loc_18000843D
0x18000831f  lea     ecx, [r12+20h]; Size
0x180008324  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008329  mov     rdi, rax
0x18000832c  test    rax, rax
0x18000832f  jz      loc_180008435
0x180008335  mov     [rax], r12
0x180008338  mov     rcx, rax; this
0x18000833b  mov     [rax+8], r12
0x18000833f  mov     [rax+10h], r12
0x180008343  mov     [rax+18h], r12
0x180008347  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x18000834b  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x180008350  mov     ebx, eax
0x180008352  test    eax, eax
0x180008354  js      loc_18000843D
0x18000835a  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x18000835e  mov     rcx, rdi; this
0x180008361  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180008366  mov     ebx, eax
0x180008368  test    eax, eax
0x18000836a  js      loc_18000843D
0x180008370  mov     rcx, [rbp+pStr]; pStr
0x180008374  call    cs:__imp_AllocADsStr
0x18000837a  mov     r14, rax
0x18000837d  test    rax, rax
0x180008380  jz      loc_180008438
0x180008386  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000838a  inc     r8
0x18000838d  cmp     [rax+r8*2], r12w
0x180008392  jnz     short loc_18000838A
0x180008394  inc     r8; unsigned __int64
0x180008397  mov     [rax], r12w
0x18000839b  mov     rdx, r14; unsigned __int16 *
0x18000839e  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x1800083a2  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x1800083a7  mov     ebx, eax
0x1800083a9  test    eax, eax
0x1800083ab  js      loc_18000843D
0x1800083b1  mov     rbx, [rbp+var_28+8]
0x1800083b5  test    rbx, rbx
0x1800083b8  jz      short loc_1800083CC
0x1800083ba  mov     rcx, rbx; pStr
0x1800083bd  call    cs:__imp_AllocADsStr
0x1800083c3  mov     [rsi+40h], rax
0x1800083c7  test    rax, rax
0x1800083ca  jz      short loc_180008438
0x1800083cc  mov     rcx, r14; pStr
0x1800083cf  call    cs:__imp_AllocADsStr
0x1800083d5  mov     [rsi+48h], rax
0x1800083d9  test    rax, rax
0x1800083dc  jz      short loc_180008438
0x1800083de  lea     rdx, [rsi+78h]; struct IMSAdminBaseW **
0x1800083e2  mov     rcx, rbx; unsigned __int16 *
0x1800083e5  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x1800083ea  mov     ebx, eax
0x1800083ec  test    eax, eax
0x1800083ee  js      short loc_18000843D
0x1800083f0  lea     rcx, [rsi+20h]
0x1800083f4  neg     rsi
0x1800083f7  sbb     rax, rax
0x1800083fa  and     rax, rcx
0x1800083fd  mov     rcx, [rbp+pStr]; bstrString
0x180008401  mov     [r15], rax
0x180008404  test    rcx, rcx
0x180008407  jz      short loc_18000840F
0x180008409  call    cs:__imp_SysFreeString
0x18000840f  mov     rcx, [rdi+8]; pStr
0x180008413  call    cs:__imp_FreeADsStr
0x180008419  mov     rcx, rdi; Block
0x18000841c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008421  mov     rcx, r14; pStr
0x180008424  call    cs:__imp_FreeADsStr
0x18000842a  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000842e  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180008433  jmp     short loc_180008492
0x180008435  mov     rdi, r12
0x180008438  mov     ebx, 8007000Eh
0x18000843d  mov     rcx, [rbp+pStr]; bstrString
0x180008441  test    rcx, rcx
0x180008444  jz      short loc_18000844C
0x180008446  call    cs:__imp_SysFreeString
0x18000844c  test    rdi, rdi
0x18000844f  jz      short loc_180008463
0x180008451  mov     rcx, [rdi+8]; pStr
0x180008455  call    cs:__imp_FreeADsStr
0x18000845b  mov     rcx, rdi; Block
0x18000845e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008463  test    r14, r14
0x180008466  jz      short loc_180008471
0x180008468  mov     rcx, r14; pStr
0x18000846b  call    cs:__imp_FreeADsStr
0x180008471  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180008475  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x18000847a  mov     [r15], r12
0x18000847d  test    rsi, rsi
0x180008480  jz      short loc_180008492
0x180008482  mov     rcx, rsi; this
0x180008485  call    ??1CIISApplicationPools@@QEAA@XZ; CIISApplicationPools::~CIISApplicationPools(void)
0x18000848a  mov     rcx, rsi; Block
0x18000848d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008492  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180008496  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x18000849b  lea     rdx, [rbp+var_2C]; unsigned int *
0x18000849f  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x1800084a3  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800084a8  lea     r11, [rsp+60h+var_s0]
0x1800084ad  mov     eax, ebx
0x1800084af  mov     rbx, [r11+30h]
0x1800084b3  mov     rsi, [r11+40h]
0x1800084b7  mov     rsp, r11
0x1800084ba  pop     r15
0x1800084bc  pop     r14
0x1800084be  pop     r12
0x1800084c0  pop     rdi
0x1800084c1  pop     rbp
0x1800084c2  retn
```
