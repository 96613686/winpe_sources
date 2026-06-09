# Database::WriteDirtyPages(Err &,DBWriteOption)

- ea: `0x10056a81`
- end: `0x10056dd6`
- name: `?WriteDirtyPages@Database@@QAEXAAVErr@@W4DBWriteOption@@@Z`
- size: `853`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x10049130`
- `0x100532cd`
- `0x10057289`
- `0x100615f0`

## callees

- `0x10051327`
- `0x10056a81`
- `0x100575a0`
- `0x1006bb81`
- `0x10074d41`
- `0x10074d75`
- `0x10076444`
- `0x1007690e`
- `0x100775c8`
- `0x10123ca8`
- `0x10123cb3`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10056db9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x10056db9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056b7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056dc9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056b7e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x10056dc9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056aa3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x10056aa3`

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
0x10056a81  mov     edi, edi
0x10056a83  push    ebp
0x10056a84  mov     ebp, esp
0x10056a86  sub     esp, 30h
0x10056a89  push    ebx
0x10056a8a  push    esi; struct Err *
0x10056a8b  push    edi; struct Database *
0x10056a8c  mov     edi, ecx
0x10056a8e  xor     ebx, ebx
0x10056a90  mov     [ebp+var_10], edi
0x10056a93  mov     [ebp+var_8], ebx
0x10056a96  lea     eax, [edi+68h]
0x10056a99  mov     [edi+0ACh], ebx
0x10056a9f  push    eax; lpCriticalSection
0x10056aa0  mov     [ebp+lpCriticalSection], eax
0x10056aa3  call    ds:__imp__EnterCriticalSection@4; EnterCriticalSection(x)
0x10056aa9  mov     edx, [edi+18Ch]
0x10056aaf  mov     [ebp+var_14], edx
0x10056ab2  test    edx, edx
0x10056ab4  jz      loc_10056DC5
0x10056aba  push    8
0x10056abc  pop     ecx
0x10056abd  cmp     [ebp+arg_4], ebx
0x10056ac0  jnz     loc_10056D67
0x10056ac6  xor     eax, eax
0x10056ac8  xor     esi, esi
0x10056aca  mov     [ebp+var_1C], eax
0x10056acd  mov     eax, edx
0x10056acf  mul     ecx
0x10056ad1  push    0FFFFFFFFh
0x10056ad3  pop     ecx
0x10056ad4  cmovb   eax, ecx
0x10056ad7  push    eax; unsigned int
0x10056ad8  call    ??_U@YAPAXI@Z; operator new[](uint)
0x10056add  pop     ecx
0x10056ade  xor     ecx, ecx
0x10056ae0  mov     [ebp+var_30], 1
0x10056ae7  xor     edx, edx
0x10056ae9  mov     [ebp+var_8], ecx
0x10056aec  mov     ebx, eax
0x10056aee  mov     [ebp+var_18], edx
0x10056af1  mov     [ebp+Block], ebx
0x10056af4  cmp     [ebp+var_14], ecx
0x10056af7  jle     loc_10056BAB
0x10056afd  mov     eax, [edi+184h]
0x10056b03  mov     edx, [eax+edx*4]
0x10056b06  test    edx, edx
0x10056b08  jz      loc_10056B92
0x10056b0e  test    byte ptr [edx+1Ch], 8
0x10056b12  jz      short loc_10056B45
0x10056b14  cmp     byte ptr [edx+52h], 0
0x10056b18  jz      short loc_10056B21
0x10056b1a  cmp     [edx+0Ch], esi
0x10056b1d  cmova   esi, [edx+0Ch]
0x10056b21  mov     [ebx+ecx*8], edx
0x10056b24  cmp     byte ptr [edx+52h], 0
0x10056b28  jz      short loc_10056B2E
0x10056b2a  xor     eax, eax
0x10056b2c  jmp     short loc_10056B37
0x10056b2e  mov     eax, [edx+1Ch]
0x10056b31  shr     eax, 4
0x10056b34  and     eax, 0Fh
0x10056b37  shl     eax, 18h
0x10056b3a  add     eax, [edx+0Ch]
0x10056b3d  mov     [ebx+ecx*8+4], eax
0x10056b41  inc     ecx
0x10056b42  mov     [ebp+var_8], ecx
0x10056b45  mov     edx, [ebp+var_18]
0x10056b48  inc     edx
0x10056b49  mov     [ebp+var_18], edx
0x10056b4c  cmp     edx, [ebp+var_14]
0x10056b4f  jl      short loc_10056AFD
0x10056b51  test    esi, esi
0x10056b53  jz      short loc_10056BAB
0x10056b55  mov     ebx, [ebp+arg_0]
0x10056b58  lea     eax, [ebp+Buffer]
0x10056b5b  push    ebx; struct Err *
0x10056b5c  push    1; nNumberOfBytesToWrite
0x10056b5e  shl     esi, 0Ch
0x10056b61  lea     ecx, [edi+4]; this
0x10056b64  push    eax; lpBuffer
0x10056b65  add     esi, 0FFFh
0x10056b6b  mov     [ebp+Buffer], 0
0x10056b6f  push    esi; lDistanceToMove
0x10056b70  call    ?Write@File@@QAEXKPAXKAAVErr@@@Z; File::Write(ulong,void *,ulong,Err &)
0x10056b75  test    byte ptr [ebx], 8
0x10056b78  jz      short loc_10056BA8
0x10056b7a  mov     eax, [ebp+lpCriticalSection]
0x10056b7d  push    eax; lpCriticalSection
0x10056b7e  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056b84  push    [ebp+Block]; Block
0x10056b87  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10056b8c  pop     ecx
0x10056b8d  jmp     loc_10056DCF
0x10056b92  push    ecx
0x10056b93  mov     ecx, [ebp+arg_0]
0x10056b96  push    0FFFFFB4Ah
0x10056b9b  call    ?SetError@Err@@QAEXJW4ErrAssert@@@Z; Err::SetError(long,ErrAssert)
0x10056ba0  mov     eax, [ebp+lpCriticalSection]
0x10056ba3  jmp     loc_10056DC8
0x10056ba8  mov     ecx, [ebp+var_8]
0x10056bab  mov     eax, ecx
0x10056bad  cdq
0x10056bae  sub     eax, edx
0x10056bb0  mov     ebx, eax
0x10056bb2  sar     ebx, 1
0x10056bb4  mov     [ebp+var_28], ebx
0x10056bb7  test    ebx, ebx
0x10056bb9  jle     short loc_10056C32
0x10056bbb  mov     edi, [ebp+Block]
0x10056bbe  mov     [ebp+var_24], ebx
0x10056bc1  mov     edx, ebx
0x10056bc3  cmp     ebx, ecx
0x10056bc5  jge     short loc_10056C28
0x10056bc7  mov     eax, edx
0x10056bc9  sub     eax, ebx
0x10056bcb  mov     [ebp+var_18], eax
0x10056bce  js      short loc_10056C20
0x10056bd0  mov     ecx, eax
0x10056bd2  shl     ecx, 3
0x10056bd5  mov     [ebp+lpCriticalSection], ecx
0x10056bd8  mov     edx, [ecx+edi+4]
0x10056bdc  lea     eax, [ecx+ebx*8]
0x10056bdf  mov     [ebp+var_2C], edx
0x10056be2  cmp     edx, [eax+edi+4]
0x10056be6  jbe     short loc_10056C1A
0x10056be8  mov     edx, [ebp+var_18]
0x10056beb  mov     esi, [ecx+edi]
0x10056bee  add     edx, ebx
0x10056bf0  mov     ebx, [ebp+lpCriticalSection]
0x10056bf3  mov     eax, [edi+edx*8]
0x10056bf6  mov     ecx, [edi+edx*8+4]
0x10056bfa  mov     [ebx+edi], eax
0x10056bfd  mov     eax, ebx
0x10056bff  mov     ebx, [ebp+var_28]
0x10056c02  mov     [eax+edi+4], ecx
0x10056c06  mov     eax, [ebp+var_2C]
0x10056c09  mov     [edi+edx*8+4], eax
0x10056c0d  mov     eax, [ebp+var_18]
0x10056c10  sub     eax, ebx
0x10056c12  mov     [edi+edx*8], esi
0x10056c15  mov     [ebp+var_18], eax
0x10056c18  jns     short loc_10056BD0
0x10056c1a  mov     ecx, [ebp+var_8]
0x10056c1d  mov     edx, [ebp+var_24]
0x10056c20  inc     edx
0x10056c21  mov     [ebp+var_24], edx
0x10056c24  cmp     edx, ecx
0x10056c26  jl      short loc_10056BC7
0x10056c28  shr     ebx, 1
0x10056c2a  mov     [ebp+var_28], ebx
0x10056c2d  jnz     short loc_10056BBE
0x10056c2f  mov     edi, [ebp+var_10]
0x10056c32  xor     esi, esi
0x10056c34  mov     [ebp+var_28], esi
0x10056c37  test    ecx, ecx
0x10056c39  jle     short loc_10056C65
0x10056c3b  mov     ebx, [ebp+arg_0]
0x10056c3e  mov     edi, [ebp+Block]
0x10056c41  mov     eax, [edi+esi*8]
0x10056c44  cmp     byte ptr [eax+52h], 0
0x10056c48  jz      short loc_10056C5F
0x10056c4a  push    ebx; struct Err *
0x10056c4b  mov     ecx, eax; this
0x10056c4d  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10056c52  test    byte ptr [ebx], 8
0x10056c55  mov     ecx, [ebp+var_8]
0x10056c58  jnz     short loc_10056C5F
0x10056c5a  inc     esi
0x10056c5b  cmp     esi, ecx
0x10056c5d  jl      short loc_10056C41
0x10056c5f  mov     edi, [ebp+var_10]
0x10056c62  mov     [ebp+var_28], esi
0x10056c65  mov     eax, [ebp+arg_0]
0x10056c68  test    byte ptr [eax], 8
0x10056c6b  jnz     loc_10056D55
0x10056c71  mov     edx, esi
0x10056c73  cmp     esi, ecx
0x10056c75  jge     loc_10056D55
0x10056c7b  mov     edi, [ebp+Block]
0x10056c7e  mov     esi, [ebp+var_1C]
0x10056c81  mov     ebx, esi
0x10056c83  mov     eax, edx
0x10056c85  cmp     esi, 2
0x10056c88  jnb     short loc_10056C9C
0x10056c8a  mov     eax, [edi+eax*8]
0x10056c8d  lea     esi, [ebx+1]
0x10056c90  inc     edx
0x10056c91  test    byte ptr [eax+1Ch], 8
0x10056c95  cmovz   esi, ebx
0x10056c98  cmp     edx, ecx
0x10056c9a  jl      short loc_10056C81
0x10056c9c  mov     edi, [ebp+var_10]
0x10056c9f  xor     ecx, ecx
0x10056ca1  inc     ecx
0x10056ca2  mov     [ebp+var_1C], esi
0x10056ca5  cmp     esi, ecx
0x10056ca7  mov     eax, 100h
0x10056cac  mov     esi, [ebp+var_28]
0x10056caf  jbe     short loc_10056CE9
0x10056cb1  cmp     [edi+48h], ecx
0x10056cb4  jz      short loc_10056CE9
0x10056cb6  mov     ecx, [edi+64h]
0x10056cb9  cmp     [edi+ecx*2+1A8h], ax
0x10056cc1  jb      short loc_10056CD1
0x10056cc3  mov     eax, [ebp+arg_0]
0x10056cc6  xor     edx, edx
0x10056cc8  push    eax; struct Err *
0x10056cc9  push    edi; unsigned int
0x10056cca  call    ?ChangeUserState@DBHeaderPage@@SGXIIPAVDatabase@@AAVErr@@@Z; DBHeaderPage::ChangeUserState(uint,uint,Database *,Err &)
0x10056ccf  jmp     short loc_10056CE9
0x10056cd1  push    ecx
0x10056cd2  mov     ecx, [ebp+arg_0]
0x10056cd5  push    0
0x10056cd7  push    dword ptr [edi+8]
0x10056cda  push    0FFFFE004h
0x10056cdf  push    0FFFFFB4Ah
0x10056ce4  call    ?SetError@Err@@QAEXJJQAG0W4ErrAssert@@@Z; Err::SetError(long,long,ushort * const,ushort * const,ErrAssert)
0x10056ce9  mov     ebx, [ebp+var_8]
0x10056cec  mov     edi, [ebp+arg_0]
0x10056cef  mov     eax, [ebp+Block]
0x10056cf2  push    edi; struct Err *
0x10056cf3  mov     ecx, [eax+esi*8]; this
0x10056cf6  call    ?Write@PageDesc@@QAEXAAVErr@@@Z; PageDesc::Write(Err &)
0x10056cfb  inc     esi
0x10056cfc  cmp     esi, ebx
0x10056cfe  jl      short loc_10056CEF
0x10056d00  cmp     [ebp+var_1C], 0
0x10056d04  mov     edi, [ebp+var_10]
0x10056d07  jz      short loc_10056D58
0x10056d09  mov     ecx, [ebp+arg_0]
0x10056d0c  test    byte ptr [ecx], 8
0x10056d0f  jnz     short loc_10056D58
0x10056d11  cmp     dword ptr [edi+48h], 1
0x10056d15  jz      short loc_10056D58
0x10056d17  mov     esi, [edi+64h]
0x10056d1a  cmp     esi, 100h
0x10056d20  jnb     short loc_10056D58
0x10056d22  movzx   eax, word ptr [edi+esi*2+1A8h]
0x10056d2a  mov     edx, eax
0x10056d2c  cmp     ax, word ptr [ebp+var_30]
0x10056d30  jz      short loc_10056D58
0x10056d32  inc     edx
0x10056d33  mov     eax, 100h
0x10056d38  cmp     edx, 0FFFFh
0x10056d3e  push    ecx; struct Err *
0x10056d3f  cmova   edx, eax
0x10056d42  mov     [edi+esi*2+1A8h], dx
0x10056d4a  mov     ecx, [edi+64h]
0x10056d4d  push    edi; unsigned int
0x10056d4e  call    ?ChangeUserState@DBHeaderPage@@SGXIIPAVDatabase@@AAVErr@@@Z; DBHeaderPage::ChangeUserState(uint,uint,Database *,Err &)
0x10056d53  jmp     short loc_10056D58
0x10056d55  mov     ebx, [ebp+var_8]
0x10056d58  push    [ebp+Block]; Block
0x10056d5b  call    ??_V@YAXPAX@Z; operator delete[](void *)
0x10056d60  mov     edx, [ebp+var_14]
0x10056d63  pop     ecx
0x10056d64  push    8
0x10056d66  pop     ecx
0x10056d67  mov     eax, [ebp+arg_0]
0x10056d6a  test    [eax], cl
0x10056d6c  jnz     short loc_10056DC5
0x10056d6e  xor     ecx, ecx
0x10056d70  mov     [ebp+var_28], ecx
0x10056d73  test    edx, edx
0x10056d75  jle     short loc_10056DA4
0x10056d77  mov     ebx, eax
0x10056d79  mov     eax, [edi+184h]
0x10056d7f  push    ebx; struct Err *
0x10056d80  mov     esi, [eax+ecx*4]
0x10056d83  mov     ecx, esi; this
0x10056d85  call    ?Unlock@PageDesc@@QAEIAAVErr@@@Z; PageDesc::Unlock(Err &)
0x10056d8a  and     byte ptr [esi+58h], 0FDh
0x10056d8e  mov     ecx, esi; this
0x10056d90  call    ?Free@PageDesc@@QAEXXZ; PageDesc::Free(void)
0x10056d95  mov     ecx, [ebp+var_28]
0x10056d98  inc     ecx
0x10056d99  mov     [ebp+var_28], ecx
0x10056d9c  cmp     ecx, [ebp+var_14]
0x10056d9f  jl      short loc_10056D79
0x10056da1  mov     ebx, [ebp+var_8]
0x10056da4  mov     ecx, edi; this
0x10056da6  mov     dword ptr [edi+18Ch], 0
0x10056db0  call    ?ReclaimPDSpace@Database@@QAEXXZ; Database::ReclaimPDSpace(void)
0x10056db5  test    ebx, ebx
0x10056db7  jle     short loc_10056DC5
0x10056db9  call    ds:__imp__GetTickCount@0; GetTickCount()
0x10056dbf  mov     [edi+0B4h], eax
0x10056dc5  lea     eax, [edi+68h]
0x10056dc8  push    eax; lpCriticalSection
0x10056dc9  call    ds:__imp__LeaveCriticalSection@4; LeaveCriticalSection(x)
0x10056dcf  pop     edi
0x10056dd0  pop     esi
0x10056dd1  pop     ebx
0x10056dd2  leave
0x10056dd3  retn    8
```
