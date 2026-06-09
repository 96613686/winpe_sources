# NetpGetSecretName(int,ushort const *,ushort const *,ushort * *)

- ea: `0x18002a3b0`
- end: `0x18002a658`
- name: `?NetpGetSecretName@@YAJHPEBG0PEAPEAG@Z`
- size: `680`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180029c60`
- `0x180029e00`
- `0x18002aa50`

## callees

- `0x180007278`
- `0x18000e270`
- `0x18002a3b0`
- `0x18002ae5c`
- `0x1800615f0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a581`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18002a581`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a605`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a605`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002a48e`
- `ntdll!RtlUpcaseUnicodeString` at `0x18002a48e`
- `ntdll!RtlFreeUnicodeString` at `0x18002a5e9`
- `ntdll!RtlFreeUnicodeString` at `0x18002a5e9`
- `ntdll!RtlInitUnicodeString` at `0x18002a47b`
- `ntdll!RtlInitUnicodeString` at `0x18002a47b`
- `bcrypt!BCryptHashData` at `0x18002a4ec`
- `bcrypt!BCryptHashData` at `0x18002a4ec`
- `bcrypt!BCryptFinishHash` at `0x18002a515`
- `bcrypt!BCryptFinishHash` at `0x18002a515`
- `bcrypt!BCryptDestroyHash` at `0x18002a615`
- `bcrypt!BCryptDestroyHash` at `0x18002a615`
- `bcrypt!BCryptCreateHash` at `0x18002a4c4`
- `bcrypt!BCryptCreateHash` at `0x18002a4c4`

## string_xrefs

- `0x18002a4d0`: `BCryptCreateHash failed 0x%08X\n`

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
0x18002a3b0  mov     [rsp-8+arg_0], rbx
0x18002a3b5  push    rbp
0x18002a3b6  push    rsi
0x18002a3b7  push    rdi
0x18002a3b8  push    r12
0x18002a3ba  push    r13
0x18002a3bc  push    r14
0x18002a3be  push    r15
0x18002a3c0  lea     rbp, [rsp-30h]
0x18002a3c5  sub     rsp, 130h
0x18002a3cc  mov     rax, cs:__security_cookie
0x18002a3d3  xor     rax, rsp
0x18002a3d6  mov     [rbp+60h+var_40], rax
0x18002a3da  xor     r13d, r13d
0x18002a3dd  lea     rax, aScGmsa84a78b8c; "_SC_GMSA_{84A78B8C-56EE-465b-8496-FFB35"...
0x18002a3e4  test    ecx, ecx
0x18002a3e6  lea     r14, aScGmsaDpapiC68; "_SC_GMSA_DPAPI_{C6810348-4834-4a1e-817D"...
0x18002a3ed  mov     r12, r9
0x18002a3f0  mov     r15, r8
0x18002a3f3  cmovz   r14, rax
0x18002a3f7  mov     rbx, rdx
0x18002a3fa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a3fe  inc     rsi
0x18002a401  cmp     [r14+rsi*2], r13w
0x18002a406  jnz     short loc_18002A3FE
0x18002a408  xorps   xmm0, xmm0
0x18002a40b  mov     [rsp+160h+SourceString], r13
0x18002a410  lea     rdx, aEnteringNetpge; "Entering NetpGetSecretName\n"
0x18002a417  mov     [rsp+160h+phHash], r13
0x18002a41c  mov     ecx, 40h ; '@'; unsigned int
0x18002a421  mov     rdi, r13
0x18002a424  movups  xmmword ptr [rsp+160h+DestinationString.Length], xmm0
0x18002a429  movups  xmmword ptr [rsp+160h+UnicodeString.Length], xmm0
0x18002a42e  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002a433  mov     r8d, 2; unsigned __int16
0x18002a439  mov     [rsp+160h+pbSecret], rbx
0x18002a43e  mov     r9, r15
0x18002a441  lea     rdx, [rsp+160h+SourceString]; unsigned __int16 **
0x18002a446  lea     ecx, [r8-1]; int
0x18002a44a  call    ?NetpConcatenate@@YAJHPEAPEAGGZZ; NetpConcatenate(int,ushort * *,ushort,...)
0x18002a44f  mov     r15, [rsp+160h+SourceString]
0x18002a454  mov     ebx, eax
0x18002a456  test    eax, eax
0x18002a458  jns     short loc_18002A473
0x18002a45a  lea     rdx, aNetpconcatenat; "NetpConcatenate failed 0x%08X\n"
0x18002a461  mov     r8d, eax
0x18002a464  mov     ecx, 40h ; '@'; unsigned int
0x18002a469  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002a46e  jmp     loc_18002A5DD
0x18002a473  mov     rdx, r15; SourceString
0x18002a476  lea     rcx, [rsp+160h+DestinationString]; DestinationString
0x18002a47b  call    cs:__imp_RtlInitUnicodeString
0x18002a481  mov     r8b, 1; AllocateDestinationString
0x18002a484  lea     rdx, [rsp+160h+DestinationString]; SourceString
0x18002a489  lea     rcx, [rsp+160h+UnicodeString]; DestinationString
0x18002a48e  call    cs:__imp_RtlUpcaseUnicodeString
0x18002a494  mov     ebx, eax
0x18002a496  test    eax, eax
0x18002a498  jns     short loc_18002A4A3
0x18002a49a  lea     rdx, aRtlupcaseunico; "RtlUpcaseUnicodeString failed 0x%08X\n"
0x18002a4a1  jmp     short loc_18002A461
0x18002a4a3  mov     rcx, cs:?NlGlobalSha256Handle@@3PEAXEA; hAlgorithm
0x18002a4aa  lea     rdx, [rsp+160h+phHash]; phHash
0x18002a4af  mov     [rsp+160h+dwFlags], r13d; dwFlags
0x18002a4b4  xor     r9d, r9d; cbHashObject
0x18002a4b7  mov     [rsp+160h+cbSecret], r13d; cbSecret
0x18002a4bc  xor     r8d, r8d; pbHashObject
0x18002a4bf  mov     [rsp+160h+pbSecret], r13; pbSecret
0x18002a4c4  call    cs:__imp_BCryptCreateHash
0x18002a4ca  mov     ebx, eax
0x18002a4cc  test    eax, eax
0x18002a4ce  jns     short loc_18002A4D9
0x18002a4d0  lea     rdx, aBcryptcreateha_0; "BCryptCreateHash failed 0x%08X\n"
0x18002a4d7  jmp     short loc_18002A461
0x18002a4d9  movzx   r8d, [rsp+160h+UnicodeString.Length]; cbInput
0x18002a4df  xor     r9d, r9d; dwFlags
0x18002a4e2  mov     rdx, [rsp+160h+UnicodeString.Buffer]; pbInput
0x18002a4e7  mov     rcx, [rsp+160h+phHash]; hHash
0x18002a4ec  call    cs:__imp_BCryptHashData
0x18002a4f2  mov     ebx, eax
0x18002a4f4  test    eax, eax
0x18002a4f6  jns     short loc_18002A504
0x18002a4f8  lea     rdx, aBcrypthashdata_0; "BCryptHashData failed 0x%08X\n"
0x18002a4ff  jmp     loc_18002A461
0x18002a504  mov     rcx, [rsp+160h+phHash]; hHash
0x18002a509  lea     rdx, [rsp+160h+pbOutput]; pbOutput
0x18002a50e  xor     r9d, r9d; dwFlags
0x18002a511  lea     r8d, [r9+20h]; cbOutput
0x18002a515  call    cs:__imp_BCryptFinishHash
0x18002a51b  mov     ebx, eax
0x18002a51d  test    eax, eax
0x18002a51f  jns     short loc_18002A52D
0x18002a521  lea     rdx, aBcryptfinishha_0; "BCryptFinishHash failed 0x%08X\n"
0x18002a528  jmp     loc_18002A461
0x18002a52d  mov     r9d, r13d
0x18002a530  lea     r10, a0123456789abcd; "0123456789abcdef"
0x18002a537  mov     eax, r9d
0x18002a53a  lea     edx, [r9+r9]
0x18002a53e  inc     r9d
0x18002a541  lea     ecx, [rdx+1]
0x18002a544  movzx   r8d, [rsp+rax+160h+pbOutput]
0x18002a54a  mov     eax, r8d
0x18002a54d  shr     r8, 4
0x18002a551  and     eax, 0Fh
0x18002a554  movzx   eax, word ptr [r10+rax*2]
0x18002a559  mov     [rbp+rdx*2+60h+var_D0], ax
0x18002a55e  movzx   eax, word ptr [r10+r8*2]
0x18002a563  mov     [rbp+rcx*2+60h+var_D0], ax
0x18002a568  cmp     r9d, 20h ; ' '
0x18002a56c  jb      short loc_18002A537
0x18002a56e  lea     eax, [rsi+41h]
0x18002a571  mov     [rbp+60h+var_50], r13w
0x18002a576  lea     rdx, [rax+rax]; uBytes
0x18002a57a  mov     ebx, eax
0x18002a57c  mov     ecx, 40h ; '@'; uFlags
0x18002a581  call    cs:__imp_LocalAlloc
0x18002a587  mov     rdi, rax
0x18002a58a  test    rax, rax
0x18002a58d  jnz     short loc_18002A5A3
0x18002a58f  mov     ebx, 0C0000017h
0x18002a594  lea     rdx, aLocalallocFail; "LocalAlloc failed 0x%08X\n"
0x18002a59b  mov     r8d, ebx
0x18002a59e  jmp     loc_18002A464
0x18002a5a3  lea     rax, [rbp+60h+var_D0]
0x18002a5a7  mov     r9, r14
0x18002a5aa  lea     r8, aWsWs; "%ws%ws"
0x18002a5b1  mov     [rsp+160h+pbSecret], rax
0x18002a5b6  mov     rdx, rbx; unsigned __int64
0x18002a5b9  mov     rcx, rdi; unsigned __int16 *
0x18002a5bc  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a5c1  mov     ebx, eax
0x18002a5c3  test    eax, eax
0x18002a5c5  jns     short loc_18002A5D3
0x18002a5c7  lea     rdx, aRtlstringcchpr_0; "RtlStringCchPrintfW failed 0x%08X\n"
0x18002a5ce  jmp     loc_18002A461
0x18002a5d3  mov     [r12], rdi
0x18002a5d7  mov     ebx, r13d
0x18002a5da  mov     rdi, r13
0x18002a5dd  cmp     [rsp+160h+UnicodeString.Buffer], r13
0x18002a5e2  jz      short loc_18002A5EF
0x18002a5e4  lea     rcx, [rsp+160h+UnicodeString]; UnicodeString
0x18002a5e9  call    cs:__imp_RtlFreeUnicodeString
0x18002a5ef  test    rdi, rdi
0x18002a5f2  jz      short loc_18002A5FD
0x18002a5f4  mov     rcx, rdi; hMem
0x18002a5f7  call    cs:__imp_LocalFree
0x18002a5fd  test    r15, r15
0x18002a600  jz      short loc_18002A60B
0x18002a602  mov     rcx, r15; hMem
0x18002a605  call    cs:__imp_LocalFree
0x18002a60b  mov     rcx, [rsp+160h+phHash]; hHash
0x18002a610  test    rcx, rcx
0x18002a613  jz      short loc_18002A61B
0x18002a615  call    cs:__imp_BCryptDestroyHash
0x18002a61b  mov     r8d, ebx
0x18002a61e  lea     rdx, aExitingNetpget; "Exiting NetpGetSecretName with Status 0"...
0x18002a625  mov     ecx, 40h ; '@'; unsigned int
0x18002a62a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18002a62f  mov     eax, ebx
0x18002a631  mov     rcx, [rbp+60h+var_40]
0x18002a635  xor     rcx, rsp; StackCookie
0x18002a638  call    __security_check_cookie
0x18002a63d  mov     rbx, [rsp+160h+arg_0]
0x18002a645  add     rsp, 130h
0x18002a64c  pop     r15
0x18002a64e  pop     r14
0x18002a650  pop     r13
0x18002a652  pop     r12
0x18002a654  pop     rdi
0x18002a655  pop     rsi
0x18002a656  pop     rbp
0x18002a657  retn
```
