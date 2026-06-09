# CIISServer::CreateServer(IUnknown *,_GUID const &,void * *)

- ea: `0x180009df0`
- end: `0x18000a027`
- name: `?CreateServer@CIISServer@@SAJPEAUIUnknown@@AEBU_GUID@@PEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000a580`

## callees

- `0x180001008`
- `0x180001048`
- `0x180003970`
- `0x180003a14`
- `0x180003bd8`
- `0x180003fdc`
- `0x1800045e0`
- `0x180009b20`
- `0x180009c20`
- `0x180009df0`
- `0x18000dee4`
- `0x18000df38`
- `0x18000e0d4`
- `0x180012010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180009f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180009faa`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f6d`
- `OLEAUT32!__imp_SysFreeString` at `0x180009faa`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ed8`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009f21`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009f33`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009ed8`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009f21`
- `ACTIVEDS!__imp_AllocADsStr` at `0x180009f33`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009f77`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009f88`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009fb9`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009fcf`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009f77`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009f88`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009fb9`
- `ACTIVEDS!__imp_FreeADsStr` at `0x180009fcf`

## pseudocode

```c
__int64 __fastcall CIISServer::CreateServer(struct IUnknown *a1, const WCHAR *a2, void **a3)
{
  LPWSTR *v5; // rdi
  WCHAR *v6; // r14
  int ServerObject; // eax
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
  ServerObject = CIISServer::AllocateServerObject(a1, (struct CCredentials *)&v18, (struct CIISServer **)&Block);
  v8 = Block;
  inited = ServerObject;
  if ( ServerObject < 0 )
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
    CIISServer::~CIISServer((CIISServer *)v8);
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
0x180009df0  mov     [rsp-28h+arg_0], rbx
0x180009df5  mov     [rsp-28h+arg_10], rsi
0x180009dfa  mov     [rsp-28h+pStr], rdx
0x180009dff  push    rbp
0x180009e00  push    rdi
0x180009e01  push    r12
0x180009e03  push    r14
0x180009e05  push    r15
0x180009e07  mov     rbp, rsp
0x180009e0a  sub     rsp, 60h
0x180009e0e  mov     r15, r8
0x180009e11  mov     rbx, rcx
0x180009e14  xor     r8d, r8d; unsigned __int16 *
0x180009e17  lea     rcx, [rbp+var_40]; this
0x180009e1b  xor     r9d, r9d; unsigned int
0x180009e1e  xor     edx, edx; pStr
0x180009e20  call    ?Initialize@CCredentials@@AEAAJPEBG0K@Z; CCredentials::Initialize(ushort const *,ushort const *,ulong)
0x180009e25  xor     r12d, r12d
0x180009e28  lea     r8, [rbp+Block]; struct CIISServer **
0x180009e2c  xorps   xmm0, xmm0
0x180009e2f  mov     [rbp+Block], r12
0x180009e33  xor     eax, eax
0x180009e35  mov     [rbp+pStr], r12
0x180009e39  lea     rdx, [rbp+var_40]; struct CCredentials *
0x180009e3d  mov     [rbp+var_8], rax
0x180009e41  mov     rcx, rbx; struct IUnknown *
0x180009e44  mov     edi, r12d
0x180009e47  movups  xmmword ptr [rbp+var_28], xmm0
0x180009e4b  mov     r14d, r12d
0x180009e4e  movups  [rbp+var_18], xmm0
0x180009e52  call    ?AllocateServerObject@CIISServer@@SAJPEAUIUnknown@@AEAVCCredentials@@PEAPEAV1@@Z; CIISServer::AllocateServerObject(IUnknown *,CCredentials &,CIISServer * *)
0x180009e57  mov     rsi, [rbp+Block]
0x180009e5b  mov     ebx, eax
0x180009e5d  test    eax, eax
0x180009e5f  js      loc_180009FA1
0x180009e65  mov     rcx, [rsi+38h]
0x180009e69  lea     rdx, [rbp+pStr]
0x180009e6d  mov     rax, [rcx]
0x180009e70  mov     rax, [rax+50h]
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  mov     ebx, eax
0x180009e7b  test    eax, eax
0x180009e7d  js      loc_180009FA1
0x180009e83  lea     ecx, [r12+20h]; Size
0x180009e88  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009e8d  mov     rdi, rax
0x180009e90  test    rax, rax
0x180009e93  jz      loc_180009F99
0x180009e99  mov     [rax], r12
0x180009e9c  mov     rcx, rax; this
0x180009e9f  mov     [rax+8], r12
0x180009ea3  mov     [rax+10h], r12
0x180009ea7  mov     [rax+18h], r12
0x180009eab  mov     rdx, [rbp+pStr]; unsigned __int16 *
0x180009eaf  call    ?Initialize@CLexer@@QEAAJPEAG@Z; CLexer::Initialize(ushort *)
0x180009eb4  mov     ebx, eax
0x180009eb6  test    eax, eax
0x180009eb8  js      loc_180009FA1
0x180009ebe  lea     rdx, [rbp+var_28]; struct _objectinfo *
0x180009ec2  mov     rcx, rdi; this
0x180009ec5  call    ?ADsObject@@YAJPEAVCLexer@@PEAU_objectinfo@@@Z; ADsObject(CLexer *,_objectinfo *)
0x180009eca  mov     ebx, eax
0x180009ecc  test    eax, eax
0x180009ece  js      loc_180009FA1
0x180009ed4  mov     rcx, [rbp+pStr]; pStr
0x180009ed8  call    cs:__imp_AllocADsStr
0x180009ede  mov     r14, rax
0x180009ee1  test    rax, rax
0x180009ee4  jz      loc_180009F9C
0x180009eea  or      r8, 0FFFFFFFFFFFFFFFFh
0x180009eee  inc     r8
0x180009ef1  cmp     [rax+r8*2], r12w
0x180009ef6  jnz     short loc_180009EEE
0x180009ef8  inc     r8; unsigned __int64
0x180009efb  mov     [rax], r12w
0x180009eff  mov     rdx, r14; unsigned __int16 *
0x180009f02  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180009f06  call    ?BuildIISPathFromADsPath@@YAJPEAU_objectinfo@@PEAG_K@Z; BuildIISPathFromADsPath(_objectinfo *,ushort *,unsigned __int64)
0x180009f0b  mov     ebx, eax
0x180009f0d  test    eax, eax
0x180009f0f  js      loc_180009FA1
0x180009f15  mov     rbx, [rbp+var_28+8]
0x180009f19  test    rbx, rbx
0x180009f1c  jz      short loc_180009F30
0x180009f1e  mov     rcx, rbx; pStr
0x180009f21  call    cs:__imp_AllocADsStr
0x180009f27  mov     [rsi+40h], rax
0x180009f2b  test    rax, rax
0x180009f2e  jz      short loc_180009F9C
0x180009f30  mov     rcx, r14; pStr
0x180009f33  call    cs:__imp_AllocADsStr
0x180009f39  mov     [rsi+48h], rax
0x180009f3d  test    rax, rax
0x180009f40  jz      short loc_180009F9C
0x180009f42  lea     rdx, [rsi+78h]; struct IMSAdminBaseW **
0x180009f46  mov     rcx, rbx; unsigned __int16 *
0x180009f49  call    ?InitServerInfo@@YAJPEAGPEAPEAUIMSAdminBaseW@@@Z; InitServerInfo(ushort *,IMSAdminBaseW * *)
0x180009f4e  mov     ebx, eax
0x180009f50  test    eax, eax
0x180009f52  js      short loc_180009FA1
0x180009f54  lea     rcx, [rsi+20h]
0x180009f58  neg     rsi
0x180009f5b  sbb     rax, rax
0x180009f5e  and     rax, rcx
0x180009f61  mov     rcx, [rbp+pStr]; bstrString
0x180009f65  mov     [r15], rax
0x180009f68  test    rcx, rcx
0x180009f6b  jz      short loc_180009F73
0x180009f6d  call    cs:__imp_SysFreeString
0x180009f73  mov     rcx, [rdi+8]; pStr
0x180009f77  call    cs:__imp_FreeADsStr
0x180009f7d  mov     rcx, rdi; Block
0x180009f80  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009f85  mov     rcx, r14; pStr
0x180009f88  call    cs:__imp_FreeADsStr
0x180009f8e  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180009f92  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180009f97  jmp     short loc_180009FF6
0x180009f99  mov     rdi, r12
0x180009f9c  mov     ebx, 8007000Eh
0x180009fa1  mov     rcx, [rbp+pStr]; bstrString
0x180009fa5  test    rcx, rcx
0x180009fa8  jz      short loc_180009FB0
0x180009faa  call    cs:__imp_SysFreeString
0x180009fb0  test    rdi, rdi
0x180009fb3  jz      short loc_180009FC7
0x180009fb5  mov     rcx, [rdi+8]; pStr
0x180009fb9  call    cs:__imp_FreeADsStr
0x180009fbf  mov     rcx, rdi; Block
0x180009fc2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009fc7  test    r14, r14
0x180009fca  jz      short loc_180009FD5
0x180009fcc  mov     rcx, r14; pStr
0x180009fcf  call    cs:__imp_FreeADsStr
0x180009fd5  lea     rcx, [rbp+var_28]; struct _objectinfo *
0x180009fd9  call    ?FreeObjectInfo@@YAXPEAU_objectinfo@@@Z; FreeObjectInfo(_objectinfo *)
0x180009fde  mov     [r15], r12
0x180009fe1  test    rsi, rsi
0x180009fe4  jz      short loc_180009FF6
0x180009fe6  mov     rcx, rsi; this
0x180009fe9  call    ??1CIISServer@@QEAA@XZ; CIISServer::~CIISServer(void)
0x180009fee  mov     rcx, rsi; Block
0x180009ff1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009ff6  lea     rcx, [rbp+var_40]; unsigned __int16 **
0x180009ffa  call    ?FreeUserName@CCredentials@@CAXAEAPEAG@Z; CCredentials::FreeUserName(ushort * &)
0x180009fff  lea     rdx, [rbp+var_2C]; unsigned int *
0x18000a003  lea     rcx, [rbp+var_38]; unsigned __int16 **
0x18000a007  call    ?FreePassword@CCredentials@@CAXAEAPEAGAEAK@Z; CCredentials::FreePassword(ushort * &,ulong &)
0x18000a00c  lea     r11, [rsp+60h+var_s0]
0x18000a011  mov     eax, ebx
0x18000a013  mov     rbx, [r11+30h]
0x18000a017  mov     rsi, [r11+40h]
0x18000a01b  mov     rsp, r11
0x18000a01e  pop     r15
0x18000a020  pop     r14
0x18000a022  pop     r12
0x18000a024  pop     rdi
0x18000a025  pop     rbp
0x18000a026  retn
```
