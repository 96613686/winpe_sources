# CDataSourceProps::SecureSetValue(ulong,ulong,tagVARIANT *,tagVARIANT *)

- ea: `0x1800a1840`
- end: `0x1800a1a1b`
- name: `?SecureSetValue@CDataSourceProps@@UEAAJKKPEAUtagVARIANT@@0@Z`
- size: `475`
- prototype: `int(CDataSourceProps *__hidden this, unsigned int, unsigned int, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800030c0`
- `0x1800a1840`
- `0x1801a65e1`
- `0x1801a65f0`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800a1985`
- `KERNEL32!GetLastError` at `0x1800a1985`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a192d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a1940`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a192d`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1800a1940`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a194c`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1800a194c`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a19a9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a19a9`
- `OLEAUT32!__imp_VariantClear` at `0x1800a19d4`
- `OLEAUT32!__imp_VariantClear` at `0x1800a19d4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a19f4`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a1876`
- `OLEAUT32!__imp_VariantCopy` at `0x1800a19f4`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a18c0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1800a18c0`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800a18dd`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1800a18dd`

## pseudocode

```c
int __fastcall CDataSourceProps::SecureSetValue(
        CDataSourceProps *this,
        int a2,
        int a3,
        struct tagVARIANT *a4,
        struct tagVARIANT *pvargSrc)
{
  int result; // eax
  OLECHAR *bstrVal; // rbp
  UINT v9; // eax
  __int64 v10; // rsi
  UINT v11; // edi
  BSTR v12; // rax
  OLECHAR *v13; // rbx
  size_t v14; // rsi
  DWORD LastError; // eax
  __int64 v16; // rdx
  int v17; // ecx

  if ( pvargSrc->vt != 8 )
    return VariantCopy(a4, pvargSrc);
  if ( a2 )
  {
    if ( a2 != 1 || a3 != 14 && a3 != 23 )
      return VariantCopy(a4, pvargSrc);
  }
  else if ( a3 != 1 && a3 != 10 )
  {
    return VariantCopy(a4, pvargSrc);
  }
  bstrVal = pvargSrc->bstrVal;
  if ( !bstrVal || !g_pfnCryptProtectMemory )
  {
    result = VariantCopy(a4, pvargSrc);
    if ( result < 0 )
      return result;
    goto LABEL_31;
  }
  v9 = SysStringByteLen(bstrVal);
  v10 = v9;
  v11 = (v9 + 19) & 0xFFFFFFF0;
  if ( v11 < v9 )
    return -2147024882;
  _mm_lfence();
  v12 = SysAllocStringByteLen(0, v11);
  v13 = v12;
  if ( !v12 )
    return -2147024882;
  v14 = v10 + 4;
  if ( bstrVal == (OLECHAR *)4 || v11 < v14 )
  {
    memset_0(v12, 0, v11);
    if ( bstrVal == (OLECHAR *)4 )
    {
      *_errno() = 22;
    }
    else
    {
      if ( v11 >= v14 )
        goto LABEL_21;
      *_errno() = 34;
    }
    _invalid_parameter_noinfo();
    goto LABEL_21;
  }
  _mm_lfence();
  memcpy_0(v12, bstrVal - 2, v14);
LABEL_21:
  if ( !(unsigned int)((__int64 (__fastcall *)(OLECHAR *, _QWORD, _QWORD))g_pfnCryptProtectMemory)(v13, v11, 0) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_180263170[0] )
      {
        LastError = GetLastError();
        bidTraceW(off_180260410[0], 3904512, off_180263170[0], LastError);
      }
    }
    SysFreeString(v13);
    return -2147467259;
  }
  result = VariantClear(a4);
  if ( result < 0 )
    return result;
  a4->llVal = (LONGLONG)v13;
  a4->vt = 8;
LABEL_31:
  v16 = *((_QWORD *)this + 72);
  v17 = *(_DWORD *)(v16 + 280);
  if ( (v17 & 4) != 0 )
    *(_DWORD *)(v16 + 280) = v17 & 0xFFFFFFFB;
  return result;
}

