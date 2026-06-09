# COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)

- ea: `0x18001868c`
- end: `0x180018965`
- name: `?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z`
- size: `729`
- prototype: `__int64 __fastcall(COleScript *this, struct CScriptBody **, OLECHAR *, unsigned int, char *, unsigned int, unsigned __int16 *, struct CompileScriptException *)`
- caller_count: `5`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x180018000`
- `0x180031160`
- `0x180031e90`
- `0x1800642e8`
- `0x18007d498`

## callees

- `0x180004c64`
- `0x18000c860`
- `0x18000c8c0`
- `0x180016e68`
- `0x1800172e8`
- `0x1800185ec`
- `0x180018630`
- `0x18001868c`
- `0x18001896c`
- `0x180018b9c`
- `0x18001a510`
- `0x18004fd84`
- `0x1800585d0`
- `0x18007e668`
- `0x1800966e0`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001890c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001890c`
- `OLEAUT32!__imp_SysStringLen` at `0x180018899`
- `OLEAUT32!__imp_SysStringLen` at `0x180018899`

## pseudocode

```c
__int64 __fastcall COleScript::Compile(
        COleScript *this,
        struct CScriptBody **a2,
        OLECHAR *a3,
        unsigned int a4,
        char *a5,
        unsigned int a6,
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
  char *v30; // [rsp+68h] [rbp-98h]
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
    if ( (byte_1800B8D81 & 8) != 0 )
      McTemplateU0pq_EventWriteTransfer(v13, JSCRIPT_PARSE_START, this);
    v16 = Parser::ParseSource((Parser *)v31, &v27, this, v10, a4, v30, a6, a8, v29, &v28);
    if ( (byte_1800B8D81 & 8) != 0 )
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
0x18001868c  mov     [rsp-8+arg_18], rbx
0x180018691  push    rbp
0x180018692  push    rsi
0x180018693  push    rdi
0x180018694  push    r12
0x180018696  push    r13
0x180018698  push    r14
0x18001869a  push    r15
0x18001869c  lea     rbp, [rsp-1C0h]
0x1800186a4  sub     rsp, 2C0h
0x1800186ab  mov     rax, cs:__security_cookie
0x1800186b2  xor     rax, rsp
0x1800186b5  mov     [rbp+1F0h+var_40], rax
0x1800186bc  mov     rax, [rbp+1F0h+arg_20]
0x1800186c3  xor     ebx, ebx
0x1800186c5  mov     r15, [rbp+1F0h+arg_38]
0x1800186cc  mov     r13d, r9d
0x1800186cf  mov     [rsp+2F0h+var_288], rax
0x1800186d4  mov     rsi, r8
0x1800186d7  mov     rax, [rbp+1F0h+arg_30]
0x1800186de  mov     r14, rdx
0x1800186e1  mov     [rsp+2F0h+var_290], rax
0x1800186e6  mov     rdi, rcx
0x1800186e9  mov     [rsp+2F0h+var_2A0], 0
0x1800186f2  test    r9b, 1
0x1800186f6  jnz     loc_180018874
0x1800186fc  lea     rcx, [rsp+2F0h+var_280]; this
0x180018701  call    ??0Parser@@QEAA@XZ; Parser::Parser(void)
0x180018706  mov     rax, [rdi+2D0h]
0x18001870d  mov     [rsp+2F0h+var_298], rax
0x180018712  test    rax, rax
0x180018715  jnz     loc_1800188B7
0x18001871b  xor     r12d, r12d
0x18001871e  test    cs:byte_1800B8D81, 8
0x180018725  jnz     loc_1800188D4
0x18001872b  lea     rax, [rsp+2F0h+var_298]
0x180018730  mov     r9, rsi; unsigned __int16 *
0x180018733  mov     [rsp+2F0h+var_2A8], rax; struct NameList **
0x180018738  lea     rdx, [rsp+2F0h+var_2A0]; struct ExecBody **
0x18001873d  mov     rax, [rsp+2F0h+var_290]
0x180018742  lea     rcx, [rsp+2F0h+var_280]; this
0x180018747  mov     [rsp+2F0h+var_2B0], rax; unsigned __int16 *
0x18001874c  mov     r8, rdi; struct COleScript *
0x18001874f  mov     eax, [rbp+1F0h+arg_28]
0x180018755  mov     [rsp+2F0h+var_2B8], r15; struct CompileScriptException *
0x18001875a  mov     [rsp+2F0h+var_2C0], eax; unsigned int
0x18001875e  mov     rax, [rsp+2F0h+var_288]
0x180018763  mov     [rsp+2F0h+var_2C8], rax; char *
0x180018768  mov     [rsp+2F0h+var_2D0], r13d; unsigned int
0x18001876d  call    ?ParseSource@Parser@@QEAAJPEAPEAVExecBody@@PEAVCOleScript@@PEBGKPEAXJPEAVCompileScriptException@@2PEAPEAVNameList@@@Z; Parser::ParseSource(ExecBody * *,COleScript *,ushort const *,ulong,void *,long,CompileScriptException *,ushort const *,NameList * *)
0x180018772  test    cs:byte_1800B8D81, 8
0x180018779  mov     esi, eax
0x18001877b  jnz     loc_1800188E8
0x180018781  mov     rcx, [rsp+2F0h+var_298]
0x180018786  xor     r13d, r13d
0x180018789  mov     [rdi+2D0h], rcx
0x180018790  test    r12d, r12d
0x180018793  jnz     loc_1800188FC
0x180018799  test    rbx, rbx
0x18001879c  jnz     loc_180018909
0x1800187a2  test    esi, esi
0x1800187a4  js      loc_18001891D
0x1800187aa  lea     rcx, [rsp+2F0h+var_280]; this
0x1800187af  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x1800187b4  mov     ecx, 58h ; 'X'; Size
0x1800187b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800187be  test    rax, rax
0x1800187c1  jz      loc_180018958
0x1800187c7  mov     rdx, [rsp+2F0h+var_2A0]; struct ExecBody *
0x1800187cc  mov     r8, rdi; struct COleScript *
0x1800187cf  mov     rcx, rax; this
0x1800187d2  call    ??0CScriptBody@@QEAA@PEAVExecBody@@PEAVCOleScript@@@Z; CScriptBody::CScriptBody(ExecBody *,COleScript *)
0x1800187d7  mov     [r14], rax
0x1800187da  test    rax, rax
0x1800187dd  jz      loc_18001895B
0x1800187e3  lea     rsi, [rdi+358h]
0x1800187ea  mov     rcx, rsi; this
0x1800187ed  call    ?Enter@MUTX@@QEAAHXZ; MUTX::Enter(void)
0x1800187f2  test    eax, eax
0x1800187f4  jz      short loc_18001886D
0x1800187f6  mov     rax, [r14]
0x1800187f9  lea     rdx, [rdi+390h]
0x180018800  mov     r8, [rdx]
0x180018803  mov     ebx, r13d
0x180018806  lea     rcx, [rax+28h]
0x18001880a  mov     [rcx], r8
0x18001880d  test    r8, r8
0x180018810  jnz     loc_180018944
0x180018816  mov     [rax+30h], rdx
0x18001881a  mov     rcx, rsi; this
0x18001881d  mov     [rdx], rax
0x180018820  call    ?Leave@MUTX@@QEAAXXZ; MUTX::Leave(void)
0x180018825  mov     rax, [rdi+2A0h]
0x18001882c  cmp     [rax+8], r13
0x180018830  jnz     loc_18001894D
0x180018836  mov     rcx, [rsp+2F0h+var_2A0]; this
0x18001883b  call    ?Release@ExecBody@@QEAAXXZ; ExecBody::Release(void)
0x180018840  mov     eax, ebx
0x180018842  mov     rcx, [rbp+1F0h+var_40]
0x180018849  xor     rcx, rsp; StackCookie
0x18001884c  call    __security_check_cookie
0x180018851  mov     rbx, [rsp+2F0h+arg_18]
0x180018859  add     rsp, 2C0h
0x180018860  pop     r15
0x180018862  pop     r14
0x180018864  pop     r13
0x180018866  pop     r12
0x180018868  pop     rdi
0x180018869  pop     rsi
0x18001886a  pop     rbp
0x18001886b  retn
0x18001886d  mov     ebx, 80004005h
0x180018872  jmp     short loc_180018825
0x180018874  bt      r13d, 9
0x180018879  jb      loc_1800186FC
0x18001887f  mov     rcx, r8; strIn
0x180018882  call    ?_SysAllocString@@YAPEAGPEBG@Z; _SysAllocString(ushort const *)
0x180018887  mov     rbx, rax
0x18001888a  test    rax, rax
0x18001888d  jnz     short loc_180018896
0x18001888f  mov     eax, 8007000Eh
0x180018894  jmp     short loc_180018842
0x180018896  mov     rcx, rbx; pbstr
0x180018899  call    cs:__imp_SysStringLen
0x1800188a0  nop     dword ptr [rax+rax+00h]
0x1800188a5  mov     edx, eax; unsigned __int64
0x1800188a7  mov     rcx, rbx; unsigned __int16 *
0x1800188aa  call    ?RemoveHTMLCommentSuffix@@YAHPEAG_K@Z; RemoveHTMLCommentSuffix(ushort *,unsigned __int64)
0x1800188af  mov     rsi, rbx
0x1800188b2  jmp     loc_1800186FC
0x1800188b7  mov     rcx, rdi; this
0x1800188ba  mov     r12d, 1
0x1800188c0  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x1800188c5  test    eax, eax
0x1800188c7  jnz     loc_18001871E
0x1800188cd  mov     ebx, 80004005h
0x1800188d2  jmp     short loc_180018935
0x1800188d4  mov     r8, rdi
0x1800188d7  lea     rdx, JSCRIPT_PARSE_START
0x1800188de  call    McTemplateU0pq_EventWriteTransfer
0x1800188e3  jmp     loc_18001872B
0x1800188e8  mov     r8, rdi
0x1800188eb  lea     rdx, JSCRIPT_PARSE_STOP
0x1800188f2  call    McTemplateU0pq_EventWriteTransfer
0x1800188f7  jmp     loc_180018781
0x1800188fc  mov     rcx, rdi; this
0x1800188ff  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x180018904  jmp     loc_180018799
0x180018909  mov     rcx, rbx; bstrString
0x18001890c  call    cs:__imp_SysFreeString
0x180018913  nop     dword ptr [rax+rax+00h]
0x180018918  jmp     loc_1800187A2
0x18001891d  cmp     esi, 86664004h
0x180018923  jnz     short loc_180018933
0x180018925  cmp     [r15+40h], r13d
0x180018929  jl      short loc_180018933
0x18001892b  mov     dword ptr [r15+40h], 80004005h
0x180018933  mov     ebx, esi
0x180018935  lea     rcx, [rsp+2F0h+var_280]; this
0x18001893a  call    ??1Parser@@QEAA@XZ; Parser::~Parser(void)
0x18001893f  jmp     loc_180018840
0x180018944  mov     [r8+30h], rcx
0x180018948  jmp     loc_180018816
0x18001894d  mov     rax, [r14]
0x180018950  lock inc dword ptr [rax]
0x180018953  jmp     loc_180018836
0x180018958  mov     [r14], r13
0x18001895b  mov     ebx, 8007000Eh
0x180018960  jmp     loc_180018836
```
