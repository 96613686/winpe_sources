# NameTbl::InvokeDef(long,ulong,tagDISPPARAMS *,tagVARIANT *,IServiceProvider *)

- ea: `0x180002ba8`
- end: `0x18000311d`
- name: `?InvokeDef@NameTbl@@IEAAJJKPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUIServiceProvider@@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(struct CSession **this, int, __int16, struct tagDISPPARAMS *, struct tagVARIANT *, struct IServiceProvider *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x1800105a0`

## callees

- `0x180002ba8`
- `0x180003124`
- `0x180003340`
- `0x180003398`
- `0x180004d40`
- `0x18000826c`
- `0x18001128c`
- `0x18001192c`
- `0x1800132f8`
- `0x180013574`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!_ltow` at `0x180003073`
- `msvcrt!_ltow` at `0x180003073`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003042`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x180003042`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003109`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x180003109`

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
  struct tagVARIANT *rgvarg; // rbx
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
0x180002ba8  mov     r11, rsp
0x180002bab  mov     [r11+10h], rbx
0x180002baf  mov     [r11+18h], rsi
0x180002bb3  push    rdi
0x180002bb4  push    r12
0x180002bb6  push    r13
0x180002bb8  push    r14
0x180002bba  push    r15
0x180002bbc  sub     rsp, 130h
0x180002bc3  mov     rax, cs:__security_cookie
0x180002bca  xor     rax, rsp
0x180002bcd  mov     [rsp+158h+var_30], rax
0x180002bd5  mov     rbx, r9
0x180002bd8  mov     [rsp+158h+var_114], r8d
0x180002bdd  mov     r9d, edx
0x180002be0  mov     rdi, rcx
0x180002be3  mov     rsi, [rsp+158h+arg_20]
0x180002beb  xorps   xmm0, xmm0
0x180002bee  xor     eax, eax
0x180002bf0  movups  [rsp+158h+var_F0], xmm0
0x180002bf5  mov     [rsp+158h+var_E0], rax
0x180002bfa  xorps   xmm1, xmm1
0x180002bfd  movups  [rsp+158h+var_88], xmm1
0x180002c05  mov     [r11-78h], rax
0x180002c09  xor     r13d, r13d
0x180002c0c  mov     qword ptr [rsp+158h+rgsabound.cElements], r13
0x180002c11  test    r8b, 0Ch
0x180002c15  jnz     loc_180002FC9
0x180002c1b  mov     ecx, [rbx+14h]
0x180002c1e  test    ecx, ecx
0x180002c20  jnz     loc_180002EF7
0x180002c26  mov     r14, rbx
0x180002c29  cmp     [r14+14h], r13d
0x180002c2d  jnz     loc_180002FC9
0x180002c33  cmp     r9d, 0FFFFF574h
0x180002c3a  jz      loc_180002FBD
0x180002c40  test    r9d, r9d
0x180002c43  jnz     loc_180002FC9
0x180002c49  cmp     [r14+10h], r13d
0x180002c4d  jz      loc_180002F36
0x180002c53  test    r8d, 4001h
0x180002c5a  jz      loc_180002FB3
0x180002c60  mov     rax, [rdi]
0x180002c63  mov     rcx, rdi
0x180002c66  mov     rax, [rax+138h]
0x180002c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c72  test    eax, eax
0x180002c74  jz      loc_180002FB3
0x180002c7a  mov     rax, [rdi+18h]
0x180002c7e  lock inc dword ptr [rax]
0x180002c81  mov     [rsp+158h+var_D0], rax
0x180002c89  xorps   xmm0, xmm0
0x180002c8c  movdqu  [rsp+158h+var_C8], xmm0
0x180002c95  mov     [rsp+158h+var_B8], r13
0x180002c9d  mov     r13, [rdi+18h]
0x180002ca1  mov     r15, [r13+438h]
0x180002ca8  mov     r12, [rsp+158h+arg_28]
0x180002cb0  mov     [r13+438h], r12
0x180002cb7  test    r12, r12
0x180002cba  jz      short loc_180002CCC
0x180002cbc  mov     rax, [r12]
0x180002cc0  mov     rcx, r12
0x180002cc3  mov     rax, [rax+8]
0x180002cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ccc  mov     rcx, [r13+430h]; this
0x180002cd3  test    rcx, rcx
0x180002cd6  jnz     loc_180002E5D
0x180002cdc  mov     rax, [r13+4D8h]
0x180002ce3  mov     [rsp+158h+var_D8], rax
0x180002ceb  mov     [r13+4D8h], r12
0x180002cf2  test    byte ptr [rsp+158h+var_114], 1
0x180002cf7  jnz     short loc_180002D76
0x180002cf9  xor     r9d, r9d; struct tagVARIANT *
0x180002cfc  mov     r8, [r14]; struct tagVARIANT *
0x180002cff  mov     edx, [r14+10h]; int
0x180002d03  lea     rcx, [rsp+158h+var_D0]; this
0x180002d0b  call    ?ImportRgvar@VarList@@QEAAJJPEAUtagVARIANT@@0@Z; VarList::ImportRgvar(long,tagVARIANT *,tagVARIANT *)
0x180002d10  mov     ebx, eax
0x180002d12  mov     [rsp+158h+var_118], eax
0x180002d16  test    eax, eax
0x180002d18  js      loc_180002E01
0x180002d1e  mov     rax, [rdi]
0x180002d21  mov     r9, qword ptr [rsp+158h+var_C8+8]
0x180002d29  mov     r8d, [r14+10h]
0x180002d2d  lea     rdx, [rsp+158h+var_70]
0x180002d35  mov     rcx, rdi
0x180002d38  mov     rax, [rax+130h]
0x180002d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d44  mov     ebx, eax
0x180002d46  mov     [rsp+158h+var_118], eax
0x180002d4a  test    eax, eax
0x180002d4c  js      loc_180002E01
0x180002d52  test    rsi, rsi
0x180002d55  jz      loc_180002E01
0x180002d5b  mov     rdx, rsi; struct tagVARIANT *
0x180002d5e  lea     rcx, [rsp+158h+var_70]; this
0x180002d66  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x180002d6b  mov     ebx, eax
0x180002d6d  mov     [rsp+158h+var_118], eax
0x180002d71  jmp     loc_180002E01
0x180002d76  cmp     rbx, r14
0x180002d79  jz      loc_180002EA2
0x180002d7f  mov     rbx, [rbx]
0x180002d82  test    rbx, rbx
0x180002d85  jnz     loc_180002E84
0x180002d8b  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStart.Data1
0x180002d92  movdqu  xmmword ptr [rsp+158h+var_A8.Data1], xmm0
0x180002d9b  mov     r8, rdi; unsigned __int64
0x180002d9e  lea     rdx, [rsp+158h+var_A8]; struct _GUID
0x180002da6  mov     rcx, [rdi+18h]; this
0x180002daa  call    ?FireDebugEvent@CSession@@QEAAJU_GUID@@_K@Z; CSession::FireDebugEvent(_GUID,unsigned __int64)
0x180002daf  mov     [rsp+158h+var_128], 0; unsigned int
0x180002db7  mov     [rsp+158h+var_130], rbx; struct tagVARIANT *
0x180002dbc  mov     rax, [r14]
0x180002dbf  mov     [rsp+158h+var_138], rax; struct tagVARIANT *
0x180002dc4  mov     r9d, [r14+10h]; int
0x180002dc8  mov     r8, rsi; struct tagVARIANT *
0x180002dcb  mov     rdx, rdi; struct NameTbl *
0x180002dce  mov     rcx, [rdi+18h]; this
0x180002dd2  call    ?Execute@CSession@@QEAAJPEAVNameTbl@@PEAUtagVARIANT@@H11K@Z; CSession::Execute(NameTbl *,tagVARIANT *,int,tagVARIANT *,tagVARIANT *,ulong)
0x180002dd7  mov     ebx, eax
0x180002dd9  mov     [rsp+158h+var_118], eax
0x180002ddd  movups  xmm0, xmmword ptr cs:GUID_ScriptFunctionStop.Data1
0x180002de4  movdqu  xmmword ptr [rsp+158h+var_98.Data1], xmm0
0x180002ded  mov     r8, rdi; unsigned __int64
0x180002df0  lea     rdx, [rsp+158h+var_98]; struct _GUID
0x180002df8  mov     rcx, [rdi+18h]; this
0x180002dfc  call    ?FireDebugEvent@CSession@@QEAAJU_GUID@@_K@Z; CSession::FireDebugEvent(_GUID,unsigned __int64)
0x180002e01  mov     rdi, [rdi+18h]
0x180002e05  mov     rsi, [rdi+438h]
0x180002e0c  mov     [rdi+438h], r15
0x180002e13  test    r15, r15
0x180002e16  jz      short loc_180002E27
0x180002e18  mov     rax, [r15]
0x180002e1b  mov     rcx, r15
0x180002e1e  mov     rax, [rax+8]
0x180002e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e27  mov     rcx, [rdi+430h]; this
0x180002e2e  test    rcx, rcx
0x180002e31  jnz     short loc_180002E72
0x180002e33  mov     rax, [rsp+158h+var_D8]
0x180002e3b  mov     [rdi+4D8h], rax
0x180002e42  test    r15, r15
0x180002e45  jnz     short loc_180002EA9
0x180002e47  test    rsi, rsi
0x180002e4a  jz      short loc_180002EBA
0x180002e4c  mov     rax, [rsi]
0x180002e4f  mov     rcx, rsi
0x180002e52  mov     rax, [rax+10h]
0x180002e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e5b  jmp     short loc_180002EBA
0x180002e5d  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x180002e62  mov     qword ptr [r13+430h], 0
0x180002e6d  jmp     loc_180002CDC
0x180002e72  call    ?Release@DexCaller@@UEAAKXZ; DexCaller::Release(void)
0x180002e77  mov     qword ptr [rdi+430h], 0
0x180002e82  jmp     short loc_180002E33
0x180002e84  movzx   ecx, word ptr [rbx]; int
0x180002e87  call    ?IsSpecialType@VAR@@SAHH@Z; VAR::IsSpecialType(int)
0x180002e8c  test    eax, eax
0x180002e8e  jz      loc_180002D8B
0x180002e94  mov     ebx, 80070057h
0x180002e99  mov     [rsp+158h+var_118], ebx
0x180002e9d  jmp     loc_180002E01
0x180002ea2  xor     ebx, ebx
0x180002ea4  jmp     loc_180002D82
0x180002ea9  mov     rax, [r15]
0x180002eac  mov     rcx, r15
0x180002eaf  mov     rax, [rax+10h]
0x180002eb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb8  jmp     short loc_180002E47
0x180002eba  lea     rcx, [rsp+158h+var_D0]; this
0x180002ec2  call    ?Close@VarList@@QEAAXXZ; VarList::Close(void)
0x180002ec7  mov     eax, ebx
0x180002ec9  mov     rcx, [rsp+158h+var_30]
0x180002ed1  xor     rcx, rsp; StackCookie
0x180002ed4  call    __security_check_cookie
0x180002ed9  lea     r11, [rsp+158h+var_28]
0x180002ee1  mov     rbx, [r11+38h]
0x180002ee5  mov     rsi, [r11+40h]
0x180002ee9  mov     rsp, r11
0x180002eec  pop     r15
0x180002eee  pop     r14
0x180002ef0  pop     r13
0x180002ef2  pop     r12
0x180002ef4  pop     rdi
0x180002ef5  retn
0x180002ef7  mov     rdx, [rbx+8]
0x180002efb  cmp     dword ptr [rdx], 0FFFFFD9Bh
0x180002f01  jnz     loc_180002C26
0x180002f07  mov     eax, [rbx+10h]
0x180002f0a  dec     eax
0x180002f0c  mov     dword ptr [rsp+158h+var_E0], eax
0x180002f10  mov     rax, [rbx]
0x180002f13  add     rax, 18h
0x180002f17  mov     qword ptr [rsp+158h+var_F0], rax
0x180002f1c  lea     eax, [rcx-1]
0x180002f1f  mov     dword ptr [rsp+158h+var_E0+4], eax
0x180002f23  lea     rax, [rdx+4]
0x180002f27  mov     qword ptr [rsp+158h+var_F0+8], rax
0x180002f2c  lea     r14, [rsp+158h+var_F0]
0x180002f31  jmp     loc_180002C29
0x180002f36  test    r8b, 2
0x180002f3a  jz      loc_180002C53
0x180002f40  test    rsi, rsi
0x180002f43  jnz     short loc_180002F7F
0x180002f45  mov     eax, 80004003h
0x180002f4a  jmp     loc_180002EC9
0x180002f4f  mov     rax, [rdi]
0x180002f52  lea     r8, [rsp+158h+var_108]
0x180002f57  lea     rdx, ?g_sym_length@@3USYM@@A; SYM g_sym_length
0x180002f5e  mov     rcx, rdi
0x180002f61  mov     rax, [rax+0E0h]
0x180002f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f6d  test    eax, eax
0x180002f6f  jz      short loc_180002FD3
0x180002f71  js      loc_180002EC9
0x180002f77  mov     r14d, r13d
0x180002f7a  jmp     loc_18000300E
0x180002f7f  mov     rax, [rdi]
0x180002f82  xor     r8d, r8d
0x180002f85  mov     rdx, rsi
0x180002f88  mov     rcx, rdi
0x180002f8b  mov     rax, [rax+88h]
0x180002f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f97  mov     ebx, eax
0x180002f99  test    eax, eax
0x180002f9b  js      loc_180002EC7
0x180002fa1  mov     rdx, rsi; struct tagVARIANT *
0x180002fa4  mov     rcx, rsi; this
0x180002fa7  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x180002fac  mov     ebx, eax
0x180002fae  jmp     loc_180002EC7
0x180002fb3  mov     ebx, 80020003h
0x180002fb8  jmp     loc_180002EC7
0x180002fbd  cmp     [r14+10h], r13d
0x180002fc1  jnz     short loc_180002FC9
0x180002fc3  test    r8b, 2
0x180002fc7  jnz     short loc_180002F4F
0x180002fc9  mov     eax, 80020003h
0x180002fce  jmp     loc_180002EC9
0x180002fd3  mov     dword ptr [rsp+158h+var_138], 1; int
0x180002fdb  mov     r9d, 3; int
0x180002fe1  lea     r8, [rsp+158h+var_108]; struct VAR *
0x180002fe6  lea     rdx, [rsp+158h+var_108]; this
0x180002feb  mov     rcx, [rdi+18h]; struct CSession *
0x180002fef  call    ?ConvertToScalar@@YAJPEAVCSession@@PEAVVAR@@1HH@Z; ConvertToScalar(CSession *,VAR *,VAR *,int,int)
0x180002ff4  test    eax, eax
0x180002ff6  js      loc_180002EC9
0x180002ffc  mov     r14d, dword ptr [rsp+158h+var_108+8]
0x180003001  cmp     r14d, 0F4240h
0x180003008  jg      loc_1800030FC
0x18000300e  test    rsi, rsi
0x180003011  jz      short loc_180003024
0x180003013  test    r14d, r14d
0x180003016  jnz     short loc_18000302B
0x180003018  mov     rbx, r13
0x18000301b  mov     word ptr [rsi], 200Ch
0x180003020  mov     [rsi+8], rbx
0x180003024  xor     eax, eax
0x180003026  jmp     loc_180002EC9
0x18000302b  mov     [rsp+158h+rgsabound.cElements], r14d
0x180003030  mov     [rsp+158h+rgsabound.lLbound], r13d
0x180003035  mov     ecx, 0Ch; vt
0x18000303a  lea     r8, [rsp+158h+rgsabound]; rgsabound
0x18000303f  lea     edx, [rcx-0Bh]; cDims
0x180003042  call    cs:__imp_SafeArrayCreate
0x180003049  nop     dword ptr [rax+rax+00h]
0x18000304e  mov     rbx, rax
0x180003051  test    rax, rax
0x180003054  jz      loc_1800030FC
0x18000305a  mov     r15d, r13d
0x18000305d  cmp     r15d, r14d
0x180003060  jge     short loc_18000301B
0x180003062  mov     r8d, 0Ah; Radix
0x180003068  lea     rdx, [rsp+158h+Buffer]; Buffer
0x180003070  mov     ecx, r15d; Value
0x180003073  call    cs:__imp__ltow
0x18000307a  nop     dword ptr [rax+rax+00h]
0x18000307f  mov     word ptr [rsp+158h+var_108], r13w
0x180003085  lea     rdx, [rsp+158h+Buffer]; unsigned __int16 *
0x18000308d  lea     rcx, [rsp+158h+var_88]; this
0x180003095  call    ?InitFromPsz@SYM@@QEAAPEAU1@PEBG@Z; SYM::InitFromPsz(ushort const *)
0x18000309a  mov     rcx, [rdi]
0x18000309d  mov     r9, [rcx+0E0h]
0x1800030a4  lea     r8, [rsp+158h+var_108]
0x1800030a9  mov     rdx, rax
0x1800030ac  mov     rcx, rdi
0x1800030af  mov     rax, r9
0x1800030b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b7  mov     r12d, eax
0x1800030ba  test    eax, eax
0x1800030bc  js      short loc_180003106
0x1800030be  lea     rdx, [rsp+158h+var_108]; struct tagVARIANT *
0x1800030c3  lea     rcx, [rsp+158h+var_108]; this
0x1800030c8  call    ?GetStdVar@VAR@@QEAAJPEAUtagVARIANT@@@Z; VAR::GetStdVar(tagVARIANT *)
0x1800030cd  mov     r12d, eax
0x1800030d0  test    eax, eax
0x1800030d2  js      short loc_180003106
0x1800030d4  movsxd  rax, r15d
  ... truncated ...
```
