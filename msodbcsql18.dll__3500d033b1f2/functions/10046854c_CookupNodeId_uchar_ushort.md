# CookupNodeId(uchar *,ushort)

- ea: `0x10046854c`
- end: `0x100468711`
- name: `?CookupNodeId@@YAJPEAEG@Z`
- size: `453`
- prototype: `__int64 __fastcall(unsigned __int8 *Destination, unsigned __int16)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100468718`

## callees

- `0x10046854c`
- `0x100548210`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceA` at `0x1004686b0`
- `KERNEL32!GetDiskFreeSpaceA` at `0x1004686b0`
- `KERNEL32!QueryPerformanceCounter` at `0x10046860b`
- `KERNEL32!QueryPerformanceCounter` at `0x10046860b`
- `KERNEL32!GlobalMemoryStatus` at `0x10046864a`
- `KERNEL32!GlobalMemoryStatus` at `0x10046864a`
- `KERNEL32!GetComputerNameW` at `0x1004685b6`
- `KERNEL32!GetComputerNameW` at `0x1004685b6`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x10046867e`
- `ADVAPI32!AllocateLocallyUniqueId` at `0x10046867e`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004686e2`
- `api-ms-win-crt-string-l1-1-0!memcpy_s` at `0x1004686e2`

## pseudocode

```c
__int64 __fastcall CookupNodeId(unsigned __int8 *Destination, unsigned __int16 a2)
{
  rsize_t v2; // rbx
  WCHAR *v5; // rdx
  __int64 v6; // rax
  int v7; // r9d
  unsigned int v8; // r8d
  char v9; // cl
  DWORD v10; // eax
  DWORD nSize; // [rsp+30h] [rbp-49h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-41h] BYREF
  DWORD SectorsPerCluster; // [rsp+40h] [rbp-39h] BYREF
  DWORD BytesPerSector; // [rsp+44h] [rbp-35h] BYREF
  DWORD TotalNumberOfClusters; // [rsp+48h] [rbp-31h] BYREF
  DWORD NumberOfFreeClusters; // [rsp+4Ch] [rbp-2Dh] BYREF
  _MEMORYSTATUS v17; // [rsp+50h] [rbp-29h] BYREF
  _DWORD Source[2]; // [rsp+88h] [rbp+Fh] BYREF
  WCHAR Buffer[8]; // [rsp+90h] [rbp+17h] BYREF
  __int128 v20; // [rsp+A0h] [rbp+27h]

  v2 = a2;
  if ( a2 < 6u )
    return 1739;
  _mm_lfence();
  nSize = 16;
  memset(Source, 0, 6);
  *(_OWORD *)Buffer = 0;
  v20 = 0;
  if ( GetComputerNameW(Buffer, &nSize) )
  {
    v5 = Buffer;
    nSize = 0;
    if ( Buffer[0] )
    {
      v6 = 0;
      v7 = 0;
      v8 = 0;
      do
      {
        v9 = *(_BYTE *)v5++ ^ *((_BYTE *)Source + v6);
        *((_BYTE *)Source + v8) = v9;
        v6 = (unsigned int)(v7 + 1);
        nSize = v6;
        v8 = v7 + 1;
        if ( (unsigned int)v6 >= 6 )
        {
          nSize = 0;
          v8 = 0;
          v6 = 0;
        }
        v7 = v6;
      }
      while ( *v5 );
    }
  }
  if ( QueryPerformanceCounter(&PerformanceCount) )
  {
    *(_DWORD *)((char *)Source + 2) ^= PerformanceCount.HighPart ^ PerformanceCount.LowPart;
    v10 = PerformanceCount.HighPart ^ PerformanceCount.LowPart ^ Source[0];
  }
  else
  {
    v10 = Source[0];
  }
  v17.dwLength = 56;
  Source[0] = ((unsigned int)&v17.dwTotalVirtual + 1 + 15) ^ v10;
  *(_DWORD *)((char *)Source + 2) ^= (unsigned int)Source;
  GlobalMemoryStatus(&v17);
  Source[0] ^= v17.dwMemoryLoad;
  *(_DWORD *)((char *)Source + 2) ^= LODWORD(v17.dwTotalPhys);
  Source[0] ^= LODWORD(v17.dwAvailPhys) ^ LODWORD(v17.dwTotalPageFile);
  *(_DWORD *)((char *)Source + 2) ^= LODWORD(v17.dwAvailPageFile) ^ LODWORD(v17.dwTotalVirtual);
  Source[0] ^= LODWORD(v17.dwAvailVirtual);
  if ( AllocateLocallyUniqueId((PLUID)&PerformanceCount) )
  {
    Source[0] ^= PerformanceCount.LowPart;
    *(_DWORD *)((char *)Source + 2) ^= PerformanceCount.HighPart;
  }
  if ( GetDiskFreeSpaceA("c:\\", &SectorsPerCluster, &BytesPerSector, &NumberOfFreeClusters, &TotalNumberOfClusters) )
  {
    *(_DWORD *)((char *)Source + 2) ^= TotalNumberOfClusters * BytesPerSector * SectorsPerCluster;
    Source[0] ^= NumberOfFreeClusters * BytesPerSector * SectorsPerCluster;
  }
  LOBYTE(Source[0]) |= 0x80u;
  memcpy_s(Destination, v2, Source, 6u);
  return 1824;
}

