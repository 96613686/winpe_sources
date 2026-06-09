# GetUniqueTempDirInPrintShare

- ea: `0x180036c28`
- end: `0x180036cfe`
- name: `GetUniqueTempDirInPrintShare`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012424`

## callees

- `0x180002300`
- `0x180018d18`
- `0x180036c28`

## import_xrefs

- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180036c72`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180036c72`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036cc5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180036cc5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036ce3`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180036ce3`

## pseudocode

```c
HRESULT __fastcall GetUniqueTempDirInPrintShare(WCHAR *a1, WCHAR *a2, BYTE *a3)
{
  HRESULT result; // eax
  __int64 v5; // rbx
  __int64 v6; // rax
  DWORD pcbNeeded; // [rsp+30h] [rbp-38h] BYREF
  GUID pguid; // [rsp+38h] [rbp-30h] BYREF

  pcbNeeded = 0;
  if ( !a2 )
    return -2147024809;
  if ( GetPrinterDriverDirectoryW(a1, a2, 1u, a3, 0x208u, &pcbNeeded) )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&a3[2 * v5] );
    if ( *(_WORD *)&a3[2 * (unsigned int)(v5 - 1)] != 92 && (unsigned int)v5 < 0x103 )
    {
      v6 = (unsigned int)v5;
      LODWORD(v5) = v5 + 1;
      *(_WORD *)&a3[2 * v6] = 92;
      *(_WORD *)&a3[2 * (unsigned int)v5] = 0;
    }
  }
  else
  {
    result = GetLastErrorAsHResult();
    LODWORD(v5) = 0;
    if ( result < 0 )
      return result;
  }
  pguid = 0;
  result = CoCreateGuid(&pguid);
  if ( result >= 0 )
    return StringFromGUID2(&pguid, (LPOLESTR)&a3[2 * (unsigned int)v5], 260 - v5);
  return result;
}

```

## disassembly

```asm
0x180036c28  push    rbx
0x180036c2a  push    rsi
0x180036c2b  push    rdi
0x180036c2c  sub     rsp, 50h
0x180036c30  mov     rax, cs:__security_cookie
0x180036c37  xor     rax, rsp
0x180036c3a  mov     [rsp+68h+var_20], rax
0x180036c3f  xor     esi, esi
0x180036c41  mov     rdi, r8
0x180036c44  mov     [rsp+68h+var_38], esi
0x180036c48  test    rdx, rdx
0x180036c4b  jnz     short loc_180036C57
0x180036c4d  mov     eax, 80070057h
0x180036c52  jmp     loc_180036CE9
0x180036c57  lea     rax, [rsp+68h+var_38]
0x180036c5c  mov     r9, rdi; pDriverDirectory
0x180036c5f  mov     [rsp+68h+pcbNeeded], rax; pcbNeeded
0x180036c64  mov     r8d, 1; Level
0x180036c6a  mov     [rsp+68h+cbBuf], 208h; cbBuf
0x180036c72  call    cs:__imp_GetPrinterDriverDirectoryW
0x180036c78  test    eax, eax
0x180036c7a  jnz     short loc_180036C89
0x180036c7c  call    GetLastErrorAsHResult
0x180036c81  mov     ebx, esi
0x180036c83  test    eax, eax
0x180036c85  jns     short loc_180036CB8
0x180036c87  jmp     short loc_180036CE9
0x180036c89  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036c8d  inc     rbx
0x180036c90  cmp     [rdi+rbx*2], si
0x180036c94  jnz     short loc_180036C8D
0x180036c96  lea     eax, [rbx-1]
0x180036c99  mov     edx, 5Ch ; '\'
0x180036c9e  cmp     [rdi+rax*2], dx
0x180036ca2  jz      short loc_180036CB8
0x180036ca4  cmp     ebx, 103h
0x180036caa  jnb     short loc_180036CB8
0x180036cac  mov     eax, ebx
0x180036cae  inc     ebx
0x180036cb0  mov     [rdi+rax*2], dx
0x180036cb4  mov     [rdi+rbx*2], si
0x180036cb8  xorps   xmm0, xmm0
0x180036cbb  lea     rcx, [rsp+68h+pguid]; pguid
0x180036cc0  movups  xmmword ptr [rsp+68h+pguid.Data1], xmm0
0x180036cc5  call    cs:__imp_CoCreateGuid
0x180036ccb  test    eax, eax
0x180036ccd  js      short loc_180036CE9
0x180036ccf  mov     eax, ebx
0x180036cd1  lea     rcx, [rsp+68h+pguid]; rguid
0x180036cd6  mov     r8d, 104h
0x180036cdc  sub     r8d, ebx; cchMax
0x180036cdf  lea     rdx, [rdi+rax*2]; lpsz
0x180036ce3  call    cs:__imp_StringFromGUID2
0x180036ce9  mov     rcx, [rsp+68h+var_20]
0x180036cee  xor     rcx, rsp; StackCookie
0x180036cf1  call    __security_check_cookie
0x180036cf6  add     rsp, 50h
0x180036cfa  pop     rdi
0x180036cfb  pop     rsi
0x180036cfc  pop     rbx
0x180036cfd  retn
```
