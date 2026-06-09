# KeyProtRouter_GetSettings

- ea: `0x18000382c`
- end: `0x180003a47`
- name: `KeyProtRouter_GetSettings`
- size: `539`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180003150`
- `0x180003460`
- `0x180006090`

## callees

- `0x180001e78`
- `0x18000382c`
- `0x180009cd0`
- `0x18000d02c`
- `0x18000e120`
- `0x180015490`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x180003942`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x180003942`
- `ntdll!RtlFreeAnsiString` at `0x1800039f1`
- `ntdll!RtlFreeAnsiString` at `0x1800039f1`
- `ntdll!RtlInitUnicodeString` at `0x18000392f`
- `ntdll!RtlInitUnicodeString` at `0x18000392f`
- `ntdll!RtlLeaveCriticalSection` at `0x180003903`
- `ntdll!RtlLeaveCriticalSection` at `0x180003903`
- `ntdll!RtlEnterCriticalSection` at `0x1800038a8`
- `ntdll!RtlEnterCriticalSection` at `0x1800038a8`
- `NTASN1!__imp_ASN1_FindOidInfo` at `0x18000396e`
- `NTASN1!__imp_ASN1_FindOidInfo` at `0x1800039e2`
- `NTASN1!__imp_ASN1_FindOidInfo` at `0x18000396e`
- `NTASN1!__imp_ASN1_FindOidInfo` at `0x1800039e2`

## string_xrefs

- `0x1800039ab`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`
- `0x180003a21`: `onecore\ds\security\cryptoapi\ncrypt\protect\ncryptprotect\reg.c`

## pseudocode

```c
__int64 __fastcall KeyProtRouter_GetSettings(__int64 *a1)
{
  int v1; // edi
  __int64 v3; // rbx
  const WCHAR *v4; // rcx
  unsigned int v5; // ebx
  _OWORD *v7; // rax
  int v8; // edx
  const WCHAR *v9; // rdx
  NTSTATUS v10; // eax
  unsigned int ProtectionDescriptor; // eax
  _STRING AnsiString; // [rsp+40h] [rbp-28h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-18h] BYREF

  v1 = 0;
  if ( !dword_18002AF50 )
    RegLoadSettings();
  v3 = qword_18002AF48;
  if ( !qword_18002AF48 )
  {
    RtlEnterCriticalSection(&g_csKeyProtectorLock);
    v3 = qword_18002AF48;
    v1 = 1;
    if ( !qword_18002AF48 )
    {
      v7 = (_OWORD *)SafeAllocaAllocateFromHeap(32);
      qword_18002AF48 = (__int64)v7;
      v3 = (__int64)v7;
      if ( !v7 )
      {
        v5 = -2146893810;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c",
            (unsigned int)"Status",
            14,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c",
            121);
        goto LABEL_15;
      }
      *v7 = 0;
      v7[1] = 0;
      *(_QWORD *)v7 = L"2.16.840.1.101.3.4.1.46";
    }
  }
  if ( !*(_QWORD *)(v3 + 8) )
  {
    v9 = *(const WCHAR **)v3;
    if ( *(_QWORD *)v3 )
    {
      if ( *v9 )
      {
        DestinationString = 0;
        AnsiString = 0;
        RtlInitUnicodeString(&DestinationString, v9);
        v10 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
        v3 = qword_18002AF48;
        if ( v10 >= 0 )
        {
          *(_QWORD *)(v3 + 8) = ASN1_FindOidInfo(AnsiString.Buffer, 2);
          RtlFreeAnsiString(&AnsiString);
          v3 = qword_18002AF48;
        }
      }
    }
    if ( !*(_QWORD *)(v3 + 8) )
    {
      *(_QWORD *)(v3 + 8) = ASN1_FindOidInfo("2.16.840.1.101.3.4.1.46", 2);
      v3 = qword_18002AF48;
    }
  }
  if ( *(_QWORD *)(v3 + 24) )
    goto LABEL_7;
  v4 = *(const WCHAR **)(v3 + 16);
  if ( !v4 || !*v4 )
    goto LABEL_7;
  ProtectionDescriptor = NCryptCreateProtectionDescriptor(v4, 0, (_QWORD *)(v3 + 24));
  v5 = ProtectionDescriptor;
  if ( !ProtectionDescriptor )
  {
    v3 = qword_18002AF48;
LABEL_7:
    *a1 = v3;
    v5 = 0;
    dword_18002AF50 = 1;
    goto LABEL_8;
  }
  DebugTraceError(
    ProtectionDescriptor,
    "Status",
    "onecore\\ds\\security\\cryptoapi\\ncrypt\\protect\\ncryptprotect\\reg.c",
    431);
LABEL_8:
  if ( v1 )
LABEL_15:
    RtlLeaveCriticalSection(&g_csKeyProtectorLock);
  return v5;
}

```

## disassembly

