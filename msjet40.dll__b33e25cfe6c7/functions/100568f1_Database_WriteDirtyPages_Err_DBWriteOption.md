# Database::WriteDirtyPages(Err &,DBWriteOption)

- ea: `0x100568f1`
- end: `0x10056c46`
- name: `?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z`
- size: `853`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10048fb0`
- `0x1005313d`
- `0x100570f9`
- `0x10061460`

## callees

- `0x10051197`
- `0x100568f1`
- `0x10057410`
- `0x1006b9f1`
- `0x10074bb1`
- `0x10074be5`
- `0x100762b4`
- `0x1007677e`
- `0x10077438`
- `0x10123af8`
- `0x10123b03`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10056c29`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10056c29`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100569ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056c39`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x100569ee`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056c39`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056913`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056913`

## pseudocode

```c
void __thiscall Database::WriteDirtyPages(unsigned int this, struct Err *a2, int a3)
{
  _DWORD *v3; // edi
  int v4; // ebx
  signed int v5; // edx
  unsigned int v6; // esi
  char *v7; // eax
  int v8; // ecx
  int v9; // edx
  _DWORD *v10; // ebx
  int v11; // edx
  int v12; // eax
  struct _RTL_CRITICAL_SECTION *v13; // eax
  unsigned int v14; // ebx
  signed int i; // edx
  unsigned int v16; // eax
  int v17; // esi
  unsigned int v18; // edx
  int v19; // ecx
  bool v20; // sf
  int v21; // esi
  PageDesc *v22; // eax
  int v23; // edx
  unsigned int v24; // esi
  unsigned int v25; // ebx
  int v26; // eax
  bool v27; // cc
  int v28; // esi
  unsigned int v29; // esi
  int v30; // eax
  __int16 v31; // dx
  int v32; // ecx
  PageDesc *v33; // esi
  struct Database *v34; // [esp+0h] [ebp-3Ch]
  struct Err *v35; // [esp+4h] [ebp-38h]
  unsigned int v36; // [esp+10h] [ebp-2Ch]
  int v37; // [esp+14h] [ebp-28h]
  int v38; // [esp+14h] [ebp-28h]
  int v39; // [esp+14h] [ebp-28h]
  unsigned int v40; // [esp+18h] [ebp-24h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [esp+1Ch] [ebp-20h]
  LPCRITICAL_SECTION lpCriticalSectiona; // [esp+1Ch] [ebp-20h]
  unsigned int v43; // [esp+20h] [ebp-1Ch]
  int v44; // [esp+24h] [ebp-18h]
  unsigned int v45; // [esp+24h] [ebp-18h]
  int v46; // [esp+28h] [ebp-14h]
  char *Block; // [esp+30h] [ebp-Ch]
  int v49; // [esp+34h] [ebp-8h]
  char Buffer; // [esp+3Bh] [ebp-1h] BYREF

  v3 = (_DWORD *)this;
  v4 = 0;
  v49 = 0;
  *(_DWORD *)(this + 172) = 0;
  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)(this + 104);
  EnterCriticalSection((LPCRITICAL_SECTION)(this + 104));
  v5 = v3[99];
  v46 = v5;
  if ( v5 )
  {
    if ( !a3 )
    {
      v6 = 0;
      v7 = (char *)operator new[](saturated_mul(8u, v5));
      v8 = 0;
      v9 = 0;
      v49 = 0;
      v10 = v7;
      v44 = 0;
      Block = v7;
      if ( v46 > 0 )
      {
        do
        {
          v11 = *(_DWORD *)(v3[97] + 4 * v9);
          if ( !v11 )
          {
            Err::SetError(a2, -1206, v8);
            v13 = lpCriticalSection;
            goto LABEL_64;
          }
          if ( (*(_BYTE *)(v11 + 28) & 8) != 0 )
          {
            if ( *(_BYTE *)(v11 + 82) && *(_DWORD *)(v11 + 12) > v6 )
              v6 = *(_DWORD *)(v11 + 12);
            v10[2 * v8] = v11;
            if ( *(_BYTE *)(v11 + 82) )
              v12 = 0;
            else
              v12 = (*(_DWORD *)(v11 + 28) >> 4) & 0xF;
            v10[2 * v8++ + 1] = *(_DWORD *)(v11 + 12) + (v12 << 24);
            v49 = v8;
          }
          v9 = v44 + 1;
          v44 = v9;
        }
        while ( v9 < v46 );
        if ( !v6 )
          goto LABEL_19;
        Buffer = 0;
        File::Write((File *)(v3 + 1), (v6 << 12) + 4095, &Buffer, 1u, a2);
        if ( (*(_BYTE *)a2 & 8) != 0 )
        {
          LeaveCriticalSection(lpCriticalSection);
          operator delete[](Block);
          return;
        }
        v8 = v49;
      }
LABEL_19:
      v14 = v8 / 2;
      v37 = v8 / 2;
      if ( v8 / 2 > 0 )
      {
        do
        {
          v40 = v14;
          for ( i = v14; i < v8; v40 = i )
          {
            v16 = i - v14;
            v45 = i - v14;
            if ( (int)(i - v14) >= 0 )
            {
              do
              {
                lpCriticalSectiona = (LPCRITICAL_SECTION)(8 * v16);
                v36 = *(_DWORD *)&Block[8 * v16 + 4];
                if ( v36 <= *(_DWORD *)&Block[8 * v16 + 4 + 8 * v14] )
                  break;
                v17 = *(_DWORD *)&Block[8 * v16];
                v18 = v14 + v45;
                v19 = *(_DWORD *)&Block[8 * v14 + 4 + 8 * v45];
                *(_DWORD *)&Block[(_DWORD)lpCriticalSectiona] = *(_DWORD *)&Block[8 * v14 + 8 * v45];
                v14 = v37;
                *(_DWORD *)&Block[(_DWORD)lpCriticalSectiona + 4] = v19;
                *(_DWORD *)&Block[8 * v18 + 4] = v36;
                v16 = v45 - v37;
                v20 = (int)(v45 - v37) < 0;
                *(_DWORD *)&Block[8 * v18] = v17;
                v45 -= v37;
              }
              while ( !v20 );
              v8 = v49;
              i = v40;
            }
            ++i;
          }
          v14 >>= 1;
          v37 = v14;
        }
        while ( v14 );
        v3 = (_DWORD *)this;
      }
      v21 = 0;
      v38 = 0;
      if ( v8 > 0 )
      {
        do
        {
          v22 = *(PageDesc **)&Block[8 * v21];
          if ( !*((_BYTE *)v22 + 82) )
            break;
          PageDesc::Write(v22, a2);
          v8 = v49;
          if ( (*(_BYTE *)a2 & 8) != 0 )
            break;
          ++v21;
        }
        while ( v21 < v49 );
        v3 = (_DWORD *)this;
        v38 = v21;
      }
      if ( (*(_BYTE *)a2 & 8) != 0 || (v23 = v21, v21 >= v8) )
      {
        v4 = v49;
      }
      else
      {
        v24 = 0;
        do
        {
          v25 = v24;
          if ( v24 >= 2 )
            break;
          v26 = *(_DWORD *)&Block[8 * v23];
          ++v24;
          ++v23;
          if ( (*(_BYTE *)(v26 + 28) & 8) == 0 )
            v24 = v25;
        }
        while ( v23 < v8 );
        v43 = v24;
        v27 = v24 <= 1;
        v28 = v38;
        if ( !v27 && *(_DWORD *)(this + 72) != 1 )
        {
          if ( *(_WORD *)(this + 2 * *(_DWORD *)(this + 100) + 424) < 0x100u )
            Err::SetError(a2, -1206, -8188, *(_DWORD *)(this + 8), 0, *(_DWORD *)(this + 100));
          else
            DBHeaderPage::ChangeUserState(this, a2, v34, v35);
        }
        v4 = v49;
        do
          PageDesc::Write(*(PageDesc **)&Block[8 * v28++], a2);
        while ( v28 < v49 );
        v3 = (_DWORD *)this;
        if ( v43 )
        {
          if ( (*(_BYTE *)a2 & 8) == 0 && *(_DWORD *)(this + 72) != 1 )
          {
            v29 = *(_DWORD *)(this + 100);
            if ( v29 < 0x100 )
            {
              v30 = *(unsigned __int16 *)(this + 2 * v29 + 424);
              if ( (_WORD)v30 != 1 )
              {
                v31 = v30 + 1;
                if ( (unsigned int)(v30 + 1) > 0xFFFF )
                  v31 = 256;
                *(_WORD *)(this + 2 * v29 + 424) = v31;
                DBHeaderPage::ChangeUserState(this, a2, v34, v35);
              }
            }
          }
        }
      }
      operator delete[](Block);
      v5 = v46;
    }
    if ( (*(_BYTE *)a2 & 8) == 0 )
    {
      v32 = 0;
      v39 = 0;
      if ( v5 > 0 )
      {
        do
        {
          v33 = *(PageDesc **)(v3[97] + 4 * v32);
          PageDesc::Unlock(v33, a2);
          *((_BYTE *)v33 + 88) &= ~2u;
          PageDesc::Free(v33);
          v32 = v39 + 1;
          v39 = v32;
        }
        while ( v32 < v46 );
        v4 = v49;
      }
      v3[99] = 0;
      Database::ReclaimPDSpace((Database *)v3);
      if ( v4 > 0 )
        v3[45] = GetTickCount();
    }
  }
  v13 = (struct _RTL_CRITICAL_SECTION *)(v3 + 26);
LABEL_64:
  LeaveCriticalSection(v13);
}

```

