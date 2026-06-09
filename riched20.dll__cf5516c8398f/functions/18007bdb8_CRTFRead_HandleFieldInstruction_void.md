# CRTFRead::HandleFieldInstruction(void)

- ea: `0x18007bdb8`
- end: `0x18007bf31`
- name: `?HandleFieldInstruction@CRTFRead@@AEAAHXZ`
- size: `377`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800026c0`

## callees

- `0x180022780`
- `0x18007633c`
- `0x18007bdb8`
- `0x18007c0c0`
- `0x18008bf2c`

## string_xrefs

- `0x18007be4f`: `HYPERLINK`

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
          *((_DWORD *)this + 12) = AppendString(
                                     (unsigned __int8 **)this + 75,
                                     v6,
                                     (unsigned int *)this + 152,
                                     (int *)this + 153);
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
0x18007bdb8  push    rbx
0x18007bdba  push    rsi
0x18007bdbb  push    rdi
0x18007bdbc  push    r12
0x18007bdbe  push    r14
0x18007bdc0  sub     rsp, 20h
0x18007bdc4  mov     rax, [rcx+88h]
0x18007bdcb  mov     rbx, rcx
0x18007bdce  mov     byte ptr [rax+201h], 0
0x18007bdd5  mov     rsi, [rcx+88h]
0x18007bddc  mov     rcx, rsi
0x18007bddf  mov     al, [rsi]
0x18007bde1  jmp     short loc_18007BDEC
0x18007bde3  cmp     al, 20h ; ' '
0x18007bde5  jnz     short loc_18007BDF0
0x18007bde7  inc     rcx; unsigned __int8 *
0x18007bdea  mov     al, [rcx]
0x18007bdec  test    al, al
0x18007bdee  jnz     short loc_18007BDE3
0x18007bdf0  mov     al, [rcx]
0x18007bdf2  mov     rdi, rcx
0x18007bdf5  jmp     short loc_18007BE00
0x18007bdf7  cmp     al, 20h ; ' '
0x18007bdf9  jz      short loc_18007BE04
0x18007bdfb  inc     rdi
0x18007bdfe  mov     al, [rdi]
0x18007be00  test    al, al
0x18007be02  jnz     short loc_18007BDF7
0x18007be04  mov     eax, 0FFBFh
0x18007be09  lea     rdx, aSymbol_0; "SYMBOL"
0x18007be10  and     [rbx+1D8h], ax
0x18007be17  sub     rsi, rcx
0x18007be1a  mov     eax, 6
0x18007be1f  add     rsi, 202h
0x18007be26  cmp     rsi, rax
0x18007be29  mov     r8, rsi
0x18007be2c  cmovg   r8, rax; int
0x18007be30  call    ?ASCIICompareI@CW32System@@SAHPEBE0H@Z; CW32System::ASCIICompareI(uchar const *,uchar const *,int)
0x18007be35  test    eax, eax
0x18007be37  jz      short loc_18007BE49
0x18007be39  mov     rdx, rdi; unsigned __int8 *
0x18007be3c  mov     rcx, rbx; this
0x18007be3f  call    ?HandleFieldSymbolInstruction@CRTFRead@@AEAAHPEAE@Z; CRTFRead::HandleFieldSymbolInstruction(uchar *)
0x18007be44  jmp     loc_18007BECE
0x18007be49  mov     r12d, 9
0x18007be4f  lea     rdx, aHyperlink; "HYPERLINK"
0x18007be56  cmp     rsi, r12
0x18007be59  cmovg   rsi, r12
0x18007be5d  mov     r8d, esi; int
0x18007be60  call    ?ASCIICompareI@CW32System@@SAHPEBE0H@Z; CW32System::ASCIICompareI(uchar const *,uchar const *,int)
0x18007be65  test    eax, eax
0x18007be67  jz      short loc_18007BECE
0x18007be69  or      word ptr [rbx+1D8h], 40h
0x18007be71  jmp     short loc_18007BE76
0x18007be73  inc     rdi
0x18007be76  cmp     byte ptr [rdi], 20h ; ' '
0x18007be79  jz      short loc_18007BE73
0x18007be7b  mov     ecx, 104h; unsigned int
0x18007be80  lea     rsi, [rbx+260h]
0x18007be87  lea     r14, [rbx+264h]
0x18007be8e  mov     [rsi], ecx
0x18007be90  xor     edx, edx; unsigned int
0x18007be92  mov     dword ptr [r14], 1
0x18007be99  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x18007be9e  test    rax, rax
0x18007bea1  jnz     short loc_18007BEA9
0x18007bea3  mov     [rbx+30h], r12d
0x18007bea7  jmp     short loc_18007BECE
0x18007bea9  mov     word ptr [rax], 20h ; ' '
0x18007beae  lea     rcx, [rbx+258h]; unsigned __int8 **
0x18007beb5  mov     [rcx], rax
0x18007beb8  cmp     byte ptr [rdi], 0
0x18007bebb  jz      short loc_18007BECE
0x18007bebd  mov     r9, r14; int *
0x18007bec0  mov     r8, rsi; int *
0x18007bec3  mov     rdx, rdi; unsigned __int8 *
0x18007bec6  call    ?AppendString@@YAHPEAPEAEPEAEPEAH2@Z; AppendString(uchar * *,uchar *,int *,int *)
0x18007becb  mov     [rbx+30h], eax
0x18007bece  movups  xmm0, xmmword ptr [rbx+54h]
0x18007bed2  mov     rcx, [rbx+0D8h]
0x18007bed9  movups  xmm1, xmmword ptr [rbx+64h]
0x18007bedd  movups  xmmword ptr [rbx+1F0h], xmm0
0x18007bee4  movsd   xmm0, qword ptr [rbx+74h]
0x18007bee9  movups  xmmword ptr [rbx+200h], xmm1
0x18007bef0  movsd   qword ptr [rbx+210h], xmm0
0x18007bef8  mov     eax, [rcx+14h]
0x18007befb  mov     [rbx+224h], eax
0x18007bf01  mov     eax, [rcx+0Ch]
0x18007bf04  mov     [rbx+218h], eax
0x18007bf0a  mov     eax, [rbx+0ECh]
0x18007bf10  mov     [rbx+21Ch], eax
0x18007bf16  mov     eax, [rbx+0F0h]
0x18007bf1c  mov     [rbx+220h], eax
0x18007bf22  mov     eax, [rbx+30h]
0x18007bf25  add     rsp, 20h
0x18007bf29  pop     r14
0x18007bf2b  pop     r12
0x18007bf2d  pop     rdi
0x18007bf2e  pop     rsi
0x18007bf2f  pop     rbx
0x18007bf30  retn
```
