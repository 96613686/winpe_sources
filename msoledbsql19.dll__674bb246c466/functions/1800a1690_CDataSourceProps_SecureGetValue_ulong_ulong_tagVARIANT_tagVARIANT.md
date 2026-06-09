# CDataSourceProps::SecureGetValue(ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1800a1690`
- end: `0x1800a1833`
- name: `?SecureGetValue@CDataSourceProps@@UEAAJKKPEAUtagVARIANT@@0@Z`
- size: `419`
- prototype: `int(CDataSourceProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800030c0`
- `0x1800a1690`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a17f2`
- `KERNEL32!GetLastError` at `0x1800a17f2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a17b2`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a17b2`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a17be`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a17be`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a17d5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a17d5`
- `OLEAUT32!__imp_VariantClear` at `0x1800a1720`
- `OLEAUT32!__imp_VariantClear` at `0x1800a1720`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a16be`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a16be`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a174d`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a174d`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800a1780`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800a1780`

## pseudocode

```c
__int64 __fastcall CDataSourceProps::SecureGetValue(
        CDataSourceProps *this,
        int a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvargSrc)
{
  unsigned int v9; // ebx
  UINT *pulVal; // rsi
  UINT v11; // eax
  unsigned __int64 v12; // r14
  UINT v13; // r15d
  BSTR v14; // rax
  LONGLONG v15; // rdi
  DWORD LastError; // eax

  v9 = VariantCopy(a4, pvargSrc);
  if ( (v9 & 0x80000000) == 0 && pvargSrc->vt == 8 )
  {
    if ( a2 )
    {
      if ( a2 != 1 || a3 != 14 && a3 != 23 )
        return v9;
    }
    else if ( a3 != 1 && a3 != 10 )
    {
      return v9;
    }
    _mm_lfence();
    pulVal = a4->pulVal;
    if ( (*(_BYTE *)(*((_QWORD *)this + 72) + 280LL) & 4) != 0 )
    {
      _mm_lfence();
      VariantClear(a4);
      a4->llVal = 0;
      return v9;
    }
    if ( pulVal )
    {
      if ( g_pfnCryptUnprotectMemory )
      {
        v11 = SysStringByteLen(a4->bstrVal);
        v12 = v11;
        if ( v11 )
        {
          if ( (unsigned int)((__int64 (__fastcall *)(UINT *, _QWORD, _QWORD))g_pfnCryptUnprotectMemory)(pulVal, v11, 0) )
          {
            v13 = *pulVal;
            v14 = SysAllocStringByteLen(0, *pulVal);
            v15 = (LONGLONG)v14;
            if ( v14 )
            {
              if ( v13 )
              {
                if ( pulVal == (UINT *)-4LL )
                {
                  memset_0(v14, 0, v13);
                  *_errno() = 22;
                  _invalid_parameter_noinfo();
                }
                else
                {
                  memcpy_0(v14, pulVal + 1, v13);
                }
              }
              a4->llVal = v15;
              memset(pulVal, 0, v12);
              SysFreeString((BSTR)pulVal);
              return v9;
            }
          }
          else if ( (bidGblFlags & 2) != 0 && off_180263178[0] )
          {
            LastError = GetLastError();
            bidTraceW(off_180260410[0], 3996672, off_180263178[0], LastError);
          }
          return (unsigned int)-2147467259;
        }
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x1800a1690  mov     [rsp+arg_0], rbx
0x1800a1695  mov     [rsp+arg_8], rbp
0x1800a169a  mov     [rsp+arg_10], rsi
0x1800a169f  push    rdi
0x1800a16a0  push    r14
0x1800a16a2  push    r15
0x1800a16a4  sub     rsp, 20h
0x1800a16a8  mov     r14, [rsp+38h+pvargSrc]
0x1800a16ad  mov     esi, edx
0x1800a16af  mov     r15, rcx
0x1800a16b2  mov     rdx, r14; pvargSrc
0x1800a16b5  mov     rcx, r9; pvargDest
0x1800a16b8  mov     rbp, r9
0x1800a16bb  mov     edi, r8d
0x1800a16be  call    cs:__imp_VariantCopy
0x1800a16c4  mov     ebx, eax
0x1800a16c6  test    eax, eax
0x1800a16c8  js      loc_1800A1818
0x1800a16ce  cmp     word ptr [r14], 8
0x1800a16d3  jnz     loc_1800A1818
0x1800a16d9  test    esi, esi
0x1800a16db  jnz     short loc_1800A16EC
0x1800a16dd  cmp     edi, 1
0x1800a16e0  jz      short loc_1800A1703
0x1800a16e2  cmp     edi, 0Ah
0x1800a16e5  jz      short loc_1800A1703
0x1800a16e7  jmp     loc_1800A1818
0x1800a16ec  cmp     esi, 1
0x1800a16ef  jnz     loc_1800A1818
0x1800a16f5  cmp     edi, 0Eh
0x1800a16f8  jz      short loc_1800A1703
0x1800a16fa  cmp     edi, 17h
0x1800a16fd  jnz     loc_1800A1818
0x1800a1703  lfence
0x1800a1706  mov     rax, [r15+240h]
0x1800a170d  mov     rsi, [rbp+8]
0x1800a1711  test    byte ptr [rax+118h], 4
0x1800a1718  jz      short loc_1800A1733
0x1800a171a  lfence
0x1800a171d  mov     rcx, rbp; pvarg
0x1800a1720  call    cs:__imp_VariantClear
0x1800a1726  mov     qword ptr [rbp+8], 0
0x1800a172e  jmp     loc_1800A1818
0x1800a1733  test    rsi, rsi
0x1800a1736  jz      loc_1800A1818
0x1800a173c  cmp     cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x1800a1744  jz      loc_1800A1818
0x1800a174a  mov     rcx, rsi; bstr
0x1800a174d  call    cs:__imp_SysStringByteLen
0x1800a1753  mov     r14d, eax
0x1800a1756  test    eax, eax
0x1800a1758  jz      loc_1800A1818
0x1800a175e  mov     rax, cs:?g_pfnCryptUnprotectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptUnprotectMemory)(void *,ulong,ulong)
0x1800a1765  xor     r8d, r8d
0x1800a1768  mov     edx, r14d
0x1800a176b  mov     rcx, rsi
0x1800a176e  call    cs:__guard_dispatch_icall_fptr
0x1800a1774  test    eax, eax
0x1800a1776  jz      short loc_1800A17DD
0x1800a1778  mov     r15d, [rsi]
0x1800a177b  xor     ecx, ecx; psz
0x1800a177d  mov     edx, r15d; len
0x1800a1780  call    cs:__imp_SysAllocStringByteLen
0x1800a1786  mov     rdi, rax
0x1800a1789  test    rax, rax
0x1800a178c  jz      loc_1800A1813
0x1800a1792  lea     rdx, [rsi+4]; Src
0x1800a1796  mov     r8d, r15d; Size
0x1800a1799  test    r15d, r15d
0x1800a179c  jz      short loc_1800A17C4
0x1800a179e  mov     rcx, rax; void *
0x1800a17a1  test    rdx, rdx
0x1800a17a4  jz      short loc_1800A17AD
0x1800a17a6  call    memcpy_0
0x1800a17ab  jmp     short loc_1800A17C4
0x1800a17ad  call    memset_0
0x1800a17b2  call    cs:__imp__errno
0x1800a17b8  mov     dword ptr [rax], 16h
0x1800a17be  call    cs:__imp__invalid_parameter_noinfo
0x1800a17c4  mov     [rbp+8], rdi
0x1800a17c8  xor     eax, eax
0x1800a17ca  mov     rdi, rsi
0x1800a17cd  mov     rcx, r14
0x1800a17d0  rep stosb
0x1800a17d2  mov     rcx, rsi; bstrString
0x1800a17d5  call    cs:__imp_SysFreeString
0x1800a17db  jmp     short loc_1800A1818
0x1800a17dd  test    byte ptr cs:_bidGblFlags, 2
0x1800a17e4  jz      short loc_1800A1813
0x1800a17e6  mov     rax, cs:off_180263178; "<CDataSourceProps::SecureGetValue|ERR|S"...
0x1800a17ed  test    rax, rax
0x1800a17f0  jz      short loc_1800A1813
0x1800a17f2  call    cs:__imp_GetLastError
0x1800a17f8  mov     r8, cs:off_180263178; "<CDataSourceProps::SecureGetValue|ERR|S"...
0x1800a17ff  mov     edx, 3CFC00h
0x1800a1804  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a180b  mov     r9d, eax
0x1800a180e  call    _bidTraceW
0x1800a1813  mov     ebx, 80004005h
0x1800a1818  mov     rbp, [rsp+38h+arg_8]
0x1800a181d  mov     eax, ebx
0x1800a181f  mov     rbx, [rsp+38h+arg_0]
0x1800a1824  mov     rsi, [rsp+38h+arg_10]
0x1800a1829  add     rsp, 20h
0x1800a182d  pop     r15
0x1800a182f  pop     r14
0x1800a1831  pop     rdi
0x1800a1832  retn
```
