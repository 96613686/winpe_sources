# CPersistStreamInit::WriteColumnToStream(CRowInfo &,ushort,tagDBBINDING *)

- ea: `0x18001db24`
- end: `0x18001dd68`
- name: `?WriteColumnToStream@CPersistStreamInit@@AEAAJAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z`
- size: `580`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16, struct tagDBBINDING *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001ee64`

## callees

- `0x180001dd4`
- `0x180003c38`
- `0x18001b654`
- `0x18001d054`
- `0x18001d350`
- `0x18001db24`
- `0x18001fe94`
- `0x180020248`

## pseudocode

```c
__int64 __fastcall CPersistStreamInit::WriteColumnToStream(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3,
        struct tagDBBINDING *a4)
{
  __int64 v6; // r12
  __int16 v7; // r15
  __int16 Flags; // ax
  int v10; // r11d
  unsigned __int64 v12; // rdx
  __int64 v13; // r8
  CPersistStreamInit *v14; // rcx
  int v15; // ebx
  void *v16; // rbp
  unsigned __int8 *v17; // rcx
  unsigned __int8 *v18; // rax
  unsigned int v19; // eax
  _BYTE *v20; // rdx
  CPersistStreamInit *v21; // rcx
  unsigned int v22; // [rsp+88h] [rbp+10h] BYREF

