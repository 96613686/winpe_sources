# NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)

- ea: `0x18002bbe0`
- end: `0x18002bec8`
- name: `?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z`
- size: `744`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18002b3c0`
- `0x18002b590`
- `0x18002c310`

## callees

- `0x180007518`
- `0x18000e910`
- `0x18002bbe0`
- `0x18002c758`
- `0x180065bec`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bdd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002bdd2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002be68`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002bcc4`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002bcc4`
- `ntdll!RtlFreeUnicodeString` at `0x18002be40`
- `ntdll!RtlFreeUnicodeString` at `0x18002be40`
- `ntdll!RtlInitUnicodeString` at `0x18002bcab`
- `ntdll!RtlInitUnicodeString` at `0x18002bcab`
- `bcrypt!BCryptHashData` at `0x18002bd31`
- `bcrypt!BCryptHashData` at `0x18002bd31`
- `bcrypt!BCryptFinishHash` at `0x18002bd60`
- `bcrypt!BCryptFinishHash` at `0x18002bd60`
- `bcrypt!BCryptDestroyHash` at `0x18002be7e`
- `bcrypt!BCryptDestroyHash` at `0x18002be7e`
- `bcrypt!BCryptCreateHash` at `0x18002bd00`
- `bcrypt!BCryptCreateHash` at `0x18002bd00`

## string_xrefs

- `0x18002bd12`: `BCryptCreateHash failed 0x%08X\n`

## pseudocode

```c
__int64 __fastcall NetpGetSecretName(
        int a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  const wchar_t *v4; // r14
  __int64 v8; // rsi
  unsigned __int16 *v9; // rdi
  NTSTATUS v10; // eax
  WCHAR *v11; // r15
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rdx
  unsigned int v14; // r9d
  __int64 v15; // rax
  __int64 v16; // rdx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-C0h] BYREF
  PCWSTR SourceString; // [rsp+48h] [rbp-B8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  UCHAR pbOutput[32]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v23[72]; // [rsp+90h] [rbp-70h] BYREF

  v4 = L"_SC_GMSA_DPAPI_{C6810348-4834-4a1e-817D-5838604E6004}_";
  if ( !a1 )
    v4 = L"_SC_GMSA_{84A78B8C-56EE-465b-8496-FFB35A1B52A7}_";
  v8 = -1;
  do
    ++v8;
  while ( v4[v8] );
  SourceString = 0;
  phHash = 0;
  v9 = 0;
  DestinationString = 0;
  UnicodeString = 0;
  NlPrintRoutine(0x40u, L"Entering NetpGetSecretName\n");
  v10 = NetpConcatenate(1, (unsigned __int16 **)&SourceString, 2u, a3, a2);
  v11 = (WCHAR *)SourceString;
  v12 = v10;
  if ( v10 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, SourceString);
    v10 = RtlUpcaseUnicodeString(&UnicodeString, &DestinationString, 1u);
    v12 = v10;
    if ( v10 >= 0 )
    {
      v10 = BCryptCreateHash(NlGlobalSha256Handle, &phHash, 0, 0, 0, 0, 0);
      v12 = v10;
      if ( v10 >= 0 )
      {
        v10 = BCryptHashData(phHash, (PUCHAR)UnicodeString.Buffer, UnicodeString.Length, 0);
        v12 = v10;
        if ( v10 >= 0 )
        {
          v10 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          v12 = v10;
          if ( v10 >= 0 )
          {
            v14 = 0;
            do
            {
              v15 = v14;
              v16 = 2 * v14++;
              LOBYTE(v15) = pbOutput[v15];
              v23[v16] = a0123456789abcd[v15 & 0xF];
              v23[(unsigned int)(v16 + 1)] = a0123456789abcd[(unsigned __int64)(unsigned __int8)v15 >> 4];
            }
            while ( v14 < 0x20 );
            v23[64] = 0;
            v9 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (unsigned int)(v8 + 65));
            if ( !v9 )
            {
              v12 = -1073741801;
              NlPrintRoutine(0x40u, L"LocalAlloc failed 0x%08X\n", 3221225495LL);
              goto LABEL_24;
            }
            v10 = RtlStringCchPrintfW(v9, (unsigned int)(v8 + 65), L"%ws%ws", v4, v23);
            v12 = v10;
            if ( v10 >= 0 )
            {
              *a4 = v9;
              v12 = 0;
              v9 = 0;
              goto LABEL_24;
            }
            v13 = L"RtlStringCchPrintfW failed 0x%08X\n";
          }
          else
          {
            v13 = L"BCryptFinishHash failed 0x%08X\n";
          }
        }
        else
        {
          v13 = L"BCryptHashData failed 0x%08X\n";
        }
      }
      else
      {
        v13 = L"BCryptCreateHash failed 0x%08X\n";
      }
    }
    else
    {
      v13 = L"RtlUpcaseUnicodeString failed 0x%08X\n";
    }
  }
  else
  {
    v13 = L"NetpConcatenate failed 0x%08X\n";
  }
  NlPrintRoutine(0x40u, v13, (unsigned int)v10);
LABEL_24:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  if ( v9 )
    LocalFree(v9);
  if ( v11 )
    LocalFree(v11);
  if ( phHash )
    BCryptDestroyHash(phHash);
  NlPrintRoutine(0x40u, L"Exiting NetpGetSecretName with Status 0x%08X\n", v12);
  return v12;
}

```

