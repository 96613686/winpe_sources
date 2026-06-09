# ARI::ProcessToken::AutoSysAppId::OpenIfPackaged(void *)

- ea: `0x180018e18`
- end: `0x18001906a`
- name: `?OpenIfPackaged@AutoSysAppId@ProcessToken@ARI@@QEAAJPEAX@Z`
- size: `594`
- prototype: `__int64 __fastcall(ARI::ProcessToken::AutoSysAppId *__hidden this, HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019350`
- `0x180056f80`

## callees

- `0x180018e18`
- `0x1800192d8`
- `0x18001930c`
- `0x1801369c9`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x180018f33`
- `ntdll!RtlInitUnicodeString` at `0x180018f51`
- `ntdll!RtlInitUnicodeString` at `0x180018f33`
- `ntdll!RtlInitUnicodeString` at `0x180018f51`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019038`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199da4`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180019038`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180199da4`
- `ntdll!NtQueryInformationToken` at `0x180018e61`
- `ntdll!NtQueryInformationToken` at `0x180018f00`
- `ntdll!NtQueryInformationToken` at `0x180018e61`
- `ntdll!NtQueryInformationToken` at `0x180018f00`
- `ntdll!RtlCompareUnicodeString` at `0x180018f85`
- `ntdll!RtlCompareUnicodeString` at `0x180018fa4`
- `ntdll!RtlCompareUnicodeString` at `0x180018f85`
- `ntdll!RtlCompareUnicodeString` at `0x180018fa4`
- `ntdll!RtlAllocateHeap` at `0x180018ec8`
- `ntdll!RtlAllocateHeap` at `0x180018ec8`

## pseudocode

```c
__int64 __fastcall ARI::ProcessToken::AutoSysAppId::OpenIfPackaged(
        ARI::ProcessToken::AutoSysAppId *this,
        HANDLE TokenHandle)
{
  void *v4; // rcx
  NTSTATUS v5; // eax
  ULONG v6; // edi
  PVOID Heap; // rax
  PVOID v9; // rbx
  int v10; // eax
  char v11; // r13
  __int64 v12; // rdi
  char v13; // r12
  char v14; // r14
  __int64 v15; // rax
  const UNICODE_STRING *v16; // r15
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-20h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-10h] BYREF
  ULONG TokenInformationLength; // [rsp+90h] [rbp+40h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+50h]

  v4 = *(void **)this;
  if ( v4 )
  {
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v4);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
  }
  TokenInformationLength = 0;
  v5 = NtQueryInformationToken(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength);
  if ( v5 == -1073741789 )
  {
    v20 = 0;
    if ( !is_mul_ok(TokenInformationLength, 0x10u)
      || (Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 16LL * TokenInformationLength), (v9 = Heap) == 0) )
    {
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
      return 8;
    }
    memset_0(Heap, 0, TokenInformationLength);
    v10 = NtQueryInformationToken(
            TokenHandle,
            TokenSecurityAttributes,
            v9,
            TokenInformationLength,
            &TokenInformationLength);
    if ( v10 >= 0 )
    {
      if ( *((_DWORD *)v9 + 1) )
      {
        v11 = 1;
        DestinationString = 0;
        RtlInitUnicodeString(&DestinationString, L"WIN://SYSAPPID");
        String1 = 0;
        RtlInitUnicodeString(&String1, L"WIN://PKG");
        v12 = 0;
        v13 = 1;
        v14 = 0;
        while ( (unsigned int)v12 < *((_DWORD *)v9 + 1) )
        {
          v15 = *((_QWORD *)v9 + 1);
          v16 = (const UNICODE_STRING *)(v15 + 40 * v12);
          if ( v11 && !RtlCompareUnicodeString(&DestinationString, (PCUNICODE_STRING)(v15 + 40 * v12), 1u) )
          {
            *((_QWORD *)this + 1) = v16;
            if ( !v13 )
            {
              *(_QWORD *)this = v9;
              AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
              v6 = 0;
              goto LABEL_24;
            }
            v11 = 0;
          }
          else if ( v13 && !RtlCompareUnicodeString(&String1, v16, 1u) )
          {
            if ( !v11 )
            {
              *(_QWORD *)this = v9;
              AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(0);
              return 0;
            }
            v14 = 1;
            v13 = 0;
          }
          v12 = (unsigned int)(v12 + 1);
        }
      }
      AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v9);
      return 1168;
    }
    v6 = RtlNtStatusToDosErrorNoTeb(v10);
    AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(v9);
  }
  else if ( v5 )
  {
    v6 = RtlNtStatusToDosErrorNoTeb(v5);
  }
  else
  {
    v6 = 1359;
  }
  v14 = 0;
  if ( v6 )
    return v6;