  v6 = a3;
  v7 = a4->wType & 0xBFFF;
  Flags = CMetaData::mdGetFlags(a2, a3);
  v22 = 0;
  if ( ((Flags & 0x2000) != 0 || v7 == 136) && !v10 )
    return 0;
  v12 = *((_QWORD *)a2 + 26);
  if ( v12 )
  {
    v13 = *((_QWORD *)a2 + 27);
    if ( v13 )
    {
      v14 = 0;
      do
      {
        if ( a4->iOrdinal == *(_QWORD *)(v13 + 8LL * (unsigned int)v14) )
          break;
        v14 = (CPersistStreamInit *)(unsigned int)((_DWORD)v14 + 1);
      }
      while ( (unsigned int)v14 < v12 );
      if ( (unsigned int)v14 == v12 )
      {
        CPersistStreamInit::FreeFetchedData(v14, a2, a4, 1u);
        return 0;
      }
    }
  }
  v15 = 0;
  v16 = *(void **)(*((_QWORD *)a2 + 8) + 16 * v6);
  if ( v10 == 3 )
  {
    if ( v12 )
    {
      v17 = (unsigned __int8 *)*((_QWORD *)a2 + 29);
      if ( v17 || (v18 = MMMAlloc(8 * *((_DWORD *)a2 + 21), v12), *((_QWORD *)a2 + 29) = v18, (v17 = v18) != 0) )
        *(_QWORD *)&v17[8 * (unsigned __int16)(*((_WORD *)a2 + 112))++] = v16;
      else
        return (unsigned int)-2147024882;
    }
  }
  else if ( (v10 & 0xFFFFFFFB) != 0 || v7 == 12 && !*(_WORD *)(a4->obValue + *((_QWORD *)a2 + 11)) )
  {
    if ( v10 != 13 && v10 && (v10 != 8 || *((_DWORD *)a2 + 49) != 1) )
    {
      v15 = -2147217887;
      if ( v10 == 2 )
        return (unsigned int)-2147217913;
    }
  }
  else
  {
    v15 = CPersistStreamInit::Write(
            this,
            *(_BYTE **)(*((_QWORD *)this + 9) + 704LL),
            *(unsigned __int8 *)(*((_QWORD *)this + 9) + 712LL),
            &v22,
            1);
    if ( v15 >= 0 )
    {
      v19 = CPersistStreamInit::_len(this, v16);
      v15 = CPersistStreamInit::Write(v21, v20, v19, &v22, 0);
      if ( v15 >= 0 )
      {
        v15 = CPersistStreamInit::WriteTag(this, 0x2Bu, &v22);
        if ( v15 >= 0 )
        {
          v15 = CPersistStreamInit::WriteTag(this, 0x29u, &v22);
          if ( v15 >= 0 )
          {
            v15 = CPersistStreamInit::WriteColumnDataToStream(this, a2, v6, a4);
            if ( v15 >= 0 )
              return (unsigned int)CPersistStreamInit::WriteTag(this, 0x29u, &v22);
          }
        }
      }
    }
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18001db24  push    rbx
0x18001db26  push    rbp
0x18001db27  push    rsi
0x18001db28  push    rdi
0x18001db29  push    r12
0x18001db2b  push    r13
0x18001db2d  push    r14
0x18001db2f  push    r15
0x18001db31  sub     rsp, 38h
0x18001db35  mov     rax, [rdx+58h]
0x18001db39  mov     rdi, rdx
0x18001db3c  mov     r10, [r9+18h]
0x18001db40  mov     rsi, rcx
0x18001db43  movzx   r12d, r8w
0x18001db47  mov     r15d, 0BFFFh
0x18001db4d  and     r15w, [r9+54h]
0x18001db52  movzx   edx, r12w; unsigned __int16
0x18001db56  mov     rcx, rdi; this
0x18001db59  mov     r14, r9
0x18001db5c  mov     r11d, [r10+rax]
0x18001db60  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001db65  xor     r13d, r13d
0x18001db68  mov     [rsp+78h+arg_8], r13d
0x18001db70  bt      eax, 0Dh
0x18001db74  jb      short loc_18001DB81
0x18001db76  mov     eax, 88h
0x18001db7b  cmp     r15w, ax
0x18001db7f  jnz     short loc_18001DB8D
0x18001db81  test    r11d, r11d
0x18001db84  jnz     short loc_18001DB8D
0x18001db86  xor     eax, eax
0x18001db88  jmp     loc_18001DD56
0x18001db8d  mov     rdx, [rdi+0D0h]; unsigned int
0x18001db94  mov     r9d, 1; unsigned int
0x18001db9a  test    rdx, rdx
0x18001db9d  jz      short loc_18001DBDC
0x18001db9f  mov     r8, [rdi+0D8h]
0x18001dba6  test    r8, r8
0x18001dba9  jz      short loc_18001DBDC
0x18001dbab  mov     ecx, r13d
0x18001dbae  test    rdx, rdx
0x18001dbb1  jz      short loc_18001DBC8
0x18001dbb3  mov     r10, [r14]
0x18001dbb6  mov     eax, ecx
0x18001dbb8  cmp     r10, [r8+rax*8]
0x18001dbbc  jz      short loc_18001DBC8
0x18001dbbe  add     ecx, r9d; this
0x18001dbc1  mov     eax, ecx
0x18001dbc3  cmp     rax, rdx
0x18001dbc6  jb      short loc_18001DBB6
0x18001dbc8  mov     eax, ecx
0x18001dbca  cmp     rax, rdx
0x18001dbcd  jnz     short loc_18001DBDC
0x18001dbcf  mov     r8, r14; struct tagDBBINDING *
0x18001dbd2  mov     rdx, rdi; struct CRowInfo *
0x18001dbd5  call    ?FreeFetchedData@CPersistStreamInit@@AEAAXAEAVCRowInfo@@PEAUtagDBBINDING@@K@Z; CPersistStreamInit::FreeFetchedData(CRowInfo &,tagDBBINDING *,ulong)
0x18001dbda  jmp     short loc_18001DB86
0x18001dbdc  mov     rax, [rdi+40h]
0x18001dbe0  mov     rcx, r12
0x18001dbe3  add     rcx, rcx
0x18001dbe6  mov     ebx, r13d
0x18001dbe9  mov     rbp, [rax+rcx*8]
0x18001dbed  cmp     r11d, 3
0x18001dbf1  jnz     short loc_18001DC4A
0x18001dbf3  test    rdx, rdx
0x18001dbf6  jz      loc_18001DD54
0x18001dbfc  mov     rcx, [rdi+0E8h]
0x18001dc03  test    rcx, rcx
0x18001dc06  jnz     short loc_18001DC32
0x18001dc08  mov     ecx, [rdi+54h]
0x18001dc0b  shl     ecx, 3; unsigned int
0x18001dc0e  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001dc13  mov     [rdi+0E8h], rax
0x18001dc1a  mov     rcx, rax
0x18001dc1d  test    rax, rax
0x18001dc20  jnz     short loc_18001DC2C
0x18001dc22  mov     ebx, 8007000Eh
0x18001dc27  jmp     loc_18001DD54
0x18001dc2c  mov     r9d, 1
0x18001dc32  movzx   eax, word ptr [rdi+0E0h]
0x18001dc39  mov     [rcx+rax*8], rbp
0x18001dc3d  add     [rdi+0E0h], r9w
0x18001dc45  jmp     loc_18001DD54
0x18001dc4a  test    r11d, 0FFFFFFFBh
0x18001dc51  jnz     loc_18001DD2B
0x18001dc57  cmp     r15w, 0Ch
0x18001dc5c  jnz     short loc_18001DC71
0x18001dc5e  mov     rcx, [r14+8]
0x18001dc62  mov     rax, [rdi+58h]
0x18001dc66  cmp     [rcx+rax], r13w
0x18001dc6b  jz      loc_18001DD2B
0x18001dc71  mov     rdx, [rsi+48h]
0x18001dc75  mov     rcx, rsi; this
0x18001dc78  mov     [rsp+78h+var_58], r9b; bool
0x18001dc7d  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x18001dc85  movzx   r8d, byte ptr [rdx+2C8h]; Size
0x18001dc8d  mov     rdx, [rdx+2C0h]; Src
0x18001dc94  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001dc99  mov     ebx, eax
0x18001dc9b  test    eax, eax
0x18001dc9d  js      loc_18001DD54
0x18001dca3  mov     rdx, rbp; void *
0x18001dca6  mov     rcx, rsi; this
0x18001dca9  call    ?_len@CPersistStreamInit@@AEBAHPEAX@Z; CPersistStreamInit::_len(void *)
0x18001dcae  mov     r8d, eax; Size
0x18001dcb1  mov     [rsp+78h+var_58], r13b; bool
0x18001dcb6  lea     r9, [rsp+78h+arg_8]; unsigned int *
0x18001dcbe  call    ?Write@CPersistStreamInit@@AEAAJPEAXKPEAK_N@Z; CPersistStreamInit::Write(void *,ulong,ulong *,bool)
0x18001dcc3  mov     ebx, eax
0x18001dcc5  test    eax, eax
0x18001dcc7  js      loc_18001DD54
0x18001dccd  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x18001dcd5  mov     dl, 2Bh ; '+'; unsigned __int8
0x18001dcd7  mov     rcx, rsi; this
0x18001dcda  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dcdf  mov     ebx, eax
0x18001dce1  test    eax, eax
0x18001dce3  js      short loc_18001DD54
0x18001dce5  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x18001dced  mov     dl, 29h ; ')'; unsigned __int8
0x18001dcef  mov     rcx, rsi; this
0x18001dcf2  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dcf7  mov     ebx, eax
0x18001dcf9  test    eax, eax
0x18001dcfb  js      short loc_18001DD54
0x18001dcfd  mov     r9, r14; struct tagDBBINDING *
0x18001dd00  movzx   r8d, r12w; unsigned __int16
0x18001dd04  mov     rdx, rdi; struct CRowInfo *
0x18001dd07  mov     rcx, rsi; this
0x18001dd0a  call    ?WriteColumnDataToStream@CPersistStreamInit@@AEAAJAEAVCRowInfo@@GPEAUtagDBBINDING@@@Z; CPersistStreamInit::WriteColumnDataToStream(CRowInfo &,ushort,tagDBBINDING *)
0x18001dd0f  mov     ebx, eax
0x18001dd11  test    eax, eax
0x18001dd13  js      short loc_18001DD54
0x18001dd15  lea     r8, [rsp+78h+arg_8]; unsigned int *
0x18001dd1d  mov     dl, 29h ; ')'; unsigned __int8
0x18001dd1f  mov     rcx, rsi; this
0x18001dd22  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001dd27  mov     ebx, eax
0x18001dd29  jmp     short loc_18001DD54
0x18001dd2b  cmp     r11d, 0Dh
0x18001dd2f  jz      short loc_18001DD54
0x18001dd31  test    r11d, r11d
0x18001dd34  jz      short loc_18001DD54
0x18001dd36  cmp     r11d, 8
0x18001dd3a  jnz     short loc_18001DD45
0x18001dd3c  cmp     [rdi+0C4h], r9d
0x18001dd43  jz      short loc_18001DD54
0x18001dd45  mov     ebx, 80040E21h
0x18001dd4a  cmp     r11d, 2
0x18001dd4e  lea     eax, [rbx-1Ah]
0x18001dd51  cmovz   ebx, eax
0x18001dd54  mov     eax, ebx
0x18001dd56  add     rsp, 38h
0x18001dd5a  pop     r15
0x18001dd5c  pop     r14
0x18001dd5e  pop     r13
0x18001dd60  pop     r12
0x18001dd62  pop     rdi
0x18001dd63  pop     rsi
0x18001dd64  pop     rbp
0x18001dd65  pop     rbx
0x18001dd66  retn
```
