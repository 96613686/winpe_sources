# GetPackageFamilyNameFromToken

- ea: `0x180033800`
- end: `0x180033ad8`
- name: `GetPackageFamilyNameFromToken`
- size: `728`
- prototype: `LONG __stdcall(HANDLE token, UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800287a4`
- `0x180066d28`
- `0x1800e97e8`

## callees

- `0x180033800`
- `0x180033d08`
- `0x180033d34`
- `0x18012d119`
- `0x180188eb9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18003394c`
- `ntdll!RtlInitUnicodeString` at `0x180033964`
- `ntdll!RtlInitUnicodeString` at `0x18003394c`
- `ntdll!RtlInitUnicodeString` at `0x180033964`
- `ntdll!wcschr` at `0x1800339fa`
- `ntdll!wcschr` at `0x1800339fa`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180033a9a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7ba`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180033a9a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18018d7ba`
- `ntdll!NtQueryInformationToken` at `0x18003386a`
- `ntdll!NtQueryInformationToken` at `0x18003391f`
- `ntdll!NtQueryInformationToken` at `0x18003386a`
- `ntdll!NtQueryInformationToken` at `0x18003391f`
- `ntdll!RtlCompareUnicodeString` at `0x180033993`
- `ntdll!RtlCompareUnicodeString` at `0x1800339ac`
- `ntdll!RtlCompareUnicodeString` at `0x180033993`
- `ntdll!RtlCompareUnicodeString` at `0x1800339ac`
- `ntdll!RtlAllocateHeap` at `0x1800338ed`
- `ntdll!RtlAllocateHeap` at `0x1800338ed`

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
0x180033800  mov     [rsp-38h+arg_8], rbx
0x180033805  mov     [rsp-38h+arg_10], r8
0x18003380a  push    rbp
0x18003380b  push    rsi
0x18003380c  push    rdi
0x18003380d  push    r12
0x18003380f  push    r13
0x180033811  push    r14
0x180033813  push    r15
0x180033815  mov     rbp, rsp
0x180033818  sub     rsp, 60h
0x18003381c  mov     rsi, rdx
0x18003381f  mov     rbx, rcx
0x180033822  test    rcx, rcx
0x180033825  jz      loc_1800338D4
0x18003382b  test    rdx, rdx
0x18003382e  jz      loc_1800338D4
0x180033834  cmp     dword ptr [rdx], 0
0x180033837  jbe     short loc_180033842
0x180033839  test    r8, r8
0x18003383c  jz      loc_1800338D4
0x180033842  xor     r9d, r9d; TokenInformationLength
0x180033845  mov     [rbp+TokenInformationLength], 0
0x18003384c  xorps   xmm0, xmm0
0x18003384f  lea     rax, [rbp+TokenInformationLength]
0x180033853  xor     r8d, r8d; TokenInformation
0x180033856  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18003385b  movdqu  xmmword ptr [rbp+P], xmm0
0x180033860  lea     r14d, [r9+27h]
0x180033864  xor     r13b, r13b
0x180033867  mov     edx, r14d; TokenInformationClass
0x18003386a  call    cs:__imp_NtQueryInformationToken
0x180033870  cmp     eax, 0C0000023h
0x180033875  jnz     loc_180033ABF
0x18003387b  mov     ecx, [rbp+TokenInformationLength]
0x18003387e  lea     eax, [r14-17h]
0x180033882  mul     rcx
0x180033885  mov     [rbp+arg_18], 0
0x18003388d  test    rdx, rdx
0x180033890  jz      short loc_1800338DB
0x180033892  xor     ecx, ecx; P
0x180033894  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033899  mov     ebx, 8
0x18003389e  jmp     short loc_1800338AD
0x1800338a0  mov     rcx, rdi; P
0x1800338a3  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800338a8  mov     ebx, 3D54h
0x1800338ad  mov     rcx, [rbp+P]; P
0x1800338b1  test    rcx, rcx
0x1800338b4  jnz     loc_180033A61
0x1800338ba  mov     eax, ebx
0x1800338bc  mov     rbx, [rsp+60h+arg_8]
0x1800338c4  add     rsp, 60h
0x1800338c8  pop     r15
0x1800338ca  pop     r14
0x1800338cc  pop     r13
0x1800338ce  pop     r12
0x1800338d0  pop     rdi
0x1800338d1  pop     rsi
0x1800338d2  pop     rbp
0x1800338d3  retn
0x1800338d4  mov     eax, 57h ; 'W'
0x1800338d9  jmp     short loc_1800338BC
0x1800338db  mov     rcx, gs:60h
0x1800338e4  mov     r8, rax; Size
0x1800338e7  xor     edx, edx; Flags
0x1800338e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800338ed  call    cs:__imp_RtlAllocateHeap
0x1800338f3  mov     rdi, rax
0x1800338f6  test    rax, rax
0x1800338f9  jz      short loc_180033892
0x1800338fb  mov     r8d, [rbp+TokenInformationLength]; Size
0x1800338ff  xor     edx, edx; Val
0x180033901  mov     rcx, rax; void *
0x180033904  call    memset_0
0x180033909  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18003390d  lea     rax, [rbp+TokenInformationLength]
0x180033911  mov     r8, rdi; TokenInformation
0x180033914  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x180033919  mov     edx, r14d; TokenInformationClass
0x18003391c  mov     rcx, rbx; TokenHandle
0x18003391f  call    cs:__imp_NtQueryInformationToken
0x180033925  test    eax, eax
0x180033927  js      loc_180033A98
0x18003392d  cmp     dword ptr [rdi+4], 0
0x180033931  jbe     loc_1800338A0
0x180033937  xorps   xmm0, xmm0
0x18003393a  lea     rdx, aWinSysappid; "WIN://SYSAPPID"
0x180033941  lea     rcx, [rbp+DestinationString]; DestinationString
0x180033945  mov     r12b, 1
0x180033948  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003394c  call    cs:__imp_RtlInitUnicodeString
0x180033952  xorps   xmm0, xmm0
0x180033955  lea     rdx, aWinPkg; "WIN://PKG"
0x18003395c  lea     rcx, [rbp+String1]; DestinationString
0x180033960  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180033964  call    cs:__imp_RtlInitUnicodeString
0x18003396a  xor     ebx, ebx
0x18003396c  mov     r15b, r12b
0x18003396f  cmp     ebx, [rdi+4]
0x180033972  jnb     loc_1800338A0
0x180033978  mov     rax, [rdi+8]
0x18003397c  lea     rcx, [rbx+rbx*4]
0x180033980  lea     r14, [rax+rcx*8]
0x180033984  test    r12b, r12b
0x180033987  jz      short loc_18003399D
0x180033989  mov     r8b, 1; CaseInsensitive
0x18003398c  lea     rcx, [rbp+DestinationString]; String1
0x180033990  mov     rdx, r14; String2
0x180033993  call    cs:__imp_RtlCompareUnicodeString
0x180033999  test    eax, eax
0x18003399b  jz      short loc_1800339BA
0x18003399d  test    r15b, r15b
0x1800339a0  jz      short loc_1800339B6
0x1800339a2  mov     r8b, 1; CaseInsensitive
0x1800339a5  lea     rcx, [rbp+String1]; String1
0x1800339a9  mov     rdx, r14; String2
0x1800339ac  call    cs:__imp_RtlCompareUnicodeString
0x1800339b2  test    eax, eax
0x1800339b4  jz      short loc_1800339CC
0x1800339b6  inc     ebx
0x1800339b8  jmp     short loc_18003396F
0x1800339ba  mov     [rbp+P+8], r14
0x1800339be  test    r15b, r15b
0x1800339c1  jz      loc_180033A76
0x1800339c7  xor     r12b, r12b
0x1800339ca  jmp     short loc_1800339B6
0x1800339cc  test    r12b, r12b
0x1800339cf  jnz     loc_180033A6B
0x1800339d5  xor     ecx, ecx; P
0x1800339d7  mov     [rbp+P], rdi
0x1800339db  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x1800339e0  mov     rax, [rbp+P+8]
0x1800339e4  mov     edx, 5Fh ; '_'; Ch
0x1800339e9  mov     edi, [rsi]
0x1800339eb  mov     rbx, [rax+20h]
0x1800339ef  movzx   r12d, word ptr [rbx]
0x1800339f3  mov     rcx, [rbx+8]; Str
0x1800339f7  shr     r12d, 1
0x1800339fa  call    cs:__imp_wcschr
0x180033a00  mov     r15, [rbx+8]
0x180033a04  add     rax, 2
0x180033a08  sub     rax, r15
0x180033a0b  sar     rax, 1
0x180033a0e  lea     r13d, [rax+0Dh]
0x180033a12  lea     r14d, [r13+1]
0x180033a16  cmp     edi, r14d
0x180033a19  jb      loc_180033AD1
0x180033a1f  mov     rdi, [rbp+arg_10]
0x180033a23  mov     rdx, r15; Src
0x180033a26  mov     eax, eax
0x180033a28  mov     rcx, rdi; void *
0x180033a2b  lea     rbx, [rax+rax]
0x180033a2f  mov     r8, rbx; Size
0x180033a32  call    memcpy_0
0x180033a37  lea     eax, [r12-0Dh]
0x180033a3c  movups  xmm0, xmmword ptr [r15+rax*2]
0x180033a41  movups  xmmword ptr [rbx+rdi], xmm0
0x180033a45  movups  xmm1, xmmword ptr [r15+rax*2+0Ah]
0x180033a4b  xor     eax, eax
0x180033a4d  movups  xmmword ptr [rbx+rdi+0Ah], xmm1
0x180033a52  mov     [rdi+r13*2], ax
0x180033a57  xor     ebx, ebx
0x180033a59  mov     [rsi], r14d
0x180033a5c  jmp     loc_1800338AD
0x180033a61  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033a66  jmp     loc_1800338BA
0x180033a6b  mov     r13b, 1
0x180033a6e  xor     r15b, r15b
0x180033a71  jmp     loc_1800339B6
0x180033a76  xor     ecx, ecx; P
0x180033a78  mov     [rbp+P], rdi
0x180033a7c  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033a81  test    r13b, r13b
0x180033a84  jnz     loc_1800339E0
0x180033a8a  lea     rcx, [rbp+P]; this
0x180033a8e  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x180033a93  jmp     loc_1800338A8
0x180033a98  mov     ecx, eax; Status
0x180033a9a  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180033aa0  mov     rcx, rdi; P
0x180033aa3  mov     ebx, eax
0x180033aa5  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180033aaa  test    ebx, ebx
0x180033aac  jz      short loc_180033A81
0x180033aae  cmp     ebx, 490h
0x180033ab4  jz      loc_1800338A8
0x180033aba  jmp     loc_1800338AD
0x180033abf  test    eax, eax
0x180033ac1  jnz     loc_18018D7B8
0x180033ac7  mov     ebx, 54Fh
0x180033acc  jmp     loc_1800338AD
0x180033ad1  mov     ebx, 7Ah ; 'z'
0x180033ad6  jmp     short loc_180033A59
0x18018d7b8  mov     ecx, eax; Status
0x18018d7ba  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18018d7c0  mov     ebx, eax
0x18018d7c2  jmp     loc_180033AAA
```
