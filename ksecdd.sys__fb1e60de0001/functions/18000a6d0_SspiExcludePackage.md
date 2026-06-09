# SspiExcludePackage

- ea: `0x18000a6d0`
- end: `0x18000aa56`
- name: `SspiExcludePackage`
- size: `902`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity, PCWSTR pszPackageName, PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppNewAuthIdentity)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180004050`
- `0x180006830`
- `0x1800085b8`
- `0x1800087e8`
- `0x180008cf0`
- `0x1800092d0`
- `0x18000a6d0`
- `0x18000aa60`
- `0x180010a00`

## import_xrefs

- `ntoskrnl!wcsstr` at `0x18000a8ef`
- `ntoskrnl!wcsstr` at `0x18000a8ef`
- `ntoskrnl!ExAllocatePool2` at `0x18000a767`
- `ntoskrnl!ExAllocatePool2` at `0x18000a825`
- `ntoskrnl!ExAllocatePool2` at `0x18000a8a8`
- `ntoskrnl!ExAllocatePool2` at `0x18000a924`
- `ntoskrnl!ExAllocatePool2` at `0x18000a767`
- `ntoskrnl!ExAllocatePool2` at `0x18000a825`
- `ntoskrnl!ExAllocatePool2` at `0x18000a8a8`
- `ntoskrnl!ExAllocatePool2` at `0x18000a924`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a7f2`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a7f2`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiExcludePackage(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthIdentity,
        PCWSTR pszPackageName,
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE *ppNewAuthIdentity)
{
  __int64 v3; // r15
  __int64 v4; // r14
  char *Buffer; // rdi
  SECURITY_STATUS v8; // ebx
  char *v9; // rsi
  __int64 v10; // rax
  wchar_t *Pool2; // rax
  unsigned __int8 *v12; // rcx
  unsigned int v13; // edx
  wchar_t *v14; // rax
  char *v15; // rax
  char *v16; // rax
  WCHAR *v17; // rcx
  __int64 v18; // rax
  PCWSTR ppszPackedCredentialsString; // [rsp+30h] [rbp-30h] BYREF
  PCWSTR SourceString; // [rsp+38h] [rbp-28h] BYREF
  PCWSTR ppszUserName; // [rsp+40h] [rbp-20h] BYREF
  PCWSTR ppszDomainName; // [rsp+48h] [rbp-18h] BYREF
  UNICODE_STRING DestinationString; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+40h] BYREF
  PSEC_WINNT_AUTH_IDENTITY_OPAQUE AuthDataCopy; // [rsp+B8h] [rbp+58h] BYREF

  v3 = -1;
  AuthDataCopy = 0;
  v4 = -1;
  ppszUserName = 0;
  ppszDomainName = 0;
  ppszPackedCredentialsString = 0;
  DestinationString = 0;
  v25 = 0;
  Buffer = 0;
  SourceString = 0;
  do
    ++v4;
  while ( pszPackageName[v4] );
  if ( AuthIdentity )
  {
    v8 = SspiCopyAuthIdentity(AuthIdentity, &AuthDataCopy);
    if ( v8 < 0 )
      goto LABEL_30;
    v9 = (char *)AuthDataCopy;
    if ( *(_DWORD *)AuthDataCopy == 513 )
    {
      v10 = *((unsigned __int16 *)AuthDataCopy + 22);
      if ( (_WORD)v10 )
      {
        Pool2 = (wchar_t *)ExAllocatePool2(256, v10 + 4, 1230267731);
        DestinationString.Buffer = Pool2;
        if ( !Pool2 )
        {
LABEL_8:
          v8 = -1073741801;
          goto LABEL_30;
        }
        memmove(Pool2, &v9[*((unsigned int *)v9 + 10)], *((unsigned __int16 *)v9 + 22));
        DestinationString.Length = *((_WORD *)v9 + 22);
        DestinationString.MaximumLength = DestinationString.Length + 2;
        *((_WORD *)v9 + 22) = 0;
        *((_DWORD *)v9 + 10) = 0;
      }
    }
    else if ( *(_DWORD *)AuthDataCopy == 512 )
    {
      v12 = (unsigned __int8 *)*((_QWORD *)AuthDataCopy + 7);
      if ( v12 )
      {
        v13 = *((_DWORD *)AuthDataCopy + 16);
        if ( (*((_DWORD *)AuthDataCopy + 13) & 1) != 0 )
        {
          v8 = SspiHelperConvertAnsiStringToUnicodeString(v12, v13, &SourceString);
          if ( v8 < 0 )
          {
            Buffer = (char *)SourceString;
            goto LABEL_30;
          }
          RtlInitUnicodeString(&DestinationString, SourceString);
        }
        else if ( v13 )
        {
          v14 = (wchar_t *)ExAllocatePool2(256, 2 * v13 + 2 + 2LL, 1230267731);
          DestinationString.Buffer = v14;
          if ( !v14 )
            goto LABEL_8;
          memmove(v14, *((const void **)v9 + 7), 2LL * *((unsigned int *)v9 + 16));
          DestinationString.Length = 2 * *((_WORD *)v9 + 32);
          DestinationString.MaximumLength = 2 * (*((_WORD *)v9 + 32) + 1);
        }
        *((_QWORD *)v9 + 7) = 0;
        *((_DWORD *)v9 + 16) = 0;
      }
    }
    v8 = SspiEncodeAuthIdentityAsStrings(AuthDataCopy, &ppszUserName, &ppszDomainName, &ppszPackedCredentialsString);
    if ( v8 < 0 )
      goto LABEL_30;
  }
  v15 = (char *)ExAllocatePool2(256, (unsigned int)(2 * v4 + 4) + 2LL, 1230267731);
  Buffer = v15;
  if ( !v15 )
    goto LABEL_8;
  *(_WORD *)v15 = 33;
  memmove(v15 + 2, pszPackageName, 2LL * (unsigned int)v4);
  if ( DestinationString.Length )
  {
    if ( wcsstr(DestinationString.Buffer, (const wchar_t *)Buffer) )
    {
      Buffer = (char *)DestinationString.Buffer;
      DestinationString = 0;
    }
    else
    {
      SspiLocalFree(Buffer);
      v16 = (char *)ExAllocatePool2(256, 2 * (_DWORD)v4 + (unsigned int)DestinationString.Length + 6 + 2LL, 1230267731);
      Buffer = v16;
      if ( !v16 )
      {
        v8 = -1073741801;
        goto LABEL_30;
      }
      memmove(v16, DestinationString.Buffer, DestinationString.Length);
      *(_WORD *)&Buffer[DestinationString.Length & 0xFFFE] = 44;
      *(_WORD *)&Buffer[(DestinationString.Length & 0xFFFE) + 2] = 33;
      memmove(
        &Buffer[2 * ((unsigned __int64)DestinationString.Length >> 1) + 4],
        pszPackageName,
        2LL * (unsigned int)v4);
    }
  }
  v8 = SspiHelperConstructAuthdataExWMarshalledW(
         ppszUserName,
         ppszDomainName,
         ppszPackedCredentialsString,
         (const unsigned __int16 *)Buffer,
         (struct _SEC_WINNT_AUTH_IDENTITY_EXW **)ppNewAuthIdentity,
         &v25);
LABEL_30:
  if ( AuthDataCopy )
    SspiFreeAuthIdentity(AuthDataCopy);
  if ( DestinationString.Buffer )
    SspiLocalFree(DestinationString.Buffer);
  if ( ppszUserName )
    SspiLocalFree((PVOID)ppszUserName);
  if ( ppszDomainName )
    SspiLocalFree((PVOID)ppszDomainName);
  v17 = (WCHAR *)ppszPackedCredentialsString;
  if ( ppszPackedCredentialsString )
  {
    do
      ++v3;
    while ( ppszPackedCredentialsString[v3] );
    v18 = 2 * v3;
    if ( 2 * v3 )
    {
      do
      {
        *(_BYTE *)v17 = 0;
        v17 = (WCHAR *)((char *)v17 + 1);
        --v18;
      }
      while ( v18 );
      v17 = (WCHAR *)ppszPackedCredentialsString;
    }
    SspiLocalFree(v17);
  }
  if ( Buffer )
    SspiLocalFree(Buffer);
  return SspNtStatusToSecStatus((unsigned int)v8);
}

```

