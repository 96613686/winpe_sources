# COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)

- ea: `0x18001b560`
- end: `0x18001b82c`
- name: `?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z`
- size: `716`
- prototype: `__int64 __fastcall(COleScript *this, struct CScriptBody **, OLECHAR *, unsigned int, const CHAR *, UINT, unsigned __int16 *, struct CompileScriptException *)`
- caller_count: `5`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180003590`
- `0x180003a8c`
- `0x18001af64`
- `0x180062fe8`
- `0x18007bc34`

## callees

- `0x180005a80`
- `0x18000f5e0`
- `0x18000f630`
- `0x180019e28`
- `0x18001a29c`
- `0x18001b520`
- `0x18001b560`
- `0x18001b834`
- `0x18001b8b8`
- `0x18001ba9c`
- `0x18001d590`
- `0x180034990`
- `0x1800576a0`
- `0x18007cde8`
- `0x1800942d0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001b7d9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b7d9`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b76c`
- `OLEAUT32!__imp_SysStringLen` at `0x18001b76c`

## pseudocode

```c
__int64 __fastcall COleScript::Compile(
        COleScript *this,
        struct CScriptBody **a2,
        OLECHAR *a3,
        unsigned int a4,
        const CHAR *a5,
        UINT a6,
        unsigned __int16 *a7,
        struct CompileScriptException *a8)
{
  OLECHAR *v8; // rbx
  const unsigned __int16 *v10; // rsi
  __int64 v13; // rcx
  int v14; // r12d
  __int64 v15; // rcx
  int v16; // esi
  CScriptBody *v17; // rax
  struct CScriptBody *v18; // rax
  volatile signed __int32 *v19; // rax
  volatile signed __int32 **v20; // rdx
  __int64 v21; // r8
  unsigned int v22; // ebx
  _QWORD *v23; // rcx
  OLECHAR *v25; // rax
  UINT v26; // eax
  ExecBody *v27; // [rsp+50h] [rbp-B0h] BYREF
  struct NameList *v28; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-A0h]
  LPCSTR v30; // [rsp+68h] [rbp-98h]
  _BYTE v31[576]; // [rsp+70h] [rbp-90h] BYREF

  v8 = 0;
  v30 = a5;
  v10 = a3;
  v29 = a7;
  v27 = 0;
  if ( (a4 & 1) == 0 || (a4 & 0x200) != 0 )
  {
LABEL_2:
    Parser::Parser((Parser *)v31);
    v28 = (struct NameList *)*((_QWORD *)this + 90);
    if ( v28 )
    {
      v14 = 1;
      if ( !(unsigned int)COleScript::DisableInterrupts(this) )
      {
        v22 = -2147467259;
        goto LABEL_34;
      }
    }
    else
    {
      v14 = 0;
    }
    if ( (byte_1800B6D81 & 8) != 0 )
      McTemplateU0pq_EventWriteTransfer(v13, JSCRIPT_PARSE_START, this);
    v16 = Parser::ParseSource((Parser *)v31, &v27, this, v10, a4, v30, a6, a8, v29, &v28);
    if ( (byte_1800B6D81 & 8) != 0 )
      McTemplateU0pq_EventWriteTransfer(v15, JSCRIPT_PARSE_STOP, this);
    *((_QWORD *)this + 90) = v28;
    if ( v14 )
      COleScript::EnableInterrupts(this);
    if ( v8 )
      SysFreeString(v8);
    if ( v16 >= 0 )
    {
      Parser::~Parser((Parser *)v31);
      v17 = (CScriptBody *)operator new(0x58u);
      if ( v17 )
      {
        v18 = CScriptBody::CScriptBody(v17, v27, this);
        *a2 = v18;
        if ( v18 )
        {
          if ( (unsigned int)MUTX::Enter((COleScript *)((char *)this + 856)) )
          {
            v19 = (volatile signed __int32 *)*a2;
            v20 = (volatile signed __int32 **)((char *)this + 912);
            v21 = *((_QWORD *)this + 114);
            v22 = 0;
            v23 = (_QWORD *)((char *)*a2 + 40);
            *v23 = v21;
            if ( v21 )
              *(_QWORD *)(v21 + 48) = v23;
            *((_QWORD *)v19 + 6) = v20;
            *v20 = v19;
            MUTX::Leave((COleScript *)((char *)this + 856));
          }
          else
          {
            v22 = -2147467259;
          }
          if ( *(_QWORD *)(*((_QWORD *)this + 84) + 8LL) )
            _InterlockedIncrement((volatile signed __int32 *)*a2);
          goto LABEL_21;
        }
      }
      else
      {
        *a2 = 0;
      }
      v22 = -2147024882;
LABEL_21:
      ExecBody::Release(v27);
      return v22;
    }
    if ( v16 == -2040119292 && *((int *)a8 + 16) >= 0 )
      *((_DWORD *)a8 + 16) = -2147467259;
    v22 = v16;
LABEL_34:
    Parser::~Parser((Parser *)v31);
    return v22;
  }
  v25 = _SysAllocString(a3);
  v8 = v25;
  if ( v25 )
  {
    v26 = SysStringLen(v25);
    RemoveHTMLCommentSuffix(v8, v26);
    v10 = v8;
    goto LABEL_2;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001b560  mov     [rsp-8+arg_18], rbx
0x18001b565  push    rbp
0x18001b566  push    rsi
0x18001b567  push    rdi
0x18001b568  push    r12
0x18001b56a  push    r13
0x18001b56c  push    r14
0x18001b56e  push    r15
0x18001b570  lea     rbp, [rsp-1C0h]
0x18001b578  sub     rsp, 2C0h
0x18001b57f  mov     rax, cs:__security_cookie
0x18001b586  xor     rax, rsp
0x18001b589  mov     [rbp+1F0h+var_40], rax
0x18001b590  mov     rax, [rbp+1F0h+arg_20]
0x18001b597  xor     ebx, ebx
0x18001b599  mov     r15, [rbp+1F0h+arg_38]
0x18001b5a0  mov     r13d, r9d
0x18001b5a3  mov     [rsp+2F0h+var_288], rax
0x18001b5a8  mov     rsi, r8
0x18001b5ab  mov     rax, [rbp+1F0h+arg_30]
0x18001b5b2  mov     r14, rdx
0x18001b5b5  mov     [rsp+2F0h+var_290], rax
0x18001b5ba  mov     rdi, rcx
0x18001b5bd  mov     [rsp+2F0h+var_2A0], 0
0x18001b5c6  test    r9b, 1
0x18001b5ca  jnz     loc_18001B747
0x18001b5d0  lea     rcx, [rsp+2F0h+var_280]; this
0x18001b5d5  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x18001b5da  mov     rax, [rdi+2D0h]
0x18001b5e1  mov     [rsp+2F0h+var_298], rax
0x18001b5e6  test    rax, rax
0x18001b5e9  jnz     loc_18001B784
0x18001b5ef  xor     r12d, r12d
0x18001b5f2  test    cs:byte_1800B6D81, 8
0x18001b5f9  jnz     loc_18001B7A1
0x18001b5ff  lea     rax, [rsp+2F0h+var_298]
0x18001b604  mov     r9, rsi; unsigned __int16 *
0x18001b607  mov     [rsp+2F0h+var_2A8], rax; struct NameList **
0x18001b60c  lea     rdx, [rsp+2F0h+var_2A0]; struct ExecBody **
0x18001b611  mov     rax, [rsp+2F0h+var_290]
0x18001b616  lea     rcx, [rsp+2F0h+var_280]; this
0x18001b61b  mov     [rsp+2F0h+var_2B0], rax; unsigned __int16 *
0x18001b620  mov     r8, rdi; struct COleScript *
0x18001b623  mov     eax, [rbp+1F0h+arg_28]
0x18001b629  mov     [rsp+2F0h+var_2B8], r15; struct CompileScriptException *
0x18001b62e  mov     [rsp+2F0h+var_2C0], eax; UINT
0x18001b632  mov     rax, [rsp+2F0h+var_288]
0x18001b637  mov     [rsp+2F0h+var_2C8], rax; LPCSTR
0x18001b63c  mov     [rsp+2F0h+var_2D0], r13d; unsigned int
0x18001b641  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@2PEAPEAVNameList@@@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,NameList * *)
0x18001b646  test    cs:byte_1800B6D81, 8
0x18001b64d  mov     esi, eax
0x18001b64f  jnz     loc_18001B7B5
0x18001b655  mov     rcx, [rsp+2F0h+var_298]
0x18001b65a  xor     r13d, r13d
0x18001b65d  mov     [rdi+2D0h], rcx
0x18001b664  test    r12d, r12d
0x18001b667  jnz     loc_18001B7C9
0x18001b66d  test    rbx, rbx
0x18001b670  jnz     loc_18001B7D6
0x18001b676  test    esi, esi
0x18001b678  js      loc_18001B7E4
0x18001b67e  lea     rcx, [rsp+2F0h+var_280]; this
0x18001b683  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001b688  mov     ecx, 58h ; 'X'; Size
0x18001b68d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b692  test    rax, rax
0x18001b695  jz      loc_18001B81F
0x18001b69b  mov     rdx, [rsp+2F0h+var_2A0]; struct ExecBody *
0x18001b6a0  mov     r8, rdi; struct COleScript *
0x18001b6a3  mov     rcx, rax; this
0x18001b6a6  call    ??0CScriptBody@@QEAA@PEAVExecBody@@PEAVCOleScript@@@Z; CScriptBody::CScriptBody(ExecBody *,COleScript *)
0x18001b6ab  mov     [r14], rax
0x18001b6ae  test    rax, rax
0x18001b6b1  jz      loc_18001B822
0x18001b6b7  lea     rsi, [rdi+358h]
0x18001b6be  mov     rcx, rsi; this
0x18001b6c1  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x18001b6c6  test    eax, eax
0x18001b6c8  jz      short loc_18001B740
0x18001b6ca  mov     rax, [r14]
0x18001b6cd  lea     rdx, [rdi+390h]
0x18001b6d4  mov     r8, [rdx]
0x18001b6d7  mov     ebx, r13d
0x18001b6da  lea     rcx, [rax+28h]
0x18001b6de  mov     [rcx], r8
0x18001b6e1  test    r8, r8
0x18001b6e4  jnz     loc_18001B80B
0x18001b6ea  mov     [rax+30h], rdx
0x18001b6ee  mov     rcx, rsi; this
0x18001b6f1  mov     [rdx], rax
0x18001b6f4  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x18001b6f9  mov     rax, [rdi+2A0h]
0x18001b700  cmp     [rax+8], r13
0x18001b704  jnz     loc_18001B814
0x18001b70a  mov     rcx, [rsp+2F0h+var_2A0]; this
0x18001b70f  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x18001b714  mov     eax, ebx
0x18001b716  mov     rcx, [rbp+1F0h+var_40]
0x18001b71d  xor     rcx, rsp; StackCookie
0x18001b720  call    __security_check_cookie
0x18001b725  mov     rbx, [rsp+2F0h+arg_18]
0x18001b72d  add     rsp, 2C0h
0x18001b734  pop     r15
0x18001b736  pop     r14
0x18001b738  pop     r13
0x18001b73a  pop     r12
0x18001b73c  pop     rdi
0x18001b73d  pop     rsi
0x18001b73e  pop     rbp
0x18001b73f  retn
0x18001b740  mov     ebx, 80004005h
0x18001b745  jmp     short loc_18001B6F9
0x18001b747  bt      r13d, 9
0x18001b74c  jb      loc_18001B5D0
0x18001b752  mov     rcx, r8; strIn
0x18001b755  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x18001b75a  mov     rbx, rax
0x18001b75d  test    rax, rax
0x18001b760  jnz     short loc_18001B769
0x18001b762  mov     eax, 8007000Eh
0x18001b767  jmp     short loc_18001B716
0x18001b769  mov     rcx, rbx; pbstr
0x18001b76c  call    cs:__imp_SysStringLen
0x18001b772  mov     edx, eax; unsigned __int64
0x18001b774  mov     rcx, rbx; unsigned __int16 *
0x18001b777  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x18001b77c  mov     rsi, rbx
0x18001b77f  jmp     loc_18001B5D0
0x18001b784  mov     rcx, rdi; this
0x18001b787  mov     r12d, 1
0x18001b78d  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001b792  test    eax, eax
0x18001b794  jnz     loc_18001B5F2
0x18001b79a  mov     ebx, 80004005h
0x18001b79f  jmp     short loc_18001B7FC
0x18001b7a1  mov     r8, rdi
0x18001b7a4  lea     rdx, JSCRIPT_PARSE_START
0x18001b7ab  call    McTemplateU0pq_EventWriteTransfer
0x18001b7b0  jmp     loc_18001B5FF
0x18001b7b5  mov     r8, rdi
0x18001b7b8  lea     rdx, JSCRIPT_PARSE_STOP
0x18001b7bf  call    McTemplateU0pq_EventWriteTransfer
0x18001b7c4  jmp     loc_18001B655
0x18001b7c9  mov     rcx, rdi; this
0x18001b7cc  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18001b7d1  jmp     loc_18001B66D
0x18001b7d6  mov     rcx, rbx; bstrString
0x18001b7d9  call    cs:__imp_SysFreeString
0x18001b7df  jmp     loc_18001B676
0x18001b7e4  cmp     esi, 86664004h
0x18001b7ea  jnz     short loc_18001B7FA
0x18001b7ec  cmp     [r15+40h], r13d
0x18001b7f0  jl      short loc_18001B7FA
0x18001b7f2  mov     dword ptr [r15+40h], 80004005h
0x18001b7fa  mov     ebx, esi
0x18001b7fc  lea     rcx, [rsp+2F0h+var_280]; this
0x18001b801  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001b806  jmp     loc_18001B714
0x18001b80b  mov     [r8+30h], rcx
0x18001b80f  jmp     loc_18001B6EA
0x18001b814  mov     rax, [r14]
0x18001b817  lock inc dword ptr [rax]
0x18001b81a  jmp     loc_18001B70A
0x18001b81f  mov     [r14], r13
0x18001b822  mov     ebx, 8007000Eh
0x18001b827  jmp     loc_18001B70A
```
