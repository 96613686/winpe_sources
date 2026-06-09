# COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,CScriptBody * *)

- ea: `0x180018000`
- end: `0x18001834a`
- name: `?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@PEAPEAVCScriptBody@@@Z`
- size: `842`
- prototype: `__int64 __fastcall(COleScript *this, OLECHAR *, int, struct SRCINFO *, wchar_t *String2, unsigned __int16 *, struct tagEXCEPINFO *, struct CScriptBody **)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180017b00`
- `0x18004e54c`

## callees

- `0x180016c84`
- `0x180016e68`
- `0x1800172e8`
- `0x180017a54`
- `0x180018000`
- `0x1800183f8`
- `0x18001868c`
- `0x1800323cc`
- `0x180041fdc`
- `0x18004c014`
- `0x1800585d0`
- `0x1800752a0`
- `0x18007533c`
- `0x1800759d0`
- `0x1800798d4`
- `0x18007b954`
- `0x18007d308`
- `0x180096692`
- `0x18009669e`
- `0x1800966aa`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800181bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800181cc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800181bc`
- `OLEAUT32!__imp_SysFreeString` at `0x1800181cc`

## pseudocode

```c
__int64 __fastcall COleScript::CreateScriptBody(
        COleScript *this,
        OLECHAR *a2,
        int a3,
        struct SRCINFO *a4,
        wchar_t *String2,
        unsigned __int16 *a6,
        struct tagEXCEPINFO *a7,
        struct CScriptBody **a8)
{
  unsigned int v12; // eax
  int v13; // ecx
  unsigned int v14; // edi
  int v15; // eax
  int v16; // edi
  struct CScriptBody *v17; // rsi
  int *v18; // rbx
  int v19; // r13d
  size_t v20; // r12
  int v21; // r15d
  struct CActiveScriptError *v22; // rax
  unsigned int v24; // ebx
  CActiveScriptError *v25; // rbx
  struct IActiveScriptError *v26; // rdx
  _DWORD Src[2]; // [rsp+40h] [rbp-79h] BYREF
  CScriptBody *v28; // [rsp+48h] [rbp-71h] BYREF
  _BYTE v29[64]; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v30; // [rsp+90h] [rbp-29h]
  __int64 v31; // [rsp+A0h] [rbp-19h]
  BSTR bstrString; // [rsp+A8h] [rbp-11h]
  BSTR v33; // [rsp+B0h] [rbp-9h]
  int v34; // [rsp+110h] [rbp+57h] BYREF
  struct CActiveScriptError *v35; // [rsp+118h] [rbp+5Fh] BYREF

