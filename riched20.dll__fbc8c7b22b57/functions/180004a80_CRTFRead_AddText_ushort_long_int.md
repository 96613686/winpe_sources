# CRTFRead::AddText(ushort *,long,int)

- ea: `0x180004a80`
- end: `0x180005067`
- name: `?AddText@CRTFRead@@AEAAHPEAGJH@Z`
- size: `1511`
- prototype: `__int64 __fastcall(CRTFRead *__hidden this, unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x180002740`
- `0x180004a80`
- `0x18003a3a0`
- `0x180048594`

## callees

- `0x180004a80`
- `0x180005070`
- `0x180005510`
- `0x180008fec`
- `0x180015448`
- `0x18001b100`
- `0x180022ad4`
- `0x1800274a0`
- `0x180049fd8`
- `0x18008d038`
- `0x18008dac4`
- `0x180093bbe`
- `0x180095010`

## pseudocode

```c
__int64 __fastcall CRTFRead::AddText(CRTFRead *this, unsigned __int16 *a2, int a3, int a4)
{
  int v4; // r14d
  unsigned __int16 *v5; // rbp
  __int64 v7; // rsi
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ecx
  char *v11; // r13
  __int64 v12; // rdi
  unsigned int v13; // r15d
  int v14; // eax
  int v15; // ecx
  __int64 v16; // rdx
  _QWORD *v17; // rdi
  int v18; // esi
  struct IUndoBuilder *v19; // rdx
  int v20; // r8d
  int v21; // r12d
  int i; // edi
  unsigned int v23; // ecx
  __int64 v24; // rbp
  int v25; // eax
  int v26; // edi
  __int64 v27; // rsi
  struct IFormatCache *v29; // rdi
  int v30; // ecx
  unsigned int v31; // edi
  unsigned __int8 v32; // al
  char v33; // cl
  __int64 v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rcx
  int v37; // eax
  bool v38; // zf
  unsigned int v39; // edi
  struct CUniscribe *Uniscribe; // rax
  CTxtBreaker *v41; // rcx
  CTxtBreaker *v42; // rax
  CTxtBreaker **v43; // rdx
  __int16 v44; // dx
  __int16 v45; // ax
  char *v46; // rsi
  __int64 v47; // rcx
  int v48; // [rsp+80h] [rbp+8h] BYREF

  v4 = a3;
  v48 = 0;
  v5 = a2;
  if ( a3 <= 0 )
    return *((unsigned int *)this + 12);
  v7 = *((_QWORD *)this + 27);
  if ( (unsigned int)a3 > *((_DWORD *)this + 171) )
  {
    v4 = *((_DWORD *)this + 171);
    *((_DWORD *)this + 12) = 18;
  }
  v8 = *((int *)this + 148);
  if ( *(_WORD *)(v7 + 10) == 13 )
  {
    if ( v4 >= 15 - (int)v8 )
      v4 = 15 - v8;
    if ( v4 > 0 )
    {
      v46 = (char *)this + 2 * v8;
      memmove_0(v46 + 556, a2, 2LL * v4);
      *(_WORD *)&v46[2 * v4 + 556] = 0;
      *((_DWORD *)this + 148) += v4;
    }
    return 0;
  }
  else
  {
    if ( (_DWORD)v8 && a4 )
    {
      *((_DWORD *)this + 148) = 0;
      if ( (*(_BYTE *)(v7 + 4) & 2) != 0 )
      {
        if ( (unsigned int)*((unsigned __int16 *)this + 122) - 2 <= 5 && *((_WORD *)this + v8 + 277) == 9 )
        {
          if ( (int)v8 <= 1 )
          {
            *((_WORD *)this + 356) = 1024;
          }
          else
          {
            v44 = *((_WORD *)this + v8 + 276);
            if ( v44 == 46 )
            {
              v45 = 512;
            }
            else if ( v44 == 41 )
            {
              v45 = 0;
              if ( *((_WORD *)this + 278) == 40 )
                v45 = 256;
            }
            else
            {
              v45 = 768;
            }
            *((_WORD *)this + 356) = v45 | *((_WORD *)this + 356) & 0xFCFF;
          }
        }
      }
      else
      {
        CRTFRead::AddText(this, (unsigned __int16 *)this + 278, v8, 0);
      }
    }
    v9 = *((_DWORD *)this + 172);
    if ( v9
      && (v47 = *((_QWORD *)this + 8), *(_DWORD *)(v47 + 40) == v9)
      && (*((_WORD *)CRchTxtPtr::GetPF((CRchTxtPtr *)(v47 + 8)) + 1) & 0x4000) != 0
      && *((_DWORD *)this + 78)
      && !(unsigned int)CTxtPtr::IsAfterEOP((CTxtPtr *)(*((_QWORD *)this + 8) + 24LL)) )
    {
      *((_DWORD *)this + 79) = 0;
      *((_DWORD *)this + 12) = 6;
    }
    else
    {
      v10 = *((_DWORD *)this + 59);
      if ( v10 || *((_DWORD *)this + 60) )
      {
        v11 = (char *)this + 64;
        CTxtRange::SetCharFormat(
          *((CTxtRange **)this + 8),
          (CRTFRead *)((char *)this + 84),
          0,
          0,
          v10,
          *((_DWORD *)this + 60));
        *(_QWORD *)((char *)this + 236) = 0;
      }
      else
      {
        v11 = (char *)this + 64;
      }
      v12 = *(_QWORD *)v11;
      (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A72D0)(
        qword_1800A72D0,
        (unsigned int)*(__int16 *)(*(_QWORD *)v11 + 96LL));
      v13 = *(__int16 *)(v12 + 96);
      if ( v7 && (v14 = *(_DWORD *)(v7 + 20), v14 >= 0) )
      {
        v15 = *((_DWORD *)this + 2);
        if ( v15 > 0 && v14 < v15 && *(_QWORD *)this )
          v16 = *(_QWORD *)this + *((_DWORD *)this + 4) * v14;
        else
          v16 = 0;
        v17 = (_QWORD *)((char *)this + 64);
      }
      else
      {
        v16 = 0;
        v17 = v11;
      }
      if ( *((_WORD *)this + 357)
        && v16
        && *(_WORD *)(v16 + 72) == 0xFFFF
        && (*((char *)this + 472) >= 0 || (GetCharFlags(*v5, 0) & 0x800000) == 0) )
      {
        v21 = CTxtRange::CleanseAndReplaceRange(*((CTxtRange **)this + 8), v4, v5, 0, 0, v5, 0, 0);
      }
      else
      {
        v18 = 0;
        v21 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, _QWORD, _DWORD, int *, _DWORD))(*(_QWORD *)*v17 + 560LL))(
                *v17,
                (unsigned int)v4,
                v5,
                0,
                0,
                &v48,
                0);
        for ( i = v4; i > 0; v18 |= GetCharFlags(v23, 0) )
        {
          v23 = *v5++;
          --i;
        }
        v24 = *((_QWORD *)this + 7);
        v25 = *(_DWORD *)(v24 + 192);
        v26 = v18 & (v18 ^ v25);
        if ( v26 )
        {
          v30 = v25 | v26;
          *(_DWORD *)(v24 + 192) = v25 | v26;
          v31 = v26 & 0x61086013;
          if ( v31 && (v30 & 0x61086013) == v31 )
          {
            if ( *(_WORD *)(v24 + 196) == 0xFFFF )
            {
              v32 = *(_BYTE *)(v24 + 198);
              v33 = v32 | 1;
              if ( v32 != (v32 | 1) )
              {
                v34 = *(_QWORD *)(v24 + 64);
                *(_BYTE *)(v24 + 198) = v33;
                *(_DWORD *)(v34 + 56) |= 0x80u;
                (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**(_QWORD **)(v24 + 48) + 72LL))(
                  *(_QWORD *)(v24 + 48),
                  0,
                  0);
              }
            }
            CTxtEdit::ItemizeDoc((CTxtEdit *)v24, v19, v20);
            v35 = *(_QWORD *)(v24 + 80);
            if ( v35 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 64LL))(v35);
            v36 = *(_QWORD *)(v24 + 88);
            if ( v36 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 64LL))(v36);
            *(_DWORD *)(v24 + 180) ^= (*(_DWORD *)(v24 + 180) ^ (*(_DWORD *)(v24 + 192) << 22)) & 0x400000;
          }
          v37 = HIBYTE(v31) & 1;
          v38 = (v31 & 0x61000000) == 0;
          v39 = v37 + 2;
          if ( v38 )
            v39 = v37;
          if ( v39 )
          {
            Uniscribe = GetUniscribe();
            v41 = *(CTxtBreaker **)(v24 + 168);
            if ( v41 )
              goto LABEL_90;
            if ( Uniscribe )
            {
              v42 = (CTxtBreaker *)CW32System::PvAlloc(0x28u, 0x40u);
              v41 = v42;
              if ( v42 )
              {
                v43 = (CTxtBreaker **)(v24 + 128);
                *((_QWORD *)v42 + 3) = 0;
                *((_QWORD *)v42 + 4) = 0;
                *(_QWORD *)v42 = &CTxtBreaker::`vftable';
                if ( v24 != -128 )
                {
                  *((_QWORD *)v42 + 1) = *v43;
                  *v43 = v42;
                }
                *((_QWORD *)v42 + 2) = v24;
              }
              else
              {
                v41 = 0;
              }
              *(_QWORD *)(v24 + 168) = v41;
              if ( v41 )
              {
LABEL_90:
                if ( (unsigned int)CTxtBreaker::AddBreaker(v41, v39) )
                  CTxtBreaker::Refresh(*(CTxtBreaker **)(v24 + 168));
              }
            }
          }
        }
      }
      v27 = *(_QWORD *)v11;
      if ( v13 != *(__int16 *)(*(_QWORD *)v11 + 96LL) )
      {
        v29 = qword_1800A72D0;
        (**(void (__fastcall ***)(struct IFormatCache *, _QWORD))qword_1800A72D0)(qword_1800A72D0, v13);
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)v29 + 8LL))(
          v29,
          (unsigned int)*(__int16 *)(v27 + 96));
        *(_WORD *)(v27 + 96) = v13;
      }
      if ( v13 != -1 )
        (*(void (__fastcall **)(struct IFormatCache *, _QWORD))(*(_QWORD *)qword_1800A72D0 + 8LL))(qword_1800A72D0, v13);
      if ( v21 == v4 || (*((_DWORD *)this + 12) = 6, v21 > 0) )
      {
        *((_DWORD *)this + 171) -= v21;
        return *((unsigned int *)this + 12);
      }
    }
    return 6;
  }
}

