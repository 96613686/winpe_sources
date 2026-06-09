# Database::WriteDirtyPages(Err &)

- ea: `0x10023bb0`
- end: `0x10023f52`
- name: `?WriteDirtyPages@Database@@QAEXAAVErr@@@Z`
- size: `930`
- prototype: `void __thiscall(Database *__hidden this, struct Err *)`
- caller_count: `4`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1001f910`
- `0x10024450`
- `0x10027e70`
- `0x1004f3b0`

## callees

- `0x1000eb60`
- `0x1000f750`
- `0x10023bb0`
- `0x100248b0`
- `0x10025db0`
- `0x1002e740`
- `0x10042440`
- `0x10042760`
- `0x1005e3b0`
- `0x1005e7e8`
- `0x1005e7f3`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10023bed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10023bed`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023c01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023f2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023c01`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10023f2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10023f1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10023f1d`

## pseudocode

```c
void __thiscall Database::WriteDirtyPages(Database *this, void **a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // ebx
  unsigned int v4; // eax
  _DWORD *v5; // eax
  int v6; // edx
  int v7; // ebx
  _DWORD *v8; // esi
  int v9; // ecx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  int v13; // edi
  int v14; // eax
  int v15; // edi
  _DWORD *v16; // esi
  int v17; // edx
  int v18; // eax
  int i; // edi
  PageDesc *v20; // ecx
  int v21; // ecx
  unsigned int v22; // eax
  unsigned int v23; // edx
  int v24; // eax
  bool v25; // zf
  int v26; // eax
  Err *v27; // ecx
  Database *v28; // esi
  unsigned int v29; // eax
  char *v30; // ecx
  int v31; // eax
  unsigned int v32; // eax
  int v33; // ecx
  int v34; // edi
  int v35; // eax
  unsigned __int16 *v36; // [esp+24h] [ebp-28h]
  unsigned __int16 *v37; // [esp+24h] [ebp-28h]
  _DWORD *Block; // [esp+28h] [ebp-24h]
  int v39; // [esp+2Ch] [ebp-20h]
  int v41; // [esp+34h] [ebp-18h]
  unsigned int v42; // [esp+38h] [ebp-14h] BYREF
  _DWORD Buffer[4]; // [esp+3Ch] [ebp-10h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 112);
  *((_DWORD *)this + 44) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  v4 = *((_DWORD *)this + 96);
  v39 = v4;
  if ( !v4 )
  {
    LeaveCriticalSection(v3);
    return;
  }
  v5 = operator new[](saturated_mul(8u, v4));
  v6 = 0;
  v7 = 0;
  v41 = 0;
  v8 = v5;
  Block = v5;
  if ( v39 > 0 )
  {
    do
    {
      v9 = *(_DWORD *)(*((_DWORD *)this + 94) + 4 * v6);
      if ( (*(_BYTE *)(v9 + 28) & 8) != 0 )
      {
        v8[2 * v7] = v9;
        if ( *(_BYTE *)(v9 + 80) )
          v10 = 0;
        else
          v10 = (*(_DWORD *)(v9 + 28) >> 4) & 0xF;
        v8[2 * v7++ + 1] = *(_DWORD *)(v9 + 12) + (v10 << 24);
      }
      ++v6;
    }
    while ( v6 < v39 );
    v41 = v7;
  }
  v11 = v7 / 2;
  Buffer[0] = v11;
  if ( v11 > 0 )
  {
    v12 = v41;
    do
    {
      v13 = v11;
      v42 = v11;
      if ( v11 < v12 )
      {
        do
        {
          v14 = v13 - v11;
          if ( v13 - v11 >= 0 )
          {
            do
            {
              v36 = (unsigned __int16 *)v8[2 * v14 + 1];
              if ( (unsigned int)v36 <= v8[2 * v11 + 1 + 2 * v14] )
                break;
              v15 = v8[2 * v14];
              v16 = &v8[2 * v14 + 2 * v11];
              v17 = v16[1];
              Block[2 * v14] = *v16;
              v11 = Buffer[0];
              Block[2 * v14 + 1] = v17;
              v14 -= v11;
              v16[1] = v36;
              *v16 = v15;
              v8 = Block;
            }
            while ( v14 >= 0 );
            v13 = v42;
          }
          v12 = v41;
          v42 = ++v13;
        }
        while ( v13 < v41 );
      }
      v11 = (unsigned int)v11 >> 1;
      Buffer[0] = v11;
    }
    while ( v11 );
  }
  v18 = v41;
  for ( i = 0; i < v41; ++i )
  {
    v20 = (PageDesc *)v8[2 * i];
    if ( !*((_BYTE *)v20 + 80) )
      break;
    PageDesc::Write(v20, (struct Err *)a2);
    v18 = v41;
    if ( (*(_BYTE *)a2 & 8) != 0 )
      goto LABEL_50;
  }
  if ( (*(_BYTE *)a2 & 8) != 0 || (v21 = i, i >= v18) )
  {
LABEL_50:
    v28 = this;
LABEL_51:
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v33 = 0;
      for ( Buffer[0] = 0; v33 < v39; Buffer[0] = v33 )
      {
        v34 = *(_DWORD *)(*((_DWORD *)v28 + 94) + 4 * v33);
        PageDesc::Unlock((PageDesc *)v34, (struct Err *)a2);
        *(_BYTE *)(v34 + 82) &= ~2u;
        if ( !*(_WORD *)(v34 + 76)
          && (*(_DWORD *)(v34 + 28) & 8) == 0
          && !*(_BYTE *)(v34 + 81)
          && !*(_WORD *)(v34 + 78)
          && !*(_DWORD *)(v34 + 24) )
        {
          v35 = *(_DWORD *)(v34 + 28) & 7;
          if ( v35 == 3 || v35 == 5 )
          {
            (**(void (__thiscall ***)(int, int))v34)(v34, 1);
            v28 = this;
          }
        }
        v33 = Buffer[0] + 1;
      }
      *((_DWORD *)v28 + 96) = 0;
      Database::ReclaimPDSpace(v28);
      if ( v41 > 0 )
        *((_DWORD *)v28 + 46) = GetTickCount();
    }
    goto LABEL_64;
  }
  v22 = 0;
  do
  {
    v23 = v22;
    if ( v22 >= 2 )
      break;
    v24 = v8[2 * v21++];
    v25 = (*(_BYTE *)(v24 + 28) & 8) == 0;
    v22 = v23 + 1;
    if ( v25 )
      v22 = v23;
  }
  while ( v21 < v41 );
  v42 = v22;
  if ( v22 > 1 && *((_DWORD *)this + 17) != 1 )
  {
    v26 = *((_DWORD *)this + 27);
    if ( *((_WORD *)this + v26 + 206) < 0x100u )
    {
      v27 = (Err *)*((_DWORD *)this + 2);
      v37 = (unsigned __int16 *)v27;
      if ( ((unsigned int)*a2 & 0xFFFFFFFE) != 0 )
      {
        if ( a2[3] )
          operator delete[](a2[3]);
        if ( a2[4] )
          operator delete[](a2[4]);
      }
      *a2 = (void *)8;
      a2[1] = (void *)-1206;
      a2[2] = (void *)-8188;
      Err::CopyString(v27, (wchar_t *)a2 + 6, v37);
      a2[4] = 0;
      Buffer[3] = -1;
    }
    else
    {
      LOWORD(Buffer[0]) = 0;
      File::Write((Database *)((char *)this + 4), 2 * v26 + 1536, Buffer, 2u, (struct Err *)a2);
    }
  }
  do
    PageDesc::Write((PageDesc *)v8[2 * i++], (struct Err *)a2);
  while ( i < v41 );
  v28 = this;
  if ( !v42 )
    goto LABEL_51;
  if ( (*(_BYTE *)a2 & 8) == 0 )
  {
    if ( *((_DWORD *)this + 17) != 1 )
    {
      v29 = *((_DWORD *)this + 27);
      if ( v29 < 0x100 )
      {
        v30 = (char *)this + 2 * v29;
        v31 = *((unsigned __int16 *)v30 + 206);
        if ( v31 != 1 )
        {
          v32 = v31 + 1;
          if ( v32 > 0xFFFF )
            LOWORD(v32) = 256;
          *((_WORD *)v30 + 206) = v32;
          LOWORD(v42) = v32;
          File::Write((Database *)((char *)this + 4), 2 * *((_DWORD *)this + 27) + 1536, &v42, 2u, (struct Err *)a2);
        }
      }
    }
    goto LABEL_51;
  }
LABEL_64:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v28 + 112));
  operator delete[](Block);
}

```

