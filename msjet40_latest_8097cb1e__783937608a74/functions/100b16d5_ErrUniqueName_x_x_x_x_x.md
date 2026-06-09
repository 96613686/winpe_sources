# ErrUniqueName(x,x,x,x,x)

- ea: `0x100b16d5`
- end: `0x100b18fd`
- name: `_ErrUniqueName@20`
- size: `552`
- prototype: `int __fastcall(int, int, const unsigned __int16 *, int, int)`
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100330a0`
- `0x100a301a`
- `0x100b1903`
- `0x100cfb84`

## callees

- `0x10017010`
- `0x100b1690`
- `0x100b16d5`
- `0x10123110`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x100b1890`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x100b1890`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100b1735`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100b1735`

## pseudocode

```c
int __fastcall ErrUniqueName(int a1, int a2, const unsigned __int16 *a3, int a4, int a5)
{
  unsigned int v5; // ecx
  unsigned __int16 *v6; // esi
  int v7; // edi
  _WORD *v9; // esi
  int v10; // edi
  int v11; // ecx
  _WORD *v12; // esi
  int v13; // edi
  signed int v14; // eax
  int v15; // ecx
  _WORD *v16; // esi
  int v17; // ecx
  char *v18; // esi
  unsigned int v19; // edi
  int v20; // ecx
  struct _FILETIME SystemTimeAsFileTime; // [esp+10h] [ebp-24h] BYREF
  unsigned int Data1; // [esp+18h] [ebp-1Ch]
  GUID pguid; // [esp+1Ch] [ebp-18h] BYREF

  if ( a3 )
  {
    if ( a2 )
      WCSCPY2(65);
    else
      *a3 = 0;
    v5 = wcslen(a3);
    v6 = (unsigned __int16 *)&a3[v5];
    v7 = 2 * v5;
    if ( a5 )
    {
      if ( CoCreateGuid(&pguid) < 0 )
        return -1011;
      if ( (int)(v7 & 0xFFFFFFFE) < 130 )
      {
        *v6 = 95;
        v9 = v6 + 1;
        Data1 = pguid.Data1;
        v10 = 8;
        while ( 1 )
        {
          v11 = ((int)v9 + 2 * v10 - 4 - (int)a3) >> 1;
          if ( v11 >= 65 )
            break;
          MapByteToHexStr(65 - v11);
          Data1 >>= 8;
          v10 -= 2;
          if ( v10 <= 0 )
          {
            if ( (int)(((char *)(v9 + 8) - (char *)a3) & 0xFFFFFFFE) < 130 )
            {
              v9[8] = 95;
              v12 = v9 + 9;
              v13 = 4;
              Data1 = pguid.Data2;
              v14 = 4;
              SystemTimeAsFileTime.dwHighDateTime = 4;
              while ( 1 )
              {
                v15 = ((int)v12 + 2 * v14 - 4 - (int)a3) >> 1;
                if ( v15 >= 65 )
                  break;
                MapByteToHexStr(65 - v15);
                LOWORD(Data1) = BYTE1(Data1);
                v14 = SystemTimeAsFileTime.dwHighDateTime - 2;
                SystemTimeAsFileTime.dwHighDateTime = v14;
                if ( v14 <= 0 )
                {
                  if ( (int)(((char *)(v12 + 4) - (char *)a3) & 0xFFFFFFFE) < 130 )
                  {
                    v12[4] = 95;
                    v16 = v12 + 5;
                    Data1 = pguid.Data3;
                    while ( 1 )
                    {
                      v17 = ((int)v16 + 2 * v13 - 4 - (int)a3) >> 1;
                      if ( v17 >= 65 )
                        break;
                      MapByteToHexStr(65 - v17);
                      LOWORD(Data1) = BYTE1(Data1);
                      v13 -= 2;
                      if ( v13 <= 0 )
                      {
                        v18 = (char *)(v16 + 4);
                        if ( (int)((v18 - (char *)a3) & 0xFFFFFFFE) >= 130 )
                          return -1038;
                        *(_WORD *)v18 = 0;
                        goto LABEL_27;
                      }
                    }
                  }
                  return -1038;
                }
              }
            }
            return -1038;
          }
        }
      }
    }
    else if ( (int)(2 * v5) < 130 )
    {
      *v6 = 95;
      v18 = (char *)(v6 + 1);
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v19 = 0;
      Data1 = (unsigned int)&SystemTimeAsFileTime;
      while ( 1 )
      {
        v20 = (int)&v18[2 * v19 - (_DWORD)a3] >> 1;
        if ( v20 >= 65 )
          break;
        MapByteToHexStr(65 - v20);
        ++Data1;
        v19 += 2;
        if ( v19 >= 8 )
        {
          *(_WORD *)&v18[2 * v19] = 0;
LABEL_27:
          *(_WORD *)&v18[2 * (64 - ((v18 - (char *)a3) >> 1))] = 0;
          return 0;
        }
      }
    }
  }
  return -1038;
}

