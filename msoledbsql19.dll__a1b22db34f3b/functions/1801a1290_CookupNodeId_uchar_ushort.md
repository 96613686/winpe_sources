# CookupNodeId(uchar *,ushort)

- ea: `0x1801a1290`
- end: `0x1801a14af`
- name: `?CookupNodeId@@YAJPEAEG@Z`
- size: `543`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned __int16)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801a16e0`

## callees

- `0x180003d80`
- `0x1801a1290`
- `0x1801a65e1`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1801a1373`
- `KERNEL32!QueryPerformanceCounter` at `0x1801a1373`
- `KERNEL32!GlobalMemoryStatus` at `0x1801a13bc`
- `KERNEL32!GlobalMemoryStatus` at `0x1801a13bc`
- `KERNEL32!GetDiskFreeSpaceA` at `0x1801a1422`
- `KERNEL32!GetDiskFreeSpaceA` at `0x1801a1422`
- `KERNEL32!GetComputerNameW` at `0x1801a131b`
- `KERNEL32!GetComputerNameW` at `0x1801a131b`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x1801a13f0`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x1801a13f0`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a1454`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a1481`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a1454`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1801a1481`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a148d`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1801a148d`

## pseudocode

```c
__int64 __fastcall CookupNodeId(unsigned __int8 *a1, unsigned __int16 a2)
{
  size_t v2; // rdi
  WCHAR *p_Buffer; // r8
  WCHAR v6; // cx
  int v7; // r9d
  __int64 v8; // rax
  unsigned int v9; // edx
  DWORD v10; // ecx
  DWORD nSize; // [rsp+30h] [rbp-49h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-41h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+40h] [rbp-39h] BYREF
  DWORD BytesPerSector; // [rsp+44h] [rbp-35h] BYREF
  DWORD SectorsPerCluster; // [rsp+48h] [rbp-31h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+4Ch] [rbp-2Dh] BYREF
  _MEMORYSTATUS v17; // [rsp+50h] [rbp-29h] BYREF
  _DWORD v18[2]; // [rsp+88h] [rbp+Fh] BYREF
  WCHAR Buffer; // [rsp+90h] [rbp+17h] BYREF
  __int128 v20; // [rsp+92h] [rbp+19h]
  __int64 v21; // [rsp+A2h] [rbp+29h]
  int v22; // [rsp+AAh] [rbp+31h]
  __int16 v23; // [rsp+AEh] [rbp+35h]

  v2 = a2;
  if ( a2 < 6u )
    return 1739;
  memset(v18, 0, 6);
  Buffer = 0;
  PerformanceCount.QuadPart = 0;
  SectorsPerCluster = 0;
  BytesPerSector = 0;
  TotalNumberOfClusters = 0;
  NumberOfFreeClusters = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  nSize = 16;
  memset(&v17, 0, sizeof(v17));
  if ( GetComputerNameW(&Buffer, &nSize) )
  {
    p_Buffer = &Buffer;
    nSize = 0;
    if ( Buffer )
    {
      LOBYTE(v6) = Buffer;
      v7 = 0;
      v8 = 0;
      v9 = 0;
      do
      {
        ++p_Buffer;
        *((_BYTE *)v18 + v9) = *((_BYTE *)v18 + v8) ^ v6;
        v8 = (unsigned int)(v7 + 1);
        nSize = v8;
        v9 = v7 + 1;
        if ( (unsigned int)v8 >= 6 )
        {
          nSize = 0;
          v9 = 0;
          v8 = 0;
        }
        v6 = *p_Buffer;
        v7 = v8;
      }
      while ( *p_Buffer );
    }
  }
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    *(_DWORD *)((char *)v18 + 2) ^= PerformanceCount.HighPart ^ PerformanceCount.LowPart;
    v10 = PerformanceCount.HighPart ^ PerformanceCount.LowPart ^ v18[0];
  }
  else
  {
    v10 = v18[0];
  }
  v17.dwLength = 56;
  v18[0] = ((unsigned int)&v17.dwTotalVirtual + 1 + 15) ^ v10;
  *(_DWORD *)((char *)v18 + 2) ^= (unsigned int)v18;
  GlobalMemoryStatus(&v17);
  v18[0] ^= v17.dwMemoryLoad;
  *(_DWORD *)((char *)v18 + 2) ^= LODWORD(v17.dwTotalPhys);
  v18[0] ^= LODWORD(v17.dwAvailPhys) ^ LODWORD(v17.dwTotalPageFile);
  *(_DWORD *)((char *)v18 + 2) ^= LODWORD(v17.dwAvailPageFile) ^ LODWORD(v17.dwTotalVirtual);
  v18[0] ^= LODWORD(v17.dwAvailVirtual);
  if ( AllocateLocallyUniqueId((PLUID)&PerformanceCount) )
  {
    v18[0] ^= PerformanceCount.LowPart;
    *(_DWORD *)((char *)v18 + 2) ^= PerformanceCount.HighPart;
  }
  if ( GetDiskFreeSpaceA("c:\\", &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters) )
  {
    *(_DWORD *)((char *)v18 + 2) ^= SectorsPerCluster * BytesPerSector * TotalNumberOfClusters;
    v18[0] ^= SectorsPerCluster * BytesPerSector * NumberOfFreeClusters;
  }
  LOBYTE(v18[0]) |= 0x80u;
  if ( !a1 )
  {
    *_errno() = 22;
LABEL_21:
    _invalid_parameter_noinfo();
    return 1824;
  }
  if ( v2 < 6 )
  {
    memset_0(a1, 0, v2);
    *_errno() = 34;
    goto LABEL_21;
  }
  *(_DWORD *)a1 = v18[0];
  *((_WORD *)a1 + 2) = v18[1];
  return 1824;
}

```

