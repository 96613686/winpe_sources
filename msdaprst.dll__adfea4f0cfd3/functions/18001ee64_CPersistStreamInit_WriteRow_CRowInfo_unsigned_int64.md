# CPersistStreamInit::WriteRow(CRowInfo &,unsigned __int64)

- ea: `0x18001ee64`
- end: `0x18001f1b6`
- name: `?WriteRow@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z`
- size: `850`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x18001e3c0`

## callees

- `0x180003c38`
- `0x180004384`
- `0x18001b008`
- `0x18001b654`
- `0x18001d1c8`
- `0x18001db24`
- `0x18001e3c0`
- `0x18001ea04`
- `0x18001ee64`
- `0x18001f520`
- `0x18001f680`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteRow(CPersistStreamInit *this, struct CRowInfo *a2, __int64 a3)
{
  __int64 *v3; // r14
  unsigned int v4; // r13d
  int v8; // edi
  bool v9; // r9
  __int64 v10; // rdx
  unsigned int i; // r12d
  __int64 v12; // r9
  __int64 v13; // r8
  int v14; // eax
  bool v15; // r9
  __int64 v16; // rdx
  unsigned int v17; // ebp
  CPersistStreamInit *v18; // rcx
  __int64 v19; // rbp
  unsigned int j; // r15d
  __int64 v21; // r14
  unsigned int k; // r12d
  unsigned __int16 v23; // dx
  __int64 v24; // rcx
  int v26; // [rsp+20h] [rbp-58h]

  v3 = (__int64 *)*((_QWORD *)a2 + 23);
  v4 = 0;
  if ( *((_DWORD *)a2 + 48)
    || (v8 = CPersistStreamInit::WriteRowHeader(this, a2, 0), v8 >= 0)
    && ((v10 = *((_QWORD *)a2 + 30)) == 0
     || (unsigned int)a3 >= *((_DWORD *)a2 + 62)
     || (*(_BYTE *)(((__int64)(int)a3 >> 3) + v10 + 4) & *((_BYTE *)bits + (a3 & 7))) == 0
     || (v8 = CPersistStreamInit::WriteAttributeDefinition(
                this,
                *(void **)(*((_QWORD *)this + 9) + 496LL),
                *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                v9,
                65,
                0),
         v8 >= 0)) )
  {
    for ( i = 0; i < *((_DWORD *)a2 + 48); ++i )
    {
      v12 = *((_QWORD *)a2 + 11);
      v13 = *v3;
      if ( ((*((_DWORD *)a2 + 49) - 2) & 0xFFFFFFFD) != 0 )
      {
        v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)a2 + 13) + 32LL))(
                *((_QWORD *)a2 + 13),
                a3,
                v13,
                v12);
        v8 = v14;
        if ( v14 == -2147217885 )
        {
          v8 = 0;
          goto LABEL_44;
        }
        if ( ((v14 + 0x80000000) & 0x80000000) == 0 && v14 != -2147217887 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180049B50[0] )
            bidTraceW(off_1800491F0[0], 2278400, off_180049B50[0], 2225, v26);
          goto LABEL_44;
        }
      }
      else
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, __int64))(**((_QWORD **)a2 + 14) + 48LL))(
               *((_QWORD *)a2 + 14),
               a3,
               v13,
               v12);
        if ( v8 < 0 )
          goto LABEL_44;
      }
      if ( !i )
      {
        v8 = CPersistStreamInit::WriteRowHeader(this, a2, 0);
        if ( v8 < 0 )
          goto LABEL_44;
        v16 = *((_QWORD *)a2 + 30);
        if ( v16 )
        {
          if ( (unsigned int)a3 < *((_DWORD *)a2 + 62)
            && (*(_BYTE *)(((__int64)(int)a3 >> 3) + v16 + 4) & *((_BYTE *)bits + (a3 & 7))) != 0 )
          {
            v8 = CPersistStreamInit::WriteAttributeDefinition(
                   this,
                   *(void **)(*((_QWORD *)this + 9) + 496LL),
                   *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                   v15,
                   65,
                   0);
            if ( v8 < 0 )
              goto LABEL_44;
          }
        }
      }
      v17 = 0;
      if ( *((_DWORD *)v3 + 4) )
      {
        while ( 1 )
        {
          v8 = CPersistStreamInit::WriteColumnToStream(
                 this,
                 a2,
                 *((_WORD *)v3 + 10) + (unsigned __int16)v17,
                 (struct tagDBBINDING *)(v3[1] + 88LL * v17));
          if ( v8 < 0 )
            break;
          if ( ++v17 >= *((_DWORD *)v3 + 4) )
            goto LABEL_26;
        }
        CPersistStreamInit::FreeFetchedData(v18, a2, (struct tagDBBINDING *)v3[1], *((_DWORD *)v3 + 4));
        goto LABEL_44;
      }
LABEL_26:
      v3 += 3;
    }
    if ( *((_DWORD *)a2 + 32) )
    {
      CPersistStreamInit::WriteRowHeader(this, a2, 1);
      v19 = *((_QWORD *)a2 + 23);
      for ( j = 0; j < *((_DWORD *)a2 + 48); ++j )
      {
        v21 = *(_QWORD *)(v19 + 8);
        for ( k = 0; k < *(_DWORD *)(v19 + 16); ++k )
        {
          if ( (CMetaData::mdGetFlags(a2, *(_WORD *)v21 - 1) & 0x2000) != 0 || CMetaData::mdGetType(a2, v23) == 136 )
          {
            v24 = *((_QWORD *)a2 + 11);
            if ( !*(_DWORD *)(v24 + *(_QWORD *)(v21 + 24)) )
            {
              v8 = CPersistStreamInit::WriteData(
                     this,
                     (struct CRowInfo *)(*((_QWORD *)a2 + 17) + ((unsigned __int64)v4 << 8)),
                     *(void **)(*(_QWORD *)(v21 + 8) + v24));
              if ( v8 < 0 )
                goto LABEL_44;
              ++v4;
            }
          }
          v21 += 88;
        }
        v19 += 24;
      }
    }
    if ( !*((_WORD *)a2 + 112) || (v8 = CPersistStreamInit::WriteForceNull(this, a2), v8 >= 0) )
      v8 = CPersistStreamInit::WriteRowFooter(this, a2, *((_DWORD *)a2 + 32) != 0);
  }
LABEL_44:
  *((_WORD *)a2 + 112) = 0;
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ee64  push    rbx
0x18001ee66  push    rbp
0x18001ee67  push    rsi
0x18001ee68  push    rdi
0x18001ee69  push    r12
0x18001ee6b  push    r13
0x18001ee6d  push    r14
0x18001ee6f  push    r15
0x18001ee71  sub     rsp, 38h
0x18001ee75  mov     r14, [rdx+0B8h]
0x18001ee7c  lea     rbp, bits
0x18001ee83  xor     r13d, r13d
0x18001ee86  mov     r15, r8
0x18001ee89  mov     rbx, rdx
0x18001ee8c  mov     rsi, rcx
0x18001ee8f  cmp     [rdx+0C0h], r13d
0x18001ee96  jnz     short loc_18001EF03
0x18001ee98  xor     r8d, r8d; bool
0x18001ee9b  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001eea0  mov     edi, eax
0x18001eea2  test    eax, eax
0x18001eea4  js      loc_18001F19A
0x18001eeaa  mov     rdx, [rbx+0F0h]
0x18001eeb1  test    rdx, rdx
0x18001eeb4  jz      short loc_18001EF03
0x18001eeb6  cmp     r15d, [rbx+0F8h]
0x18001eebd  jnb     short loc_18001EF03
0x18001eebf  movsxd  rcx, r15d
0x18001eec2  mov     rax, rcx
0x18001eec5  and     ecx, 7
0x18001eec8  sar     rax, 3
0x18001eecc  mov     al, [rax+rdx+4]
0x18001eed0  test    [rcx+rbp], al
0x18001eed3  jz      short loc_18001EF03
0x18001eed5  mov     rdx, [rsi+48h]
0x18001eed9  mov     rcx, rsi; this
0x18001eedc  mov     [rsp+78h+var_50], r13b; bool
0x18001eee1  mov     [rsp+78h+var_58], 41h ; 'A'; char
0x18001eee6  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001eeed  mov     rdx, [rdx+1F0h]; void *
0x18001eef4  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001eef9  mov     edi, eax
0x18001eefb  test    eax, eax
0x18001eefd  js      loc_18001F19A
0x18001ef03  mov     r12d, r13d
0x18001ef06  mov     edi, 1
0x18001ef0b  mov     ebp, 80000000h
0x18001ef10  cmp     r12d, [rbx+0C0h]
0x18001ef17  jnb     loc_18001F0A3
0x18001ef1d  mov     eax, [rbx+0C4h]
0x18001ef23  mov     rdx, r15
0x18001ef26  mov     r9, [rbx+58h]
0x18001ef2a  sub     eax, 2
0x18001ef2d  mov     r8, [r14]
0x18001ef30  test    eax, 0FFFFFFFDh
0x18001ef35  jz      short loc_18001EFA2
0x18001ef37  mov     rcx, [rbx+68h]
0x18001ef3b  mov     rax, [rcx]
0x18001ef3e  mov     rax, [rax+20h]
0x18001ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef47  mov     edi, eax
0x18001ef49  cmp     eax, 80040E23h
0x18001ef4e  jz      loc_18001F086
0x18001ef54  add     eax, ebp
0x18001ef56  test    ebp, eax
0x18001ef58  jnz     short loc_18001EFBC
0x18001ef5a  cmp     edi, 80040E21h
0x18001ef60  jz      short loc_18001EFBC
0x18001ef62  test    byte ptr cs:_bidGblFlags, 2
0x18001ef69  jz      loc_18001F19A
0x18001ef6f  mov     rax, cs:off_180049B50; "<CPersistStreamInit::WriteRow|ADO|ERR> "...
0x18001ef76  test    rax, rax
0x18001ef79  jz      loc_18001F19A
0x18001ef7f  mov     r8, cs:off_180049B50; "<CPersistStreamInit::WriteRow|ADO|ERR> "...
0x18001ef86  mov     r9d, 8B1h
0x18001ef8c  mov     rcx, cs:off_1800491F0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001ef93  mov     edx, 22C400h
0x18001ef98  call    _bidTraceW
0x18001ef9d  jmp     loc_18001F19A
0x18001efa2  mov     rcx, [rbx+70h]
0x18001efa6  mov     rax, [rcx]
0x18001efa9  mov     rax, [rax+30h]
0x18001efad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efb2  mov     edi, eax
0x18001efb4  test    eax, eax
0x18001efb6  js      loc_18001F19A
0x18001efbc  test    r12d, r12d
0x18001efbf  jnz     short loc_18001F039
0x18001efc1  xor     r8d, r8d; bool
0x18001efc4  mov     rdx, rbx; struct CRowInfo *
0x18001efc7  mov     rcx, rsi; this
0x18001efca  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001efcf  mov     edi, eax
0x18001efd1  test    eax, eax
0x18001efd3  js      loc_18001F19A
0x18001efd9  mov     rdx, [rbx+0F0h]
0x18001efe0  test    rdx, rdx
0x18001efe3  jz      short loc_18001F039
0x18001efe5  cmp     r15d, [rbx+0F8h]
0x18001efec  jnb     short loc_18001F039
0x18001efee  movsxd  rcx, r15d
0x18001eff1  mov     rax, rcx
0x18001eff4  and     ecx, 7
0x18001eff7  sar     rax, 3
0x18001effb  mov     al, [rax+rdx+4]
0x18001efff  lea     rdx, bits
0x18001f006  test    [rcx+rdx], al
0x18001f009  jz      short loc_18001F039
0x18001f00b  mov     rdx, [rsi+48h]
0x18001f00f  mov     rcx, rsi; this
0x18001f012  mov     [rsp+78h+var_50], r13b; bool
0x18001f017  mov     [rsp+78h+var_58], 41h ; 'A'; char
0x18001f01c  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001f023  mov     rdx, [rdx+1F0h]; void *
0x18001f02a  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001f02f  mov     edi, eax
0x18001f031  test    eax, eax
0x18001f033  js      loc_18001F19A
0x18001f039  mov     ebp, r13d
0x18001f03c  cmp     [r14+10h], r13d
0x18001f040  jbe     short loc_18001F075
0x18001f042  mov     eax, ebp
0x18001f044  movzx   r8d, bp
0x18001f048  add     r8w, [r14+14h]; unsigned __int16
0x18001f04d  mov     rdx, rbx; struct CRowInfo *
0x18001f050  imul    r9, rax, 58h ; 'X'
0x18001f054  mov     rcx, rsi; this
0x18001f057  add     r9, [r14+8]; struct tagDBBINDING *
0x18001f05b  call    ?WriteColumnToStream@CPersistStreamInit@@AEAAJAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z; CPersistStreamInit::WriteColumnToStream(CRowInfo &,ushort,tagDBBINDING *)
0x18001f060  mov     edi, eax
0x18001f062  test    eax, eax
0x18001f064  js      short loc_18001F08E
0x18001f066  mov     edi, 1
0x18001f06b  add     ebp, edi
0x18001f06d  cmp     ebp, [r14+10h]
0x18001f071  jb      short loc_18001F042
0x18001f073  jmp     short loc_18001F07A
0x18001f075  mov     edi, 1
0x18001f07a  add     r12d, edi
0x18001f07d  add     r14, 18h
0x18001f081  jmp     loc_18001EF0B
0x18001f086  mov     edi, r13d
0x18001f089  jmp     loc_18001F19A
0x18001f08e  mov     r9d, [r14+10h]; unsigned int
0x18001f092  mov     rdx, rbx; struct CRowInfo *
0x18001f095  mov     r8, [r14+8]; struct tagDBBINDING *
0x18001f099  call    ?FreeFetchedData@CPersistStreamInit@@AEAAXAEAVCRowInfo@@PEAUtagDBBINDING@@K@Z; CPersistStreamInit::FreeFetchedData(CRowInfo &,tagDBBINDING *,ulong)
0x18001f09e  jmp     loc_18001F19A
0x18001f0a3  cmp     [rbx+80h], r13d
0x18001f0aa  jz      loc_18001F162
0x18001f0b0  mov     r8b, dil; bool
0x18001f0b3  mov     rdx, rbx; struct CRowInfo *
0x18001f0b6  mov     rcx, rsi; this
0x18001f0b9  call    ?WriteRowHeader@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowHeader(CRowInfo &,bool)
0x18001f0be  mov     rbp, [rbx+0B8h]
0x18001f0c5  xor     r15d, r15d
0x18001f0c8  cmp     r15d, [rbx+0C0h]
0x18001f0cf  jnb     loc_18001F15F
0x18001f0d5  mov     r14, [rbp+8]
0x18001f0d9  xor     r12d, r12d
0x18001f0dc  cmp     r12d, [rbp+10h]
0x18001f0e0  jnb     short loc_18001F153
0x18001f0e2  movzx   eax, word ptr [r14]
0x18001f0e6  mov     rcx, rbx; this
0x18001f0e9  sub     ax, di
0x18001f0ec  movzx   edx, ax; unsigned __int16
0x18001f0ef  movzx   r10d, ax
0x18001f0f3  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001f0f8  bt      eax, 0Dh
0x18001f0fc  jb      short loc_18001F110
0x18001f0fe  mov     rcx, rbx; this
0x18001f101  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001f106  mov     ecx, 88h
0x18001f10b  cmp     ax, cx
0x18001f10e  jnz     short loc_18001F14A
0x18001f110  mov     rcx, [rbx+58h]
0x18001f114  mov     rax, [r14+18h]
0x18001f118  cmp     dword ptr [rcx+rax], 0
0x18001f11c  jnz     short loc_18001F14A
0x18001f11e  mov     r8, [r14+8]
0x18001f122  mov     edx, r13d
0x18001f125  shl     rdx, 8
0x18001f129  add     rdx, [rbx+88h]; struct CRowInfo *
0x18001f130  mov     r8, [r8+rcx]; unsigned __int64
0x18001f134  mov     rcx, rsi; this
0x18001f137  call    ?WriteData@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_K@Z; CPersistStreamInit::WriteData(CRowInfo &,unsigned __int64)
0x18001f13c  mov     edi, eax
0x18001f13e  test    eax, eax
0x18001f140  js      short loc_18001F197
0x18001f142  mov     edi, 1
0x18001f147  add     r13d, edi
0x18001f14a  add     r12d, edi
0x18001f14d  add     r14, 58h ; 'X'
0x18001f151  jmp     short loc_18001F0DC
0x18001f153  add     r15d, edi
0x18001f156  add     rbp, 18h
0x18001f15a  jmp     loc_18001F0C8
0x18001f15f  xor     r13d, r13d
0x18001f162  cmp     [rbx+0E0h], r13w
0x18001f16a  jz      short loc_18001F17D
0x18001f16c  mov     rdx, rbx; struct CRowInfo *
0x18001f16f  mov     rcx, rsi; this
0x18001f172  call    ?WriteForceNull@CPersistStreamInit@@AEAAJAEAVCRowInfo@@@Z; CPersistStreamInit::WriteForceNull(CRowInfo &)
0x18001f177  mov     edi, eax
0x18001f179  test    eax, eax
0x18001f17b  js      short loc_18001F19A
0x18001f17d  cmp     [rbx+80h], r13d
0x18001f184  mov     rdx, rbx; struct CRowInfo *
0x18001f187  mov     rcx, rsi; this
0x18001f18a  setnz   r8b; bool
0x18001f18e  call    ?WriteRowFooter@CPersistStreamInit@@AEAAJAEAVCRowInfo@@_N@Z; CPersistStreamInit::WriteRowFooter(CRowInfo &,bool)
0x18001f193  mov     edi, eax
0x18001f195  jmp     short loc_18001F19A
0x18001f197  xor     r13d, r13d
0x18001f19a  mov     [rbx+0E0h], r13w
0x18001f1a2  mov     eax, edi
0x18001f1a4  add     rsp, 38h
0x18001f1a8  pop     r15
0x18001f1aa  pop     r14
0x18001f1ac  pop     r13
0x18001f1ae  pop     r12
0x18001f1b0  pop     rdi
0x18001f1b1  pop     rsi
0x18001f1b2  pop     rbp
0x18001f1b3  pop     rbx
0x18001f1b4  retn
```
