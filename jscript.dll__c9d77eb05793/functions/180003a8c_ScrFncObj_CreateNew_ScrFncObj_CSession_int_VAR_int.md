# ScrFncObj::CreateNew(ScrFncObj * *,CSession *,int,VAR *,int)

- ea: `0x180003a8c`
- end: `0x180003fa6`
- name: `?CreateNew@ScrFncObj@@SAJPEAPEAV1@PEAVCSession@@HPEAVVAR@@H@Z`
- size: `1306`
- prototype: `static int(struct ScrFncObj **, struct CSession *, int, struct VAR *, int)`
- caller_count: `2`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x18004b450`
- `0x180061fc0`

## callees

- `0x1800038c8`
- `0x180003a8c`
- `0x180003fac`
- `0x18000441c`
- `0x180004470`
- `0x18000895c`
- `0x18000ad6c`
- `0x18000ded0`
- `0x180018650`
- `0x180019c60`
- `0x18001a9d4`
- `0x18001b2a8`
- `0x18001b560`
- `0x180043e08`
- `0x18004b26c`
- `0x1800576a0`
- `0x1800782bc`
- `0x18009429a`

## import_xrefs

- `msvcrt!free` at `0x180003da7`
- `msvcrt!free` at `0x180003f84`
- `msvcrt!free` at `0x180003da7`
- `msvcrt!free` at `0x180003f84`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d06`
- `OLEAUT32!__imp_SysFreeString` at `0x180003cfc`
- `OLEAUT32!__imp_SysFreeString` at `0x180003d06`

## pseudocode