```

## disassembly

```asm
0x100b16d5  mov     edi, edi
0x100b16d7  push    ebp
0x100b16d8  mov     ebp, esp
0x100b16da  sub     esp, 28h
0x100b16dd  mov     eax, ___security_cookie
0x100b16e2  xor     eax, ebp
0x100b16e4  mov     [ebp+var_8], eax
0x100b16e7  push    ebx
0x100b16e8  push    esi
0x100b16e9  mov     esi, [ebp+arg_0]
0x100b16ec  mov     ebx, esi
0x100b16ee  push    edi
0x100b16ef  test    esi, esi
0x100b16f1  jz      loc_100B18E7
0x100b16f7  test    edx, edx
0x100b16f9  jz      short loc_100B1706
0x100b16fb  push    41h ; 'A'
0x100b16fd  mov     ecx, esi
0x100b16ff  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100b1704  jmp     short loc_100B170B
0x100b1706  xor     eax, eax
0x100b1708  mov     [esi], ax
0x100b170b  mov     ecx, esi
0x100b170d  xor     edi, edi
0x100b170f  lea     edx, [ecx+2]
0x100b1712  mov     ax, [ecx]
0x100b1715  add     ecx, 2
0x100b1718  cmp     ax, di
0x100b171b  jnz     short loc_100B1712
0x100b171d  sub     ecx, edx
0x100b171f  sar     ecx, 1
0x100b1721  cmp     [ebp+arg_8], 0
0x100b1725  lea     esi, [esi+ecx*2]
0x100b1728  lea     edi, [ecx+ecx]
0x100b172b  jz      loc_100B1878
0x100b1731  lea     eax, [ebp+pguid]
0x100b1734  push    eax; pguid
0x100b1735  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x100b173b  test    eax, eax
0x100b173d  jns     short loc_100B1749
0x100b173f  mov     eax, 0FFFFFC0Dh
0x100b1744  jmp     loc_100B18EC
0x100b1749  and     edi, 0FFFFFFFEh
0x100b174c  cmp     edi, 82h
0x100b1752  jge     loc_100B18E7
0x100b1758  push    5Fh ; '_'
0x100b175a  pop     eax
0x100b175b  mov     [esi], ax
0x100b175e  add     esi, 2
0x100b1761  mov     eax, [ebp+pguid.Data1]
0x100b1764  push    8
0x100b1766  mov     [ebp+var_1C], eax
0x100b1769  pop     edi
0x100b176a  lea     edx, ds:0FFFFFFFCh[edi*2]
0x100b1771  mov     ecx, edx
0x100b1773  sub     ecx, ebx
0x100b1775  add     ecx, esi
0x100b1777  sar     ecx, 1
0x100b1779  cmp     ecx, 41h ; 'A'
0x100b177c  jge     loc_100B18E7
0x100b1782  push    41h ; 'A'
0x100b1784  pop     eax
0x100b1785  sub     eax, ecx
0x100b1787  add     edx, esi
0x100b1789  push    eax
0x100b178a  mov     eax, [ebp+var_1C]
0x100b178d  movzx   ecx, al
0x100b1790  call    MapByteToHexStr
0x100b1795  shr     [ebp+var_1C], 8
0x100b1799  sub     edi, 2
0x100b179c  test    edi, edi
0x100b179e  jg      short loc_100B176A
0x100b17a0  lea     eax, [esi+10h]
0x100b17a3  sub     eax, ebx
0x100b17a5  and     eax, 0FFFFFFFEh
0x100b17a8  cmp     eax, 82h
0x100b17ad  jge     loc_100B18E7
0x100b17b3  push    5Fh ; '_'
0x100b17b5  pop     eax
0x100b17b6  mov     [esi+10h], ax
0x100b17ba  add     esi, 12h
0x100b17bd  movzx   eax, [ebp+pguid.Data2]
0x100b17c1  push    4
0x100b17c3  pop     edi
0x100b17c4  mov     [ebp+var_1C], eax
0x100b17c7  mov     eax, edi
0x100b17c9  mov     [ebp+SystemTimeAsFileTime.dwHighDateTime], edi
0x100b17cc  lea     edx, ds:0FFFFFFFCh[eax*2]
0x100b17d3  mov     ecx, edx
0x100b17d5  sub     ecx, ebx
0x100b17d7  add     ecx, esi
0x100b17d9  sar     ecx, 1
0x100b17db  cmp     ecx, 41h ; 'A'
0x100b17de  jge     loc_100B18E7
0x100b17e4  push    41h ; 'A'
0x100b17e6  pop     eax
0x100b17e7  sub     eax, ecx
0x100b17e9  add     edx, esi
0x100b17eb  movzx   ecx, byte ptr [ebp+var_1C]
0x100b17ef  push    eax
0x100b17f0  call    MapByteToHexStr
0x100b17f5  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x100b17f8  shr     word ptr [ebp+var_1C], 8
0x100b17fd  sub     eax, 2
0x100b1800  mov     [ebp+SystemTimeAsFileTime.dwHighDateTime], eax
0x100b1803  test    eax, eax
0x100b1805  jg      short loc_100B17CC
0x100b1807  lea     eax, [esi+8]
0x100b180a  sub     eax, ebx
0x100b180c  and     eax, 0FFFFFFFEh
0x100b180f  cmp     eax, 82h
0x100b1814  jge     loc_100B18E7
0x100b181a  push    5Fh ; '_'
0x100b181c  pop     eax
0x100b181d  mov     [esi+8], ax
0x100b1821  add     esi, 0Ah
0x100b1824  movzx   eax, [ebp+pguid.Data3]
0x100b1828  mov     [ebp+var_1C], eax
0x100b182b  lea     edx, ds:0FFFFFFFCh[edi*2]
0x100b1832  mov     ecx, edx
0x100b1834  sub     ecx, ebx
0x100b1836  add     ecx, esi
0x100b1838  sar     ecx, 1
0x100b183a  cmp     ecx, 41h ; 'A'
0x100b183d  jge     loc_100B18E7
0x100b1843  push    41h ; 'A'
0x100b1845  pop     eax
0x100b1846  sub     eax, ecx
0x100b1848  add     edx, esi
0x100b184a  movzx   ecx, byte ptr [ebp+var_1C]
0x100b184e  push    eax
0x100b184f  call    MapByteToHexStr
0x100b1854  shr     word ptr [ebp+var_1C], 8
0x100b1859  sub     edi, 2
0x100b185c  test    edi, edi
0x100b185e  jg      short loc_100B182B
0x100b1860  add     esi, 8
0x100b1863  mov     eax, esi
0x100b1865  sub     eax, ebx
0x100b1867  and     eax, 0FFFFFFFEh
0x100b186a  cmp     eax, 82h
0x100b186f  jge     short loc_100B18E7
0x100b1871  xor     eax, eax
0x100b1873  mov     [esi], ax
0x100b1876  jmp     short loc_100B18D2
0x100b1878  and     edi, 0FFFFFFFEh
0x100b187b  cmp     edi, 82h
0x100b1881  jge     short loc_100B18E7
0x100b1883  push    5Fh ; '_'
0x100b1885  pop     eax
0x100b1886  mov     [esi], ax
0x100b1889  lea     eax, [ebp+SystemTimeAsFileTime]
0x100b188c  push    eax; lpSystemTimeAsFileTime
0x100b188d  add     esi, 2
0x100b1890  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x100b1896  lea     eax, [ebp+SystemTimeAsFileTime]
0x100b1899  xor     edi, edi
0x100b189b  mov     [ebp+var_1C], eax
0x100b189e  lea     edx, [edi+edi]
0x100b18a1  mov     ecx, edx
0x100b18a3  sub     ecx, ebx
0x100b18a5  add     ecx, esi
0x100b18a7  sar     ecx, 1
0x100b18a9  cmp     ecx, 41h ; 'A'
0x100b18ac  jge     short loc_100B18E7
0x100b18ae  push    41h ; 'A'
0x100b18b0  pop     eax
0x100b18b1  sub     eax, ecx
0x100b18b3  add     edx, esi
0x100b18b5  push    eax
0x100b18b6  mov     eax, [ebp+var_1C]
0x100b18b9  movzx   ecx, byte ptr [eax]
0x100b18bc  call    MapByteToHexStr
0x100b18c1  inc     [ebp+var_1C]
0x100b18c4  add     edi, 2
0x100b18c7  cmp     edi, 8
0x100b18ca  jb      short loc_100B189E
0x100b18cc  xor     eax, eax
0x100b18ce  mov     [esi+edi*2], ax
0x100b18d2  mov     ecx, esi
0x100b18d4  sub     ecx, ebx
0x100b18d6  sar     ecx, 1
0x100b18d8  push    40h ; '@'
0x100b18da  pop     eax
0x100b18db  sub     eax, ecx
0x100b18dd  xor     ecx, ecx
0x100b18df  mov     [esi+eax*2], cx
0x100b18e3  xor     eax, eax
0x100b18e5  jmp     short loc_100B18EC
0x100b18e7  mov     eax, 0FFFFFBF2h
0x100b18ec  mov     ecx, [ebp+var_8]
0x100b18ef  pop     edi
0x100b18f0  pop     esi
0x100b18f1  xor     ecx, ebp; StackCookie
0x100b18f3  pop     ebx
0x100b18f4  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100b18f9  leave
0x100b18fa  retn    0Ch
```
