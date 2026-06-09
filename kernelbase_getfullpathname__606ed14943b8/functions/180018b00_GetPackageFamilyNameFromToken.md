# GetPackageFamilyNameFromToken

- ea: `0x180018b00`
- end: `0x180018e12`
- name: `GetPackageFamilyNameFromToken`
- size: `786`
- prototype: `LONG __stdcall(HANDLE token, UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180003e18`
- `0x18000ec14`
- `0x1800f1fc8`

## callees

- `0x180018b00`
- `0x1800192d8`
- `0x18001930c`
- `0x1801369c9`
- `0x180194eb9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018c5f`
- `ntdll!RtlInitUnicodeString` at `0x180018c7d`
- `ntdll!RtlInitUnicodeString` at `0x180018c5f`
- `ntdll!RtlInitUnicodeString` at `0x180018c7d`
- `ntdll!wcschr` at `0x180018d25`
- `ntdll!wcschr` at `0x180018d25`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018dcb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d8e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180018dcb`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199d8e`
- `ntdll!NtQueryInformationToken` at `0x180018b6a`
- `ntdll!NtQueryInformationToken` at `0x180018c2c`
- `ntdll!NtQueryInformationToken` at `0x180018b6a`
- `ntdll!NtQueryInformationToken` at `0x180018c2c`
- `ntdll!RtlCompareUnicodeString` at `0x180018cb2`
- `ntdll!RtlCompareUnicodeString` at `0x180018cd1`
- `ntdll!RtlCompareUnicodeString` at `0x180018cb2`
- `ntdll!RtlCompareUnicodeString` at `0x180018cd1`
- `ntdll!RtlAllocateHeap` at `0x180018bf4`
- `ntdll!RtlAllocateHeap` at `0x180018bf4`

## pseudocode

```c
LONG __stdcall GetPackageFamilyNameFromToken(HANDLE token, UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)
{
  char v5; // r13
  NTSTATUS v6; // eax
  LONG v7; // ebx
  PVOID Heap; // rax
  PVOID v10; // rdi
  int v11; // eax
  char v12; // r12
  __int64 v13; // rbx
  char v14; // r15
  __int64 v15; // rax
  const UNICODE_STRING *v16; // r14
  UINT32 v17; // edi
  unsigned __int16 *v18; // rbx
  int v19; // r12d
  wchar_t *v20; // rax
  __int64 v21; // r15
  __int64 v22; // rax
  __int64 v23; // r13
  UINT32 v24; // r14d
  _WORD *v25; // rdi
  const void *v26; // rdx
  size_t v27; // rbx
  __int64 v28; // rax
  PVOID P[2]; // [rsp+30h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+A0h] [rbp+40h] BYREF
  void *v33; // [rsp+B0h] [rbp+50h]
  __int64 v34; // [rsp+B8h] [rbp+58h]

  v33 = packageFamilyName;
  if ( !token || !packageFamilyNameLength || *packageFamilyNameLength && !packageFamilyName )
    return 87;
  TokenInformationLength = 0;
  *(_OWORD *)P = 0;
  v5 = 0;
  v6 = NtQueryInformationToken(token, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v6 != -1073741789 )
  {
    if ( !v6 )
    {
      v7 = 1359;
      goto LABEL_10;
    }
    v7 = RtlNtStatusToDosErrorNoTeb(v6);
    goto LABEL_36;
  }
  v34 = 0;
  if ( is_mul_ok(TokenInformationLength, 0x10u) )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength);
    v10 = Heap;
    if ( Heap )
    {
      memset_0(Heap, 0, TokenInformationLength);
      v11 = NtQueryInformationToken(
              token,
              TokenSecurityAttributes,
              v10,
              TokenInformationLength,
              &TokenInformationLength);
      if ( v11 >= 0 )
      {
        if ( *((_DWORD *)v10 + 1) )
        {
          v12 = 1;
          DestinationString = 0;
          RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
          String1 = 0;
          RtlInitUnicodeString(&String1, L"WIN://PKG");
          v13 = 0;
          v14 = 1;
          while ( (unsigned int)v13 < *((_DWORD *)v10 + 1) )
          {
            v15 = *((_QWORD *)v10 + 1);
            v16 = (const UNICODE_STRING *)(v15 + 40 * v13);
            if ( v12 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v15 + 40 * v13), 1u) )
            {
              P[1] = (PVOID)v16;
              if ( !v14 )
              {
                P[0] = v10;
                AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                goto LABEL_33;
              }
              v12 = 0;
            }
            else if ( v14 && !RtlCompareUnicodeString(&String1, v16, 1u) )
            {
              if ( !v12 )
              {
                P[0] = v10;
                AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
                goto LABEL_28;
              }
              v5 = 1;
              v14 = 0;
            }
            v13 = (unsigned int)(v13 + 1);
          }
        }
        AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v10);
LABEL_9:
        v7 = 15700;
        goto LABEL_10;
      }
      v7 = RtlNtStatusToDosErrorNoTeb(v11);
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v10);
LABEL_36:
      if ( v7 )
      {
        if ( v7 != 1168 )
          goto LABEL_10;
      }
      else
      {
LABEL_33:
        if ( v5 )
        {
LABEL_28:
          v17 = *packageFamilyNameLength;
          v18 = (unsigned __int16 *)*((_QWORD *)P[1] + 4);
          v19 = *v18 >> 1;
          v20 = wcschr(*((const wchar_t **)v18 + 1), 0x5Fu);
          v21 = *((_QWORD *)v18 + 1);
          v22 = ((__int64)v20 - v21 + 2) >> 1;
          v23 = (unsigned int)(v22 + 13);
          v24 = v22 + 14;
          if ( v17 < (int)v22 + 14 )
          {
            v7 = 122;
          }
          else
          {
            v25 = v33;
            v26 = (const void *)*((_QWORD *)v18 + 1);
            v27 = (unsigned int)v22;
            memcpy_0(v33, v26, v27 * 2);
            v28 = (unsigned int)(v19 - 13);
            *(_OWORD *)&v25[v27] = *(_OWORD *)(v21 + 2 * v28);
            *(_OWORD *)&v25[v27 + 5] = *(_OWORD *)(v21 + 2 * v28 + 10);
            v25[v23] = 0;
            v7 = 0;
          }
          *packageFamilyNameLength = v24;
          goto LABEL_10;
        }
        ARI::ProcessToken::AutoSysAppId::Close((ARI::ProcessToken::AutoSysAppId *)P);
      }
      goto LABEL_9;
    }
  }
  AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
  v7 = 8;
LABEL_10:
  if ( P[0] )
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(P[0]);
  return v7;
}

```

