# CCommunityTransport::HashToken(tagUSERNAMETOKEN *)

- ea: `0x1800afb18`
- end: `0x1800afeeb`
- name: `?HashToken@CCommunityTransport@@AEAAJPEAUtagUSERNAMETOKEN@@@Z`
- size: `979`
- prototype: `int(CCommunityTransport *__hidden this, struct tagUSERNAMETOKEN *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800af160`

## callees

- `0x180012cd0`
- `0x180022420`
- `0x1800247c8`
- `0x1800ae5c8`
- `0x1800afb18`
- `0x1800c9fe8`
- `0x1800cb240`
- `0x1800cb284`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `ADVAPI32!CryptAcquireContextA` at `0x1800afba8`
- `ADVAPI32!CryptAcquireContextA` at `0x1800afba8`
- `ADVAPI32!CryptGenRandom` at `0x1800afc61`
- `ADVAPI32!CryptGenRandom` at `0x1800afc61`
- `ADVAPI32!CryptCreateHash` at `0x1800afbcc`
- `ADVAPI32!CryptCreateHash` at `0x1800afbcc`
- `ADVAPI32!CryptHashData` at `0x1800afd4b`
- `ADVAPI32!CryptHashData` at `0x1800afd4b`
- `ADVAPI32!CryptGetHashParam` at `0x1800afd97`
- `ADVAPI32!CryptGetHashParam` at `0x1800afd97`
- `KERNEL32!GetSystemTime` at `0x1800afbf3`
- `KERNEL32!GetSystemTime` at `0x1800afbf3`

## pseudocode

