# CRTFRead::HandleFieldInstruction(void)

- ea: `0x18007e120`
- end: `0x18007e29a`
- name: `?HandleFieldInstruction@CRTFRead@@AEAAHXZ`
- size: `378`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180002740`

## callees

- `0x1800274a0`
- `0x1800783e0`
- `0x18007e120`
- `0x18007e42c`
- `0x18008e5e0`

## string_xrefs

- `0x18007e1b7`: `HYPERLINK`

## pseudocode

```c
__int64 __fastcall CRTFRead::HandleFieldInstruction(CRTFRead *this)
{
  const unsigned __int8 *v2; // rsi
  const unsigned __int8 *v3; // rcx
  unsigned __int8 i; // al
  unsigned __int8 v5; // al
  unsigned __int8 *v6; // rdi
  __int64 v7; // rsi
  int v8; // r8d
  const unsigned __int8 *v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rcx
  __int128 v12; // xmm1
  __int64 v13; // xmm0_8

  *(_BYTE *)(*((_QWORD *)this + 17) + 513LL) = 0;
  v2 = (const unsigned __int8 *)*((_QWORD *)this + 17);
  v3 = v2;
  for ( i = *v2; i == 32; i = *v3 )
    ++v3;
  v5 = *v3;
  v6 = (unsigned __int8 *)v3;
  while ( v5 && v5 != 32 )
    v5 = *++v6;
  *((_WORD *)this + 236) &= ~0x40u;
  v7 = v2 - v3 + 514;
  v8 = v7;
  if ( v7 > 6 )
    v8 = 6;
  if ( (unsigned int)CW32System::ASCIICompareI(v3, "SYMBOL", v8) )
  {
    CRTFRead::HandleFieldSymbolInstruction(this, v6);
  }
  else
  {
    if ( v7 > 9 )
      LODWORD(v7) = 9;
    if ( (unsigned int)CW32System::ASCIICompareI(v9, "HYPERLINK", v7) )
    {
      *((_WORD *)this + 236) |= 0x40u;
      while ( *v6 == 32 )
        ++v6;
      *((_DWORD *)this + 152) = 260;
      *((_DWORD *)this + 153) = 1;
      v10 = CW32System::PvAlloc(0x104u, 0);
      if ( v10 )
      {
        *v10 = 32;
        *((_QWORD *)this + 75) = v10;
        if ( *v6 )
          *((_DWORD *)this + 12) = AppendString((unsigned __int8 **)this + 75, v6, (int *)this + 152, (int *)this + 153);
      }
      else
      {
        *((_DWORD *)this + 12) = 9;
      }
    }
  }
  v11 = *((_QWORD *)this + 27);
  v12 = *(_OWORD *)((char *)this + 100);
  *((_OWORD *)this + 31) = *(_OWORD *)((char *)this + 84);
  v13 = *(_QWORD *)((char *)this + 116);
  *((_OWORD *)this + 32) = v12;
  *((_QWORD *)this + 66) = v13;
  *((_DWORD *)this + 137) = *(_DWORD *)(v11 + 20);
  *((_DWORD *)this + 134) = *(_DWORD *)(v11 + 12);
  *((_DWORD *)this + 135) = *((_DWORD *)this + 59);
  *((_DWORD *)this + 136) = *((_DWORD *)this + 60);
  return *((unsigned int *)this + 12);
}

