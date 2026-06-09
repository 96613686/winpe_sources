# UtPutUNICODEData(ulong,ushort *,char * *,ushort * *,ulong *)

- ea: `0x180038034`
- end: `0x1800381da`
- name: `?UtPutUNICODEData@@YAJKPEAGPEAPEADPEAPEAGPEAK@Z`
- size: `422`
- prototype: `HRESULT __fastcall(unsigned int ulLength, wchar_t *str, char **pszANSI, wchar_t **pszOLESTR, unsigned int *pdwResultLen)`
- caller_count: `4`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180085cfc`
- `0x180085d7c`
- `0x18008d5d4`
- `0x18008d9a8`

## callees

- `0x180009374`
- `0x18000b2d4`
- `0x18001b810`
- `0x180036c7c`
- `0x180038034`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800380e0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800380e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038096`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038128`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180038187`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003806e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003814b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003815f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180038054`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003806e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003814b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003815f`

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
  int fUseDef; // [rsp+80h] [rbp+8h] BYREF

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
0x180038034  push    rbx
0x180038036  push    rbp
0x180038037  push    rsi
0x180038038  push    rdi
0x180038039  push    r14
0x18003803b  push    r15
0x18003803d  sub     rsp, 48h
0x180038041  mov     ebp, ulLength
0x180038043  mov     rbx, pszOLESTR
0x180038046  mov     rcx, [pszANSI]; pv
0x180038049  mov     rsi, pszANSI
0x18003804c  mov     r15, str
0x18003804f  test    rcx, rcx
0x180038052  jz      short loc_180038061
0x180038054  call    cs:__imp_CoTaskMemFree
0x18003805a  mov     qword ptr [rsi], 0
0x180038061  test    rbx, rbx
0x180038064  jz      short loc_18003807B
0x180038066  mov     rcx, [rbx]; pv
0x180038069  test    rcx, rcx
0x18003806c  jz      short loc_18003807B
0x18003806e  call    cs:__imp_CoTaskMemFree
0x180038074  mov     qword ptr [rbx], 0
0x18003807b  lea     r14d, ds:2[rbp*2]
0x180038083  mov     edi, r14d
0x180038086  call    GetSafeAllocSize
0x18003808b  cmp     rdi, rax
0x18003808e  jnb     loc_1800381C1
0x180038094  mov     ulLength, edi; cb
0x180038096  call    cs:__imp_CoTaskMemAlloc
0x18003809c  mov     rdi, rax
0x18003809f  test    rax, rax
0x1800380a2  jz      loc_1800381C1
0x1800380a8  lea     rax, [rsp+78h+fUseDef]
0x1800380b0  mov     [rsp+78h+fUseDef], 0
0x1800380bb  mov     [rsp+78h+lpUsedDefaultChar], rax; lpUsedDefaultChar
0x1800380c0  mov     r9d, ebp; cchWideChar
0x1800380c3  lea     rax, DefaultChar; "?"
0x1800380ca  mov     pszANSI, r15; lpWideCharStr
0x1800380cd  mov     [rsp+78h+lpDefaultChar], rax; lpDefaultChar
0x1800380d2  xor     edx, edx; dwFlags
0x1800380d4  mov     [rsp+78h+cbMultiByte], r14d; cbMultiByte
0x1800380d9  xor     ulLength, ulLength; CodePage
0x1800380db  mov     [rsp+78h+lpMultiByteStr], rdi; lpMultiByteStr
0x1800380e0  call    cs:__imp_WideCharToMultiByte
0x1800380e6  mov     r14, [rsp+78h+arg_20]
0x1800380ee  test    eax, eax
0x1800380f0  jz      short loc_18003815C
0x1800380f2  cmp     [rsp+78h+fUseDef], 0
0x1800380fa  jnz     short loc_18003815C
0x1800380fc  test    rbx, rbx
0x1800380ff  jz      short loc_180038108
0x180038101  mov     qword ptr [rbx], 0
0x180038108  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003810c  inc     rax
0x18003810f  cmp     byte ptr [rdi+rax], 0
0x180038113  jnz     short loc_18003810C
0x180038115  inc     eax
0x180038117  mov     [r14], eax
0x18003811a  mov     ebx, eax
0x18003811c  call    GetSafeAllocSize
0x180038121  cmp     rbx, rax
0x180038124  jnb     short loc_180038153
0x180038126  mov     ulLength, ebx; cb
0x180038128  call    cs:__imp_CoTaskMemAlloc
0x18003812e  mov     [rsi], rax
0x180038131  test    rax, rax
0x180038134  jz      loc_1800381BA
0x18003813a  mov     edx, [r14]; cchDest
0x18003813d  mov     pszANSI, rdi; pszSrc
0x180038140  mov     rcx, rax; pszDest
0x180038143  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180038148  mov     rcx, rdi; pv
0x18003814b  call    cs:__imp_CoTaskMemFree
0x180038151  jmp     short loc_1800381AF
0x180038153  mov     qword ptr [rsi], 0
0x18003815a  jmp     short loc_1800381BA
0x18003815c  mov     rcx, rdi; pv
0x18003815f  call    cs:__imp_CoTaskMemFree
0x180038165  test    rbx, rbx
0x180038168  jz      short loc_1800381D3
0x18003816a  lea     eax, [rbp+1]
0x18003816d  mov     qword ptr [rsi], 0
0x180038174  mov     esi, eax
0x180038176  lea     rdi, [rax+rax]
0x18003817a  call    GetSafeAllocSize
0x18003817f  cmp     rdi, rax
0x180038182  jnb     short loc_1800381B3
0x180038184  mov     rcx, rdi; cb
0x180038187  call    cs:__imp_CoTaskMemAlloc
0x18003818d  mov     [rbx], rax
0x180038190  test    rax, rax
0x180038193  jz      short loc_1800381BA
0x180038195  mov     pszANSI, r15; pszSrc
0x180038198  mov     edx, esi; cchDest
0x18003819a  mov     rcx, rax; pszDest
0x18003819d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800381a2  mov     rcx, r15; string
0x1800381a5  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x1800381aa  inc     eax
0x1800381ac  mov     [r14], eax
0x1800381af  xor     eax, eax
0x1800381b1  jmp     short loc_1800381C6
0x1800381b3  mov     qword ptr [rbx], 0
0x1800381ba  mov     dword ptr [r14], 0
0x1800381c1  mov     eax, 8007000Eh
0x1800381c6  add     rsp, 48h
0x1800381ca  pop     r15
0x1800381cc  pop     r14
0x1800381ce  pop     rdi
0x1800381cf  pop     rsi
0x1800381d0  pop     rbp
0x1800381d1  pop     rbx
0x1800381d2  retn
0x1800381d3  mov     eax, 80004005h
0x1800381d8  jmp     short loc_1800381C6
```