```asm
0x18000382c  mov     [rsp+arg_0], rbx
0x180003831  mov     [rsp+arg_8], rsi
0x180003836  push    rdi
0x180003837  sub     rsp, 60h
0x18000383b  mov     eax, cs:dword_18002AF50
0x180003841  xor     edi, edi
0x180003843  mov     rsi, rcx
0x180003846  test    eax, eax
0x180003848  jz      loc_180003984
0x18000384e  mov     rbx, cs:qword_18002AF48
0x180003855  test    rbx, rbx
0x180003858  jz      short loc_1800038A1
0x18000385a  cmp     qword ptr [rbx+8], 0
0x18000385f  jz      loc_18000390B
0x180003865  lea     r8, [rbx+18h]
0x180003869  cmp     qword ptr [r8], 0
0x18000386d  jnz     short loc_18000387C
0x18000386f  mov     rcx, [rbx+10h]; Src
0x180003873  test    rcx, rcx
0x180003876  jnz     loc_180003A03
0x18000387c  mov     [rsi], rbx
0x18000387f  xor     ebx, ebx
0x180003881  mov     cs:dword_18002AF50, 1
0x18000388b  test    edi, edi
0x18000388d  jnz     short loc_1800038FC
0x18000388f  mov     rsi, [rsp+68h+arg_8]
0x180003894  mov     eax, ebx
0x180003896  mov     rbx, [rsp+68h+arg_0]
0x18000389b  add     rsp, 60h
0x18000389f  pop     rdi
0x1800038a0  retn
0x1800038a1  lea     rcx, g_csKeyProtectorLock; CriticalSection
0x1800038a8  call    cs:__imp_RtlEnterCriticalSection
0x1800038ae  mov     rbx, cs:qword_18002AF48
0x1800038b5  mov     edi, 1
0x1800038ba  test    rbx, rbx
0x1800038bd  jnz     short loc_18000385A
0x1800038bf  lea     ecx, [rdi+1Fh]
0x1800038c2  call    SafeAllocaAllocateFromHeap
0x1800038c7  mov     cs:qword_18002AF48, rax
0x1800038ce  mov     rbx, rax
0x1800038d1  test    rax, rax
0x1800038d4  jnz     loc_18000398E
0x1800038da  mov     ebx, 8009000Eh
0x1800038df  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038e6  lea     rax, WPP_GLOBAL_Control
0x1800038ed  cmp     rcx, rax
0x1800038f0  jz      short loc_1800038FC
0x1800038f2  test    [rcx+1Ch], dil
0x1800038f6  jnz     loc_1800039A7
0x1800038fc  lea     rcx, g_csKeyProtectorLock; CriticalSection
0x180003903  call    cs:__imp_RtlLeaveCriticalSection
0x180003909  jmp     short loc_18000388F
0x18000390b  mov     rdx, [rbx]; SourceString
0x18000390e  test    rdx, rdx
0x180003911  jz      short loc_180003957
0x180003913  xor     eax, eax
0x180003915  cmp     ax, [rdx]
0x180003918  jz      short loc_180003957
0x18000391a  xorps   xmm0, xmm0
0x18000391d  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x180003922  xorps   xmm1, xmm1
0x180003925  movups  xmmword ptr [rsp+68h+DestinationString.Length], xmm0
0x18000392a  movups  xmmword ptr [rsp+68h+AnsiString.Length], xmm1
0x18000392f  call    cs:__imp_RtlInitUnicodeString
0x180003935  mov     r8b, 1; AllocateDestinationString
0x180003938  lea     rdx, [rsp+68h+DestinationString]; SourceString
0x18000393d  lea     rcx, [rsp+68h+AnsiString]; DestinationString
0x180003942  call    cs:__imp_RtlUnicodeStringToAnsiString
0x180003948  mov     rbx, cs:qword_18002AF48
0x18000394f  test    eax, eax
0x180003951  jns     loc_1800039D8
0x180003957  cmp     qword ptr [rbx+8], 0
0x18000395c  jnz     loc_180003865
0x180003962  mov     edx, 2
0x180003967  lea     rcx, a21684011013414_0; "2.16.840.1.101.3.4.1.46"
0x18000396e  call    cs:__imp_ASN1_FindOidInfo
0x180003974  mov     [rbx+8], rax
0x180003978  mov     rbx, cs:qword_18002AF48
0x18000397f  jmp     loc_180003865
0x180003984  call    _RegLoadSettings
0x180003989  jmp     loc_18000384E
0x18000398e  xorps   xmm0, xmm0
0x180003991  movups  xmmword ptr [rax], xmm0
0x180003994  movups  xmmword ptr [rax+10h], xmm0
0x180003998  lea     rax, a21684011013414_1; "2.16.840.1.101.3.4.1.46"
0x18000399f  mov     [rbx], rax
0x1800039a2  jmp     loc_18000385A
0x1800039a7  mov     rcx, [rcx+10h]
0x1800039ab  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800039b2  mov     [rsp+68h+var_38], 179h
0x1800039ba  lea     r9, aStatus; "Status"
0x1800039c1  mov     [rsp+68h+var_40], r8
0x1800039c6  mov     [rsp+68h+var_48], 8009000Eh
0x1800039ce  call    WPP_SF_sDsd
0x1800039d3  jmp     loc_1800038FC
0x1800039d8  mov     rcx, [rsp+68h+AnsiString.Buffer]
0x1800039dd  mov     edx, 2
0x1800039e2  call    cs:__imp_ASN1_FindOidInfo
0x1800039e8  lea     rcx, [rsp+68h+AnsiString]; AnsiString
0x1800039ed  mov     [rbx+8], rax
0x1800039f1  call    cs:__imp_RtlFreeAnsiString
0x1800039f7  mov     rbx, cs:qword_18002AF48
0x1800039fe  jmp     loc_180003957
0x180003a03  xor     eax, eax
0x180003a05  cmp     ax, [rcx]
0x180003a08  jz      loc_18000387C
0x180003a0e  xor     edx, edx
0x180003a10  call    NCryptCreateProtectionDescriptor
0x180003a15  mov     ebx, eax
0x180003a17  test    eax, eax
0x180003a19  jz      short loc_180003A3B
0x180003a1b  mov     r9d, 1AFh
0x180003a21  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003a28  lea     rdx, aStatus; "Status"
0x180003a2f  mov     ecx, eax
0x180003a31  call    DebugTraceError
0x180003a36  jmp     loc_18000388B
0x180003a3b  mov     rbx, cs:qword_18002AF48
0x180003a42  jmp     loc_18000387C
```
