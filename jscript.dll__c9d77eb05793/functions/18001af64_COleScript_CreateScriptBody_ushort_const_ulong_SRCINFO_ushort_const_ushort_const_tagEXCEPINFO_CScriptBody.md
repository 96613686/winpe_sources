# COleScript::CreateScriptBody(ushort const *,ulong,SRCINFO *,ushort const *,ushort const *,tagEXCEPINFO *,CScriptBody * *)

- ea: `0x18001af64`
- end: `0x18001b2a1`
- name: `?CreateScriptBody@COleScript@@QEAAJPEBGKPEAVSRCINFO@@00PEAUtagEXCEPINFO@@PEAPEAVCScriptBody@@@Z`
- size: `829`
- prototype: `__int64 __fastcall(COleScript *this, const unsigned __int16 *, int, struct SRCINFO *, wchar_t *String2, const unsigned __int16 *, struct tagEXCEPINFO *, struct CScriptBody **)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18001aa80`
- `0x18004d6ec`

## callees

- `0x180003fac`
- `0x180019c60`
- `0x180019e28`
- `0x18001a29c`
- `0x18001a9d4`
- `0x18001af64`
- `0x18001b344`
- `0x18001b560`
- `0x1800304c0`
- `0x18004b26c`
- `0x1800576a0`
- `0x180073dc0`
- `0x180073e58`
- `0x1800744d0`
- `0x1800782bc`
- `0x18007a194`
- `0x18007bab4`
- `0x180094282`
- `0x18009428e`
- `0x18009429a`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001b120`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b12a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b120`
- `OLEAUT32!__imp_SysFreeString` at `0x18001b12a`

## pseudocode

