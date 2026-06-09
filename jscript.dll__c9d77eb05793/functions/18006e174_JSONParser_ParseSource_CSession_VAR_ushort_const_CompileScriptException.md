# JSONParser::ParseSource(CSession *,VAR *,ushort const *,CompileScriptException *)

- ea: `0x18006e174`
- end: `0x18006e306`
- name: `?ParseSource@JSONParser@@QEAAJPEAVCSession@@PEAVVAR@@PEBGPEAVCompileScriptException@@@Z`
- size: `402`
- prototype: `__int64 __fastcall(JSONParser *__hidden this, struct CSession *, struct VAR *, const unsigned __int16 *, struct CompileScriptException *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006bdb0`

## callees

- `0x18001f400`
- `0x18002bdd0`
- `0x180048390`
- `0x180049968`
- `0x180049e48`
- `0x180069c04`
- `0x18006db48`
- `0x18006e174`
- `0x1800742e8`
- `0x180094252`
- `0x18009429a`

## import_xrefs

- `msvcrt!_controlfp` at `0x18006e19e`
- `msvcrt!_controlfp` at `0x18006e1b1`
- `msvcrt!_controlfp` at `0x18006e2f3`
- `msvcrt!_controlfp` at `0x18006e19e`
- `msvcrt!_controlfp` at `0x18006e1b1`
- `msvcrt!_controlfp` at `0x18006e2f3`

## pseudocode

```c
__int64 __fastcall JSONParser::ParseSource(
        JSONParser *this,
        struct COleScript **a2,
        struct VAR *a3,
        const unsigned __int16 *a4,
        struct CompileScriptException *a5)
{
  unsigned int v7; // ecx
  struct HashTbl *v8; // rax
  Scanner *v9; // rax
  unsigned __int64 v10; // rdx
  unsigned int v11; // ebx
  unsigned int NewValue; // [rsp+40h] [rbp-10h]

  NewValue = _controlfp(0, 0);
  _controlfp(0x1Fu, 0x30F031Fu);
  *((_QWORD *)this + 39) = a2;
  if ( a5 )
    memset_0(a5, 0, 0x68u);
  if ( setjmp_0((_JBTYPE *)this + 1) )
  {
    v11 = CompileScriptException::ProcessError(
            a5,
            a2[5],
            *((struct Scanner **)this + 38),
            (JSONParser *)((char *)this + 16),
            0,
            0,
            0,
            a4);
  }
  else
  {
    if ( !a4 )
      JSONParser::Error(this, 5);
    v8 = HashTbl::Create(v7, (JSONParser *)((char *)this + 16));
    *(_QWORD *)this = v8;
    if ( !v8 )
      JSONParser::Error(this, 1001);
    v9 = Scanner::Create(v8, (JSONParser *)((char *)this + 288), (JSONParser *)((char *)this + 16));
    *((_QWORD *)this + 38) = v9;
    if ( !v9 )
      JSONParser::Error(this, 1001);
    Scanner::SetText(v9, a4, 0);
    Scanner::Scan(*((_QWORD *)this + 38), v10);
    JSONParser::ParseObject(this, (struct CSession *)a2, a3);
    if ( *((_DWORD *)this + 72) != 127 )
      JSONParser::Error(this, 1002);
    Scanner::Release(*((Scanner **)this + 38));
    *((_QWORD *)this + 38) = 0;
    v11 = 0;
  }
  _controlfp(NewValue, 0xFFFFFFFF);
  return v11;
}

```

## disassembly