## disassembly

```asm
0x180018b00  mov     [rsp-38h+arg_8], rbx
0x180018b05  mov     [rsp-38h+arg_10], r8
0x180018b0a  push    rbp
0x180018b0b  push    rsi
0x180018b0c  push    rdi
0x180018b0d  push    r12
0x180018b0f  push    r13
0x180018b11  push    r14
0x180018b13  push    r15
0x180018b15  mov     rbp, rsp
0x180018b18  sub     rsp, 60h
0x180018b1c  mov     rsi, rdx
0x180018b1f  mov     rbx, rcx
0x180018b22  test    rcx, rcx
0x180018b25  jz      loc_180018BDB
0x180018b2b  test    rdx, rdx
0x180018b2e  jz      loc_180018BDB
0x180018b34  cmp     dword ptr [rdx], 0
0x180018b37  jbe     short loc_180018B42
0x180018b39  test    r8, r8
0x180018b3c  jz      loc_180018BDB
0x180018b42  xor     r9d, r9d; TokenInformationLength
0x180018b45  mov     [rbp+TokenInformationLength], 0
0x180018b4c  xorps   xmm0, xmm0
0x180018b4f  lea     rax, [rbp+TokenInformationLength]
0x180018b53  xor     r8d, r8d; TokenInformation
0x180018b56  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180018b5b  movdqu  xmmword ptr [rbp+P], xmm0
0x180018b60  lea     r14d, [r9+27h]
0x180018b64  xor     r13b, r13b
0x180018b67  mov     edx, r14d; TokenInformationClass
0x180018b6a  call    cs:__imp_NtQueryInformationToken
0x180018b71  nop     dword ptr [rax+rax+00h]
0x180018b76  cmp     eax, 0C0000023h
0x180018b7b  jnz     loc_180018DF6
0x180018b81  mov     ecx, [rbp+TokenInformationLength]
0x180018b84  lea     eax, [r14-17h]
0x180018b88  mul     rcx
0x180018b8b  mov     [rbp+arg_18], 0
0x180018b93  test    rdx, rdx
0x180018b96  jz      short loc_180018BE2
0x180018b98  xor     ecx, ecx; P
0x180018b9a  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018b9f  mov     ebx, 8
0x180018ba4  jmp     short loc_180018BB3
0x180018ba6  mov     rcx, rdi; P
0x180018ba9  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018bae  mov     ebx, 3D54h
0x180018bb3  mov     rcx, [rbp+P]; P
0x180018bb7  test    rcx, rcx
0x180018bba  jnz     loc_180018D92
0x180018bc0  mov     eax, ebx
0x180018bc2  mov     rbx, [rsp+60h+arg_8]
0x180018bca  add     rsp, 60h
0x180018bce  pop     r15
0x180018bd0  pop     r14
0x180018bd2  pop     r13
0x180018bd4  pop     r12
0x180018bd6  pop     rdi
0x180018bd7  pop     rsi
0x180018bd8  pop     rbp
0x180018bd9  retn
0x180018bdb  mov     eax, 57h ; 'W'
0x180018be0  jmp     short loc_180018BC2
0x180018be2  mov     rcx, gs:60h
0x180018beb  mov     r8, rax; Size
0x180018bee  xor     edx, edx; Flags
0x180018bf0  mov     rcx, [rcx+30h]; HeapHandle
0x180018bf4  call    cs:__imp_RtlAllocateHeap
0x180018bfb  nop     dword ptr [rax+rax+00h]
0x180018c00  mov     rdi, rax
0x180018c03  test    rax, rax
0x180018c06  jz      short loc_180018B98
0x180018c08  mov     r8d, [rbp+TokenInformationLength]; Size
0x180018c0c  xor     edx, edx; Val
0x180018c0e  mov     rcx, rax; void *
0x180018c11  call    memset_0
0x180018c16  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180018c1a  lea     rax, [rbp+TokenInformationLength]
0x180018c1e  mov     r8, rdi; TokenInformation
0x180018c21  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180018c26  mov     edx, r14d; TokenInformationClass
0x180018c29  mov     rcx, rbx; TokenHandle
0x180018c2c  call    cs:__imp_NtQueryInformationToken
0x180018c33  nop     dword ptr [rax+rax+00h]
0x180018c38  test    eax, eax
0x180018c3a  js      loc_180018DC9
0x180018c40  cmp     dword ptr [rdi+4], 0
0x180018c44  jbe     loc_180018BA6
0x180018c4a  xorps   xmm0, xmm0
0x180018c4d  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180018c54  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018c58  mov     r12b, 1
0x180018c5b  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018c5f  call    cs:__imp_RtlInitUnicodeString
0x180018c66  nop     dword ptr [rax+rax+00h]
0x180018c6b  xorps   xmm0, xmm0
0x180018c6e  lea     rdx, aWinPkg; "WIN://PKG"
0x180018c75  lea     rcx, [rbp+String1]; DestinationString
0x180018c79  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180018c7d  call    cs:__imp_RtlInitUnicodeString
0x180018c84  nop     dword ptr [rax+rax+00h]
0x180018c89  xor     ebx, ebx
0x180018c8b  mov     r15b, r12b
0x180018c8e  cmp     ebx, [rdi+4]
0x180018c91  jnb     loc_180018BA6
0x180018c97  mov     rax, [rdi+8]
0x180018c9b  lea     rcx, [rbx+rbx*4]
0x180018c9f  lea     r14, [rax+rcx*8]
0x180018ca3  test    r12b, r12b
0x180018ca6  jz      short loc_180018CC2
0x180018ca8  mov     r8b, 1; CaseInsensitive
0x180018cab  lea     rcx, [rbp+DestinationString]; String1
0x180018caf  mov     rdx, r14; String2
0x180018cb2  call    cs:__imp_RtlCompareUnicodeString
0x180018cb9  nop     dword ptr [rax+rax+00h]
0x180018cbe  test    eax, eax
0x180018cc0  jz      short loc_180018CE5
0x180018cc2  test    r15b, r15b
0x180018cc5  jz      short loc_180018CE1
0x180018cc7  mov     r8b, 1; CaseInsensitive
0x180018cca  lea     rcx, [rbp+String1]; String1
0x180018cce  mov     rdx, r14; String2
0x180018cd1  call    cs:__imp_RtlCompareUnicodeString
0x180018cd8  nop     dword ptr [rax+rax+00h]
0x180018cdd  test    eax, eax
0x180018cdf  jz      short loc_180018CF7
0x180018ce1  inc     ebx
0x180018ce3  jmp     short loc_180018C8E
0x180018ce5  mov     [rbp+P+8], r14
0x180018ce9  test    r15b, r15b
0x180018cec  jz      loc_180018DA7
0x180018cf2  xor     r12b, r12b
0x180018cf5  jmp     short loc_180018CE1
0x180018cf7  test    r12b, r12b
0x180018cfa  jnz     loc_180018D9C
0x180018d00  xor     ecx, ecx; P
0x180018d02  mov     [rbp+P], rdi
0x180018d06  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018d0b  mov     rax, [rbp+P+8]
0x180018d0f  mov     edx, 5Fh ; '_'; Ch
0x180018d14  mov     edi, [rsi]
0x180018d16  mov     rbx, [rax+20h]
0x180018d1a  movzx   r12d, word ptr [rbx]
0x180018d1e  mov     rcx, [rbx+8]; Str
0x180018d22  shr     r12d, 1
0x180018d25  call    cs:__imp_wcschr
0x180018d2c  nop     dword ptr [rax+rax+00h]
0x180018d31  mov     r15, [rbx+8]
0x180018d35  add     rax, 2
0x180018d39  sub     rax, r15
0x180018d3c  sar     rax, 1
0x180018d3f  lea     r13d, [rax+0Dh]
0x180018d43  lea     r14d, [r13+1]
0x180018d47  cmp     edi, r14d
0x180018d4a  jb      loc_180018E08
0x180018d50  mov     rdi, [rbp+arg_10]
0x180018d54  mov     rdx, r15; Src
0x180018d57  mov     eax, eax
0x180018d59  mov     rcx, rdi; void *
0x180018d5c  lea     rbx, [rax+rax]
0x180018d60  mov     r8, rbx; Size
0x180018d63  call    memcpy_0
0x180018d68  lea     eax, [r12-0Dh]
0x180018d6d  movups  xmm0, xmmword ptr [r15+rax*2]
0x180018d72  movups  xmmword ptr [rbx+rdi], xmm0
0x180018d76  movups  xmm1, xmmword ptr [r15+rax*2+0Ah]
0x180018d7c  xor     eax, eax
0x180018d7e  movups  xmmword ptr [rbx+rdi+0Ah], xmm1
0x180018d83  mov     [rdi+r13*2], ax
0x180018d88  xor     ebx, ebx
0x180018d8a  mov     [rsi], r14d
0x180018d8d  jmp     loc_180018BB3
0x180018d92  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018d97  jmp     loc_180018BC0
0x180018d9c  mov     r13b, 1
0x180018d9f  xor     r15b, r15b
0x180018da2  jmp     loc_180018CE1
0x180018da7  xor     ecx, ecx; P
0x180018da9  mov     [rbp+P], rdi
0x180018dad  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018db2  test    r13b, r13b
0x180018db5  jnz     loc_180018D0B
0x180018dbb  lea     rcx, [rbp+P]; this
0x180018dbf  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180018dc4  jmp     loc_180018BAE
0x180018dc9  mov     ecx, eax; Status
0x180018dcb  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180018dd2  nop     dword ptr [rax+rax+00h]
0x180018dd7  mov     rcx, rdi; P
0x180018dda  mov     ebx, eax
0x180018ddc  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018de1  test    ebx, ebx
0x180018de3  jz      short loc_180018DB2
0x180018de5  cmp     ebx, 490h
0x180018deb  jz      loc_180018BAE
0x180018df1  jmp     loc_180018BB3
0x180018df6  test    eax, eax
0x180018df8  jnz     loc_180199D8C
0x180018dfe  mov     ebx, 54Fh
0x180018e03  jmp     loc_180018BB3
0x180018e08  mov     ebx, 7Ah ; 'z'
0x180018e0d  jmp     loc_180018D8A
0x180199d8c  mov     ecx, eax; Status
0x180199d8e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180199d95  nop     dword ptr [rax+rax+00h]
0x180199d9a  mov     ebx, eax
0x180199d9c  jmp     loc_180018DE1
```
