# myNCCreatePersistedKey(unsigned __int64,unsigned __int64 *,ushort const *,ushort const *,ulong,ulong)

- ea: `0x18002b370`
- end: `0x18002b4d4`
- name: `?myNCCreatePersistedKey@@YAJ_KPEA_KPEBG2KK@Z`
- size: `356`
- prototype: `__int64 __usercall@<rax>(NCRYPT_PROV_HANDLE hProvider@<rcx>, NCRYPT_KEY_HANDLE *phKey@<rdx>, const unsigned __int16 *Src@<r8>, const unsigned __int16 *@<r9>, DWORD, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18003253c`

## callees

- `0x180020a6c`
- `0x18002b370`
- `0x18002b4dc`
- `0x18002b5e8`

## import_xrefs

- `msvcrt!wcschr` at `0x18002b3a4`
- `msvcrt!wcschr` at `0x18002b3fc`
- `msvcrt!wcschr` at `0x18002b3a4`
- `msvcrt!wcschr` at `0x18002b3fc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002b4bb`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002b3d9`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x18002b3d9`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002b499`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18002b499`
- `ncrypt!NCryptCreatePersistedKey` at `0x18002b43c`
- `ncrypt!NCryptCreatePersistedKey` at `0x18002b43c`

## pseudocode

