# GetTTFFieldFromFile(CHandle &,ushort,ushort,ushort,bool,uint,CAPITempBufferRef<ushort> &)

- ea: `0x1800f158c`
- end: `0x1800f193f`
- name: `?GetTTFFieldFromFile@@YAKAEAVCHandle@@GGG_NIAEAV?$CAPITempBufferRef@G@@@Z`
- size: `947`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800f1458`
- `0x18014abd8`

## callees

- `0x18006cb7c`
- `0x1800f158c`
- `0x1802201a8`
- `0x180265240`

## import_xrefs

- `KERNEL32!ReadFile` at `0x1800f162a`
- `KERNEL32!ReadFile` at `0x1800f1699`
- `KERNEL32!ReadFile` at `0x1800f1719`
- `KERNEL32!ReadFile` at `0x1800f1766`
- `KERNEL32!ReadFile` at `0x1800f18da`
- `KERNEL32!ReadFile` at `0x1800f162a`
- `KERNEL32!ReadFile` at `0x1800f1699`
- `KERNEL32!ReadFile` at `0x1800f1719`
- `KERNEL32!ReadFile` at `0x1800f1766`
- `KERNEL32!ReadFile` at `0x1800f18da`
- `KERNEL32!SetFilePointer` at `0x1800f15fd`
- `KERNEL32!SetFilePointer` at `0x1800f16ef`
- `KERNEL32!SetFilePointer` at `0x1800f18b0`
- `KERNEL32!SetFilePointer` at `0x1800f15fd`
- `KERNEL32!SetFilePointer` at `0x1800f16ef`
- `KERNEL32!SetFilePointer` at `0x1800f18b0`

## pseudocode

```c
__int64 __fastcall GetTTFFieldFromFile(
        HANDLE *a1,
        __int64 a2,
        __int16 a3,
        __int16 a4,
        char a5,
        unsigned int a6,
        void **a7)
{
  HANDLE v9; // rcx
  HANDLE v11; // rcx
  unsigned int v13; // ebx
  unsigned int v14; // esi
  LONG v15; // ebx
  int i; // ebx
  __int16 v17; // r15
  __int16 v18; // r12
  int v19; // r13d
  int v20; // ebx
  DWORD v21; // r14d
  unsigned int v22; // esi
  LONG v23; // ebx
  char *v24; // rsi
  int j; // r9d
  __int64 v26; // rdx
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-71h] BYREF
  int v28; // [rsp+34h] [rbp-6Dh] BYREF
  unsigned __int16 v29; // [rsp+38h] [rbp-69h]
  int v30; // [rsp+3Ch] [rbp-65h]
  int v31; // [rsp+40h] [rbp-61h]
  int v32; // [rsp+44h] [rbp-5Dh]
  void **v33; // [rsp+48h] [rbp-59h]
  __int64 v34; // [rsp+50h] [rbp-51h] BYREF
  int v35; // [rsp+58h] [rbp-49h]
  __int128 v36; // [rsp+60h] [rbp-41h] BYREF
  _BYTE Buffer[32]; // [rsp+70h] [rbp-31h] BYREF

  v33 = a7;
  v9 = *a1;
  v28 = 0;
  memset(Buffer, 0, 28);
  v29 = 0;
  v34 = 0;
  v36 = 0;
  v35 = 0;
  if ( a5 )
  {
    if ( !FTTCSeek(v9, a6) )
      return 0;
  }
  else if ( SetFilePointer(v9, 0, 0, 0) )
  {
    return 0;
  }
  v11 = *a1;
  NumberOfBytesRead = 0;
  if ( ReadFile(v11, Buffer, 0xCu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 12 )
  {
    v13 = 0;
    v14 = Buffer[5] | (unsigned __int16)(Buffer[4] << 8);
    while ( v13 < v14 && v13 < 0x28 && ReadFile(*a1, &v36, 0x10u, &NumberOfBytesRead, 0) && NumberOfBytesRead == 16 )
    {
      if ( (_DWORD)v36 == 1701667182 )
      {
        v15 = ((WORD4(v36) & 0xFF00 | (DWORD2(v36) << 16)) << 8)
            | ((HIWORD(DWORD2(v36)) | DWORD2(v36) & 0xFF0000u) >> 8);
        if ( SetFilePointer(*a1, v15, 0, 0) == v15
          && ReadFile(*a1, &v28, 6u, &NumberOfBytesRead, 0)
          && NumberOfBytesRead == 6 )
        {
          for ( i = HIBYTE(HIWORD(v28)) | (unsigned __int16)(BYTE2(v28) << 8);
                i && ReadFile(*a1, &v34, 0xCu, &NumberOfBytesRead, 0) && NumberOfBytesRead == 12;
                --i )
          {
            if ( (BYTE1(v34) | (unsigned __int16)((unsigned __int8)v34 << 8)) == 3
              && ((HIBYTE(WORD2(v34)) | (unsigned __int16)(BYTE4(v34) << 8)) == a3
               && (HIBYTE(HIWORD(v34)) | (unsigned __int16)(BYTE6(v34) << 8)) == a4
               || (HIBYTE(HIWORD(v34)) | (unsigned __int16)(BYTE6(v34) << 8)) == a4 && a3 == 2048) )
            {
              v17 = (unsigned __int8)v29;
              v18 = BYTE2(v35);
              v19 = DWORD2(v36) & 0xFF0000;
              v30 = DWORD2(v36) << 16;
              v20 = WORD4(v36) & 0xFF00;
              v31 = HIBYTE(v29);
              v32 = HIBYTE(HIWORD(v35));
              v21 = BYTE1(v35) | (unsigned __int16)((unsigned __int8)v35 << 8);
              v22 = HIWORD(DWORD2(v36));
              if ( !(unsigned __int8)CAPITempBufferRef<unsigned short>::SetSize(v33, (v21 >> 1) + 1, 0) )
                return 0;
              v23 = (v32 | (unsigned __int16)(v18 << 8))
                  + (v31 | (unsigned __int16)(v17 << 8))
                  + (((v19 | v22) >> 8) | ((v30 | v20) << 8));
              v24 = (char *)*v33;
              if ( SetFilePointer(*a1, v23, 0, 0) != v23
                || !ReadFile(*a1, v24, v21, &NumberOfBytesRead, 0)
                || v21 != NumberOfBytesRead )
              {
                return 0;
              }
              for ( j = 0;
                    j < (unsigned __int64)v21 >> 1;
                    *(_WORD *)&v24[2 * v26] = _byteswap_ushort(*(_WORD *)&v24[2 * v26]) )
              {
                v26 = j++;
              }
              *(_WORD *)&v24[v21 & 0xFFFFFFFE] = 0;
              return v21 + 1;
            }
          }
        }
        return 0;
      }
      ++v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800f158c  push    rbp
0x1800f158e  push    rbx
0x1800f158f  push    rsi
0x1800f1590  push    rdi
0x1800f1591  push    r12
0x1800f1593  push    r13
0x1800f1595  push    r14
0x1800f1597  push    r15
0x1800f1599  lea     rbp, [rsp-7]
0x1800f159e  sub     rsp, 0A8h
0x1800f15a5  mov     rax, cs:__security_cookie
0x1800f15ac  xor     rax, rsp
0x1800f15af  mov     [rbp+3Fh+var_50], rax
0x1800f15b3  mov     rax, [rbp+3Fh+arg_30]
0x1800f15b7  xorps   xmm0, xmm0
0x1800f15ba  mov     [rbp+3Fh+var_98], rax
0x1800f15be  xor     r12d, r12d
0x1800f15c1  xor     eax, eax
0x1800f15c3  mov     rdi, rcx
0x1800f15c6  movzx   r15d, r9w
0x1800f15ca  mov     rcx, [rcx]; hFile
0x1800f15cd  movzx   r14d, r8w
0x1800f15d1  mov     [rbp+3Fh+var_AC], eax
0x1800f15d4  movups  xmmword ptr [rbp+3Fh+Buffer], xmm0
0x1800f15d8  mov     [rbp+3Fh+var_A8], ax
0x1800f15dc  movups  xmmword ptr [rbp+3Fh+Buffer+0Ch], xmm0
0x1800f15e0  mov     [rbp+3Fh+var_90], rax
0x1800f15e4  movups  [rbp+3Fh+var_80], xmm0
0x1800f15e8  mov     [rbp+3Fh+var_88], eax
0x1800f15eb  cmp     [rbp+3Fh+arg_20], r12b
0x1800f15ef  jnz     loc_1800F17A1
0x1800f15f5  xor     r9d, r9d; dwMoveMethod
0x1800f15f8  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800f15fb  xor     edx, edx; lDistanceToMove
0x1800f15fd  call    cs:__imp_SetFilePointer
0x1800f1604  nop     dword ptr [rax+rax+00h]
0x1800f1609  test    eax, eax
0x1800f160b  jnz     short loc_1800F163A
0x1800f160d  mov     rcx, [rdi]; hFile
0x1800f1610  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f1614  mov     r13d, 0Ch
0x1800f161a  mov     [rbp+3Fh+NumberOfBytesRead], r12d
0x1800f161e  mov     r8d, r13d; nNumberOfBytesToRead
0x1800f1621  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800f1626  lea     rdx, [rbp+3Fh+Buffer]; lpBuffer
0x1800f162a  call    cs:__imp_ReadFile
0x1800f1631  nop     dword ptr [rax+rax+00h]
0x1800f1636  test    eax, eax
0x1800f1638  jnz     short loc_1800F165D
0x1800f163a  xor     eax, eax
0x1800f163c  mov     rcx, [rbp+3Fh+var_50]
0x1800f1640  xor     rcx, rsp; StackCookie
0x1800f1643  call    __security_check_cookie
0x1800f1648  add     rsp, 0A8h
0x1800f164f  pop     r15
0x1800f1651  pop     r14
0x1800f1653  pop     r13
0x1800f1655  pop     r12
0x1800f1657  pop     rdi
0x1800f1658  pop     rsi
0x1800f1659  pop     rbx
0x1800f165a  pop     rbp
0x1800f165b  retn
0x1800f165d  cmp     [rbp+3Fh+NumberOfBytesRead], r13d
0x1800f1661  jnz     short loc_1800F163A
0x1800f1663  movzx   eax, [rbp+3Fh+Buffer+4]
0x1800f1667  mov     ebx, r12d
0x1800f166a  shl     ax, 8
0x1800f166e  movzx   esi, ax
0x1800f1671  movzx   eax, word ptr [rbp+3Fh+Buffer+4]
0x1800f1675  shr     eax, 8
0x1800f1678  or      esi, eax
0x1800f167a  cmp     ebx, esi
0x1800f167c  jnb     short loc_1800F163A
0x1800f167e  cmp     ebx, 28h ; '('
0x1800f1681  jnb     short loc_1800F163A
0x1800f1683  mov     rcx, [rdi]; hFile
0x1800f1686  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f168a  mov     r8d, 10h; nNumberOfBytesToRead
0x1800f1690  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800f1695  lea     rdx, [rbp+3Fh+var_80]; lpBuffer
0x1800f1699  call    cs:__imp_ReadFile
0x1800f16a0  nop     dword ptr [rax+rax+00h]
0x1800f16a5  test    eax, eax
0x1800f16a7  jz      short loc_1800F163A
0x1800f16a9  cmp     [rbp+3Fh+NumberOfBytesRead], 10h
0x1800f16ad  jnz     short loc_1800F163A
0x1800f16af  cmp     dword ptr [rbp+3Fh+var_80], 656D616Eh
0x1800f16b6  jz      short loc_1800F16BC
0x1800f16b8  inc     ebx
0x1800f16ba  jmp     short loc_1800F167A
0x1800f16bc  mov     ecx, dword ptr [rbp+3Fh+var_80+8]
0x1800f16bf  mov     esi, 0FF0000h
0x1800f16c4  mov     ebx, ecx
0x1800f16c6  mov     eax, ecx
0x1800f16c8  shr     eax, 10h
0x1800f16cb  and     ebx, esi
0x1800f16cd  or      ebx, eax
0x1800f16cf  xor     r9d, r9d; dwMoveMethod
0x1800f16d2  mov     eax, ecx
0x1800f16d4  shr     ebx, 8
0x1800f16d7  shl     eax, 10h
0x1800f16da  and     ecx, 0FF00h
0x1800f16e0  or      eax, ecx
0x1800f16e2  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800f16e5  mov     rcx, [rdi]; hFile
0x1800f16e8  shl     eax, 8
0x1800f16eb  or      ebx, eax
0x1800f16ed  mov     edx, ebx; lDistanceToMove
0x1800f16ef  call    cs:__imp_SetFilePointer
0x1800f16f6  nop     dword ptr [rax+rax+00h]
0x1800f16fb  cmp     eax, ebx
0x1800f16fd  jnz     loc_1800F163A
0x1800f1703  mov     rcx, [rdi]; hFile
0x1800f1706  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f170a  mov     r8d, 6; nNumberOfBytesToRead
0x1800f1710  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800f1715  lea     rdx, [rbp+3Fh+var_AC]; lpBuffer
0x1800f1719  call    cs:__imp_ReadFile
0x1800f1720  nop     dword ptr [rax+rax+00h]
0x1800f1725  test    eax, eax
0x1800f1727  jz      loc_1800F163A
0x1800f172d  cmp     [rbp+3Fh+NumberOfBytesRead], 6
0x1800f1731  jnz     loc_1800F163A
0x1800f1737  movzx   eax, byte ptr [rbp+3Fh+var_AC+2]
0x1800f173b  shl     ax, 8
0x1800f173f  movzx   ebx, ax
0x1800f1742  movzx   eax, word ptr [rbp+3Fh+var_AC+2]
0x1800f1746  shr     eax, 8
0x1800f1749  or      ebx, eax
0x1800f174b  test    ebx, ebx
0x1800f174d  jz      loc_1800F163A
0x1800f1753  mov     rcx, [rdi]; hFile
0x1800f1756  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f175a  mov     r8d, r13d; nNumberOfBytesToRead
0x1800f175d  mov     [rsp+0E0h+lpOverlapped], r12; lpOverlapped
0x1800f1762  lea     rdx, [rbp+3Fh+var_90]; lpBuffer
0x1800f1766  call    cs:__imp_ReadFile
0x1800f176d  nop     dword ptr [rax+rax+00h]
0x1800f1772  test    eax, eax
0x1800f1774  jz      loc_1800F163A
0x1800f177a  cmp     [rbp+3Fh+NumberOfBytesRead], r13d
0x1800f177e  jnz     loc_1800F163A
0x1800f1784  movzx   ecx, byte ptr [rbp+3Fh+var_90]
0x1800f1788  movzx   eax, word ptr [rbp+3Fh+var_90]
0x1800f178c  shl     cx, 8
0x1800f1790  shr     ax, 8
0x1800f1794  or      cx, ax
0x1800f1797  cmp     cx, 3
0x1800f179b  jz      short loc_1800F17B6
0x1800f179d  dec     ebx
0x1800f179f  jmp     short loc_1800F174B
0x1800f17a1  mov     edx, [rbp+3Fh+arg_28]; unsigned int
0x1800f17a4  call    ?FTTCSeek@@YA_NPEAXI@Z; FTTCSeek(void *,uint)
0x1800f17a9  test    al, al
0x1800f17ab  jz      loc_1800F163A
0x1800f17b1  jmp     loc_1800F160D
0x1800f17b6  movzx   ecx, byte ptr [rbp+3Fh+var_90+4]
0x1800f17ba  movzx   eax, word ptr [rbp+3Fh+var_90+4]
0x1800f17be  movzx   edx, word ptr [rbp+3Fh+var_90+6]
0x1800f17c2  shl     cx, 8
0x1800f17c6  shr     ax, 8
0x1800f17ca  or      cx, ax
0x1800f17cd  cmp     cx, r14w
0x1800f17d1  jnz     short loc_1800F17EA
0x1800f17d3  movzx   ecx, dl
0x1800f17d6  movzx   eax, dx
0x1800f17d9  shl     cx, 8
0x1800f17dd  shr     ax, 8
0x1800f17e1  or      cx, ax
0x1800f17e4  cmp     cx, r15w
0x1800f17e8  jz      short loc_1800F1809
0x1800f17ea  movzx   eax, dl
0x1800f17ed  shl     ax, 8
0x1800f17f1  shr     dx, 8
0x1800f17f5  or      ax, dx
0x1800f17f8  cmp     ax, r15w
0x1800f17fc  jnz     short loc_1800F179D
0x1800f17fe  mov     eax, 800h
0x1800f1803  cmp     ax, r14w
0x1800f1807  jnz     short loc_1800F179D
0x1800f1809  mov     ebx, dword ptr [rbp+3Fh+var_80+8]
0x1800f180c  xor     r8d, r8d
0x1800f180f  mov     rcx, [rbp+3Fh+var_98]
0x1800f1813  mov     eax, ebx
0x1800f1815  movzx   r15d, byte ptr [rbp+3Fh+var_A8]
0x1800f181a  mov     r13d, ebx
0x1800f181d  movzx   r12d, byte ptr [rbp+3Fh+var_88+2]
0x1800f1822  and     r13d, esi
0x1800f1825  shl     eax, 10h
0x1800f1828  mov     esi, ebx
0x1800f182a  mov     [rbp+3Fh+var_A4], eax
0x1800f182d  and     ebx, 0FF00h
0x1800f1833  movzx   eax, [rbp+3Fh+var_A8]
0x1800f1837  shr     eax, 8
0x1800f183a  mov     [rbp+3Fh+var_A0], eax
0x1800f183d  movzx   eax, word ptr [rbp+3Fh+var_88+2]
0x1800f1841  shr     eax, 8
0x1800f1844  mov     [rbp+3Fh+var_9C], eax
0x1800f1847  movzx   eax, byte ptr [rbp+3Fh+var_88]
0x1800f184b  shl     ax, 8
0x1800f184f  movzx   r14d, ax
0x1800f1853  movzx   eax, word ptr [rbp+3Fh+var_88]
0x1800f1857  shr     eax, 8
0x1800f185a  or      r14d, eax
0x1800f185d  shr     esi, 10h
0x1800f1860  mov     edx, r14d
0x1800f1863  shr     edx, 1
0x1800f1865  inc     edx
0x1800f1867  call    ?SetSize@?$CAPITempBufferRef@G@@QEAA_NH_N@Z; CAPITempBufferRef<ushort>::SetSize(int,bool)
0x1800f186c  test    al, al
0x1800f186e  jz      loc_1800F163A
0x1800f1874  or      ebx, [rbp+3Fh+var_A4]
0x1800f1877  or      esi, r13d
0x1800f187a  mov     rcx, [rdi]; hFile
0x1800f187d  xor     r9d, r9d; dwMoveMethod
0x1800f1880  shl     ebx, 8
0x1800f1883  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800f1886  shr     esi, 8
0x1800f1889  or      ebx, esi
0x1800f188b  shl     r15w, 8
0x1800f1890  movzx   eax, r15w
0x1800f1894  or      eax, [rbp+3Fh+var_A0]
0x1800f1897  add     ebx, eax
0x1800f1899  shl     r12w, 8
0x1800f189e  movzx   eax, r12w
0x1800f18a2  or      eax, [rbp+3Fh+var_9C]
0x1800f18a5  add     ebx, eax
0x1800f18a7  mov     rax, [rbp+3Fh+var_98]
0x1800f18ab  mov     edx, ebx; lDistanceToMove
0x1800f18ad  mov     rsi, [rax]
0x1800f18b0  call    cs:__imp_SetFilePointer
0x1800f18b7  nop     dword ptr [rax+rax+00h]
0x1800f18bc  cmp     eax, ebx
0x1800f18be  jnz     loc_1800F163A
0x1800f18c4  mov     rcx, [rdi]; hFile
0x1800f18c7  lea     r9, [rbp+3Fh+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800f18cb  mov     r8d, r14d; nNumberOfBytesToRead
0x1800f18ce  mov     [rsp+0E0h+lpOverlapped], 0; lpOverlapped
0x1800f18d7  mov     rdx, rsi; lpBuffer
0x1800f18da  call    cs:__imp_ReadFile
0x1800f18e1  nop     dword ptr [rax+rax+00h]
0x1800f18e6  test    eax, eax
0x1800f18e8  jz      loc_1800F163A
0x1800f18ee  cmp     r14d, [rbp+3Fh+NumberOfBytesRead]
0x1800f18f2  jnz     loc_1800F163A
0x1800f18f8  mov     r10d, r14d
0x1800f18fb  mov     r9d, 0
0x1800f1901  shr     r10, 1
0x1800f1904  mov     r8d, r14d
0x1800f1907  jz      short loc_1800F192B
0x1800f1909  movsxd  rdx, r9d
0x1800f190c  inc     r9d
0x1800f190f  movzx   eax, byte ptr [rsi+rdx*2+1]
0x1800f1914  movzx   ecx, byte ptr [rsi+rdx*2]
0x1800f1918  shl     cx, 8
0x1800f191c  or      cx, ax
0x1800f191f  movsxd  rax, r9d
0x1800f1922  mov     [rsi+rdx*2], cx
0x1800f1926  cmp     rax, r10
0x1800f1929  jb      short loc_1800F1909
0x1800f192b  and     r8, 0FFFFFFFFFFFFFFFEh
0x1800f192f  xor     eax, eax
0x1800f1931  mov     [r8+rsi], ax
0x1800f1936  lea     eax, [r14+1]
0x1800f193a  jmp     loc_1800F163C
```