## disassembly

```asm
0x18000a6d0  mov     [rsp-38h+arg_8], rbx
0x18000a6d5  push    rbp
0x18000a6d6  push    rsi
0x18000a6d7  push    rdi
0x18000a6d8  push    r12
0x18000a6da  push    r13
0x18000a6dc  push    r14
0x18000a6de  push    r15
0x18000a6e0  mov     rbp, rsp
0x18000a6e3  sub     rsp, 60h
0x18000a6e7  xor     esi, esi
0x18000a6e9  xorps   xmm0, xmm0
0x18000a6ec  or      r15, 0FFFFFFFFFFFFFFFFh
0x18000a6f0  mov     [rbp+AuthDataCopy], rsi
0x18000a6f4  mov     r14, r15
0x18000a6f7  mov     [rbp+ppszUserName], rsi
0x18000a6fb  mov     r13, r8
0x18000a6fe  mov     [rbp+ppszDomainName], rsi
0x18000a702  mov     r12, rdx
0x18000a705  mov     [rbp+ppszPackedCredentialsString], rsi
0x18000a709  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a70d  mov     [rbp+arg_0], esi
0x18000a710  mov     edi, esi
0x18000a712  mov     [rbp+SourceString], rsi
0x18000a716  inc     r14
0x18000a719  cmp     [rdx+r14*2], si
0x18000a71e  jnz     short loc_18000A716
0x18000a720  test    rcx, rcx
0x18000a723  jz      loc_18000A892
0x18000a729  lea     rdx, [rbp+AuthDataCopy]; AuthDataCopy
0x18000a72d  call    SspiCopyAuthIdentity
0x18000a732  mov     ebx, eax
0x18000a734  test    eax, eax
0x18000a736  js      loc_18000A9BC
0x18000a73c  mov     rsi, [rbp+AuthDataCopy]
0x18000a740  mov     eax, [rsi]
0x18000a742  cmp     eax, 201h
0x18000a747  jnz     short loc_18000A7B7
0x18000a749  movzx   eax, word ptr [rsi+2Ch]
0x18000a74d  xor     ebx, ebx
0x18000a74f  test    ax, ax
0x18000a752  jz      loc_18000A871
0x18000a758  lea     rdx, [rax+4]
0x18000a75c  mov     ecx, 100h
0x18000a761  mov     r8d, 49546553h
0x18000a767  call    cs:__imp_ExAllocatePool2
0x18000a76e  nop     dword ptr [rax+rax+00h]
0x18000a773  mov     [rbp+DestinationString.Buffer], rax
0x18000a777  test    rax, rax
0x18000a77a  jnz     short loc_18000A788
0x18000a77c  mov     ebx, 0C0000017h
0x18000a781  xor     esi, esi
0x18000a783  jmp     loc_18000A9BC
0x18000a788  mov     edx, [rsi+28h]
0x18000a78b  mov     rcx, rax; void *
0x18000a78e  movzx   r8d, word ptr [rsi+2Ch]; Size
0x18000a793  add     rdx, rsi; Src
0x18000a796  call    memmove
0x18000a79b  movzx   eax, word ptr [rsi+2Ch]
0x18000a79f  mov     [rbp+DestinationString.Length], ax
0x18000a7a3  add     ax, 2
0x18000a7a7  mov     [rbp+DestinationString.MaximumLength], ax
0x18000a7ab  mov     [rsi+2Ch], bx
0x18000a7af  mov     [rsi+28h], ebx
0x18000a7b2  jmp     loc_18000A871
0x18000a7b7  cmp     eax, 200h
0x18000a7bc  jnz     loc_18000A871
0x18000a7c2  mov     rcx, [rsi+38h]; unsigned __int8 *
0x18000a7c6  xor     ebx, ebx
0x18000a7c8  test    rcx, rcx
0x18000a7cb  jz      loc_18000A871
0x18000a7d1  mov     eax, [rsi+34h]
0x18000a7d4  mov     edx, [rsi+40h]; unsigned int
0x18000a7d7  test    al, 1
0x18000a7d9  jz      short loc_18000A80B
0x18000a7db  lea     r8, [rbp+SourceString]; unsigned __int16 **
0x18000a7df  call    ?SspiHelperConvertAnsiStringToUnicodeString@@YAJPEAEKPEAPEBG@Z; SspiHelperConvertAnsiStringToUnicodeString(uchar *,ulong,ushort const * *)
0x18000a7e4  mov     ebx, eax
0x18000a7e6  test    eax, eax
0x18000a7e8  js      short loc_18000A802
0x18000a7ea  mov     rdx, [rbp+SourceString]; SourceString
0x18000a7ee  lea     rcx, [rbp+DestinationString]; DestinationString
0x18000a7f2  call    cs:__imp_RtlInitUnicodeString
0x18000a7f9  nop     dword ptr [rax+rax+00h]
0x18000a7fe  xor     ebx, ebx
0x18000a800  jmp     short loc_18000A86A
0x18000a802  mov     rdi, [rbp+SourceString]
0x18000a806  jmp     loc_18000A781
0x18000a80b  test    edx, edx
0x18000a80d  jz      short loc_18000A86A
0x18000a80f  lea     edx, ds:2[rdx*2]
0x18000a816  mov     ecx, 100h
0x18000a81b  add     rdx, 2
0x18000a81f  mov     r8d, 49546553h
0x18000a825  call    cs:__imp_ExAllocatePool2
0x18000a82c  nop     dword ptr [rax+rax+00h]
0x18000a831  mov     [rbp+DestinationString.Buffer], rax
0x18000a835  test    rax, rax
0x18000a838  jz      loc_18000A77C
0x18000a83e  mov     r8d, [rsi+40h]
0x18000a842  mov     rcx, rax; void *
0x18000a845  mov     rdx, [rsi+38h]; Src
0x18000a849  add     r8, r8; Size
0x18000a84c  call    memmove
0x18000a851  movzx   eax, word ptr [rsi+40h]
0x18000a855  add     ax, ax
0x18000a858  mov     [rbp+DestinationString.Length], ax
0x18000a85c  movzx   eax, word ptr [rsi+40h]
0x18000a860  inc     ax
0x18000a863  add     ax, ax
0x18000a866  mov     [rbp+DestinationString.MaximumLength], ax
0x18000a86a  mov     [rsi+38h], rbx
0x18000a86e  mov     [rsi+40h], ebx
0x18000a871  mov     rcx, [rbp+AuthDataCopy]; pAuthIdentity
0x18000a875  lea     r9, [rbp+ppszPackedCredentialsString]; ppszPackedCredentialsString
0x18000a879  lea     r8, [rbp+ppszDomainName]; ppszDomainName
0x18000a87d  lea     rdx, [rbp+ppszUserName]; ppszUserName
0x18000a881  call    SspiEncodeAuthIdentityAsStrings
0x18000a886  xor     esi, esi
0x18000a888  mov     ebx, eax
0x18000a88a  test    eax, eax
0x18000a88c  js      loc_18000A9BC
0x18000a892  lea     esi, [r14+r14]
0x18000a896  mov     ecx, 100h
0x18000a89b  lea     edx, [rsi+4]
0x18000a89e  mov     r8d, 49546553h
0x18000a8a4  add     rdx, 2
0x18000a8a8  call    cs:__imp_ExAllocatePool2
0x18000a8af  nop     dword ptr [rax+rax+00h]
0x18000a8b4  mov     rdi, rax
0x18000a8b7  test    rax, rax
0x18000a8ba  jz      loc_18000A77C
0x18000a8c0  mov     ebx, r14d
0x18000a8c3  lea     rcx, [rax+2]; void *
0x18000a8c7  add     rbx, rbx
0x18000a8ca  mov     word ptr [rax], 21h ; '!'
0x18000a8cf  mov     r8, rbx; Size
0x18000a8d2  mov     rdx, r12; Src
0x18000a8d5  call    memmove
0x18000a8da  xor     r14d, r14d
0x18000a8dd  cmp     [rbp+DestinationString.Length], r14w
0x18000a8e2  jz      loc_18000A996
0x18000a8e8  mov     rcx, [rbp+DestinationString.Buffer]; Str
0x18000a8ec  mov     rdx, rdi; SubStr
0x18000a8ef  call    cs:__imp_wcsstr
0x18000a8f6  nop     dword ptr [rax+rax+00h]
0x18000a8fb  test    rax, rax
0x18000a8fe  jnz     loc_18000A98B
0x18000a904  mov     rcx, rdi; DataBuffer
0x18000a907  call    SspiLocalFree
0x18000a90c  movzx   edx, [rbp+DestinationString.Length]
0x18000a910  mov     ecx, 100h
0x18000a915  add     edx, 6
0x18000a918  mov     r8d, 49546553h
0x18000a91e  add     edx, esi
0x18000a920  add     rdx, 2
0x18000a924  call    cs:__imp_ExAllocatePool2
0x18000a92b  nop     dword ptr [rax+rax+00h]
0x18000a930  xor     esi, esi
0x18000a932  mov     rdi, rax
0x18000a935  test    rax, rax
0x18000a938  jnz     short loc_18000A941
0x18000a93a  mov     ebx, 0C0000017h
0x18000a93f  jmp     short loc_18000A9BC
0x18000a941  movzx   r8d, [rbp+DestinationString.Length]; Size
0x18000a946  mov     rcx, rdi; void *
0x18000a949  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x18000a94d  call    memmove
0x18000a952  movzx   eax, [rbp+DestinationString.Length]
0x18000a956  mov     r8, rbx; Size
0x18000a959  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000a95d  mov     rdx, r12; Src
0x18000a960  mov     word ptr [rax+rdi], 2Ch ; ','
0x18000a966  movzx   eax, [rbp+DestinationString.Length]
0x18000a96a  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000a96e  mov     word ptr [rax+rdi+2], 21h ; '!'
0x18000a975  movzx   eax, [rbp+DestinationString.Length]
0x18000a979  shr     rax, 1
0x18000a97c  add     rax, 2
0x18000a980  lea     rcx, [rdi+rax*2]; void *
0x18000a984  call    memmove
0x18000a989  jmp     short loc_18000A998
0x18000a98b  mov     rdi, [rbp+DestinationString.Buffer]
0x18000a98f  xorps   xmm0, xmm0
0x18000a992  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18000a996  xor     esi, esi
0x18000a998  mov     r8, [rbp+ppszPackedCredentialsString]; unsigned __int16 *
0x18000a99c  lea     rax, [rbp+arg_0]
0x18000a9a0  mov     rdx, [rbp+ppszDomainName]; unsigned __int16 *
0x18000a9a4  mov     r9, rdi; unsigned __int16 *
0x18000a9a7  mov     rcx, [rbp+ppszUserName]; unsigned __int16 *
0x18000a9ab  mov     [rsp+60h+var_38], rax; unsigned int *
0x18000a9b0  mov     [rsp+60h+var_40], r13; struct _SEC_WINNT_AUTH_IDENTITY_EXW **
0x18000a9b5  call    ?SspiHelperConstructAuthdataExWMarshalledW@@YAJPEBG000PEAPEAU_SEC_WINNT_AUTH_IDENTITY_EXW@@PEAK@Z; SspiHelperConstructAuthdataExWMarshalledW(ushort const *,ushort const *,ushort const *,ushort const *,_SEC_WINNT_AUTH_IDENTITY_EXW * *,ulong *)
0x18000a9ba  mov     ebx, eax
0x18000a9bc  mov     rcx, [rbp+AuthDataCopy]; AuthData
0x18000a9c0  test    rcx, rcx
0x18000a9c3  jz      short loc_18000A9CA
0x18000a9c5  call    SspiFreeAuthIdentity
0x18000a9ca  mov     rcx, [rbp+DestinationString.Buffer]; DataBuffer
0x18000a9ce  test    rcx, rcx
0x18000a9d1  jz      short loc_18000A9D8
0x18000a9d3  call    SspiLocalFree
0x18000a9d8  mov     rcx, [rbp+ppszUserName]; DataBuffer
0x18000a9dc  test    rcx, rcx
0x18000a9df  jz      short loc_18000A9E6
0x18000a9e1  call    SspiLocalFree
0x18000a9e6  mov     rcx, [rbp+ppszDomainName]; DataBuffer
0x18000a9ea  test    rcx, rcx
0x18000a9ed  jz      short loc_18000A9F4
0x18000a9ef  call    SspiLocalFree
0x18000a9f4  mov     rcx, [rbp+ppszPackedCredentialsString]
0x18000a9f8  test    rcx, rcx
0x18000a9fb  jz      short loc_18000AA29
0x18000a9fd  inc     r15
0x18000aa00  cmp     [rcx+r15*2], si
0x18000aa05  jnz     short loc_18000A9FD
0x18000aa07  lea     rax, [r15+r15]
0x18000aa0b  test    rax, rax
0x18000aa0e  jz      short loc_18000AA24
0x18000aa10  mov     edx, 1
0x18000aa15  mov     [rcx], sil
0x18000aa18  add     rcx, rdx
0x18000aa1b  sub     rax, rdx
0x18000aa1e  jnz     short loc_18000AA15
0x18000aa20  mov     rcx, [rbp+ppszPackedCredentialsString]; DataBuffer
0x18000aa24  call    SspiLocalFree
0x18000aa29  test    rdi, rdi
0x18000aa2c  jz      short loc_18000AA36
0x18000aa2e  mov     rcx, rdi; DataBuffer
0x18000aa31  call    SspiLocalFree
0x18000aa36  mov     ecx, ebx
0x18000aa38  call    SspNtStatusToSecStatus
0x18000aa3d  mov     rbx, [rsp+60h+arg_8]
0x18000aa45  add     rsp, 60h
0x18000aa49  pop     r15
0x18000aa4b  pop     r14
0x18000aa4d  pop     r13
0x18000aa4f  pop     r12
0x18000aa51  pop     rdi
0x18000aa52  pop     rsi
0x18000aa53  pop     rbp
0x18000aa54  retn
```