```

## disassembly

```asm
0x18007e120  push    rbx
0x18007e122  push    rsi
0x18007e123  push    rdi
0x18007e124  push    r12
0x18007e126  push    r14
0x18007e128  sub     rsp, 20h
0x18007e12c  mov     rax, [rcx+88h]
0x18007e133  mov     rbx, rcx
0x18007e136  mov     byte ptr [rax+201h], 0
0x18007e13d  mov     rsi, [rcx+88h]
0x18007e144  mov     rcx, rsi
0x18007e147  mov     al, [rsi]
0x18007e149  jmp     short loc_18007E154
0x18007e14b  cmp     al, 20h ; ' '
0x18007e14d  jnz     short loc_18007E158
0x18007e14f  inc     rcx; unsigned __int8 *
0x18007e152  mov     al, [rcx]
0x18007e154  test    al, al
0x18007e156  jnz     short loc_18007E14B
0x18007e158  mov     al, [rcx]
0x18007e15a  mov     rdi, rcx
0x18007e15d  jmp     short loc_18007E168
0x18007e15f  cmp     al, 20h ; ' '
0x18007e161  jz      short loc_18007E16C
0x18007e163  inc     rdi
0x18007e166  mov     al, [rdi]
0x18007e168  test    al, al
0x18007e16a  jnz     short loc_18007E15F
0x18007e16c  mov     eax, 0FFBFh
0x18007e171  lea     rdx, aSymbol_0; "SYMBOL"
0x18007e178  and     [rbx+1D8h], ax
0x18007e17f  sub     rsi, rcx
0x18007e182  mov     eax, 6
0x18007e187  add     rsi, 202h
0x18007e18e  cmp     rsi, rax
0x18007e191  mov     r8, rsi
0x18007e194  cmovg   r8, rax; int
0x18007e198  call    ?ASCIICompareI@CW32System@@SAHPEBE0H@Z; CW32System::ASCIICompareI(uchar const *,uchar const *,int)
0x18007e19d  test    eax, eax
0x18007e19f  jz      short loc_18007E1B1
0x18007e1a1  mov     rdx, rdi; unsigned __int8 *
0x18007e1a4  mov     rcx, rbx; this
0x18007e1a7  call    ?HandleFieldSymbolInstruction@CRTFRead@@AEAAHPEAE@Z; CRTFRead::HandleFieldSymbolInstruction(uchar *)
0x18007e1ac  jmp     loc_18007E236
0x18007e1b1  mov     r12d, 9
0x18007e1b7  lea     rdx, aHyperlink; "HYPERLINK"
0x18007e1be  cmp     rsi, r12
0x18007e1c1  cmovg   rsi, r12
0x18007e1c5  mov     r8d, esi; int
0x18007e1c8  call    ?ASCIICompareI@CW32System@@SAHPEBE0H@Z; CW32System::ASCIICompareI(uchar const *,uchar const *,int)
0x18007e1cd  test    eax, eax
0x18007e1cf  jz      short loc_18007E236
0x18007e1d1  or      word ptr [rbx+1D8h], 40h
0x18007e1d9  jmp     short loc_18007E1DE
0x18007e1db  inc     rdi
0x18007e1de  cmp     byte ptr [rdi], 20h ; ' '
0x18007e1e1  jz      short loc_18007E1DB
0x18007e1e3  mov     ecx, 104h; unsigned int
0x18007e1e8  lea     rsi, [rbx+260h]
0x18007e1ef  lea     r14, [rbx+264h]
0x18007e1f6  mov     [rsi], ecx
0x18007e1f8  xor     edx, edx; unsigned int
0x18007e1fa  mov     dword ptr [r14], 1
0x18007e201  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007e206  test    rax, rax
0x18007e209  jnz     short loc_18007E211
0x18007e20b  mov     [rbx+30h], r12d
0x18007e20f  jmp     short loc_18007E236
0x18007e211  mov     word ptr [rax], 20h ; ' '
0x18007e216  lea     rcx, [rbx+258h]; unsigned __int8 **
0x18007e21d  mov     [rcx], rax
0x18007e220  cmp     byte ptr [rdi], 0
0x18007e223  jz      short loc_18007E236
0x18007e225  mov     r9, r14; int *
0x18007e228  mov     r8, rsi; int *
0x18007e22b  mov     rdx, rdi; unsigned __int8 *
0x18007e22e  call    ?AppendString@@YAHPEAPEAEPEAEPEAH2@Z; AppendString(uchar * *,uchar *,int *,int *)
0x18007e233  mov     [rbx+30h], eax
0x18007e236  movups  xmm0, xmmword ptr [rbx+54h]
0x18007e23a  mov     rcx, [rbx+0D8h]
0x18007e241  movups  xmm1, xmmword ptr [rbx+64h]
0x18007e245  movups  xmmword ptr [rbx+1F0h], xmm0
0x18007e24c  movsd   xmm0, qword ptr [rbx+74h]
0x18007e251  movups  xmmword ptr [rbx+200h], xmm1
0x18007e258  movsd   qword ptr [rbx+210h], xmm0
0x18007e260  mov     eax, [rcx+14h]
0x18007e263  mov     [rbx+224h], eax
0x18007e269  mov     eax, [rcx+0Ch]
0x18007e26c  mov     [rbx+218h], eax
0x18007e272  mov     eax, [rbx+0ECh]
0x18007e278  mov     [rbx+21Ch], eax
0x18007e27e  mov     eax, [rbx+0F0h]
0x18007e284  mov     [rbx+220h], eax
0x18007e28a  mov     eax, [rbx+30h]
0x18007e28d  add     rsp, 20h
0x18007e291  pop     r14
0x18007e293  pop     r12
0x18007e295  pop     rdi
0x18007e296  pop     rsi
0x18007e297  pop     rbx
0x18007e298  retn
```
