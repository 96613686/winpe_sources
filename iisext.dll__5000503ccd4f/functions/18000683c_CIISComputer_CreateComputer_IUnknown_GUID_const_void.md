# CIISComputer::CreateComputer(IUnknown *,_GUID const &,void * *)

- ea: `0x18000683c`
- end: `0x180006a76`
- name: `?CreateComputer@CIISComputer@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `570`
- prototype: `__int64 __fastcall(struct IUnknown *, const WCHAR *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180006ff0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x1800064a0`
- `0x1800065a0`
- `0x18000683c`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800069ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069f9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800069f9`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180006925`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000696e`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180006980`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180006925`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000696e`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180006980`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800069c9`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800069da`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180006a08`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180006a1e`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800069c9`
- `ACTIVEDS!__imp_FreeADsStr` at `0x1800069da`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180006a08`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180006a1e`

## pseudocode

```c
__int64 __fastcall CIISComputer::CreateComputer(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int ComputerObject; // eax
  struct IMSAdminBaseW **v8; // rsi
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
  ComputerObject = CIISComputer::AllocateComputerObject(a1, (struct CCredentials *)&v18, (struct CIISComputer **)&Block);
  v8 = (struct IMSAdminBaseW **)Block;
  inited = ComputerObject;
  if ( ComputerObject < 0 )
    goto LABEL_22;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)Block + 7) + 80LL))(
             *((_QWORD *)Block + 7),
             &pStr);
  if ( inited < 0 )
    goto LABEL_22;
  v10 = (LPWSTR *)operator new(0x20u);
  v5 = v10;
  if ( v10 )
  {
    *v10 = 0;
    v10[1] = 0;
    v10[2] = 0;
    v10[3] = 0;
  }
  else
  {
    v5 = 0;
  }
  inited = CLexer::Initialize((CLexer *)v5, (unsigned __int16 *)pStr);
  if ( inited < 0 )
    goto LABEL_22;
  inited = ADsObject((struct CLexer *)v5, (struct _objectinfo *)v21);
  if ( inited < 0 )
    goto LABEL_22;
  v11 = AllocADsStr(pStr);
  v6 = v11;
  if ( !v11 )
    goto LABEL_21;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  *v11 = 0;
  inited = BuildIISPathFromADsPath((struct _objectinfo *)v21, v11, v12 + 1);
  if ( inited < 0 )
    goto LABEL_22;
  if ( ((v13 = (unsigned __int16 *)v21[1]) == 0
     || (v14 = AllocADsStr(v21[1]), (v8[8] = (struct IMSAdminBaseW *)v14) != 0))
    && (v15 = AllocADsStr(v6), (v8[9] = (struct IMSAdminBaseW *)v15) != 0) )
  {
    inited = InitServerInfo(v13, v8 + 15);
    if ( inited >= 0 )
    {
      v16 = (OLECHAR *)pStr;
      *a3 = (void *)((unsigned __int64)(v8 + 4) & -(__int64)(v8 != 0));
      if ( v16 )
        SysFreeString(v16);
      if ( v5 )
      {
        FreeADsStr(v5[1]);
        operator delete(v5);
      }
      FreeADsStr(v6);
      FreeObjectInfo((struct _objectinfo *)v21);
      goto LABEL_30;
    }
  }
  else
  {
LABEL_21:
    inited = -2147024882;
  }
LABEL_22:
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
    CIISComputer::~CIISComputer((CIISComputer *)v8);
    operator delete(v8);
  }
LABEL_30:
  CCredentials::FreeUserName(&v18);
  CCredentials::FreePassword(&v19, &v20);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000683c  mov     [rsp-28h+arg_0], rbx
