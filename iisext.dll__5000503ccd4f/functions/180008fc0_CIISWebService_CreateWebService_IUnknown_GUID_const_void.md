# CIISWebService::CreateWebService(IUnknown *,_GUID const &,void * *)

- ea: `0x180008fc0`
- end: `0x1800091f7`
- name: `?CreateWebService@CIISWebService@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, service_task`

## callers

- `0x180009af0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x1800085f0`
- `0x180008834`
- `0x180008fc0`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000913d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000917a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000913d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000917a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800090a8`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800090f1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009103`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800090a8`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800090f1`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009103`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009147`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009158`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009189`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000919f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009147`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009158`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009189`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000919f`

## pseudocode

```c
__int64 __fastcall CIISWebService::CreateWebService(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int WebServiceObject; // eax
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
  WebServiceObject = CIISWebService::AllocateWebServiceObject(
                       a1,
                       (struct CCredentials *)&v18,
                       (struct CIISWebService **)&Block);
  v8 = Block;
  inited = WebServiceObject;
  if ( WebServiceObject < 0 )
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
    CIISWebService::~CIISWebService((CIISWebService *)v8);
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
0x180008fc0  mov     [rsp-28h+arg_0], rbx
0x180008fc5  mov     [rsp-28h+arg_10], rsi
0x180008fca  mov     [rsp-28h+pStr], rdx
0x180008fcf  push    rbp
0x180008fd0  push    rdi
0x180008fd1  push    r12
0x180008fd3  push    r14
0x180008fd5  push    r15
0x180008fd7  mov     rbp, rsp
0x180008fda  sub     rsp, 60h
0x180008fde  mov     r15, r8
0x180008fe1  mov     rbx, rcx
0x180008fe4  xor     r8d, r8d; unsigned __int16 *
0x180008fe7  lea     rcx, [rbp+var_40]; this
0x180008feb  xor     r9d, r9d; unsigned int
0x180008fee  xor     edx, edx; pStr
0x180008ff0  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180008ff5  xor     r12d, r12d
0x180008ff8  lea     r8, [rbp+Block]; struct CIISWebService **
0x180008ffc  xorps   xmm0, xmm0
0x180008fff  mov     [rbp+Block], r12
0x180009003  xor     eax, eax
0x180009005  mov     [rbp+pStr], r12
0x180009009  lea     rdx, [rbp+var_40]; struct CCredentials *
0x18000900d  mov     [rbp+var_8], rax
0x180009011  mov     rcx, rbx; struct IUnknown *
0x180009014  mov     edi, r12d
0x180009017  movups  xmmword ptr [rbp+var_28], xmm0
0x18000901b  mov     r14d, r12d
0x18000901e  movups  [rbp+var_18], xmm0
0x180009022  call    ?AllocateWebServiceObject@CIISWebService@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISWebService::AllocateWebServiceObject(IUnknown *,CCredentials &,CIISWebService * *)
0x180009027  mov     rsi, [rbp+Block]
0x18000902b  mov     ebx, eax
0x18000902d  test    eax, eax
0x18000902f  js      loc_180009171
0x180009035  mov     rcx, [rsi+38h]
0x180009039  lea     rdx, [rbp+pStr]
0x18000903d  mov     rax, [rcx]
0x180009040  mov     rax, [rax+50h]
0x180009044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009049  mov     ebx, eax
0x18000904b  test    eax, eax
0x18000904d  js      loc_180009171
0x180009053  lea     ecx, [r12+20h]; Size
0x180009058  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000905d  mov     rdi, rax
0x180009060  test    rax, rax
0x180009063  jz      loc_180009169
0x180009069  mov     [rax], r12
0x18000906c  mov     rcx, rax; this
0x18000906f  mov     [rax+8], r12
0x180009073  mov     [rax+10h], r12
0x180009077  mov     [rax+18h], r12
0x18000907b  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x18000907f  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x180009084  mov     ebx, eax
0x180009086  test    eax, eax
0x180009088  js      loc_180009171
0x18000908e  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x180009092  mov     rcx, rdi; this
0x180009095  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x18000909a  mov     ebx, eax
0x18000909c  test    eax, eax
0x18000909e  js      loc_180009171
0x1800090a4  mov     rcx, [rbp+pStr]; pStr
0x1800090a8  call    cs:__imp_AllocADsStr
0x1800090ae  mov     r14, rax
0x1800090b1  test    rax, rax
0x1800090b4  jz      loc_18000916C
0x1800090ba  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800090be  inc     r8
0x1800090c1  cmp     [rax+r8*2], r12w
0x1800090c6  jnz     short loc_1800090BE
0x1800090c8  inc     r8; unsigned __int64
0x1800090cb  mov     [rax], r12w
0x1800090cf  mov     rdx, r14; unsigned __int16 *
0x1800090d2  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x1800090d6  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x1800090db  mov     ebx, eax
0x1800090dd  test    eax, eax
0x1800090df  js      loc_180009171
0x1800090e5  mov     rbx, [rbp+var_28+8]
0x1800090e9  test    rbx, rbx
0x1800090ec  jz      short loc_180009100
0x1800090ee  mov     rcx, rbx; pStr
0x1800090f1  call    cs:__imp_AllocADsStr
0x1800090f7  mov     [rsi+40h], rax
0x1800090fb  test    rax, rax
0x1800090fe  jz      short loc_18000916C
0x180009100  mov     rcx, r14; pStr
0x180009103  call    cs:__imp_AllocADsStr
0x180009109  mov     [rsi+48h], rax
0x18000910d  test    rax, rax
0x180009110  jz      short loc_18000916C
0x180009112  lea     rdx, [rsi+78h]; struct IMSAdminBaseW **
0x180009116  mov     rcx, rbx; unsigned __int16 *
0x180009119  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x18000911e  mov     ebx, eax
0x180009120  test    eax, eax
0x180009122  js      short loc_180009171
0x180009124  lea     rcx, [rsi+20h]
0x180009128  neg     rsi
0x18000912b  sbb     rax, rax
0x18000912e  and     rax, rcx
0x180009131  mov     rcx, [rbp+pStr]; bstrString
0x180009135  mov     [r15], rax
0x180009138  test    rcx, rcx
0x18000913b  jz      short loc_180009143
0x18000913d  call    cs:__imp_SysFreeString
0x180009143  mov     rcx, [rdi+8]; pStr
0x180009147  call    cs:__imp_FreeADsStr
0x18000914d  mov     rcx, rdi; Block
0x180009150  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009155  mov     rcx, r14; pStr
0x180009158  call    cs:__imp_FreeADsStr
0x18000915e  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180009162  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180009167  jmp     short loc_1800091C6
0x180009169  mov     rdi, r12
0x18000916c  mov     ebx, 8007000Eh
0x180009171  mov     rcx, [rbp+pStr]; bstrString
0x180009175  test    rcx, rcx
0x180009178  jz      short loc_180009180
0x18000917a  call    cs:__imp_SysFreeString
0x180009180  test    rdi, rdi
0x180009183  jz      short loc_180009197
0x180009185  mov     rcx, [rdi+8]; pStr
0x180009189  call    cs:__imp_FreeADsStr
0x18000918f  mov     rcx, rdi; Block
0x180009192  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009197  test    r14, r14
0x18000919a  jz      short loc_1800091A5
0x18000919c  mov     rcx, r14; pStr
0x18000919f  call    cs:__imp_FreeADsStr
0x1800091a5  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x1800091a9  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x1800091ae  mov     [r15], r12
0x1800091b1  test    rsi, rsi
0x1800091b4  jz      short loc_1800091C6
0x1800091b6  mov     rcx, rsi; this
0x1800091b9  call    ??1CIISWebService@@QEAA@XZ; CIISWebService::~CIISWebService(void)
0x1800091be  mov     rcx, rsi; Block
0x1800091c1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800091c6  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x1800091ca  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x1800091cf  lea     rdx, [rbp+var_2C]; unsigned int *
0x1800091d3  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x1800091d7  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800091dc  lea     r11, [rsp+60h+var_s0]
0x1800091e1  mov     eax, ebx
0x1800091e3  mov     rbx, [r11+30h]
0x1800091e7  mov     rsi, [r11+40h]
0x1800091eb  mov     rsp, r11
0x1800091ee  pop     r15
0x1800091f0  pop     r14
0x1800091f2  pop     r12
0x1800091f4  pop     rdi
0x1800091f5  pop     rbp
0x1800091f6  retn
```