## disassembly

```asm
0x10023bb0  mov     edi, edi
0x10023bb2  push    ebp
0x10023bb3  mov     ebp, esp
0x10023bb5  push    0FFFFFFFFh
0x10023bb7  push    offset ?CommitPDs@Database@@QAEXAAVTransaction@@W4TransactionType@@AAVErr@@@Z_SEH
0x10023bbc  mov     eax, large fs:0
0x10023bc2  push    eax
0x10023bc3  sub     esp, 30h
0x10023bc6  push    ebx
0x10023bc7  push    esi
0x10023bc8  push    edi
0x10023bc9  mov     eax, ___security_cookie
0x10023bce  xor     eax, ebp
0x10023bd0  push    eax; unsigned int
0x10023bd1  lea     eax, [ebp+var_C]
0x10023bd4  mov     large fs:0, eax
0x10023bda  mov     edi, ecx
0x10023bdc  mov     [ebp+var_1C], edi
0x10023bdf  lea     ebx, [edi+70h]
0x10023be2  mov     dword ptr [edi+0B0h], 0
0x10023bec  push    ebx; lpCriticalSection
0x10023bed  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10023bf3  mov     eax, [edi+180h]
0x10023bf9  mov     [ebp+var_20], eax
0x10023bfc  test    eax, eax
0x10023bfe  jnz     short loc_10023C1B
0x10023c00  push    ebx; lpCriticalSection
0x10023c01  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10023c07  mov     ecx, [ebp+var_C]
0x10023c0a  mov     large fs:0, ecx
0x10023c11  pop     ecx
0x10023c12  pop     edi
0x10023c13  pop     esi
0x10023c14  pop     ebx
0x10023c15  mov     esp, ebp
0x10023c17  pop     ebp
0x10023c18  retn    4
0x10023c1b  mov     ecx, 8
0x10023c20  mul     ecx
0x10023c22  mov     ecx, 0FFFFFFFFh
0x10023c27  cmovb   eax, ecx
0x10023c2a  push    eax; unsigned int
0x10023c2b  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10023c30  xor     edx, edx
0x10023c32  xor     ebx, ebx
0x10023c34  add     esp, 4
0x10023c37  mov     [ebp+var_18], ebx
0x10023c3a  mov     esi, eax
0x10023c3c  mov     [ebp+Block], esi
0x10023c3f  cmp     [ebp+var_20], edx
0x10023c42  jle     short loc_10023C89
0x10023c44  nop     dword ptr [eax+00h]
0x10023c48  nop     dword ptr [eax+eax+00000000h]
0x10023c50  mov     eax, [edi+178h]
0x10023c56  mov     ecx, [eax+edx*4]
0x10023c59  test    byte ptr [ecx+1Ch], 8
0x10023c5d  jz      short loc_10023C80
0x10023c5f  mov     [esi+ebx*8], ecx
0x10023c62  cmp     byte ptr [ecx+50h], 0
0x10023c66  jz      short loc_10023C6C
0x10023c68  xor     eax, eax
0x10023c6a  jmp     short loc_10023C75
0x10023c6c  mov     eax, [ecx+1Ch]
0x10023c6f  shr     eax, 4
0x10023c72  and     eax, 0Fh
0x10023c75  shl     eax, 18h
0x10023c78  add     eax, [ecx+0Ch]
0x10023c7b  mov     [esi+ebx*8+4], eax
0x10023c7f  inc     ebx
0x10023c80  inc     edx
0x10023c81  cmp     edx, [ebp+var_20]
0x10023c84  jl      short loc_10023C50
0x10023c86  mov     [ebp+var_18], ebx
0x10023c89  mov     eax, ebx
0x10023c8b  cdq
0x10023c8c  sub     eax, edx
0x10023c8e  mov     ebx, eax
0x10023c90  sar     ebx, 1
0x10023c92  mov     [ebp+Buffer], ebx
0x10023c95  test    ebx, ebx
0x10023c97  jle     short loc_10023D07
0x10023c99  mov     eax, [ebp+var_18]
0x10023c9c  nop     dword ptr [eax+00h]
0x10023ca0  mov     edi, ebx
0x10023ca2  mov     [ebp+var_14], edi
0x10023ca5  cmp     ebx, eax
0x10023ca7  jge     short loc_10023D00
0x10023ca9  nop     dword ptr [eax+00000000h]
0x10023cb0  mov     eax, edi
0x10023cb2  sub     eax, ebx
0x10023cb4  js      short loc_10023CF5
0x10023cb6  mov     edx, [esi+eax*8+4]
0x10023cba  lea     ecx, [esi+ebx*8]
0x10023cbd  mov     [ebp+var_28], edx
0x10023cc0  cmp     edx, [ecx+eax*8+4]
0x10023cc4  jbe     short loc_10023CF2
0x10023cc6  mov     edi, [esi+eax*8]
0x10023cc9  lea     ecx, [eax+ebx]
0x10023ccc  mov     ebx, [ebp+Block]
0x10023ccf  lea     esi, [esi+ecx*8]
0x10023cd2  mov     ecx, [esi]
0x10023cd4  mov     edx, [esi+4]
0x10023cd7  mov     [ebx+eax*8], ecx
0x10023cda  mov     ecx, ebx
0x10023cdc  mov     ebx, [ebp+Buffer]
0x10023cdf  mov     [ecx+eax*8+4], edx
0x10023ce3  sub     eax, ebx
0x10023ce5  mov     ecx, [ebp+var_28]
0x10023ce8  mov     [esi+4], ecx
0x10023ceb  mov     [esi], edi
0x10023ced  mov     esi, [ebp+Block]
0x10023cf0  jns     short loc_10023CB6
0x10023cf2  mov     edi, [ebp+var_14]
0x10023cf5  mov     eax, [ebp+var_18]
0x10023cf8  inc     edi
0x10023cf9  mov     [ebp+var_14], edi
0x10023cfc  cmp     edi, eax
0x10023cfe  jl      short loc_10023CB0
0x10023d00  shr     ebx, 1
0x10023d02  mov     [ebp+Buffer], ebx
0x10023d05  jnz     short loc_10023CA0
0x10023d07  mov     eax, [ebp+var_18]
0x10023d0a  xor     edi, edi
0x10023d0c  mov     ebx, [ebp+arg_0]
0x10023d0f  test    eax, eax
0x10023d11  jle     short loc_10023D33
0x10023d13  mov     ecx, [esi+edi*8]; this
0x10023d16  cmp     byte ptr [ecx+50h], 0
0x10023d1a  jz      short loc_10023D33
0x10023d1c  push    ebx; struct Err *
0x10023d1d  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10023d22  test    byte ptr [ebx], 8
0x10023d25  mov     eax, [ebp+var_18]
0x10023d28  jnz     loc_10023E8C
0x10023d2e  inc     edi
0x10023d2f  cmp     edi, eax
0x10023d31  jl      short loc_10023D13
0x10023d33  test    byte ptr [ebx], 8
0x10023d36  jnz     loc_10023E8C
0x10023d3c  mov     ecx, edi
0x10023d3e  cmp     edi, eax
0x10023d40  jge     loc_10023E8C
0x10023d46  xor     eax, eax
0x10023d48  mov     edx, eax
0x10023d4a  cmp     eax, 2
0x10023d4d  jnb     short loc_10023D62
0x10023d4f  mov     eax, [esi+ecx*8]
0x10023d52  inc     ecx
0x10023d53  test    byte ptr [eax+1Ch], 8
0x10023d57  lea     eax, [edx+1]
0x10023d5a  cmovz   eax, edx
0x10023d5d  cmp     ecx, [ebp+var_18]
0x10023d60  jl      short loc_10023D48
0x10023d62  mov     [ebp+var_14], eax
0x10023d65  mov     edx, 100h
0x10023d6a  cmp     eax, 1
0x10023d6d  jbe     loc_10023E10
0x10023d73  mov     ecx, [ebp+var_1C]
0x10023d76  cmp     dword ptr [ecx+44h], 1
0x10023d7a  jz      loc_10023E10
0x10023d80  mov     eax, [ecx+6Ch]
0x10023d83  cmp     [ecx+eax*2+19Ch], dx
0x10023d8b  jb      short loc_10023DAC
0x10023d8d  xor     edx, edx
0x10023d8f  lea     eax, ds:600h[eax*2]
0x10023d96  push    ebx; struct Err *
0x10023d97  mov     word ptr [ebp+Buffer], dx
0x10023d9b  add     ecx, 4; this
0x10023d9e  push    2; nNumberOfBytesToWrite
0x10023da0  lea     edx, [ebp+Buffer]
0x10023da3  push    edx; lpBuffer
0x10023da4  push    eax; lDistanceToMove
0x10023da5  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x10023daa  jmp     short loc_10023E10
0x10023dac  test    dword ptr [ebx], 0FFFFFFFEh
0x10023db2  mov     ecx, [ecx+8]
0x10023db5  mov     [ebp+var_28], ecx
0x10023db8  jz      short loc_10023DDA
0x10023dba  mov     eax, [ebx+0Ch]
0x10023dbd  test    eax, eax
0x10023dbf  jz      short loc_10023DCA
0x10023dc1  push    eax; Block
0x10023dc2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023dc7  add     esp, 4
0x10023dca  mov     eax, [ebx+10h]
0x10023dcd  test    eax, eax
0x10023dcf  jz      short loc_10023DDA
0x10023dd1  push    eax; Block
0x10023dd2  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023dd7  add     esp, 4
0x10023dda  push    [ebp+var_28]; unsigned __int16 *
0x10023ddd  lea     eax, [ebx+0Ch]
0x10023de0  mov     dword ptr [ebx], 8
0x10023de6  push    eax; unsigned __int16 **
0x10023de7  mov     dword ptr [ebx+4], 0FFFFFB4Ah
0x10023dee  mov     dword ptr [ebx+8], 0FFFFE004h
0x10023df5  call    ?CopyString@Err@@AAEXAAPAGPBG@Z; Err::CopyString(ushort * &,ushort const *)
0x10023dfa  mov     dword ptr [ebx+10h], 0
0x10023e01  mov     [ebp+var_4], 0FFFFFFFFh
0x10023e08  nop     dword ptr [eax+eax+00000000h]
0x10023e10  mov     ecx, [esi+edi*8]; this
0x10023e13  push    ebx; struct Err *
0x10023e14  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10023e19  inc     edi
0x10023e1a  cmp     edi, [ebp+var_18]
0x10023e1d  jl      short loc_10023E10
0x10023e1f  cmp     [ebp+var_14], 0
0x10023e23  mov     esi, [ebp+var_1C]
0x10023e26  jz      short loc_10023E8F
0x10023e28  test    byte ptr [ebx], 8
0x10023e2b  jnz     loc_10023F29
0x10023e31  cmp     dword ptr [esi+44h], 1
0x10023e35  jz      short loc_10023E8F
0x10023e37  mov     eax, [esi+6Ch]
0x10023e3a  cmp     eax, 100h
0x10023e3f  jnb     short loc_10023E8F
0x10023e41  lea     ecx, [esi+eax*2]
0x10023e44  movzx   eax, word ptr [ecx+19Ch]
0x10023e4b  mov     edx, eax
0x10023e4d  cmp     eax, 1
0x10023e50  jz      short loc_10023E8F
0x10023e52  lea     eax, [edx+1]
0x10023e55  mov     edx, 100h
0x10023e5a  cmp     eax, 0FFFFh
0x10023e5f  push    ebx; struct Err *
0x10023e60  cmova   eax, edx
0x10023e63  movzx   eax, ax
0x10023e66  mov     [ecx+19Ch], ax
0x10023e6d  lea     ecx, [esi+4]; this
0x10023e70  mov     word ptr [ebp+var_14], ax
0x10023e74  lea     eax, [ebp+var_14]
0x10023e77  push    2; nNumberOfBytesToWrite
0x10023e79  push    eax; lpBuffer
0x10023e7a  mov     eax, [esi+6Ch]
0x10023e7d  lea     eax, ds:600h[eax*2]
0x10023e84  push    eax; lDistanceToMove
0x10023e85  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x10023e8a  jmp     short loc_10023E8F
0x10023e8c  mov     esi, [ebp+var_1C]
0x10023e8f  test    byte ptr [ebx], 8
0x10023e92  jnz     loc_10023F29
0x10023e98  xor     ecx, ecx
0x10023e9a  mov     [ebp+Buffer], ecx
0x10023e9d  cmp     [ebp+var_20], ecx
0x10023ea0  jle     short loc_10023F06
0x10023ea2  mov     eax, [esi+178h]
0x10023ea8  push    ebx; struct Err *
0x10023ea9  mov     edi, [eax+ecx*4]
0x10023eac  mov     ecx, edi; this
0x10023eae  call    ?Unlock@PageDesc@@QAEIAAVErr@@@Z; PageDesc::Unlock(Err &)
0x10023eb3  and     byte ptr [edi+52h], 0FDh
0x10023eb7  cmp     word ptr [edi+4Ch], 0
0x10023ebc  jnz     short loc_10023EFA
0x10023ebe  mov     eax, [edi+1Ch]
0x10023ec1  test    al, 8
0x10023ec3  jnz     short loc_10023EFA
0x10023ec5  cmp     byte ptr [edi+51h], 0
0x10023ec9  jnz     short loc_10023EFA
0x10023ecb  cmp     word ptr [edi+4Eh], 0
0x10023ed0  jnz     short loc_10023EFA
0x10023ed2  cmp     dword ptr [edi+18h], 0
0x10023ed6  jnz     short loc_10023EFA
0x10023ed8  and     eax, 7
0x10023edb  cmp     eax, 3
0x10023ede  jz      short loc_10023EE5
0x10023ee0  cmp     eax, 5
0x10023ee3  jnz     short loc_10023EFA
0x10023ee5  mov     eax, [edi]
0x10023ee7  push    1; void *
0x10023ee9  mov     esi, [eax]
0x10023eeb  mov     ecx, esi
0x10023eed  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x10023ef3  mov     ecx, edi
0x10023ef5  call    esi
0x10023ef7  mov     esi, [ebp+var_1C]
0x10023efa  mov     ecx, [ebp+Buffer]
0x10023efd  inc     ecx
0x10023efe  mov     [ebp+Buffer], ecx
0x10023f01  cmp     ecx, [ebp+var_20]
0x10023f04  jl      short loc_10023EA2
0x10023f06  mov     ecx, esi; this
0x10023f08  mov     dword ptr [esi+180h], 0
0x10023f12  call    ?ReclaimPDSpace@Database@@QAEXXZ; Database::ReclaimPDSpace(void)
0x10023f17  cmp     [ebp+var_18], 0
0x10023f1b  jle     short loc_10023F29
0x10023f1d  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10023f23  mov     [esi+0B8h], eax
0x10023f29  lea     eax, [esi+70h]
0x10023f2c  push    eax; lpCriticalSection
0x10023f2d  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10023f33  push    [ebp+Block]; Block
0x10023f36  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10023f3b  add     esp, 4
0x10023f3e  mov     ecx, [ebp+var_C]
0x10023f41  mov     large fs:0, ecx
0x10023f48  pop     ecx
0x10023f49  pop     edi
0x10023f4a  pop     esi
0x10023f4b  pop     ebx
0x10023f4c  mov     esp, ebp
  ... truncated ...
```