## disassembly

```asm
0x1801a1290  push    rbp
0x1801a1292  push    rbx
0x1801a1293  push    rdi
0x1801a1294  lea     rbp, [rsp-47h]
0x1801a1299  sub     rsp, 0C0h
0x1801a12a0  mov     rax, cs:__security_cookie
0x1801a12a7  xor     rax, rsp
0x1801a12aa  mov     [rbp+57h+var_20], rax
0x1801a12ae  movzx   edi, dx
0x1801a12b1  mov     rbx, rcx
0x1801a12b4  cmp     edi, 6
0x1801a12b7  jnb     short loc_1801A12C3
0x1801a12b9  mov     eax, 6CBh
0x1801a12be  jmp     loc_1801A1498
0x1801a12c3  xor     eax, eax
0x1801a12c5  mov     [rsp+0D0h+arg_10], rsi
0x1801a12cd  xor     esi, esi
0x1801a12cf  mov     [rbp+57h+var_48], eax
0x1801a12d2  xorps   xmm0, xmm0
0x1801a12d5  mov     [rbp+57h+Buffer], si
0x1801a12d9  lea     rdx, [rbp+57h+nSize]; nSize
0x1801a12dd  mov     qword ptr [rbp+57h+PerformanceCount], rsi
0x1801a12e1  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1801a12e5  mov     [rbp+57h+SectorsPerCluster], esi
0x1801a12e8  mov     [rbp+57h+BytesPerSector], esi
0x1801a12eb  mov     [rbp+57h+TotalNumberOfClusters], esi
0x1801a12ee  mov     [rbp+57h+NumberOfFreeClusters], esi
0x1801a12f1  mov     [rbp+57h+var_44], ax
0x1801a12f5  movups  [rbp+57h+var_3E], xmm0
0x1801a12f9  mov     [rbp+57h+var_2E], rax
0x1801a12fd  mov     [rbp+57h+var_26], eax
0x1801a1300  mov     [rbp+57h+var_22], ax
0x1801a1304  mov     [rbp+57h+nSize], 10h
0x1801a130b  movups  xmmword ptr [rbp+57h+var_80.dwLength], xmm0
0x1801a130f  mov     [rbp+57h+var_80.dwAvailVirtual], rax
0x1801a1313  movups  xmmword ptr [rbp+57h+var_80.dwAvailPhys], xmm0
0x1801a1317  movups  xmmword ptr [rbp+57h+var_80.dwAvailPageFile], xmm0
0x1801a131b  call    cs:__imp_GetComputerNameW
0x1801a1321  test    eax, eax
0x1801a1323  jz      short loc_1801A136F
0x1801a1325  lea     r8, [rbp+57h+Buffer]
0x1801a1329  mov     [rbp+57h+nSize], esi
0x1801a132c  cmp     [rbp+57h+Buffer], si
0x1801a1330  jz      short loc_1801A136F
0x1801a1332  movzx   ecx, byte ptr [rbp+57h+Buffer]
0x1801a1336  mov     r9d, esi
0x1801a1339  mov     eax, esi
0x1801a133b  mov     edx, esi
0x1801a133d  nop     dword ptr [rax]
0x1801a1340  xor     cl, byte ptr [rbp+rax+57h+var_48]
0x1801a1344  lea     r8, [r8+2]
0x1801a1348  mov     eax, edx
0x1801a134a  mov     byte ptr [rbp+rax+57h+var_48], cl
0x1801a134e  lea     eax, [r9+1]
0x1801a1352  mov     [rbp+57h+nSize], eax
0x1801a1355  mov     edx, eax
0x1801a1357  cmp     eax, 6
0x1801a135a  jb      short loc_1801A1363
0x1801a135c  mov     [rbp+57h+nSize], esi
0x1801a135f  mov     edx, esi
0x1801a1361  mov     eax, esi
0x1801a1363  movzx   ecx, word ptr [r8]
0x1801a1367  mov     r9d, eax
0x1801a136a  test    cx, cx
0x1801a136d  jnz     short loc_1801A1340
0x1801a136f  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x1801a1373  call    cs:__imp_QueryPerformanceCounter
0x1801a1379  mov     rsi, [rsp+0D0h+arg_10]
0x1801a1381  test    eax, eax
0x1801a1383  jz      short loc_1801A139E
0x1801a1385  mov     ecx, [rbp+57h+var_48+2]
0x1801a1388  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x1801a138c  xor     ecx, eax
0x1801a138e  xor     ecx, dword ptr [rbp+57h+PerformanceCount+4]
0x1801a1391  mov     [rbp+57h+var_48+2], ecx
0x1801a1394  mov     ecx, [rbp+57h+var_48]
0x1801a1397  xor     ecx, eax
0x1801a1399  xor     ecx, dword ptr [rbp+57h+PerformanceCount+4]
0x1801a139c  jmp     short loc_1801A13A1
0x1801a139e  mov     ecx, [rbp+57h+var_48]
0x1801a13a1  lea     rax, [rbp+57h+var_48]
0x1801a13a5  mov     [rbp+57h+var_80.dwLength], 38h ; '8'
0x1801a13ac  xor     ecx, eax
0x1801a13ae  lea     rax, [rbp+57h+var_48]
0x1801a13b2  mov     [rbp+57h+var_48], ecx
0x1801a13b5  lea     rcx, [rbp+57h+var_80]; lpBuffer
0x1801a13b9  xor     [rbp+57h+var_48+2], eax
0x1801a13bc  call    cs:__imp_GlobalMemoryStatus
0x1801a13c2  mov     eax, [rbp+57h+var_80.dwMemoryLoad]
0x1801a13c5  lea     rcx, [rbp+57h+PerformanceCount]; Luid
0x1801a13c9  xor     [rbp+57h+var_48], eax
0x1801a13cc  mov     eax, dword ptr [rbp+57h+var_80.dwTotalPhys]
0x1801a13cf  xor     [rbp+57h+var_48+2], eax
0x1801a13d2  mov     eax, [rbp+57h+var_48]
0x1801a13d5  xor     eax, dword ptr [rbp+57h+var_80.dwTotalPageFile]
0x1801a13d8  xor     eax, dword ptr [rbp+57h+var_80.dwAvailPhys]
0x1801a13db  mov     [rbp+57h+var_48], eax
0x1801a13de  mov     eax, [rbp+57h+var_48+2]
0x1801a13e1  xor     eax, dword ptr [rbp+57h+var_80.dwTotalVirtual]
0x1801a13e4  xor     eax, dword ptr [rbp+57h+var_80.dwAvailPageFile]
0x1801a13e7  mov     [rbp+57h+var_48+2], eax
0x1801a13ea  mov     eax, dword ptr [rbp+57h+var_80.dwAvailVirtual]
0x1801a13ed  xor     [rbp+57h+var_48], eax
0x1801a13f0  call    cs:__imp_AllocateLocallyUniqueId
0x1801a13f6  test    eax, eax
0x1801a13f8  jz      short loc_1801A1406
0x1801a13fa  mov     eax, dword ptr [rbp+57h+PerformanceCount]
0x1801a13fd  xor     [rbp+57h+var_48], eax
0x1801a1400  mov     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x1801a1403  xor     [rbp+57h+var_48+2], eax
0x1801a1406  lea     rax, [rbp+57h+TotalNumberOfClusters]
0x1801a140a  lea     r9, [rbp+57h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x1801a140e  mov     [rsp+0D0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1801a1413  lea     r8, [rbp+57h+BytesPerSector]; lpBytesPerSector
0x1801a1417  lea     rdx, [rbp+57h+SectorsPerCluster]; lpSectorsPerCluster
0x1801a141b  lea     rcx, RootPathName; "c:\\"
0x1801a1422  call    cs:__imp_GetDiskFreeSpaceA
0x1801a1428  test    eax, eax
0x1801a142a  jz      short loc_1801A1448
0x1801a142c  mov     eax, [rbp+57h+TotalNumberOfClusters]
0x1801a142f  imul    eax, [rbp+57h+BytesPerSector]
0x1801a1433  imul    eax, [rbp+57h+SectorsPerCluster]
0x1801a1437  xor     [rbp+57h+var_48+2], eax
0x1801a143a  mov     eax, [rbp+57h+NumberOfFreeClusters]
0x1801a143d  imul    eax, [rbp+57h+BytesPerSector]
0x1801a1441  imul    eax, [rbp+57h+SectorsPerCluster]
0x1801a1445  xor     [rbp+57h+var_48], eax
0x1801a1448  or      byte ptr [rbp+57h+var_48], 80h
0x1801a144c  mov     r8, rdi; Size
0x1801a144f  test    rbx, rbx
0x1801a1452  jnz     short loc_1801A1462
0x1801a1454  call    cs:__imp__errno
0x1801a145a  mov     dword ptr [rax], 16h
0x1801a1460  jmp     short loc_1801A148D
0x1801a1462  cmp     r8, 6
0x1801a1466  jb      short loc_1801A1477
0x1801a1468  mov     eax, [rbp+57h+var_48]
0x1801a146b  mov     [rbx], eax
0x1801a146d  movzx   eax, [rbp+57h+var_44]
0x1801a1471  mov     [rbx+4], ax
0x1801a1475  jmp     short loc_1801A1493
0x1801a1477  xor     edx, edx; Val
0x1801a1479  mov     rcx, rbx; void *
0x1801a147c  call    memset_0
0x1801a1481  call    cs:__imp__errno
0x1801a1487  mov     dword ptr [rax], 22h ; '"'
0x1801a148d  call    cs:__imp__invalid_parameter_noinfo
0x1801a1493  mov     eax, 720h
0x1801a1498  mov     rcx, [rbp+57h+var_20]
0x1801a149c  xor     rcx, rsp; StackCookie
0x1801a149f  call    __security_check_cookie
0x1801a14a4  add     rsp, 0C0h
0x1801a14ab  pop     rdi
0x1801a14ac  pop     rbx
0x1801a14ad  pop     rbp
0x1801a14ae  retn
```