0x180006841  mov     [rsp-28h+arg_10], rsi
0x180006846  mov     [rsp-28h+pStr], rdx
0x18000684b  push    rbp
0x18000684c  push    rdi
0x18000684d  push    r12
0x18000684f  push    r14
0x180006851  push    r15
0x180006853  mov     rbp, rsp
0x180006856  sub     rsp, 60h
0x18000685a  mov     r15, r8
0x18000685d  mov     rbx, rcx
0x180006860  xor     r8d, r8d; unsigned __int16 *
0x180006863  lea     rcx, [rbp+var_40]; this
0x180006867  xor     r9d, r9d; unsigned int
0x18000686a  xor     edx, edx; pStr
0x18000686c  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180006871  xor     r12d, r12d
0x180006874  lea     r8, [rbp+Block]; struct CIISComputer **
0x180006878  xorps   xmm0, xmm0
0x18000687b  mov     [rbp+Block], r12
0x18000687f  xor     eax, eax
0x180006881  mov     [rbp+pStr], r12
0x180006885  lea     rdx, [rbp+var_40]; struct CCredentials *
0x180006889  mov     [rbp+var_8], rax
0x18000688d  mov     rcx, rbx; struct IUnknown *
0x180006890  mov     edi, r12d
0x180006893  movups  xmmword ptr [rbp+var_28], xmm0
0x180006897  mov     r14d, r12d
0x18000689a  movups  [rbp+var_18], xmm0
0x18000689e  call    ?AllocateComputerObject@CIISComputer@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISComputer::AllocateComputerObject(IUnknown *,CCredentials &,CIISComputer * *)
0x1800068a3  mov     rsi, [rbp+Block]
0x1800068a7  mov     ebx, eax
0x1800068a9  test    eax, eax
0x1800068ab  js      loc_1800069F0
0x1800068b1  mov     rcx, [rsi+38h]
0x1800068b5  lea     rdx, [rbp+pStr]
0x1800068b9  mov     rax, [rcx]
0x1800068bc  mov     rax, [rax+50h]
0x1800068c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c5  mov     ebx, eax
0x1800068c7  test    eax, eax
0x1800068c9  js      loc_1800069F0
0x1800068cf  lea     ecx, [r12+20h]; Size
0x1800068d4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800068d9  mov     rdi, rax
0x1800068dc  test    rax, rax
0x1800068df  jz      short loc_1800068F2
0x1800068e1  mov     [rax], r12
0x1800068e4  mov     [rax+8], r12
0x1800068e8  mov     [rax+10h], r12
0x1800068ec  mov     [rax+18h], r12
0x1800068f0  jmp     short loc_1800068F5
0x1800068f2  mov     rdi, r12
0x1800068f5  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x1800068f9  mov     rcx, rdi; this
0x1800068fc  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x180006901  mov     ebx, eax
0x180006903  test    eax, eax
0x180006905  js      loc_1800069F0
0x18000690b  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x18000690f  mov     rcx, rdi; this
0x180006912  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180006917  mov     ebx, eax
0x180006919  test    eax, eax
0x18000691b  js      loc_1800069F0
0x180006921  mov     rcx, [rbp+pStr]; pStr
0x180006925  call    cs:__imp_AllocADsStr
0x18000692b  mov     r14, rax
0x18000692e  test    rax, rax
0x180006931  jz      loc_1800069EB
0x180006937  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000693b  inc     r8
0x18000693e  cmp     [rax+r8*2], r12w
0x180006943  jnz     short loc_18000693B
0x180006945  inc     r8; unsigned __int64
0x180006948  mov     [rax], r12w
0x18000694c  mov     rdx, r14; unsigned __int16 *
0x18000694f  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180006953  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x180006958  mov     ebx, eax
0x18000695a  test    eax, eax
0x18000695c  js      loc_1800069F0
0x180006962  mov     rbx, [rbp+var_28+8]
0x180006966  test    rbx, rbx
0x180006969  jz      short loc_18000697D
0x18000696b  mov     rcx, rbx; pStr
0x18000696e  call    cs:__imp_AllocADsStr
0x180006974  mov     [rsi+40h], rax
0x180006978  test    rax, rax
0x18000697b  jz      short loc_1800069EB
0x18000697d  mov     rcx, r14; pStr
0x180006980  call    cs:__imp_AllocADsStr
0x180006986  mov     [rsi+48h], rax
0x18000698a  test    rax, rax
0x18000698d  jz      short loc_1800069EB
0x18000698f  lea     rdx, [rsi+78h]; struct IMSAdminBaseW **
0x180006993  mov     rcx, rbx; unsigned __int16 *
0x180006996  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x18000699b  mov     ebx, eax
0x18000699d  test    eax, eax
0x18000699f  js      short loc_1800069F0
0x1800069a1  lea     rcx, [rsi+20h]
0x1800069a5  neg     rsi
0x1800069a8  sbb     rax, rax
0x1800069ab  and     rax, rcx
0x1800069ae  mov     rcx, [rbp+pStr]; bstrString
0x1800069b2  mov     [r15], rax
0x1800069b5  test    rcx, rcx
0x1800069b8  jz      short loc_1800069C0
0x1800069ba  call    cs:__imp_SysFreeString
0x1800069c0  test    rdi, rdi
0x1800069c3  jz      short loc_1800069D7
0x1800069c5  mov     rcx, [rdi+8]; pStr
0x1800069c9  call    cs:__imp_FreeADsStr
0x1800069cf  mov     rcx, rdi; Block
0x1800069d2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800069d7  mov     rcx, r14; pStr
0x1800069da  call    cs:__imp_FreeADsStr
0x1800069e0  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x1800069e4  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x1800069e9  jmp     short loc_180006A45
0x1800069eb  mov     ebx, 8007000Eh
0x1800069f0  mov     rcx, [rbp+pStr]; bstrString
0x1800069f4  test    rcx, rcx
0x1800069f7  jz      short loc_1800069FF
0x1800069f9  call    cs:__imp_SysFreeString
0x1800069ff  test    rdi, rdi
0x180006a02  jz      short loc_180006A16
0x180006a04  mov     rcx, [rdi+8]; pStr
0x180006a08  call    cs:__imp_FreeADsStr
0x180006a0e  mov     rcx, rdi; Block
0x180006a11  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a16  test    r14, r14
0x180006a19  jz      short loc_180006A24
0x180006a1b  mov     rcx, r14; pStr
0x180006a1e  call    cs:__imp_FreeADsStr
0x180006a24  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180006a28  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180006a2d  mov     [r15], r12
0x180006a30  test    rsi, rsi
0x180006a33  jz      short loc_180006A45
0x180006a35  mov     rcx, rsi; this
0x180006a38  call    ??1CIISComputer@@QEAA@XZ; CIISComputer::~CIISComputer(void)
0x180006a3d  mov     rcx, rsi; Block
0x180006a40  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a45  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180006a49  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180006a4e  lea     rdx, [rbp+var_2C]; unsigned int *
0x180006a52  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180006a56  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180006a5b  lea     r11, [rsp+60h+var_s0]
0x180006a60  mov     eax, ebx
0x180006a62  mov     rbx, [r11+30h]
0x180006a66  mov     rsi, [r11+40h]
0x180006a6a  mov     rsp, r11
0x180006a6d  pop     r15
0x180006a6f  pop     r14
0x180006a71  pop     r12
0x180006a73  pop     rdi
0x180006a74  pop     rbp
0x180006a75  retn
```