```asm
0x18006e174  mov     rax, rsp
0x18006e177  mov     [rax+20h], r9
0x18006e17b  mov     [rax+18h], r8
0x18006e17f  mov     [rax+10h], rdx
0x18006e183  mov     [rax+8], rcx
0x18006e187  push    rbp
0x18006e188  push    rbx
0x18006e189  push    rsi
0x18006e18a  push    rdi
0x18006e18b  push    r14
0x18006e18d  mov     rbp, rsp
0x18006e190  sub     rsp, 50h
0x18006e194  mov     rbx, rdx
0x18006e197  mov     rdi, rcx
0x18006e19a  xor     edx, edx; Mask
0x18006e19c  xor     ecx, ecx; NewValue
0x18006e19e  call    cs:__imp__controlfp
0x18006e1a4  mov     edx, 30F031Fh; Mask
0x18006e1a9  mov     ecx, 1Fh; NewValue
0x18006e1ae  mov     [rbp+NewValue], eax
0x18006e1b1  call    cs:__imp__controlfp
0x18006e1b7  mov     rcx, [rbp+arg_20]; void *
0x18006e1bb  mov     [rdi+138h], rbx
0x18006e1c2  test    rcx, rcx
0x18006e1c5  jz      short loc_18006E1D2
0x18006e1c7  xor     edx, edx; Val
0x18006e1c9  lea     r8d, [rdx+68h]; Size
0x18006e1cd  call    memset_0
0x18006e1d2  lea     rcx, [rdi+10h]; Buf
0x18006e1d6  mov     rdx, rsp
0x18006e1d9  call    _setjmp_0
0x18006e1de  test    eax, eax
0x18006e1e0  jnz     loc_18006E2A8
0x18006e1e6  mov     rdi, [rbp+arg_18]
0x18006e1ea  test    rdi, rdi
0x18006e1ed  jnz     short loc_18006E1FC
0x18006e1ef  mov     rcx, [rbp+arg_0]; this
0x18006e1f3  lea     edx, [rax+5]; int
0x18006e1f6  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006e1fc  mov     rbx, [rbp+arg_0]
0x18006e200  lea     rdx, [rbx+10h]; struct ErrHandler *
0x18006e204  call    ?Create@HashTbl@@SAPEAV1@IPEAVErrHandler@@@Z; HashTbl::Create(uint,ErrHandler *)
0x18006e209  mov     [rbx], rax
0x18006e20c  test    rax, rax
0x18006e20f  jnz     short loc_18006E21F
0x18006e211  mov     edx, 3E9h; int
0x18006e216  mov     rcx, rbx; this
0x18006e219  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006e21f  lea     r14, [rbx+120h]
0x18006e226  mov     rcx, rax; struct HashTbl *
0x18006e229  mov     rdx, r14; struct Token *
0x18006e22c  lea     r8, [rbx+10h]; struct ErrHandler *
0x18006e230  call    ?Create@Scanner@@SAPEAV1@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Create(HashTbl *,Token *,ErrHandler *)
0x18006e235  mov     [rbx+130h], rax
0x18006e23c  test    rax, rax
0x18006e23f  jnz     short loc_18006E24F
0x18006e241  mov     edx, 3E9h; int
0x18006e246  mov     rcx, rbx; this
0x18006e249  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006e24f  xor     r8d, r8d; unsigned int
0x18006e252  mov     rdx, rdi; unsigned __int16 *
0x18006e255  mov     rcx, rax; this
0x18006e258  call    ?SetText@Scanner@@QEAAXPEBGK@Z; Scanner::SetText(ushort const *,ulong)
0x18006e25d  mov     rcx, [rbx+130h]
0x18006e264  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006e269  mov     r8, [rbp+arg_10]; struct VAR *
0x18006e26d  mov     rcx, rbx; this
0x18006e270  mov     rdx, [rbp+arg_8]; struct CSession *
0x18006e274  call    ?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z; JSONParser::ParseObject(CSession *,VAR *)
0x18006e279  cmp     dword ptr [r14], 7Fh
0x18006e27d  jz      short loc_18006E28D
0x18006e27f  mov     edx, 3EAh; int
0x18006e284  mov     rcx, rbx; this
0x18006e287  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006e28d  mov     rcx, [rbx+130h]; this
0x18006e294  call    ?Release@Scanner@@QEAAXXZ; Scanner::Release(void)
0x18006e299  mov     qword ptr [rbx+130h], 0
0x18006e2a4  xor     ebx, ebx
0x18006e2a6  jmp     short loc_18006E2ED
0x18006e2a8  mov     r8, [rbp+arg_0]
0x18006e2ac  mov     rax, [rbp+arg_18]
0x18006e2b0  mov     rdx, [rbp+arg_8]
0x18006e2b4  mov     rcx, [rbp+arg_20]; this
0x18006e2b8  mov     [rsp+50h+var_18], rax; unsigned __int16 *
0x18006e2bd  lea     r9, [r8+10h]; struct ErrHandler *
0x18006e2c1  mov     r8, [r8+130h]; struct Scanner *
0x18006e2c8  mov     rdx, [rdx+28h]; struct COleScript *
0x18006e2cc  mov     [rsp+50h+psz], 0; psz
0x18006e2d5  mov     [rsp+50h+len], 0; len
0x18006e2dd  mov     [rsp+50h+var_30], 0; struct ParseNode *
0x18006e2e6  call    ?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z; CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)
0x18006e2eb  mov     ebx, eax
0x18006e2ed  mov     ecx, [rbp+NewValue]; NewValue
0x18006e2f0  or      edx, 0FFFFFFFFh; Mask
0x18006e2f3  call    cs:__imp__controlfp
0x18006e2f9  mov     eax, ebx
0x18006e2fb  add     rsp, 50h
0x18006e2ff  pop     r14
0x18006e301  pop     rdi
0x18006e302  pop     rsi
0x18006e303  pop     rbx
0x18006e304  pop     rbp
0x18006e305  retn
```