```

## disassembly

```asm
0x10046854c  mov     [rsp-8+arg_10], rbx
0x100468551  mov     [rsp-8+arg_18], rsi
0x100468556  push    rbp
0x100468557  push    rdi
0x100468558  push    r14
0x10046855a  lea     rbp, [rsp-47h]
0x10046855f  sub     rsp, 0C0h
0x100468566  mov     rax, cs:__security_cookie
0x10046856d  xor     rax, rsp
0x100468570  mov     [rbp+57h+var_20], rax
0x100468574  movzx   ebx, dx
0x100468577  mov     r14d, 6
0x10046857d  mov     rdi, rcx
0x100468580  cmp     bx, r14w
0x100468584  jnb     short loc_100468590
0x100468586  mov     eax, 6CBh
0x10046858b  jmp     loc_1004686ED
0x100468590  lfence
0x100468593  xor     eax, eax
0x100468595  mov     [rbp+57h+nSize], 10h
0x10046859c  xorps   xmm0, xmm0
0x10046859f  mov     [rbp+57h+Source], eax
0x1004685a2  lea     rdx, [rbp+57h+nSize]; nSize
0x1004685a6  mov     [rbp+57h+var_44], ax
0x1004685aa  lea     rcx, [rbp+57h+Buffer]; lpBuffer
0x1004685ae  movups  xmmword ptr [rbp+57h+Buffer], xmm0
0x1004685b2  movups  [rbp+57h+var_30], xmm0
0x1004685b6  call    cs:__imp_GetComputerNameW
0x1004685bc  xor     esi, esi
0x1004685be  test    eax, eax
0x1004685c0  jz      short loc_100468607
0x1004685c2  lea     rdx, [rbp+57h+Buffer]
0x1004685c6  mov     [rbp+57h+nSize], esi
0x1004685c9  cmp     [rbp+57h+Buffer], si
0x1004685cd  jz      short loc_100468607
0x1004685cf  mov     eax, esi
0x1004685d1  mov     r9d, esi
0x1004685d4  mov     r8d, esi
0x1004685d7  mov     cl, byte ptr [rbp+rax+57h+Source]
0x1004685db  xor     cl, [rdx]
0x1004685dd  lea     rdx, [rdx+2]
0x1004685e1  mov     eax, r8d
0x1004685e4  mov     byte ptr [rbp+rax+57h+Source], cl
0x1004685e8  lea     eax, [r9+1]
0x1004685ec  mov     [rbp+57h+nSize], eax
0x1004685ef  mov     r8d, eax
0x1004685f2  cmp     eax, r14d
0x1004685f5  jb      short loc_1004685FF
0x1004685f7  mov     [rbp+57h+nSize], esi
0x1004685fa  mov     r8d, esi
0x1004685fd  mov     eax, esi
0x1004685ff  mov     r9d, eax
0x100468602  cmp     [rdx], si
0x100468605  jnz     short loc_1004685D7
0x100468607  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x10046860b  call    cs:__imp_QueryPerformanceCounter
0x100468611  test    eax, eax
0x100468613  jz      short loc_10046862C
0x100468615  mov     eax, [rbp+57h+Source+2]
0x100468618  xor     eax, dword ptr [rbp+57h+PerformanceCount]
0x10046861b  xor     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x10046861e  mov     [rbp+57h+Source+2], eax
0x100468621  mov     eax, [rbp+57h+Source]
0x100468624  xor     eax, dword ptr [rbp+57h+PerformanceCount]
0x100468627  xor     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x10046862a  jmp     short loc_10046862F
0x10046862c  mov     eax, [rbp+57h+Source]
0x10046862f  lea     rcx, [rbp+57h+Source]
0x100468633  mov     [rbp+57h+var_80.dwLength], 38h ; '8'
0x10046863a  xor     eax, ecx
0x10046863c  lea     rcx, [rbp+57h+var_80]; lpBuffer
0x100468640  mov     [rbp+57h+Source], eax
0x100468643  lea     rax, [rbp+57h+Source]
0x100468647  xor     [rbp+57h+Source+2], eax
0x10046864a  call    cs:__imp_GlobalMemoryStatus
0x100468650  mov     eax, [rbp+57h+var_80.dwMemoryLoad]
0x100468653  lea     rcx, [rbp+57h+PerformanceCount]; Luid
0x100468657  xor     [rbp+57h+Source], eax
0x10046865a  mov     eax, dword ptr [rbp+57h+var_80.dwTotalPhys]
0x10046865d  xor     [rbp+57h+Source+2], eax
0x100468660  mov     eax, [rbp+57h+Source]
0x100468663  xor     eax, dword ptr [rbp+57h+var_80.dwTotalPageFile]
0x100468666  xor     eax, dword ptr [rbp+57h+var_80.dwAvailPhys]
0x100468669  mov     [rbp+57h+Source], eax
0x10046866c  mov     eax, [rbp+57h+Source+2]
0x10046866f  xor     eax, dword ptr [rbp+57h+var_80.dwTotalVirtual]
0x100468672  xor     eax, dword ptr [rbp+57h+var_80.dwAvailPageFile]
0x100468675  mov     [rbp+57h+Source+2], eax
0x100468678  mov     eax, dword ptr [rbp+57h+var_80.dwAvailVirtual]
0x10046867b  xor     [rbp+57h+Source], eax
0x10046867e  call    cs:__imp_AllocateLocallyUniqueId
0x100468684  test    eax, eax
0x100468686  jz      short loc_100468694
0x100468688  mov     eax, dword ptr [rbp+57h+PerformanceCount]
0x10046868b  xor     [rbp+57h+Source], eax
0x10046868e  mov     eax, dword ptr [rbp+57h+PerformanceCount+4]
0x100468691  xor     [rbp+57h+Source+2], eax
0x100468694  lea     rax, [rbp+57h+TotalNumberOfClusters]
0x100468698  lea     r9, [rbp+57h+NumberOfFreeClusters]; lpNumberOfFreeClusters
0x10046869c  mov     [rsp+0D0h+lpTotalNumberOfClusters], rax; lpTotalNumberOfClusters
0x1004686a1  lea     r8, [rbp+57h+BytesPerSector]; lpBytesPerSector
0x1004686a5  lea     rdx, [rbp+57h+SectorsPerCluster]; lpSectorsPerCluster
0x1004686a9  lea     rcx, RootPathName; "c:\\"
0x1004686b0  call    cs:__imp_GetDiskFreeSpaceA
0x1004686b6  test    eax, eax
0x1004686b8  jz      short loc_1004686D1
0x1004686ba  mov     edx, [rbp+57h+SectorsPerCluster]
0x1004686bd  imul    edx, [rbp+57h+BytesPerSector]
0x1004686c1  mov     eax, edx
0x1004686c3  imul    edx, [rbp+57h+NumberOfFreeClusters]
0x1004686c7  imul    eax, [rbp+57h+TotalNumberOfClusters]
0x1004686cb  xor     [rbp+57h+Source+2], eax
0x1004686ce  xor     [rbp+57h+Source], edx
0x1004686d1  or      byte ptr [rbp+57h+Source], 80h
0x1004686d5  lea     r8, [rbp+57h+Source]; Source
0x1004686d9  mov     rdx, rbx; DestinationSize
0x1004686dc  mov     r9, r14; SourceSize
0x1004686df  mov     rcx, rdi; Destination
0x1004686e2  call    cs:__imp_memcpy_s
0x1004686e8  mov     eax, 720h
0x1004686ed  mov     rcx, [rbp+57h+var_20]
0x1004686f1  xor     rcx, rsp; StackCookie
0x1004686f4  call    __security_check_cookie
0x1004686f9  lea     r11, [rsp+0D0h+var_10]
0x100468701  mov     rbx, [r11+30h]
0x100468705  mov     rsi, [r11+38h]
0x100468709  mov     rsp, r11
0x10046870c  pop     r14
0x10046870e  pop     rdi
0x10046870f  pop     rbp
0x100468710  retn
```
