# ErrUniqueName(x,x,x,x,x)

- ea: `0x100b1546`
- end: `0x100b176e`
- name: `_ErrUniqueName@20`
- size: `552`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x10032f00`
- `0x100a2e8a`
- `0x100b1774`
- `0x100cf9f4`

## callees

- `0x10016ed0`
- `0x100b1501`
- `0x100b1546`
- `0x10122f60`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x100b1701`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x100b1701`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100b15a6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x100b15a6`

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
0x100b1546  mov     edi, edi
0x100b1548  push    ebp
0x100b1549  mov     ebp, esp
0x100b154b  sub     esp, 28h
0x100b154e  mov     eax, ___security_cookie
0x100b1553  xor     eax, ebp
0x100b1555  mov     [ebp+var_8], eax
0x100b1558  push    ebx
0x100b1559  push    esi
0x100b155a  mov     esi, [ebp+arg_0]
0x100b155d  mov     ebx, esi
0x100b155f  push    edi
0x100b1560  test    esi, esi
0x100b1562  jz      loc_100B1758
0x100b1568  test    edx, edx
0x100b156a  jz      short loc_100B1577
0x100b156c  push    41h ; 'A'
0x100b156e  mov     ecx, esi
0x100b1570  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100b1575  jmp     short loc_100B157C
0x100b1577  xor     eax, eax
0x100b1579  mov     [esi], ax
0x100b157c  mov     ecx, esi
0x100b157e  xor     edi, edi
0x100b1580  lea     edx, [ecx+2]
0x100b1583  mov     ax, [ecx]
0x100b1586  add     ecx, 2
0x100b1589  cmp     ax, di
0x100b158c  jnz     short loc_100B1583
0x100b158e  sub     ecx, edx
0x100b1590  sar     ecx, 1
0x100b1592  cmp     [ebp+arg_8], 0
0x100b1596  lea     esi, [esi+ecx*2]
0x100b1599  lea     edi, [ecx+ecx]
0x100b159c  jz      loc_100B16E9
0x100b15a2  lea     eax, [ebp+pguid]
0x100b15a5  push    eax; pguid
0x100b15a6  call    ds:__imp__CoCreateGuid@4; CoCreateGuid(x)
0x100b15ac  test    eax, eax
0x100b15ae  jns     short loc_100B15BA
0x100b15b0  mov     eax, 0FFFFFC0Dh
0x100b15b5  jmp     loc_100B175D
0x100b15ba  and     edi, 0FFFFFFFEh
0x100b15bd  cmp     edi, 82h
0x100b15c3  jge     loc_100B1758
0x100b15c9  push    5Fh ; '_'
0x100b15cb  pop     eax
0x100b15cc  mov     [esi], ax
0x100b15cf  add     esi, 2
0x100b15d2  mov     eax, [ebp+pguid.Data1]
0x100b15d5  push    8
0x100b15d7  mov     [ebp+var_1C], eax
0x100b15da  pop     edi
0x100b15db  lea     edx, ds:0FFFFFFFCh[edi*2]
0x100b15e2  mov     ecx, edx
0x100b15e4  sub     ecx, ebx
0x100b15e6  add     ecx, esi
0x100b15e8  sar     ecx, 1
0x100b15ea  cmp     ecx, 41h ; 'A'
0x100b15ed  jge     loc_100B1758
0x100b15f3  push    41h ; 'A'
0x100b15f5  pop     eax
0x100b15f6  sub     eax, ecx
0x100b15f8  add     edx, esi
0x100b15fa  push    eax
0x100b15fb  mov     eax, [ebp+var_1C]
0x100b15fe  movzx   ecx, al
0x100b1601  call    MapByteToHexStr
0x100b1606  shr     [ebp+var_1C], 8
0x100b160a  sub     edi, 2
0x100b160d  test    edi, edi
0x100b160f  jg      short loc_100B15DB
0x100b1611  lea     eax, [esi+10h]
0x100b1614  sub     eax, ebx
0x100b1616  and     eax, 0FFFFFFFEh
0x100b1619  cmp     eax, 82h
0x100b161e  jge     loc_100B1758
0x100b1624  push    5Fh ; '_'
0x100b1626  pop     eax
0x100b1627  mov     [esi+10h], ax
0x100b162b  add     esi, 12h
0x100b162e  movzx   eax, [ebp+pguid.Data2]
0x100b1632  push    4
0x100b1634  pop     edi
0x100b1635  mov     [ebp+var_1C], eax
0x100b1638  mov     eax, edi
0x100b163a  mov     [ebp+SystemTimeAsFileTime.dwHighDateTime], edi
0x100b163d  lea     edx, ds:0FFFFFFFCh[eax*2]
0x100b1644  mov     ecx, edx
0x100b1646  sub     ecx, ebx
0x100b1648  add     ecx, esi
0x100b164a  sar     ecx, 1
0x100b164c  cmp     ecx, 41h ; 'A'
0x100b164f  jge     loc_100B1758
0x100b1655  push    41h ; 'A'
0x100b1657  pop     eax
0x100b1658  sub     eax, ecx
0x100b165a  add     edx, esi
0x100b165c  movzx   ecx, byte ptr [ebp+var_1C]
0x100b1660  push    eax
0x100b1661  call    MapByteToHexStr
0x100b1666  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x100b1669  shr     word ptr [ebp+var_1C], 8
0x100b166e  sub     eax, 2
0x100b1671  mov     [ebp+SystemTimeAsFileTime.dwHighDateTime], eax
0x100b1674  test    eax, eax
0x100b1676  jg      short loc_100B163D
0x100b1678  lea     eax, [esi+8]
0x100b167b  sub     eax, ebx
0x100b167d  and     eax, 0FFFFFFFEh
0x100b1680  cmp     eax, 82h
0x100b1685  jge     loc_100B1758
0x100b168b  push    5Fh ; '_'
0x100b168d  pop     eax
0x100b168e  mov     [esi+8], ax
0x100b1692  add     esi, 0Ah
0x100b1695  movzx   eax, [ebp+pguid.Data3]
0x100b1699  mov     [ebp+var_1C], eax
0x100b169c  lea     edx, ds:0FFFFFFFCh[edi*2]
0x100b16a3  mov     ecx, edx
0x100b16a5  sub     ecx, ebx
0x100b16a7  add     ecx, esi
0x100b16a9  sar     ecx, 1
0x100b16ab  cmp     ecx, 41h ; 'A'
0x100b16ae  jge     loc_100B1758
0x100b16b4  push    41h ; 'A'
0x100b16b6  pop     eax
0x100b16b7  sub     eax, ecx
0x100b16b9  add     edx, esi
0x100b16bb  movzx   ecx, byte ptr [ebp+var_1C]
0x100b16bf  push    eax
0x100b16c0  call    MapByteToHexStr
0x100b16c5  shr     word ptr [ebp+var_1C], 8
0x100b16ca  sub     edi, 2
0x100b16cd  test    edi, edi
0x100b16cf  jg      short loc_100B169C
0x100b16d1  add     esi, 8
0x100b16d4  mov     eax, esi
0x100b16d6  sub     eax, ebx
0x100b16d8  and     eax, 0FFFFFFFEh
0x100b16db  cmp     eax, 82h
0x100b16e0  jge     short loc_100B1758
0x100b16e2  xor     eax, eax
0x100b16e4  mov     [esi], ax
0x100b16e7  jmp     short loc_100B1743
0x100b16e9  and     edi, 0FFFFFFFEh
0x100b16ec  cmp     edi, 82h
0x100b16f2  jge     short loc_100B1758
0x100b16f4  push    5Fh ; '_'
0x100b16f6  pop     eax
0x100b16f7  mov     [esi], ax
0x100b16fa  lea     eax, [ebp+SystemTimeAsFileTime]
0x100b16fd  push    eax; lpSystemTimeAsFileTime
0x100b16fe  add     esi, 2
0x100b1701  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x100b1707  lea     eax, [ebp+SystemTimeAsFileTime]
0x100b170a  xor     edi, edi
0x100b170c  mov     [ebp+var_1C], eax
0x100b170f  lea     edx, [edi+edi]
0x100b1712  mov     ecx, edx
0x100b1714  sub     ecx, ebx
0x100b1716  add     ecx, esi
0x100b1718  sar     ecx, 1
0x100b171a  cmp     ecx, 41h ; 'A'
0x100b171d  jge     short loc_100B1758
0x100b171f  push    41h ; 'A'
0x100b1721  pop     eax
0x100b1722  sub     eax, ecx
0x100b1724  add     edx, esi
0x100b1726  push    eax
0x100b1727  mov     eax, [ebp+var_1C]
0x100b172a  movzx   ecx, byte ptr [eax]
0x100b172d  call    MapByteToHexStr
0x100b1732  inc     [ebp+var_1C]
0x100b1735  add     edi, 2
0x100b1738  cmp     edi, 8
0x100b173b  jb      short loc_100B170F
0x100b173d  xor     eax, eax
0x100b173f  mov     [esi+edi*2], ax
0x100b1743  mov     ecx, esi
0x100b1745  sub     ecx, ebx
0x100b1747  sar     ecx, 1
0x100b1749  push    40h ; '@'
0x100b174b  pop     eax
0x100b174c  sub     eax, ecx
0x100b174e  xor     ecx, ecx
0x100b1750  mov     [esi+eax*2], cx
0x100b1754  xor     eax, eax
0x100b1756  jmp     short loc_100B175D
0x100b1758  mov     eax, 0FFFFFBF2h
0x100b175d  mov     ecx, [ebp+var_8]
0x100b1760  pop     edi
0x100b1761  pop     esi
0x100b1762  xor     ecx, ebp; StackCookie
0x100b1764  pop     ebx
0x100b1765  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100b176a  leave
0x100b176b  retn    0Ch
```