LABEL_24:
  if ( v14 )
    return v6;
  ARI::ProcessToken::AutoSysAppId::Close(this);
  return 15700;
}

```

## disassembly

```asm
0x180018e18  mov     [rsp-38h+arg_8], rbx
0x180018e1d  push    rbp
0x180018e1e  push    rsi
0x180018e1f  push    rdi
0x180018e20  push    r12
0x180018e22  push    r13
0x180018e24  push    r14
0x180018e26  push    r15
0x180018e28  mov     rbp, rsp
0x180018e2b  sub     rsp, 50h
0x180018e2f  mov     rsi, rcx
0x180018e32  mov     rdi, rdx
0x180018e35  mov     rcx, [rcx]; P
0x180018e38  test    rcx, rcx
0x180018e3b  jnz     loc_180018FEE
0x180018e41  xor     r9d, r9d; TokenInformationLength
0x180018e44  mov     [rbp+TokenInformationLength], 0
0x180018e4b  lea     rax, [rbp+TokenInformationLength]
0x180018e4f  xor     r8d, r8d; TokenInformation
0x180018e52  mov     rcx, rdi; TokenHandle
0x180018e55  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180018e5a  lea     r14d, [r9+27h]
0x180018e5e  mov     edx, r14d; TokenInformationClass
0x180018e61  call    cs:__imp_NtQueryInformationToken
0x180018e68  nop     dword ptr [rax+rax+00h]
0x180018e6d  cmp     eax, 0C0000023h
0x180018e72  jnz     loc_18001905B
0x180018e78  mov     ecx, [rbp+TokenInformationLength]
0x180018e7b  lea     eax, [r14-17h]
0x180018e7f  mul     rcx
0x180018e82  mov     [rbp+arg_10], 0
0x180018e8a  test    rdx, rdx
0x180018e8d  jz      short loc_180018EB6
0x180018e8f  xor     ecx, ecx; P
0x180018e91  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018e96  mov     edi, 8
0x180018e9b  mov     eax, edi
0x180018e9d  mov     rbx, [rsp+50h+arg_8]
0x180018ea5  add     rsp, 50h
0x180018ea9  pop     r15
0x180018eab  pop     r14
0x180018ead  pop     r13
0x180018eaf  pop     r12
0x180018eb1  pop     rdi
0x180018eb2  pop     rsi
0x180018eb3  pop     rbp
0x180018eb4  retn
0x180018eb6  mov     rcx, gs:60h
0x180018ebf  mov     r8, rax; Size
0x180018ec2  xor     edx, edx; Flags
0x180018ec4  mov     rcx, [rcx+30h]; HeapHandle
0x180018ec8  call    cs:__imp_RtlAllocateHeap
0x180018ecf  nop     dword ptr [rax+rax+00h]
0x180018ed4  mov     rbx, rax
0x180018ed7  test    rax, rax
0x180018eda  jz      short loc_180018E8F
0x180018edc  mov     r8d, [rbp+TokenInformationLength]; Size
0x180018ee0  xor     edx, edx; Val
0x180018ee2  mov     rcx, rax; void *
0x180018ee5  call    memset_0
0x180018eea  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180018eee  lea     rax, [rbp+TokenInformationLength]
0x180018ef2  mov     r8, rbx; TokenInformation
0x180018ef5  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x180018efa  mov     edx, r14d; TokenInformationClass
0x180018efd  mov     rcx, rdi; TokenHandle
0x180018f00  call    cs:__imp_NtQueryInformationToken
0x180018f07  nop     dword ptr [rax+rax+00h]
0x180018f0c  test    eax, eax
0x180018f0e  js      loc_180019036
0x180018f14  cmp     dword ptr [rbx+4], 0
0x180018f18  jbe     loc_180018FB8
0x180018f1e  xorps   xmm0, xmm0
0x180018f21  lea     rdx, SourceString; "WIN://SYSAPPID"
0x180018f28  lea     rcx, [rbp+DestinationString]; DestinationString
0x180018f2c  mov     r13b, 1
0x180018f2f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180018f33  call    cs:__imp_RtlInitUnicodeString
0x180018f3a  nop     dword ptr [rax+rax+00h]
0x180018f3f  xorps   xmm0, xmm0
0x180018f42  lea     rdx, aWinPkg; "WIN://PKG"
0x180018f49  lea     rcx, [rbp+String1]; DestinationString
0x180018f4d  movups  xmmword ptr [rbp+String1.Length], xmm0
0x180018f51  call    cs:__imp_RtlInitUnicodeString
0x180018f58  nop     dword ptr [rax+rax+00h]
0x180018f5d  xor     edi, edi
0x180018f5f  mov     r12b, r13b
0x180018f62  xor     r14b, r14b
0x180018f65  cmp     edi, [rbx+4]
0x180018f68  jnb     short loc_180018FB8
0x180018f6a  mov     rax, [rbx+8]
0x180018f6e  lea     rcx, [rdi+rdi*4]
0x180018f72  lea     r15, [rax+rcx*8]
0x180018f76  test    r13b, r13b
0x180018f79  jz      short loc_180018F95
0x180018f7b  mov     r8b, 1; CaseInsensitive
0x180018f7e  lea     rcx, [rbp+DestinationString]; String1
0x180018f82  mov     rdx, r15; String2
0x180018f85  call    cs:__imp_RtlCompareUnicodeString
0x180018f8c  nop     dword ptr [rax+rax+00h]
0x180018f91  test    eax, eax
0x180018f93  jz      short loc_180018FCA
0x180018f95  test    r12b, r12b
0x180018f98  jz      short loc_180018FB4
0x180018f9a  mov     r8b, 1; CaseInsensitive
0x180018f9d  lea     rcx, [rbp+String1]; String1
0x180018fa1  mov     rdx, r15; String2
0x180018fa4  call    cs:__imp_RtlCompareUnicodeString
0x180018fab  nop     dword ptr [rax+rax+00h]
0x180018fb0  test    eax, eax
0x180018fb2  jz      short loc_180018FD8
0x180018fb4  inc     edi
0x180018fb6  jmp     short loc_180018F65
0x180018fb8  mov     rcx, rbx; P
0x180018fbb  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018fc0  mov     edi, 490h
0x180018fc5  jmp     loc_180018E9B
0x180018fca  mov     [rsi+8], r15
0x180018fce  test    r12b, r12b
0x180018fd1  jz      short loc_18001900F
0x180018fd3  xor     r13b, r13b
0x180018fd6  jmp     short loc_180018FB4
0x180018fd8  test    r13b, r13b
0x180018fdb  jnz     short loc_180019007
0x180018fdd  xor     ecx, ecx; P
0x180018fdf  mov     [rsi], rbx
0x180018fe2  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018fe7  xor     edi, edi
0x180018fe9  jmp     loc_180018E9B
0x180018fee  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180018ff3  mov     qword ptr [rsi], 0
0x180018ffa  mov     qword ptr [rsi+8], 0
0x180019002  jmp     loc_180018E41
0x180019007  mov     r14b, 1
0x18001900a  xor     r12b, r12b
0x18001900d  jmp     short loc_180018FB4
0x18001900f  xor     ecx, ecx; P
0x180019011  mov     [rsi], rbx
0x180019014  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x180019019  xor     edi, edi
0x18001901b  test    r14b, r14b
0x18001901e  jnz     loc_180018E9B
0x180019024  mov     rcx, rsi; this
0x180019027  call    ?Close@AutoSysAppId@ProcessToken@ARI@@QEAAJXZ; ARI::ProcessToken::AutoSysAppId::Close(void)
0x18001902c  mov     eax, 3D54h
0x180019031  jmp     loc_180018E9D
0x180019036  mov     ecx, eax; Status
0x180019038  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x18001903f  nop     dword ptr [rax+rax+00h]
0x180019044  mov     rcx, rbx; P
0x180019047  mov     edi, eax
0x180019049  call    ??$AutoPtrRtlHeapDeallocate@Utag_STATE_ENUM_ITEM@@@@YAXPEAUtag_STATE_ENUM_ITEM@@@Z; AutoPtrRtlHeapDeallocate<tag_STATE_ENUM_ITEM>(tag_STATE_ENUM_ITEM *)
0x18001904e  xor     r14b, r14b
0x180019051  test    edi, edi
0x180019053  jnz     loc_180018E9B
0x180019059  jmp     short loc_18001901B
0x18001905b  test    eax, eax
0x18001905d  jnz     loc_180199DA2
0x180019063  mov     edi, 54Fh
0x180019068  jmp     short loc_18001904E
0x180199da2  mov     ecx, eax; Status
0x180199da4  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180199dab  nop     dword ptr [rax+rax+00h]
0x180199db0  mov     edi, eax
0x180199db2  jmp     loc_18001904E
```