```

## disassembly

```asm
0x1800a1840  push    r13
0x1800a1842  push    r14
0x1800a1844  sub     rsp, 28h
0x1800a1848  mov     eax, edx
0x1800a184a  mov     r14, r9
0x1800a184d  mov     rdx, [rsp+38h+pvargSrc]; pvargSrc
0x1800a1852  mov     r13, rcx
0x1800a1855  cmp     word ptr [rdx], 8
0x1800a1859  jnz     short loc_1800A186B
0x1800a185b  test    eax, eax
0x1800a185d  jnz     short loc_1800A187D
0x1800a185f  cmp     r8d, 1
0x1800a1863  jz      short loc_1800A188E
0x1800a1865  cmp     r8d, 0Ah
0x1800a1869  jz      short loc_1800A188E
0x1800a186b  mov     rcx, r14
0x1800a186e  add     rsp, 28h
0x1800a1872  pop     r14
0x1800a1874  pop     r13
0x1800a1876  jmp     cs:__imp_VariantCopy
0x1800a187d  cmp     eax, 1
0x1800a1880  jnz     short loc_1800A186B
0x1800a1882  cmp     r8d, 0Eh
0x1800a1886  jz      short loc_1800A188E
0x1800a1888  cmp     r8d, 17h
0x1800a188c  jnz     short loc_1800A186B
0x1800a188e  mov     [rsp+38h+arg_0], rbx
0x1800a1893  mov     [rsp+38h+arg_8], rbp
0x1800a1898  mov     rbp, [rdx+8]
0x1800a189c  mov     [rsp+38h+arg_10], rsi
0x1800a18a1  mov     [rsp+38h+arg_18], rdi
0x1800a18a6  test    rbp, rbp
0x1800a18a9  jz      loc_1800A19F1
0x1800a18af  cmp     cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA, 0; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800a18b7  jz      loc_1800A19F1
0x1800a18bd  mov     rcx, rbp; bstr
0x1800a18c0  call    cs:__imp_SysStringByteLen
0x1800a18c6  mov     esi, eax
0x1800a18c8  lea     edi, [rsi+13h]
0x1800a18cb  and     edi, 0FFFFFFF0h
0x1800a18ce  cmp     edi, eax
0x1800a18d0  jb      loc_1800A19EA
0x1800a18d6  lfence
0x1800a18d9  mov     edx, edi; len
0x1800a18db  xor     ecx, ecx; psz
0x1800a18dd  call    cs:__imp_SysAllocStringByteLen
0x1800a18e3  mov     rbx, rax
0x1800a18e6  test    rax, rax
0x1800a18e9  jz      loc_1800A19EA
0x1800a18ef  mov     [rsp+38h+var_18], r15
0x1800a18f4  add     rsi, 4
0x1800a18f8  lea     r15, [rbp-4]
0x1800a18fc  mov     ebp, edi
0x1800a18fe  test    r15, r15
0x1800a1901  jz      short loc_1800A191B
0x1800a1903  cmp     rbp, rsi
0x1800a1906  jb      short loc_1800A191B
0x1800a1908  lfence
0x1800a190b  mov     r8, rsi; Size
0x1800a190e  mov     rdx, r15; Src
0x1800a1911  mov     rcx, rax; void *
0x1800a1914  call    memcpy_0
0x1800a1919  jmp     short loc_1800A1952
0x1800a191b  mov     r8, rbp; Size
0x1800a191e  xor     edx, edx; Val
0x1800a1920  mov     rcx, rbx; void *
0x1800a1923  call    memset_0
0x1800a1928  test    r15, r15
0x1800a192b  jnz     short loc_1800A193B
0x1800a192d  call    cs:__imp__errno
0x1800a1933  mov     dword ptr [rax], 16h
0x1800a1939  jmp     short loc_1800A194C
0x1800a193b  cmp     rbp, rsi
0x1800a193e  jnb     short loc_1800A1952
0x1800a1940  call    cs:__imp__errno
0x1800a1946  mov     dword ptr [rax], 22h ; '"'
0x1800a194c  call    cs:__imp__invalid_parameter_noinfo
0x1800a1952  mov     rax, cs:?g_pfnCryptProtectMemory@@3P6AHPEAXKK@ZEA; int (*g_pfnCryptProtectMemory)(void *,ulong,ulong)
0x1800a1959  xor     r8d, r8d
0x1800a195c  mov     edx, edi
0x1800a195e  mov     rcx, rbx
0x1800a1961  call    cs:__guard_dispatch_icall_fptr
0x1800a1967  mov     r15, [rsp+38h+var_18]
0x1800a196c  test    eax, eax
0x1800a196e  jnz     short loc_1800A19D1
0x1800a1970  test    byte ptr cs:_bidGblFlags, 2
0x1800a1977  jz      short loc_1800A19A6
0x1800a1979  mov     rax, cs:off_180263170; "<CDataSourceProps::SecureSetValue|ERR|S"...
0x1800a1980  test    rax, rax
0x1800a1983  jz      short loc_1800A19A6
0x1800a1985  call    cs:__imp_GetLastError
0x1800a198b  mov     r8, cs:off_180263170; "<CDataSourceProps::SecureSetValue|ERR|S"...
0x1800a1992  mov     edx, 3B9400h
0x1800a1997  mov     rcx, cs:off_180260410; "C:\\__w\\1\\s\\Sql\\Ntdbms\\sqlncli\\ol"...
0x1800a199e  mov     r9d, eax
0x1800a19a1  call    _bidTraceW
0x1800a19a6  mov     rcx, rbx; bstrString
0x1800a19a9  call    cs:__imp_SysFreeString
0x1800a19af  mov     eax, 80004005h
0x1800a19b4  mov     rsi, [rsp+38h+arg_10]
0x1800a19b9  mov     rbp, [rsp+38h+arg_8]
0x1800a19be  mov     rbx, [rsp+38h+arg_0]
0x1800a19c3  mov     rdi, [rsp+38h+arg_18]
0x1800a19c8  add     rsp, 28h
0x1800a19cc  pop     r14
0x1800a19ce  pop     r13
0x1800a19d0  retn
0x1800a19d1  mov     rcx, r14; pvarg
0x1800a19d4  call    cs:__imp_VariantClear
0x1800a19da  test    eax, eax
0x1800a19dc  js      short loc_1800A19B4
0x1800a19de  mov     [r14+8], rbx
0x1800a19e2  mov     word ptr [r14], 8
0x1800a19e8  jmp     short loc_1800A19FE
0x1800a19ea  mov     eax, 8007000Eh
0x1800a19ef  jmp     short loc_1800A19B4
0x1800a19f1  mov     rcx, r14; pvargDest
0x1800a19f4  call    cs:__imp_VariantCopy
0x1800a19fa  test    eax, eax
0x1800a19fc  js      short loc_1800A19B4
0x1800a19fe  mov     rdx, [r13+240h]
0x1800a1a05  mov     ecx, [rdx+118h]
0x1800a1a0b  test    cl, 4
0x1800a1a0e  jz      short loc_1800A19B4
0x1800a1a10  and     ecx, 0FFFFFFFBh
0x1800a1a13  mov     [rdx+118h], ecx
0x1800a1a19  jmp     short loc_1800A19B4
```
