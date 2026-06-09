# NameTbl::InvokeDef(long,ulong,tagDISPPARAMS *,tagVARIANT *,IServiceProvider *)

- ea: `0x180032b50`
- end: `0x1800330b2`
- name: `?InvokeDef@NameTbl@@IEAAJJKPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUIServiceProvider@@@Z`
- size: `1378`
- prototype: `__int64 __usercall@<rax>(NameTbl *__hidden this@<rcx>, int@<edx>, unsigned int@<r8d>, struct tagDISPPARAMS *@<r9>, struct tagVARIANT *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180013350`

## callees

- `0x18000b130`
- `0x180013f64`
- `0x1800145ec`
- `0x180016498`
- `0x180032b50`
- `0x1800330b8`
- `0x1800332d0`
- `0x180033328`
- `0x18003390c`
- `0x180033e0c`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!_ltow` at `0x180033014`
- `msvcrt!_ltow` at `0x180033014`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180032fe9`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180032fe9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800330a4`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800330a4`

## pseudocode

```c
__int64 __fastcall NameTbl::InvokeDef(
        struct CSession **this,
        int a2,
        __int16 a3,
        struct tagDISPPARAMS *a4,
        struct tagVARIANT *a5,
        struct IServiceProvider *a6)
{
  UINT cNamedArgs; // ecx
  struct tagDISPPARAMS *v10; // r14
  volatile signed __int32 *v11; // rax
  struct CSession *v12; // r13
  __int64 v13; // r15
  DexCaller *v14; // rcx
  int v15; // ebx
  VARIANTARG *rgvarg; // rbx
  struct CSession *v17; // rdi
  __int64 v18; // rsi
  DexCaller *v19; // rcx
  __int64 result; // rax
  DISPID *rgdispidNamedArgs; // rdx
  LONG lVal; // r14d
  SAFEARRAY *v23; // rbx
  int i; // r15d
  struct SYM *v25; // rax
  int StdVar; // r12d
  char v27; // [rsp+44h] [rbp-114h]
  SAFEARRAYBOUND rgsabound; // [rsp+48h] [rbp-110h] BYREF
  struct tagVARIANT v29; // [rsp+50h] [rbp-108h] BYREF
  __int128 v30; // [rsp+68h] [rbp-F0h] BYREF
  __int64 v31; // [rsp+78h] [rbp-E0h]
  __int64 v32; // [rsp+80h] [rbp-D8h]
  volatile signed __int32 *v33; // [rsp+88h] [rbp-D0h] BYREF
  __int128 v34; // [rsp+90h] [rbp-C8h]
  __int64 v35; // [rsp+A0h] [rbp-B8h]
  struct _GUID v36; // [rsp+B0h] [rbp-A8h] BYREF
  struct _GUID v37; // [rsp+C0h] [rbp-98h] BYREF
  __int128 v38; // [rsp+D0h] [rbp-88h] BYREF
  __int64 v39; // [rsp+E0h] [rbp-78h]
  _BYTE v40[24]; // [rsp+E8h] [rbp-70h] BYREF
  wchar_t Buffer[20]; // [rsp+100h] [rbp-58h] BYREF

  v27 = a3;
  v30 = 0;
  v31 = 0;
  v38 = 0;
  v39 = 0;
  rgsabound = 0;
  if ( (a3 & 0xC) != 0 )
    return 2147614723LL;
  cNamedArgs = a4->cNamedArgs;
  if ( cNamedArgs && (rgdispidNamedArgs = a4->rgdispidNamedArgs, *rgdispidNamedArgs == -613) )
  {
    LODWORD(v31) = a4->cArgs - 1;
    *(_QWORD *)&v30 = a4->rgvarg + 1;
    HIDWORD(v31) = cNamedArgs - 1;
    *((_QWORD *)&v30 + 1) = rgdispidNamedArgs + 1;
    v10 = (struct tagDISPPARAMS *)&v30;
  }
  else
  {
    v10 = a4;
  }
  if ( v10->cNamedArgs )
    return 2147614723LL;
  if ( a2 == -2700 )
  {
    if ( v10->cArgs || (a3 & 2) == 0 )
      return 2147614723LL;
    result = (*((__int64 (__fastcall **)(struct CSession **, wchar_t **, struct tagVARIANT *))*this + 28))(
               this,
               &g_sym_length,
               &v29);
    if ( (_DWORD)result )
    {
      if ( (int)result < 0 )
        return result;
      lVal = 0;
    }
    else
    {
      result = ConvertToScalar(this[3], (struct VAR *)&v29, (struct VAR *)&v29, 3, 1);
      if ( (int)result < 0 )
        return result;
      lVal = v29.lVal;
      if ( v29.lVal > 1000000 )
        return 2147942414LL;
    }
    if ( !a5 )
      return 0;
    if ( !lVal )
    {
      v23 = 0;
LABEL_56:
      a5->vt = 8204;
      a5->llVal = (LONGLONG)v23;
      return 0;
    }
    rgsabound.cElements = lVal;
    rgsabound.lLbound = 0;
    v23 = SafeArrayCreate(0xCu, 1u, &rgsabound);
    if ( v23 )
    {
      for ( i = 0; i < lVal; ++i )
      {
        _ltow(i, Buffer, 10);
        v29.vt = 0;
        v25 = SYM::InitFromPsz((SYM *)&v38, Buffer);
        StdVar = (*((__int64 (__fastcall **)(struct CSession **, struct SYM *, struct tagVARIANT *))*this + 28))(
                   this,
                   v25,
                   &v29);
        if ( StdVar < 0 || (StdVar = VAR::GetStdVar((VAR *)&v29, &v29), StdVar < 0) )
        {
          SafeArrayDestroy(v23);
          return (unsigned int)StdVar;
        }
        *((struct tagVARIANT *)v23->pvData + i) = v29;
      }
      goto LABEL_56;
    }
    return 2147942414LL;
  }
  if ( a2 )
    return 2147614723LL;
  if ( v10->cArgs || (a3 & 2) == 0 )
  {
    if ( (a3 & 0x4001) != 0 && (*((unsigned int (__fastcall **)(struct CSession **))*this + 39))(this) )
    {
      v11 = (volatile signed __int32 *)this[3];
      _InterlockedIncrement(v11);
      v33 = v11;
      v34 = 0;
      v35 = 0;
      v12 = this[3];
      v13 = *((_QWORD *)v12 + 135);
      *((_QWORD *)v12 + 135) = a6;
      if ( a6 )
        ((void (__fastcall *)(struct IServiceProvider *))a6->lpVtbl->AddRef)(a6);
      v14 = (DexCaller *)*((_QWORD *)v12 + 134);
      if ( v14 )
      {
        DexCaller::Release(v14);
        *((_QWORD *)v12 + 134) = 0;
      }
      v32 = *((_QWORD *)v12 + 155);
      *((_QWORD *)v12 + 155) = a6;
      if ( (v27 & 1) != 0 )
      {
        if ( a4 == v10 )
          rgvarg = 0;
        else
          rgvarg = a4->rgvarg;
        if ( rgvarg && (unsigned int)VAR::IsSpecialType(rgvarg->vt) )
        {
          v15 = -2147024809;
        }
        else
        {
          v36 = GUID_ScriptFunctionStart;
          CSession::FireDebugEvent(this[3], &v36, (unsigned __int64)this);
          v15 = CSession::Execute(this[3], (struct NameTbl *)this, a5, v10->cArgs, v10->rgvarg, rgvarg, 0);
          v37 = GUID_ScriptFunctionStop;
          CSession::FireDebugEvent(this[3], &v37, (unsigned __int64)this);
        }
      }
      else
      {
        v15 = VarList::ImportRgvar((VarList *)&v33, v10->cArgs, v10->rgvarg, 0);
        if ( v15 >= 0 )
        {
          v15 = (*((__int64 (__fastcall **)(struct CSession **, _BYTE *, _QWORD, _QWORD))*this + 38))(
                  this,
                  v40,
                  v10->cArgs,
                  *((_QWORD *)&v34 + 1));
          if ( v15 >= 0 )
          {
            if ( a5 )
              v15 = VAR::GetStdVar((VAR *)v40, a5);
          }
        }
      }
      v17 = this[3];
      v18 = *((_QWORD *)v17 + 135);
      *((_QWORD *)v17 + 135) = v13;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v19 = (DexCaller *)*((_QWORD *)v17 + 134);
      if ( v19 )
      {
        DexCaller::Release(v19);
        *((_QWORD *)v17 + 134) = 0;
      }
      *((_QWORD *)v17 + 155) = v32;
      if ( v13 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      VarList::Close((VarList *)&v33);
    }
    else
    {
      return (unsigned int)-2147352573;
    }
  }
  else
  {
    if ( !a5 )
      return 2147500035LL;
    v15 = (*((__int64 (__fastcall **)(struct CSession **, struct tagVARIANT *, _QWORD))*this + 17))(this, a5, 0);
    if ( v15 >= 0 )
      return (unsigned int)VAR::GetStdVar((VAR *)a5, a5);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180032b50  mov     r11, rsp
0x180032b53  mov     [r11+10h], rbx
0x180032b57  mov     [r11+18h], rsi
0x180032b5b  push    rdi
0x180032b5c  push    r12
0x180032b5e  push    r13
0x180032b60  push    r14
0x180032b62  push    r15
0x180032b64  sub     rsp, 130h
0x180032b6b  mov     rax, cs:__security_cookie
0x180032b72  xor     rax, rsp
0x180032b75  mov     [rsp+158h+var_30], rax
0x180032b7d  mov     rbx, r9
0x180032b80  mov     [rsp+158h+var_114], r8d
0x180032b85  mov     r9d, edx
0x180032b88  mov     rdi, rcx
0x180032b8b  mov     rsi, [rsp+158h+arg_20]
0x180032b93  xorps   xmm0, xmm0
0x180032b96  xor     eax, eax
0x180032b98  movups  [rsp+158h+var_F0], xmm0
0x180032b9d  mov     [rsp+158h+var_E0], rax
0x180032ba2  xorps   xmm1, xmm1
0x180032ba5  movups  [rsp+158h+var_88], xmm1
0x180032bad  mov     [r11-78h], rax
0x180032bb1  xor     r13d, r13d
0x180032bb4  mov     qword ptr [rsp+158h+rgsabound.cElements], r13
0x180032bb9  test    r8b, 0Ch
0x180032bbd  jnz     loc_180032F70
0x180032bc3  mov     ecx, [rbx+14h]
0x180032bc6  test    ecx, ecx
0x180032bc8  jnz     loc_180032E9E
0x180032bce  mov     r14, rbx
0x180032bd1  cmp     [r14+14h], r13d
0x180032bd5  jnz     loc_180032F70
0x180032bdb  cmp     r9d, 0FFFFF574h
0x180032be2  jz      loc_180032F64
0x180032be8  test    r9d, r9d
0x180032beb  jnz     loc_180032F70
0x180032bf1  cmp     [r14+10h], r13d
0x180032bf5  jz      loc_180032EDD
0x180032bfb  test    r8d, 4001h
0x180032c02  jz      loc_180032F5A
0x180032c08  mov     rax, [rdi]
0x180032c0b  mov     rcx, rdi
0x180032c0e  mov     rax, [rax+138h]
0x180032c15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c1a  test    eax, eax
0x180032c1c  jz      loc_180032F5A
0x180032c22  mov     rax, [rdi+18h]
0x180032c26  lock inc dword ptr [rax]
0x180032c29  mov     [rsp+158h+var_D0], rax
0x180032c31  xorps   xmm0, xmm0
0x180032c34  movdqu  [rsp+158h+var_C8], xmm0
0x180032c3d  mov     [rsp+158h+var_B8], r13
0x180032c45  mov     r13, [rdi+18h]
0x180032c49  mov     r15, [r13+438h]
0x180032c50  mov     r12, [rsp+158h+arg_28]
0x180032c58  mov     [r13+438h], r12
0x180032c5f  test    r12, r12
0x180032c62  jz      short loc_180032C74
0x180032c64  mov     rax, [r12]
0x180032c68  mov     rcx, r12
0x180032c6b  mov     rax, [rax+8]
0x180032c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032c74  mov     rcx, [r13+430h]; this
0x180032c7b  test    rcx, rcx
0x180032c7e  jnz     loc_180032E05
0x180032c84  mov     rax, [r13+4D8h]
0x180032c8b  mov     [rsp+158h+var_D8], rax
0x180032c93  mov     [r13+4D8h], r12
0x180032c9a  test    byte ptr [rsp+158h+var_114], 1
0x180032c9f  jnz     short loc_180032D1E
0x180032ca1  xor     r9d, r9d; struct tagVARIANT *
0x180032ca4  mov     r8, [r14]; struct tagVARIANT *
0x180032ca7  mov     edx, [r14+10h]; int
0x180032cab  lea     rcx, [rsp+158h+var_D0]; this
0x180032cb3  call    ?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z; VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)
0x180032cb8  mov     ebx, eax
0x180032cba  mov     [rsp+158h+var_118], eax
0x180032cbe  test    eax, eax
0x180032cc0  js      loc_180032DA9
0x180032cc6  mov     rax, [rdi]
0x180032cc9  mov     r9, qword ptr [rsp+158h+var_C8+8]
0x180032cd1  mov     r8d, [r14+10h]
0x180032cd5  lea     rdx, [rsp+158h+var_70]
0x180032cdd  mov     rcx, rdi
0x180032ce0  mov     rax, [rax+130h]
0x180032ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032cec  mov     ebx, eax
0x180032cee  mov     [rsp+158h+var_118], eax
0x180032cf2  test    eax, eax
0x180032cf4  js      loc_180032DA9
0x180032cfa  test    rsi, rsi
0x180032cfd  jz      loc_180032DA9
0x180032d03  mov     rdx, rsi; struct tagVARIANT *
0x180032d06  lea     rcx, [rsp+158h+var_70]; this
0x180032d0e  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x180032d13  mov     ebx, eax
0x180032d15  mov     [rsp+158h+var_118], eax
0x180032d19  jmp     loc_180032DA9
0x180032d1e  cmp     rbx, r14
0x180032d21  jz      loc_180032E4A
0x180032d27  mov     rbx, [rbx]
0x180032d2a  test    rbx, rbx
0x180032d2d  jnz     loc_180032E2C
0x180032d33  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStart.Data1
0x180032d3a  movdqu  xmmword ptr [rsp+158h+var_A8.Data1], xmm0
0x180032d43  mov     r8, rdi; unsigned __int64
0x180032d46  lea     rdx, [rsp+158h+var_A8]; struct _GUID
0x180032d4e  mov     rcx, [rdi+18h]; this
0x180032d52  call    ?FireDebugEvent@CSession@@QEAAJU_GUID@@_K@Z; CSession::FireDebugEvent(_GUID,unsigned __int64)
0x180032d57  mov     [rsp+158h+var_128], 0; unsigned int
0x180032d5f  mov     [rsp+158h+var_130], rbx; struct tagVARIANT *
0x180032d64  mov     rax, [r14]
0x180032d67  mov     [rsp+158h+var_138], rax; struct tagVARIANT *
0x180032d6c  mov     r9d, [r14+10h]; int
0x180032d70  mov     r8, rsi; struct tagVARIANT *
0x180032d73  mov     rdx, rdi; struct NameTbl *
0x180032d76  mov     rcx, [rdi+18h]; this
0x180032d7a  call    ?Execute@CSession@@QEAAJPEAVNameTbl@@PEAUtagVARIANT@@H11K@Z; CSession::Execute(NameTbl *,tagVARIANT *,int,tagVARIANT *,tagVARIANT *,ulong)
0x180032d7f  mov     ebx, eax
0x180032d81  mov     [rsp+158h+var_118], eax
0x180032d85  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStop.Data1
0x180032d8c  movdqu  xmmword ptr [rsp+158h+var_98.Data1], xmm0
0x180032d95  mov     r8, rdi; unsigned __int64
0x180032d98  lea     rdx, [rsp+158h+var_98]; struct _GUID
0x180032da0  mov     rcx, [rdi+18h]; this
0x180032da4  call    ?FireDebugEvent@CSession@@QEAAJU_GUID@@_K@Z; CSession::FireDebugEvent(_GUID,unsigned __int64)
0x180032da9  mov     rdi, [rdi+18h]
0x180032dad  mov     rsi, [rdi+438h]
0x180032db4  mov     [rdi+438h], r15
0x180032dbb  test    r15, r15
0x180032dbe  jz      short loc_180032DCF
0x180032dc0  mov     rax, [r15]
0x180032dc3  mov     rcx, r15
0x180032dc6  mov     rax, [rax+8]
0x180032dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dcf  mov     rcx, [rdi+430h]; this
0x180032dd6  test    rcx, rcx
0x180032dd9  jnz     short loc_180032E1A
0x180032ddb  mov     rax, [rsp+158h+var_D8]
0x180032de3  mov     [rdi+4D8h], rax
0x180032dea  test    r15, r15
0x180032ded  jnz     short loc_180032E51
0x180032def  test    rsi, rsi
0x180032df2  jz      short loc_180032E62
0x180032df4  mov     rax, [rsi]
0x180032df7  mov     rcx, rsi
0x180032dfa  mov     rax, [rax+10h]
0x180032dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e03  jmp     short loc_180032E62
0x180032e05  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x180032e0a  mov     qword ptr [r13+430h], 0
0x180032e15  jmp     loc_180032C84
0x180032e1a  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x180032e1f  mov     qword ptr [rdi+430h], 0
0x180032e2a  jmp     short loc_180032DDB
0x180032e2c  movzx   ecx, word ptr [rbx]; int
0x180032e2f  call    ?IsSpecialType@VAR@@SAHH@Z; VAR::IsSpecialType(int)
0x180032e34  test    eax, eax
0x180032e36  jz      loc_180032D33
0x180032e3c  mov     ebx, 80070057h
0x180032e41  mov     [rsp+158h+var_118], ebx
0x180032e45  jmp     loc_180032DA9
0x180032e4a  xor     ebx, ebx
0x180032e4c  jmp     loc_180032D2A
0x180032e51  mov     rax, [r15]
0x180032e54  mov     rcx, r15
0x180032e57  mov     rax, [rax+10h]
0x180032e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e60  jmp     short loc_180032DEF
0x180032e62  lea     rcx, [rsp+158h+var_D0]; this
0x180032e6a  call    ?Close@VarList@@QEAAXXZ; VarList::Close(void)
0x180032e6f  mov     eax, ebx
0x180032e71  mov     rcx, [rsp+158h+var_30]
0x180032e79  xor     rcx, rsp; StackCookie
0x180032e7c  call    __security_check_cookie
0x180032e81  lea     r11, [rsp+158h+var_28]
0x180032e89  mov     rbx, [r11+38h]
0x180032e8d  mov     rsi, [r11+40h]
0x180032e91  mov     rsp, r11
0x180032e94  pop     r15
0x180032e96  pop     r14
0x180032e98  pop     r13
0x180032e9a  pop     r12
0x180032e9c  pop     rdi
0x180032e9d  retn
0x180032e9e  mov     rdx, [rbx+8]
0x180032ea2  cmp     dword ptr [rdx], 0FFFFFD9Bh
0x180032ea8  jnz     loc_180032BCE
0x180032eae  mov     eax, [rbx+10h]
0x180032eb1  dec     eax
0x180032eb3  mov     dword ptr [rsp+158h+var_E0], eax
0x180032eb7  mov     rax, [rbx]
0x180032eba  add     rax, 18h
0x180032ebe  mov     qword ptr [rsp+158h+var_F0], rax
0x180032ec3  lea     eax, [rcx-1]
0x180032ec6  mov     dword ptr [rsp+158h+var_E0+4], eax
0x180032eca  lea     rax, [rdx+4]
0x180032ece  mov     qword ptr [rsp+158h+var_F0+8], rax
0x180032ed3  lea     r14, [rsp+158h+var_F0]
0x180032ed8  jmp     loc_180032BD1
0x180032edd  test    r8b, 2
0x180032ee1  jz      loc_180032BFB
0x180032ee7  test    rsi, rsi
0x180032eea  jnz     short loc_180032F26
0x180032eec  mov     eax, 80004003h
0x180032ef1  jmp     loc_180032E71
0x180032ef6  mov     rax, [rdi]
0x180032ef9  lea     r8, [rsp+158h+var_108]
0x180032efe  lea     rdx, ?g_sym_length@@3USYM@@A; SYM g_sym_length
0x180032f05  mov     rcx, rdi
0x180032f08  mov     rax, [rax+0E0h]
0x180032f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f14  test    eax, eax
0x180032f16  jz      short loc_180032F7A
0x180032f18  js      loc_180032E71
0x180032f1e  mov     r14d, r13d
0x180032f21  jmp     loc_180032FB5
0x180032f26  mov     rax, [rdi]
0x180032f29  xor     r8d, r8d
0x180032f2c  mov     rdx, rsi
0x180032f2f  mov     rcx, rdi
0x180032f32  mov     rax, [rax+88h]
0x180032f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f3e  mov     ebx, eax
0x180032f40  test    eax, eax
0x180032f42  js      loc_180032E6F
0x180032f48  mov     rdx, rsi; struct tagVARIANT *
0x180032f4b  mov     rcx, rsi; this
0x180032f4e  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x180032f53  mov     ebx, eax
0x180032f55  jmp     loc_180032E6F
0x180032f5a  mov     ebx, 80020003h
0x180032f5f  jmp     loc_180032E6F
0x180032f64  cmp     [r14+10h], r13d
0x180032f68  jnz     short loc_180032F70
0x180032f6a  test    r8b, 2
0x180032f6e  jnz     short loc_180032EF6
0x180032f70  mov     eax, 80020003h
0x180032f75  jmp     loc_180032E71
0x180032f7a  mov     dword ptr [rsp+158h+var_138], 1; int
0x180032f82  mov     r9d, 3; int
0x180032f88  lea     r8, [rsp+158h+var_108]; struct VAR *
0x180032f8d  lea     rdx, [rsp+158h+var_108]; this
0x180032f92  mov     rcx, [rdi+18h]; struct CSession *
0x180032f96  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x180032f9b  test    eax, eax
0x180032f9d  js      loc_180032E71
0x180032fa3  mov     r14d, dword ptr [rsp+158h+var_108+8]
0x180032fa8  cmp     r14d, 0F4240h
0x180032faf  jg      loc_180033097
0x180032fb5  test    rsi, rsi
0x180032fb8  jz      short loc_180032FCB
0x180032fba  test    r14d, r14d
0x180032fbd  jnz     short loc_180032FD2
0x180032fbf  mov     rbx, r13
0x180032fc2  mov     word ptr [rsi], 200Ch
0x180032fc7  mov     [rsi+8], rbx
0x180032fcb  xor     eax, eax
0x180032fcd  jmp     loc_180032E71
0x180032fd2  mov     [rsp+158h+rgsabound.cElements], r14d
0x180032fd7  mov     [rsp+158h+rgsabound.lLbound], r13d
0x180032fdc  mov     ecx, 0Ch; vt
0x180032fe1  lea     r8, [rsp+158h+rgsabound]; rgsabound
0x180032fe6  lea     edx, [rcx-0Bh]; cDims
0x180032fe9  call    cs:__imp_SafeArrayCreate
0x180032fef  mov     rbx, rax
0x180032ff2  test    rax, rax
0x180032ff5  jz      loc_180033097
0x180032ffb  mov     r15d, r13d
0x180032ffe  cmp     r15d, r14d
0x180033001  jge     short loc_180032FC2
0x180033003  mov     r8d, 0Ah; Radix
0x180033009  lea     rdx, [rsp+158h+Buffer]; Buffer
0x180033011  mov     ecx, r15d; Value
0x180033014  call    cs:__imp__ltow
0x18003301a  mov     word ptr [rsp+158h+var_108], r13w
0x180033020  lea     rdx, [rsp+158h+Buffer]; unsigned __int16 *
0x180033028  lea     rcx, [rsp+158h+var_88]; this
0x180033030  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x180033035  mov     rcx, [rdi]
0x180033038  mov     r9, [rcx+0E0h]
0x18003303f  lea     r8, [rsp+158h+var_108]
0x180033044  mov     rdx, rax
0x180033047  mov     rcx, rdi
0x18003304a  mov     rax, r9
0x18003304d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033052  mov     r12d, eax
0x180033055  test    eax, eax
0x180033057  js      short loc_1800330A1
0x180033059  lea     rdx, [rsp+158h+var_108]; struct tagVARIANT *
0x18003305e  lea     rcx, [rsp+158h+var_108]; this
0x180033063  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x180033068  mov     r12d, eax
0x18003306b  test    eax, eax
0x18003306d  js      short loc_1800330A1
0x18003306f  movsxd  rax, r15d
0x180033072  lea     rcx, [rax+rax*2]
0x180033076  mov     rax, [rbx+10h]
  ... truncated ...
```