  Src[1] = *((_DWORD *)a4 + 6);
  v28 = 0;
  if ( (a3 & 0x60) == 0x60 )
    return 2147942487LL;
  v12 = ComputeGrfscr(String2);
  v13 = 2;
  v14 = v12;
  if ( (a3 & 0x40) != 0 )
    v13 = 3;
  Src[0] = v13;
  if ( (a3 & 0x80) != 0 )
  {
    v13 |= 8u;
    Src[0] = v13;
  }
  if ( (a3 & 0x80000020) == 0x80000020 )
  {
    v14 = v12 | 2;
    Src[0] = v13 | 4;
  }
  if ( (a3 & 0x80) != 0 )
    *((_DWORD *)a4 + 7) |= 1u;
  if ( (a3 & 0x40000000) != 0 )
    *((_DWORD *)a4 + 7) |= 2u;
  memset_0(v29, 0, 0x50u);
  v31 = 0;
  bstrString = 0;
  v33 = 0;
  v15 = COleScript::Compile(this, &v28, a2, v14, (char *)a4, 0x20u, a6, (struct CompileScriptException *)v29);
  v34 = v15;
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( v15 != -2040119292 )
    {
LABEL_26:
      SysFreeString(bstrString);
      SysFreeString(v33);
      ScriptException::~ScriptException((ScriptException *)v29);
      return (unsigned int)v16;
    }
    v35 = 0;
    if ( (int)CompileScriptException::GetActiveScriptError((CompileScriptException *)v29, &v35) >= 0 )
    {
      v25 = v35;
      v26 = (struct IActiveScriptError *)((char *)v35 + 8);
      if ( !v35 )
        v26 = 0;
      if ( (unsigned int)COleScript::OnScriptError(this, v26) )
      {
        CompileScriptException::GetError((CompileScriptException *)v29, &v34, a7);
        v16 = v34;
      }
      else
      {
        ScriptException::DetachActiveScriptError((ScriptException *)v29);
        v16 = -2147352319;
      }
      CActiveScriptError::Release(v25);
      goto LABEL_26;
    }
    v24 = v30;
  }
  else
  {
    v17 = v28;
    if ( (a3 & 0x100) != 0 )
      *((_DWORD *)v28 + 20) = 1;
    if ( (unsigned int)COleScript::DisableInterrupts(this) )
    {
      if ( (unsigned int)COleScript::FDebuggerEnabled(this) )
      {
        v16 = COleScript::DbgRegisterScriptBlock(this, v17);
        if ( v16 < 0 )
          goto LABEL_24;
      }
      if ( a8 )
      {
        *a8 = v17;
      }
      else
      {
        v18 = (int *)*((_QWORD *)this + 87);
        if ( !v18 )
        {
          v18 = (int *)operator new(0x20u);
          if ( !v18 )
          {
            *((_QWORD *)this + 87) = 0;
LABEL_33:
            v16 = -2147024882;
LABEL_24:
            COleScript::EnableInterrupts(this);
            if ( v17 )
              CScriptBody::Release(v17);
            goto LABEL_26;
          }
          v18[2] = 1;
          *(_QWORD *)v18 = &GL::`vftable';
          v18[3] = 16;
          *((_QWORD *)v18 + 2) = 0;
          *((_QWORD *)v18 + 3) = 0;
          *((_QWORD *)this + 87) = v18;
        }
        v19 = v18[7];
        v20 = v18[3];
        v21 = v20 * (v19 + 1);
        if ( v21 > v18[6] && !(unsigned int)GL::FEnsureSize((GL *)v18, v21) )
          goto LABEL_33;
        v22 = (struct CActiveScriptError *)(v19 * (int)v20 + *((_QWORD *)v18 + 2));
        v35 = v22;
        if ( v19 < v18[7] )
        {
          memmove_0((char *)v22 + v20, v22, v21 - v19 * (int)v20 - (int)v20);
          v22 = v35;
        }
        memcpy_0(v22, Src, v20);
        ++v18[7];
      }
      _InterlockedIncrement((volatile signed __int32 *)v17);
      goto LABEL_24;
    }
    v24 = -2147467259;
  }
  CompileScriptException::~CompileScriptException((CompileScriptException *)v29);
  return v24;
}

```

## disassembly

```asm
0x180018000  mov     [rsp-8+arg_0], rbx
0x180018005  push    rbp
0x180018006  push    rsi
0x180018007  push    rdi
0x180018008  push    r12
0x18001800a  push    r13
0x18001800c  push    r14
0x18001800e  push    r15
0x180018010  lea     rbp, [rsp-7]
0x180018015  sub     rsp, 0C0h
0x18001801c  mov     eax, [r9+18h]
0x180018020  xor     r12d, r12d
0x180018023  mov     [rbp+37h+var_AC], eax
0x180018026  mov     rbx, r9
0x180018029  mov     eax, r8d
0x18001802c  mov     [rbp+37h+var_A8], r12
0x180018030  and     eax, 60h
0x180018033  mov     r15d, r8d
0x180018036  mov     rsi, rdx
0x180018039  mov     r14, rcx
0x18001803c  cmp     al, 60h ; '`'
0x18001803e  jz      loc_180018291
0x180018044  mov     rcx, [rbp+37h+String2]; String2
0x180018048  call    ?ComputeGrfscr@@YAKPEBG@Z; ComputeGrfscr(ushort const *)
0x18001804d  lea     ecx, [r12+2]
0x180018052  test    r15b, 40h
0x180018056  mov     edi, eax
0x180018058  mov     edx, r15d
0x18001805b  lea     eax, [rcx+1]
0x18001805e  cmovnz  ecx, eax
0x180018061  mov     [rbp+37h+Src], ecx
0x180018064  and     edx, 80h
0x18001806a  jnz     loc_18001829B
0x180018070  mov     r8d, 80000020h
0x180018076  mov     eax, r15d
0x180018079  and     eax, r8d
0x18001807c  cmp     eax, r8d
0x18001807f  jz      loc_1800182A6
0x180018085  test    edx, edx
0x180018087  jnz     loc_1800182B4
0x18001808d  bt      r15d, 1Eh
0x180018092  jb      loc_1800182BD
0x180018098  xor     edx, edx; Val
0x18001809a  lea     rcx, [rbp+37h+var_A0]; void *
0x18001809e  lea     r8d, [rdx+50h]; Size
0x1800180a2  call    memset_0
0x1800180a7  lea     rax, [rbp+37h+var_A0]
0x1800180ab  mov     [rbp+37h+var_50], r12
0x1800180af  mov     [rsp+0F0h+var_B8], rax; struct CompileScriptException *
0x1800180b4  lea     rdx, [rbp+37h+var_A8]; struct CScriptBody **
0x1800180b8  mov     rax, [rbp+37h+arg_28]
0x1800180bc  mov     r13d, 20h ; ' '
0x1800180c2  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x1800180c7  mov     r9d, edi; unsigned int
0x1800180ca  mov     [rsp+0F0h+var_C8], r13d; int
0x1800180cf  mov     r8, rsi; unsigned __int16 *
0x1800180d2  mov     rcx, r14; this
0x1800180d5  mov     [rsp+0F0h+var_D0], rbx; void *
0x1800180da  mov     [rbp+37h+bstrString], r12
0x1800180de  mov     [rbp+37h+var_40], r12
0x1800180e2  call    ?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z; COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)
0x1800180e7  mov     [rbp+37h+arg_10], eax
0x1800180ea  mov     edi, eax
0x1800180ec  test    eax, eax
0x1800180ee  js      loc_180018269
0x1800180f4  mov     rsi, [rbp+37h+var_A8]
0x1800180f8  bt      r15d, 8
0x1800180fd  jb      loc_18001830F
0x180018103  mov     rcx, r14; this
0x180018106  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001810b  test    eax, eax
0x18001810d  jz      loc_18001831B
0x180018113  mov     rcx, r14; this
0x180018116  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x18001811b  test    eax, eax
0x18001811d  jnz     loc_180018330
0x180018123  mov     rax, [rbp+37h+arg_38]
0x180018127  test    rax, rax
0x18001812a  jnz     loc_180018250
0x180018130  mov     rbx, [r14+2B8h]
0x180018137  test    rbx, rbx
0x18001813a  jz      loc_1800181FF
0x180018140  mov     r13d, [rbx+1Ch]
0x180018144  movsxd  r12, dword ptr [rbx+0Ch]
0x180018148  lea     r15d, [r13+1]
0x18001814c  imul    r15d, r12d
0x180018150  cmp     r15d, [rbx+18h]
0x180018154  jg      loc_18001823B
0x18001815a  mov     rax, [rbx+10h]
0x18001815e  mov     edx, r12d
0x180018161  imul    edx, r13d
0x180018165  movsxd  rcx, edx
0x180018168  add     rax, rcx
0x18001816b  mov     [rbp+37h+arg_18], rax
0x18001816f  cmp     r13d, [rbx+1Ch]
0x180018173  jge     short loc_18001818E
0x180018175  sub     r15d, edx
0x180018178  lea     rcx, [rax+r12]; void *
0x18001817c  sub     r15d, r12d
0x18001817f  mov     rdx, rax; Src
0x180018182  movsxd  r8, r15d; Size
0x180018185  call    memmove_0
0x18001818a  mov     rax, [rbp+37h+arg_18]
0x18001818e  mov     r8, r12; Size
0x180018191  lea     rdx, [rbp+37h+Src]; Src
0x180018195  mov     rcx, rax; void *
0x180018198  call    memcpy_0
0x18001819d  inc     dword ptr [rbx+1Ch]
0x1800181a0  lock inc dword ptr [rsi]
0x1800181a3  mov     rcx, r14; this
0x1800181a6  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x1800181ab  test    rsi, rsi
0x1800181ae  jz      short loc_1800181B8
0x1800181b0  mov     rcx, rsi; this
0x1800181b3  call    ?Release@CScriptBody@@QEAAXXZ; CScriptBody::Release(void)
0x1800181b8  mov     rcx, [rbp+37h+bstrString]; bstrString
0x1800181bc  call    cs:__imp_SysFreeString
0x1800181c3  nop     dword ptr [rax+rax+00h]
0x1800181c8  mov     rcx, [rbp+37h+var_40]; bstrString
0x1800181cc  call    cs:__imp_SysFreeString
0x1800181d3  nop     dword ptr [rax+rax+00h]
0x1800181d8  lea     rcx, [rbp+37h+var_A0]; this
0x1800181dc  call    ??1ScriptException@@QEAA@XZ; ScriptException::~ScriptException(void)
0x1800181e1  mov     eax, edi
0x1800181e3  mov     rbx, [rsp+0F0h+arg_0]
0x1800181eb  add     rsp, 0C0h
0x1800181f2  pop     r15
0x1800181f4  pop     r14
0x1800181f6  pop     r13
0x1800181f8  pop     r12
0x1800181fa  pop     rdi
0x1800181fb  pop     rsi
0x1800181fc  pop     rbp
0x1800181fd  retn
0x1800181ff  mov     rcx, r13; Size
0x180018202  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018207  mov     rbx, rax
0x18001820a  test    rax, rax
0x18001820d  jz      short loc_180018258
0x18001820f  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x180018216  mov     dword ptr [rbx+8], 1
0x18001821d  mov     [rbx], rax
0x180018220  mov     dword ptr [rbx+0Ch], 10h
0x180018227  mov     [rbx+10h], r12
0x18001822b  mov     [rbx+18h], r12
0x18001822f  mov     [r14+2B8h], rbx
0x180018236  jmp     loc_180018140
0x18001823b  mov     edx, r15d; int
0x18001823e  mov     rcx, rbx; this
0x180018241  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x180018246  test    eax, eax
0x180018248  jnz     loc_18001815A
0x18001824e  jmp     short loc_18001825F
0x180018250  mov     [rax], rsi
0x180018253  jmp     loc_1800181A0
0x180018258  mov     [r14+2B8h], r12
0x18001825f  mov     edi, 8007000Eh
0x180018264  jmp     loc_1800181A3
0x180018269  cmp     eax, 86664004h
0x18001826e  jnz     loc_1800181B8
0x180018274  lea     rdx, [rbp+37h+arg_18]; struct CActiveScriptError **
0x180018278  mov     [rbp+37h+arg_18], r12
0x18001827c  lea     rcx, [rbp+37h+var_A0]; this
0x180018280  call    ?GetActiveScriptError@CompileScriptException@@QEAAJPEAPEAVCActiveScriptError@@@Z; CompileScriptException::GetActiveScriptError(CActiveScriptError * *)
0x180018285  test    eax, eax
0x180018287  jns     short loc_1800182C6
0x180018289  mov     ebx, [rbp+37h+var_60]
0x18001828c  jmp     loc_180018320
0x180018291  mov     eax, 80070057h
0x180018296  jmp     loc_1800181E3
0x18001829b  or      ecx, 8
0x18001829e  mov     [rbp+37h+Src], ecx
0x1800182a1  jmp     loc_180018070
0x1800182a6  or      edi, 2
0x1800182a9  or      ecx, 4
0x1800182ac  mov     [rbp+37h+Src], ecx
0x1800182af  jmp     loc_180018085
0x1800182b4  or      dword ptr [rbx+1Ch], 1
0x1800182b8  jmp     loc_18001808D
0x1800182bd  or      dword ptr [rbx+1Ch], 2
0x1800182c1  jmp     loc_180018098
0x1800182c6  mov     rbx, [rbp+37h+arg_18]
0x1800182ca  lea     rdx, [rbx+8]
0x1800182ce  test    rbx, rbx
0x1800182d1  jnz     short loc_1800182D6
0x1800182d3  mov     rdx, r12; struct IActiveScriptError *
0x1800182d6  mov     rcx, r14; this
0x1800182d9  call    ?OnScriptError@COleScript@@QEAAJPEAUIActiveScriptError@@@Z; COleScript::OnScriptError(IActiveScriptError *)
0x1800182de  lea     rcx, [rbp+37h+var_A0]; this
0x1800182e2  test    eax, eax
0x1800182e4  jnz     short loc_1800182F2
0x1800182e6  call    ?DetachActiveScriptError@ScriptException@@QEAAXXZ; ScriptException::DetachActiveScriptError(void)
0x1800182eb  mov     edi, 80020101h
0x1800182f0  jmp     short loc_180018302
0x1800182f2  mov     r8, [rbp+37h+arg_30]; struct tagEXCEPINFO *
0x1800182f6  lea     rdx, [rbp+37h+arg_10]; int *
0x1800182fa  call    ?GetError@CompileScriptException@@QEAAXPEAJPEAUtagEXCEPINFO@@@Z; CompileScriptException::GetError(long *,tagEXCEPINFO *)
0x1800182ff  mov     edi, [rbp+37h+arg_10]
0x180018302  mov     rcx, rbx; this
0x180018305  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x18001830a  jmp     loc_1800181B8
0x18001830f  mov     dword ptr [rsi+50h], 1
0x180018316  jmp     loc_180018103
0x18001831b  mov     ebx, 80004005h
0x180018320  lea     rcx, [rbp+37h+var_A0]; this
0x180018324  call    ??1CompileScriptException@@QEAA@XZ; CompileScriptException::~CompileScriptException(void)
0x180018329  mov     eax, ebx
0x18001832b  jmp     loc_1800181E3
0x180018330  mov     rdx, rsi; struct CScriptBody *
0x180018333  mov     rcx, r14; this
0x180018336  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x18001833b  mov     edi, eax
0x18001833d  test    eax, eax
0x18001833f  js      loc_1800181A3
0x180018345  jmp     loc_180018123
```
