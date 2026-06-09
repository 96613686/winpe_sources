# GetCachedCredentials(HKEY__ *,ushort const *,ushort *,ulong)

- ea: `0x18002281c`
- end: `0x180022a08`
- name: `?GetCachedCredentials@@YAJPEAUHKEY__@@PEBGPEAGK@Z`
- size: `492`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000b4d4`

## callees

- `0x180002240`
- `0x180009650`
- `0x18002281c`
- `0x180022a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800229b6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022887`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800228e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180022887`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800228e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228ae`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800228ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800229cf`
- `CRYPT32!CryptUnprotectData` at `0x180022955`
- `CRYPT32!CryptUnprotectData` at `0x180022955`

## pseudocode

```c
__int64 __fastcall GetCachedCredentials(HKEY hKey, const unsigned __int16 *a2, unsigned __int16 *a3)
{
  unsigned int inited; // ebx
  BYTE *lpData; // rax
  signed int LastError; // eax
  bool v9; // cc
  int v10; // edx
  __int64 v11; // rax
  DWORD v12; // edx
  BYTE *pbData; // rcx
  unsigned int v14; // eax
  __int64 v15; // rax
  DWORD Type; // [rsp+40h] [rbp-19h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-11h] BYREF
  DWORD cbData[4]; // [rsp+58h] [rbp-1h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+68h] [rbp+Fh] BYREF
  _DWORD v21[2]; // [rsp+78h] [rbp+1Fh] BYREF

  inited = InitCredentialPersist();
  if ( !inited )
  {
    Type = 0;
    *(_OWORD *)cbData = 0;
    if ( RegQueryValueExW(hKey, L"Password", 0, &Type, 0, cbData) || Type != 3 || !cbData[0] )
      return (unsigned int)-2147467259;
    lpData = (BYTE *)LocalAlloc(0, cbData[0]);
    *(_QWORD *)&cbData[2] = lpData;
    if ( !lpData )
      return (unsigned int)-2147024882;
    LastError = RegQueryValueExW(hKey, L"Password", 0, &Type, lpData, cbData);
    inited = LastError;
    v9 = LastError <= 0;
    if ( !LastError )
    {
      pOptionalEntropy.cbData = 4;
      pOptionalEntropy.pbData = (BYTE *)v21;
      v10 = 0;
      pDataOut = 0;
      v21[0] = 0;
      if ( *a2 )
      {
        do
        {
          v11 = v10++;
          *((_BYTE *)v21 + (v11 & 3)) += a2[v11] & 0x1F;
        }
        while ( a2[v10] );
      }
      if ( CryptUnprotectData((DATA_BLOB *)cbData, 0, &pOptionalEntropy, 0, 0, 1u, &pDataOut) )
      {
        v12 = pDataOut.cbData;
        pbData = pDataOut.pbData;
        if ( (pDataOut.cbData & 1) != 0 || *(_WORD *)&pDataOut.pbData[2 * ((unsigned __int64)pDataOut.cbData >> 1) - 2] )
        {
          inited = -2147467259;
        }
        else
        {
          v14 = StringCchCopyW(a3, 0x80u, (unsigned __int16 *)pDataOut.pbData);
          pbData = pDataOut.pbData;
          inited = v14;
          v12 = pDataOut.cbData;
        }
        v15 = v12;
        if ( v12 )
        {
          do
          {
            *pbData++ = 0;
            --v15;
          }
          while ( v15 );
          pbData = pDataOut.pbData;
        }
        LocalFree(pbData);
LABEL_21:
        LocalFree(*(HLOCAL *)&cbData[2]);
        return inited;
      }
      LastError = GetLastError();
      inited = LastError;
      v9 = LastError <= 0;
    }
    if ( !v9 )
      inited = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_21;
  }
  return inited;
}

```

## disassembly

