# SC_MBR::ReadPartitionTable(SC_DISK_LAYOUT * *)

- ea: `0x140006384`
- end: `0x14000669a`
- name: `?ReadPartitionTable@SC_MBR@@QEAAJPEAPEAVSC_DISK_LAYOUT@@@Z`
- size: `790`
- prototype: `__int64 __fastcall(SC_DISK **this, struct SC_DISK_LAYOUT **, unsigned __int8)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14000a33c`

## callees

- `0x1400053d4`
- `0x14000590c`
- `0x140005950`
- `0x140006384`
- `0x14000a530`
- `0x140011140`
- `0x140011440`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140006623`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006663`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006623`
- `ntoskrnl!ExFreePoolWithTag` at `0x140006663`

## pseudocode

```c
__int64 __fastcall SC_MBR::ReadPartitionTable(SC_DISK **this, struct SC_DISK_LAYOUT **a2, unsigned __int8 a3)
{
  SC_DISK *v3; // rax
  SC_DISK **v4; // r12
  __int64 v5; // rbp
  struct SC_DISK_LAYOUT *v6; // rax
  struct SC_DISK_LAYOUT *v7; // rbx
  unsigned int v8; // edi
  __int64 v9; // r14
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r13
  unsigned int i; // esi
  __int64 v14; // rbp
  char v15; // r15
  unsigned int v16; // r12d
  char v17; // r15
  __int64 v18; // rax
  __int16 v19; // ax
  __int64 v20; // r8
  unsigned int v21; // eax
  int v22; // ecx
  bool v23; // al
  unsigned int v24; // ecx
  unsigned int v25; // r15d
  struct SC_DISK_LAYOUT *v26; // rax
  struct SC_DISK_LAYOUT *v27; // rsi
  unsigned int v29; // [rsp+20h] [rbp-58h]
  int Sectors; // [rsp+24h] [rbp-54h]
  __int64 v31; // [rsp+28h] [rbp-50h]
  char v34; // [rsp+90h] [rbp+18h]
  unsigned int v35; // [rsp+98h] [rbp+20h]

  v3 = *this;
  v4 = this;
  *a2 = 0;
  v5 = *((_QWORD *)v3 + 33);
  v31 = v5;
  v6 = (struct SC_DISK_LAYOUT *)SC_ENV::Allocate(0x270u, (unsigned int)a2, a3, 0);
  v7 = v6;
  if ( v6 )
  {
    v35 = 0;
    v8 = 0;
    v34 = 0;
    Sectors = 0;
    v29 = 0;
    v9 = 0;
    memset(v6, 0, 0x270u);
    *((_DWORD *)v7 + 2) = *(_DWORD *)(v5 + 440);
    *((_DWORD *)v7 + 3) = MBR_HEADER::CheckSum((MBR_HEADER *)v5);
    while ( 1 )
    {
      if ( *(_WORD *)(v5 + 510) != 0xAA55 )
      {
LABEL_35:
        *((_DWORD *)v7 + 1) = (v9 + 3) & 0xFFFFFFFC;
        *a2 = v7;
        return v8;
      }
      v12 = 0;
      for ( i = 0; i < 4; ++i )
      {
        v14 = 16LL * i + v5 + 446;
        v15 = *(_BYTE *)(v14 + 4);
        if ( v15 == 5 || v15 == 15 )
        {
          if ( v12 )
          {
            v17 = 1;
            v34 = 1;
            goto LABEL_25;
          }
          v12 = v14;
          v16 = v35;
        }
        else
        {
          v16 = v29;
        }
        if ( !MBR_ENTRY::Validate((MBR_ENTRY *)v14, v16, *((_QWORD *)*this + 31)) )
        {
          v17 = 1;
          v34 = 1;
LABEL_24:
          v4 = this;
          goto LABEL_25;
        }
        v18 = (unsigned int)v9;
        v9 = (unsigned int)(v9 + 1);
        if ( !v15 )
        {
          v17 = v34;
          goto LABEL_24;
        }
        v10 = 18 * v18;
        *((_DWORD *)v7 + 36 * v18 + 12) = 0;
        if ( v16 )
          v19 = 0;
        else
          v19 = i + 1;
        *((_WORD *)v7 + 4 * v10 + 26) = v19;
        v20 = v16;
        v4 = this;
        v11 = (*(unsigned int *)(v14 + 8) + v20) << *((_DWORD *)*this + 60);
        *((_QWORD *)v7 + v10 + 7) = v11;
        *((_QWORD *)v7 + v10 + 8) = (unsigned __int64)*(unsigned int *)(v14 + 12) << *((_DWORD *)*this + 60);
        *((_DWORD *)v7 + 2 * v10 + 18) = 0;
        *((_BYTE *)v7 + 8 * v10 + 80) = *(_BYTE *)(v14 + 4);
        *((_BYTE *)v7 + 8 * v10 + 81) = *(_BYTE *)v14 == 0x80;
        v21 = *(unsigned __int8 *)(v14 + 4);
        v23 = 1;
        if ( (unsigned __int8)v21 <= 0xFu )
        {
          v22 = 32801;
          if ( _bittest(&v22, v21) )
            v23 = 0;
        }
        v17 = v34;
        *((_BYTE *)v7 + 8 * v10 + 82) = v23;
        *((_DWORD *)v7 + 2 * v10 + 21) = *(_DWORD *)(v14 + 8);
        *((_DWORD *)v7 + 2 * v10 + 22) = *((_DWORD *)v7 + 2);
        *((_DWORD *)v7 + 2 * v10 + 23) = 0;
        *((_QWORD *)v7 + v10 + 12) = v11;
LABEL_25:
        v5 = v31;
      }
      v8 = Sectors;
      if ( v17 || !v12 )
        goto LABEL_35;
      v24 = v35;
      v25 = *(_DWORD *)(v12 + 8) + v35;
      if ( !v35 )
        v24 = *(_DWORD *)(v12 + 8);
      v35 = v24;
      v29 = v25;
      v26 = (struct SC_DISK_LAYOUT *)SC_ENV::Allocate((unsigned int)(144 * v9 + 624), v10, v11, 0);
      v27 = v26;
      if ( !v26 )
      {
        v8 = -1073741670;
        if ( !v7 )
          return v8;
LABEL_34:
        ExFreePoolWithTag(v7, 0);
        return v8;
      }
      memmove(v26, v7, 144 * (int)v9 + 48);
      memset((char *)v27 + 144 * v9 + 48, 0, 0x240u);
      ExFreePoolWithTag(v7, 0);
      v7 = v27;
      Sectors = SC_DISK::ReadSectors(*v4, 1u, v25, 0);
      v8 = Sectors;
      if ( Sectors < 0 )
        goto LABEL_34;
    }
  }
  return (unsigned int)-1073741670;
}

