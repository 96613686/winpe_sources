# UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)

- ea: `0x18003bf64`
- end: `0x18003c131`
- name: `?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z`
- size: `461`
- prototype: `HRESULT __fastcall(unsigned int ulLength, wchar_t *str, char **pszANSI, wchar_t **pszOLESTR, unsigned int *pdwResultLen)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800803e4`
- `0x180080470`
- `0x180088adc`
- `0x180088f04`

## callees

- `0x1800077fc`
- `0x18000a574`
- `0x18001a630`
- `0x18003ac50`
- `0x18003bf64`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003c01e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18003c01e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bfd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003bfd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003c0d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c0a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bf8f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bfac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c08f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003c0a6`

## pseudocode

```c
__int64 __fastcall UtPutUNICODEData(
        int ulLength,
        wchar_t *str,
        LPVOID *pszANSI,
        LPVOID *pszOLESTR,
        unsigned int *pdwResultLen)
{
  unsigned __int64 v9; // rdi
  char *lpMultiByteStr; // rdi
  int v11; // eax
  unsigned int *v12; // r14
  __int64 v13; // rax
  unsigned int v14; // eax
  unsigned int v15; // ebx
  char *v16; // rax
  SIZE_T v17; // rdi
  wchar_t *v18; // rax
  int fUseDef; // [rsp+60h] [rbp+8h] BYREF

  if ( *pszANSI )
  {
    CoTaskMemFree(*pszANSI);
    *pszANSI = 0;
  }
  if ( pszOLESTR && *pszOLESTR )
  {
    CoTaskMemFree(*pszOLESTR);
    *pszOLESTR = 0;
  }
  v9 = (unsigned int)(2 * ulLength + 2);
  if ( v9 >= GetSafeAllocSize() )
    return 2147942414LL;
  lpMultiByteStr = (char *)CoTaskMemAlloc((unsigned int)v9);
  if ( !lpMultiByteStr )
    return 2147942414LL;
  fUseDef = 0;
  v11 = WideCharToMultiByte(0, 0, str, ulLength, lpMultiByteStr, 2 * ulLength + 2, "?", &fUseDef);
  v12 = pdwResultLen;
  if ( v11 && !fUseDef )
  {
    if ( pszOLESTR )
      *pszOLESTR = 0;
    v13 = -1;
    do
      ++v13;
    while ( lpMultiByteStr[v13] );
    v14 = v13 + 1;
    *v12 = v14;
    v15 = v14;
    if ( v14 >= GetSafeAllocSize() )
    {
      *pszANSI = 0;
    }
    else
    {
      v16 = (char *)CoTaskMemAlloc(v15);
      *pszANSI = v16;
      if ( v16 )
      {
        StringCchCopyA(v16, *v12, lpMultiByteStr);
        CoTaskMemFree(lpMultiByteStr);
        return 0;
      }
    }
LABEL_24:
    *v12 = 0;
    return 2147942414LL;
  }
  CoTaskMemFree(lpMultiByteStr);
  if ( pszOLESTR )
  {
    *pszANSI = 0;
    v17 = 2LL * (unsigned int)(ulLength + 1);
    if ( v17 >= GetSafeAllocSize() )
    {
      *pszOLESTR = 0;
    }
    else
    {
      v18 = (wchar_t *)CoTaskMemAlloc(v17);
      *pszOLESTR = v18;
      if ( v18 )
      {
        StringCchCopyW(v18, (unsigned int)(ulLength + 1), str);
        *v12 = safe_lstrlenW(str) + 1;
        return 0;
      }
    }
    goto LABEL_24;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x18003bf64  mov     [rsp+arg_8], rbx
0x18003bf69  mov     [rsp+arg_10], rbp
0x18003bf6e  mov     [rsp+arg_18], rsi
0x18003bf73  push    rdi
0x18003bf74  push    r14
0x18003bf76  push    r15
0x18003bf78  sub     rsp, 40h
0x18003bf7c  mov     ebp, ulLength
0x18003bf7e  mov     rbx, pszOLESTR
0x18003bf81  mov     rcx, [pszANSI]; pv
0x18003bf84  mov     rsi, pszANSI
0x18003bf87  mov     r15, str
0x18003bf8a  test    rcx, rcx
0x18003bf8d  jz      short loc_18003BF9F
0x18003bf8f  call    cs:__imp_CoTaskMemFree
0x18003bf96  nop     dword ptr [rax+rax+00h]
0x18003bf9b  and     qword ptr [rsi], 0
0x18003bf9f  test    rbx, rbx
0x18003bfa2  jz      short loc_18003BFBC
0x18003bfa4  mov     rcx, [rbx]; pv
0x18003bfa7  test    rcx, rcx
0x18003bfaa  jz      short loc_18003BFBC
0x18003bfac  call    cs:__imp_CoTaskMemFree
0x18003bfb3  nop     dword ptr [rax+rax+00h]
0x18003bfb8  and     qword ptr [rbx], 0
0x18003bfbc  lea     r14d, ds:2[rbp*2]
0x18003bfc4  mov     edi, r14d
0x18003bfc7  call    GetSafeAllocSize
0x18003bfcc  cmp     rdi, rax
0x18003bfcf  jnb     loc_18003C10B
0x18003bfd5  mov     ulLength, edi; cb
0x18003bfd7  call    cs:__imp_CoTaskMemAlloc
0x18003bfde  nop     dword ptr [rax+rax+00h]
0x18003bfe3  mov     rdi, rax
0x18003bfe6  test    rax, rax
0x18003bfe9  jz      loc_18003C10B
0x18003bfef  and     [rsp+58h+fUseDef], 0
0x18003bff4  lea     rax, [rsp+58h+fUseDef]
0x18003bff9  mov     [rsp+58h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x18003bffe  mov     r9d, ebp; cchWideChar
0x18003c001  lea     rax, DefaultChar; "?"
0x18003c008  mov     pszANSI, r15; lpWideCharStr
0x18003c00b  mov     [rsp+58h+lpDefaultChar], rax; lpDefaultChar
0x18003c010  xor     edx, edx; dwFlags
0x18003c012  mov     [rsp+58h+cbMultiByte], r14d; cbMultiByte
0x18003c017  xor     ulLength, ulLength; CodePage
0x18003c019  mov     [rsp+58h+lpMultiByteStr], rdi; lpMultiByteStr
0x18003c01e  call    cs:__imp_WideCharToMultiByte
0x18003c025  nop     dword ptr [rax+rax+00h]
0x18003c02a  mov     r14, [rsp+58h+arg_20]
0x18003c032  test    eax, eax
0x18003c034  jz      short loc_18003C0A3
0x18003c036  cmp     [rsp+58h+fUseDef], 0
0x18003c03b  jnz     short loc_18003C0A3
0x18003c03d  test    rbx, rbx
0x18003c040  jz      short loc_18003C046
0x18003c042  and     qword ptr [rbx], 0
0x18003c046  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003c04a  inc     rax
0x18003c04d  cmp     byte ptr [rdi+rax], 0
0x18003c051  jnz     short loc_18003C04A
0x18003c053  inc     eax
0x18003c055  mov     [r14], eax
0x18003c058  mov     ebx, eax
0x18003c05a  call    GetSafeAllocSize
0x18003c05f  cmp     rbx, rax
0x18003c062  jnb     short loc_18003C09D
0x18003c064  mov     ulLength, ebx; cb
0x18003c066  call    cs:__imp_CoTaskMemAlloc
0x18003c06d  nop     dword ptr [rax+rax+00h]
0x18003c072  mov     [rsi], rax
0x18003c075  test    rax, rax
0x18003c078  jz      loc_18003C107
0x18003c07e  mov     edx, [r14]; cchDest
0x18003c081  mov     pszANSI, rdi; pszSrc
0x18003c084  mov     rcx, rax; pszDest
0x18003c087  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18003c08c  mov     rcx, rdi; pv
0x18003c08f  call    cs:__imp_CoTaskMemFree
0x18003c096  nop     dword ptr [rax+rax+00h]
0x18003c09b  jmp     short loc_18003C0FF
0x18003c09d  and     qword ptr [rsi], 0
0x18003c0a1  jmp     short loc_18003C107
0x18003c0a3  mov     rcx, rdi; pv
0x18003c0a6  call    cs:__imp_CoTaskMemFree
0x18003c0ad  nop     dword ptr [rax+rax+00h]
0x18003c0b2  test    rbx, rbx
0x18003c0b5  jz      short loc_18003C12A
0x18003c0b7  and     qword ptr [rsi], 0
0x18003c0bb  lea     eax, [rbp+1]
0x18003c0be  mov     esi, eax
0x18003c0c0  lea     rdi, [rax+rax]
0x18003c0c4  call    GetSafeAllocSize
0x18003c0c9  cmp     rdi, rax
0x18003c0cc  jnb     short loc_18003C103
0x18003c0ce  mov     rcx, rdi; cb
0x18003c0d1  call    cs:__imp_CoTaskMemAlloc
0x18003c0d8  nop     dword ptr [rax+rax+00h]
0x18003c0dd  mov     [rbx], rax
0x18003c0e0  test    rax, rax
0x18003c0e3  jz      short loc_18003C107
0x18003c0e5  mov     pszANSI, r15; pszSrc
0x18003c0e8  mov     edx, esi; cchDest
0x18003c0ea  mov     rcx, rax; pszDest
0x18003c0ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003c0f2  mov     rcx, r15; string
0x18003c0f5  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18003c0fa  inc     eax
0x18003c0fc  mov     [r14], eax
0x18003c0ff  xor     eax, eax
0x18003c101  jmp     short loc_18003C110
0x18003c103  and     qword ptr [rbx], 0
0x18003c107  and     dword ptr [r14], 0
0x18003c10b  mov     eax, 8007000Eh
0x18003c110  mov     rbx, [rsp+58h+arg_8]
0x18003c115  mov     rbp, [rsp+58h+arg_10]
0x18003c11a  mov     rsi, [rsp+58h+arg_18]
0x18003c11f  add     rsp, 40h
0x18003c123  pop     r15
0x18003c125  pop     r14
0x18003c127  pop     rdi
0x18003c128  retn
0x18003c12a  mov     eax, 80004005h
0x18003c12f  jmp     short loc_18003C110
```
