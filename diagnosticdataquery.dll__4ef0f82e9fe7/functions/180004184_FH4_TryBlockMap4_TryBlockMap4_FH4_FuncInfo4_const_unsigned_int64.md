# FH4::TryBlockMap4::TryBlockMap4(FH4::FuncInfo4 const *,unsigned __int64)

- ea: `0x180004184`
- end: `0x180004268`
- name: `??0TryBlockMap4@FH4@@QEAA@PEBUFuncInfo4@1@_K@Z`
- size: `228`
- prototype: `FH4::TryBlockMap4 *__fastcall(FH4::TryBlockMap4 *this, const struct FH4::FuncInfo4 *, __int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033d8`
- `0x1800038f4`
- `0x180003e28`

## callees

- `0x180004184`

## pseudocode

```c
FH4::TryBlockMap4 *__fastcall FH4::TryBlockMap4::TryBlockMap4(
        FH4::TryBlockMap4 *this,
        const struct FH4::FuncInfo4 *a2,
        __int64 a3)
{
  _BYTE *v4; // rdx
  __int64 v5; // rcx
  _BYTE *v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  _BYTE *v9; // rdx
  int v10; // eax
  __int64 v11; // rcx
  _BYTE *v12; // rdx
  int v13; // eax
  __int64 v14; // rcx
  _DWORD *v15; // rdx

  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 2) = 0;
  *(_OWORD *)((char *)this + 24) = 0;
  if ( *((_DWORD *)a2 + 3) )
  {
    v4 = (_BYTE *)(a3 + *((int *)a2 + 3));
    *((_QWORD *)this + 1) = v4;
    v5 = *v4 & 0xF;
    v6 = &v4[-*((char *)&FH4::s_negLengthTab + v5)];
    v7 = *((_DWORD *)v6 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v5);
    *((_QWORD *)this + 1) = v6;
    *(_DWORD *)this = v7;
    *((_QWORD *)this + 2) = v6;
    v8 = *v6 & 0xF;
    v9 = &v6[-*((char *)&FH4::s_negLengthTab + v8)];
    v10 = *((_DWORD *)v9 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v8);
    *((_QWORD *)this + 1) = v9;
    *((_DWORD *)this + 6) = v10;
    v11 = *v9 & 0xF;
    v12 = &v9[-*((char *)&FH4::s_negLengthTab + v11)];
    v13 = *((_DWORD *)v12 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v11);
    *((_QWORD *)this + 1) = v12;
    *((_DWORD *)this + 7) = v13;
    v14 = *v12 & 0xF;
    v15 = &v12[-*((char *)&FH4::s_negLengthTab + v14)];
    *((_DWORD *)this + 8) = *(v15 - 1) >> *((_BYTE *)&FH4::s_shiftTab + v14);
    *((_QWORD *)this + 1) = v15;
    LODWORD(v14) = *v15;
    *((_QWORD *)this + 1) = v15 + 1;
    *((_DWORD *)this + 9) = v14;
  }
  else
  {
    *(_DWORD *)this = 0;
  }
  return this;
}

```

## disassembly

```asm
0x180004184  xor     eax, eax
0x180004186  xorps   xmm0, xmm0
0x180004189  mov     [rcx+8], rax
0x18000418d  mov     r9, rcx
0x180004190  mov     [rcx+10h], rax
0x180004194  movups  xmmword ptr [rcx+18h], xmm0
0x180004198  cmp     [rdx+0Ch], eax
0x18000419b  jz      loc_180004262
0x1800041a1  movsxd  rdx, dword ptr [rdx+0Ch]
0x1800041a5  add     rdx, r8
0x1800041a8  lea     r8, cs:180000000h
0x1800041af  mov     [rcx+8], rdx
0x1800041b3  movzx   ecx, byte ptr [rdx]
0x1800041b6  and     ecx, 0Fh
0x1800041b9  movsx   rax, byte ptr [rcx+r8+10238h]
0x1800041c2  mov     cl, [rcx+r8+10248h]
0x1800041ca  sub     rdx, rax
0x1800041cd  mov     eax, [rdx-4]
0x1800041d0  shr     eax, cl
0x1800041d2  mov     [r9+8], rdx
0x1800041d6  mov     [r9], eax
0x1800041d9  mov     [r9+10h], rdx
0x1800041dd  movzx   ecx, byte ptr [rdx]
0x1800041e0  and     ecx, 0Fh
0x1800041e3  movsx   rax, byte ptr [rcx+r8+10238h]
0x1800041ec  mov     cl, [rcx+r8+10248h]
0x1800041f4  sub     rdx, rax
0x1800041f7  mov     eax, [rdx-4]
0x1800041fa  shr     eax, cl
0x1800041fc  mov     [r9+8], rdx
0x180004200  mov     [r9+18h], eax
0x180004204  movzx   ecx, byte ptr [rdx]
0x180004207  and     ecx, 0Fh
0x18000420a  movsx   rax, byte ptr [rcx+r8+10238h]
0x180004213  mov     cl, [rcx+r8+10248h]
0x18000421b  sub     rdx, rax
0x18000421e  mov     eax, [rdx-4]
0x180004221  shr     eax, cl
0x180004223  mov     [r9+8], rdx
0x180004227  mov     [r9+1Ch], eax
0x18000422b  movzx   ecx, byte ptr [rdx]
0x18000422e  and     ecx, 0Fh
0x180004231  movsx   rax, byte ptr [rcx+r8+10238h]
0x18000423a  mov     cl, [rcx+r8+10248h]
0x180004242  sub     rdx, rax
0x180004245  mov     eax, [rdx-4]
0x180004248  shr     eax, cl
0x18000424a  mov     [r9+20h], eax
0x18000424e  lea     rax, [rdx+4]
0x180004252  mov     [r9+8], rdx
0x180004256  mov     ecx, [rdx]
0x180004258  mov     [r9+8], rax
0x18000425c  mov     [r9+24h], ecx
0x180004260  jmp     short loc_180004264
0x180004262  mov     [rcx], eax
0x180004264  mov     rax, r9
0x180004267  retn
```