```c
__int64 __fastcall COleScript::CreateScriptBody(
        COleScript *this,
        const unsigned __int16 *a2,
        int a3,
        struct SRCINFO *a4,
        wchar_t *String2,
        const unsigned __int16 *a6,
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
  v15 = COleScript::Compile(this, &v28, a2, v14, a4, 32, a6, (struct CompileScriptException *)v29);
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
0x18001af64  mov     [rsp-8+arg_0], rbx
0x18001af69  push    rbp
0x18001af6a  push    rsi
0x18001af6b  push    rdi
0x18001af6c  push    r12
0x18001af6e  push    r13
0x18001af70  push    r14
0x18001af72  push    r15
0x18001af74  lea     rbp, [rsp-7]
0x18001af79  sub     rsp, 0C0h
0x18001af80  mov     eax, [r9+18h]
0x18001af84  xor     r12d, r12d
0x18001af87  mov     [rbp+37h+var_AC], eax
0x18001af8a  mov     rbx, r9
0x18001af8d  mov     eax, r8d
0x18001af90  mov     [rbp+37h+var_A8], r12
0x18001af94  and     eax, 60h
0x18001af97  mov     r15d, r8d
0x18001af9a  mov     rsi, rdx
0x18001af9d  mov     r14, rcx
0x18001afa0  cmp     al, 60h ; '`'
0x18001afa2  jz      loc_18001B1E8
0x18001afa8  mov     rcx, [rbp+37h+String2]; String2
0x18001afac  call    ?ComputeGrfscr@@YAKPEBG@Z; ComputeGrfscr(ushort const *)
0x18001afb1  lea     ecx, [r12+2]
0x18001afb6  test    r15b, 40h
0x18001afba  mov     edi, eax
0x18001afbc  mov     edx, r15d
0x18001afbf  lea     eax, [rcx+1]
0x18001afc2  cmovnz  ecx, eax
0x18001afc5  mov     [rbp+37h+Src], ecx
0x18001afc8  and     edx, 80h
0x18001afce  jnz     loc_18001B1F2
0x18001afd4  mov     r8d, 80000020h
0x18001afda  mov     eax, r15d
0x18001afdd  and     eax, r8d
0x18001afe0  cmp     eax, r8d
0x18001afe3  jz      loc_18001B1FD
0x18001afe9  test    edx, edx
0x18001afeb  jnz     loc_18001B20B
0x18001aff1  bt      r15d, 1Eh
0x18001aff6  jb      loc_18001B214
0x18001affc  xor     edx, edx; Val
0x18001affe  lea     rcx, [rbp+37h+var_A0]; void *
0x18001b002  lea     r8d, [rdx+50h]; Size
0x18001b006  call    memset_0
0x18001b00b  lea     rax, [rbp+37h+var_A0]
0x18001b00f  mov     [rbp+37h+var_50], r12
0x18001b013  mov     [rsp+0F0h+var_B8], rax; struct CompileScriptException *
0x18001b018  lea     rdx, [rbp+37h+var_A8]; struct CScriptBody **
0x18001b01c  mov     rax, [rbp+37h+arg_28]
0x18001b020  mov     r13d, 20h ; ' '
0x18001b026  mov     [rsp+0F0h+var_C0], rax; unsigned __int16 *
0x18001b02b  mov     r9d, edi; unsigned int
0x18001b02e  mov     [rsp+0F0h+var_C8], r13d; int
0x18001b033  mov     r8, rsi; unsigned __int16 *
0x18001b036  mov     rcx, r14; this
0x18001b039  mov     [rsp+0F0h+var_D0], rbx; void *
0x18001b03e  mov     [rbp+37h+bstrString], r12
0x18001b042  mov     [rbp+37h+var_40], r12
0x18001b046  call    ?Compile@COleScript@@QEAAJPEAPEAVCScriptBody@@PEBGKPEAXJ1PEAVCompileScriptException@@@Z; COleScript::Compile(CScriptBody * *,ushort const *,ulong,void *,long,ushort const *,CompileScriptException *)
0x18001b04b  mov     [rbp+37h+arg_10], eax
0x18001b04e  mov     edi, eax
0x18001b050  test    eax, eax
0x18001b052  js      loc_18001B1C0
0x18001b058  mov     rsi, [rbp+37h+var_A8]
0x18001b05c  bt      r15d, 8
0x18001b061  jb      loc_18001B266
0x18001b067  mov     rcx, r14; this
0x18001b06a  call    ?DisableInterrupts@COleScript@@AEAAHXZ; COleScript::DisableInterrupts(void)
0x18001b06f  test    eax, eax
0x18001b071  jz      loc_18001B272
0x18001b077  mov     rcx, r14; this
0x18001b07a  call    ?FDebuggerEnabled@COleScript@@QEAAHXZ; COleScript::FDebuggerEnabled(void)
0x18001b07f  test    eax, eax
0x18001b081  jnz     loc_18001B287
0x18001b087  mov     rax, [rbp+37h+arg_38]
0x18001b08b  test    rax, rax
0x18001b08e  jnz     loc_18001B1A7
0x18001b094  mov     rbx, [r14+2B8h]
0x18001b09b  test    rbx, rbx
0x18001b09e  jz      loc_18001B156
0x18001b0a4  mov     r13d, [rbx+1Ch]
0x18001b0a8  movsxd  r12, dword ptr [rbx+0Ch]
0x18001b0ac  lea     r15d, [r13+1]
0x18001b0b0  imul    r15d, r12d
0x18001b0b4  cmp     r15d, [rbx+18h]
0x18001b0b8  jg      loc_18001B192
0x18001b0be  mov     rax, [rbx+10h]
0x18001b0c2  mov     edx, r12d
0x18001b0c5  imul    edx, r13d
0x18001b0c9  movsxd  rcx, edx
0x18001b0cc  add     rax, rcx
0x18001b0cf  mov     [rbp+37h+arg_18], rax
0x18001b0d3  cmp     r13d, [rbx+1Ch]
0x18001b0d7  jge     short loc_18001B0F2
0x18001b0d9  sub     r15d, edx
0x18001b0dc  lea     rcx, [rax+r12]; void *
0x18001b0e0  sub     r15d, r12d
0x18001b0e3  mov     rdx, rax; Src
0x18001b0e6  movsxd  r8, r15d; Size
0x18001b0e9  call    memmove_0
0x18001b0ee  mov     rax, [rbp+37h+arg_18]
0x18001b0f2  mov     r8, r12; Size
0x18001b0f5  lea     rdx, [rbp+37h+Src]; Src
0x18001b0f9  mov     rcx, rax; void *
0x18001b0fc  call    memcpy_0
0x18001b101  inc     dword ptr [rbx+1Ch]
0x18001b104  lock inc dword ptr [rsi]
0x18001b107  mov     rcx, r14; this
0x18001b10a  call    ?EnableInterrupts@COleScript@@AEAAXXZ; COleScript::EnableInterrupts(void)
0x18001b10f  test    rsi, rsi
0x18001b112  jz      short loc_18001B11C
0x18001b114  mov     rcx, rsi; this
0x18001b117  call    ?Release@CScriptBody@@QEAAXXZ; CScriptBody::Release(void)
0x18001b11c  mov     rcx, [rbp+37h+bstrString]; bstrString
0x18001b120  call    cs:__imp_SysFreeString
0x18001b126  mov     rcx, [rbp+37h+var_40]; bstrString
0x18001b12a  call    cs:__imp_SysFreeString
0x18001b130  lea     rcx, [rbp+37h+var_A0]; this
0x18001b134  call    ??1ScriptException@@QEAA@XZ; ScriptException::~ScriptException(void)
0x18001b139  mov     eax, edi
0x18001b13b  mov     rbx, [rsp+0F0h+arg_0]
0x18001b143  add     rsp, 0C0h
0x18001b14a  pop     r15
0x18001b14c  pop     r14
0x18001b14e  pop     r13
0x18001b150  pop     r12
0x18001b152  pop     rdi
0x18001b153  pop     rsi
0x18001b154  pop     rbp
0x18001b155  retn
0x18001b156  mov     rcx, r13; Size
0x18001b159  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001b15e  mov     rbx, rax
0x18001b161  test    rax, rax
0x18001b164  jz      short loc_18001B1AF
0x18001b166  lea     rax, ??_7GL@@6B@; const GL::`vftable'
0x18001b16d  mov     dword ptr [rbx+8], 1
0x18001b174  mov     [rbx], rax
0x18001b177  mov     dword ptr [rbx+0Ch], 10h
0x18001b17e  mov     [rbx+10h], r12
0x18001b182  mov     [rbx+18h], r12
0x18001b186  mov     [r14+2B8h], rbx
0x18001b18d  jmp     loc_18001B0A4
0x18001b192  mov     edx, r15d; int
0x18001b195  mov     rcx, rbx; this
0x18001b198  call    ?FEnsureSize@GL@@AEAAHJ@Z; GL::FEnsureSize(long)
0x18001b19d  test    eax, eax
0x18001b19f  jnz     loc_18001B0BE
0x18001b1a5  jmp     short loc_18001B1B6
0x18001b1a7  mov     [rax], rsi
0x18001b1aa  jmp     loc_18001B104
0x18001b1af  mov     [r14+2B8h], r12
0x18001b1b6  mov     edi, 8007000Eh
0x18001b1bb  jmp     loc_18001B107
0x18001b1c0  cmp     eax, 86664004h
0x18001b1c5  jnz     loc_18001B11C
0x18001b1cb  lea     rdx, [rbp+37h+arg_18]; struct CActiveScriptError **
0x18001b1cf  mov     [rbp+37h+arg_18], r12
0x18001b1d3  lea     rcx, [rbp+37h+var_A0]; this
0x18001b1d7  call    ?GetActiveScriptError@CompileScriptException@@QEAAJPEAPEAVCActiveScriptError@@@Z; CompileScriptException::GetActiveScriptError(CActiveScriptError * *)
0x18001b1dc  test    eax, eax
0x18001b1de  jns     short loc_18001B21D
0x18001b1e0  mov     ebx, [rbp+37h+var_60]
0x18001b1e3  jmp     loc_18001B277
0x18001b1e8  mov     eax, 80070057h
0x18001b1ed  jmp     loc_18001B13B
0x18001b1f2  or      ecx, 8
0x18001b1f5  mov     [rbp+37h+Src], ecx
0x18001b1f8  jmp     loc_18001AFD4
0x18001b1fd  or      edi, 2
0x18001b200  or      ecx, 4
0x18001b203  mov     [rbp+37h+Src], ecx
0x18001b206  jmp     loc_18001AFE9
0x18001b20b  or      dword ptr [rbx+1Ch], 1
0x18001b20f  jmp     loc_18001AFF1
0x18001b214  or      dword ptr [rbx+1Ch], 2
0x18001b218  jmp     loc_18001AFFC
0x18001b21d  mov     rbx, [rbp+37h+arg_18]
0x18001b221  lea     rdx, [rbx+8]
0x18001b225  test    rbx, rbx
0x18001b228  jnz     short loc_18001B22D
0x18001b22a  mov     rdx, r12; struct IActiveScriptError *
0x18001b22d  mov     rcx, r14; this
0x18001b230  call    ?OnScriptError@COleScript@@QEAAJPEAUIActiveScriptError@@@Z; COleScript::OnScriptError(IActiveScriptError *)
0x18001b235  lea     rcx, [rbp+37h+var_A0]; this
0x18001b239  test    eax, eax
0x18001b23b  jnz     short loc_18001B249
0x18001b23d  call    ?DetachActiveScriptError@ScriptException@@QEAAXXZ; ScriptException::DetachActiveScriptError(void)
0x18001b242  mov     edi, 80020101h
0x18001b247  jmp     short loc_18001B259
0x18001b249  mov     r8, [rbp+37h+arg_30]; struct tagEXCEPINFO *
0x18001b24d  lea     rdx, [rbp+37h+arg_10]; int *
0x18001b251  call    ?GetError@CompileScriptException@@QEAAXPEAJPEAUtagEXCEPINFO@@@Z; CompileScriptException::GetError(long *,tagEXCEPINFO *)
0x18001b256  mov     edi, [rbp+37h+arg_10]
0x18001b259  mov     rcx, rbx; this
0x18001b25c  call    ?Release@CActiveScriptError@@UEAAKXZ; CActiveScriptError::Release(void)
0x18001b261  jmp     loc_18001B11C
0x18001b266  mov     dword ptr [rsi+50h], 1
0x18001b26d  jmp     loc_18001B067
0x18001b272  mov     ebx, 80004005h
0x18001b277  lea     rcx, [rbp+37h+var_A0]; this
0x18001b27b  call    ??1CompileScriptException@@QEAA@XZ; CompileScriptException::~CompileScriptException(void)
0x18001b280  mov     eax, ebx
0x18001b282  jmp     loc_18001B13B
0x18001b287  mov     rdx, rsi; struct CScriptBody *
0x18001b28a  mov     rcx, r14; this
0x18001b28d  call    ?DbgRegisterScriptBlock@COleScript@@QEAAJPEAVCScriptBody@@@Z; COleScript::DbgRegisterScriptBlock(CScriptBody *)
0x18001b292  mov     edi, eax
0x18001b294  test    eax, eax
0x18001b296  js      loc_18001B107
0x18001b29c  jmp     loc_18001B087
```
