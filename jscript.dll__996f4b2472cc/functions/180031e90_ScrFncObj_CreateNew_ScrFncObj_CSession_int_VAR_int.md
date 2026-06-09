# ScrFncObj::CreateNew(ScrFncObj * *,CSession *,int,VAR *,int)

- ea: `0x180031e90`
- end: `0x1800323c3`
- name: `?CreateNew@ScrFncObj@@SAJPEAPEAV1@PEAVCSession@@HPEAVVAR@@H@Z`
- size: `1331`
- prototype: `__int64 __fastcall(struct ScrFncObj **, struct CSession *, int, VARIANTARG *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800307e0`
- `0x180063200`

## callees

- `0x180007e9c`
- `0x18000b0e0`
- `0x180015514`
- `0x180016c84`
- `0x180017a54`
- `0x180018350`
- `0x18001868c`
- `0x1800309ec`
- `0x180031cc8`
- `0x180031e90`
- `0x1800323cc`
- `0x180032664`
- `0x1800326c0`
- `0x18003557c`
- `0x18004c014`
- `0x1800585d0`
- `0x1800798d4`
- `0x1800966aa`

## import_xrefs

- `msvcrt!free` at `0x1800321b7`
- `msvcrt!free` at `0x18003239b`
- `msvcrt!free` at `0x1800321b7`
- `msvcrt!free` at `0x18003239b`
- `OLEAUT32!__imp_SysFreeString` at `0x180032100`
- `OLEAUT32!__imp_SysFreeString` at `0x180032110`
- `OLEAUT32!__imp_SysFreeString` at `0x180032100`
- `OLEAUT32!__imp_SysFreeString` at `0x180032110`

## pseudocode

