# JSONParser::ParseSource(CSession *,VAR *,ushort const *,CompileScriptException *)

- ea: `0x18006f530`
- end: `0x18006f6d5`
- name: `?ParseSource@JSONParser@@QEAAJPEAVCSession@@PEAVVAR@@PEBGPEAVCompileScriptException@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(JSONParser *__hidden this, struct CSession *, struct VAR *, const unsigned __int16 *, struct CompileScriptException *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d0e0`

## callees

- `0x18001c430`
- `0x180029010`
- `0x18004904c`
- `0x18004a538`
- `0x18004aaac`
- `0x18006af44`
- `0x18006eee0`
- `0x18006f530`
- `0x1800757dc`
- `0x180096662`
- `0x1800966aa`

## import_xrefs

- `msvcrt!_controlfp` at `0x18006f55a`
- `msvcrt!_controlfp` at `0x18006f573`
- `msvcrt!_controlfp` at `0x18006f6bb`
- `msvcrt!_controlfp` at `0x18006f55a`
- `msvcrt!_controlfp` at `0x18006f573`
- `msvcrt!_controlfp` at `0x18006f6bb`

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
0x18006f530  mov     rax, rsp
0x18006f533  mov     [rax+20h], r9
0x18006f537  mov     [rax+18h], r8
0x18006f53b  mov     [rax+10h], rdx
0x18006f53f  mov     [rax+8], rcx
0x18006f543  push    rbp
0x18006f544  push    rbx
0x18006f545  push    rsi
0x18006f546  push    rdi
0x18006f547  push    r14
0x18006f549  mov     rbp, rsp
0x18006f54c  sub     rsp, 50h
0x18006f550  mov     rbx, rdx
0x18006f553  mov     rdi, rcx
0x18006f556  xor     edx, edx; Mask
0x18006f558  xor     ecx, ecx; NewValue
0x18006f55a  call    cs:__imp__controlfp
0x18006f561  nop     dword ptr [rax+rax+00h]
0x18006f566  mov     edx, 30F031Fh; Mask
0x18006f56b  mov     ecx, 1Fh; NewValue
0x18006f570  mov     [rbp+NewValue], eax
0x18006f573  call    cs:__imp__controlfp
0x18006f57a  nop     dword ptr [rax+rax+00h]
0x18006f57f  mov     rcx, [rbp+arg_20]; void *
0x18006f583  mov     [rdi+138h], rbx
0x18006f58a  test    rcx, rcx
0x18006f58d  jz      short loc_18006F59A
0x18006f58f  xor     edx, edx; Val
0x18006f591  lea     r8d, [rdx+68h]; Size
0x18006f595  call    memset_0
0x18006f59a  lea     rcx, [rdi+10h]; Buf
0x18006f59e  mov     rdx, rsp
0x18006f5a1  call    _setjmp_0
0x18006f5a6  test    eax, eax
0x18006f5a8  jnz     loc_18006F670
0x18006f5ae  mov     rdi, [rbp+arg_18]
0x18006f5b2  test    rdi, rdi
0x18006f5b5  jnz     short loc_18006F5C4
0x18006f5b7  mov     rcx, [rbp+arg_0]; this
0x18006f5bb  lea     edx, [rax+5]; int
0x18006f5be  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f5c4  mov     rbx, [rbp+arg_0]
0x18006f5c8  lea     rdx, [rbx+10h]; struct ErrHandler *
0x18006f5cc  call    ?Create@HashTbl@@SAPEAV1@IPEAVErrHandler@@@Z; HashTbl::Create(uint,ErrHandler *)
0x18006f5d1  mov     [rbx], rax
0x18006f5d4  test    rax, rax
0x18006f5d7  jnz     short loc_18006F5E7
0x18006f5d9  mov     edx, 3E9h; int
0x18006f5de  mov     rcx, rbx; this
0x18006f5e1  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f5e7  lea     r14, [rbx+120h]
0x18006f5ee  mov     rcx, rax; struct HashTbl *
0x18006f5f1  mov     rdx, r14; struct Token *
0x18006f5f4  lea     r8, [rbx+10h]; struct ErrHandler *
0x18006f5f8  call    ?Create@Scanner@@SAPEAV1@PEAVHashTbl@@PEAUToken@@PEAVErrHandler@@@Z; Scanner::Create(HashTbl *,Token *,ErrHandler *)
0x18006f5fd  mov     [rbx+130h], rax
0x18006f604  test    rax, rax
0x18006f607  jnz     short loc_18006F617
0x18006f609  mov     edx, 3E9h; int
0x18006f60e  mov     rcx, rbx; this
0x18006f611  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f617  xor     r8d, r8d; unsigned int
0x18006f61a  mov     rdx, rdi; unsigned __int16 *
0x18006f61d  mov     rcx, rax; this
0x18006f620  call    ?SetText@Scanner@@QEAAXPEBGK@Z; Scanner::SetText(ushort const *,ulong)
0x18006f625  mov     rcx, [rbx+130h]
0x18006f62c  call    ?Scan@Scanner@@QEAA?AW4tokens@@XZ; Scanner::Scan(void)
0x18006f631  mov     r8, [rbp+arg_10]; struct VAR *
0x18006f635  mov     rcx, rbx; this
0x18006f638  mov     rdx, [rbp+arg_8]; struct CSession *
0x18006f63c  call    ?ParseObject@JSONParser@@AEAAXPEAVCSession@@PEAVVAR@@@Z; JSONParser::ParseObject(CSession *,VAR *)
0x18006f641  cmp     dword ptr [r14], 7Fh
0x18006f645  jz      short loc_18006F655
0x18006f647  mov     edx, 3EAh; int
0x18006f64c  mov     rcx, rbx; this
0x18006f64f  call    ?Error@JSONParser@@AEAAXH@Z; JSONParser::Error(int)
0x18006f655  mov     rcx, [rbx+130h]; this
0x18006f65c  call    ?Release@Scanner@@QEAAXXZ; Scanner::Release(void)
0x18006f661  mov     qword ptr [rbx+130h], 0
0x18006f66c  xor     ebx, ebx
0x18006f66e  jmp     short loc_18006F6B5
0x18006f670  mov     r8, [rbp+arg_0]
0x18006f674  mov     rax, [rbp+arg_18]
0x18006f678  mov     rdx, [rbp+arg_8]
0x18006f67c  mov     rcx, [rbp+arg_20]; this
0x18006f680  mov     [rsp+50h+var_18], rax; unsigned __int16 *
0x18006f685  lea     r9, [r8+10h]; struct ErrHandler *
0x18006f689  mov     r8, [r8+130h]; struct Scanner *
0x18006f690  mov     rdx, [rdx+28h]; struct COleScript *
0x18006f694  mov     [rsp+50h+var_20], 0; char *
0x18006f69d  mov     [rsp+50h+var_28], 0; unsigned int
0x18006f6a5  mov     [rsp+50h+var_30], 0; struct ParseNode *
0x18006f6ae  call    ?ProcessError@CompileScriptException@@QEAAJPEAVCOleScript@@PEAVScanner@@PEAVErrHandler@@PEAUParseNode@@JPEAXPEBG@Z; CompileScriptException::ProcessError(COleScript *,Scanner *,ErrHandler *,ParseNode *,long,void *,ushort const *)
0x18006f6b3  mov     ebx, eax
0x18006f6b5  mov     ecx, [rbp+NewValue]; NewValue
0x18006f6b8  or      edx, 0FFFFFFFFh; Mask
0x18006f6bb  call    cs:__imp__controlfp
0x18006f6c2  nop     dword ptr [rax+rax+00h]
0x18006f6c7  mov     eax, ebx
0x18006f6c9  add     rsp, 50h
0x18006f6cd  pop     r14
0x18006f6cf  pop     rdi
0x18006f6d0  pop     rsi
0x18006f6d1  pop     rbx
0x18006f6d2  pop     rbp
0x18006f6d3  retn
```
