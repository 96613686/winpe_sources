# CXMLReader::ReduceStack(CParseNode *)

- ea: `0x1800286bc`
- end: `0x180028733`
- name: `?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z`
- size: `119`
- prototype: `void __fastcall(CXMLReader *__hidden this, struct CParseNode *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180023fe0`
- `0x1800263a4`
- `0x1800287cc`

## callees

- `0x180026d20`
- `0x18002748c`
- `0x1800286bc`

## pseudocode

```c
void __fastcall CXMLReader::ReduceStack(CXMLReader *this, struct CParseNode *a2)
{
  CNodeStack *v3; // rsi
  __int64 v5; // rcx
  __int64 v7; // rax
  CParseNode *v8; // rax
  struct CParseNode *v9; // rbx

  v3 = (CXMLReader *)((char *)this + 416);
  do
  {
    v8 = (CParseNode *)CNodeStack::Pop(v3);
    v9 = v8;
    if ( !v8 )
      break;
    CParseNode::Init(v8, 0, 0, 0, 0, 0);
    v5 = *((_QWORD *)this + 51);
    if ( (*(_DWORD *)(v5 + 20))-- == 1 )
    {
      v7 = *(_QWORD *)(v5 + 8);
      if ( v7 )
        continue;
    }
    v7 = v5;
    *((_QWORD *)this + 51) = v7;
  }
  while ( v9 != a2 );
}

```

## disassembly

```asm
0x1800286bc  push    rbx
0x1800286be  push    rbp
0x1800286bf  push    rsi
0x1800286c0  push    rdi
0x1800286c1  sub     rsp, 38h
0x1800286c5  mov     rbp, rdx
0x1800286c8  lea     rsi, [rcx+1A0h]
0x1800286cf  mov     rdi, rcx
0x1800286d2  jmp     short loc_180028719
0x1800286d4  mov     [rsp+58h+var_30], 0; unsigned int
0x1800286dc  xor     r9d, r9d; unsigned __int16 *
0x1800286df  xor     r8d, r8d; unsigned int
0x1800286e2  mov     [rsp+58h+var_38], 0; unsigned int
0x1800286ea  xor     edx, edx; struct CParseNode *
0x1800286ec  mov     rcx, rbx; this
0x1800286ef  call    ?Init@CParseNode@@QEAAJPEAV1@KPEBGKK@Z; CParseNode::Init(CParseNode *,ulong,ushort const *,ulong,ulong)
0x1800286f4  mov     rcx, [rdi+198h]
0x1800286fb  add     dword ptr [rcx+14h], 0FFFFFFFFh
0x1800286ff  jnz     short loc_18002870A
0x180028701  mov     rax, [rcx+8]
0x180028705  test    rax, rax
0x180028708  jnz     short loc_18002870D
0x18002870a  mov     rax, rcx
0x18002870d  mov     [rdi+198h], rax
0x180028714  cmp     rbx, rbp
0x180028717  jz      short loc_180028729
0x180028719  mov     rcx, rsi; this
0x18002871c  call    ?Pop@CNodeStack@@QEAAPEAXXZ; CNodeStack::Pop(void)
0x180028721  mov     rbx, rax
0x180028724  test    rax, rax
0x180028727  jnz     short loc_1800286D4
0x180028729  add     rsp, 38h
0x18002872d  pop     rdi
0x18002872e  pop     rsi
0x18002872f  pop     rbp
0x180028730  pop     rbx
0x180028731  retn
```