```c
__int64 __fastcall ScrFncObj::CreateNew(struct ScrFncObj **a1, struct CSession *a2, int a3, VARIANTARG *a4, int a5)
{
  COleScript *v5; // r12
  struct CScriptBody *v7; // rsi
  int v8; // edi
  VARIANTARG *v9; // rbx
  __int64 v10; // rcx
  _WORD *v11; // rdx
  int v12; // ecx
  int v13; // r14d
  VARIANTARG *v14; // r13
  int v15; // r8d
  int v16; // edx
  _WORD *v17; // rdi
  __int64 v18; // rcx
  int v19; // r8d
  int appended; // ebx
  const unsigned __int16 *v21; // rdx
  int v22; // r8d
  int v23; // r8d
  int v24; // edx
  _WORD *v25; // rdx
  __int64 v26; // rcx
  int v27; // r8d
  unsigned __int16 *v28; // rdi
  int v29; // eax
  int v30; // eax
  int v31; // r8d
  __int64 v32; // rax
  __int64 v33; // rax
  const unsigned __int16 *v35; // rdx
  int v36; // r8d
  ScrFncObj *v37; // rax
  struct ScrFncObj *v38; // rax
  void *Block; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v40; // [rsp+48h] [rbp-B8h]
  int v41; // [rsp+50h] [rbp-B0h]
  struct CScriptBody *v42; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  VARIANTARG v44; // [rsp+68h] [rbp-98h] BYREF
  struct CScriptBody *v45; // [rsp+80h] [rbp-80h] BYREF
  __int64 v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+98h] [rbp-68h]
  _BYTE v49[8]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagEXCEPINFO v50; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v51; // [rsp+F0h] [rbp-10h]
  BSTR bstrString; // [rsp+F8h] [rbp-8h]
  BSTR v53; // [rsp+100h] [rbp+0h]
  _BYTE v54[80]; // [rsp+110h] [rbp+10h] BYREF
  struct VAR *v56; // [rsp+178h] [rbp+78h] BYREF

  v5 = (COleScript *)*((_QWORD *)a2 + 5);
  v56 = 0;
  Block = 0;
  v7 = 0;
  v40 = 0;
  v41 = 0;
  v42 = 0;
  if ( !v5 )
  {
    appended = -2147418113;
LABEL_53:
    BuildString::Reset((BuildString *)&Block);
    return (unsigned int)appended;
  }
  if ( *((_DWORD *)v5 + 240) )
  {
    appended = -2146823255;
    goto LABEL_53;
  }
  v43 = *((_QWORD *)a2 + 10);
  if ( a3 < 1 )
  {
    v44.vt = 128;
    v44.llVal = (LONGLONG)&cbstrEmpty;
  }
  v8 = 1;
  v9 = &v44;
  if ( a3 >= 1 )
  {
    v8 = a3;
    v9 = a4;
  }
  if ( !(unsigned int)BuildString::FEnsureSpace((BuildString *)&Block, 19) )
    goto LABEL_67;
  v10 = SHIDWORD(v40);
  v11 = Block;
  *(_OWORD *)((char *)Block + 2 * SHIDWORD(v40)) = *(_OWORD *)L"function anonymous(";
  *(_OWORD *)&v11[v10 + 8] = *(_OWORD *)L" anonymous(";
  *(_QWORD *)&v11[v10 + 15] = *(_QWORD *)L"ous(";
  v12 = v10 + 19;
  HIDWORD(v40) = v12;
  if ( v11 )
    v11[v12] = 0;
  a5 = 0;
  v13 = 1;
  v14 = &v9[v8];
  while ( v13 < v8 )
  {
    v56 = (struct VAR *)&v14[-v13];
    appended = ConvertToString(a2, (struct IDispatch ***)&v56, &v44, 1);
    if ( appended < 0 )
      goto LABEL_35;
    v35 = (const unsigned __int16 *)*((_QWORD *)v56 + 1);
    v36 = v35 ? *((_DWORD *)v35 - 1) >> 1 : 0;
    appended = BuildString::AppendSz((BuildString *)&Block, v35, v36);
    if ( appended < 0 )
      goto LABEL_35;
    if ( v13 < v8 - 1 )
    {
      appended = BuildString::AppendSz((BuildString *)&Block, L", ", 2);
      if ( appended < 0 )
        goto LABEL_35;
    }
    ++v13;
  }
  v15 = HIDWORD(v40);
  v16 = HIDWORD(v40) + 4;
  v56 = (struct VAR *)&v14[-v8];
  if ( HIDWORD(v40) + 4 < SHIDWORD(v40) )
    goto LABEL_67;
  if ( v16 < (int)v40 )
    goto LABEL_14;
  if ( !(unsigned int)BuildString::FEnsureSpace((BuildString *)&Block, v16) )
  {
LABEL_67:
    appended = -2147024882;
    goto LABEL_35;
  }
  v15 = HIDWORD(v40);
LABEL_14:
  v17 = Block;
  v18 = v15;
  v19 = v15 + 4;
  HIDWORD(v40) = v19;
  *(_QWORD *)((char *)Block + 2 * v18) = *(_QWORD *)L") {\n";
  if ( v17 )
    v17[v19] = 0;
  appended = ConvertToString(a2, (struct IDispatch ***)&v56, &v44, 1);
  if ( appended < 0 )
    goto LABEL_36;
  v21 = (const unsigned __int16 *)*((_QWORD *)v56 + 1);
  if ( v21 )
    v22 = *((_DWORD *)v21 - 1) >> 1;
  else
    v22 = 0;
  appended = BuildString::AppendSz((BuildString *)&Block, v21, v22);
  if ( appended >= 0 )
  {
    v23 = HIDWORD(v40);
    v24 = HIDWORD(v40) + 2;
    if ( HIDWORD(v40) + 2 >= SHIDWORD(v40) )
    {
      if ( v24 < (int)v40 )
        goto LABEL_22;
      if ( (unsigned int)BuildString::FEnsureSpace((BuildString *)&Block, v24) )
      {
        v23 = HIDWORD(v40);
LABEL_22:
        v25 = Block;
        v26 = v23;
        v27 = v23 + 2;
        HIDWORD(v40) = v27;
        *(_DWORD *)((char *)Block + 2 * v26) = *(_DWORD *)L"\n}";
        if ( v25 )
          v25[v27] = 0;
        v28 = BuildString::PszReset((BuildString *)&Block);
        appended = COleScript::CheckDynamicCodeSafety(v5, v28);
        if ( appended < 0 )
          goto LABEL_31;
        memset_0(v49, 0, 0x50u);
        v51 = 0;
        bstrString = 0;
        v53 = 0;
        v29 = COleScript::Compile(v5, &v42, v28, 0, 0, 0, L"anonymous code", (struct CompileScriptException *)v49);
        a5 = v29;
        appended = v29;
        if ( v29 < 0 )
        {
          if ( v29 == -2040119292 )
          {
            CSession::RecordExcepInfoAndClear(a2, &v50, &a5);
            appended = a5;
          }
          CompileScriptException::~CompileScriptException((CompileScriptException *)v49);
          v7 = v42;
          goto LABEL_31;
        }
        SysFreeString(bstrString);
        SysFreeString(v53);
        ScriptException::~ScriptException((ScriptException *)v49);
        v30 = COleScript::FDebuggerEnabled(v5);
        v7 = v42;
        if ( !v30 || (appended = COleScript::DbgRegisterScriptBlock(v5, v42), appended >= 0) )
        {
          v31 = 0;
          if ( v43 )
            v31 = *(_DWORD *)(*(_QWORD *)(v43 + 56) + 24LL);
          v32 = *((_QWORD *)v7 + 8);
          if ( *(int *)(v32 + 28) <= 1 )
          {
            appended = -2146828237;
          }
          else
          {
            v33 = *(int *)(v32 + 24);
            v46 = *((_QWORD *)v7 + 9);
            v48 = v31;
            v45 = v7;
            v47 = v46 + *(int *)(v33 + v46 + 4);
            appended = CSession::GetTypeProto(a2, 3, (struct VAR *)v54);
            if ( appended >= 0 )
            {
              v37 = (ScrFncObj *)operator new(0xD8u);
              if ( v37 )
              {
                v38 = ScrFncObj::ScrFncObj(v37, a2, (struct FncInfo *)&v45, (struct VAR *)v54, 0);
                *a1 = v38;
                if ( v38 )
                  goto LABEL_31;
              }
              else
              {
                *a1 = 0;
              }
              appended = -2147024882;
            }
          }
        }
LABEL_31:
        if ( v28 )
          free(v28);
        if ( v7 )
          CScriptBody::Release(v7);
        goto LABEL_35;
      }
    }
    goto LABEL_67;
  }
LABEL_35:
  v17 = Block;
LABEL_36:
  if ( v17 )
    free(v17);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180031e90  mov     [rsp-8+arg_10], rbx
0x180031e95  mov     [rsp-8+arg_0], rcx
0x180031e9a  push    rbp
0x180031e9b  push    rsi
0x180031e9c  push    rdi
0x180031e9d  push    r12
0x180031e9f  push    r13
0x180031ea1  push    r14
0x180031ea3  push    r15
0x180031ea5  lea     rbp, [rsp-30h]
0x180031eaa  sub     rsp, 130h
0x180031eb1  mov     r12, [rdx+28h]
0x180031eb5  xor     r14d, r14d
0x180031eb8  mov     [rbp+60h+arg_8], r14
0x180031ebc  mov     r15, rdx
0x180031ebf  mov     [rsp+160h+Block], r14
0x180031ec4  mov     esi, r14d
0x180031ec7  mov     [rsp+160h+var_118], r14
0x180031ecc  mov     [rsp+160h+var_110], r14d
0x180031ed1  mov     [rsp+160h+var_108], r14
0x180031ed6  test    r12, r12
0x180031ed9  jz      loc_18003229C
0x180031edf  cmp     [r12+3C0h], r14d
0x180031ee7  jnz     loc_1800322A3
0x180031eed  mov     rax, [rdx+50h]
0x180031ef1  lea     ecx, [r14+1]
0x180031ef5  mov     [rsp+160h+var_100], rax
0x180031efa  cmp     r8d, ecx
0x180031efd  jl      loc_1800322B7
0x180031f03  mov     edi, ecx
0x180031f05  lea     rbx, [rsp+160h+var_F8]
0x180031f0a  lea     rcx, [rsp+160h+Block]; this
0x180031f0f  mov     edx, 13h; int
0x180031f14  cmovge  edi, r8d
0x180031f18  cmovge  rbx, r9
0x180031f1c  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180031f21  test    eax, eax
0x180031f23  jz      loc_1800323B9
0x180031f29  movsxd  rcx, dword ptr [rsp+160h+var_118+4]
0x180031f2e  mov     rdx, [rsp+160h+Block]
0x180031f33  movups  xmm0, xmmword ptr cs:aFunctionAnonym_0; "function anonymous("
0x180031f3a  movups  xmmword ptr [rdx+rcx*2], xmm0
0x180031f3e  movups  xmm1, xmmword ptr cs:aFunctionAnonym_0+10h; " anonymous("
0x180031f45  movups  xmmword ptr [rdx+rcx*2+10h], xmm1
0x180031f4a  movsd   xmm0, qword ptr cs:aFunctionAnonym_0+1Eh; "ous("
0x180031f52  movsd   qword ptr [rdx+rcx*2+1Eh], xmm0
0x180031f58  add     ecx, 13h
0x180031f5b  mov     dword ptr [rsp+160h+var_118+4], ecx
0x180031f5f  test    rdx, rdx
0x180031f62  jz      short loc_180031F6C
0x180031f64  movsxd  rcx, ecx
0x180031f67  mov     [rdx+rcx*2], r14w
0x180031f6c  movsxd  rax, edi
0x180031f6f  mov     [rbp+60h+arg_20], r14d
0x180031f76  mov     r14d, 1
0x180031f7c  lea     rcx, [rax+rax*2]
0x180031f80  lea     r13, [rbx+rcx*8]
0x180031f84  cmp     r14d, edi
0x180031f87  jl      loc_1800321E1
0x180031f8d  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x180031f92  neg     edi
0x180031f94  movsxd  rax, edi
0x180031f97  lea     edx, [r8+4]; int
0x180031f9b  lea     rcx, [rax+rax*2]
0x180031f9f  lea     rax, ds:0[rcx*8]
0x180031fa7  add     rax, r13
0x180031faa  mov     [rbp+60h+arg_8], rax
0x180031fae  cmp     edx, r8d
0x180031fb1  jl      loc_1800323B9
0x180031fb7  cmp     edx, dword ptr [rsp+160h+var_118]
0x180031fbb  jge     loc_180032254
0x180031fc1  xor     r14d, r14d
0x180031fc4  mov     rdi, [rsp+160h+Block]
0x180031fc9  mov     rax, qword ptr cs:asc_1800A2720; ") {\n"
0x180031fd0  movsxd  rcx, r8d
0x180031fd3  add     r8d, 4
0x180031fd7  mov     dword ptr [rsp+160h+var_118+4], r8d
0x180031fdc  mov     [rdi+rcx*2], rax
0x180031fe0  test    rdi, rdi
0x180031fe3  jz      short loc_180031FED
0x180031fe5  movsxd  rcx, r8d
0x180031fe8  mov     [rdi+rcx*2], r14w
0x180031fed  mov     r9d, 1; int
0x180031ff3  lea     r8, [rsp+160h+var_F8]; struct VAR *
0x180031ff8  lea     rdx, [rbp+60h+arg_8]; struct VAR **
0x180031ffc  mov     rcx, r15; struct CSession *
0x180031fff  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180032004  mov     ebx, eax
0x180032006  test    eax, eax
0x180032008  js      loc_1800321AF
0x18003200e  mov     rax, [rbp+60h+arg_8]
0x180032012  mov     rdx, [rax+8]; unsigned __int16 *
0x180032016  test    rdx, rdx
0x180032019  jz      loc_18003228F
0x18003201f  mov     r8d, [rdx-4]
0x180032023  shr     r8d, 1; int
0x180032026  lea     rcx, [rsp+160h+Block]; this
0x18003202b  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180032030  mov     ebx, eax
0x180032032  test    eax, eax
0x180032034  js      loc_1800321AA
0x18003203a  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x18003203f  lea     edx, [r8+2]; int
0x180032043  cmp     edx, r8d
0x180032046  jl      loc_1800323B9
0x18003204c  cmp     edx, dword ptr [rsp+160h+var_118]
0x180032050  jge     loc_180032273
0x180032056  mov     rdx, [rsp+160h+Block]
0x18003205b  mov     eax, dword ptr cs:asc_1800A272C; "\n}"
0x180032061  movsxd  rcx, r8d
0x180032064  add     r8d, 2
0x180032068  mov     dword ptr [rsp+160h+var_118+4], r8d
0x18003206d  mov     [rdx+rcx*2], eax
0x180032070  test    rdx, rdx
0x180032073  jz      short loc_18003207D
0x180032075  movsxd  rcx, r8d
0x180032078  mov     [rdx+rcx*2], r14w
0x18003207d  lea     rcx, [rsp+160h+Block]; this
0x180032082  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x180032087  mov     rdx, rax; unsigned __int16 *
0x18003208a  mov     rcx, r12; this
0x18003208d  mov     rdi, rax
0x180032090  call    ?CheckDynamicCodeSafety@COleScript@@QEAAJPEBG@Z; COleScript::CheckDynamicCodeSafety(ushort const *)
0x180032095  mov     ebx, eax
0x180032097  test    eax, eax
0x180032099  js      loc_180032198
0x18003209f  xor     edx, edx; Val
0x1800320a1  lea     rcx, [rbp+60h+var_C0]; void *
0x1800320a5  lea     r8d, [rdx+50h]; Size
0x1800320a9  call    memset_0
0x1800320ae  lea     rax, [rbp+60h+var_C0]
0x1800320b2  mov     [rbp+60h+var_70], rsi
0x1800320b6  mov     [rsp+160h+var_128], rax; struct CompileScriptException *
0x1800320bb  lea     rdx, [rsp+160h+var_108]; struct CScriptBody **
0x1800320c0  lea     rax, aAnonymousCode; "anonymous code"
0x1800320c7  mov     [rbp+60h+bstrString], r14
0x1800320cb  mov     [rsp+160h+var_130], rax; unsigned __int16 *
0x1800320d0  xor     r9d, r9d; unsigned int
0x1800320d3  mov     [rsp+160h+var_138], r14d; int
0x1800320d8  mov     r8, rdi; unsigned __int16 *
0x1800320db  mov     rcx, r12; this
0x1800320de  mov     [rsp+160h+var_140], r14; void *
0x1800320e3  mov     [rbp+60h+var_60], r14
0x1800320e7  call    ?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z; COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)
0x1800320ec  mov     [rbp+60h+arg_20], eax
0x1800320f2  mov     ebx, eax
0x1800320f4  test    eax, eax
0x1800320f6  js      loc_1800322F8
0x1800320fc  mov     rcx, [rbp+60h+bstrString]; bstrString
0x180032100  call    cs:__imp_SysFreeString
0x180032107  nop     dword ptr [rax+rax+00h]
0x18003210c  mov     rcx, [rbp+60h+var_60]; bstrString
0x180032110  call    cs:__imp_SysFreeString
0x180032117  nop     dword ptr [rax+rax+00h]
0x18003211c  lea     rcx, [rbp+60h+var_C0]; this
0x180032120  call    ??1ScriptException@@QEAA@XZ; ScriptException::~ScriptException(void)
0x180032125  mov     rcx, r12; this
0x180032128  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x18003212d  mov     rsi, [rsp+160h+var_108]
0x180032132  test    eax, eax
0x180032134  jnz     loc_18003232B
0x18003213a  mov     rax, [rsp+160h+var_100]
0x18003213f  mov     r8d, r14d
0x180032142  test    rax, rax
0x180032145  jz      short loc_18003214F
0x180032147  mov     rax, [rax+38h]
0x18003214b  mov     r8d, [rax+18h]
0x18003214f  mov     rax, [rsi+40h]
0x180032153  cmp     dword ptr [rax+1Ch], 1
0x180032157  jle     loc_18003238E
0x18003215d  mov     rdx, [rsi+48h]
0x180032161  movsxd  rax, dword ptr [rax+18h]
0x180032165  mov     [rbp+60h+var_D8], rdx
0x180032169  mov     [rbp+60h+var_C8], r8d
0x18003216d  lea     r8, [rbp+60h+var_50]; struct VAR *
0x180032171  mov     [rbp+60h+var_E0], rsi
0x180032175  movsxd  rcx, dword ptr [rax+rdx+4]
0x18003217a  add     rcx, rdx
0x18003217d  mov     edx, 3; int
0x180032182  mov     [rbp+60h+var_D0], rcx
0x180032186  mov     rcx, r15; this
0x180032189  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x18003218e  mov     ebx, eax
0x180032190  test    eax, eax
0x180032192  jns     loc_180032345
0x180032198  test    rdi, rdi
0x18003219b  jnz     loc_180032398
0x1800321a1  test    rsi, rsi
0x1800321a4  jnz     loc_1800323AC
0x1800321aa  mov     rdi, [rsp+160h+Block]
0x1800321af  test    rdi, rdi
0x1800321b2  jz      short loc_1800321C3
0x1800321b4  mov     rcx, rdi; Block
0x1800321b7  call    cs:__imp_free
0x1800321be  nop     dword ptr [rax+rax+00h]
0x1800321c3  mov     eax, ebx
0x1800321c5  mov     rbx, [rsp+160h+arg_10]
0x1800321cd  add     rsp, 130h
0x1800321d4  pop     r15
0x1800321d6  pop     r14
0x1800321d8  pop     r13
0x1800321da  pop     r12
0x1800321dc  pop     rdi
0x1800321dd  pop     rsi
0x1800321de  pop     rbp
0x1800321df  retn
0x1800321e1  mov     eax, r14d
0x1800321e4  lea     r8, [rsp+160h+var_F8]; struct VAR *
0x1800321e9  neg     eax
0x1800321eb  lea     rdx, [rbp+60h+arg_8]; struct VAR **
0x1800321ef  cdqe
0x1800321f1  mov     r9d, 1; int
0x1800321f7  lea     rcx, [rax+rax*2]
0x1800321fb  lea     rax, ds:0[rcx*8]
0x180032203  mov     rcx, r15; struct CSession *
0x180032206  add     rax, r13
0x180032209  mov     [rbp+60h+arg_8], rax
0x18003220d  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180032212  mov     ebx, eax
0x180032214  test    eax, eax
0x180032216  js      short loc_1800321AA
0x180032218  mov     rax, [rbp+60h+arg_8]
0x18003221c  mov     rdx, [rax+8]; unsigned __int16 *
0x180032220  test    rdx, rdx
0x180032223  jz      short loc_180032297
0x180032225  mov     r8d, [rdx-4]
0x180032229  shr     r8d, 1; int
0x18003222c  lea     rcx, [rsp+160h+Block]; this
0x180032231  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180032236  mov     ebx, eax
0x180032238  test    eax, eax
0x18003223a  js      loc_1800321AA
0x180032240  lea     eax, [rdi-1]
0x180032243  cmp     r14d, eax
0x180032246  jl      loc_1800322D2
0x18003224c  inc     r14d
0x18003224f  jmp     loc_180031F84
0x180032254  lea     rcx, [rsp+160h+Block]; this
0x180032259  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x18003225e  xor     r14d, r14d
0x180032261  test    eax, eax
0x180032263  jz      loc_1800323B9
0x180032269  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x18003226e  jmp     loc_180031FC4
0x180032273  lea     rcx, [rsp+160h+Block]; this
0x180032278  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x18003227d  test    eax, eax
0x18003227f  jz      loc_1800323B9
0x180032285  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x18003228a  jmp     loc_180032056
0x18003228f  mov     r8d, r14d
0x180032292  jmp     loc_180032026
0x180032297  xor     r8d, r8d
0x18003229a  jmp     short loc_18003222C
0x18003229c  mov     ebx, 8000FFFFh
0x1800322a1  jmp     short loc_1800322A8
0x1800322a3  mov     ebx, 800A13A9h
0x1800322a8  lea     rcx, [rsp+160h+Block]; this
0x1800322ad  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x1800322b2  jmp     loc_1800321C3
0x1800322b7  mov     eax, 80h
0x1800322bc  mov     [rsp+160h+var_F8], ax
0x1800322c1  lea     rax, ?cbstrEmpty@@3UConstBstr@@A; ConstBstr cbstrEmpty
0x1800322c8  mov     [rsp+160h+var_F0], rax
0x1800322cd  jmp     loc_180031F03
0x1800322d2  mov     r8d, 2; int
0x1800322d8  lea     rdx, asc_1800A2158; ", "
0x1800322df  lea     rcx, [rsp+160h+Block]; this
0x1800322e4  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x1800322e9  mov     ebx, eax
0x1800322eb  test    eax, eax
0x1800322ed  js      loc_1800321AA
0x1800322f3  jmp     loc_18003224C
0x1800322f8  cmp     eax, 86664004h
0x1800322fd  jnz     short loc_180032318
0x1800322ff  lea     r8, [rbp+60h+arg_20]; int *
0x180032306  mov     rcx, r15; this
0x180032309  lea     rdx, [rbp+60h+var_B8]; struct tagEXCEPINFO *
0x18003230d  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x180032312  mov     ebx, [rbp+60h+arg_20]
0x180032318  lea     rcx, [rbp+60h+var_C0]; this
0x18003231c  call    ??1CompileScriptException@@QEAA@XZ; CompileScriptException::~CompileScriptException(void)
0x180032321  mov     rsi, [rsp+160h+var_108]
0x180032326  jmp     loc_180032198
0x18003232b  mov     rdx, rsi; struct CScriptBody *
0x18003232e  mov     rcx, r12; this
0x180032331  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x180032336  mov     ebx, eax
0x180032338  test    eax, eax
0x18003233a  js      loc_180032198
0x180032340  jmp     loc_18003213A
0x180032345  mov     ecx, 0D8h; Size
0x18003234a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003234f  test    rax, rax
0x180032352  jz      short loc_18003237D
0x180032354  lea     r9, [rbp+60h+var_50]; struct VAR *
0x180032358  mov     dword ptr [rsp+160h+var_140], r14d; int
0x18003235d  lea     r8, [rbp+60h+var_E0]; struct FncInfo *
0x180032361  mov     rdx, r15; struct CSession *
0x180032364  mov     rcx, rax; this
  ... truncated ...
```