```c
__int64 __fastcall ScrFncObj::CreateNew(struct ScrFncObj **a1, struct CSession *a2, int a3, struct VAR *a4, int a5)
{
  COleScript *v5; // r12
  struct CScriptBody *v7; // rsi
  int v8; // edi
  __int16 *v9; // rbx
  __int64 v10; // rcx
  _WORD *v11; // rdx
  int v12; // ecx
  int v13; // r14d
  __int16 *v14; // r13
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
  __int16 v44; // [rsp+68h] [rbp-98h] BYREF
  void *v45; // [rsp+70h] [rbp-90h]
  struct CScriptBody *v46; // [rsp+80h] [rbp-80h] BYREF
  __int64 v47; // [rsp+88h] [rbp-78h]
  __int64 v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+98h] [rbp-68h]
  _BYTE v50[8]; // [rsp+A0h] [rbp-60h] BYREF
  struct tagEXCEPINFO v51; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v52; // [rsp+F0h] [rbp-10h]
  BSTR bstrString; // [rsp+F8h] [rbp-8h]
  BSTR v54; // [rsp+100h] [rbp+0h]
  _BYTE v55[80]; // [rsp+110h] [rbp+10h] BYREF
  struct VAR *v57; // [rsp+178h] [rbp+78h] BYREF

  v5 = (COleScript *)*((_QWORD *)a2 + 5);
  v57 = 0;
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
    v44 = 128;
    v45 = &cbstrEmpty;
  }
  v8 = 1;
  v9 = &v44;
  if ( a3 >= 1 )
  {
    v8 = a3;
    v9 = (__int16 *)a4;
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
  v14 = &v9[12 * v8];
  while ( v13 < v8 )
  {
    v57 = (struct VAR *)&v14[-12 * v13];
    appended = ConvertToString(a2, &v57, (struct VAR *)&v44, 1);
    if ( appended < 0 )
      goto LABEL_35;
    v35 = (const unsigned __int16 *)*((_QWORD *)v57 + 1);
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
  v57 = (struct VAR *)&v14[-12 * v8];
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
  appended = ConvertToString(a2, &v57, (struct VAR *)&v44, 1);
  if ( appended < 0 )
    goto LABEL_36;
  v21 = (const unsigned __int16 *)*((_QWORD *)v57 + 1);
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
        memset_0(v50, 0, 0x50u);
        v52 = 0;
        bstrString = 0;
        v54 = 0;
        v29 = COleScript::Compile(v5, &v42, v28, 0, 0, 0, L"anonymous code", (struct CompileScriptException *)v50);
        a5 = v29;
        appended = v29;
        if ( v29 < 0 )
        {
          if ( v29 == -2040119292 )
          {
            CSession::RecordExcepInfoAndClear(a2, &v51, &a5);
            appended = a5;
          }
          CompileScriptException::~CompileScriptException((CompileScriptException *)v50);
          v7 = v42;
          goto LABEL_31;
        }
        SysFreeString(bstrString);
        SysFreeString(v54);
        ScriptException::~ScriptException((ScriptException *)v50);
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
            v47 = *((_QWORD *)v7 + 9);
            v49 = v31;
            v46 = v7;
            v48 = v47 + *(int *)(v33 + v47 + 4);
            appended = CSession::GetTypeProto(a2, 3, (struct VAR *)v55);
            if ( appended >= 0 )
            {
              v37 = (ScrFncObj *)operator new(0xD8u);
              if ( v37 )
              {
                v38 = ScrFncObj::ScrFncObj(v37, a2, (struct FncInfo *)&v46, (struct VAR *)v55, 0);
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
0x180003a8c  mov     [rsp-8+arg_10], rbx
0x180003a91  mov     [rsp-8+arg_0], rcx
0x180003a96  push    rbp
0x180003a97  push    rsi
0x180003a98  push    rdi
0x180003a99  push    r12
0x180003a9b  push    r13
0x180003a9d  push    r14
0x180003a9f  push    r15
0x180003aa1  lea     rbp, [rsp-30h]
0x180003aa6  sub     rsp, 130h
0x180003aad  mov     r12, [rdx+28h]
0x180003ab1  xor     r14d, r14d
0x180003ab4  mov     [rbp+60h+arg_8], r14
0x180003ab8  mov     r15, rdx
0x180003abb  mov     [rsp+160h+Block], r14
0x180003ac0  mov     esi, r14d
0x180003ac3  mov     [rsp+160h+var_118], r14
0x180003ac8  mov     [rsp+160h+var_110], r14d
0x180003acd  mov     [rsp+160h+var_108], r14
0x180003ad2  test    r12, r12
0x180003ad5  jz      loc_180003E85
0x180003adb  cmp     [r12+3C0h], r14d
0x180003ae3  jnz     loc_180003E8C
0x180003ae9  mov     rax, [rdx+50h]
0x180003aed  lea     ecx, [r14+1]
0x180003af1  mov     [rsp+160h+var_100], rax
0x180003af6  cmp     r8d, ecx
0x180003af9  jl      loc_180003EA0
0x180003aff  mov     edi, ecx
0x180003b01  lea     rbx, [rsp+160h+var_F8]
0x180003b06  lea     rcx, [rsp+160h+Block]; this
0x180003b0b  mov     edx, 13h; int
0x180003b10  cmovge  edi, r8d
0x180003b14  cmovge  rbx, r9
0x180003b18  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180003b1d  test    eax, eax
0x180003b1f  jz      loc_180003F9C
0x180003b25  movsxd  rcx, dword ptr [rsp+160h+var_118+4]
0x180003b2a  mov     rdx, [rsp+160h+Block]
0x180003b2f  movups  xmm0, xmmword ptr cs:aFunctionAnonym_0; "function anonymous("
0x180003b36  movups  xmmword ptr [rdx+rcx*2], xmm0
0x180003b3a  movups  xmm1, xmmword ptr cs:aFunctionAnonym_0+10h; " anonymous("
0x180003b41  movups  xmmword ptr [rdx+rcx*2+10h], xmm1
0x180003b46  movsd   xmm0, qword ptr cs:aFunctionAnonym_0+1Eh; "ous("
0x180003b4e  movsd   qword ptr [rdx+rcx*2+1Eh], xmm0
0x180003b54  add     ecx, 13h
0x180003b57  mov     dword ptr [rsp+160h+var_118+4], ecx
0x180003b5b  test    rdx, rdx
0x180003b5e  jz      short loc_180003B68
0x180003b60  movsxd  rcx, ecx
0x180003b63  mov     [rdx+rcx*2], r14w
0x180003b68  movsxd  rax, edi
0x180003b6b  mov     [rbp+60h+arg_20], r14d
0x180003b72  mov     r14d, 1
0x180003b78  lea     rcx, [rax+rax*2]
0x180003b7c  lea     r13, [rbx+rcx*8]
0x180003b80  cmp     r14d, edi
0x180003b83  jl      loc_180003DCA
0x180003b89  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x180003b8e  neg     edi
0x180003b90  movsxd  rax, edi
0x180003b93  lea     edx, [r8+4]; int
0x180003b97  lea     rcx, [rax+rax*2]
0x180003b9b  lea     rax, ds:0[rcx*8]
0x180003ba3  add     rax, r13
0x180003ba6  mov     [rbp+60h+arg_8], rax
0x180003baa  cmp     edx, r8d
0x180003bad  jl      loc_180003F9C
0x180003bb3  cmp     edx, dword ptr [rsp+160h+var_118]
0x180003bb7  jge     loc_180003E3D
0x180003bbd  xor     r14d, r14d
0x180003bc0  mov     rdi, [rsp+160h+Block]
0x180003bc5  mov     rax, qword ptr cs:asc_1800A03F8; ") {\n"
0x180003bcc  movsxd  rcx, r8d
0x180003bcf  add     r8d, 4
0x180003bd3  mov     dword ptr [rsp+160h+var_118+4], r8d
0x180003bd8  mov     [rdi+rcx*2], rax
0x180003bdc  test    rdi, rdi
0x180003bdf  jz      short loc_180003BE9
0x180003be1  movsxd  rcx, r8d
0x180003be4  mov     [rdi+rcx*2], r14w
0x180003be9  mov     r9d, 1; int
0x180003bef  lea     r8, [rsp+160h+var_F8]; struct VAR *
0x180003bf4  lea     rdx, [rbp+60h+arg_8]; struct VAR **
0x180003bf8  mov     rcx, r15; struct CSession *
0x180003bfb  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180003c00  mov     ebx, eax
0x180003c02  test    eax, eax
0x180003c04  js      loc_180003D9F
0x180003c0a  mov     rax, [rbp+60h+arg_8]
0x180003c0e  mov     rdx, [rax+8]; unsigned __int16 *
0x180003c12  test    rdx, rdx
0x180003c15  jz      loc_180003E78
0x180003c1b  mov     r8d, [rdx-4]
0x180003c1f  shr     r8d, 1; int
0x180003c22  lea     rcx, [rsp+160h+Block]; this
0x180003c27  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180003c2c  mov     ebx, eax
0x180003c2e  test    eax, eax
0x180003c30  js      loc_180003D9A
0x180003c36  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x180003c3b  lea     edx, [r8+2]; int
0x180003c3f  cmp     edx, r8d
0x180003c42  jl      loc_180003F9C
0x180003c48  cmp     edx, dword ptr [rsp+160h+var_118]
0x180003c4c  jge     loc_180003E5C
0x180003c52  mov     rdx, [rsp+160h+Block]
0x180003c57  mov     eax, dword ptr cs:asc_1800A0404; "\n}"
0x180003c5d  movsxd  rcx, r8d
0x180003c60  add     r8d, 2
0x180003c64  mov     dword ptr [rsp+160h+var_118+4], r8d
0x180003c69  mov     [rdx+rcx*2], eax
0x180003c6c  test    rdx, rdx
0x180003c6f  jz      short loc_180003C79
0x180003c71  movsxd  rcx, r8d
0x180003c74  mov     [rdx+rcx*2], r14w
0x180003c79  lea     rcx, [rsp+160h+Block]; this
0x180003c7e  call    ?PszReset@BuildString@@QEAAPEAGXZ; BuildString::PszReset(void)
0x180003c83  mov     rdx, rax; unsigned __int16 *
0x180003c86  mov     rcx, r12; this
0x180003c89  mov     rdi, rax
0x180003c8c  call    ?CheckDynamicCodeSafety@COleScript@@QEAAJPEBG@Z; COleScript::CheckDynamicCodeSafety(ushort const *)
0x180003c91  mov     ebx, eax
0x180003c93  test    eax, eax
0x180003c95  js      loc_180003D88
0x180003c9b  xor     edx, edx; Val
0x180003c9d  lea     rcx, [rbp+60h+var_C0]; void *
0x180003ca1  lea     r8d, [rdx+50h]; Size
0x180003ca5  call    memset_0
0x180003caa  lea     rax, [rbp+60h+var_C0]
0x180003cae  mov     [rbp+60h+var_70], rsi
0x180003cb2  mov     [rsp+160h+var_128], rax; struct CompileScriptException *
0x180003cb7  lea     rdx, [rsp+160h+var_108]; struct CScriptBody **
0x180003cbc  lea     rax, aAnonymousCode; "anonymous code"
0x180003cc3  mov     [rbp+60h+bstrString], r14
0x180003cc7  mov     [rsp+160h+var_130], rax; unsigned __int16 *
0x180003ccc  xor     r9d, r9d; unsigned int
0x180003ccf  mov     [rsp+160h+var_138], r14d; int
0x180003cd4  mov     r8, rdi; unsigned __int16 *
0x180003cd7  mov     rcx, r12; this
0x180003cda  mov     [rsp+160h+var_140], r14; void *
0x180003cdf  mov     [rbp+60h+var_60], r14
0x180003ce3  call    ?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z; COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)
0x180003ce8  mov     [rbp+60h+arg_20], eax
0x180003cee  mov     ebx, eax
0x180003cf0  test    eax, eax
0x180003cf2  js      loc_180003EE1
0x180003cf8  mov     rcx, [rbp+60h+bstrString]; bstrString
0x180003cfc  call    cs:__imp_SysFreeString
0x180003d02  mov     rcx, [rbp+60h+var_60]; bstrString
0x180003d06  call    cs:__imp_SysFreeString
0x180003d0c  lea     rcx, [rbp+60h+var_C0]; this
0x180003d10  call    ??1ScriptException@@QEAA@XZ; ScriptException::~ScriptException(void)
0x180003d15  mov     rcx, r12; this
0x180003d18  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x180003d1d  mov     rsi, [rsp+160h+var_108]
0x180003d22  test    eax, eax
0x180003d24  jnz     loc_180003F14
0x180003d2a  mov     rax, [rsp+160h+var_100]
0x180003d2f  mov     r8d, r14d
0x180003d32  test    rax, rax
0x180003d35  jz      short loc_180003D3F
0x180003d37  mov     rax, [rax+38h]
0x180003d3b  mov     r8d, [rax+18h]
0x180003d3f  mov     rax, [rsi+40h]
0x180003d43  cmp     dword ptr [rax+1Ch], 1
0x180003d47  jle     loc_180003F77
0x180003d4d  mov     rdx, [rsi+48h]
0x180003d51  movsxd  rax, dword ptr [rax+18h]
0x180003d55  mov     [rbp+60h+var_D8], rdx
0x180003d59  mov     [rbp+60h+var_C8], r8d
0x180003d5d  lea     r8, [rbp+60h+var_50]; struct VAR *
0x180003d61  mov     [rbp+60h+var_E0], rsi
0x180003d65  movsxd  rcx, dword ptr [rax+rdx+4]
0x180003d6a  add     rcx, rdx
0x180003d6d  mov     edx, 3; int
0x180003d72  mov     [rbp+60h+var_D0], rcx
0x180003d76  mov     rcx, r15; this
0x180003d79  call    ?GetTypeProto@CSession@@QEAAJHPEAVVAR@@@Z; CSession::GetTypeProto(int,VAR *)
0x180003d7e  mov     ebx, eax
0x180003d80  test    eax, eax
0x180003d82  jns     loc_180003F2E
0x180003d88  test    rdi, rdi
0x180003d8b  jnz     loc_180003F81
0x180003d91  test    rsi, rsi
0x180003d94  jnz     loc_180003F8F
0x180003d9a  mov     rdi, [rsp+160h+Block]
0x180003d9f  test    rdi, rdi
0x180003da2  jz      short loc_180003DAD
0x180003da4  mov     rcx, rdi; Block
0x180003da7  call    cs:__imp_free
0x180003dad  mov     eax, ebx
0x180003daf  mov     rbx, [rsp+160h+arg_10]
0x180003db7  add     rsp, 130h
0x180003dbe  pop     r15
0x180003dc0  pop     r14
0x180003dc2  pop     r13
0x180003dc4  pop     r12
0x180003dc6  pop     rdi
0x180003dc7  pop     rsi
0x180003dc8  pop     rbp
0x180003dc9  retn
0x180003dca  mov     eax, r14d
0x180003dcd  lea     r8, [rsp+160h+var_F8]; struct VAR *
0x180003dd2  neg     eax
0x180003dd4  lea     rdx, [rbp+60h+arg_8]; struct VAR **
0x180003dd8  cdqe
0x180003dda  mov     r9d, 1; int
0x180003de0  lea     rcx, [rax+rax*2]
0x180003de4  lea     rax, ds:0[rcx*8]
0x180003dec  mov     rcx, r15; struct CSession *
0x180003def  add     rax, r13
0x180003df2  mov     [rbp+60h+arg_8], rax
0x180003df6  call    ?ConvertToString@@YAJPEAVCSession@@PEAPEAVVAR@@PEAV2@H@Z; ConvertToString(CSession *,VAR * *,VAR *,int)
0x180003dfb  mov     ebx, eax
0x180003dfd  test    eax, eax
0x180003dff  js      short loc_180003D9A
0x180003e01  mov     rax, [rbp+60h+arg_8]
0x180003e05  mov     rdx, [rax+8]; unsigned __int16 *
0x180003e09  test    rdx, rdx
0x180003e0c  jz      short loc_180003E80
0x180003e0e  mov     r8d, [rdx-4]
0x180003e12  shr     r8d, 1; int
0x180003e15  lea     rcx, [rsp+160h+Block]; this
0x180003e1a  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180003e1f  mov     ebx, eax
0x180003e21  test    eax, eax
0x180003e23  js      loc_180003D9A
0x180003e29  lea     eax, [rdi-1]
0x180003e2c  cmp     r14d, eax
0x180003e2f  jl      loc_180003EBB
0x180003e35  inc     r14d
0x180003e38  jmp     loc_180003B80
0x180003e3d  lea     rcx, [rsp+160h+Block]; this
0x180003e42  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180003e47  xor     r14d, r14d
0x180003e4a  test    eax, eax
0x180003e4c  jz      loc_180003F9C
0x180003e52  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x180003e57  jmp     loc_180003BC0
0x180003e5c  lea     rcx, [rsp+160h+Block]; this
0x180003e61  call    ?FEnsureSpace@BuildString@@AEAAHJ@Z; BuildString::FEnsureSpace(long)
0x180003e66  test    eax, eax
0x180003e68  jz      loc_180003F9C
0x180003e6e  mov     r8d, dword ptr [rsp+160h+var_118+4]
0x180003e73  jmp     loc_180003C52
0x180003e78  mov     r8d, r14d
0x180003e7b  jmp     loc_180003C22
0x180003e80  xor     r8d, r8d
0x180003e83  jmp     short loc_180003E15
0x180003e85  mov     ebx, 8000FFFFh
0x180003e8a  jmp     short loc_180003E91
0x180003e8c  mov     ebx, 800A13A9h
0x180003e91  lea     rcx, [rsp+160h+Block]; this
0x180003e96  call    ?Reset@BuildString@@QEAAXXZ; BuildString::Reset(void)
0x180003e9b  jmp     loc_180003DAD
0x180003ea0  mov     eax, 80h
0x180003ea5  mov     [rsp+160h+var_F8], ax
0x180003eaa  lea     rax, ?cbstrEmpty@@3UConstBstr@@A; ConstBstr cbstrEmpty
0x180003eb1  mov     [rsp+160h+var_F0], rax
0x180003eb6  jmp     loc_180003AFF
0x180003ebb  mov     r8d, 2; int
0x180003ec1  lea     rdx, asc_1800A0208; ", "
0x180003ec8  lea     rcx, [rsp+160h+Block]; this
0x180003ecd  call    ?AppendSz@BuildString@@QEAAJPEBGJ@Z; BuildString::AppendSz(ushort const *,long)
0x180003ed2  mov     ebx, eax
0x180003ed4  test    eax, eax
0x180003ed6  js      loc_180003D9A
0x180003edc  jmp     loc_180003E35
0x180003ee1  cmp     eax, 86664004h
0x180003ee6  jnz     short loc_180003F01
0x180003ee8  lea     r8, [rbp+60h+arg_20]; int *
0x180003eef  mov     rcx, r15; this
0x180003ef2  lea     rdx, [rbp+60h+var_B8]; struct tagEXCEPINFO *
0x180003ef6  call    ?RecordExcepInfoAndClear@CSession@@QEAAXPEAUtagEXCEPINFO@@PEAJ@Z; CSession::RecordExcepInfoAndClear(tagEXCEPINFO *,long *)
0x180003efb  mov     ebx, [rbp+60h+arg_20]
0x180003f01  lea     rcx, [rbp+60h+var_C0]; this
0x180003f05  call    ??1CompileScriptException@@QEAA@XZ; CompileScriptException::~CompileScriptException(void)
0x180003f0a  mov     rsi, [rsp+160h+var_108]
0x180003f0f  jmp     loc_180003D88
0x180003f14  mov     rdx, rsi; struct CScriptBody *
0x180003f17  mov     rcx, r12; this
0x180003f1a  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x180003f1f  mov     ebx, eax
0x180003f21  test    eax, eax
0x180003f23  js      loc_180003D88
0x180003f29  jmp     loc_180003D2A
0x180003f2e  mov     ecx, 0D8h; Size
0x180003f33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003f38  test    rax, rax
0x180003f3b  jz      short loc_180003F66
0x180003f3d  lea     r9, [rbp+60h+var_50]; struct VAR *
0x180003f41  mov     dword ptr [rsp+160h+var_140], r14d; int
0x180003f46  lea     r8, [rbp+60h+var_E0]; struct FncInfo *
0x180003f4a  mov     rdx, r15; struct CSession *
0x180003f4d  mov     rcx, rax; this
0x180003f50  call    ??0ScrFncObj@@IEAA@PEAVCSession@@PEAVFncInfo@@PEAVVAR@@H@Z; ScrFncObj::ScrFncObj(CSession *,FncInfo *,VAR *,int)
0x180003f55  mov     rcx, [rbp+60h+arg_0]
0x180003f59  mov     [rcx], rax
  ... truncated ...
```
