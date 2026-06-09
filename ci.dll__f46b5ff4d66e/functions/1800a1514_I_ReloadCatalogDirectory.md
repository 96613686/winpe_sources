# I_ReloadCatalogDirectory

- ea: `0x1800a1514`
- end: `0x1800a1962`
- name: `I_ReloadCatalogDirectory`
- size: `1102`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x180061140`

## callees

- `0x18000c52c`
- `0x1800a1514`
- `0x1800a1968`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a165e`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a165e`
- `ntoskrnl!ExAllocatePool2` at `0x1800a1623`
- `ntoskrnl!ExAllocatePool2` at `0x1800a1623`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a1951`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a1951`
- `ntoskrnl!ZwOpenFile` at `0x1800a15cc`
- `ntoskrnl!ZwOpenFile` at `0x1800a15cc`
- `ntoskrnl!ZwClose` at `0x1800a15e7`
- `ntoskrnl!ZwClose` at `0x1800a15e7`
- `ntoskrnl!qsort` at `0x1800a1746`
- `ntoskrnl!qsort` at `0x1800a1746`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a16b3`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1800a16b3`

## pseudocode

```c
__int64 __fastcall I_ReloadCatalogDirectory(
        int a1,
        char a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        UNICODE_STRING *a7,
        _DWORD *a8)
{
  unsigned int *v8; // rdi
  UNICODE_STRING *v9; // r14
  NTSTATUS v10; // esi
  __int64 Pool2; // rax
  _QWORD *v13; // r12
  unsigned int *v14; // r15
  BOOLEAN RestartScan; // bl
  FILE_INFORMATION_CLASS FileInformationClass; // ecx
  NTSTATUS v17; // eax
  unsigned int *i; // rbx
  __int64 v19; // r14
  unsigned int v20; // eax
  _WORD *j; // rcx
  __int64 v22; // rax
  __int64 k; // r12
  int v24; // eax
  int v25; // eax
  __int64 v26; // rax
  int v27; // eax
  int v28; // eax
  __int64 v29; // [rsp+68h] [rbp-81h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-79h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-71h] BYREF
  PCUNICODE_STRING v32; // [rsp+88h] [rbp-61h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-59h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-19h] BYREF
  int v38; // [rsp+148h] [rbp+5Fh]
  FILE_INFORMATION_CLASS v40; // [rsp+168h] [rbp+7Fh]

  FileHandle = 0;
  LODWORD(v29) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v8 = 0;
  memset(&ObjectAttributes.Length + 1, 0, 20);
  IoStatusBlock = 0;
  DestinationString = 0;
  SourceString = 0;
  CiGetCurrentSiloState();
  v9 = (UNICODE_STRING *)&stru_18002EFE0;
  ObjectAttributes.Length = 48;
  *a8 = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a7 )
    v9 = a7;
  v32 = v9;
  ObjectAttributes.ObjectName = v9;
  v10 = ZwOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4021u);
  if ( v10 >= 0 )
  {
    Pool2 = ExAllocatePool2(258, 155648, 1919109443);
    v8 = (unsigned int *)Pool2;
    if ( Pool2 )
    {
      v10 = 0;
      v13 = (_QWORD *)(Pool2 + 153600);
      v14 = 0;
      v38 = 0;
      RestartScan = 1;
      _InterlockedIncrement(&g_ReloadInProgressCount);
      RtlInitUnicodeString(&DestinationString, L"*.cat");
      FileInformationClass = FileIdFullDirectoryInformation;
LABEL_11:
      while ( 1 )
      {
        v40 = FileInformationClass;
        while ( 1 )
        {
          v17 = ZwQueryDirectoryFile(
                  FileHandle,
                  0,
                  0,
                  0,
                  &IoStatusBlock,
                  v8,
                  0x25800u,
                  FileInformationClass,
                  v14 != 0,
                  &DestinationString,
                  RestartScan);
          if ( v17 < 0 )
            break;
          if ( v14 )
          {
            SourceString.Buffer = (PWSTR)(v14 + 16);
            SourceString.MaximumLength = *((_WORD *)v14 + 30);
            SourceString.Length = SourceString.MaximumLength;
            v27 = I_ReloadCatalog(
                    a1,
                    0,
                    a4,
                    a5,
                    a6,
                    &SourceString,
                    v32,
                    0,
                    0,
                    (__int64)(v14 + 6),
                    (__int64)(v14 + 8),
                    (__int64)&v29);
            if ( v27 < 0 )
            {
              if ( v27 == -1073741801 || v27 == -1073741670 )
                v10 = v27;
            }
            else
            {
              v28 = v29;
              *a8 |= v29;
              if ( v28 )
                ++v38;
            }
          }
          else
          {
            for ( i = v8; ; i = (unsigned int *)((char *)i + v26) )
            {
              v19 = 0;
              while ( 1 )
              {
                if ( a2 )
                {
                  v20 = i[15] >> 1;
                  if ( v20 >= 0xB )
                  {
                    for ( j = i + 20; j < (_WORD *)i + v20 + 30; ++j )
                    {
                      if ( *j == 126 && j[3] == 45 && j[6] == 126 )
                        goto LABEL_26;
                    }
                  }
                }
                v13[v19] = i;
                v19 = (unsigned int)(v19 + 1);
LABEL_26:
                v22 = *i;
                if ( !(_DWORD)v22 || (_DWORD)v19 == 256 )
                  break;
                i = (unsigned int *)((char *)i + v22);
              }
              qsort(v13, (unsigned int)v19, 8u, I_SortDirectoryInfoByFileId);
              for ( k = 0; (unsigned int)k < (unsigned int)v19; k = (unsigned int)(k + 1) )
              {
                SourceString.Buffer = (PWSTR)(*(_QWORD *)&v8[2 * k + 38400] + 80LL);
                SourceString.MaximumLength = *(_WORD *)(*(_QWORD *)&v8[2 * k + 38400] + 60LL);
                SourceString.Length = SourceString.MaximumLength;
                v24 = I_ReloadCatalog(
                        a1,
                        0,
                        a4,
                        a5,
                        a6,
                        &SourceString,
                        v32,
                        (int)FileHandle,
                        (unsigned int)*(_QWORD *)&v8[2 * k + 38400] + 72,
                        *(_QWORD *)&v8[2 * k + 38400] + 24LL,
                        *(_QWORD *)&v8[2 * k + 38400] + 32LL,
                        (__int64)&v29);
                if ( v24 < 0 )
                {
                  if ( !v38 )
                  {
                    FileInformationClass = FileDirectoryInformation;
                    v13 = v8 + 38400;
                    RestartScan = 1;
                    v14 = v8;
                    goto LABEL_11;
                  }
                  if ( v24 == -1073741670 || v24 == -1073741801 )
                    v10 = v24;
                }
                else
                {
                  v25 = v29;
                  *a8 |= v29;
                  if ( v25 )
                    ++v38;
                }
              }
              v26 = *i;
              v13 = v8 + 38400;
              if ( !(_DWORD)v26 )
                break;
            }
          }
          FileInformationClass = v40;
          RestartScan = 0;
        }
        if ( !RestartScan || v14 )
          break;
        v14 = v8;
        FileInformationClass = FileDirectoryInformation;
      }
      if ( v10 >= 0 && (v17 == -1073741801 || v17 == -1073741670) )
        v10 = v17;
      _InterlockedDecrement(&g_ReloadInProgressCount);
    }
    else
    {
      v10 = -1073741801;
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v8 )
    ExFreePoolWithTag(v8, 0x72634943u);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800a1514  mov     rax, rsp
0x1800a1517  mov     [rax+20h], r9d
0x1800a151b  mov     [rax+18h], r8b
0x1800a151f  mov     [rax+10h], dl
0x1800a1522  mov     [rax+8], rcx
0x1800a1526  push    rbp
0x1800a1527  push    rbx
0x1800a1528  push    rsi
0x1800a1529  push    rdi
0x1800a152a  push    r12
0x1800a152c  push    r13
0x1800a152e  push    r14
0x1800a1530  push    r15
0x1800a1532  lea     rbp, [rax-47h]
0x1800a1536  sub     rsp, 0E8h
0x1800a153d  xorps   xmm0, xmm0
0x1800a1540  xor     ebx, ebx
0x1800a1542  xorps   xmm1, xmm1
0x1800a1545  mov     [rbp+3Fh+FileHandle], rbx
0x1800a1549  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.ObjectName], xmm0
0x1800a154d  xor     eax, eax
0x1800a154f  mov     dword ptr [rsp+120h+var_C0], ebx
0x1800a1553  movups  xmmword ptr [rbp+3Fh+ObjectAttributes+1Ch], xmm0
0x1800a1557  mov     edi, ebx
0x1800a1559  movups  xmmword ptr [rbp+3Fh+ObjectAttributes.Length], xmm0
0x1800a155d  movups  xmmword ptr [rbp+3Fh+IoStatusBlock], xmm0
0x1800a1561  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm1
0x1800a1565  movups  xmmword ptr [rbp+3Fh+SourceString.Length], xmm0
0x1800a1569  call    CiGetCurrentSiloState
0x1800a156e  mov     rax, [rbp+3Fh+arg_38]
0x1800a1575  lea     r14, stru_18002EFE0
0x1800a157c  xorps   xmm0, xmm0
0x1800a157f  mov     [rsp+120h+OpenOptions], 4021h; OpenOptions
0x1800a1587  lea     r9, [rbp+3Fh+IoStatusBlock]; IoStatusBlock
0x1800a158b  mov     [rbp+3Fh+ObjectAttributes.Length], 30h ; '0'
0x1800a1592  lea     r8, [rbp+3Fh+ObjectAttributes]; ObjectAttributes
0x1800a1596  mov     [rbp+3Fh+ObjectAttributes.RootDirectory], rbx
0x1800a159a  mov     [rax], ebx
0x1800a159c  lea     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1800a15a0  mov     rax, [rbp+3Fh+arg_30]
0x1800a15a4  mov     edx, 100001h; DesiredAccess
0x1800a15a9  test    rax, rax
0x1800a15ac  mov     [rbp+3Fh+ObjectAttributes.Attributes], 240h
0x1800a15b3  movdqu  xmmword ptr [rbp+3Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800a15b8  cmovnz  r14, rax
0x1800a15bc  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x1800a15c4  mov     [rbp+3Fh+var_A0], r14
0x1800a15c8  mov     [rbp+3Fh+ObjectAttributes.ObjectName], r14
0x1800a15cc  call    cs:__imp_ZwOpenFile
0x1800a15d3  nop     dword ptr [rax+rax+00h]
0x1800a15d8  mov     esi, eax
0x1800a15da  test    eax, eax
0x1800a15dc  jns     short loc_1800A1613
0x1800a15de  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x1800a15e2  test    rcx, rcx
0x1800a15e5  jz      short loc_1800A15F3
0x1800a15e7  call    cs:__imp_ZwClose
0x1800a15ee  nop     dword ptr [rax+rax+00h]
0x1800a15f3  test    rdi, rdi
0x1800a15f6  jnz     loc_1800A1949
0x1800a15fc  mov     eax, esi
0x1800a15fe  add     rsp, 0E8h
0x1800a1605  pop     r15
0x1800a1607  pop     r14
0x1800a1609  pop     r13
0x1800a160b  pop     r12
0x1800a160d  pop     rdi
0x1800a160e  pop     rsi
0x1800a160f  pop     rbx
0x1800a1610  pop     rbp
0x1800a1611  retn
0x1800a1613  mov     edx, 26000h
0x1800a1618  mov     ecx, 102h
0x1800a161d  mov     r8d, 72634943h
0x1800a1623  call    cs:__imp_ExAllocatePool2
0x1800a162a  nop     dword ptr [rax+rax+00h]
0x1800a162f  mov     rdi, rax
0x1800a1632  test    rax, rax
0x1800a1635  jz      loc_1800A1904
0x1800a163b  xor     esi, esi
0x1800a163d  lea     r12, [rax+25800h]
0x1800a1644  xor     r15d, r15d
0x1800a1647  mov     [rbp+3Fh+arg_10], esi
0x1800a164a  mov     bl, 1
0x1800a164c  lock inc cs:g_ReloadInProgressCount
0x1800a1653  lea     rdx, aCat; "*.cat"
0x1800a165a  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x1800a165e  call    cs:__imp_RtlInitUnicodeString
0x1800a1665  nop     dword ptr [rax+rax+00h]
0x1800a166a  lea     ecx, [rsi+26h]
0x1800a166d  mov     r13d, 0C0000017h
0x1800a1673  mov     dword ptr [rbp+3Fh+arg_30], ecx
0x1800a1676  mov     [rsp+120h+RestartScan], bl; RestartScan
0x1800a167a  lea     rdx, [rbp+3Fh+DestinationString]
0x1800a167e  mov     [rsp+120h+FileName], rdx; FileName
0x1800a1683  test    r15, r15
0x1800a1686  setnz   al
0x1800a1689  xor     r9d, r9d; ApcContext
0x1800a168c  mov     [rsp+120h+ReturnSingleEntry], al; ReturnSingleEntry
0x1800a1690  xor     r8d, r8d; ApcRoutine
0x1800a1693  mov     [rsp+120h+FileInformationClass], ecx; FileInformationClass
0x1800a1697  lea     rax, [rbp+3Fh+IoStatusBlock]
0x1800a169b  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x1800a169f  xor     edx, edx; Event
0x1800a16a1  mov     [rsp+120h+Length], 25800h; Length
0x1800a16a9  mov     qword ptr [rsp+120h+OpenOptions], rdi; FileInformation
0x1800a16ae  mov     qword ptr [rsp+120h+ShareAccess], rax; IoStatusBlock
0x1800a16b3  call    cs:__imp_ZwQueryDirectoryFile
0x1800a16ba  nop     dword ptr [rax+rax+00h]
0x1800a16bf  test    eax, eax
0x1800a16c1  js      loc_1800A18DC
0x1800a16c7  test    r15, r15
0x1800a16ca  jnz     loc_1800A184B
0x1800a16d0  mov     rbx, rdi
0x1800a16d3  mov     r13b, [rbp+3Fh+arg_8]
0x1800a16d7  xor     r14d, r14d
0x1800a16da  test    r13b, r13b
0x1800a16dd  jz      short loc_1800A1718
0x1800a16df  mov     eax, [rbx+3Ch]
0x1800a16e2  shr     eax, 1
0x1800a16e4  cmp     eax, 0Bh
0x1800a16e7  jb      short loc_1800A1718
0x1800a16e9  mov     edx, eax
0x1800a16eb  lea     rcx, [rbx+50h]
0x1800a16ef  add     rdx, 0FFFFFFFFFFFFFFF6h
0x1800a16f3  lea     rdx, [rcx+rdx*2]
0x1800a16f7  cmp     rcx, rdx
0x1800a16fa  jnb     short loc_1800A1718
0x1800a16fc  cmp     word ptr [rcx], 7Eh ; '~'
0x1800a1700  jz      short loc_1800A1708
0x1800a1702  add     rcx, 2
0x1800a1706  jmp     short loc_1800A16F7
0x1800a1708  cmp     word ptr [rcx+6], 2Dh ; '-'
0x1800a170d  jnz     short loc_1800A1702
0x1800a170f  cmp     word ptr [rcx+0Ch], 7Eh ; '~'
0x1800a1714  jnz     short loc_1800A1702
0x1800a1716  jmp     short loc_1800A171F
0x1800a1718  mov     [r12+r14*8], rbx
0x1800a171c  inc     r14d
0x1800a171f  mov     eax, [rbx]
0x1800a1721  test    eax, eax
0x1800a1723  jz      short loc_1800A1733
0x1800a1725  cmp     r14d, 100h
0x1800a172c  jz      short loc_1800A1733
0x1800a172e  add     rbx, rax
0x1800a1731  jmp     short loc_1800A16DA
0x1800a1733  mov     edx, r14d; NumOfElements
0x1800a1736  lea     r9, I_SortDirectoryInfoByFileId; PtFuncCompare
0x1800a173d  mov     r8d, 8; SizeOfElements
0x1800a1743  mov     rcx, r12; Base
0x1800a1746  call    cs:__imp_qsort
0x1800a174d  nop     dword ptr [rax+rax+00h]
0x1800a1752  xor     r12d, r12d
0x1800a1755  mov     r13d, 0C0000017h
0x1800a175b  cmp     r12d, r14d
0x1800a175e  jnb     loc_1800A1830
0x1800a1764  mov     r9d, [rbp+3Fh+arg_20]; int
0x1800a1768  lea     r8, [rdi+25800h]
0x1800a176f  mov     rax, [r8+r12*8]
0x1800a1773  add     rax, 50h ; 'P'
0x1800a1777  mov     [rbp+3Fh+SourceString.Buffer], rax
0x1800a177b  mov     rax, [r8+r12*8]
0x1800a177f  movzx   ecx, word ptr [rax+3Ch]
0x1800a1783  mov     [rbp+3Fh+SourceString.MaximumLength], cx
0x1800a1787  mov     [rbp+3Fh+SourceString.Length], cx
0x1800a178b  mov     rax, [r8+r12*8]
0x1800a178f  lea     r8, [rsp+120h+var_C0]
0x1800a1794  mov     [rsp+120h+var_C8], r8; __int64
0x1800a1799  mov     r8d, [rbp+3Fh+arg_18]; int
0x1800a179d  lea     rcx, [rax+20h]
0x1800a17a1  lea     rdx, [rax+18h]
0x1800a17a5  mov     qword ptr [rsp+120h+RestartScan], rcx; __int64
0x1800a17aa  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x1800a17ae  add     rax, 48h ; 'H'
0x1800a17b2  mov     [rsp+120h+FileName], rdx; __int64
0x1800a17b7  xor     edx, edx; int
0x1800a17b9  mov     qword ptr [rsp+120h+ReturnSingleEntry], rax; int
0x1800a17be  mov     rax, [rbp+3Fh+FileHandle]
0x1800a17c2  mov     qword ptr [rsp+120h+FileInformationClass], rax; int
0x1800a17c7  mov     rax, [rbp+3Fh+var_A0]
0x1800a17cb  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x1800a17d0  lea     rax, [rbp+3Fh+SourceString]
0x1800a17d4  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x1800a17d9  mov     eax, [rbp+3Fh+arg_28]
0x1800a17dc  mov     [rsp+120h+ShareAccess], eax; int
0x1800a17e0  call    I_ReloadCatalog
0x1800a17e5  test    eax, eax
0x1800a17e7  js      short loc_1800A1805
0x1800a17e9  mov     eax, dword ptr [rsp+120h+var_C0]
0x1800a17ed  mov     rcx, [rbp+3Fh+arg_38]
0x1800a17f4  or      [rcx], eax
0x1800a17f6  test    eax, eax
0x1800a17f8  jz      short loc_1800A17FD
0x1800a17fa  inc     [rbp+3Fh+arg_10]
0x1800a17fd  inc     r12d
0x1800a1800  jmp     loc_1800A175B
0x1800a1805  cmp     [rbp+3Fh+arg_10], 0
0x1800a1809  jnz     short loc_1800A1821
0x1800a180b  mov     ecx, 1
0x1800a1810  lea     r12, [rdi+25800h]
0x1800a1817  mov     bl, cl
0x1800a1819  mov     r15, rdi
0x1800a181c  jmp     loc_1800A1673
0x1800a1821  cmp     eax, 0C000009Ah
0x1800a1826  jnz     loc_1800A190E
0x1800a182c  mov     esi, eax
0x1800a182e  jmp     short loc_1800A17FD
0x1800a1830  mov     eax, [rbx]
0x1800a1832  lea     r12, [rdi+25800h]
0x1800a1839  test    eax, eax
0x1800a183b  jnz     loc_1800A18FC
0x1800a1841  mov     ecx, dword ptr [rbp+3Fh+arg_30]
0x1800a1844  xor     bl, bl
0x1800a1846  jmp     loc_1800A1676
0x1800a184b  mov     r9d, [rbp+3Fh+arg_20]; int
0x1800a184f  lea     rax, [r15+40h]
0x1800a1853  mov     r8d, [rbp+3Fh+arg_18]; int
0x1800a1857  lea     rdx, [rsp+120h+var_C0]
0x1800a185c  mov     [rsp+120h+var_C8], rdx; __int64
0x1800a1861  lea     rcx, [r15+18h]
0x1800a1865  mov     [rbp+3Fh+SourceString.Buffer], rax
0x1800a1869  xor     edx, edx; int
0x1800a186b  movzx   eax, word ptr [r15+3Ch]
0x1800a1870  mov     [rbp+3Fh+SourceString.MaximumLength], ax
0x1800a1874  mov     [rbp+3Fh+SourceString.Length], ax
0x1800a1878  lea     rax, [r15+20h]
0x1800a187c  mov     qword ptr [rsp+120h+RestartScan], rax; __int64
0x1800a1881  mov     rax, [rbp+3Fh+var_A0]
0x1800a1885  mov     [rsp+120h+FileName], rcx; __int64
0x1800a188a  mov     rcx, qword ptr [rbp+3Fh+arg_0]; int
0x1800a188e  mov     qword ptr [rsp+120h+ReturnSingleEntry], 0; int
0x1800a1897  mov     qword ptr [rsp+120h+FileInformationClass], 0; int
0x1800a18a0  mov     qword ptr [rsp+120h+Length], rax; PCUNICODE_STRING
0x1800a18a5  lea     rax, [rbp+3Fh+SourceString]
0x1800a18a9  mov     qword ptr [rsp+120h+OpenOptions], rax; SourceString
0x1800a18ae  mov     eax, [rbp+3Fh+arg_28]
0x1800a18b1  mov     [rsp+120h+ShareAccess], eax; int
0x1800a18b5  call    I_ReloadCatalog
0x1800a18ba  test    eax, eax
0x1800a18bc  js      short loc_1800A191C
0x1800a18be  mov     eax, dword ptr [rsp+120h+var_C0]
0x1800a18c2  mov     r14, [rbp+3Fh+arg_38]
0x1800a18c9  or      [r14], eax
0x1800a18cc  test    eax, eax
0x1800a18ce  jz      loc_1800A1841
0x1800a18d4  inc     [rbp+3Fh+arg_10]
0x1800a18d7  jmp     loc_1800A1841
0x1800a18dc  test    bl, bl
0x1800a18de  jnz     short loc_1800A1933
0x1800a18e0  test    esi, esi
0x1800a18e2  js      short loc_1800A18F0
0x1800a18e4  cmp     eax, r13d
0x1800a18e7  jz      short loc_1800A1945
0x1800a18e9  cmp     eax, 0C000009Ah
0x1800a18ee  jz      short loc_1800A1945
0x1800a18f0  lock dec cs:g_ReloadInProgressCount
0x1800a18f7  jmp     loc_1800A15DE
0x1800a18fc  add     rbx, rax
0x1800a18ff  jmp     loc_1800A16D3
0x1800a1904  mov     esi, 0C0000017h
0x1800a1909  jmp     loc_1800A15DE
0x1800a190e  cmp     eax, r13d
0x1800a1911  jz      loc_1800A182C
0x1800a1917  jmp     loc_1800A17FD
0x1800a191c  cmp     eax, r13d
0x1800a191f  jz      short loc_1800A192C
0x1800a1921  cmp     eax, 0C000009Ah
0x1800a1926  jnz     loc_1800A1841
0x1800a192c  mov     esi, eax
0x1800a192e  jmp     loc_1800A1841
0x1800a1933  test    r15, r15
0x1800a1936  jnz     short loc_1800A18E0
0x1800a1938  mov     r15, rdi
0x1800a193b  mov     ecx, 1
0x1800a1940  jmp     loc_1800A1673
0x1800a1945  mov     esi, eax
0x1800a1947  jmp     short loc_1800A18F0
0x1800a1949  mov     edx, 72634943h; Tag
0x1800a194e  mov     rcx, rdi; P
0x1800a1951  call    cs:__imp_ExFreePoolWithTag
0x1800a1958  nop     dword ptr [rax+rax+00h]
0x1800a195d  jmp     loc_1800A15FC
```