```

## disassembly

```asm
0x140006384  mov     [rsp+arg_8], rdx
0x140006389  mov     [rsp+arg_0], rcx
0x14000638e  push    rbx
0x14000638f  push    rbp
0x140006390  push    rsi
0x140006391  push    rdi
0x140006392  push    r12
0x140006394  push    r13
0x140006396  push    r14
0x140006398  push    r15
0x14000639a  sub     rsp, 38h
0x14000639e  mov     rax, [rcx]
0x1400063a1  mov     r12, rcx
0x1400063a4  mov     esi, 270h
0x1400063a9  mov     qword ptr [rdx], 0
0x1400063b0  xor     r9d, r9d; unsigned int
0x1400063b3  mov     ecx, esi; unsigned __int64
0x1400063b5  mov     rbp, [rax+108h]
0x1400063bc  mov     [rsp+78h+var_50], rbp
0x1400063c1  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400063c6  mov     rbx, rax
0x1400063c9  test    rax, rax
0x1400063cc  jnz     short loc_1400063D8
0x1400063ce  mov     edi, 0C000009Ah
0x1400063d3  jmp     loc_140006686
0x1400063d8  xor     ecx, ecx
0x1400063da  xor     r15b, r15b
0x1400063dd  mov     [rsp+78h+arg_18], ecx
0x1400063e4  xor     edi, edi
0x1400063e6  mov     [rsp+78h+arg_10], r15b
0x1400063ee  mov     r8, rsi; Size
0x1400063f1  xor     r15d, r15d
0x1400063f4  mov     [rsp+78h+var_54], edi
0x1400063f8  xor     edx, edx; Val
0x1400063fa  mov     [rsp+78h+var_58], r15d
0x1400063ff  mov     rcx, rbx; void *
0x140006402  xor     r14d, r14d
0x140006405  call    memset
0x14000640a  mov     eax, [rbp+1B8h]
0x140006410  mov     rcx, rbp; this
0x140006413  mov     [rbx+8], eax
0x140006416  call    ?CheckSum@MBR_HEADER@@QEAAKXZ; MBR_HEADER::CheckSum(void)
0x14000641b  mov     [rbx+0Ch], eax
0x14000641e  mov     eax, 0AA55h
0x140006423  mov     r9d, 1
0x140006429  cmp     [rbp+1FEh], ax
0x140006430  jnz     loc_140006671
0x140006436  mov     edi, [rsp+78h+arg_18]
0x14000643d  xor     r13d, r13d
0x140006440  xor     esi, esi
0x140006442  add     rbp, 1BEh
0x140006449  mov     eax, esi
0x14000644b  shl     rax, 4
0x14000644f  add     rbp, rax
0x140006452  mov     r15b, [rbp+4]
0x140006456  cmp     r15b, 5
0x14000645a  jz      short loc_140006469
0x14000645c  cmp     r15b, 0Fh
0x140006460  jz      short loc_140006469
0x140006462  mov     r12d, [rsp+78h+var_58]
0x140006467  jmp     short loc_140006484
0x140006469  test    r13, r13
0x14000646c  jz      short loc_14000647E
0x14000646e  mov     r15b, r9b
0x140006471  mov     [rsp+78h+arg_10], r9b
0x140006479  jmp     loc_14000658D
0x14000647e  mov     r13, rbp
0x140006481  mov     r12d, edi
0x140006484  mov     r8, [rsp+78h+arg_0]
0x14000648c  mov     edx, r12d; unsigned int
0x14000648f  mov     rcx, rbp; this
0x140006492  mov     r8, [r8]
0x140006495  mov     r8, [r8+0F8h]; unsigned __int64
0x14000649c  call    ?Validate@MBR_ENTRY@@QEAAEK_K@Z; MBR_ENTRY::Validate(ulong,unsigned __int64)
0x1400064a1  mov     r9d, 1
0x1400064a7  test    al, al
0x1400064a9  jnz     short loc_1400064BB
0x1400064ab  mov     r15b, r9b
0x1400064ae  mov     [rsp+78h+arg_10], r9b
0x1400064b6  jmp     loc_140006585
0x1400064bb  mov     eax, r14d
0x1400064be  add     r14d, r9d
0x1400064c1  test    r15b, r15b
0x1400064c4  jz      loc_14000657D
0x1400064ca  lea     rdx, [rax+rax*8]
0x1400064ce  add     rdx, rdx
0x1400064d1  mov     dword ptr [rbx+rdx*8+30h], 0
0x1400064d9  test    r12d, r12d
0x1400064dc  jnz     short loc_1400064E4
0x1400064de  lea     eax, [r9+rsi]
0x1400064e2  jmp     short loc_1400064E6
0x1400064e4  xor     eax, eax
0x1400064e6  mov     [rbx+rdx*8+34h], ax
0x1400064eb  mov     eax, [rbp+8]
0x1400064ee  mov     r8d, r12d
0x1400064f1  mov     r12, [rsp+78h+arg_0]
0x1400064f9  add     r8, rax
0x1400064fc  mov     rcx, [r12]
0x140006500  mov     ecx, [rcx+0F0h]
0x140006506  shl     r8, cl
0x140006509  mov     [rbx+rdx*8+38h], r8
0x14000650e  mov     rcx, [r12]
0x140006512  mov     eax, [rbp+0Ch]
0x140006515  mov     ecx, [rcx+0F0h]
0x14000651b  shl     rax, cl
0x14000651e  mov     [rbx+rdx*8+40h], rax
0x140006523  mov     dword ptr [rbx+rdx*8+48h], 0
0x14000652b  mov     al, [rbp+4]
0x14000652e  mov     [rbx+rdx*8+50h], al
0x140006532  cmp     byte ptr [rbp+0], 80h
0x140006536  setz    al
0x140006539  mov     [rbx+rdx*8+51h], al
0x14000653d  movzx   eax, byte ptr [rbp+4]
0x140006541  cmp     al, 0Fh
0x140006543  ja      short loc_140006553
0x140006545  mov     ecx, 8021h
0x14000654a  bt      ecx, eax
0x14000654d  jnb     short loc_140006553
0x14000654f  xor     al, al
0x140006551  jmp     short loc_140006556
0x140006553  mov     al, r9b
0x140006556  mov     r15b, [rsp+78h+arg_10]
0x14000655e  mov     [rbx+rdx*8+52h], al
0x140006562  mov     eax, [rbp+8]
0x140006565  mov     [rbx+rdx*8+54h], eax
0x140006569  mov     eax, [rbx+8]
0x14000656c  mov     [rbx+rdx*8+58h], eax
0x140006570  xor     eax, eax
0x140006572  mov     [rbx+rdx*8+5Ch], eax
0x140006576  mov     [rbx+rdx*8+60h], r8
0x14000657b  jmp     short loc_14000658D
0x14000657d  mov     r15b, [rsp+78h+arg_10]
0x140006585  mov     r12, [rsp+78h+arg_0]
0x14000658d  mov     rbp, [rsp+78h+var_50]
0x140006592  add     esi, r9d
0x140006595  cmp     esi, 4
0x140006598  jb      loc_140006442
0x14000659e  mov     edi, [rsp+78h+var_54]
0x1400065a2  test    r15b, r15b
0x1400065a5  jnz     loc_140006671
0x1400065ab  test    r13, r13
0x1400065ae  jz      loc_140006671
0x1400065b4  mov     ecx, [rsp+78h+arg_18]
0x1400065bb  lea     edi, [r14+r14*8]
0x1400065bf  mov     eax, [r13+8]
0x1400065c3  test    ecx, ecx
0x1400065c5  lea     r15d, [rax+rcx]
0x1400065c9  cmovz   ecx, eax
0x1400065cc  mov     [rsp+78h+arg_18], ecx
0x1400065d3  xor     r9d, r9d; unsigned int
0x1400065d6  shl     edi, 4
0x1400065d9  mov     [rsp+78h+var_58], r15d
0x1400065de  lea     ecx, [rdi+270h]; unsigned __int64
0x1400065e4  call    ?Allocate@SC_ENV@@SAPEAX_KKEK@Z; SC_ENV::Allocate(unsigned __int64,ulong,uchar,ulong)
0x1400065e9  mov     rsi, rax
0x1400065ec  test    rax, rax
0x1400065ef  jz      short loc_140006654
0x1400065f1  lea     ecx, [rdi+30h]
0x1400065f4  mov     rdx, rbx; Src
0x1400065f7  movsxd  r8, ecx; Size
0x1400065fa  mov     rcx, rax; void *
0x1400065fd  call    memmove
0x140006602  lea     rcx, [r14+r14*8]
0x140006606  xor     edx, edx; Val
0x140006608  shl     rcx, 4
0x14000660c  mov     r8d, 240h; Size
0x140006612  add     rcx, 30h ; '0'
0x140006616  add     rcx, rsi; void *
0x140006619  call    memset
0x14000661e  xor     edx, edx; Tag
0x140006620  mov     rcx, rbx; P
0x140006623  call    cs:__imp_ExFreePoolWithTag
0x14000662a  nop     dword ptr [rax+rax+00h]
0x14000662f  mov     rcx, [r12]; this
0x140006633  xor     r9d, r9d; void *
0x140006636  mov     r8d, r15d; unsigned __int64
0x140006639  mov     rbx, rsi
0x14000663c  lea     edx, [r9+1]; unsigned int
0x140006640  call    ?ReadSectors@SC_DISK@@QEAAJK_KPEAX@Z; SC_DISK::ReadSectors(ulong,unsigned __int64,void *)
0x140006645  mov     [rsp+78h+var_54], eax
0x140006649  mov     edi, eax
0x14000664b  test    eax, eax
0x14000664d  js      short loc_14000665E
0x14000664f  jmp     loc_14000641E
0x140006654  mov     edi, 0C000009Ah
0x140006659  test    rbx, rbx
0x14000665c  jz      short loc_140006686
0x14000665e  xor     edx, edx; Tag
0x140006660  mov     rcx, rbx; P
0x140006663  call    cs:__imp_ExFreePoolWithTag
0x14000666a  nop     dword ptr [rax+rax+00h]
0x14000666f  jmp     short loc_140006686
0x140006671  lea     eax, [r14+3]
0x140006675  and     eax, 0FFFFFFFCh
0x140006678  mov     [rbx+4], eax
0x14000667b  mov     rax, [rsp+78h+arg_8]
0x140006683  mov     [rax], rbx
0x140006686  mov     eax, edi
0x140006688  add     rsp, 38h
0x14000668c  pop     r15
0x14000668e  pop     r14
0x140006690  pop     r13
0x140006692  pop     r12
0x140006694  pop     rdi
0x140006695  pop     rsi
0x140006696  pop     rbp
0x140006697  pop     rbx
0x140006698  retn
```