```c
__int64 __fastcall myNCCreatePersistedKey(
        NCRYPT_PROV_HANDLE hProvider,
        NCRYPT_KEY_HANDLE *phKey,
        const unsigned __int16 *Src,
        const unsigned __int16 *a4,
        DWORD dwLegacyKeySpec,
        DWORD dwFlags)
{
  const unsigned __int16 *v8; // rbp
  wchar_t *v9; // rdi
  unsigned __int8 *v10; // rsi
  wchar_t *v11; // rax
  BOOL v12; // r15d
  int v13; // eax
  int v14; // ebx
  wchar_t *v15; // rax
  SECURITY_STATUS PersistedKey; // eax
  unsigned int v17; // edx
  const unsigned __int16 *v18; // rcx
  __int64 v19; // r9
  wchar_t *Str; // [rsp+98h] [rbp+20h] BYREF

  Str = 0;
  v8 = Src;
  v9 = 0;
  v10 = 0;
  v11 = wcschr(Src, 0x3Au);
  *phKey = 0;
  v12 = v11 != 0;
  if ( v11 )
  {
    v13 = myDupString(v8, &Str);
    v14 = v13;
    if ( v13 )
    {
      CSPrintErrorLineFile(0x36501C4u, v13);
      v9 = Str;
      goto LABEL_15;
    }
    v9 = Str;
    v15 = wcschr(Str, 0x3Au);
    v10 = (unsigned __int8 *)v15;
    if ( v15 )
    {
      *v15 = 0;
      v10 = (unsigned __int8 *)(v15 + 1);
      v8 = v9;
    }
    else
    {
      v12 = 0;
    }
  }
  PersistedKey = NCryptCreatePersistedKey(hProvider, phKey, v8, 0, dwLegacyKeySpec, dwFlags);
  v14 = PersistedKey;
  if ( PersistedKey )
  {
    v17 = 58393028;
    v18 = v8;
LABEL_14:
    CSPrintErrorLineFileData(v18, v17, PersistedKey);
    goto LABEL_15;
  }
  if ( !v12 )
    goto LABEL_18;
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)&v10[2 * v19] );
  PersistedKey = myNCSetProperty(*phKey, L"ParameterSetName", v10, 2 * (int)v19 + 2, 0);
  v14 = PersistedKey;
  if ( PersistedKey )
  {
    v17 = 59048388;
    v18 = L"ParameterSetName";
    goto LABEL_14;
  }
LABEL_15:
  if ( v14 < 0 && *phKey )
  {
    myNCFreeObject(*phKey);
    *phKey = 0;
  }
LABEL_18:
  if ( v9 )
    LocalFree(v9);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002b370  mov     rax, rsp
0x18002b373  mov     [rax+20h], r9
0x18002b377  push    rbx
0x18002b378  push    rbp
0x18002b379  push    rsi
0x18002b37a  push    rdi
0x18002b37b  push    r12
0x18002b37d  push    r13
0x18002b37f  push    r14
0x18002b381  push    r15
0x18002b383  sub     rsp, 38h
0x18002b387  xor     r13d, r13d
0x18002b38a  mov     r14, rdx
0x18002b38d  mov     r12, rcx
0x18002b390  mov     [rax+20h], r13
0x18002b394  mov     rcx, r8; Str
0x18002b397  mov     rbp, r8
0x18002b39a  mov     edi, r13d
0x18002b39d  mov     esi, r13d
0x18002b3a0  lea     edx, [r13+3Ah]; Ch
0x18002b3a4  call    cs:__imp_wcschr
0x18002b3aa  mov     r15d, r13d
0x18002b3ad  mov     [r14], r13
0x18002b3b0  test    rax, rax
0x18002b3b3  setnz   r15b
0x18002b3b7  test    rax, rax
0x18002b3ba  jz      short loc_18002B41A
0x18002b3bc  lea     rdx, [rsp+78h+Str]; unsigned __int16 **
0x18002b3c4  mov     rcx, rbp; Src
0x18002b3c7  call    ?myDupString@@YAJPEBGPEAPEAG@Z; myDupString(ushort const *,ushort * *)
0x18002b3cc  mov     ebx, eax
0x18002b3ce  test    eax, eax
0x18002b3d0  jz      short loc_18002B3EC
0x18002b3d2  mov     edx, eax
0x18002b3d4  mov     ecx, 36501C4h
0x18002b3d9  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18002b3df  mov     rdi, [rsp+78h+Str]
0x18002b3e7  jmp     loc_18002B49F
0x18002b3ec  mov     rdi, [rsp+78h+Str]
0x18002b3f4  mov     edx, 3Ah ; ':'; Ch
0x18002b3f9  mov     rcx, rdi; Str
0x18002b3fc  call    cs:__imp_wcschr
0x18002b402  mov     rsi, rax
0x18002b405  test    rax, rax
0x18002b408  jz      short loc_18002B417
0x18002b40a  mov     [rax], r13w
0x18002b40e  add     rsi, 2
0x18002b412  mov     rbp, rdi
0x18002b415  jmp     short loc_18002B41A
0x18002b417  mov     r15d, r13d
0x18002b41a  mov     eax, [rsp+78h+arg_28]
0x18002b421  xor     r9d, r9d; pszKeyName
0x18002b424  mov     [rsp+78h+dwFlags], eax; dwFlags
0x18002b428  mov     r8, rbp; pszAlgId
0x18002b42b  mov     eax, [rsp+78h+arg_20]
0x18002b432  mov     rdx, r14; phKey
0x18002b435  mov     rcx, r12; hProvider
0x18002b438  mov     [rsp+78h+dwLegacyKeySpec], eax; dwLegacyKeySpec
0x18002b43c  call    cs:__imp_NCryptCreatePersistedKey
0x18002b442  mov     ebx, eax
0x18002b444  test    eax, eax
0x18002b446  jz      short loc_18002B452
0x18002b448  mov     edx, 37B01C4h
0x18002b44d  mov     rcx, rbp
0x18002b450  jmp     short loc_18002B496
0x18002b452  test    r15d, r15d
0x18002b455  jz      short loc_18002B4B3
0x18002b457  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b45b  inc     r9
0x18002b45e  cmp     [rsi+r9*2], r13w
0x18002b463  jnz     short loc_18002B45B
0x18002b465  mov     rcx, [r14]; unsigned __int64
0x18002b468  lea     r9d, ds:2[r9*2]; unsigned int
0x18002b470  mov     r8, rsi; unsigned __int8 *
0x18002b473  mov     [rsp+78h+dwLegacyKeySpec], r13d; DWORD
0x18002b478  lea     rdx, aParametersetna; "ParameterSetName"
0x18002b47f  call    ?myNCSetProperty@@YAJ_KPEBGPEAEKK@Z; myNCSetProperty(unsigned __int64,ushort const *,uchar *,ulong,ulong)
0x18002b484  mov     ebx, eax
0x18002b486  test    eax, eax
0x18002b488  jz      short loc_18002B49F
0x18002b48a  mov     edx, 38501C4h
0x18002b48f  lea     rcx, aParametersetna; "ParameterSetName"
0x18002b496  mov     r8d, eax
0x18002b499  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18002b49f  test    ebx, ebx
0x18002b4a1  jns     short loc_18002B4B3
0x18002b4a3  mov     rcx, [r14]; unsigned __int64
0x18002b4a6  test    rcx, rcx
0x18002b4a9  jz      short loc_18002B4B3
0x18002b4ab  call    ?myNCFreeObject@@YAJ_K@Z; myNCFreeObject(unsigned __int64)
0x18002b4b0  mov     [r14], r13
0x18002b4b3  test    rdi, rdi
0x18002b4b6  jz      short loc_18002B4C1
0x18002b4b8  mov     rcx, rdi; hMem
0x18002b4bb  call    cs:__imp_LocalFree
0x18002b4c1  mov     eax, ebx
0x18002b4c3  add     rsp, 38h
0x18002b4c7  pop     r15
0x18002b4c9  pop     r14
0x18002b4cb  pop     r13
0x18002b4cd  pop     r12
0x18002b4cf  pop     rdi
0x18002b4d0  pop     rsi
0x18002b4d1  pop     rbp
0x18002b4d2  pop     rbx
0x18002b4d3  retn
```