## disassembly

```asm
0x18002bbe0  mov     [rsp-8+arg_0], rbx
0x18002bbe5  push    rbp
0x18002bbe6  push    rsi
0x18002bbe7  push    rdi
0x18002bbe8  push    r12
0x18002bbea  push    r13
0x18002bbec  push    r14
0x18002bbee  push    r15
0x18002bbf0  lea     rbp, [rsp-30h]
0x18002bbf5  sub     rsp, 130h
0x18002bbfc  mov     rax, cs:__security_cookie
0x18002bc03  xor     rax, rsp
0x18002bc06  mov     [rbp+60h+var_40], rax
0x18002bc0a  xor     r13d, r13d
0x18002bc0d  lea     rax, aScGmsa84a78b8c; "_SC_GMSA_{84A78B8C-56EE-465b-8496-FFB35"...
0x18002bc14  test    ecx, ecx
0x18002bc16  lea     r14, aScGmsaDpapiC68; "_SC_GMSA_DPAPI_{C6810348-4834-4a1e-817D"...
0x18002bc1d  mov     r12, r9
0x18002bc20  mov     r15, r8
0x18002bc23  cmovz   r14, rax
0x18002bc27  mov     rbx, rdx
0x18002bc2a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002bc2e  inc     rsi
0x18002bc31  cmp     [r14+rsi*2], r13w
0x18002bc36  jnz     short loc_18002BC2E
0x18002bc38  xorps   xmm0, xmm0
0x18002bc3b  mov     [rsp+160h+SourceString], r13
0x18002bc40  lea     rdx, aEnteringNetpge; "Entering NetpGetSecretName\n"
0x18002bc47  mov     [rsp+160h+phHash], r13
0x18002bc4c  mov     ecx, 40h ; '@'; unsigned int
0x18002bc51  mov     rdi, r13
0x18002bc54  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x18002bc59  movups  xmmword ptr [rsp+160h+UnicodeString.Length], xmm0
0x18002bc5e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002bc63  mov     r8d, 2; unsigned __int16
0x18002bc69  mov     [rsp+160h+pbSecret], rbx
0x18002bc6e  mov     r9, r15
0x18002bc71  lea     rdx, [rsp+160h+SourceString]; unsigned __int16 **
0x18002bc76  lea     ecx, [r8-1]; int
0x18002bc7a  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x18002bc7f  mov     r15, [rsp+160h+SourceString]
0x18002bc84  mov     ebx, eax
0x18002bc86  test    eax, eax
0x18002bc88  jns     short loc_18002BCA3
0x18002bc8a  lea     rdx, aNetpconcatenat; "NetpConcatenate failed 0x%08X\n"
0x18002bc91  mov     r8d, eax
0x18002bc94  mov     ecx, 40h ; '@'; unsigned int
0x18002bc99  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002bc9e  jmp     loc_18002BE34
0x18002bca3  mov     rdx, r15; SourceString
0x18002bca6  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x18002bcab  call    cs:__imp_RtlInitUnicodeString
0x18002bcb2  nop     dword ptr [rax+rax+00h]
0x18002bcb7  mov     r8b, 1; AllocateDestinationString
0x18002bcba  lea     rdx, [rsp+160h+DestinationString]; SourceString
0x18002bcbf  lea     rcx, [rsp+160h+UnicodeString]; DestinationString
0x18002bcc4  call    cs:__imp_RtlUpcaseUnicodeString
0x18002bccb  nop     dword ptr [rax+rax+00h]
0x18002bcd0  mov     ebx, eax
0x18002bcd2  test    eax, eax
0x18002bcd4  jns     short loc_18002BCDF
0x18002bcd6  lea     rdx, aRtlupcaseunico; "RtlUpcaseUnicodeString failed 0x%08X\n"
0x18002bcdd  jmp     short loc_18002BC91
0x18002bcdf  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hAlgorithm
0x18002bce6  lea     rdx, [rsp+160h+phHash]; phHash
0x18002bceb  mov     [rsp+160h+dwFlags], r13d; dwFlags
0x18002bcf0  xor     r9d, r9d; cbHashObject
0x18002bcf3  mov     [rsp+160h+cbSecret], r13d; cbSecret
0x18002bcf8  xor     r8d, r8d; pbHashObject
0x18002bcfb  mov     [rsp+160h+pbSecret], r13; pbSecret
0x18002bd00  call    cs:__imp_BCryptCreateHash
0x18002bd07  nop     dword ptr [rax+rax+00h]
0x18002bd0c  mov     ebx, eax
0x18002bd0e  test    eax, eax
0x18002bd10  jns     short loc_18002BD1E
0x18002bd12  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash failed 0x%08X\n"
0x18002bd19  jmp     loc_18002BC91
0x18002bd1e  movzx   r8d, [rsp+160h+UnicodeString.Length]; cbInput
0x18002bd24  xor     r9d, r9d; dwFlags
0x18002bd27  mov     rdx, [rsp+160h+UnicodeString.Buffer]; pbInput
0x18002bd2c  mov     rcx, [rsp+160h+phHash]; hHash
0x18002bd31  call    cs:__imp_BCryptHashData
0x18002bd38  nop     dword ptr [rax+rax+00h]
0x18002bd3d  mov     ebx, eax
0x18002bd3f  test    eax, eax
0x18002bd41  jns     short loc_18002BD4F
0x18002bd43  lea     rdx, aBcrypthashdata_0; "BCryptHashData failed 0x%08X\n"
0x18002bd4a  jmp     loc_18002BC91
0x18002bd4f  mov     rcx, [rsp+160h+phHash]; hHash
0x18002bd54  lea     rdx, [rsp+160h+pbOutput]; pbOutput
0x18002bd59  xor     r9d, r9d; dwFlags
0x18002bd5c  lea     r8d, [r9+20h]; cbOutput
0x18002bd60  call    cs:__imp_BCryptFinishHash
0x18002bd67  nop     dword ptr [rax+rax+00h]
0x18002bd6c  mov     ebx, eax
0x18002bd6e  test    eax, eax
0x18002bd70  jns     short loc_18002BD7E
0x18002bd72  lea     rdx, aBcryptfinishha_0; "BCryptFinishHash failed 0x%08X\n"
0x18002bd79  jmp     loc_18002BC91
0x18002bd7e  mov     r9d, r13d
0x18002bd81  lea     r10, a0123456789abcd; "0123456789abcdef"
0x18002bd88  mov     eax, r9d
0x18002bd8b  lea     edx, [r9+r9]
0x18002bd8f  inc     r9d
0x18002bd92  lea     ecx, [rdx+1]
0x18002bd95  movzx   r8d, [rsp+rax+160h+pbOutput]
0x18002bd9b  mov     eax, r8d
0x18002bd9e  shr     r8, 4
0x18002bda2  and     eax, 0Fh
0x18002bda5  movzx   eax, word ptr [r10+rax*2]
0x18002bdaa  mov     [rbp+rdx*2+60h+var_D0], ax
0x18002bdaf  movzx   eax, word ptr [r10+r8*2]
0x18002bdb4  mov     [rbp+rcx*2+60h+var_D0], ax
0x18002bdb9  cmp     r9d, 20h ; ' '
0x18002bdbd  jb      short loc_18002BD88
0x18002bdbf  lea     eax, [rsi+41h]
0x18002bdc2  mov     [rbp+60h+var_50], r13w
0x18002bdc7  lea     rdx, [rax+rax]; uBytes
0x18002bdcb  mov     ebx, eax
0x18002bdcd  mov     ecx, 40h ; '@'; uFlags
0x18002bdd2  call    cs:__imp_LocalAlloc
0x18002bdd9  nop     dword ptr [rax+rax+00h]
0x18002bdde  mov     rdi, rax
0x18002bde1  test    rax, rax
0x18002bde4  jnz     short loc_18002BDFA
0x18002bde6  mov     ebx, 0C0000017h
0x18002bdeb  lea     rdx, aLocalallocFail; "LocalAlloc failed 0x%08X\n"
0x18002bdf2  mov     r8d, ebx
0x18002bdf5  jmp     loc_18002BC94
0x18002bdfa  lea     rax, [rbp+60h+var_D0]
0x18002bdfe  mov     r9, r14
0x18002be01  lea     r8, aWsWs; "%ws%ws"
0x18002be08  mov     [rsp+160h+pbSecret], rax
0x18002be0d  mov     rdx, rbx; unsigned __int64
0x18002be10  mov     rcx, rdi; unsigned __int16 *
0x18002be13  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002be18  mov     ebx, eax
0x18002be1a  test    eax, eax
0x18002be1c  jns     short loc_18002BE2A
0x18002be1e  lea     rdx, aRtlstringcchpr_0; "RtlStringCchPrintfW failed 0x%08X\n"
0x18002be25  jmp     loc_18002BC91
0x18002be2a  mov     [r12], rdi
0x18002be2e  mov     ebx, r13d
0x18002be31  mov     rdi, r13
0x18002be34  cmp     [rsp+160h+UnicodeString.Buffer], r13
0x18002be39  jz      short loc_18002BE4C
0x18002be3b  lea     rcx, [rsp+160h+UnicodeString]; UnicodeString
0x18002be40  call    cs:__imp_RtlFreeUnicodeString
0x18002be47  nop     dword ptr [rax+rax+00h]
0x18002be4c  test    rdi, rdi
0x18002be4f  jz      short loc_18002BE60
0x18002be51  mov     rcx, rdi; hMem
0x18002be54  call    cs:__imp_LocalFree
0x18002be5b  nop     dword ptr [rax+rax+00h]
0x18002be60  test    r15, r15
0x18002be63  jz      short loc_18002BE74
0x18002be65  mov     rcx, r15; hMem
0x18002be68  call    cs:__imp_LocalFree
0x18002be6f  nop     dword ptr [rax+rax+00h]
0x18002be74  mov     rcx, [rsp+160h+phHash]; hHash
0x18002be79  test    rcx, rcx
0x18002be7c  jz      short loc_18002BE8A
0x18002be7e  call    cs:__imp_BCryptDestroyHash
0x18002be85  nop     dword ptr [rax+rax+00h]
0x18002be8a  mov     r8d, ebx
0x18002be8d  lea     rdx, aExitingNetpget; "Exiting NetpGetSecretName with Status 0"...
0x18002be94  mov     ecx, 40h ; '@'; unsigned int
0x18002be99  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002be9e  mov     eax, ebx
0x18002bea0  mov     rcx, [rbp+60h+var_40]
0x18002bea4  xor     rcx, rsp; StackCookie
0x18002bea7  call    __security_check_cookie
0x18002beac  mov     rbx, [rsp+160h+arg_0]
0x18002beb4  add     rsp, 130h
0x18002bebb  pop     r15
0x18002bebd  pop     r14
0x18002bebf  pop     r13
0x18002bec1  pop     r12
0x18002bec3  pop     rdi
0x18002bec4  pop     rsi
0x18002bec5  pop     rbp
0x18002bec6  retn
```
