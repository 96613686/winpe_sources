# CIISApplicationPool::CreateApplicationPool(IUnknown *,_GUID const &,void * *)

- ea: `0x18000745c`
- end: `0x1800076bf`
- name: `?CreateApplicationPool@CIISApplicationPool@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `611`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180007fa0`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x180007020`
- `0x1800072a0`
- `0x18000745c`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180007605`
- `OLEAUT32!__imp_SysFreeString` at `0x180007642`
- `OLEAUT32!__imp_SysFreeString` at `0x180007605`
- `OLEAUT32!__imp_SysFreeString` at `0x180007642`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180007541`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000759a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800075b0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800075c7`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180007541`
- `ACTIVEDS!__imp_AllocADsStr` at `0x18000759a`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800075b0`
- `ACTIVEDS!__imp_AllocADsStr` at `0x1800075c7`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000760f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007620`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007651`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007667`
- `ACTIVEDS!__imp_FreeADsStr` at `0x18000760f`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007620`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007651`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180007667`

## pseudocode

```c
__int64 __fastcall CIISApplicationPool::CreateApplicationPool(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int ApplicationPoolObject; // eax
  void *v8; // rsi
  int inited; // ebx
  LPWSTR *v10; // rax
  LPWSTR v11; // rax
  __int64 v12; // r8
  unsigned __int16 *v13; // rbx
  const WCHAR *v14; // r15
  LPWSTR v15; // rax
  LPWSTR v16; // rax
  LPWSTR v17; // rax
  OLECHAR *v18; // rcx
  unsigned __int16 *v20; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v21; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v22; // [rsp+34h] [rbp-2Ch] BYREF
  LPCWSTR v23[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v24; // [rsp+48h] [rbp-18h]
  __int64 v25; // [rsp+58h] [rbp-8h]
  LPCWSTR pStr; // [rsp+A8h] [rbp+48h] BYREF
  void *Block; // [rsp+B8h] [rbp+58h] BYREF

  pStr = a2;
  CCredentials::Initialize((CCredentials *)&v20, 0, 0, 0);
  Block = 0;
  pStr = 0;
  v25 = 0;
  v5 = 0;
  *(_OWORD *)v23 = 0;
  v6 = 0;
  v24 = 0;
  ApplicationPoolObject = CIISApplicationPool::AllocateApplicationPoolObject(
                            a1,
                            (struct CCredentials *)&v20,
                            (struct CIISApplicationPool **)&Block);
  v8 = Block;
  inited = ApplicationPoolObject;
  if ( ApplicationPoolObject < 0 )
    goto LABEL_21;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)Block + 7) + 80LL))(
             *((_QWORD *)Block + 7),
             &pStr);
  if ( inited < 0 )
    goto LABEL_21;
  v10 = (LPWSTR *)operator new(0x20u);
  v5 = v10;
  if ( !v10 )
  {
    v5 = 0;
LABEL_20:
    inited = -2147024882;
    goto LABEL_21;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  inited = CLexer::Initialize((CLexer *)v10, (unsigned __int16 *)pStr);
  if ( inited < 0 )
    goto LABEL_21;
  inited = ADsObject((struct CLexer *)v5, (struct _objectinfo *)v23);
  if ( inited < 0 )
    goto LABEL_21;
  v11 = AllocADsStr(pStr);
  v6 = v11;
  if ( !v11 )
    goto LABEL_20;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  *v11 = 0;
  inited = BuildIISPathFromADsPath((struct _objectinfo *)v23, v11, v12 + 1);
  if ( inited < 0 )
    goto LABEL_21;
  v13 = (unsigned __int16 *)v23[1];
  v14 = *(const WCHAR **)(v25 + 16LL * (unsigned int)(DWORD1(v24) - 1));
  if ( v23[1] )
  {
    v15 = AllocADsStr(v23[1]);
    *((_QWORD *)v8 + 8) = v15;
    if ( !v15 )
      goto LABEL_20;
  }
  v16 = AllocADsStr(v6);
  *((_QWORD *)v8 + 9) = v16;
  if ( !v16 )
    goto LABEL_20;
  if ( v14 )
  {
    v17 = AllocADsStr(v14);
    *((_QWORD *)v8 + 10) = v17;
    if ( !v17 )
      goto LABEL_20;
  }
  inited = InitServerInfo(v13, (struct IMSAdminBaseW **)v8 + 16);
  if ( inited >= 0 )
  {
    v18 = (OLECHAR *)pStr;
    *a3 = (void *)(((unsigned __int64)v8 + 32) & -(__int64)(v8 != 0));
    if ( v18 )
      SysFreeString(v18);
    FreeADsStr(v5[1]);
    operator delete(v5);
    FreeADsStr(v6);
    FreeObjectInfo((struct _objectinfo *)v23);
    goto LABEL_29;
  }
LABEL_21:
  if ( pStr )
    SysFreeString((BSTR)pStr);
  if ( v5 )
  {
    FreeADsStr(v5[1]);
    operator delete(v5);
  }
  if ( v6 )
    FreeADsStr(v6);
  FreeObjectInfo((struct _objectinfo *)v23);
  *a3 = 0;
  if ( v8 )
  {
    CIISApplicationPool::~CIISApplicationPool((CIISApplicationPool *)v8);
    operator delete(v8);
  }
LABEL_29:
  CCredentials::FreeUserName(&v20);
  CCredentials::FreePassword(&v21, &v22);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x18000745c  mov     [rsp-38h+arg_0], rbx
0x180007461  mov     [rsp-38h+pStr], rdx
0x180007466  push    rbp
0x180007467  push    rsi
0x180007468  push    rdi
0x180007469  push    r12
0x18000746b  push    r13
0x18000746d  push    r14
0x18000746f  push    r15
0x180007471  mov     rbp, rsp
0x180007474  sub     rsp, 60h
0x180007478  mov     r12, r8
0x18000747b  mov     rbx, rcx
0x18000747e  xor     r8d, r8d; unsigned __int16 *
0x180007481  lea     rcx, [rbp+var_40]; this
0x180007485  xor     r9d, r9d; unsigned int
0x180007488  xor     edx, edx; pStr
0x18000748a  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x18000748f  xor     r13d, r13d
0x180007492  lea     r8, [rbp+Block]; struct CIISApplicationPool **
0x180007496  xorps   xmm0, xmm0
0x180007499  mov     [rbp+Block], r13
0x18000749d  xor     eax, eax
0x18000749f  mov     [rbp+pStr], r13
0x1800074a3  lea     rdx, [rbp+var_40]; struct CCredentials *
0x1800074a7  mov     [rbp+var_8], rax
0x1800074ab  mov     rcx, rbx; struct IUnknown *
0x1800074ae  mov     edi, r13d
0x1800074b1  movups  xmmword ptr [rbp+var_28], xmm0
0x1800074b5  mov     r14d, r13d
0x1800074b8  movups  [rbp+var_18], xmm0
0x1800074bc  call    ?AllocateApplicationPoolObject@CIISApplicationPool@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISApplicationPool::AllocateApplicationPoolObject(IUnknown *,CCredentials &,CIISApplicationPool * *)
0x1800074c1  mov     rsi, [rbp+Block]
0x1800074c5  mov     ebx, eax
0x1800074c7  test    eax, eax
0x1800074c9  js      loc_180007639
0x1800074cf  mov     rcx, [rsi+38h]
0x1800074d3  lea     rdx, [rbp+pStr]
0x1800074d7  mov     rax, [rcx]
0x1800074da  mov     rax, [rax+50h]
0x1800074de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074e3  mov     ebx, eax
0x1800074e5  test    eax, eax
0x1800074e7  js      loc_180007639
0x1800074ed  lea     ecx, [r13+20h]; Size
0x1800074f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800074f6  mov     rdi, rax
0x1800074f9  test    rax, rax
0x1800074fc  jz      loc_180007631
0x180007502  mov     [rax], r13
0x180007505  mov     rcx, rax; this
0x180007508  mov     [rax+8], r13
0x18000750c  mov     [rax+10h], r13
0x180007510  mov     [rax+18h], r13
0x180007514  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x180007518  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x18000751d  mov     ebx, eax
0x18000751f  test    eax, eax
0x180007521  js      loc_180007639
0x180007527  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x18000752b  mov     rcx, rdi; this
0x18000752e  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180007533  mov     ebx, eax
0x180007535  test    eax, eax
0x180007537  js      loc_180007639
0x18000753d  mov     rcx, [rbp+pStr]; pStr
0x180007541  call    cs:__imp_AllocADsStr
0x180007547  mov     r14, rax
0x18000754a  test    rax, rax
0x18000754d  jz      loc_180007634
0x180007553  or      r8, 0FFFFFFFFFFFFFFFFh
0x180007557  inc     r8
0x18000755a  cmp     [rax+r8*2], r13w
0x18000755f  jnz     short loc_180007557
0x180007561  inc     r8; unsigned __int64
0x180007564  mov     [rax], r13w
0x180007568  mov     rdx, r14; unsigned __int16 *
0x18000756b  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000756f  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x180007574  mov     ebx, eax
0x180007576  test    eax, eax
0x180007578  js      loc_180007639
0x18000757e  mov     ecx, dword ptr [rbp+var_18+4]
0x180007581  mov     rax, [rbp+var_8]
0x180007585  dec     ecx
0x180007587  mov     rbx, [rbp+var_28+8]
0x18000758b  add     rcx, rcx
0x18000758e  mov     r15, [rax+rcx*8]
0x180007592  test    rbx, rbx
0x180007595  jz      short loc_1800075AD
0x180007597  mov     rcx, rbx; pStr
0x18000759a  call    cs:__imp_AllocADsStr
0x1800075a0  mov     [rsi+40h], rax
0x1800075a4  test    rax, rax
0x1800075a7  jz      loc_180007634
0x1800075ad  mov     rcx, r14; pStr
0x1800075b0  call    cs:__imp_AllocADsStr
0x1800075b6  mov     [rsi+48h], rax
0x1800075ba  test    rax, rax
0x1800075bd  jz      short loc_180007634
0x1800075bf  test    r15, r15
0x1800075c2  jz      short loc_1800075D6
0x1800075c4  mov     rcx, r15; pStr
0x1800075c7  call    cs:__imp_AllocADsStr
0x1800075cd  mov     [rsi+50h], rax
0x1800075d1  test    rax, rax
0x1800075d4  jz      short loc_180007634
0x1800075d6  lea     rdx, [rsi+80h]; struct IMSAdminBaseW **
0x1800075dd  mov     rcx, rbx; unsigned __int16 *
0x1800075e0  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x1800075e5  mov     ebx, eax
0x1800075e7  test    eax, eax
0x1800075e9  js      short loc_180007639
0x1800075eb  lea     rcx, [rsi+20h]
0x1800075ef  neg     rsi
0x1800075f2  sbb     rax, rax
0x1800075f5  and     rax, rcx
0x1800075f8  mov     rcx, [rbp+pStr]; bstrString
0x1800075fc  mov     [r12], rax
0x180007600  test    rcx, rcx
0x180007603  jz      short loc_18000760B
0x180007605  call    cs:__imp_SysFreeString
0x18000760b  mov     rcx, [rdi+8]; pStr
0x18000760f  call    cs:__imp_FreeADsStr
0x180007615  mov     rcx, rdi; Block
0x180007618  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000761d  mov     rcx, r14; pStr
0x180007620  call    cs:__imp_FreeADsStr
0x180007626  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x18000762a  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x18000762f  jmp     short loc_18000768F
0x180007631  mov     rdi, r13
0x180007634  mov     ebx, 8007000Eh
0x180007639  mov     rcx, [rbp+pStr]; bstrString
0x18000763d  test    rcx, rcx
0x180007640  jz      short loc_180007648
0x180007642  call    cs:__imp_SysFreeString
0x180007648  test    rdi, rdi
0x18000764b  jz      short loc_18000765F
0x18000764d  mov     rcx, [rdi+8]; pStr
0x180007651  call    cs:__imp_FreeADsStr
0x180007657  mov     rcx, rdi; Block
0x18000765a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000765f  test    r14, r14
0x180007662  jz      short loc_18000766D
0x180007664  mov     rcx, r14; pStr
0x180007667  call    cs:__imp_FreeADsStr
0x18000766d  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180007671  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180007676  mov     [r12], r13
0x18000767a  test    rsi, rsi
0x18000767d  jz      short loc_18000768F
0x18000767f  mov     rcx, rsi; this
0x180007682  call    ??1CIISApplicationPool@@QEAA@XZ; CIISApplicationPool::~CIISApplicationPool(void)
0x180007687  mov     rcx, rsi; Block
0x18000768a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000768f  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180007693  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180007698  lea     rdx, [rbp+var_2C]; unsigned int *
0x18000769c  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x1800076a0  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x1800076a5  mov     eax, ebx
0x1800076a7  mov     rbx, [rsp+60h+arg_0]
0x1800076af  add     rsp, 60h
0x1800076b3  pop     r15
0x1800076b5  pop     r14
0x1800076b7  pop     r13
0x1800076b9  pop     r12
0x1800076bb  pop     rdi
0x1800076bc  pop     rsi
0x1800076bd  pop     rbp
0x1800076be  retn
```
