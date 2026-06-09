# CIISApp::CreateApp(IUnknown *,_GUID const &,void * *)

- ea: `0x180005a58`
- end: `0x180005ca5`
- name: `?CreateApp@CIISApp@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `589`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops`

## callers

- `0x180006470`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x180004f98`
- `0x180005310`
- `0x180005a58`
- `0x180005e50`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180005bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c27`
- `OLEAUT32!__imp_SysFreeString` at `0x180005bea`
- `OLEAUT32!__imp_SysFreeString` at `0x180005c27`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b3f`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b86`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b9c`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b3f`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b86`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180005b9c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005bf4`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c05`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c36`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c4c`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005bf4`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c05`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c36`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180005c4c`

## pseudocode

```c
__int64 __fastcall CIISApp::CreateApp(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int AppObject; // eax
  void *v8; // rsi
  int inited; // ebx
  LPWSTR *v10; // rax
  LPWSTR v11; // rax
  __int64 v12; // r8
  LPWSTR v13; // rax
  LPWSTR v14; // rax
  OLECHAR *v15; // rcx
  unsigned __int16 *v17; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 *v18; // [rsp+28h] [rbp-38h] BYREF
  unsigned int v19; // [rsp+34h] [rbp-2Ch] BYREF
  LPCWSTR v20[2]; // [rsp+38h] [rbp-28h] BYREF
  __int128 v21; // [rsp+48h] [rbp-18h]
  __int64 v22; // [rsp+58h] [rbp-8h]
  LPCWSTR pStr; // [rsp+98h] [rbp+38h] BYREF
  void *Block; // [rsp+A8h] [rbp+48h] BYREF

  pStr = a2;
  CCredentials::Initialize((CCredentials *)&v17, 0, 0, 0);
  Block = 0;
  pStr = 0;
  v22 = 0;
  v5 = 0;
  *(_OWORD *)v20 = 0;
  v6 = 0;
  v21 = 0;
  AppObject = CIISApp::AllocateAppObject(a1, (struct CCredentials *)&v17, (struct CIISApp **)&Block);
  v8 = Block;
  inited = AppObject;
  if ( AppObject < 0 )
    goto LABEL_20;
  inited = (*(__int64 (__fastcall **)(_QWORD, LPCWSTR *))(**((_QWORD **)Block + 7) + 80LL))(
             *((_QWORD *)Block + 7),
             &pStr);
  if ( inited < 0 )
    goto LABEL_20;
  v10 = (LPWSTR *)operator new(0x20u);
  v5 = v10;
  if ( !v10 )
  {
    v5 = 0;
LABEL_19:
    inited = -2147024882;
    goto LABEL_20;
  }
  *v10 = 0;
  v10[1] = 0;
  v10[2] = 0;
  v10[3] = 0;
  inited = CLexer::Initialize((CLexer *)v10, (unsigned __int16 *)pStr);
  if ( inited < 0 )
    goto LABEL_20;
  inited = ADsObject((struct CLexer *)v5, (struct _objectinfo *)v20);
  if ( inited < 0 )
    goto LABEL_20;
  v11 = AllocADsStr(pStr);
  v6 = v11;
  if ( !v11 )
    goto LABEL_19;
  v12 = -1;
  do
    ++v12;
  while ( v11[v12] );
  *v11 = 0;
  inited = BuildIISPathFromADsPath((struct _objectinfo *)v20, v11, v12 + 1);
  if ( inited < 0 )
    goto LABEL_20;
  if ( v20[1] )
  {
    v13 = AllocADsStr(v20[1]);
    *((_QWORD *)v8 + 8) = v13;
    if ( !v13 )
      goto LABEL_19;
  }
  v14 = AllocADsStr(v6);
  *((_QWORD *)v8 + 9) = v14;
  if ( !v14 )
    goto LABEL_19;
  inited = InitServerInfo((unsigned __int16 *)v20[1], (struct IMSAdminBaseW **)v8 + 15);
  if ( inited >= 0 )
  {
    inited = CIISApp::InitWamAdm((CIISApp *)v8, (unsigned __int16 *)v20[1]);
    if ( inited >= 0 )
    {
      v15 = (OLECHAR *)pStr;
      *a3 = (void *)(((unsigned __int64)v8 + 32) & -(__int64)(v8 != 0));
      if ( v15 )
        SysFreeString(v15);
      FreeADsStr(v5[1]);
      operator delete(v5);
      FreeADsStr(v6);
      FreeObjectInfo((struct _objectinfo *)v20);
      goto LABEL_28;
    }
  }
LABEL_20:
  if ( pStr )
    SysFreeString((BSTR)pStr);
  if ( v5 )
  {
    FreeADsStr(v5[1]);
    operator delete(v5);
  }
  if ( v6 )
    FreeADsStr(v6);
  FreeObjectInfo((struct _objectinfo *)v20);
  *a3 = 0;
  if ( v8 )
  {
    CIISApp::~CIISApp((CIISApp *)v8);
    operator delete(v8);
  }
LABEL_28:
  CCredentials::FreeUserName(&v17);
  CCredentials::FreePassword(&v18, &v19);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180005a58  mov     [rsp-28h+arg_0], rbx
0x180005a5d  mov     [rsp-28h+arg_10], rsi
0x180005a62  mov     [rsp-28h+pStr], rdx
0x180005a67  push    rbp
0x180005a68  push    rdi
0x180005a69  push    r12
0x180005a6b  push    r13
0x180005a6d  push    r14
0x180005a6f  mov     rbp, rsp
0x180005a72  sub     rsp, 60h
0x180005a76  mov     r12, r8
0x180005a79  mov     rbx, rcx
0x180005a7c  xor     r8d, r8d; unsigned __int16 *
0x180005a7f  lea     rcx, [rbp+var_40]; this
0x180005a83  xor     r9d, r9d; unsigned int
0x180005a86  xor     edx, edx; pStr
0x180005a88  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180005a8d  xor     r13d, r13d
0x180005a90  lea     r8, [rbp+Block]; struct CIISApp **
0x180005a94  xorps   xmm0, xmm0
0x180005a97  mov     [rbp+Block], r13
0x180005a9b  xor     eax, eax
0x180005a9d  mov     [rbp+pStr], r13
0x180005aa1  lea     rdx, [rbp+var_40]; struct CCredentials *
0x180005aa5  mov     [rbp+var_8], rax
0x180005aa9  mov     rcx, rbx; struct IUnknown *
0x180005aac  mov     edi, r13d
0x180005aaf  movups  xmmword ptr [rbp+var_28], xmm0
0x180005ab3  mov     r14d, r13d
0x180005ab6  movups  [rbp+var_18], xmm0
0x180005aba  call    ?AllocateAppObject@CIISApp@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISApp::AllocateAppObject(IUnknown *,CCredentials &,CIISApp * *)
0x180005abf  mov     rsi, [rbp+Block]
0x180005ac3  mov     ebx, eax
0x180005ac5  test    eax, eax
0x180005ac7  js      loc_180005C1E
0x180005acd  mov     rcx, [rsi+38h]
0x180005ad1  lea     rdx, [rbp+pStr]
0x180005ad5  mov     rax, [rcx]
0x180005ad8  mov     rax, [rax+50h]
0x180005adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ae1  mov     ebx, eax
0x180005ae3  test    eax, eax
0x180005ae5  js      loc_180005C1E
0x180005aeb  lea     ecx, [r13+20h]; Size
0x180005aef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005af4  mov     rdi, rax
0x180005af7  test    rax, rax
0x180005afa  jz      loc_180005C16
0x180005b00  mov     [rax], r13
0x180005b03  mov     rcx, rax; this
0x180005b06  mov     [rax+8], r13
0x180005b0a  mov     [rax+10h], r13
0x180005b0e  mov     [rax+18h], r13
0x180005b12  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x180005b16  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x180005b1b  mov     ebx, eax
0x180005b1d  test    eax, eax
0x180005b1f  js      loc_180005C1E
0x180005b25  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x180005b29  mov     rcx, rdi; this
0x180005b2c  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180005b31  mov     ebx, eax
0x180005b33  test    eax, eax
0x180005b35  js      loc_180005C1E
0x180005b3b  mov     rcx, [rbp+pStr]; pStr
0x180005b3f  call    cs:__imp_AllocADsStr
0x180005b45  mov     r14, rax
0x180005b48  test    rax, rax
0x180005b4b  jz      loc_180005C19
0x180005b51  or      r8, 0FFFFFFFFFFFFFFFFh
0x180005b55  inc     r8
0x180005b58  cmp     [rax+r8*2], r13w
0x180005b5d  jnz     short loc_180005B55
0x180005b5f  inc     r8; unsigned __int64
0x180005b62  mov     [rax], r13w
0x180005b66  mov     rdx, r14; unsigned __int16 *
0x180005b69  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180005b6d  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x180005b72  mov     ebx, eax
0x180005b74  test    eax, eax
0x180005b76  js      loc_180005C1E
0x180005b7c  cmp     [rbp+var_28+8], r13
0x180005b80  jz      short loc_180005B99
0x180005b82  mov     rcx, [rbp+var_28+8]; pStr
0x180005b86  call    cs:__imp_AllocADsStr
0x180005b8c  mov     [rsi+40h], rax
0x180005b90  test    rax, rax
0x180005b93  jz      loc_180005C19
0x180005b99  mov     rcx, r14; pStr
0x180005b9c  call    cs:__imp_AllocADsStr
0x180005ba2  mov     [rsi+48h], rax
0x180005ba6  test    rax, rax
0x180005ba9  jz      short loc_180005C19
0x180005bab  mov     rcx, [rbp+var_28+8]; unsigned __int16 *
0x180005baf  lea     rdx, [rsi+78h]; struct IMSAdminBaseW **
0x180005bb3  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x180005bb8  mov     ebx, eax
0x180005bba  test    eax, eax
0x180005bbc  js      short loc_180005C1E
0x180005bbe  mov     rdx, [rbp+var_28+8]; unsigned __int16 *
0x180005bc2  mov     rcx, rsi; this
0x180005bc5  call    ?InitWamAdm@CIISApp@@QEAAJPEAG@Z; CIISApp::InitWamAdm(ushort *)
0x180005bca  mov     ebx, eax
0x180005bcc  test    eax, eax
0x180005bce  js      short loc_180005C1E
0x180005bd0  lea     rcx, [rsi+20h]
0x180005bd4  neg     rsi
0x180005bd7  sbb     rax, rax
0x180005bda  and     rax, rcx
0x180005bdd  mov     rcx, [rbp+pStr]; bstrString
0x180005be1  mov     [r12], rax
0x180005be5  test    rcx, rcx
0x180005be8  jz      short loc_180005BF0
0x180005bea  call    cs:__imp_SysFreeString
0x180005bf0  mov     rcx, [rdi+8]; pStr
0x180005bf4  call    cs:__imp_FreeADsStr
0x180005bfa  mov     rcx, rdi; Block
0x180005bfd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005c02  mov     rcx, r14; pStr
0x180005c05  call    cs:__imp_FreeADsStr
0x180005c0b  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180005c0f  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180005c14  jmp     short loc_180005C74
0x180005c16  mov     rdi, r13
0x180005c19  mov     ebx, 8007000Eh
0x180005c1e  mov     rcx, [rbp+pStr]; bstrString
0x180005c22  test    rcx, rcx
0x180005c25  jz      short loc_180005C2D
0x180005c27  call    cs:__imp_SysFreeString
0x180005c2d  test    rdi, rdi
0x180005c30  jz      short loc_180005C44
0x180005c32  mov     rcx, [rdi+8]; pStr
0x180005c36  call    cs:__imp_FreeADsStr
0x180005c3c  mov     rcx, rdi; Block
0x180005c3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005c44  test    r14, r14
0x180005c47  jz      short loc_180005C52
0x180005c49  mov     rcx, r14; pStr
0x180005c4c  call    cs:__imp_FreeADsStr
0x180005c52  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180005c56  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180005c5b  mov     [r12], r13
0x180005c5f  test    rsi, rsi
0x180005c62  jz      short loc_180005C74
0x180005c64  mov     rcx, rsi; this
0x180005c67  call    ??1CIISApp@@QEAA@XZ; CIISApp::~CIISApp(void)
0x180005c6c  mov     rcx, rsi; Block
0x180005c6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005c74  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180005c78  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180005c7d  lea     rdx, [rbp+var_2C]; unsigned int *
0x180005c81  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x180005c85  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x180005c8a  lea     r11, [rsp+60h+var_s0]
0x180005c8f  mov     eax, ebx
0x180005c91  mov     rbx, [r11+30h]
0x180005c95  mov     rsi, [r11+40h]
0x180005c99  mov     rsp, r11
0x180005c9c  pop     r14
0x180005c9e  pop     r13
0x180005ca0  pop     r12
0x180005ca2  pop     rdi
0x180005ca3  pop     rbp
0x180005ca4  retn
```