## disassembly

```asm
0x100568f1  mov     edi, edi
0x100568f3  push    ebp
0x100568f4  mov     ebp, esp
0x100568f6  sub     esp, 30h
0x100568f9  push    ebx
0x100568fa  push    esi; struct Err *
0x100568fb  push    edi; struct Database *
0x100568fc  mov     edi, ecx
0x100568fe  xor     ebx, ebx
0x10056900  mov     [ebp+var_10], edi
0x10056903  mov     [ebp+var_8], ebx
0x10056906  lea     eax, [edi+68h]
0x10056909  mov     [edi+0ACh], ebx
0x1005690f  push    eax; lpCriticalSection
0x10056910  mov     [ebp+lpCriticalSection], eax
0x10056913  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056919  mov     edx, [edi+18Ch]
0x1005691f  mov     [ebp+var_14], edx
0x10056922  test    edx, edx
0x10056924  jz      loc_10056C35
0x1005692a  push    8
0x1005692c  pop     ecx
0x1005692d  cmp     [ebp+arg_4], ebx
0x10056930  jnz     loc_10056BD7
0x10056936  xor     eax, eax
0x10056938  xor     esi, esi
0x1005693a  mov     [ebp+var_1C], eax
0x1005693d  mov     eax, edx
0x1005693f  mul     ecx
0x10056941  push    0FFFFFFFFh
0x10056943  pop     ecx
0x10056944  cmovb   eax, ecx
0x10056947  push    eax; unsigned int
0x10056948  call    ??_U@YAPAXI@Z; operator new[](uint)
0x1005694d  pop     ecx
0x1005694e  xor     ecx, ecx
0x10056950  mov     [ebp+var_30], 1
0x10056957  xor     edx, edx
0x10056959  mov     [ebp+var_8], ecx
0x1005695c  mov     ebx, eax
0x1005695e  mov     [ebp+var_18], edx
0x10056961  mov     [ebp+Block], ebx
0x10056964  cmp     [ebp+var_14], ecx
0x10056967  jle     loc_10056A1B
0x1005696d  mov     eax, [edi+184h]
0x10056973  mov     edx, [eax+edx*4]
0x10056976  test    edx, edx
0x10056978  jz      loc_10056A02
0x1005697e  test    byte ptr [edx+1Ch], 8
0x10056982  jz      short loc_100569B5
0x10056984  cmp     byte ptr [edx+52h], 0
0x10056988  jz      short loc_10056991
0x1005698a  cmp     [edx+0Ch], esi
0x1005698d  cmova   esi, [edx+0Ch]
0x10056991  mov     [ebx+ecx*8], edx
0x10056994  cmp     byte ptr [edx+52h], 0
0x10056998  jz      short loc_1005699E
0x1005699a  xor     eax, eax
0x1005699c  jmp     short loc_100569A7
0x1005699e  mov     eax, [edx+1Ch]
0x100569a1  shr     eax, 4
0x100569a4  and     eax, 0Fh
0x100569a7  shl     eax, 18h
0x100569aa  add     eax, [edx+0Ch]
0x100569ad  mov     [ebx+ecx*8+4], eax
0x100569b1  inc     ecx
0x100569b2  mov     [ebp+var_8], ecx
0x100569b5  mov     edx, [ebp+var_18]
0x100569b8  inc     edx
0x100569b9  mov     [ebp+var_18], edx
0x100569bc  cmp     edx, [ebp+var_14]
0x100569bf  jl      short loc_1005696D
0x100569c1  test    esi, esi
0x100569c3  jz      short loc_10056A1B
0x100569c5  mov     ebx, [ebp+arg_0]
0x100569c8  lea     eax, [ebp+Buffer]
0x100569cb  push    ebx; struct Err *
0x100569cc  push    1; nNumberOfBytesToWrite
0x100569ce  shl     esi, 0Ch
0x100569d1  lea     ecx, [edi+4]; this
0x100569d4  push    eax; lpBuffer
0x100569d5  add     esi, 0FFFh
0x100569db  mov     [ebp+Buffer], 0
0x100569df  push    esi; lDistanceToMove
0x100569e0  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x100569e5  test    byte ptr [ebx], 8
0x100569e8  jz      short loc_10056A18
0x100569ea  mov     eax, [ebp+lpCriticalSection]
0x100569ed  push    eax; lpCriticalSection
0x100569ee  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x100569f4  push    [ebp+Block]; Block
0x100569f7  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x100569fc  pop     ecx
0x100569fd  jmp     loc_10056C3F
0x10056a02  push    ecx
0x10056a03  mov     ecx, [ebp+arg_0]
0x10056a06  push    0FFFFFB4Ah
0x10056a0b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10056a10  mov     eax, [ebp+lpCriticalSection]
0x10056a13  jmp     loc_10056C38
0x10056a18  mov     ecx, [ebp+var_8]
0x10056a1b  mov     eax, ecx
0x10056a1d  cdq
0x10056a1e  sub     eax, edx
0x10056a20  mov     ebx, eax
0x10056a22  sar     ebx, 1
0x10056a24  mov     [ebp+var_28], ebx
0x10056a27  test    ebx, ebx
0x10056a29  jle     short loc_10056AA2
0x10056a2b  mov     edi, [ebp+Block]
0x10056a2e  mov     [ebp+var_24], ebx
0x10056a31  mov     edx, ebx
0x10056a33  cmp     ebx, ecx
0x10056a35  jge     short loc_10056A98
0x10056a37  mov     eax, edx
0x10056a39  sub     eax, ebx
0x10056a3b  mov     [ebp+var_18], eax
0x10056a3e  js      short loc_10056A90
0x10056a40  mov     ecx, eax
0x10056a42  shl     ecx, 3
0x10056a45  mov     [ebp+lpCriticalSection], ecx
0x10056a48  mov     edx, [ecx+edi+4]
0x10056a4c  lea     eax, [ecx+ebx*8]
0x10056a4f  mov     [ebp+var_2C], edx
0x10056a52  cmp     edx, [eax+edi+4]
0x10056a56  jbe     short loc_10056A8A
0x10056a58  mov     edx, [ebp+var_18]
0x10056a5b  mov     esi, [ecx+edi]
0x10056a5e  add     edx, ebx
0x10056a60  mov     ebx, [ebp+lpCriticalSection]
0x10056a63  mov     eax, [edi+edx*8]
0x10056a66  mov     ecx, [edi+edx*8+4]
0x10056a6a  mov     [ebx+edi], eax
0x10056a6d  mov     eax, ebx
0x10056a6f  mov     ebx, [ebp+var_28]
0x10056a72  mov     [eax+edi+4], ecx
0x10056a76  mov     eax, [ebp+var_2C]
0x10056a79  mov     [edi+edx*8+4], eax
0x10056a7d  mov     eax, [ebp+var_18]
0x10056a80  sub     eax, ebx
0x10056a82  mov     [edi+edx*8], esi
0x10056a85  mov     [ebp+var_18], eax
0x10056a88  jns     short loc_10056A40
0x10056a8a  mov     ecx, [ebp+var_8]
0x10056a8d  mov     edx, [ebp+var_24]
0x10056a90  inc     edx
0x10056a91  mov     [ebp+var_24], edx
0x10056a94  cmp     edx, ecx
0x10056a96  jl      short loc_10056A37
0x10056a98  shr     ebx, 1
0x10056a9a  mov     [ebp+var_28], ebx
0x10056a9d  jnz     short loc_10056A2E
0x10056a9f  mov     edi, [ebp+var_10]
0x10056aa2  xor     esi, esi
0x10056aa4  mov     [ebp+var_28], esi
0x10056aa7  test    ecx, ecx
0x10056aa9  jle     short loc_10056AD5
0x10056aab  mov     ebx, [ebp+arg_0]
0x10056aae  mov     edi, [ebp+Block]
0x10056ab1  mov     eax, [edi+esi*8]
0x10056ab4  cmp     byte ptr [eax+52h], 0
0x10056ab8  jz      short loc_10056ACF
0x10056aba  push    ebx; struct Err *
0x10056abb  mov     ecx, eax; this
0x10056abd  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10056ac2  test    byte ptr [ebx], 8
0x10056ac5  mov     ecx, [ebp+var_8]
0x10056ac8  jnz     short loc_10056ACF
0x10056aca  inc     esi
0x10056acb  cmp     esi, ecx
0x10056acd  jl      short loc_10056AB1
0x10056acf  mov     edi, [ebp+var_10]
0x10056ad2  mov     [ebp+var_28], esi
0x10056ad5  mov     eax, [ebp+arg_0]
0x10056ad8  test    byte ptr [eax], 8
0x10056adb  jnz     loc_10056BC5
0x10056ae1  mov     edx, esi
0x10056ae3  cmp     esi, ecx
0x10056ae5  jge     loc_10056BC5
0x10056aeb  mov     edi, [ebp+Block]
0x10056aee  mov     esi, [ebp+var_1C]
0x10056af1  mov     ebx, esi
0x10056af3  mov     eax, edx
0x10056af5  cmp     esi, 2
0x10056af8  jnb     short loc_10056B0C
0x10056afa  mov     eax, [edi+eax*8]
0x10056afd  lea     esi, [ebx+1]
0x10056b00  inc     edx
0x10056b01  test    byte ptr [eax+1Ch], 8
0x10056b05  cmovz   esi, ebx
0x10056b08  cmp     edx, ecx
0x10056b0a  jl      short loc_10056AF1
0x10056b0c  mov     edi, [ebp+var_10]
0x10056b0f  xor     ecx, ecx
0x10056b11  inc     ecx
0x10056b12  mov     [ebp+var_1C], esi
0x10056b15  cmp     esi, ecx
0x10056b17  mov     eax, 100h
0x10056b1c  mov     esi, [ebp+var_28]
0x10056b1f  jbe     short loc_10056B59
0x10056b21  cmp     [edi+48h], ecx
0x10056b24  jz      short loc_10056B59
0x10056b26  mov     ecx, [edi+64h]
0x10056b29  cmp     [edi+ecx*2+1A8h], ax
0x10056b31  jb      short loc_10056B41
0x10056b33  mov     eax, [ebp+arg_0]
0x10056b36  xor     edx, edx
0x10056b38  push    eax; struct Err *
0x10056b39  push    edi; unsigned int
0x10056b3a  call    ?ChangeUserState@DBHeaderPage@@SGXIIPAVDatabase@@AAVErr@@@Z; DBHeaderPage::ChangeUserState(uint,uint,Database *,Err &)
0x10056b3f  jmp     short loc_10056B59
0x10056b41  push    ecx
0x10056b42  mov     ecx, [ebp+arg_0]
0x10056b45  push    0
0x10056b47  push    dword ptr [edi+8]
0x10056b4a  push    0FFFFE004h
0x10056b4f  push    0FFFFFB4Ah
0x10056b54  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x10056b59  mov     ebx, [ebp+var_8]
0x10056b5c  mov     edi, [ebp+arg_0]
0x10056b5f  mov     eax, [ebp+Block]
0x10056b62  push    edi; struct Err *
0x10056b63  mov     ecx, [eax+esi*8]; this
0x10056b66  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10056b6b  inc     esi
0x10056b6c  cmp     esi, ebx
0x10056b6e  jl      short loc_10056B5F
0x10056b70  cmp     [ebp+var_1C], 0
0x10056b74  mov     edi, [ebp+var_10]
0x10056b77  jz      short loc_10056BC8
0x10056b79  mov     ecx, [ebp+arg_0]
0x10056b7c  test    byte ptr [ecx], 8
0x10056b7f  jnz     short loc_10056BC8
0x10056b81  cmp     dword ptr [edi+48h], 1
0x10056b85  jz      short loc_10056BC8
0x10056b87  mov     esi, [edi+64h]
0x10056b8a  cmp     esi, 100h
0x10056b90  jnb     short loc_10056BC8
0x10056b92  movzx   eax, word ptr [edi+esi*2+1A8h]
0x10056b9a  mov     edx, eax
0x10056b9c  cmp     ax, word ptr [ebp+var_30]
0x10056ba0  jz      short loc_10056BC8
0x10056ba2  inc     edx
0x10056ba3  mov     eax, 100h
0x10056ba8  cmp     edx, 0FFFFh
0x10056bae  push    ecx; struct Err *
0x10056baf  cmova   edx, eax
0x10056bb2  mov     [edi+esi*2+1A8h], dx
0x10056bba  mov     ecx, [edi+64h]
0x10056bbd  push    edi; unsigned int
0x10056bbe  call    ?ChangeUserState@DBHeaderPage@@SGXIIPAVDatabase@@AAVErr@@@Z; DBHeaderPage::ChangeUserState(uint,uint,Database *,Err &)
0x10056bc3  jmp     short loc_10056BC8
0x10056bc5  mov     ebx, [ebp+var_8]
0x10056bc8  push    [ebp+Block]; Block
0x10056bcb  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10056bd0  mov     edx, [ebp+var_14]
0x10056bd3  pop     ecx
0x10056bd4  push    8
0x10056bd6  pop     ecx
0x10056bd7  mov     eax, [ebp+arg_0]
0x10056bda  test    [eax], cl
0x10056bdc  jnz     short loc_10056C35
0x10056bde  xor     ecx, ecx
0x10056be0  mov     [ebp+var_28], ecx
0x10056be3  test    edx, edx
0x10056be5  jle     short loc_10056C14
0x10056be7  mov     ebx, eax
0x10056be9  mov     eax, [edi+184h]
0x10056bef  push    ebx; struct Err *
0x10056bf0  mov     esi, [eax+ecx*4]
0x10056bf3  mov     ecx, esi; this
0x10056bf5  call    ?Unlock@PageDesc@@QAEIAAVErr@@@Z; PageDesc::Unlock(Err &)
0x10056bfa  and     byte ptr [esi+58h], 0FDh
0x10056bfe  mov     ecx, esi; this
0x10056c00  call    ?Free@PageDesc@@QAEXXZ; PageDesc::Free(void)
0x10056c05  mov     ecx, [ebp+var_28]
0x10056c08  inc     ecx
0x10056c09  mov     [ebp+var_28], ecx
0x10056c0c  cmp     ecx, [ebp+var_14]
0x10056c0f  jl      short loc_10056BE9
0x10056c11  mov     ebx, [ebp+var_8]
0x10056c14  mov     ecx, edi; this
0x10056c16  mov     dword ptr [edi+18Ch], 0
0x10056c20  call    ?ReclaimPDSpace@Database@@QAEXXZ; Database::ReclaimPDSpace(void)
0x10056c25  test    ebx, ebx
0x10056c27  jle     short loc_10056C35
0x10056c29  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10056c2f  mov     [edi+0B4h], eax
0x10056c35  lea     eax, [edi+68h]
0x10056c38  push    eax; lpCriticalSection
0x10056c39  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056c3f  pop     edi
0x10056c40  pop     esi
0x10056c41  pop     ebx
0x10056c42  leave
0x10056c43  retn    8
```