```asm
0x18002281c  mov     [rsp-8+arg_8], rbx
0x180022821  push    rbp
0x180022822  push    rsi
0x180022823  push    rdi
0x180022824  push    r14
0x180022826  push    r15
0x180022828  lea     rbp, [rsp-37h]
0x18002282d  sub     rsp, 90h
0x180022834  mov     rax, cs:__security_cookie
0x18002283b  xor     rax, rsp
0x18002283e  mov     [rbp+57h+var_30], rax
0x180022842  mov     r14, r8
0x180022845  mov     rdi, rdx
0x180022848  mov     rsi, rcx
0x18002284b  call    ?InitCredentialPersist@@YAJXZ; InitCredentialPersist(void)
0x180022850  xor     r15d, r15d
0x180022853  mov     ebx, eax
0x180022855  test    eax, eax
0x180022857  jnz     loc_1800229E3
0x18002285d  lea     rax, [rbp+57h+cbData]
0x180022861  mov     [rbp+57h+Type], r15d
0x180022865  xorps   xmm0, xmm0
0x180022868  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x18002286d  lea     r9, [rbp+57h+Type]; lpType
0x180022871  mov     [rsp+0B0h+lpData], r15; lpData
0x180022876  xor     r8d, r8d; lpReserved
0x180022879  lea     rdx, ValueName; "Password"
0x180022880  mov     rcx, rsi; hKey
0x180022883  movups  xmmword ptr [rbp+57h+cbData], xmm0
0x180022887  call    cs:__imp_RegQueryValueExW
0x18002288d  test    eax, eax
0x18002288f  jnz     loc_1800229DE
0x180022895  cmp     [rbp+57h+Type], 3
0x180022899  jnz     loc_1800229DE
0x18002289f  mov     eax, [rbp+57h+cbData]
0x1800228a2  test    eax, eax
0x1800228a4  jz      loc_1800229DE
0x1800228aa  mov     edx, eax; uBytes
0x1800228ac  xor     ecx, ecx; uFlags
0x1800228ae  call    cs:__imp_LocalAlloc
0x1800228b4  mov     qword ptr [rbp+57h+cbData+8], rax
0x1800228b8  test    rax, rax
0x1800228bb  jz      loc_1800229D7
0x1800228c1  lea     rcx, [rbp+57h+cbData]
0x1800228c5  xor     r8d, r8d; lpReserved
0x1800228c8  mov     [rsp+0B0h+lpcbData], rcx; lpcbData
0x1800228cd  lea     r9, [rbp+57h+Type]; lpType
0x1800228d1  mov     rcx, rsi; hKey
0x1800228d4  mov     [rsp+0B0h+lpData], rax; lpData
0x1800228d9  lea     rdx, ValueName; "Password"
0x1800228e0  call    cs:__imp_RegQueryValueExW
0x1800228e6  mov     ebx, eax
0x1800228e8  test    eax, eax
0x1800228ea  jnz     loc_1800229C0
0x1800228f0  lea     rax, [rbp+57h+var_38]
0x1800228f4  mov     [rbp+57h+pOptionalEntropy.cbData], 4
0x1800228fb  mov     [rbp+57h+pOptionalEntropy.pbData], rax
0x1800228ff  xorps   xmm0, xmm0
0x180022902  xor     eax, eax
0x180022904  mov     edx, r15d
0x180022907  movups  xmmword ptr [rbp+57h+var_68.cbData], xmm0
0x18002290b  mov     [rbp+57h+var_38], eax
0x18002290e  cmp     [rdi], r15w
0x180022912  jz      short loc_180022932
0x180022914  movsxd  rax, edx
0x180022917  inc     edx
0x180022919  mov     rcx, rax
0x18002291c  and     ecx, 3
0x18002291f  mov     al, [rdi+rax*2]
0x180022922  and     al, 1Fh
0x180022924  add     byte ptr [rbp+rcx+57h+var_38], al
0x180022928  movsxd  rax, edx
0x18002292b  cmp     [rdi+rax*2], r15w
0x180022930  jnz     short loc_180022914
0x180022932  lea     rax, [rbp+57h+var_68]
0x180022936  xor     r9d, r9d; pvReserved
0x180022939  mov     [rsp+0B0h+pDataOut], rax; pDataOut
0x18002293e  lea     r8, [rbp+57h+pOptionalEntropy]; pOptionalEntropy
0x180022942  mov     dword ptr [rsp+0B0h+lpcbData], 1; dwFlags
0x18002294a  lea     rcx, [rbp+57h+cbData]; pDataIn
0x18002294e  xor     edx, edx; ppszDataDescr
0x180022950  mov     [rsp+0B0h+lpData], r15; pPromptStruct
0x180022955  call    cs:__imp_CryptUnprotectData
0x18002295b  test    eax, eax
0x18002295d  jz      short loc_1800229B6
0x18002295f  mov     edx, [rbp+57h+var_68.cbData]
0x180022962  mov     rcx, [rbp+57h+var_68.pbData]
0x180022966  test    dl, 1
0x180022969  jnz     short loc_180022993
0x18002296b  mov     eax, edx
0x18002296d  shr     rax, 1
0x180022970  cmp     [rcx+rax*2-2], r15w
0x180022976  jnz     short loc_180022993
0x180022978  mov     r8, rcx; unsigned __int16 *
0x18002297b  mov     edx, 80h; unsigned __int64
0x180022980  mov     rcx, r14; unsigned __int16 *
0x180022983  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022988  mov     rcx, [rbp+57h+var_68.pbData]
0x18002298c  mov     ebx, eax
0x18002298e  mov     edx, [rbp+57h+var_68.cbData]
0x180022991  jmp     short loc_180022998
0x180022993  mov     ebx, 80004005h
0x180022998  mov     eax, edx
0x18002299a  test    edx, edx
0x18002299c  jz      short loc_1800229AE
0x18002299e  mov     [rcx], r15b
0x1800229a1  inc     rcx
0x1800229a4  sub     rax, 1
0x1800229a8  jnz     short loc_18002299E
0x1800229aa  mov     rcx, [rbp+57h+var_68.pbData]; hMem
0x1800229ae  call    cs:__imp_LocalFree
0x1800229b4  jmp     short loc_1800229CB
0x1800229b6  call    cs:__imp_GetLastError
0x1800229bc  mov     ebx, eax
0x1800229be  test    eax, eax
0x1800229c0  jle     short loc_1800229CB
0x1800229c2  movzx   ebx, ax
0x1800229c5  or      ebx, 80070000h
0x1800229cb  mov     rcx, qword ptr [rbp+57h+cbData+8]; hMem
0x1800229cf  call    cs:__imp_LocalFree
0x1800229d5  jmp     short loc_1800229E3
0x1800229d7  mov     ebx, 8007000Eh
0x1800229dc  jmp     short loc_1800229E3
0x1800229de  mov     ebx, 80004005h
0x1800229e3  mov     eax, ebx
0x1800229e5  mov     rcx, [rbp+57h+var_30]
0x1800229e9  xor     rcx, rsp; StackCookie
0x1800229ec  call    __security_check_cookie
0x1800229f1  mov     rbx, [rsp+0B0h+arg_8]
0x1800229f9  add     rsp, 90h
0x180022a00  pop     r15
0x180022a02  pop     r14
0x180022a04  pop     rdi
0x180022a05  pop     rsi
0x180022a06  pop     rbp
0x180022a07  retn
```