```

## disassembly

```asm
0x180004a80  mov     rax, rsp
0x180004a83  push    rbx
0x180004a84  push    rbp
0x180004a85  push    r12
0x180004a87  push    r14
0x180004a89  sub     rsp, 58h
0x180004a8d  xor     r12d, r12d
0x180004a90  mov     r14d, r8d
0x180004a93  mov     [rax+8], r12d
0x180004a97  mov     rbp, rdx
0x180004a9a  mov     rbx, rcx
0x180004a9d  test    r8d, r8d
0x180004aa0  jle     loc_180004C7C
0x180004aa6  mov     [rax+10h], rsi
0x180004aaa  mov     eax, [rcx+2ACh]
0x180004ab0  mov     rsi, [rcx+0D8h]
0x180004ab7  cmp     r8d, eax
0x180004aba  ja      loc_180004F11
0x180004ac0  cmp     word ptr [rsi+0Ah], 0Dh
0x180004ac5  movsxd  rcx, dword ptr [rcx+250h]
0x180004acc  mov     [rsp+78h+var_28], rdi
0x180004ad1  jz      loc_180004CC0
0x180004ad7  test    ecx, ecx
0x180004ad9  jnz     loc_180004F4F
0x180004adf  mov     eax, [rbx+2B0h]
0x180004ae5  test    eax, eax
0x180004ae7  jnz     loc_180004FC9
0x180004aed  mov     ecx, [rbx+0ECh]
0x180004af3  mov     [rsp+78h+var_30], r13
0x180004af8  mov     [rsp+78h+var_38], r15
0x180004afd  test    ecx, ecx
0x180004aff  jnz     short loc_180004B0E
0x180004b01  cmp     [rbx+0F0h], r12d
0x180004b08  jz      loc_180004FDB
0x180004b0e  mov     eax, [rbx+0F0h]
0x180004b14  lea     r13, [rbx+40h]
0x180004b18  mov     dword ptr [rsp+78h+var_50], eax; unsigned int
0x180004b1c  lea     rdx, [rbx+54h]; struct CCharFormat *
0x180004b20  mov     dword ptr [rsp+78h+var_58], ecx; unsigned int
0x180004b24  xor     r9d, r9d; struct IUndoBuilder *
0x180004b27  mov     rcx, [r13+0]; this
0x180004b2b  xor     r8d, r8d; unsigned int
0x180004b2e  call    ?SetCharFormat@CTxtRange@@QEAAJPEBVCCharFormat@@KPEAVIUndoBuilder@@KK@Z; CTxtRange::SetCharFormat(CCharFormat const *,ulong,IUndoBuilder *,ulong,ulong)
0x180004b33  mov     [rbx+0ECh], r12
0x180004b3a  mov     rcx, cs:qword_1800A72D0
0x180004b41  mov     rdi, [r13+0]
0x180004b45  mov     rax, [rcx]
0x180004b48  movsx   edx, word ptr [rdi+60h]
0x180004b4c  mov     rax, [rax]
0x180004b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b54  movsx   r15d, word ptr [rdi+60h]
0x180004b59  test    rsi, rsi
0x180004b5c  jz      loc_180004E5E
0x180004b62  mov     eax, [rsi+14h]
0x180004b65  test    eax, eax
0x180004b67  js      loc_180004E5E
0x180004b6d  mov     ecx, [rbx+8]
0x180004b70  test    ecx, ecx
0x180004b72  jle     loc_180004E69
0x180004b78  cmp     eax, ecx
0x180004b7a  jge     loc_180004E69
0x180004b80  mov     rcx, [rbx]
0x180004b83  test    rcx, rcx
0x180004b86  jz      loc_180004E69
0x180004b8c  imul    eax, [rbx+10h]
0x180004b90  movsxd  rdx, eax
0x180004b93  add     rdx, rcx
0x180004b96  lea     rdi, [rbx+40h]
0x180004b9a  cmp     [rbx+2CAh], r12w
0x180004ba2  jnz     loc_180004E0F
0x180004ba8  mov     rcx, [rdi]
0x180004bab  lea     rdx, [rsp+78h+arg_0]
0x180004bb3  mov     dword ptr [rsp+78h+var_48], r12d
0x180004bb8  xor     r9d, r9d
0x180004bbb  mov     [rsp+78h+var_50], rdx
0x180004bc0  mov     r8, rbp
0x180004bc3  mov     edx, r14d
0x180004bc6  mov     dword ptr [rsp+78h+var_58], r12d
0x180004bcb  mov     rax, [rcx]
0x180004bce  mov     rax, [rax+230h]
0x180004bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bda  xor     esi, esi
0x180004bdc  mov     r12d, eax
0x180004bdf  mov     edi, r14d
0x180004be2  test    r14d, r14d
0x180004be5  jle     short loc_180004C07
0x180004be7  nop     word ptr [rax+rax+00000000h]
0x180004bf0  movzx   ecx, word ptr [rbp+0]; unsigned int
0x180004bf4  lea     rbp, [rbp+2]
0x180004bf8  xor     edx, edx; unsigned __int8
0x180004bfa  dec     edi
0x180004bfc  call    ?GetCharFlags@@YAKKE@Z; GetCharFlags(ulong,uchar)
0x180004c01  or      esi, eax
0x180004c03  test    edi, edi
0x180004c05  jg      short loc_180004BF0
0x180004c07  mov     rbp, [rbx+38h]
0x180004c0b  mov     eax, [rbp+0C0h]
0x180004c11  mov     edi, eax
0x180004c13  xor     edi, esi
0x180004c15  and     edi, esi
0x180004c17  jnz     loc_180004CDB
0x180004c1d  mov     rsi, [r13+0]
0x180004c21  mov     r13, [rsp+78h+var_30]
0x180004c26  movsx   eax, word ptr [rsi+60h]
0x180004c2a  cmp     r15d, eax
0x180004c2d  jnz     short loc_180004C8B
0x180004c2f  cmp     r15d, 0FFFFFFFFh
0x180004c33  jz      short loc_180004C4B
0x180004c35  mov     rcx, cs:qword_1800A72D0
0x180004c3c  mov     edx, r15d
0x180004c3f  mov     rax, [rcx]
0x180004c42  mov     rax, [rax+8]
0x180004c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c4b  mov     r15, [rsp+78h+var_38]
0x180004c50  cmp     r12d, r14d
0x180004c53  jnz     loc_180005052
0x180004c59  sub     [rbx+2ACh], r12d
0x180004c60  mov     eax, [rbx+30h]
0x180004c63  mov     rdi, [rsp+78h+var_28]
0x180004c68  mov     rsi, [rsp+78h+arg_8]
0x180004c70  add     rsp, 58h
0x180004c74  pop     r14
0x180004c76  pop     r12
0x180004c78  pop     rbp
0x180004c79  pop     rbx
0x180004c7a  retn
0x180004c7c  mov     eax, [rcx+30h]
0x180004c7f  add     rsp, 58h
0x180004c83  pop     r14
0x180004c85  pop     r12
0x180004c87  pop     rbp
0x180004c88  pop     rbx
0x180004c89  retn
0x180004c8b  mov     rdi, cs:qword_1800A72D0
0x180004c92  mov     edx, r15d
0x180004c95  mov     rcx, rdi
0x180004c98  mov     rax, [rdi]
0x180004c9b  mov     rax, [rax]
0x180004c9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ca3  mov     rax, [rdi]
0x180004ca6  mov     rcx, rdi
0x180004ca9  movsx   edx, word ptr [rsi+60h]
0x180004cad  mov     rax, [rax+8]
0x180004cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb6  mov     [rsi+60h], r15w
0x180004cbb  jmp     loc_180004C2F
0x180004cc0  mov     eax, 0Fh
0x180004cc5  sub     eax, ecx
0x180004cc7  cmp     r14d, eax
0x180004cca  cmovge  r14d, eax
0x180004cce  test    r14d, r14d
0x180004cd1  jg      loc_180004F20
0x180004cd7  xor     eax, eax
0x180004cd9  jmp     short loc_180004C63
0x180004cdb  mov     ecx, edi
0x180004cdd  or      ecx, eax
0x180004cdf  mov     [rbp+0C0h], ecx
0x180004ce5  and     edi, 61086013h
0x180004ceb  jz      loc_180004D81
0x180004cf1  and     ecx, 61086013h
0x180004cf7  cmp     ecx, edi
0x180004cf9  jnz     loc_180004D81
0x180004cff  cmp     word ptr [rbp+0C4h], 0FFFFh
0x180004d07  jnz     short loc_180004D40
0x180004d09  movzx   eax, byte ptr [rbp+0C6h]
0x180004d10  movzx   ecx, al
0x180004d13  or      cl, 1
0x180004d16  cmp     al, cl
0x180004d18  jz      short loc_180004D40
0x180004d1a  mov     rax, [rbp+40h]
0x180004d1e  xor     r8d, r8d
0x180004d21  mov     [rbp+0C6h], cl
0x180004d27  xor     edx, edx
0x180004d29  or      dword ptr [rax+38h], 80h
0x180004d30  mov     rcx, [rbp+30h]
0x180004d34  mov     rax, [rcx]
0x180004d37  mov     rax, [rax+48h]
0x180004d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d40  mov     rcx, rbp; this
0x180004d43  call    ?ItemizeDoc@CTxtEdit@@QEAAXPEAVIUndoBuilder@@J@Z; CTxtEdit::ItemizeDoc(IUndoBuilder *,long)
0x180004d48  mov     rcx, [rbp+50h]
0x180004d4c  test    rcx, rcx
0x180004d4f  jnz     loc_180004FFE
0x180004d55  mov     rcx, [rbp+58h]
0x180004d59  test    rcx, rcx
0x180004d5c  jnz     loc_18000500F
0x180004d62  mov     eax, [rbp+0B4h]
0x180004d68  mov     ecx, [rbp+0C0h]
0x180004d6e  shl     ecx, 16h
0x180004d71  xor     ecx, eax
0x180004d73  and     ecx, 400000h
0x180004d79  xor     ecx, eax
0x180004d7b  mov     [rbp+0B4h], ecx
0x180004d81  mov     eax, edi
0x180004d83  shr     eax, 18h
0x180004d86  and     eax, 1
0x180004d89  test    edi, 61000000h
0x180004d8f  lea     edi, [rax+2]
0x180004d92  cmovz   edi, eax
0x180004d95  test    edi, edi
0x180004d97  jz      loc_180004C1D
0x180004d9d  call    ?GetUniscribe@@YAPEAVCUniscribe@@XZ; GetUniscribe(void)
0x180004da2  mov     rcx, [rbp+0A8h]
0x180004da9  test    rcx, rcx
0x180004dac  jnz     loc_180005032
0x180004db2  test    rax, rax
0x180004db5  jz      loc_180004C1D
0x180004dbb  mov     edx, 40h ; '@'; unsigned int
0x180004dc0  mov     ecx, 28h ; '('; unsigned int
0x180004dc5  call    ?PvAlloc@CW32System@@SAPEAXKI@Z; CW32System::PvAlloc(ulong,uint)
0x180004dca  mov     rcx, rax
0x180004dcd  test    rax, rax
0x180004dd0  jz      loc_180005020
0x180004dd6  lea     rdx, [rbp+80h]
0x180004ddd  mov     qword ptr [rcx+18h], 0
0x180004de5  mov     qword ptr [rcx+20h], 0
0x180004ded  lea     rax, ??_7CTxtBreaker@@6B@; const CTxtBreaker::`vftable'
0x180004df4  mov     [rcx], rax
0x180004df7  test    rdx, rdx
0x180004dfa  jz      short loc_180004E06
0x180004dfc  mov     rax, [rdx]
0x180004dff  mov     [rcx+8], rax
0x180004e03  mov     [rdx], rcx
0x180004e06  mov     [rcx+10h], rbp
0x180004e0a  jmp     loc_180005022
0x180004e0f  test    rdx, rdx
0x180004e12  jz      loc_180004BA8
0x180004e18  cmp     word ptr [rdx+48h], 0FFFFh
0x180004e1d  jnz     loc_180004BA8
0x180004e23  test    byte ptr [rbx+1D8h], 80h
0x180004e2a  jnz     loc_180004FE4
0x180004e30  mov     rcx, [rbx+40h]; this
0x180004e34  xor     r9d, r9d; int
0x180004e37  mov     [rsp+78h+var_40], r12d; unsigned int
0x180004e3c  mov     r8, rbp; unsigned __int16 *
0x180004e3f  mov     [rsp+78h+var_48], r12; int *
0x180004e44  mov     edx, r14d; int
0x180004e47  mov     [rsp+78h+var_50], rbp; unsigned __int16 *
0x180004e4c  mov     [rsp+78h+var_58], r12; struct IUndoBuilder *
0x180004e51  call    ?CleanseAndReplaceRange@CTxtRange@@QEAAJJPEBGHPEAVIUndoBuilder@@PEAGPEAJK@Z; CTxtRange::CleanseAndReplaceRange(long,ushort const *,int,IUndoBuilder *,ushort *,long *,ulong)
0x180004e56  mov     r12d, eax
0x180004e59  jmp     loc_180004C1D
0x180004e5e  mov     rdx, r12
0x180004e61  mov     rdi, r13
0x180004e64  jmp     loc_180004B9A
0x180004e69  mov     rdx, r12
0x180004e6c  jmp     loc_180004B96
0x180004e71  movzx   eax, word ptr [rbx+0F4h]
0x180004e78  sub     eax, 2
0x180004e7b  cmp     eax, 5
0x180004e7e  ja      loc_180004ADF
0x180004e84  cmp     word ptr [rbx+rcx*2+22Ah], 9
0x180004e8d  jnz     loc_180004ADF
0x180004e93  cmp     ecx, 1
0x180004e96  jle     loc_180004FBB
0x180004e9c  movzx   edx, word ptr [rbx+rcx*2+228h]
0x180004ea4  movzx   ecx, word ptr [rbx+2C8h]
0x180004eab  cmp     dx, 2Eh ; '.'
0x180004eaf  jnz     loc_180004F83
0x180004eb5  mov     eax, 200h
0x180004eba  jmp     loc_180004FA4
0x180004ebf  add     rcx, 8; this
0x180004ec3  call    ?GetPF@CRchTxtPtr@@QEBAPEBVCParaFormat@@XZ; CRchTxtPtr::GetPF(void)
0x180004ec8  mov     ecx, 4000h
0x180004ecd  test    [rax+2], cx
0x180004ed1  jz      loc_180004AED
0x180004ed7  cmp     [rbx+138h], r12d
0x180004ede  jz      loc_180004AED
0x180004ee4  mov     rcx, [rbx+40h]
0x180004ee8  add     rcx, 18h; this
0x180004eec  call    ?IsAfterEOP@CTxtPtr@@QEAAHXZ; CTxtPtr::IsAfterEOP(void)
0x180004ef1  test    eax, eax
0x180004ef3  jnz     loc_180004AED
0x180004ef9  mov     [rbx+13Ch], r12d
0x180004f00  mov     dword ptr [rbx+30h], 6
0x180004f07  mov     eax, 6
0x180004f0c  jmp     loc_180004C63
0x180004f11  mov     r14d, eax
0x180004f14  mov     dword ptr [rcx+30h], 12h
0x180004f1b  jmp     loc_180004AC0
0x180004f20  movsxd  rax, r14d
0x180004f23  lea     rsi, [rbx+rcx*2]
0x180004f27  lea     rcx, [rsi+22Ch]; void *
0x180004f2e  lea     rdi, [rax+rax]
0x180004f32  mov     r8, rdi; Size
0x180004f35  call    memmove_0
0x180004f3a  mov     [rdi+rsi+22Ch], r12w
0x180004f43  add     [rbx+250h], r14d
0x180004f4a  jmp     loc_180004CD7
0x180004f4f  test    r9d, r9d
0x180004f52  jz      loc_180004ADF
0x180004f58  mov     [rbx+250h], r12d
0x180004f5f  test    byte ptr [rsi+4], 2
0x180004f63  jnz     loc_180004E71
0x180004f69  mov     r8d, ecx; int
0x180004f6c  lea     rdx, [rbx+22Ch]; unsigned __int16 *
0x180004f73  mov     rcx, rbx; this
0x180004f76  xor     r9d, r9d; int
0x180004f79  call    ?AddText@CRTFRead@@AEAAHPEAGJH@Z; CRTFRead::AddText(ushort *,long,int)
0x180004f7e  jmp     loc_180004ADF
  ... truncated ...
```