```c
__int64 __fastcall CCommunityTransport::HashToken(CCommunityTransport *this, struct tagUSERNAMETOKEN *a2)
{
  char *v5; // rdi
  int LastError; // ebx
  CCommunityTransport *v7; // rcx
  int v8; // edx
  __int64 i; // r8
  __int64 v10; // r9
  int j; // r10d
  int v12; // eax
  CCommunityTransport *v13; // rcx
  DWORD pdwDataLen; // [rsp+50h] [rbp-B0h] BYREF
  HCRYPTPROV phProv; // [rsp+58h] [rbp-A8h] BYREF
  HCRYPTHASH phHash; // [rsp+60h] [rbp-A0h] BYREF
  char *v17; // [rsp+68h] [rbp-98h] BYREF
  char *v18; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v19; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+80h] [rbp-80h] BYREF
  BYTE pbData[8]; // [rsp+90h] [rbp-70h] BYREF
  WORD wHour; // [rsp+98h] [rbp-68h]
  BYTE v23[272]; // [rsp+C0h] [rbp-40h] BYREF

  v18 = 0;
  v17 = 0;
  memset_0(v23, 0, 0x104u);
  if ( !a2 )
    return 2147942487LL;
  phProv = 0;
  phHash = 0;
  if ( CryptAcquireContextA(&phProv, 0, 0, 1u, 0xF0000040) )
    CryptCreateHash(phProv, 0x8004u, 0, 0, &phHash);
  v5 = (char *)ZeroAllocate(0x15u);
  if ( v5 )
  {
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    LastError = StringCchPrintfA(
                  v5,
                  0x15u,
                  "%04d-%02d-%02dT%02d:%02d:%02dZ",
                  SystemTime.wYear,
                  SystemTime.wMonth,
                  SystemTime.wDay,
                  SystemTime.wHour,
                  SystemTime.wMinute,
                  SystemTime.wSecond);
    if ( LastError >= 0 )
    {
      if ( phProv )
      {
        if ( !CryptGenRandom(phProv, 0xAu, (BYTE *)&SystemTime) )
        {
          LastError = HrGetLastError();
          if ( LastError < 0 )
            goto LABEL_38;
        }
        v8 = 0;
        *(_QWORD *)pbData = *(_QWORD *)&SystemTime.wYear;
        wHour = SystemTime.wHour;
        do
          ++v8;
        while ( v8 < 10 );
        for ( i = 0; i != 20; ++i )
        {
          if ( (unsigned int)v8 < 0x27 )
          {
            v7 = (CCommunityTransport *)v8++;
            pbData[(_QWORD)v7] = v5[i];
          }
        }
        if ( this != (CCommunityTransport *)-12436LL )
        {
          v10 = -1;
          do
            ++v10;
          while ( *((_BYTE *)this + v10 + 12436) );
          for ( j = 0; j < (int)v10; ++j )
          {
            if ( (unsigned int)v8 < 0x27 )
            {
              v7 = (CCommunityTransport *)v8++;
              pbData[(_QWORD)v7] = *((_BYTE *)this + j + 12436);
            }
          }
        }
        pdwDataLen = 0;
        LastError = CCommunityTransport::EncodeToBase64(v7, (const char *)&SystemTime, 0xAu, &v18, &pdwDataLen);
        if ( LastError < 0 )
          goto LABEL_38;
        LastError = -2147418113;
        if ( !CCryptHash::HasProviderAndHash((CCryptHash *)&phProv) )
          goto LABEL_38;
        if ( CryptHashData(phHash, pbData, 0x27u, 0) || (v12 = HrGetLastError(), v12 >= 0) )
        {
          pdwDataLen = 260;
          if ( !CCryptHash::HasProviderAndHash((CCryptHash *)&phProv) )
            goto LABEL_38;
          if ( !CryptGetHashParam(phHash, 2u, v23, &pdwDataLen, 0) )
          {
            LastError = HrGetLastError();
            if ( LastError < 0 )
              goto LABEL_38;
          }
          v19 = 0;
          LastError = CCommunityTransport::EncodeToBase64(v13, (const char *)v23, pdwDataLen, &v17, &v19);
          if ( LastError < 0 )
            goto LABEL_38;
          LastError = StringCchCopyA((char *)a2, 0x100u, (const char *)this + 12180);
          if ( LastError < 0 )
            goto LABEL_38;
          LastError = StringCchCopyA((char *)a2 + 256, 0x4Eu, v17);
          if ( LastError < 0 )
            goto LABEL_38;
          LastError = StringCchCopyA((char *)a2 + 334, 0x14u, v18);
          if ( LastError < 0 )
            goto LABEL_38;
          v12 = StringCchCopyA((char *)a2 + 354, 0x15u, v5);
        }
        LastError = v12;
      }
      else
      {
        LastError = -2146885626;
      }
    }
  }
  else
  {
    LastError = -2147024882;
  }
LABEL_38:
  if ( v17 )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    v17 = 0;
  }
  if ( v18 )
  {
    ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
    v18 = 0;
  }
  if ( v5 )
    ((void (__fastcall *)(LPMALLOC, char *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v5);
  CCryptHash::~CCryptHash((CCryptHash *)&phProv);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800afb18  mov     [rsp-8+arg_10], rbx
0x1800afb1d  mov     [rsp-8+arg_18], rsi
0x1800afb22  push    rbp
0x1800afb23  push    rdi
0x1800afb24  push    r14
0x1800afb26  lea     rbp, [rsp-0E0h]
0x1800afb2e  sub     rsp, 1E0h
0x1800afb35  mov     rax, cs:__security_cookie
0x1800afb3c  xor     rax, rsp
0x1800afb3f  mov     [rbp+0F0h+var_20], rax
0x1800afb46  mov     rsi, rdx
0x1800afb49  mov     [rsp+1F0h+var_180], 0
0x1800afb52  mov     r14, rcx
0x1800afb55  mov     [rsp+1F0h+var_188], 0
0x1800afb5e  xor     edx, edx; Val
0x1800afb60  lea     rcx, [rbp+0F0h+var_130]; void *
0x1800afb64  mov     r8d, 104h; Size
0x1800afb6a  call    memset_0
0x1800afb6f  test    rsi, rsi
0x1800afb72  jnz     short loc_1800AFB7E
0x1800afb74  mov     eax, 80070057h
0x1800afb79  jmp     loc_1800AFEC4
0x1800afb7e  mov     r9d, 1; dwProvType
0x1800afb84  mov     [rsp+1F0h+phProv], 0
0x1800afb8d  xor     r8d, r8d; szProvider
0x1800afb90  mov     [rsp+1F0h+phHash], 0
0x1800afb99  xor     edx, edx; szContainer
0x1800afb9b  mov     [rsp+1F0h+dwFlags], 0F0000040h; dwFlags
0x1800afba3  lea     rcx, [rsp+1F0h+phProv]; phProv
0x1800afba8  call    cs:__imp_CryptAcquireContextA
0x1800afbae  test    eax, eax
0x1800afbb0  jz      short loc_1800AFBD2
0x1800afbb2  mov     rcx, [rsp+1F0h+phProv]; hProv
0x1800afbb7  lea     rax, [rsp+1F0h+phHash]
0x1800afbbc  xor     r9d, r9d; dwFlags
0x1800afbbf  mov     qword ptr [rsp+1F0h+dwFlags], rax; phHash
0x1800afbc4  xor     r8d, r8d; hKey
0x1800afbc7  mov     edx, 8004h; Algid
0x1800afbcc  call    cs:__imp_CryptCreateHash
0x1800afbd2  mov     ecx, 15h; Size
0x1800afbd7  call    ?ZeroAllocate@@YAPEAXK@Z; ZeroAllocate(ulong)
0x1800afbdc  mov     rdi, rax
0x1800afbdf  test    rax, rax
0x1800afbe2  jz      loc_1800AFE4C
0x1800afbe8  xorps   xmm0, xmm0
0x1800afbeb  lea     rcx, [rbp+0F0h+SystemTime]; lpSystemTime
0x1800afbef  movups  xmmword ptr [rbp+0F0h+SystemTime.wYear], xmm0
0x1800afbf3  call    cs:__imp_GetSystemTime
0x1800afbf9  movzx   ecx, [rbp+0F0h+SystemTime.wSecond]
0x1800afbfd  movzx   edx, [rbp+0F0h+SystemTime.wMinute]
0x1800afc01  movzx   r8d, [rbp+0F0h+SystemTime.wHour]
0x1800afc06  movzx   r10d, [rbp+0F0h+SystemTime.wDay]
0x1800afc0b  movzx   r11d, [rbp+0F0h+SystemTime.wMonth]
0x1800afc10  movzx   r9d, [rbp+0F0h+SystemTime.wYear]
0x1800afc15  mov     [rsp+1F0h+var_1B0], ecx
0x1800afc19  mov     rcx, rdi; char *
0x1800afc1c  mov     [rsp+1F0h+var_1B8], edx
0x1800afc20  mov     edx, 15h; unsigned __int64
0x1800afc25  mov     [rsp+1F0h+var_1C0], r8d
0x1800afc2a  lea     r8, a04d02d02dt02d0_0; "%04d-%02d-%02dT%02d:%02d:%02dZ"
0x1800afc31  mov     [rsp+1F0h+var_1C8], r10d
0x1800afc36  mov     [rsp+1F0h+dwFlags], r11d
0x1800afc3b  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800afc40  mov     ebx, eax
0x1800afc42  test    eax, eax
0x1800afc44  js      loc_1800AFE51
0x1800afc4a  mov     rcx, [rsp+1F0h+phProv]; hProv
0x1800afc4f  test    rcx, rcx
0x1800afc52  jz      loc_1800AFE45
0x1800afc58  lea     r8, [rbp+0F0h+SystemTime]; pbBuffer
0x1800afc5c  mov     edx, 0Ah; dwLen
0x1800afc61  call    cs:__imp_CryptGenRandom
0x1800afc67  test    eax, eax
0x1800afc69  jnz     short loc_1800AFC7A
0x1800afc6b  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800afc70  mov     ebx, eax
0x1800afc72  test    eax, eax
0x1800afc74  js      loc_1800AFE51
0x1800afc7a  mov     rax, qword ptr [rbp+0F0h+SystemTime.wYear]
0x1800afc7e  xor     edx, edx
0x1800afc80  mov     qword ptr [rbp+0F0h+pbData], rax
0x1800afc84  movzx   eax, [rbp+0F0h+SystemTime.wHour]
0x1800afc88  mov     [rbp+0F0h+var_158], ax
0x1800afc8c  inc     edx
0x1800afc8e  cmp     edx, 0Ah
0x1800afc91  jl      short loc_1800AFC8C
0x1800afc93  xor     r8d, r8d
0x1800afc96  cmp     edx, 27h ; '''
0x1800afc99  jnb     short loc_1800AFCA8
0x1800afc9b  mov     al, [rdi+r8]
0x1800afc9f  movsxd  rcx, edx
0x1800afca2  inc     edx
0x1800afca4  mov     [rbp+rcx+0F0h+pbData], al
0x1800afca8  inc     r8
0x1800afcab  cmp     r8, 14h
0x1800afcaf  jnz     short loc_1800AFC96
0x1800afcb1  lea     rax, [r14+3094h]
0x1800afcb8  test    rax, rax
0x1800afcbb  jz      short loc_1800AFCF4
0x1800afcbd  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800afcc1  inc     r9
0x1800afcc4  cmp     byte ptr [rax+r9], 0
0x1800afcc9  jnz     short loc_1800AFCC1
0x1800afccb  xor     r10d, r10d
0x1800afcce  test    r9d, r9d
0x1800afcd1  jle     short loc_1800AFCF4
0x1800afcd3  cmp     edx, 27h ; '''
0x1800afcd6  jnb     short loc_1800AFCEC
0x1800afcd8  movsxd  rcx, edx; this
0x1800afcdb  inc     edx
0x1800afcdd  movsxd  rax, r10d
0x1800afce0  mov     al, [rax+r14+3094h]
0x1800afce8  mov     [rbp+rcx+0F0h+pbData], al
0x1800afcec  inc     r10d
0x1800afcef  cmp     r10d, r9d
0x1800afcf2  jl      short loc_1800AFCD3
0x1800afcf4  lea     rax, [rsp+1F0h+pdwDataLen]
0x1800afcf9  mov     [rsp+1F0h+pdwDataLen], 0
0x1800afd01  lea     r9, [rsp+1F0h+var_180]; char **
0x1800afd06  mov     qword ptr [rsp+1F0h+dwFlags], rax; unsigned int *
0x1800afd0b  mov     r8d, 0Ah; unsigned int
0x1800afd11  lea     rdx, [rbp+0F0h+SystemTime]; char *
0x1800afd15  call    ?EncodeToBase64@CCommunityTransport@@AEAAJPEBDKPEAPEADPEAK@Z; CCommunityTransport::EncodeToBase64(char const *,ulong,char * *,ulong *)
0x1800afd1a  mov     ebx, eax
0x1800afd1c  test    eax, eax
0x1800afd1e  js      loc_1800AFE51
0x1800afd24  lea     rcx, [rsp+1F0h+phProv]; this
0x1800afd29  mov     ebx, 8000FFFFh
0x1800afd2e  call    ?HasProviderAndHash@CCryptHash@@AEBA_NXZ; CCryptHash::HasProviderAndHash(void)
0x1800afd33  test    al, al
0x1800afd35  jz      loc_1800AFE51
0x1800afd3b  mov     rcx, [rsp+1F0h+phHash]; hHash
0x1800afd40  lea     rdx, [rbp+0F0h+pbData]; pbData
0x1800afd44  xor     r9d, r9d; dwFlags
0x1800afd47  lea     r8d, [r9+27h]; dwDataLen
0x1800afd4b  call    cs:__imp_CryptHashData
0x1800afd51  test    eax, eax
0x1800afd53  jnz     short loc_1800AFD62
0x1800afd55  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800afd5a  test    eax, eax
0x1800afd5c  js      loc_1800AFE41
0x1800afd62  lea     rcx, [rsp+1F0h+phProv]; this
0x1800afd67  mov     [rsp+1F0h+pdwDataLen], 104h
0x1800afd6f  call    ?HasProviderAndHash@CCryptHash@@AEBA_NXZ; CCryptHash::HasProviderAndHash(void)
0x1800afd74  test    al, al
0x1800afd76  jz      loc_1800AFE51
0x1800afd7c  mov     rcx, [rsp+1F0h+phHash]; hHash
0x1800afd81  lea     r9, [rsp+1F0h+pdwDataLen]; pdwDataLen
0x1800afd86  lea     r8, [rbp+0F0h+var_130]; pbData
0x1800afd8a  mov     [rsp+1F0h+dwFlags], 0; dwFlags
0x1800afd92  mov     edx, 2; dwParam
0x1800afd97  call    cs:__imp_CryptGetHashParam
0x1800afd9d  test    eax, eax
0x1800afd9f  jnz     short loc_1800AFDB0
0x1800afda1  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x1800afda6  mov     ebx, eax
0x1800afda8  test    eax, eax
0x1800afdaa  js      loc_1800AFE51
0x1800afdb0  mov     r8d, [rsp+1F0h+pdwDataLen]; unsigned int
0x1800afdb5  lea     rax, [rsp+1F0h+var_178]
0x1800afdba  lea     r9, [rsp+1F0h+var_188]; char **
0x1800afdbf  mov     qword ptr [rsp+1F0h+dwFlags], rax; unsigned int *
0x1800afdc4  lea     rdx, [rbp+0F0h+var_130]; char *
0x1800afdc8  mov     [rsp+1F0h+var_178], 0
0x1800afdd0  call    ?EncodeToBase64@CCommunityTransport@@AEAAJPEBDKPEAPEADPEAK@Z; CCommunityTransport::EncodeToBase64(char const *,ulong,char * *,ulong *)
0x1800afdd5  mov     ebx, eax
0x1800afdd7  test    eax, eax
0x1800afdd9  js      short loc_1800AFE51
0x1800afddb  lea     r8, [r14+2F94h]; char *
0x1800afde2  mov     edx, 100h; unsigned __int64
0x1800afde7  mov     rcx, rsi; char *
0x1800afdea  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800afdef  mov     ebx, eax
0x1800afdf1  test    eax, eax
0x1800afdf3  js      short loc_1800AFE51
0x1800afdf5  mov     r8, [rsp+1F0h+var_188]; char *
0x1800afdfa  lea     rcx, [rsi+100h]; char *
0x1800afe01  mov     edx, 4Eh ; 'N'; unsigned __int64
0x1800afe06  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800afe0b  mov     ebx, eax
0x1800afe0d  test    eax, eax
0x1800afe0f  js      short loc_1800AFE51
0x1800afe11  mov     r8, [rsp+1F0h+var_180]; char *
0x1800afe16  lea     rcx, [rsi+14Eh]; char *
0x1800afe1d  mov     edx, 14h; unsigned __int64
0x1800afe22  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800afe27  mov     ebx, eax
0x1800afe29  test    eax, eax
0x1800afe2b  js      short loc_1800AFE51
0x1800afe2d  lea     rcx, [rsi+162h]; char *
0x1800afe34  mov     r8, rdi; char *
0x1800afe37  mov     edx, 15h; unsigned __int64
0x1800afe3c  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800afe41  mov     ebx, eax
0x1800afe43  jmp     short loc_1800AFE51
0x1800afe45  mov     ebx, 80092006h
0x1800afe4a  jmp     short loc_1800AFE51
0x1800afe4c  mov     ebx, 8007000Eh
0x1800afe51  mov     rdx, [rsp+1F0h+var_188]
0x1800afe56  test    rdx, rdx
0x1800afe59  jz      short loc_1800AFE77
0x1800afe5b  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800afe62  mov     rax, [rcx]
0x1800afe65  mov     rax, [rax+28h]
0x1800afe69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe6e  mov     [rsp+1F0h+var_188], 0
0x1800afe77  mov     rdx, [rsp+1F0h+var_180]
0x1800afe7c  test    rdx, rdx
0x1800afe7f  jz      short loc_1800AFE9D
0x1800afe81  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800afe88  mov     rax, [rcx]
0x1800afe8b  mov     rax, [rax+28h]
0x1800afe8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afe94  mov     [rsp+1F0h+var_180], 0
0x1800afe9d  test    rdi, rdi
0x1800afea0  jz      short loc_1800AFEB8
0x1800afea2  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x1800afea9  mov     rdx, rdi
0x1800afeac  mov     rax, [rcx]
0x1800afeaf  mov     rax, [rax+28h]
0x1800afeb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afeb8  lea     rcx, [rsp+1F0h+phProv]; this
0x1800afebd  call    ??1CCryptHash@@QEAA@XZ; CCryptHash::~CCryptHash(void)
0x1800afec2  mov     eax, ebx
0x1800afec4  mov     rcx, [rbp+0F0h+var_20]
0x1800afecb  xor     rcx, rsp; StackCookie
0x1800afece  call    __security_check_cookie
0x1800afed3  lea     r11, [rsp+1F0h+var_10]
0x1800afedb  mov     rbx, [r11+30h]
0x1800afedf  mov     rsi, [r11+38h]
0x1800afee3  mov     rsp, r11
0x1800afee6  pop     r14
0x1800afee8  pop     rdi
0x1800afee9  pop     rbp
0x1800afeea  retn
```
